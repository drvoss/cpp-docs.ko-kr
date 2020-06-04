---
title: SYMBOL_NAME_DATA 구조
description: C++ 빌드 인사이트 SDK SYMBOL_NAME_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SYMBOL_NAME_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1217572f20a772fde629533d6ab170c14dc5b5e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325347"
---
# <a name="symbol_name_data-structure"></a>SYMBOL_NAME_DATA 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `SYMBOL_NAME_DATA` 컴파일러 프런트 엔드 기호를 설명합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct SYMBOL_NAME_DATA_TAG
{
    unsigned long long  Key;
    const char*         Name;

} SYMBOL_NAME_DATA;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `Key` | 기호의 키입니다. 이 값은 분석중인 추적 내에서 고유합니다. |
| `Name` | 기호의 이름입니다. |

## <a name="remarks"></a>설명

두 개의 서로 다른 컴파일러 프런트 엔드 패스에서 오는 기호는 이름이 같지만 키는 다를 수 있습니다. 이 경우 기호 이름을 사용하여 두 형식이 동일한지 확인합니다.

::: moniker-end
