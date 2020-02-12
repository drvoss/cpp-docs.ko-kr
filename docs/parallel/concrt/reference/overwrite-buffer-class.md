---
title: overwrite_buffer 클래스
ms.date: 11/04/2016
f1_keywords:
- overwrite_buffer
- AGENTS/concurrency::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::has_value
- AGENTS/concurrency::overwrite_buffer::value
- AGENTS/concurrency::overwrite_buffer::accept_message
- AGENTS/concurrency::overwrite_buffer::consume_message
- AGENTS/concurrency::overwrite_buffer::link_target_notification
- AGENTS/concurrency::overwrite_buffer::propagate_message
- AGENTS/concurrency::overwrite_buffer::propagate_to_any_targets
- AGENTS/concurrency::overwrite_buffer::release_message
- AGENTS/concurrency::overwrite_buffer::reserve_message
- AGENTS/concurrency::overwrite_buffer::resume_propagation
- AGENTS/concurrency::overwrite_buffer::send_message
- AGENTS/concurrency::overwrite_buffer::supports_anonymous_source
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
ms.openlocfilehash: 5b222170112f43ae9700054f42e1368545612d00
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138795"
---
# <a name="overwrite_buffer-class"></a>overwrite_buffer 클래스

`overwrite_buffer` 메시징 블록은 한 번에 하나의 메시지를 저장할 수 있는, 순서가 지정된 다중 대상 다중 소스 `propagator_block`입니다. 새 메시지가 이전에 보유한 메시지를 덮어씁니다.

## <a name="syntax"></a>구문

```cpp
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
버퍼에 의해 저장 및 전파 되는 메시지의 페이로드 유형입니다.

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[overwrite_buffer](#ctor)|오버로드되었습니다. `overwrite_buffer` 메시징 블록을 생성 합니다.|
|[~ overwrite_buffer 소멸자](#dtor)|`overwrite_buffer` 메시징 블록을 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[has_value](#has_value)|이 `overwrite_buffer` 메시징 블록에 아직 값이 있는지 여부를 확인 합니다.|
|[value](#value)|`overwrite_buffer` 메시징 블록에 저장 되는 메시지의 현재 페이로드에 대 한 참조를 가져옵니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[accept_message](#accept_message)|메시지의 복사본을 호출자에 게 반환 하는이 `overwrite_buffer` 메시징 블록이 제공한 메시지를 수락 합니다.|
|[consume_message](#consume_message)|이전에 `overwrite_buffer` 메시징 블록이 제공한 메시지를 사용 하 여 대상에서 예약 하 고 메시지의 복사본을 호출자에 게 반환 합니다.|
|[link_target_notification](#link_target_notification)|새 대상이이 `overwrite_buffer` 메시징 블록에 연결 되었음을 알리는 콜백입니다.|
|[propagate_message](#propagate_message)|`ISource` 블록에서이 `overwrite_buffer` 메시징 블록으로 메시지를 비동기적으로 전달 합니다. 소스 블록에서 호출 되는 경우 `propagate` 메서드에서 호출 됩니다.|
|[propagate_to_any_targets](#propagate_to_any_targets)|는이 `overwrite_buffer` messaging 블록에 `message _PMessage`을 배치 하 고 연결 된 모든 대상에 제공 합니다.|
|[release_message](#release_message)|이전 메시지 예약을 해제 합니다. [Source_block:: release_message](source-block-class.md#release_message)를 재정의 합니다.|
|[reserve_message](#reserve_message)|이 `overwrite_buffer` 메시징 블록에서 이전에 제공 된 메시지를 예약 합니다. [Source_block:: reserve_message](source-block-class.md#reserve_message)를 재정의 합니다.|
|[resume_propagation](#resume_propagation)|예약이 해제 된 후 전파를 다시 시작 합니다. [Source_block:: resume_propagation](source-block-class.md#resume_propagation)를 재정의 합니다.|
|[send_message](#send_message)|`ISource` 블록에서이 `overwrite_buffer` 메시징 블록으로 메시지를 동기적으로 전달 합니다. 소스 블록에서 호출 되는 경우 `send` 메서드에서 호출 됩니다.|
|[supports_anonymous_source](#supports_anonymous_source)|`supports_anonymous_source` 메서드를 재정의하여 이 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할 수 있음을 나타냅니다. [ITarget:: supports_anonymous_source](itarget-class.md#supports_anonymous_source)을 재정의 합니다.|

## <a name="remarks"></a>설명

`overwrite_buffer` 메시징 블록은 저장 된 메시지의 복사본을 각 대상에 전파 합니다.

자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)을 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`overwrite_buffer`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

## <a name="accept_message"></a>accept_message

메시지의 복사본을 호출자에 게 반환 하는이 `overwrite_buffer` 메시징 블록이 제공한 메시지를 수락 합니다.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
제공 된 `message` 개체의 `runtime_object_identity`입니다.

### <a name="return-value"></a>Return Value

호출자에 게 소유권이 있는 `message` 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`overwrite_buffer` 메시징 블록은 현재 저장 된 메시지의 소유권을 전송 하는 대신 해당 대상에 메시지의 복사본을 반환 합니다.

## <a name="consume_message"></a>consume_message

이전에 `overwrite_buffer` 메시징 블록이 제공한 메시지를 사용 하 여 대상에서 예약 하 고 메시지의 복사본을 호출자에 게 반환 합니다.

```cpp
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
사용 중인 `message` 개체의 `runtime_object_identity`입니다.

### <a name="return-value"></a>Return Value

