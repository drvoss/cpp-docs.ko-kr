---
title: 작업 클래스
description: C++ 빌드 인사이트 SDK 활동 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Activity
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2ea04150aec9c0b2366d97e6e4c15de557a4f47c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325256"
---
# <a name="activity-class"></a>작업 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `Activity` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. 모든 활동 이벤트와 일치하는 데 사용합니다. [클래스와](../event-table.md) 일치시킬 수 있는 모든 이벤트를 보려면 이벤트 테이블을 참조하십시오. `Activity`

## <a name="syntax"></a>구문

```cpp
class Activity : public Event
{
public:
    Activity(const RawEvent& event);

    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;
    const long long& ExclusiveDurationTicks() const;
    const long long& CPUTicks() const;
    const long long& ExclusiveCPUTicks() const;
    const long long& WallClockTimeResponsibilityTicks() const;
    const long long& ExclusiveWallClockTimeResponsibilityTicks() const;

    std::chrono::nanoseconds Duration() const;
    std::chrono::nanoseconds ExclusiveDuration() const;
    std::chrono::nanoseconds CPUTime() const ;
    std::chrono::nanoseconds ExclusiveCPUTime() const;
    std::chrono::nanoseconds WallClockTimeResponsibility() const;
    std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
};
```

## <a name="remarks"></a>설명

클래스의 여러 멤버 `Activity` 함수는 틱 수를 반환합니다. C++ 빌드 인사이트는 Windows의 성능 카운터를 눈금의 소스로 사용합니다. 눈금 개수는 눈금 빈도와 함께 사용하여 초와 같은 시간 단위로 변환해야 합니다. 이벤트 `TickFrequency` 베이스 클래스에서 [Event](event.md) 사용할 수 있는 멤버 함수는 틱 주파수를 얻기 위해 호출될 수 있습니다. [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) 페이지에는 틱을 시간 단위로 변환하는 예제가 표시됩니다.

틱을 시간 단위로 직접 변환하지 않으려면 클래스는 `Activity` 시간 값을 나노초 단위로 반환하는 멤버 함수를 제공합니다. 표준 C++ `chrono` 라이브러리를 사용하여 다른 시간 단위로 변환합니다.

## <a name="members"></a>멤버

[Event](event.md) 기본 클래스에서 상속된 멤버와 `Activity` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructor"></a>생성자

