---
title: FILE_DATA 구조체
description: C++ BUILD Insights SDK FILE_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 72cae8c8eb81bdb8d94897c46c5af90c89e92ab4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335197"
---
# <a name="file_data-structure"></a>FILE_DATA 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`FILE_DATA` 구조는 파일 입력 또는 출력을 설명 합니다.

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
| `Path` | 파일의 절대 경로입니다. |
| `TypeCode` | 파일의 형식을 설명 하는 코드입니다. 자세한 내용은 [FILE_TYPE_CODE](file-type-code-enum.md)를 참조 하세요. |

::: moniker-end
