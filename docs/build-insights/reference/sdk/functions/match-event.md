---
title: MatchEvent
description: C++ BUILD Insights SDK matchevent 함수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f8022953e2f56f7c8917f161b094c50e0c5ecbdf
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334357"
---
# <a name="matchevent"></a>MatchEvent

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`MatchEvent` 함수를 사용 하 여 이벤트 유형 목록과 이벤트를 일치 시킬 수 있습니다. 이벤트가 목록의 형식과 일치 하면 추가 처리를 위해 처리기에 전달 됩니다.

## <a name="syntax"></a>구문

```cpp
template <
    typename        TEvent,
    typename...     TEvents,
    typename        TCallable,
    typename...     TExtraArgs>
bool MatchEvent(
    const RawEvent& event,
    TCallable&&     callable,
    TExtraArgs&&... extraArgs);
```

### <a name="parameters"></a>매개 변수

*Tevent*\
일치 시키려는 첫 번째 이벤트 유형입니다.

*Tevents*\
일치 시키려는 나머지 이벤트 유형입니다.

*Tcallable 가능*\
`operator()`를 지 원하는 형식입니다. 이 연산자에 전달 되는 인수에 대 한 자세한 내용은 *호출 가능* 매개 변수 설명을 참조 하세요.

*TExtraArgs*\
`MatchEvent`에 전달 된 추가 인수의 형식입니다.

*event*\
*Tevent* 및 *tevent*에서 설명한 이벤트 유형과 일치 하는지 비교할 이벤트입니다.

*호출 가능*\
`MatchEvent`는 *tevent* 및 *tevent*에서 설명 하는 이벤트 유형과 이벤트를 성공적으로 일치 한 후 호출 *가능* 호출을 호출 합니다. *호출 가능* 으로 전달 되는 첫 번째 인수는 일치 된 이벤트 형식의 r 값입니다. *ExtraArgs* 매개 변수 팩은 *호출 가능*의 나머지 매개 변수에서 완벽 하 게 전달 됩니다.  

*extraArgs*\
일치 하는 이벤트 형식과 함께 *호출할* 수 있도록 완벽 하 게 전달 되는 인수입니다.

### <a name="return-value"></a>반환 값

일치가 성공 했으면 **true** 이 고, 그렇지 않으면 **false** 인 **부울** 값입니다.

## <a name="remarks"></a>주의

*Tevent* 및 *tevent* 매개 변수에 사용할 이벤트 유형은 *캡처 클래스*목록에서 선택 합니다. 이벤트 목록과 일치 하는 데 사용할 수 있는 캡처 클래스는 [이벤트 표](../event-table.md)를 참조 하세요.

## <a name="example"></a>예제

```cpp
void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    auto& functionEvent = eventStack.Back(); // The Function event

    bool b1 = MatchEvent<Function, Thread>(
        functionEvent, [](auto matchedEvent){ /* Do something... */});

    bool b2 = MatchEvent<CodeGeneration, Thread>(
        functionEvent, [](auto matchedEvent){ /* Do something... */});


    // b1: true because the list of types contains Function, which is
    //     the type of the event we are trying to match.
    // b2: false because the list of types doesn't contain Function.
}
```

::: moniker-end
