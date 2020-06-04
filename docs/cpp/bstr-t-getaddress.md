---
title: _bstr_t::GetAddress
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
ms.openlocfilehash: ca78bd1b607ba4a86bbc824887a7ec767cd5476e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181254"
---
# <a name="_bstr_tgetaddress"></a>_bstr_t::GetAddress

**Microsoft 전용**

기존 문자열을 해제하고 새로 할당된 문자열의 주소를 반환합니다.

## <a name="syntax"></a>구문

```
BSTR* GetAddress( );
```

## <a name="return-value"></a>반환 값

`BSTR`로 래핑되는 `_bstr_t`에 대한 포인터입니다.

## <a name="remarks"></a>주의

**Getaddress** 는 `BSTR`를 공유 하는 모든 `_bstr_t` 개체에 영향을 줍니다. 두 개 이상의 `_bstr_t` 복사 생성자와 **operator =** 를 사용 하 여 `BSTR`를 공유할 수 있습니다.

## <a name="example"></a>예제

**Getaddress**를 사용 하는 예제는 [_Bstr_t:: Assign](../cpp/bstr-t-assign.md) 을 참조 하십시오.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_bstr_t 클래스](../cpp/bstr-t-class.md)
