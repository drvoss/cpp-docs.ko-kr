---
title: '연습: 에이전트 기반 애플리케이션 만들기'
ms.date: 04/25/2019
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
ms.openlocfilehash: 3ece04811a75fba22db447875dc6ed08c22987b5
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142048"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>연습: 에이전트 기반 애플리케이션 만들기

이 항목에서는 기본 에이전트 기반 응용 프로그램을 만드는 방법에 대해 설명 합니다. 이 연습에서는 텍스트 파일에서 비동기적으로 데이터를 읽는 에이전트를 만들 수 있습니다. 응용 프로그램은 Adler-32 체크섬 알고리즘을 사용 하 여 해당 파일의 내용에 대 한 체크섬을 계산 합니다.

## <a name="prerequisites"></a>필수 구성 요소

이 연습을 완료 하려면 다음 항목을 이해 해야 합니다.

- [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)

- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)

- [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)

- [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)

## <a name="top"></a> 섹션

이 연습에서는 다음 작업을 수행 하는 방법을 보여 줍니다.

- [콘솔 애플리케이션 만들기](#createapplication)

- [File_reader 클래스 만들기](#createagentclass)

- [응용 프로그램에서 file_reader 클래스 사용](#useagentclass)

## <a name="createapplication"></a>콘솔 응용 프로그램 만들기

이 섹션에서는 프로그램에서 사용 하 C++ 는 헤더 파일을 참조 하는 콘솔 응용 프로그램을 만드는 방법을 보여 줍니다. 초기 단계는 사용 중인 Visual Studio 버전에 따라 달라 집니다. 이 페이지의 왼쪽 위에서 버전 선택기가 올바르게 설정 되어 있는지 확인 합니다.

::: moniker range="vs-2019"

### <a name="to-create-a-c-console-application-in-visual-studio-2019"></a>Visual Studio 2019 C++ 에서 콘솔 응용 프로그램을 만들려면

1. 주 메뉴에서 **파일** > **새** > **프로젝트** 를 선택 하 여 **새 프로젝트 만들기** 대화 상자를 엽니다.

1. 대화 상자 맨 위에서 **언어**를 **C++** 로 설정하고 **플랫폼**을 **Windows**로 설정하고 **프로젝트 형식**을 **콘솔**로 설정합니다. 

1. 필터링된 프로젝트 형식 목록에서 **콘솔 앱**을 선택한 후 **다음**을 선택합니다. 다음 페이지에서 프로젝트 이름으로 `BasicAgent`을 입력 하 고 원하는 경우 프로젝트 위치를 지정 합니다.

1. **만들기** 단추를 선택하여 프로젝트를 만듭니다.

1. **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다. **구성 속성** > **C/C++ ** > **미리** 컴파일된 헤더 > **미리 컴파일된 헤더** **만들기**를 선택 합니다.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-c-console-application-in-visual-studio-2017-and-earlier"></a>Visual Studio 2017 C++ 및 이전 버전에서 콘솔 응용 프로그램을 만들려면

1. **파일** 메뉴에서 **새로 만들기**를 클릭 한 다음 **프로젝트** 를 클릭 하 여 **새 프로젝트** 대화 상자를 표시 합니다.

1. **새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 ** C++ 시각적** 노드를 선택 하 고 **템플릿** 창에서 **Win32 콘솔 응용 프로그램** 을 선택 합니다. 프로젝트 이름 (예: `BasicAgent`)을 입력 한 다음 **확인** 을 클릭 하 여 **Win32 콘솔 응용 프로그램 마법사**를 표시 합니다.

1. **Win32 콘솔 응용 프로그램 마법사** 대화 상자에서 **마침**을 클릭 합니다.

::: moniker-end

1. *Pch .h* (Visual Studio 2017 및 이전 버전의*stdafx.h* )에서 다음 코드를 추가 합니다.

[!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]

   헤더 파일 에이전트에는 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md) 클래스의 기능이 포함 되어 있습니다.

1. 응용 프로그램을 빌드하고 실행 하 여 성공적으로 만들어졌는지 확인 합니다. 응용 프로그램을 빌드하려면 **빌드** 메뉴에서 **솔루션 빌드**를 클릭 합니다. 응용 프로그램이 성공적으로 빌드되면 **디버그** 메뉴에서 **디버깅 시작** 을 클릭 하 여 응용 프로그램을 실행 합니다.

[[맨 위로 이동](#top)]

## <a name="createagentclass"></a>File_reader 클래스 만들기

이 섹션에서는 `file_reader` 클래스를 만드는 방법을 보여 줍니다. 런타임은 각 에이전트가 자체 컨텍스트에서 작업을 수행 하도록 예약 합니다. 따라서 동기적으로 작업을 수행 하는 에이전트를 만들 수 있지만 다른 구성 요소와 비동기적으로 상호 작용 합니다. `file_reader` 클래스는 지정 된 입력 파일에서 데이터를 읽고 해당 파일의 데이터를 지정 된 대상 구성 요소로 보냅니다.

#### <a name="to-create-the-file_reader-class"></a>File_reader 클래스를 만들려면

1. 프로젝트에 새 C++ 헤더 파일을 추가 합니다. 이렇게 하려면 **솔루션 탐색기**의 **헤더 파일** 노드를 마우스 오른쪽 단추로 클릭 하 고 **추가**를 클릭 한 다음 **새 항목**을 클릭 합니다. **템플릿** 창에서 **헤더 파일 (.h)** 을 선택 합니다. **새 항목 추가** 대화 상자에서 **이름** 상자에 `file_reader.h`를 입력 한 다음 **추가**를 클릭 합니다.

1. File_reader에서 다음 코드를 추가 합니다.

[!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]

1. File_reader에서 `agent`에서 파생 되는 `file_reader` 라는 클래스를 만듭니다.

[!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]

1. 클래스의 `private` 섹션에 다음 데이터 멤버를 추가 합니다.

[!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]

   `_file_name` 멤버는 에이전트가 읽는 파일 이름입니다. `_target` 멤버는 에이전트가 파일의 콘텐츠를 기록 하는 [concurrency:: ITarget](../../parallel/concrt/reference/itarget-class.md) 개체입니다. `_error` 멤버는 에이전트 수명 동안 발생 하는 모든 오류를 저장 합니다.

1. `file_reader` 클래스의 `public` 섹션에 `file_reader` 생성자에 대 한 다음 코드를 추가 합니다.

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

   각 생성자 오버 로드는 `file_reader` 데이터 멤버를 설정 합니다. 두 번째 및 세 번째 생성자 오버 로드를 사용 하면 응용 프로그램에서 에이전트와 함께 특정 스케줄러를 사용할 수 있습니다. 첫 번째 오버 로드는 에이전트와 기본 스케줄러를 사용 합니다.

1. `file_reader` 클래스의 public 섹션에 `get_error` 메서드를 추가 합니다.

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

   `get_error` 메서드는 에이전트가 지속 되는 동안 발생 하는 모든 오류를 검색 합니다.

1. 클래스의 `protected` 섹션에서 [concurrency:: agent:: run](reference/agent-class.md#run) 메서드를 구현 합니다.

[!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]

`run` 메서드는 파일을 열고이 파일에서 데이터를 읽습니다. `run` 메서드는 예외 처리를 사용 하 여 파일을 처리 하는 동안 발생 하는 모든 오류를 캡처합니다.

   이 메서드는 파일에서 데이터를 읽을 때마다 [concurrency:: asend](reference/concurrency-namespace-functions.md#asend) 함수를 호출 하 여 해당 데이터를 대상 버퍼로 보냅니다. 이 메서드는 빈 문자열을 대상 버퍼로 보내 처리의 끝을 표시 합니다.

다음 예제에서는 file_reader의 전체 내용을 보여 줍니다.

[!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]

[[맨 위로 이동](#top)]

## <a name="useagentclass"></a>응용 프로그램에서 file_reader 클래스 사용

이 섹션에서는 `file_reader` 클래스를 사용 하 여 텍스트 파일의 내용을 읽는 방법을 보여 줍니다. 또한이 파일 데이터를 수신 하 고 Adler-32 체크섬을 계산 하는 [concurrency:: call](../../parallel/concrt/reference/call-class.md) 개체를 만드는 방법을 보여 줍니다.

#### <a name="to-use-the-file_reader-class-in-your-application"></a>응용 프로그램에서 file_reader 클래스를 사용 하려면

1. BasicAgent .cpp에서 다음 `#include` 문을 추가 합니다.

[!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]

1. BasicAgent .cpp에서 다음 `using` 지시문을 추가 합니다.

[!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]

1. `_tmain` 함수에서 처리의 끝을 알리는 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 개체를 만듭니다.

[!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]

1. 데이터를 받을 때 체크섬을 업데이트 하는 `call` 개체를 만듭니다.

[!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]

   이 `call` 개체는 또한 처리의 끝을 알리기 위해 빈 문자열을 받을 때 `event` 개체를 설정 합니다.

1. Test.txt 파일에서 읽는 `file_reader` 개체를 만들고 해당 파일의 내용을 `call` 개체에 씁니다.

[!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]

1. 에이전트를 시작 하 고 완료 될 때까지 기다립니다.

[!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]

1. `call` 개체가 모든 데이터를 수신 하 고 완료 될 때까지 기다립니다.

[!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]

1. 파일 판독기에서 오류를 확인 합니다. 오류가 발생 하지 않은 경우 최종 Adler-32 합계를 계산 하 고 합계를 콘솔에 출력 합니다.

[!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]

다음 예에서는 전체 BasicAgent .cpp 파일을 보여 줍니다.

[!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]

[[맨 위로 이동](#top)]

## <a name="sample-input"></a>샘플 입력

입력 파일 텍스트의 샘플 콘텐츠는 다음과 같습니다.

```Output
The quick brown fox
jumps
over the lazy dog
```

## <a name="sample-output"></a>샘플 출력

샘플 입력에 사용할 경우이 프로그램은 다음과 같은 출력을 생성 합니다.

```Output
Adler-32 sum is fefb0d75
```

## <a name="robust-programming"></a>강력한 프로그래밍

데이터 멤버에 대 한 동시 액세스를 방지 하려면 작업을 수행 하는 메서드를 클래스의 `protected` 또는 `private` 섹션에 추가 하는 것이 좋습니다. 에이전트와 메시지를 주고 받는 메서드만 클래스의 `public` 섹션으로 추가 합니다.

항상 [concurrency:: agent::d one](reference/agent-class.md#done) 메서드를 호출 하 여 에이전트를 완료 된 상태로 전환 합니다. 일반적으로 `run` 메서드에서 반환 하기 전에이 메서드를 호출 합니다.

## <a name="next-steps"></a>다음 단계

에이전트 기반 응용 프로그램의 또 다른 예를 보려면 [연습: join을 사용 하 여 교착 상태 방지](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)를 참조 하세요.

## <a name="see-also"></a>참고 항목

[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)<br/>
[동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)<br/>
[연습: 조인을 사용하여 교착 상태 방지](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)
