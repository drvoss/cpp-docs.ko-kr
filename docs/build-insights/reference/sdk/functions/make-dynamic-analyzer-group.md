---
title: 메이크다이내믹분석기그룹
description: C++ 빌드 인사이트 SDK MakeDynamicAnalyzerGroup 함수 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 148eeea41f29ac6dd75653feed7f3f3f8c301911
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323968"
---
# <a name="makedynamicanalyzergroup"></a>메이크다이내믹분석기그룹

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `MakeDynamicAnalyzerGroup` 함수는 동적 분석기 그룹을 만드는 데 사용됩니다. 분석기 그룹의 구성원은 추적의 모든 이벤트가 분석될 때까지 이벤트를 왼쪽에서 오른쪽으로 하나씩 받습니다.

## <a name="syntax"></a>구문

```cpp
auto MakeDynamicAnalyzerGroup(std::vector<IAnalyzer*> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::shared_ptr<IAnalyzer>> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::unique_ptr<IAnalyzer>> analyzers);
```

### <a name="parameters"></a>매개 변수

*분석기*\
동적 분석기 그룹에 포함된 [IAnalyzer](../other-types/ianalyzer-class.md) 포인터의 벡터입니다. 이러한 포인터는 원시, `std::unique_ptr`또는 `std::shared_ptr`.

### <a name="return-value"></a>Return Value

동적 분석기 그룹입니다. **자동** 키워드를 사용하여 반환 값을 캡처합니다.

## <a name="remarks"></a>설명

정적 분석기 그룹과 달리 동적 분석기 그룹의 구성원을 컴파일 타임에 알 필요가 없습니다. 프로그램 입력에 따라 또는 컴파일 타임에 알 수 없는 다른 값을 기반으로 런타임에 분석기 그룹 구성원을 선택할 수 있습니다. 정적 분석기 그룹과 달리 동적 분석기 그룹 내의 [IAnalyzer](../other-types/ianalyzer-class.md) 포인터에는 다형성 동작이 있으며 가상 함수 호출이 올바르게 전달됩니다. 이러한 유연성은 이벤트 처리 시간이 느려질 수 있습니다. 모든 분석기 그룹 구성원이 컴파일 타임에 알려져 있고 다형성 동작이 필요하지 않은 경우 정적 분석기 그룹을 사용하는 것이 좋습니다. 정적 분석기 그룹을 사용하려면 [대신 MakeStaticAnalyzerGroup을](make-static-analyzer-group.md) 호출합니다.

동적 분석기 그룹은 정적 분석기 그룹 내부에 캡슐화될 수 있습니다. 그것은 [확인정적 분석기 그룹에](make-static-analyzer-group.md)주소를 전달하여 수행됩니다. 동적 분석기 그룹을 정적 분석기 그룹만 허용하는 [Analyze와](analyze.md)같은 함수에 전달하는 데 이 기술을 사용합니다.

::: moniker-end
