---
title: 온분석이벤트펀크 타입데프
description: C++ 빌드 인사이트 SDK OnAnalysisEventFunc 유형 def 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnAnalysisEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: eacd174279caff0db22586d5e40d3a866afc4459
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329121"
---
# <a name="onanalysiseventfunc-typedef"></a>온분석이벤트펀크 타입데프

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

`OnAnalysisEventFunc` typedef는 [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 구조에 사용되는 함수 시그니처 중 하나입니다.

## <a name="syntax"></a>구문

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnAnalysisEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    void*                           callbackContext);
```

### <a name="parameters"></a>매개 변수

*이벤트 스택*\
현재 이벤트의 이벤트 스택입니다. 이벤트 스택에 대한 자세한 내용은 [이벤트](../event-table.md)를 참조하십시오.

*콜백컨텍스트*\
[ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) 또는 [RELOG_DESCRIPTOR](relog-descriptor-struct.md)이 콜백에 대해 설정된 컨텍스트 값입니다.

### <a name="return-value"></a>Return Value

다음에 발생할 CALLBACK_CODE [값을](callback-code-enum.md) 제어합니다.

::: moniker-end
