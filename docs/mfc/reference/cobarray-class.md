---
title: CObArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CObArray
- AFXCOLL/CObArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
ms.openlocfilehash: c19715f62704bfc97059421451929cbbec2506ce
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754466"
---
# <a name="cobarray-class"></a>CObArray 클래스

`CObject` 포인터 배열을 지원합니다.

## <a name="syntax"></a>구문

```
class CObArray : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CObArray::CObArray](#cobarray)|포인터에 대한 `CObject` 빈 배열을 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CObArray::추가](#add)|배열 끝에 요소를 추가하고 필요하면 배열을 확장합니다.|
|[CObArray::부속](#append)|배열에 다른 배열을 추가하고 필요하면 배열을 확장합니다.|
|[CObArray::복사](#copy)|배열에 다른 배열을 복사하고 필요하면 배열을 확장합니다.|
|[CObArray::요소](#elementat)|배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.|
|[CObArray::무료 엑스트라](#freeextra)|현재 상한을 초과하며 사용되지 않는 모든 메모리를 해제합니다.|
|[CObArray::GetAt](#getat)|지정된 인덱스의 값을 반환합니다.|
|[CObArray::GetCount](#getcount)|이 배열에 있는 요소의 수를 가져옵니다.|
|[CObArray::GetData](#getdata)|배열의 요소에 대한 액세스를 허용합니다. NULL일 수 있습니다.|
|[CObArray::GetSize](#getsize)|이 배열에 있는 요소의 수를 가져옵니다.|
|[CObArray::GetUpper바운드](#getupperbound)|유효한 최대 인덱스를 반환합니다.|
|[CObArray::삽입](#insertat)|지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.|
|[CObArray::비어 있음](#isempty)|배열이 비어 있는지를 확인합니다.|
|[CObArray::모두 제거](#removeall)|이 배열의 모든 요소를 반환합니다.|
|[CObArray::제거](#removeat)|특정 인덱스의 요소를 제거합니다.|
|[CObArray::SetAt](#setat)|지정된 인덱스의 값을 설정합니다. 배열은 확장할 수 없습니다.|
|[CObArray::SetAtGrow](#setatgrow)|지정된 인덱스의 값을 설정합니다. 필요한 경우 배열을 확장합니다.|
|[CObArray::SetSize](#setsize)|이 배열에 포함된 요소의 수를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CObArray::연산자 \[\]](#operator_at)|지정한 인덱스에 있는 요소를 설정하거나 가져옵니다.|

## <a name="remarks"></a>설명

이러한 개체 배열은 C 배열과 유사하지만 필요에 따라 동적으로 축소되고 증가할 수 있습니다.

배열 인덱스는 항상 위치 0에서 시작합니다. 상한을 수정할지 또는 현재 바운드를 지나 요소를 추가할 때 배열이 확장되도록 허용할지 결정할 수 있습니다. 일부 요소가 null인 경우에도 메모리는 상한에 연속적으로 할당됩니다.

Win32에서 `CObArray` 개체의 크기는 사용 가능한 메모리로만 제한됩니다.

C 배열과 마찬가지로 `CObArray` 인덱싱된 요소에 대한 액세스 시간은 일정하며 배열 크기와 독립적입니다.

`CObArray`IMPLEMENT_SERIAL 매크로를 통합하여 해당 요소의 직렬화 및 덤프를 지원합니다. 포인터 배열이 `CObject` 오버로드된 삽입 연산자 또는 `Serialize` 멤버 함수를 사용하여 아카이브에 저장되는 경우 각 `CObject` 요소는 배열 인덱스와 함께 직렬화됩니다.

배열에 개별 `CObject` 요소의 덤프가 필요한 경우 `CDumpContext` 개체의 깊이를 1 이상으로 설정해야 합니다.

개체가 `CObArray` 삭제되거나 해당 요소가 제거될 때 `CObject` 참조하는 개체가 아닌 포인터만 제거됩니다.

> [!NOTE]
> 배열을 사용하기 전에 `SetSize`를 사용하여 배열 크기를 설정하고 배열에 대해 메모리를 할당합니다. `SetSize`를 사용하지 않는 경우 배열에 요소를 추가하면 배열이 자주 다시 할당되고 복사됩니다. 이처럼 다시 할당 및 복사가 자주 수행되면 효율성이 떨어지며 메모리가 조각화될 수 있습니다.

배열 클래스 파생은 목록 파생과 유사합니다. 특수 목적 목록 클래스의 파생에 대한 자세한 내용은 [컬렉션](../../mfc/collections.md)문서를 참조하십시오.

> [!NOTE]
> 배열을 직렬화하려면 파생 클래스의 구현에 IMPLEMENT_SERIAL 매크로를 사용해야 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CObArray`

