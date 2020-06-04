---
title: 온트레이스인포푼크 타입데프
description: C++ 빌드 인사이트 SDK OnTraceInfoFunc 유형 def 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnTraceInfoFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b987d4db9852c2e52c148bb91015ad414c04d41b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329015"
---
# <a name="ontraceinfofunc-typedef"></a>온트레이스인포푼크 타입데프

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

`OnTraceInfoFunc` typedef는 [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 및 [RELOG_CALLBACKS](relog-callbacks-struct.md) 구조에 사용되는 함수 시그니처 중 하나입니다.

## <a name="syntax"></a>구문

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnTraceInfoFunc)(
    const TRACE_INFO_DATA*          traceInfo,
    void*                           callbackContext);
```

### <a name="parameters"></a>매개 변수

*추적 정보*\
현재 분석되거나 다시 기록중인 추적에 대한 정보가 포함된 [TRACE_INFO_DATA](../c-event-data-types/trace-info-data-struct.md) 개체입니다.

*콜백컨텍스트*\
[ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) 또는 [RELOG_DESCRIPTOR](relog-descriptor-struct.md)이 콜백에 대해 설정된 컨텍스트 값입니다.

### <a name="return-value"></a>Return Value

다음에 발생할 CALLBACK_CODE [값을](callback-code-enum.md) 제어합니다.

::: moniker-end
