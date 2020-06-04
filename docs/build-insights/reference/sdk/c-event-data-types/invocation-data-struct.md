---
title: INVOCATION_DATA 구조
description: C++ 빌드 인사이트 SDK INVOCATION_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4e1f428facac413d7a4a5c059452dd8cdb07be4c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325481"
---
# <a name="invocation_data-structure"></a>INVOCATION_DATA 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `INVOCATION_DATA` 컴파일러 또는 링커 호출을 설명합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct INVOCATION_DATA_TAG
{
    int                         MSVCToolCode;

    INVOCATION_VERSION_DATA     ToolVersion;

    const char*                 ToolVersionString;
    const wchar_t*              WorkingDirectory;
    const wchar_t*              ToolPath;

} INVOCATION_DATA;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `MSVCToolCode` | 호출의 형식을 식별하는 코드입니다. 자세한 내용은 [MSVC_TOOL_CODE](msvc-tool-code-enum.md)를 참조하십시오. |
| `ToolVersion` | 호출된 도구의 버전을 정수 값 그룹으로 저장하는 개체입니다. |
| `ToolVersionString` | 텍스트 형식으로 호출된 도구의 버전을 설명합니다. |
| `WorkingDirectory` | 호출이 만들어진 디렉터리입니다. |
| `ToolPath` | 호출된 도구의 절대 경로입니다. |

::: moniker-end
