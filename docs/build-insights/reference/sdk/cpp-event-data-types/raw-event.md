---
title: RawEvent 클래스
description: C++ BUILD Insights SDK RawEvent 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RawEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4088920d6070e14d64ccd046238c1c49b2556ea1
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334603"
---
# <a name="rawevent-class"></a>RawEvent 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`RawEvent` 클래스는 [Eventstack](event-stack.md)의 일반 이벤트를 나타내는 데 사용 됩니다.

## <a name="syntax"></a>구문

```cpp
class RawEvent
{
public:
    RawEvent(const EVENT_DATA& event);

    const unsigned short&        EventId() const;
    const unsigned long long&    EventInstanceId() const;
    const long long&             TickFrequency() const;
    const long long&             StartTimestamp() const;
    const long long&             StopTimestamp() const;
    const long long&             ExclusiveDurationTicks() const;
    const long long&             CPUTicks() const;
    const long long&             ExclusiveCPUTicks() const;
    const long long&             WallClockTimeResponsibilityTicks() const;
    const long long&             ExclusiveWallClockTimeResponsibilityTicks() const;
    const void*                  Data() const;
    const unsigned long&         ProcessId() const;
    const unsigned long&         ThreadId() const;
    const unsigned short&        ProcessorIndex() const;
    const char*                  EventName() const;
    const wchar_t*               EventWideName() const;

    std::chrono::nanoseconds Duration() const;
    std::chrono::nanoseconds ExclusiveDuration() const;
    std::chrono::nanoseconds CPUTime() const ;
    std::chrono::nanoseconds ExclusiveCPUTime() const;
    std::chrono::nanoseconds WallClockTimeResponsibility() const;
    std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
};
```

## <a name="remarks"></a>주의

`RawEvent` 클래스의 여러 멤버 함수는 틱 수를 반환 합니다. C++빌드 정보에는 Windows의 성능 카운터가 틱의 원본으로 사용 됩니다. 틱 수를 시간 단위 (예: 초)로 변환 하려면 틱 빈도와 함께 사용 해야 합니다. 틱 빈도를 가져오기 위해 `TickFrequency` 멤버 함수를 호출할 수 있습니다. 틱을 시간 단위로 변환 하는 방법에 대 한 예제는 [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) 페이지를 참조 하세요.

틱을 직접 변환 하지 않으려는 경우 `RawEvent` 클래스는 시간 값을 나노초로 반환 하는 멤버 함수를 제공 합니다. 표준 C++ `chrono` 라이브러리를 사용 하 여 나노초를 다른 시간 단위로 변환 합니다.

## <a name="members"></a>멤버

### <a name="constructor"></a>생성자

[RawEvent](#raw-event)

### <a name="functions"></a>함수

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[데이터](#data)\
[지속 시간](#duration)\
[EventId](#event-id)
[Eventinstanceid](#event-instance-id)
[EventName](#event-name)\
[Eventwidename](#event-wide-name)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ExclusiveDuration](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[ExclusiveWallClockTimeResponsibility](#exclusive-wall-clock-time-responsibility)\
[ExclusiveWallClockTimeResponsibilityTicks](#exclusive-wall-clock-time-responsibility-ticks)\
[ProcessId](#process-id)\
[ProcessorIndex](#processor-index)\
[Starttimestamp](#start-timestamp)\
[StopTimestamp](#stop-timestamp)\
[ThreadId](#thread-id)\
[TickFrequency](#tick-frequency)\
[WallClockTimeResponsibility](#wall-clock-time-responsibility)\
[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)

## <a name="raw-event"></a>RawEvent

```cpp
RawEvent(const EVENT_DATA& data);
```

### <a name="parameters"></a>매개 변수

*event*\
이벤트 데이터입니다.

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

## <a name="data"></a>데이터로

```cpp
const void* Data() const;
```

### <a name="return-value"></a>반환 값

이 이벤트에 포함 된 추가 데이터에 대 한 포인터입니다. 이 필드를 해석 하는 방법에 대 한 자세한 내용은 [EVENT_DATA](../c-event-data-types/event-data-struct.md)를 참조 하세요.

## <a name="duration"></a>작업

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>반환 값

작업의 기간 (나노초)입니다.

## <a name="event-id"></a>EventId

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>반환 값

이벤트 유형을 식별 하는 번호입니다. 이벤트 식별자 목록은 [EVENT_ID](../c-event-data-types/event-id-enum.md)를 참조 하세요.

## <a name="event-instance-id"></a>EventInstanceId

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>반환 값

추적 내에서 이벤트를 고유 하 게 식별 하는 번호입니다. 동일한 추적을 여러 번 분석 하거나 다시 로깅하는 경우에는이 값이 변경 되지 않습니다. 이 값을 사용 하 여 동일한 추적을 통해 여러 분석 또는 다시 로깅 패스에서 동일한 이벤트를 식별할 수 있습니다.

## <a name="event-name"></a>EventName

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>반환 값

[EventId](#event-id)로 식별 되는 이벤트 유형의 이름을 포함 하는 ANSI 문자열입니다.

## <a name="event-wide-name"></a>EventWideName

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>반환 값

[EventId](#event-id)로 식별 되는 이벤트 유형의 이름을 포함 하는 와이드 문자열입니다.

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

## <a name="process-id"></a>ProcessId

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>반환 값

이벤트가 발생 한 프로세스의 식별자입니다.

## <a name="processor-index"></a>ProcessorIndex

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>반환 값

이벤트가 발생 한 논리 프로세서의 인덱스 (0부터 시작)입니다.

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

## <a name="thread-id"></a>ThreadId

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>반환 값

이벤트가 발생 한 스레드의 식별자입니다.

## <a name="tick-frequency"></a>TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>반환 값

이 이벤트의 틱 기간을 평가할 때 사용할 초당 틱 수입니다.

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
