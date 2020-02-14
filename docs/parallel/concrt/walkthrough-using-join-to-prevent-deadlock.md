---
title: '연습: join을 사용하여 교착 상태 방지'
ms.date: 04/25/2019
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
ms.openlocfilehash: 4df83e944552fd6c0d2482efa72883d87cd45f8c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140650"
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>연습: join을 사용하여 교착 상태 방지

이 항목에서는 만찬 문제를 사용 하 여 [concurrency:: join](../../parallel/concrt/reference/join-class.md) 클래스를 사용 하 여 응용 프로그램의 교착 상태를 방지 하는 방법을 설명 합니다. 소프트웨어 애플리케이션에서 *교착 상태*는 두 개 이상의 프로세스가 각각 리소스를 보유하고 함께 다른 프로세스가 다른 리소스를 해제할 때까지 대기하는 경우 발생합니다.

식탁 (만찬) 문제는 여러 동시 프로세스 간에 리소스 집합을 공유할 때 발생할 수 있는 일반적인 문제 집합의 특정 예입니다.

## <a name="prerequisites"></a>필수 구성 요소

이 연습을 시작 하기 전에 다음 항목을 참조 하세요.

- [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)

- [연습: 에이전트 기반 애플리케이션 만들기](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)

- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)

- [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)

- [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)

## <a name="top"></a> 섹션

이 연습에는 다음과 같은 섹션이 있습니다.

