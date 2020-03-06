---
title: MakeStaticAnalyzerGroup
description: C++ BUILD Insights SDK MakeStaticAnalyzerGroup 함수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5eabb0fcbb0a0bb0eea0f4e6bbf27b8e4c53c3ab
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334393"
---
# <a name="makestaticanalyzergroup"></a>MakeStaticAnalyzerGroup

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`MakeStaticAnalyzerGroup` 함수는 [분석](analyze.md) 또는 [Relog](relog.md)와 같은 함수에 전달할 수 있는 정적 분석기 그룹을 만드는 데 사용 됩니다. 분석기 그룹의 멤버는 추적의 모든 이벤트가 분석 될 때까지 왼쪽에서 오른쪽으로 하나씩 이벤트를 수신 합니다.

## <a name="syntax"></a>구문

```cpp
template <typename... TAnalyzerPtrs>
auto MakeStaticAnalyzerGroup(TAnalyzerPtrs... analyzers);
```

### <a name="parameters"></a>매개 변수

*TAnalyzerPtrs*\
이 매개 변수는 항상 추론 됩니다.

*분석기*\
정적 분석기 그룹에 포함 된 [Ianalyzer](../other-types/ianalyzer-class.md) 포인터의 매개 변수 팩입니다. 이러한 포인터는 raw, `std::unique_ptr`또는 `std::shared_ptr`수 있습니다.

### <a name="return-value"></a>반환 값

정적 분석기 그룹입니다. **Auto** 키워드를 사용 하 여 반환 값을 캡처합니다.

## <a name="remarks"></a>주의

동적 분석기 그룹과 달리 정적 분석기 그룹의 멤버는 컴파일 타임에 알고 있어야 합니다. 또한 정적 분석기 그룹에는 다형성 동작이 없는 [Ianalyzer](../other-types/ianalyzer-class.md) 포인터가 포함 됩니다. 정적 분석기 그룹을 사용 하 여 ETW (ETW(Windows용 이벤트 추적)) 추적을 분석 하는 경우 `IAnalyzer` 인터페이스를 호출 하면 항상 analyzer 그룹 멤버가 가리키는 개체로 확인 됩니다. 이러한 유연성 손실에는 더 빠른 이벤트 처리 시간이 발생할 수 있습니다. 컴파일 시간에 분석기 그룹의 멤버를 알 수 없거나 `IAnalyzer` 포인터에 다형 동작이 필요한 경우 동적 분석기 그룹을 사용 하는 것이 좋습니다. 동적 분석기 그룹을 사용 하려면 대신 [MakeDynamicAnalyzerGroup](make-static-analyzer-group.md) 를 호출 합니다.

::: moniker-end
