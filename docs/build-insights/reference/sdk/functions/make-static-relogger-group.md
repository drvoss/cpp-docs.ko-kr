---
title: 메이크스테틱 리로거그룹
description: C ++ 빌드 통찰력 SDK 확인StaticReloggerGroup 기능 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 75b638537cb8e0cdeeb5476a3f5277e8e90d9baf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323907"
---
# <a name="makestaticreloggergroup"></a>메이크스테틱 리로거그룹

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `MakeStaticReloggerGroup` 함수는 [Relog](relog.md)와 같은 함수에 전달될 수 있는 정적 relogger 그룹을 만드는 데 사용됩니다. relogger 그룹의 구성원은 추적의 모든 이벤트가 처리될 때까지 이벤트를 왼쪽에서 오른쪽으로 하나씩 받습니다.

## <a name="syntax"></a>구문

```cpp
template <typename... TReloggerPtrs>
auto MakeStaticReloggerGroup(TReloggerPtrs... reloggers);
```

### <a name="parameters"></a>매개 변수

*트레로거 프터*\
이 매개 변수는 항상 추론됩니다.

*리로거*\
정적 relogger 그룹에 포함 된 [IRelogger](../other-types/irelogger-class.md) 포인터의 매개 변수 팩. 이러한 포인터는 원시, `std::unique_ptr`또는 `std::shared_ptr`. [IAnalyzer](../other-types/ianalyzer-class.md) 포인터는 상속 `IRelogger` 관계때문에 포인터로도 간주됩니다.

### <a name="return-value"></a>Return Value

정적 리로거 그룹입니다. **자동** 키워드를 사용하여 반환 값을 캡처합니다.

## <a name="remarks"></a>설명

동적 relogger 그룹과 달리, 정적 relogger 그룹의 구성원은 컴파일 시간에 알려져 있어야 합니다. 또한 정적 리로거 그룹에는 다형성 동작이 없는 [IRelogger](../other-types/irelogger-class.md) 포인터가 포함되어 있습니다. 정적 리로거 그룹을 사용하여 ETW(Windows용 이벤트 추적) 추적을 분석하는 경우 인터페이스 호출은 `IRelogger` 항상 relogger 그룹 구성원이 직접 가리키는 개체로 확인됩니다. 이러한 유연성 손실은 이벤트 처리 시간이 빨라집니다. 컴파일 타임에 리로거 그룹의 구성원을 알 수 없거나 `IRelogger` 포인터에 다형성 동작이 필요한 경우 동적 relogger 그룹을 사용하는 것이 좋습니다. 대신 [MakeDynamicReloggerGroup을](make-dynamic-relogger-group.md) 호출 하 여 동적 relogger 그룹을 사용할 수 있습니다.

::: moniker-end