- [식탁 만찬 문제](#problem)

- [Naive 구현](#deadlock)

- [Join을 사용 하 여 교착 상태 방지](#solution)

## <a name="problem"></a>식탁 만찬 문제

만찬 문제는 응용 프로그램에서 교착 상태가 발생 하는 방식을 보여 줍니다. 이 문제에서 5 개의 만찬가 둥근 테이블에 있습니다. 모든 philosopher는 사고와 시기 사이를 대체 합니다. 모든 philosopher는 인접 한 chopstick를 왼쪽에, 다른 chopstick는 오른쪽에 있는를 공유 해야 합니다. 다음 그림에서는이 레이아웃을 보여 줍니다.

![식탁 만찬 문제](../../parallel/concrt/media/dining_philosophersproblem.png "철학자들의 만찬 문제")

Philosopher는 두 가지 젓가락를 보유 해야 합니다. 모든 philosopher가 하나의 chopstick을 보유 하 고 다른 하나를 대기 하는 경우 philosopher는 물론 모든 결핍를 사용할 수 없습니다.

[[맨 위로 이동](#top)]

## <a name="deadlock"></a>Naive 구현

다음 예제에서는 naive의 식탁 구현을 보여 줍니다. [Concurrency:: agent](../../parallel/concrt/reference/agent-class.md)에서 파생 되는 `philosopher` 클래스를 사용 하면 각 philosopher 독립적으로 작동할 수 있습니다. 이 예제에서는 [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) 개체의 공유 배열을 사용 하 여 각 `philosopher` 개체에 젓가락 쌍에 대 한 단독 액세스를 제공 합니다.

구현을 그림에 연결 하기 위해 `philosopher` 클래스는 하나의 philosopher 나타냅니다. `int` 변수는 각 chopstick를 나타냅니다. `critical_section` 개체는 젓가락 rest 인 소유자 역할을 합니다. `run` 메서드는 philosopher의 수명을 시뮬레이션 합니다. `think` 메서드는 생각의 동작을 시뮬레이션 하 고 `eat` 메서드는 고의 행동을 시뮬레이션 합니다.

`philosopher` 개체는 `eat` 메서드를 호출 하기 전에 소유자의 젓가락 제거를 시뮬레이트하기 위해 `critical_section` 개체를 모두 잠급니다. `eat`호출 후 `philosopher` 개체는 `critical_section` 개체를 잠금 해제 된 상태로 다시 설정 하 여 소유자에 게 젓가락을 반환 합니다.

`pickup_chopsticks` 메서드는 교착 상태가 발생할 수 있는 위치를 보여 줍니다. 모든 `philosopher` 개체가 잠금 중 하나에 대 한 액세스 권한을 얻을 경우 다른 `philosopher` 개체에서 다른 잠금을 제어 하므로 `philosopher` 개체를 계속할 수 없습니다.

### <a name="example"></a>예제

[!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]

### <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사 하 여 Visual Studio 프로젝트에 붙여넣거나, `philosophers-deadlock.cpp` 이름이 지정 된 파일에 붙여 넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.

> **cl.exe/EHsc philosophers-deadlock**

[[맨 위로 이동](#top)]

## <a name="solution"></a>Join을 사용 하 여 교착 상태 방지

이 섹션에서는 메시지 버퍼 및 메시지 전달 함수를 사용 하 여 교착 상태의 가능성을 제거 하는 방법을 보여 줍니다.

이 예제를 앞의 예제와 연결 하기 위해 `philosopher` 클래스는 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) 개체 및 `join` 개체를 사용 하 여 각 `critical_section` 개체를 바꿉니다. `join` 개체는 philosopher에 젓가락를 제공 하는 중재자 역할을 합니다.

이 예제에서는 대상이 `unbounded_buffer` 개체에서 메시지를 받을 때 메시지 큐에서 메시지가 제거 되기 때문에 `unbounded_buffer` 클래스를 사용 합니다. 그러면 메시지를 포함 하는 `unbounded_buffer` 개체가 chopstick를 사용할 수 있음을 나타낼 수 있습니다. 메시지를 포함 하지 않는 `unbounded_buffer` 개체는 chopstick 사용 중임을 나타냅니다.

이 예에서는 non-greedy 조인이 non-greedy `join` 개체를 사용 합니다. non-greedy 조인은 두 `unbounded_buffer` 개체가 모두 메시지를 포함 하는 경우에만 각 `philosopher` 개체에 젓가락에 대 한 액세스를 제공 합니다. Greedy 조인은 사용할 수 있게 되는 즉시 메시지를 수락 하므로 greedy 조인은 교착 상태를 방지 하지 않습니다. 모든 non-greedy `join` 개체가 메시지 중 하나를 수신 하지만 다른 개체를 사용할 수 있게 될 때까지 계속 대기 하는 경우 교착 상태가 발생할 수 있습니다.

Greedy 및 non-greedy 조인에 대 한 자세한 내용과 다양 한 메시지 버퍼 유형 간의 차이점에 대 한 자세한 내용은 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)을 참조 하세요.

### <a name="to-prevent-deadlock-in-this-example"></a>이 예제에서 교착 상태를 방지 하려면

1. 예제에서 다음 코드를 제거 합니다.

[!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]

1. `_left` 형식 및 `philosopher` 클래스의 `_right` 데이터 멤버를 `unbounded_buffer`로 변경 합니다.

[!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]

1. `philosopher` 생성자를 수정 하 여 `unbounded_buffer` 개체를 매개 변수로 사용 합니다.

[!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]

1. Non-greedy `join` 개체를 사용 하 여 젓가락에 대 한 메시지 버퍼에서 메시지를 수신 하도록 `pickup_chopsticks` 메서드를 수정 합니다.

[!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]

1. 두 젓가락 모두에 대 한 메시지 버퍼로 메시지를 전송 하 여 젓가락에 대 한 액세스를 해제 하도록 `putdown_chopsticks` 메서드를 수정 합니다.

[!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]

1. `run` 메서드를 수정 하 여 `pickup_chopsticks` 메서드의 결과를 저장 하 고 해당 결과를 `putdown_chopsticks` 메서드로 전달 합니다.

[!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]

1. `wmain` 함수에서 `chopsticks` 변수의 선언을 각각 하나의 메시지를 포함 하는 `unbounded_buffer` 개체의 배열로 수정 합니다.

[!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]

### <a name="description"></a>설명

다음은 non-greedy `join` 개체를 사용 하 여 교착 상태 위험을 제거 하는 완료 된 예제를 보여 줍니다.

### <a name="example"></a>예제

[!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_9.cpp)]

이 예제의 결과는 다음과 같습니다.

```Output
aristotle ate 50 times.
descartes ate 50 times.
hobbes ate 50 times.
socrates ate 50 times.
plato ate 50 times.
```

### <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사 하 여 Visual Studio 프로젝트에 붙여넣거나, `philosophers-join.cpp` 이름이 지정 된 파일에 붙여 넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.

> **cl.exe/EHsc philosophers-join**

[[맨 위로 이동](#top)]

## <a name="see-also"></a>참고 항목

[동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)<br/>
[동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)
