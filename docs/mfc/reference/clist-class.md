---
title: CList 클래스
ms.date: 11/04/2016
f1_keywords:
- CList
- AFXTEMPL/CList
- AFXTEMPL/CList::CList
- AFXTEMPL/CList::AddHead
- AFXTEMPL/CList::AddTail
- AFXTEMPL/CList::Find
- AFXTEMPL/CList::FindIndex
- AFXTEMPL/CList::GetAt
- AFXTEMPL/CList::GetCount
- AFXTEMPL/CList::GetHead
- AFXTEMPL/CList::GetHeadPosition
- AFXTEMPL/CList::GetNext
- AFXTEMPL/CList::GetPrev
- AFXTEMPL/CList::GetSize
- AFXTEMPL/CList::GetTail
- AFXTEMPL/CList::GetTailPosition
- AFXTEMPL/CList::InsertAfter
- AFXTEMPL/CList::InsertBefore
- AFXTEMPL/CList::IsEmpty
- AFXTEMPL/CList::RemoveAll
- AFXTEMPL/CList::RemoveAt
- AFXTEMPL/CList::RemoveHead
- AFXTEMPL/CList::RemoveTail
- AFXTEMPL/CList::SetAt
helpviewer_keywords:
- CList [MFC], CList
- CList [MFC], AddHead
- CList [MFC], AddTail
- CList [MFC], Find
- CList [MFC], FindIndex
- CList [MFC], GetAt
- CList [MFC], GetCount
- CList [MFC], GetHead
- CList [MFC], GetHeadPosition
- CList [MFC], GetNext
- CList [MFC], GetPrev
- CList [MFC], GetSize
- CList [MFC], GetTail
- CList [MFC], GetTailPosition
- CList [MFC], InsertAfter
- CList [MFC], InsertBefore
- CList [MFC], IsEmpty
- CList [MFC], RemoveAll
- CList [MFC], RemoveAt
- CList [MFC], RemoveHead
- CList [MFC], RemoveTail
- CList [MFC], SetAt
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
ms.openlocfilehash: adc065687f0c2c40b7e66326ff9d1e6210a6962c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754137"
---
# <a name="clist-class"></a>CList 클래스

순차적으로 또는 값별로 액세스할 수 있고 고유하지 않은 개체의 순서가 지정된 목록을 지원합니다.

## <a name="syntax"></a>구문

