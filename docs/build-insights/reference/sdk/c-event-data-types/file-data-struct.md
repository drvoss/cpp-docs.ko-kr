---
title: FILE_DATA 구조
description: C++ 빌드 인사이트 SDK FILE_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6b7b0129c54fa4b1d5285bafb38761da45bab4e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325584"
---
# <a name="file_data-structure"></a>FILE_DATA 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `FILE_DATA` 파일 입력 또는 출력을 설명합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct FILE_DATA_TAG
{
    const wchar_t*      Path;
    int                 TypeCode;

} FILE_DATA;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `Path` | 파일의 절대 경로 |
| `TypeCode` | 파일 형식을 설명하는 코드입니다. 자세한 내용은 [FILE_TYPE_CODE](file-type-code-enum.md)를 참조하십시오. |

::: moniker-end
