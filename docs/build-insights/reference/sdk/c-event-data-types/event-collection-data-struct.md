---
title: EVENT_COLLECTION_DATA 구조
description: C++ 빌드 인사이트 SDK EVENT_COLLECTION_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_COLLECTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 88ba39ede8c86f47c2e6458332ae005eddc06fda
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325687"
---
# <a name="event_collection_data-structure"></a>EVENT_COLLECTION_DATA 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `EVENT_COLLECTION_DATA` [EVENT_DATA](event-data-struct.md) 요소의 배열을 설명합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct EVENT_COLLECTION_DATA_TAG
{
    unsigned int            Count;
    const EVENT_DATA*       Elements;

} EVENT_COLLECTION_DATA;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `Count` | 배열의 `EVENT_DATA` 요소 수입니다. |
| `Elements` | 배열의 첫 `EVENT_DATA` 번째 요소에 대한 포인터입니다. |

::: moniker-end