## <a name="requirements"></a>요구 사항

**헤더:** afxcoll.h

## <a name="cobarrayadd"></a><a name="add"></a>CObArray::추가

배열의 끝에 새 요소를 추가하여 배열을 1씩 증가시입니다.

```
INT_PTR Add(CObject* newElement);
```

### <a name="parameters"></a>매개 변수

*new엘리먼트*<br/>
이 `CObject` 배열에 추가할 포인터입니다.

### <a name="return-value"></a>Return Value

추가된 요소의 인덱스입니다.

### <a name="remarks"></a>설명

[SetSize가](#setsize) *nGrowBy* 값이 1보다 큰 경우 추가 메모리가 할당될 수 있습니다. 그러나 상한은 1로 증가합니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::Add`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR 추가 (바이트);** `newElement` **);**<br /><br /> **throw(C메모리예외);\***|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR 추가 (DWORD);** `newElement` **);**<br /><br /> **throw(C메모리예외);\***|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR 추가(무효);** <strong>\*</strong> `newElement` **);**<br /><br /> **throw(C메모리예외);\***|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR 추가 (LPCTSTR);** `newElement` **던지기\* (CMemoryException);**<br /><br /> **INT_PTR 추가 (const CString** `newElement` **&);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR 추가 (UINT);** `newElement` **);**<br /><br /> **throw(C메모리예외);\***|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR 추가 (WORD);** `newElement` **);**<br /><br /> **throw(C메모리예외);\***|

### <a name="example"></a>예제

  모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
Add example: A CObArray with 2 elements
[0] = a CAge at $442A 21
[1] = a CAge at $4468 40
```

## <a name="cobarrayappend"></a><a name="append"></a>CObArray::부속

이 멤버 함수를 호출하여 지정된 배열의 끝에 다른 배열의 내용을 추가합니다.

```
INT_PTR Append(const CObArray& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
배열에 추가할 요소의 소스입니다.

### <a name="return-value"></a>Return Value

첫 번째 추가된 요소의 인덱스입니다.

### <a name="remarks"></a>설명

배열은 동일한 형식이어야 합니다.

필요한 경우 `Append` 배열에 추가된 요소를 수용하기 위해 추가 메모리를 할당할 수 있습니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::Append`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR 부록 (cByteArray&** *src를* **구성);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR 부록 (cdWordArray&** *src를* **구성);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR 부록 (cPtrArray&** *src를* **const);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR 부록 (const CStringArray&** *src);* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR 부록(cuintArray&** *src);* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR 부록 (cwordArray&** *src를* const); **);**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]

## <a name="cobarraycopy"></a><a name="copy"></a>CObArray::복사

이 멤버 함수를 호출하여 동일한 형식의 다른 배열의 요소로 지정된 배열의 요소를 덮어씁니다.

```cpp
void Copy(const CObArray& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
배열에 복사할 요소의 소스입니다.

### <a name="remarks"></a>설명

`Copy`메모리를 확보하지 않습니다. 그러나 필요한 경우 `Copy` 배열에 복사된 요소를 수용하기 위해 추가 메모리를 할당할 수 있습니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::Copy`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**[무단전&** *src* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**무효 복사 (const CDWordArray&** *src);* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**무효 복사 (const CPtrArray&** *src);* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**[src&]** *src* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**무효 복사 (const CUIntArray&** *src);* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**무효 복사 (const CWordArray&** *src);* **);**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]

## <a name="cobarraycobarray"></a><a name="cobarray"></a>CObArray::CObArray

빈 `CObject` 포인터 배열을 생성합니다.

```
CObArray();
```

### <a name="remarks"></a>설명

배열은 한 번에 하나의 요소를 증가시다.

다음 표에서는 와 `CObArray::CObArray`유사한 다른 생성자가 표시됩니다.

|클래스|생성자|
|-----------|-----------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**CByteArray ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**CDWordArray ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**CPtrArray ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CStringArray ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**CUIntArray ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**CWordArray ();**|

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]

## <a name="cobarrayelementat"></a><a name="elementat"></a>CObArray::요소

배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.

```
CObject*& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0보다 크거나 같고 `GetUpperBound`에서 반환되는 값보다 크거나 같을 수 있는 정수 인덱스입니다.

### <a name="return-value"></a>Return Value

포인터에 대한 `CObject` 참조입니다.

### <a name="remarks"></a>설명

배열에 대한 왼쪽 할당 연산자를 구현하는 데 사용됩니다. 이 함수는 특수 배열 연산자만 구현하는 데 사용해야 하는 고급 함수입니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::ElementAt`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**바이트& 엘리먼트At (INT_PTR);** `nIndex` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD& 엘리먼트At (INT_PTR);** `nIndex` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**무효\*& ElementAt (INT_PTR);** `nIndex` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString& ElementAt (INT_PTR);** `nIndex` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT& 엘리먼트At (INT_PTR);** `nIndex` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**워드& ElementAt (INT_PTR);** `nIndex` **);**|

### <a name="example"></a>예제

  [CObArray::GetSize에](#getsize)대한 예제를 참조하십시오.

## <a name="cobarrayfreeextra"></a><a name="freeextra"></a>CObArray::무료 엑스트라

배열이 커짐동안 할당된 추가 메모리를 해제합니다.

```cpp
void FreeExtra();
```

### <a name="remarks"></a>설명

이 함수는 배열의 크기 나 상한에 영향을 주지 않습니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::FreeExtra`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**무효 프리 엑스트라 ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**무효 프리 엑스트라 ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**무효 프리 엑스트라 ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**무효 프리 엑스트라 ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**무효 프리 엑스트라 ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**무효 프리 엑스트라 ();**|

### <a name="example"></a>예제

  [CObArray::GetData에](#getdata)대한 예제를 참조하십시오.

## <a name="cobarraygetat"></a><a name="getat"></a>CObArray::GetAt

지정된 인덱스에서 배열 요소를 반환합니다.

```
CObject* GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0보다 크거나 같고 `GetUpperBound`에서 반환되는 값보다 크거나 같을 수 있는 정수 인덱스입니다.

### <a name="return-value"></a>Return Value

현재 `CObject` 이 인덱스에 있는 포인터 요소입니다.

### <a name="remarks"></a>설명

> [!NOTE]
> 음수 값 또는 반환된 `GetUpperBound` 값보다 큰 값을 전달하면 어설션이 실패합니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::GetAt`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE GetAt (INT_PTR)** `nIndex` **const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt (INT_PTR)** `nIndex` **const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**무효\* GetAt (INT_PTR)** `nIndex` **const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString GetAt (INT_PTR)** `nIndex` **const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT GetAt (INT_PTR)** `nIndex` **const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**워드 겟앳 (INT_PTR)** `nIndex` **const;**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]

## <a name="cobarraygetcount"></a><a name="getcount"></a>CObArray::GetCount

배열 요소의 수를 반환합니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Return Value

배열의 항목 수입니다.

### <a name="remarks"></a>설명

배열의 요소 수를 검색하려면 이 메서드를 호출합니다. 인덱스는 0을 기준으로 하므로 크기는 가장 큰 인덱스보다 1 큽니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::GetCount`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR 겟카운트()**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR 겟카운트()**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR 겟카운트()**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR 겟카운트()**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR 겟카운트()**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR 겟카운트()**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]

## <a name="cobarraygetdata"></a><a name="getdata"></a>CObArray::GetData

이 멤버 함수를 사용하여 배열의 요소에 직접 액세스할 수 있습니다.

```
const CObject** GetData() const;

CObject** GetData();
```

### <a name="return-value"></a>Return Value

`CObject` 포인터 배열에 대한 포인터입니다.

### <a name="remarks"></a>설명

사용 가능한 요소가 `GetData` 없는 경우 null 값을 반환합니다.

배열의 요소에 직접 액세스하면 더 빠르게 작업할 수 있지만 `GetData`호출할 때 주의하십시오. 오류가 발생하면 배열의 요소에 직접 영향을 미칩니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::GetData`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**\* [바이트]() 바이트\* 겟데이터();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**const DWORD\* GetData () const;DWORD\* GetData();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**const\* \* void GetData ()\* \* const;void GetData();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**const CString\* GetData() const; 문자열\* GetData ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**구성부 UINT\* GetData() UINT\* GetData ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**const\* WORD GetData () const; 워드\* 겟데이터();**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]

## <a name="cobarraygetsize"></a><a name="getsize"></a>CObArray::GetSize

배열의 크기를 반환합니다.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>설명

인덱스는 0부터 기반하므로 크기는 가장 큰 인덱스보다 1 더 큽니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::GetSize`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetSize () const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetSize () const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetSize () const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetSize () const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetSize () const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]

## <a name="cobarraygetupperbound"></a><a name="getupperbound"></a>CObArray::GetUpper바운드

이 배열의 현재 상한을 반환합니다.

```
INT_PTR GetUpperBound() const;
```

### <a name="return-value"></a>Return Value

상한(0기준)의 인덱스입니다.

### <a name="remarks"></a>설명

배열 인덱스는 0 기반이므로 이 함수는 값 `GetSize`1보다 작은 값을 반환합니다.

조건 `GetUpperBound( )` = -1은 배열에 요소가 포함되어 있지 없음을 나타냅니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::GetUpperBound`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR 겟어퍼바운드() const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR 겟어퍼바운드() const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR 겟어퍼바운드() const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR 겟어퍼바운드() const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR 겟어퍼바운드() const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR 겟어퍼바운드() const;**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]

## <a name="cobarrayinsertat"></a><a name="insertat"></a>CObArray::삽입

지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.

```cpp
void InsertAt(
    INT_PTR nIndex,
    CObject* newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CObArray* pNewArray);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
`GetUpperBound`에서 반환되는 값보다 클 수 있는 정수 인덱스입니다.

*new엘리먼트*<br/>
이 `CObject` 배열에 배치할 포인터입니다. *newValue* NULL의 요소가 허용됩니다.

*nCount*<br/>
이 요소를 삽입해야 하는 횟수(기본값은 1)입니다.

*n스타트 인덱스*<br/>
`GetUpperBound`에서 반환되는 값보다 클 수 있는 정수 인덱스입니다.

*pNewArray*<br/>
이 배열에 추가할 요소를 포함하는 또 다른 배열입니다.

### <a name="remarks"></a>설명

첫 번째 `InsertAt` 버전의 요소는 배열의 지정된 인덱스에 하나의 요소(또는 요소의 여러 복사본)를 삽입합니다. 이 과정에서 이 인덱스의 기존 요소를 증가시켜 위로 이동하고 위의 모든 요소를 위로 이동합니다.

두 번째 버전은 *nStartIndex* `CObArray` 위치에서 시작하여 다른 컬렉션의 모든 요소를 삽입합니다.

반대로 `SetAt` 이 함수는 지정된 배열 요소 하나를 대체하며 요소를 이동하지 않습니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::InsertAt`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void InsertAt (INT_PTR,** `nIndex` **바이트** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw(C메모리예외);\***<br /><br /> **보이드 삽입 (INT_PTR** `nStartIndex` **, CByteArray);** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw(C메모리예외);\***|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**보이드 InsertAt (INT_PTR,** `nIndex` **DWORD** `newElement` **, int** `nCount` = **1);**<br /><br /> **throw(C메모리예외);\***<br /><br /> **빈데인 삽입(INT_PTR,** `nStartIndex` **CDWordArray);** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw(C메모리예외);\***|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void InsertAt (INT_PTR,** `nIndex` **void** <strong>\*</strong> `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw(C메모리예외);\***<br /><br /> **보이드 인서트(INT_PTR,** `nStartIndex` **CPtrArray);** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw(C메모리예외);\***|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**무효 InsertAt (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw(C메모리예외);\***<br /><br /> **보이드 삽입 (INT_PTR** `nStartIndex` **, CStringArray);** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw(C메모리예외);\***|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**보이드 InsertAt (INT_PTR,** `nIndex` **UINT** `newElement` **, int** `nCount` = **1);**<br /><br /> **throw(C메모리예외);\***<br /><br /> **빈티드 인서트(INT_PTR,** `nStartIndex` **CUIntArray);** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw(C메모리예외);\***|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, WORD** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw(C메모리예외);\***<br /><br /> **보이드 인서트(INT_PTR,** `nStartIndex` **CWordArray);** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw(C메모리예외);\***|

### <a name="example"></a>예제

  모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
InsertAt example: A CObArray with 3 elements
[0] = a CAge at $45C8 21
[1] = a CAge at $4646 30
[2] = a CAge at $4606 40
```

## <a name="cobarrayisempty"></a><a name="isempty"></a>CObArray::비어 있음

배열이 비어 있는지를 확인합니다.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Return Value

배열이 비어 있는 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="cobarrayoperator--"></a><a name="operator_at"></a>CObArray::연산자 [ ]

이러한 하위 스크립트 연산자는 `SetAt` 및 `GetAt` 기능을 편리하게 대체할 수 있습니다.

```
CObject*& operator[](int_ptr nindex);
CObject* operator[](int_ptr nindex) const;
```

### <a name="remarks"></a>설명

**const가**아닌 배열에 대해 호출된 첫 번째 연산자는 할당 문의 오른쪽(r-value) 또는 왼쪽(l-값)에서 사용할 수 있습니다. **const** 배열에 대 한 호출 하는 두 번째, 오른쪽에만 사용할 수 있습니다.

라이브러리의 디버그 버전은 할당 문의 왼쪽 또는 오른쪽에 있는 하위 스크립트가 경계를 벗어난 경우 어설션합니다.

다음 표에서는 와 `CObArray::operator []`유사한 다른 연산자가 표시됩니다.

|클래스|연산자|
|-----------|--------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**바이트& 연산자 [](int_ptr;** `nindex` ** \)**<br /><br /> **바이트 연산자 [](int_ptr** `nindex` ** \) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD& 연산자 [](int_ptr;** `nindex` ** \)**<br /><br /> **DWORD 연산자 [](int_ptr** `nindex` ** \) const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**무효\*& 연산자 [](int_ptr;** `nindex` ** \)**<br /><br /> **void\* 연산자 [](int_ptr** `nindex` ** \) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString& 연산자 [](int_ptr;** `nindex` ** \)**<br /><br /> **CString 연산자 [](int_ptr** `nindex` ** \) const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT& 연산자 [](int_ptr;** `nindex` ** \)**<br /><br /> **UINT 연산자 [](int_ptr** `nindex` ** \) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD& 연산자 [](int_ptr;** `nindex` ** \)**<br /><br /> **WORD 연산자 [](int_ptr** `nindex` ** \) const;**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]

## <a name="cobarrayremoveall"></a><a name="removeall"></a>CObArray::모두 제거

이 배열에서 모든 포인터를 제거하지만 실제로 `CObject` 개체를 삭제하지는 않습니다.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>설명

배열이 이미 비어 있으면 함수가 계속 작동합니다.

이 `RemoveAll` 함수는 포인터 저장에 사용되는 모든 메모리를 해제합니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::RemoveAll`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**무효 제거모든 ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**무효 제거모든 ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**무효 제거모든 ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**무효 제거모든 ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**무효 제거모든 ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**무효 제거모든 ();**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]

## <a name="cobarrayremoveat"></a><a name="removeat"></a>CObArray::제거

배열의 지정된 인덱스에서 시작하는 하나 이상의 요소를 제거합니다.

```cpp
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0보다 크거나 같고 `GetUpperBound`에서 반환되는 값보다 크거나 같을 수 있는 정수 인덱스입니다.

*nCount*<br/>
제거할 요소의 수입니다.

### <a name="remarks"></a>설명

이 과정에서 제거된 요소 위의 모든 요소가 아래로 이동합니다. 배열의 상한을 감소시키지만 메모리를 확보하지는 않습니다.

제거 지점 위의 배열에 포함된 것보다 더 많은 요소를 제거하려고 하면 라이브러리의 디버그 버전이 어설션됩니다.

함수는 `RemoveAt` 배열에서 `CObject` 포인터를 제거하지만 개체 자체는 삭제하지 않습니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::RemoveAt`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**무효 제거At (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**무효 제거At (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**무효 제거At (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**무효 제거At (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**무효 제거At (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**무효 제거At (INT_PTR,** `nIndex` **INT_PTR** *nCount* **= 1);**|

### <a name="example"></a>예제

  모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
RemoveAt example: A CObArray with 1 elements
[0] = a CAge at $4606 40
```

## <a name="cobarraysetat"></a><a name="setat"></a>CObArray::SetAt

지정된 인덱스에서 배열 요소를 설정합니다.

```cpp
void SetAt(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0보다 크거나 같고 `GetUpperBound`에서 반환되는 값보다 크거나 같을 수 있는 정수 인덱스입니다.

*new엘리먼트*<br/>
이 배열에 삽입할 개체 포인터입니다. NULL 값이 허용됩니다.

### <a name="remarks"></a>설명

`SetAt`배열이 증가하지 않습니다. 배열이 자동으로 증가하도록 하려면 사용합니다. `SetAtGrow`

인덱스 값이 배열에서 유효한 위치를 나타내는지 확인해야 합니다. 범위를 벗어난 경우 라이브러리의 디버그 버전이 어설션됩니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::SetAt`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**무효 SetAt (INT_PTR** `nIndex` **, 바이트);** `newElement` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**[INT_PTR,** `nIndex` **DWORD)** `newElement` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**무효 SetAt (INT_PTR,** `nIndex` <strong>\*</strong> `newElement` **무효);** **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**무효 SetAt (INT_PTR** `nIndex` **, LPCTSTR);** `newElement` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**[INT_PTR,** `nIndex` **UINT)** `newElement` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**무효 SetAt (INT_PTR** `nIndex` **, 워드);** `newElement` **);**|

### <a name="example"></a>예제

  모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
SetAt example: A CObArray with 2 elements
[0] = a CAge at $47E0 30
[1] = a CAge at $47A0 40
```

## <a name="cobarraysetatgrow"></a><a name="setatgrow"></a>CObArray::SetAtGrow

지정된 인덱스에서 배열 요소를 설정합니다.

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0보다 크거나 같은 정수 인덱스입니다.

*new엘리먼트*<br/>
이 배열에 추가할 개체 포인터입니다. NULL 값이 허용됩니다.

### <a name="remarks"></a>설명

필요한 경우 배열이 자동으로 증가합니다(즉, 상한은 새 요소를 수용하도록 조정됩니다).

다음 표에서는 와 유사한 다른 멤버 `CObArray::SetAtGrow`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**무효 SetAtGrow (INT_PTR,** `nIndex` **BYTE);** `newElement` **);**<br /><br /> **throw(C메모리예외);\***|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**무효 SetAtGrow (INT_PTR** `nIndex` **, DWORD);** `newElement` **);**<br /><br /> **throw(C메모리예외);\***|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**무효 SetAtGrow (INT_PTR,** `nIndex` <strong>\*</strong> `newElement` **무효);** **);**<br /><br /> **throw(C메모리예외);\***|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**무효 SetAtGrow (INT_PTR** `nIndex` **, LPCTSTR);** `newElement` **);**<br /><br /> **throw(C메모리예외);\***|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**[INT_PTR,** `nIndex` **UINT)** `newElement` **);**<br /><br /> **throw(C메모리예외);\***|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**[INT_PTR=** `nIndex` **=]** `newElement` **);**<br /><br /> **throw(C메모리예외);\***|

### <a name="example"></a>예제

  모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
SetAtGrow example: A CObArray with 4 elements
[0] = a CAge at $47C0 21
[1] = a CAge at $4800 40
[2] = NULL
[3] = a CAge at $4840 65
```

## <a name="cobarraysetsize"></a><a name="setsize"></a>CObArray::SetSize

빈 배열 또는 기존 배열의 크기를 설정합니다. 필요한 경우 메모리를 할당합니다.

```cpp
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>매개 변수

*nNewSize*<br/>
새 배열 크기(요소 수)입니다. 0보다 크거나 같아야 합니다.

*nGrowBy*<br/>
크기 증가가 필요한 경우 할당할 요소 슬롯의 최소 수입니다.

### <a name="remarks"></a>설명

새 크기가 이전 크기보다 작으면 배열이 잘리고 사용되지 않는 모든 메모리가 해제됩니다. 효율성을 위해 `SetSize` 사용하기 전에 배열의 크기를 설정하려면 호출하십시오. 이렇게 하면 항목이 추가될 때마다 배열을 재할당하고 복사할 필요가 없습니다.

*nGrowBy* 매개 변수는 배열이 증가하는 동안 내부 메모리 할당에 영향을 줍니다. 이 사용으로 보고된 배열 `GetSize` 크기에는 `GetUpperBound`영향을 미치지 않습니다.

배열의 크기가 커지면 새로 할당된 모든 **CObject** <strong>\*</strong> 포인터가 NULL로 설정됩니다.

다음 표에서는 와 유사한 다른 멤버 `CObArray::SetSize`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw(C메모리예외);\***|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw(C메모리예외);\***|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw(C메모리예외);\***|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw(C메모리예외);\***|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw(C메모리예외);\***|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw(C메모리예외);\***|

### <a name="example"></a>예제

  [CObArray::GetData에](#getdata)대한 예제를 참조하십시오.

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CStringArray 클래스](../../mfc/reference/cstringarray-class.md)<br/>
[CPtrArray 클래스](../../mfc/reference/cptrarray-class.md)<br/>
[CByteArray 클래스](../../mfc/reference/cbytearray-class.md)<br/>
[CWordArray 클래스](../../mfc/reference/cwordarray-class.md)<br/>
[CDWordArray 클래스](../../mfc/reference/cdwordarray-class.md)
