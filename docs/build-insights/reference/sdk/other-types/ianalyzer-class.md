---
title: I분석기 클래스
description: C++ 빌드 인사이트 SDK IAnalyzer 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IAnalyzer
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: be9d80bb94450458c73fd6ce8d908985ba6f293d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329181"
---
# <a name="ianalyzer-class"></a>I분석기 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `IAnalyzer` 클래스는 ETW(Windows) 추적에 대한 이벤트 추적을 분석하기 위한 인터페이스를 제공합니다. 그것은 [메이크 다이내믹 분석기 그룹,](../functions/make-dynamic-analyzer-group.md) [메이크 DynamicReloggerGroup,](../functions/make-dynamic-relogger-group.md) [정전기 분석기 그룹](../functions/make-dynamic-analyzer-group.md)및 [확인StaticReloggerGroup](../functions/make-static-analyzer-group.md) 기능과 함께 사용됩니다. 기본 `IAnalyzer` 클래스로 사용하여 분석기 또는 리로거 그룹의 일부가 될 수 있는 고유한 분석기를 만듭니다.

## <a name="syntax"></a>구문

```cpp
class IAnalyzer : public IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
    virtual AnalysisControl OnStopActivity(const EventStack& eventStack)
    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
    virtual AnalysisControl OnBeginAnalysis();
    virtual AnalysisControl OnEndAnalysis();
    virtual AnalysisControl OnBeginAnalysisPass();
    virtual AnalysisControl OnEndAnalysisPass();

    AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnBeginRelogging() final;
    AnalysisControl OnEndRelogging() final;
    AnalysisControl OnBeginReloggingPass() final;
    AnalysisControl OnEndReloggingPass() final;

    virtual ~IAnalyzer();
};
```

## <a name="remarks"></a>설명

파생되는 `IAnalyzer` 클래스는 분석기와 리로거로 모두 사용할 수 있습니다. 리로거로 사용할 경우 리로거 관련 함수는 분석기로 리디렉션됩니다. 그 반대의 경우도 마찬가지입니다: 분석기로 사용할 수 없는 클래스에서 `IRelogger` 파생된 클래스입니다. 리로거 그룹에서 분석기를 사용하는 것은 일반적인 패턴입니다. 리로거 그룹의 초기 위치에 배치될 때 분석기는 정보를 미리 계산하고 나중에 재배치자가 사용할 수 있도록 할 수 있습니다.

재정의되지 않은 모든 함수에 대한 기본 return `AnalysisControl::CONTINUE`값은 입니다. 자세한 내용은 [AnalysisControl](analysis-control-enum-class.md)을 참조하십시오.

## <a name="members"></a>멤버

