---
title: TRACING_SESSION_SYSTEM_EVENT_FLAGS 상수
description: C++ BUILD Insights SDK TRACING_SESSION_SYSTEM_EVENT_FLAGS 상수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ce0b0ea373ec53f0d5bcf228269299d69b49bb95
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333997"
---
# <a name="tracing_session_system_event_flags-constants"></a>TRACING_SESSION_SYSTEM_EVENT_FLAGS 상수

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`TRACING_SESSION_SYSTEM_EVENT_FLAGS` 상수는 추적 하는 동안 수집할 시스템 이벤트를 설명 하는 데 사용 됩니다. [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md) 구조체의 `SystemEventFlags` 필드를 초기화 하는 데 사용 합니다.

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

| 이름 | 이 플래그에 의해 설정 된 이벤트 |
|--|--|
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT` | 이 플래그는 명시적으로 지정 되지 않은 C++ 경우에도 BUILD Insights SDK에서 기본적으로 활성화 됩니다. 이를 통해 C++ 빌드 정보에 필요한 기본 시스템 이벤트가 제대로 작동 합니다. 이 플래그를 사용 하는 이벤트는 프로세스, 스레드 및 이미지 로드에 대 한 정보를 제공 합니다. 이러한 이벤트는 사용 하지 않도록 설정할 수 없습니다. |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | CPU 샘플 |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL` | 이 플래그는 모든 시스템 이벤트를 설정 합니다. |

::: moniker-end
