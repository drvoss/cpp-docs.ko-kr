---
title: CAtlList 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlList
- ATLCOLL/ATL::CAtlList
- ATLCOLL/ATL::CAtlList::INARGTYPE
- ATLCOLL/ATL::CAtlList::CAtlList
- ATLCOLL/ATL::CAtlList::AddHead
- ATLCOLL/ATL::CAtlList::AddHeadList
- ATLCOLL/ATL::CAtlList::AddTail
- ATLCOLL/ATL::CAtlList::AddTailList
- ATLCOLL/ATL::CAtlList::AssertValid
- ATLCOLL/ATL::CAtlList::Find
- ATLCOLL/ATL::CAtlList::FindIndex
- ATLCOLL/ATL::CAtlList::GetAt
- ATLCOLL/ATL::CAtlList::GetCount
- ATLCOLL/ATL::CAtlList::GetHead
- ATLCOLL/ATL::CAtlList::GetHeadPosition
- ATLCOLL/ATL::CAtlList::GetNext
- ATLCOLL/ATL::CAtlList::GetPrev
- ATLCOLL/ATL::CAtlList::GetTail
- ATLCOLL/ATL::CAtlList::GetTailPosition
- ATLCOLL/ATL::CAtlList::InsertAfter
- ATLCOLL/ATL::CAtlList::InsertBefore
- ATLCOLL/ATL::CAtlList::IsEmpty
- ATLCOLL/ATL::CAtlList::MoveToHead
- ATLCOLL/ATL::CAtlList::MoveToTail
- ATLCOLL/ATL::CAtlList::RemoveAll
- ATLCOLL/ATL::CAtlList::RemoveAt
- ATLCOLL/ATL::CAtlList::RemoveHead
- ATLCOLL/ATL::CAtlList::RemoveHeadNoReturn
- ATLCOLL/ATL::CAtlList::RemoveTail
- ATLCOLL/ATL::CAtlList::RemoveTailNoReturn
- ATLCOLL/ATL::CAtlList::SetAt
- ATLCOLL/ATL::CAtlList::SwapElements
helpviewer_keywords:
- CAtlList class
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
ms.openlocfilehash: 91b1841423fe159bb5fdd0f06a112c601b1dbc83
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318938"
---
# <a name="catllist-class"></a>CAtlList 클래스

