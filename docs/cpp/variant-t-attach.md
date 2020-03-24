---
title: _variant_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
ms.openlocfilehash: 3792ed4d0fcd86c4a4e846771c450413fda130b5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187767"
---
# <a name="_variant_tattach"></a>_variant_t::Attach

**Microsoft 전용**

**_Variant_t** 개체에 `VARIANT` 개체를 연결 합니다.

## <a name="syntax"></a>구문

```
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>매개 변수

*varSrc*<br/>
이 **_variant_t** 개체에 연결할 `VARIANT` 개체입니다.

## <a name="remarks"></a>설명

`VARIANT`를 캡슐화 하 여 소유권을 가져옵니다. 이 멤버 함수는 기존의 캡슐화 된 `VARIANT`를 해제 한 다음 제공 된 `VARIANT`를 복사 하 고 해당 `VARTYPE`를 VT_EMPTY로 설정 하 여 **_variant_t** 소멸자만 해당 리소스를 해제할 수 있도록 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_variant_t 클래스](../cpp/variant-t-class.md)
