---
title: IsSame 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
- internal/Microsoft::WRL::Details::IsSame::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsSame structure
- Microsoft::WRL::Details::IsSame::value constant
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
ms.openlocfilehash: fcaf33309521b44163022e0ffa9b1e03e53e2551
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371338"
---
# <a name="issame-structure"></a>IsSame 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename T1, typename T2>
struct IsSame;

template <typename T1>
struct IsSame<T1, T1>;
```

### <a name="parameters"></a>매개 변수

*T1*<br/>
형식입니다.

*T2*<br/>
다른 유형입니다.

## <a name="remarks"></a>설명

지정된 형식이 지정된 다른 형식과 동일한지 여부를 테스트합니다.

## <a name="members"></a>멤버

### <a name="public-constants"></a>공용 상수

속성                    | Description
----------------------- | --------------------------------------------------
[IsSame::값](#value) | 한 형식이 다른 형식과 동일한지 여부를 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IsSame`

## <a name="requirements"></a>요구 사항

**헤더:** 내부.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="issamevalue"></a><a name="value"></a>IsSame::값

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
template <typename T1, typename T2>
struct IsSame
{
    static const bool value = false;
};

template <typename T1>
struct IsSame<T1, T1>
{
    static const bool value = true;
};
```

### <a name="remarks"></a>설명

한 형식이 다른 형식과 동일한지 여부를 나타냅니다.

`value`템플릿 매개 변수가 동일한 경우 **true이고** 템플릿 매개 변수가 다른 경우 **false입니다.**
