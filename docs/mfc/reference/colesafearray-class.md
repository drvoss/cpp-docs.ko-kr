---
title: 콜레세이프어레이어레이 클래스
ms.date: 08/29/2019
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
helpviewer_keywords:
- COleSafeArray [MFC], COleSafeArray
- COleSafeArray [MFC], AccessData
- COleSafeArray [MFC], AllocData
- COleSafeArray [MFC], AllocDescriptor
- COleSafeArray [MFC], Attach
- COleSafeArray [MFC], Clear
- COleSafeArray [MFC], Copy
- COleSafeArray [MFC], Create
- COleSafeArray [MFC], CreateOneDim
- COleSafeArray [MFC], Destroy
- COleSafeArray [MFC], DestroyData
- COleSafeArray [MFC], DestroyDescriptor
- COleSafeArray [MFC], Detach
- COleSafeArray [MFC], GetByteArray
- COleSafeArray [MFC], GetDim
- COleSafeArray [MFC], GetElement
- COleSafeArray [MFC], GetElemSize
- COleSafeArray [MFC], GetLBound
- COleSafeArray [MFC], GetOneDimSize
- COleSafeArray [MFC], GetUBound
- COleSafeArray [MFC], Lock
- COleSafeArray [MFC], PtrOfIndex
- COleSafeArray [MFC], PutElement
- COleSafeArray [MFC], Redim
- COleSafeArray [MFC], ResizeOneDim
- COleSafeArray [MFC], UnaccessData
- COleSafeArray [MFC], Unlock
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
ms.openlocfilehash: 10e9975bac776429a38bfc707215a9465ce35c2e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753763"
---
# <a name="colesafearray-class"></a>콜레세이프어레이어레이 클래스

임의의 형식 및 차원 배열 작업용 클래스입니다.

## <a name="syntax"></a>구문

