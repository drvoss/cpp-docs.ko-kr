---
title: CArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CArray
- AFXTEMPL/CArray
- AFXTEMPL/CArray::CArray
- AFXTEMPL/CArray::Add
- AFXTEMPL/CArray::Append
- AFXTEMPL/CArray::Copy
- AFXTEMPL/CArray::ElementAt
- AFXTEMPL/CArray::FreeExtra
- AFXTEMPL/CArray::GetAt
- AFXTEMPL/CArray::GetCount
- AFXTEMPL/CArray::GetData
- AFXTEMPL/CArray::GetSize
- AFXTEMPL/CArray::GetUpperBound
- AFXTEMPL/CArray::InsertAt
- AFXTEMPL/CArray::IsEmpty
- AFXTEMPL/CArray::RemoveAll
- AFXTEMPL/CArray::RemoveAt
- AFXTEMPL/CArray::SetAt
- AFXTEMPL/CArray::SetAtGrow
- AFXTEMPL/CArray::SetSize
helpviewer_keywords:
- CArray [MFC], CArray
- CArray [MFC], Add
- CArray [MFC], Append
- CArray [MFC], Copy
- CArray [MFC], ElementAt
- CArray [MFC], FreeExtra
- CArray [MFC], GetAt
- CArray [MFC], GetCount
- CArray [MFC], GetData
- CArray [MFC], GetSize
- CArray [MFC], GetUpperBound
- CArray [MFC], InsertAt
- CArray [MFC], IsEmpty
- CArray [MFC], RemoveAll
- CArray [MFC], RemoveAt
- CArray [MFC], SetAt
- CArray [MFC], SetAtGrow
- CArray [MFC], SetSize
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
ms.openlocfilehash: 3355e72c58365e97f8f3f8ce09754285f671915a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753972"
---
# <a name="carray-class"></a>CArray 클래스

C 배열과 비슷하지만 필요에 따라 동적으로 줄이고 늘릴 수 있는 배열을 지원합니다.

## <a name="syntax"></a>구문

```
template <class TYPE, class ARG_TYPE = const TYPE&>
class CArray : public CObject
```

#### <a name="parameters"></a>매개 변수

*유형*<br/>
배열에 저장된 개체의 유형을 지정하는 템플릿 매개 변수입니다. *TYPE은* `CArray`에서 반환되는 매개 변수입니다.

