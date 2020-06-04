---
title: CTypedPtrArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrArray
- AFXTEMPL/CTypedPtrArray
- AFXTEMPL/CTypedPtrArray::Add
- AFXTEMPL/CTypedPtrArray::Append
- AFXTEMPL/CTypedPtrArray::Copy
- AFXTEMPL/CTypedPtrArray::ElementAt
- AFXTEMPL/CTypedPtrArray::GetAt
- AFXTEMPL/CTypedPtrArray::InsertAt
- AFXTEMPL/CTypedPtrArray::SetAt
- AFXTEMPL/CTypedPtrArray::SetAtGrow
helpviewer_keywords:
- CTypedPtrArray [MFC], Add
- CTypedPtrArray [MFC], Append
- CTypedPtrArray [MFC], Copy
- CTypedPtrArray [MFC], ElementAt
- CTypedPtrArray [MFC], GetAt
- CTypedPtrArray [MFC], InsertAt
- CTypedPtrArray [MFC], SetAt
- CTypedPtrArray [MFC], SetAtGrow
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
ms.openlocfilehash: 20cf147e955b6b19919f35750b0f46a8b5a67ad0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752067"
---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray 클래스

`CPtrArray` 또는 `CObArray`클래스의 개체에 대해 형식 안전 "래퍼"를 제공합니다.

