---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: 0cd300a09c29668c496d93109d1bc862947e948c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187559"
---
# <a name="_variant_tsetstring"></a>_variant_t::SetString

**Microsoft 전용**

이 `_variant_t` 개체에 문자열을 할당합니다.

## <a name="syntax"></a>구문

```
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>매개 변수

*.Psrc*<br/>
문자열에 대한 포인터입니다.

## <a name="remarks"></a>설명

ANSI 문자열을 유니코드 `BSTR` 문자열로 변환하고 이 `_variant_t` 개체에 할당합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_variant_t 클래스](../cpp/variant-t-class.md)
