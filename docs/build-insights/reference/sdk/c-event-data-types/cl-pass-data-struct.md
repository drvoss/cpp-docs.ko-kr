---
title: CL_PASS_DATA 구조
description: C++ 빌드 인사이트 SDK CL_PASS_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CL_PASS_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b0a41e59068ade285f1ffa1a9ce13734ef5f1f32
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325705"
---
# <a name="cl_pass_data-structure"></a>CL_PASS_DATA 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `CL_PASS_DATA` 컴파일 패스를 설명합니다.

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
| `TranslationUnitPassCode` | 실행 중인 컴파일 패스를 식별하는 코드입니다. 자세한 내용은 [TRANSLATION_UNIT_PASS_CODE](translation-unit-pass-code-enum.md)를 참조하십시오. |
| `InputSourcePath` | 이 컴파일 패스가 실행되는 C 또는 C++ 소스 파일입니다. |
| `OutputObjectPath` | 컴파일러에서 생성되는 개체 파일입니다. |

::: moniker-end
