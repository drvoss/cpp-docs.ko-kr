---
title: CObList 클래스
ms.date: 11/04/2016
f1_keywords:
- CObList
- AFXCOLL/CObList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
helpviewer_keywords:
- CObList [MFC], CObList
- CObList [MFC], AddHead
- CObList [MFC], AddTail
- CObList [MFC], Find
- CObList [MFC], FindIndex
- CObList [MFC], GetAt
- CObList [MFC], GetCount
- CObList [MFC], GetHead
- CObList [MFC], GetHeadPosition
- CObList [MFC], GetNext
- CObList [MFC], GetPrev
- CObList [MFC], GetSize
- CObList [MFC], GetTail
- CObList [MFC], GetTailPosition
- CObList [MFC], InsertAfter
- CObList [MFC], InsertBefore
- CObList [MFC], IsEmpty
- CObList [MFC], RemoveAll
- CObList [MFC], RemoveAt
- CObList [MFC], RemoveHead
- CObList [MFC], RemoveTail
- CObList [MFC], SetAt
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
ms.openlocfilehash: f24965357e0b71f28ba39b82d045600e7e1a44e2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749690"
---
# <a name="coblist-class"></a>CObList 클래스

f는 순차적으로 `CObject` 또는 포인터 값으로 액세스할 수 있는 고유하지 않은 포인터의 정렬된 목록을 지원합니다.

## <a name="syntax"></a>구문