이 클래스는 목록 개체를 만들고 관리하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlList
```

#### <a name="parameters"></a>매개 변수

*전자*<br/>
요소 형식입니다.

*에트해협*<br/>
요소를 복사하거나 이동하는 데 사용되는 코드입니다. 자세한 내용은 [CElementTraits 클래스를](../../atl/reference/celementtraits-class.md) 참조하십시오.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[카틀리스트::INARGTYPE](#inargtype)||

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[카틀리스트:::카틀리스트](#catllist)|생성자입니다.|
|[카틀리스트::~카틀리스트](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[카틀리스트::애드헤드](#addhead)|이 메서드를 호출하여 목록의 헤드에 요소를 추가합니다.|
|[카틀리스트::추가 헤드 리스트](#addheadlist)|이 메서드를 호출하여 목록의 헤드에 기존 목록을 추가합니다.|
|[카틀리스트::애드테일](#addtail)|이 메서드를 호출하여 이 목록의 꼬리에 요소를 추가합니다.|
|[카틀리스트::애드테일리스트](#addtaillist)|이 메서드를 호출하여 이 목록의 꼬리에 기존 목록을 추가합니다.|
|[카틀리스트::어설션 유효](#assertvalid)|목록이 유효한지 확인하려면 이 메서드를 호출합니다.|
|[카틀리스트::찾기](#find)|지정된 요소에 대 한 목록을 검색 하려면이 메서드를 호출 합니다.|
|[카틀리스트::찾기 인덱스](#findindex)|인덱스 값이 주어지면 이 메서드를 호출하여 요소의 위치를 가져옵니다.|
|[카틀리스트::겟앳](#getat)|이 메서드를 호출하여 목록의 지정된 위치에 요소를 반환합니다.|
|[카틀리스트::겟카운트](#getcount)|이 메서드를 호출하여 목록의 개체 수를 반환합니다.|
|[카틀리스트::겟헤드](#gethead)|이 메서드를 호출하여 목록의 헤드에 있는 요소를 반환합니다.|
|[카틀리스트::GetHeadposition](#getheadposition)|목록의 머리의 위치를 얻기 위해이 메서드를 호출합니다.|
|[카틀리스트::GetNext](#getnext)|이 메서드를 호출하여 목록에서 다음 요소를 반환합니다.|
|[카틀리스트::겟프레프](#getprev)|이 메서드를 호출하여 목록에서 이전 요소를 반환합니다.|
|[카틀리스트::겟테일](#gettail)|이 메서드를 호출하여 목록의 꼬리에 있는 요소를 반환합니다.|
|[카틀리스트::GetTailPosition](#gettailposition)|목록의 꼬리 위치를 얻으려면이 메서드를 호출합니다.|
|[카틀리스트::삽입 후](#insertafter)|지정된 위치 다음 목록에 새 요소를 삽입하려면 이 메서드를 호출합니다.|
|[카틀리스트::삽입 전](#insertbefore)|지정된 위치 앞에 목록에 새 요소를 삽입하려면 이 메서드를 호출합니다.|
|[카틀리스트::비어 있음](#isempty)|이 메서드를 호출하여 목록이 비어 있는지 확인합니다.|
|[카틀리스트::무브토헤드](#movetohead)|지정된 요소를 목록의 헤드로 이동하려면 이 메서드를 호출합니다.|
|[카틀리스트::무브토테일](#movetotail)|지정된 요소를 목록의 꼬리로 이동하려면 이 메서드를 호출합니다.|
|[카틀리스트::모두 제거](#removeall)|이 메서드를 호출하여 목록에서 모든 요소를 제거합니다.|
|[카틀리스트::리무트앳](#removeat)|이 메서드를 호출하여 목록에서 단일 요소를 제거합니다.|
|[카틀리스트::제거헤드](#removehead)|이 메서드를 호출하여 목록의 헤드에 있는 요소를 제거합니다.|
|[카틀리스트::제거헤드노리턴](#removeheadnoreturn)|값을 반환하지 않고 목록의 헤드에 있는 요소를 제거하려면 이 메서드를 호출합니다.|
|[카틀리스트::제거테일](#removetail)|이 메서드를 호출하여 목록의 꼬리에 있는 요소를 제거합니다.|
|[카틀리스트::제거테일노리턴](#removetailnoreturn)|값을 반환하지 않고 목록의 꼬리에 있는 요소를 제거하려면 이 메서드를 호출합니다.|
|[카틀리스트::세팅](#setat)|이 메서드를 호출하여 목록의 지정된 위치에 요소 값을 설정합니다.|
|[카틀리스트::스왑엘리먼트](#swapelements)|이 메서드를 호출하여 목록의 요소를 바꿉꿉입니다.|

## <a name="remarks"></a>설명

클래스는 `CAtlList` 순차적으로 또는 값으로 액세스할 수 있는 고유하지 않은 개체의 정렬된 목록을 지원합니다. `CAtlList`목록은 이중으로 연결된 목록처럼 행동합니다. 각 목록에는 머리와 꼬리가 있으며 새 요소(또는 경우에 따라 목록)를 목록의 끝에 추가하거나 특정 요소 앞또는 후에 삽입할 수 있습니다.

대부분의 메서드는 `CAtlList` 위치 값을 사용합니다. 이 값은 요소가 저장되는 실제 메모리 위치를 참조하는 메서드에서 사용되며 직접 계산하거나 예측해서는 안 됩니다. 목록에서 *nth*요소에 액세스해야 하는 경우 [CAtlList:FindIndex](#findindex) 메서드는 지정된 인덱스에 해당하는 위치 값을 반환합니다. 방법 [CAtlList::GetNext](#getnext) 및 [CAtlList::GetPrev](#getprev) 목록의 개체를 통해 반복 하는 데 사용할 수 있습니다.

ATL에서 사용할 수 있는 컬렉션 클래스에 대한 자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="catllistaddhead"></a><a name="addhead"></a>카틀리스트::애드헤드

이 메서드를 호출하여 목록의 헤드에 요소를 추가합니다.

```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```

### <a name="parameters"></a>매개 변수

*요소*<br/>
새 요소입니다.

### <a name="return-value"></a>Return Value

새로 추가된 요소의 위치를 반환합니다.

### <a name="remarks"></a>설명

첫 번째 버전을 사용하는 경우 빈 요소는 복사본 생성자가 아닌 기본 생성자사용을 사용하여 만들어집니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]

## <a name="catllistaddheadlist"></a><a name="addheadlist"></a>카틀리스트::추가 헤드 리스트

이 메서드를 호출하여 목록의 헤드에 기존 목록을 추가합니다.

```
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>매개 변수

