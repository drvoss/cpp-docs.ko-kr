---
title: 스톱앤분석트레이싱세션
description: C ++ 빌드 인사이트 SDK StopAndanalyzeTracingSession 함수 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9c9bd4a092c22dfcdfb6d463b74207ec11ee6d64
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323698"
---
# <a name="stopandanalyzetracingsession"></a>스톱앤분석트레이싱세션

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `StopAndAnalyzeTracingSession` 함수는 진행 중인 추적 세션을 중지하고 임시 파일에 결과 추적을 저장합니다. 그런 다음 분석 세션이 임시 파일을 입력으로 사용하여 즉시 시작됩니다. 이 함수를 호출하는 실행 에는 관리자 권한이 있어야 합니다.

## <a name="syntax"></a>구문

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE StopAndAnalyzeTracingSession(
    const char*                                   sessionName,
    unsigned                                      numberOfAnalysisPasses,
    TRACING_SESSION_STATISTICS*                   statistics,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE StopAndAnalyzeTracingSession(
    const wchar_t*                                sessionName,
    unsigned                                      numberOfAnalysisPasses,
    TRACING_SESSION_STATISTICS*                   statistics,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>매개 변수

*세션 이름*\
중지할 추적 세션의 이름입니다. [StartTracingSession,](start-tracing-session.md) [StartTracingSessionA](start-tracing-session-a.md)또는 [StartTracingSessionW에](start-tracing-session-w.md)전달된 세션 이름과 동일한 세션 이름을 사용합니다.

*숫자분석패스*\
추적에서 실행되는 분석 횟수가 전달됩니다. 트레이스는 분석 패스당 한 번 제공된 분석기 그룹을 통과합니다.

*통계*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) 개체에 대한 포인터입니다. `StopAndAnalyzeTracingSession`반환하기 전에 이 개체에 추적 수집 통계를 씁니다.

*분석기 그룹*\
분석에 사용되는 분석기 그룹입니다. [MakeStaticAnalyzerGroup에](make-static-analyzer-group.md) 전화하여 분석기 그룹을 만듭니다. [MakeDynamicAnalyzerGroup에서](make-dynamic-analyzer-group.md)얻은 동적 분석기 그룹을 사용하려는 경우 먼저 해당 주소를 에 전달하여 정적 분석기 `MakeStaticAnalyzerGroup`그룹 내부에 캡슐화합니다.

### <a name="return-value"></a>Return Value

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

::: moniker-end
