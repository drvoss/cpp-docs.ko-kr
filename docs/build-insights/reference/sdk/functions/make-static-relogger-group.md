---
title: MakeStaticReloggerGroup
description: C++ BUILD Insights SDK MakeStaticReloggerGroup 함수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 06927af89b16d9de1148e555868dd2022c59b171
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334387"
---
# <a name="makestaticreloggergroup"></a>MakeStaticReloggerGroup

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`MakeStaticReloggerGroup` 함수는 [Relog](relog.md)와 같은 함수에 전달할 수 있는 정적 재로 거 거 그룹을 만드는 데 사용 됩니다. 재로 거 거 그룹의 멤버는 추적의 모든 이벤트가 처리 될 때까지 왼쪽에서 오른쪽으로 한 이벤트를 수신 합니다.

## <a name="syntax"></a>구문

```cpp
template <typename... TReloggerPtrs>
auto MakeStaticReloggerGroup(TReloggerPtrs... reloggers);
```

### <a name="parameters"></a>매개 변수

*TReloggerPtrs*\
이 매개 변수는 항상 추론 됩니다.

*reloggers 거*\
정적 re로 거 그룹에 포함 된 [Irelogger](../other-types/irelogger-class.md) 포인터의 매개 변수 팩입니다. 이러한 포인터는 raw, `std::unique_ptr`또는 `std::shared_ptr`수 있습니다. 또한 [Ianalyzer](../other-types/ianalyzer-class.md) 포인터는 상속 관계로 인해 포인터 `IRelogger` 간주 됩니다.

### <a name="return-value"></a>반환 값

정적 재로 거 있는 그룹입니다. **Auto** 키워드를 사용 하 여 반환 값을 캡처합니다.

## <a name="remarks"></a>주의

동적 재로 거 거 그룹과 달리 정적 재로 거 그룹의 멤버는 컴파일 타임에 알고 있어야 합니다. 또한 정적 재로 거 거 그룹에는 다형 동작을 포함 하지 않는 [irelogger 거](../other-types/irelogger-class.md) 포인터가 포함 됩니다. 정적 재로 거 거 그룹을 사용 하 여 ETW(Windows용 이벤트 추적) (ETW) 추적을 분석 하는 경우 `IRelogger` 인터페이스를 호출 하면 항상 재로 거 거 그룹 멤버가 가리키는 개체로 확인 됩니다. 이러한 유연성 손실에는 더 빠른 이벤트 처리 시간이 발생할 수 있습니다. 컴파일 시간에 재로 거 거 그룹의 멤버를 알 수 없거나 `IRelogger` 포인터에 다형 동작이 필요한 경우에는 동적 재로 거 거 그룹을 사용 하는 것이 좋습니다. 대신 [MakeDynamicReloggerGroup](make-dynamic-relogger-group.md) 를 호출 하 여 동적 재로 거 거 그룹을 사용할 수 있습니다.

::: moniker-end