*plNew*<br/>
추가할 목록입니다.

### <a name="remarks"></a>설명

*plNew가* 가리키는 목록은 기존 목록의 시작 부분에 삽입됩니다. 디버그 빌드에서 *plNew가* NULL과 같으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]

## <a name="catllistaddtail"></a><a name="addtail"></a>카틀리스트::애드테일

이 메서드를 호출하여 이 목록의 꼬리에 요소를 추가합니다.

```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```

### <a name="parameters"></a>매개 변수

*요소*<br/>
추가할 요소입니다.

### <a name="return-value"></a>Return Value

새로 추가된 요소의 위치를 반환합니다.

### <a name="remarks"></a>설명

첫 번째 버전을 사용하는 경우 빈 요소는 복사본 생성자가 아닌 기본 생성자사용을 사용하여 만들어집니다. 요소가 목록의 끝에 추가되므로 이제 꼬리가 됩니다. 이 메서드는 빈 목록과 함께 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]

## <a name="catllistaddtaillist"></a><a name="addtaillist"></a>카틀리스트::애드테일리스트

이 메서드를 호출하여 이 목록의 꼬리에 기존 목록을 추가합니다.

```
void AddTailList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>매개 변수

*plNew*<br/>
추가할 목록입니다.

### <a name="remarks"></a>설명

*plNew가* 가리키는 목록은 목록 개체의 마지막 요소(있는 경우) 후에 삽입됩니다. 따라서 *plNew* 목록의 마지막 요소는 꼬리가 됩니다. 디버그 빌드에서 *plNew가* NULL과 같으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]

## <a name="catllistassertvalid"></a><a name="assertvalid"></a>카틀리스트::어설션 유효

목록이 유효한지 확인하려면 이 메서드를 호출합니다.

```
void AssertValid() const;
```

### <a name="remarks"></a>설명

디버그 빌드에서 목록 개체가 유효하지 않은 경우 어설션 오류가 발생합니다. 유효하려면 빈 목록에 NULL을 가리키는 머리와 꼬리가 모두 있어야 하며 비어 있지 않은 목록에는 유효한 주소를 가리키는 머리와 꼬리가 모두 있어야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]

## <a name="catllistcatllist"></a><a name="catllist"></a>카틀리스트:::카틀리스트

생성자입니다.

```
CAtlList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
블록의 크기입니다.

### <a name="remarks"></a>설명

개체의 생성자입니다. `CAtlList` 블록 크기는 새 요소가 필요할 때 할당된 메모리 양을 측정한 값입니다. 블록 크기가 클수록 메모리 할당 루틴에 대한 호출이 줄어들지만 더 많은 리소스를 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#18](../../atl/codesnippet/cpp/catllist-class_6.cpp)]

