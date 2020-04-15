---
title: C스트링엘리먼트트레이스클래스
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
ms.openlocfilehash: 32980e19443cb17a3a688c85ff21195c60ed2124
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330596"
---
# <a name="cstringelementtraitsi-class"></a>C스트링엘리먼트트레이스클래스

이 클래스는 컬렉션 클래스 개체에 저장된 문자열과 관련된 정적 함수를 제공합니다. [CStringElementTraits와](../../atl/reference/cstringelementtraits-class.md)유사하지만 대/소문자를 구분하지 않은 비교를 수행합니다.

## <a name="syntax"></a>구문

```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>
class CStringElementTraitsI : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션에 저장할 데이터 유형입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[CStringElementTraitsI::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가하는 데 사용할 데이터 형식입니다.|
|[C스트링엘리먼트 해협::OUTARGTYPE](#outargtype)|컬렉션 클래스 개체에서 요소를 검색하는 데 사용할 데이터 형식입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C스트링요소해협::비교요소](#compareelements)|이 정적 함수를 호출하여 두 문자열 요소를 같음으로 비교하고 대/소문자 차이를 무시합니다.|
|[C스트링요소해협::비교요소정렬](#compareelementsordered)|이 정적 함수를 호출하여 대/소문자 차이를 무시하고 두 문자열 요소를 비교합니다.|
|[C스트링요소해협::해시](#hash)|이 정적 함수를 호출하여 지정된 문자열 요소에 대한 해시 값을 계산합니다.|

## <a name="remarks"></a>설명

이 클래스는 문자열을 비교하고 해시 값을 만들기 위한 정적 함수를 제공합니다. 이러한 함수는 컬렉션 클래스를 사용하여 문자열 기반 데이터를 저장할 때 유용합니다. 문자열 개체를 참조로 처리해야 할 경우 [CStringRefElementTraits를](../../atl/reference/cstringrefelementtraits-class.md) 사용합니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringElementTraitsI`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="cstringelementtraitsicompareelements"></a><a name="compareelements"></a>C스트링요소해협::비교요소

이 정적 함수를 호출하여 두 문자열 요소를 같음으로 비교하고 대/소문자 차이를 무시합니다.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 문자열 요소입니다.

*str2*<br/>
두 번째 문자열 요소입니다.

### <a name="return-value"></a>Return Value

요소가 같으면 true를 반환하고 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

비교는 대/소문자를 구분하지 않습니다.

## <a name="cstringelementtraitsicompareelementsordered"></a><a name="compareelementsordered"></a>C스트링요소해협::비교요소정렬

이 정적 함수를 호출하여 대/소문자 차이를 무시하고 두 문자열 요소를 비교합니다.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 문자열 요소입니다.

*str2*<br/>
두 번째 문자열 요소입니다.

### <a name="return-value"></a>Return Value

문자열이 동일한 경우 0, *str1이 str2보다* < 경우 0이면 0이거나 *str1이* *str2보다*큰 경우 0을 >. *str2* [CStringT::비교](../../atl-mfc-shared/reference/cstringt-class.md#compare) 메서드는 비교를 수행하는 데 사용됩니다.

### <a name="remarks"></a>설명

비교는 대/소문자를 구분하지 않습니다.

## <a name="cstringelementtraitsihash"></a><a name="hash"></a>C스트링요소해협::해시

이 정적 함수를 호출하여 지정된 문자열 요소에 대한 해시 값을 계산합니다.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
문자열 요소입니다.

### <a name="return-value"></a>Return Value

문자열의 내용을 사용하여 계산된 해시 값을 반환합니다.

## <a name="cstringelementtraitsiinargtype"></a><a name="inargtype"></a>CStringElementTraitsI::INARGTYPE

컬렉션 클래스 개체에 요소를 추가하는 데 사용할 데이터 형식입니다.

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsioutargtype"></a><a name="outargtype"></a>C스트링엘리먼트 해협::OUTARGTYPE

컬렉션 클래스 개체에서 요소를 검색하는 데 사용할 데이터 형식입니다.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>참고 항목

[CElementTraitsBase 클래스](../../atl/reference/celementtraitsbase-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CStringElementTraits 클래스](../../atl/reference/cstringelementtraits-class.md)