[활동](#activity)

### <a name="functions"></a>Functions

[CPU틱](#cpu-ticks)\
[CPU 시간](#cpu-time)\
[기간](#duration)\
[익스클루시브CPU틱](#exclusive-cpu-ticks)\
[익스클루시브CPU타임](#exclusive-cpu-time)\
[독점 기간](#exclusive-duration)\
[배타적 지속 시간틱](#exclusive-duration-ticks)\
[익스클루시브월클럭타임책임](#exclusive-wall-clock-time-responsibility)\
[익스클루시브월클럭타임책임틱스](#exclusive-wall-clock-time-responsibility-ticks)\
[스타트타임스탬프](#start-timestamp)\
[스톱타임스탬프](#stop-timestamp)\
[월클럭타임책임](#wall-clock-time-responsibility)\
[월시계시간책임틱스](#wall-clock-time-responsibility-ticks)

## <a name="activity"></a><a name="activity"></a> 작업

```cpp
Activity(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
모든 활동 이벤트.

## <a name="cputicks"></a><a name="cpu-ticks"></a>CPU틱

```cpp
const long long& CPUTicks() const;
```

### <a name="return-value"></a>Return Value

이 작업 중에 발생한 CPU 틱 수입니다. CPU 틱은 일반 틱과 다릅니다. CPU 틱은 CPU가 활동에서 코드를 실행하는 경우에만 계산됩니다. 활동과 연결된 스레드가 절전 모드일 때 CPU 체크는 계산되지 않습니다.

## <a name="cputime"></a><a name="cpu-time"></a>CPU 시간

```cpp
std::chrono::nanoseconds CPUTime()() const;
```

### <a name="return-value"></a>Return Value

CPU가 이 활동 내에서 코드를 실행하는 시간입니다. 이 값은 자식 활동이 별도의 스레드에서 실행되는 경우 활동 기간보다 높을 수 있습니다. 값은 나노초 단위로 반환됩니다.

## <a name="duration"></a><a name="duration"></a>기간

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Return Value

나노초 단위로 활동하는 기간입니다.

## <a name="exclusivecputicks"></a><a name="exclusive-cpu-ticks"></a>익스클루시브CPU틱

```cpp
const long long& ExclusiveCPUTicks() const;
```

### <a name="return-value"></a>Return Value

[CPUTicks와](#cpu-ticks)동일하지만 자식 활동에서 발생한 CPU 틱은 포함하지 않습니다.

## <a name="exclusivecputime"></a><a name="exclusive-cpu-time"></a>익스클루시브CPU타임

```cpp
std::chrono::nanoseconds ExclusiveCPUTime() const;
```

### <a name="return-value"></a>Return Value

[CPUTime과](#cpu-time)동일합니다.

## <a name="exclusiveduration"></a><a name="exclusive-duration"></a>독점 기간

```cpp
std::chrono::nanoseconds ExclusiveDuration() const;
```

### <a name="return-value"></a>Return Value

하위 활동에 소요된 시간을 포함하지 않는 나노초의 활동 기간입니다.

## <a name="exclusivedurationticks"></a><a name="exclusive-duration-ticks"></a>배타적 지속 시간틱

```cpp
const long long& ExclusiveDurationTicks() const;
```

### <a name="return-value"></a>Return Value

자식 활동에서 발생한 틱 수를 제외한 이 활동에서 발생한 틱 수입니다.

## <a name="exclusivewallclocktimeresponsibility"></a><a name="exclusive-wall-clock-time-responsibility"></a>익스클루시브월클럭타임책임

```cpp
std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Return Value

[WallClockTime책임과](#wall-clock-time-responsibility)동일하지만, 아동 활동의 월 시계 시간 책임을 포함하지 않습니다.

## <a name="exclusivewallclocktimeresponsibilityticks"></a><a name="exclusive-wall-clock-time-responsibility-ticks"></a>익스클루시브월클럭타임책임틱스

```cpp
const long long& ExclusiveWallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Return Value

[WallClockTimeResponsibilityTicks와](#wall-clock-time-responsibility-ticks)동일하지만, 자식 활동의 벽 시계 시간 책임 틱을 포함하지 않습니다.

## <a name="starttimestamp"></a><a name="start-timestamp"></a>스타트타임스탬프

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Return Value

활동이 시작될 때 캡처된 눈금 값입니다.

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a>스톱타임스탬프

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Return Value

활동이 중지될 때 캡처된 틱 값입니다.

## <a name="wallclocktimeresponsibility"></a><a name="wall-clock-time-responsibility"></a>월클럭타임책임

```cpp
std::chrono::nanoseconds WallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Return Value

이 활동의 벽 시계 시간 책임은 나노초단위로 이루어집니다. 월 시계 시간 책임이 무엇을 의미하는지에 대한 자세한 내용은 [월 클럭타임책임 체크를](#wall-clock-time-responsibility-ticks)참조하십시오.

## <a name="wallclocktimeresponsibilityticks"></a><a name="wall-clock-time-responsibility-ticks"></a>월시계시간책임틱스

```cpp
const long long& WallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Return Value

전체 월 시계 시간에 대한 이 활동의 기여도를 나타내는 틱 수입니다. 벽 시계 시간 책임 진드기는 일반 진드기와 다릅니다. 월 시계 시간 책임 틱은 활동 간의 병렬성을 고려합니다. 두 개의 병렬 활동은 50틱의 지속 시간과 동일한 시작 및 중지 시간을 가질 수 있습니다. 이 경우 둘 다 25틱의 월 클럭 시간 책임이 할당됩니다.

::: moniker-end