```
class CObList : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CObList:::COblist](#coblist)|포인터에 대한 `CObject` 빈 목록을 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CObList::추가 헤드](#addhead)|목록의 헤드에 요소(또는 다른 목록의 모든 요소)를 추가합니다(새 헤드를 만듭니다).|
|[CObList::꼬리 추가](#addtail)|목록의 꼬리에 요소(또는 다른 목록의 모든 요소)를 추가합니다(새 꼬리를 만듭니다).|
|[CObList::찾기](#find)|포인터 값으로 지정된 요소의 위치를 가져옵니다.|
|[CObList::찾기 인덱스](#findindex)|0기반 인덱스로 지정된 요소의 위치를 가져옵니다.|
|[CObList::GetAt](#getat)|지정된 위치에 요소를 가져옵니다.|
|[CObList::GetCount](#getcount)|이 목록의 요소 수를 반환합니다.|
|[CObList::GetHead](#gethead)|목록의 머리 요소를 반환합니다(비일 수 없음).|
|[CObList::GetHeadposition](#getheadposition)|목록의 머리 요소의 위치를 반환합니다.|
|[CObList::GetNext](#getnext)|반복에 대한 다음 요소를 가져옵니다.|
|[CObList::GetPrev](#getprev)|반복에 대한 이전 요소를 가져옵니다.|
|[CObList::GetSize](#getsize)|이 목록의 요소 수를 반환합니다.|
|[CObList::GetTail](#gettail)|목록의 tail 요소를 반환합니다(비일 수 없음).|
|[CObList::GetTailPosition](#gettailposition)|목록의 꼬리 요소의 위치를 반환합니다.|
|[CObList::삽입 후](#insertafter)|지정된 위치 후에 새 요소를 삽입합니다.|
|[CObList::삽입 하기 전에](#insertbefore)|지정된 위치 앞에 새 요소를 삽입합니다.|
|[CObList::비어 있음](#isempty)|빈 목록 조건(요소 없음)에 대한 테스트입니다.|
|[CObList::제거모두](#removeall)|이 목록에서 모든 요소를 제거합니다.|
|[CObList::제거](#removeat)|위치에 의해 지정된 이 목록에서 요소를 제거합니다.|
|[CObList::제거헤드](#removehead)|목록의 머리에서 요소를 제거합니다.|
|[CObList::제거테일](#removetail)|목록의 꼬리에서 요소를 제거합니다.|
|[CObList::SetAt](#setat)|지정된 위치에 요소를 설정합니다.|

## <a name="remarks"></a>설명

`CObList`목록은 이중으로 연결된 목록처럼 행동합니다.

위치 형식의 변수는 목록의 키입니다. POSITION 변수를 모두 거시적 으로 사용하여 목록을 순차적으로 탐색하고 장소를 보관하는 책갈피로 사용할 수 있습니다. 그러나 위치는 인덱스와 동일하지 않습니다.

요소 삽입은 목록 헤드, 꼬리 및 알려진 위치에서 매우 빠릅니다. 값 또는 인덱스별로 요소를 조회하려면 순차적인 검색이 필요합니다. 목록이 길면 이 검색속도가 느려질 수 있습니다.

`CObList`IMPLEMENT_SERIAL 매크로를 통합하여 해당 요소의 직렬화 및 덤프를 지원합니다. 포인터 목록이 `CObject` 오버로드된 삽입 연산자 또는 `Serialize` 멤버 함수를 사용하여 아카이브에 저장되면 `CObject` 각 요소가 차례로 직렬화됩니다.

목록에서 개별 `CObject` 요소의 덤프가 필요한 경우 덤프 컨텍스트의 깊이를 1 이상으로 설정해야 합니다.

개체가 `CObList` 삭제되거나 해당 요소가 제거될 때 `CObject` 참조하는 개체가 아닌 포인터만 제거됩니다.

에서 사용자 고유의 `CObList`클래스를 파생할 수 있습니다. `CObject`에서 파생 된 개체에 대 한 포인터를 유지 하도록 설계 된 새 목록 클래스 새 데이터 멤버 및 새 멤버 함수를 추가 합니다. 결과 목록은 포인터를 `CObject` 삽입할 수 있으므로 엄격하게 안전한 형식이 아닙니다.

> [!NOTE]
> 목록을 직렬화하려면 파생 클래스의 구현에 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로를 사용해야 합니다.

사용에 `CObList`대한 자세한 내용은 [컬렉션](../../mfc/collections.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>요구 사항

**헤더:** afxcoll.h

## <a name="coblistaddhead"></a><a name="addhead"></a>CObList::추가 헤드

이 목록의 헤드에 새 요소 또는 요소 목록을 추가합니다.

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>매개 변수

*new엘리먼트*<br/>
이 `CObject` 목록에 추가할 포인터입니다.

*pNewList*<br/>
다른 `CObList` 목록에 대한 포인터입니다. *pNewList의* 요소가 이 목록에 추가됩니다.

### <a name="return-value"></a>Return Value

첫 번째 버전은 새로 삽입된 요소의 POSITION 값을 반환합니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::AddHead`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 애드헤드(무효);** <strong>\*</strong> `newElement` **);**<br /><br /> **무효 애드헤드 (CPtrList);** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 추가 헤드 (const CString** `newElement` **&);**<br /><br /> **위치 애드헤드 (LPCTSTR);** `newElement` **);**<br /><br /> **보이드 애드헤드(CStringList);** <strong>\*</strong> `pNewList` **);**|

### <a name="remarks"></a>설명

작업이 시작되기 전에 목록이 비어 있을 수 있습니다.

### <a name="example"></a>예제

  클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

## <a name="coblistaddtail"></a><a name="addtail"></a>CObList::꼬리 추가

이 목록의 꼬리에 새 요소 또는 요소 목록을 추가합니다.

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>매개 변수

*new엘리먼트*<br/>
이 `CObject` 목록에 추가할 포인터입니다.

*pNewList*<br/>
다른 `CObList` 목록에 대한 포인터입니다. *pNewList의* 요소가 이 목록에 추가됩니다.

### <a name="return-value"></a>Return Value

첫 번째 버전은 새로 삽입된 요소의 POSITION 값을 반환합니다.

### <a name="remarks"></a>설명

