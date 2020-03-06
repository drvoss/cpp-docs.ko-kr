---
title: StartTracingSessionW
description: C++ BUILD Insights SDK StartTracingSessionW 함수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StartTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 072b02166f2841e6d210306ef75c9fc64fea9778
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334249"
---
# <a name="starttracingsessionw"></a>StartTracingSessionW

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`StartTracingSessionW` 함수는 추적 세션을 시작 합니다. 이 함수를 호출 하는 실행 파일에는 관리자 권한이 있어야 합니다.

## <a name="syntax"></a>구문

```cpp
enum RESULT_CODE StartTracingSessionW(
    const wchar_t*                 sessionName,
    const TRACING_SESSION_OPTIONS* options);
```

### <a name="parameters"></a>매개 변수

*세션 이름*\
시작할 추적 세션의 이름입니다. [StopTracingSessionW](stop-tracing-session-w.md)또는 기타 stop 추적 함수를 호출할 때 동일한 이름을 사용 합니다.

*옵션*\
[TRACING_SESSION_OPTIONS](../other-types/tracing-session-options-struct.md) 개체에 대 한 포인터입니다. 이 개체를 사용 하 여 추적 세션에서 수집 해야 하는 이벤트를 선택할 수 있습니다.

### <a name="return-value"></a>반환 값

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

::: moniker-end
