---
title: CStringElementTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
ms.openlocfilehash: 078cfd5ff93bfcd8acc747904ea05e6a2e762bc1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330616"
---
# <a name="cstringelementtraits-class"></a>CStringElementTraits 클래스

이 클래스는 개체를 저장하는 `CString` 컬렉션 클래스에서 사용되는 정적 함수를 제공합니다.

## <a name="syntax"></a>구문

```
template <typename T>
class CStringElementTraits
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션에 저장할 데이터 유형입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[CString요소특성::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가하는 데 사용할 데이터 형식입니다.|
|[C스트링요소특성::아웃라그타입](#outargtype)|컬렉션 클래스 개체에서 요소를 검색하는 데 사용할 데이터 형식입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C스트링요소특성::비교요소](#compareelements)|(정적) 이 함수를 호출하여 두 문자열 요소를 같음으로 비교합니다.|
|[CString요소 특성::비교요소정렬](#compareelementsordered)|(정적) 이 함수를 호출하여 두 문자열 요소를 비교합니다.|
|[C스트링요소::복사 요소](#copyelements)|(정적) 컬렉션 클래스 개체에 저장된 요소를 복사하려면 `CString` 이 함수를 호출합니다.|
|[C스트링요소(약):해시](#hash)|(정적) 지정된 문자열 요소에 대한 해시 값을 계산하려면 이 함수를 호출합니다.|
|[CString요소 특성::재배치요소](#relocateelements)|(정적) 이 함수를 호출하여 컬렉션 클래스 개체에 저장된 요소를 재배치합니다. `CString`|

## <a name="remarks"></a>설명

이 클래스는 문자열을 복사, 이동 및 비교하고 해시 값을 만들기 위한 정적 함수를 제공합니다. 이러한 함수는 컬렉션 클래스를 사용하여 문자열 기반 데이터를 저장할 때 유용합니다. 대/소문자를 구분하지 않는 비교가 필요한 경우 [CStringElementTraitsI를](../../atl/reference/cstringelementtraitsi-class.md) 사용합니다. 문자열 개체를 참조로 처리할 때 [CStringRefElementTraits를](../../atl/reference/cstringrefelementtraits-class.md) 사용합니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** cstringt.h

## <a name="cstringelementtraitscompareelements"></a><a name="compareelements"></a>C스트링요소특성::비교요소

이 정적 함수를 호출하여 두 문자열 요소를 같음으로 비교합니다.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 문자열 요소입니다.

*str2*<br/>
두 번째 문자열 요소입니다.

### <a name="return-value"></a>Return Value

요소가 같으면 true를 반환하고 그렇지 않으면 false를 반환합니다.

## <a name="cstringelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>CString요소 특성::비교요소정렬

이 정적 함수를 호출하여 두 문자열 요소를 비교합니다.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 문자열 요소입니다.

*str2*<br/>
두 번째 문자열 요소입니다.

### <a name="return-value"></a>Return Value

문자열이 동일한 경우 0, *str1이 str2보다* < 경우 0이면 0이거나 *str1이* *str2보다*큰 경우 0을 >. *str2* [CStringT::비교](../../atl-mfc-shared/reference/cstringt-class.md#compare) 메서드는 비교를 수행하는 데 사용됩니다.

## <a name="cstringelementtraitscopyelements"></a><a name="copyelements"></a>C스트링요소::복사 요소

이 정적 함수를 `CString` 호출하여 컬렉션 클래스 개체에 저장된 요소를 복사합니다.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>매개 변수

*pDest*<br/>
복사된 데이터를 수신할 첫 번째 요소에 대한 포인터입니다.

*pSrc*<br/>
복사할 첫 번째 요소에 대한 포인터입니다.

*n엘리먼츠*<br/>
복사할 요소의 수입니다.

### <a name="remarks"></a>설명

원본 및 대상 요소가 겹치지 않아야 합니다.

## <a name="cstringelementtraitshash"></a><a name="hash"></a>C스트링요소(약):해시

이 정적 함수를 호출하여 지정된 문자열 요소에 대한 해시 값을 계산합니다.

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
문자열 요소입니다.

### <a name="return-value"></a>Return Value

문자열의 내용을 사용하여 계산된 해시 값을 반환합니다.

## <a name="cstringelementtraitsinargtype"></a><a name="inargtype"></a>CString요소특성::INARGTYPE

컬렉션 클래스 개체에 요소를 추가하는 데 사용할 데이터 형식입니다.

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsoutargtype"></a><a name="outargtype"></a>C스트링요소특성::아웃라그타입

컬렉션 클래스 개체에서 요소를 검색하는 데 사용할 데이터 형식입니다.

```
typedef T& OUTARGTYPE;
```

## <a name="cstringelementtraitsrelocateelements"></a><a name="relocateelements"></a>CString요소 특성::재배치요소

이 정적 함수를 `CString` 호출하여 컬렉션 클래스 개체에 저장된 요소를 재배치합니다.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>매개 변수

*pDest*<br/>
재배치된 데이터를 수신할 첫 번째 요소에 대한 포인터입니다.

*pSrc*<br/>
재배치할 첫 번째 요소에 대한 포인터입니다.

*n엘리먼츠*<br/>
재배치할 요소 의 수입니다.

### <a name="remarks"></a>설명

이 정적 함수는 대부분의 데이터 형식에 충분한 [memmove를](../../c-runtime-library/reference/memmove-wmemmove.md)호출합니다. 이동 중인 개체에 자체 멤버에 대한 포인터가 포함되어 있는 경우 이 정적 함수를 재정의해야 합니다.

## <a name="see-also"></a>참고 항목

[CElementTraitsBase 클래스](../../atl/reference/celementtraitsbase-class.md)<br/>
[C스트링엘리먼트트레이스클래스](../../atl/reference/cstringelementtraitsi-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
