---
title: CRBMultiMap 클래스
ms.date: 11/04/2016
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
ms.openlocfilehash: 1e36bc267b3a539d2d1d4bf370b9cdc33828c760
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331431"
---
# <a name="crbmultimap-class"></a>CRBMultiMap 클래스

이 클래스는 각 키가 빨간색-검은색 이진 트리를 사용하여 두 개 이상의 값과 연결할 수 있도록 하는 매핑 구조를 나타냅니다.

## <a name="syntax"></a>구문

```
template<typename K,
         typename V,
         class KTraits = CElementTraits<K>,
         class VTraits = CElementTraits<V>>
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
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
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|생성자입니다.|
|[CRBMultiMap::~CRBMultiMap](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CRBMultiMap::찾기우선위키](#findfirstwithkey)|지정된 키가 있는 첫 번째 요소의 위치를 찾으려면 이 메서드를 호출합니다.|
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|지정된 키와 연결된 값을 얻고 위치 값을 업데이트하려면 이 메서드를 호출합니다.|
|[CRB MultiMap::GetNextWithKey키](#getnextwithkey)|지정된 키와 연결된 요소를 얻고 위치 값을 업데이트하려면 이 메서드를 호출합니다.|
|[CRBMultiMap::삽입](#insert)|이 메서드를 호출하여 요소 쌍을 맵에 삽입합니다.|
|[CRBMultiMap::제거키](#removekey)|지정된 키에 대한 모든 키/값 요소를 제거하려면 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

`CRBMultiMap`지정된 형식의 매핑 배열을 지원하여 키 요소 및 값의 정렬된 배열을 관리합니다. [CRBMap](../../atl/reference/crbmap-class.md) 클래스와 달리 각 키는 두 개 이상의 값과 연결할 수 있습니다.

요소(키와 값으로 구성됨)는 [CRBMultiMap::Insert](#insert) 메서드를 사용하여 이진 트리 구조에 저장됩니다. [CRBMultiMap::RemoveKey](#removekey) 메서드를 사용하여 요소를 제거할 수 있으며, 이 메서드는 지정된 키와 일치하는 모든 요소를 삭제합니다.

[CRBTree:GetHeadPosition,](../../atl/reference/crbtree-class.md#getheadposition) [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext)및 [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnextvalue)값과 같은 메서드를 사용 하 고 트리를 트래버스 가능 하 게 됩니다. [CRBMultiMap::FindFirstWithKey,](#findfirstwithkey) [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)및 [CRBMultiMap::GetNextWithKey](#getnextwithkey) 메서드를 사용하여 키당 잠재적으로 여러 값에 액세스할 수 있습니다. 실제로 이에 대한 그림은 [CRBMultiMap::CRBMultiMap의](#crbmultimap) 예제를 참조하십시오.

*KTraits* 및 *VTraits* 매개 변수는 요소를 복사하거나 이동하는 데 필요한 추가 코드를 포함하는 특성 클래스입니다.

`CRBMultiMap`빨간색-검정 알고리즘을 사용 하 여 이진 트리를 구현 하는 [CRBTree에서](../../atl/reference/crbtree-class.md)파생 됩니다. [CAtlMap](../../atl/reference/catlmap-class.md) 클래스에 대한 `CRBMultiMap` `CRBMap` 대안과 제공됩니다. 소수의 요소만 저장해야 하는 경우 대신 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스를 사용하는 것이 좋습니다.

다양한 컬렉션 클래스와 그 기능 및 성능 특성에 대한 자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMultiMap`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="crbmultimapcrbmultimap"></a><a name="crbmultimap"></a>CRBMultiMap::CRBMultiMap

생성자입니다.

```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
블록의 크기입니다.

### <a name="remarks"></a>설명

*nBlockSize* 매개 변수는 새 요소가 필요할 때 할당된 메모리 양을 측정한 값입니다. 블록 크기가 클수록 메모리 할당 루틴에 대한 호출이 줄어들지만 더 많은 리소스를 사용합니다. 기본값은 한 번에 10개의 요소에 대한 공간을 할당합니다.

사용 가능한 다른 방법에 대한 자세한 내용은 기본 클래스 [CRBTree에](../../atl/reference/crbtree-class.md) 대한 설명서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]

## <a name="crbmultimapcrbmultimap"></a><a name="dtor"></a>CRBMultiMap::~CRBMultiMap

소멸자입니다.

```
~CRBMultiMap() throw();
```

### <a name="remarks"></a>설명

할당된 리소스를 해제합니다.

사용 가능한 다른 방법에 대한 자세한 내용은 기본 클래스 [CRBTree에](../../atl/reference/crbtree-class.md) 대한 설명서를 참조하십시오.

## <a name="crbmultimapfindfirstwithkey"></a><a name="findfirstwithkey"></a>CRBMultiMap::찾기우선위키

지정된 키가 있는 첫 번째 요소의 위치를 찾으려면 이 메서드를 호출합니다.

```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>매개 변수

*키*<br/>
찾을 요소를 식별하는 키를 지정합니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 키가 발견되면 첫 번째 키/값 요소의 위치를 반환합니다.

### <a name="remarks"></a>설명

