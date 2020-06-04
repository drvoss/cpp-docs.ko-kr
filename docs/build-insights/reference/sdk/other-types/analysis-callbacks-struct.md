---
title: ANALYSIS_CALLBACKS 구조
description: C++ 빌드 인사이트 SDK ANALYSIS_CALLBACKS 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3c6de999b19657f999f884075ee53e21a4d2f2b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323490"
---
# <a name="analysis_callbacks-structure"></a>ANALYSIS_CALLBACKS 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `ANALYSIS_CALLBACKS` [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) 또는 [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 개체를 초기화할 때 사용됩니다. ETW(Windows용 이벤트 추적) 추적을 분석하거나 다시 기록하는 동안 호출할 함수를 지정합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct ANALYSIS_CALLBACKS_TAG
{
    OnAnalysisEventFunc     OnStartActivity;
    OnAnalysisEventFunc     OnStopActivity;
    OnAnalysisEventFunc     OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginAnalysis;
    OnBeginEndPassFunc      OnEndAnalysis;
    OnBeginEndPassFunc      OnBeginAnalysisPass;
    OnBeginEndPassFunc      OnEndAnalysisPass;
} ANALYSIS_CALLBACKS;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `OnStartActivity` | 활동 시작 이벤트를 처리하기 위해 호출되었습니다. |
| `OnStopActivity` | 활동 중지 이벤트를 처리하기 위해 호출됩니다. |
| `OnSimpleEvent` | 간단한 이벤트를 처리하기 위해 호출됩니다. |
| `OnTraceInfo` | 각 분석 패스의 시작 부분에 호출되는 분석 세션의 경우 각 분석 패스의 시작 부분에 호출된 세션 을 다시 기록하고 다시 리로깅 패스의 시작 부분에 다시 호출합니다. 이 함수는 OnBeginAnalysisPass가 호출된 후에만 호출됩니다. |
| `OnBeginAnalysis` | 분석 패스가 시작되기 전에 호출된 분석 세션의 경우 분석 단계가 시작되기 전에 두 번 호출된 리로깅 세션의 경우: 한 번은 리로깅 세션의 시작을 알리고, 다시 한 번 분석 단계의 시작을 발표합니다. |
| `OnEndAnalysis` | 분석 세션의 경우 모든 분석 가공 패스가 종료된 후 이 함수가 호출됩니다. 리로깅 세션의 경우 분석 단계의 모든 분석 이가 끝나면 이 함수가 호출됩니다. 그런 다음 리로깅 패스가 끝난 후 다시 호출됩니다. |
| `OnBeginAnalysisPass` | 이벤트를 처리하기 전에 분석 패스 또는 리로깅 패스를 시작할 때 호출됩니다. |
| `OnEndAnalysisPass` | 모든 이벤트를 처리한 후 분석 패스 또는 리로깅 패스를 종료할 때 호출됩니다. |

## <a name="remarks"></a>설명

리로깅 세션의 분석 단계는 리로깅 세션의 일부로 간주되며 여러 분석 전달을 포함할 수 있습니다. 이러한 이유로 `OnBeginAnalysis` 리로깅 세션이 시작될 때 연속으로 두 번 호출됩니다. `OnEndAnalysis`다시 로깅 단계를 시작하기 전에 분석 단계의 끝에서 호출되고 다시 로깅 단계가 끝날 때 다시 호출됩니다. 리로깅 단계에는 항상 단일 리로깅 패스가 포함됩니다.

분석기는 리로깅 세션의 분석 및 리로깅 단계 모두에 속할 수 있습니다. 이러한 분석기는 OnBeginAnalysis 및 `OnEndAnalysis` 호출 쌍을 추적하여 현재 진행 중인 단계를 결정할 수 있습니다. 호출없이 `OnBeginAnalysis` `OnEndAnalysis` 두 번의 호출은 분석 단계가 진행 중임을 의미합니다. 두 `OnBeginAnalysis` 번의 `OnEndAnalysis` 호출과 한 번의 호출은 리로깅 단계가 진행 중임을 의미합니다. 두 OnBeginAnalysis `OnEndAnalysis` 두 호출은 두 단계가 모두 끝났는 것을 의미합니다.

구조의 모든 `ANALYSIS_CALLBACKS` 멤버는 유효한 함수를 가리겨야 합니다. 수락된 함수 서명에 대한 자세한 내용은 [OnAnalysisEventFunc](on-analysis-event-func-typedef.md), [OnTraceInfoFunc](on-trace-info-func-typedef.md)및 [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md)을 참조하십시오.

::: moniker-end
