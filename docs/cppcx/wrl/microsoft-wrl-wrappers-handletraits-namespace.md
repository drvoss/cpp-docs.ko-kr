---
title: Microsoft::WRL::Wrappers::HandleTraits 네임스페이스
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: b19cc426fc7c1b4fc6ec0638730d59998f8c108a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213735"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits 네임스페이스

일반적인 핸들 기반 리소스 형식의 특성을 설명 합니다.

## <a name="syntax"></a>구문

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>멤버

### <a name="structures"></a>구조

|이름|설명|
|----------|-----------------|
|[CriticalSectionTraits 구조체](criticalsectiontraits-structure.md)|중요 한 섹션을 해제 하기 위해 잘못 된 임계 영역 또는 함수를 지원 하도록 `CriticalSection` 개체를 특수화 합니다.|
|[EventTraits 구조체](eventtraits-structure.md)|`Event` 클래스 핸들의 특징을 정의 합니다.|
|[FileHandleTraits 구조체](filehandletraits-structure.md)|파일 핸들의 특징을 정의 합니다.|
|[HANDLENullTraits 구조체](handlenulltraits-structure.md)|초기화 되지 않은 핸들의 공통 특성을 정의 합니다.|
|[HANDLETraits 구조체](handletraits-structure.md)|핸들의 공통 특성을 정의 합니다.|
|[MutexTraits 구조체](mutextraits-structure.md)|[뮤텍스](mutex-class.md) 클래스의 공통 특성을 정의 합니다.|
|[SemaphoreTraits 구조체](semaphoretraits-structure.md)|세마포 개체의 공통 특성을 정의 합니다.|
|[SRWLockExclusiveTraits 구조체](srwlockexclusivetraits-structure.md)|배타적 잠금 모드에서 `SRWLock` 클래스의 공통 특성에 대해 설명 합니다.|
|[SRWLockSharedTraits 구조체](srwlocksharedtraits-structure.md)|공유 잠금 모드의 `SRWLock` 클래스의 공통 특성에 대해 설명 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임 스페이스:** Microsoft:: WRL:: 래퍼

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Wrappers 네임스페이스](microsoft-wrl-wrappers-namespace.md)
