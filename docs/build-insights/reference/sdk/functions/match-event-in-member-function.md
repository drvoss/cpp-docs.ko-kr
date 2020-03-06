---
title: MatchEventInMemberFunction
description: C++ BUILD Insights SDK MatchEventInMemberFunction 함수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: eabbb8a91609b1447ebcc19af32df2ffed347c24
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334381"
---
# <a name="matcheventinmemberfunction"></a>MatchEventInMemberFunction

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`MatchEventInMemberFunction` 함수를 사용 하 여 멤버 함수의 첫 번째 매개 변수에 설명 된 형식과 이벤트를 일치 시킬 수 있습니다. 일치 하는 이벤트는 추가 처리를 위해 멤버 함수로 전달 됩니다.

## <a name="syntax"></a>구문

```cpp
template <
    typename     TInterface,
    typename     TReturn,
    typename     TEvent,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventInMemberFunction(
    const RawEvent&          event,
    TInterface*              objectPtr,
    TReturn (TInterface::*   memberFunc)(TEvent, TExtraParams...),
    TExtraArgs&&...          extraArgs);
```

### <a name="parameters"></a>매개 변수

*Tinterface*\
멤버 함수를 포함 하는 형식입니다.

*Treturn*\
멤버 함수의 반환 형식입니다.

*Tevent*\
일치 시킬 이벤트의 형식입니다.

*TExtraParams*\
일치 시킬 이벤트 유형과 함께 멤버 함수에서 허용 하는 추가 매개 변수의 형식입니다.

*TExtraArgs*\
`MatchEventInMemberFunction`에 전달 된 추가 인수의 형식입니다.

*event*\
*Tevent*에서 설명 하는 이벤트 유형과 일치 하는지 비교할 이벤트입니다.

*Objectptr*\
*Memberfunc* 가 호출 되는 개체에 대 한 포인터입니다.

*Memberfunc*\
일치 시킬 이벤트 유형을 설명 하는 멤버 함수입니다.

*extraArgs*\
이벤트 유형 매개 변수와 함께 *Memberfunc* 에 완벽 하 게 전달 되는 인수입니다.

### <a name="return-value"></a>반환 값

일치가 성공 했으면 **true** 이 고, 그렇지 않으면 **false** 인 **부울** 값입니다.

## <a name="remarks"></a>주의

*Tevent* 매개 변수에 사용할 이벤트 유형은 *캡처 클래스*목록에서 선택할 수 있습니다. 이벤트 목록과 일치 하는 데 사용할 수 있는 캡처 클래스는 [이벤트 표](../event-table.md)를 참조 하세요.

## <a name="example"></a>예제

```cpp
void MyClass::Foo1(Function f) {}

void MyClass::Foo2(Compiler cl) {}

void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    auto& functionEvent = eventStack.Back(); // The Function event

    bool b1 = MatchEventInMemberFunction(
        functionEvent, this, &MyClass::Foo1);

    bool b2 = MatchEventInMemberFunction(
        functionEvent, this, &MyClass::Foo2);

    // b1: true because the first parameter of Foo1 is Function.
    // b2: false because the first parameter of Foo2 isn't Function.
}
```

::: moniker-end
