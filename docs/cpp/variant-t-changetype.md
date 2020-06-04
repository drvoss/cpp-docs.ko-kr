---
title: _variant_t::ChangeType
ms.date: 11/04/2016
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
ms.openlocfilehash: c2283158856a6781ab2e12c51f4e2ad0e4f1d531
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750722"
---
# <a name="_variant_tchangetype"></a>_variant_t::ChangeType

**마이크로소프트 특정**

`_variant_t` 개체의 유형을 표시된 `VARTYPE`으로 변경합니다.

## <a name="syntax"></a>구문

```cpp
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>매개 변수

*Vartype*<br/>
이 `VARTYPE` `_variant_t` 개체에 대한 입니다.

*pSrc*<br/>
변환할 `_variant_t` 개체의 포인터입니다. 이 값이 NULL이면 변환이 수행됩니다.

## <a name="remarks"></a>설명

이 멤버 함수는 `_variant_t` 개체를 `VARTYPE`표시된 으로 변환합니다. *pSrc가* NULL이면 변환이 수행되고 그렇지 `_variant_t` 않으면 이 개체가 *pSrc에서* 복사된 다음 변환됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[_variant_t 클래스](../cpp/variant-t-class.md)
