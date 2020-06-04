---
title: _variant_t Extractors
ms.date: 11/04/2016
f1_keywords:
- _variant_t.operatordouble
- operatorlong
- _variant_t::operator_bstr_t
- operatordouble
- _variant_t.operatorCY
- operatorCY
- _variant_t::operatorCY
- _variant_t::operatordouble
- operatorfloat
- operatorBYTE
- _variant_t.operatorDECIMAL
- _variant_t::operatorlong
- operatorIDispatch
- _variant_t.operatorBYTE
- operatorDECIMAL
- _variant_t.operator_bstr_t
- _variant_t::operatorDECIMAL
- _variant_t.operatorIUnknown
- _variant_t.operatorlong
- _variant_t::operatorIDispatch
- _variant_t::operatorIUnknown
- operatorIUnknown
- _variant_t.operatorbool
- _variant_t::operatorBYTE
- _variant_t.operatorfloat
- operator_bstr_t
- _variant_t::operatorbool
- operatorshort
- _variant_t::operatorshort
- _variant_t::operatorfloat
- _variant_t.operatorIDispatch
- _variant_t.operatorshort
helpviewer_keywords:
- extractors, _variant_t class
- operator CY
- operator IDispatch
- operator SHORT
- operator double
- operator long
- operator _bstr_t
- operator DECIMAL
- operator float
- operator bool
- operator BYTE
- operator IUnknown
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
ms.openlocfilehash: 685df7285e58e0cf2ceeded5ac27641364897298
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187702"
---
# <a name="_variant_t-extractors"></a>_variant_t Extractors

**Microsoft 전용**

캡슐화 된 `VARIANT` 개체에서 데이터를 추출 합니다.

## <a name="syntax"></a>구문

```
operator short( ) const;
operator long( ) const;
operator float( ) const;
operator double( ) const;
operator CY( ) const;
operator _bstr_t( ) const;
operator IDispatch*( ) const;
operator bool( ) const;
operator IUnknown*( ) const;
operator DECIMAL( ) const;
operator BYTE( ) const;
operator VARIANT() const throw();
operator char() const;
operator unsigned short() const;
operator unsigned long() const;
operator int() const;
operator unsigned int() const;
operator __int64() const;
operator unsigned __int64() const;
```

## <a name="remarks"></a>설명

캡슐화 된 `VARIANT`에서 원시 데이터를 추출 합니다. `VARIANT` 올바른 형식이 아니면 변환을 시도 하는 데 `VariantChangeType` 사용 되며 오류가 발생 하면 오류가 생성 됩니다.

- **연산자 short ()** **Short** 정수 값을 추출 합니다.

- **연산자 long ()** 정수 ( **long** ) 값을 추출 합니다.

- **operator float ()** **부동 소수점** 숫자 값을 추출 합니다.

- **operator double ()** **Double** 정수 값을 추출 합니다.

- **연산자 CY ()** `CY` 개체를 추출 합니다.

- **연산자 bool ()** **부울** 값을 추출 합니다.

- **연산자 DECIMAL ()** `DECIMAL` 값을 추출 합니다.

- **연산자 BYTE ()** `BYTE` 값을 추출 합니다.

- **연산자 _bstr_t ()** `_bstr_t` 개체에 캡슐화 되는 문자열을 추출 합니다.

- **Operator IDispatch\*()** 캡슐화 된 `VARIANT`에서가 나 포인터를 추출 합니다. 결과 포인터에서 `AddRef`가 호출 되므로 `Release`를 호출 하 여 해제할 수 있습니다.

- **Operator IUnknown\*()** 캡슐화 된 `VARIANT`에서 COM 인터페이스 포인터를 추출 합니다. 결과 포인터에서 `AddRef`가 호출 되므로 `Release`를 호출 하 여 해제할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_variant_t 클래스](../cpp/variant-t-class.md)
