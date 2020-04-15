---
title: CriticalSectionTraits 구조체
ms.date: 09/26/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock method
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
ms.openlocfilehash: 05c93bf6a2765bd11489075067c627ab3c3ab691
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372574"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits 구조체

잘못된 `CriticalSection` 임계 섹션 또는 임계 섹션을 해제하는 함수를 지원하는 개체를 전문화합니다.

## <a name="syntax"></a>구문

```
struct CriticalSectionTraits;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성   | Description
------ | -----------------------------------------------------------------------------------------------------------------
`Type` | 임계 `typedef` 섹션에 대한 포인터를 정의하는 A입니다. `Type`는 `typedef CRITICAL_SECTION* Type;`으로 정의됩니다.

### <a name="public-methods"></a>Public 메서드

속성                                                       | Description
---------------------------------------------------------- | -----------------
[임계 절인 특성::GetInvalid값](#getinvalidvalue) | 템플릿이 `CriticalSection` 항상 유효하지 않도록 템플릿을 전문화합니다.
[임계절기::잠금 해제](#unlock)                   | 지정된 `CriticalSection` 임계 섹션 개체의 소유권 해제를 지원하므로 템플릿을 전문화합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CriticalSectionTraits`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼::핸들 트레이츠

## <a name="criticalsectiontraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>임계 절인 특성::GetInvalid값

템플릿이 `CriticalSection` 항상 유효하지 않도록 템플릿을 전문화합니다.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Return Value

항상 잘못된 임계 섹션에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

`Type` 수정자는 로 `typedef CRITICAL_SECTION* Type;`정의됩니다.

## <a name="criticalsectiontraitsunlock"></a><a name="unlock"></a>임계절기::잠금 해제

지정된 `CriticalSection` 임계 섹션 개체의 소유권 해제를 지원하므로 템플릿을 전문화합니다.

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>매개 변수

*cs*<br/>
임계 섹션 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

`Type` 수정자는 로 `typedef CRITICAL_SECTION* Type;`정의됩니다.

자세한 내용은 Windows API 설명서의 **동기화 기능** 섹션에서 **LeaveCriticalSection 함수를** 참조하십시오.
