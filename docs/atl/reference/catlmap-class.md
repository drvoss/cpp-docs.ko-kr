---
title: CAtlMap 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlMap
- ATLCOLL/ATL::CAtlMap
- ATLCOLL/ATL::CAtlMap::KINARGTYPE
- ATLCOLL/ATL::CAtlMap::KOUTARGTYPE
- ATLCOLL/ATL::CAtlMap::VINARGTYPE
- ATLCOLL/ATL::CAtlMap::VOUTARGTYPE
- ATLCOLL/ATL::CPair::m_key
- ATLCOLL/ATL::CPair::m_value
- ATLCOLL/ATL::CAtlMap::CAtlMap
- ATLCOLL/ATL::CAtlMap::AssertValid
- ATLCOLL/ATL::CAtlMap::DisableAutoRehash
- ATLCOLL/ATL::CAtlMap::EnableAutoRehash
- ATLCOLL/ATL::CAtlMap::GetAt
- ATLCOLL/ATL::CAtlMap::GetCount
- ATLCOLL/ATL::CAtlMap::GetHashTableSize
- ATLCOLL/ATL::CAtlMap::GetKeyAt
- ATLCOLL/ATL::CAtlMap::GetNext
- ATLCOLL/ATL::CAtlMap::GetNextAssoc
- ATLCOLL/ATL::CAtlMap::GetNextKey
- ATLCOLL/ATL::CAtlMap::GetNextValue
- ATLCOLL/ATL::CAtlMap::GetStartPosition
- ATLCOLL/ATL::CAtlMap::GetValueAt
- ATLCOLL/ATL::CAtlMap::InitHashTable
- ATLCOLL/ATL::CAtlMap::IsEmpty
- ATLCOLL/ATL::CAtlMap::Lookup
- ATLCOLL/ATL::CAtlMap::Rehash
- ATLCOLL/ATL::CAtlMap::RemoveAll
- ATLCOLL/ATL::CAtlMap::RemoveAtPos
- ATLCOLL/ATL::CAtlMap::RemoveKey
- ATLCOLL/ATL::CAtlMap::SetAt
- ATLCOLL/ATL::CAtlMap::SetOptimalLoad
- ATLCOLL/ATL::CAtlMap::SetValueAt
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
ms.openlocfilehash: 8954eeae28f13fb50643646b41c032588ecc278f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748658"
---
# <a name="catlmap-class"></a>CAtlMap 클래스

