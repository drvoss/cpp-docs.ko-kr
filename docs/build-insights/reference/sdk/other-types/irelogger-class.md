---
title: IRelogger 클래스
description: C++ BUILD Insights SDK IRelogger 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IRelogger
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d0796cec3fe4ac6183279e8d8013a9550f18b61c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422897"
---
# <a name="irelogger-class"></a>IRelogger 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`IRelogger` 클래스는 ETW (ETW(Windows용 이벤트 추적)) 추적을 다시 로깅하는 인터페이스를 제공 합니다. [MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md) 및 [MakeStaticReloggerGroup](../functions/make-static-analyzer-group.md) 함수에 사용 됩니다. `IRelogger`를 기본 클래스로 사용 하 여 재로 거 거 그룹의 일부가 될 수 있는 고유한 다시로 거를 만듭니다.

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

재정의 되지 않는 모든 함수의 기본 반환 값은 `AnalysisControl::CONTINUE`입니다. 자세한 내용은 [AnalysisControl](analysis-control-enum-class.md)를 참조 하세요.

## <a name="members"></a>구성원

### <a name="destructor"></a>소멸자

[~ IRelogger 거](#irelogger-destructor)

### <a name="functions"></a>Functions

[Onbeginrelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[Onstartactivity](#on-start-activity)\
[Onstopactivity](#on-stop-activity)\
[OnTraceInfo](#on-trace-info)

## <a name="irelogger-destructor"></a>~ IRelogger 거

IRelogger 거 클래스를 소멸 시킵니다.

```cpp
virtual ~IRelogger();
```

## <a name="on-begin-relogging"></a>OnBeginRelogging

이 함수는 relogging pass가 시작 되기 전에 호출 됩니다.

```cpp
virtual AnalysisControl OnBeginRelogging();
```

### <a name="return-value"></a>Return Value

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-begin-relogging-pass"></a>OnBeginReloggingPass

이 함수는 relogging pass의 시작 부분에서 호출 됩니다.

```cpp
virtual AnalysisControl OnBeginReloggingPass();
```

### <a name="return-value"></a>Return Value

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-end-relogging"></a>OnEndRelogging

이 함수는 다시 로깅 패스가 종료 된 후에 호출 됩니다.

```cpp
virtual AnalysisControl OnEndRelogging();
```

### <a name="return-value"></a>Return Value

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-end-relogging-pass"></a>OnEndReloggingPass

이 함수는 relogging 패스가 끝날 때 호출 됩니다.

```cpp
virtual AnalysisControl OnEndReloggingPass();
```

### <a name="return-value"></a>Return Value

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-simple-event"></a>OnSimpleEvent

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

이 함수는 단순 이벤트가 처리 될 때 호출 됩니다.

### <a name="parameters"></a>매개 변수

*Eventstack*\
이 간단한 이벤트에 대 한 이벤트 스택입니다. 이벤트 스택에 대 한 자세한 내용은 [이벤트](../event-table.md)를 참조 하세요.

### <a name="return-value"></a>Return Value

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-start-activity"></a>OnStartActivity

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

이 함수는 작업 시작 이벤트가 처리 될 때 호출 됩니다.

### <a name="parameters"></a>매개 변수

*Eventstack*\
이 작업 시작 이벤트에 대 한 이벤트 스택입니다. 이벤트 스택에 대 한 자세한 내용은 [이벤트](../event-table.md)를 참조 하세요.

### <a name="return-value"></a>Return Value

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-stop-activity"></a>OnStopActivity

이 함수는 활동 중지 이벤트가 처리 될 때 호출 됩니다.

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="parameters"></a>매개 변수

*Eventstack*\
이 작업 중지 이벤트의 이벤트 스택입니다. 이벤트 스택에 대 한 자세한 내용은 [이벤트](../event-table.md)를 참조 하세요.

### <a name="return-value"></a>Return Value

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-trace-info"></a>OnTraceInfo

```cpp
virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
```

이 함수는 모든 분석 또는 다시 로깅 단계가 시작 될 때 한 번 호출 됩니다.

### <a name="parameters"></a>매개 변수

*Traceinfo*\
사용 중인 추적에 대 한 유용한 속성을 포함 하는 [Traceinfo](../cpp-event-data-types/trace-info.md) 개체입니다.

### <a name="return-value"></a>Return Value

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

::: moniker-end