*ARG_TYPE*<br/>
배열에 저장된 개체에 액세스하는 데 사용되는 인수 형식을 지정하는 템플릿 매개 변수입니다. 종종 *TYPE*에 대한 참조입니다. *ARG_TYPE* `CArray`에 전달되는 매개 변수입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CArray::CArray](#carray)|빈 배열을 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[배열 ::추가](#add)|배열 끝에 요소를 추가하고 필요하면 배열을 확장합니다.|
|[배열 ::부속](#append)|배열에 다른 배열을 추가합니다. 필요한 경우 배열이 증가합니다.|
|[배열::복사](#copy)|배열에 다른 배열을 복사하고 필요하면 배열을 확장합니다.|
|[배열 ::요소](#elementat)|배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.|
|[CArray ::무료 엑스트라](#freeextra)|현재 상한을 초과하며 사용되지 않는 모든 메모리를 해제합니다.|
|[CArray::GetAt](#getat)|지정된 인덱스의 값을 반환합니다.|
|[배열 :: GetCount](#getcount)|이 배열에 있는 요소의 수를 가져옵니다.|
|[CArray::GetData](#getdata)|배열의 요소에 대한 액세스를 허용합니다. NULL일 수 있습니다.|
|[배열 :: GetSize](#getsize)|이 배열에 있는 요소의 수를 가져옵니다.|
|[CArray::GetUpper바운드](#getupperbound)|유효한 최대 인덱스를 반환합니다.|
|[배열::삽입](#insertat)|지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.|
|[배열::비어 있음](#isempty)|배열이 비어 있는지 여부를 확인합니다.|
|[배열 :: 모두 제거](#removeall)|이 배열의 모든 요소를 반환합니다.|
|[배열 :: 제거At](#removeat)|특정 인덱스의 요소를 제거합니다.|
|[CArray::SetAt](#setat)|지정된 인덱스의 값을 설정합니다. 배열은 확장할 수 없습니다.|
|[CArray:::세터그로우](#setatgrow)|지정된 인덱스의 값을 설정합니다. 필요한 경우 배열을 확장합니다.|
|[배열 :: 세트 크기](#setsize)|이 배열에 포함된 요소의 수를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[operator&#91;&#93;](#operator_at)|지정한 인덱스에 있는 요소를 설정하거나 가져옵니다.|

## <a name="remarks"></a>설명

배열 인덱스는 항상 위치 0에서 시작합니다. 상한을 수정할지 또는 현재 바운드를 지나 요소를 추가할 때 배열이 확장될지 결정할 수 있습니다. 일부 요소가 null인 경우에도 메모리는 상한에 연속적으로 할당됩니다.

> [!NOTE]
> `CArray` 개체의 크기를 조정하거나 요소를 추가하는 대부분의 메서드는 [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) 사용하여 요소를 이동합니다. 생성자가 호출되어야 `memcpy_s` 하는 개체와 호환되지 않기 때문에 이 문제는 문제가 됩니다. 의 `CArray` 항목이 `memcpy_s`와 호환되지 않는 경우 적절한 `CArray` 크기의 새 항목을 만들어야 합니다. 그런 다음 [CArray::Copy](#copy) 및 [CArray:SetAt를](#setat) 사용하여 새 배열을 채우기 위해 이러한 `memcpy_s`메서드는 대신 할당 연산자를 사용하므로.

C 배열과 마찬가지로 `CArray` 인덱싱된 요소에 대한 액세스 시간은 일정하며 배열 크기와 독립적입니다.

> [!TIP]
> 배열을 사용하기 전에 [SetSize를](#setsize) 사용하여 크기를 설정하고 메모리를 할당합니다. `SetSize`를 사용하지 않는 경우 배열에 요소를 추가하면 배열이 자주 다시 할당되고 복사됩니다. 이처럼 다시 할당 및 복사가 자주 수행되면 효율성이 떨어지며 메모리가 조각화될 수 있습니다.

배열에 개별 요소의 덤프가 필요한 경우 [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 개체의 깊이를 1 이상으로 설정해야 합니다.

이 클래스의 특정 멤버 함수는 클래스의 대부분의 용도에 맞게 `CArray` 사용자 지정해야 하는 전역 도우미 함수를 호출합니다. MFC 매크로 및 전역 섹션에서 [컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md) 항목을 참조하십시오.

배열 클래스 파생은 목록 파생과 같습니다.

사용 `CArray`방법에 대한 자세한 내용은 [컬렉션](../../mfc/collections.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CArray`

## <a name="requirements"></a>요구 사항

**헤더:** afxtempl.h

## <a name="carrayadd"></a><a name="add"></a>배열 ::추가

배열의 끝에 새 요소를 추가하여 배열을 1씩 증가시입니다.

```
INT_PTR Add(ARG_TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*ARG_TYPE*<br/>
이 배열의 요소를 참조하는 인수 유형을 지정하는 템플릿 매개 변수입니다.

*new엘리먼트*<br/>
이 배열에 추가할 요소입니다.

### <a name="return-value"></a>Return Value

추가된 요소의 인덱스입니다.

### <a name="remarks"></a>설명

[SetSize값이](#setsize) 1보다 큰 `nGrowBy` 경우 추가 메모리가 할당될 수 있습니다. 그러나 상한은 1로 증가합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]

## <a name="carrayappend"></a><a name="append"></a>배열 ::부속

이 멤버 함수를 호출하여 한 배열의 내용을 다른 배열의 끝에 추가합니다.

```
INT_PTR Append(const CArray& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
배열에 추가할 요소의 소스입니다.

### <a name="return-value"></a>Return Value

첫 번째 추가된 요소의 인덱스입니다.

### <a name="remarks"></a>설명

배열은 동일한 형식이어야 합니다.

필요한 경우 `Append` 배열에 추가된 요소를 수용하기 위해 추가 메모리를 할당할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]

## <a name="carraycarray"></a><a name="carray"></a>CArray::CArray

빈 배열을 생성합니다.

```
CArray();
```

### <a name="remarks"></a>설명

배열은 한 번에 하나의 요소를 증가시다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]

## <a name="carraycopy"></a><a name="copy"></a>배열::복사

이 멤버 함수를 사용하여 한 배열의 요소를 다른 배열로 복사합니다.

```cpp
void Copy(const CArray& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
배열에 복사할 요소의 소스입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 호출하여 한 배열의 요소를 다른 배열의 요소로 덮어씁니다.

`Copy`메모리를 확보하지 않습니다. 그러나 필요한 경우 `Copy` 배열에 복사된 요소를 수용하기 위해 추가 메모리를 할당할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]

## <a name="carrayelementat"></a><a name="elementat"></a>배열 ::요소

배열 내의 지정된 요소에 대한 임시 참조를 반환합니다.

```
TYPE& ElementAt(INT_PTR nIndex);
const TYPE& ElementAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0보다 크거나 같고 [GetUpperBound에서](#getupperbound)반환된 값보다 크거나 같은 정수 인덱스입니다.

### <a name="return-value"></a>Return Value

배열 요소에 대한 참조입니다.

### <a name="remarks"></a>설명

배열에 대한 왼쪽 할당 연산자를 구현하는 데 사용됩니다.

### <a name="example"></a>예제

  [GetSize](#getsize)에 대한 예제를 참조하십시오.

## <a name="carrayfreeextra"></a><a name="freeextra"></a>CArray ::무료 엑스트라

배열이 커짐동안 할당된 추가 메모리를 해제합니다.

```cpp
void FreeExtra();
```

### <a name="remarks"></a>설명

이 함수는 배열의 크기 나 상한에 영향을 주지 않습니다.

### <a name="example"></a>예제

  [GetData](#getdata)에 대한 예제를 참조하십시오.

## <a name="carraygetat"></a><a name="getat"></a>CArray::GetAt

지정된 인덱스에서 배열 요소를 반환합니다.

```
TYPE& GetAt(INT_PTR nIndex);
const TYPE& GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
배열 요소의 형식을 지정하는 템플릿 매개 변수입니다.

*nIndex*<br/>
0보다 크거나 같고 [GetUpperBound에서](#getupperbound)반환된 값보다 크거나 같은 정수 인덱스입니다.

### <a name="return-value"></a>Return Value

현재 이 인덱스에 있는 배열 요소입니다.

### <a name="remarks"></a>설명

음수 값 또는 반환된 `GetUpperBound` 값보다 큰 값을 전달하면 어설션이 실패합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]

## <a name="carraygetcount"></a><a name="getcount"></a>배열 :: GetCount

배열 요소의 수를 반환합니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Return Value

배열의 항목 수입니다.

### <a name="remarks"></a>설명

배열의 요소 수를 검색하려면 이 메서드를 호출합니다. 인덱스는 0을 기준으로 하므로 크기는 가장 큰 인덱스보다 1 큽니다. 이 메서드를 호출하면 [CArray:GetSize](#getsize) 메서드와 동일한 결과가 생성됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]

## <a name="carraygetdata"></a><a name="getdata"></a>CArray::GetData

이 멤버 함수를 사용하여 배열의 요소에 직접 액세스할 수 있습니다.

```
const TYPE* GetData() const;
TYPE* GetData();
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
배열 요소의 형식을 지정하는 템플릿 매개 변수입니다.

### <a name="return-value"></a>Return Value

배열 요소에 대한 포인터입니다.

### <a name="remarks"></a>설명

사용 가능한 요소가 `GetData` 없는 경우 null 값을 반환합니다.

배열의 요소에 직접 액세스하면 더 빠르게 작업할 수 있지만 `GetData`호출할 때 주의하십시오. 오류가 발생하면 배열의 요소에 직접 영향을 미칩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]

## <a name="carraygetsize"></a><a name="getsize"></a>배열 :: GetSize

배열의 크기를 반환합니다.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>설명

인덱스는 0을 기준으로 하므로 크기는 가장 큰 인덱스보다 1 큽니다. 이 메서드를 호출하면 [CArray::GetCount](#getcount) 메서드와 동일한 결과가 생성됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]

## <a name="carraygetupperbound"></a><a name="getupperbound"></a>CArray::GetUpper바운드

이 배열의 현재 상한을 반환합니다.

```
INT_PTR GetUpperBound() const;
```

### <a name="remarks"></a>설명

배열 인덱스는 0 기반이므로 이 함수는 값 `GetSize`1보다 작은 값을 반환합니다.

조건 `GetUpperBound( )` = -1은 배열에 요소가 포함되어 있지 없음을 나타냅니다.

### <a name="example"></a>예제

  [CArray::GetAt에](#getat)대한 예제를 참조하십시오.

## <a name="carrayinsertat"></a><a name="insertat"></a>배열::삽입

첫 번째 `InsertAt` 버전의 요소는 배열의 지정된 인덱스에 하나의 요소(또는 요소의 여러 복사본)를 삽입합니다.

```cpp
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CArray* pNewArray);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
`GetUpperBound`에서 반환되는 값보다 클 수 있는 정수 인덱스입니다.

*ARG_TYPE*<br/>
이 배열의 요소 유형을 지정하는 템플릿 매개 변수입니다.

*new엘리먼트*<br/>
이 배열에 배치할 요소입니다.

*nCount*<br/>
이 요소를 삽입해야 하는 횟수(기본값은 1)입니다.

*n스타트 인덱스*<br/>
[GetUpperBound](#getupperbound)에서 반환된 값보다 클 수 있는 정수 인덱스입니다.

*pNewArray*<br/>
이 배열에 추가할 요소를 포함하는 또 다른 배열입니다.

### <a name="remarks"></a>설명

이 과정에서 이 인덱스의 기존 요소를 증가시켜 위로 이동하고 위의 모든 요소를 위로 이동합니다.

두 번째 버전은 *nStartIndex* `CArray` 위치에서 시작하여 다른 컬렉션의 모든 요소를 삽입합니다.

반대로 `SetAt` 이 함수는 지정된 배열 요소 하나를 대체하며 요소를 이동하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]

## <a name="carrayisempty"></a><a name="isempty"></a>배열::비어 있음

배열이 비어 있는지 여부를 확인합니다.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Return Value

배열에 요소가 없는 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="carrayoperator-"></a><a name="operator_at"></a>CArray::연산자\[\]

이러한 하위 스크립트 연산자는 [SetAt](#setat) 및 [GetAt](#getat) 함수를 편리하게 대체할 수 있습니다.

```
TYPE& operator[](int_ptr nindex);
const TYPE& operator[](int_ptr nindex) const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
이 배열의 요소 유형을 지정하는 템플릿 매개 변수입니다.

*nIndex*<br/>
액세스할 요소의 인덱스입니다.

### <a name="remarks"></a>설명

**const가**아닌 배열에 대해 호출된 첫 번째 연산자는 할당 문의 오른쪽(r-value) 또는 왼쪽(l-값)에서 사용할 수 있습니다. **const** 배열에 대 한 호출 하는 두 번째, 오른쪽에만 사용할 수 있습니다.

라이브러리의 디버그 버전은 할당 문의 왼쪽 또는 오른쪽에 있는 하위 스크립트가 경계를 벗어난 경우 어설션합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]

## <a name="carrayrelocateelements"></a><a name="relocateelements"></a>CArray::재배치요소

배열이 증가하거나 축소될 때 데이터를 새 버퍼로 재배치합니다.

```
template<class TYPE, class ARG_TYPE>
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,
    const TYPE* pData,
    INT_PTR nCount);
```

### <a name="parameters"></a>매개 변수

*pNewData*<br/>
요소 배열에 대한 새 버퍼입니다.

*Pdata*<br/>
요소의 이전 배열입니다.

*nCount*<br/>
이전 배열의 요소 수입니다.

### <a name="remarks"></a>설명

*pNewData는* 항상 모든 *pData* 요소를 보유할 수 있을 만큼 충분히 큽잡입니다.

[CArray](../../mfc/reference/carray-class.md) 구현 [(SetSize](#setsize) 또는 [FreeExtra](#freeextra) 호출 될 때) 배열 이 성장 하거나 축소 해야 하는 경우 새 버퍼에 이전 데이터를 복사 하려면이 메서드를 사용 합니다. 기본 구현은 데이터를 복사합니다.

요소에 자체 멤버 중 하나에 대한 포인터가 포함되어 있거나 다른 구조체에 배열 요소 중 하나에 대한 포인터가 포함된 배열의 경우 포인터는 일반 복사본으로 업데이트되지 않습니다. 이 경우 관련 형식을 `RelocateElements` 사용하는 특수화를 구현하여 포인터를 수정할 수 있습니다. 또한 데이터 복사에 대한 책임도 있습니다.

## <a name="carrayremoveall"></a><a name="removeall"></a>배열 :: 모두 제거

이 배열의 모든 요소를 반환합니다.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>설명

배열이 이미 비어 있으면 함수가 계속 작동합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]

## <a name="carrayremoveat"></a><a name="removeat"></a>배열 :: 제거At

배열의 지정된 인덱스에서 시작하는 하나 이상의 요소를 제거합니다.

```cpp
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0보다 크거나 같고 [GetUpperBound에서](#getupperbound)반환된 값보다 크거나 같은 정수 인덱스입니다.

*nCount*<br/>
제거할 요소의 수입니다.

### <a name="remarks"></a>설명

이 과정에서 제거된 요소 위의 모든 요소가 아래로 이동합니다. 배열의 상한을 감소시키지만 메모리를 확보하지는 않습니다.

제거 지점 위의 배열에 포함된 것보다 더 많은 요소를 제거하려고 하면 라이브러리의 디버그 버전이 어설션됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]

## <a name="carraysetat"></a><a name="setat"></a>CArray::SetAt

지정된 인덱스에서 배열 요소를 설정합니다.

```cpp
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0보다 크거나 같고 [GetUpperBound에서](#getupperbound)반환된 값보다 크거나 같은 정수 인덱스입니다.

*ARG_TYPE*<br/>
배열 요소를 참조하는 데 사용되는 인수 유형을 지정하는 템플릿 매개 변수입니다.

*new엘리먼트*<br/>
지정된 위치에 저장할 새 요소 값입니다.

### <a name="remarks"></a>설명

`SetAt`배열이 증가하지 않습니다. 배열이 자동으로 증가하려면 [SetAtGrow를](#setatgrow) 사용합니다.

인덱스 값이 배열에서 유효한 위치를 나타내는지 확인해야 합니다. 범위를 벗어난 경우 라이브러리의 디버그 버전이 어설션됩니다.

### <a name="example"></a>예제

  [GetAt](#getat)에 대한 예제를 참조하십시오.

## <a name="carraysetatgrow"></a><a name="setatgrow"></a>CArray:::세터그로우

지정된 인덱스에서 배열 요소를 설정합니다.

```cpp
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0보다 크거나 같은 정수 인덱스입니다.

*ARG_TYPE*<br/>
배열의 요소 유형을 지정하는 템플릿 매개 변수입니다.

*new엘리먼트*<br/>
이 배열에 추가할 요소입니다. NULL 값이 허용됩니다.

### <a name="remarks"></a>설명

필요한 경우 배열이 자동으로 증가합니다(즉, 상한은 새 요소를 수용하도록 조정됩니다).

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]

## <a name="carraysetsize"></a><a name="setsize"></a>배열 :: 세트 크기

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

새 크기가 이전 크기보다 작으면 배열이 잘리고 사용되지 않는 모든 메모리가 해제됩니다.

이 함수를 사용하여 배열 사용을 시작하기 전에 배열 크기를 설정합니다. `SetSize`를 사용하지 않는 경우 배열에 요소를 추가하면 배열이 자주 다시 할당되고 복사됩니다. 이처럼 다시 할당 및 복사가 자주 수행되면 효율성이 떨어지며 메모리가 조각화될 수 있습니다.

*nGrowBy* 매개 변수는 배열이 증가하는 동안 내부 메모리 할당에 영향을 줍니다. GetSize 및 [GetUpperBound에서](#getupperbound) [GetSize](#getsize) 보고한 배열 크기에 는 영향을 미치지 않습니다. 기본값을 사용하는 경우 MFC는 메모리 조각화를 방지하고 대부분의 경우 효율성을 최적화하기 위해 계산된 방식으로 메모리를 할당합니다.

### <a name="example"></a>예제

  [GetData](#getdata)에 대한 예제를 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CObArray 클래스](../../mfc/reference/cobarray-class.md)<br/>
[컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md)
