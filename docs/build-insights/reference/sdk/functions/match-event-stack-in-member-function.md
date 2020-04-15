---
title: 매치이벤트스택인멤버기능
description: C ++ 빌드 인사이트 SDK MatchEventStackInMemberFunction 함수 함수 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStackInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 28842a02e7edc2e00266d8c7941798f4ce714ded
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323882"
---
# <a name="matcheventstackinmemberfunction"></a>매치이벤트스택인멤버기능

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

함수는 `MatchEventStackInMemberFunction` 멤버 함수의 매개 변수 목록에서 설명하는 특정 이벤트 계층 구조와 이벤트 스택을 일치시도록 사용됩니다. 일치하는 계층구조는 추가 처리를 위해 멤버 함수로 전달됩니다. 이벤트, 이벤트 스택 및 계층구조에 대한 자세한 내용은 [이벤트 테이블을](../event-table.md)참조하십시오.

## <a name="syntax"></a>구문

```cpp
template <
    typename     TInterface,
    typename     TReturn,
    typename     T1,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventStackInMemberFunction(
    const EventStack&         eventStack,
    TInterface*               objectPtr,
    TReturn (TInterface::*    memberFunc)(T1, TExtraParams...),
    TExtraArgs&&...           extraArgs);

template <
    typename     TInterface,
    typename     TReturn,
    typename     T1,
    typename     T2,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventStackInMemberFunction(
    const EventStack&         eventStack,
    TInterface*               objectPtr,
    TReturn (TInterface::*    memberFunc)(T1, T2, TExtraParams...),
    TExtraArgs&&...           extraArgs);

// Etc...

template <
    typename     TInterface,
    typename     TReturn,
    typename     T1,
    typename     T2,
    typename     T3,
    typename     T4,
    typename     T5,
    typename     T6,
    typename     T7,
    typename     T8,
    typename     T9,
    typename     T10,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventStackInMemberFunction(
    const EventStack&         eventStack,
    TInterface*               objectPtr,
    TReturn (TInterface::*    memberFunc)(T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, TExtraParams...),
    TExtraArgs&&...           extraArgs);
```

### <a name="parameters"></a>매개 변수

*인터페이스*\
멤버 함수를 포함하는 형식입니다.

*TReturn*\
멤버 함수의 반환 형식입니다.

*T1*, ..., *T10*\
일치할 이벤트 계층 구조를 설명하는 형식입니다.

*TExtraParams*\
멤버 함수에서 허용하는 추가 매개 변수의 형식과 이벤트 계층 유형입니다.

*TExtraArgs*\
에 전달된 추가 인수의 `MatchEventStackInMemberFunction`형식입니다.

*이벤트 스택*\
*T1에서* *T10까지*설명하는 이벤트 형식 계층 구조와 일치하는 이벤트 스택입니다.

*개체Ptr*\
*멤버Func가* 호출되는 개체에 대한 포인터입니다.

*멤버펑*\
일치할 이벤트 형식 계층 구조를 설명하는 멤버 함수입니다.

*엑스트라 아르그*\
이벤트 형식 계층 구조 매개 변수와 함께 *memberFunc에* 완벽하게 전달되는 인수입니다.

### <a name="return-value"></a>Return Value

일치가 성공한 경우 **true인** **bool** 값 또는 그렇지 않으면 **false입니다.**

## <a name="remarks"></a>설명

*eventStack의* 마지막 이벤트는 항상 일치하는 이벤트 유형 계층 구조의 마지막 항목과 일치합니다. 이벤트 유형 계층구조의 다른 모든 형식은 동일한 순서로 제공되는 경우 마지막 을 제외한 *eventStack의* 모든 위치와 일치할 수 있습니다.

*T1부터* *T10* 매개 변수에 사용할 이벤트 유형은 *캡처 클래스*목록에서 선택됩니다. 이벤트 목록 및 이벤트 와 일치하는 데 사용할 수 있는 캡처 클래스는 [이벤트 테이블을](../event-table.md)참조하십시오.

## <a name="example"></a>예제

```cpp
void MyClass::Foo1(Compiler cl, BackEndPass bep, C2DLL c2,
    CodeGeneration cg, Thread t, Function f) { }

void MyClass::Foo2(Compiler cl, Function f) { }

void MyClass::Foo3(Thread t, Compiler cl, Function f) { }

void MyClass::Foo4(Compiler cl) { }

void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    bool b1 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo1);

    bool b2 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo2);

    bool b3 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo3);

    bool b4 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo4);

    // b1: true because the parameter types of Foo1 match the eventStack
    //     exactly.
    // b2: true because Function is the last entry in both the member
    //     function parameter list and 'eventStack', and also because
    //     Compiler comes before Function in 'eventStack' and in the
    //     parameter type list.
    // b3: false because, even though both Thread and Compiler come
    //     before Function in 'eventStack', the member function parameter
    //     list doesn't list them in the right order.
    // b4: false because the last entry in the member function parameter
    //     list is Compiler, which doesn't match the last entry in 'eventStack'
    //     (Function).
}
```

::: moniker-end
