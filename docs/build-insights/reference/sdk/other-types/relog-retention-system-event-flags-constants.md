---
title: RELOG_RETENTION_SYSTEM_EVENT_FLAGS 상수
description: C++ 빌드 인사이트 SDK RELOG_RETENTION_SYSTEM_EVENT_FLAGS 상수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_RETENTION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7110f809a819357b31951c203c1fa6ac9fb9f42e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323466"
---
# <a name="relog_retention_system_event_flags-constants"></a>RELOG_RETENTION_SYSTEM_EVENT_FLAGS 상수

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

`RELOG_RETENTION_SYSTEM_EVENT_FLAGS` 상수는 다시 기록된 추적에 유지할 시스템 이벤트를 설명하는 데 사용됩니다. [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 구조의 `SystemEventsRetentionFlags` 필드를 초기화하는 데 사용합니다.

## <a name="syntax"></a>구문

```cpp
static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES = 0x1ULL;

static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL         = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | CPU 샘플 시스템 이벤트를 다시 기록된 추적에 보관합니다. |
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL` | 모든 시스템 이벤트를 다시 기록한 추적에 보관합니다. |

## <a name="remarks"></a>설명

::: moniker-end
