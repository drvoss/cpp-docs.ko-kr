---
title: ANALYSIS_CALLBACKS 구조체
description: C++ BUILD Insights SDK ANALYSIS_CALLBACKS 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8c35e740d97488969a6b69467d54412297e49227
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334147"
---
# <a name="analysis_callbacks-structure"></a>ANALYSIS_CALLBACKS 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

[ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) 또는 [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 개체를 초기화할 때 `ANALYSIS_CALLBACKS` 구조가 사용 됩니다. ETW(Windows용 이벤트 추적) (ETW) 추적을 분석 하거나 다시 로깅하는 동안 호출할 함수를 지정 합니다.

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
| `OnStartActivity` | 작업 시작 이벤트를 처리 하기 위해 호출 됩니다. |
| `OnStopActivity` | 작업 중지 이벤트를 처리 하기 위해 호출 됩니다. |
| `OnSimpleEvent` | 간단한 이벤트를 처리 하기 위해 호출 됩니다. |
| `OnTraceInfo` | 분석 세션의 경우 각 분석 단계가 시작 될 때 호출 됩니다. 다시 로깅 세션의 경우 각 분석 단계가 시작 될 때와 다시 로깅 단계가 시작 될 때 호출 됩니다. 이 함수는 OnBeginAnalysisPass가 호출 된 후에만 호출 됩니다. |
| `OnBeginAnalysis` | 분석 세션의 경우 분석 단계가 시작 되기 전에 호출 됩니다. 다시 로깅 세션의 경우 분석 단계가 시작 되기 전에 두 번 호출 됩니다. 다시 로깅 세션의 시작을 알리고 분석 단계의 시작을 발표 하는 데 한 번 더 합니다. |
| `OnEndAnalysis` | 분석 세션의 경우이 함수는 모든 분석 단계가 종료 된 후에 호출 됩니다. Relogging 세션의 경우이 함수는 분석 단계의 모든 분석 단계가 종료 될 때 호출 됩니다. 그런 다음 다시 로깅 패스가 종료 된 후 다시 호출 됩니다. |
| `OnBeginAnalysisPass` | 이벤트를 처리 하기 전에 분석 패스 또는 다시 로깅 통과를 시작할 때 호출 됩니다. |
| `OnEndAnalysisPass` | 모든 이벤트를 처리 한 후 분석 패스 또는 다시 로깅 통과를 종료할 때 호출 됩니다. |

## <a name="remarks"></a>주의

다시 로깅 세션의 분석 단계는 relogging 세션의 일부로 간주 되며 여러 분석 패스를 포함할 수 있습니다. 이러한 이유로 다시 로깅 세션이 시작 될 때 행에서 `OnBeginAnalysis`가 두 번 호출 됩니다. `OnEndAnalysis`는 분석 단계가 끝날 때, 다시 로깅 단계를 시작 하기 전에, 다시 로깅 단계가 끝날 때 한 번만 호출 됩니다. 재 로깅 단계에는 항상 단일 다시 로깅 단계가 포함 됩니다.

분석기는 다시 로깅 세션의 분석 및 재 로깅 단계 모두에 속할 수 있습니다. 이러한 분석기는 OnBeginAnalysis `OnEndAnalysis` 호출 쌍을 추적 하 여 현재 진행 중인 단계를 확인할 수 있습니다. `OnEndAnalysis` 호출 없이 두 개의 `OnBeginAnalysis` 호출은 분석 단계가 진행 되 고 있음을 의미 합니다. 두 개의 `OnBeginAnalysis` 호출과 하나의 `OnEndAnalysis` 호출은 다시 로깅 단계가 진행 되 고 있음을 의미 합니다. 두 개의 OnBeginAnalysis 두 개의 `OnEndAnalysis` 호출은 두 단계가 모두 종료 되었음을 의미 합니다.

`ANALYSIS_CALLBACKS` 구조체의 모든 멤버는 유효한 함수를 가리켜야 합니다. 허용 되는 함수 서명에 대 한 자세한 내용은 [OnAnalysisEventFunc](on-analysis-event-func-typedef.md), [ontraceinfofunc](on-trace-info-func-typedef.md)및 [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md)를 참조 하세요.

::: moniker-end
