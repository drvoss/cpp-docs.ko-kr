---
title: target_block 클래스
ms.date: 11/04/2016
f1_keywords:
- target_block
- AGENTS/concurrency::target_block
- AGENTS/concurrency::target_block::target_block
- AGENTS/concurrency::target_block::propagate
- AGENTS/concurrency::target_block::send
- AGENTS/concurrency::target_block::async_send
- AGENTS/concurrency::target_block::decline_incoming_messages
- AGENTS/concurrency::target_block::enable_batched_processing
- AGENTS/concurrency::target_block::initialize_target
- AGENTS/concurrency::target_block::link_source
- AGENTS/concurrency::target_block::process_input_messages
- AGENTS/concurrency::target_block::process_message
- AGENTS/concurrency::target_block::propagate_message
- AGENTS/concurrency::target_block::register_filter
- AGENTS/concurrency::target_block::remove_sources
- AGENTS/concurrency::target_block::send_message
- AGENTS/concurrency::target_block::sync_send
- AGENTS/concurrency::target_block::unlink_source
- AGENTS/concurrency::target_block::unlink_sources
- AGENTS/concurrency::target_block::wait_for_async_sends
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
ms.openlocfilehash: 4009133161133a99aeb0ee040f0c82fdbabecaa0
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142649"
---
# <a name="target_block-class"></a>target_block 클래스

`target_block` 클래스는 대상 전용 블록에 대해 기본 링크 관리 기능 및 오류 검사를 제공하는 추상 기본 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

### <a name="parameters"></a>매개 변수

*_SourceLinkRegistry*<br/>
소스 링크를 포함 하는 데 사용할 링크 레지스트리입니다.