```
class COleSafeArray : public tagVARIANT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레세이프어레이::콜레세이프어레이](#colesafearray)|`COleSafeArray` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COle세이프어레이::액세스 데이터](#accessdata)|배열 데이터에 대한 포인터를 검색합니다.|
|[콜레세이프어레이::알록데이터](#allocdata)|배열에 메모리를 할당합니다.|
|[COleSafeArray::Alloc설명자](#allocdescriptor)|안전 배열 설명자에 대 한 메모리를 할당 합니다.|
|[COle세이프어레이::연결](#attach)|개체에 대한 `VARIANT` 기존 배열을 제어합니다. `COleSafeArray`|
|[COle세이프어레이::클리어](#clear)|기본 `VARIANT`의 모든 데이터를 해제합니다.|
|[COle세이프어레이::복사](#copy)|기존 배열의 복사본을 만듭니다.|
|[COleSafeArray::만들기](#create)|안전한 배열을 만듭니다.|
|[COleSafeArray::CreateOneDim](#createonedim)|1차원 `COleSafeArray` 개체를 만듭니다.|
|[콜레세이프어레이::D에스트로이](#destroy)|기존 배열을 삭제합니다.|
|[콜레세이프어레이::D에스트로이데이터](#destroydata)|안전한 배열의 데이터를 삭제합니다.|
|[COleSafeArray::D에스트로이 스크립트](#destroydescriptor)|안전 배열의 설명자가 삭제됩니다.|
|[COleSafeArray::D에타치](#detach)|데이터가 해제되지 않도록 `COleSafeArray` 개체에서 VARIANT 배열을 분리합니다.|
|[COleSafeArray::GetByteArray](#getbytearray)|안전 배열의 내용을 [CByteArray로](../../mfc/reference/cbytearray-class.md)복사합니다.|
|[COle세이프어레이: 겟딤](#getdim)|배열의 차원 수를 반환합니다.|
|[COle세이프어레이::겟엘리먼트](#getelement)|안전 배열의 단일 요소를 검색합니다.|
|[COleSafeArray::GetElemSize](#getelemsize)|안전한 배열에서 하나의 요소의 크기를 바이트로 반환합니다.|
|[COle세이프어레이::겟바운드](#getlbound)|안전 배열의 모든 차원에 대해 하한을 반환합니다.|
|[콜레세이프어레이::겟원딤사이즈](#getonedimsize)|1차원 `COleSafeArray` 개체의 요소 수를 반환합니다.|
|[COleSafeArray::GetU바운드](#getubound)|안전 배열의 모든 차원에 대한 상한을 반환합니다.|
|[COle세이프어레이::잠금](#lock)|배열의 잠금 수를 증분하고 배열 설명자의 배열 데이터에 대한 포인터를 배치합니다.|
|[코올세이프어레이::P트로오브인덱스](#ptrofindex)|인덱싱된 요소에 대한 포인터를 반환합니다.|
|[콜레세이프어레이::PutElement](#putelement)|단일 요소를 배열에 할당합니다.|
|[콜레세이프어레이::레임](#redim)|안전 배열의 가장 중요하지 않은(가장 오른쪽) 바인딩을 변경합니다.|
|[콜레세이프어레이::리사이즈원딤](#resizeonedim)|1차원 `COleSafeArray` 개체의 요소 수를 변경합니다.|
|[COleSafeArray::액세스 해제 데이터](#unaccessdata)|배열의 잠금 수를 삭제하고 `AccessData`에서 검색한 포인터를 무효화합니다.|
|[COleSafeArray::잠금 해제](#unlock)|배열을 해제하거나 크기를 조정할 수 있도록 배열의 잠금 수를 감소시입니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[COleSafeArray::연산자 LPCVARIANT](#operator_lpcvariant)|개체의 기본 `VARIANT` 구조에 `COleSafeArray` 액세스합니다.|
|[COleSafeArray::연산자 LPVARIANT](#operator_lpvariant)|개체의 기본 `VARIANT` 구조에 `COleSafeArray` 액세스합니다.|
|[COleSafeArray::연산자 =](#operator_eq)|`COleSafeArray` 값을`SAFEARRAY`개체(, 또는 `VARIANT` `COleVariant` `COleSafeArray` 배열)로 복사합니다.|
|[COleSafeArray::연산자 ==](#operator_eq_eq)|두 변형 배열`SAFEARRAY`(, `VARIANT` `COleVariant`또는 `COleSafeArray` 배열)을 비교합니다.|
|[COleSafeArray::연산자&lt;&lt;](#operator_lt_lt)|`COleSafeArray` 개체의 내용을 덤프 컨텍스트에 출력합니다.|

## <a name="remarks"></a>설명

`COleSafeArray`OLE `VARIANT` 구조에서 파생됩니다. OLE `SAFEARRAY` 멤버 함수는 1차원 바이트 배열을 위해 특별히 설계된 멤버 함수 집합뿐만 아니라 를 통해 `COleSafeArray`사용할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="colesafearrayaccessdata"></a><a name="accessdata"></a>COle세이프어레이::액세스 데이터

배열 데이터에 대한 포인터를 검색합니다.

```cpp
void AccessData(void** ppvData);
```

### <a name="parameters"></a>매개 변수

*ppvData*<br/>
배열 데이터에 대한 포인터입니다.

### <a name="remarks"></a>설명

오류가 발생하면 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException을](../../mfc/reference/coleexception-class.md)throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

## <a name="colesafearrayallocdata"></a><a name="allocdata"></a>콜레세이프어레이::알록데이터

안전한 배열에 메모리를 할당합니다.

```cpp
void AllocData();
```

### <a name="remarks"></a>설명

오류가 발생하면 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException을](../../mfc/reference/coleexception-class.md)throw합니다.

## <a name="colesafearrayallocdescriptor"></a><a name="allocdescriptor"></a>COleSafeArray::Alloc설명자

안전 배열의 설명자에 메모리를 할당합니다.

```cpp
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>매개 변수

*dwDims*<br/>
안전 배열의 차원 수입니다.

### <a name="remarks"></a>설명

오류가 발생하면 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException을](../../mfc/reference/coleexception-class.md)throw합니다.

## <a name="colesafearrayattach"></a><a name="attach"></a>COle세이프어레이::연결

`COleSafeArray` 기존 `VARIANT` 배열의 데이터를 개체에 제어합니다.

