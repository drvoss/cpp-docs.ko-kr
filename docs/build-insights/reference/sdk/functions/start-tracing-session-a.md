---
title: 스타트트레이싱세션A
description: C++ 빌드 인사이트 SDK 스타트레이싱SessionA 함수 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StartTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1c184e214c7f55bb7eaa6eb03f21e792ef90fa40
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323773"
---
# <a name="starttracingsessiona"></a>스타트트레이싱세션A

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

함수가 `StartTracingSessionA` 추적 세션을 시작합니다. 이 함수를 호출하는 실행 에는 관리자 권한이 있어야 합니다.

## <a name="syntax"></a>구문

```cpp
enum RESULT_CODE StartTracingSessionA(
    const char*                    sessionName,
    const TRACING_SESSION_OPTIONS* options);
```

### <a name="parameters"></a>매개 변수

*세션 이름*\
시작할 추적 세션의 이름입니다. [StopTracingSessionA](stop-tracing-session.md) 또는 다른 정지 추적 함수를 호출할 때 동일한 이름을 사용합니다.

*옵션*\
[TRACING_SESSION_OPTIONS](../other-types/tracing-session-options-struct.md) 개체에 대한 포인터입니다. 이 개체를 사용하여 추적 세션에서 수집할 이벤트를 선택합니다.

### <a name="return-value"></a>Return Value

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

::: moniker-end
