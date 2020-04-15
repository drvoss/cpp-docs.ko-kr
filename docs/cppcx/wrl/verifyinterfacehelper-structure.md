---
title: VerifyInterfaceHelper 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInterfaceHelper structure
- Microsoft::WRL::Details::VerifyInterfaceHelper::Verify method
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
ms.openlocfilehash: 09c2cc7e08e2dc0e8df42c64d285c37627c5925a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374240"
---
# <a name="verifyinterfacehelper-structure"></a>VerifyInterfaceHelper 구조체

Windows 런타임 C++ 템플릿 라이브러리 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <bool isWinRTInterface, typename I>
struct VerifyInterfaceHelper;

template <typename I>
struct VerifyInterfaceHelper<false, I>;
```

### <a name="parameters"></a>매개 변수

*Ⅰ*<br/>
확인할 인터페이스입니다.

*isWinRT인터페이스*

## <a name="remarks"></a>설명

템플릿 매개 변수에 의해 지정된 인터페이스가 특정 요구 사항을 충족하는지 확인합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

속성                                            | Description
----------------------------------------------- | ---------------------------------------------------------------------------------------------------
[VerifyInterfaceHelper::Verify 메서드](#verify) | 현재 템플릿 매개 변수에 의해 지정된 인터페이스가 특정 요구 사항을 충족하는지 확인합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`VerifyInterfaceHelper`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="verifyinterfacehelperverify"></a><a name="verify"></a>확인인터페이스도우미::확인

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
static void Verify();
```

### <a name="remarks"></a>설명

현재 템플릿 매개 변수에 의해 지정된 인터페이스가 특정 요구 사항을 충족하는지 확인합니다.
