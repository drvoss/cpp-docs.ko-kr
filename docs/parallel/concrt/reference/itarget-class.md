---
title: ITarget 클래스
ms.date: 11/04/2016
f1_keywords:
- ITarget
- AGENTS/concurrency::ITarget
- AGENTS/concurrency::ITarget::propagate
- AGENTS/concurrency::ITarget::send
- AGENTS/concurrency::ITarget::supports_anonymous_source
- AGENTS/concurrency::ITarget::link_source
- AGENTS/concurrency::ITarget::unlink_source
- AGENTS/concurrency::ITarget::unlink_sources
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
ms.openlocfilehash: dc9eacad744536e640417a4ebf51b975bd05bcc7
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142029"
---
# <a name="itarget-class"></a>ITarget 클래스

`ITarget` 클래스는 모든 대상 블록에 대한 인터페이스입니다. 대상 블록은 `ISource` 블록에서 제공한 메시지를 사용합니다.

## <a name="syntax"></a>구문

```cpp
template<class T>
class ITarget;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
대상 블록에서 허용 하는 메시지 내 페이로드의 데이터 형식입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|name|설명|
|----------|-----------------|
|`filter_method`|제공 된 메시지를 수락 해야 하는지 여부를 확인 하기 위해 `bool` 값을 반환 하는 블록에서 사용 하는 메서드의 서명입니다.|
|`type`|`T`에 대 한 형식 별칭입니다.|

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[~ ITarget 소멸자](#dtor)|`ITarget` 개체를 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[배포할](#propagate)|파생 클래스에서 재정의 되는 경우 소스 블록에서이 대상 블록으로 메시지를 비동기적으로 전달 합니다.|
|[send](#send)|파생 클래스에서 재정의 되는 경우 메시지를 대상 블록에 동기적으로 전달 합니다.|
|[supports_anonymous_source](#supports_anonymous_source)|파생 클래스에서 재정의된 경우, 연결되지 않은 소스에서 제공하는 메시지를 메시지 블록이 수락할지 여부에 따라 true 또는 false를 반환합니다. 재정의 된 메서드가 **true**를 반환 하는 경우 나중에 연기 된 메시지를 사용 하려면 소스 링크 레지스트리에서 소스를 식별 해야 하므로 대상이 제공 된 메시지를 연기할 수 없습니다.|

### <a name="protected-methods"></a>보호된 메서드

|name|설명|
|----------|-----------------|
|[link_source](#link_source)|파생 클래스에서 재정의 되는 경우 지정 된 소스 블록을이 `ITarget` 블록에 연결 합니다.|
|[unlink_source](#unlink_source)|파생 클래스에서 재정의 되는 경우이 `ITarget` 블록에서 지정 된 소스 블록을 해제 합니다.|
|[unlink_sources](#unlink_sources)|파생 클래스에서 재정의 되는 경우이 `ITarget` 블록에서 모든 소스 블록을 해제 합니다.|

## <a name="remarks"></a>설명

자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)을 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

`ITarget`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

## <a name="dtor"></a>~ ITarget

`ITarget` 개체를 소멸 시킵니다.

```cpp
virtual ~ITarget();
```

## <a name="link_source"></a>link_source

파생 클래스에서 재정의 되는 경우 지정 된 소스 블록을이 `ITarget` 블록에 연결 합니다.

```cpp
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>매개 변수

*_PSource*<br/>
이 `ITarget` 블록에 연결 된 `ISource` 블록입니다.

### <a name="remarks"></a>설명

이 함수는 `ITarget` 블록에서 직접 호출 하면 안 됩니다. 블록은 `ISource` 블록에 대 한 `link_target` 메서드를 사용 하 여 연결 해야 하며,이는 해당 대상에서 `link_source` 메서드를 호출 합니다.

## <a name="propagate"></a>배포할

파생 클래스에서 재정의 되는 경우 소스 블록에서이 대상 블록으로 메시지를 비동기적으로 전달 합니다.

```cpp
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
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

## <a name="send"></a>보내기

파생 클래스에서 재정의 되는 경우 메시지를 대상 블록에 동기적으로 전달 합니다.

```cpp
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
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

## <a name="supports_anonymous_source"></a>supports_anonymous_source

파생 클래스에서 재정의된 경우, 연결되지 않은 소스에서 제공하는 메시지를 메시지 블록이 수락할지 여부에 따라 true 또는 false를 반환합니다. 재정의 된 메서드가 **true**를 반환 하는 경우 나중에 연기 된 메시지를 사용 하면 소스를 해당 소스 link 레지스트리에서 확인 하도록 대상이 제공 된 메시지를 연기할 수 없습니다.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Return Value

블록이 연결 되지 않은 소스에서 메시지를 수락할 수 있으면 **true** 이 고, 그렇지 않으면 **false** 입니다.

## <a name="unlink_source"></a>unlink_source

파생 클래스에서 재정의 되는 경우이 `ITarget` 블록에서 지정 된 소스 블록을 해제 합니다.

```cpp
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>매개 변수

*_PSource*<br/>
이 `ITarget` 블록에서 연결이 해제 되는 `ISource` 블록입니다.

### <a name="remarks"></a>설명

이 함수는 `ITarget` 블록에서 직접 호출 하면 안 됩니다. `unlink_target` 또는 `unlink_targets` 메서드를 사용 하 여 블록의 연결을 해제 해야 합니다. `ISource` 블록에서는 해당 대상에 대해 `unlink_source` 메서드를 호출 합니다.

## <a name="unlink_sources"></a>unlink_sources

파생 클래스에서 재정의 되는 경우이 `ITarget` 블록에서 모든 소스 블록을 해제 합니다.

```cpp
virtual void unlink_sources() = 0;
```

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[ISource 클래스](isource-class.md)
