---
title: 이벤트 클래스
description: C++ 빌드 인사이트 SDK 이벤트 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Event
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 25d58f642a1c314e48ddff62553394bcc65e4717
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324959"
---
# <a name="event-class"></a>이벤트 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `Event` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. 모든 이벤트와 일치하는 데 사용합니다.

## <a name="syntax"></a>구문

```cpp
class Event
{
public:
    Event(const RawEvent& event);

    const unsigned short&        EventId() const;
    const unsigned long long&    EventInstanceId() const;
    const long long&             TickFrequency() const;
    const long long&             Timestamp() const;
    const unsigned long&         ProcessId() const;
    const unsigned long&         ThreadId() const;
    const unsigned short&        ProcessorIndex() const;
    const char*                  EventName() const;
    const wchar_t*               EventWideName() const;
};
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

[이벤트](#entity)

### <a name="functions"></a>Functions

[데이터](#data)
[이벤트 ID](#event-id)\
[이벤트 인스턴스 ID](#event-instance-id)\
[Eventname](#event-name)\
[이벤트와이드 네임](#event-wide-name)\
[프로세스 ID](#process-id)\
[프로세서 인덱스](#processor-index)\
[스레드 ID](#thread-id)\
[틱 주파수](#tick-frequency)\
[타임 스탬프](#timestamp)

## <a name="event"></a><a name="entity"></a> 이벤트

```cpp
Event(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
모든 이벤트.

## <a name="data"></a><a name="data"></a>데이터

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Return Value

이 이벤트에 포함된 추가 데이터에 대한 포인터입니다. 이 필드를 해석하는 방법에 대한 자세한 내용은 [EVENT_DATA](../c-event-data-types/event-data-struct.md)을 참조하십시오.

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

[EventId로](#event-id)식별된 이벤트의 이름을 포함하는 넓은 문자열입니다.

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

## <a name="timestamp"></a><a name="timestamp"></a>타임 스탬프

```cpp
const long long& Timestamp() const;
```

### <a name="return-value"></a>Return Value

이벤트가 활동인 경우 이 함수는 활동이 시작된 시점에 캡처된 눈금 값을 반환합니다. 간단한 이벤트의 경우 이 함수는 이벤트가 발생했을 때 캡처된 눈금 값을 반환합니다.

::: moniker-end
