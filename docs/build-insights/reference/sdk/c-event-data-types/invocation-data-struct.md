---
title: INVOCATION_DATA 구조체
description: C++ BUILD Insights SDK INVOCATION_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b2e8ddcf79201d8bcbbb8eb298b96b5c7680f90e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335143"
---
# <a name="invocation_data-structure"></a>INVOCATION_DATA 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`INVOCATION_DATA` 구조에서는 컴파일러 또는 링커 호출을 설명 합니다.

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
| `MSVCToolCode` | 호출의 형식을 식별 하는 코드입니다. 자세한 내용은 [MSVC_TOOL_CODE](msvc-tool-code-enum.md)를 참조 하세요. |
| `ToolVersion` | 호출 된 도구의 버전을 정수 계열 값 그룹으로 저장 하는 개체입니다. |
| `ToolVersionString` | 호출 된 도구의 버전을 텍스트 형식으로 설명 합니다. |
| `WorkingDirectory` | 호출을 수행한 디렉터리입니다. |
| `ToolPath` | 호출 된 도구의 절대 경로입니다. |

::: moniker-end