## <a name="catllistcatllist"></a><a name="dtor"></a>카틀리스트::~카틀리스트

소멸자입니다.

```
~CAtlList() throw();
```

### <a name="remarks"></a>설명

[CAtlList::RemoveAll을](#removeall) 호출하여 목록에서 모든 요소를 제거하는 등 할당된 모든 리소스를 해제합니다.

디버그 빌드에서 호출 후 목록에 일부 요소가 여전히 포함되어 있으면 `RemoveAll`어설션 오류가 발생합니다.

## <a name="catllistfind"></a><a name="find"></a>카틀리스트::찾기

지정된 요소에 대 한 목록을 검색 하려면이 메서드를 호출 합니다.

```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```

### <a name="parameters"></a>매개 변수

*요소*<br/>
목록에서 찾을 요소입니다.

*포스스타트애프터*<br/>
검색의 시작 위치입니다. 값을 지정하지 않으면 head 요소로 검색이 시작됩니다.

### <a name="return-value"></a>Return Value

발견 된 경우 요소의 POSITION 값을 반환, 그렇지 않으면 NULL을 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 목록 개체가 유효하지 않거나 *posStartAfter* 값이 범위를 벗어난 경우 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]

## <a name="catllistfindindex"></a><a name="findindex"></a>카틀리스트::찾기 인덱스

인덱스 값이 주어지면 이 메서드를 호출하여 요소의 위치를 가져옵니다.

```
POSITION FindIndex(size_t iElement) const throw();
```

### <a name="parameters"></a>매개 변수

*아이 엘리먼트*<br/>
필요한 목록 요소의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

*iElement가* 범위를 벗어난 경우 해당 위치 값 또는 NULL을 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 지정된 인덱스 값에 해당하는 POSITION를 반환하여 목록의 *nth*요소에 액세스할 수 있도록 합니다.

디버그 빌드에서 목록 개체가 유효하지 않은 경우 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]

## <a name="catllistgetat"></a><a name="getat"></a>카틀리스트::겟앳

이 메서드를 호출하여 목록의 지정된 위치에 요소를 반환합니다.