```
template<class TYPE, class ARG_TYPE = const TYPE&>
class CList : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CList::CList](#clist)|빈 정렬된 목록을 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CList::추가 헤드](#addhead)|목록의 헤드에 요소(또는 다른 목록의 모든 요소)를 추가합니다(새 헤드를 만듭니다).|
|[CList::추가 꼬리](#addtail)|목록의 꼬리에 요소(또는 다른 목록의 모든 요소)를 추가합니다(새 꼬리를 만듭니다).|
|[CList::찾기](#find)|포인터 값으로 지정된 요소의 위치를 가져옵니다.|
|[CList::찾기 인덱스](#findindex)|0기반 인덱스로 지정된 요소의 위치를 가져옵니다.|
|[CList::GetAt](#getat)|지정된 위치에 요소를 가져옵니다.|
|[CList::GetCount](#getcount)|이 목록의 요소 수를 반환합니다.|
|[CList::GetHead](#gethead)|목록의 머리 요소를 반환합니다(비일 수 없음).|
|[CList::GetHeadposition](#getheadposition)|목록의 머리 요소의 위치를 반환합니다.|
|[CList::GetNext](#getnext)|반복에 대한 다음 요소를 가져옵니다.|
|[CList::GetPrev](#getprev)|반복에 대한 이전 요소를 가져옵니다.|
|[CList::GetSize](#getsize)|이 목록의 요소 수를 반환합니다.|
|[CList::GetTail](#gettail)|목록의 tail 요소를 반환합니다(비일 수 없음).|
|[CList::GetTail포지션](#gettailposition)|목록의 꼬리 요소의 위치를 반환합니다.|
|[CList::삽입 후](#insertafter)|지정된 위치 후에 새 요소를 삽입합니다.|
|[CList::InsertBefore](#insertbefore)|지정된 위치 앞에 새 요소를 삽입합니다.|
|[CList::비어 있음](#isempty)|빈 목록 조건(요소 없음)에 대한 테스트입니다.|
|[CList::모두 제거](#removeall)|이 목록에서 모든 요소를 제거합니다.|
|[CList::RemoveAt](#removeat)|위치에 의해 지정된 이 목록에서 요소를 제거합니다.|
|[CList::제거헤드](#removehead)|목록의 머리에서 요소를 제거합니다.|
|[CList::제거테일](#removetail)|목록의 꼬리에서 요소를 제거합니다.|
|[CList::SetAt](#setat)|지정된 위치에 요소를 설정합니다.|

#### <a name="parameters"></a>매개 변수

*유형*<br/>
목록에 저장된 개체의 유형입니다.

*ARG_TYPE*<br/>
목록에 저장된 개체를 참조하는 데 사용되는 형식을 입력합니다. 참조가 될 수 있습니다.

## <a name="remarks"></a>설명

`CList`목록은 이중으로 연결된 목록처럼 행동합니다.

위치 형식의 변수는 목록의 키입니다. POSITION 변수를 이터레이터로 사용하여 목록을 순차적으로 통과하고 장소를 보관하는 책갈피로 사용할 수 있습니다. 그러나 위치는 인덱스와 동일하지 않습니다.

요소 삽입은 목록 헤드, 꼬리 및 알려진 위치에서 매우 빠릅니다. 값 또는 인덱스별로 요소를 조회하려면 순차적인 검색이 필요합니다. 목록이 길면 이 검색속도가 느려질 수 있습니다.

목록에서 개별 요소의 덤프가 필요한 경우 덤프 컨텍스트의 깊이를 1 이상으로 설정해야 합니다.

이 클래스의 특정 멤버 함수는 클래스의 대부분의 용도에 맞게 `CList` 사용자 지정해야 하는 전역 도우미 함수를 호출합니다. "매크로 및 전역" 섹션에서 [컬렉션 클래스 도우미를](../../mfc/reference/collection-class-helpers.md) 참조하십시오.

사용에 `CList`대한 자세한 내용은 [컬렉션](../../mfc/collections.md)문서를 참조하십시오.

## <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CList`

## <a name="requirements"></a>요구 사항

**헤더:** afxtempl.h

## <a name="clistaddhead"></a><a name="addhead"></a>CList::추가 헤드

이 목록의 헤드에 새 요소 또는 요소 목록을 추가합니다.

```
POSITION AddHead(ARG_TYPE newElement);
void AddHead(CList* pNewList);
```

### <a name="parameters"></a>매개 변수

*ARG_TYPE*<br/>
목록 요소의 형식을 지정하는 템플릿 매개 변수입니다(참조일 수 있음).

*new엘리먼트*<br/>
새 요소입니다.

*pNewList*<br/>
다른 `CList` 목록에 대한 포인터입니다. *pNewList의* 요소가 이 목록에 추가됩니다.

### <a name="return-value"></a>Return Value

첫 번째 버전은 새로 삽입된 요소의 POSITION 값을 반환합니다.

### <a name="remarks"></a>설명

작업이 시작되기 전에 목록이 비어 있을 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]

## <a name="clistaddtail"></a><a name="addtail"></a>CList::추가 꼬리

이 목록의 꼬리에 새 요소 또는 요소 목록을 추가합니다.

```
POSITION AddTail(ARG_TYPE newElement);
void AddTail(CList* pNewList);
```

### <a name="parameters"></a>매개 변수

*ARG_TYPE*<br/>
목록 요소의 형식을 지정하는 템플릿 매개 변수입니다(참조일 수 있음).

*new엘리먼트*<br/>
이 목록에 추가할 요소입니다.

*pNewList*<br/>
다른 `CList` 목록에 대한 포인터입니다. *pNewList의* 요소가 이 목록에 추가됩니다.

### <a name="return-value"></a>Return Value

첫 번째 버전은 새로 삽입된 요소의 POSITION 값을 반환합니다.

### <a name="remarks"></a>설명

작업이 시작되기 전에 목록이 비어 있을 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#37](../../mfc/codesnippet/cpp/clist-class_3.cpp)]

