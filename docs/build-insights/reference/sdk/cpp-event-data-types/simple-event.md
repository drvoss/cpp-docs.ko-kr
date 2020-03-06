---
title: SimpleEvent 클래스
description: C++ BUILD Insights SDK SimpleEvent 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SimpleEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4c30f81236138328322d8c870d4ad69d9988b49a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334591"
---
# <a name="simpleevent-class"></a>SimpleEvent 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`SimpleEvent` 클래스는 [Matchevent](../functions/match-event.md), [matcheventinmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)및 [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. 이를 사용 하 여 모든 단순 이벤트를 일치 시킵니다. `SimpleEvent` 클래스에서 일치 시킬 수 있는 모든 이벤트를 보려면 [이벤트 표](../event-table.md) 를 참조 하세요.

## <a name="syntax"></a>구문

```cpp
class SimpleEvent : public Event
{
public:
    SimpleEvent(const RawEvent& event);
};
```

## <a name="members"></a>멤버

해당 [이벤트](event.md) 기본 클래스의 상속 된 멤버와 함께 `SimpleEvent` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[SimpleEvent](#simple-event)

## <a name="simple-event"></a>SimpleEvent

```cpp
SimpleEvent(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*event*\
모든 간단한 이벤트입니다.

::: moniker-end