*_MessageProcessorType*<br/>
메시지 처리를 위한 프로세서 유형입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|name|설명|
|----------|-----------------|
|`source_iterator`|이 `target_block` 개체의 `source_link_manager`에 대 한 반복기의 형식입니다.|

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[target_block](#ctor)|`target_block` 개체를 생성합니다.|
|[~ target_block 소멸자](#dtor)|`target_block` 개체를 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[배포할](#propagate)|소스 블록에서이 대상 블록으로 메시지를 비동기적으로 전달 합니다.|
|[send](#send)|소스 블록에서이 대상 블록으로 메시지를 동기적으로 전달 합니다.|

### <a name="protected-methods"></a>보호된 메서드

|name|설명|
|----------|-----------------|
|[async_send](#async_send)|처리할 메시지를 비동기적으로 보냅니다.|
|[decline_incoming_messages](#decline_incoming_messages)|새 메시지를 거부 해야 함을 블록에 나타냅니다.|
|[enable_batched_processing](#enable_batched_processing)|이 블록에 대한 일괄 처리를 할 수 있도록 합니다.|
|[initialize_target](#initialize_target)|기본 개체를 초기화 합니다. 특히 `message_processor` 개체를 초기화 해야 합니다.|
|[link_source](#link_source)|지정 된 소스 블록을이 `target_block` 개체에 연결 합니다.|
|[process_input_messages](#process_input_messages)|입력으로 받은 메시지를 처리합니다.|
|[process_message](#process_message)|파생 클래스에 재정의된 경우 이 `target_block` 개체가 수락했던 메시지를 처리합니다.|
|[propagate_message](#propagate_message)|파생 클래스에서 재정의 되는 경우이 메서드는 `ISource` 블록에서이 `target_block` 개체로 비동기적으로 메시지를 전달 합니다. 소스 블록에서 호출 되는 경우 `propagate` 메서드에서 호출 됩니다.|
|[register_filter](#register_filter)|받은 모든 메시지에 대해 호출할 필터 메서드를 등록 합니다.|
|[remove_sources](#remove_sources)|처리 중인 비동기 보내기 작업이 완료 되기를 기다린 후 모든 소스를 해제 합니다.|
|[send_message](#send_message)|파생 클래스에서 재정의 되는 경우이 메서드는 `ISource` 블록에서이 `target_block` 개체로 동기적으로 메시지를 전달 합니다. 소스 블록에서 호출 되는 경우 `send` 메서드에서 호출 됩니다.|
|[sync_send](#sync_send)|처리할 메시지를 동기적으로 보냅니다.|
|[unlink_source](#unlink_source)|이 `target_block` 개체에서 지정 된 소스 블록을 해제 합니다.|
|[unlink_sources](#unlink_sources)|이 `target_block` 개체에서 모든 소스 블록을 해제 합니다. [ITarget:: unlink_sources](itarget-class.md#unlink_sources)을 재정의 합니다.|
|[wait_for_async_sends](#wait_for_async_sends)|모든 비동기 전파 완료 될 때까지 기다립니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

[ITarget](itarget-class.md)

`target_block`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

## <a name="async_send"></a>async_send

처리할 메시지를 비동기적으로 보냅니다.

```cpp
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
보내고 있는 메시지에 대 한 포인터입니다.

## <a name="decline_incoming_messages"></a>decline_incoming_messages

새 메시지를 거부 해야 함을 블록에 나타냅니다.

```cpp
void decline_incoming_messages();
```

### <a name="remarks"></a>설명

이 메서드는 소멸이 진행 되는 동안 새 메시지가 거부 되도록 소멸자에서 호출 됩니다.

## <a name="enable_batched_processing"></a>enable_batched_processing

이 블록에 대한 일괄 처리를 할 수 있도록 합니다.

```cpp
void enable_batched_processing();
```

## <a name="initialize_target"></a>initialize_target

기본 개체를 초기화 합니다. 특히 `message_processor` 개체를 초기화 해야 합니다.

```cpp
void initialize_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>매개 변수

*_PScheduler*<br/>
작업을 예약 하는 데 사용할 스케줄러입니다.

*_PScheduleGroup*<br/>
작업을 예약 하는 데 사용할 일정 그룹입니다.

## <a name="link_source"></a>link_source

지정 된 소스 블록을이 `target_block` 개체에 연결 합니다.

```cpp
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>매개 변수

*_PSource*<br/>
연결할 `ISource` 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 함수는 `target_block` 개체에서 직접 호출 하면 안 됩니다. 블록은 `ISource` 블록에 대 한 `link_target` 메서드를 사용 하 여 연결 해야 하며,이는 해당 대상에서 `link_source` 메서드를 호출 합니다.

## <a name="process_input_messages"></a>process_input_messages

입력으로 받은 메시지를 처리합니다.

```cpp
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
처리할 메시지에 대 한 포인터입니다.

## <a name="process_message"></a>process_message

파생 클래스에 재정의된 경우 이 `target_block` 개체가 수락했던 메시지를 처리합니다.

```cpp
virtual void process_message(message<_Source_type> *);
```

## <a name="propagate"></a>배포할

소스 블록에서이 대상 블록으로 메시지를 비동기적으로 전달 합니다.

```cpp
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
`message` 개체에 대한 포인터입니다.

*_PSource*<br/>
메시지를 제공 하는 소스 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

대상에서 메시지를 사용 하 여 수행 하기로 결정 한 내용을 나타내는 [message_status](concurrency-namespace-enums.md) 입니다.

### <a name="remarks"></a>설명

`_PMessage` 또는 `_PSource` 매개 변수 중 하나가 `NULL`되는 경우 메서드는 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외를 throw 합니다.

## <a name="propagate_message"></a>propagate_message

파생 클래스에서 재정의 되는 경우이 메서드는 `ISource` 블록에서이 `target_block` 개체로 비동기적으로 메시지를 전달 합니다. 소스 블록에서 호출 되는 경우 `propagate` 메서드에서 호출 됩니다.

```cpp
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
`message` 개체에 대한 포인터입니다.

*_PSource*<br/>
메시지를 제공 하는 소스 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

대상에서 메시지를 사용 하 여 수행 하기로 결정 한 내용을 나타내는 [message_status](concurrency-namespace-enums.md) 입니다.

## <a name="register_filter"></a>register_filter

받은 모든 메시지에 대해 호출할 필터 메서드를 등록 합니다.

```cpp
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>매개 변수

*_Filter*<br/>
필터 메서드입니다.

## <a name="remove_sources"></a>remove_sources

처리 중인 비동기 보내기 작업이 완료 되기를 기다린 후 모든 소스를 해제 합니다.

```cpp
void remove_sources();
```

### <a name="remarks"></a>설명

모든 대상 블록은이 루틴을 호출 하 여 해당 소멸자에서 원본을 제거 해야 합니다.

## <a name="send"></a>보내기

소스 블록에서이 대상 블록으로 메시지를 동기적으로 전달 합니다.

```cpp
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
`message` 개체에 대한 포인터입니다.

*_PSource*<br/>
메시지를 제공 하는 소스 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

대상에서 메시지를 사용 하 여 수행 하기로 결정 한 내용을 나타내는 [message_status](concurrency-namespace-enums.md) 입니다.

### <a name="remarks"></a>설명

`_PMessage` 또는 `_PSource` 매개 변수 중 하나가 `NULL`되는 경우 메서드는 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외를 throw 합니다.

메시지 시작 외부에 `send` 메서드를 사용 하 고 네트워크 내의 메시지를 전파 하는 것은 위험 하며 교착 상태가 발생할 수 있습니다.

`send` 반환 될 때 메시지가 이미 수락 되었고 대상 블록으로 전송 되었거나 대상에서 거부 되었습니다.

## <a name="send_message"></a>send_message

파생 클래스에서 재정의 되는 경우이 메서드는 `ISource` 블록에서이 `target_block` 개체로 동기적으로 메시지를 전달 합니다. 소스 블록에서 호출 되는 경우 `send` 메서드에서 호출 됩니다.

```cpp
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>Return Value

대상에서 메시지를 사용 하 여 수행 하기로 결정 한 내용을 나타내는 [message_status](concurrency-namespace-enums.md) 입니다.

### <a name="remarks"></a>설명

기본적으로이 블록은 파생 클래스에 의해 재정의 되지 않는 한 `declined` 반환 합니다.

## <a name="sync_send"></a>sync_send

처리할 메시지를 동기적으로 보냅니다.

```cpp
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
보내고 있는 메시지에 대 한 포인터입니다.

## <a name="ctor"></a>target_block

`target_block` 개체를 생성합니다.

```cpp
target_block();
```

## <a name="dtor"></a>~ target_block

`target_block` 개체를 소멸 시킵니다.

```cpp
virtual ~target_block();
```

## <a name="unlink_source"></a>unlink_source

이 `target_block` 개체에서 지정 된 소스 블록을 해제 합니다.

```cpp
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>매개 변수

*_PSource*<br/>
연결을 끊을 `ISource` 블록에 대 한 포인터입니다.

## <a name="unlink_sources"></a>unlink_sources

이 `target_block` 개체에서 모든 소스 블록을 해제 합니다.

```cpp
virtual void unlink_sources();
```

## <a name="wait_for_async_sends"></a>wait_for_async_sends

모든 비동기 전파 완료 될 때까지 기다립니다.

```cpp
void wait_for_async_sends();
```

### <a name="remarks"></a>설명

메시지 블록 소멸자는이 메서드를 사용 하 여 블록을 제거 하기 전에 모든 비동기 작업을 완료 하는 데 시간이 소요 되었는지 확인 합니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[ITarget 클래스](itarget-class.md)
