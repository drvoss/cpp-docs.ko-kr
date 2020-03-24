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
ms.openlocfilehash: b0692c9befaa6b7e787ada624dcbb56b074c9f9d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160465"
---
# <a name="_variant_tchangetype"></a>_variant_t::ChangeType

**Microsoft 전용**

`_variant_t` 개체의 형식을 지정 된 `VARTYPE`로 변경 합니다.

## <a name="syntax"></a>구문

```
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>매개 변수

*vartype*<br/>
이 `_variant_t` 개체에 대 한 `VARTYPE`입니다.

*.Psrc*<br/>
변환할 `_variant_t` 개체의 포인터입니다. 이 값이 NULL 이면 변환이 대신 수행 됩니다.

## <a name="remarks"></a>설명

이 멤버 함수는 `_variant_t` 개체를 표시 된 `VARTYPE`변환 합니다. *Psrc* 가 NULL 인 경우 변환이 수행 됩니다. 그렇지 않으면이 `_variant_t` 개체가 *psrc* 에서 복사 된 후 변환 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_variant_t 클래스](../cpp/variant-t-class.md)
