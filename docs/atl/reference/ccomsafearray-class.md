---
title: CComSafeArray 클래스
ms.date: 05/06/2019
f1_keywords:
- CComSafeArray
- ATLSAFE/ATL::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::Add
- ATLSAFE/ATL::CComSafeArray::Attach
- ATLSAFE/ATL::CComSafeArray::CopyFrom
- ATLSAFE/ATL::CComSafeArray::CopyTo
- ATLSAFE/ATL::CComSafeArray::Create
- ATLSAFE/ATL::CComSafeArray::Destroy
- ATLSAFE/ATL::CComSafeArray::Detach
- ATLSAFE/ATL::CComSafeArray::GetAt
- ATLSAFE/ATL::CComSafeArray::GetCount
- ATLSAFE/ATL::CComSafeArray::GetDimensions
- ATLSAFE/ATL::CComSafeArray::GetLowerBound
- ATLSAFE/ATL::CComSafeArray::GetSafeArrayPtr
- ATLSAFE/ATL::CComSafeArray::GetType
- ATLSAFE/ATL::CComSafeArray::GetUpperBound
- ATLSAFE/ATL::CComSafeArray::IsSizable
- ATLSAFE/ATL::CComSafeArray::MultiDimGetAt
- ATLSAFE/ATL::CComSafeArray::MultiDimSetAt
- ATLSAFE/ATL::CComSafeArray::Resize
- ATLSAFE/ATL::CComSafeArray::SetAt
- ATLSAFE/ATL::CComSafeArray::m_psa
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
ms.openlocfilehash: d1e72d364858ea31541d574ed77bdc8ccca7d748
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327396"
---
# <a name="ccomsafearray-class"></a>CComSafeArray 클래스

이 클래스는 구조의 `SAFEARRAY` 래퍼입니다.

## <a name="syntax"></a>구문

