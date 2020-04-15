---
title: 온비벤드패스펀크 타입데프
description: C ++ 빌드 인사이트 SDK OnBeginEndPassFunc 유형 def 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnBeginEndPassFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3b3fc453245a47463c29ceeb30dfdc48c79aef35
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329079"
---
# <a name="onbeginendpassfunc-typedef"></a>온비벤드패스펀크 타입데프

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

`OnBeginEndPassFunc` typedef는 [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 및 [RELOG_CALLBACKS](relog-callbacks-struct.md) 구조에 사용되는 함수 시그니처 중 하나입니다.

## <a name="syntax"></a>구문

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnBeginEndPassFunc)(
    void*                           callbackContext);
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `callbackContext` |  |

::: moniker-end
