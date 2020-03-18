---
title: source_block 클래스
ms.date: 11/04/2016
f1_keywords:
- source_block
- AGENTS/concurrency::source_block
- AGENTS/concurrency::source_block::source_block
- AGENTS/concurrency::source_block::accept
- AGENTS/concurrency::source_block::acquire_ref
- AGENTS/concurrency::source_block::consume
- AGENTS/concurrency::source_block::link_target
- AGENTS/concurrency::source_block::release
- AGENTS/concurrency::source_block::release_ref
- AGENTS/concurrency::source_block::reserve
- AGENTS/concurrency::source_block::unlink_target
- AGENTS/concurrency::source_block::unlink_targets
- AGENTS/concurrency::source_block::accept_message
- AGENTS/concurrency::source_block::async_send
- AGENTS/concurrency::source_block::consume_message
- AGENTS/concurrency::source_block::enable_batched_processing
- AGENTS/concurrency::source_block::initialize_source
- AGENTS/concurrency::source_block::link_target_notification
- AGENTS/concurrency::source_block::process_input_messages
- AGENTS/concurrency::source_block::propagate_output_messages
- AGENTS/concurrency::source_block::propagate_to_any_targets
- AGENTS/concurrency::source_block::release_message
- AGENTS/concurrency::source_block::remove_targets
- AGENTS/concurrency::source_block::reserve_message
- AGENTS/concurrency::source_block::resume_propagation
- AGENTS/concurrency::source_block::sync_send
- AGENTS/concurrency::source_block::unlink_target_notification
- AGENTS/concurrency::source_block::wait_for_outstanding_async_sends
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
ms.openlocfilehash: 3a0d69bc2e2904b1dcf37a7e9891d95bd869a610
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424190"
---
# <a name="source_block-class"></a>source_block 클래스

`source_block` 클래스는 소스 전용 블록에 대한 추상 기본 클래스입니다. 이 클래스는 기본 링크 관리 기능 및 일반적인 오류 검사를 제공합니다.

## <a name="syntax"></a>구문

```cpp
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```

### <a name="parameters"></a>매개 변수

*_TargetLinkRegistry*<br/>
대상 링크를 보유 하는 데 사용할 링크 레지스트리

*_MessageProcessorType*<br/>
메시지 처리를 위한 프로세서 유형입니다.

## <a name="members"></a>구성원

### <a name="public-typedefs"></a>공용 형식 정의

