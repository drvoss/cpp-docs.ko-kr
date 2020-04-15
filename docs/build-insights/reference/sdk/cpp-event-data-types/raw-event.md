---
title: RawEvent 클래스
description: C++ 빌드 인사이트 SDK RawEvent 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RawEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 83629457ac3a0d1f991f6b084af2f3400612b2ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324377"
---
# <a name="rawevent-class"></a>RawEvent 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `RawEvent` [EventStack](event-stack.md)에서 일반 이벤트를 나타내는 데 사용됩니다.

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

## <a name="remarks"></a>설명

클래스의 여러 멤버 `RawEvent` 함수는 틱 수를 반환합니다. C++ 빌드 인사이트는 Windows의 성능 카운터를 눈금의 소스로 사용합니다. 눈금 개수는 눈금 빈도와 함께 사용하여 초와 같은 시간 단위로 변환해야 합니다. 상기 `TickFrequency` 부재 함수는 진드기 주파수를 얻기 위해 호출될 수 있다. 눈금은 시간 단위로 변환하는 방법에 대한 예제는 [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) 페이지를 참조하십시오.

눈금을 직접 변환하지 않으려면 클래스는 `RawEvent` 시간 값을 나노초 단위로 반환하는 멤버 함수를 제공합니다. 표준 C++ `chrono` 라이브러리를 사용하여 나노초를 다른 시간 단위로 변환합니다.

## <a name="members"></a>멤버

### <a name="constructor"></a>생성자

[원시 이벤트](#raw-event)

### <a name="functions"></a>Functions

[CPU틱](#cpu-ticks)\
[CPU 시간](#cpu-time)\
[데이터](#data)\
[기간](#duration)\
[EventId](#event-id)
[이벤트인스턴스Id](#event-instance-id)
[이벤트 이름](#event-name)\
[이벤트와이드 네임](#event-wide-name)\
[익스클루시브CPU틱](#exclusive-cpu-ticks)\
[익스클루시브CPU타임](#exclusive-cpu-time)\
[독점 기간](#exclusive-duration)\
[배타적 지속 시간틱](#exclusive-duration-ticks)\
[익스클루시브월클럭타임책임](#exclusive-wall-clock-time-responsibility)\
[익스클루시브월클럭타임책임틱스](#exclusive-wall-clock-time-responsibility-ticks)\
[프로세스 ID](#process-id)\
[프로세서 인덱스](#processor-index)\
[스타트타임스탬프](#start-timestamp)\
[스톱타임스탬프](#stop-timestamp)\
[스레드 ID](#thread-id)\
[틱 주파수](#tick-frequency)\
[월클럭타임책임](#wall-clock-time-responsibility)\
[월시계시간책임틱스](#wall-clock-time-responsibility-ticks)

## <a name="rawevent"></a><a name="raw-event"></a>원시 이벤트

```cpp
RawEvent(const EVENT_DATA& data);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
이벤트 데이터입니다.

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

## <a name="data"></a><a name="data"></a>데이터

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Return Value

이 이벤트에 포함된 추가 데이터에 대한 포인터입니다. 이 필드를 해석하는 방법에 대한 자세한 내용은 [EVENT_DATA](../c-event-data-types/event-data-struct.md)을 참조하십시오.

## <a name="duration"></a><a name="duration"></a>기간

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Return Value

나노초 단위로 활동하는 기간입니다.

## <a name="eventid"></a><a name="event-id"></a>Eventid

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>Return Value

이벤트 유형을 식별하는 숫자입니다. 이벤트 식별자 목록은 [EVENT_ID](../c-event-data-types/event-id-enum.md)를 참조하십시오.

## <a name="eventinstanceid"></a><a name="event-instance-id"></a>이벤트 인스턴스 ID

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>Return Value

추적 내부의 이벤트를 고유하게 식별하는 숫자입니다. 이 값은 동일한 추적을 여러 번 분석하거나 다시 작업할 때 변경되지 않습니다. 이 값을 사용하여 여러 분석에서 동일한 이벤트를 식별하거나 동일한 추적을 통해 다시 로깅합니다.

## <a name="eventname"></a><a name="event-name"></a>Eventname

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>Return Value

[EventId로](#event-id)식별된 이벤트 형식의 이름을 포함하는 ANSI 문자열입니다.

## <a name="eventwidename"></a><a name="event-wide-name"></a>이벤트와이드 네임

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>Return Value

[EventId로](#event-id)식별된 이벤트 형식의 이름을 포함하는 넓은 문자열입니다.

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

## <a name="processid"></a><a name="process-id"></a>프로세스 ID

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>Return Value

이벤트가 발생한 프로세스의 식별자입니다.

## <a name="processorindex"></a><a name="processor-index"></a>프로세서 인덱스

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>Return Value

이벤트가 발생한 논리 프로세서에 대한 0기반 인덱스입니다.

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

## <a name="threadid"></a><a name="thread-id"></a>스레드 ID

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>Return Value

이벤트가 발생한 스레드의 식별자입니다.

## <a name="tickfrequency"></a><a name="tick-frequency"></a>틱 주파수

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Return Value

이 이벤트의 틱으로 측정된 기간을 평가할 때 사용할 초당 틱 수입니다.

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
