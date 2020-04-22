---
title: CRBTree 클래스
ms.date: 11/04/2016
f1_keywords:
- CRBTree
- ATLCOLL/ATL::CRBTree
- ATLCOLL/ATL::CRBTree::KINARGTYPE
- ATLCOLL/ATL::CRBTree::KOUTARGTYPE
- ATLCOLL/ATL::CRBTree::VINARGTYPE
- ATLCOLL/ATL::CRBTree::VOUTARGTYPE
- ATLCOLL/ATL::CRBTree::FindFirstKeyAfter
- ATLCOLL/ATL::CRBTree::GetAt
- ATLCOLL/ATL::CRBTree::GetCount
- ATLCOLL/ATL::CRBTree::GetHeadPosition
- ATLCOLL/ATL::CRBTree::GetKeyAt
- ATLCOLL/ATL::CRBTree::GetNext
- ATLCOLL/ATL::CRBTree::GetNextAssoc
- ATLCOLL/ATL::CRBTree::GetNextKey
- ATLCOLL/ATL::CRBTree::GetNextValue
- ATLCOLL/ATL::CRBTree::GetPrev
- ATLCOLL/ATL::CRBTree::GetTailPosition
- ATLCOLL/ATL::CRBTree::GetValueAt
- ATLCOLL/ATL::CRBTree::IsEmpty
- ATLCOLL/ATL::CRBTree::RemoveAll
- ATLCOLL/ATL::CRBTree::RemoveAt
- ATLCOLL/ATL::CRBTree::SetValueAt
helpviewer_keywords:
- CRBTree class
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
ms.openlocfilehash: 58c001ccef35d4265ef5b7fe200654781f130872
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746583"
---
# <a name="crbtree-class"></a>CRBTree 클래스