## <a name="clistclist"></a><a name="clist"></a>CList::CList

빈 정렬된 목록을 생성합니다.

```
CList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
목록을 확장하기 위한 메모리 할당 세분성입니다.

### <a name="remarks"></a>설명

목록이 커지면 *nBlockSize* 항목 단위로 메모리가 할당됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]

## <a name="clistfind"></a><a name="find"></a>CList::찾기

목록을 순차적으로 검색하여 지정된 *searchValue*와 일치하는 첫 번째 요소를 찾습니다.

```
POSITION Find(
    ARG_TYPE searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>매개 변수

*ARG_TYPE*<br/>
목록 요소의 형식을 지정하는 템플릿 매개 변수입니다(참조일 수 있음).

*검색값*<br/>
목록에서 찾을 값입니다.

*시작 후*<br/>
검색의 시작 위치입니다. 값을 지정하지 않으면 head 요소로 검색이 시작됩니다.

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 POSITION 값입니다. 개체를 찾을 수 없는 경우 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#39](../../mfc/codesnippet/cpp/clist-class_5.cpp)]

## <a name="clistfindindex"></a><a name="findindex"></a>CList::찾기 인덱스

*nIndex* 값을 인덱스로 사용하여 목록에

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
찾을 목록 요소의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 POSITION 값입니다. null *nIndex가* 음수이거나 너무 큰 경우.

### <a name="remarks"></a>설명

목록의 머리에서 순차적 스캔을 시작하여 *nth*요소에서 중지합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]

## <a name="clistgetat"></a><a name="getat"></a>CList::GetAt

지정된 위치에서 목록 요소를 가져옵니다.

```
TYPE& GetAt(POSITION position);
const TYPE& GetAt(POSITION position) const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
목록의 개체 유형을 지정하는 템플릿 매개 변수입니다.

*위치*<br/>
얻을 요소 목록의 위치입니다.

### <a name="return-value"></a>Return Value

에 대한 `GetHead`반환 값 설명을 참조하십시오.

### <a name="remarks"></a>설명

`GetAt`은 지정된 위치와 연결된 요소(또는 요소에 대한 참조)를 반환합니다. 인덱스와 같지 않으며 POSITION 값으로 직접 작동할 수 없습니다. 위치 형식의 변수는 목록의 키입니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

### <a name="example"></a>예제

  [CList::GetHeadPosition에](#getheadposition)대한 예제를 참조하십시오.

## <a name="clistgetcount"></a><a name="getcount"></a>CList::GetCount

이 목록의 요소 수를 가져옵니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Return Value

요소 수를 포함하는 정수 값입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하면 [CList:GetSize](#getsize) 메서드와 동일한 결과가 생성됩니다.

### <a name="example"></a>예제

  [CList::RemoveHead](#removehead)에 대한 예제를 참조하십시오.

## <a name="clistgethead"></a><a name="gethead"></a>CList::GetHead

이 목록의 헤드 요소(또는 헤드 요소에 대한 참조)를 가져옵니다.

```
const TYPE& GetHead() const;

TYPE& GetHead();
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
목록의 개체 유형을 지정하는 템플릿 매개 변수입니다.

### <a name="return-value"></a>Return Value

목록이 **const인**경우 `GetHead` 목록의 헤드에 있는 요소의 복사본을 반환합니다. 이렇게 하면 할당 문의 오른쪽에서만 함수를 사용할 수 있으며 목록이 수정되지 않도록 보호할 수 있습니다.

목록이 **const가**아닌 `GetHead` 경우 목록의 헤드에 있는 요소에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 함수를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

을 호출하기 `GetHead`전에 목록이 비어 있지 않은지 확인해야 합니다. 목록이 비어 있으면 Microsoft 재단 클래스 라이브러리의 디버그 버전이 어설션됩니다. [IsEmpty를](#isempty) 사용하여 목록에 요소가 포함되어 있는지 확인합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]

## <a name="clistgetheadposition"></a><a name="getheadposition"></a>CList::GetHeadposition

이 목록의 헤드 요소의 위치를 가져옵니다.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 POSITION 값입니다. 목록이 비어 있는 경우 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]