인터페이스의 [OnTraceInfo](irelogger-class.md#on-trace-info) 멤버 외에도 `IAnalyzer` 클래스에는 다음 멤버가 포함됩니다. `IRelogger`

### <a name="destructor"></a>소멸자

[~ I분석기](#ianalyzer-destructor)

### <a name="functions"></a>Functions

[온비인분석](#on-begin-analysis)\
[온비분석패스](#on-begin-analysis-pass)\
[온비비레로깅](#on-begin-relogging)\
[온비르로깅패스](#on-begin-relogging-pass)\
[온엔드분석](#on-end-analysis)\
[온엔드분석패스](#on-end-analysis-pass)\
[온엔드 리로깅](#on-end-relogging)\
[온엔드리로깅패스](#on-end-relogging-pass)\
[온심플 이벤트](#on-simple-event)\
[온스타트 활동](#on-start-activity)\
[온스톱 활동](#on-stop-activity)

## <a name="ianalyzer"></a><a name="ianalyzer-destructor"></a>~ I분석기

IAnalyzer 클래스를 파괴합니다.

```cpp
virtual ~IAnalyzer();
```

## <a name="onbeginanalysis"></a><a name="on-begin-analysis"></a>온비인분석

분석기 그룹의 분석기 부분의 경우 첫 번째 분석 패스가 시작되기 전에 이 함수가 호출됩니다. 리로거 그룹의 분석기 부분의 경우 리로깅 패스가 시작되기 전에 이 함수가 호출됩니다. 동일한 리로깅 세션의 분석기 및 relogger 그룹의 분석기 부분의 경우 첫 번째 분석 패스가 시작되기 전에 이 함수가 두 번 호출됩니다.

```cpp
virtual AnalysisControl OnBeginAnalysis();
```

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="onbeginanalysispass"></a><a name="on-begin-analysis-pass"></a>온비분석패스

분석기 그룹의 일부 분석기의 경우 이 함수는 모든 분석 패스의 시작 부분에서 호출됩니다. 리로거 그룹의 분석기 부분의 경우 이 함수는 리로거 패스의 시작 부분에서 호출됩니다. 동일한 리로깅 세션의 분석기 및 relogger 그룹의 분석기 부분의 경우 이 함수는 모든 분석 패스의 시작 부분과 relogger 패스의 시작 부분에서 호출됩니다.

```cpp
virtual AnalysisControl OnBeginAnalysisPass();
```

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a>온비비레로깅

```cpp
AnalysisControl OnBeginRelogging() final;
```

이 함수는 재정의할 수 없습니다. 분석기는 relogger 그룹의 일부인 경우 C++ 빌드 인사이트 SDK에서 호출합니다. 이 함수는 [OnBeginAnalysis로](#on-begin-analysis)호출을 리디렉션합니다.

### <a name="return-value"></a>Return Value

[OnBeginAnalysis](#on-begin-analysis) 호출의 결과입니다.

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a>온비르로깅패스

이 함수는 재정의할 수 없습니다. 분석기는 relogger 그룹의 일부인 경우 C++ 빌드 인사이트 SDK에서 호출합니다. 이 함수는 [OnBeginAnalysisPass로](#on-begin-analysis-pass)호출을 리디렉션합니다.

```cpp
AnalysisControl OnBeginReloggingPass() final;
```

### <a name="return-value"></a>Return Value

[OnBeginAnalysisPass](#on-begin-analysis-pass) 호출의 결과입니다.

## <a name="onendanalysis"></a><a name="on-end-analysis"></a>온엔드분석

분석기 그룹의 일부인 분석기의 경우 마지막 분석 패스가 끝난 후 이 함수가 호출됩니다. 리로거 그룹의 일부인 분석기의 경우 리로깅 패스가 종료된 후 이 함수가 호출됩니다. 동일한 리로깅 세션의 분석기 및 relogger 그룹의 일부인 분석기의 경우 이 함수를 두 번 호출합니다.

1. 모든 분석 패스가 종료된 후 리로깅 패스가 시작되기 전에
1. 리로깅 패스가 종료된 후.

```cpp
virtual AnalysisControl OnEndAnalysis();
```

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="onendanalysispass"></a><a name="on-end-analysis-pass"></a>온엔드분석패스

분석기 그룹의 분석기 부분의 경우 이 함수는 모든 분석 패스의 끝에 호출됩니다. 리로거 그룹의 분석기 부분의 경우 이 함수는 리로거 패스의 끝에서 호출됩니다. 동일한 리로깅 세션의 분석기 및 relogger 그룹의 분석기 부분의 경우 이 함수는 모든 분석 패스의 끝과 리로거 패스의 끝에서 호출됩니다.

```cpp
virtual AnalysisControl OnEndAnalysisPass();
```

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="onendrelogging"></a><a name="on-end-relogging"></a>온엔드 리로깅

이 함수는 재정의할 수 없습니다. 분석기는 relogger 그룹의 일부인 경우 C++ 빌드 인사이트 SDK에서 호출합니다. 이 함수는 [OnEndAnalysis로](#on-end-analysis)호출을 리디렉션합니다.

```cpp
AnalysisControl OnEndRelogging() final;
```

### <a name="return-value"></a>Return Value

[OnEndAnalysis](#on-end-analysis) 호출의 결과입니다.

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a>온엔드리로깅패스

이 함수는 재정의할 수 없습니다. 분석기는 relogger 그룹의 일부인 경우 C++ 빌드 인사이트 SDK에서 호출합니다. 이 함수는 [OnEndAnalysisPass로](#on-end-analysis-pass)호출을 리디렉션합니다.

```cpp
AnalysisControl OnEndReloggingPass() final;
```

### <a name="return-value"></a>Return Value

[OnEndAnalysisPass](#on-end-analysis-pass) 호출의 결과입니다.

## <a name="onsimpleevent"></a><a name="on-simple-event"></a>온심플 이벤트

이 함수는 간단한 이벤트가 처리될 때 호출됩니다. 이 함수의 두 번째 버전은 재정의할 수 없습니다. 분석기는 relogger 그룹의 일부인 경우 C++ 빌드 인사이트 SDK에서 호출합니다. 버전 2에 대한 모든 호출은 버전 1로 리디렉션됩니다.

### <a name="version-1"></a>버전 1

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

### <a name="version-2"></a>버전 2

```cpp
AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>매개 변수

*이벤트 스택*\
이 간단한 이벤트의 이벤트 스택입니다. 이벤트 스택에 대한 자세한 내용은 [이벤트](../event-table.md)를 참조하십시오.

*다시 로그세션*\
이 매개 변수는 사용되지 않습니다.

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="onstartactivity"></a><a name="on-start-activity"></a>온스타트 활동

이 함수는 활동 시작 이벤트가 처리될 때 호출됩니다. 이 함수의 두 번째 버전은 재정의할 수 없습니다. 분석기는 relogger 그룹의 일부인 경우 C++ 빌드 인사이트 SDK에서 호출합니다. 버전 2에 대한 모든 호출은 버전 1로 리디렉션됩니다.

### <a name="version-1"></a>버전 1

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>버전 2

```cpp
AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>매개 변수

*이벤트 스택*\
이 활동 시작 이벤트의 이벤트 스택입니다. 이벤트 스택에 대한 자세한 내용은 [이벤트](../event-table.md)를 참조하십시오.

*다시 로그세션*\
이 매개 변수는 사용되지 않습니다.

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="onstopactivity"></a><a name="on-stop-activity"></a>온스톱 활동

이 함수는 활동 중지 이벤트가 처리될 때 호출됩니다. 이 함수의 두 번째 버전은 재정의할 수 없습니다. 분석기는 relogger 그룹의 일부인 경우 C++ 빌드 인사이트 SDK에서 호출합니다. 버전 2에 대한 모든 호출은 버전 1로 리디렉션됩니다.

### <a name="version-1"></a>버전 1

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>버전 2

```cpp
AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>매개 변수

*이벤트 스택*\
이 활동 중지 이벤트의 이벤트 스택입니다. 이벤트 스택에 대한 자세한 내용은 [이벤트](../event-table.md)를 참조하십시오.

*다시 로그세션*\
이 매개 변수는 사용되지 않습니다.

### <a name="return-value"></a>Return Value

다음에 발생할 일을 설명하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

::: moniker-end