```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
특정 요소를 지정하는 POSITION 값입니다.

### <a name="return-value"></a>Return Value

요소에 대한 참조 또는 복사본입니다.

### <a name="remarks"></a>설명

목록이 **const인**경우 `GetAt` 요소의 복사본을 반환합니다. 이렇게 하면 할당 문의 오른쪽에서만 메서드를 사용할 수 있으며 목록이 수정되지 않도록 보호할 수 있습니다.

목록이 **const가**아닌 `GetAt` 경우 요소에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 메서드를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

디버그 빌드에서 *pos가* NULL과 같으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[CAtlList::FindIndex](#findindex)에 대한 예제를 참조하십시오.

## <a name="catllistgetcount"></a><a name="getcount"></a>카틀리스트::겟카운트

이 메서드를 호출하여 목록의 개체 수를 반환합니다.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Return Value

목록에 있는 요소 수를 반환합니다.

### <a name="example"></a>예제

[CAtlList::Find에](#find)대한 예제를 참조하십시오.

## <a name="catllistgethead"></a><a name="gethead"></a>카틀리스트::겟헤드

이 메서드를 호출하여 목록의 헤드에 있는 요소를 반환합니다.

```
E& GetHead() throw();
const E& GetHead() const throw();
```

### <a name="return-value"></a>Return Value

목록의 헤드에 있는 요소에 대한 참조 또는 복사본을 반환합니다.

### <a name="remarks"></a>설명

목록이 **const인**경우 `GetHead` 목록의 헤드에 있는 요소의 복사본을 반환합니다. 이렇게 하면 할당 문의 오른쪽에서만 메서드를 사용할 수 있으며 목록이 수정되지 않도록 보호할 수 있습니다.

목록이 **const가**아닌 `GetHead` 경우 목록의 헤드에 있는 요소에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 메서드를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

디버그 빌드에서 목록의 머리가 NULL을 가리키는 경우 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[CAtlList::AddHead](#addhead)에 대한 예제를 참조하십시오.

## <a name="catllistgetheadposition"></a><a name="getheadposition"></a>카틀리스트::GetHeadposition

목록의 머리의 위치를 얻기 위해이 메서드를 호출합니다.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Return Value

목록의 헤드에 있는 요소에 해당하는 POSITION 값을 반환합니다.

### <a name="remarks"></a>설명

목록이 비어 있으면 반환되는 값은 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#21](../../atl/codesnippet/cpp/catllist-class_9.cpp)]

## <a name="catllistgetnext"></a><a name="getnext"></a>카틀리스트::GetNext

이 메서드를 호출하여 목록에서 다음 요소를 반환합니다.

```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
이전 호출에서 `GetNext`반환되는 위치 값 [: CAtlList::GetHeadPosition](#getheadposition)또는 기타 `CAtlList` 메서드입니다.

### <a name="return-value"></a>Return Value

목록이 **const인**경우 `GetNext` 목록의 다음 요소의 복사본을 반환합니다. 이렇게 하면 할당 문의 오른쪽에서만 메서드를 사용할 수 있으며 목록이 수정되지 않도록 보호할 수 있습니다.

목록이 **const가**아닌 `GetNext` 경우 목록의 다음 요소에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 메서드를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

POSITION 카운터 *pos는*목록의 다음 요소를 가리키도록 업데이트되거나 요소가 더 이상 없는 경우 NULL로 업데이트됩니다. 디버그 빌드에서 *pos가* NULL과 같으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[CAtlList::GetHeadPosition에](#getheadposition)대한 예제를 참조하십시오.

## <a name="catllistgetprev"></a><a name="getprev"></a>카틀리스트::겟프레프

이 메서드를 호출하여 목록에서 이전 요소를 반환합니다.

```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
이전 호출에서 `GetPrev`반환되는 위치 값 [: CAtlList::GetTailPosition](#gettailposition)및 기타 `CAtlList` 메서드입니다.

### <a name="return-value"></a>Return Value

목록이 **const인**경우 `GetPrev` 목록 요소의 복사본을 반환합니다. 이렇게 하면 할당 문의 오른쪽에서만 메서드를 사용할 수 있으며 목록이 수정되지 않도록 보호할 수 있습니다.

목록이 **const가**아닌 `GetPrev` 경우 목록의 요소에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 메서드를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

POSITION 카운터 *pos는*목록의 이전 요소를 가리키도록 업데이트되거나 요소가 더 이상 없는 경우 NULL로 업데이트됩니다. 디버그 빌드에서 *pos가* NULL과 같으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[CAtlList::GetTailPosition에](#gettailposition)대한 예제를 참조하십시오.

## <a name="catllistgettail"></a><a name="gettail"></a>카틀리스트::겟테일

이 메서드를 호출하여 목록의 꼬리에 있는 요소를 반환합니다.

```
E& GetTail() throw();
const E& GetTail() const throw();
```

### <a name="return-value"></a>Return Value

목록의 꼬리에 있는 요소에 대한 참조 또는 복사본을 반환합니다.

### <a name="remarks"></a>설명

목록이 **const인**경우 `GetTail` 목록의 헤드에 있는 요소의 복사본을 반환합니다. 이렇게 하면 할당 문의 오른쪽에서만 메서드를 사용할 수 있으며 목록이 수정되지 않도록 보호할 수 있습니다.

목록이 **const가**아닌 `GetTail` 경우 목록의 헤드에 있는 요소에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 메서드를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

디버그 빌드에서 목록의 꼬리가 NULL을 가리키는 경우 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[CAtlList::AddTail](#addtail)에 대한 예제를 참조하십시오.

## <a name="catllistgettailposition"></a><a name="gettailposition"></a>카틀리스트::GetTailPosition

목록의 꼬리 위치를 얻으려면이 메서드를 호출합니다.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Return Value

목록의 꼬리에 있는 요소에 해당하는 POSITION 값을 반환합니다.

### <a name="remarks"></a>설명

목록이 비어 있으면 반환되는 값은 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#22](../../atl/codesnippet/cpp/catllist-class_10.cpp)]

## <a name="catllistinargtype"></a><a name="inargtype"></a>카틀리스트::INARGTYPE

요소가 입력 인수로 전달될 때 사용되는 형식입니다.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

## <a name="catllistinsertafter"></a><a name="insertafter"></a>카틀리스트::삽입 후

지정된 위치 다음 목록에 새 요소를 삽입하려면 이 메서드를 호출합니다.

```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
새 요소가 삽입되는 위치 값입니다.

*요소*<br/>
삽입할 요소입니다.

### <a name="return-value"></a>Return Value

새 요소의 POSITION 값을 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 목록이 유효하지 않거나 삽입이 실패하거나 꼬리 다음의 요소를 삽입하려고 시도하는 경우 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]

## <a name="catllistinsertbefore"></a><a name="insertbefore"></a>카틀리스트::삽입 전

지정된 위치 앞에 목록에 새 요소를 삽입하려면 이 메서드를 호출합니다.

```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
새 요소는 이 POSITION 값 앞에 목록에 삽입됩니다.

*요소*<br/>
삽입할 요소입니다.

### <a name="return-value"></a>Return Value

새 요소의 POSITION 값을 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 목록이 유효하지 않거나, 삽입이 실패하거나, 헤드 앞에 요소를 삽입하려고 시도하는 경우 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]

## <a name="catllistisempty"></a><a name="isempty"></a>카틀리스트::비어 있음

이 메서드를 호출하여 목록이 비어 있는지 확인합니다.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Return Value

목록에 개체가 없는 경우 true를 반환합니다( 그렇지 않으면 false).

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]

## <a name="catllistmovetohead"></a><a name="movetohead"></a>카틀리스트::무브토헤드

지정된 요소를 목록의 헤드로 이동하려면 이 메서드를 호출합니다.

```
void MoveToHead(POSITION pos) throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
이동할 요소의 위치 값입니다.

### <a name="remarks"></a>설명

지정된 요소가 현재 위치에서 목록의 머리로 이동됩니다. 디버그 빌드에서 *pos가* NULL과 같으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]