이 클래스는 빨간색-검정 트리를 만들고 활용하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBTree
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
|[CRBTree::키나르그타입](#kinargtype)|키가 입력 인수로 전달될 때 사용되는 형식입니다.|
|[CRBTree::쿠타르그타입](#koutargtype)|키가 출력 인수로 반환될 때 사용되는 형식입니다.|
|[CRBTree::비나르그타입](#vinargtype)|값이 입력 인수로 전달될 때 사용되는 형식입니다.|
|[CRBTree::부타르그타입](#voutargtype)|값이 출력 인수로 전달될 때 사용되는 형식입니다.|

### <a name="public-classes"></a>public 클래스

|속성|Description|
|----------|-----------------|
|[CRBTree:::코페어 클래스](#cpair_class)|키 및 값 요소를 포함하는 클래스입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CRB트리::~CRB트리](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CRBTree::찾기퍼스트키 후](#findfirstkeyafter)|사용 가능한 다음 키를 사용하는 요소의 위치를 찾으려면 이 메서드를 호출합니다.|
|[CRBTree::GetAt](#getat)|이 메서드를 호출하여 트리의 지정된 위치에 요소를 가져옵니다.|
|[CRBTree::겟카운트](#getcount)|이 메서드를 호출하여 트리의 요소 수를 가져옵니다.|
|[CRBTree::GetHeadposition](#getheadposition)|이 메서드를 호출하여 트리의 헤드에 있는 요소에 대한 위치 값을 가져옵니다.|
|[CRBTree::GetKeyAt](#getkeyat)|이 메서드를 호출하여 트리의 지정된 위치에서 키를 가져옵니다.|
|[CRBTree::GetNext](#getnext)|이 메서드를 호출하여 개체에 저장된 `CRBTree` 요소에 대한 포인터를 가져오고 위치를 다음 요소로 이동합니다.|
|[CRBTree::GetNextAssoc](#getnextassoc)|맵에 저장된 요소의 키와 값을 얻고 위치를 다음 요소로 진행하려면 이 메서드를 호출합니다.|
|[CRBTree::GetNextKey](#getnextkey)|이 메서드를 호출하여 트리에 저장된 요소의 키를 얻고 위치를 다음 요소로 이동합니다.|
|[CRBTree::GetNextValue](#getnextvalue)|이 메서드를 호출하여 트리에 저장된 요소의 값을 얻고 위치를 다음 요소로 이동합니다.|
|[CRBTree ::GetPrev](#getprev)|이 메서드를 호출하여 개체에 저장된 `CRBTree` 요소에 대한 포인터를 얻은 다음 위치를 이전 요소로 업데이트합니다.|
|[CRBTree::GetTail포지션](#gettailposition)|이 메서드를 호출하여 트리의 꼬리에 있는 요소에 대한 위치 값을 가져옵니다.|
|[CRBTree::GetValueAt](#getvalueat)|이 메서드를 호출하여 개체의 지정된 위치에 `CRBTree` 저장된 값을 검색합니다.|
|[CRBTree::비어 있음](#isempty)|빈 트리 개체를 테스트하려면 이 메서드를 호출합니다.|
|[CRBTree::모두 제거](#removeall)|이 메서드를 호출하여 개체에서 모든 요소를 제거합니다. `CRBTree`|
|[CRBTree::제거](#removeat)|이 메서드를 호출하여 개체의 지정된 `CRBTree` 위치에서 요소를 제거합니다.|
|[CRBTree::설정값](#setvalueat)|이 메서드를 호출하여 개체의 지정된 위치에 `CRBTree` 저장된 값을 변경합니다.|

## <a name="remarks"></a>설명

빨간색-검정 트리는 노드당 추가 정보를 사용하여 "균형", 즉 트리 높이가 불균형하게 커지지 않고 성능에 영향을 주는 이진 검색 트리입니다.

이 템플릿 클래스는 [CRBMap](../../atl/reference/crbmap-class.md) 및 [CRBMultiMap](../../atl/reference/crbmultimap-class.md)에서 사용할 수 있도록 설계되었습니다. 이러한 파생 클래스를 구성하는 메서드의 대부분은 에서 `CRBTree`제공됩니다.

다양한 컬렉션 클래스와 그 기능 및 성능 특성에 대한 자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="crbtreecpair-class"></a><a name="cpair_class"></a>CRBTree:::코페어 클래스

키 및 값 요소를 포함하는 클래스입니다.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>설명

이 클래스는 [CRBTree::GetAt,](#getat) [CRBTree::GetNext](#getnext)및 [CRBTree:GetPrev에서](#getprev) 트리 구조에 저장된 키 및 값 요소에 액세스하는 메서드에서 사용됩니다.

구성원은 다음과 같습니다.

|||
|-|-|
|`m_key`|키 요소를 저장하는 데이터 멤버입니다.|
|`m_value`|값 요소를 저장하는 데이터 멤버입니다.|

## <a name="crbtreecrbtree"></a><a name="dtor"></a>CRB트리::~CRB트리

소멸자입니다.

```
~CRBTree() throw();
```

### <a name="remarks"></a>설명

할당된 리소스를 해제합니다. [CRBTree::RemoveAll을](#removeall) 호출하여 모든 요소를 삭제합니다.

## <a name="crbtreefindfirstkeyafter"></a><a name="findfirstkeyafter"></a>CRBTree::찾기퍼스트키 후

사용 가능한 다음 키를 사용하는 요소의 위치를 찾으려면 이 메서드를 호출합니다.

```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키 값입니다.

### <a name="return-value"></a>Return Value

사용 가능한 다음 키를 사용하는 요소의 위치 값을 반환합니다. 요소가 더 이상 없는 경우 NULL이 반환됩니다.

### <a name="remarks"></a>설명

이 방법을 사용하면 위치 값을 미리 계산하지 않고도 트리를 쉽게 통과할 수 있습니다.

## <a name="crbtreegetat"></a><a name="getat"></a>CRBTree::GetAt

이 메서드를 호출하여 트리의 지정된 위치에 요소를 가져옵니다.

```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
위치 값입니다.

*key*<br/>
키를 받는 변수입니다.

*value*<br/>
값을 받는 변수입니다.

### <a name="return-value"></a>Return Value

처음 두 양식은 [CPair에](#cpair_class)대한 포인터를 반환합니다. 세 번째 양식은 지정된 위치에 대한 키와 값을 얻습니다.

### <a name="remarks"></a>설명

위치 값은 이전에 [CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::GetTailPosition](#gettailposition)와 같은 메서드에 대한 호출로 결정할 수 있습니다.

디버그 빌드에서 *pos가* NULL과 같으면 어설션 오류가 발생합니다.

## <a name="crbtreegetcount"></a><a name="getcount"></a>CRBTree::겟카운트

이 메서드를 호출하여 트리의 요소 수를 가져옵니다.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Return Value

트리에 저장된 요소 수(각 키/값 쌍은 하나의 요소)를 반환합니다.

## <a name="crbtreegetheadposition"></a><a name="getheadposition"></a>CRBTree::GetHeadposition

이 메서드를 호출하여 트리의 헤드에 있는 요소에 대한 위치 값을 가져옵니다.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Return Value

트리의 헤드에 있는 요소에 대한 위치 값을 반환합니다.

### <a name="remarks"></a>설명

반환되는 `GetHeadPosition` 값은 [CRBTree::GetKeyAt](#getkeyat) 또는 [CRBTree::GetNext에서](#getnext) 트리를 탐색하고 값을 검색하는 메서드와 함께 사용할 수 있습니다.

## <a name="crbtreegetkeyat"></a><a name="getkeyat"></a>CRBTree::GetKeyAt

이 메서드를 호출하여 트리의 지정된 위치에서 키를 가져옵니다.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
위치 값입니다.

### <a name="return-value"></a>Return Value

트리의 위치 *pos에* 저장된 키를 반환합니다.

### <a name="remarks"></a>설명

*pos가* 유효한 위치 값이 아닌 경우 결과를 예측할 수 없습니다. 디버그 빌드에서 *pos가* NULL과 같으면 어설션 오류가 발생합니다.

## <a name="crbtreegetnext"></a><a name="getnext"></a>CRBTree::GetNext

이 메서드를 호출하여 개체에 저장된 `CRBTree` 요소에 대한 포인터를 가져오고 위치를 다음 요소로 이동합니다.

```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter와](#findfirstkeyafter)같은 메서드에 대한 이전 호출에 의해 반환된 위치 카운터입니다.

### <a name="return-value"></a>Return Value

트리의 다음 [CPair](#cpair_class) 값에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

*pos* 위치 카운터는 각 호출 후 업데이트됩니다. 검색된 요소가 트리의 마지막 요소인 경우 *pos는* NULL로 설정됩니다.

## <a name="crbtreegetnextassoc"></a><a name="getnextassoc"></a>CRBTree::GetNextAssoc

맵에 저장된 요소의 키와 값을 얻고 위치를 다음 요소로 진행하려면 이 메서드를 호출합니다.

```cpp
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter와](#findfirstkeyafter)같은 메서드에 대한 이전 호출에 의해 반환된 위치 카운터입니다.

*key*<br/>
트리 키의 형식을 지정하는 템플릿 매개 변수입니다.

*value*<br/>
트리 값의 형식을 지정하는 템플릿 매개 변수입니다.

### <a name="remarks"></a>설명

*pos* 위치 카운터는 각 호출 후 업데이트됩니다. 검색된 요소가 트리의 마지막 요소인 경우 *pos는* NULL로 설정됩니다.

## <a name="crbtreegetnextkey"></a><a name="getnextkey"></a>CRBTree::GetNextKey

이 메서드를 호출하여 트리에 저장된 요소의 키를 얻고 위치를 다음 요소로 이동합니다.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter와](#findfirstkeyafter)같은 메서드에 대한 이전 호출에 의해 반환된 위치 카운터입니다.

### <a name="return-value"></a>Return Value

트리의 다음 키에 대한 참조를 반환합니다.

### <a name="remarks"></a>설명

현재 위치 카운터, *pos를*업데이트합니다. 트리에 더 이상 항목이 없는 경우 위치 카운터는 NULL로 설정됩니다.

## <a name="crbtreegetnextvalue"></a><a name="getnextvalue"></a>CRBTree::GetNextValue

이 메서드를 호출하여 트리에 저장된 요소의 값을 얻고 위치를 다음 요소로 이동합니다.

```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter와](#findfirstkeyafter)같은 메서드에 대한 이전 호출에 의해 반환된 위치 카운터입니다.

### <a name="return-value"></a>Return Value

트리의 다음 값에 대한 참조를 반환합니다.

### <a name="remarks"></a>설명

현재 위치 카운터, *pos를*업데이트합니다. 트리에 더 이상 항목이 없는 경우 위치 카운터는 NULL로 설정됩니다.

## <a name="crbtreegetprev"></a><a name="getprev"></a>CRBTree ::GetPrev

이 메서드를 호출하여 개체에 저장된 `CRBTree` 요소에 대한 포인터를 얻은 다음 위치를 이전 요소로 업데이트합니다.

```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter와](#findfirstkeyafter)같은 메서드에 대한 이전 호출에 의해 반환된 위치 카운터입니다.

### <a name="return-value"></a>Return Value

트리에 저장된 이전 [CPair](#cpair_class) 값에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

현재 위치 카운터, *pos를*업데이트합니다. 트리에 더 이상 항목이 없는 경우 위치 카운터는 NULL로 설정됩니다.

## <a name="crbtreegettailposition"></a><a name="gettailposition"></a>CRBTree::GetTail포지션

이 메서드를 호출하여 트리의 꼬리에 있는 요소에 대한 위치 값을 가져옵니다.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Return Value

트리의 꼬리에 있는 요소에 대한 위치 값을 반환합니다.

### <a name="remarks"></a>설명

반환되는 `GetTailPosition` 값은 [CRBTree::GetKeyAt](#getkeyat) 또는 [CRBTree::GetPrev와](#getprev) 같은 메서드를 사용하여 트리를 탐색하고 값을 검색할 수 있습니다.

## <a name="crbtreegetvalueat"></a><a name="getvalueat"></a>CRBTree::GetValueAt

이 메서드를 호출하여 개체의 지정된 위치에 `CRBTree` 저장된 값을 검색합니다.

```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter와](#findfirstkeyafter)같은 메서드에 대한 이전 호출에 의해 반환된 위치 카운터입니다.

### <a name="return-value"></a>Return Value

개체의 지정된 위치에 저장된 값에 대한 `CRBTree` 참조를 반환합니다.

## <a name="crbtreeisempty"></a><a name="isempty"></a>CRBTree::비어 있음

빈 트리 개체를 테스트하려면 이 메서드를 호출합니다.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Return Value

트리가 비어 있는 경우 TRUE를 반환합니다.

## <a name="crbtreekinargtype"></a><a name="kinargtype"></a>CRBTree::키나르그타입

키가 입력 인수로 전달될 때 사용되는 형식입니다.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="crbtreekoutargtype"></a><a name="koutargtype"></a>CRBTree::쿠타르그타입

키가 출력 인수로 반환될 때 사용되는 형식입니다.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="crbtreeremoveall"></a><a name="removeall"></a>CRBTree::모두 제거

이 메서드를 호출하여 개체에서 모든 요소를 제거합니다. `CRBTree`

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>설명

개체를 `CRBTree` 지우고 요소를 저장하는 데 사용되는 메모리를 해제합니다.

## <a name="crbtreeremoveat"></a><a name="removeat"></a>CRBTree::제거

이 메서드를 호출하여 개체의 지정된 `CRBTree` 위치에서 요소를 제거합니다.

```cpp
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter와](#findfirstkeyafter)같은 메서드에 대한 이전 호출에 의해 반환된 위치 카운터입니다.

### <a name="remarks"></a>설명

지정된 위치에 저장된 키/값 쌍을 제거합니다. 요소를 저장하는 데 사용되는 메모리가 해제됩니다. *pos에서* 참조하는 위치는 유효하지 않으며 트리의 다른 요소의 위치는 유효하지만 반드시 동일한 순서를 유지하지는 않습니다.

## <a name="crbtreesetvalueat"></a><a name="setvalueat"></a>CRBTree::설정값

이 메서드를 호출하여 개체의 지정된 위치에 `CRBTree` 저장된 값을 변경합니다.

```cpp
void SetValueAt(POSITION pos, VINARGTYPE value);
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
[CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter와](#findfirstkeyafter)같은 메서드에 대한 이전 호출에 의해 반환된 위치 카운터입니다.

*value*<br/>
개체에 추가할 값입니다. `CRBTree`

### <a name="remarks"></a>설명

개체의 지정된 위치에 저장된 값 `CRBTree` 요소를 변경합니다.

## <a name="crbtreevinargtype"></a><a name="vinargtype"></a>CRBTree::비나르그타입

값이 입력 인수로 전달될 때 사용되는 형식입니다.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="crbtreevoutargtype"></a><a name="voutargtype"></a>CRBTree::부타르그타입

값이 출력 인수로 전달될 때 사용되는 형식입니다.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)
