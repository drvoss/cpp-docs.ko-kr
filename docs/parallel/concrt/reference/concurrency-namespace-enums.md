---
title: concurrency 네임스페이스 열거형
ms.date: 11/04/2016
f1_keywords:
- CONCRT/concurrency::Agents_EventType
- CONCRT/concurrency::Concrt_TraceFlags
- CONCRT/concurrency::CriticalRegionType
- CONCRT/concurrency::PolicyElementKey
- CONCRT/concurrency::SchedulerType
- CONCRT/concurrency::SwitchingProxyState
- CONCRT/concurrency::WinRTInitializationType
- CONCRT/concurrency::join_type
- CONCRT/concurrency::message_status Enumeration
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
ms.openlocfilehash: e3a943ed52ce9653086203713bb98331f809314d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372718"
---
# <a name="concurrency-namespace-enums"></a>concurrency 네임스페이스 열거형

||||
|-|-|-|
|[Agents_EventType](#agents_eventtype)|[ConcRT_EventType](#concrt_eventtype)|[Concrt_TraceFlags](#concrt_traceflags)|
|[중요 지역 유형](#criticalregiontype)|[동적 진행률 피드백 유형](#dynamicprogressfeedbacktype)|[정책요소키](#policyelementkey)|
|[스케줄러 유형](#schedulertype)|[스케줄링 프로토콜 유형](#schedulingprotocoltype)|[스위칭프록시상태](#switchingproxystate)|
|[윈트초기화유형](#winrtinitializationtype)|[agent_status](#agent_status)|[join_type](#join_type)|
|[message_status](#message_status)|[task_group_status](#task_group_status)|

## <a name="agent_status-enumeration"></a><a name="agent_status"></a>agent_status 열거

`agent`에 유효한 상태입니다.

```cpp
enum agent_status;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`agent_canceled`|`agent`을 취소했습니다.|
|`agent_created`|이 `agent` 생성되었지만 시작되지 않았습니다.|
|`agent_done`|취소 `agent` 하지 않고 완료 되었습니다.|
|`agent_runnable`|이 `agent` 메서드가 시작되었지만 메서드를 `run` 입력하지 않았습니다.|
|`agent_started`|시작되었습니다. `agent`|

### <a name="remarks"></a>설명

자세한 내용은 [비동기 에이전트](../../../parallel/concrt/asynchronous-agents.md)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** concrt.h

## <a name="agents_eventtype-enumeration"></a><a name="agents_eventtype"></a>Agents_EventType 열거

에이전트 라이브러리에서 제공하는 추적 기능을 사용하여 추적할 수 있는 이벤트 형식입니다.

```cpp
enum Agents_EventType;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`AGENTS_EVENT_CREATE`|개체의 생성을 나타내는 이벤트 형식입니다.|
|`AGENTS_EVENT_DESTROY`|개체의 제거를 나타내는 이벤트 형식입니다.|
|`AGENTS_EVENT_END`|일부 처리의 종료를 나타내는 이벤트 형식입니다.|
|`AGENTS_EVENT_LINK`|메시지 블록의 연결을 나타내는 이벤트 형식입니다.|
|`AGENTS_EVENT_NAME`|개체의 이름을 나타내는 이벤트 형식입니다.|
|`AGENTS_EVENT_SCHEDULE`|프로세스의 일정을 나타내는 이벤트 형식입니다.|
|`AGENTS_EVENT_START`|일부 처리의 시작을 나타내는 이벤트 형식입니다.|
|`AGENTS_EVENT_UNLINK`|메시지 블록의 연결 해제를 나타내는 이벤트 형식입니다.|

### <a name="requirements"></a>요구 사항

**헤더:** concrt.h

## <a name="concrt_eventtype-enumeration"></a><a name="concrt_eventtype"></a>ConcRT_EventType 열거

동시성 런타임에서 제공하는 추적 기능을 사용하여 추적할 수 있는 이벤트 형식입니다.

```cpp
enum ConcRT_EventType;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`CONCRT_EVENT_ATTACH`|스케줄러에 연결하는 행위를 나타내는 이벤트 형식입니다.|
|`CONCRT_EVENT_BLOCK`|컨텍스트 차단 행위를 나타내는 이벤트 형식입니다.|
|`CONCRT_EVENT_DETACH`|스케줄러에서 분리하는 행위를 나타내는 이벤트 형식입니다.|
|`CONCRT_EVENT_END`|시작/종료 이벤트 쌍의 시작을 표시하는 이벤트 유형입니다.|
|`CONCRT_EVENT_GENERIC`|기타 이벤트에 사용되는 이벤트 유형입니다.|
|`CONCRT_EVENT_IDLE`|유휴 상태가 되는 컨텍스트의 역할을 나타내는 이벤트 형식입니다.|
|`CONCRT_EVENT_START`|시작/종료 이벤트 쌍의 시작을 표시하는 이벤트 유형입니다.|
|`CONCRT_EVENT_UNBLOCK`|컨텍스트 차단 해제 행위를 나타내는 이벤트 형식입니다.|
|`CONCRT_EVENT_YIELD`|컨텍스트 산출의 행위를 나타내는 이벤트 형식입니다.|

### <a name="requirements"></a>요구 사항

**헤더:** concrt.h **네임스페이스:** 동시성

## <a name="concrt_traceflags-enumeration"></a><a name="concrt_traceflags"></a>Concrt_TraceFlags 열거

이벤트 형식에 대한 추적 플래그입니다.

```cpp
enum Concrt_TraceFlags;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`AgentEventFlag`||
|`AllEventsFlag`||
|`ContextEventFlag`||
|`PPLEventFlag`||
|`ResourceManagerEventFlag`||
|`SchedulerEventFlag`||
|`VirtualProcessorEventFlag`||

### <a name="requirements"></a>요구 사항

**헤더:** concrt.h

## <a name="criticalregiontype-enumeration"></a><a name="criticalregiontype"></a>중요 영역 유형 열거

컨텍스트가 있는 위험 영역의 형식입니다.

```cpp
enum CriticalRegionType;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`InsideCriticalRegion`|컨텍스트가 임계 영역 내에 있음을 나타냅니다. 임계 영역 내부에 있으면 비동기 일시 중단이 스케줄러에서 숨김이 됩니다. 이러한 일시 중단이 발생하면 리소스 관리자는 스레드가 실행 가능해질 때까지 기다렸다가 스케줄러를 다시 호출하는 대신 다시 시작합니다. 이러한 영역 내에서 가져온 모든 잠금은 세심한 주의를 기울여야 합니다.|
|`InsideHyperCriticalRegion`|컨텍스트가 매우 중요한 영역 내에 있음을 나타냅니다. 초임계 영역 내에서는 동기 및 비동기 일시 중단이 스케줄러에서 숨김이 모두 있습니다. 이러한 일시 중단 또는 차단이 발생하면 리소스 관리자는 스레드가 실행 가능해질 때까지 기다렸다가 스케줄러를 다시 호출하는 대신 다시 시작합니다. 이러한 리전 내에서 가져온 잠금은 이러한 영역 외부에서 실행되는 코드와 공유해서는 안 됩니다. 이렇게 하면 예기치 않은 교착 상태가 발생합니다.|
|`OutsideCriticalRegion`|컨텍스트가 모든 중요 영역 외부에 있음을 나타냅니다.|

### <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

## <a name="dynamicprogressfeedbacktype-enumeration"></a><a name="dynamicprogressfeedbacktype"></a>동적 진행률 피드백 유형 열거형

`DynamicProgressFeedback` 정책에서 스케줄러에 대한 리소스를 스케줄러에서 수집한 통계 정보에 따라 균형을 조정할지, 아니면 `IVirtualProcessorRoot` 인터페이스의 `Activate` 및 `Deactivate` 메서드 호출을 통해 유휴 상태로 들어오고 나가는 가상 프로세서를 기준으로만 균형을 조정할지를 설명하는 데 사용됩니다. 사용 가능한 스케줄러 정책에 대한 자세한 내용은 [PolicyElementKey](concurrency-namespace-enums.md)를 참조하십시오.

```cpp
enum DynamicProgressFeedbackType;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`ProgressFeedbackDisabled`|스케줄러는 진행률 정보를 수집하지 않습니다. 재조정은 기본 하드웨어 스레드의 구독 수준에만 따라 수행됩니다. 구독 수준에 대한 자세한 내용은 [IExecutionResource::현재 구독 수준](IExecutionResource-structure.md)을 참조하십시오.<br /><br /> 이 값은 런타임에서 사용하도록 예약되어 있습니다.|
|`ProgressFeedbackEnabled`|스케줄러는 진행률 정보를 수집하여 리소스 관리자에게 전달합니다. 리소스 관리자는 이 통계 정보를 활용하여 기본 하드웨어 스레드의 구독 수준 외에 스케줄러를 대신하여 리소스의 균형을 조정합니다. 구독 수준에 대한 자세한 내용은 [IExecutionResource::현재 구독 수준](IExecutionResource-structure.md)을 참조하십시오.|

## <a name="join_type-enumeration"></a><a name="join_type"></a>join_type 열거

`join` 메시징 블록의 형식입니다.

```cpp
enum join_type;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`greedy`|Greedy `join` 메시징 블록은 전파 시 즉시 메시지를 수락합니다. 이는 더 효율적이지만 네트워크 구성에 따라 라이브 잠금이 가능합니다.|
|`non_greedy`|탐욕스키 `join` 메시징 블록은 메시지를 연기하고 모든 메시지가 도착한 후에 메시지를 시도하고 소비합니다. 이들은 작동하도록 보장되지만 더 느립니다.|

### <a name="requirements"></a>요구 사항

**헤더:** agents.h

## <a name="message_status-enumeration"></a><a name="message_status"></a>message_status 열거

블록에 대한 `message` 개체 제공에 유효한 응답입니다.

```cpp
enum message_status;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`accepted`|대상이 메시지를 수락했습니다.|
|`declined`|대상이 메시지를 수락하지 않았습니다.|
|`missed`|대상이 메시지를 수락하려고 했지만 더 이상 사용할 수 없습니다.|
|`postponed`|대상이 메시지를 연기했습니다.|

### <a name="requirements"></a>요구 사항

**헤더:** agents.h

## <a name="policyelementkey-enumeration"></a><a name="policyelementkey"></a>정책요소키 열거

스케줄러 동작의 측면을 설명하는 정책 키입니다. 각 정책 요소는 키-값 쌍으로 설명됩니다. 스케줄러 정책 및 스케줄러에 미치는 영향에 대한 자세한 내용은 [작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)를 참조하십시오.

```cpp
enum PolicyElementKey;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`ContextPriority`|스케줄러의 각 컨텍스트의 운영 체제 스레드 우선 순위입니다. 이 키가 값으로 `INHERIT_THREAD_PRIORITY` 설정되면 스케줄러의 컨텍스트는 스케줄러를 만든 스레드의 우선 순위를 상속합니다.<br /><br /> 유효한 값 : Windows `SetThreadPriority` 함수및 특수 값에 대한 유효한 값 중 어느 값일지`INHERIT_THREAD_PRIORITY`<br /><br /> 기본값 :`THREAD_PRIORITY_NORMAL`|
|`ContextStackSize`|킬로바이트의 스케줄러에서 각 컨텍스트의 예약된 스택 크기입니다.<br /><br /> 유효한 값 : 양수 정수<br /><br /> 기본값 `0`: 스택 크기에 대한 프로세스의 기본값을 사용할 수 있음을 나타냅니다.|
|`DynamicProgressFeedback`|스케줄러에서 수집한 통계 정보에 따라 또는 기본 하드웨어 스레드의 구독 수준에 따라 스케줄러의 리소스를 재조정할지 여부를 결정합니다. 자세한 내용은 [DynamicProgressFeedbackType](#dynamicprogressfeedbacktype)을 참조하십시오.<br /><br /> 유효한 값 : 열거형의 `DynamicProgressFeedbackType` 멤버 `ProgressFeedbackEnabled` 또는`ProgressFeedbackDisabled`<br /><br /> 기본값 :`ProgressFeedbackEnabled`|
|`LocalContextCacheSize`|`SchedulingProtocol` 정책 키가 값으로 `EnhanceScheduleGroupLocality`설정되면 가상 프로세서 로컬 큐당 캐시할 수 있는 실행 가능한 컨텍스트의 최대 수를 지정합니다. 이러한 컨텍스트는 일반적으로 실행 가능해지도록 하는 가상 프로세서의 LIFO(선입호) 순서로 실행됩니다. 이 정책 키는 `SchedulingProtocol` 키가 값으로 `EnhanceForwardProgress`설정될 때 아무런 의미가 없습니다.<br /><br /> 유효한 값 : 음수 정수<br /><br /> 기본값 :`8`|
|`MaxConcurrency`|스케줄러에서 원하는 최대 동시성 수준입니다. 리소스 관리자는 처음에 이 많은 가상 프로세서를 할당하려고 합니다. [MaxExecutionResources라는](concurrency-namespace-constants1.md#maxexecutionresources) 특수 값은 원하는 동시성 수준이 컴퓨터의 하드웨어 스레드 수와 동일하다는 것을 나타냅니다. 에 `MinConcurrency` 대해 지정된 값이 컴퓨터의 `MaxConcurrency` 하드웨어 스레드 수보다 크고 `MaxExecutionResources`로 지정된 경우 `MaxConcurrency` 에 대한 값이 `MinConcurrency`에 대해 설정된 값과 일치하도록 발생합니다.<br /><br /> 유효한 값 : 양수 정수 및 특수 값`MaxExecutionResources`<br /><br /> 기본값 :`MaxExecutionResources`|
|`MaxPolicyElementKey`|최대 정책 요소 키입니다. 유효한 요소 키가 아닙니다.|
|`MinConcurrency`|리소스 관리자가 스케줄러에 제공해야 하는 최소 동시성 수준입니다. 스케줄러에 할당된 가상 프로세서 의 수는 최소 값 아래로 이동하지 않습니다. [MaxExecutionResources라는](concurrency-namespace-constants1.md#maxexecutionresources) 특수 값은 최소 동시성 수준이 컴퓨터의 하드웨어 스레드 수와 동일하다는 것을 나타냅니다. 에 대해 지정된 `MaxConcurrency` 값이 컴퓨터의 하드웨어 스레드 수보다 `MinConcurrency` 작고 `MaxExecutionResources`로 지정된 `MinConcurrency` 경우 에 대한 값이 `MaxConcurrency`에 대해 설정된 값과 일치하도록 낮아집니다.<br /><br /> 유효한 값 : 음수 정수 및 `MaxExecutionResources`특수 값입니다. 동시성 런타임이 스케줄러의 생성에 사용되는 스케줄러 정책의 경우에는 값 `0`이 유효하지 않습니다.<br /><br /> 기본값 :`1`|
|`SchedulerKind`|스케줄러가 기본 실행 컨텍스트에 사용할 스레드 유형입니다. 자세한 내용은 [스케줄러 유형](#schedulertype)을 참조하십시오.<br /><br /> 유효한 값: `SchedulerType` 열거형의 멤버. 예: `ThreadScheduler`<br /><br /> 기본값 `ThreadScheduler`: . 이는 모든 운영 체제에서 Win32 스레드로 변환됩니다.|
|`SchedulingProtocol`|스케줄러에서 사용할 스케줄링 알고리즘에 대해 설명합니다. 자세한 내용은 [스케줄링프로토콜유형](#schedulingprotocoltype)을 참조하십시오.<br /><br /> 유효한 값 : 열거형의 `SchedulingProtocolType` 멤버 `EnhanceScheduleGroupLocality` 또는`EnhanceForwardProgress`<br /><br /> 기본값 :`EnhanceScheduleGroupLocality`|
|`TargetOversubscriptionFactor`|하드웨어 스레드당 가상 프로세서의 미정 수입니다. 필요할 경우 시스템의 하드웨어 스레드로 `MaxConcurrency`를 만족시키기 위해 리소스 관리자에서 대상 초과 구독 비율을 증가시킬 수 있습니다.<br /><br /> 유효한 값 : 양수 정수<br /><br /> 기본값 :`1`|
|`WinRTInitialization`||

### <a name="requirements"></a>요구 사항

**헤더:** concrt.h

## <a name="schedulertype-enumeration"></a><a name="schedulertype"></a>스케줄형식 열거

`SchedulerKind` 정책에서 스케줄러가 기본 실행 컨텍스트에 활용해야 하는 스레드 형식을 설명하는 데 사용됩니다. 사용 가능한 스케줄러 정책에 대한 자세한 내용은 [PolicyElementKey](concurrency-namespace-enums.md)를 참조하십시오.

```cpp
enum SchedulerType;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`ThreadScheduler`|일반 Win32 스레드의 명시적 요청을 나타냅니다.|
|`UmsThreadDefault`|사용자 모드 예약 가능(UMS) 스레드는 Visual Studio 2013의 동시성 런타임에서 지원되지 않습니다. `UmsThreadDefault`를 `SchedulerType` 정책의 값으로 사용하면 오류가 발생하지 않습니다. 그러나 해당 정책을 사용하여 만들어진 스케줄러는 기본적으로 Win32 스레드를 사용합니다.|

### <a name="requirements"></a>요구 사항

**헤더:** concrt.h

## <a name="schedulingprotocoltype-enumeration"></a><a name="schedulingprotocoltype"></a>스케줄링 프로토콜 유형 열거

`SchedulingProtocol` 정책에서 스케줄러에 활용되는 일정 알고리즘을 설명하는 데 사용됩니다. 사용 가능한 스케줄러 정책에 대한 자세한 내용은 [PolicyElementKey](concurrency-namespace-enums.md)를 참조하십시오.

```cpp
enum SchedulingProtocolType;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`EnhanceForwardProgress`|스케줄러는 각 작업을 실행한 후 일정 그룹을 통해 라운드 로빈을 선호합니다. 차단되지 않은 컨텍스트는 일반적으로 FIFO(선입호선) 방식으로 예약됩니다. 가상 프로세서는 차단되지 않은 컨텍스트를 캐시하지 않습니다.|
|`EnhanceScheduleGroupLocality`|스케줄러는 다른 일정 그룹으로 이동하기 전에 현재 일정 그룹 내의 작업에 대해 계속 작업하는 것을 선호합니다. 차단되지 않은 컨텍스트는 가상 프로세서별로 캐시되며 일반적으로 차단을 해제한 가상 프로세서에 의해 LIFO(마지막 선입시) 방식으로 예약됩니다.|

### <a name="requirements"></a>요구 사항

**헤더:** concrt.h

## <a name="switchingproxystate-enumeration"></a><a name="switchingproxystate"></a>스위칭프록시상태 열거

다른 스레드 프록시로의 협조적 컨텍스트 전환을 실행하는 경우 스레드 프록시의 현재 상태를 나타내는 데 사용됩니다.

```cpp
enum SwitchingProxyState;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`Blocking`|호출 스레드가 협조적으로 차단되고 있으며 이후에 다시 실행되고 다른 작업을 수행할 때까지 호출자에서 독점적으로 소유해야 한다는 것을 나타냅니다.|
|`Idle`|호출 스레드가 스케줄러에서 더 이상 필요하지 않으며 리소스 관리자로 반환되고 있음을 나타냅니다. 디스패치되는 컨텍스트는 더 이상 리소스 관리자에서 사용할 수 없습니다.|
|`Nesting`|호출 스레드가 하위 스케줄러를 중첩하고 다른 스케줄러에 연결하기 위해 호출자가 필요합니다.|

### <a name="remarks"></a>설명

형식의 `SwitchingProxyState` 매개 변수는 리소스 `IThreadProxy::SwitchTo` 관리자가 호출하는 스레드 프록시를 처리하는 방법을 알려주는 메서드에 전달됩니다.

이 형식이 사용되는 방법에 대한 자세한 내용은 [IThreadProxy:SwitchTo](ithreadproxy-structure.md#switchto)를 참조하십시오.

## <a name="task_group_status-enumeration"></a><a name="task_group_status"></a>task_group_status 열거

`task_group` 또는 `structured_task_group` 개체의 실행 상태를 설명합니다. 이 형식의 값은 작업 그룹에 예약된 작업이 완료되기를 기다리는 수많은 메서드에 의해 반환됩니다.

```cpp
enum task_group_status;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`canceled`|`task_group` 또는 `structured_task_group` 개체가 취소되었습니다. 하나 이상의 작업이 실행되지 않았을 수 있습니다.|
|`completed`|`task_group` 또는 `structured_task_group` 개체의 큐에 대기 중인 작업이 성공적으로 완료되었습니다.|
|`not_complete`|`task_group` 개체의 큐에 대기 중인 작업이 완료되지 않았습니다. 이 값은 현재 동시성 런타임에서 반환되지 않습니다.|

### <a name="requirements"></a>요구 사항

**헤더:** pplinterface.h

## <a name="winrtinitializationtype-enumeration"></a><a name="winrtinitializationtype"></a>WinRT 초기화유형 열거형

`WinRTInitialization` 정책에서 Windows 8 또는 그 이상 버전의 운영 체제에서 실행되는 애플리케이션에 대한 스케줄러 스레드에서 Windows 런타임이 초기화될지 여부와 초기화되는 방법을 설명하는데 사용됩니다. 사용 가능한 스케줄러 정책에 대한 자세한 내용은 [PolicyElementKey](concurrency-namespace-enums.md)를 참조하십시오.

```cpp
enum WinRTInitializationType;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`DoNotInitializeWinRT`|애플리케이션이 Windows 8 또는 그 이상 버전의 운영 체제에서 실행될 경우 스케줄러 내의 스레드는 Windows 런타임을 초기화하지 않습니다.|
|`InitializeWinRTAsMTA`|애플리케이션이 Windows 8 또는 그 이상 버전의 운영 체제에서 실행할 경우 스케줄러 내의 각 스레드는 Windows 런타임을 초기화하고 이것을 멀티스레드의 일부로 선언합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)
