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
ms.openlocfilehash: d0822dfc730cbbb64f8364e6fa8fe8bc7207f9f9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750735"
---
# <a name="_variant_tattach"></a>_variant_t::Attach

**마이크로소프트 특정**

개체를 `VARIANT` **_variant_t** 개체에 연결합니다.

## <a name="syntax"></a>구문

```cpp
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>매개 변수

*varSrc*<br/>
이 `VARIANT` **_variant_t** 개체에 연결할 개체입니다.

## <a name="remarks"></a>설명

캡슐화하여 `VARIANT` 소유권을 받습니다. 이 `VARIANT`멤버 함수는 캡슐화된 기존 모든 캡슐을 `VARIANT`해제한 `VARTYPE` 다음 제공된 VT_EMPTY 복사하여 해당 리소스가 **_variant_t** 소멸자에서만 해제될 수 있도록 설정합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[_variant_t 클래스](../cpp/variant-t-class.md)
