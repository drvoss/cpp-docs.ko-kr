---
title: SRWLock 클래스
ms.date: 09/25/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock_
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::~SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
helpviewer_keywords:
- Microsoft::WRL::Wrappers::SRWLock class
- Microsoft::WRL::Wrappers::SRWLock::LockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::LockShared method
- Microsoft::WRL::Wrappers::SRWLock::SRWLock, constructor
- Microsoft::WRL::Wrappers::SRWLock::SRWLock_ data member
- Microsoft::WRL::Wrappers::SRWLock::~SRWLock, destructor
- Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::TryLockShared method
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
ms.openlocfilehash: e305ad54e30455ce7c25f356c454791da0783591
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377273"
---
# <a name="srwlock-class"></a>SRWLock 클래스

슬림 판독기/작성기 잠금을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class SRWLock;
```

## <a name="remarks"></a>설명

슬림 판독기/기록기 잠금은 스레드 간 액세스를 개체 또는 리소스에 동기화하는 데 사용됩니다. 자세한 내용은 [동기화 함수를](/windows/win32/Sync/synchronization-functions)참조하십시오.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성                | Description
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | 단독 모드에서 획득한 `SRWLock` 개체의 동의어입니다.
`SyncLockShared`    | 공유 모드에서 획득한 `SRWLock` 개체의 동의어입니다.

### <a name="public-constructors"></a>Public 생성자

속성                                     | Description
---------------------------------------- | --------------------------------------------------
[SRWLock :: SRWWLock](#srwlock-constructor) | `SRWLock` 클래스의 새 인스턴스를 초기화합니다.
[SRWLock ::~SRWLock](#tilde-srwlock)      | 클래스의 인스턴스를 초기화합니다. `SRWLock`

### <a name="public-methods"></a>Public 메서드

속성                                           | Description
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock :: 잠금 독점](#lockexclusive)       | 전용 모드에서 `SRWLock` 개체를 획득합니다.
[SRWLock::잠금 공유](#lockshared)             | 공유 모드에서 `SRWLock` 개체를 수집합니다.
[SRWLock::트라이록독점](#trylockexclusive) | 현재 또는 `SRWLock` 지정된 `SRWLock` 개체에 대해 단독 모드에서 개체를 획득하려고 시도합니다.
[SRWLock::트라이록공유](#trylockshared)       | 현재 또는 `SRWLock` 지정된 `SRWLock` 개체에 대해 공유 모드에서 개체를 가져오려고 시도합니다.

### <a name="protected-data-member"></a>보호된 데이터 멤버

속성                                      | Description
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock::SRWLock_](#srwlock-data-member) | 현재 `SRWLock` 개체에 대한 기본 잠금 변수를 포함합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`SRWLock`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼

## <a name="srwlocksrwlock"></a><a name="tilde-srwlock"></a>SRWLock ::~SRWLock

클래스의 인스턴스를 초기화합니다. `SRWLock`

```cpp
~SRWLock();
```

## <a name="srwlocklockexclusive"></a><a name="lockexclusive"></a>SRWLock :: 잠금 독점

전용 모드에서 `SRWLock` 개체를 획득합니다.

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
개체에 `SRWLock` 대한 포인터입니다.

### <a name="return-value"></a>Return Value

배타적 모드의 `SRWLock` 개체입니다.

## <a name="srwlocklockshared"></a><a name="lockshared"></a>SRWLock::잠금 공유

공유 모드에서 `SRWLock` 개체를 수집합니다.

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
개체에 `SRWLock` 대한 포인터입니다.

### <a name="return-value"></a>Return Value

공유 `SRWLock` 모드의 개체입니다.

## <a name="srwlocksrwlock"></a><a name="srwlock-constructor"></a>SRWLock :: SRWWLock

`SRWLock` 클래스의 새 인스턴스를 초기화합니다.

```cpp
SRWLock();
```

## <a name="srwlocksrwlock_"></a><a name="srwlock-data-member"></a>SRWLock::SRWLock_

현재 `SRWLock` 개체에 대한 기본 잠금 변수를 포함합니다.

```cpp
SRWLOCK SRWLock_;
```

## <a name="srwlocktrylockexclusive"></a><a name="trylockexclusive"></a>SRWLock::트라이록독점

현재 또는 `SRWLock` 지정된 `SRWLock` 개체에 대해 단독 모드에서 개체를 획득하려고 시도합니다. 호출이 성공하면 호출 스레드가 잠금의 소유권을 가져옵니다.

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
개체에 `SRWLock` 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 단독 `SRWLock` 모드의 개체와 호출 스레드가 잠금의 소유권을 가져옵니다. 그렇지 않으면 `SRWLock` 상태가 잘못된 개체입니다.

## <a name="srwlocktrylockshared"></a><a name="trylockshared"></a>SRWLock::트라이록공유

현재 또는 `SRWLock` 지정된 `SRWLock` 개체에 대해 공유 모드에서 개체를 가져오려고 시도합니다.

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
개체에 `SRWLock` 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 공유 `SRWLock` 모드의 개체와 호출 스레드가 잠금의 소유권을 가져옵니다. 그렇지 않으면 `SRWLock` 상태가 잘못된 개체입니다.