```cpp
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>매개 변수

*varSrc*<br/>
`VARIANT` 개체입니다. *varSrc* 매개 변수에는 VARTYPE [VT_ARRAY](/windows/win32/api/wtypes/ne-wtypes-varenum)있어야 합니다.

### <a name="remarks"></a>설명

소스의 `VARIANT`유형은 VT_EMPTY 설정됩니다. 이 함수는 현재 배열(있는 경우)을 지웁션합니다.

### <a name="example"></a>예제

  [COleSafeArray::AccessData에](#accessdata)대한 예제를 참조하십시오.

## <a name="colesafearrayclear"></a><a name="clear"></a>COle세이프어레이::클리어

안전 배열을 지웁습니다.

```cpp
void Clear();
```

### <a name="remarks"></a>설명

이 함수는 개체의 VT_EMPTY `VARTYPE` 설정하여 안전한 배열을 지웁히습니다. 현재 내용이 해제되고 배열이 해제됩니다.

## <a name="colesafearraycolesafearray"></a><a name="colesafearray"></a>콜레세이프어레이::콜레세이프어레이

`COleSafeArray` 개체를 생성합니다.

```
COleSafeArray();

COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);

COleSafeArray(const COleSafeArray& saSrc);
COleSafeArray(const VARIANT& varSrc);
COleSafeArray(LPCVARIANT pSrc);
COleSafeArray(const COleVariant& varSrc);
```

### <a name="parameters"></a>매개 변수

*사스크 (동음이의)*<br/>
기존 `COleSafeArray` 개체또는 `SAFEARRAY` 새 `COleSafeArray` 개체에 복사할 수 있습니다.

*vtSrc*<br/>
새 `COleSafeArray` 개체의 VARTYPE입니다.

*psaSrc*<br/>
새 `COleSafeArray` 개체에 `SAFEARRAY` 복사할 a에 대한 포인터입니다.

*varSrc*<br/>
새 `COleSafeArray` `VARIANT` 개체에 복사할 기존 또는 `COleVariant` 개체입니다.

*pSrc*<br/>
새 `VARIANT` `COleSafeArray` 개체에 복사할 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이러한 생성자는 모두 새 `COleSafeArray` 개체를 만듭니다. 매개 변수가 없는 경우 `COleSafeArray` 빈 개체가 생성됩니다(VT_EMPTY). `COleSafeArray` VARTYPE이 암시적으로 알려진 다른 배열에서 복사되는 `COleSafeArray`경우(a . `COleVariant`또는) `VARIANT`소스 배열의 VARTYPE이 유지되며 지정할 필요가 없습니다. `COleSafeArray` VARTYPE을 알 수 없는 다른 배열에서`SAFEARRAY`복사된 경우 () varTYPE을 *vtSrc* 매개 변수에 지정해야 합니다.

오류가 발생하면 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException을](../../mfc/reference/coleexception-class.md)throw합니다.

## <a name="colesafearraycopy"></a><a name="copy"></a>COle세이프어레이::복사

기존 안전 배열의 복사본을 만듭니다.

```cpp
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>매개 변수

*PPSA*<br/>
새 배열 설명기를 반환할 위치에 대한 포인터입니다.

### <a name="remarks"></a>설명

오류가 발생하면 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException을](../../mfc/reference/coleexception-class.md)throw합니다.

## <a name="colesafearraycreate"></a><a name="create"></a>COleSafeArray::만들기

배열에 대한 데이터를 할당하고 초기화합니다.

```cpp
void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    DWORD* rgElements);

void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    SAFEARRAYBOUND* rgsabounds);
```

### <a name="parameters"></a>매개 변수

*vtSrc*<br/>
배열의 기본 형식(즉, 배열의 각 요소의 VARTYPE)입니다. VARTYPE은 변형 형식의 하위 집합으로 제한됩니다. VT_ARRAY VT_BYREF 플래그를 설정할 수 없습니다. VT_EMPTY 및 VT_NULL 배열에 대 한 유효한 기본 형식이 아닙니다. 다른 모든 유형은 합법적입니다.

*dwDims*<br/>
배열의 차원 수입니다. 이 배열은 [Redim](#redim).

*rgElements*<br/>
배열의 각 차원에 대한 요소 수의 배열에 대한 포인터입니다.

*rgsabounds*<br/>
배열에 할당할 경계 벡터(각 차원에 대해 하나씩)를 포인터합니다.

### <a name="remarks"></a>설명

이 함수는 필요한 경우 현재 배열 데이터를 지웁히 지웁습니다. 오류가 발생하면 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)을 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraycreateonedim"></a><a name="createonedim"></a>COleSafeArray::CreateOneDim

새 1차원 `COleSafeArray` 개체를 만듭니다.

