---
title: RELOG_DESCRIPTOR 구조
description: C++ 빌드 인사이트 SDK RELOG_DESCRIPTOR 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c3aee49fe9f609ca37082693ddcfd5e838cc96a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328947"
---
# <a name="relog_descriptor-structure"></a>RELOG_DESCRIPTOR 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `RELOG_DESCRIPTOR` 구조는 [RelogA](../functions/relog-a.md) 및 [RelogW](../functions/relog-w.md) 함수와 함께 사용됩니다. WINDOWS용 이벤트 추적(ETW) 추적을 다시 기록하는 방법을 설명합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct RELOG_DESCRIPTOR_TAG
{
    unsigned                NumberOfAnalysisPasses;
    ANALYSIS_CALLBACKS      AnalysisCallbacks;
    RELOG_CALLBACKS         RelogCallbacks;
    unsigned long long      SystemEventsRetentionFlags;
    void*                   AnalysisContext;
    void*                   RelogContext;
} RELOG_DESCRIPTOR;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `NumberOfAnalysisPasses` | 다시 로깅 세션의 분석 단계에서 ETW 추적을 통해 수행해야 하는 분석 패스 수입니다. |
| `AnalysisCallbacks` | 다시 로깅 세션의 분석 단계에서 호출할 함수를 지정하는 [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 개체입니다. |
| `RelogCallbacks` | 다시 로깅 세션의 리로깅 단계에서 호출할 함수를 지정하는 [RELOG_CALLBACKS](relog-callbacks-struct.md) 개체입니다. |
| `SystemEventsRetentionFlags` | 다시 기록된 추적에 보관할 시스템 ETW 이벤트를 지정하는 [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](relog-retention-system-event-flags-constants.md) 비트 마스크입니다. |
| `AnalysisContext` | 지정된 모든 콜백 함수에 인수로 전달되는 사용자 제공 컨텍스트`AnalysisCallbacks` |
| `RelogContext` | 지정된 모든 콜백 함수에 인수로 전달되는 사용자 제공 컨텍스트`RelogCallbacks` |

## <a name="remarks"></a>설명

relogging 세션 중에 ETW 이벤트의 리로깅은 에 지정된 콜백 함수를 통해 사용자가 제어합니다. `RelogCallbacks` 그러나 CPU 샘플과 같은 시스템 ETW 이벤트는 이러한 콜백 함수로 전달되지 않습니다. `SystemEventsRetentionFlags` 필드를 사용하여 시스템 ETW 이벤트의 재로깅을 제어합니다.

`AnalysisCallbacks` 및 `RelogCallbacks` 구조는 비멤버 함수에 대한 포인터만 허용합니다. 개체 포인터로 설정하여 이 제한을 해결할 수 있습니다. 이 개체 포인터는 모든 비멤버 콜백 함수에 대한 인수로 전달됩니다. 이 포인터를 사용하여 비멤버 콜백 함수 내에서 멤버 함수를 호출합니다.

리로깅 세션의 분석 단계는 항상 리로깅 단계 전에 실행됩니다.

::: moniker-end
