---
title: SRWLockSharedTraits 구조체
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock method
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
ms.openlocfilehash: 0dc43d4b9c16145ed7a5abe03cddb598c59b1e94
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374295"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits 구조체

공유 잠금 모드에서 `SRWLock` 클래스의 일반적인 특성을 설명합니다.

## <a name="syntax"></a>구문

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성   | Description
------ | --------------------------------------------------------------------------
`Type` | [SRWLOCK](srwlock-class.md) 클래스에 대한 포인터의 동의어입니다.

### <a name="public-methods"></a>Public 메서드

속성                                                     | Description
-------------------------------------------------------- | -----------------------------------------------------------------
[SRWLock공유 해협::GetInvalid값](#getinvalidvalue) | 항상 유효하지 않은 `SRWLockSharedTraits` 개체를 검색합니다.
[SRWLock공유 해협::잠금 해제](#unlock)                   | 지정된 개체의 단독 `SRWLock` 컨트롤을 해제합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`SRWLockSharedTraits`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼::핸들 트레이츠

## <a name="srwlocksharedtraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>SRWLock공유 해협::GetInvalid값

항상 유효하지 않은 `SRWLockSharedTraits` 개체를 검색합니다.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Return Value

개체에 대한 `SRWLockSharedTraits` 핸들입니다.

## <a name="srwlocksharedtraitsunlock"></a><a name="unlock"></a>SRWLock공유 해협::잠금 해제

지정된 개체의 단독 `SRWLock` 컨트롤을 해제합니다.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>매개 변수

*스워록*<br/>
개체에 대한 `SRWLock` 핸들입니다.
