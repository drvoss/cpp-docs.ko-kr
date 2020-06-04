---
title: _bstr_t::GetBSTR
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
ms.openlocfilehash: da438c65256d9a7e5bf5b02e108fee1385171d2d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181215"
---
# <a name="_bstr_tgetbstr"></a>_bstr_t::GetBSTR

**Microsoft 전용**

`BSTR`에 의해 래핑되는 `_bstr_t`의 시작 부분을 가리킵니다.

## <a name="syntax"></a>구문

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>반환 값

`BSTR`에 의해 래핑되는 `_bstr_t`의 시작 부분입니다.

## <a name="remarks"></a>주의

**Getbstr** 은 `BSTR`을 공유 하는 모든 `_bstr_t` 개체에 영향을 줍니다. 두 개 이상의 `_bstr_t` 복사 생성자와 **operator =** 를 사용 하 여 `BSTR`를 공유할 수 있습니다.

## <a name="example"></a>예제

**Getbstr**를 사용 하는 예제는 [_Bstr_t:: Assign](../cpp/bstr-t-assign.md) 을 참조 하십시오.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_bstr_t 클래스](../cpp/bstr-t-class.md)