```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
배열에 저장할 데이터의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComSafeArray::CComSafeArray](#ccomsafearray)|생성자입니다.|
|[CComSafeArray::~CComSafeArray](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComSafeArray::추가](#add)|에 하나 이상의 요소 `SAFEARRAY` 또는 구조를 추가합니다. `CComSafeArray`|
|[CComSafeArray::연결](#attach)|`SAFEARRAY` 구조를 오브젝트에 연결합니다. `CComSafeArray`|
|[CComSafeArray::복사에서](#copyfrom)|`SAFEARRAY` 구조체의 내용을 개체에 복사합니다. `CComSafeArray`|
|[CComSafeArray::복사토](#copyto)|`CComSafeArray` 개체의 복사본을 만듭니다.|
|[개체를 만들려면](#create)|`CComSafeArray` 개체를 만듭니다.|
|[CComSafeArray::Destroy](#destroy)|`CComSafeArray` 개체를 제거합니다.|
|[CComSafeArray::D에타치](#detach)|개체에서 `SAFEARRAY` 분리합니다. `CComSafeArray`|
|[CComSafeArray::GetAt](#getat)|1차원 배열에서 단일 요소를 검색합니다.|
|[CComSafeArray::겟카운트](#getcount)|배열의 요소 수를 반환합니다.|
|[CComSafeArray::GetDimensions](#getdimensions)|배열의 차원 수를 반환합니다.|
|[CComSafeArray::GetLower바운드](#getlowerbound)|배열의 지정된 차원에 대한 하한을 반환합니다.|
|[CComSafeArray::GetSafeArrayPtr](#getsafearrayptr)|`m_psa` 데이터 멤버의 주소를 반환합니다.|
|[CComSafeArray::GetType](#gettype)|배열에 저장된 데이터의 형식을 반환합니다.|
|[CComSafeArray::GetUpper바운드](#getupperbound)|배열의 모든 차원에 대한 상한을 반환합니다.|
|[CComSafeArray:::이시화 가능](#issizable)|`CComSafeArray` 개체의 크기를 조정할 수 있는지 테스트합니다.|
|[CComSafeArray::멀티딤게타](#multidimgetat)|다차원 배열에서 단일 요소를 검색합니다.|
|[CComSafeArray::멀티딤셋](#multidimsetat)|다차원 배열의 요소 값을 설정합니다.|
|[CComSafeArray::크기 조정](#resize)|`CComSafeArray` 개체의 크기를 조정합니다.|
|[CComSafeArray::SetAt](#setat)|1차원 배열의 요소 값을 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CComSafeArray::연산자 LPSAFEARRAY](#operator_lpsafearray)|값을 포인터에 캐스팅합니다. `SAFEARRAY`|
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|배열에서 요소를 검색합니다.|
|[CComSafeArray::연산자 =](#operator_eq)|대입 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComSafeArray::m_psa](#m_psa)|이 데이터 멤버는 구조의 주소를 보유합니다. `SAFEARRAY`|

## <a name="remarks"></a>설명

`CComSafeArray` 는 [SAFEARRAY Data Type](/windows/win32/api/oaidl/ns-oaidl-safearray) 클래스에 대한 래퍼를 제공합니다. 따라서 거의 모든 VARIANT 지원 형식의 1차원 및 다차원 배열을 쉽게 만들고 관리할 수 있습니다.

`CComSafeArray` 는 프로세스 간의 배열 전달을 간소화할 뿐만 아니라 상한과 하한에 대해 배열 인덱스 값을 확인하여 추가 보안을 제공합니다.

`CComSafeArray` 의 하한은 모든 사용자 정의 값에서 시작할 수 있지만 C++를 통해 액세스하는 배열에서는 0을 하한으로 사용해야 합니다. Visual Basic과 같은 다른 언어에서는 다른 경계 값(예: -10~10)을 사용할 수 있습니다.

[개체를 만들려면](#create) CComSafeArray::Create `CComSafeArray` 를 사용하고, 제거하려면 [CComSafeArray::Destroy](#destroy) 를 사용합니다.

`CComSafeArray` 는 VARIANT 데이터 형식의 다음 하위 집합을 포함할 수 있습니다.

|VARTYPE|Description|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ulonglong|
|VT_R4|float|
|VT_R8|double|
|VT_DECIMAL|decimal pointer|
|VT_VARIANT|variant pointer|
|VT_CY|Currency 데이터 형식|

## <a name="requirements"></a>요구 사항

**헤더:** atlsafe.h

## <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]

## <a name="ccomsafearrayadd"></a><a name="add"></a>CComSafeArray::추가

에 하나 이상의 요소 `SAFEARRAY` 또는 구조를 추가합니다. `CComSafeArray`

```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>매개 변수

*psaSrc*<br/>
`SAFEARRAY` 개체에 대한 포인터입니다.

*울카운트*<br/>
배열에 추가할 개체 수입니다.

*Pt*<br/>
배열에 추가할 하나 이상의 개체에 대한 포인터입니다.

*T*<br/>
배열에 추가할 개체에 대한 참조입니다.

*bCopy*<br/>
데이터 복사본을 만들어야 하는지 여부를 나타냅니다. 기본값은 TRUE입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

새 개체는 기존 `SAFEARRAY` 개체의 끝에 추가됩니다. 다차원 `SAFEARRAY` 개체에 개체를 추가하는 것은 지원되지 않습니다. 기존 개체 배열을 추가할 때 두 배열모두 동일한 형식의 요소를 포함해야 합니다.

bSTR 또는 VARIANT 형식의 요소가 배열에 추가될 때 *bCopy* 플래그가 고려됩니다. TRUE의 기본값은 요소가 배열에 추가될 때 새 복사본이 데이터로 만들어지도록 합니다.

## <a name="ccomsafearrayattach"></a><a name="attach"></a>CComSafeArray::연결

`SAFEARRAY` 구조를 오브젝트에 연결합니다. `CComSafeArray`

