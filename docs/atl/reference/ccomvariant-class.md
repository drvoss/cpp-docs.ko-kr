---
title: CComVariant 클래스
ms.date: 11/04/2016
f1_keywords:
- CComVariant
- ATLCOMCLI/ATL::CComVariant
- ATLCOMCLI/ATL::CComVariant::CComVariant
- ATLCOMCLI/ATL::CComVariant::Attach
- ATLCOMCLI/ATL::CComVariant::ChangeType
- ATLCOMCLI/ATL::CComVariant::Clear
- ATLCOMCLI/ATL::CComVariant::Copy
- ATLCOMCLI/ATL::CComVariant::CopyTo
- ATLCOMCLI/ATL::CComVariant::Detach
- ATLCOMCLI/ATL::CComVariant::GetSize
- ATLCOMCLI/ATL::CComVariant::ReadFromStream
- ATLCOMCLI/ATL::CComVariant::SetByRef
- ATLCOMCLI/ATL::CComVariant::WriteToStream
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
ms.openlocfilehash: 9a84d91e20242fb206d1d3f71fcb3dd207561f62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327223"
---
# <a name="ccomvariant-class"></a>CComVariant 클래스

이 클래스는 VARIANT 형식을 래핑하여 저장된 데이터 형식을 나타내는 멤버를 제공합니다.

