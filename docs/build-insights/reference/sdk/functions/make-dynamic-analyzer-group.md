---
title: MakeDynamicAnalyzerGroup
description: C++ BUILD Insights SDK MakeDynamicAnalyzerGroup 함수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f409d685c6af6514b73cd837d668a962c1a0d01a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334405"
---
# <a name="makedynamicanalyzergroup"></a>MakeDynamicAnalyzerGroup

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`MakeDynamicAnalyzerGroup` 함수는 동적 분석기 그룹을 만드는 데 사용 됩니다. 분석기 그룹의 멤버는 추적의 모든 이벤트가 분석 될 때까지 왼쪽에서 오른쪽으로 하나씩 이벤트를 수신 합니다.

## <a name="syntax"></a>구문

```cpp
auto MakeDynamicAnalyzerGroup(std::vector<IAnalyzer*> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::shared_ptr<IAnalyzer>> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::unique_ptr<IAnalyzer>> analyzers);
```

### <a name="parameters"></a>매개 변수

*분석기*\
동적 분석기 그룹에 포함 된 [Ianalyzer](../other-types/ianalyzer-class.md) 포인터의 벡터입니다. 이러한 포인터는 raw, `std::unique_ptr`또는 `std::shared_ptr`수 있습니다.

### <a name="return-value"></a>반환 값

동적 분석기 그룹입니다. **Auto** 키워드를 사용 하 여 반환 값을 캡처합니다.

## <a name="remarks"></a>주의

정적 분석기 그룹과 달리 동적 분석기 그룹의 멤버는 컴파일 타임에 알 필요가 없습니다. 프로그램 입력을 기반으로 런타임 시 analyzer 그룹 멤버를 선택 하거나 컴파일 타임에 알 수 없는 다른 값을 기준으로 할 수 있습니다. 정적 분석기 그룹과 달리, 동적 분석기 그룹 내의 [Ianalyzer](../other-types/ianalyzer-class.md) 포인터는 다형성 동작을 가지 며 가상 함수 호출은 올바르게 디스패치 됩니다. 이러한 유연성은 이벤트 처리 시간이 느려질 수 있습니다. 컴파일 시간에 모든 분석기 그룹 멤버를 알 수 있으며 다형성 동작이 필요 하지 않은 경우에는 정적 분석기 그룹을 사용 하는 것이 좋습니다. 정적 분석기 그룹을 사용 하려면 대신 [MakeStaticAnalyzerGroup](make-static-analyzer-group.md) 를 호출 합니다.

동적 분석기 그룹은 정적 분석기 그룹 내에 캡슐화 할 수 있습니다. [MakeStaticAnalyzerGroup](make-static-analyzer-group.md)에 해당 주소를 전달 하 여 수행 합니다. 이 기법을 사용 하 여 정적 분석기 그룹을 허용 하는 [분석과](analyze.md)같은 함수에 동적 분석기 그룹을 전달할 수 있습니다.

::: moniker-end
