---
title: _variant_t::_variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t::_variant_t
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
ms.openlocfilehash: fff116ef04967a1887eaa075d92d3ea0283d5427
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187533"
---
# <a name="_variant_t_variant_t"></a>_variant_t::_variant_t

**Microsoft 전용**

`_variant_t` 개체를 생성합니다.

## <a name="syntax"></a>구문

```
_variant_t( ) throw( );

_variant_t(
   const VARIANT& varSrc
);

_variant_t(
   const VARIANT* pVarSrc
);

_variant_t(
   const _variant_t& var_t_Src
);

_variant_t(
   VARIANT& varSrc,
   bool fCopy
);

_variant_t(
   short sSrc,
   VARTYPE vtSrc = VT_I2
);

_variant_t(
   long lSrc,
   VARTYPE vtSrc = VT_I4
);

_variant_t(
   float fltSrc
) throw( );

_variant_t(
   double dblSrc,
   VARTYPE vtSrc = VT_R8
);

_variant_t(
   const CY& cySrc
) throw( );

_variant_t(
   const _bstr_t& bstrSrc
);

_variant_t(
   const wchar_t *wstrSrc
);

_variant_t(
   const char* strSrc
);

_variant_t(
   IDispatch* pDispSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   bool bSrc
) throw( );

_variant_t(
   IUnknown* pIUknownSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   const DECIMAL& decSrc
) throw( );

_variant_t(
   BYTE bSrc
) throw( );

variant_t(
   char cSrc
) throw();

_variant_t(
   unsigned short usSrc
) throw();

_variant_t(
   unsigned long ulSrc
) throw();

_variant_t(
   int iSrc
) throw();

_variant_t(
   unsigned int uiSrc
) throw();

_variant_t(
   __int64 i8Src
) throw();

_variant_t(
   unsigned __int64 ui8Src
) throw();
```

#### <a name="parameters"></a>매개 변수

*varSrc*<br/>
새 `VARIANT` 개체로 복사할 `_variant_t` 개체입니다.

*pVarSrc*<br/>
새 `_variant_t` 개체로 복사할 `VARIANT` 개체에 대 한 포인터입니다.

*var_t_Src*<br/>
새 `_variant_t` 개체로 복사할 `_variant_t` 개체입니다.

*fCopy*<br/>
**False**이면 제공 된 `VARIANT` 개체가 `VariantCopy`으로 새 복사본을 만들지 않고 새 `_variant_t` 개체에 연결 됩니다.

*ISrc, sSrc*<br/>
새 `_variant_t` 개체로 복사할 정수 값입니다.

*vtSrc*<br/>
새 `_variant_t` 개체의 `VARTYPE`입니다.

*fltSrc, dblSrc*<br/>
새 `_variant_t` 개체에 복사될 숫자 값입니다.

*cySrc*<br/>
새 `CY` 개체로 복사할 `_variant_t` 개체입니다.

*bstrSrc*<br/>
새 `_bstr_t` 개체로 복사할 `_variant_t` 개체입니다.

*strSrc, wstrSrc*<br/>
새 `_variant_t` 개체로 복사할 문자열입니다.

*bSrc*<br/>
새 `_variant_t` 개체로 복사 될 **부울** 값입니다.

*pIUknownSrc*<br/>
새 `_variant_t` 개체에 캡슐화 될 VT_UNKNOWN 개체에 대 한 COM 인터페이스 포인터입니다.

*pDispSrc*<br/>
새 `_variant_t` 개체에 캡슐화 될 VT_DISPATCH 개체에 대 한 COM 인터페이스 포인터입니다.

*원본 없음*<br/>
새 `DECIMAL` 개체로 복사할 `_variant_t` 값입니다.

*bSrc*<br/>
새 `BYTE` 개체로 복사할 `_variant_t` 값입니다.

*cSrc*<br/>
새 `_variant_t` 개체로 복사할 **문자** 값입니다.

*usSrc*<br/>
새 `_variant_t` 개체로 복사할 **부호 없는 short** 값입니다.

*ulSrc*<br/>
새 `_variant_t` 개체로 복사할 **부호 없는 long** 값입니다.

*iSrc*<br/>
새 `_variant_t` 개체로 복사할 **정수** 값입니다.

*uiSrc*<br/>
새 `_variant_t` 개체로 복사할 **부호 없는 정수** 값입니다.

*i8Src*<br/>
새 `_variant_t` 개체에 복사할 **__int64** 값입니다.

*ui8Src*<br/>
새 `_variant_t` 개체에 복사할 **부호 없는 __int64** 값입니다.

## <a name="remarks"></a>설명

- **_variant_t ()** `VT_EMPTY`빈 `_variant_t` 개체를 생성 합니다.

- **_variant_t (variant &** *varsrc* **)** `VARIANT` 개체의 복사본에서 `_variant_t` 개체를 생성 합니다. 변형 형식이 유지됩니다.

