---
title: 링커패스 클래스
description: C ++ 빌드 인사이트 SDK LinkerPass 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2b0c5a02958560faeff30500543b6e6d4921ac52
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324608"
---
# <a name="linkerpass-class"></a>링커패스 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `LinkerPass` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [PASS1](../event-table.md#pass1) 또는 [PASS2](../event-table.md#pass2) 이벤트와 일치하는 데 사용합니다.

## <a name="syntax"></a>구문

```cpp
class LinkerPass : public Activity
{
public:
    LinkerPass(const RawEvent& event);
};
```

## <a name="members"></a>멤버

[활동](activity.md) 기본 클래스의 상속된 멤버와 `LinkerPass` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[링커 패스](#linker-pass)

## <a name="linkerpass"></a><a name="linker-pass"></a>링커 패스

```cpp
LinkerPass(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[PASS1](../event-table.md#pass1) 또는 [PASS2](../event-table.md#pass2) 이벤트.

::: moniker-end
