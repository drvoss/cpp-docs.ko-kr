---
title: TRANSLATION_UNIT_PASS_CODE 열거형
description: C++ 빌드 인사이트 SDK TRANSLATION_UNIT_PASS_CODE 열거형 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRANSLATION_UNIT_PASS_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b0162d7e53bb7ee7035b94a6b640f6db87cd8b8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325286"
---
# <a name="translation_unit_pass_code-enum"></a>TRANSLATION_UNIT_PASS_CODE 열거형

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

`TRANSLATION_UNIT_PASS_CODE` 열거형입니다.

## <a name="members"></a>멤버

| 이름 | 값 | Description |
|--|--|--|
| `TRANSLATION_UNIT_PASS_CODE_FRONT_END` | 0 (0x00000000) | 소스 코드를 구문 분석하여 중간 언어로 변환하는 프런트 엔드 패스입니다. |
| `TRANSLATION_UNIT_PASS_CODE_BACK_END` | 1 (0x00000001) | 중간 언어를 최적화하고 기계 코드로 변환하는 백 엔드 패스. |

## <a name="remarks"></a>설명

C SDK 함수에서 사용됩니다.

::: moniker-end