작업이 시작되기 전에 목록이 비어 있을 수 있습니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::AddTail`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 추가 테일 (무효);** <strong>\*</strong> `newElement` **);**<br /><br /> **무효 애드테일 (CPtrList);** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 애드테일(const CString** `newElement` **&);**<br /><br /> **위치 애드테일 (LPCTSTR);** `newElement` **);**<br /><br /> **보이드 애드테일(CStringList);** <strong>\*</strong> `pNewList` **);**|

### <a name="example"></a>예제

  클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

## <a name="coblistcoblist"></a><a name="coblist"></a>CObList:::COblist

빈 `CObject` 포인터 목록을 생성합니다.

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
목록을 확장하기 위한 메모리 할당 세분성입니다.

### <a name="remarks"></a>설명

목록이 커지면 *nBlockSize* 항목 단위로 메모리가 할당됩니다. 메모리 할당에 실패하면 `CMemoryException` a가 throw됩니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::CObList`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>예제

  다음은 모든 컬렉션 `CObject`예제에 사용된 `CAge` -derived 클래스의 목록입니다.

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

다음은 생성자 `CObList` 사용의 예입니다.

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

## <a name="coblistfind"></a><a name="find"></a>CObList::찾기

목록을 순차적으로 검색하여 지정된 `CObject` `CObject` 포인터와 일치하는 첫 번째 포인터를 찾습니다.

```
POSITION Find(
    CObject* searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>매개 변수

*검색값*<br/>
이 목록에서 찾을 개체 포인터입니다.

*시작 후*<br/>
검색의 시작 위치입니다.

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 POSITION 값입니다. 개체를 찾을 수 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

포인터 값은 개체의 내용이 아니라 비교됩니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::Find`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 찾기(void,** <strong>\*</strong> `searchValue` **위치** `startAfter` **= NULL) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 찾기(LPCTSTR,** `searchValue` **위치** `startAfter` **= NULL) const;**|

### <a name="example"></a>예제

클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

## <a name="coblistfindindex"></a><a name="findindex"></a>CObList::찾기 인덱스

*nIndex* 값을 인덱스로 사용하여 목록에

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
찾을 목록 요소의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 POSITION 값입니다. *nIndex가* 너무 큰 경우 NULL입니다. *(nIndex가* 음수인 경우 프레임워크는 어설션을 생성합니다.)

### <a name="remarks"></a>설명

목록의 머리에서 순차적 스캔을 시작하여 *nth*요소에서 중지합니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::FindIndex`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 찾기인덱스(INT_PTR)** `nIndex` **) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 찾기인덱스(INT_PTR)** `nIndex` **) const;**|

### <a name="example"></a>예제

클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

## <a name="coblistgetat"></a><a name="getat"></a>CObList::GetAt

위치 형식의 변수는 목록의 키입니다.

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>매개 변수

*위치*<br/>
이전 `GetHeadPosition` 또는 `Find` 멤버 함수 호출에서 반환된 POSITION 값입니다.

### <a name="return-value"></a>Return Value

[GetHead에](#gethead)대한 반환 값 설명을 참조하십시오.

### <a name="remarks"></a>설명

인덱스와 같지 않으며 POSITION 값으로 직접 작동할 수 없습니다. `GetAt`은 지정된 `CObject` 위치와 연결된 포인터를 검색합니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::GetAt`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const\* void& GetAt (위치** *position* **위치) const;**<br /><br /> **무효\*& GetAt (위치** *위치);* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetAt (위치** *position* **위치) const;**<br /><br /> **스트링& GetAt (위치** *위치);* **);**|