- **_variant_t (variant** <strong>\*</strong> *pvarsrc* **)** `VARIANT` 개체의 복사본에서 `_variant_t` 개체를 생성 합니다. 변형 형식이 유지됩니다.

- **_variant_t (_variant_t &** *var_t_Src* **)** 다른 `_variant_t` 개체에서 `_variant_t` 개체를 생성 합니다. 변형 형식이 유지됩니다.

- **_variant_t (variant &** *varsrc* **, bool**`fCopy` **)** 기존 `VARIANT` 개체에서 `_variant_t` 개체를 생성 합니다. *Fcopy* 가 **False**인 경우 **VARIANT** 개체는 복사를 만들지 않고 새 개체에 연결 됩니다.

- **_variant_t (short***sSrc* **, VARTYPE**`vtSrc` **= VT_I2)** VT_I2 형식의 `_variant_t` 개체 또는 **short** 정수 값에서 VT_BOOL를 생성 합니다. 다른 `VARTYPE` E_INVALIDARG 오류가 발생 합니다.

- **_variant_t (long**`lSrc` **, VARTYPE**`vtSrc` **= VT_I4)** 정수 ( **long** ) 값에서 VT_I4, VT_BOOL 또는 VT_ERROR 형식의 `_variant_t` 개체를 생성 합니다. 다른 `VARTYPE` E_INVALIDARG 오류가 발생 합니다.

- **_variant_t (float**`fltSrc` **)** **Float** 숫자 값에서 VT_R4 형식의 `_variant_t` 개체를 생성 합니다.

- **_variant_t (이중**`dblSrc` **, VARTYPE**`vtSrc` **= VT_R8)** **Double** 숫자 값에서 VT_R8 또는 VT_DATE 형식의 `_variant_t` 개체를 생성 합니다. 다른 `VARTYPE` E_INVALIDARG 오류가 발생 합니다.

- **_variant_t (CY &** `cySrc` **)** `CY` 개체에서 VT_CY 형식의 `_variant_t` 개체를 생성 합니다.

- **_variant_t (_bstr_t &** `bstrSrc` **)** `_bstr_t` 개체에서 VT_BSTR 형식의 `_variant_t` 개체를 생성 합니다. 새 `BSTR`이 할당됩니다.

- **_variant_t (wchar_t** <strong>\*</strong> *wstrSrc*  **)** 유니코드 문자열에서 VT_BSTR 형식의 `_variant_t` 개체를 생성 합니다. 새 `BSTR`이 할당됩니다.

- **_variant_t (char** <strong>\*</strong>`strSrc` **)** 문자열에서 VT_BSTR 형식의 `_variant_t` 개체를 생성 합니다. 새 `BSTR`이 할당됩니다.

- **_variant_t (bool**`bSrc` **)** **BOOL** 값에서 VT_BOOL 형식의 `_variant_t` 개체를 생성 합니다.

- **_variant_t (IUnknown** <strong>\*</strong>`pIUknownSrc` **, bool**`fAddRef` **= true)** COM 인터페이스 포인터에서 VT_UNKNOWN 형식의 `_variant_t` 개체를 생성 합니다. `fAddRef` **true**이면 제공 된 인터페이스 포인터에서 `AddRef`를 호출 하 여 `_variant_t` 개체가 제거 될 때 발생 하는 `Release`에 대 한 호출과 일치 시킵니다. 제공 된 인터페이스 포인터에 대 한 `Release`를 호출 하는 것은 사용자에 게 있습니다. `fAddRef` **false**이면이 생성자는 제공 된 인터페이스 포인터의 소유권을 갖습니다. 제공 된 인터페이스 포인터에서 `Release`를 호출 하지 마세요.

- **_variant_t (IDispatch** <strong>\*</strong>`pDispSrc` **, bool**`fAddRef` **= true)** COM 인터페이스 포인터에서 VT_DISPATCH 형식의 `_variant_t` 개체를 생성 합니다. `fAddRef` **true**이면 제공 된 인터페이스 포인터에서 `AddRef`를 호출 하 여 `_variant_t` 개체가 제거 될 때 발생 하는 `Release`에 대 한 호출과 일치 시킵니다. 제공 된 인터페이스 포인터에 대 한 `Release`를 호출 하는 것은 사용자에 게 있습니다. `fAddRef` **false**이면이 생성자는 제공 된 인터페이스 포인터의 소유권을 갖습니다. 제공 된 인터페이스 포인터에서 `Release`를 호출 하지 마세요.

- **_variant_t (10 진수 &** `decSrc` **)** `DECIMAL` 값에서 VT_DECIMAL 형식의 `_variant_t` 개체를 생성 합니다.

- **_variant_t (바이트**`bSrc` **)** `BYTE` 값에서 `VT_UI1` 형식의 `_variant_t` 개체를 생성 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_variant_t 클래스](../cpp/variant-t-class.md)
