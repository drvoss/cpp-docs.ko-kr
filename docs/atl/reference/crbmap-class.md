---
title: CRBMap 클래스
ms.date: 11/04/2016
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
helpviewer_keywords:
- CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
ms.openlocfilehash: 9e367ccc875eedf63e4f47018598662af2dfcf7d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331401"
---
# <a name="crbmap-class"></a>CRBMap 클래스

이 클래스는 빨간색-검은색 이진 트리를 사용하여 매핑 구조를 나타냅니다.

## <a name="syntax"></a>구문

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
```

#### <a name="parameters"></a>매개 변수

*K*<br/>
키 요소 유형입니다.

*Ⅴ*<br/>
값 요소 형식입니다.

*크트레이스*<br/>
키 요소를 복사하거나 이동하는 데 사용되는 코드입니다. 자세한 내용은 [CElementTraits 클래스를](../../atl/reference/celementtraits-class.md) 참조하십시오.

*브이트레이스*<br/>
값 요소를 복사하거나 이동하는 데 사용되는 코드입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CRBMap::CRBMap](#crbmap)|생성자입니다.|
|[CRBMap::~CRBMap](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CRBMap::조회](#lookup)|이 메서드를 호출하여 개체의 `CRBMap` 키 또는 값을 찾습니다.|
|[CRBMap::제거키](#removekey)|키가 주어지면 이 메서드를 `CRBMap` 호출하여 개체에서 요소를 제거합니다.|
|[CRBMap::SetAt](#setat)|이 메서드를 호출하여 요소 쌍을 맵에 삽입합니다.|

## <a name="remarks"></a>설명

`CRBMap`는 지정된 형식의 매핑 배열에 대한 지원을 제공하여 키 요소및 관련 값의 정렬된 배열을 관리합니다. 각 키에는 하나의 연결된 값만 있을 수 있습니다. 요소(키와 값으로 구성됨)는 [CRBMap:SetAt](#setat) 메서드를 사용하여 이진 트리 구조에 저장됩니다. [CRBMap::RemoveKey](#removekey) 메서드를 사용하여 요소를 제거할 수 있으며, 이 메서드는 지정된 키 값으로 요소를 삭제합니다.

[CRBTree:GetHeadPosition,](../../atl/reference/crbtree-class.md#getheadposition) [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext)및 [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnextvalue)값과 같은 메서드를 사용 하 고 트리를 트래버스 가능 하 게 됩니다.

*KTraits* 및 *VTraits* 매개 변수는 요소를 복사하거나 이동하는 데 필요한 추가 코드를 포함하는 특성 클래스입니다.

`CRBMap`빨간색-검정 알고리즘을 사용 하 여 이진 트리를 구현 하는 [CRBTree에서](../../atl/reference/crbtree-class.md)파생 됩니다. [CRBMultiMap은](../../atl/reference/crbmultimap-class.md) 각 키에 대해 여러 값을 허용하는 변형입니다. 그것은 너무에서 `CRBTree`파생 된 그래서 많은 `CRBMap`기능을 공유 합니다.

둘 다에 `CRBMap` `CRBMultiMap` 대한 대안이며 [CAtlMap](../../atl/reference/catlmap-class.md) 클래스에서 제공됩니다. 소수의 요소만 저장해야 하는 경우 대신 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스를 사용하는 것이 좋습니다.

다양한 컬렉션 클래스와 그 기능 및 성능 특성에 대한 자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMap`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="crbmapcrbmap"></a><a name="crbmap"></a>CRBMap::CRBMap

생성자입니다.

```
explicit CRBMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
블록의 크기입니다.

### <a name="remarks"></a>설명

*nBlockSize* 매개 변수는 새 요소가 필요할 때 할당된 메모리 양을 측정한 값입니다. 블록 크기가 클수록 메모리 할당 루틴에 대한 호출이 줄어들지만 더 많은 리소스를 사용합니다. 기본값은 한 번에 10개의 요소에 대한 공간을 할당합니다.

사용 가능한 다른 방법에 대한 자세한 내용은 기본 클래스 [CRBTree에](../../atl/reference/crbtree-class.md) 대한 설명서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]

## <a name="crbmapcrbmap"></a><a name="dtor"></a>CRBMap::~CRBMap

소멸자입니다.

```
~CRBMap() throw();
```

### <a name="remarks"></a>설명

할당된 리소스를 해제합니다.

사용 가능한 다른 방법에 대한 자세한 내용은 기본 클래스 [CRBTree에](../../atl/reference/crbtree-class.md) 대한 설명서를 참조하십시오.

## <a name="crbmaplookup"></a><a name="lookup"></a>CRBMap::조회

이 메서드를 호출하여 개체의 `CRBMap` 키 또는 값을 찾습니다.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>매개 변수

*키*<br/>
조회할 요소를 식별하는 키를 지정합니다.

*value*<br/>
조회된 값을 받는 변수입니다.

### <a name="return-value"></a>Return Value

메서드의 첫 번째 형식은 키가 발견되면 true를 반환합니다(그렇지 않으면 false). 두 번째 및 세 번째 양식은 [CPair에](crbtree-class.md#cpair_class)대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

사용 가능한 다른 방법에 대한 자세한 내용은 기본 클래스 [CRBTree에](../../atl/reference/crbtree-class.md) 대한 설명서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]

## <a name="crbmapremovekey"></a><a name="removekey"></a>CRBMap::제거키

키가 주어지면 이 메서드를 `CRBMap` 호출하여 개체에서 요소를 제거합니다.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>매개 변수

*키*<br/>
제거할 요소 쌍에 해당하는 키입니다.

### <a name="return-value"></a>Return Value

키가 발견되고 제거된 경우 true를 반환합니다.

### <a name="remarks"></a>설명

사용 가능한 다른 방법에 대한 자세한 내용은 기본 클래스 [CRBTree에](../../atl/reference/crbtree-class.md) 대한 설명서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]

## <a name="crbmapsetat"></a><a name="setat"></a>CRBMap::SetAt

이 메서드를 호출하여 요소 쌍을 맵에 삽입합니다.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>매개 변수

*키*<br/>
개체에 추가할 키 `CRBMap` 값입니다.

*value*<br/>
개체에 추가할 값입니다. `CRBMap`

### <a name="return-value"></a>Return Value

개체에서 키/값 요소 쌍의 위치를 `CRBMap` 반환합니다.

### <a name="remarks"></a>설명

`SetAt`일치하는 키가 발견되면 기존 요소를 대체합니다. 키가 없는 경우 새 키/값 쌍이 만들어집니다.

사용 가능한 다른 방법에 대한 자세한 내용은 기본 클래스 [CRBTree에](../../atl/reference/crbtree-class.md) 대한 설명서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]

## <a name="see-also"></a>참고 항목

[CRBTree 클래스](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap 클래스](../../atl/reference/catlmap-class.md)<br/>
[CRBMultiMap 클래스](../../atl/reference/crbmultimap-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