에 있는 `CRBMultiMap` 키에는 하나 이상의 연관된 값이 있을 수 있습니다. 이 메서드는 특정 키와 연결된 첫 번째 값(실제로 유일한 값일 수 있음)의 위치 값을 제공합니다. 그런 다음 반환된 위치 값을 [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) 또는 [CRBMultiMap::GetNextWithKey키와](#getnextwithkey) 함께 사용하여 값을 얻고 위치를 업데이트할 수 있습니다.

사용 가능한 다른 방법에 대한 자세한 내용은 기본 클래스 [CRBTree에](../../atl/reference/crbtree-class.md) 대한 설명서를 참조하십시오.

### <a name="example"></a>예제

[CRBMultiMap::CRBMultiMap에](#crbmultimap)대한 예제를 참조하십시오.

## <a name="crbmultimapgetnextvaluewithkey"></a><a name="getnextvaluewithkey"></a>CRBMultiMap::GetNextValueWithKey

지정된 키와 연결된 값을 얻고 위치 값을 업데이트하려면 이 메서드를 호출합니다.

```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CRBMultiMap::FindFirstWithKey](#findfirstwithkey) 또는 [CRBMultiMap::GetNextWithKey](#getnextwithkey)키 또는 이전 호출에 대 한 호출로 `GetNextValueWithKey`얻은 위치 값입니다.

*키*<br/>
찾을 요소를 식별하는 키를 지정합니다.

### <a name="return-value"></a>Return Value

지정된 키와 연결된 요소 쌍을 반환합니다.

### <a name="remarks"></a>설명

위치 값이 키와 연결된 다음 값을 가리키도록 업데이트됩니다. 값이 더 이상 없으면 위치 값이 NULL로 설정됩니다.

사용 가능한 다른 방법에 대한 자세한 내용은 기본 클래스 [CRBTree에](../../atl/reference/crbtree-class.md) 대한 설명서를 참조하십시오.

### <a name="example"></a>예제

[CRBMultiMap::CRBMultiMap에](#crbmultimap)대한 예제를 참조하십시오.

## <a name="crbmultimapgetnextwithkey"></a><a name="getnextwithkey"></a>CRB MultiMap::GetNextWithKey키

지정된 키와 연결된 요소를 얻고 위치 값을 업데이트하려면 이 메서드를 호출합니다.

```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CRBMultiMap::FindFirstWithKey](#findfirstwithkey) 또는 [CRBMultiMap::GetNextValueWithKey에](#getnextvaluewithkey)대한 이전 호출로 `GetNextWithKey`얻은 위치 값입니다.

*키*<br/>
찾을 요소를 식별하는 키를 지정합니다.

### <a name="return-value"></a>Return Value

지정된 키와 연결된 다음 [CRBTree::CPair 클래스](crbtree-class.md#cpair_class) 요소를 반환합니다.

### <a name="remarks"></a>설명

위치 값이 키와 연결된 다음 값을 가리키도록 업데이트됩니다. 값이 더 이상 없으면 위치 값이 NULL로 설정됩니다.

사용 가능한 다른 방법에 대한 자세한 내용은 기본 클래스 [CRBTree에](../../atl/reference/crbtree-class.md) 대한 설명서를 참조하십시오.

## <a name="crbmultimapinsert"></a><a name="insert"></a>CRBMultiMap::삽입

이 메서드를 호출하여 요소 쌍을 맵에 삽입합니다.

```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>매개 변수

*키*<br/>
개체에 추가할 키 `CRBMultiMap` 값입니다.

*value*<br/>
`CRBMultiMap` *키와*연결된 개체에 추가할 값입니다.

### <a name="return-value"></a>Return Value

개체에서 키/값 요소 쌍의 위치를 `CRBMultiMap` 반환합니다.

### <a name="remarks"></a>설명

사용 가능한 다른 방법에 대한 자세한 내용은 기본 클래스 [CRBTree에](../../atl/reference/crbtree-class.md) 대한 설명서를 참조하십시오.

### <a name="example"></a>예제

[CRBMultiMap::CRBMultiMap에](#crbmultimap)대한 예제를 참조하십시오.

## <a name="crbmultimapremovekey"></a><a name="removekey"></a>CRBMultiMap::제거키

지정된 키에 대한 모든 키/값 요소를 제거하려면 이 메서드를 호출합니다.

```
size_t RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>매개 변수

*키*<br/>
삭제할 요소를 식별하는 키를 지정합니다.

### <a name="return-value"></a>Return Value

지정된 키와 연결된 값 수를 반환합니다.

### <a name="remarks"></a>설명

`RemoveKey`*키와*일치하는 키가 있는 모든 키/값 요소를 삭제합니다.

사용 가능한 다른 방법에 대한 자세한 내용은 기본 클래스 [CRBTree에](../../atl/reference/crbtree-class.md) 대한 설명서를 참조하십시오.

### <a name="example"></a>예제

[CRBMultiMap::CRBMultiMap에](#crbmultimap)대한 예제를 참조하십시오.

## <a name="see-also"></a>참고 항목

[CRBTree 클래스](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap 클래스](../../atl/reference/catlmap-class.md)<br/>
[CRBMap 클래스](../../atl/reference/crbmap-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