이 클래스는 맵 개체를 만들고 관리하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CAtlMap
```

#### <a name="parameters"></a>매개 변수

*K (주)*<br/>
키 요소 유형입니다.

*Ⅴ*<br/>
값 요소 형식입니다.

*크트레이스*<br/>
키 요소를 복사하거나 이동하는 데 사용되는 코드입니다. 자세한 내용은 [CElementTraits 클래스를](../../atl/reference/celementtraits-class.md) 참조하십시오.

*브이트레이스*<br/>
값 요소를 복사하거나 이동하는 데 사용되는 코드입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[카틀맵::키나르그타입](#kinargtype)|키가 입력 인수로 전달될 때 사용되는 형식|
|[카틀맵::쿠타르그타입](#koutargtype)|키가 출력 인수로 반환될 때 사용되는 형식입니다.|
|[카틀맵::비나르그타입](#vinargtype)|값이 입력 인수로 전달될 때 사용되는 형식입니다.|
|[카틀맵::부타르그타입](#voutargtype)|값이 출력 인수로 전달될 때 사용되는 형식입니다.|

### <a name="public-classes"></a>public 클래스

|속성|Description|
|----------|-----------------|
|[카틀맵::CPair 클래스](#cpair_class)|키 및 값 요소를 포함하는 클래스입니다.|

### <a name="cpair-data-members"></a>CPair 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CPair::m_key](#m_key)|키 요소를 저장하는 데이터 멤버입니다.|
|[CPair::m_value](#m_value)|값 요소를 저장하는 데이터 멤버입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[카틀맵:::카틀맵](#catlmap)|생성자입니다.|
|[카틀맵::~카틀맵](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[카틀맵::어설션 유효](#assertvalid)|이 메서드가 유효하지 않은 `CAtlMap` 경우 ASSERT를 발생시도록 호출합니다.|
|[카틀맵::D가능오토리해시](#disableautorehash)|이 메서드를 호출하여 개체의 자동 `CAtlMap` 해시를 사용하지 않도록 설정합니다.|
|[카틀맵::인에이블오토리해시](#enableautorehash)|이 메서드를 호출하여 개체를 자동으로 `CAtlMap` 다시 해시할 수 있습니다.|
|[카틀맵::GetAt](#getat)|맵에서 지정된 위치에 요소를 반환하려면 이 메서드를 호출합니다.|
|[카틀맵::겟카운트](#getcount)|맵의 요소 수를 검색하려면 이 메서드를 호출합니다.|
|[카틀맵::겟해시테이블사이즈](#gethashtablesize)|이 메서드를 호출하여 맵의 해시 테이블에서 저장소 수를 확인합니다.|
|[카틀맵::겟키앳](#getkeyat)|이 메서드를 호출하여 개체의 지정된 위치에 `CAtlMap` 저장된 키를 검색합니다.|
|[카틀맵::GetNext](#getnext)|이 메서드를 호출하여 개체에 저장된 다음 `CAtlMap` 요소 쌍에 대한 포인터를 가져옵니다.|
|[카틀맵::겟넥스트아소크](#getnextassoc)|반복에 대한 다음 요소를 가져옵니다.|
|[카틀맵::겟넥스트키](#getnextkey)|이 메서드를 호출하여 개체에서 `CAtlMap` 다음 키를 검색합니다.|
|[카틀맵::GetNextValue](#getnextvalue)|개체에서 다음 값을 얻으려면이 `CAtlMap` 메서드를 호출 합니다.|
|[카틀맵::GetStart포지션](#getstartposition)|이 메서드를 호출하여 맵 반복을 시작합니다.|
|[카틀맵::겟밸류앳](#getvalueat)|이 메서드를 호출하여 개체의 지정된 위치에 `CAtlMap` 저장된 값을 검색합니다.|
|[카틀맵::이니티해시테이블](#inithashtable)|이 메서드를 호출하여 해시 테이블을 초기화합니다.|
|[카틀맵::비어 있음](#isempty)|빈 맵 개체를 테스트하려면 이 메서드를 호출합니다.|
|[카틀맵::조회](#lookup)|이 메서드를 호출하여 개체의 `CAtlMap` 키 또는 값을 찾습니다.|
|[카틀맵::리해시](#rehash)|이 메서드를 호출하여 `CAtlMap` 개체를 다시 해시합니다.|
|[카틀맵::모두 제거](#removeall)|이 메서드를 호출하여 개체에서 모든 요소를 제거합니다. `CAtlMap`|
|[카틀맵::리크아포스](#removeatpos)|이 메서드를 호출하여 개체의 지정된 `CAtlMap` 위치에서 요소를 제거합니다.|
|[카틀맵::리무브키](#removekey)|키가 주어지면 이 메서드를 `CAtlMap` 호출하여 개체에서 요소를 제거합니다.|
|[카틀맵::세팅](#setat)|이 메서드를 호출하여 요소 쌍을 맵에 삽입합니다.|
|[카틀맵::최적 로드 설정](#setoptimalload)|이 메서드를 호출하여 개체의 `CAtlMap` 최적 로드를 설정합니다.|
|[카틀맵::셋밸류At](#setvalueat)|이 메서드를 호출하여 개체의 지정된 위치에 `CAtlMap` 저장된 값을 변경합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|`CAtlMap`에 새 요소를 바꾸거나 추가합니다.|

## <a name="remarks"></a>설명

`CAtlMap`는 지정된 형식의 매핑 배열에 대한 지원을 제공하여 키 요소및 관련 값의 정렬되지 않은 배열을 관리합니다. 키와 값으로 구성된 요소(키와 값으로 구성)는 해시 알고리즘을 사용하여 저장되므로 많은 양의 데이터를 효율적으로 저장하고 검색할 수 있습니다.

*KTraits* 및 *VTraits* 매개 변수는 요소를 복사하거나 이동하는 데 필요한 추가 코드를 포함하는 특성 클래스입니다.

`CAtlMap` [CRBMap](../../atl/reference/crbmap-class.md) 클래스에서 제공하는 대안입니다. `CRBMap`또한 키/값 쌍을 저장하지만 성능 특성이 다릅니다. 항목을 삽입하거나, 키를 찾거나, `CRBMap` 개체에서 키를 삭제하는 데 걸린 시간은 순서 *log(n)이며*여기서 *n은* 요소 수입니다. 에 `CAtlMap`대 한 이러한 모든 작업은 일반적으로 일정 한 시간이 걸릴, 최악의 시나리오 순서 *n*일 수 있지만 . 따라서 일반적인 경우에는 `CAtlMap` 더 빠릅니다.

저장된 요소를 `CRBMap` 반복할 때와 `CAtlMap` 다른 차이점이 분명해집니다. 에서 `CRBMap`요소는 정렬된 순서로 방문합니다. 에서 `CAtlMap`요소는 정렬되지 않으며 순서를 유추할 수 없습니다.

소수의 요소를 저장해야 하는 경우 대신 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스를 사용하는 것이 좋습니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="catlmapassertvalid"></a><a name="assertvalid"></a>카틀맵::어설션 유효

개체가 유효하지 않은 경우 `CAtlMap` ASSERT를 발생시키기 위해 이 메서드를 호출합니다.

```cpp
void AssertValid() const;
```

### <a name="remarks"></a>설명

디버그 빌드에서 이 메서드는 개체가 `CAtlMap` 유효하지 않은 경우 ASSERT를 발생시게 됩니다.

### <a name="example"></a>예제

[CAtlMap::CAtlMap](#catlmap)에 대한 예제를 참조하십시오.

## <a name="catlmapcatlmap"></a><a name="catlmap"></a>카틀맵:::카틀맵

생성자입니다.

```
CAtlMap(
    UINT nBins = 17,
    float fOptimalLoad = 0.75f,
    float fLoThreshold = 0.25f,
    float fHiThreshold = 2.25f,
    UINT nBlockSize = 10) throw ();
