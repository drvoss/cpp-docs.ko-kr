---
title: reader_writer_lock 클래스
ms.date: 11/04/2016
f1_keywords:
- reader_writer_lock
- CONCRT/concurrency::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock_read
- CONCRT/concurrency::reader_writer_lock::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::lock
- CONCRT/concurrency::reader_writer_lock::lock_read
- CONCRT/concurrency::reader_writer_lock::try_lock
- CONCRT/concurrency::reader_writer_lock::try_lock_read
- CONCRT/concurrency::reader_writer_lock::unlock
helpviewer_keywords:
- reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
ms.openlocfilehash: 13b44387f3e9489090ec31345fe4347ff5f205ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376249"
---
# <a name="reader_writer_lock-class"></a>reader_writer_lock 클래스

로컬 전용 회전을 사용한 작성기 우선 큐 기반 읽기/쓰기 잠금입니다. 잠금은 작성기에 대해 FIFO(선입 선출) 액세스 권한을 부여하며 작성기의 연속 부하 상태에서는 판독기에 제공되지 않습니다.

## <a name="syntax"></a>구문

```cpp
class reader_writer_lock;
```

## <a name="members"></a>멤버

### <a name="public-classes"></a>public 클래스

|속성|Description|
|----------|-----------------|
|[reader_writer_lock::scoped_lock 클래스](#scoped_lock_class)|잠금 개체를 기록기로 획득하는 `reader_writer_lock` 데 사용할 수 있는 예외 안전 RAII 래퍼입니다.|
|[reader_writer_lock::scoped_lock_read 클래스](#scoped_lock_read_class)|잠금 개체를 판독기로 획득하는 `reader_writer_lock` 데 사용할 수 있는 예외 안전 RAII 래퍼입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[reader_writer_lock](#ctor)|새 `reader_writer_lock` 개체를 생성합니다.|
|[~ reader_writer_lock 소멸자](#dtor)|개체를 `reader_writer_lock` 삭제합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[lock](#lock)|판독기-작성기 잠금을 기록기로 획득합니다.|
|[lock_read](#lock_read)|판독기-작성기 잠금을 판독기로 획득합니다. 작성기가 있는 경우 활성 독자는 완료될 때까지 기다려야 합니다. 독자는 단순히 잠금에 대한 관심을 등록하고 작성기가 잠금을 해제할 때까지 기다립니다.|
|[try_lock](#try_lock)|차단하지 않고 판독기-작성기 잠금을 작성자로 획득하려고 시도합니다.|
|[try_lock_read](#try_lock_read)|차단하지 않고 판독기-작성기 잠금을 판독기로 획득하려고 시도합니다.|
|[잠금을 해제](#unlock)|누가 잠근 사람, 판독기 또는 기록기를 기반으로 판독기-작성기 잠금을 해제합니다.|

## <a name="remarks"></a>설명

자세한 내용은 [동기화 데이터 구조를](../../../parallel/concrt/synchronization-data-structures.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`reader_writer_lock`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

## <a name="lock"></a><a name="lock"></a>잠금

판독기-작성기 잠금을 기록기로 획득합니다.

```cpp
void lock();
```

### <a name="remarks"></a>설명

[scoped_lock](#scoped_lock_class) 구문에서 `reader_writer_lock` 객체를 획득하고 릴리스하는 것이 안전한 방법으로 작성자로서 사용하는 것이 더 안전합니다.

작성기가 잠금을 가져오려고 시도하면 이후 판독기는 작성기가 잠금을 성공적으로 가져와 해제할 때까지 차단됩니다. 이 잠금은 작성기로 편향되어 있으며 작성자의 지속적인 부하에서 판독기를 굶어 사용할 수 있습니다.

기록기는 잠금을 종료하는 작성자가 다음 기록기를 줄에 놓습니다.

호출 컨텍스트에서 잠금이 이미 유지된 경우 [improper_lock](improper-lock-class.md) 예외가 throw됩니다.

## <a name="lock_read"></a><a name="lock_read"></a>lock_read

판독기-작성기 잠금을 판독기로 획득합니다. 작성기가 있는 경우 활성 독자는 완료될 때까지 기다려야 합니다. 독자는 단순히 잠금에 대한 관심을 등록하고 작성기가 잠금을 해제할 때까지 기다립니다.

```cpp
void lock_read();
```

### <a name="remarks"></a>설명

[scoped_lock_read](#scoped_lock_read_class) 구문에서 객체를 획득하고 `reader_writer_lock` 릴리스하는 것이 안전한 방법으로 개체를 확보하는 것이 더 안전합니다.

잠금을 기다리는 작성기가 있는 경우 판독기는 줄에 있는 모든 작성기가 잠금을 획득하고 해제할 때까지 기다립니다. 이 잠금은 작성기로 편향되어 있으며 작성자의 지속적인 부하에서 판독기를 굶어 사용할 수 있습니다.

## <a name="reader_writer_lock"></a><a name="ctor"></a>reader_writer_lock

새 `reader_writer_lock` 개체를 생성합니다.

```cpp
reader_writer_lock();
```

## <a name="reader_writer_lock"></a><a name="dtor"></a>~ reader_writer_lock

개체를 `reader_writer_lock` 삭제합니다.

```cpp
~reader_writer_lock();
```

### <a name="remarks"></a>설명

소멸자가 실행될 때 잠금이 더 이상 유지되지 않습니다. 판독기 작성기 잠금이 잠금으로 소멸하도록 허용하면 여전히 고정된 동작이 발생합니다.

## <a name="reader_writer_lockscoped_lock-class"></a><a name="scoped_lock_class"></a>reader_writer_lock::scoped_lock 클래스

잠금 개체를 기록기로 획득하는 `reader_writer_lock` 데 사용할 수 있는 예외 안전 RAII 래퍼입니다.

```cpp
class scoped_lock;
```

## <a name="scoped_lockscoped_lock"></a><a name="scoped_lock_ctor"></a>scoped_lock:scoped_lock

개체를 `scoped_lock` 생성하고 매개 `reader_writer_lock` 변수에 전달된 개체를 `_Reader_writer_lock` 작성기로 획득합니다. 다른 스레드에서 잠금을 유지하면 이 호출이 차단됩니다.

```cpp
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>매개 변수

*_Reader_writer_lock*<br/>
기록기로 획득할 `reader_writer_lock` 개체입니다.

## <a name="scoped_lockscoped_lock"></a><a name="scoped_lock_dtor"></a>scoped_lock:~scoped_lock

개체를 `reader_writer_lock` 삭제 하 고 해당 생성자에서 제공 된 잠금을 해제 합니다.

```cpp
~scoped_lock();
```

## <a name="reader_writer_lockscoped_lock_read-class"></a><a name="scoped_lock_read_class"></a>reader_writer_lock::scoped_lock_read 클래스

잠금 개체를 판독기로 획득하는 `reader_writer_lock` 데 사용할 수 있는 예외 안전 RAII 래퍼입니다.

```cpp
class scoped_lock_read;
```

## <a name="scoped_lock_readscoped_lock_read"></a><a name="scoped_lock_read_ctor"></a>scoped_lock_read:scoped_lock_read

개체를 `scoped_lock_read` 생성하고 매개 `reader_writer_lock` 변수에 전달된 개체를 `_Reader_writer_lock` 판독기로 획득합니다. 다른 스레드에서 기록기로 잠금을 유지하거나 보류 중인 기록기가 있는 경우 이 호출이 차단됩니다.

```cpp
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>매개 변수

*_Reader_writer_lock*<br/>
판독기로 획득할 `reader_writer_lock` 개체입니다.

## <a name="a-namescoped_lock_read_dtor--reader_writer_lockscoped_lock_readscoped_lock_read-destructor"></a><a name="scoped_lock_read_dtor">reader_writer_lock:scoped_lock_read:~scoped_lock_read 파괴자

개체를 `scoped_lock_read` 삭제 하 고 해당 생성자에서 제공 된 잠금을 해제 합니다.

```cpp
~scoped_lock_read();
```

## <a name="try_lock"></a><a name="try_lock"></a>try_lock

차단하지 않고 판독기-작성기 잠금을 작성자로 획득하려고 시도합니다.

### <a name="syntax"></a>구문

```cpp
bool try_lock();
```

### <a name="return-value"></a>Return Value

잠금을 획득한 경우 값 **true입니다.** 그렇지 않으면 값이 **false입니다.**

## <a name="try_lock_read"></a><a name="try_lock_read"></a>try_lock_read

차단하지 않고 판독기-작성기 잠금을 판독기로 획득하려고 시도합니다.

```cpp
bool try_lock_read();
```

### <a name="return-value"></a>Return Value

잠금을 획득한 경우 값 **true입니다.** 그렇지 않으면 값이 **false입니다.**

## <a name="unlock"></a><a name="unlock"></a>잠금을 해제

누가 잠근 사람, 판독기 또는 기록기를 기반으로 판독기-작성기 잠금을 해제합니다.

```cpp
void unlock();
```

### <a name="remarks"></a>설명

잠금을 기다리는 기록기가 있는 경우 잠금 해제는 항상 FIFO 순서의 다음 기록기로 이동합니다. 이 잠금은 작성기로 편향되어 있으며 작성자의 지속적인 부하에서 판독기를 굶어 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)<br/>
[critical_section 클래스](critical-section-class.md)
