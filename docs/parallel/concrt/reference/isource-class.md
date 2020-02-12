---
title: ISource 클래스
ms.date: 11/04/2016
f1_keywords:
- ISource
- AGENTS/concurrency::ISource
- AGENTS/concurrency::ISource::accept
- AGENTS/concurrency::ISource::acquire_ref
- AGENTS/concurrency::ISource::consume
- AGENTS/concurrency::ISource::link_target
- AGENTS/concurrency::ISource::release
- AGENTS/concurrency::ISource::release_ref
- AGENTS/concurrency::ISource::reserve
- AGENTS/concurrency::ISource::unlink_target
- AGENTS/concurrency::ISource::unlink_targets
helpviewer_keywords:
- ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
ms.openlocfilehash: a9ef9990db6376536f2f2a15c053b3b1d4ed12cf
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139312"
---
# <a name="isource-class"></a>ISource 클래스

`ISource` 클래스는 모든 소스 블록에 대한 인터페이스입니다. 소스 블록은 `ITarget` 블록에 메시지를 전파합니다.

## <a name="syntax"></a>구문

```cpp
template<class T>
class ISource;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
소스 블록에 의해 생성 되는 메시지 내 페이로드의 데이터 형식입니다.

## <a name="members"></a>구성원

### <a name="public-typedefs"></a>공용 형식 정의

|속성|Description|
|----------|-----------------|
|`source_type`|`T`에 대 한 형식 별칭입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[~ ISource 소멸자](#dtor)|`ISource` 개체를 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[수락할](#accept)|파생 클래스에서 재정의 되는 경우이 `ISource` 블록으로 제공 된 메시지를 수락 하 여 호출자에 게 소유권을 전송 합니다.|
|[acquire_ref](#acquire_ref)|파생 클래스에서 재정의 되는 경우 삭제를 방지 하기 위해이 `ISource` 블록에서 참조 횟수를 가져옵니다.|
|[consume](#consume)|파생 클래스에서 재정의 되는 경우이 `ISource` 블록에서 이전에 제공 된 메시지를 사용 하 고 대상에서 성공적으로 예약 하 여 호출자에 게 소유권을 전송 합니다.|
|[link_target](#link_target)|파생 클래스에서 재정의 되는 경우 대상 블록을이 `ISource` 블록에 연결 합니다.|
|[release](#release)|파생 클래스에서 재정의 되는 경우 이전의 성공적인 메시지 예약을 해제 합니다.|
|[release_ref](#release_ref)|파생 클래스에서 재정의 되는 경우이 `ISource` 블록에서 참조 횟수를 해제 합니다.|
|[reserve](#reserve)|파생 클래스에서 재정의 되는 경우이 `ISource` 블록에서 이전에 제공 된 메시지를 예약 합니다.|
|[unlink_target](#unlink_target)|파생 클래스에서 재정의 되는 경우이 `ISource` 블록에서 대상 블록의 연결을 끊습니다 (이전에 연결 된 경우).|
|[unlink_targets](#unlink_targets)|파생 클래스에서 재정의 되는 경우이 `ISource` 블록에서 모든 대상 블록을 해제 합니다.|

## <a name="remarks"></a>설명

자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)을 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

`ISource`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

## <a name="accept"></a>수락할

파생 클래스에서 재정의 되는 경우이 `ISource` 블록으로 제공 된 메시지를 수락 하 여 호출자에 게 소유권을 전송 합니다.

```cpp
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
제공 된 `message` 개체의 `runtime_object_identity`입니다.

*_PTarget*<br/>
`accept` 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

호출자에 게 소유권이 있는 메시지에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`accept` 메서드는이 `ISource` 블록에서 메시지를 제공 하는 동안 대상에 의해 호출 됩니다. 이 소스가 메시지의 복사본을 만들도록 결정 한 경우 반환 되는 메시지 포인터는 `ITarget` 블록의 `propagate` 메서드로 전달 된 것과 다를 수 있습니다.

## <a name="acquire_ref"></a>acquire_ref

파생 클래스에서 재정의 되는 경우 삭제를 방지 하기 위해이 `ISource` 블록에서 참조 횟수를 가져옵니다.

```cpp
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 `link_target` 메서드를 실행 하는 동안이 소스에 연결 되는 `ITarget` 개체에 의해 호출 됩니다.

## <a name="consume"></a>활용

파생 클래스에서 재정의 되는 경우이 `ISource` 블록에서 이전에 제공 된 메시지를 사용 하 고 대상에서 성공적으로 예약 하 여 호출자에 게 소유권을 전송 합니다.

```cpp
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
예약 된 `message` 개체의 `runtime_object_identity`입니다.

*_PTarget*<br/>
`consume` 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

호출자에 게 소유권이 있는 `message` 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`consume` 메서드는 `accept`와 비슷하지만 항상 **true**를 반환 하는 `reserve`를 호출 해야 합니다.

## <a name="dtor"></a>~ ISource

`ISource` 개체를 소멸 시킵니다.

```cpp
virtual ~ISource();
```

## <a name="link_target"></a>link_target

파생 클래스에서 재정의 되는 경우 대상 블록을이 `ISource` 블록에 연결 합니다.

```cpp
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 `ISource` 블록에 연결 되는 대상 블록에 대 한 포인터입니다.

## <a name="release"></a>릴리스

파생 클래스에서 재정의 되는 경우 이전의 성공적인 메시지 예약을 해제 합니다.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
예약 된 `message` 개체의 `runtime_object_identity`입니다.

*_PTarget*<br/>
`release` 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

## <a name="release_ref"></a>release_ref

파생 클래스에서 재정의 되는 경우이 `ISource` 블록에서 참조 횟수를 해제 합니다.

```cpp
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는이 소스에서 연결이 해제 되는 `ITarget` 개체에 의해 호출 됩니다. 소스 블록은 대상 블록에 예약 된 모든 리소스를 해제할 수 있습니다.

## <a name="reserve"></a>두기

파생 클래스에서 재정의 되는 경우이 `ISource` 블록에서 이전에 제공 된 메시지를 예약 합니다.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
제공 된 `message` 개체의 `runtime_object_identity`입니다.

*_PTarget*<br/>
`reserve` 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

메시지가 성공적으로 예약 되었으면 **true** 이 고, 그렇지 않으면 **false** 입니다. 예약은 메시지를 이미 다른 대상이 예약했거나 수락한 경우, 소스에서 예약을 거부한 경우 등과 같은 다양한 이유로 실패할 수 있습니다.

### <a name="remarks"></a>설명

`reserve`호출한 후 성공 하면 `consume` 또는 `release`를 호출 하 여 메시지를 각각 소유 하거나 제공 해야 합니다.

## <a name="unlink_target"></a>unlink_target

파생 클래스에서 재정의 되는 경우이 `ISource` 블록에서 대상 블록의 연결을 끊습니다 (이전에 연결 된 경우).

```cpp
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 `ISource` 블록에서 연결이 해제 되는 대상 블록에 대 한 포인터입니다.

## <a name="unlink_targets"></a>unlink_targets

파생 클래스에서 재정의 되는 경우이 `ISource` 블록에서 모든 대상 블록을 해제 합니다.

```cpp
virtual void unlink_targets() = 0;
```

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[ITarget 클래스](itarget-class.md)