## <a name="clistgetnext"></a><a name="getnext"></a>CList::GetNext

*rPosition로*식별된 목록 요소를 *rPosition* 가져옵니다.

```
TYPE& GetNext(POSITION& rPosition);
const TYPE& GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
목록의 요소 유형을 지정하는 템플릿 매개 변수입니다.

*rPosition*<br/>
이전, `GetNext` [GetHeadPosition](#getheadposition)또는 기타 멤버 함수 호출에서 반환된 POSITION 값에 대한 참조입니다.

### <a name="return-value"></a>Return Value

목록이 **const인**경우 `GetNext` 목록 요소의 복사본을 반환합니다. 이렇게 하면 할당 문의 오른쪽에서만 함수를 사용할 수 있으며 목록이 수정되지 않도록 보호할 수 있습니다.

목록이 **const가**아닌 `GetNext` 경우 목록의 요소에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 함수를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

또는 `Find`에 `GetNext` 대한 호출을 사용하여 초기 위치를 설정하는 경우 `GetHeadPosition` 정방향 반복 루프에서 사용할 수 있습니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

검색된 요소가 목록의 마지막 요소인 경우 새 `rPosition` 값은 NULL로 설정됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]

## <a name="clistgetprev"></a><a name="getprev"></a>CList::GetPrev

으로 식별된 `rPosition` `rPosition` 목록 요소를 가져옵니다.

```
TYPE& GetPrev(POSITION& rPosition);
const TYPE& GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
목록의 요소 유형을 지정하는 템플릿 매개 변수입니다.

*rPosition*<br/>
이전 `GetPrev` 또는 다른 멤버 함수 호출에서 반환된 POSITION 값에 대한 참조입니다.

### <a name="return-value"></a>Return Value

목록이 **const인**경우 `GetPrev` 목록의 헤드에 있는 요소의 복사본을 반환합니다. 이렇게 하면 할당 문의 오른쪽에서만 함수를 사용할 수 있으며 목록이 수정되지 않도록 보호할 수 있습니다.

목록이 **const가**아닌 `GetPrev` 경우 목록의 요소에 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 함수를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

또는 `Find`에 `GetPrev` 대한 호출을 사용하여 초기 위치를 설정하는 경우 `GetTailPosition` 역반복 루프에서 사용할 수 있습니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

검색된 요소가 목록의 첫 번째 요소인 경우 *rPosition의* 새 값이 NULL로 설정됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]

## <a name="clistgetsize"></a><a name="getsize"></a>CList::GetSize

목록 요소 수를 반환합니다.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Return Value

목록에 있는 항목의 수입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 목록의 요소 수를 검색합니다.  이 메서드를 호출하면 [CList:GetCount](#getcount) 메서드와 동일한 결과가 생성됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]

## <a name="clistgettail"></a><a name="gettail"></a>CList::GetTail

이 `CObject` 목록의 tail 요소를 나타내는 포인터를 가져옵니다.

```
TYPE& GetTail();
const TYPE& GetTail() const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
목록의 요소 유형을 지정하는 템플릿 매개 변수입니다.

### <a name="return-value"></a>Return Value

[GetHead에](../../mfc/reference/coblist-class.md#gethead)대한 반환 값 설명을 참조하십시오.

### <a name="remarks"></a>설명

을 호출하기 `GetTail`전에 목록이 비어 있지 않은지 확인해야 합니다. 목록이 비어 있으면 Microsoft 재단 클래스 라이브러리의 디버그 버전이 어설션됩니다. [IsEmpty를](../../mfc/reference/coblist-class.md#isempty) 사용하여 목록에 요소가 포함되어 있는지 확인합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]

## <a name="clistgettailposition"></a><a name="gettailposition"></a>CList::GetTail포지션

이 목록의 꼬리 요소의 위치를 가져옵니다. 목록이 비어 있는 경우 NULL입니다.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 POSITION 값입니다. 목록이 비어 있는 경우 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]

## <a name="clistinsertafter"></a><a name="insertafter"></a>CList::삽입 후

지정된 위치에 있는 요소 다음의 요소를 이 목록에 추가합니다.

```
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*위치*<br/>
이전 `GetNext`에서 반환 된 `GetPrev`POSITION `Find` 값 또는 멤버 함수 호출입니다.

*ARG_TYPE*<br/>
목록 요소의 형식을 지정하는 템플릿 매개 변수입니다.

*new엘리먼트*<br/>
이 목록에 추가할 요소입니다.

### <a name="return-value"></a>Return Value

반복 또는 목록 요소 검색에 사용할 수 있는 POSITION 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]

