---
title: 매치 이벤트
description: C++ 빌드 인사이트 SDK MatchEvent 함수 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 0c60653641c676716bcdd60865433773da79325f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323864"
---
# <a name="matchevent"></a>매치 이벤트

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `MatchEvent` 함수는 이벤트 유형 목록과 이벤트를 일치시도록 사용됩니다. 이벤트가 목록의 형식과 일치하면 추가 처리를 위해 처리기로 전달됩니다.

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

*T이벤트*\
일치하려는 첫 번째 이벤트 유형입니다.

*TEvents*\
일치하려는 나머지 이벤트 유형입니다.

*T콜 가능*\
을 지원하는 `operator()`형식입니다. 이 연산자에게 전달되는 인수에 대한 자세한 내용은 *호출 가능한* 매개 변수 설명을 참조하십시오.

*TExtraArgs*\
에 전달된 추가 인수의 `MatchEvent`형식입니다.

*이벤트*\
TEvent 및 *TEvents에서* 설명하는 이벤트 *TEvents*유형과 일치하는 이벤트입니다.

*호출할*\
`MatchEvent`TEvent 및 *TEvents에서*설명하는 이벤트 형식과 이벤트를 *TEvent* 성공적으로 일치시켜 *호출합니다.* *호출 가능한* 호출에 전달된 첫 번째 인수는 일치하는 이벤트 형식의 r 값입니다. *extraArgs* 매개 변수 팩은 *호출 가능한의*나머지 매개 변수에서 완벽하게 전달됩니다.  

*엑스트라 아르그*\
일치하는 이벤트 유형과 함께 *호출 가능한* 것으로 완벽하게 전달되는 인수입니다.

### <a name="return-value"></a>Return Value

일치가 성공한 경우 **true인** **bool** 값또는 그렇지 않으면 **false입니다.**

## <a name="remarks"></a>설명

*TEvent* 및 *TEvents* 매개 변수에 사용할 이벤트 유형은 *캡처 클래스*목록에서 선택됩니다. 이벤트 목록 및 이벤트 와 일치하는 데 사용할 수 있는 캡처 클래스는 [이벤트 테이블을](../event-table.md)참조하십시오.

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
