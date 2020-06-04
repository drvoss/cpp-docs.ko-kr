---
title: 스톱앤로그트레이싱세션
description: C ++ 빌드 인사이트 SDK StopAndRelogTracingSession 기능 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1f6f5af63d25504226707d977791430463374328
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323663"
---
# <a name="stopandrelogtracingsession"></a>스톱앤로그트레이싱세션

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `StopAndRelogTracingSession` 함수는 진행 중인 추적 세션을 중지하고 임시 파일에 결과 추적을 저장합니다. 그런 다음 임시 파일을 입력으로 사용하여 리로깅 세션이 즉시 시작됩니다. 리로깅 세션에서 생성된 마지막 다시 기록된 추적은 호출인이 지정한 파일에 저장됩니다. 이 함수를 호출하는 실행 에는 관리자 권한이 있어야 합니다.

## <a name="syntax"></a>구문

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const char*                                   sessionName,
    const char*                                   outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const wchar_t*                                sessionName,
    const wchar_t*                                outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>매개 변수

*세션 이름*\
중지할 추적 세션의 이름입니다. [StartTracingSession,](start-tracing-session.md) [StartTracingSessionA](start-tracing-session-a.md)또는 [StartTracingSessionW에](start-tracing-session-w.md)전달된 세션 이름과 동일한 세션 이름을 사용합니다.

*출력로그파일*\
리로깅 세션에서 생성된 다시 기록된 추적을 작성하는 파일입니다.

*통계*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) 개체에 대한 포인터입니다. `StopAndRelogTracingSession`반환하기 전에 이 개체에 추적 수집 통계를 씁니다.

*숫자분석패스*\
추적에서 실행되는 분석 횟수가 전달됩니다. 트레이스는 분석 패스당 한 번 제공된 분석기 그룹을 통과합니다.

*시스템이벤트보존플래그*\
다시 기록된 추적에 보관할 시스템 ETW 이벤트를 지정하는 [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md) 비트 마스크입니다.

*분석기 그룹*\
리로깅 세션의 분석 단계에 사용되는 분석기 그룹입니다. [MakeStaticAnalyzerGroup에](make-static-analyzer-group.md) 전화하여 분석기 그룹을 만듭니다. [MakeDynamicAnalyzerGroup에서](make-dynamic-analyzer-group.md)얻은 동적 분석기 그룹을 사용하려는 경우 먼저 해당 주소를 에 전달하여 정적 분석기 `MakeStaticAnalyzerGroup`그룹 내부에 캡슐화합니다.

*리로거 그룹*\
*outputLogFile에*지정된 추적 파일로 이벤트를 다시 기록하는 relogger 그룹 . 다시 로거 [그룹을 만들려면 정적 Relogger 그룹 확인을](make-static-relogger-group.md) 호출합니다. [MakeDynamicReloggerGroup에서](make-dynamic-relogger-group.md)얻은 동적 relogger 그룹을 사용 하려는 경우 먼저 에 주소를 전달 하 여 정적 relogger 그룹 내에서 캡슐화 `MakeStaticReloggerGroup`합니다.

### <a name="return-value"></a>Return Value

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

### <a name="remarks"></a>설명

입력 추적은 분석기 그룹 번호를 통해 *전달됩니다OfAnalysisPasses* 시간. 패스를 다시 기록하는 데는 유사한 옵션이 없습니다. 모든 분석 패스가 완료된 후 추적은 relogger 그룹을 한 번만 전달합니다.

relogger 클래스 내에서 CPU 샘플 과 같은 시스템 이벤트의 리로깅은 지원되지 않습니다. *시스템이벤트RetentionFlags* 매개 변수를 사용하여 출력 추적에 유지할 시스템 이벤트를 결정합니다.

::: moniker-end
