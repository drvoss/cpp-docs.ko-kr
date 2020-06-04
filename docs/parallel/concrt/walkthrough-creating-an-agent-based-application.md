---
title: '연습: 에이전트 기반 애플리케이션 만들기'
ms.date: 04/25/2019
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
ms.openlocfilehash: 20197786e3d3c2d34d29af748c1cc073902cf70d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377451"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>연습: 에이전트 기반 애플리케이션 만들기

이 항목에서는 기본 에이전트 기반 응용 프로그램을 만드는 방법에 대해 설명합니다. 이 연습에서는 텍스트 파일에서 데이터를 비동기적으로 읽는 에이전트를 만들 수 있습니다. 응용 프로그램은 Adler-32 체크섬 알고리즘을 사용하여 해당 파일의 내용의 체크섬을 계산합니다.

## <a name="prerequisites"></a>사전 요구 사항

이 연습을 완료하려면 다음 항목을 이해해야 합니다.

- [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)

- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)

- [메시지 전달 기능](../../parallel/concrt/message-passing-functions.md)

- [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)

## <a name="sections"></a><a name="top"></a>섹션

이 연습에서는 다음 작업을 수행하는 방법을 보여 줍니다.

- [콘솔 애플리케이션 만들기](#createapplication)

- [file_reader 클래스 만들기](#createagentclass)

- [응용 프로그램에서 file_reader 클래스 사용](#useagentclass)

## <a name="creating-the-console-application"></a><a name="createapplication"></a>콘솔 응용 프로그램 만들기

이 섹션에서는 프로그램에서 사용할 헤더 파일을 참조하는 C++ 콘솔 응용 프로그램을 만드는 방법을 보여 주며 있습니다. 초기 단계는 사용 중인 Visual Studio 버전에 따라 다릅니다. 선호하는 버전의 Visual Studio에 대한 설명서를 보려면 **버전** 선택기 컨트롤을 사용합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker range="vs-2019"

### <a name="to-create-a-c-console-application-in-visual-studio-2019"></a>Visual Studio 2019에서 C++ 콘솔 응용 프로그램을 만들려면

1. 주 메뉴에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트 만들기** 대화 상자를 엽니다.

1. 대화 상자 맨 위에서 **언어**를 **C++** 로 설정하고 **플랫폼**을 **Windows**로 설정하고 **프로젝트 형식**을 **콘솔**로 설정합니다.

1. 필터링된 프로젝트 형식 목록에서 **콘솔 앱**을 선택한 후 **다음**을 선택합니다. 다음 페이지에서 프로젝트의 `BasicAgent` 이름으로 입력하고 원하는 경우 프로젝트 위치를 지정합니다.

1. **만들기** 단추를 선택하여 프로젝트를 만듭니다.

1. **솔루션 탐색기에서**프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **구성 속성** > **C/C++** > **미리 컴파일된 헤더에서** > **미리 컴파일된 헤더** **만들기를**선택합니다.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-c-console-application-in-visual-studio-2017-and-earlier"></a>Visual Studio 2017 및 이전 환경에서 C++ 콘솔 응용 프로그램을 만들려면

1. **파일** 메뉴에서 **새로**를 클릭한 다음 **프로젝트를** 클릭하여 **새 프로젝트** 대화 상자를 표시합니다.

1. 새 **프로젝트** 대화 상자에서 **프로젝트 유형** 창에서 **Visual C++** 노드를 선택한 다음 템플릿 창에서 **Win32 콘솔 응용 프로그램을** **선택합니다.** 예를 들어 `BasicAgent`프로젝트의 이름을 입력한 다음 **확인을** 클릭하여 **Win32 콘솔 응용 프로그램 마법사를**표시합니다.

1. **Win32 콘솔 응용 프로그램 마법사** 대화 상자에서 **완료를**클릭합니다.

::: moniker-end

1. *pch.h(Visual* Studio 2017 및 이전 의*stdafx.h)에서* 다음 코드를 추가합니다.

[!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]

   헤더 파일 agent.h 동시성의 기능을 [포함::agent](../../parallel/concrt/reference/agent-class.md) 클래스입니다.

1. 응용 프로그램을 빌드하고 실행하여 응용 프로그램을 성공적으로 만들었는지 확인합니다. 응용 프로그램을 빌드하려면 **빌드** 메뉴에서 **솔루션 빌드를**클릭합니다. 응용 프로그램이 성공적으로 빌드되면 **디버그** 메뉴에서 **디버깅 시작을** 클릭하여 응용 프로그램을 실행합니다.

【[맨 위](#top)】

## <a name="creating-the-file_reader-class"></a><a name="createagentclass"></a>file_reader 클래스 만들기

이 섹션에서는 클래스를 `file_reader` 만드는 방법을 보여 주며 있습니다. 런타임은 각 에이전트가 자체 컨텍스트에서 작업을 수행하도록 예약합니다. 따라서 작업을 동기적으로 수행하지만 다른 구성 요소와 비동기적으로 상호 작용하는 에이전트를 만들 수 있습니다. 클래스는 `file_reader` 지정된 입력 파일에서 데이터를 읽고 해당 파일의 데이터를 지정된 대상 구성 요소로 보냅니다.

#### <a name="to-create-the-file_reader-class"></a>file_reader 클래스를 만들려면

1. 프로젝트에 새 C++ 헤더 파일을 추가합니다. 이렇게 하려면 **솔루션 탐색기에서** **헤더 파일** 노드를 마우스 오른쪽 단추를 클릭하고 **추가를**클릭한 다음 **새 항목**을 클릭합니다. **템플릿** 창에서 **헤더 파일(.h)을 선택합니다.** 새 **항목 추가** 대화 상자에서 `file_reader.h` **이름** 상자를 입력한 다음 **에 추가를**클릭합니다.

1. file_reader.h에서 다음 코드를 추가합니다.

[!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]

1. file_reader.h에서 `agent`에서 파생되는 이름의 `file_reader` 클래스를 만듭니다.

[!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]

1. 클래스의 섹션에 다음 `private` 데이터 멤버를 추가합니다.

[!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]

   멤버는 `_file_name` 에이전트가 읽는 파일 이름입니다. 멤버는 `_target` [동시성::ITarget](../../parallel/concrt/reference/itarget-class.md) 에이전트가 파일의 내용을 쓰는 개체입니다. 멤버는 `_error` 에이전트의 수명 동안 발생하는 모든 오류를 보유합니다.

1. 생성자의 다음 코드를 클래스의 섹션에 `public` 추가합니다. `file_reader` `file_reader`

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

   각 생성자 오버로드는 데이터 멤버를 설정합니다. `file_reader` 두 번째 및 세 번째 생성자 오버로드를 사용하면 응용 프로그램에서 에이전트와 함께 특정 스케줄러를 사용할 수 있습니다. 첫 번째 오버로드는 에이전트와 함께 기본 스케줄러를 사용합니다.

1. 메서드를 `get_error` 클래스의 공용 섹션에 추가합니다. `file_reader`

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

   메서드는 `get_error` 에이전트의 수명 동안 발생하는 모든 오류를 검색합니다.

1. [동시성을 구현:::에이전트::실행](reference/agent-class.md#run) 메서드 `protected` 클래스의 섹션에서 합니다.

[!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]

메서드는 `run` 파일을 열고 데이터를 읽습니다. 이 `run` 메서드는 예외 처리를 사용하여 파일 처리 중에 발생하는 오류를 캡처합니다.

   이 메서드가 파일에서 데이터를 읽을 때마다 [동시성::asend](reference/concurrency-namespace-functions.md#asend) 함수를 호출하여 해당 데이터를 대상 버퍼로 보냅니다. 처리 종료를 나타내기 위해 빈 문자열을 대상 버퍼로 보냅니다.

다음 예제에서는 file_reader.h의 전체 내용을 보여 주다.

[!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]

【[맨 위](#top)】

## <a name="using-the-file_reader-class-in-the-application"></a><a name="useagentclass"></a>응용 프로그램에서 file_reader 클래스 사용

이 섹션에서는 클래스를 `file_reader` 사용하여 텍스트 파일의 내용을 읽는 방법을 보여 주며 있습니다. 또한 이 파일 데이터를 수신하고 Adler-32 체크섬을 계산하는 [동시성::call](../../parallel/concrt/reference/call-class.md) 개체를 만드는 방법도 보여 옵니다.

#### <a name="to-use-the-file_reader-class-in-your-application"></a>응용 프로그램에서 file_reader 클래스를 사용하려면

1. BasicAgent.cpp에서 다음 `#include` 문을 추가합니다.

[!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]

1. BasicAgent.cpp에서 다음 `using` 지시문을 추가합니다.

[!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]

1. 함수에서 `_tmain` 처리 종료를 알리는 [동시성::event](../../parallel/concrt/reference/event-class.md) 개체를 만듭니다.

[!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]

1. 데이터를 `call` 수신할 때 체크섬을 업데이트하는 개체를 만듭니다.

[!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]

   이 `call` 개체는 `event` 처리 종료를 알리기 위해 빈 문자열을 수신할 때도 개체를 설정합니다.

1. `file_reader` 파일 test.txt에서 읽고 해당 파일의 내용을 `call` 개체에 쓰는 개체를 만듭니다.

[!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]

1. 에이전트를 시작하고 완료될 때까지 기다립니다.

[!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]

1. 개체가 `call` 모든 데이터를 수신하고 완료될 때까지 기다립니다.

[!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]

1. 파일 판독기에서 오류가 있는지 확인합니다. 오류가 발생하지 않으면 최종 Adler-32 합계를 계산하고 합계를 콘솔에 인쇄합니다.

[!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]

다음 예제에서는 전체 BasicAgent.cpp 파일을 보여 주실 수 있습니다.

[!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]

【[맨 위](#top)】

## <a name="sample-input"></a>샘플 입력

다음은 입력 파일 text.txt의 샘플 내용입니다.

```Output
The quick brown fox
jumps
over the lazy dog
```

## <a name="sample-output"></a>샘플 출력

샘플 입력과 함께 사용하면 이 프로그램은 다음과 같은 출력을 생성합니다.

```Output
Adler-32 sum is fefb0d75
```

## <a name="robust-programming"></a>강력한 프로그래밍

데이터 멤버에 대한 동시 액세스를 방지하려면 작업을 수행하는 메서드를 `protected` `private` 클래스의 또는 섹션에 추가하는 것이 좋습니다. 에이전트에서 메시지를 보내거나 받는 메서드만 클래스의 `public` 섹션으로 추가합니다.

항상 [동시성:::agent::d one](reference/agent-class.md#done) 메서드를 호출하여 에이전트를 완료된 상태로 이동합니다. 일반적으로 메서드에서 반환 하기 전에이 메서드를 호출 합니다. `run`

## <a name="next-steps"></a>다음 단계

에이전트 기반 응용 프로그램의 또 다른 예는 [연습: 조인을 사용하여 교착 상태를 방지합니다.](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)

## <a name="see-also"></a>참고 항목

[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[메시지 전달 기능](../../parallel/concrt/message-passing-functions.md)<br/>
[동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)<br/>
[연습: join을 사용하여 교착 상태 방지](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)
