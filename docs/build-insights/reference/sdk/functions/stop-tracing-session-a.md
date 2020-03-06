---
title: StopTracingSessionA
description: C++ BUILD Insights SDK StopTracingSessionA 함수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 12f0c7a9665c47f36fb5e88d799673918017bb98
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334195"
---
# <a name="stoptracingsessiona"></a>StopTracingSessionA

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`StopTracingSessionA` 함수는 진행 중인 추적 세션을 중지 하 고 원시 추적 파일을 생성 합니다. [분석,](analyze.md) [AnalzeA](analyze-a.md)및 [AnalyzeW](analyze-w.md) 함수에 원시 추적 파일을 전달 하 여 분석 세션을 시작할 수 있습니다. 원시 추적 파일을 [Relog](relog.md), [reloga](relog-a.md)및 [reloga](relog-w.md) 함수로 전달 하 여 relogging 세션을 시작할 수도 있습니다. `StopTracingSessionA`를 호출 하는 실행 파일에는 관리자 권한이 있어야 합니다.

## <a name="syntax"></a>구문

```cpp
enum RESULT_CODE StopTracingSessionA(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>매개 변수

*세션 이름*\
중지할 추적 세션의 이름입니다. [StartTracingSession](start-tracing-session.md), [StartTracingSessionA](start-tracing-session-a.md)또는 [StartTracingSessionW](start-tracing-session-w.md)에 전달 된 것과 동일한 세션 이름을 사용 합니다.

*Outputlogfile*\
원시 추적을 저장 해야 하는 최종 출력 로그 파일의 경로입니다.

*통계*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) 개체에 대 한 포인터입니다. `StopTracingSessionA`는를 반환 하기 전에이 개체에 추적 컬렉션 통계를 씁니다.

### <a name="return-value"></a>반환 값

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

::: moniker-end
