---
title: TRACING_SESSION_OPTIONS 구조체
description: C++ BUILD Insights SDK TRACING_SESSION_OPTIONS 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_OPTIONS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3f02552d5df4ffe71bc4be5c46e4b5239f25d73c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333871"
---
# <a name="tracing_session_options-structure"></a>TRACING_SESSION_OPTIONS 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

[ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) 또는 [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 구조를 초기화할 때 `TRACING_SESSION_OPTIONS` 구조가 사용 됩니다. 추적을 수집 하는 동안 캡처할 이벤트를 설명 합니다.

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
| `SystemEventFlags` | 캡처할 시스템 이벤트를 설명 하는 비트 마스크입니다. 자세한 내용은 [TRACING_SESSION_SYSTEM_EVENT_FLAGS](tracing-session-system-event-flags-constants.md)를 참조 하세요. |
| `MsvcEventFlags` | 캡처할 MSVC 이벤트를 설명 하는 비트 마스크입니다. 자세한 내용은 [TRACING_SESSION_MSVC_EVENT_FLAGS](tracing-session-msvc-event-flags-constants.md)를 참조 하세요. |

::: moniker-end
