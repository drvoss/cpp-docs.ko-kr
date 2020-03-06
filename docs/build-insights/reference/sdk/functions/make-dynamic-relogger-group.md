---
title: MakeDynamicReloggerGroup
description: C++ BUILD Insights SDK MakeDynamicReloggerGroup 함수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4ad394d3ba2982e7ee4f2a497fef2ea65a3c1769
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334399"
---
# <a name="makedynamicreloggergroup"></a>MakeDynamicReloggerGroup

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`MakeDynamicReloggerGroup` 함수는 동적 재로 거 거 그룹을 만드는 데 사용 됩니다. 재로 거 거 그룹의 멤버는 추적의 모든 이벤트가 처리 될 때까지 왼쪽에서 오른쪽으로 한 이벤트를 수신 합니다.

## <a name="syntax"></a>구문

```cpp
auto MakeDynamicReloggerGroup(std::vector<IRelogger*> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::shared_ptr<IRelogger>> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::unique_ptr<IRelogger>> reloggers);
```

### <a name="parameters"></a>매개 변수

*reloggers 거*\
동적 re로 거 그룹에 포함 된 [Irelogger](../other-types/irelogger-class.md) 가리키는 벡터입니다. 이러한 포인터는 raw, `std::unique_ptr`또는 `std::shared_ptr`수 있습니다. 또한 [Ianalyzer](../other-types/ianalyzer-class.md) 포인터는 상속 관계로 인해 포인터 `IRelogger` 간주 됩니다.

### <a name="return-value"></a>반환 값

동적 재로 거 그룹입니다. **Auto** 키워드를 사용 하 여 반환 값을 캡처합니다.

## <a name="remarks"></a>주의

정적 재로 거 거 그룹과 달리 동적 재로 거 그룹의 멤버는 컴파일 타임에 알 필요가 없습니다. 프로그램 입력을 기반으로 런타임에 또는 컴파일 시간에 알 수 없는 다른 값에 따라 재로 거 거 그룹 멤버를 선택할 수 있습니다. 정적 재로 거 거 그룹과 달리 동적 재로 거 그룹 내의 [irelogger 거](../other-types/irelogger-class.md) 포인터는 다형성 동작을 가지 며 가상 함수 호출은 올바르게 디스패치 됩니다. 이러한 유연성은 이벤트 처리 시간이 느려질 수 있습니다. 모든 재로 거 그룹 멤버를 컴파일 타임에 알고 있는 경우 다형성 동작이 필요 하지 않은 경우에는 정적 재로 거 거 그룹을 사용 하는 것이 좋습니다. 정적 재로 거 거 그룹을 사용 하려면 대신 [MakeStaticReloggerGroup](make-static-relogger-group.md) 를 호출 합니다.

동적 재로 거 거 그룹은 정적 재로 거 거 그룹 내에 캡슐화 할 수 있습니다. 해당 주소를 [MakeStaticReloggerGroup](make-static-relogger-group.md)에 전달 합니다. 정적 재로 거 거 그룹을 허용 하는 [Relog](relog.md)와 같은 함수에 동적 재로 거 거 그룹을 전달 하는 데이 방법을 사용 합니다.

::: moniker-end
