---
title: critical_section 클래스
ms.date: 11/04/2016
f1_keywords:
- critical_section
- CONCRT/concurrency::critical_section
- CONCRT/concurrency::critical_section::critical_section::scoped_lock Class
- CONCRT/concurrency::critical_section::critical_section
- CONCRT/concurrency::critical_section::lock
- CONCRT/concurrency::critical_section::native_handle
- CONCRT/concurrency::critical_section::try_lock
- CONCRT/concurrency::critical_section::try_lock_for
- CONCRT/concurrency::critical_section::unlock
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
ms.openlocfilehash: 24f96282a7728c6db6e0b05d36406f15383913f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372685"
---
# <a name="critical_section-class"></a>critical_section 클래스

동시성 런타임을 명시적으로 인식하는 재진입성이 아닌 뮤텍스입니다.

## <a name="syntax"></a>구문

```cpp
class critical_section;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|`native_handle_type`|`critical_section` 개체에 대한 참조입니다.|

### <a name="public-classes"></a>public 클래스

|속성|Description|
|----------|-----------------|
|[critical_section::scoped_lock 클래스](#critical_section__scoped_lock_class)|개체에 대한 예외 안전 `critical_section` RAII 래퍼입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[critical_section](#ctor)|새 임계 섹션을 생성합니다.|
|[~ critical_section 소멸자](#dtor)|임계 부분을 파괴합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[lock](#lock)|이 임계 섹션을 획득합니다.|
|[native_handle](#native_handle)|플랫폼이 있는 경우 특정 네이티브 핸들을 반환합니다.|
|[try_lock](#try_lock)|차단하지 않고 잠금을 획득하려고 시도합니다.|
|[try_lock_for](#try_lock_for)|특정 기간(밀리초) 동안 차단하지 않고 잠금을 가져오려고 시도합니다.|
|[잠금을 해제](#unlock)|임계 부분을 잠금 해제합니다.|

## <a name="remarks"></a>설명

자세한 내용은 [동기화 데이터 구조를](../../../parallel/concrt/synchronization-data-structures.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`critical_section`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

## <a name="critical_section"></a><a name="ctor"></a>critical_section

새 임계 섹션을 생성합니다.

```cpp
critical_section();
```

## <a name="critical_section"></a><a name="dtor"></a>~ critical_section

임계 부분을 파괴합니다.

```cpp
~critical_section();
```

### <a name="remarks"></a>설명

소멸자가 실행될 때 잠금이 더 이상 유지되지 않습니다. 임계 섹션이 잠금 으로 파괴될 수 있도록 허용하면 정의되지 않은 동작이 발생합니다.

## <a name="lock"></a><a name="lock"></a>잠금

이 임계 섹션을 획득합니다.

```cpp
void lock();
```

### <a name="remarks"></a>설명

[scoped_lock](#critical_section__scoped_lock_class) 구문에서 객체를 획득하고 `critical_section` 릴리스하는 것이 더 안전한 경우가 많습니다.

호출 컨텍스트에서 잠금이 이미 유지된 경우 [improper_lock](improper-lock-class.md) 예외가 throw됩니다.

## <a name="native_handle"></a><a name="native_handle"></a>native_handle

플랫폼이 있는 경우 특정 네이티브 핸들을 반환합니다.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Return Value

임계 섹션에 대한 참조입니다.

### <a name="remarks"></a>설명

`critical_section` 개체는 Windows 운영 체제에 대한 플랫폼 특정 기본 핸들과 연결되지 않습니다. 메서드는 개체 자체에 대한 참조를 반환합니다.

## <a name="critical_sectionscoped_lock-class"></a><a name="critical_section__scoped_lock_class"></a>critical_section:scoped_lock 클래스

개체에 대한 예외 안전 `critical_section` RAII 래퍼입니다.

```cpp
class scoped_lock;
```

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_ctor"></a>scoped_lock:scoped_lock

개체를 `scoped_lock` 생성하고 매개 `critical_section` 변수에서 전달된 개체를 획득합니다. `_Critical_section` 임계 섹션이 다른 스레드에 의해 유지되는 경우 이 호출은 차단됩니다.

```cpp
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>매개 변수

*_Critical_section*<br/>
잠글 수 있는 임계 섹션입니다.

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_dtor"></a>scoped_lock:~scoped_lock

개체를 `scoped_lock` 삭제 하고 해당 생성자에서 제공 하는 임계 섹션을 해제 합니다.

```cpp
~scoped_lock();
```

## <a name="try_lock"></a><a name="try_lock"></a>try_lock

차단하지 않고 잠금을 획득하려고 시도합니다.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Return Value

잠금을 획득한 경우 값 **true입니다.** 그렇지 않으면 값이 **false입니다.**

## <a name="try_lock_for"></a><a name="try_lock_for"></a>try_lock_for

특정 기간(밀리초) 동안 차단하지 않고 잠금을 가져오려고 시도합니다.

```cpp
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>매개 변수

*_Timeout*<br/>
시간이 초과되기 전에 대기하는 기간(밀리초)입니다.

### <a name="return-value"></a>Return Value

잠금을 획득한 경우 값 **true입니다.** 그렇지 않으면 값이 **false입니다.**

## <a name="unlock"></a><a name="unlock"></a>잠금을 해제

임계 부분을 잠금 해제합니다.

```cpp
void unlock();
```

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)<br/>
[reader_writer_lock 클래스](reader-writer-lock-class.md)
