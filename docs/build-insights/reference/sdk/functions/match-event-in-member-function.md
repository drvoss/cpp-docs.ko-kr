---
title: 매치이벤트인멤버기능
description: C++ 빌드 인사이트 SDK MatchEventInMemberFunction 함수 기능 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 522630da16e3f4a1294316d88140f4bc25dca2c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323893"
---
# <a name="matcheventinmemberfunction"></a>매치이벤트인멤버기능

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

함수는 `MatchEventInMemberFunction` 멤버 함수의 첫 번째 매개 변수에서 설명하는 형식과 이벤트를 일치시도록 사용됩니다. 일치하는 이벤트는 추가 처리를 위해 멤버 함수로 전달됩니다.

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

*인터페이스*\
멤버 함수를 포함하는 형식입니다.

*TReturn*\
멤버 함수의 반환 형식입니다.

*T이벤트*\
일치할 이벤트의 유형입니다.

*TExtraParams*\
일치하는 이벤트 형식과 함께 멤버 함수에서 허용하는 추가 매개 변수의 형식입니다.

*TExtraArgs*\
에 전달된 추가 인수의 `MatchEventInMemberFunction`형식입니다.

*이벤트*\
*TEvent에서*설명하는 이벤트 유형과 일치하는 이벤트입니다.

*개체Ptr*\
*멤버Func호출되는* 개체에 대한 포인터입니다.

*멤버펑*\
일치할 이벤트 유형을 설명하는 멤버 함수입니다.

*엑스트라 아르그*\
이벤트 형식 매개 변수와 함께 *memberFunc에* 완벽하게 전달되는 인수입니다.

### <a name="return-value"></a>Return Value

일치가 성공한 경우 **true인** **bool** 값 또는 그렇지 않으면 **false입니다.**

## <a name="remarks"></a>설명

*TEvent* 매개 변수에 사용할 이벤트 형식을 *캡처 클래스*목록에서 선택할 수 있습니다. 이벤트 목록 및 이벤트 와 일치하는 데 사용할 수 있는 캡처 클래스는 [이벤트 테이블을](../event-table.md)참조하십시오.

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
