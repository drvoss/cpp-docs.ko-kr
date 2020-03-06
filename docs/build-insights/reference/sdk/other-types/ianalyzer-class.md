---
title: IAnalyzer 클래스
description: C++ BUILD Insights SDK ianalyzer 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IAnalyzer
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 53f7b36695bb24d96ccfe88afbb56ff717c94dc9
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334081"
---
# <a name="ianalyzer-class"></a>IAnalyzer 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`IAnalyzer` 클래스는 ETW (ETW(Windows용 이벤트 추적)) 추적을 분석 하기 위한 인터페이스를 제공 합니다. [MakeDynamicAnalyzerGroup](../functions/make-dynamic-analyzer-group.md), [MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md), [MakeStaticAnalyzerGroup](../functions/make-dynamic-analyzer-group.md)및 [MakeStaticReloggerGroup](../functions/make-static-analyzer-group.md) 함수와 함께 사용 됩니다. `IAnalyzer`를 기본 클래스로 사용 하 여 분석기 또는 재로 거 거 그룹의 일부가 될 수 있는 자체 분석기를 만듭니다.

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

## <a name="remarks"></a>주의

`IAnalyzer`에서 파생 되는 클래스는 분석기와 reloggers 모두 사용할 수 있습니다. Reloggers 거로 사용 되는 경우에는 reloggers 관련 된 함수가 해당 분석기로 리디렉션됩니다. 반대의 경우는 그렇지 않습니다. `IRelogger`에서 파생 되는 클래스를 분석기로 사용할 수 없습니다. 재로 거 거 그룹에서 분석기를 사용 하는 것은 일반적인 패턴입니다. 재로 거 거 그룹의 초기 위치에 배치 되 면 분석기는 정보를 미리 계산 하 고 이후 위치에서 다시로 거에 사용할 수 있도록 설정할 수 있습니다.

재정의 되지 않는 모든 함수의 기본 반환 값은 `AnalysisControl::CONTINUE`입니다. 자세한 내용은 [AnalysisControl](analysis-control-enum-class.md)를 참조 하세요.

## <a name="members"></a>멤버

