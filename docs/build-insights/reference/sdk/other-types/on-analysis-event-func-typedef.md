---
title: OnAnalysisEventFunc typedef
description: C++ BUILD Insights SDK OnAnalysisEventFunc typedef 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnAnalysisEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d260f6060e759f315589abda82e31c2c2b95a65e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334063"
---
# <a name="onanalysiseventfunc-typedef"></a>OnAnalysisEventFunc typedef

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`OnAnalysisEventFunc` typedef는 [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 구조에서 사용 되는 함수 서명 중 하나입니다.

## <a name="syntax"></a>구문

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnAnalysisEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    void*                           callbackContext);
```

### <a name="parameters"></a>매개 변수

*Eventstack*\
현재 이벤트의 이벤트 스택입니다. 이벤트 스택에 대 한 자세한 내용은 [이벤트](../event-table.md)를 참조 하세요.

*callbackContext*\
[ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) 또는 [RELOG_DESCRIPTOR](relog-descriptor-struct.md)에서이 콜백에 대해 설정 된 컨텍스트 값입니다.

### <a name="return-value"></a>반환 값

다음에 수행 해야 하는 작업을 제어 하는 [CALLBACK_CODE](callback-code-enum.md) 값입니다.

::: moniker-end
