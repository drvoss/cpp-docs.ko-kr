---
title: 이벤트 클래스
description: C++ BUILD Insights SDK 이벤트 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Event
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 205a4e0ca9dd9449933f38f02d4ceafd5df8ead2
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334891"
---
# <a name="event-class"></a>이벤트 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`Event` 클래스는 [Matchevent](../functions/match-event.md), [matcheventinmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)및 [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. 이를 사용 하 여 모든 이벤트를 일치 시킵니다.

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

### <a name="functions"></a>함수

[EventId](#event-id)\ [데이터](#data)

[Eventinstanceid](#event-instance-id)\
[EventName](#event-name)\
[Eventwidename](#event-wide-name)\
[ProcessId](#process-id)\
[ProcessorIndex](#processor-index)\
[ThreadId](#thread-id)\
[TickFrequency](#tick-frequency)\
[Timestamp](#timestamp)

## <a name="entity"></a>이벤트

```cpp
Event(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*event*\
모든 이벤트입니다.

## <a name="data"></a>데이터로

```cpp
const void* Data() const;
```

### <a name="return-value"></a>반환 값

이 이벤트에 포함 된 추가 데이터에 대 한 포인터입니다. 이 필드를 해석 하는 방법에 대 한 자세한 내용은 [EVENT_DATA](../c-event-data-types/event-data-struct.md)를 참조 하세요.

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

[EventId](#event-id)로 식별 되는 이벤트의 이름을 포함 하는 와이드 문자열입니다.

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

## <a name="timestamp"></a>없으면

```cpp
const long long& Timestamp() const;
```

### <a name="return-value"></a>반환 값

이벤트가 활동 인 경우이 함수는 활동이 시작 될 때 캡처된 틱 값을 반환 합니다. 간단한 이벤트의 경우이 함수는 이벤트가 발생 했을 때 캡처된 틱 값을 반환 합니다.

::: moniker-end