```cpp
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>매개 변수

*vtSrc*<br/>
배열의 기본 형식(즉, 배열의 각 요소의 VARTYPE)입니다.

*dwElements*<br/>
배열의 요소 수입니다. [ResizeOneDim](#resizeonedim).

*pvSrcData*<br/>
배열에 복사할 데이터에 대한 포인터입니다.

*nL바운드*<br/>
배열의 하한입니다.

### <a name="remarks"></a>설명

함수는 포인터 *pvSrcData가* NULL이 아닌 경우 지정된 데이터를 복사하여 배열에 대한 데이터를 할당하고 초기화합니다.

오류가 발생하면 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)을 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

## <a name="colesafearraydestroy"></a><a name="destroy"></a>콜레세이프어레이::D에스트로이

기존 배열 설명자와 배열의 모든 데이터를 삭제합니다.

```cpp
void Destroy();
```

### <a name="remarks"></a>설명

개체가 배열에 저장되면 각 개체가 해제됩니다. 오류가 발생하면 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException을](../../mfc/reference/coleexception-class.md)throw합니다.

## <a name="colesafearraydestroydata"></a><a name="destroydata"></a>콜레세이프어레이::D에스트로이데이터

안전한 배열의 모든 데이터를 삭제합니다.

```cpp
void DestroyData();
```

### <a name="remarks"></a>설명

개체가 배열에 저장되면 각 개체가 해제됩니다. 오류가 발생하면 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException을](../../mfc/reference/coleexception-class.md)throw합니다.

## <a name="colesafearraydestroydescriptor"></a><a name="destroydescriptor"></a>COleSafeArray::D에스트로이 스크립트

안전 배열의 설명자가 삭제됩니다.

```cpp
void DestroyDescriptor();
```

### <a name="remarks"></a>설명

오류가 발생하면 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException을](../../mfc/reference/coleexception-class.md)throw합니다.

## <a name="colesafearraydetach"></a><a name="detach"></a>COleSafeArray::D에타치

`VARIANT` 개체에서 데이터를 분리합니다. `COleSafeArray`

```
VARIANT Detach();
```

### <a name="return-value"></a>Return Value

개체의 `VARIANT` 기본 `COleSafeArray` 값입니다.

### <a name="remarks"></a>설명

이 함수는 개체의 VARTYPE을 VT_EMPTY 설정하여 안전한 배열로 데이터를 분리합니다. Windows 함수 [VariantClear를](/windows/win32/api/oleauto/nf-oleauto-variantclear)호출하여 배열을 해제하는 것은 호출자의 책임입니다.

오류가 발생하면 함수는 [COleException](../../mfc/reference/coleexception-class.md)을 throw합니다.

### <a name="example"></a>예제

  [COleSafeArray::PutElement에](#putelement)대한 예제를 참조하십시오.

## <a name="colesafearraygetbytearray"></a><a name="getbytearray"></a>COleSafeArray::GetByteArray

안전 배열의 내용을 `CByteArray`에 복사합니다.

```cpp
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>매개 변수

*바이트*<br/>
[CByteArray](../../mfc/reference/cbytearray-class.md) 개체에 대한 참조입니다.

## <a name="colesafearraygetdim"></a><a name="getdim"></a>COle세이프어레이: 겟딤

개체의 차원 수를 반환합니다. `COleSafeArray`

```
DWORD GetDim();
```

### <a name="return-value"></a>Return Value

안전 배열의 차원 수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraygetelement"></a><a name="getelement"></a>COle세이프어레이::겟엘리먼트

안전 배열의 단일 요소를 검색합니다.

```cpp
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>매개 변수

*rg인덱스*<br/>
각 배열 차원의 인덱스 배열에 대한 포인터입니다.

*pvData*<br/>
배열의 요소를 배치할 위치에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 함수는 요소를 `SafeArrayLock` `SafeArrayUnlock` 검색하기 전과 후에 windows 함수를 자동으로 호출합니다. 데이터 요소가 문자열, 개체 또는 변형인 경우 함수는 올바른 방식으로 요소를 복사합니다. 매개 변수 *pvData* 요소를 포함 할 수있는 충분한 버퍼를 가리커야한다.

오류가 발생하면 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException을](../../mfc/reference/coleexception-class.md)throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

## <a name="colesafearraygetelemsize"></a><a name="getelemsize"></a>COleSafeArray::GetElemSize

개체에서 요소의 크기를 검색합니다. `COleSafeArray`

```
DWORD GetElemSize();
```

### <a name="return-value"></a>Return Value

안전 배열 요소의 크기(바이트)입니다.

## <a name="colesafearraygetlbound"></a><a name="getlbound"></a>COle세이프어레이::겟바운드

개체의 모든 차원에 대해 `COleSafeArray` 하한을 반환합니다.

```cpp
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>매개 변수