### <a name="example"></a>예제

  [FindIndex](#findindex)에 대한 예제를 참조하십시오.

## <a name="coblistgetcount"></a><a name="getcount"></a>CObList::GetCount

이 목록의 요소 수를 가져옵니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Return Value

요소 수를 포함하는 정수 값입니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::GetCount`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR 겟카운트()**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR 겟카운트()**|

### <a name="example"></a>예제

클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

## <a name="coblistgethead"></a><a name="gethead"></a>CObList::GetHead

이 `CObject` 목록의 머리 요소를 나타내는 포인터를 가져옵니다.

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>Return Value

에 대한 포인터를 `const CObList`통해 목록에 액세스하는 `GetHead` 경우 `CObject` 포인터를 반환합니다. 이렇게 하면 할당 문의 오른쪽에만 함수를 사용할 수 있으므로 목록이 수정되지 않도록 보호할 수 있습니다.

에 대한 포인터를 `CObList`통해 목록에 직접 액세스하는 `GetHead` 경우 포인터에 `CObject` 대한 참조를 반환합니다. 이렇게 하면 할당 문의 양쪽에서 함수를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

을 호출하기 `GetHead`전에 목록이 비어 있지 않은지 확인해야 합니다. 목록이 비어 있으면 Microsoft 재단 클래스 라이브러리의 디버그 버전이 어설션됩니다. [IsEmpty를](#isempty) 사용하여 목록에 요소가 포함되어 있는지 확인합니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::GetHead`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const\* void& GetHead () const; 무효\*& 겟헤드();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetHead () const; 스트링& 겟헤드 ();**|

### <a name="example"></a>예제

클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

다음 예제에서는 할당 문의 `GetHead` 왼쪽에 사용 하 여 보여 줍니다.

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

## <a name="coblistgetheadposition"></a><a name="getheadposition"></a>CObList::GetHeadposition

이 목록의 헤드 요소의 위치를 가져옵니다.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 POSITION 값입니다. 목록이 비어 있는 경우 NULL입니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::GetHeadPosition`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 GetHeadPosition () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 GetHeadPosition () const;**|

### <a name="example"></a>예제

클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

## <a name="coblistgetnext"></a><a name="getnext"></a>CObList::GetNext

*rPosition로* `POSITION` 식별된 목록 요소를 *rPosition* 가져옵니다.

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*rPosition*<br/>
이전 `GetNext`에서 반환 되는 POSITION 값에 대 한 참조입니다. `GetHeadPosition`

### <a name="return-value"></a>Return Value

[GetHead에](#gethead)대한 반환 값 설명을 참조하십시오.

### <a name="remarks"></a>설명

또는 `Find`에 `GetNext` 대한 호출을 사용하여 초기 위치를 설정하는 경우 `GetHeadPosition` 정방향 반복 루프에서 사용할 수 있습니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

검색된 요소가 목록의 마지막 요소인 경우 *rPosition의* 새 값이 NULL로 설정됩니다.

반복 중에 요소를 제거할 수 있습니다. [RemoveAt](#removeat)에 대한 예제를 참조하십시오.

> [!NOTE]
> MFC 8.0을 현재 이 메서드의 const `const CObject*` 버전대신 `const CObject*&`반환하도록 변경되었습니다.  이 변경은 컴파일러가 C++ 표준을 준수하도록 하기 위해 만들어졌습니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::GetNext`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>예제

  클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

## <a name="coblistgetprev"></a><a name="getprev"></a>CObList::GetPrev

*rPosition로*식별된 목록 요소를 *rPosition* 가져옵니다.

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*rPosition*<br/>
이전 `GetPrev` 또는 다른 멤버 함수 호출에서 반환된 POSITION 값에 대한 참조입니다.

### <a name="return-value"></a>Return Value

[GetHead에](#gethead)대한 반환 값 설명을 참조하십시오.

### <a name="remarks"></a>설명

또는 `Find`에 `GetPrev` 대한 호출을 사용하여 초기 위치를 설정하는 경우 `GetTailPosition` 역반복 루프에서 사용할 수 있습니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

검색된 요소가 목록의 첫 번째 요소인 경우 *rPosition의* 새 값이 NULL로 설정됩니다.

> [!NOTE]
> MFC 8.0을 현재 이 메서드의 const `const CObject*` 버전대신 `const CObject*&`반환하도록 변경되었습니다.  이 변경은 컴파일러가 C++ 표준을 준수하도록 하기 위해 만들어졌습니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::GetPrev`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>예제

  클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
a CAge at $421C 21
a CAge at $421C 40
```

## <a name="coblistgetsize"></a><a name="getsize"></a>CObList::GetSize

목록 요소 수를 반환합니다.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Return Value

목록에 있는 항목의 수입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 목록의 요소 수를 검색합니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::GetSize`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetSize () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>예제

클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

## <a name="coblistgettail"></a><a name="gettail"></a>CObList::GetTail

이 `CObject` 목록의 tail 요소를 나타내는 포인터를 가져옵니다.

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>Return Value

[GetHead에](#gethead)대한 반환 값 설명을 참조하십시오.

### <a name="remarks"></a>설명

을 호출하기 `GetTail`전에 목록이 비어 있지 않은지 확인해야 합니다. 목록이 비어 있으면 Microsoft 재단 클래스 라이브러리의 디버그 버전이 어설션됩니다. [IsEmpty를](#isempty) 사용하여 목록에 요소가 포함되어 있는지 확인합니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::GetTail`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const\* void& GetTail () const; 무효\*& 겟테일();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetTail () const; 스트링& 게테일 ();**|

### <a name="example"></a>예제

클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

## <a name="coblistgettailposition"></a><a name="gettailposition"></a>CObList::GetTailPosition

이 목록의 꼬리 요소의 위치를 가져옵니다. 목록이 비어 있는 경우 **NULL입니다.**

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 POSITION 값입니다. 목록이 비어 있는 경우 NULL입니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::GetTailPosition`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 GetTailPosition () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 GetTailPosition () const;**|

### <a name="example"></a>예제

클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

## <a name="coblistinsertafter"></a><a name="insertafter"></a>CObList::삽입 후

지정된 위치에 있는 요소 다음의 요소를 이 목록에 추가합니다.

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>매개 변수

*위치*<br/>
이전 `GetNext`에서 반환 된 `GetPrev`POSITION `Find` 값 또는 멤버 함수 호출입니다.

*new엘리먼트*<br/>
이 목록에 추가할 개체 포인터입니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::InsertAfter`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 삽입 후 (위치** *position* **위치, 무효);** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 삽입 후 (위치** *위치,* **const CString&);** `newElement` **);**<br /><br /> **위치 삽입 후 (위치** *위치,* **LPCTSTR);** `newElement` **);**|

