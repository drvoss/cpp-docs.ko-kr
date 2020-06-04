---
title: thread 클래스
ms.date: 11/04/2016
f1_keywords:
- thread/std::thread
- thread/std::thread::id Class
- thread/std::thread::thread
- thread/std::thread::detach
- thread/std::thread::get_id
- thread/std::thread::hardware_concurrency
- thread/std::thread::join
- thread/std::thread::joinable
- thread/std::thread::native_handle
- thread/std::thread::swap
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
helpviewer_keywords:
- std::thread [C++]
- std::thread [C++], thread
- std::thread [C++], detach
- std::thread [C++], get_id
- std::thread [C++], hardware_concurrency
- std::thread [C++], join
- std::thread [C++], joinable
- std::thread [C++], native_handle
- std::thread [C++], swap
ms.openlocfilehash: 13996a8ec4ab56fc56a78606d1a2ce8d76994c0d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375849"
---
# <a name="thread-class"></a>thread 클래스

애플리케이션 내의 실행 스레드를 관찰하고 관리하는 데 사용되는 개체를 정의합니다.

## <a name="syntax"></a>구문

```cpp
class thread;
```

## <a name="remarks"></a>설명

**스레드** 개체를 사용하여 응용 프로그램 내에서 실행 스레드를 관찰하고 관리할 수 있습니다. 기본 생성자를 사용하여 만드는 스레드 개체는 실행 스레드와 연결되지 않습니다. 호출 가능 개체를 사용하여 생성되는 스레드 개체는 새 실행 스레드를 만들고 해당 스레드의 호출 가능 개체를 호출합니다. 스레드 개체는 이동할 수는 있지만 복사할 수는 없습니다. 따라서 실행 스레드는 하나만 스레드 개체에만 연결할 수 있습니다.

모든 실행 스레드에는 `thread::id` 형식의 고유 식별자가 있습니다. `this_thread::get_id` 함수는 호출 스레드의 식별자를 반환합니다. `thread::get_id` 구성원 함수는 스레드 개체가 관리하는 스레드의 식별자를 반환합니다. 기본 생성 스레드 개체의 경우 `thread::get_id` 메서드는 모든 기본 생성 스레드 개체에 대해서는 동일하고 호출 시에 조인할 수 실행 스레드에 대해 `this_thread::get_id`에서 반환하는 값과는 다른 값이 포함된 개체를 반환합니다.

## <a name="members"></a>멤버

### <a name="public-classes"></a>public 클래스

