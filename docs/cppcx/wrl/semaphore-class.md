---
title: Semaphore 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Semaphore class
- Microsoft::WRL::Wrappers::Semaphore::Lock method
- Microsoft::WRL::Wrappers::Semaphore::operator= operator
- Microsoft::WRL::Wrappers::Semaphore::Semaphore, constructor
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
ms.openlocfilehash: e017b1b6316c4b6d49563d9a543950ab28961d90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359353"
---
# <a name="semaphore-class"></a>Semaphore 클래스

제한된 사용자 수를 지원할 수 있는 공유 리소스를 제어하는 동기화 개체를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성       | Description
---------- | ------------------------------------------------------
`SyncLock` | 동기 잠금을 지원하는 클래스의 동의어입니다.

### <a name="public-constructors"></a>Public 생성자

속성                               | Description
---------------------------------- | ----------------------------------------------------
[세마포어::세마포어](#semaphore) | `Semaphore` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                     | Description
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[세마포어::잠금](#lock) | 현재 개체 또는 지정된 핸들과 연결된 개체가 신호 상태에 있거나 지정된 시간 시간 간격이 경과할 때까지 기다립니다.

### <a name="public-operators"></a>Public 연산자

속성                                     | Description
---------------------------------------- | ---------------------------------------------------------------------------------------
[세마포어::연산자=](#operator-assign) | 지정된 핸들을 `Semaphore` 개체에서 현재 `Semaphore` 개체로 이동합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Semaphore`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼

## <a name="semaphorelock"></a><a name="lock"></a>세마포어::잠금

현재 개체 또는 지정된 핸들과 연결된 `Semaphore` 개체가 신호 상태에 있거나 지정된 시간 시간 간격이 경과할 때까지 기다립니다.

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>매개 변수

*밀리초*<br/>
제한 시간 간격(밀리초)입니다. 기본값은 INFINITE으로, 무제한 대기합니다.

*H*<br/>
개체에 대한 `Semaphore` 핸들입니다.

### <a name="return-value"></a>Return Value

`Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`

## <a name="semaphoreoperator"></a><a name="operator-assign"></a>세마포어::연산자=

지정된 핸들을 `Semaphore` 개체에서 현재 `Semaphore` 개체로 이동합니다.

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
개체에 대한 Rvalue 참조입니다. `Semaphore`

### <a name="return-value"></a>Return Value

현재 `Semaphore` 개체에 대한 참조입니다.

## <a name="semaphoresemaphore"></a><a name="semaphore"></a>세마포어::세마포어

`Semaphore` 클래스의 새 인스턴스를 초기화합니다.

```cpp
explicit Semaphore(
   HANDLE h
);

WRL_NOTHROW Semaphore(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
개체에 대한 핸들 또는 rvalue 참조입니다. `Semaphore`
