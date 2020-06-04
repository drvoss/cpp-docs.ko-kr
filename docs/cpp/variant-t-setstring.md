---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: 60ad1c1bd95eb35f2a4f2800f79d0326c68a1176
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745855"
---
# <a name="_variant_tsetstring"></a>_variant_t::SetString

**마이크로소프트 특정**

이 `_variant_t` 개체에 문자열을 할당합니다.

## <a name="syntax"></a>구문

```cpp
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>매개 변수

*pSrc*<br/>
문자열에 대한 포인터입니다.

## <a name="remarks"></a>설명

ANSI 문자열을 유니코드 `BSTR` 문자열로 변환하고 이 `_variant_t` 개체에 할당합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[_variant_t 클래스](../cpp/variant-t-class.md)
