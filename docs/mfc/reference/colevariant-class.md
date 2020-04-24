---
title: COle변형 클래스
ms.date: 11/04/2016
f1_keywords:
- COleVariant
- AFXDISP/COleVariant
- AFXDISP/COleVariant::COleVariant
- AFXDISP/COleVariant::Attach
- AFXDISP/COleVariant::ChangeType
- AFXDISP/COleVariant::Clear
- AFXDISP/COleVariant::Detach
- AFXDISP/COleVariant::GetByteArrayFromVariantArray
- AFXDISP/COleVariant::SetString
helpviewer_keywords:
- COleVariant [MFC], COleVariant
- COleVariant [MFC], Attach
- COleVariant [MFC], ChangeType
- COleVariant [MFC], Clear
- COleVariant [MFC], Detach
- COleVariant [MFC], GetByteArrayFromVariantArray
- COleVariant [MFC], SetString
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
ms.openlocfilehash: 7d8abea39a9baa3f447ca0d5f3ab1183367d531f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753716"
---
# <a name="colevariant-class"></a>COle변형 클래스

[VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 데이터 형식을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class COleVariant : public tagVARIANT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COle변형::콜레변종](#colevariant)|`COleVariant` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COle변형::연결](#attach)|변형을 `COleVariant`에 연결합니다.|
|[COle변형::변경 유형](#changetype)|이 `COleVariant` 개체의 변형 형식을 변경합니다.|
|[COle변형::지우기](#clear)|이 `COleVariant` 개체를 지웁니다.|
|[콜레변종::D에타치](#detach)|에서 VARIANT을 분리 `COleVariant` 하고 VARIANT를 반환 합니다.|
|[COle변형::겟바이트어레이에서변형배열](#getbytearrayfromvariantarray)|기존 변형 배열에서 바이트 배열을 검색합니다.|
|[COle변형::세트스트링](#setstring)|문자열을 특정 형식(일반적으로 ANSI)으로 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[COleVariant::연산자 LPCVARIANT](#operator_lpcvariant)|`COleVariant` 값을 로 `LPCVARIANT`변환합니다.|
|[COleVariant::연산자 LPVARIANT](#operator_lpvariant)|개체를 `COleVariant` 로 변환합니다. `LPVARIANT`|
|[COleVariant::연산자 =](#operator_eq)|값을 복사합니다. `COleVariant`|
|[COleVariant::연산자 ==](#operator_eq_eq)|두 `COleVariant` 값을 비교합니다.|
|[COle변형::연산자 &lt; &lt;,&gt;&gt;](#operator_lt_lt__gt_gt)|`COleVariant` 값을 `CArchive` 출력하거나 `CDumpContext` `COleVariant` `CArchive`에서 개체를 입력합니다.|

## <a name="remarks"></a>설명

이 데이터 형식은 OLE 자동화에 사용됩니다. 특히 [DISPPARAMS](/windows/win32/api/oaidl/ns-oaidl-dispparams) 구조에는 VARIANT 구조의 배열에 대한 포인터가 포함되어 있습니다. 구조는 `DISPPARAMS` [IDispatch::Invoke에](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)매개 변수를 전달하는 데 사용됩니다.

> [!NOTE]
> 이 클래스는 구조에서 `VARIANT` 파생됩니다. `COleVariant` 즉, 을 `VARIANT` 호출하는 매개 변수에 전달할 수 있으며 `VARIANT` 구조의 데이터 멤버가 `COleVariant`에 액세스할 수 있는 데이터 멤버임을 의미합니다.

두 개의 관련 MFC 클래스 [COleCurrency](../../mfc/reference/colecurrency-class.md) 및 [COleDateTime은](../../atl-mfc-shared/reference/coledatetime-class.md) 변형 `VT_CY`데이터 형식 `VT_DATE`통화 () 및 DATE ()를 캡슐화합니다. 클래스는 `COleVariant` DAO 클래스에서 광범위하게 사용됩니다. 이 클래스의 일반적인 사용에 대 한 이러한 클래스를 참조 하십시오(예: [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 및 [CDaoRecordset)](../../mfc/reference/cdaorecordset-class.md)

자세한 내용은 [변형,](/windows/win32/api/oaidl/ns-oaidl-variant) [통화,](/windows/win32/api/wtypes/ns-wtypes-cy~r1) [DISPPARAMS](/windows/win32/api/oaidl/ns-oaidl-dispparams)및 [IDispatch::Windows](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) SDK의 항목을 참조하십시오.

클래스 및 OLE 자동화에서의 사용에 대한 자세한 내용은 자동화 문서의 "OLE 자동화에서 매개 변수 전달"을 참조하십시오. [Automation](../../mfc/automation.md) `COleVariant`

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagVARIANT`

`COleVariant`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="colevariantattach"></a><a name="attach"></a>COle변형::연결

이 함수를 호출하여 지정된 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) `COleVariant` 개체를 현재 개체에 연결합니다.

```cpp
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>매개 변수

*varSrc*<br/>
현재 `COleVariant` `VARIANT` 개체에 연결할 기존 개체입니다.

### <a name="remarks"></a>설명

이 함수는 *varSrc의* VARTYPE을 VT_EMPTY 설정합니다.

자세한 내용은 Windows SDK의 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 및 [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum) 항목을 참조하십시오.

## <a name="colevariantcolevariant"></a><a name="colevariant"></a>COle변형::콜레변종

`COleVariant` 개체를 생성합니다.

```
COleVariant();
COleVariant(const VARIANT& varSrc);
COleVariant(const COleVariant& varSrc);
COleVariant(LPCVARIANT pSrc);
COleVariant(LPCTSTR lpszSrc);
COleVariant(LPCTSTR lpszSrc, VARTYPE vtSrc);
COleVariant(CString& strSrc);
COleVariant(BYTE nSrc);
COleVariant(short nSrc, VARTYPE vtSrc = VT_I2);
COleVariant(long lSrc,VARTYPE vtSrc = VT_I4);
COleVariant(const COleCurrency& curSrc);
COleVariant(float fltSrc);
COleVariant(double dblSrc);
COleVariant(const COleDateTime& timeSrc);
COleVariant(const CByteArray& arrSrc);
COleVariant(const CLongBinary& lbSrc);
COleVariant(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>매개 변수

*varSrc*<br/>
새 `COleVariant` `COleVariant` 개체에 복사할 기존 또는 `VARIANT` 개체입니다.

*pSrc*<br/>
새 `VARIANT` `COleVariant` 개체에 복사될 개체에 대한 포인터입니다.

*lpszSrc*<br/>
새 `COleVariant` 개체에 복사할 null 종료된 문자열입니다.

*vtSrc*<br/>
새 `VARTYPE` `COleVariant` 개체에 대한 입니다.

*strSrc*<br/>
새 `COleVariant` 개체에 복사할 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.

*nSrc,* *lSrc* A 숫자 값을 새 `COleVariant` 개체에 복사할 수 있습니다.

*vtSrc*<br/>
새 `VARTYPE` `COleVariant` 개체에 대한 입니다.

*커서스 (동음이의)*<br/>
새 `COleVariant` 개체에 복사할 [COleCurrency](../../mfc/reference/colecurrency-class.md) 개체입니다.

*fltSrc,* *dblSrc*<br/>
새 `COleVariant` 개체에 복사될 숫자 값입니다.

*timeSrc*<br/>
새 `COleVariant` 개체에 복사할 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체입니다.

*아르스크 (동음이의)*<br/>
새 `COleVariant` 개체에 복사할 [CByteArray](../../mfc/reference/cbytearray-class.md) 개체입니다.

*lbSrc*<br/>
새 `COleVariant` 개체에 복사할 [CLongBinary](../../mfc/reference/clongbinary-class.md) 개체입니다.

*Pidl*<br/>
새 `COleVariant` 개체에 복사할 [ITEMIDLIST](/windows/win32/api/shtypes/ns-shtypes-itemidlist) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

이러한 모든 생성자는 `COleVariant` 지정된 값으로 초기화된 새 개체를 만듭니다. 이러한 각 생성자에 대한 간략한 설명은 다음과 같습니다.

- **COle변형() )** VT_EMPTY 빈 `COleVariant` 개체를 만듭니다.

- **콜레변형** *(varSrc)* **)** 기존 `VARIANT` 또는 `COleVariant` 개체를 복사합니다. 변형 형식이 유지됩니다.

- **셀레변형** *(pSrc)* **)** 기존 `VARIANT` 또는 `COleVariant` 개체를 복사합니다. 변형 형식이 유지됩니다.

- **콜레변종** *(lpszSrc)* **)** 새 개체(유니코드)VT_BSTR 문자열을 복사합니다.

- **콜레변형** *(lpszSrc,* **,** *vtSrc)* **)** 문자열을 새 개체에 복사합니다. 매개 변수 *vtSrc는* VT_BSTR(유니코드) 또는 VT_BSTRT(ANSI)이어야 합니다.

- **콜레변종** *(strSrc)* **)** 새 개체(유니코드)VT_BSTR 문자열을 복사합니다.

- **콜레변종** *(nSrc)* **)** VT_UI1 새 개체에 8비트 정수를 복사합니다.

- **콜레데전이브** *(nSrc,* **,** *vtSrc)* **)** 16비트 정수(또는 부울 값)를 새 개체에 복사합니다. 매개 변수 *vtSrc는* VT_I2 또는 VT_BOOL.

- **콜레변형** *(lSrc,* **,** *vtSrc)* **)** 32비트 정수(또는 SCODE 값)를 새 개체에 복사합니다. 매개 변수 *vtSrc는* VT_I4, VT_ERROR 또는 VT_BOOL 있어야 합니다.

- **셀레변형(커스셔스)** *curSrc* **)** VT_CY 새 `COleCurrency` 개체에 값을 복사합니다.

- **콜레변종** *(fltSrc)* **)** VT_R4 새 개체에 32비트 부동 점 값을 복사합니다.

- **콜레변종** *(dblSrc)* **)** VT_R8 새 개체에 64비트 부동 점 값을 복사합니다.

- **콜레변종(시간Src)** *timeSrc* **)** `COleDateTime` VT_DATE 새 개체에 값을 복사합니다.

- **콜레변종** *(아르스rc)* **)** `CByteArray` VT_EMPTY 새 개체에 개체를 복사합니다.

- **콜레변형** *(lbSrc)* **)** `CLongBinary` VT_EMPTY 새 개체에 개체를 복사합니다.

SCODE에 대한 자세한 내용은 Windows SDK의 [COM 오류 코드 구조를](/windows/win32/com/structure-of-com-error-codes) 참조하십시오.

## <a name="colevariantchangetype"></a><a name="changetype"></a>COle변형::변경 유형

이 `COleVariant` 개체에서 변형 값의 형식을 변환합니다.

```cpp
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```

### <a name="parameters"></a>매개 변수

*Vartype*<br/>
이 `COleVariant` 개체의 VARTYPE입니다.

*pSrc*<br/>
변환할 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 개체에 대한 포인터입니다. 이 값이 NULL이면 `COleVariant` 이 개체가 변환의 소스로 사용됩니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum)및 [변형 변경 유형](/windows/win32/api/oleauto/nf-oleauto-variantchangetype) 항목을 참조하십시오.

## <a name="colevariantclear"></a><a name="clear"></a>COle변형::지우기

`VARIANT`을 지웁니다.

```cpp
void Clear();
```

### <a name="remarks"></a>설명

이렇게 하면 이 개체에 대한 VARTYPE이 VT_EMPTY 설정됩니다. `COleVariant` 소멸자는 이 함수를 호출합니다.

자세한 내용은 Windows `VARIANT`SDK의 `VariantClear` "VARTYPE 및 항목"을 참조하십시오.

## <a name="colevariantdetach"></a><a name="detach"></a>콜레변종::D에타치

기본 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 개체를 이 `COleVariant` 개체에서 분리합니다.

```
VARIANT Detach();
```

### <a name="remarks"></a>설명

이 함수는 이 `COleVariant` 개체에 대한 VARTYPE을 VT_EMPTY 설정합니다.

> [!NOTE]
> 호출 `Detach`한 후 결과 `VariantClear` `VARIANT` 구조를 호출하는 것은 호출자의 책임입니다.

자세한 내용은 Windows SDK의 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum)및 [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) 항목을 참조하십시오.

## <a name="colevariantgetbytearrayfromvariantarray"></a><a name="getbytearrayfromvariantarray"></a>COle변형::겟바이트어레이에서변형배열

기존 변형 배열에서 바이트 배열을 검색합니다.

```cpp
void GetByteArrayFromVariantArray(CByteArray& bytes);
```

### <a name="parameters"></a>매개 변수

*바이트*<br/>
기존 [CByteArray](../../mfc/reference/cbytearray-class.md) 개체에 대한 참조입니다.

## <a name="colevariantoperator-lpcvariant"></a><a name="operator_lpcvariant"></a>COleVariant::연산자 LPCVARIANT

이 캐스팅 연산자는 이 `VARIANT` `COleVariant` 개체에서 값이 복사된 구조를 반환합니다.

```
operator LPCVARIANT() const;
```

### <a name="remarks"></a>설명

## <a name="colevariantoperator-lpvariant"></a><a name="operator_lpvariant"></a>COleVariant::연산자 LPVARIANT

이 캐스팅 연산자에게 `VARIANT` 호출하여 `COleVariant` 이 개체의 기본 구조에 액세스합니다.

```
operator LPVARIANT();
```

### <a name="remarks"></a>설명

> [!CAUTION]
> 이 함수에서 `VARIANT` 반환되는 포인터에 의해 액세스되는 구조의 값을 `COleVariant` 변경하면 이 개체의 값이 변경됩니다.

## <a name="colevariantoperator-"></a><a name="operator_eq"></a>COleVariant::연산자 =

이러한 오버로드된 할당 연산자는 `COleVariant` 소스 값을 이 개체에 복사합니다.

```
const COleVariant& operator=(const VARIANT& varSrc);
const COleVariant& operator=(LPCVARIANT pSrc);
const COleVariant& operator=(const COleVariant& varSrc);
const COleVariant& operator=(const LPCTSTR lpszSrc);
const COleVariant& operator=(const CString& strSrc);
const COleVariant& operator=(BYTE nSrc);
const COleVariant& operator=(short nSrc);
const COleVariant& operator=(long lSrc);
const COleVariant& operator=(const COleCurrency& curSrc);
const COleVariant& operator=(float fltSrc);
const COleVariant& operator=(double dblSrc);
const COleVariant& operator=(const COleDateTime& dateSrc);
const COleVariant& operator=(const CByteArray& arrSrc);
const COleVariant& operator=(const CLongBinary& lbSrc);
```

### <a name="remarks"></a>설명

각 연산자에 대한 간략한 설명은 다음과 같습니다.

- **연산자** *=(varSrc)* **)** 기존 VARIANT 또는 `COleVariant` 개체를 이 개체에 복사합니다.

- **연산자** *=(pSrc)* **)** *pSrc에서* 액세스하는 VARIANT 개체를 이 개체에 복사합니다.

- **연산자** *=(lpszSrc)* **)** null 종료된 문자열을 이 개체에 복사하고 VARTYPE을 VT_BSTR 설정합니다.

- **연산자** *=(strSrc)* **)** [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체를 이 개체에 복사하고 VARTYPE을 VT_BSTR 설정합니다.

- **연산자** *=(nSrc)* **)** 8비트 또는 16비트 정수 값을 이 개체에 복사합니다. *nSrc가* 8비트 값인 경우 이 의 VARTYPE은 VT_UI1 설정됩니다. *nSrc가* 16비트 값이고 이 값의 VARTYPE이 VT_BOOL 경우 유지됩니다. 그렇지 않으면 VT_I2 설정됩니다.

- **연산자** *=(lSrc)* **)** 32비트 정수 값을 이 개체에 복사합니다. 이 것의 VARTYPE이 VT_ERROR 경우 유지됩니다. 그렇지 않으면 VT_I4 설정됩니다.

- **연산자** *=(curSrc)* **)** [COleCurrency](../../mfc/reference/colecurrency-class.md) 개체를 이 개체에 복사하고 VARTYPE을 VT_CY 설정합니다.

- **연산자** *=(fltSrc)* **)** 32비트 부동 점 값을 이 개체에 복사하고 VARTYPE을 VT_R4 설정합니다.

- **연산자** *=(dblSrc)* **)** 64비트 부동 점 값을 이 개체에 복사하고 VARTYPE을 VT_R8 설정합니다.

- **연산자** *=(날짜Src)* **)** [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체를 이 개체에 복사하고 VARTYPE을 VT_DATE 설정합니다.

- **연산자** *=(arrSrc)* **)** [CByteArray](../../mfc/reference/cbytearray-class.md) 개체를 이 `COleVariant` 개체에 복사합니다.

- **연산자** *=(lbSrc)* **)** [CLongBinary](../../mfc/reference/clongbinary-class.md) 개체를 이 `COleVariant` 개체에 복사합니다.

자세한 내용은 Windows SDK의 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 및 [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum) 항목을 참조하십시오.

## <a name="colevariantoperator-"></a><a name="operator_eq_eq"></a>COleVariant::연산자 ==

이 연산자는 두 변형 값을 비교하고 같으면 0이 아닌 값을 반환합니다. 그렇지 않으면 0.

```
BOOL operator==(const VARIANT& varSrc) const;
BOOL operator==(LPCVARIANT pSrc) const;
```

## <a name="colevariantoperator-ltlt-gtgt"></a><a name="operator_lt_lt__gt_gt"></a>COle변형::연산자 &lt; &lt;,&gt;&gt;

`COleVariant` 값을 `CArchive` 출력하거나 `CdumpContext` `COleVariant` `CArchive`에서 개체를 입력합니다.

```
friend CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    OleVariant varSrc);

friend CArchive& AFXAPI operator<<(
    CArchive& ar,
    COleVariant varSrc);

friend CArchive& AFXAPI operator>>(
    CArchive& ar,
    COleVariant& varSrc);
```

### <a name="remarks"></a>설명

`COleVariant` 삽입 ()**\<** 연산자는 진단 덤프 및 아카이브에 저장을 지원합니다. 추출 ()**>>** 연산자는 아카이브에서 로드를 지원합니다.

## <a name="colevariantsetstring"></a><a name="setstring"></a>COle변형::세트스트링

문자열을 특정 유형으로 설정합니다.

```cpp
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```

### <a name="parameters"></a>매개 변수

*lpszSrc*<br/>
새 `COleVariant` 개체에 복사할 null 종료된 문자열입니다.

*VtSrc*<br/>
새 `COleVariant` 개체의 VARTYPE입니다.

### <a name="remarks"></a>설명

매개 변수 *vtSrc는* VT_BSTR(유니코드) 또는 VT_BSTRT(ANSI)이어야 합니다. `SetString`일반적으로 문자열을 ANSI로 설정하는 데 사용되며, [COleVariant::COleVariant](#colevariant) 생성자의 기본값은 문자열 또는 문자열 포인터 매개 변수가 있고 VARTYPE이 유니코드가 없기 때문에 일반적으로 ANSI로 설정합니다.

UNICODE가 아닌 빌드의 DAO 레코드 집합은 문자열이 ANSI가 될 것으로 예상합니다. 따라서 개체를 `COleVariant` 사용하는 DAO 함수의 경우 UNICODE 레코드 집합을 만들지 않는 경우 **cOleVariant::COleVariant(lpszSrc** *lpszSrc* **,** *vtSrc)* **)** 생성자 형식을 사용하여 VT_BSTRT(ANSI)로 설정하거나 anSI 문자열을 만들기 위해 VT_BSTRT *vtSrc* 를 사용하여 설정합니다. *vtSrc* `SetString` 예를 들어 `CDaoRecordset` 함수 [CDaoRecordset::검색](../../mfc/reference/cdaorecordset-class.md#seek) 및 [CDaoRecordset::SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) 매개 변수로 개체를 사용 합니다. `COleVariant` DAO 레코드 집합이 유니코드가 아닌 경우 이러한 개체는 ANSI여야 합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
