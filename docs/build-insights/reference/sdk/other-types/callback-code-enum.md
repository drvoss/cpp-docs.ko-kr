---
title: CALLBACK_CODE 열거형
description: C++ 빌드 인사이트 SDK CALLBACK_CODE 열거형 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CALLBACK_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d0d3dcc70040f562cd40755188e545f709a807b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329185"
---
# <a name="callback_code-enum"></a>CALLBACK_CODE 열거형

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

`CALLBACK_CODE` 열거형은 분석 또는 리로깅 세션의 흐름을 제어하는 데 사용됩니다. [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 또는 [RELOG_CALLBACKS](relog-callbacks-struct.md) 함수에서 CALLBACK_CODE 값을 반환하여 다음에 발생할 일을 제어합니다.

## <a name="members"></a>멤버

| 이름 | 값 | Description |
|--|--|--|
| `CALLBACK_CODE_ANALYSIS_SUCCESS` | 1 (0x00000001) | 현재 분석 또는 리로깅 세션을 정상적으로 계속합니다. |
| `CALLBACK_CODE_ANALYSIS_FAILURE` | 2 (0x00000002) | 현재 분석 또는 리로깅 세션을 취소하고 오류를 시그널합니다. |
| `CALLBACK_CODE_ANALYSIS_CANCEL` | 4 (0x000000004) | 현재 분석 또는 리로깅 세션을 취소합니다. |

::: moniker-end