```

### <a name="parameters"></a>매개 변수

*nBins*<br/>
저장된 요소에 대한 포인터를 제공하는 저장소 수입니다. 저장소에 대한 설명은 이 항목의 후반부에서 설명을 참조하십시오.

*f최적 로드*<br/>
최적의 하중 비율.

*fLo 임계값*<br/>
부하 비율에 대한 낮은 임계값입니다.

*fHi임계값*<br/>
부하 비율에 대한 상위 임계값입니다.

*nBlockSize*<br/>
블록의 크기입니다.

### <a name="remarks"></a>설명

`CAtlMap`먼저 키에 해시 알고리즘을 사용하여 인덱스를 만들어 저장된 모든 요소를 참조합니다. 이 인덱스는 저장된 요소에 대한 포인터를 포함하는 "bin"을 참조합니다. 저장소가 이미 사용 중이면 후속 요소에 액세스하기 위해 링크된 목록이 만들어집니다. 목록을 트래버스하는 것은 올바른 요소에 직접 액세스하는 것보다 느리므로 맵 구조는 저장소 요구 사항과 성능의 균형을 유지해야 합니다. 대부분의 경우 좋은 결과를 제공하기 위해 기본 매개 변수가 선택되었습니다.

하중 비율은 저장소 수와 맵 오브젝트에 저장된 요소 수의 비율입니다. 맵 구조를 다시 계산하면 *fOptimalLoad* 매개변수 값이 필요한 저장소 수를 계산하는 데 사용됩니다. 이 값은 [CAtlMap::SetOptimalLoad 메서드를](#setoptimalload) 사용하여 변경할 수 있습니다.

*fLoThreshold* 매개 변수는 로드 비율이 도달하기 전에 `CAtlMap` 도달할 수 있는 낮은 값으로 맵의 최적 크기를 다시 계산합니다.

*fHiThreshold* 매개 변수는 `CAtlMap` 오브젝트가 맵의 최적 크기를 다시 계산하기 전에 하중 비율이 도달할 수 있는 상한값입니다.

이 재계산 프로세스(재해싱이라고 함)는 기본적으로 활성화되어 있습니다. 한 번에 많은 데이터를 입력할 때 이 프로세스를 사용하지 않도록 설정하려면 [CAtlMap::DAutoRehash](#disableautorehash) 메서드를 호출합니다. [CAtlMap::EnableAutoRehash](#enableautorehash) 메서드를 사용하여 다시 활성화합니다.

*nBlockSize* 매개 변수는 새 요소가 필요할 때 할당된 메모리 양을 측정한 값입니다. 블록 크기가 클수록 메모리 할당 루틴에 대한 호출이 줄어들지만 더 많은 리소스를 사용합니다.

데이터를 저장하기 전에 [CAtlMap::InitHashTable](#inithashtable)을 호출하여 해시 테이블을 초기화해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]

## <a name="catlmapcatlmap"></a><a name="dtor"></a>카틀맵::~카틀맵

소멸자입니다.

```
~CAtlMap() throw();
```

### <a name="remarks"></a>설명

할당된 리소스를 해제합니다.

## <a name="catlmapcpair-class"></a><a name="cpair_class"></a>카틀맵::CPair 클래스

키 및 값 요소를 포함하는 클래스입니다.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>설명

이 클래스는 매핑 구조에 저장된 키 및 값 요소에 액세스하기 위해 [CAtlMap::GetNext](#getnext) 및 [CAtlMap:조회](#lookup) 메서드에서 사용됩니다.

## <a name="catlmapdisableautorehash"></a><a name="disableautorehash"></a>카틀맵::D가능오토리해시

이 메서드를 호출하여 개체의 자동 `CAtlMap` 해시를 사용하지 않도록 설정합니다.

```cpp
void DisableAutoRehash() throw();
```

### <a name="remarks"></a>설명

자동 재해시가 활성화되면(기본적으로) 로드 값(배열에 저장된 요소 수에 대한 bin 수의 비율)이 맵을 만들 때 지정된 최대 값 또는 최소 값을 초과하는 경우 해시 테이블의 저장소 수가 자동으로 다시 계산됩니다.

`DisableAutoRehash`많은 수의 요소가 한 번에 맵에 추가될 때 가장 유용합니다. 제한을 초과할 때마다 다시 해싱 프로세스를 트리거하는 대신 호출하고 `DisableAutoRehash`요소를 추가하고 마지막으로 [CAtlMap::EnableAutoRehash를](#enableautorehash)호출하는 것이 더 효율적입니다.

## <a name="catlmapenableautorehash"></a><a name="enableautorehash"></a>카틀맵::인에이블오토리해시

이 메서드를 호출하여 개체를 자동으로 `CAtlMap` 다시 해시할 수 있습니다.

```cpp
void EnableAutoRehash() throw();
```

### <a name="remarks"></a>설명

자동 재해시가 활성화되면(기본적으로) 로드 값(배열에 저장된 요소 수에 대한 bin 수의 비율)이 맵을 만들 때 지정된 최대 값 또는 최소 값을 초과하는 경우 해시 테이블의 저장소 수가 자동으로 다시 계산됩니다.

`EnableAutoRefresh`가장 자주 [CAtlMap에](#disableautorehash)대 한 호출 후 사용::D

## <a name="catlmapgetat"></a><a name="getat"></a>카틀맵::GetAt

맵에서 지정된 위치에 요소를 반환하려면 이 메서드를 호출합니다.

```cpp
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CAtlMap::GetNextAssoc](#getnextassoc) 또는 [CAtlMap::GetStartPosition에](#getstartposition)대한 이전 호출로 반환된 위치 카운터.

*key*<br/>
맵 키의 유형을 지정하는 템플릿 매개 변수입니다.

*value*<br/>
맵 값의 유형을 지정하는 템플릿 매개변수입니다.

### <a name="return-value"></a>Return Value

맵에 저장된 키/값 요소의 현재 쌍에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 *pos가* NULL과 같으면 어설션 오류가 발생합니다.

## <a name="catlmapgetcount"></a><a name="getcount"></a>카틀맵::겟카운트

맵의 요소 수를 검색하려면 이 메서드를 호출합니다.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Return Value

맵 오브젝트의 요소 수를 반환합니다. 단일 요소는 키/값 쌍입니다.

### <a name="example"></a>예제

[CAtlMap::CAtlMap](#catlmap)에 대한 예제를 참조하십시오.

## <a name="catlmapgethashtablesize"></a><a name="gethashtablesize"></a>카틀맵::겟해시테이블사이즈

이 메서드를 호출하여 맵의 해시 테이블에서 저장소 수를 확인합니다.

```
UINT GetHashTableSize() const throw();
```

### <a name="return-value"></a>Return Value

해시 테이블의 저장소 수를 반환합니다. 설명은 [CAtlMap::CAtlMap을](#catlmap) 참조하십시오.

## <a name="catlmapgetkeyat"></a><a name="getkeyat"></a>카틀맵::겟키앳

이 메서드를 호출하여 개체의 지정된 위치에 `CAtlMap` 저장된 키를 검색합니다.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CAtlMap::GetNextAssoc](#getnextassoc) 또는 [CAtlMap::GetStartPosition에](#getstartposition)대한 이전 호출로 반환된 위치 카운터.

### <a name="return-value"></a>Return Value

개체의 지정된 위치에 저장된 키에 대한 `CAtlMap` 참조를 반환합니다.

### <a name="example"></a>예제

[CAtlMap::CAtlMap](#catlmap)에 대한 예제를 참조하십시오.

## <a name="catlmapgetnext"></a><a name="getnext"></a>카틀맵::GetNext

이 메서드를 호출하여 개체에 저장된 다음 `CAtlMap` 요소 쌍에 대한 포인터를 가져옵니다.

```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CAtlMap::GetNextAssoc](#getnextassoc) 또는 [CAtlMap::GetStartPosition에](#getstartposition)대한 이전 호출로 반환된 위치 카운터.

### <a name="return-value"></a>Return Value

맵에 저장된 키/값 요소의 다음 쌍에 대한 포인터를 반환합니다. *pos* 위치 카운터는 각 호출 후 업데이트됩니다. 검색된 요소가 맵의 마지막 요소인 경우 *pos는* NULL로 설정됩니다.

## <a name="catlmapgetnextassoc"></a><a name="getnextassoc"></a>카틀맵::겟넥스트아소크

반복에 대한 다음 요소를 가져옵니다.

```cpp
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CAtlMap::GetNextAssoc](#getnextassoc) 또는 [CAtlMap::GetStartPosition에](#getstartposition)대한 이전 호출로 반환된 위치 카운터.

*key*<br/>
맵 키의 유형을 지정하는 템플릿 매개 변수입니다.

*value*<br/>
맵 값의 유형을 지정하는 템플릿 매개변수입니다.

### <a name="remarks"></a>설명

*pos* 위치 카운터는 각 호출 후 업데이트됩니다. 검색된 요소가 맵의 마지막 요소인 경우 *pos는* NULL로 설정됩니다.

## <a name="catlmapgetnextkey"></a><a name="getnextkey"></a>카틀맵::겟넥스트키

이 메서드를 호출하여 개체에서 `CAtlMap` 다음 키를 검색합니다.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CAtlMap::GetNextAssoc](#getnextassoc) 또는 [CAtlMap::GetStartPosition에](#getstartposition)대한 이전 호출로 반환된 위치 카운터.

### <a name="return-value"></a>Return Value

맵의 다음 키에 대한 참조를 반환합니다.

### <a name="remarks"></a>설명

현재 위치 카운터, *pos를*업데이트합니다. 맵에 더 이상 항목이 없는 경우 위치 카운터가 NULL로 설정됩니다.

## <a name="catlmapgetnextvalue"></a><a name="getnextvalue"></a>카틀맵::GetNextValue

개체에서 다음 값을 얻으려면이 `CAtlMap` 메서드를 호출 합니다.

```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CAtlMap::GetNextAssoc](#getnextassoc) 또는 [CAtlMap::GetStartPosition에](#getstartposition)대한 이전 호출로 반환된 위치 카운터.

### <a name="return-value"></a>Return Value

맵의 다음 값에 대한 참조를 반환합니다.

### <a name="remarks"></a>설명

현재 위치 카운터, *pos를*업데이트합니다. 맵에 더 이상 항목이 없는 경우 위치 카운터가 NULL로 설정됩니다.

### <a name="example"></a>예제

[CAtlMap::CAtlMap](#catlmap)에 대한 예제를 참조하십시오.

## <a name="catlmapgetstartposition"></a><a name="getstartposition"></a>카틀맵::GetStart포지션

이 메서드를 호출하여 맵 반복을 시작합니다.

```
POSITION GetStartPosition() const throw();
```

### <a name="return-value"></a>Return Value

시작 위치를 반환하거나 맵이 비어 있으면 NULL이 반환됩니다.

### <a name="remarks"></a>설명

메서드에 전달할 수 있는 POSITION 값을 반환 하 여 `GetNextAssoc` 맵 반복을 시작 하려면이 메서드를 호출 합니다.

> [!NOTE]
> 반복 시퀀스를 예측할 수 없습니다.

### <a name="example"></a>예제

[CAtlMap::CAtlMap](#catlmap)에 대한 예제를 참조하십시오.

## <a name="catlmapgetvalueat"></a><a name="getvalueat"></a>카틀맵::겟밸류앳

이 메서드를 호출하여 개체의 지정된 위치에 `CAtlMap` 저장된 값을 검색합니다.

```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CAtlMap::GetNextAssoc](#getnextassoc) 또는 [CAtlMap::GetStartPosition에](#getstartposition)대한 이전 호출로 반환된 위치 카운터.

### <a name="return-value"></a>Return Value

개체의 지정된 위치에 저장된 값에 대한 `CAtlMap` 참조를 반환합니다.

## <a name="catlmapinithashtable"></a><a name="inithashtable"></a>카틀맵::이니티해시테이블

이 메서드를 호출하여 해시 테이블을 초기화합니다.

```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```

### <a name="parameters"></a>매개 변수

*nBins*<br/>
해시 테이블에서 사용하는 저장소 수입니다. 설명은 [CAtlMap::CAtlMap을](#catlmap) 참조하십시오.

*bAllocNow*<br/>
메모리를 할당해야 하는 경우 플래그 표시입니다.

### <a name="return-value"></a>Return Value

성공적인 초기화시 TRUE를 반환하고 실패시 FALSE를 반환합니다.

### <a name="remarks"></a>설명

`InitHashTable`모든 요소가 해시 테이블에 저장되기 전에 호출해야 합니다.  이 메서드가 명시적으로 호출되지 않으면 `CAtlMap` 생성자가 지정한 bin 수를 사용하여 요소가 처음 추가될 때 자동으로 호출됩니다.  그렇지 않으면 *nBins* 매개 변수에 의해 지정된 새 bin 수를 사용하여 맵이 초기화됩니다.

*bAllocNow* 매개 변수가 false이면 해시 테이블에 필요한 메모리가 처음 필요할 때까지 할당되지 않습니다. 이 기능은 맵이 사용될지 확실하지 않은 경우에 유용할 수 있습니다.

### <a name="example"></a>예제

[CAtlMap::CAtlMap](#catlmap)에 대한 예제를 참조하십시오.

## <a name="catlmapisempty"></a><a name="isempty"></a>카틀맵::비어 있음

빈 맵 개체를 테스트하려면 이 메서드를 호출합니다.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Return Value

그렇지 않으면 맵이 비어 있는 경우 TRUE를 반환합니다.

## <a name="catlmapkinargtype"></a><a name="kinargtype"></a>카틀맵::키나르그타입

키가 입력 인수로 전달될 때 사용되는 형식입니다.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="catlmapkoutargtype"></a><a name="koutargtype"></a>카틀맵::쿠타르그타입

키가 출력 인수로 반환될 때 사용되는 형식입니다.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="catlmaplookup"></a><a name="lookup"></a>카틀맵::조회

이 메서드를 호출하여 개체의 `CAtlMap` 키 또는 값을 찾습니다.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
조회할 요소를 식별하는 키를 지정합니다.

*value*<br/>
조회된 값을 받는 변수입니다.

### <a name="return-value"></a>Return Value

메서드의 첫 번째 형식은 키가 발견되면 true를 반환합니다(그렇지 않으면 false). 두 번째 및 세 번째 양식은 [CAtlMap::GetNext](#getnext) 등을 호출하는 위치로 사용할 수 있는 [CPair에](#cpair_class) 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

`Lookup`해시 알고리즘을 사용하여 지정된 키 매개 변수와 정확히 일치하는 키가 포함된 맵 요소를 빠르게 찾습니다.

## <a name="catlmapoperator-"></a><a name="operator_at"></a>CAtlMap::연산자\[\]

`CAtlMap`에 새 요소를 바꾸거나 추가합니다.

```
V& operator[](kinargtype key) throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
추가하거나 바꿀 요소의 키입니다.

### <a name="return-value"></a>Return Value

지정된 키와 연결된 값에 대한 참조를 반환합니다.

### <a name="example"></a>예제

키가 이미 있으면 요소가 대체됩니다. 키가 없으면 새 요소가 추가됩니다. [CAtlMap::CAtlMap](#catlmap)에 대한 예제를 참조하십시오.

## <a name="catlmaprehash"></a><a name="rehash"></a>카틀맵::리해시

이 메서드를 호출하여 `CAtlMap` 개체를 다시 해시합니다.

```cpp
void Rehash(UINT nBins = 0);
```

### <a name="parameters"></a>매개 변수

*nBins*<br/>
해시 테이블에서 사용할 새 저장소 수입니다. 설명은 [CAtlMap::CAtlMap을](#catlmap) 참조하십시오.

### <a name="remarks"></a>설명

*nBin이* 0이면 `CAtlMap` 맵의 요소 수와 최적의 부하 설정에 따라 적절한 숫자를 계산합니다. 일반적으로 다시 해싱 프로세스는 자동으로 수행되지만 [CAtlMap::DisableAutoRehash가](#disableautorehash) 호출된 경우 이 메서드는 필요한 크기 조정을 수행합니다.

## <a name="catlmapremoveall"></a><a name="removeall"></a>카틀맵::모두 제거

이 메서드를 호출하여 개체에서 모든 요소를 제거합니다. `CAtlMap`

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>설명

개체를 `CAtlMap` 지우고 요소를 저장하는 데 사용되는 메모리를 해제합니다.

## <a name="catlmapremoveatpos"></a><a name="removeatpos"></a>카틀맵::리크아포스

이 메서드를 호출하여 개체의 지정된 `CAtlMap` 위치에서 요소를 제거합니다.

```cpp
void RemoveAtPos(POSITION pos) throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CAtlMap::GetNextAssoc](#getnextassoc) 또는 [CAtlMap::GetStartPosition에](#getstartposition)대한 이전 호출로 반환된 위치 카운터.

### <a name="remarks"></a>설명

지정된 위치에 저장된 키/값 쌍을 제거합니다. 요소를 저장하는 데 사용되는 메모리가 해제됩니다. *pos에서* 참조하는 위치는 유효하지 않으며 맵의 다른 요소의 위치는 유효하지만 반드시 동일한 순서를 유지하지는 않습니다.

## <a name="catlmapremovekey"></a><a name="removekey"></a>카틀맵::리무브키

키가 주어지면 이 메서드를 `CAtlMap` 호출하여 개체에서 요소를 제거합니다.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
제거할 요소 쌍에 해당하는 키입니다.

### <a name="return-value"></a>Return Value

키가 발견되고 제거되면 TRUE를 반환합니다( 오류 시 FALSE).

### <a name="example"></a>예제

[CAtlMap::CAtlMap](#catlmap)에 대한 예제를 참조하십시오.

## <a name="catlmapsetat"></a><a name="setat"></a>카틀맵::세팅

이 메서드를 호출하여 요소 쌍을 맵에 삽입합니다.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
개체에 추가할 키 `CAtlMap` 값입니다.

*value*<br/>
개체에 추가할 값입니다. `CAtlMap`

### <a name="return-value"></a>Return Value

개체에서 키/값 요소 쌍의 위치를 `CAtlMap` 반환합니다.

### <a name="remarks"></a>설명

`SetAt`일치하는 키가 발견되면 기존 요소를 대체합니다. 키가 없는 경우 새 키/값 쌍이 만들어집니다.

## <a name="catlmapsetoptimalload"></a><a name="setoptimalload"></a>카틀맵::최적 로드 설정

이 메서드를 호출하여 개체의 `CAtlMap` 최적 로드를 설정합니다.

```cpp
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```

### <a name="parameters"></a>매개 변수

*f최적 로드*<br/>
최적의 하중 비율.

*fLo 임계값*<br/>
부하 비율에 대한 낮은 임계값입니다.

*fHi임계값*<br/>
부하 비율에 대한 상위 임계값입니다.

*bRehashNow*<br/>
해시 테이블을 다시 계산해야 하는지 나타내는 플래그입니다.

### <a name="remarks"></a>설명

이 메서드는 `CAtlMap` 개체에 대 한 최적의 하중 값을 재정의 합니다. 다양한 매개 변수에 대한 설명은 [CAtlMap::CAtlMap을](#catlmap) 참조하십시오. *bRehashNowtrue이고* 요소 수가 최소 값 및 최대 값 밖에 있으면 해시 테이블이 다시 계산됩니다.

## <a name="catlmapsetvalueat"></a><a name="setvalueat"></a>카틀맵::셋밸류At

이 메서드를 호출하여 개체의 지정된 위치에 `CAtlMap` 저장된 값을 변경합니다.

```cpp
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CAtlMap::GetNextAssoc](#getnextassoc) 또는 [CAtlMap::GetStartPosition에](#getstartposition)대한 이전 호출로 반환된 위치 카운터.

*value*<br/>
개체에 추가할 값입니다. `CAtlMap`

### <a name="remarks"></a>설명

개체의 지정된 위치에 저장된 값 `CAtlMap` 요소를 변경합니다.

## <a name="catlmapvinargtype"></a><a name="vinargtype"></a>카틀맵::비나르그타입

값이 입력 인수로 전달될 때 사용되는 형식입니다.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="catlmapvoutargtype"></a><a name="voutargtype"></a>카틀맵::부타르그타입

값이 출력 인수로 전달될 때 사용되는 형식입니다.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="catlmapcpairm_key"></a><a name="m_key"></a>카틀맵::C페어::m_key

키 요소를 저장하는 데이터 멤버입니다.

```
const K m_key;
```

### <a name="parameters"></a>매개 변수

*K (주)*<br/>
키 요소 유형입니다.

## <a name="catlmapcpairm_value"></a><a name="m_value"></a>카틀맵::C페어::m_value

값 요소를 저장하는 데이터 멤버입니다.

```
V  m_value;
```

### <a name="parameters"></a>매개 변수

*Ⅴ*<br/>
값 요소 형식입니다.

## <a name="see-also"></a>참조

[선택 윤곽 샘플](../../overview/visual-cpp-samples.md)<br/>
[업데이트PV 샘플](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
