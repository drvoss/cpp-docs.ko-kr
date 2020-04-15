---
title: 메이크다이나믹리로거그룹
description: C ++ 빌드 통찰력 SDK 메이크DynamicReloggerGroup 기능 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f49e37f8e1a8b9ca9a800d20b2891a54453095ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323947"
---
# <a name="makedynamicreloggergroup"></a>메이크다이나믹리로거그룹

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `MakeDynamicReloggerGroup` 함수는 동적 리로거 그룹을 만드는 데 사용됩니다. relogger 그룹의 구성원은 추적의 모든 이벤트가 처리될 때까지 이벤트를 왼쪽에서 오른쪽으로 하나씩 받습니다.

## <a name="syntax"></a>구문

```cpp
auto MakeDynamicReloggerGroup(std::vector<IRelogger*> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::shared_ptr<IRelogger>> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::unique_ptr<IRelogger>> reloggers);
```

### <a name="parameters"></a>매개 변수

*리로거*\
동적 리로거 그룹에 포함 된 [IRelogger](../other-types/irelogger-class.md) 포인터의 벡터. 이러한 포인터는 원시, `std::unique_ptr`또는 `std::shared_ptr`. [IAnalyzer](../other-types/ianalyzer-class.md) 포인터는 상속 `IRelogger` 관계때문에 포인터로도 간주됩니다.

### <a name="return-value"></a>Return Value

동적 리로거 그룹입니다. **자동** 키워드를 사용하여 반환 값을 캡처합니다.

## <a name="remarks"></a>설명

정적 relogger 그룹과는 달리, 동적 relogger 그룹의 구성원은 컴파일 타임에 알 필요가 없습니다. 프로그램 입력에 따라 또는 컴파일 타임에 알 수 없는 다른 값을 기반으로 런타임에 relogger 그룹 구성원을 선택할 수 있습니다. 정적 다시 로거 그룹과 달리 동적 relogger 그룹 내의 [IRelogger](../other-types/irelogger-class.md) 포인터는 다형성 동작을 가지고 있으며, 가상 함수 호출이 올바르게 전달됩니다. 이러한 유연성은 이벤트 처리 시간이 느려질 수 있습니다. 모든 relogger 그룹 구성원이 컴파일 타임에 알려진 경우, 당신은 다형성 동작이 필요하지 않은 경우, 정적 relogger 그룹을 사용하는 것이 좋습니다. 정적 리로거 그룹을 사용 하려면, [대신 확인 정적 ReloggerGroup](make-static-relogger-group.md) 를 호출.

동적 relogger 그룹 정적 relogger 그룹 내에서 캡슐화 될 수 있습니다. 당신은 확인에 주소를 [전달정적ReloggerGroup](make-static-relogger-group.md). 동적 relogger 그룹을 정적 relogger 그룹만 허용하는 [Relog와](relog.md)같은 함수에 전달하는 이 기술을 사용합니다.

::: moniker-end
