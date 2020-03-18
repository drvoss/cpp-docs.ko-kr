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
ms.openlocfilehash: 2fc3a3643c675394de555f1411030e278bcee775
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424034"
---
# <a name="coblist-class"></a>CObList 클래스

fSupports 순차적으로 또는 포인터 값으로 액세스할 수 있는 고유 하지 않은 `CObject` 포인터의 순서가 지정 된 목록을 지원 합니다.

## <a name="syntax"></a>구문

```
class CObList : public CObject
```

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CObList:: CObList](#coblist)|`CObject` 포인터에 대 한 빈 목록을 생성 합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CObList:: AddHead](#addhead)|요소 (또는 다른 목록의 모든 요소)를 목록의 헤드에 추가 합니다 (새 헤드를 만듭니다).|
|[CObList:: AddTail](#addtail)|요소 (또는 다른 목록의 모든 요소)를 목록 끝에 추가 합니다 (새 꼬리를 만듭니다).|
|[CObList:: Find](#find)|포인터 값으로 지정 된 요소의 위치를 가져옵니다.|
|[CObList:: FindIndex](#findindex)|0부터 시작 하는 인덱스로 지정 된 요소의 위치를 가져옵니다.|
|[CObList:: GetAt](#getat)|지정 된 위치에 있는 요소를 가져옵니다.|
|[CObList:: GetCount](#getcount)|이 목록에 있는 요소의 수를 반환 합니다.|
|[CObList:: GetHead](#gethead)|목록의 head 요소를 반환 합니다 (비워 둘 수 없음).|
|[CObList:: Geadposition](#getheadposition)|목록에서 head 요소의 위치를 반환 합니다.|
|[CObList:: GetNext](#getnext)|반복할 다음 요소를 가져옵니다.|
|[CObList:: GetPrev](#getprev)|반복을 위한 이전 요소를 가져옵니다.|
|[CObList:: GetSize](#getsize)|이 목록에 있는 요소의 수를 반환 합니다.|
|[CObList:: GetTail](#gettail)|목록의 tail 요소를 반환 합니다 (비워 둘 수 없음).|
|[CObList:: GetTailPosition](#gettailposition)|목록에서 tail 요소의 위치를 반환 합니다.|
|[CObList:: InsertAfter](#insertafter)|지정 된 위치 뒤에 새 요소를 삽입 합니다.|
|[CObList:: InsertBefore](#insertbefore)|지정 된 위치 앞에 새 요소를 삽입 합니다.|
|[CObList:: IsEmpty](#isempty)|빈 목록 조건 (요소 없음)을 테스트 합니다.|
|[CObList:: RemoveAll](#removeall)|이 목록에서 모든 요소를 제거 합니다.|
|[CObList:: RemoveAt](#removeat)|이 목록에서 위치로 지정 된 요소를 제거 합니다.|
|[CObList:: RemoveHead](#removehead)|목록에서 요소를 제거 합니다.|
|[CObList:: RemoveTail](#removetail)|목록의 끝에서 요소를 제거 합니다.|
|[CObList:: SetAt](#setat)|지정 된 위치에 요소를 설정 합니다.|

## <a name="remarks"></a>설명

`CObList` 목록은 이중 연결 목록 처럼 동작 합니다.

POSITION 형식의 변수는 목록의 키입니다. 위치 변수를 반복기로 사용 하 여 목록을 순차적으로 이동 하 고 책갈피를 사용 하 여 위치를 유지할 수 있습니다. 그러나 위치는 인덱스와 동일 하지 않습니다.

요소 삽입은 목록 헤드, 꼬리 및 알려진 위치에서 매우 빠릅니다. 순차 검색은 값 또는 인덱스를 기준으로 요소를 조회 하는 데 필요 합니다. 목록이 길면이 검색 속도가 느릴 수 있습니다.

`CObList`는 IMPLEMENT_SERIAL 매크로를 통합 하 여 요소의 serialization 및 덤프를 지원 합니다. 오버 로드 된 삽입 연산자나 `Serialize` 멤버 함수를 사용 하 여 `CObject` 포인터 목록이 보관 파일에 저장 된 경우 각 `CObject` 요소가 차례로 serialize 됩니다.

목록에서 개별 `CObject` 요소에 대 한 덤프가 필요한 경우 덤프 컨텍스트의 깊이를 1 이상으로 설정 해야 합니다.

`CObList` 개체가 삭제 되거나 해당 요소가 제거 되 면 참조 하는 개체가 아닌 `CObject` 포인터만 제거 됩니다.

`CObList`에서 고유한 클래스를 파생 시킬 수 있습니다. `CObject`에서 파생 된 개체에 대 한 포인터를 보유 하도록 디자인 된 새 목록 클래스는 새 데이터 멤버와 새 멤버 함수를 추가 합니다. 결과 목록은 모든 `CObject` 포인터를 삽입할 수 있으므로 엄격한 형식이 안전 하지 않습니다.

> [!NOTE]
>  목록을 serialize 하려는 경우 파생 클래스의 구현에서 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로를 사용 해야 합니다.

`CObList`사용에 대 한 자세한 내용은 [컬렉션](../../mfc/collections.md)문서를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>요구 사항

**헤더:** afxcoll.h

##  <a name="addhead"></a>CObList:: AddHead

이 목록의 맨 위에 새 요소나 요소 목록을 추가 합니다.

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>매개 변수

*newElement*<br/>
이 목록에 추가할 `CObject` 포인터입니다.

*pNewList*<br/>
다른 `CObList` 목록에 대 한 포인터입니다. *Pnewlist* 의 요소가이 목록에 추가 됩니다.

### <a name="return-value"></a>Return Value

첫 번째 버전은 새로 삽입 된 요소의 위치 값을 반환 합니다.

다음 표에서는 `CObList::AddHead`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION AddHead (void** <strong>\*</strong> `newElement` **);**<br /><br /> **Void AddHead (CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION AddHead (Const CString &** `newElement` **);**<br /><br /> **POSITION AddHead (LPCTSTR** `newElement` **);**<br /><br /> **Void AddHead (CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="remarks"></a>설명

작업을 수행 하기 전에 목록이 비어 있을 수 있습니다.

### <a name="example"></a>예제

  `CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

##  <a name="addtail"></a>CObList:: AddTail

이 목록의 꼬리에 새 요소 또는 요소 목록을 추가 합니다.

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>매개 변수

*newElement*<br/>
이 목록에 추가할 `CObject` 포인터입니다.

*pNewList*<br/>
다른 `CObList` 목록에 대 한 포인터입니다. *Pnewlist* 의 요소가이 목록에 추가 됩니다.

### <a name="return-value"></a>Return Value

첫 번째 버전은 새로 삽입 된 요소의 위치 값을 반환 합니다.

### <a name="remarks"></a>설명

작업을 수행 하기 전에 목록이 비어 있을 수 있습니다.

다음 표에서는 `CObList::AddTail`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION AddTail (void** <strong>\*</strong> `newElement` **);**<br /><br /> **Void AddTail (CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**AddTail (Const CString & `newElement`)을 배치** 합니다 **.**<br /><br /> **AddTail (LPCTSTR** `newElement` **)** 위치<br /><br /> **Void AddTail (CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="example"></a>예제

  `CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

##  <a name="coblist"></a>CObList:: CObList

빈 `CObject` 포인터 목록을 생성 합니다.

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
목록을 확장 하기 위한 메모리 할당 세분성입니다.

### <a name="remarks"></a>설명

목록이 커지면 메모리는 *Nblocksize* 항목의 단위로 할당 됩니다. 메모리 할당이 실패 하면 `CMemoryException`이 throw 됩니다.

다음 표에서는 `CObList::CObList`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Cptrlist (INT_PTR** `nBlockSize` **= 10);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>예제

  다음은 모든 컬렉션 예제에서 사용 `CAge` `CObject`파생 클래스 목록입니다.

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

다음은 `CObList` 생성자 사용법의 예입니다.

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

##  <a name="find"></a>CObList:: Find

지정 된 `CObject` 포인터와 일치 하는 첫 번째 `CObject` 포인터를 찾기 위해 목록을 순서 대로 검색 합니다.

```
POSITION Find(
    CObject* searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>매개 변수

*searchValue*<br/>
이 목록에 있는 개체 포인터입니다.

*startAfter*<br/>
검색의 시작 위치입니다.

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 위치 값입니다. 개체를 찾을 수 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

포인터 값은 개체의 내용이 아니라 비교 됩니다.

다음 표에서는 `CObList::Find`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Position Find (void** <strong>\*</strong> `searchValue` **, position** `startAfter` **= NULL) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Position Find (LPCTSTR** `searchValue` **, Position** `startAfter` **= NULL) const;**|

### <a name="example"></a>예제

`CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

##  <a name="findindex"></a>CObList:: FindIndex

*N 인덱스* 값을 목록에 인덱스로 사용 합니다.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
찾을 목록 요소의 인덱스 (0부터 시작)입니다.

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 위치 값입니다. *N 인덱스가* 너무 클 경우 NULL입니다. *N 인덱스가* 음수인 경우 프레임 워크는 어설션을 생성 합니다.

### <a name="remarks"></a>설명

목록의 헤드에서 순차적 검색을 시작 하 고 *n*번째 요소에서 중지 합니다.

다음 표에서는 `CObList::FindIndex`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 FindIndex (INT_PTR** `nIndex` **) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 FindIndex (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>예제

`CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

##  <a name="getat"></a>CObList:: GetAt

POSITION 형식의 변수는 목록의 키입니다.

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>매개 변수

*position*<br/>
이전 `GetHeadPosition` 또는 `Find` 멤버 함수 호출에서 반환 된 위치 값입니다.

### <a name="return-value"></a>Return Value

[GetHead](#gethead)에 대 한 반환 값 설명을 참조 하세요.

### <a name="remarks"></a>설명

인덱스와 동일 하지 않으며 위치 값에 직접 작업할 수 없습니다. `GetAt`는 지정 된 위치와 연결 된 `CObject` 포인터를 검색 합니다.

위치 값이 목록에서 올바른 위치를 나타내는지 확인 해야 합니다. 잘못 된 경우 MFC 라이브러리의 디버그 버전에서 어설션 합니다.

다음 표에서는 `CObList::GetAt`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetAt (위치** *위치* **) const;**<br /><br /> **void\*& GetAt (위치** *위치* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const CString & GetAt (위치** *위치* **) const;**<br /><br /> **CString & GetAt (위치** *위치* **);**|

### <a name="example"></a>예제

  [Findindex](#findindex)의 예제를 참조 하세요.

##  <a name="getcount"></a>CObList:: GetCount

이 목록에 있는 요소의 수를 가져옵니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Return Value

요소 수를 포함 하는 정수 값입니다.

다음 표에서는 `CObList::GetCount`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetCount () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>예제

`CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

##  <a name="gethead"></a>CObList:: GetHead

이 목록의 head 요소를 나타내는 `CObject` 포인터를 가져옵니다.

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>Return Value

`const CObList`에 대 한 포인터를 통해 목록에 액세스 하는 경우 `GetHead`는 `CObject` 포인터를 반환 합니다. 이를 통해 함수를 대입문의 오른쪽에만 사용할 수 있으므로 목록을 수정 하지 않도록 보호할 수 있습니다.

목록이 직접 또는 `CObList`포인터를 통해 액세스 되는 경우 `GetHead` `CObject` 포인터에 대 한 참조를 반환 합니다. 이를 통해 대입문의 한쪽에서 함수를 사용할 수 있으므로 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

`GetHead`를 호출 하기 전에 목록이 비어 있지 않은지 확인 해야 합니다. 목록이 비어 있으면 MFC 라이브러리의 디버그 버전에서 어설션 합니다. [IsEmpty](#isempty) 를 사용 하 여 목록에 요소가 포함 되어 있는지 확인 합니다.

다음 표에서는 `CObList::GetHead`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetHead () const; void\*& GetHead ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetHead () const; CString & GetHead ();**|

### <a name="example"></a>예제

`CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

다음 예에서는 대입문의 왼쪽에 `GetHead`를 사용 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

##  <a name="getheadposition"></a>CObList:: Geadposition

이 목록에 있는 head 요소의 위치를 가져옵니다.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 위치 값입니다. 목록이 비어 있으면 NULL입니다.

다음 표에서는 `CObList::GetHeadPosition`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Adposition () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Adposition () const;**|

### <a name="example"></a>예제

`CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

##  <a name="getnext"></a>CObList:: GetNext

*Rposition*으로 식별 되는 목록 요소를 가져온 다음 *rposition* 을 목록에서 다음 항목의 `POSITION` 값으로 설정 합니다.

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*rPosition*<br/>
이전 `GetNext`, `GetHeadPosition`또는 기타 멤버 함수 호출에서 반환 된 위치 값에 대 한 참조입니다.

### <a name="return-value"></a>Return Value

[GetHead](#gethead)에 대 한 반환 값 설명을 참조 하세요.

### <a name="remarks"></a>설명

`GetHeadPosition` 또는 `Find`를 호출 하 여 초기 위치를 설정 하는 경우 전방 반복 루프에서 `GetNext`를 사용할 수 있습니다.

위치 값이 목록에서 올바른 위치를 나타내는지 확인 해야 합니다. 잘못 된 경우 MFC 라이브러리의 디버그 버전에서 어설션 합니다.

검색 된 요소가 목록에서 마지막 이면 *Rposition* 의 새 값이 NULL로 설정 됩니다.

반복 하는 동안 요소를 제거할 수 있습니다. [RemoveAt](#removeat)의 예제를 참조 하세요.

> [!NOTE]
>  MFC 8.0에서이 메서드의 const 버전은 `const CObject*&`대신 `const CObject*`을 반환 하도록 변경 되었습니다.  이러한 변경으로 인해 컴파일러를 C++ 표준 준수 상태로 전환 했습니다.

다음 표에서는 `CObList::GetNext`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>예제

  `CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

##  <a name="getprev"></a>CObList:: GetPrev

*Rposition*으로 식별 되는 목록 요소를 가져온 다음 *rposition* 을 목록에 있는 이전 항목의 위치 값으로 설정 합니다.

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*rPosition*<br/>
이전 `GetPrev` 또는 다른 멤버 함수 호출에서 반환 된 위치 값에 대 한 참조입니다.

### <a name="return-value"></a>Return Value

[GetHead](#gethead)에 대 한 반환 값 설명을 참조 하세요.

### <a name="remarks"></a>설명

`GetTailPosition` 또는 `Find`를 호출 하 여 초기 위치를 설정 하는 경우 역방향 반복 루프에서 `GetPrev`를 사용할 수 있습니다.

위치 값이 목록에서 올바른 위치를 나타내는지 확인 해야 합니다. 잘못 된 경우 MFC 라이브러리의 디버그 버전에서 어설션 합니다.

검색 된 요소가 목록의 첫 번째 이면 *Rposition* 의 새 값이 NULL로 설정 됩니다.

> [!NOTE]
>  MFC 8.0에서이 메서드의 const 버전은 `const CObject*&`대신 `const CObject*`을 반환 하도록 변경 되었습니다.  이러한 변경으로 인해 컴파일러를 C++ 표준 준수 상태로 전환 했습니다.

다음 표에서는 `CObList::GetPrev`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>예제

  `CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
a CAge at $421C 21
a CAge at $421C 40
```

##  <a name="getsize"></a>CObList:: GetSize

목록 요소의 수를 반환 합니다.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Return Value

목록에 있는 항목의 수입니다.

### <a name="remarks"></a>설명

목록의 요소 수를 검색 하려면이 메서드를 호출 합니다.

다음 표에서는 `CObList::GetSize`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetSize () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>예제

`CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

##  <a name="gettail"></a>CObList:: GetTail

이 목록의 꼬리 요소를 나타내는 `CObject` 포인터를 가져옵니다.

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>Return Value

[GetHead](#gethead)에 대 한 반환 값 설명을 참조 하세요.

### <a name="remarks"></a>설명

`GetTail`를 호출 하기 전에 목록이 비어 있지 않은지 확인 해야 합니다. 목록이 비어 있으면 MFC 라이브러리의 디버그 버전에서 어설션 합니다. [IsEmpty](#isempty) 를 사용 하 여 목록에 요소가 포함 되어 있는지 확인 합니다.

다음 표에서는 `CObList::GetTail`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetTail () const; void\*& GetTail ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetTail () const; CString & GetTail ();**|

### <a name="example"></a>예제

`CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

##  <a name="gettailposition"></a>CObList:: GetTailPosition

이 목록에 있는 tail 요소의 위치를 가져옵니다. 목록이 비어 있으면 **NULL** 입니다.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 위치 값입니다. 목록이 비어 있으면 NULL입니다.

다음 표에서는 `CObList::GetTailPosition`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION GetTailPosition () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION GetTailPosition () const;**|

### <a name="example"></a>예제

`CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

##  <a name="insertafter"></a>CObList:: InsertAfter

이 목록에서 지정 된 위치에 있는 요소 뒤에 요소를 추가 합니다.

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>매개 변수

*position*<br/>
이전 `GetNext`, `GetPrev`또는 `Find` 멤버 함수 호출에서 반환 되는 위치 값입니다.

*newElement*<br/>
이 목록에 추가할 개체 포인터입니다.

다음 표에서는 `CObList::InsertAfter`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Position InsertAfter (위치** *위치* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Position InsertAfter (위치** *위치* **, const CString &** `newElement` **);**<br /><br /> **Position InsertAfter (position** *position* **, LPCTSTR** `newElement` **);**|

### <a name="return-value"></a>Return Value

*Position 매개 변수와* 동일한 위치 값입니다.

### <a name="example"></a>예제

  `CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

##  <a name="insertbefore"></a>CObList:: InsertBefore

이 목록에서 지정된 위치의 요소 앞에 요소를 추가합니다.

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>매개 변수

*position*<br/>
이전 `GetNext`, `GetPrev`또는 `Find` 멤버 함수 호출에서 반환 되는 위치 값입니다.

*newElement*<br/>
이 목록에 추가할 개체 포인터입니다.

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 위치 값입니다. 목록이 비어 있으면 NULL입니다.

다음 표에서는 `CObList::InsertBefore`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Position InsertBefore (위치** *위치* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Position InsertBefore (위치** *위치* **, const CString &** `newElement` **);**<br /><br /> **Position InsertBefore (position** *position* **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>예제

  `CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

##  <a name="isempty"></a>CObList:: IsEmpty

이 목록에 요소가 없는지 여부를 나타냅니다.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Return Value

이 목록이 비어 있으면 0이 아닌 값입니다. 그렇지 않으면 0입니다.

다음 표에서는 `CObList::IsEmpty`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL IsEmpty () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL IsEmpty () const;**|

### <a name="example"></a>예제

  [RemoveAll](#removeall)의 예제를 참조 하세요.

##  <a name="removeall"></a>CObList:: RemoveAll

이 목록에서 모든 요소를 제거 하 고 연결 된 `CObList` 메모리를 해제 합니다.

```
void RemoveAll();
```

### <a name="remarks"></a>설명

목록이 이미 비어 있으면 오류가 발생 하지 않습니다.

`CObList`에서 요소를 제거 하는 경우 목록에서 개체 포인터를 제거 합니다. 개체 자체를 삭제 하는 것은 사용자의 책임입니다.

다음 표에서는 `CObList::RemoveAll`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAll ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAll ();**|

### <a name="example"></a>예제

`CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

##  <a name="removeat"></a>CObList:: RemoveAt

이 목록에서 지정 된 요소를 제거 합니다.

```
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>매개 변수

*position*<br/>
목록에서 제거할 요소의 위치입니다.

### <a name="remarks"></a>설명

`CObList`에서 요소를 제거 하는 경우 목록에서 개체 포인터를 제거 합니다. 개체 자체를 삭제 하는 것은 사용자의 책임입니다.

위치 값이 목록에서 올바른 위치를 나타내는지 확인 해야 합니다. 잘못 된 경우 MFC 라이브러리의 디버그 버전에서 어설션 합니다.

다음 표에서는 `CObList::RemoveAt`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Void RemoveAt (위치** *위치* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Void RemoveAt (위치** *위치* **);**|

### <a name="example"></a>예제

  목록을 반복 하는 동안 요소를 제거할 때는 주의 해야 합니다. 다음 예제에서는 [GetNext](#getnext)에 대해 유효한 **위치** 값을 보장 하는 제거 기법을 보여 줍니다.

`CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

이 프로그램의 결과는 다음과 같습니다.

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

##  <a name="removehead"></a>CObList:: RemoveHead

목록의 맨 위에 있는 요소를 제거 하 고 해당 요소에 대 한 포인터를 반환 합니다.

```
CObject* RemoveHead();
```

### <a name="return-value"></a>Return Value

목록 맨 위에 있는 `CObject` 포인터입니다.

### <a name="remarks"></a>설명

`RemoveHead`를 호출 하기 전에 목록이 비어 있지 않은지 확인 해야 합니다. 목록이 비어 있으면 MFC 라이브러리의 디버그 버전에서 어설션 합니다. [IsEmpty](#isempty) 를 사용 하 여 목록에 요소가 포함 되어 있는지 확인 합니다.

다음 표에서는 `CObList::RemoveHead`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveHead ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead ();**|

### <a name="example"></a>예제

`CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

##  <a name="removetail"></a>CObList:: RemoveTail

목록의 끝에서 요소를 제거 하 고 해당 요소에 대 한 포인터를 반환 합니다.

```
CObject* RemoveTail();
```

### <a name="return-value"></a>Return Value

목록의 끝에 있는 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`RemoveTail`를 호출 하기 전에 목록이 비어 있지 않은지 확인 해야 합니다. 목록이 비어 있으면 MFC 라이브러리의 디버그 버전에서 어설션 합니다. [IsEmpty](#isempty) 를 사용 하 여 목록에 요소가 포함 되어 있는지 확인 합니다.

다음 표에서는 `CObList::RemoveTail`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveTail ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail ();**|

### <a name="example"></a>예제

`CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

##  <a name="setat"></a>CObList:: SetAt

지정 된 위치에 요소를 설정 합니다.

```
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
설정할 요소의 위치입니다.

*newElement*<br/>
목록에 쓸 `CObject` 포인터입니다.

### <a name="remarks"></a>설명

POSITION 형식의 변수는 목록의 키입니다. 인덱스와 동일 하지 않으며 위치 값에 직접 작업할 수 없습니다. `SetAt`는 목록의 지정 된 위치에 `CObject` 포인터를 씁니다.

위치 값이 목록에서 올바른 위치를 나타내는지 확인 해야 합니다. 잘못 된 경우 MFC 라이브러리의 디버그 버전에서 어설션 합니다.

다음 표에서는 `CObList::SetAt`와 유사한 다른 멤버 함수를 보여 줍니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Void SetAt (위치** `pos` **, const CString &** `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Void SetAt (위치** `pos` **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>예제

  `CAge` 클래스 목록은 [CObList:: CObList](#coblist) 를 참조 하세요.

[!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
SetAt example: A CObList with 2 elements
a CAge at $4D98 40
a CAge at $4DB8 65
```

## <a name="see-also"></a>참고 항목

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CStringList 클래스](../../mfc/reference/cstringlist-class.md)<br/>
[CPtrList 클래스](../../mfc/reference/cptrlist-class.md)
