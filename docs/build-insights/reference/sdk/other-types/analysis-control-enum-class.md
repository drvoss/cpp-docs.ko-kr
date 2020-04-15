---
title: 분석제어 열거형 클래스
description: C++ 빌드 인사이트 SDK 분석제어 열거형 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalysisControl
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e9431f878390127f2cefbe8f0ee42ca509e147de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323638"
---
# <a name="analysiscontrol-enum-class"></a>분석제어 열거형 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

`AnalysisControl` 열거형 클래스는 분석 또는 리로깅 세션의 흐름을 제어하는 데 사용됩니다. `AnalysisControl` [IAnalyzer](ianalyzer-class.md) 또는 [IRelogger](irelogger-class.md) 멤버 함수에서 코드를 반환 하여 다음에 발생할 일을 제어합니다.

## <a name="members"></a>멤버

|  |  |
|--|--|
| `BLOCK` | 분석기 또는 리로거 그룹에서 현재 이벤트가 더 전파되는 것을 방지합니다. |
| `CANCEL` | 현재 분석 또는 리로깅 세션을 취소합니다. |
| `CONTINUE` | 현재 분석 또는 리로깅 세션을 정상적으로 계속합니다. 현재 이벤트를 다음 분석기 또는 리로거 그룹 구성원에게 전파합니다. |
| `FAILURE` | 현재 분석 또는 리로깅 세션을 취소하고 오류를 시그널합니다. |

::: moniker-end