호출자에 게 소유권이 있는 `message` 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`accept`와 비슷하지만 항상 `reserve`에 대 한 호출 뒤에 나옵니다.

## <a name="has_value"></a>has_value

이 `overwrite_buffer` 메시징 블록에 아직 값이 있는지 여부를 확인 합니다.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Return Value

블록에서 값을 받으면 **true** 이 고, 그렇지 않으면 **false** 입니다.

## <a name="link_target_notification"></a>link_target_notification

새 대상이이 `overwrite_buffer` 메시징 블록에 연결 되었음을 알리는 콜백입니다.

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
새로 연결 된 대상에 대 한 포인터입니다.

## <a name="dtor"></a>~ overwrite_buffer

`overwrite_buffer` 메시징 블록을 소멸 시킵니다.

```cpp
~overwrite_buffer();
```

## <a name="ctor"></a>overwrite_buffer

`overwrite_buffer` 메시징 블록을 생성 합니다.

```cpp
overwrite_buffer();

overwrite_buffer(
    filter_method const& _Filter);

overwrite_buffer(
    Scheduler& _PScheduler);

overwrite_buffer(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```

### <a name="parameters"></a>매개 변수

*_Filter*<br/>
제공 된 메시지를 수락 해야 하는지 여부를 결정 하는 필터 함수입니다.

*_PScheduler*<br/>
`Scheduler` 메시징 블록의 전파 작업이 예약되는 `overwrite_buffer` 개체입니다.

*_PScheduleGroup*<br/>
`ScheduleGroup` 메시징 블록의 전파 작업이 예약되는 `overwrite_buffer` 개체입니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.

### <a name="remarks"></a>설명

런타임은 `_PScheduler` 또는 `_PScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.

`filter_method` 형식은 제공 된 메시지를 수락 해야 하는지 여부를 확인 하기 위해이 `overwrite_buffer` 메시징 블록에서 호출 하는 시그니처 `bool (T const &)`를 사용 하는 함수입니다.

## <a name="propagate_message"></a>propagate_message

`ISource` 블록에서이 `overwrite_buffer` 메시징 블록으로 메시지를 비동기적으로 전달 합니다. 소스 블록에서 호출 되는 경우 `propagate` 메서드에서 호출 됩니다.

```cpp
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
`message` 개체에 대한 포인터입니다.

*_PSource*<br/>
메시지를 제공 하는 소스 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

대상에서 메시지를 사용 하 여 수행 하기로 결정 한 내용을 나타내는 [message_status](concurrency-namespace-enums.md) 입니다.

## <a name="propagate_to_any_targets"></a>propagate_to_any_targets

는이 `overwrite_buffer` messaging 블록에 `message _PMessage`을 배치 하 고 연결 된 모든 대상에 제공 합니다.

```cpp
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
이 `overwrite_buffer`에서 소유권을 가져온 `message` 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 `overwrite_buffer`의 현재 메시지를 새로 허용 된 메시지 `_PMessage`덮어씁니다.

## <a name="send_message"></a>send_message

`ISource` 블록에서이 `overwrite_buffer` 메시징 블록으로 메시지를 동기적으로 전달 합니다. 소스 블록에서 호출 되는 경우 `send` 메서드에서 호출 됩니다.

```cpp
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
`message` 개체에 대한 포인터입니다.

*_PSource*<br/>
메시지를 제공 하는 소스 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

대상에서 메시지를 사용 하 여 수행 하기로 결정 한 내용을 나타내는 [message_status](concurrency-namespace-enums.md) 입니다.

## <a name="supports_anonymous_source"></a>supports_anonymous_source

`supports_anonymous_source` 메서드를 재정의하여 이 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할 수 있음을 나타냅니다.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Return Value

블록에서 제공 된 메시지를 연기 하지 않으므로 **true** 입니다.

## <a name="release_message"></a>release_message

이전 메시지 예약을 해제 합니다.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
해제 되는 `message` 개체의 `runtime_object_identity`입니다.

## <a name="reserve_message"></a>reserve_message

이 `overwrite_buffer` 메시징 블록에서 이전에 제공 된 메시지를 예약 합니다.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
예약 되는 `message` 개체의 `runtime_object_identity`입니다.

### <a name="return-value"></a>Return Value

메시지가 성공적으로 예약 되었으면 **true** 이 고, 그렇지 않으면 **false** 입니다.

### <a name="remarks"></a>설명

`reserve`가 호출 되 면 **true**를 반환 하는 경우 `consume` 또는 `release`를 호출 하 여 메시지 소유권을 가져오거나 해제 해야 합니다.

## <a name="resume_propagation"></a>resume_propagation

예약이 해제 된 후 전파를 다시 시작 합니다.

```cpp
virtual void resume_propagation();
```

## <a name="value"></a>기본값

`overwrite_buffer` 메시징 블록에 저장 되는 메시지의 현재 페이로드에 대 한 참조를 가져옵니다.

```cpp
T value();
```

### <a name="return-value"></a>Return Value

현재 저장 된 메시지의 페이로드입니다.

### <a name="remarks"></a>설명

`overwrite_buffer`에 저장 된 값은이 메서드가 반환 된 후 즉시 변경 될 수 있습니다. 이 메서드는 `overwrite_buffer`에 현재 저장 된 메시지가 없는 경우 메시지가 도착할 때까지 기다립니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[unbounded_buffer 클래스](unbounded-buffer-class.md)<br/>
[single_assignment 클래스](single-assignment-class.md)
