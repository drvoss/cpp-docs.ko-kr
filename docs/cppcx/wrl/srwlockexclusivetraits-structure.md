---
title: SRWLockExclusiveTraits 구조체
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock method
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
ms.openlocfilehash: eb7b30915d6061e8470601df33fecec310d1bbca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374302"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits 구조체

전용 잠금 모드에서 `SRWLock` 클래스의 일반적인 특성을 설명합니다.

## <a name="syntax"></a>구문

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성   | Description
------ | --------------------------------------------------------------------------
`Type` | [SRWLOCK](srwlock-class.md) 클래스에 대한 포인터의 동의어입니다.

### <a name="public-methods"></a>Public 메서드

속성                                                        | Description
----------------------------------------------------------- | --------------------------------------------------------------------
[SRWLock 배타적 특성::GetInvalid값](#getinvalidvalue) | 항상 유효하지 않은 `SRWLockExclusiveTraits` 개체를 검색합니다.
[SRWLock 배타적 인 해협 :: 잠금 해제](#unlock)                   | 지정된 개체의 단독 `SRWLock` 컨트롤을 해제합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`SRWLockExclusiveTraits`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼::핸들 트레이츠

## <a name="srwlockexclusivetraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>SRWLock 배타적 특성::GetInvalid값

항상 유효하지 않은 `SRWLockExclusiveTraits` 개체를 검색합니다.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Return Value

빈 `SRWLockExclusiveTraits` 개체입니다.

## <a name="srwlockexclusivetraitsunlock"></a><a name="unlock"></a>SRWLock 배타적 인 해협 :: 잠금 해제

지정된 개체의 단독 `SRWLock` 컨트롤을 해제합니다.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>매개 변수

*스워록*<br/>
개체에 `SRWLock` 핸들을 보입니다.