## <a name="syntax"></a>구문

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrArray : public BASE_CLASS
```

#### <a name="parameters"></a>매개 변수

*BASE_CLASS*<br/>
형식이 입력된 포인터 배열 클래스의 기본 클래스입니다. 배열 `CObArray` 클래스(또는)여야 `CPtrArray`합니다.

*유형*<br/>
기본 클래스 배열에 저장된 요소의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CTypedPtr배열::추가](#add)|배열의 끝에 새 요소를 추가합니다. 필요한 경우 배열을 증가시면 됩니다.|
|[CTypedPtr배열::부속](#append)|한 배열의 내용을 다른 배열의 끝에 추가합니다. 필요한 경우 배열을 증가시면 됩니다.|
|[CTypedPtr배열::복사](#copy)|배열에 다른 배열을 복사하고 필요하면 배열을 확장합니다.|
|[CTypedPtr배열::엘리먼트At](#elementat)|배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.|
|[CTypedPtr배열::GetAt](#getat)|지정된 인덱스의 값을 반환합니다.|
|[CTypedPtr배열::삽입](#insertat)|지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.|
|[CTypedPtr배열::SetAt](#setat)|지정된 인덱스의 값을 설정합니다. 배열은 확장할 수 없습니다.|
|[CTypedPtr배열::세터그로우](#setatgrow)|지정된 인덱스의 값을 설정합니다. 필요한 경우 배열을 확장합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CTypedPtr배열::연산자 \[\]](#operator_at)|지정한 인덱스에 있는 요소를 설정하거나 가져옵니다.|

## <a name="remarks"></a>설명

C++ `CTypedPtrArray` 형식 `CPtrArray` `CObArray`검사 기능이 아닌 Or를 사용하는 경우 일치하지 않는 포인터 유형으로 인한 오류를 제거하는 데 도움이 됩니다.

또한 래퍼는 `CTypedPtrArray` 사용하거나 `CObArray` `CPtrArray`에 필요한 많은 주조를 수행합니다.

모든 `CTypedPtrArray` 함수가 인라인이기 때문에 이 템플릿을 사용하면 코드의 크기 나 속도에 큰 영향을 미치지 않습니다.

사용에 `CTypedPtrArray`대한 자세한 내용은 [문서 컬렉션](../../mfc/collections.md) 및 템플릿 기반 [클래스를](../../mfc/template-based-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`BASE_CLASS`

`CTypedPtrArray`

## <a name="requirements"></a>요구 사항

**헤더:** afxtempl.h

## <a name="ctypedptrarrayadd"></a><a name="add"></a>CTypedPtr배열::추가

이 멤버 `BASE_CLASS`함수는 **::Add**를 호출합니다.

```
INT_PTR Add(TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
배열에 추가할 요소 유형을 지정하는 템플릿 매개 변수입니다.

*new엘리먼트*<br/>
이 배열에 추가할 요소입니다.

### <a name="return-value"></a>Return Value

추가된 요소의 인덱스입니다.

### <a name="remarks"></a>설명

자세한 설명은 [CObArray::Add](../../mfc/reference/cobarray-class.md#add)를 참조하십시오.

## <a name="ctypedptrarrayappend"></a><a name="append"></a>CTypedPtr배열::부속

이 멤버 `BASE_CLASS`함수는 ::Aend**를 호출합니다.

```
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>매개 변수

*BASE_CLASS*<br/>
형식이 입력된 포인터 배열 클래스의 기본 클래스입니다. 배열 클래스여야 [합니다(CObArray](../../mfc/reference/cobarray-class.md) 또는 [CPtrArray).](../../mfc/reference/cptrarray-class.md)

*유형*<br/>
기본 클래스 배열에 저장된 요소의 형식입니다.

*src*<br/>
배열에 추가할 요소의 소스입니다.

### <a name="return-value"></a>Return Value

첫 번째 추가된 요소의 인덱스입니다.

### <a name="remarks"></a>설명

자세한 설명은 [CObArray::추가](../../mfc/reference/cobarray-class.md#append)를 참조하십시오.

## <a name="ctypedptrarraycopy"></a><a name="copy"></a>CTypedPtr배열::복사

이 멤버 `BASE_CLASS`함수는 **::Copy**를 호출합니다.

```cpp
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>매개 변수

*BASE_CLASS*<br/>
형식이 입력된 포인터 배열 클래스의 기본 클래스입니다. 배열 클래스여야 [합니다(CObArray](../../mfc/reference/cobarray-class.md) 또는 [CPtrArray).](../../mfc/reference/cptrarray-class.md)

*유형*<br/>
기본 클래스 배열에 저장된 요소의 형식입니다.

*src*<br/>
배열에 복사할 요소의 소스입니다.

### <a name="remarks"></a>설명

자세한 설명은 [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)를 참조하십시오.

## <a name="ctypedptrarrayelementat"></a><a name="elementat"></a>CTypedPtr배열::엘리먼트At

이 인라인 `BASE_CLASS`함수는 **::ElementAt**.

```
TYPE& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
이 배열에 저장된 요소의 형식을 지정하는 템플릿 매개 변수입니다.

*nIndex*<br/>
0보다 크거나 같고 `BASE_CLASS` **::GetUpperBound에서**반환되는 값보다 크거나 같을 수 있는 정수 인덱스입니다.

### <a name="return-value"></a>Return Value

*nIndex*. 이 요소는 템플릿 매개 변수 *TYPE에*의해 지정된 형식입니다.

### <a name="remarks"></a>설명

더 자세한 설명은 [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)를 참조하십시오.

## <a name="ctypedptrarraygetat"></a><a name="getat"></a>CTypedPtr배열::GetAt

이 인라인 `BASE_CLASS`함수는 **::GetAt 를 호출합니다.**

```
TYPE GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
배열에 저장된 요소의 유형을 지정하는 템플릿 매개 변수입니다.

*nIndex*<br/>
0보다 크거나 같고 `BASE_CLASS` **::GetUpperBound에서**반환되는 값보다 크거나 같을 수 있는 정수 인덱스입니다.

### <a name="return-value"></a>Return Value

*nIndex*. 이 요소는 템플릿 매개 변수 *TYPE에*의해 지정된 형식입니다.

### <a name="remarks"></a>설명

더 자세한 설명은 [CObArray::GetAt를](../../mfc/reference/cobarray-class.md#getat) 참조하십시오.

## <a name="ctypedptrarrayinsertat"></a><a name="insertat"></a>CTypedPtr배열::삽입

이 멤버 `BASE_CLASS`함수는 **::InsertAt 를 호출합니다.**

```cpp
void InsertAt(
    INT_PTR nIndex,
    TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[CObArray:GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)에서 반환하는 값보다 클 수 있는 정수 인덱스입니다.

*유형*<br/>
기본 클래스 배열에 저장된 요소의 형식입니다.

*new엘리먼트*<br/>
이 배열에 배치할 개체 포인터입니다. *newValue* **NULL의** 요소가 허용됩니다.

*nCount*<br/>
이 요소를 삽입해야 하는 횟수(기본값은 1)입니다.

*n스타트 인덱스*<br/>
`CObArray::GetUpperBound`에서 반환되는 값보다 클 수 있는 정수 인덱스입니다.

*BASE_CLASS*<br/>
형식이 입력된 포인터 배열 클래스의 기본 클래스입니다. 배열 클래스여야 [합니다(CObArray](../../mfc/reference/cobarray-class.md) 또는 [CPtrArray).](../../mfc/reference/cptrarray-class.md)

*pNewArray*<br/>
이 배열에 추가할 요소를 포함하는 또 다른 배열입니다.

### <a name="remarks"></a>설명

자세한 설명은 [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)를 참조하십시오.

## <a name="ctypedptrarrayoperator--"></a><a name="operator_at"></a>CTypedPtrArray::연산자 [

이러한 인라인 연산자는 `BASE_CLASS` **::연산자 [] 를**호출합니다.

```
TYPE& operator[ ](int_ptr nindex);
TYPE operator[ ](int_ptr nindex) const;
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
배열에 저장된 요소의 유형을 지정하는 템플릿 매개 변수입니다.

*nIndex*<br/>
0보다 크거나 같고 `BASE_CLASS` **::GetUpperBound에서**반환되는 값보다 크거나 같을 수 있는 정수 인덱스입니다.

### <a name="remarks"></a>설명

**const가**아닌 배열에 대해 호출된 첫 번째 연산자는 할당 문의 오른쪽(r-value) 또는 왼쪽(l-값)에서 사용할 수 있습니다. **const** 배열에 대해 호출된 두 번째 배열은 오른쪽에서만 사용할 수 있습니다.

라이브러리의 디버그 버전은 할당 문의 왼쪽 또는 오른쪽에 있는 하위 스크립트가 경계를 벗어난 경우 어설션합니다.

## <a name="ctypedptrarraysetat"></a><a name="setat"></a>CTypedPtr배열::SetAt

이 멤버 `BASE_CLASS`함수는 **::SetAt 를 호출합니다.**

```cpp
void SetAt(
    INT_PTR nIndex,
    TYPE ptr);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0보다 크거나 같고 [CObArray::GetUpperBound에서](../../mfc/reference/cobarray-class.md#getupperbound)반환된 값보다 크거나 같을 수 있는 정수 인덱스입니다.

*유형*<br/>
기본 클래스 배열에 저장된 요소의 형식입니다.

*Ptr*<br/>
nIndex의 배열에 삽입할 요소에 대한 포인터입니다. NULL 값이 허용됩니다.

### <a name="remarks"></a>설명

더 자세한 설명은 [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)를 참조하십시오.

## <a name="ctypedptrarraysetatgrow"></a><a name="setatgrow"></a>CTypedPtr배열::세터그로우

이 멤버 `BASE_CLASS`함수는 **::SetAtGrow**를 호출합니다.

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0보다 크거나 같은 정수 인덱스입니다.

*유형*<br/>
기본 클래스 배열에 저장된 요소의 형식입니다.

*new엘리먼트*<br/>
이 배열에 추가할 개체 포인터입니다. **NULL** 값이 허용됩니다.

### <a name="remarks"></a>설명

더 자세한 설명은 [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)를 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CPtrArray 클래스](../../mfc/reference/cptrarray-class.md)<br/>
[CObArray 클래스](../../mfc/reference/cobarray-class.md)
