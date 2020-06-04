---
title: _variant_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator=
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
ms.openlocfilehash: 402251592a87b723d75fd1b2cd0786be7b17dbfc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187624"
---
# <a name="_variant_toperator-"></a>_variant_t::operator =

**Microsoft 전용**

## <a name="syntax"></a>구문

```
_variant_t& operator=(
   const VARIANT& varSrc
);

_variant_t& operator=(
   const VARIANT* pVarSrc
);

_variant_t& operator=(
   const _variant_t& var_t_Src
);

_variant_t& operator=(
   short sSrc
);

_variant_t& operator=(
   long lSrc
);

_variant_t& operator=(
   float fltSrc
);

_variant_t& operator=(
   double dblSrc
);

_variant_t& operator=(
   const CY& cySrc
);

_variant_t& operator=(
   const _bstr_t& bstrSrc
);

_variant_t& operator=(
   const wchar_t* wstrSrc
);

_variant_t& operator=(
   const char* strSrc
);

_variant_t& operator=(
   IDispatch* pDispSrc
);

_variant_t& operator=(
   bool bSrc
);

_variant_t& operator=(
   IUnknown* pSrc
);

_variant_t& operator=(
   const DECIMAL& decSrc
);

_variant_t& operator=(
   BYTE bSrc
);

_variant_t& operator=(
   char cSrc
);

_variant_t& operator=(
   unsigned short usSrc
);

_variant_t& operator=(
   unsigned long ulSrc
);

_variant_t& operator=(
   int iSrc
);

_variant_t& operator=(
   unsigned int uiSrc
);

_variant_t& operator=(
   __int64 i8Src
);

_variant_t& operator=(
   unsigned __int64 ui8Src
);
```

## <a name="remarks"></a>설명

다음 연산자는 `_variant_t` 개체에 새 값을 할당합니다.

- **operator = (** *varsrc* **)** `_variant_t` 개체에 기존 `VARIANT`을 할당 합니다.

- **operator = (** *pvarsrc* **)** `_variant_t` 개체에 기존 `VARIANT`을 할당 합니다.

- **연산자 = (** *var_t_Src* **)** `_variant_t` 개체에 기존 `_variant_t` 개체를 할당 합니다.

- **연산자 = (** *sSrc* **)** `_variant_t` 개체에 **short** 정수 값을 할당 합니다.

- **연산자 = (** `lSrc` **)** `_variant_t` 개체에 정수 ( **long** ) 값을 할당 합니다.

- **연산자 = (**  *fltSrc*  **)** **부동 소수점** 숫자 값을 `_variant_t` 개체에 할당 합니다.

- **연산자 = (** *dblSrc* **)** `_variant_t` 개체에 **double** 숫자 값을 할당 합니다.

- **operator = (** *cysrc* **)** `_variant_t` 개체에 `CY` 개체를 할당 합니다.

- **연산자 = (** *bstrSrc* **)** `_variant_t` 개체에 `BSTR` 개체를 할당 합니다.

- **연산자 = (**  *wstrSrc*  **)** `_variant_t` 개체에 유니코드 문자열을 할당 합니다.

- **연산자 = (** `strSrc` **)** `_variant_t` 개체에 멀티 바이트 문자열을 할당 합니다.

- **연산자 = (** `bSrc` **)** `_variant_t` 개체에 **부울** 값을 할당 합니다.

- **연산자 = (** *pDispSrc* **)** `_variant_t` 개체에 `VT_DISPATCH` 개체를 할당 합니다.

- **연산자 = (** *pIUnknownSrc* **)** `_variant_t` 개체에 `VT_UNKNOWN` 개체를 할당 합니다.

- **operator = (** *src* **)** `_variant_t` 개체에 `DECIMAL` 값을 할당 합니다.

- **연산자 = (** `bSrc` **)** `_variant_t` 개체에 `BYTE` 값을 할당 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_variant_t 클래스](../cpp/variant-t-class.md)
