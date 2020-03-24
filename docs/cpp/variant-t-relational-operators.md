---
title: _variant_t 관계형 연산자
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
ms.openlocfilehash: e0d7ea1a0bcaf8329cff0cdfb0c01154f3c5a73b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187572"
---
# <a name="_variant_t-relational-operators"></a>_variant_t 관계형 연산자

**Microsoft 전용**

두 `_variant_t` 개체가 같음 또는 같지 않음을 비교합니다.

## <a name="syntax"></a>구문

```
bool operator==(
   const VARIANT& varSrc) const;
bool operator==(
   const VARIANT* pSrc) const;
bool operator!=(
   const VARIANT& varSrc) const;
bool operator!=(
   const VARIANT* pSrc) const;
```

#### <a name="parameters"></a>매개 변수

*varSrc*<br/>
`_variant_t` 개체와 비교할 `VARIANT`입니다.

*.Psrc*<br/>
`_variant_t` 개체와 비교할 `VARIANT`에 대 한 포인터입니다.

## <a name="return-value"></a>Return Value

비교가 포함 되 면 **true** 를 반환 하 고 그렇지 않으면 **false** 를 반환 합니다.

## <a name="remarks"></a>설명

`_variant_t` 개체를 `VARIANT`와 비교 하 여 같음 또는 같지 않은지 테스트 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_variant_t 클래스](../cpp/variant-t-class.md)
