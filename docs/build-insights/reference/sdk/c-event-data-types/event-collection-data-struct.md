---
title: EVENT_COLLECTION_DATA 구조체
description: C++ BUILD Insights SDK EVENT_COLLECTION_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_COLLECTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1a622a8459b6aa6d9dcbe0faaf90ae545b449466
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335245"
---
# <a name="event_collection_data-structure"></a>EVENT_COLLECTION_DATA 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`EVENT_COLLECTION_DATA` 구조체는 [EVENT_DATA](event-data-struct.md) 요소의 배열을 설명 합니다.

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
| `Elements` | 배열의 첫 번째 `EVENT_DATA` 요소에 대 한 포인터입니다. |

::: moniker-end