*dwDim*<br/>
하한을 얻을 수 있는 배열 차원입니다.

*pL바운드*<br/>
하한을 반환하는 위치에 대한 포인터입니다.

### <a name="remarks"></a>설명

오류가 발생하면 함수는 [COleException](../../mfc/reference/coleexception-class.md)을 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

## <a name="colesafearraygetonedimsize"></a><a name="getonedimsize"></a>콜레세이프어레이::겟원딤사이즈

1차원 `COleSafeArray` 개체의 요소 수를 반환합니다.

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>Return Value

1차원 안전 배열의 요소 수입니다.

### <a name="example"></a>예제

  [COleSafeArray::CreateOneDim에](#createonedim)대한 예제를 참조하십시오.

## <a name="colesafearraygetubound"></a><a name="getubound"></a>COleSafeArray::GetU바운드

안전 배열의 모든 차원에 대한 상한을 반환합니다.

```cpp
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>매개 변수

*dwDim*<br/>
상한을 얻을 수 있는 배열 차원입니다.

*푸바운드 (것)와*<br/>
상한을 반환하는 위치에 대한 포인터입니다.

### <a name="remarks"></a>설명

오류가 발생하면 함수는 [COleException](../../mfc/reference/coleexception-class.md)을 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

## <a name="colesafearraylock"></a><a name="lock"></a>COle세이프어레이::잠금

배열의 잠금 수를 증분하고 배열 설명자의 배열 데이터에 대한 포인터를 배치합니다.

```cpp
void Lock();
```

### <a name="remarks"></a>설명

오류시 [COleException](../../mfc/reference/coleexception-class.md).

배열 설명자의 포인터는 호출될 `Unlock` 때까지 유효합니다. 호출은 `Lock` 중첩될 수 있습니다. 동일한 수의 `Unlock` 호출이 필요합니다.

배열은 잠겨 있는 동안삭제할 수 없습니다.

## <a name="colesafearrayoperator-lpcvariant"></a><a name="operator_lpcvariant"></a>COleSafeArray::연산자 LPCVARIANT

이 캐스팅 연산자에게 `VARIANT` 호출하여 `COleSafeArray` 이 개체의 기본 구조에 액세스합니다.

```
operator LPCVARIANT() const;
```

## <a name="colesafearrayoperator-lpvariant"></a><a name="operator_lpvariant"></a>COleSafeArray::연산자 LPVARIANT

이 캐스팅 연산자에게 `VARIANT` 호출하여 `COleSafeArray` 이 개체의 기본 구조에 액세스합니다.

```
operator LPVARIANT();
```

### <a name="remarks"></a>설명

이 함수에서 반환되는 `VARIANT` 포인터에 의해 액세스되는 구조의 값을 변경하면 `COleSafeArray` 이 개체의 값이 변경됩니다.

## <a name="colesafearrayoperator-"></a><a name="operator_eq"></a>COleSafeArray::연산자 =

이러한 오버로드된 할당 연산자는 `COleSafeArray` 소스 값을 이 개체에 복사합니다.

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>설명

각 연산자에 대한 간략한 설명은 다음과 같습니다.

- **연산자** *=(saSrc)* **)** 기존 `COleSafeArray` 개체를 이 개체에 복사합니다.

- **연산자** *=(varSrc)* **)** 기존 `VARIANT` 또는 `COleVariant` 배열을 이 개체에 복사합니다.

- **연산자** *=(pSrc)* **)** `VARIANT` *pSrc에서* 액세스하는 배열 개체를 이 개체에 복사합니다.

## <a name="colesafearrayoperator-"></a><a name="operator_eq_eq"></a>COleSafeArray::연산자 ==

이 연산자는 두`SAFEARRAY`배열(, `COleSafeArray` 또는 `VARIANT` `COleVariant`배열)을 비교하고 같으면 0이 아닌 것을 반환합니다. 그렇지 않으면 0.

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>설명

두 배열은 차원 수가 같고 각 차원의 크기가 같고 요소 값이 같으면 동일합니다.

## <a name="colesafearrayoperator-ltlt"></a><a name="operator_lt_lt"></a>COleSafeArray::연산자&lt;&lt;

`COleSafeArray` 삽입(<<) 연산자는 `COleSafeArray` 개체의 진단 덤프 및 아카이브에 저장을 지원합니다.

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

## <a name="colesafearrayptrofindex"></a><a name="ptrofindex"></a>코올세이프어레이::P트로오브인덱스

인덱스 값에 의해 지정 된 요소에 대 한 포인터를 반환 합니다.

```cpp
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>매개 변수

*rg인덱스*<br/>
배열의 요소를 식별하는 인덱스 값의 배열입니다. 요소에 대한 모든 인덱스를 지정해야 합니다.

*ppvData*<br/>
반환시 *rgIndices의*값으로 식별 된 요소에 대한 포인터 .

## <a name="colesafearrayputelement"></a><a name="putelement"></a>콜레세이프어레이::PutElement

단일 요소를 배열에 할당합니다.

```cpp
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>매개 변수

*rg인덱스*<br/>
각 배열 차원의 인덱스 배열에 대한 포인터입니다.

*pvData*<br/>
배열에 할당할 데이터에 대한 포인터입니다. VT_DISPATCH, VT_UNKNOWN 및 VT_BSTR 변형 형식은 포인터이며 다른 수준의 간접이 필요하지 않습니다.

### <a name="remarks"></a>설명

이 함수는 요소를 할당하기 전과 후에 Windows 함수 [SafeArrayLock](/windows/win32/api/oleauto/nf-oleauto-safearraylock) 및 [SafeArrayUnlock를](/windows/win32/api/oleauto/nf-oleauto-safearrayunlock) 자동으로 호출합니다. 데이터 요소가 문자열, 개체 또는 Variant이면 함수는 이를 올바르게 복사하고 기존 요소가 문자열, 개체 또는 Variant이면 제대로 지워집니다.

배열에는 여러 잠금이 있을 수 있으므로 다른 작업에 의해 배열이 잠긴 동안 요소를 배열에 삽입할 수 있습니다.

오류가 발생하면 함수는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException을](../../mfc/reference/coleexception-class.md)throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

## <a name="colesafearrayredim"></a><a name="redim"></a>콜레세이프어레이::레임

안전 배열의 가장 중요하지 않은(가장 오른쪽) 바인딩을 변경합니다.

```cpp
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>매개 변수

*psabound뉴*<br/>
새 배열 바인딩을 포함하는 새 안전 배열 바인딩 구조에 대한 포인터입니다. 배열의 가장 중요한 차원만 변경할 수 있습니다.

### <a name="remarks"></a>설명

오류가 발생하면 함수는 [COleException](../../mfc/reference/coleexception-class.md)을 throw합니다.

## <a name="colesafearrayresizeonedim"></a><a name="resizeonedim"></a>콜레세이프어레이::리사이즈원딤

1차원 `COleSafeArray` 개체의 요소 수를 변경합니다.

```cpp
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>매개 변수

*dwElements*<br/>
1차원 안전 배열의 요소 수입니다.

### <a name="remarks"></a>설명

오류가 발생하면 함수는 [COleException](../../mfc/reference/coleexception-class.md)을 throw합니다.

### <a name="example"></a>예제

  [COleSafeArray::CreateOneDim에](#createonedim)대한 예제를 참조하십시오.

## <a name="colesafearrayunaccessdata"></a><a name="unaccessdata"></a>COleSafeArray::액세스 해제 데이터

배열의 잠금 수를 삭제하고 `AccessData`에서 검색한 포인터를 무효화합니다.

```cpp
void UnaccessData();
```

### <a name="remarks"></a>설명

오류가 발생하면 함수는 [COleException](../../mfc/reference/coleexception-class.md)을 throw합니다.

### <a name="example"></a>예제

  [COleSafeArray::AccessData에](#accessdata)대한 예제를 참조하십시오.

## <a name="colesafearrayunlock"></a><a name="unlock"></a>COleSafeArray::잠금 해제

배열을 해제하거나 크기를 조정할 수 있도록 배열의 잠금 수를 감소시입니다.

```cpp
void Unlock();
```

### <a name="remarks"></a>설명

이 함수는 배열의 데이터에 대한 액세스가 완료된 후 호출됩니다. 오류시 [COleException](../../mfc/reference/coleexception-class.md).

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COle변형 클래스](../../mfc/reference/colevariant-class.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)<br/>
[C데이터베이스 클래스](../../mfc/reference/cdatabase-class.md)<br/>
