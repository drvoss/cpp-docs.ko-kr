---
title: ForceInlinee 클래스
description: C++ BUILD Insights SDK ForceInlinee 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ForceInlinee
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7d3cce13601a0b3edbcd2b57664b2d0d94a7d3df
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334837"
---
# <a name="forceinlinee-class"></a>ForceInlinee 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`ForceInlinee` 클래스는 [Matchevent](../functions/match-event.md), [matcheventinmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)및 [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. 이를 사용 하 여 [FORCE_INLINEE](../event-table.md#force-inlinee) 이벤트를 일치 시킵니다.

## <a name="syntax"></a>구문

```cpp
class ForceInlinee : public SimpleEvent
{
public:
    ForceInlinee(const RawEvent& event);

    const char*             Name() const;
    const unsigned short&   Size() const;
};
```

## <a name="members"></a>멤버

[SimpleEvent](simple-event.md) 기본 클래스에서 상속 된 멤버와 함께 `ForceInlinee` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[ForceInlinee](#force-inlinee)

### <a name="functions"></a>함수

[이름](#name)
[크기](#size)

## <a name="force-inlinee"></a>ForceInlinee

```cpp
ForceInlinee(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*event*\
[FORCE_INLINEE](../event-table.md#force-inlinee) 이벤트입니다.

## <a name="name"></a> Name

```cpp
const char* Name() const;
```

### <a name="return-value"></a>반환 값

U t f-8로 인코딩된 강제 인라인 함수의 이름입니다.

## <a name="size"></a>크기가

```cpp
const unsigned short& Size() const;
```

### <a name="return-value"></a>반환 값

강제 인라인 함수의 크기 (중간 명령 수)입니다.

::: moniker-end
