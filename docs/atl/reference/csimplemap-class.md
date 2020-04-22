---
title: CSimpleMap 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayElementType
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayKeyType
- ATLSIMPCOLL/ATL::CSimpleMap::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::Add
- ATLSIMPCOLL/ATL::CSimpleMap::FindKey
- ATLSIMPCOLL/ATL::CSimpleMap::FindVal
- ATLSIMPCOLL/ATL::CSimpleMap::GetKeyAt
- ATLSIMPCOLL/ATL::CSimpleMap::GetSize
- ATLSIMPCOLL/ATL::CSimpleMap::GetValueAt
- ATLSIMPCOLL/ATL::CSimpleMap::Lookup
- ATLSIMPCOLL/ATL::CSimpleMap::Remove
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleMap::ReverseLookup
- ATLSIMPCOLL/ATL::CSimpleMap::SetAt
- ATLSIMPCOLL/ATL::CSimpleMap::SetAtIndex
helpviewer_keywords:
- CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
ms.openlocfilehash: eed41c2250728d257b6d303e79c3afd36a543dbb
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747647"
---
# <a name="csimplemap-class"></a>CSimpleMap 클래스

이 클래스는 간단한 매핑 배열에 대한 지원을 제공합니다.

## <a name="syntax"></a>구문

```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>
class CSimpleMap
```

#### <a name="parameters"></a>매개 변수

*TKey*<br/>
키 요소 유형입니다.

*TVal (주)*<br/>
값 요소 형식입니다.

