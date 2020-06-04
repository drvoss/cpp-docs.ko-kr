---
title: TRACING_SESSION_SYSTEM_EVENT_FLAGS 상수
description: C++ 빌드 인사이트 SDK TRACING_SESSION_SYSTEM_EVENT_FLAGS 상수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 264d697cc905eb6b44c8ec7de835a552976f0eb8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323280"
---
# <a name="tracing_session_system_event_flags-constants"></a>TRACING_SESSION_SYSTEM_EVENT_FLAGS 상수

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

`TRACING_SESSION_SYSTEM_EVENT_FLAGS` 상수는 추적 중에 수집할 시스템 이벤트를 설명하는 데 사용됩니다. [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md) 구조의 `SystemEventFlags` 필드를 초기화하는 데 사용합니다.

## <a name="syntax"></a>구문

```cpp
static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT      = 0x1ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES  = 0x2ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL          = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>멤버

| 속성 | 이 플래그로 설정된 이벤트 |
|--|--|
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT` | 이 플래그는 명시적으로 지정되지 않은 경우에도 C++ 빌드 인사이트 SDK에 의해 기본적으로 활성화됩니다. C++ 빌드 인사이트가 제대로 작동하도록 필요한 기본 시스템 이벤트를 사용할 수 있습니다. 이 플래그에서 사용할 수 있는 이벤트는 프로세스, 스레드 및 이미지 로드에 대한 정보를 제공합니다. 이러한 이벤트는 비활성화할 수 없습니다. |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | CPU 샘플 |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL` | 이 플래그는 모든 시스템 이벤트를 켭니다. |

::: moniker-end
