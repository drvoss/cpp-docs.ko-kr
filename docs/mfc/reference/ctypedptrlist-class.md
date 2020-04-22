---
title: CTypedPtrList 클래스
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
helpviewer_keywords:
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
ms.openlocfilehash: 9f4899d4470903a4145cc171579e4b251b984f95
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747193"
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList 클래스

클래스 `CPtrList`의 개체에 대한 형식 안전 "래퍼"를 제공합니다.

## <a name="syntax"></a>구문

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrList : public BASE_CLASS
```

#### <a name="parameters"></a>매개 변수

*BASE_CLASS*<br/>
형식이 있는 포인터 목록 클래스의 기본 클래스입니다. 포인터 목록 클래스(또는)여야 `CObList` `CPtrList`합니다.

*유형*<br/>
기본 클래스 목록에 저장된 요소의 유형입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CTypedPtrList::추가 헤드](#addhead)|목록의 헤드에 요소(또는 다른 목록의 모든 요소)를 추가합니다(새 헤드를 만듭니다).|
|[CTypedPtrList::추가 꼬리](#addtail)|목록의 꼬리에 요소(또는 다른 목록의 모든 요소)를 추가합니다(새 꼬리를 만듭니다).|
|[CTypedPtrList::GetAt](#getat)|지정된 위치에 요소를 가져옵니다.|
|[CTypedPtrList::GetHead](#gethead)|목록의 머리 요소를 반환합니다(비일 수 없음).|
|[CTypedPtrList::GetNext](#getnext)|반복에 대한 다음 요소를 가져옵니다.|
|[CTypedPtrList::GetPrev](#getprev)|반복에 대한 이전 요소를 가져옵니다.|
|[CTypedPtrList::GetTail](#gettail)|목록의 tail 요소를 반환합니다(비일 수 없음).|
|[CTypedPtrList::제거헤드](#removehead)|목록의 머리에서 요소를 제거합니다.|
|[CTypedPtrList::제거테일](#removetail)|목록의 꼬리에서 요소를 제거합니다.|
|[CTypedPtrList::SetAt](#setat)|지정된 위치에 요소를 설정합니다.|

## <a name="remarks"></a>설명

C++ `CTypedPtrList` 형식 `CObList` `CPtrList`검사 기능이 아닌 Or를 사용하는 경우 일치하지 않는 포인터 유형으로 인한 오류를 제거하는 데 도움이 됩니다.

또한 래퍼는 `CTypedPtrList` 사용하거나 `CObList` `CPtrList`에 필요한 많은 주조를 수행합니다.

모든 `CTypedPtrList` 함수가 인라인이기 때문에 이 템플릿을 사용하면 코드의 크기 나 속도에 큰 영향을 미치지 않습니다.

에서 `CObList` 파생된 목록은 직렬화할 수 `CPtrList` 있지만 파생된 목록은 직렬화할 수 없습니다.

`CTypedPtrList` 개체를 삭제하거나 해당 요소를 제거할 경우 참조하는 엔터티가 아니라 포인터만 제거됩니다.

사용에 `CTypedPtrList`대한 자세한 내용은 [문서 컬렉션](../../mfc/collections.md) 및 템플릿 기반 [클래스를](../../mfc/template-based-classes.md)참조하십시오.

## <a name="example"></a>예제

이 예제에서는 `CTypedPtrList`의 인스턴스를 만들고, 하나의 개체를 추가하고, 목록을 디스크에 직렬화한 다음, 개체를 삭제합니다.

[!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]

[!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`BASE_CLASS`

`_CTypedPtrList`

`CTypedPtrList`

## <a name="requirements"></a>요구 사항

**헤더:** afxtempl.h

## <a name="ctypedptrlistaddhead"></a><a name="addhead"></a>CTypedPtrList::추가 헤드

이 멤버 `BASE_CLASS`함수는 **::AddHead**를 호출합니다.

```
POSITION AddHead(TYPE newElement);
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
기본 클래스 목록에 저장된 요소의 유형입니다.

