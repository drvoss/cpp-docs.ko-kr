---
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: 1fe8cfb5b644b3c7c34cf3325a91ebdf23a04946
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190328"
---
# <a name="_bstr_tcopy"></a>_bstr_t::copy

**Microsoft 전용**

캡슐화된 `BSTR`의 복사본을 구성합니다.

## <a name="syntax"></a>구문

```
BSTR copy( bool fCopy = true ) const;
```

#### <a name="parameters"></a>매개 변수

*fCopy*<br/>
TRUE 이면 **복사** 시 포함 된 `BSTR`의 복사본이 반환 되 고, **그렇지 않으면 복사는** 실제 BSTR을 반환 합니다.

## <a name="remarks"></a>주의

캡슐화된 `BSTR` 개체에 새로 할당된 복사본을 반환합니다.

## <a name="example"></a>예제

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_bstr_t 클래스](../cpp/bstr-t-class.md)
