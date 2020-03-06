---
title: INVOCATION_VERSION_DATA 구조체
description: C++ BUILD Insights SDK INVOCATION_VERSION_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_VERSION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 040b0f90b14133ec2b25f7a12d35b88d382c4f7a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335131"
---
# <a name="invocation_version_data-structure"></a>INVOCATION_VERSION_DATA 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`INVOCATION_VERSION_DATA` 구조체는 버전 번호를 정수 계열 값 그룹으로 설명 합니다.

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
| `VersionMajor` | 버전의 주 번호입니다. |
| `VersionMinor` | 버전의 부 번호입니다. |
| `BuildNumberMajor` | 빌드의 주 번호입니다. |
| `BuildNumberMinor` | 빌드의 부 번호입니다. |

::: moniker-end
