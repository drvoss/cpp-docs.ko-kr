---
title: SyncLockT 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::sync_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockT class
- Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockT::sync_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT, constructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT, destructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock method
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
ms.openlocfilehash: 52c4404fa28f680a9a7a4592d03f535e8406d1a4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374277"
---
# <a name="synclockt-class"></a>SyncLockT 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename SyncTraits>
class SyncLockT;
```

### <a name="parameters"></a>매개 변수

*싱크특성*<br/>
리소스의 소유권을 가져갈 수 있는 형식입니다.

## <a name="remarks"></a>설명

리소스의 단독 또는 공유 소유권을 취할 수 있는 형식을 나타냅니다.

예를 `SyncLockT` 들어 [SRWLock](srwlock-class.md) 클래스를 구현하는 데 클래스가 사용됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                      | Description
----------------------------------------- | ----------------------------------------------------
[동기화 잠금::동기화 잠금](#synclockt)        | `SyncLockT` 클래스의 새 인스턴스를 초기화합니다.
[동기화 잠금: :~동기화 잠금](#tilde-synclockt) | 클래스의 인스턴스를 초기화합니다. `SyncLockT`

### <a name="protected-constructors"></a>Protected 생성자

속성                               | Description
---------------------------------- | ----------------------------------------------------
[동기화 잠금::동기화 잠금](#synclockt) | `SyncLockT` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                             | Description
-------------------------------- | --------------------------------------------------------------------------------------------------------------
[동기화잠금::잠금](#islocked) | 현재 `SyncLockT` 개체가 리소스를 소유하고 있는지 여부를 나타냅니다. 즉, 개체가 `SyncLockT` *잠겨*있습니다.
[동기화 잠금::잠금 해제](#unlock)     | 현재 `SyncLockT` 개체가 보유한 리소스(있는 경우)의 제어를 해제합니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

속성                      | Description
------------------------- | -------------------------------------------------------------------
[동기화잠금: sync_](#sync) | 클래스로 표시되는 기본 `SyncLockT` 리소스를 보유합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`SyncLockT`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼::D

## <a name="synclocktsynclockt"></a><a name="tilde-synclockt"></a>동기화 잠금: :~동기화 잠금

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
~SyncLockT();
```

### <a name="remarks"></a>설명

클래스의 인스턴스를 초기화합니다. `SyncLockT`

이 소멸자는 현재 `SyncLockT` 인스턴스의 잠금을 해제합니다.

## <a name="synclocktislocked"></a><a name="islocked"></a>동기화잠금::잠금

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
bool IsLocked() const;
```

### <a name="return-value"></a>Return Value

개체가 `SyncLockT` 잠겨 있는 경우 **true입니다.** 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

현재 `SyncLockT` 개체가 리소스를 소유하고 있는지 여부를 나타냅니다. 즉, 개체가 `SyncLockT` *잠겨*있습니다.

## <a name="synclocktsync_"></a><a name="sync"></a>동기화잠금: sync_

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
typename SyncTraits::Type sync_;
```

### <a name="remarks"></a>설명

클래스로 표시되는 기본 `SyncLockT` 리소스를 보유합니다.

## <a name="synclocktsynclockt"></a><a name="synclockt"></a>동기화 잠금::동기화 잠금

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()
);
```

### <a name="parameters"></a>매개 변수

*다른*<br/>
다른 `SyncLockT` 개체에 대한 rvalue 참조입니다.

*동기화*<br/>
다른 `SyncLockWithStatusT` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

`SyncLockT` 클래스의 새 인스턴스를 초기화합니다.

첫 번째 생성자는 *다른* `SyncLockT` 매개 변수에 의해 지정된 다른 `SyncLockT` 개체에서 현재 `SyncLockT` 개체를 초기화한 다음 다른 개체를 무효화합니다. 두 번째 생성자는 `protected`은 현재 `SyncLockT` 개체를 잘못된 상태로 초기화합니다.

## <a name="synclocktunlock"></a><a name="unlock"></a>동기화 잠금::잠금 해제

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
void Unlock();
```

### <a name="remarks"></a>설명

현재 `SyncLockT` 개체가 보유한 리소스(있는 경우)의 제어를 해제합니다.