*TEqual*<br/>
특성 개체, 형식의 `T`요소에 대 한 같음 테스트를 정의 합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[C심플맵::_ArrayElementType](#_arrayelementtype)|값 형식에 대 한 typedef입니다.|
|[C심플맵::_ArrayKeyType](#_arraykeytype)|키 유형에 대한 형식 def입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C심플맵::C심플맵](#csimplemap)|생성자입니다.|
|[CSimplemap::~CSimpleMap](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C심플맵::추가](#add)|맵 배열에 키 및 관련 값을 추가합니다.|
|[C심플맵::찾기키](#findkey)|특정 키를 찾습니다.|
|[C심플맵::찾기](#findval)|특정 값을 찾습니다.|
|[C심플맵::겟키앳](#getkeyat)|지정된 키를 검색합니다.|
|[C심플맵::겟사이즈](#getsize)|매핑 배열의 항목 수를 반환합니다.|
|[C심플맵::GetValueAt](#getvalueat)|지정된 값을 검색합니다.|
|[C심플맵::조회](#lookup)|지정된 키와 연결된 값을 반환합니다.|
|[C심플맵::제거](#remove)|키 및 일치 값을 제거합니다.|
|[C심플맵::모두 제거](#removeall)|모든 키와 값을 제거합니다.|
|[C심플맵::리무브앳](#removeat)|특정 키 및 일치 값을 제거합니다.|
|[C심플맵::리버스룩업](#reverselookup)|지정된 값과 연결된 키를 반환합니다.|
|[C심플맵::세팅](#setat)|지정된 키와 연결된 값을 설정합니다.|
|[C심플맵::SetAtIndex](#setatindex)|특정 키와 값을 설정합니다.|

## <a name="remarks"></a>설명

`CSimpleMap`지정된 형식의 `T`간단한 매핑 배열을 지원하여 키 요소및 관련 값의 정렬되지 않은 배열을 관리합니다.

매개 `TEqual` 변수는 형식의 `T`두 요소에 대한 같음 함수를 정의하는 수단을 제공합니다. [CSimpleMapEqualHelper와](../../atl/reference/csimplemapequalhelper-class.md)유사한 클래스를 만들어 지정된 배열에 대한 같음 테스트의 동작을 변경할 수 있습니다. 예를 들어 포인터 배열을 처리할 때 포인터참조 값에 따라 같음을 정의하는 것이 유용할 수 있습니다. 기본 구현은 **연산자==()를**사용합니다.

이전 `CSimpleMap` ATL 릴리스와의 호환성을 위해 두 가지 및 [CSimpleArray가](../../atl/reference/csimplearray-class.md) 제공되며 보다 완전하고 효율적인 컬렉션 구현은 [CAtlArray](../../atl/reference/catlarray-class.md) 및 [CAtlMap에서](../../atl/reference/catlmap-class.md)제공됩니다.

ATL 및 MFC의 다른 맵 컬렉션과 달리 이 클래스는 간단한 배열로 구현되며 조회 검색에는 선형 검색이 필요합니다. `CAtlMap`배열에 많은 수의 요소가 포함되어 있는 경우에 사용해야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 아시프콜.h

## <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]

## <a name="csimplemapadd"></a><a name="add"></a>C심플맵::추가

맵 배열에 키 및 관련 값을 추가합니다.

```
BOOL Add(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키입니다.

*발*<br/>
연결된 값입니다.

### <a name="return-value"></a>Return Value

키와 값이 성공적으로 추가된 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

각 키 와 값 쌍 추가로 인해 매핑 배열 메모리가 해제되고 다시 할당되어 각 키에 대한 데이터가 항상 연속적으로 저장되도록 합니다. 즉, 두 번째 키 요소는 항상 메모리의 첫 번째 키 요소를 직접 따릅니다.

## <a name="csimplemap_arrayelementtype"></a><a name="_arrayelementtype"></a>C심플맵::_ArrayElementType

키 형식에 대한 형식 def입니다.

```
typedef TVal _ArrayElementType;
```

## <a name="csimplemap_arraykeytype"></a><a name="_arraykeytype"></a>C심플맵::_ArrayKeyType

값 형식에 대한 형식 def입니다.

```
typedef TKey _ArrayKeyType;
```

## <a name="csimplemapcsimplemap"></a><a name="csimplemap"></a>C심플맵::C심플맵

생성자입니다.

```
CSimpleMap();
```

### <a name="remarks"></a>설명

데이터 멤버를 초기화합니다.

## <a name="csimplemapcsimplemap"></a><a name="dtor"></a>CSimplemap::~CSimpleMap

소멸자입니다.

```
~CSimpleMap();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제합니다.

## <a name="csimplemapfindkey"></a><a name="findkey"></a>C심플맵::찾기키

특정 키를 찾습니다.

```
int FindKey(const TKey& key) const;
```

### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 키입니다.

### <a name="return-value"></a>Return Value

발견 되면 키 인덱스를 반환하고 그렇지 않으면 -1을 반환합니다.

## <a name="csimplemapfindval"></a><a name="findval"></a>C심플맵::찾기

특정 값을 찾습니다.

```
int FindVal(const TVal& val) const;
```

### <a name="parameters"></a>매개 변수

*발*<br/>
검색할 값입니다.

### <a name="return-value"></a>Return Value

값이 발견되면 값의 인덱스를 반환하고 그렇지 않으면 -1을 반환합니다.

## <a name="csimplemapgetkeyat"></a><a name="getkeyat"></a>C심플맵::겟키앳

지정된 인덱스에서 키를 검색합니다.

```
TKey& GetKeyAt(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
반환할 키의 인덱스입니다.

### <a name="return-value"></a>Return Value

*nIndex*에서 참조하는 키를 반환합니다.

### <a name="remarks"></a>설명

*nIndex에서* 전달된 인덱스는 반환 값이 의미 있는 경우 유효해야 합니다.

## <a name="csimplemapgetsize"></a><a name="getsize"></a>C심플맵::겟사이즈

매핑 배열의 항목 수를 반환합니다.

```
int GetSize() const;
```

### <a name="return-value"></a>Return Value

매핑 배열에서 항목 수(키와 값은 하나의 항목)를 반환합니다.

## <a name="csimplemapgetvalueat"></a><a name="getvalueat"></a>C심플맵::GetValueAt

특정 인덱스에서 값을 검색합니다.

```
TVal& GetValueAt(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
반환할 값의 인덱스입니다.

### <a name="return-value"></a>Return Value

*nIndex*에서 참조하는 값을 반환합니다.

### <a name="remarks"></a>설명

*nIndex에서* 전달된 인덱스는 반환 값이 의미 있는 경우 유효해야 합니다.

## <a name="csimplemaplookup"></a><a name="lookup"></a>C심플맵::조회

지정된 키와 연결된 값을 반환합니다.

```
TVal Lookup(const TKey& key) const;
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키입니다.

### <a name="return-value"></a>Return Value

연결된 값을 반환합니다. 일치하는 키가 발견되지 않으면 NULL이 반환됩니다.

## <a name="csimplemapremove"></a><a name="remove"></a>C심플맵::제거

키 및 일치 값을 제거합니다.

```
BOOL Remove(const TKey& key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키입니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 키 및 일치 값이 성공적으로 제거된 경우 TRUE를 반환합니다.

## <a name="csimplemapremoveall"></a><a name="removeall"></a>C심플맵::모두 제거

모든 키와 값을 제거합니다.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>설명

매핑 배열 개체에서 모든 키와 값을 제거합니다.

## <a name="csimplemapremoveat"></a><a name="removeat"></a>C심플맵::리무브앳

지정된 인덱스에서 키 및 관련 값을 제거합니다.

```
BOOL RemoveAt(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
제거할 키 및 관련 값의 인덱스입니다.

### <a name="return-value"></a>Return Value

지정된 인덱스가 잘못된 인덱스인 경우 TRUE를 반환합니다.

## <a name="csimplemapreverselookup"></a><a name="reverselookup"></a>C심플맵::리버스룩업

지정된 값과 연결된 키를 반환합니다.

```
TKey ReverseLookup(const TVal& val) const;
```

### <a name="parameters"></a>매개 변수

*발*<br/>
값입니다.

### <a name="return-value"></a>Return Value

연결된 키를 반환합니다. 일치하는 키가 발견되지 않으면 NULL이 반환됩니다.

## <a name="csimplemapsetat"></a><a name="setat"></a>C심플맵::세팅

지정된 키와 연결된 값을 설정합니다.

```
BOOL SetAt(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키입니다.

*발*<br/>
할당할 새 값입니다.

### <a name="return-value"></a>Return Value

키가 발견되고 값이 성공적으로 변경된 경우 TRUE를 반환합니다.

## <a name="csimplemapsetatindex"></a><a name="setatindex"></a>C심플맵::SetAtIndex

지정된 인덱스에서 키와 값을 설정합니다.

```
BOOL SetAtIndex(
    int nIndex,
    const TKey& key,
    const TVal& val);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
변경할 키와 값 쌍을 참조하는 인덱스입니다.

*key*<br/>
새 키입니다.

*발*<br/>
새 값입니다.

### <a name="return-value"></a>Return Value

인덱스가 유효하지 않은 경우 TRUE, FALSE를 반환합니다.

### <a name="remarks"></a>설명

*nIndex*.

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)