*new엘리먼트*<br/>
이 목록에 추가할 개체 포인터입니다. NULL 값이 허용됩니다.

*BASE_CLASS*<br/>
형식이 있는 포인터 목록 클래스의 기본 클래스입니다. 포인터 목록 [클래스(CObList](../../mfc/reference/coblist-class.md) 또는 [CPtrList)여야](../../mfc/reference/cptrlist-class.md)합니다.

*pNewList*<br/>
다른 [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) 개체에 대한 포인터입니다. *pNewList의* 요소가 이 목록에 추가됩니다.

### <a name="return-value"></a>Return Value

첫 번째 버전은 새로 삽입된 요소의 POSITION 값을 반환합니다.

### <a name="remarks"></a>설명

첫 번째 버전은 목록의 머리 앞에 새 요소를 추가합니다. 두 번째 버전은 머리 앞에 다른 요소 목록을 추가합니다.

## <a name="ctypedptrlistaddtail"></a><a name="addtail"></a>CTypedPtrList::추가 꼬리

이 멤버 `BASE_CLASS`함수는 **::AddTail**.

```
POSITION AddTail(TYPE newElement);
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
기본 클래스 목록에 저장된 요소의 유형입니다.

*new엘리먼트*<br/>
이 목록에 추가할 개체 포인터입니다. NULL 값이 허용됩니다.

*BASE_CLASS*<br/>
형식이 있는 포인터 목록 클래스의 기본 클래스입니다. 포인터 목록 [클래스(CObList](../../mfc/reference/coblist-class.md) 또는 [CPtrList)여야](../../mfc/reference/cptrlist-class.md)합니다.

*pNewList*<br/>
다른 [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) 개체에 대한 포인터입니다. *pNewList의* 요소가 이 목록에 추가됩니다.

### <a name="return-value"></a>Return Value

첫 번째 버전은 새로 삽입된 요소의 POSITION 값을 반환합니다.

### <a name="remarks"></a>설명

첫 번째 버전은 목록의 꼬리 앞에 새 요소를 추가합니다. 두 번째 버전은 목록의 꼬리 앞에 다른 요소 목록을 추가합니다.

## <a name="ctypedptrlistgetat"></a><a name="getat"></a>CTypedPtrList::GetAt

위치 형식의 변수는 목록의 키입니다.

```
TYPE& GetAt(POSITION position);
TYPE GetAt(POSITION position) const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
목록에 저장된 요소의 유형을 지정하는 템플릿 매개 변수입니다.

*위치*<br/>
이전 `GetHeadPosition` 또는 `Find` 멤버 함수 호출에서 반환된 POSITION 값입니다.

### <a name="return-value"></a>Return Value

에 대한 포인터를 `const CTypedPtrList`통해 목록에 액세스하는 `GetAt` 경우 템플릿 매개 변수 *TYPE에서*지정한 형식의 포인터를 반환합니다. 이렇게 하면 할당 문의 오른쪽에만 함수를 사용할 수 있으므로 목록이 수정되지 않도록 보호할 수 있습니다.

에 대한 포인터를 통해 목록이 직접 `CTypedPtrList`액세스되는 `GetAt` 경우 는 템플릿 매개 변수 *TYPE에*의해 지정된 형식의 포인터에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 함수를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

인덱스와 같지 않으며 POSITION 값으로 직접 작동할 수 없습니다. `GetAt`은 지정된 `CObject` 위치와 연결된 포인터를 검색합니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

이 인라인 `BASE_CLASS`함수는 **::GetAt 를 호출합니다.**

## <a name="ctypedptrlistgethead"></a><a name="gethead"></a>CTypedPtrList::GetHead

이 목록의 머리 요소를 나타내는 포인터를 가져옵니다.

