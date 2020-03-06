---
title: AnalysisControl enum 클래스
description: C++ BUILD Insights SDK AnalysisControl 열거형 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalysisControl
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: cf162c11e0a7109b8d733dab79df80782398e14d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334123"
---
# <a name="analysiscontrol-enum-class"></a>AnalysisControl enum 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`AnalysisControl` enum 클래스는 분석 또는 다시 로깅 세션의 흐름을 제어 하는 데 사용 됩니다. [Ianalyzer](ianalyzer-class.md) 또는 [ire로거가](irelogger-class.md) 멤버 함수에서 `AnalysisControl` 코드를 반환 하 여 다음에 수행 해야 하는 작업을 제어 합니다.

## <a name="members"></a>멤버

|  |  |
|--|--|
| `BLOCK` | 분석기 또는 재로 거 거 그룹에서 현재 이벤트가 더 이상 전파 되지 않도록 합니다. |
| `CANCEL` | 현재 분석 또는 다시 로깅 세션을 취소 합니다. |
| `CONTINUE` | 현재 분석을 계속 하거나 세션을 다시 기록 합니다. 현재 이벤트를 다음 분석기 또는 재로 거 group 멤버로 전파 합니다. |
| `FAILURE` | 현재 분석 또는 다시 로깅 세션을 취소 하 고 오류를 알립니다. |

::: moniker-end