|속성|Description|
|----------|-----------------|
|`target_iterator`|연결 된 대상을 탐색 하는 반복기입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[source_block](#ctor)|`source_block` 개체를 생성합니다.|
|[~ source_block 소멸자](#dtor)|`source_block` 개체를 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[수락할](#accept)|이 `source_block` 개체가 제공 하는 메시지를 수락 하 여 호출자에 게 소유권을 전송 합니다.|
|[acquire_ref](#acquire_ref)|삭제를 방지 하기 위해이 `source_block` 개체에 대 한 참조 횟수를 가져옵니다.|
|[consume](#consume)|이 `source_block` 개체에서 이전에 제공 하 고 대상에 의해 성공적으로 예약 되어 호출자에 게 소유권을 전송 하는 메시지를 사용 합니다.|
|[link_target](#link_target)|대상 블록을이 `source_block` 개체에 연결 합니다.|
|[release](#release)|이전의 성공적인 메시지 예약을 해제 합니다.|
|[release_ref](#release_ref)|이 `source_block` 개체에 대 한 참조 횟수를 해제 합니다.|
|[reserve](#reserve)|이 `source_block` 개체에서 이전에 제공한 메시지를 예약 합니다.|
|[unlink_target](#unlink_target)|이 `source_block` 개체에서 대상 블록을 해제 합니다.|
|[unlink_targets](#unlink_targets)|이 `source_block` 개체에서 모든 대상 블록을 해제 합니다. ( [ISource:: unlink_targets](isource-class.md#unlink_targets)을 재정의 합니다.)|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[accept_message](#accept_message)|파생 클래스에서 재정의 되는 경우 소스에서 제공 된 메시지를 수락 합니다. 메시지 블록은 `_MsgId`의 유효성을 검사 하 고 메시지를 반환 하려면이 메서드를 재정의 해야 합니다.|
|[async_send](#async_send)|비동기 방식으로 메시지를 큐에 대기 시키고 아직 수행 되지 않은 경우 전파 작업을 시작 합니다.|
|[consume_message](#consume_message)|파생 클래스에서 재정의 되는 경우 이전에 예약 된 메시지를 사용 합니다.|
|[enable_batched_processing](#enable_batched_processing)|이 블록에 대한 일괄 처리를 할 수 있도록 합니다.|
|[initialize_source](#initialize_source)|이 `source_block`내의 `message_propagator`를 초기화 합니다.|
|[link_target_notification](#link_target_notification)|새 대상이이 `source_block` 개체에 연결 되었음을 알리는 콜백입니다.|
|[process_input_messages](#process_input_messages)|입력된 메시지를 처리합니다. source_block에서 파생되는 전파자 블록에만 유용합니다.|
|[propagate_output_messages](#propagate_output_messages)|메시지를 대상으로 전파합니다.|
|[propagate_to_any_targets](#propagate_to_any_targets)|파생 클래스에서 재정의 되는 경우 지정 된 메시지를 연결 된 대상 중 하나 또는 모두에 전파 합니다. 메시지 블록에 대 한 주요 전파 루틴입니다.|
|[release_message](#release_message)|파생 클래스에서 재정의 되는 경우 이전 메시지 예약을 해제 합니다.|
|[remove_targets](#remove_targets)|이 소스 블록의 모든 대상 링크를 제거 합니다. 이를 소멸자에서 호출 해야 합니다.|
|[reserve_message](#reserve_message)|파생 클래스에서 재정의 되는 경우이 `source_block` 개체에서 이전에 제공 된 메시지를 예약 합니다.|
|[resume_propagation](#resume_propagation)|파생 클래스에서 재정의 된 경우 예약이 해제 된 후 전파를 다시 시작 합니다.|
|[sync_send](#sync_send)|아직 수행 하지 않은 경우 메시지를 동기적으로 큐에 대기 시키고 전파 작업을 시작 합니다.|
|[unlink_target_notification](#unlink_target_notification)|이 `source_block` 개체에서 대상이 연결 해제 되었음을 알리는 콜백입니다.|
|[wait_for_outstanding_async_sends](#wait_for_outstanding_async_sends)|모든 비동기 전파 완료 될 때까지 기다립니다. 이 전파자 특정 spin wait는 메시지 블록의 소멸자에 사용 되어 모든 비동기 전파가 블록을 제거 하기 전에 완료할 시간이 있는지 확인 합니다.|

## <a name="remarks"></a>설명

메시지 블록은이 클래스에서 제공 하는 링크 관리 및 동기화를 활용 하기 위해이 블록에서 파생 되어야 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[ISource](isource-class.md)

`source_block`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

## <a name="accept"></a>수락할

이 `source_block` 개체가 제공 하는 메시지를 수락 하 여 호출자에 게 소유권을 전송 합니다.

```cpp
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
제공 된 `message` 개체의 `runtime_object_identity`입니다.

*_PTarget*<br/>
`accept` 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

호출자에 게 소유권이 있는 `message` 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

매개 변수 `_PTarget` `NULL`경우 메서드는 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외를 throw 합니다.

`accept` 메서드는이 `ISource` 블록에서 메시지를 제공 하는 동안 대상에 의해 호출 됩니다. 이 소스가 메시지의 복사본을 만들도록 결정 한 경우 반환 되는 메시지 포인터는 `ITarget` 블록의 `propagate` 메서드로 전달 된 것과 다를 수 있습니다.

## <a name="accept_message"></a>accept_message

파생 클래스에서 재정의 되는 경우 소스에서 제공 된 메시지를 수락 합니다. 메시지 블록은 `_MsgId`의 유효성을 검사 하 고 메시지를 반환 하려면이 메서드를 재정의 해야 합니다.

```cpp
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
`message` 개체의 런타임 개체 id입니다.

### <a name="return-value"></a>Return Value

호출자에 게 소유권이 있는 메시지에 대 한 포인터입니다.

### <a name="remarks"></a>설명

소유권을 이전 하려면 원래 메시지 포인터가 반환 되어야 합니다. 소유권을 유지 하려면 메시지 페이로드의 복사본을 만들고 반환 해야 합니다.

## <a name="acquire_ref"></a>acquire_ref

삭제를 방지 하기 위해이 `source_block` 개체에 대 한 참조 횟수를 가져옵니다.

```cpp
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```

### <a name="remarks"></a>설명

이 메서드는 `link_target` 메서드를 실행 하는 동안이 소스에 연결 되는 `ITarget` 개체에 의해 호출 됩니다.

## <a name="async_send"></a>async_send

비동기 방식으로 메시지를 큐에 대기 시키고 아직 수행 되지 않은 경우 전파 작업을 시작 합니다.

```cpp
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>매개 변수

*_Msg*<br/>
비동기적으로 보낼 `message` 개체에 대 한 포인터입니다.

## <a name="consume"></a>활용

이 `source_block` 개체에서 이전에 제공 하 고 대상에 의해 성공적으로 예약 되어 호출자에 게 소유권을 전송 하는 메시지를 사용 합니다.

```cpp
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
예약 된 `message` 개체의 `runtime_object_identity`입니다.

*_PTarget*<br/>
`consume` 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

호출자에 게 소유권이 있는 `message` 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

매개 변수 `_PTarget` `NULL`경우 메서드는 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외를 throw 합니다.

매개 변수가 `_PTarget` `reserve`를 호출한 대상을 나타내지 않는 경우 메서드는 [bad_target](bad-target-class.md) 예외를 throw 합니다.

`consume` 메서드는 `accept`와 비슷하지만 항상 **true**를 반환 하는 `reserve`를 호출 해야 합니다.

## <a name="consume_message"></a>consume_message

파생 클래스에서 재정의 되는 경우 이전에 예약 된 메시지를 사용 합니다.

```cpp
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
사용 중인 `message` 개체의 `runtime_object_identity`입니다.

### <a name="return-value"></a>Return Value

호출자에 게 소유권이 있는 메시지에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`accept`와 비슷하지만 항상 `reserve`에 대 한 호출 뒤에 나옵니다.

## <a name="enable_batched_processing"></a>enable_batched_processing

이 블록에 대한 일괄 처리를 할 수 있도록 합니다.

```cpp
void enable_batched_processing();
```

## <a name="initialize_source"></a>initialize_source

이 `source_block`내의 `message_propagator`를 초기화 합니다.

```cpp
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>매개 변수

*_PScheduler*<br/>
작업을 예약 하는 데 사용할 스케줄러입니다.

*_PScheduleGroup*<br/>
작업을 예약 하는 데 사용할 일정 그룹입니다.

## <a name="link_target"></a>link_target

대상 블록을이 `source_block` 개체에 연결 합니다.

```cpp
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 `source_block` 개체에 연결할 `ITarget` 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

매개 변수 `_PTarget` `NULL`경우 메서드는 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외를 throw 합니다.

## <a name="link_target_notification"></a>link_target_notification

새 대상이이 `source_block` 개체에 연결 되었음을 알리는 콜백입니다.

```cpp
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```

## <a name="process_input_messages"></a>process_input_messages

입력된 메시지를 처리합니다. source_block에서 파생되는 전파자 블록에만 유용합니다.

```cpp
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
처리할 메시지에 대 한 포인터입니다.

## <a name="propagate_output_messages"></a>propagate_output_messages

메시지를 대상으로 전파합니다.

```cpp
virtual void propagate_output_messages();
```

## <a name="propagate_to_any_targets"></a>propagate_to_any_targets

파생 클래스에서 재정의 되는 경우 지정 된 메시지를 연결 된 대상 중 하나 또는 모두에 전파 합니다. 메시지 블록에 대 한 주요 전파 루틴입니다.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
전파할 메시지에 대 한 포인터입니다.

## <a name="release"></a>릴리스

이전의 성공적인 메시지 예약을 해제 합니다.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
예약 된 `message` 개체의 `runtime_object_identity`입니다.

*_PTarget*<br/>
`release` 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

매개 변수 `_PTarget` `NULL`경우 메서드는 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외를 throw 합니다.

매개 변수가 `_PTarget` `reserve`를 호출한 대상을 나타내지 않는 경우 메서드는 [bad_target](bad-target-class.md) 예외를 throw 합니다.

## <a name="release_message"></a>release_message

파생 클래스에서 재정의 되는 경우 이전 메시지 예약을 해제 합니다.

```cpp
virtual void release_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
해제 되는 `message` 개체의 `runtime_object_identity`입니다.

## <a name="release_ref"></a>release_ref

이 `source_block` 개체에 대 한 참조 횟수를 해제 합니다.

```cpp
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는이 소스에서 연결이 해제 되는 `ITarget` 개체에 의해 호출 됩니다. 소스 블록은 대상 블록에 예약 된 모든 리소스를 해제할 수 있습니다.

## <a name="remove_targets"></a>remove_targets

이 소스 블록의 모든 대상 링크를 제거 합니다. 이를 소멸자에서 호출 해야 합니다.

```cpp
void remove_targets();
```

## <a name="reserve"></a>두기

이 `source_block` 개체에서 이전에 제공한 메시지를 예약 합니다.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
제공 된 `message` 개체의 `runtime_object_identity`입니다.

*_PTarget*<br/>
`reserve` 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

메시지가 성공적으로 예약 되었으면 **true** 이 고, 그렇지 않으면 **false** 입니다. 예약은 메시지를 이미 다른 대상이 예약했거나 수락한 경우, 소스에서 예약을 거부한 경우 등과 같은 다양한 이유로 실패할 수 있습니다.

### <a name="remarks"></a>설명

매개 변수 `_PTarget` `NULL`경우 메서드는 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외를 throw 합니다.

`reserve`호출한 후 성공 하면 `consume` 또는 `release`를 호출 하 여 메시지를 각각 소유 하거나 제공 해야 합니다.

## <a name="reserve_message"></a>reserve_message

파생 클래스에서 재정의 되는 경우이 `source_block` 개체에서 이전에 제공 된 메시지를 예약 합니다.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
예약 되는 `message` 개체의 `runtime_object_identity`입니다.

### <a name="return-value"></a>Return Value

메시지가 성공적으로 예약 되었으면 **true** 이 고, 그렇지 않으면 **false** 입니다.

### <a name="remarks"></a>설명

`reserve`가 호출 되 면 **true**를 반환 하는 경우 `consume` 또는 `release`를 호출 하 여 메시지 소유권을 가져오거나 해제 해야 합니다.

## <a name="resume_propagation"></a>resume_propagation

파생 클래스에서 재정의 된 경우 예약이 해제 된 후 전파를 다시 시작 합니다.

```cpp
virtual void resume_propagation() = 0;
```

## <a name="ctor"></a>source_block

`source_block` 개체를 생성합니다.

```cpp
source_block();
```

## <a name="dtor"></a>~ source_block

`source_block` 개체를 소멸 시킵니다.

```cpp
virtual ~source_block();
```

## <a name="sync_send"></a>sync_send

아직 수행 하지 않은 경우 메시지를 동기적으로 큐에 대기 시키고 전파 작업을 시작 합니다.

```cpp
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>매개 변수

*_Msg*<br/>
동기적으로 보낼 `message` 개체에 대 한 포인터입니다.

## <a name="unlink_target"></a>unlink_target

이 `source_block` 개체에서 대상 블록을 해제 합니다.

```cpp
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 `source_block` 개체에서 연결을 해제할 `ITarget` 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

매개 변수 `_PTarget` `NULL`경우 메서드는 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외를 throw 합니다.

## <a name="unlink_target_notification"></a>unlink_target_notification

이 `source_block` 개체에서 대상이 연결 해제 되었음을 알리는 콜백입니다.

```cpp
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
연결이 해제 된 `ITarget` 블록입니다.

## <a name="unlink_targets"></a>unlink_targets

이 `source_block` 개체에서 모든 대상 블록을 해제 합니다.

```cpp
virtual void unlink_targets();
```

## <a name="wait_for_outstanding_async_sends"></a>wait_for_outstanding_async_sends

모든 비동기 전파 완료 될 때까지 기다립니다. 이 전파자 특정 spin wait는 메시지 블록의 소멸자에 사용 되어 모든 비동기 전파가 블록을 제거 하기 전에 완료할 시간이 있는지 확인 합니다.

```cpp
void wait_for_outstanding_async_sends();
```

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[ISource 클래스](isource-class.md)
