---
title: 아이레로거 클래스
description: C ++ 빌드 통찰력 SDK IRelogger 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IRelogger
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 146377b2b44df43ed4b2f749efd9fb614a2a09c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329150"
---
# <a name="irelogger-class"></a>아이레로거 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `IRelogger` 클래스는 ETW(Windows) 추적에 대한 이벤트 추적을 다시 하기 위한 인터페이스를 제공합니다. 그것은 [메이크 다이내믹 리로거 그룹과](../functions/make-dynamic-relogger-group.md) [메이크스테틱 리로거 그룹](../functions/make-static-analyzer-group.md) 기능과 함께 사용. 리로거 그룹의 일부가 될 수 있는 사용자 고유의 리로거를 만들려면 기본 클래스로 사용합니다. `IRelogger`

## <a name="syntax"></a>구문

```cpp
class IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
    virtual AnalysisControl OnBeginRelogging();
    virtual AnalysisControl OnEndRelogging();
    virtual AnalysisControl OnBeginReloggingPass();
    virtual AnalysisControl OnEndReloggingPass() ;

    virtual ~IRelogger();
};
```

## <a name="remarks"></a>설명

재정의되지 않은 모든 함수에 대한 기본 return `AnalysisControl::CONTINUE`값은 입니다. 자세한 내용은 [AnalysisControl](analysis-control-enum-class.md)을 참조하십시오.

## <a name="members"></a>멤버

### <a name="destructor"></a>소멸자

[~ 아이레로거](#irelogger-destructor)

### <a name="functions"></a>Functions

[온비비레로깅](#on-begin-relogging)\
[온비르로깅패스](#on-begin-relogging-pass)\
[온엔드 리로깅](#on-end-relogging)\
[온엔드리로깅패스](#on-end-relogging-pass)\
[온심플 이벤트](#on-simple-event)\
[온스타트 활동](#on-start-activity)\
[온스톱 활동](#on-stop-activity)\
[온트레이스정보](#on-trace-info)

## <a name="irelogger"></a><a name="irelogger-destructor"></a>~ 아이레로거

IRelogger 클래스를 파괴합니다.

```cpp
virtual ~IRelogger();
```

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a>온비비레로깅

이 함수는 리로깅 패스가 시작되기 전에 호출됩니다.

```cpp
virtual AnalysisControl OnBeginRelogging();
```

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a>온비르로깅패스

이 함수는 리로깅 패스의 시작 부분에서 호출됩니다.

```cpp
virtual AnalysisControl OnBeginReloggingPass();
```

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="onendrelogging"></a><a name="on-end-relogging"></a>온엔드 리로깅

이 함수는 리로깅 패스가 종료된 후 호출됩니다.

```cpp
virtual AnalysisControl OnEndRelogging();
```

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a>온엔드리로깅패스

이 함수는 리로깅 패스의 끝에서 호출됩니다.

```cpp
virtual AnalysisControl OnEndReloggingPass();
```

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="onsimpleevent"></a><a name="on-simple-event"></a>온심플 이벤트

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

이 함수는 간단한 이벤트가 처리될 때 호출됩니다.

### <a name="parameters"></a>매개 변수

*이벤트 스택*\
이 간단한 이벤트의 이벤트 스택입니다. 이벤트 스택에 대한 자세한 내용은 [이벤트](../event-table.md)를 참조하십시오.

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="onstartactivity"></a><a name="on-start-activity"></a>온스타트 활동

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

이 함수는 활동 시작 이벤트가 처리될 때 호출됩니다.

### <a name="parameters"></a>매개 변수

*이벤트 스택*\
이 활동 시작 이벤트의 이벤트 스택입니다. 이벤트 스택에 대한 자세한 내용은 [이벤트](../event-table.md)를 참조하십시오.

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="onstopactivity"></a><a name="on-stop-activity"></a>온스톱 활동

이 함수는 활동 중지 이벤트가 처리될 때 호출됩니다.

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="parameters"></a>매개 변수

*이벤트 스택*\
이 활동 중지 이벤트의 이벤트 스택입니다. 이벤트 스택에 대한 자세한 내용은 [이벤트](../event-table.md)를 참조하십시오.

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="ontraceinfo"></a><a name="on-trace-info"></a>온트레이스정보

```cpp
virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
```

이 함수는 모든 분석 또는 리로깅 패스의 시작 부분에 한 번 호출됩니다.

### <a name="parameters"></a>매개 변수

*추적 정보*\
사용 중인 추적에 대한 유용한 속성을 포함하는 [TraceInfo](../cpp-event-data-types/trace-info.md) 개체입니다.

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

::: moniker-end