```
HRESULT Attach(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>매개 변수

*psaSrc*<br/>
구조에 대한 `SAFEARRAY` 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

`SAFEARRAY` 구조를 객체에 `CComSafeArray` 연결하여 기존 `CComSafeArray` 메서드를 사용할 수 있도록 합니다.

## <a name="ccomsafearrayccomsafearray"></a><a name="ccomsafearray"></a>CComSafeArray::CComSafeArray

생성자입니다.

```
CComSafeArray();
CComSafeArray(const SAFEARRAYBOUND& bound);
CComSafeArray(ULONG  ulCount, LONG lLBound = 0);
CComSafeArray(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
CComSafeArray(const CComSafeArray& saSrc);
CComSafeArray(const SAFEARRAY& saSrc);
CComSafeArray(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>매개 변수

*바인딩됨*<br/>
`SAFEARRAYBOUND` 구조입니다.

*울카운트*<br/>
배열의 요소 수입니다.

*lL바운드*<br/>
하한 값; 즉, 배열의 첫 번째 요소의 인덱스입니다.

*핀 바운드*<br/>
구조에 대한 `SAFEARRAYBOUND` 포인터입니다.

*uDims*<br/>
배열의 차원 수입니다.

*사스크 (동음이의)*<br/>
구조또는객체에대한참조입니다. `SAFEARRAY` `CComSafeArray` 두 경우 모두 생성자는 이 참조를 사용하여 배열의 복사본을 만들므로 구성 후 배열이 참조되지 않습니다.

*psaSrc*<br/>
구조에 대한 `SAFEARRAY` 포인터입니다. 생성자는 이 주소를 사용하여 배열의 복사본을 만들므로 구성 후 배열이 참조되지 않습니다.

### <a name="remarks"></a>설명

`CComSafeArray` 개체를 만듭니다.

## <a name="ccomsafearrayccomsafearray"></a><a name="dtor"></a>CComSafeArray::~CComSafeArray

소멸자입니다.

```
~CComSafeArray() throw()
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제합니다.

## <a name="ccomsafearraycopyfrom"></a><a name="copyfrom"></a>CComSafeArray::복사에서

`SAFEARRAY` 구조체의 내용을 개체에 복사합니다. `CComSafeArray`

```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>매개 변수

*ppArray*<br/>
복사할 `SAFEARRAY` 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 a의 `SAFEARRAY` 내용을 현재 `CComSafeArray` 개체에 복사합니다. 배열의 기존 내용이 대체됩니다.

## <a name="ccomsafearraycopyto"></a><a name="copyto"></a>CComSafeArray::복사토

`CComSafeArray` 개체의 복사본을 만듭니다.

```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>매개 변수

*ppArray*<br/>
새 `SAFEARRAY`를 만들 수 있는 위치에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 `CComSafeArray` 개체의 내용을 `SAFEARRAY` 구조체로 복사합니다.

## <a name="ccomsafearraycreate"></a><a name="create"></a>CComSafeArray::만들기

`CComSafeArray`을 만듭니다.

```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```

### <a name="parameters"></a>매개 변수

*핀 바운드*<br/>
`SAFEARRAYBOUND` 개체에 대한 포인터입니다.

*uDims*<br/>
배열의 차수입니다.

*울카운트*<br/>
배열의 요소 수입니다.

*lL바운드*<br/>
하한 값; 즉, 배열의 첫 번째 요소의 인덱스입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

객체는 `CComSafeArray` 기존 `SAFEARRAYBOUND` 구조와 차원 수에서 만들거나 배열의 요소 수와 하한을 지정하여 만들 수 있습니다. 배열을 C++에서 액세스하려면 하한이 0이어야 합니다. 다른 언어는 하한에 대한 다른 값을 허용할 수 있습니다(예: Visual Basic은 -10에서 10과 같은 범위의 요소가 있는 배열을 지원합니다).

## <a name="ccomsafearraydestroy"></a><a name="destroy"></a>CComSafeArray::D에스트로이

`CComSafeArray` 개체를 제거합니다.

```
HRESULT Destroy();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

기존 개체와 `CComSafeArray` 개체에 포함된 모든 데이터를 삭제합니다.

## <a name="ccomsafearraydetach"></a><a name="detach"></a>CComSafeArray::D에타치

개체에서 `SAFEARRAY` 분리합니다. `CComSafeArray`

```
LPSAFEARRAY Detach();
```

### <a name="return-value"></a>Return Value

개체에 대한 `SAFEARRAY` 포인터를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 `SAFEARRAY` 개체에서 개체를 분리합니다. `CComSafeArray`

## <a name="ccomsafearraygetat"></a><a name="getat"></a>CComSafeArray::GetAt

1차원 배열에서 단일 요소를 검색합니다.

```
T& GetAt(LONG lIndex) const;
```

### <a name="parameters"></a>매개 변수

*l인덱스*<br/>
반환할 배열의 값의 인덱스 번호입니다.

### <a name="return-value"></a>Return Value

필요한 배열 요소에 대한 참조를 반환합니다.

## <a name="ccomsafearraygetcount"></a><a name="getcount"></a>CComSafeArray::겟카운트

배열의 요소 수를 반환합니다.

```
ULONG GetCount(UINT uDim = 0) const;
```

### <a name="parameters"></a>매개 변수

*uDim*<br/>
배열 차원입니다.

### <a name="return-value"></a>Return Value

배열의 요소 수를 반환합니다.

### <a name="remarks"></a>설명

다차원 배열과 함께 사용할 경우 이 메서드는 특정 차원의 요소 수만 반환합니다.

## <a name="ccomsafearraygetdimensions"></a><a name="getdimensions"></a>CComSafeArray::GetDimensions

배열의 차원 수를 반환합니다.

```
UINT GetDimensions() const;
```

### <a name="return-value"></a>Return Value

배열의 차원 수를 반환합니다.

## <a name="ccomsafearraygetlowerbound"></a><a name="getlowerbound"></a>CComSafeArray::GetLower바운드

배열의 지정된 차원에 대한 하한을 반환합니다.

```
LONG GetLowerBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>매개 변수

*uDim*<br/>
하한을 얻을 수 있는 배열 차원입니다. 생략된 경우 기본값은 0입니다.

### <a name="return-value"></a>Return Value

하한을 반환합니다.

### <a name="remarks"></a>설명

하한이 0이면 첫 번째 요소가 요소 번호 0인 C와 같은 배열을 나타냅니다. 예를 들어 잘못된 차원 인수와 같은 오류가 발생하는 경우 `AtlThrow` 이 메서드는 오류를 설명하는 HRESULT를 호출합니다.

## <a name="ccomsafearraygetsafearrayptr"></a><a name="getsafearrayptr"></a>CComSafeArray::GetSafeArrayPtr

`m_psa` 데이터 멤버의 주소를 반환합니다.

```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```

### <a name="return-value"></a>Return Value

[CComSafeArray::m_psa](#m_psa) 데이터 멤버에 대한 포인터를 반환합니다.

## <a name="ccomsafearraygettype"></a><a name="gettype"></a>CComSafeArray::GetType

배열에 저장된 데이터의 형식을 반환합니다.

```
VARTYPE GetType() const;
```

### <a name="return-value"></a>Return Value

배열에 저장된 데이터 형식을 반환합니다.

|VARTYPE|Description|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ulonglong|
|VT_R4|float|
|VT_R8|double|
|VT_DECIMAL|decimal pointer|
|VT_VARIANT|variant pointer|
|VT_CY|Currency 데이터 형식|

## <a name="ccomsafearraygetupperbound"></a><a name="getupperbound"></a>CComSafeArray::GetUpper바운드

배열의 모든 차원에 대한 상한을 반환합니다.

```
LONG GetUpperBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>매개 변수

*uDim*<br/>
상한을 얻을 수 있는 배열 차원입니다. 생략된 경우 기본값은 0입니다.

### <a name="return-value"></a>Return Value

상한을 반환합니다. 이 값은 이 차원의 최대 유효한 인덱스인 포함입니다.

### <a name="remarks"></a>설명

예를 들어 잘못된 차원 인수와 같은 오류가 발생하는 경우 `AtlThrow` 이 메서드는 오류를 설명하는 HRESULT를 호출합니다.

## <a name="ccomsafearrayissizable"></a><a name="issizable"></a>CComSafeArray:::이시화 가능

`CComSafeArray` 개체의 크기를 조정할 수 있는지 테스트합니다.

```
bool IsSizable() const;
```

### <a name="return-value"></a>Return Value

크기를 조정할 `CComSafeArray` 수 있는 경우 TRUE를 반환하고, 할 수 없는 경우 FALSE를 반환합니다.

## <a name="ccomsafearraym_psa"></a><a name="m_psa"></a>CComSafeArray::m_psa

액세스한 `SAFEARRAY` 구조의 주소를 보유합니다.

```
LPSAFEARRAY m_psa;
```

## <a name="ccomsafearraymultidimgetat"></a><a name="multidimgetat"></a>CComSafeArray::멀티딤게타

다차원 배열에서 단일 요소를 검색합니다.

```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```

### <a name="parameters"></a>매개 변수

*알 인덱스*<br/>
배열의 각 차원에 대한 인덱스 벡터에 대한 포인터입니다. 가장 왼쪽(가장 중요한) `alIndex[0]`차원은 .

*T*<br/>
반환된 데이터에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="ccomsafearraymultidimsetat"></a><a name="multidimsetat"></a>CComSafeArray::멀티딤셋

다차원 배열의 요소 값을 설정합니다.

```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```

### <a name="parameters"></a>매개 변수

*알 인덱스*<br/>
배열의 각 차원에 대한 인덱스 벡터에 대한 포인터입니다. 가장 오른쪽(가장 중요하지 않은) 차원은 [0]입니다. `alIndex`

*T*<br/>
새 요소의 값을 지정합니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이것은 [CComSafeArray의 다차원 버전입니다:SetAt](#setat).

## <a name="ccomsafearrayoperator-"></a><a name="operator_at"></a>CComSafeArray::연산자\[\]

배열에서 요소를 검색합니다.

```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```

### <a name="parameters"></a>매개 변수

*l인덱스, nIndex*<br/>
배열에 필요한 요소의 인덱스 번호입니다.

### <a name="return-value"></a>Return Value

적절한 배열 요소를 반환합니다.

### <a name="remarks"></a>설명

[CComSafeArray::GetAt와](#getat)유사한 기능을 수행하지만 이 연산자는 단일 차원 배열에서만 작동합니다.

## <a name="ccomsafearrayoperator-"></a><a name="operator_eq"></a>CComSafeArray::연산자 =

대입 연산자입니다.

```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>매개 변수

*사스크 (동음이의)*<br/>
`CComSafeArray` 개체에 대한 참조입니다.

*psaSrc*<br/>
`SAFEARRAY` 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

배열에 저장된 데이터의 형식을 반환합니다.

## <a name="ccomsafearrayoperator-lpsafearray"></a><a name="operator_lpsafearray"></a>CComSafeArray::연산자 LPSAFEARRAY

값을 포인터에 캐스팅합니다. `SAFEARRAY`

```
operator LPSAFEARRAY() const;
```

### <a name="return-value"></a>Return Value

값을 포인터에 캐스팅합니다. `SAFEARRAY`

## <a name="ccomsafearrayresize"></a><a name="resize"></a>CComSafeArray::크기 조정

`CComSafeArray` 개체의 크기를 조정합니다.

```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```

### <a name="parameters"></a>매개 변수

*핀 바운드*<br/>
요소 수와 `SAFEARRAYBOUND` 배열의 하한에 대한 정보가 포함된 구조체에 대한 포인터입니다.

*울카운트*<br/>
크기 조정된 배열의 요청된 개체 수입니다.

*lL바운드*<br/>
하한입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 가장 오른쪽 차원만 크기를 조정합니다. FALSE로 반환되는 `IsResizable` 배열의 크기는 조정되지 않습니다.

## <a name="ccomsafearraysetat"></a><a name="setat"></a>CComSafeArray::SetAt

1차원 배열의 요소 값을 설정합니다.

```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>매개 변수

*l인덱스*<br/>
설정할 배열 요소의 인덱스 번호입니다.

*T*<br/>
지정된 요소의 새 값입니다.

*bCopy*<br/>
데이터 복사본을 만들어야 하는지 여부를 나타냅니다. 기본값은 TRUE입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

bSTR 또는 VARIANT 형식의 요소가 배열에 추가될 때 *bCopy* 플래그가 고려됩니다. TRUE의 기본값은 요소가 배열에 추가될 때 새 복사본이 데이터로 만들어지도록 합니다.

## <a name="see-also"></a>참고 항목

[SAFEARRAY Data Type](/windows/win32/api/oaidl/ns-oaidl-safearray)<br/>
[개체를 만들려면](#create)<br/>
[CComSafeArray::Destroy](#destroy)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
