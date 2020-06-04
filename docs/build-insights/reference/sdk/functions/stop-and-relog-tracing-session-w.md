---
title: 스톱앤로그트레이싱세션W
description: C ++ 빌드 인사이트 SDK StopAndRelogTracingSessionW 함수 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c542ba8f313f30cf5adb069dd02cf3db29ffc532
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323685"
---
# <a name="stopandrelogtracingsessionw"></a>스톱앤로그트레이싱세션W

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `StopAndRelogTracingSessionW` 함수는 진행 중인 추적 세션을 중지하고 임시 파일에 결과 추적을 저장합니다. 그런 다음 임시 파일을 입력으로 사용하여 리로깅 세션이 즉시 시작됩니다. 리로깅 세션에서 생성된 마지막 다시 기록된 추적은 호출인이 지정한 파일에 저장됩니다. 이 함수를 호출하는 실행 에는 관리자 권한이 있어야 합니다.

## <a name="syntax"></a>구문

```cpp
enum RESULT_CODE StopAndRelogTracingSessionW(
    const wchar_t*              sessionName,
    const wchar_t*              outputLogFile,
    TRACING_SESSION_STATISTICS* statistics,
    const RELOG_DESCRIPTOR*     relogDescriptor);
```

### <a name="parameters"></a>매개 변수

*세션 이름*\
중지할 추적 세션의 이름입니다. [StartTracingSession,](start-tracing-session.md) [StartTracingSessionA](start-tracing-session-a.md)또는 [StartTracingSessionW에](start-tracing-session-w.md)전달된 세션 이름과 동일한 세션 이름을 사용합니다.

*출력로그파일*\
리로깅 세션에서 생성된 다시 기록된 추적을 작성하는 파일입니다.

*통계*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) 개체에 대한 포인터입니다. `StopAndRelogTracingSessionW`반환하기 전에 이 개체에 추적 수집 통계를 씁니다.

*분석설명자*\
[RELOG_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) 개체에 대한 포인터입니다. 이 개체를 사용하여 에서 시작되는 리로깅 `StopAndRelogTracingSessionW`세션을 구성합니다.

### <a name="return-value"></a>Return Value

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

::: moniker-end
