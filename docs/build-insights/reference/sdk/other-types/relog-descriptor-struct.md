---
title: RELOG_DESCRIPTOR 구조체
description: C++ BUILD Insights SDK RELOG_DESCRIPTOR 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f6f20835ed6535dd05def629200c113772e8f077
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333973"
---
# <a name="relog_descriptor-structure"></a>RELOG_DESCRIPTOR 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`RELOG_DESCRIPTOR` 구조는 [Reloga](../functions/relog-a.md) 및 [reloga](../functions/relog-w.md) 함수와 함께 사용 됩니다. ETW(Windows용 이벤트 추적) (ETW) 추적을 relogged 하는 방법을 설명 합니다.

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
| `NumberOfAnalysisPasses` | 재 로깅 세션의 분석 단계에서 ETW 추적을 통해 수행 해야 하는 분석 패스의 수입니다. |
| `AnalysisCallbacks` | 재 로깅 세션의 분석 단계 중에 호출할 함수를 지정 하는 [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 개체입니다. |
| `RelogCallbacks` | 재 로깅 세션의 relogging 단계에서 호출할 함수를 지정 하는 [RELOG_CALLBACKS](relog-callbacks-struct.md) 개체입니다. |
| `SystemEventsRetentionFlags` | Relogged 추적에 유지할 시스템 ETW 이벤트를 지정 하는 [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](relog-retention-system-event-flags-constants.md) 비트 마스크입니다. |
| `AnalysisContext` | 에 지정 된 모든 콜백 함수에 인수로 전달 되는 사용자 제공 컨텍스트입니다 `AnalysisCallbacks` |
| `RelogContext` | 에 지정 된 모든 콜백 함수에 인수로 전달 되는 사용자 제공 컨텍스트입니다 `RelogCallbacks` |

## <a name="remarks"></a>주의

다시 로깅 세션 중에 ETW 이벤트의 다시 로깅은 `RelogCallbacks`에 지정 된 콜백 함수를 통해 사용자에 의해 제어 됩니다. 그러나 CPU 샘플과 같은 시스템 ETW 이벤트는 이러한 콜백 함수로 전달 되지 않습니다. `SystemEventsRetentionFlags` 필드를 사용 하 여 시스템 ETW 이벤트의 다시 로깅을 제어할 수 있습니다.

`AnalysisCallbacks` 및 `RelogCallbacks` 구조는 비멤버 함수에 대 한 포인터만 허용 합니다. 이 제한을 개체 포인터로 설정 하면 이러한 제한을 해결할 수 있습니다. 이 개체 포인터는 모든 멤버가 아닌 콜백 함수에 인수로 전달 됩니다. 멤버가 아닌 콜백 함수 내에서 멤버 함수를 호출 하려면이 포인터를 사용 합니다.

재 로깅 세션의 분석 단계는 항상 다시 로깅 단계 이전에 실행 됩니다.

::: moniker-end