### <a name="return-value"></a>Return Value

위치 매개 변수와 동일한 *위치* 값입니다.

### <a name="example"></a>예제

  클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

## <a name="coblistinsertbefore"></a><a name="insertbefore"></a>CObList::삽입 하기 전에

이 목록에서 지정된 위치의 요소 앞에 요소를 추가합니다.

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>매개 변수

*위치*<br/>
이전 `GetNext`에서 반환 된 `GetPrev`POSITION `Find` 값 또는 멤버 함수 호출입니다.

*new엘리먼트*<br/>
이 목록에 추가할 개체 포인터입니다.

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 POSITION 값입니다. 목록이 비어 있는 경우 NULL입니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::InsertBefore`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 삽입 전 (위치** *위치,* **보이드);** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 삽입전(위치** *position* **위치, 콘스트 스트링&);** `newElement` **);**<br /><br /> **위치 삽입 전 (위치** *위치,* **LPCTSTR);** `newElement` **);**|

### <a name="example"></a>예제

  클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

## <a name="coblistisempty"></a><a name="isempty"></a>CObList::비어 있음

이 목록에 요소가 포함되어 있지 않은지 여부를 나타냅니다.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Return Value

이 목록이 비어 있으면 0이 아닙니다. 그렇지 않으면 0.

다음 표에서는 와 유사한 다른 멤버 `CObList::IsEmpty`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL IsEmpty() const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL IsEmpty() const;**|

### <a name="example"></a>예제

  [RemoveAll에](#removeall)대한 예제를 참조하십시오.

## <a name="coblistremoveall"></a><a name="removeall"></a>CObList::제거모두

이 목록에서 모든 요소를 제거하고 연결된 `CObList` 메모리를 해제합니다.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>설명

목록이 이미 비어 있으면 오류가 생성되지 않습니다.

에서 `CObList`요소를 제거하면 목록에서 개체 포인터가 제거됩니다. 개체 를 스스로 삭제하는 것은 사용자의 책임입니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::RemoveAll`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**무효 제거모든 ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**무효 제거모든 ();**|

