---
title: 매치이벤트스택
description: C++ 빌드 인사이트 SDK MatchEventStack 함수 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a223d420e8c48667fbd1c6569f02d0486f597b5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323869"
---
# <a name="matcheventstack"></a>매치이벤트스택

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `MatchEventStack` 함수는 특정 이벤트 계층 구조와 이벤트 스택을 일치시도록 사용됩니다. 일치하는 계층구조는 추가 처리를 위해 처리기로 전달됩니다. 이벤트, 이벤트 스택 및 계층구조에 대한 자세한 내용은 [이벤트 테이블을](../event-table.md)참조하십시오.

## <a name="syntax"></a>구문

```cpp
template <
    typename          TEvent,
    typename...       TEvents,
    typename          TCallable,
    typename...       TExtraArgs>
bool MatchEventStack(
    const EventStack& eventStack,
    TCallable&&       callable,
    TExtraArgs&&...   extraArgs);
```

### <a name="parameters"></a>매개 변수

*T이벤트*\
이벤트 스택에서 일치할 장녀 부모의 유형입니다.

*TEvents*\
이벤트 스택에서 일치하려는 나머지 형식입니다.

*T콜 가능*\
을 지원하는 `operator()`형식입니다. 이 연산자에게 전달되는 인수에 대한 자세한 내용은 *호출 가능한* 매개 변수 설명을 참조하십시오.

*TExtraArgs*\
에 전달된 추가 인수의 `MatchEventStack`형식입니다.

*이벤트 스택*\
TEvent 및 *TEvents에서* 설명하는 이벤트 형식 *TEvents*계층 구조와 일치하는 이벤트 스택입니다.

*호출할*\
이벤트 스택을 TEvent 및 `MatchEventStack` *TEvents에서* 설명하는 *TEvents*이벤트 형식 계층 구조와 성공적으로 일치하면 *호출 가능*합니다. 이벤트 계층 구조의 각 형식에 대해 *호출 가능한* 하나의 r-value 인수를 전달합니다. *extraArgs* 매개 변수 팩은 *호출 가능한의*나머지 매개 변수에서 완벽하게 전달됩니다.

*엑스트라 아르그*\
일치하는 이벤트 유형과 함께 *호출 가능한* 것으로 완벽하게 전달되는 인수입니다.

### <a name="return-value"></a>Return Value

일치가 성공한 경우 **true인** **bool** 값 또는 그렇지 않으면 **false입니다.**

## <a name="remarks"></a>설명

*eventStack의* 마지막 이벤트는 항상 연결 된 \[ *TEvent*, *TEvents의* 마지막 항목에 대 한 일치... \] 유형 목록. 다른 모든 *TEvent* 및 *TEvents* 항목은 동일한 순서로 제공되는 경우 마지막 항목을 제외한 *eventStack의* 모든 위치와 일치할 수 있습니다.

*TEvent* 및 *TEvents* 매개 변수에 사용할 이벤트 유형은 *캡처 클래스*목록에서 선택됩니다. 이벤트 목록 및 이벤트 와 일치하는 데 사용할 수 있는 캡처 클래스는 [이벤트 테이블을](../event-table.md)참조하십시오.

## <a name="example"></a>예제

```cpp
void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    bool b1 = MatchEventStack<Compiler, BackEndPass, C2DLL,
                CodeGeneration, Thread, Function>(
        eventStack, [](Compiler cl, BackEndPass bep, C2DLL c2,
            CodeGeneration cg, Thread t, Function f){ /* Do something ... */ });

    bool b2 = MatchEventStack<Compiler, Function>(
        eventStack, [](Compiler cl, Function f){ /* Do something... */ });

    bool b3 = MatchEventStack<Thread, Compiler, Function>(
        eventStack, [](Thread t, Compiler cl Function f){ /* Do something... */ });

    bool b4 = MatchEventStack<Compiler>(
        eventStack, [](Compiler cl){ /* Do something... */ });


    // b1: true because the list of types matches the eventStack exactly.
    // b2: true because Function is the last entry in both the type list
    //     and 'eventStack', and also because Compiler comes before
    //     Function in 'eventStack' and in the type list.
    // b3: false because, even though both Thread and Compiler come
    //     before Function in 'eventStack', they aren't listed in the
    //     right order in the type list.
    // b4: false because the last entry in the type list is Compiler,
    //     which doesn't match the last entry in 'eventStack' (Function).
}
```

::: moniker-end