```
TYPE& GetHead();
TYPE GetHead() const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
목록에 저장된 요소의 유형을 지정하는 템플릿 매개 변수입니다.

### <a name="return-value"></a>Return Value

에 대한 포인터를 `const CTypedPtrList`통해 목록에 액세스하는 `GetHead` 경우 템플릿 매개 변수 *TYPE에서*지정한 형식의 포인터를 반환합니다. 이렇게 하면 할당 문의 오른쪽에만 함수를 사용할 수 있으므로 목록이 수정되지 않도록 보호할 수 있습니다.

에 대한 포인터를 통해 목록이 직접 `CTypedPtrList`액세스되는 `GetHead` 경우 는 템플릿 매개 변수 *TYPE에*의해 지정된 형식의 포인터에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 함수를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

을 호출하기 `GetHead`전에 목록이 비어 있지 않은지 확인해야 합니다. 목록이 비어 있으면 Microsoft 재단 클래스 라이브러리의 디버그 버전이 어설션됩니다. [IsEmpty를](../../mfc/reference/coblist-class.md#isempty) 사용하여 목록에 요소가 포함되어 있는지 확인합니다.

## <a name="ctypedptrlistgetnext"></a><a name="getnext"></a>CTypedPtrList::GetNext

*rPosition로*식별된 목록 요소를 *rPosition* 가져옵니다.

```
TYPE& GetNext(POSITION& rPosition);
TYPE GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
이 목록에 포함된 요소 유형을 지정하는 템플릿 매개 변수입니다.

*rPosition*<br/>
이전 `GetNext`에서 반환 되는 POSITION 값에 대 한 참조입니다. `GetHeadPosition`

### <a name="return-value"></a>Return Value

에 대한 포인터를 `const CTypedPtrList`통해 목록에 액세스하는 `GetNext` 경우 템플릿 매개 변수 *TYPE에서*지정한 형식의 포인터를 반환합니다. 이렇게 하면 할당 문의 오른쪽에만 함수를 사용할 수 있으므로 목록이 수정되지 않도록 보호할 수 있습니다.

에 대한 포인터를 통해 목록이 직접 `CTypedPtrList`액세스되는 `GetNext` 경우 는 템플릿 매개 변수 *TYPE에*의해 지정된 형식의 포인터에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 함수를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

