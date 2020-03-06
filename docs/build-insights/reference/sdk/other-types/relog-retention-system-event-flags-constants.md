---
title: RELOG_RETENTION_SYSTEM_EVENT_FLAGS 상수
description: C++ BUILD Insights SDK RELOG_RETENTION_SYSTEM_EVENT_FLAGS 상수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_RETENTION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 74afc10faa26ba39a669a05aa3e3cabd1a211293
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333967"
---
# <a name="relog_retention_system_event_flags-constants"></a>RELOG_RETENTION_SYSTEM_EVENT_FLAGS 상수

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`RELOG_RETENTION_SYSTEM_EVENT_FLAGS` 상수는 relogged 추적에 유지할 시스템 이벤트를 설명 하는 데 사용 됩니다. [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 구조체의 `SystemEventsRetentionFlags` 필드를 초기화 하는 데 사용 합니다.

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
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | Relogged 추적에서 CPU 샘플 시스템 이벤트를 유지 합니다. |
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL` | 모든 시스템 이벤트를 relogged 추적에 보관 합니다. |

## <a name="remarks"></a>주의

::: moniker-end
