---
title: TRACING_SESSION_OPTIONS 구조
description: C++ 빌드 인사이트 SDK TRACING_SESSION_OPTIONS 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_OPTIONS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5aeb6299aea8dc0661b9469ee524e7aa4d010aca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323435"
---
# <a name="tracing_session_options-structure"></a>TRACING_SESSION_OPTIONS 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `TRACING_SESSION_OPTIONS` [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) 또는 [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 구조를 초기화할 때 사용됩니다. 추적 을 수집하는 동안 캡처할 이벤트를 설명합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct TRACING_SESSION_OPTIONS_TAG
{
    unsigned long long SystemEventFlags;
    unsigned long long MsvcEventFlags;

} TRACING_SESSION_OPTIONS;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `SystemEventFlags` | 캡처할 시스템 이벤트를 설명하는 비트 마스크입니다. 자세한 내용은 [TRACING_SESSION_SYSTEM_EVENT_FLAGS](tracing-session-system-event-flags-constants.md)를 참조하십시오. |
| `MsvcEventFlags` | 캡처할 MSVC 이벤트를 설명하는 비트 마스크입니다. 자세한 내용은 [TRACING_SESSION_MSVC_EVENT_FLAGS](tracing-session-msvc-event-flags-constants.md)을 참조하십시오. |

::: moniker-end
