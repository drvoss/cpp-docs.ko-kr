---
title: 작업 클래스
description: C++ BUILD Insights SDK 활동 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Activity
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6de411c375b42e4acfb44bf0fac9d28ad57f1ca7
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335029"
---
# <a name="activity-class"></a>작업 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`Activity` 클래스는 [Matchevent](../functions/match-event.md), [matcheventinmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)및 [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. 모든 작업 이벤트와 일치 하는 데 사용 합니다. `Activity` 클래스에서 일치 시킬 수 있는 모든 이벤트를 보려면 [이벤트 표](../event-table.md) 를 참조 하세요.

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

## <a name="remarks"></a>주의

`Activity` 클래스의 여러 멤버 함수는 틱 수를 반환 합니다. C++빌드 정보에는 Windows의 성능 카운터가 틱의 원본으로 사용 됩니다. 틱 수를 시간 단위 (예: 초)로 변환 하려면 틱 빈도와 함께 사용 해야 합니다. [이벤트](event.md) 기본 클래스에서 사용할 수 있는 `TickFrequency` 멤버 함수를 호출 하 여 틱 빈도를 가져올 수 있습니다. [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) 페이지에서는 틱을 시간 단위로 변환 하는 예를 보여 줍니다.

틱을 시간 단위로 직접 변환 하지 않으려는 경우 `Activity` 클래스는 시간 값을 나노초로 반환 하는 멤버 함수를 제공 합니다. 표준 C++ `chrono` 라이브러리를 사용 하 여 다른 시간 단위로 변환 합니다.

## <a name="members"></a>멤버

[이벤트](event.md) 기본 클래스에서 상속 된 해당 멤버와 함께 `Activity` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructor"></a>생성자

[활동](#activity)

### <a name="functions"></a>함수

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[지속 시간](#duration)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ExclusiveDuration](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[ExclusiveWallClockTimeResponsibility](#exclusive-wall-clock-time-responsibility)\
[ExclusiveWallClockTimeResponsibilityTicks](#exclusive-wall-clock-time-responsibility-ticks)\
[Starttimestamp](#start-timestamp)\
[StopTimestamp](#stop-timestamp)\
[WallClockTimeResponsibility](#wall-clock-time-responsibility)\
[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)

## <a name="activity"></a>활동이

```cpp
Activity(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*event*\
모든 작업 이벤트입니다.

## <a name="cpu-ticks"></a>CPUTicks

```cpp
const long long& CPUTicks() const;
```

### <a name="return-value"></a>반환 값

이 작업 중에 발생 한 CPU 틱 수입니다. CPU 틱은 일반 틱과 다릅니다. Cpu 틱은 CPU가 활동에서 코드를 실행 하는 경우에만 계산 됩니다. 작업과 연결 된 스레드가 절전 모드 이면 CPU 틱이 계산 되지 않습니다.

## <a name="cpu-time"></a>CPUTime

```cpp
std::chrono::nanoseconds CPUTime()() const;
```

### <a name="return-value"></a>반환 값

이 작업 내에서 CPU가 코드를 실행 하는 시간입니다. 자식 활동이 별도의 스레드에서 실행 되는 경우이 값은 활동 기간 보다 클 수 있습니다. 값은 나노초로 반환 됩니다.

## <a name="duration"></a>작업

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>반환 값

작업의 기간 (나노초)입니다.

## <a name="exclusive-cpu-ticks"></a>ExclusiveCPUTicks

```cpp
const long long& ExclusiveCPUTicks() const;
```

### <a name="return-value"></a>반환 값

[CPUTicks](#cpu-ticks)와 동일 하지만 자식 활동에서 발생 한 CPU 틱은 포함 하지 않습니다.

## <a name="exclusive-cpu-time"></a>ExclusiveCPUTime

```cpp
std::chrono::nanoseconds ExclusiveCPUTime() const;
```

### <a name="return-value"></a>반환 값

자식 활동의 CPU 시간이 포함 되지 않는다는 점을 제외 하 고 [CPUTime](#cpu-time)와 동일 합니다.

## <a name="exclusive-duration"></a>ExclusiveDuration

```cpp
std::chrono::nanoseconds ExclusiveDuration() const;
```

### <a name="return-value"></a>반환 값

자식 활동에서 소요 된 시간을 포함 하지 않는 작업 기간 (나노초)입니다.

## <a name="exclusive-duration-ticks"></a>ExclusiveDurationTicks

```cpp
const long long& ExclusiveDurationTicks() const;
```

### <a name="return-value"></a>반환 값

자식 활동에서 발생 한 틱 수를 제외 하 고이 활동에서 발생 한 틱 수입니다.

## <a name="exclusive-wall-clock-time-responsibility"></a>ExclusiveWallClockTimeResponsibility

```cpp
std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
```

### <a name="return-value"></a>반환 값

[WallClockTimeResponsibility](#wall-clock-time-responsibility)와 동일 하지만 자식 활동의 벽 시계 시간 업무를 포함 하지 않습니다.

## <a name="exclusive-wall-clock-time-responsibility-ticks"></a>ExclusiveWallClockTimeResponsibilityTicks

```cpp
const long long& ExclusiveWallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>반환 값

[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)와 동일 하지만 자식 활동의 벽 시계 시간 업무를 포함 하지 않습니다.

## <a name="start-timestamp"></a>StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>반환 값

활동을 시작할 때 캡처된 틱 값입니다.

## <a name="stop-timestamp"></a>StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>반환 값

작업을 중지할 때 캡처된 틱 값입니다.

## <a name="wall-clock-time-responsibility"></a>WallClockTimeResponsibility

```cpp
std::chrono::nanoseconds WallClockTimeResponsibility() const;
```

### <a name="return-value"></a>반환 값

이 작업의 벽 시계 시간 (나노초)입니다. 벽 시계 시간 업무에 대 한 자세한 내용은 [WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)를 참조 하세요.

## <a name="wall-clock-time-responsibility-ticks"></a>WallClockTimeResponsibilityTicks

```cpp
const long long& WallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>반환 값

전체 벽 시계 시간에 대 한이 활동의 기여를 나타내는 틱 수입니다. 벽 시계 시간 업무 눈금이 일반 틱과 다릅니다. 벽 시계 시간 책임 틱은 활동 간의 병렬 처리를 고려 합니다. 두 병렬 작업의 기간은 50이 고 동일한 시작 및 중지 시간이 있을 수 있습니다. 이 경우에는 둘 다 벽 시계 시간을 25 틱으로 할당 합니다.

::: moniker-end
