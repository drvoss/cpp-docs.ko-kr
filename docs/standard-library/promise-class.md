---
title: promise 클래스
ms.date: 10/18/2018
f1_keywords:
- future/std::promise
- future/std::promise::promise
- future/std::promise::get_future
- future/std::promise::set_exception
- future/std::promise::set_exception_at_thread_exit
- future/std::promise::set_value
- future/std::promise::set_value_at_thread_exit
- future/std::promise::swap
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
helpviewer_keywords:
- std::promise [C++]
- std::promise [C++], promise
- std::promise [C++], get_future
- std::promise [C++], set_exception
- std::promise [C++], set_exception_at_thread_exit
- std::promise [C++], set_value
- std::promise [C++], set_value_at_thread_exit
- std::promise [C++], swap
ms.openlocfilehash: a6541fefb2423853f8e59a662e1c8a37777dc14c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323036"
---
# <a name="promise-class"></a>promise 클래스

*비동기 공급자에*대해 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
class promise;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[약속](#promise)|`promise` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[get_future](#get_future)|이 promise와 연관된 [future](../standard-library/future-class.md)를 반환합니다.|
|[set_exception](#set_exception)|예외를 나타내기 위해 이 promise의 결과를 원자 단위로 설정합니다.|
|[set_exception_at_thread_exit](#set_exception_at_thread_exit)|예외를 나타내기 위해 이 promise의 결과를 원자 단위로 설정하고 현재 스레드에 있는 모든 스레드 지역 개체가 제거된 후에만 통지를 전달합니다.|
|[set_value](#set_value)|이 promise의 결과를 원자 단위로 설정하여 값을 나타냅니다.|
|[set_value_at_thread_exit](#set_value_at_thread_exit)|값을 나타내기 위해 이 promise의 결과를 원자 단위로 설정하고 현재 스레드에 있는 모든 스레드 지역 개체가 제거된 후에만 통지를 전달합니다.|
|[스왑](#swap)|이 promise의 *연결된 비동기 상태*를 지정한 개체의 연결된 비동기 상태와 교환합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[약속::연산자=](#op_eq)|이 promise 개체의 공유 상태에 대한 할당입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

*약속*

## <a name="requirements"></a>요구 사항

**헤더:** \<미래의>

**네임스페이스:** std

## <a name="promiseget_future"></a><a name="get_future"></a>약속:get_future

이 promise와 동일한 *연결된 비동기 상태*가 있는 [future](../standard-library/future-class.md) 개체를 반환합니다.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>설명

promise 개체가 비어 있는 경우 이 메서드는 [error_code](../standard-library/error-code-class.md)가 `no_state`인 [future_error](../standard-library/future-error-class.md)를 throw합니다.

이 메서드가 연결된 비동기 상태가 동일한 promise 개체를 위해 호출된 경우 `future_error`가 `error_code`인 `future_already_retrieved`를 thorw합니다.

## <a name="promiseoperator"></a><a name="op_eq"></a>약속::연산자=

지정된 `promise` 개체에서 *연결된 비동기 상태*를 전송합니다.

```cpp
promise& operator=(promise&& Other) noexcept;
```

### <a name="parameters"></a>매개 변수

*다른*\
`promise` 개체입니다.

### <a name="return-value"></a>Return Value

`*this`

### <a name="remarks"></a>설명

이 연산자는 연결된 비동기 상태를 *기타*에서 전송합니다. 전송 후 *기타가* *비어*있습니다.

## <a name="promisepromise-constructor"></a><a name="promise"></a>약속::p로이스 생성자

`promise` 개체를 생성합니다.

```cpp
promise();
template <class Alloc>
promise(allocator_arg_t, const Alloc& Al);
promise(promise&& Other) noexcept;
```

### <a name="parameters"></a>매개 변수

*알*\
메모리 할당자입니다. 자세한 내용은 [ \<할당자>](../standard-library/allocators-header.md) 참조하세요.

*다른*\
`promise` 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 *빈* `promise` 개체를 생성합니다.

두 번째 생성자는 빈 `promise` 개체를 생성하고 메모리 할당에 *Al을* 사용합니다.

세 번째 생성자는 `promise` 개체를 생성하고 연결된 비동기 상태를 *기타에서*전송하고 *기타를* 비웁깁니다.

## <a name="promiseset_exception"></a><a name="set_exception"></a>약속::set_exception

이 `promise` 개체의 결과로 예외를 원자 단위로 저장하고 *연결된 비동기 상태*를 *ready*로 설정합니다.

```cpp
void set_exception(exception_ptr Exc);
```

### <a name="parameters"></a>매개 변수

*Exc*\
이 메서드가 예외 결과로 저장한 [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)입니다.

### <a name="remarks"></a>설명

`promise` 개체에 연결된 비동기 상태가 없는 경우 이 메서드는 오류 코드가 `no_state`인 [future_error](../standard-library/future-error-class.md)를 throw합니다.

`set_exception`, [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_value](#set_value) 또는 [set_value_at_thread_exit](#set_value_at_thread_exit)가 동일한 연관 비동기 상태의 `promise` 개체에 대해 이미 호출된 경우 이 메서드는 오류 코드가 `promise_already_satisfied`인 `future_error`를 throw합니다.

이 메서드의 결과로 연결된 비동기 상태에서 차단된 모든 스레드의 차단은 해제됩니다.

## <a name="promiseset_exception_at_thread_exit"></a><a name="set_exception_at_thread_exit"></a>약속:set_exception_at_thread_exit

이 `promise`의 결과를 원자 단위로 예외로 설정하여 현재 스레드의 스레드 로컬 개체가 모두 소멸된 후에만 통지를 전달합니다.

```cpp
void set_exception_at_thread_exit(exception_ptr Exc);
```

### <a name="parameters"></a>매개 변수

*Exc*\
이 메서드가 예외 결과로 저장한 [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)입니다.

### <a name="remarks"></a>설명

promise 개체에 *연결된 비동기 상태*가 없는 경우 이 메서드는 오류 코드가 `no_state`인 [future_error](../standard-library/future-error-class.md)를 throw합니다.

[set_exception](#set_exception), `set_exception_at_thread_exit` [set_value](#set_value)또는 [set_value_at_thread_exit](#set_value_at_thread_exit) 연결된 비동기 `promise` 상태가 동일한 개체에 대해 이미 호출된 경우 `future_error` 이 메서드는 `promise_already_satisfied`오류 코드가 있는 을 throw합니다.

[set_exception](#set_exception)과 달리 이 메서드는 현재 스레드에서 모든 스레드 로컬 개체가 제거될 때까지 연결된 비동기 상태를 ready로 설정하지 않습니다. 일반적으로 연관된 비동기 상태에서 차단된 스레드는 현재 스레드가 종료될 때까지 차단 해제되지 않습니다.

## <a name="promiseset_value"></a><a name="set_value"></a>약속:set_value

이 `promise` 개체의 결과로 값을 원자 단위로 저장하고 *연결된 비동기 상태*를 *ready*로 설정합니다.

```cpp
void promise::set_value(const Ty& Val);
void promise::set_value(Ty&& Val);
void promise<Ty&>::set_value(Ty& Val);
void promise<void>::set_value();
```

### <a name="parameters"></a>매개 변수

*발*\
결과로 저장할 값입니다.

### <a name="remarks"></a>설명

`promise` 개체에 연결된 비동기 상태가 없는 경우 이 메서드는 오류 코드가 `no_state`인 [future_error](../standard-library/future-error-class.md)를 throw합니다.

[set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit), `set_value` 또는 [set_value_at_thread_exit](#set_value_at_thread_exit)가 동일한 연관 비동기 상태의 `promise` 개체에 대해 이미 호출된 경우 이 메서드는 오류 코드가 `promise_already_satisfied`인 `future_error`를 throw합니다.

이 메서드의 결과로 연결된 비동기 상태에서 차단된 모든 스레드의 차단은 해제됩니다.

첫 번째 메서드는 *Val이* 연결된 비동기 상태로 복사될 때 throw되는 예외도 throw합니다. 이 경우 연결된 비동기 상태는 ready로 설정되지 않습니다.

두 번째 메서드는 *Val이* 연결된 비동기 상태로 이동할 때 throw되는 예외도 throw합니다. 이 경우 연결된 비동기 상태는 ready로 설정되지 않습니다.

부분 전문화의 `promise<Ty&>`경우 저장된 값은 실제로 *Val*에 대한 참조입니다.

특수화 `promise<void>`에 대해 저장된 값은 없습니다.

## <a name="promiseset_value_at_thread_exit"></a><a name="set_value_at_thread_exit"></a>약속::set_value_at_thread_exit

이 `promise` 개체의 결과로 값을 원자 단위로 저장합니다.

```cpp
void promise::set_value_at_thread_exit(const Ty& Val);
void promise::set_value_at_thread_exit(Ty&& Val);
void promise<Ty&>::set_value_at_thread_exit(Ty& Val);
void promise<void>::set_value_at_thread_exit();
```

### <a name="parameters"></a>매개 변수

*발*\
결과로 저장할 값입니다.

### <a name="remarks"></a>설명

promise 개체에 *연결된 비동기 상태*가 없는 경우 이 메서드는 오류 코드가 `no_state`인 [future_error](../standard-library/future-error-class.md)를 throw합니다.

[set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_value](#set_value) 또는 `set_value_at_thread_exit`가 동일한 연관 비동기 상태의 `promise` 개체에 대해 호출된 경우 이 메서드는 오류 코드가 `promise_already_satisfied`인 `future_error`를 throw합니다.

`set_value`와 달리 이 메서드는 현재 스레드에서 모든 스레드 로컬 개체가 제거될 때까지 연결된 비동기 상태를 ready로 설정하지 않습니다. 일반적으로 연관된 비동기 상태에서 차단된 스레드는 현재 스레드가 종료될 때까지 차단 해제되지 않습니다.

첫 번째 메서드는 *Val이* 연결된 비동기 상태로 복사될 때 throw되는 예외도 throw합니다.

두 번째 메서드는 *Val이* 연결된 비동기 상태로 이동할 때 throw되는 예외도 throw합니다.

부분 전문화의 `promise<Ty&>`경우 저장된 값은 Val *에*대한 참조입니다.

특수화 `promise<void>`에 대해 저장된 값은 없습니다.

## <a name="promiseswap"></a><a name="swap"></a>약속::스왑

이 promise 개체의 *연결된 비동기 상태*를 지정한 개체의 연결된 비동기 상태와 교환합니다.

```cpp
void swap(promise& Other) noexcept;
```

### <a name="parameters"></a>매개 변수

*다른*\
`promise` 개체입니다.

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)
