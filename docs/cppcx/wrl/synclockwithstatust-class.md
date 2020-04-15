---
title: SyncLockWithStatusT 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT class
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT, constructor
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
ms.openlocfilehash: 77bcb8336e4650de7ed01a067fa1bdd7ec0ba3e8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374274"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename SyncTraits>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>매개 변수

*싱크특성*<br/>
리소스의 단독 또는 공유 소유권을 사용할 수 있는 형식입니다.

## <a name="remarks"></a>설명

리소스의 단독 또는 공유 소유권을 취할 수 있는 형식을 나타냅니다.

이 `SyncLockWithStatusT` 클래스는 [뮤텍스](mutex-class.md) 및 [세마포어](semaphore-class.md) 클래스를 구현하는 데 사용됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                                             | Description
---------------------------------------------------------------- | --------------------------------------------------------------
[동기화잠금상태::동기화잠금상태T](#synclockwithstatust) | `SyncLockWithStatusT` 클래스의 새 인스턴스를 초기화합니다.

### <a name="protected-constructors"></a>Protected 생성자

속성                                                             | Description
---------------------------------------------------------------- | --------------------------------------------------------------
[동기화잠금상태::동기화잠금상태T](#synclockwithstatust) | `SyncLockWithStatusT` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                                         | Description
-------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------
[동기화잠금상태::겟상태](#getstatus) | 현재 `SyncLockWithStatusT` 개체의 대기 상태를 검색합니다.
[동기화잠금상태::잠김](#islocked)   | 현재 `SyncLockWithStatusT` 개체가 리소스를 소유하고 있는지 여부를 나타냅니다. 즉, 개체가 `SyncLockWithStatusT` *잠겨*있습니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

속성                                    | Description
--------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------
[동기화잠금상태::status_](#status) | 현재 `SyncLockWithStatusT` 개체를 기반으로 개체에 대한 잠금 작업 후 기본 대기 작업의 결과를 보유합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼::D

## <a name="synclockwithstatustgetstatus"></a><a name="getstatus"></a>동기화잠금상태::겟상태

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
DWORD GetStatus() const;
```

### <a name="return-value"></a>Return Value

`SyncLockWithStatusT` [뮤텍스](mutex-class.md) 또는 [세마포와](semaphore-class.md)같은 클래스를 기반으로 하는 개체에 대한 대기 작업의 결과입니다. 0(0)은 대기 작업이 신호 상태를 반환했음을 나타냅니다. 그렇지 않으면 시간 제한 값이 경과하는 등 다른 상태가 발생했습니다.

### <a name="remarks"></a>설명

현재 `SyncLockWithStatusT` 개체의 대기 상태를 검색합니다.

GetStatus() 함수는 기본 [status_](#status) 데이터 멤버의 값을 검색합니다. `SyncLockWithStatusT` 클래스를 기반으로 하는 개체가 잠금 작업을 수행하면 개체가 먼저 개체를 사용할 수 있게 될 때까지 기다립니다. 해당 대기 작업의 결과는 데이터 `status_` 멤버에 저장됩니다. 데이터 멤버의 `status_` 가능한 값은 대기 작업의 반환 값입니다. 자세한 내용은 MSDN 라이브러리에서 `WaitForSingleObjectEx()` 함수의 반환 값을 참조하세요.

## <a name="synclockwithstatustislocked"></a><a name="islocked"></a>동기화잠금상태::잠김

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
bool IsLocked() const;
```

### <a name="remarks"></a>설명

현재 `SyncLockWithStatusT` 개체가 리소스를 소유하고 있는지 여부를 나타냅니다. 즉, 개체가 `SyncLockWithStatusT` *잠겨*있습니다.

### <a name="return-value"></a>Return Value

개체가 `SyncLockWithStatusT` 잠겨 있는 경우 **true입니다.** 그렇지 **않으면, 거짓**.

## <a name="synclockwithstatuststatus_"></a><a name="status"></a>동기화잠금상태::status_

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
DWORD status_;
```

### <a name="remarks"></a>설명

현재 `SyncLockWithStatusT` 개체를 기반으로 개체에 대한 잠금 작업 후 기본 대기 작업의 결과를 보유합니다.

## <a name="synclockwithstatustsynclockwithstatust"></a><a name="synclockwithstatust"></a>동기화잠금상태::동기화잠금상태T

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
SyncLockWithStatusT(
   _Inout_ SyncLockWithStatusT&& other
);

explicit SyncLockWithStatusT(
   typename SyncTraits::Type sync,
   DWORD status
);
```

### <a name="parameters"></a>매개 변수

*다른*<br/>
다른 `SyncLockWithStatusT` 개체에 대한 rvalue 참조입니다.

*동기화*<br/>
다른 `SyncLockWithStatusT` 개체에 대한 참조입니다.

*상태*<br/>
*다른* 매개 변수 또는 *동기화* 매개 변수의 [status_](#status) 데이터 멤버의 값입니다.

### <a name="remarks"></a>설명

`SyncLockWithStatusT` 클래스의 새 인스턴스를 초기화합니다.

첫 번째 생성자는 *다른* `SyncLockWithStatusT` 매개 변수에 의해 지정된 다른 `SyncLockWithStatusT` 개체에서 현재 `SyncLockWithStatusT` 개체를 초기화한 다음 다른 개체를 무효화합니다. 두 번째 생성자는 `protected`은 현재 `SyncLockWithStatusT` 개체를 잘못된 상태로 초기화합니다.
