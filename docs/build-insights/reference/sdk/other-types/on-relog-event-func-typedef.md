---
title: 온리로그이벤트펀크 타입데프
description: C ++ 빌드 인사이트 SDK OnRelogEventFunc 형식 def 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnRelogEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2df8646d530c089b1239978d716b2b619a5b4b61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329077"
---
# <a name="onrelogeventfunc-typedef"></a>온리로그이벤트펀크 타입데프

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

`OnRelogEventFunc` typedef는 [RELOG_CALLBACKS](relog-callbacks-struct.md) 구조에 사용되는 함수 시그니처 중 하나입니다.

## <a name="syntax"></a>구문

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnRelogEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    const void*                     relogSession,
    void*                           callbackContext);
```

### <a name="parameters"></a>매개 변수

*이벤트 스택*\
현재 이벤트의 이벤트 스택입니다. 이벤트 스택에 대한 자세한 내용은 [이벤트](../event-table.md)를 참조하십시오.

*다시 로그세션*\
[InjectEvent를](../functions/inject-event.md)호출할 때 사용할 리로깅 세션 포인터입니다.

*콜백컨텍스트*\
[RELOG_DESCRIPTOR](analysis-descriptor-struct.md)이 콜백에 대해 설정된 컨텍스트 값입니다.

### <a name="return-value"></a>Return Value

다음에 발생할 CALLBACK_CODE [값을](callback-code-enum.md) 제어합니다.

::: moniker-end
