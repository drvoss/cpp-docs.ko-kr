---
title: TRANSLATION_UNIT_PASS_CODE 열거형
description: C++ BUILD Insights SDK TRANSLATION_UNIT_PASS_CODE 열거형 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRANSLATION_UNIT_PASS_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1219eed98fd01e8c91d8750977e2d8ca4498d649
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335047"
---
# <a name="translation_unit_pass_code-enum"></a>TRANSLATION_UNIT_PASS_CODE 열거형

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`TRANSLATION_UNIT_PASS_CODE` 열거형입니다.

## <a name="members"></a>멤버

| 이름 | 값 | 설명 |
|--|--|--|
| `TRANSLATION_UNIT_PASS_CODE_FRONT_END` | 0 (0x00000000) | 소스 코드를 구문 분석 하 고 중간 언어로 변환 하는 프런트 엔드 패스입니다. |
| `TRANSLATION_UNIT_PASS_CODE_BACK_END` | 1 (0x00000001) | 중간 언어를 최적화 하 고 기계어 코드로 변환 하는 백 엔드 패스입니다. |

## <a name="remarks"></a>주의

C SDK 함수에서 사용 됩니다.

::: moniker-end
