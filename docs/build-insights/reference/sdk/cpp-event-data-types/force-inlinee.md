---
title: 포스인린 클래스
description: C++ 빌드 인사이트 SDK ForceInlinee 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ForceInlinee
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c6a1af0384197a0a3b6062ad9ef30537c348190d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324779"
---
# <a name="forceinlinee-class"></a>포스인린 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `ForceInlinee` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [FORCE_INLINEE](../event-table.md#force-inlinee) 이벤트와 일치하는 데 사용합니다.

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

[SimpleEvent](simple-event.md) 기본 클래스에서 상속된 멤버와 `ForceInlinee` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[포스인린](#force-inlinee)

### <a name="functions"></a>Functions

[이름](#name)
[크기](#size)

## <a name="forceinlinee"></a><a name="force-inlinee"></a>포스인린

```cpp
ForceInlinee(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[FORCE_INLINEE](../event-table.md#force-inlinee) 이벤트입니다.

## <a name="name"></a><a name="name"></a>이름

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Return Value

UTF-8로 인코딩된 강제 인라인 함수의 이름입니다.

## <a name="size"></a><a name="size"></a> 크기

```cpp
const unsigned short& Size() const;
```

### <a name="return-value"></a>Return Value

중간 명령 수로 강제 인라인 함수의 크기입니다.

::: moniker-end