또는 [CPtrList ::Find에](../../mfc/reference/coblist-class.md#find)대한 호출로 초기 `GetHeadPosition` 위치를 설정하는 경우 정방향 반복 루프에서 사용할 `GetNext` 수 있습니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

검색된 요소가 목록의 마지막 요소인 경우 *rPosition의* 새 값이 NULL로 설정됩니다.

반복 중에 요소를 제거할 수 있습니다. [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)에 대한 예제를 참조하십시오.

## <a name="ctypedptrlistgetprev"></a><a name="getprev"></a>CTypedPtrList::GetPrev

*rPosition로*식별된 목록 요소를 *rPosition* 가져옵니다.

```
TYPE& GetPrev(POSITION& rPosition);
TYPE GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
이 목록에 포함된 요소 유형을 지정하는 템플릿 매개 변수입니다.

*rPosition*<br/>
이전 `GetPrev` 또는 다른 멤버 함수 호출에서 반환된 POSITION 값에 대한 참조입니다.

### <a name="return-value"></a>Return Value

에 대한 포인터를 `const CTypedPtrList`통해 목록에 액세스하는 `GetPrev` 경우 템플릿 매개 변수 *TYPE에서*지정한 형식의 포인터를 반환합니다. 이렇게 하면 할당 문의 오른쪽에만 함수를 사용할 수 있으므로 목록이 수정되지 않도록 보호할 수 있습니다.

에 대한 포인터를 통해 목록이 직접 `CTypedPtrList`액세스되는 `GetPrev` 경우 는 템플릿 매개 변수 *TYPE에*의해 지정된 형식의 포인터에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 함수를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

또는 `Find`에 `GetPrev` 대한 호출을 사용하여 초기 위치를 설정하는 경우 `GetTailPosition` 역반복 루프에서 사용할 수 있습니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

검색된 요소가 목록의 첫 번째 요소인 경우 *rPosition의* 새 값이 NULL로 설정됩니다.

## <a name="ctypedptrlistgettail"></a><a name="gettail"></a>CTypedPtrList::GetTail

이 목록의 머리 요소를 나타내는 포인터를 가져옵니다.

```
TYPE& GetTail();
TYPE GetTail() const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
목록에 저장된 요소의 유형을 지정하는 템플릿 매개 변수입니다.

### <a name="return-value"></a>Return Value

에 대한 포인터를 `const CTypedPtrList`통해 목록에 액세스하는 `GetTail` 경우 템플릿 매개 변수 *TYPE에서*지정한 형식의 포인터를 반환합니다. 이렇게 하면 할당 문의 오른쪽에만 함수를 사용할 수 있으므로 목록이 수정되지 않도록 보호할 수 있습니다.

에 대한 포인터를 통해 목록이 직접 `CTypedPtrList`액세스되는 `GetTail` 경우 는 템플릿 매개 변수 *TYPE에*의해 지정된 형식의 포인터에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 함수를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

을 호출하기 `GetTail`전에 목록이 비어 있지 않은지 확인해야 합니다. 목록이 비어 있으면 Microsoft 재단 클래스 라이브러리의 디버그 버전이 어설션됩니다. [IsEmpty를](../../mfc/reference/coblist-class.md#isempty) 사용하여 목록에 요소가 포함되어 있는지 확인합니다.

## <a name="ctypedptrlistremovehead"></a><a name="removehead"></a>CTypedPtrList::제거헤드

목록의 헤드에서 요소를 제거하고 반환합니다.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
목록에 저장된 요소의 유형을 지정하는 템플릿 매개 변수입니다.

### <a name="return-value"></a>Return Value

이전에 목록의 머리에 있는 포인터입니다. 이 포인터는 템플릿 매개 변수 *TYPE에*의해 지정된 형식입니다.

### <a name="remarks"></a>설명

을 호출하기 `RemoveHead`전에 목록이 비어 있지 않은지 확인해야 합니다. 목록이 비어 있으면 Microsoft 재단 클래스 라이브러리의 디버그 버전이 어설션됩니다. [IsEmpty를](../../mfc/reference/coblist-class.md#isempty) 사용하여 목록에 요소가 포함되어 있는지 확인합니다.

## <a name="ctypedptrlistremovetail"></a><a name="removetail"></a>CTypedPtrList::제거테일

목록의 꼬리에서 요소를 제거하고 반환합니다.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
목록에 저장된 요소의 유형을 지정하는 템플릿 매개 변수입니다.

### <a name="return-value"></a>Return Value

목록의 꼬리에 있는 포인터입니다. 이 포인터는 템플릿 매개 변수 *TYPE에*의해 지정된 형식입니다.

### <a name="remarks"></a>설명

을 호출하기 `RemoveTail`전에 목록이 비어 있지 않은지 확인해야 합니다. 목록이 비어 있으면 Microsoft 재단 클래스 라이브러리의 디버그 버전이 어설션됩니다. [IsEmpty를](../../mfc/reference/coblist-class.md#isempty) 사용하여 목록에 요소가 포함되어 있는지 확인합니다.

## <a name="ctypedptrlistsetat"></a><a name="setat"></a>CTypedPtrList::SetAt

이 멤버 `BASE_CLASS`함수는 **::SetAt 를 호출합니다.**

```cpp
void SetAt(POSITION pos, TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
설정할 요소의 위치입니다.

*유형*<br/>
기본 클래스 목록에 저장된 요소의 유형입니다.

*new엘리먼트*<br/>
목록에 쓸 개체 포인터입니다.

### <a name="remarks"></a>설명

위치 형식의 변수는 목록의 키입니다. 인덱스와 같지 않으며 POSITION 값으로 직접 작동할 수 없습니다. `SetAt`은 목록의 지정된 위치에 개체 포인터를 씁니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

더 자세한 설명은 [CObList::SetAt](../../mfc/reference/coblist-class.md#setat)를 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CPtrList 클래스](../../mfc/reference/cptrlist-class.md)<br/>
[CObList 클래스](../../mfc/reference/coblist-class.md)
