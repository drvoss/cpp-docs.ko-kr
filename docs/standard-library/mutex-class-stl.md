---
title: mutex 클래스(C++ 표준 라이브러리)| Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- mutex/std::mutex
- mutex/std::mutex::mutex
- mutex/std::mutex::lock
- mutex/std::mutex::native_handle
- mutex/std::mutex::try_lock
- mutex/std::mutex::unlock
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
helpviewer_keywords:
- std::mutex [C++]
- std::mutex [C++], mutex
- std::mutex [C++], lock
- std::mutex [C++], native_handle
- std::mutex [C++], try_lock
- std::mutex [C++], unlock
ms.openlocfilehash: 84e6e3a46903a204444df9886556ae2c563304a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364838"
---
# <a name="mutex-class-c-standard-library"></a>mutex 클래스(C++ 표준 라이브러리)

*뮤텍스 형식을*나타냅니다. 이 형식의 객체는 프로그램 내에서 상호 제외를 강제 수행하기 위해 사용될 수 있습니다.

## <a name="syntax"></a>구문

```cpp
class mutex;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[뮤텍스](#mutex)|`mutex` 개체를 생성합니다.|
|[뮤텍스 :~뮤텍스 소멸자](#dtormutex_destructor)|`mutex` 개체에서 사용하는 리소스를 모두 해제합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[lock](#lock)|스레드가 `mutex`의 소유권을 가져올 때까지 호출 스레드를 차단합니다.|
|[native_handle](#native_handle)|뮤텍스 핸들을 나타내는 특정 구현 형식을 반환합니다.|
|[try_lock](#try_lock)|차단되지 않고 `mutex`의 소유권을 가져오려고 시도합니다.|
|[잠금을 해제](#unlock)|`mutex`의 소유권을 해제합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<뮤텍스>

**네임스페이스:** std

## <a name="mutexlock"></a><a name="lock"></a>뮤텍스::잠금

스레드가 `mutex`의 소유권을 가져올 때까지 호출 스레드를 차단합니다.

```cpp
void lock();
```

### <a name="remarks"></a>설명

호출 스레드가 이미 `mutex`를 소유하고 있는 경우, 이 동작은 정의되지 않습니다.

## <a name="mutexmutex-constructor"></a><a name="mutex"></a>뮤텍스::뮤텍스 생성자

잠기지 않은 `mutex` 개체를 생성합니다.

```cpp
constexpr mutex() noexcept;
```

## <a name="mutexmutex-destructor"></a><a name="dtormutex_destructor"></a>뮤텍스 :~뮤텍스 소멸자

`mutex` 개체에서 사용하는 리소스를 모두 해제합니다.

```cpp
~mutex();
```

### <a name="remarks"></a>설명

소멸자가 실행될 때 개체가 잠겨 있는 경우, 이 동작은 정의되지 않습니다.

## <a name="mutexnative_handle"></a><a name="native_handle"></a>뮤텍스:native_handle

뮤텍스 핸들을 나타내는 특정 구현 형식을 반환합니다. 뮤텍스 핸들은 구현별 방식으로 사용할 수 있습니다.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Return Value

`native_handle_type`은 `void *`로 캐스팅된 `Concurrency::critical_section *`으로 정의됩니다.

## <a name="mutextry_lock"></a><a name="try_lock"></a>뮤텍스:try_lock

차단되지 않고 `mutex`의 소유권을 가져오려고 시도합니다.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Return Value

메서드가 성공적으로 소유권을 `mutex`획득하는 **경우.** 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

호출 스레드가 이미 `mutex`를 소유하고 있는 경우, 이 동작은 정의되지 않습니다.

## <a name="mutexunlock"></a><a name="unlock"></a>뮤텍스::잠금 해제

`mutex`의 소유권을 해제합니다.

```cpp
void unlock();
```

### <a name="remarks"></a>설명

호출 스레드가 `mutex`를 소유하지 않은 경우, 이 동작은 정의되지 않습니다.

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[\<뮤텍스>](../standard-library/mutex.md)
