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
ms.openlocfilehash: 8c209d5a8d2a35f2643e90e5595d86f41519f30b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216559"
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
다른 형식입니다.

## <a name="remarks"></a>설명

지정 된 형식이 다른 지정 된 형식과 동일한 지 테스트 합니다.

## <a name="members"></a>멤버

### <a name="public-constants"></a>공용 상수

Name                    | 설명
----------------------- | --------------------------------------------------
[IsSame:: value](#value) | 한 형식이 다른 형식 인지 여부를 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IsSame`

## <a name="requirements"></a>요구 사항

**헤더:** internal. h

**네임 스페이스:** Microsoft:: WRL::D etails

## <a name="issamevalue"></a><a name="value"></a>IsSame:: value

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

한 형식이 다른 형식 인지 여부를 나타냅니다.

`value`**`true`** 템플릿 매개 변수가 동일한 경우이 고, **`false`** 템플릿 매개 변수가 다른 경우입니다.
