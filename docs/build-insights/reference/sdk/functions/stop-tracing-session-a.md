---
title: 스톱트레이싱세션A
description: C++ 빌드 인사이트 SDK StopTracingSessionA 함수 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 15560ecf4959ccda0d617c09d3645750210f331a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323496"
---
# <a name="stoptracingsessiona"></a>스톱트레이싱세션A

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `StopTracingSessionA` 함수는 진행 중인 추적 세션을 중지하고 원시 추적 파일을 생성합니다. 원시 추적 파일은 [분석,](analyze.md) [AnalzeA](analyze-a.md)및 [AnalyzeW](analyze-w.md) 함수로 전달되어 분석 세션을 시작할 수 있습니다. 원시 추적 파일은 [Relog,](relog.md) [RelogA](relog-a.md)및 [RelogW](relog-w.md) 함수로 전달되어 세션 재로깅을 시작할 수도 있습니다. 실행 하기 호출 `StopTracingSessionA` 관리자 권한이 있어야 합니다.

## <a name="syntax"></a>구문

```cpp
enum RESULT_CODE StopTracingSessionA(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>매개 변수

*세션 이름*\
중지할 추적 세션의 이름입니다. [StartTracingSession,](start-tracing-session.md) [StartTracingSessionA](start-tracing-session-a.md)또는 [StartTracingSessionW에](start-tracing-session-w.md)전달된 세션 이름과 동일한 세션 이름을 사용합니다.

*출력로그파일*\
원시 추적을 저장해야 하는 최종 출력 로그 파일에 대한 경로입니다.

*통계*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) 개체에 대한 포인터입니다. `StopTracingSessionA`반환하기 전에 이 개체에 추적 수집 통계를 씁니다.

### <a name="return-value"></a>Return Value

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

::: moniker-end
