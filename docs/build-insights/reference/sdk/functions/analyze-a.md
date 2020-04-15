---
title: 분석A
description: C++ 빌드 인사이트 SDK AnalyzeA 함수 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalyzeA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7c7602c49ab5f3ce67693424019e253727563293
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324139"
---
# <a name="analyzea"></a>분석A

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `AnalyzeA` 함수는 ETW(Windows) 추적에 대한 입력 이벤트 추적에서 읽은 MSVC 이벤트를 분석하는 데 사용됩니다.

## <a name="syntax"></a>구문

```cpp
enum RESULT_CODE AnalyzeA(
    const char*                inputLogFile,
    const ANALYSIS_DESCRIPTOR* analysisDescriptor);
```

### <a name="parameters"></a>매개 변수

*입력로그파일*\
이벤트를 읽으려는 입력 ETW 추적입니다.

*분석설명자*\
[ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) 개체에 대한 포인터입니다. 이 개체를 사용하여 분석을 구성합니다.

### <a name="return-value"></a>Return Value

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

::: moniker-end