## <a name="catllistmovetotail"></a><a name="movetotail"></a>카틀리스트::무브토테일

지정된 요소를 목록의 꼬리로 이동하려면 이 메서드를 호출합니다.

```
void MoveToTail(POSITION pos) throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
이동할 요소의 위치 값입니다.

### <a name="remarks"></a>설명

지정된 요소가 현재 위치에서 목록의 꼬리로 이동됩니다. 디버그 빌드에서 *pos가* NULL과 같으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[CAtlList::MoveToHead에](#movetohead)대한 예제를 참조하십시오.

## <a name="catllistremoveall"></a><a name="removeall"></a>카틀리스트::모두 제거

이 메서드를 호출하여 목록에서 모든 요소를 제거합니다.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>설명

이 메서드는 목록에서 모든 요소를 제거 하 고 할당 된 메모리를 해제 합니다. 디버그 빌드에서 모든 요소가 삭제되지 않거나 목록 구조가 손상된 경우 ATLASSERT가 발생합니다.

### <a name="example"></a>예제

[CAtlList::IsEmpty](#isempty)에 대한 예제를 참조하십시오.

## <a name="catllistremoveat"></a><a name="removeat"></a>카틀리스트::리무트앳

이 메서드를 호출하여 목록에서 단일 요소를 제거합니다.

```
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
제거할 요소의 위치 값입니다.

