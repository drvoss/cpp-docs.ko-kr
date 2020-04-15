---
title: INVOCATION_VERSION_DATA 구조
description: C++ 빌드 인사이트 SDK INVOCATION_VERSION_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_VERSION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1211b4eb999fd63767af71c6884d7d20d6920df0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325459"
---
# <a name="invocation_version_data-structure"></a>INVOCATION_VERSION_DATA 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `INVOCATION_VERSION_DATA` 버전 번호를 정수 값 그룹으로 설명합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct INVOCATION_VERSION_DATA_TAG
{
    unsigned short VersionMajor;
    unsigned short VersionMinor;
    unsigned short BuildNumberMajor;
    unsigned short BuildNumberMinor;

} INVOCATION_VERSION_DATA;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `VersionMajor` | 버전의 주요 번호입니다. |
| `VersionMinor` | 버전의 사소한 번호입니다. |
| `BuildNumberMajor` | 빌드의 주요 숫자입니다. |
| `BuildNumberMinor` | 빌드의 작은 숫자입니다. |

::: moniker-end
