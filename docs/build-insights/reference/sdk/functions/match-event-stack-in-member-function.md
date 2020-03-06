---
title: MatchEventStackInMemberFunction
description: C++ 빌드 Insights SDK MatchEventStackInMemberFunction 함수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStackInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2a966ea5209a25a62c08cb0873d0565299a15d27
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334369"
---
# <a name="matcheventstackinmemberfunction"></a>MatchEventStackInMemberFunction

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`MatchEventStackInMemberFunction` 함수는 멤버 함수의 매개 변수 목록에서 설명 하는 특정 이벤트 계층 구조와 이벤트 스택을 일치 시키는 데 사용 됩니다. 일치 하는 계층은 추가 처리를 위해 멤버 함수로 전달 됩니다. 이벤트, 이벤트 스택 및 계층에 대 한 자세한 내용은 [이벤트 표](../event-table.md)를 참조 하세요.

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

*Tinterface*\
멤버 함수를 포함 하는 형식입니다.

*Treturn*\
멤버 함수의 반환 형식입니다.

*T1*, ..., *T10*\
일치 시킬 이벤트 계층 구조를 설명 하는 형식입니다.

*TExtraParams*\
멤버 함수에서 허용 하는 추가 매개 변수의 형식 및 이벤트 계층 구조 형식입니다.

*TExtraArgs*\
`MatchEventStackInMemberFunction`에 전달 된 추가 인수의 형식입니다.

*Eventstack*\
*T1* 에서 *T10*로 설명 하는 이벤트 유형 계층 구조와 일치 하는지 비교할 이벤트 스택입니다.

*Objectptr*\
*Memberfunc* 가 호출 되는 개체에 대 한 포인터입니다.

*Memberfunc*\
일치 시킬 이벤트 형식 계층 구조를 설명 하는 멤버 함수입니다.

*extraArgs*\
이벤트 유형 계층 구조 매개 변수와 함께 *Memberfunc* 에 완벽 하 게 전달 되는 인수입니다.

### <a name="return-value"></a>반환 값

일치가 성공 했으면 **true** 이 고, 그렇지 않으면 **false** 인 **부울** 값입니다.

## <a name="remarks"></a>주의

*Eventstack* 의 마지막 이벤트는 일치 시킬 이벤트 유형 계층의 마지막 항목과 항상 일치 합니다. 이벤트 유형 계층 구조에 있는 다른 모든 형식은 동일한 순서로 제공 된 마지막를 제외 하 고 *Eventstack* 의 모든 위치와 일치할 수 있습니다.

T- *T10* 매개 변수에 사용할 이벤트 유형이 *캡처 클래스*목록에서 선택 됩니다. 이벤트 목록과 일치 하는 데 사용할 수 있는 캡처 클래스는 [이벤트 표](../event-table.md)를 참조 하세요.

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
