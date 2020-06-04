---
title: 트레이스인정보 클래스
description: C++ 빌드 인사이트 SDK TraceInfo 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TraceInfo
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 75d53937e3999f5692dee0ecf419e0ce5f49a274
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324169"
---
# <a name="traceinfo-class"></a>트레이스인정보 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `TraceInfo` 분석 되 거나 다시 기록 되는 추적에 대 한 유용한 속성에 액세스 하는 데 사용 됩니다.

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

## <a name="remarks"></a>설명

전체 추적 `StartTimestamp` `StopTimestamp` 중에 경과된 틱 수를 얻기 위해 에서 빼기합니다. 결과 `TickFrequency` 값을 시간 단위로 변환하는 데 사용합니다. 눈금을 시간으로 변환하는 예제는 [EVENT_DATA](../c-event-data-types/event-data-struct.md)를 참조하십시오.

눈금을 직접 변환하지 않으려면 `TraceInfo` 클래스는 나노초 단위로 추적 기간을 반환하는 멤버 함수를 제공합니다. 표준 C++ `chrono` 라이브러리를 사용하여 이 값을 다른 시간 단위로 변환합니다.

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

[트레이스정보](#trace-info)

### <a name="functions"></a>Functions

[기간](#duration)
[논리 프로세서카운트](#logical-processor-count)
[시작 타임스탬프](#start-timestamp)
[중지 타임스탬프](#stop-timestamp)
[틱 빈도](#tick-frequency)

## <a name="duration"></a><a name="duration"></a>기간

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Return Value

나노초 단위로 활동하는 기간입니다.

## <a name="logicalprocessorcount"></a><a name="logical-processor-count"></a>논리 프로세서 카운트

```cpp
const unsigned long& LogicalProcessorCount() const;
```

### <a name="return-value"></a>Return Value

추적이 수집된 컴퓨터의 논리 프로세서 수입니다.

## <a name="starttimestamp"></a><a name="start-timestamp"></a>스타트타임스탬프

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Return Value

추적이 시작될 때 캡처된 틱 값입니다.

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a>스톱타임스탬프

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Return Value

추적이 중지될 때 캡처된 틱 값입니다.

## <a name="tickfrequency"></a><a name="tick-frequency"></a>틱 주파수

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Return Value

틱으로 측정된 기간을 평가할 때 사용할 초당 틱 수입니다.

## <a name="traceinfo"></a><a name="trace-info"></a>트레이스정보

```cpp
TraceInfo(const TRACE_INFO_DATA& data);
```

### <a name="parameters"></a>매개 변수

*데이터*\
추적에 대한 정보를 포함하는 데이터입니다.

::: moniker-end