## <a name="clistinsertbefore"></a><a name="insertbefore"></a>CList::삽입 하기 전에

이 목록에서 지정된 위치의 요소 앞에 요소를 추가합니다.

```
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*위치*<br/>
이전 `GetNext`에서 반환 된 `GetPrev`POSITION `Find` 값 또는 멤버 함수 호출입니다.

*ARG_TYPE*<br/>
목록 요소의 형식을 지정하는 템플릿 매개 변수입니다(참조일 수 있음).

*new엘리먼트*<br/>
이 목록에 추가할 요소입니다.

### <a name="return-value"></a>Return Value

반복 또는 목록 요소 검색에 사용할 수 있는 POSITION 값입니다.

### <a name="remarks"></a>설명

*위치가* NULL이면 요소가 목록의 헤드에 삽입됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]

## <a name="clistisempty"></a><a name="isempty"></a>CList::비어 있음

이 목록에 요소가 포함되어 있지 않은지 여부를 나타냅니다.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Return Value

이 목록이 비어 있으면 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]

## <a name="clistremoveall"></a><a name="removeall"></a>CList::모두 제거

이 목록에서 모든 요소를 제거하고 연결된 메모리를 해제합니다.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>설명

목록이 이미 비어 있으면 오류가 생성되지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]

## <a name="clistremoveat"></a><a name="removeat"></a>CList::RemoveAt

이 목록에서 지정된 요소를 제거합니다.

```cpp
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>매개 변수

*위치*<br/>
목록에서 제거할 요소의 위치입니다.

### <a name="remarks"></a>설명

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]

## <a name="clistremovehead"></a><a name="removehead"></a>CList::제거헤드

목록의 머리에서 요소를 제거하고 포인터를 반환합니다.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
목록의 요소 유형을 지정하는 템플릿 매개 변수입니다.

### <a name="return-value"></a>Return Value

목록의 머리에 이전에 있는 요소입니다.

### <a name="remarks"></a>설명

을 호출하기 `RemoveHead`전에 목록이 비어 있지 않은지 확인해야 합니다. 목록이 비어 있으면 Microsoft 재단 클래스 라이브러리의 디버그 버전이 어설션됩니다. [IsEmpty를](#isempty) 사용하여 목록에 요소가 포함되어 있는지 확인합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]

## <a name="clistremovetail"></a><a name="removetail"></a>CList::제거테일

목록의 꼬리에서 요소를 제거하고 포인터를 반환합니다.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
목록의 요소 유형을 지정하는 템플릿 매개 변수입니다.

### <a name="return-value"></a>Return Value

목록의 꼬리에 있던 요소입니다.

### <a name="remarks"></a>설명

을 호출하기 `RemoveTail`전에 목록이 비어 있지 않은지 확인해야 합니다. 목록이 비어 있으면 Microsoft 재단 클래스 라이브러리의 디버그 버전이 어설션됩니다. [IsEmpty를](#isempty) 사용하여 목록에 요소가 포함되어 있는지 확인합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]

## <a name="clistsetat"></a><a name="setat"></a>CList::SetAt

위치 형식의 변수는 목록의 키입니다.

```cpp
void SetAt(POSITION pos, ARG_TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
설정할 요소의 위치입니다.

*ARG_TYPE*<br/>
목록 요소의 형식을 지정하는 템플릿 매개 변수입니다(참조일 수 있음).

*new엘리먼트*<br/>
목록에 추가할 요소입니다.

### <a name="remarks"></a>설명

인덱스와 같지 않으며 POSITION 값으로 직접 작동할 수 없습니다. `SetAt`요소를 목록의 지정된 위치에 씁니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CMap 클래스](../../mfc/reference/cmap-class.md)<br/>
[CArray 클래스](../../mfc/reference/carray-class.md)
