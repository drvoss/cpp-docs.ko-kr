---
title: CL_PASS_DATA 구조체
description: C++ BUILD Insights SDK CL_PASS_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CL_PASS_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3df5b5bc1cddbadc4a4d432ae021dd8b338c532e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335257"
---
# <a name="cl_pass_data-structure"></a>CL_PASS_DATA 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`CL_PASS_DATA` 구조는 컴파일 패스를 설명 합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct CL_PASS_DATA_TAG
{
    int                         TranslationUnitPassCode;
    const wchar_t*              InputSourcePath;
    const wchar_t*              OutputObjectPath;

} CL_PASS_DATA;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `TranslationUnitPassCode` | 실행 되는 컴파일 패스를 식별 하는 코드입니다. 자세한 내용은 [TRANSLATION_UNIT_PASS_CODE](translation-unit-pass-code-enum.md)를 참조 하세요. |
| `InputSourcePath` | 이 컴파일 패스가 C++ 실행 되는 C 또는 소스 파일입니다. |
| `OutputObjectPath` | 컴파일러에서 생성 되는 개체 파일입니다. |

::: moniker-end
