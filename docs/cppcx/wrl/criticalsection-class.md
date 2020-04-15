---
title: CriticalSection 클래스
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::cs_
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::IsValid
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::CriticalSection class
- Microsoft::WRL::Wrappers::CriticalSection::cs_ data member
- Microsoft::WRL::Wrappers::CriticalSection::IsValid method
- Microsoft::WRL::Wrappers::CriticalSection::Lock method
- Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection, destructor
- Microsoft::WRL::Wrappers::CriticalSection::CriticalSection, constructor
- Microsoft::WRL::Wrappers::CriticalSection::TryLock method
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
ms.openlocfilehash: 5deb89e795d1886ca316886ae1ea260ce1f36fd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372596"
---
# <a name="criticalsection-class"></a>CriticalSection 클래스

임계 영역 개체를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class CriticalSection;
```

## <a name="members"></a>멤버

### <a name="constructor"></a>생성자

속성                                                        | Description
----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[임계 섹션::중요 섹션](#criticalsection)        | 뮤텍스 개체와 유사하지만 단일 프로세스의 스레드에만 사용할 수 있는 동기화 개체를 초기화합니다.
[임계 섹션::~임계 섹션](#tilde-criticalsection) | 현재 `CriticalSection` 오브젝트를 초기화하고 삭제합니다.

### <a name="public-methods"></a>Public 메서드

속성                                 | Description
------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------
[임계 섹션::유효합니다.](#isvalid) | 현재 임계 영역이 유효한지 여부를 나타냅니다.
[임계 섹션::잠금](#lock)       | 지정된 임계 영역 개체의 소유권을 기다립니다. 함수가 호출 스레드가 소유권을 부여받는 시기를 반환합니다.
[임계 섹션::트라이록](#trylock) | 차단하지 않고 임계 섹션에 들어가려고 시도합니다. 호출이 성공하면 호출 스레드는 중요 섹션의 소유권을 차지합니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

속성                        | Description
--------------------------- | ----------------------------------------
[임계 섹션:cs_](#cs) | 임계 영역 데이터 멤버를 선언합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CriticalSection`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼

## <a name="criticalsectioncriticalsection"></a><a name="tilde-criticalsection"></a>임계 섹션::~임계 섹션

현재 `CriticalSection` 오브젝트를 초기화하고 삭제합니다.

```cpp
WRL_NOTHROW ~CriticalSection();
```

## <a name="criticalsectioncriticalsection"></a><a name="criticalsection"></a>임계 섹션::중요 섹션

뮤텍스 개체와 유사하지만 단일 프로세스의 스레드에만 사용할 수 있는 동기화 개체를 초기화합니다.

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>매개 변수

*스핀 카운트*<br/>
임계 영역 개체의 스핀 수입니다. 기본값은 0입니다.

### <a name="remarks"></a>설명

중요한 섹션 및 스핀수에 대한 `InitializeCriticalSectionAndSpinCount` 자세한 내용은 `Synchronization` Windows API documenation 섹션의 함수를 참조하십시오.

## <a name="criticalsectioncs_"></a><a name="cs"></a>임계 섹션:cs_

임계 영역 데이터 멤버를 선언합니다.

```cpp
CRITICAL_SECTION cs_;
```

### <a name="remarks"></a>설명

이 데이터 멤버가 보호됩니다.

## <a name="criticalsectionisvalid"></a><a name="isvalid"></a>임계 섹션::유효합니다.

현재 임계 영역이 유효한지 여부를 나타냅니다.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Return Value

기본적으로 항상 **true를 반환합니다.**

## <a name="criticalsectionlock"></a><a name="lock"></a>임계 섹션::잠금

지정된 임계 영역 개체의 소유권을 기다립니다. 함수가 호출 스레드가 소유권을 부여받는 시기를 반환합니다.

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>매개 변수

*cs*<br/>
사용자가 지정한 임계 영역 개체입니다.

### <a name="return-value"></a>Return Value

현재 임계 영역의 잠금을 해제하는 데 사용할 수 있는 잠금 개체입니다.

### <a name="remarks"></a>설명

첫 번째 `Lock` 함수는 현재 임계 영역 개체에 영향을 미칩니다. 두 번째 `Lock` 함수는 사용자가 지정한 임계 영역에 영향을 미칩니다.

## <a name="criticalsectiontrylock"></a><a name="trylock"></a>임계 섹션::트라이록

차단하지 않고 임계 섹션에 들어가려고 시도합니다. 호출이 성공하면 호출 스레드는 중요 섹션의 소유권을 차지합니다.

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>매개 변수

*cs*<br/>
사용자가 지정한 임계 영역 개체입니다.

### <a name="return-value"></a>Return Value

임계 섹션이 성공적으로 입력된 경우 또는 현재 스레드가 이미 임계 섹션을 소유하고 있는 경우 비영값입니다. 다른 스레드가 이미 임계 섹션을 소유하고 있는 경우 0입니다.

### <a name="remarks"></a>설명

첫 번째 `TryLock` 함수는 현재 임계 영역 개체에 영향을 미칩니다. 두 번째 `TryLock` 함수는 사용자가 지정한 임계 영역에 영향을 미칩니다.
