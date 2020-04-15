---
title: FUNCTION_DATA 구조
description: C++ 빌드 인사이트 SDK FUNCTION_DATA 구조 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FUNCTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ec715192e3480932d351cdb4be1443c329a4868b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325535"
---
# <a name="function_data-structure"></a>FUNCTION_DATA 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `FUNCTION_DATA` 함수를 설명합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct FUNCTION_DATA_TAG
{
    const char*         Name;

} FUNCTION_DATA;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `Name` | UTF-8로 인코딩된 함수의 이름입니다. |

::: moniker-end