### <a name="remarks"></a>설명

*pos에서* 참조하는 요소가 제거되고 메모리가 해제됩니다. 목록의 머리 `RemoveAt` 또는 꼬리를 제거하는 데 사용할 수 있습니다.

디버그 빌드에서 목록이 유효하지 않거나 요소를 제거하면 목록 구조의 일부가 아닌 메모리에 액세스하는 경우 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]

## <a name="catllistremovehead"></a><a name="removehead"></a>카틀리스트::제거헤드

이 메서드를 호출하여 목록의 헤드에 있는 요소를 제거합니다.

```
E RemoveHead();
```

### <a name="return-value"></a>Return Value

목록의 헤드에 있는 요소를 반환합니다.

### <a name="remarks"></a>설명

헤드 요소가 목록에서 삭제되고 메모리가 해제됩니다. 요소의 복사본이 반환됩니다. 디버그 빌드에서 목록이 비어 있으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]

## <a name="catllistremoveheadnoreturn"></a><a name="removeheadnoreturn"></a>카틀리스트::제거헤드노리턴

값을 반환하지 않고 목록의 헤드에 있는 요소를 제거하려면 이 메서드를 호출합니다.

```
void RemoveHeadNoReturn() throw();
```

### <a name="remarks"></a>설명

헤드 요소가 목록에서 삭제되고 메모리가 해제됩니다. 디버그 빌드에서 목록이 비어 있으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[CAtlList::IsEmpty](#isempty)에 대한 예제를 참조하십시오.

## <a name="catllistremovetail"></a><a name="removetail"></a>카틀리스트::제거테일

이 메서드를 호출하여 목록의 꼬리에 있는 요소를 제거합니다.

```
E RemoveTail();
```

### <a name="return-value"></a>Return Value

목록의 꼬리에 있는 요소를 반환합니다.

### <a name="remarks"></a>설명

tail 요소가 목록에서 삭제되고 메모리가 해제됩니다. 요소의 복사본이 반환됩니다. 디버그 빌드에서 목록이 비어 있으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]

## <a name="catllistremovetailnoreturn"></a><a name="removetailnoreturn"></a>카틀리스트::제거테일노리턴

값을 반환하지 않고 목록의 꼬리에 있는 요소를 제거하려면 이 메서드를 호출합니다.

```
void RemoveTailNoReturn() throw();
```

### <a name="remarks"></a>설명

tail 요소가 목록에서 삭제되고 메모리가 해제됩니다. 디버그 빌드에서 목록이 비어 있으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[CAtlList::IsEmpty](#isempty)에 대한 예제를 참조하십시오.

## <a name="catllistsetat"></a><a name="setat"></a>카틀리스트::세팅

이 메서드를 호출하여 목록의 지정된 위치에 요소 값을 설정합니다.

```
void SetAt(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
변경할 요소에 해당하는 POSITION 값입니다.

*요소*<br/>
새 요소 값입니다.

### <a name="remarks"></a>설명

기존 값을 *요소로*바꿉꿉습니다. 디버그 빌드에서 *pos가* NULL과 같으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]

## <a name="catllistswapelements"></a><a name="swapelements"></a>카틀리스트::스왑엘리먼트

이 메서드를 호출하여 목록의 요소를 바꿉꿉입니다.

```
void SwapElements(POSITION pos1, POSITION pos2) throw();
```

### <a name="parameters"></a>매개 변수

*pos1*<br/>
첫 번째 위치 값입니다.

*pos2*<br/>
두 번째 위치 값입니다.

### <a name="remarks"></a>설명

지정된 두 위치에서 요소를 바꿉습니다. 디버그 빌드에서 두 위치 값이 NULL과 같으면 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]

## <a name="see-also"></a>참고 항목

[CList 클래스](../../mfc/reference/clist-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
