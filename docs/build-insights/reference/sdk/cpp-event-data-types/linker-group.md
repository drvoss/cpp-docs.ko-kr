---
title: LinkerGroup 클래스
description: C++ BUILD Insights SDK LinkerGroup 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 95b0dcc3a771ec07ee60185a79a5ddbc29434b5d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334729"
---
# <a name="linkergroup-class"></a>LinkerGroup 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`LinkerGroup` 클래스는 [Matcheventstack](../functions/match-event-stack.md) 및 [Matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. [링커](../event-table.md#linker) 이벤트 그룹을 일치 시키는 데 사용 합니다.

## <a name="syntax"></a>구문

```cpp
class LinkerGroup : public EventGroup<Linker>
{
public:
    LinkerGroup(std::deque<Linker>&& group);
};
```

## <a name="members"></a>멤버

[Eventgroup\<링커\>](event-group.md) 기본 클래스에서 상속 된 멤버와 함께 `LinkerGroup` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[LinkerGroup](#linker-group)

## <a name="linker-group"></a>LinkerGroup

```cpp
LinkerGroup(std::deque<Linker>&& group);
```

### <a name="parameters"></a>매개 변수

*그룹*\
[링커](../event-table.md#linker) 이벤트의 그룹입니다.

::: moniker-end
