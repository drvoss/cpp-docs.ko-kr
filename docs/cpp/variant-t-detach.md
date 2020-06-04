---
title: _variant_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
ms.openlocfilehash: 9737db6b77483fa55e1dad90b9464752cd8537a5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187741"
---
# <a name="_variant_tdetach"></a>_variant_t::Detach

**Microsoft 전용**

이 `_variant_t` 개체에서 캡슐화 된 `VARIANT` 개체를 분리 합니다.

## <a name="syntax"></a>구문

```
VARIANT Detach( );
```

## <a name="return-value"></a>Return Value

캡슐화 된 `VARIANT`입니다.

## <a name="remarks"></a>설명

캡슐화 된 `VARIANT`를 추출 하 여 반환한 다음이 `_variant_t` 개체를 삭제 하지 않고 지웁니다. 이 멤버 함수는 캡슐화에서 `VARIANT`를 제거 하 고이 `_variant_t` 개체의 `VARTYPE`를 VT_EMPTY로 설정 합니다. [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) 함수를 호출 하 여 반환 된 `VARIANT`를 해제 하는 것이 좋습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_variant_t 클래스](../cpp/variant-t-class.md)
