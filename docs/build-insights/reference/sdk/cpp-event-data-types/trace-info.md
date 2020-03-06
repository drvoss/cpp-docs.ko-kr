---
title: TraceInfo 클래스
description: C++ BUILD Insights SDK traceinfo 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TraceInfo
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5cf32c8dc954a803a11888231d35b1050ac81cc3
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334501"
---
# <a name="traceinfo-class"></a>TraceInfo 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`TraceInfo` 클래스는 분석 또는 relogged 추적에 대 한 유용한 속성에 액세스 하는 데 사용 됩니다.

## <a name="syntax"></a>구문

```cpp
class TraceInfo
{
public:
    TraceInfo(const TRACE_INFO_DATA& data);

    const unsigned long& LogicalProcessorCount() const;

    const long long& TickFrequency() const;
    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;

    std::chrono::nanoseconds Duration() const;
};
```

## <a name="remarks"></a>주의

`StopTimestamp`에서 `StartTimestamp`를 빼서 전체 추적 중 경과 된 틱 수를 가져옵니다. `TickFrequency`를 사용 하 여 결과 값을 시간 단위로 변환 합니다. 틱을 시간으로 변환 하는 예는 [EVENT_DATA](../c-event-data-types/event-data-struct.md)를 참조 하세요.

틱을 직접 변환 하지 않으려는 경우 `TraceInfo` 클래스는 추적 기간 (나노초)을 반환 하는 멤버 함수를 제공 합니다. 표준 C++ `chrono` 라이브러리를 사용 하 여이 값을 다른 시간 단위로 변환 합니다.

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

[TraceInfo](#trace-info)

### <a name="functions"></a>함수

[Duration](#duration)
[LogicalProcessorCount](#logical-processor-count)
[Starttimestamp](#start-timestamp)
[StopTimestamp](#stop-timestamp)
[TickFrequency](#tick-frequency)

## <a name="duration"></a>작업

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>반환 값

작업의 기간 (나노초)입니다.

## <a name="logical-processor-count"></a>LogicalProcessorCount

```cpp
const unsigned long& LogicalProcessorCount() const;
```

### <a name="return-value"></a>반환 값

추적이 수집 된 컴퓨터의 논리 프로세서 수입니다.

## <a name="start-timestamp"></a>StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>반환 값

추적이 시작 될 때 캡처된 틱 값입니다.

## <a name="stop-timestamp"></a>StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>반환 값

추적이 중지 될 때 캡처된 틱 값입니다.

## <a name="tick-frequency"></a>TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>반환 값

틱 기간을 평가할 때 사용할 초당 틱 수입니다.

## <a name="trace-info"></a>TraceInfo

```cpp
TraceInfo(const TRACE_INFO_DATA& data);
```

### <a name="parameters"></a>매개 변수

*데이터*\
추적에 대 한 정보를 포함 하는 데이터입니다.

::: moniker-end
