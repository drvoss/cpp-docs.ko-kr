---
title: 심플이벤트 클래스
description: C++ 빌드 인사이트 SDK SimpleEvent 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SimpleEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 414ff5c1af99acc612384c1ae39f6e12ab051275
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324363"
---
# <a name="simpleevent-class"></a>심플이벤트 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `SimpleEvent` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. 간단한 이벤트와 일치하는 데 사용합니다. [클래스와](../event-table.md) 일치시킬 수 있는 모든 이벤트를 보려면 이벤트 테이블을 참조하십시오. `SimpleEvent`

## <a name="syntax"></a>구문

```cpp
class SimpleEvent : public Event
{
public:
    SimpleEvent(const RawEvent& event);
};
```

## <a name="members"></a>멤버

[해당 Event](event.md) 기본 클래스에서 상속된 멤버와 함께 `SimpleEvent` 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[심플 이벤트](#simple-event)

## <a name="simpleevent"></a><a name="simple-event"></a>심플 이벤트

```cpp
SimpleEvent(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
모든 간단한 이벤트.

::: moniker-end