### <a name="example"></a>예제

클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

## <a name="coblistremoveat"></a><a name="removeat"></a>CObList::제거

이 목록에서 지정된 요소를 제거합니다.

```cpp
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>매개 변수

*위치*<br/>
목록에서 제거할 요소의 위치입니다.

### <a name="remarks"></a>설명

에서 `CObList`요소를 제거하면 목록에서 개체 포인터가 제거됩니다. 개체 를 스스로 삭제하는 것은 사용자의 책임입니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::RemoveAt`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**무효 제거 (위치);** *position* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**무효 제거 (위치);** *position* **);**|

### <a name="example"></a>예제

  목록 반복 중에 요소를 제거할 때는 주의해야 합니다. 다음 예제에서는 GetNext 에 대 한 유효한 **위치** 값을 보장 하는 제거 기술을 보여 [주면](#getnext)됩니다.

클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

이 프로그램의 결과는 다음과 같습니다.

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

## <a name="coblistremovehead"></a><a name="removehead"></a>CObList::제거헤드

목록의 머리에서 요소를 제거하고 포인터를 반환합니다.

```
CObject* RemoveHead();
```

### <a name="return-value"></a>Return Value

이전에 `CObject` 목록의 머리에 있는 포인터입니다.

### <a name="remarks"></a>설명

을 호출하기 `RemoveHead`전에 목록이 비어 있지 않은지 확인해야 합니다. 목록이 비어 있으면 Microsoft 재단 클래스 라이브러리의 디버그 버전이 어설션됩니다. [IsEmpty를](#isempty) 사용하여 목록에 요소가 포함되어 있는지 확인합니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::RemoveHead`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**무효\* 제거헤드 ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**스트링 제거헤드 ();**|

### <a name="example"></a>예제

클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

## <a name="coblistremovetail"></a><a name="removetail"></a>CObList::제거테일

목록의 꼬리에서 요소를 제거하고 포인터를 반환합니다.

```
CObject* RemoveTail();
```

### <a name="return-value"></a>Return Value

목록의 꼬리에 있는 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

을 호출하기 `RemoveTail`전에 목록이 비어 있지 않은지 확인해야 합니다. 목록이 비어 있으면 Microsoft 재단 클래스 라이브러리의 디버그 버전이 어설션됩니다. [IsEmpty를](#isempty) 사용하여 목록에 요소가 포함되어 있는지 확인합니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::RemoveTail`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**무효\* 제거테일 ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**스트링 제거테일 ();**|

### <a name="example"></a>예제

클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

## <a name="coblistsetat"></a><a name="setat"></a>CObList::SetAt

지정된 위치에 요소를 설정합니다.

```cpp
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
설정할 요소의 위치입니다.

*new엘리먼트*<br/>
목록에 `CObject` 쓸 포인터입니다.

### <a name="remarks"></a>설명

위치 형식의 변수는 목록의 키입니다. 인덱스와 같지 않으며 POSITION 값으로 직접 작동할 수 없습니다. `SetAt`은 `CObject` 목록의 지정된 위치에 포인터를 씁니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

다음 표에서는 와 유사한 다른 멤버 `CObList::SetAt`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**[위치]** `pos` **스트링&);** `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**무효 SetAt (위치** `pos` **, LPCTSTR);** `newElement` **);**|

### <a name="example"></a>예제

  클래스 목록은 [CObList::CObList를](#coblist) `CAge` 참조하십시오.

[!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
SetAt example: A CObList with 2 elements
a CAge at $4D98 40
a CAge at $4DB8 65
```

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CStringList 클래스](../../mfc/reference/cstringlist-class.md)<br/>
[CPtrList 클래스](../../mfc/reference/cptrlist-class.md)
