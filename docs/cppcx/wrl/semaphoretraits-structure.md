---
title: SemaphoreTraits 구조체
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock method
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
ms.openlocfilehash: 11719576c9fc7b23f4cd318ee1b3ed9ca3f5edaa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360734"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits 구조체

개체의 공통 특성을 정의합니다. `Semaphore`

## <a name="syntax"></a>구문

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

속성                               | Description
---------------------------------- | --------------------------------------
[세마포어해협::잠금 해제](#unlock) | 공유 리소스의 컨트롤을 해제합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼::핸들 트레이츠

## <a name="semaphoretraitsunlock"></a><a name="unlock"></a>세마포어해협::잠금 해제

공유 리소스의 컨트롤을 해제합니다.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
개체에 `Semaphore` 핸들을 보입니다.

### <a name="remarks"></a>설명

잠금 해제 작업이 실패하면 오류의 원인을 나타내는 오류가 `Unlock()` 발생합니다.
