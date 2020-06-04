---
title: Mutex 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Mutex class
- Microsoft::WRL::Wrappers::Mutex::Lock method
- Microsoft::WRL::Wrappers::Mutex::Mutex, constructor
- Microsoft::WRL::Wrappers::Mutex::operator= operator
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
ms.openlocfilehash: 36466bd00c5b100f20ee87173e68fdef4131ec23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371231"
---
# <a name="mutex-class"></a>Mutex 클래스

공유 리소스를 단독으로 제어하는 동기화 개체를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class Mutex : public HandleT<HandleTraits::MutexTraits>;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성       | Description
---------- | ------------------------------------------------------
`SyncLock` | 동기 잠금을 지원하는 클래스의 동의어입니다.

### <a name="public-constructor"></a>공용 생성자

속성                   | Description
---------------------- | ------------------------------------------------
[뮤텍스::뮤텍스](#mutex) | `Mutex` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-members"></a>일반 인

속성                 | Description
-------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------
[뮤텍스::잠금](#lock) | 현재 개체 또는 지정된 핸들과 연결된 `Mutex` 개체가 뮤텍스를 해제하거나 지정된 시간 시간 간격이 경과할 때까지 기다립니다.

### <a name="public-operator"></a>공용 운영자

속성                                 | Description
------------------------------------ | ---------------------------------------------------------------------------
[뮤텍스::연산자=](#operator-assign) | 지정된 `Mutex` 객체를 현재 `Mutex` 객체에 할당(이동)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Mutex`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼

## <a name="mutexlock"></a><a name="lock"></a>뮤텍스::잠금

현재 개체 또는 지정된 핸들과 연결된 `Mutex` 개체가 뮤텍스를 해제하거나 지정된 시간 시간 간격이 경과할 때까지 기다립니다.

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
개체의 핸들입니다. `Mutex`

### <a name="return-value"></a>Return Value

## <a name="mutexmutex"></a><a name="mutex"></a>뮤텍스::뮤텍스

`Mutex` 클래스의 새 인스턴스를 초기화합니다.

```cpp
explicit Mutex(
   HANDLE h
);

Mutex(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
개체에 대한 핸들 또는 핸들에 대한 rvalue 참조입니다. `Mutex`

### <a name="remarks"></a>설명

첫 번째 생성자는 지정된 `Mutex` 핸들에서 개체를 초기화합니다. 두 번째 생성자는 지정된 `Mutex` 핸들에서 개체를 초기화한 다음 뮤텍스의 `Mutex` 소유권을 현재 개체로 이동합니다.

## <a name="mutexoperator"></a><a name="operator-assign"></a>뮤텍스::연산자=

지정된 `Mutex` 객체를 현재 `Mutex` 객체에 할당(이동)합니다.

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
개체에 대한 rvalue `Mutex` 참조입니다.

### <a name="return-value"></a>Return Value

현재 `Mutex` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

자세한 내용은 [Rvalue 참조 선언자: &&](../../cpp/rvalue-reference-declarator-amp-amp.md)의 **의미 체계 이동** 섹션을 참조하십시오.
