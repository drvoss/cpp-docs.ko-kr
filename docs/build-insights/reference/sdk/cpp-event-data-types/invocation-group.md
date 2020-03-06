---
title: InvocationGroup 클래스
description: C++ BUILD Insights SDK InvocationGroup 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InvocationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b9a2bbcd2b7649b9b5703adc08ed41b272e10276
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334753"
---
# <a name="invocationgroup-class"></a>InvocationGroup 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`InvocationGroup` 클래스는 [Matcheventstack](../functions/match-event-stack.md) 및 [Matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. 이를 사용 하 여 [컴파일러](../event-table.md#compiler) 및 [링커](../event-table.md#linker) 이벤트를 혼합 하는 그룹을 찾습니다.

## <a name="syntax"></a>구문

```cpp
class InvocationGroup : public EventGroup<Invocation>
{
public:
    InvocationGroup(std::deque<Invocation>&& group);
};
```

## <a name="members"></a>멤버

[Eventgroup\<호출\>](event-group.md) 기본 클래스에서 상속 된 멤버와 함께 `InvocationGroup` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[InvocationGroup](#invocation-group)

## <a name="invocation-group"></a>InvocationGroup

```cpp
InvocationGroup(std::deque<Invocation>&& group);
```

### <a name="parameters"></a>매개 변수

*그룹*\
[컴파일러](../event-table.md#compiler) 및 [링커](../event-table.md#linker) 이벤트의 혼합을 포함 하는 그룹입니다.

::: moniker-end
