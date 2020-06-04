---
title: ANALYSIS_DESCRIPTOR 구조
description: C++ 빌드 인사이트 SDK ANALYSIS_DESCRIPTOR 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1de7f2a5bc3f02a327daaecf8c2cebc44687ba43
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323606"
---
# <a name="analysis_descriptor-structure"></a>ANALYSIS_DESCRIPTOR 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `ANALYSIS_DESCRIPTOR` 구조는 [AnalyzeA](../functions/analyze-a.md) 및 [AnalyzeW](../functions/analyze-w.md) 함수와 함께 사용됩니다. WINDOWS용 이벤트 추적(ETW) 추적을 분석하는 방법을 설명합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct ANALYSIS_DESCRIPTOR_TAG
{
    unsigned                NumberOfPasses;
    ANALYSIS_CALLBACKS      Callbacks;
    void*                   Context;
} ANALYSIS_DESCRIPTOR;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `NumberOfPasses` | ETW 추적을 통해 수행해야 하는 분석 패스 수입니다. |
| `Callbacks` | 분석 세션 중에 호출할 함수를 지정하는 [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 개체입니다. |
| `Context` | 지정된 모든 콜백 함수에 인수로 전달되는 사용자 제공 컨텍스트`Callbacks` |

## <a name="remarks"></a>설명

구조는 `Callbacks` 비멤버 함수에 대한 포인터만 허용합니다. 개체 포인터로 설정하여 `Context` 이 제한을 해결할 수 있습니다. 이 개체 포인터는 모든 비멤버 콜백 함수에 대한 인수로 전달됩니다. 이 포인터를 사용하여 비멤버 콜백 함수 내에서 멤버 함수를 호출합니다.

::: moniker-end