## <a name="syntax"></a>구문

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComVariant::CComVariant](#ccomvariant)|생성자입니다.|
|[CComVariant::~CComVariant](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComVariant::연결](#attach)|개체에 VARIANT을 `CComVariant` 연결합니다.|
|[CComVariant::변경 유형](#changetype)|개체를 `CComVariant` 새 유형으로 변환합니다.|
|[CComVariant::지우기](#clear)|개체를 `CComVariant` 지웁습니다.|
|[CComVariant::복사](#copy)|개체에 VARIANT을 `CComVariant` 복사합니다.|
|[CComVariant::복사](#copyto)|개체의 내용을 복사합니다. `CComVariant`|
|[CComVariant::D에타치](#detach)|기본 VARIANT을 개체에서 `CComVariant` 분리합니다.|
|[CComVariant::GetSize](#getsize)|`CComVariant` 개체 내용의 바이트 수의 크기를 반환합니다.|
|[CComVariant::읽기에서 스트림](#readfromstream)|스트림에서 VARIANT을 로드합니다.|
|[CComVariant::SetByRef](#setbyref)|개체를 `CComVariant` 초기화하고 멤버를 `vt` VT_BYREF 설정합니다.|
|[CComVariant::쓰기토스트림](#writetostream)|기본 VARIANT을 스트림에 저장합니다.|

### <a name="public-operators"></a>Public 연산자

|||
|-|-|
|[CComVariant:운영자 <](#operator_lt)|개체가 `CComVariant` 지정된 VARIANT보다 적은지 여부를 나타냅니다.|
|[CComVariant:운영자 >](#operator_gt)|개체가 `CComVariant` 지정된 VARIANT보다 큰지 여부를 나타냅니다.|
|[연산자 !=](#operator_neq)|개체가 `CComVariant` 지정된 VARIANT과 같지 않은지 여부를 나타냅니다.|
|[연산자 =](#operator_eq)|개체에 값을 할당합니다. `CComVariant`|
|[연산자 ==](#operator_eq_eq)|개체가 `CComVariant` 지정된 VARIANT과 같는지 여부를 나타냅니다.|

## <a name="remarks"></a>설명

`CComVariant`공용 구조체에 저장된 데이터의 형식을 나타내는 멤버와 멤버로 구성된 VARIANT 및 VARIANTARG 형식을 래핑합니다. VARIANT는 일반적으로 자동화에 사용됩니다.

`CComVariant`VARIANT을 사용할 수 있는 모든 곳에서 사용할 수 있도록 VARIANT 형식에서 파생됩니다. 예를 들어 V_VT 매크로를 사용하여 a의 유형을 `CComVariant` 추출하거나 VARIANT을 `vt` 사용하여 멤버에 직접 액세스할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>요구 사항

**헤더:** atlcomcli.h

## <a name="ccomvariantattach"></a><a name="attach"></a>CComVariant::연결

`CComVariant` 개체의 현재 내용을 안전하게 지우고 *pSrc* 내용을 이 개체에 복사한 다음 *pSrc의* 변형 유형을 VT_EMPTY 설정합니다.

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>매개 변수

*pSrc*<br/>
【인】 개체에 연결할 [VARIANT을](/windows/win32/api/oaidl/ns-oaidl-variant) 가리킵니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

*pSrc가* 보유한 데이터의 소유권은 `CComVariant` 개체로 전송됩니다.

## <a name="ccomvariantccomvariant"></a><a name="ccomvariant"></a>CComVariant::CComVariant

각 생성자는 `CComVariant` `VariantInit` Win32 함수를 호출하거나 전달된 매개 변수에 따라 개체의 값과 형식을 설정하여 개체의 안전한 초기화를 처리합니다.

```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```

### <a name="parameters"></a>매개 변수

*varSrc*<br/>
【인】 개체를 초기화하는 데 사용되는 `CComVariant` VARIANT 또는 VARIANT입니다. `CComVariant` 소스 변형의 내용은 변환 없이 대상에 복사됩니다.

*lpszSrc*<br/>
【인】 개체를 초기화하는 데 `CComVariant` 사용되는 문자 문자열입니다. 생성자의 LPCOLESTR 버전또는 ANSI 문자열을 LPCSTR 버전에 0-종단 된 와이드 (유니코드) 문자 문자열을 전달할 수 있습니다. 두 경우 모두 문자열을 `SysAllocString`사용하여 할당된 유니코드 BSTR로 변환됩니다. `CComVariant` 개체의 형식이 VT_BSTR.

*bSrc*<br/>
【인】 개체를 초기화하는 데 `CComVariant` 사용되는 **bool입니다.** **bool** 인수는 저장되기 전에 VARIANT_BOOL 변환됩니다. 개체의 형식은 `CComVariant` VT_BOOL.

*nSrc*<br/>
【인】 **int**, **BYTE**, **짧은**, **긴,** LONGLONG, ULONGLONG, **서명되지 않은 짧은,** **서명되지 않은 긴,** 또는 `CComVariant` 객체를 초기화하는 데 사용되는 **서명되지 않은 int.** `CComVariant` 개체의 형식은 각각 VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 또는 VT_UI4 됩니다.

*vtSrc*<br/>
【인】 변형의 유형입니다. 첫 번째 매개 변수가 **int인**경우 유효한 형식이 VT_I4 VT_INT. 첫 번째 매개 변수가 **길면**유효한 형식이 VT_I4 VT_ERROR. 첫 번째 매개 변수가 **두 번째**인 경우 유효한 형식이 VT_R8 VT_DATE. 첫 번째 매개 변수가 **서명되지 않은 int인**경우 유효한 형식이 VT_UI4 VT_UINT.

*fltSrc*<br/>
【인】 개체를 초기화하는 `CComVariant` 데 사용되는 **float입니다.** 개체의 형식은 `CComVariant` VT_R4.

*dblSrc*<br/>
【인】 개체를 초기화하는 `CComVariant` 데 사용되는 **double입니다.** 개체의 형식은 `CComVariant` VT_R8.

*시스터드 (동음이의)*<br/>
【인】 개체를 `CY` 초기화하는 `CComVariant` 데 사용됩니다. 개체의 형식은 `CComVariant` VT_CY.

*pSrc*<br/>
【인】 `IDispatch` 개체를 `IUnknown` 초기화하는 데 `CComVariant` 사용되는 또는 포인터입니다. `AddRef`인터페이스 포인터에서 호출됩니다. `CComVariant` 개체의 형식은 각각 VT_DISPATCH 또는 VT_UNKNOWN.

또는 개체를 초기화하는 데 `CComVariant` 사용되는 SAFERRAY 포인터입니다. SAFEARRAY의 복사본이 개체에 `CComVariant` 저장됩니다. `CComVariant` 개체의 형식은 SAFEARRAY 및 VT_ARRAY 원래 형식의 조합입니다.

*Csrc*<br/>
【인】 개체를 초기화하는 `CComVariant` 데 사용되는 **char입니다.** 개체의 형식이 `CComVariant` VT_I1.

*블스트셔 (동음이의)*<br/>
【인】 개체를 초기화하는 데 `CComVariant` 사용되는 BSTR입니다. `CComVariant` 개체의 형식이 VT_BSTR.

### <a name="remarks"></a>설명

소멸자는 [CComVariant::Clear를](#clear)호출하여 정리를 관리합니다.

## <a name="ccomvariantccomvariant"></a><a name="dtor"></a>CComVariant::~CComVariant

소멸자입니다.

```
~CComVariant() throw();
```

### <a name="remarks"></a>설명

이 메서드는 [CComVariant::Clear를](#clear)호출하여 정리를 관리합니다.

## <a name="ccomvariantchangetype"></a><a name="changetype"></a>CComVariant::변경 유형

개체를 `CComVariant` 새 유형으로 변환합니다.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>매개 변수

*vtNew*<br/>
【인】 개체의 새 `CComVariant` 형식입니다.

*pSrc*<br/>
【인】 값이 새 유형으로 변환되는 VARIANT에 대한 포인터입니다. 기본값은 NULL이며, `CComVariant` 이는 개체가 제자리에서 변환된다는 것을 의미합니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

*pSrc에* `ChangeType` 대한 값을 전달하는 경우 이 VARIANT을 변환의 소스로 사용합니다. 그렇지 않으면 `CComVariant` 개체가 원본이 됩니다.

## <a name="ccomvariantclear"></a><a name="clear"></a>CComVariant::지우기

Win32 `CComVariant` 함수를 `VariantClear` 호출하여 개체를 지웁습니다.

```
HRESULT Clear();
```

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

소멸자는 자동으로 를 호출합니다. `Clear`

## <a name="ccomvariantcopy"></a><a name="copy"></a>CComVariant::복사

개체를 `CComVariant` 해제 한 다음 지정 된 VARIANT의 복사본을 할당 합니다.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>매개 변수

*pSrc*<br/>
【인】 복사할 [VARIANT에](/windows/win32/api/oaidl/ns-oaidl-variant) 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="ccomvariantcopyto"></a><a name="copyto"></a>CComVariant::복사

개체의 내용을 복사합니다. `CComVariant`

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>매개 변수

*가장 프스트*<br/>
개체의 내용의 복사본을 받게 됩니다 BSTR가리킵니입니다. `CComVariant`

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

개체는 `CComVariant` VT_BSTR 형식이어야 합니다.

## <a name="ccomvariantdetach"></a><a name="detach"></a>CComVariant::D에타치

`CComVariant` 기본 VARIANT을 개체에서 분리하고 개체의 형식을 VT_EMPTY 설정합니다.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>매개 변수

*pDest*<br/>
【아웃】 개체의 기본 VARIANT 값을 반환합니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

*pDest에서* 참조하는 VARIANT의 내용은 호출 `CComVariant` 개체의 값과 형식이 할당되기 전에 자동으로 지워집니다.

## <a name="ccomvariantgetsize"></a><a name="getsize"></a>CComVariant::GetSize

단순 고정 크기의 VARIANT의 경우 이 메서드는 기본 데이터 **형식과** **SIZEOF(VARTYPE)의 sizeof를**반환합니다.

```
ULONG GetSize() const;
```

### <a name="return-value"></a>Return Value

개체의 현재 내용의 바이트 크기입니다. `CComVariant`

### <a name="remarks"></a>설명

VARIANT에 인터페이스 포인터, `GetSize` 또는 `IPersistStream` `IPersistStreamInit`에 대한 쿼리가 포함되어 있는 경우. 성공하면 반환 값은 CLSID 및 `GetSizeMax` **SIZEOF(VARTYPE)의**크기와 함께 반환되는 **값의** 하위 순서 32비트입니다. 인터페이스 포인터가 NULL이면 `GetSize` CLSID 와 **SIZEof(VARTYPE)의 sizeof를**반환합니다. **sizeof** 전체 크기가 ULONG_MAX 큰 `GetSize` 경우 오류를 나타내는 **SIZEof(VARTYPE)를** 반환합니다.

다른 모든 경우에, VT_BSTR 형식의 임시 VARIANT은 현재 VARIANT에서 강제 변환됩니다. 이 BSTR의 길이는 문자열 길이의 크기와 문자열 자체의 길이와 null 문자 의 크기와 **VARTYPE(VARTYPE)으로**계산됩니다. VARIANT을 VT_BSTR 형식의 VARIANT에 강제 변환할 수 없는 경우 `GetSize` **sizeof(VARTYPE)를**반환합니다.

이 메서드에서 반환 되는 크기는 성공적인 조건에서 [CComVariant::WriteToStream에서](#writetostream) 사용 하는 바이트의 수와 일치 합니다.

## <a name="ccomvariantoperator-"></a><a name="operator_eq"></a>CComVariant::연산자 =

개체에 값과 해당 형식을 `CComVariant` 할당합니다.

```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```

### <a name="parameters"></a>매개 변수

*varSrc*<br/>
【인】 개체에 할당할 변형입니다. [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) `CComVariant` `CComVariant` 소스 변형의 내용은 변환 없이 대상에 복사됩니다.

*블스트셔 (동음이의)*<br/>
【인】 개체에 할당할 BSTR입니다. `CComVariant` `CComVariant` 개체의 형식이 VT_BSTR.

*lpszSrc*<br/>
【인】 개체에 할당할 문자 `CComVariant` 문자열입니다. 0-종단 된 와이드 (유니코드) 문자열을 연산자의 LPCOLESTR 버전또는 ANSI 문자열을 LPCSTR 버전으로 전달할 수 있습니다. 두 경우 모두 문자열은 을 사용하여 `SysAllocString`할당된 유니코드 BSTR로 변환됩니다. `CComVariant` 개체의 형식이 VT_BSTR.

*bSrc*<br/>
【인】 개체에 할당할 **bool입니다.** `CComVariant` **bool** 인수는 저장되기 전에 VARIANT_BOOL 변환됩니다. 개체의 형식은 `CComVariant` VT_BOOL.

*nSrc*<br/>
【인】 **int,** BYTE, **짧은,** **긴,** LONGLONG, ULONGLONG, **서명되지 않은 짧은,** **서명되지 않은 긴,** 또는 `CComVariant` **서명되지 않은 int는** 개체에 할당됩니다. `CComVariant` 개체의 형식은 각각 VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 또는 VT_UI4 됩니다.

*fltSrc*<br/>
【인】 개체에 할당할 **float입니다.** `CComVariant` 개체의 형식은 `CComVariant` VT_R4.

*dblSrc*<br/>
【인】 개체에 할당할 **double입니다.** `CComVariant` 개체의 형식은 `CComVariant` VT_R8.

*시스터드 (동음이의)*<br/>
【인】 개체에 할당할 `CY` `CComVariant` 수 있습니다. 개체의 형식은 `CComVariant` VT_CY.

*pSrc*<br/>
【인】 개체에 할당할 `IDispatch` 또는 `IUnknown` `CComVariant` 포인터입니다. `AddRef`인터페이스 포인터에서 호출됩니다. `CComVariant` 개체의 형식은 각각 VT_DISPATCH 또는 VT_UNKNOWN.

또는 개체에 할당할 SAFEARRAY `CComVariant` 포인터입니다. SAFEARRAY의 복사본이 개체에 `CComVariant` 저장됩니다. `CComVariant` 개체의 형식은 SAFEARRAY 및 VT_ARRAY 원래 형식의 조합입니다.

*Csrc*<br/>
【인】 개체에 할당할 문자입니다. `CComVariant` 개체의 형식이 `CComVariant` VT_I1.

## <a name="ccomvariantoperator-"></a><a name="operator_eq_eq"></a>CComVariant::연산자 ==

개체가 `CComVariant` 지정된 VARIANT과 같는지 여부를 나타냅니다.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>설명

*varSrc의* 값과 형식이 개체의 값과 형식과 각각 같으면 `CComVariant` TRUE를 반환합니다. 그렇지 않으면 FALSE입니다. 운영자는 사용자의 기본 로캘을 사용하여 비교를 수행합니다.

연산자는 변형 형식의 값만 비교합니다. 문자열, 정수 및 부동 점을 비교하지만 배열이나 레코드는 비교하지 않습니다.

## <a name="ccomvariantoperator-"></a><a name="operator_neq"></a>CComVariant::연산자 !=

개체가 `CComVariant` 지정된 VARIANT과 같지 않은지 여부를 나타냅니다.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>설명

*varSrc의* 값 이나 형식이 개체의 값 또는 형식과 각각 같지 `CComVariant` 않은 경우 TRUE를 반환 합니다. 그렇지 않으면 FALSE입니다. 운영자는 사용자의 기본 로캘을 사용하여 비교를 수행합니다.

연산자는 변형 형식의 값만 비교합니다. 문자열, 정수 및 부동 점을 비교하지만 배열이나 레코드는 비교하지 않습니다.

## <a name="ccomvariantoperator-lt"></a><a name="operator_lt"></a>CComVariant::연산자&lt;

개체가 `CComVariant` 지정된 VARIANT보다 적은지 여부를 나타냅니다.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>설명

`CComVariant` 개체 값이 *varSrc*값보다 적으면 TRUE를 반환합니다. 그렇지 않으면 FALSE입니다. 운영자는 사용자의 기본 로캘을 사용하여 비교를 수행합니다.

## <a name="ccomvariantoperator-gt"></a><a name="operator_gt"></a>CComVariant::연산자&gt;

개체가 `CComVariant` 지정된 VARIANT보다 큰지 여부를 나타냅니다.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>설명

`CComVariant` 개체값이 *varSrc*값보다 큰 경우 TRUE를 반환합니다. 그렇지 않으면 FALSE입니다. 운영자는 사용자의 기본 로캘을 사용하여 비교를 수행합니다.

## <a name="ccomvariantreadfromstream"></a><a name="readfromstream"></a>CComVariant::읽기에서 스트림

기본 VARIANT을 지정된 스트림에 포함된 VARIANT로 설정합니다.

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
【인】 데이터를 포함하는 스트림의 [IStream](/windows/win32/api/objidl/nn-objidl-istream) 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

`ReadToStream`[WriteToStream에](#writetostream)대한 이전 호출이 필요합니다.

## <a name="ccomvariantsetbyref"></a><a name="setbyref"></a>CComVariant::SetByRef

개체를 `CComVariant` 초기화하고 멤버를 `vt` VT_BYREF 설정합니다.

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
VARIANT의 유형(예: BSTR, **int)** 또는 **char**.

*Pt*<br/>
개체를 초기화하는 `CComVariant` 데 사용되는 포인터입니다.

### <a name="remarks"></a>설명

`SetByRef`는 `CComVariant` 개체를 포인터 *pT로* 초기화하고 멤버를 `vt` VT_BYREF 설정하는 함수 템플릿입니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

## <a name="ccomvariantwritetostream"></a><a name="writetostream"></a>CComVariant::쓰기토스트림

기본 VARIANT을 스트림에 저장합니다.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
【인】 스트림의 [IStream](/windows/win32/api/objidl/nn-objidl-istream) 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
