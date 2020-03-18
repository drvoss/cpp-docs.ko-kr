---
title: agent 클래스
ms.date: 11/04/2016
f1_keywords:
- agent
- AGENTS/concurrency::agent
- AGENTS/concurrency::agent::agent
- AGENTS/concurrency::agent::cancel
- AGENTS/concurrency::agent::start
- AGENTS/concurrency::agent::status
- AGENTS/concurrency::agent::status_port
- AGENTS/concurrency::agent::wait
- AGENTS/concurrency::agent::wait_for_all
- AGENTS/concurrency::agent::wait_for_one
- AGENTS/concurrency::agent::done
- AGENTS/concurrency::agent::run
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
ms.openlocfilehash: f0092f5f90bbdf253c09dbdc80849c3db472212f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79427478"
---
# <a name="agent-class"></a>agent 클래스

모든 독립 에이전트에 대한 기본 클래스로 사용되는 클래스입니다. 다른 에이전트로부터 상태를 숨기고 메시지 전달을 사용하여 상호 작용하는 데 사용됩니다.

## <a name="syntax"></a>구문

```cpp
class agent;
```

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[에이전트](#ctor)|오버로드되었습니다. 에이전트를 생성 합니다.|
|[~ 에이전트 소멸자](#dtor)|에이전트를 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[cancel](#cancel)|에이전트를 `agent_created` 또는 `agent_runnable` 상태에서 `agent_canceled` 상태로 이동 합니다.|
|[start](#start)|에이전트를 `agent_created` 상태에서 `agent_runnable` 상태로 이동 하 고 실행을 예약 합니다.|
|[status](#status)|에이전트의 상태 정보에 대 한 동기 원본입니다.|
|[status_port](#status_port)|에이전트의 상태 정보에 대 한 비동기 원본입니다.|
|[대기한](#wait)|에이전트가 작업을 완료할 때까지 기다립니다.|
|[wait_for_all](#wait_for_all)|지정 된 모든 에이전트가 작업을 완료할 때까지 기다립니다.|
|[wait_for_one](#wait_for_one)|지정 된 에이전트 중 하나가 해당 작업을 완료할 때까지 기다립니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[done](#done)|에이전트를 `agent_done` 상태로 이동 하 여 에이전트가 완료 되었음을 나타냅니다.|
|[run](#run)|에이전트의 주 작업을 나타냅니다. `run` 파생 클래스에서 재정의 되 고 에이전트가 시작 된 후 수행 해야 하는 작업을 지정 합니다.|

## <a name="remarks"></a>설명

자세한 내용은 [비동기 에이전트](../../../parallel/concrt/asynchronous-agents.md)를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

`agent`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

## <a name="ctor"></a>에이전트

에이전트를 생성 합니다.

```cpp
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```

### <a name="parameters"></a>매개 변수

*_PScheduler*<br/>
에이전트의 실행 태스크가 예약 된 `Scheduler` 개체입니다.

*_PGroup*<br/>
에이전트의 실행 태스크가 예약 된 `ScheduleGroup` 개체입니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.

### <a name="remarks"></a>설명

런타임은 `_PScheduler` 또는 `_PGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.

## <a name="dtor"></a>~ 에이전트

에이전트를 소멸 시킵니다.

```cpp
virtual ~agent();
```

### <a name="remarks"></a>설명

터미널 상태가 아닌 에이전트 (`agent_done` 또는 `agent_canceled`)를 삭제 하는 것은 오류입니다. 이는 `agent` 클래스에서 상속 되는 클래스의 소멸자에서 에이전트가 터미널 상태에 도달할 때까지 대기 하 여 방지할 수 있습니다.

## <a name="cancel"></a>취소

에이전트를 `agent_created` 또는 `agent_runnable` 상태에서 `agent_canceled` 상태로 이동 합니다.

```cpp
bool cancel();
```

### <a name="return-value"></a>Return Value

에이전트가 취소 되었으면 **true** 이 고, 그렇지 않으면 **false** 입니다. 에이전트의 실행이 이미 시작 되었거나 이미 완료 된 경우에는 에이전트를 취소할 수 없습니다.

## <a name="done"></a>끝났습니다

에이전트를 `agent_done` 상태로 이동 하 여 에이전트가 완료 되었음을 나타냅니다.

```cpp
bool done();
```

### <a name="return-value"></a>Return Value

에이전트가 `agent_done` 상태로 이동 하면 **true** 이 고, 그렇지 않으면 **false** 입니다. 취소 된 에이전트는 `agent_done` 상태로 이동할 수 없습니다.

### <a name="remarks"></a>설명

에이전트의 실행이 완료 된 것을 알고 있는 경우 `run` 메서드의 끝에서이 메서드를 호출 해야 합니다.

## <a name="run"></a>실행할지

에이전트의 주 작업을 나타냅니다. `run` 파생 클래스에서 재정의 되 고 에이전트가 시작 된 후 수행 해야 하는 작업을 지정 합니다.

```cpp
virtual void run() = 0;
```

### <a name="remarks"></a>설명

에이전트 상태는이 메서드를 호출 하기 직전에 `agent_started`로 변경 됩니다. 메서드는를 반환 하기 전에 적절 한 상태를 사용 하 여 에이전트에 대 한 `done`를 호출 하 고 예외를 throw 하지 않을 수 있습니다.

## <a name="start"></a>시작

에이전트를 `agent_created` 상태에서 `agent_runnable` 상태로 이동 하 고 실행을 예약 합니다.

```cpp
bool start();
```

### <a name="return-value"></a>Return Value

에이전트가 올바르게 시작 되었으면 **true** 이 고, 그렇지 않으면 **false** 입니다. 취소 된 에이전트는 시작할 수 없습니다.

## <a name="status"></a>업무

에이전트의 상태 정보에 대 한 동기 원본입니다.

```cpp
agent_status status();
```

### <a name="return-value"></a>Return Value

에이전트의 현재 상태를 반환 합니다. 반환 된 상태는 반환 된 후 즉시 변경 될 수 있습니다.

## <a name="status_port"></a>status_port

에이전트의 상태 정보에 대 한 비동기 원본입니다.

```cpp
ISource<agent_status>* status_port();
```

### <a name="return-value"></a>Return Value

에이전트의 현재 상태에 대 한 메시지를 보낼 수 있는 메시지 원본을 반환 합니다.

## <a name="wait"></a>대기한

에이전트가 작업을 완료할 때까지 기다립니다.

```cpp
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>매개 변수

*_PAgent*<br/>
대기할 에이전트에 대 한 포인터입니다.

*_Timeout*<br/>
대기할 최대 시간 (밀리초)입니다.

### <a name="return-value"></a>Return Value

대기가 완료 되 면 에이전트의 `agent_status`입니다. `agent_canceled` 또는 `agent_done`수 있습니다.

### <a name="remarks"></a>설명

에이전트가 `agent_canceled` 또는 `agent_done` 상태로 들어가면 에이전트 태스크가 완료 됩니다.

`_Timeout` 매개 변수에 상수 `COOPERATIVE_TIMEOUT_INFINITE`이외의 값이 있는 경우 에이전트가 태스크를 완료 하기 전에 지정 된 시간이 만료 되 면 [operation_timed_out](operation-timed-out-class.md) 예외가 throw 됩니다.

## <a name="wait_for_all"></a>wait_for_all

지정 된 모든 에이전트가 작업을 완료할 때까지 기다립니다.

```cpp
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>매개 변수

*count*<br/>
`_PAgents`배열에 있는 에이전트 포인터의 수입니다.

*_PAgents*<br/>
대기할 에이전트에 대 한 포인터의 배열입니다.

*_PStatus*<br/>
에이전트 상태 배열에 대 한 포인터입니다. 각 상태 값은 메서드가 반환 될 때 해당 에이전트의 상태를 나타냅니다.

*_Timeout*<br/>
대기할 최대 시간 (밀리초)입니다.

### <a name="remarks"></a>설명

에이전트가 `agent_canceled` 또는 `agent_done` 상태로 들어가면 에이전트 태스크가 완료 됩니다.

`_Timeout` 매개 변수에 상수 `COOPERATIVE_TIMEOUT_INFINITE`이외의 값이 있는 경우 에이전트가 태스크를 완료 하기 전에 지정 된 시간이 만료 되 면 [operation_timed_out](operation-timed-out-class.md) 예외가 throw 됩니다.

## <a name="wait_for_one"></a>wait_for_one

지정 된 에이전트 중 하나가 해당 작업을 완료할 때까지 기다립니다.

```cpp
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>매개 변수

*count*<br/>
`_PAgents`배열에 있는 에이전트 포인터의 수입니다.

*_PAgents*<br/>
대기할 에이전트에 대 한 포인터의 배열입니다.

*_Status*<br/>
에이전트 상태를 배치할 변수에 대 한 참조입니다.

*_Index*<br/>
에이전트 인덱스가 배치 될 변수에 대 한 참조입니다.

*_Timeout*<br/>
대기할 최대 시간 (밀리초)입니다.

### <a name="remarks"></a>설명

에이전트가 `agent_canceled` 또는 `agent_done` 상태로 들어가면 에이전트 태스크가 완료 됩니다.

`_Timeout` 매개 변수에 상수 `COOPERATIVE_TIMEOUT_INFINITE`이외의 값이 있는 경우 에이전트가 태스크를 완료 하기 전에 지정 된 시간이 만료 되 면 [operation_timed_out](operation-timed-out-class.md) 예외가 throw 됩니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)
