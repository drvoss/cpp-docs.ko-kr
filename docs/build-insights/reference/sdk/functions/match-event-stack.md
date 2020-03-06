---
title: MatchEventStack
description: C++ BUILD Insights SDK MatchEventStack 함수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 445c2d00c24da10754d32256de0c691e82b557e1
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334363"
---
# <a name="matcheventstack"></a>MatchEventStack

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`MatchEventStack` 함수는 특정 이벤트 계층 구조와 이벤트 스택을 일치 시키는 데 사용 됩니다. 추가 처리를 위해 일치 하는 계층이 처리기에 전달 됩니다. 이벤트, 이벤트 스택 및 계층에 대 한 자세한 내용은 [이벤트 표](../event-table.md)를 참조 하세요.

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

*Tevent*\
이벤트 스택에서 일치 시킬 eldest 부모의 형식입니다.

*Tevents*\
이벤트 스택에서 일치 시키려는 나머지 형식입니다.

*Tcallable 가능*\
`operator()`를 지 원하는 형식입니다. 이 연산자에 전달 되는 인수에 대 한 자세한 내용은 *호출 가능* 매개 변수 설명을 참조 하세요.

*TExtraArgs*\
`MatchEventStack`에 전달 되는 추가 인수의 형식입니다.

*Eventstack*\
*Tevent* 및 *tevent*에서 설명한 이벤트 유형 계층 구조와 일치 하는지 비교할 이벤트 스택입니다.

*호출 가능*\
*Tevent* 및 *tevent*에서 설명 하는 이벤트 유형 계층 구조와 이벤트 스택을 성공적으로 일치 하는 경우 `MatchEventStack` *호출할*호출을 호출 합니다. 이벤트 계층의 각 형식에 대해 *호출* 가능한 하나의 r 값 인수를 전달 합니다. *ExtraArgs* 매개 변수 팩은 *호출 가능*의 나머지 매개 변수에서 완벽 하 게 전달 됩니다.

*extraArgs*\
일치 하는 이벤트 형식과 함께 *호출할* 수 있도록 완벽 하 게 전달 되는 인수입니다.

### <a name="return-value"></a>반환 값

일치가 성공 했으면 **true** 이 고, 그렇지 않으면 **false** 인 **부울** 값입니다.

## <a name="remarks"></a>주의

*Eventstack* 의 마지막 이벤트는 연결 된 \[*tevent*, *tevent ...* \] type 목록의 마지막 항목과 항상 일치 합니다. 다른 모든 *Tevent* 및 *tevent* 항목은 Last를 제외한 *eventstack* 의 모든 위치와 일치할 수 있습니다 (동일한 순서로 제공 됨).

*Tevent* 및 *tevent* 매개 변수에 사용할 이벤트 유형은 *캡처 클래스*목록에서 선택 합니다. 이벤트 목록과 일치 하는 데 사용할 수 있는 캡처 클래스는 [이벤트 표](../event-table.md)를 참조 하세요.

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
