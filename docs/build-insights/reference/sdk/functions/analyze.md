---
title: 분석
description: Build C++ Insights SDK는 함수 참조를 분석 합니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyze
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 49161641d1cff1c64261d95bb2caace2f802543a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334435"
---
# <a name="analyze"></a>분석

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`Analyze` 함수는 빌드를 C++ 추적 하는 동안 MSVC에서 가져온 ETW(WINDOWS용 이벤트 추적) (ETW) 추적을 분석 하는 데 사용 됩니다. ETW 추적의 이벤트는 호출자가 제공한 분석기 그룹에 순차적으로 전달 됩니다. 이 함수는 한 행에서 여러 번 이벤트 스트림을 분석기 그룹으로 전달할 수 있도록 하는 다중 패스 분석을 지원 합니다.

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

*TAnalyzerGroupMembers*\
이 매개 변수는 항상 추론 됩니다.

*Inputlogfile*\
이벤트를 읽으려고 하는 입력 ETW 추적입니다.

*numberofpasses*\
입력 추적에서 실행할 분석 패스의 수입니다. Trace는 제공 된 분석기 그룹을 분석 통과 당 한 번씩 전달 합니다.

*analyzerGroup*\
분석에 사용 되는 분석기 그룹입니다. [MakeStaticAnalyzerGroup](make-static-analyzer-group.md) 를 호출 하 여 분석기 그룹을 만듭니다. [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md)에서 가져온 동적 분석기 그룹을 사용 하려면 먼저 해당 주소를 `MakeStaticAnalyzerGroup`으로 전달 하 여 정적 분석기 그룹 내에 캡슐화 합니다.

### <a name="return-value"></a>반환 값

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

::: moniker-end
