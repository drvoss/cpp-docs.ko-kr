---
title: VerifyInheritanceHelper 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
ms.openlocfilehash: 3650cfb70ffc12572b3965534eff4e1f2ecb2cf5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374226"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename I, typename Base>
struct VerifyInheritanceHelper;

template <typename I>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>매개 변수

*Ⅰ*<br/>
형식입니다.

*기본*<br/>
다른 유형입니다.

## <a name="remarks"></a>설명

한 인터페이스가 다른 인터페이스에서 파생되는지 여부를 테스트합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

속성                                       | Description
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[상속 도우미 확인::확인](#verify) | 현재 템플릿 매개 변수에 의해 지정된 두 인터페이스를 테스트하고 한 인터페이스가 다른 인터페이스에서 파생되는지 여부를 결정합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`VerifyInheritanceHelper`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="verifyinheritancehelperverify"></a><a name="verify"></a>상속 도우미 확인::확인

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
static void Verify();
```

### <a name="remarks"></a>설명

현재 템플릿 매개 변수에 의해 지정된 두 인터페이스를 테스트하고 한 인터페이스가 다른 인터페이스에서 파생되는지 여부를 결정합니다.

한 인터페이스가 다른 인터페이스에서 파생되지 않으면 오류가 발생합니다.
