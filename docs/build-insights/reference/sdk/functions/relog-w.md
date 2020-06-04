---
title: 리로그W
description: C++ 빌드 인사이트 SDK RelogW 함수 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c5d5f6e35c7cd24d2324ce1d8a0434d9048b1d85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323805"
---
# <a name="relogw"></a>리로그W

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `RelogW` 함수는 ETW(Windows용 입력 이벤트 추적) 추적에서 MSVC 이벤트를 읽고 수정된 새 ETW 추적에 기록하는 데 사용됩니다.

## <a name="syntax"></a>구문

```cpp
enum RESULT_CODE RelogW(
    const wchar_t*          inputLogFile,
    const wchar_t*          outputLogFile,
    const RELOG_DESCRIPTOR* relogDescriptor);
```

### <a name="parameters"></a>매개 변수

*입력로그파일*\
이벤트를 읽으려는 입력 ETW 추적입니다.

*출력로그파일*\
새 이벤트를 작성할 파일입니다.

*다시 로그 설명자*\
[RELOG_DESCRIPTOR](../other-types/relog-descriptor-struct.md) 개체에 대한 포인터입니다. 이 개체를 사용하여 리로깅 세션을 구성합니다.

### <a name="return-value"></a>Return Value

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

::: moniker-end