|속성|Description|
|----------|-----------------|
|[스레드::ID 클래스](#id_class)|관련 스레드를 고유하게 식별합니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[스레드(thread)](#thread)|**스레드** 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[분리](#detach)|스레드 **개체에서** 연결된 스레드를 분리합니다.|
|[get_id](#get_id)|관련 스레드의 고유 식별자를 반환합니다.|
|[hardware_concurrency](#hardware_concurrency)|정적. 하드웨어 스레드 컨텍스트 수의 추정치를 반환합니다.|
|[가입](#join)|관련 스레드가 완료될 때까지 차단합니다.|
|[조인 가능](#joinable)|관련 스레드가 조인 가능한지를 지정합니다.|
|[native_handle](#native_handle)|뮤텍스 핸들을 나타내는 구현별 형식을 반환합니다.|
|[스왑](#swap)|개체 상태를 지정된 **스레드** 개체로 바꿉습니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[thread::operator=](#op_eq)|스레드를 현재 **스레드** 개체와 연결합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<스레드>

**네임스페이스:** std

## <a name="threaddetach"></a><a name="detach"></a>스레드::d에타치

관련 스레드를 분리합니다. 종료 시에는 운영 체제가 스레드 리소스를 해제합니다.

```cpp
void detach();
```

### <a name="remarks"></a>설명

`detach`에 대한 호출 이후 [get_id](#get_id)를 후속 호출하면 [id](#id_class)가 반환됩니다.

호출 개체와 연결된 스레드를 조인할 수 없는 경우 함수는 오류 코드가 `invalid_argument`인 [system_error](../standard-library/system-error-class.md)를 throw합니다.

호출 개체와 연결된 스레드가 유효하지 않은 경우 함수는 오류 코드가 `no_such_process`인 `system_error`를 throw합니다.

## <a name="threadget_id"></a><a name="get_id"></a>스레드::get_id

연결된 스레드에 대한 고유 식별자를 반환합니다.

```cpp
id get_id() const noexcept;
```

### <a name="return-value"></a>Return Value

연결된 스레드를 고유하게 식별하는 [thread::id](#id_class) 개체이거나, 개체에 스레드가 연결되어 있지 않은 경우 `thread::id()`입니다.

## <a name="threadhardware_concurrency"></a><a name="hardware_concurrency"></a>스레드::hardware_concurrency

하드웨어 스레드 컨텍스트 수의 추정치를 반환하는 정적 메서드입니다.

```cpp
static unsigned int hardware_concurrency() noexcept;
```

### <a name="return-value"></a>Return Value

하드웨어 스레드 컨텍스트 수의 추정치입니다. 값이 계산할 수 없는 상태이거나 올바르게 정의되어 있지 않으면 이 메서드는 0을 반환합니다.

## <a name="threadid-class"></a><a name="id_class"></a>스레드::ID 클래스

프로세스에서 각 실행 스레드에 대한 고유 식별자를 반환합니다.

```cpp
class thread::id {
    id() noexcept;
};
```

### <a name="remarks"></a>설명

기본 생성자는 모든 기존 스레드에 대해 `thread::id` 개체와 비교하여 같지 않은 개체를 생성합니다.

모든 기본 생성 `thread::id` 개체의 비교 결과는 같습니다.

## <a name="threadjoin"></a><a name="join"></a>스레드::조인

호출 개체와 연결된 실행 스레드가 완료될 때까지 차단합니다.

```cpp
void join();
```

### <a name="remarks"></a>설명

호출이 성공하면 호출 개체에 대한 [get_id](#get_id) 후속 호출에서는 기존 스레드의 `thread::id`와 비교할 때 같지 않은 기본 [thread::id](#id_class)가 반환됩니다. 호출이 성공하지 않으면 `get_id`에서 반환되는 값은 변경되지 않습니다.

## <a name="threadjoinable"></a><a name="joinable"></a>스레드::조인 가능

연결된 스레드가 *조인 가능한지*여부를 지정합니다.

```cpp
bool joinable() const noexcept;
```

### <a name="return-value"></a>Return Value

연결된 스레드를 *조인할 수*있는 경우 **true입니다.** 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

스레드 개체는 `get_id() != id()`인 경우 *조인 가능*합니다.

## <a name="threadnative_handle"></a><a name="native_handle"></a>스레드::native_handle

뮤텍스 핸들을 나타내는 구현별 형식을 반환합니다. 스레드 핸들은 구현별 방식으로 사용할 수 있습니다.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Return Value

`native_handle_type`은 `void *`로 캐스팅된 Win32 `HANDLE`로 정의됩니다.

## <a name="threadoperator"></a><a name="op_eq"></a>스레드::연산자 =

지정한 개체의 스레드를 현재 개체에 연결합니다.

```cpp
thread& operator=(thread&& Other) noexcept;
```

### <a name="parameters"></a>매개 변수

*다른*\
**스레드** 개체입니다.

### <a name="return-value"></a>Return Value

`*this`

### <a name="remarks"></a>설명

호출 개체가 조인 가능하면 메서드는 detach를 호출합니다.

연결이 설정되면 `Other`는 기본 생성 상태로 설정됩니다.

## <a name="threadswap"></a><a name="swap"></a>스레드::스왑

개체 상태를 지정된 **스레드** 개체의 상태로 바꿉습니다.

```cpp
void swap(thread& Other) noexcept;
```

### <a name="parameters"></a>매개 변수

*다른*\
**스레드** 개체입니다.

## <a name="threadthread-constructor"></a><a name="thread"></a>스레드::스레드 생성자

**스레드** 개체를 생성합니다.

```cpp
thread() noexcept;
template <class Fn, class... Args>
explicit thread(Fn&& F, Args&&... A);

thread(thread&& Other) noexcept;
```

### <a name="parameters"></a>매개 변수

*F*\
스레드에 의해 실행되는 애플리케이션 정의 함수

*A.*\
*F.*

*다른*\
기존 **스레드** 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 실행 스레드와 연결되지 않는 개체를 생성합니다. 생성된 개체에 대한 `get_id` 호출에서 반환되는 값은 `thread::id()`입니다.

두 번째 생성자는 새 실행 스레드와 연결된 개체를 생성하고 [ \<기능>](../standard-library/functional.md)정의된 `INVOKE` 의사 함수를 실행합니다. 새 스레드를 시작할 수 있는 리소스가 부족한 경우 함수는 오류 코드가 `resource_unavailable_try_again`인 [system_error](../standard-library/system-error-class.md) 개체를 throw합니다. *F에* 대한 호출이 catch되지 않은 예외로 종료되면 [종료가](../standard-library/exception-functions.md#terminate) 호출됩니다.

세 번째 생성자는 `Other`에 연결된 스레드와 연결되는 개체를 생성합니다. 그러면 `Other`는 기본 생성 상태로 설정됩니다.

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[\<스레드>](../standard-library/thread.md)
