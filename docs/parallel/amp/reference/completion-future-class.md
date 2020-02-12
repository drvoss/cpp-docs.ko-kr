---
title: completion_future 클래스
ms.date: 11/04/2016
f1_keywords:
- completion_future
- AMPRT/completion_future
- AMPRT/Concurrency::completion_future::completion_future
- AMPRT/Concurrency::completion_future::get
- AMPRT/Concurrency::completion_future::then
- AMPRT/Concurrency::completion_future::to_task
- AMPRT/Concurrency::completion_future::valid
- AMPRT/Concurrency::completion_future::wait
- AMPRT/Concurrency::completion_future::wait_for
- AMPRT/Concurrency::completion_future::wait_until
ms.assetid: 1303c62e-546d-4b02-a578-251ed3fc0b6b
ms.openlocfilehash: 69aacad02df5290f161e9d8d311be347668be9f9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127022"
---
# <a name="completion_future-class"></a>completion_future 클래스

C++ AMP 비동기 작업에 해당 하는 미래를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class completion_future;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[completion_future 생성자](#ctor)|`completion_future` 클래스의 새 인스턴스를 초기화합니다.|
|[~ completion_future 소멸자](#dtor)|`completion_future` 개체를 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[get](#get)|연결 된 비동기 작업이 완료 될 때까지 대기 합니다.|
|[다음](#then)|연결 된 비동기 작업의 실행이 완료 될 때 실행할 `completion_future` 개체에 콜백 함수 개체를 연결 합니다.|
|[to_task](#to_task)|연결 된 비동기 작업에 해당 하는 `task` 개체를 반환 합니다.|
|[유효](#valid)|개체가 비동기 작업에 연결 되어 있는지 여부를 나타내는 부울 값을 가져옵니다.|
|[대기한](#wait)|연결 된 비동기 작업이 완료 될 때까지 차단 합니다.|
|[wait_for](#wait_for)|연결 된 비동기 작업이 완료 되거나 `_Rel_time`에서 지정한 시간이 경과할 때까지 차단 합니다.|
|[wait_until](#wait_until)|연결 된 비동기 작업이 완료 될 때까지 또는 현재 시간이 `_Abs_time`지정 된 값을 초과할 때까지 차단 합니다.|

### <a name="public-operators"></a>Public 연산자

|name|설명|
|----------|-----------------|
|[operator std:: shared_future\<void >](#operator_shared_future)|`completion_future` 개체를 `std::shared_future` 개체로 암시적으로 변환 합니다.|
|[operator=](#operator_eq)|지정 된 `completion_future` 개체의 내용을이 개체에 복사 합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`completion_future`

## <a name="requirements"></a>요구 사항

**헤더:** amprt. h

**네임스페이스:** 동시성

## <a name="ctor"></a>completion_future

`completion_future` 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
completion_future();

completion_future(
    const completion_future& _Other );

completion_future(
    completion_future&& _Other );
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
복사하거나 이동시킬 `completion_future` 개체입니다.

### <a name="overloads-list"></a>오버 로드 목록

|name|설명|
|----------|-----------------|
|`completion_future();`|`completion_future` 클래스의 새 인스턴스를 초기화합니다.|
|`completion_future(const completion_future& _Other);`|생성자를 복사하여 `completion_future` 클래스의 새 인스턴스를 초기화합니다.|
|`completion_future(completion_future&& _Other);`|생성자를 이동시켜 `completion_future` 클래스의 새 인스턴스를 초기화합니다.|

## <a name="get"></a> get

연결 된 비동기 작업이 완료 될 때까지 대기 합니다. 비동기 작업 중 하나가 발생한 경우 저장된 예외를 throw합니다.

### <a name="syntax"></a>구문

```cpp
void get() const;
```

## <a name="operator_shared_future"></a>operator std:: shared_future\<void >

`completion_future` 개체를 `std::shared_future` 개체로 암시적으로 변환 합니다.

### <a name="syntax"></a>구문

```cpp
operator std::shared_future<void>() const;
```

### <a name="return-value"></a>Return Value

`std::shared_future` 개체입니다.

## <a name="operator_eq"></a>연산자 =

지정 된 `completion_future` 개체의 내용을이 개체에 복사 합니다.

### <a name="syntax"></a>구문

```cpp
completion_future&  operator= (const completion_future& _Other );
completion_future&  operator= (completion_future&& _Other );
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
복사할 개체입니다.

### <a name="return-value"></a>Return Value

이 `completion_future` 개체에 대 한 참조입니다.

## <a name="overloads-list"></a>오버 로드 목록

|name|설명|
|----------|-----------------|
|`completion_future& operator=(const completion_future& _Other);`|전체 복사본을 사용하여 지정된 `completion_future` 개체의 내용을 여기로 복사합니다.|
|`completion_future& operator=(completion_future&& _Other);`|이동 할당을 사용하여 지정된 `completion_future` 개체의 내용을 여기로 복사합니다.|

## <a name="then"></a>다음

연결 된 비동기 작업의 실행이 완료 될 때 실행할 `completion_future` 개체에 콜백 함수 개체를 연결 합니다.

### <a name="syntax"></a>구문

```cpp
template <typename _Functor>
void then(const _Functor & _Func ) const;
```

### <a name="parameters"></a>매개 변수

*_Functor*<br/>
콜백 구조 함수입니다.

*_Func*<br/>
콜백 함수 개체입니다.

## <a name="to_task"></a>to_task

연결 된 비동기 작업에 해당 하는 `task` 개체를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
concurrency::task<void> to_task() const;
```

### <a name="return-value"></a>Return Value

연결된 비동기 작업에 해당하는 `task` 개체입니다.

## <a name="valid"></a>유효

개체가 비동기 작업에 연결되어 있는지 여부를 나타내는 부울 값을 가져옵니다.

### <a name="syntax"></a>구문

```cpp
bool valid() const;
```

### <a name="return-value"></a>Return Value

개체가 비동기 작업과 연결 되어 있으면 **true** 이 고, 그렇지 않으면입니다. 그렇지 않으면 **false**입니다.

## <a name="wait"></a>대기한

연결 된 비동기 작업이 완료 될 때까지 차단 합니다.

### <a name="syntax"></a>구문

```cpp
void wait() const;
```

## <a name="wait_for"></a>wait_for

연결 된 비동기 작업이 완료 되거나 `_Rel_time`에 지정 된 시간이 경과할 때까지 차단 합니다.

### <a name="syntax"></a>구문

```cpp
template <
    class _Rep,
    class _Period
>
std::future_status::future_status wait_for(
    const std::chrono::duration< _Rep, _Period>& _Rel_time ) const;
```

### <a name="parameters"></a>매개 변수

*_Rep*<br/>
틱 수를 나타내는 산술 형식입니다.

*_Period*<br/>
틱 당 경과 된 시간 (초)을 나타내는 std:: ratio입니다.

*_Rel_time*<br/>
작업이 완료될 때까지 대기하는 최대 시간입니다.

### <a name="return-value"></a>Return Value

HRESULT = NO_ERROR를

- 연결 된 비동기 작업이 실행 되 고 있지 않으면 `std::future_status::deferred` 합니다.

- 연결 된 비동기 작업이 완료 되 면 `std::future_status::ready` 합니다.

- 지정 된 기간이 경과 된 경우 `std::future_status::timeout` 합니다.

## <a name="wait_until"></a>wait_until

연결 된 비동기 작업이 완료 될 때까지 또는 현재 시간이 `_Abs_time`지정 된 값을 초과할 때까지 차단 합니다.

### <a name="syntax"></a>구문

```cpp
template <
    class _Clock,
    class _Duration
>
std::future_status::future_status wait_until(
    const std::chrono::time_point< _Clock, _Duration>& _Abs_time ) const;
```

### <a name="parameters"></a>매개 변수

*_Clock*<br/>
이 시점에서 측정 되는 클록입니다.

*_Duration*<br/>
`_Clock`epoch 이후의 시간 간격이 며, 그 후에는 함수가 시간 초과 됩니다.

*_Abs_time*<br/>
함수의 시간 제한이 초과 되는 시점입니다.

### <a name="return-value"></a>Return Value

HRESULT = NO_ERROR를

1. 연결 된 비동기 작업이 실행 되 고 있지 않으면 `std::future_status::deferred` 합니다.

1. 연결 된 비동기 작업이 완료 되 면 `std::future_status::ready` 합니다.

1. 지정 된 기간이 경과 된 경우를 `std::future_status::timeout` 합니다.

## <a name="dtor"></a>~ completion_future

`completion_future` 개체를 소멸 시킵니다.

### <a name="syntax"></a>구문

```cpp
~completion_future();
```

## <a name="see-also"></a>참고 항목

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
