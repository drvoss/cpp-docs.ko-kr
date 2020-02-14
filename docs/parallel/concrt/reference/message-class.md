---
title: message 클래스
ms.date: 11/04/2016
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
ms.openlocfilehash: 700d052b6f22c970387a3ab45d299538a5b74e1b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139536"
---
# <a name="message-class"></a>message 클래스

메시징 블록 간에 전달되는 데이터 페이로드를 포함하는 기본 메시지 봉투입니다.

## <a name="syntax"></a>구문

```cpp
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
메시지 내 페이로드의 데이터 형식입니다.

## <a name="members"></a>구성원

### <a name="public-typedefs"></a>공용 형식 정의

|속성|Description|
|----------|-----------------|
|`type`|`T`에 대 한 형식 별칭입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[message](#ctor)|오버로드되었습니다. `message` 개체를 생성합니다.|
|[~ 메시지 소멸자](#dtor)|`message` 개체를 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[add_ref](#add_ref)|`message` 개체에 대 한 참조 횟수에를 추가 합니다. 메시지 수명을 확인 하기 위해 참조 계산이 필요한 메시지 블록에 사용 됩니다.|
|[msg_id](#msg_id)|`message` 개체의 ID를 반환 합니다.|
|[remove_ref](#remove_ref)|`message` 개체에 대 한 참조 횟수에서 뺍니다. 메시지 수명을 확인 하기 위해 참조 계산이 필요한 메시지 블록에 사용 됩니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[payload](#payload)|`message` 개체의 페이로드입니다.|

## <a name="remarks"></a>설명

자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)을 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

`message`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

## <a name="add_ref"></a>add_ref

`message` 개체에 대 한 참조 횟수에를 추가 합니다. 메시지 수명을 확인 하기 위해 참조 계산이 필요한 메시지 블록에 사용 됩니다.

```cpp
long add_ref();
```

### <a name="return-value"></a>Return Value

참조 횟수의 새 값입니다.

## <a name="ctor"></a>메시지

`message` 개체를 생성합니다.

```cpp
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```

### <a name="parameters"></a>매개 변수

*_P*<br/>
이 메시지의 페이로드입니다.

*_Id*<br/>
이 메시지의 고유 ID입니다.

*_Msg*<br/>
`message` 개체에 대 한 참조 또는 포인터입니다.

### <a name="remarks"></a>설명

`message` 개체에 대 한 포인터를 인수로 사용 하는 생성자는 매개 변수 `_Msg` `NULL`경우 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외를 throw 합니다.

## <a name="dtor"></a>~ 메시지

`message` 개체를 소멸 시킵니다.

```cpp
virtual ~message();
```

## <a name="msg_id"></a>msg_id

`message` 개체의 ID를 반환 합니다.

```cpp
runtime_object_identity msg_id() const;
```

### <a name="return-value"></a>Return Value

`runtime_object_identity` 개체의 `message`입니다.

## <a name="payload"></a>페이로드와

`message` 개체의 페이로드입니다.

```cpp
T const payload;
```

## <a name="remove_ref"></a>remove_ref

`message` 개체에 대 한 참조 횟수에서 뺍니다. 메시지 수명을 확인 하기 위해 참조 계산이 필요한 메시지 블록에 사용 됩니다.

```cpp
long remove_ref();
```

### <a name="return-value"></a>Return Value

참조 횟수의 새 값입니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)