`IRelogger` 인터페이스의 [Ontraceinfo](irelogger-class.md#on-trace-info) 멤버 외에도 `IAnalyzer` 클래스에는 다음 멤버가 포함 되어 있습니다.

### <a name="destructor"></a>소멸자

[~ IAnalyzer](#ianalyzer-destructor)

### <a name="functions"></a>함수

[Onbeginanalysis](#on-begin-analysis)\
[OnBeginAnalysisPass](#on-begin-analysis-pass)\
[Onbeginrelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndAnalysis](#on-end-analysis)\
[OnEndAnalysisPass](#on-end-analysis-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[Onstartactivity](#on-start-activity)\
[OnStopActivity](#on-stop-activity)

## <a name="ianalyzer-destructor"></a>~ IAnalyzer

IAnalyzer 클래스를 소멸 시킵니다.

```cpp
virtual ~IAnalyzer();
```

## <a name="on-begin-analysis"></a>OnBeginAnalysis

분석기 그룹의 분석기 부분에 대해이 함수는 첫 번째 분석 단계가 시작 되기 전에 호출 됩니다. 재로 거 거 그룹의 분석기 부분에 대해이 함수는 다시 로깅 패스가 시작 되기 전에 호출 됩니다. 동일한 재로 거 세션의 분석기 및 재로 거 거 그룹 모두의 분석기 부분에 대해이 함수는 첫 번째 분석 단계가 시작 되기 전에 두 번 호출 됩니다.

```cpp
virtual AnalysisControl OnBeginAnalysis();
```

### <a name="return-value"></a>반환 값

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-begin-analysis-pass"></a>OnBeginAnalysisPass

분석기 그룹의 분석기 부분에서이 함수는 모든 분석 단계가 시작 될 때 호출 됩니다. 재로 거 거 그룹의 분석기 부분에서이 함수는 재로 거 pass의 시작 부분에서 호출 됩니다. 동일한 재로 거 세션의 분석기 및 재로 거 거 그룹 모두의 분석기 부분에 대해이 함수는 모든 분석 패스의 시작 부분에서 그리고 재로 거 pass의 시작 부분에서 호출 됩니다.

```cpp
virtual AnalysisControl OnBeginAnalysisPass();
```

### <a name="return-value"></a>반환 값

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-begin-relogging"></a>OnBeginRelogging

```cpp
AnalysisControl OnBeginRelogging() final;
```

이 함수는 재정의할 수 없습니다. 분석기가 재로 거 거 C++ 그룹의 일부인 경우 Build Insights SDK에서 호출 됩니다. 이 함수는 [Onbeginanalysis](#on-begin-analysis)에 대 한 호출을 리디렉션합니다.

### <a name="return-value"></a>반환 값

[Onbeginanalysis](#on-begin-analysis) 호출의 결과입니다.

## <a name="on-begin-relogging-pass"></a>OnBeginReloggingPass

이 함수는 재정의할 수 없습니다. 분석기가 재로 거 거 C++ 그룹의 일부인 경우 Build Insights SDK에서 호출 됩니다. 이 함수는 [OnBeginAnalysisPass](#on-begin-analysis-pass)에 대 한 호출을 리디렉션합니다.

```cpp
AnalysisControl OnBeginReloggingPass() final;
```

### <a name="return-value"></a>반환 값

[OnBeginAnalysisPass](#on-begin-analysis-pass) 호출의 결과입니다.

## <a name="on-end-analysis"></a>OnEndAnalysis

분석기 그룹의 일부인 분석기의 경우이 함수는 마지막 분석 단계가 종료 된 후에 호출 됩니다. 재로 거 거 그룹에 속하는 분석기의 경우,이 함수는 다시 로깅 패스가 종료 된 후에 호출 됩니다. 동일한 재로 거 세션의 분석기 및 재로 거 거 그룹 모두에 속하는 분석기의 경우이 함수는 두 번 호출 됩니다.

1. 모든 분석 단계가 종료 되 고 다시 로깅 패스가 시작 되기 전에
1. 다시 로깅 단계가 종료 된 후

```cpp
virtual AnalysisControl OnEndAnalysis();
```

### <a name="return-value"></a>반환 값

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-end-analysis-pass"></a>OnEndAnalysisPass

분석기 그룹의 분석기 부분에서이 함수는 모든 분석 단계가 끝날 때 호출 됩니다. 재로 거 거 그룹의 분석기 부분에서이 함수는 재로 거 pass의 끝에서 호출 됩니다. 동일한 재로 거 세션의 분석기 및 다시로 거 그룹 모두의 분석기 부분에 대해이 함수는 모든 분석 패스의 끝에서 그리고 재로 거 pass의 끝에서 호출 됩니다.

```cpp
virtual AnalysisControl OnEndAnalysisPass();
```

### <a name="return-value"></a>반환 값

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-end-relogging"></a>OnEndRelogging

이 함수는 재정의할 수 없습니다. 분석기가 재로 거 거 C++ 그룹의 일부인 경우 Build Insights SDK에서 호출 됩니다. 이 함수는 [OnEndAnalysis](#on-end-analysis)에 대 한 호출을 리디렉션합니다.

```cpp
AnalysisControl OnEndRelogging() final;
```

### <a name="return-value"></a>반환 값

[OnEndAnalysis](#on-end-analysis) 호출의 결과입니다.

## <a name="on-end-relogging-pass"></a>OnEndReloggingPass

이 함수는 재정의할 수 없습니다. 분석기가 재로 거 거 C++ 그룹의 일부인 경우 Build Insights SDK에서 호출 됩니다. 이 함수는 [OnEndAnalysisPass](#on-end-analysis-pass)에 대 한 호출을 리디렉션합니다.

```cpp
AnalysisControl OnEndReloggingPass() final;
```

### <a name="return-value"></a>반환 값

[OnEndAnalysisPass](#on-end-analysis-pass) 호출의 결과입니다.

## <a name="on-simple-event"></a>OnSimpleEvent

이 함수는 단순 이벤트가 처리 될 때 호출 됩니다. 이 함수의 두 번째 버전은 재정의할 수 없습니다. 분석기가 재로 거 거 C++ 그룹의 일부인 경우 Build Insights SDK에서 호출 됩니다. 버전 2에 대 한 모든 호출은 버전 1로 리디렉션됩니다.

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

*Eventstack*\
이 간단한 이벤트에 대 한 이벤트 스택입니다. 이벤트 스택에 대 한 자세한 내용은 [이벤트](../event-table.md)를 참조 하세요.

*Relogsession*\
이 매개 변수는 사용되지 않습니다.

### <a name="return-value"></a>반환 값

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-start-activity"></a>OnStartActivity

이 함수는 작업 시작 이벤트가 처리 될 때 호출 됩니다. 이 함수의 두 번째 버전은 재정의할 수 없습니다. 분석기가 재로 거 거 C++ 그룹의 일부인 경우 Build Insights SDK에서 호출 됩니다. 버전 2에 대 한 모든 호출은 버전 1로 리디렉션됩니다.

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

*Eventstack*\
이 작업 시작 이벤트에 대 한 이벤트 스택입니다. 이벤트 스택에 대 한 자세한 내용은 [이벤트](../event-table.md)를 참조 하세요.

*Relogsession*\
이 매개 변수는 사용되지 않습니다.

### <a name="return-value"></a>반환 값

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

## <a name="on-stop-activity"></a>OnStopActivity

이 함수는 활동 중지 이벤트가 처리 될 때 호출 됩니다. 이 함수의 두 번째 버전은 재정의할 수 없습니다. 분석기가 재로 거 거 C++ 그룹의 일부인 경우 Build Insights SDK에서 호출 됩니다. 버전 2에 대 한 모든 호출은 버전 1로 리디렉션됩니다.

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

*Eventstack*\
이 작업 중지 이벤트의 이벤트 스택입니다. 이벤트 스택에 대 한 자세한 내용은 [이벤트](../event-table.md)를 참조 하세요.

*Relogsession*\
이 매개 변수는 사용되지 않습니다.

### <a name="return-value"></a>반환 값

다음에 수행 해야 하는 작업을 설명 하는 [AnalysisControl](analysis-control-enum-class.md) 코드입니다.

::: moniker-end
