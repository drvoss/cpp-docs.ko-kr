---
title: 분석
description: C++ 빌드 인사이트 SDK 분석 함수 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyze
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 08b3643270cc785b3fbea36720d192b4a1473104
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324103"
---
# <a name="analyze"></a>분석

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `Analyze` 함수는 C++ 빌드를 추적하는 동안 MSVC에서 얻은 ETW(Windows용 이벤트 추적) 추적을 분석하는 데 사용됩니다. ETW 추적의 이벤트는 호출자가 제공하는 분석기 그룹에 순차적으로 전달됩니다. 이 함수는 이벤트 스트림을 분석기 그룹에 연속으로 여러 번 전달할 수 있는 다중 패스 분석을 지원합니다.

## <a name="syntax"></a>구문

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const char*                                   inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const wchar_t*                                inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>매개 변수

*T분석기 그룹구성원*\
이 매개 변수는 항상 추론됩니다.

*입력로그파일*\
이벤트를 읽으려는 입력 ETW 추적입니다.

*번호OfPasses*\
입력 추적에서 실행되는 분석 패스 수입니다. 트레이스는 분석 패스당 한 번 제공된 분석기 그룹을 통과합니다.

*분석기 그룹*\
분석에 사용되는 분석기 그룹입니다. [MakeStaticAnalyzerGroup에](make-static-analyzer-group.md) 전화하여 분석기 그룹을 만듭니다. [MakeDynamicAnalyzerGroup에서](make-dynamic-analyzer-group.md)얻은 동적 분석기 그룹을 사용하려면 먼저 주소를 에 전달하여 정적 분석기 `MakeStaticAnalyzerGroup`그룹 내부에 캡슐화합니다.

### <a name="return-value"></a>Return Value

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

::: moniker-end
