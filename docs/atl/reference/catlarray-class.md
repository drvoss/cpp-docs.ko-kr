---
title: 카틀어레이어리 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlArray
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Add
- ATLCOLL/ATL::Append
- ATLCOLL/ATL::AssertValid
- ATLCOLL/ATL::Copy
- ATLCOLL/ATL::FreeExtra
- ATLCOLL/ATL::GetAt
- ATLCOLL/ATL::GetCount
- ATLCOLL/ATL::GetData
- ATLCOLL/ATL::InsertArrayAt
- ATLCOLL/ATL::InsertAt
- ATLCOLL/ATL::IsEmpty
- ATLCOLL/ATL::RemoveAll
- ATLCOLL/ATL::RemoveAt
- ATLCOLL/ATL::SetAt
- ATLCOLL/ATL::SetAtGrow
- ATLCOLL/ATL::SetCount
- ATLCOLL/ATL::INARGTYPE
- ATLCOLL/ATL::OUTARGTYPE
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
ms.openlocfilehash: 85168af654d3d63e06559486b464938b7fd90ad3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321569"
---
# <a name="catlarray-class"></a>카틀어레이어리 클래스

이 클래스는 배열 개체를 구현합니다.

## <a name="syntax"></a>구문

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```

#### <a name="parameters"></a>매개 변수

*전자*<br/>
배열에 저장할 데이터의 형식입니다.

*에트해협*<br/>
요소를 복사하거나 이동하는 데 사용되는 코드입니다.

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[추가](#add)|배열 개체에 요소를 추가 하려면이 메서드를 호출 합니다.|
|[추가](#append)|이 메서드를 호출하여 한 배열의 내용을 다른 배열의 끝에 추가합니다.|
|[어설션 유효](#assertvalid)|이 메서드를 호출하여 배열 개체가 유효한지 확인합니다.|
|[CAtlArray](#catlarray)|생성자입니다.|
|[~카틀어레이레이](#dtor)|소멸자입니다.|
|[복사](#copy)|한 배열의 요소를 다른 배열로 복사하려면 이 메서드를 호출합니다.|
|[무료 엑스트라](#freeextra)|배열에서 빈 요소를 제거 하려면이 메서드를 호출 합니다.|
|[Getat](#getat)|이 메서드를 호출하여 배열 개체에서 단일 요소를 검색합니다.|
|[GetCount](#getcount)|배열에 저장된 요소 수를 반환하려면 이 메서드를 호출합니다.|
|[GetData](#getdata)|이 메서드를 호출하여 배열의 첫 번째 요소에 대한 포인터를 반환합니다.|
|[삽입배열At](#insertarrayat)|한 배열을 다른 배열에 삽입하려면 이 메서드를 호출합니다.|
|[삽입](#insertat)|이 메서드를 호출하여 새 요소(또는 요소의 여러 복사본)를 배열 개체에 삽입합니다.|
|[IsEmpty](#isempty)|배열이 비어 있는지 테스트하려면 이 메서드를 호출합니다.|
|[Removeall](#removeall)|배열 개체에서 모든 요소를 제거 하려면이 메서드를 호출 합니다.|
|[RemoveAt](#removeat)|배열에서 하나 이상의 요소를 제거 하려면이 메서드를 호출 합니다.|
|[셋 앳](#setat)|배열 개체에서 요소의 값을 설정 하려면이 메서드를 호출 합니다.|
|[세타그로우](#setatgrow)|이 메서드를 호출하여 배열 개체에서 요소의 값을 설정하고 필요에 따라 배열을 확장합니다.|
|[세트 카운트](#setcount)|배열 개체의 크기를 설정 하려면이 메서드를 호출 합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 &#91;&#93;](#operator_at)|이 연산자호출하여 배열의 요소에 대한 참조를 반환합니다.|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[INARGTYPE](#inargtype)|배열에 요소를 추가하는 데 사용할 데이터 형식입니다.|
|[외형](#outargtype)|배열에서 요소를 검색하는 데 사용할 데이터 형식입니다.|

## <a name="remarks"></a>설명

`CAtlArray`는 사용자 정의 형식의 요소 배열을 만들고 관리하는 메서드를 제공합니다. 표준 C 배열과 유사하지만 `CAtlArray` 개체는 필요에 따라 동적으로 축소되고 증가할 수 있습니다. 배열 인덱스는 항상 위치 0에서 시작하며 상한은 고정되거나 새 요소가 추가될 때 확장될 수 있습니다.

소수의 요소가 있는 배열의 경우 ATL 클래스 [CSimpleArray를](../../atl/reference/csimplearray-class.md) 사용할 수 있습니다.

`CAtlArray`MFC의 `CArray` 클래스와 밀접한 관련이 있으며 직렬화 지원없이 MFC 프로젝트에서 작동합니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="catlarrayadd"></a><a name="add"></a>카틀어레이어레이::추가

배열 개체에 요소를 추가 하려면이 메서드를 호출 합니다.

```
size_t Add(INARGTYPE element);
size_t Add();
```

### <a name="parameters"></a>매개 변수

*요소*<br/>
배열에 추가할 요소입니다.

### <a name="return-value"></a>Return Value

추가된 요소의 인덱스를 반환합니다.

### <a name="remarks"></a>설명

새 요소가 배열의 끝에 추가됩니다. 요소가 제공되지 않으면 빈 요소가 추가됩니다. 즉, 실제 요소가 추가된 것처럼 배열의 크기가 증가합니다. 작업이 실패하면 [atlThrow은](debugging-and-error-reporting-global-functions.md#atlthrow) 인수 E_OUTOFMEMORY 호출됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]

## <a name="catlarrayappend"></a><a name="append"></a>카틀어레이어레이::부속

이 메서드를 호출하여 한 배열의 내용을 다른 배열의 끝에 추가합니다.

```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>매개 변수

*aSrc*<br/>
어플할 배열입니다.

### <a name="return-value"></a>Return Value

첫 번째 추가된 요소의 인덱스를 반환합니다.

### <a name="remarks"></a>설명

제공된 배열의 요소가 기존 배열의 끝에 추가됩니다. 필요한 경우 새 요소를 수용하기 위해 메모리가 할당됩니다.

배열은 동일한 형식이어야 하며 배열을 자체에 추가할 수 없습니다.

디버그 빌드에서 `CAtlArray` 인수가 유효한 배열이 아니거나 *aSrc가* 동일한 개체를 참조하는 경우 ATLASSERT가 발생합니다. 릴리스 빌드에서 잘못된 인수는 예측할 수 없는 동작으로 이어질 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]

## <a name="catlarrayassertvalid"></a><a name="assertvalid"></a>카틀어레이레이::어설션 유효

이 메서드를 호출하여 배열 개체가 유효한지 확인합니다.

```
void AssertValid() const;
```

### <a name="remarks"></a>설명

배열 개체가 유효하지 않으면 ATLASSERT가 어설션을 throw합니다. 이 메서드는 _DEBUG 정의된 경우에만 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]

## <a name="catlarraycatlarray"></a><a name="catlarray"></a>카틀어레이레이::카틀어레이레이

생성자입니다.

```
CAtlArray() throw();
```

### <a name="remarks"></a>설명

배열 개체를 초기화합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]

## <a name="catlarraycatlarray"></a><a name="dtor"></a>카틀어레이어리::~카틀어레이레이

소멸자입니다.

```
~CAtlArray() throw();
```

### <a name="remarks"></a>설명

배열 개체에서 사용되는 리소스를 해제합니다.

## <a name="catlarraycopy"></a><a name="copy"></a>카틀어레이어이치::복사

한 배열의 요소를 다른 배열로 복사하려면 이 메서드를 호출합니다.

```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>매개 변수

*aSrc*<br/>
배열에 복사할 요소의 소스입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 한 배열의 요소를 다른 배열의 요소로 덮어씁니다. 필요한 경우 새 요소를 수용하기 위해 메모리가 할당됩니다. 배열의 요소를 자체적으로 복사할 수 없습니다.

배열의 기존 내용을 유지하려면 [대신 CAtlArray::Aend를](#append) 사용합니다.

디버그 빌드에서 기존 `CAtlArray` 개체가 유효하지 않거나 *aSrc가* 동일한 개체를 참조하는 경우 ATLASSERT가 발생합니다. 릴리스 빌드에서 잘못된 인수는 예측할 수 없는 동작으로 이어질 수 있습니다.

> [!NOTE]
> `CAtlArray::Copy`[CAutoPtr](../../atl/reference/cautoptr-class.md) 클래스로 만든 요소로 구성된 배열은 지원하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]

## <a name="catlarrayfreeextra"></a><a name="freeextra"></a>카틀어레이레이::프리엑스트라

배열에서 빈 요소를 제거 하려면이 메서드를 호출 합니다.

```
void FreeExtra() throw();
```

### <a name="remarks"></a>설명

빈 요소는 제거되지만 배열의 크기와 상한은 변경되지 않습니다.

디버그 빌드에서 CAtlArray 개체가 유효하지 않거나 배열이 최대 크기를 초과하는 경우 ATLASSERT가 발생합니다.

## <a name="catlarraygetat"></a><a name="getat"></a>카틀어레이레이::겟앳

이 메서드를 호출하여 배열 개체에서 단일 요소를 검색합니다.

```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```

### <a name="parameters"></a>매개 변수

*아이 엘리먼트*<br/>
반환할 배열 요소의 인덱스 값입니다.

### <a name="return-value"></a>Return Value

필요한 배열 요소에 대한 참조를 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 *iElement가* 배열의 요소 수를 초과하면 ATLASSERT가 발생합니다. 릴리스 빌드에서 잘못된 인수로 인해 예기치 않은 동작이 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]

## <a name="catlarraygetcount"></a><a name="getcount"></a>카틀어레이레이::겟카운트

배열에 저장된 요소 수를 반환하려면 이 메서드를 호출합니다.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Return Value

배열에 저장된 요소 수를 반환합니다.

### <a name="remarks"></a>설명

배열의 첫 번째 요소가 위치 0에 있기 `GetCount` 때문에 반환되는 값은 항상 가장 큰 인덱스보다 1 큽입니다.

### <a name="example"></a>예제

[CAtlArray::GetAt에](#getat)대한 예제를 참조하십시오.

## <a name="catlarraygetdata"></a><a name="getdata"></a>카틀어레이어레이::겟데이터

이 메서드를 호출하여 배열의 첫 번째 요소에 대한 포인터를 반환합니다.

```
E* GetData() throw();
const E* GetData() const throw();
```

### <a name="return-value"></a>Return Value

배열에 첫 번째 요소를 저장하는 메모리 위치에 대한 포인터를 반환합니다. 사용 가능한 요소가 없는 경우 NULL이 반환됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]

## <a name="catlarrayinargtype"></a><a name="inargtype"></a>카틀어레이레이::이나르그타입

배열에 요소를 추가하는 데 사용할 데이터 형식입니다.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

## <a name="catlarrayinsertarrayat"></a><a name="insertarrayat"></a>카틀어레이어레이::인서트어레이어

한 배열을 다른 배열에 삽입하려면 이 메서드를 호출합니다.

```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```

### <a name="parameters"></a>매개 변수

*iStart*<br/>
배열을 삽입할 인덱스입니다.

*파뉴*<br/>
삽입할 배열입니다.

### <a name="remarks"></a>설명

배열 *paNew의* 요소는 요소 *iStart에서*시작하여 배열 개체에 복사됩니다. 덮어쓰지 않도록 기존 배열 요소가 이동됩니다.

디버그 빌드에서 `CAtlArray` 개체가 유효하지 않거나 *paNew* 포인터가 NULL또는 유효하지 않은 경우 ATLASSERT가 발생합니다.

> [!NOTE]
> `CAtlArray::InsertArrayAt`[CAutoPtr](../../atl/reference/cautoptr-class.md) 클래스로 만든 요소로 구성된 배열은 지원하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]

## <a name="catlarrayinsertat"></a><a name="insertat"></a>카틀어레이어레이::삽입

이 메서드를 호출하여 새 요소(또는 요소의 여러 복사본)를 배열 개체에 삽입합니다.

```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```

### <a name="parameters"></a>매개 변수

*아이 엘리먼트*<br/>
요소 또는 요소를 삽입할 인덱스입니다.

*요소*<br/>
삽입할 요소 또는 요소의 값입니다.

*nCount*<br/>
추가할 요소의 수입니다.

### <a name="remarks"></a>설명

인덱스 *iElement에서*시작하여 하나 이상의 요소를 배열에 삽입합니다. 덮어쓰지 않도록 기존 요소가 이동됩니다.

디버그 빌드에서 `CAtlArray` 개체가 유효하지 않거나, 추가할 요소 수가 0이거나, 배열이 포함하기에 너무 큰 요소 수가 너무 큰 경우 ATLASSERT가 발생합니다. 소매 빌드에서 잘못된 매개 변수를 전달하면 예기치 않은 결과가 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]

## <a name="catlarrayisempty"></a><a name="isempty"></a>카틀어레이어레이::비어 있음

배열이 비어 있는지 테스트하려면 이 메서드를 호출합니다.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Return Value

배열이 비어 있는 경우 true를 반환합니다.

### <a name="remarks"></a>설명

배열에 요소가 없는 경우 비어 있다고 합니다. 따라서 배열에 빈 요소가 포함되어 있더라도 비어 있지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]

## <a name="catlarrayoperator-"></a><a name="operator_at"></a>CAtlArray::연산자 []

이 연산자호출하여 배열의 요소에 대한 참조를 반환합니다.

```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```

### <a name="parameters"></a>매개 변수

*아이 엘리먼트*<br/>
반환할 배열 요소의 인덱스 값입니다.

### <a name="return-value"></a>Return Value

필요한 배열 요소에 대한 참조를 반환합니다.

### <a name="remarks"></a>설명

[CAtlArray::GetAt와](#getat)유사한 기능을 수행합니다. MFC 클래스 [CArray와](../../mfc/reference/carray-class.md)달리 이 연산자는 [CAtlArray::SetAt](#setat)를 대신사용할 수 없습니다.

디버그 빌드에서 *iElement가* 배열의 총 요소 수를 초과하면 ATLASSERT가 발생합니다. 소매 빌드에서 잘못된 매개 변수로 인해 예기치 않은 결과가 발생할 수 있습니다.

## <a name="catlarrayoutargtype"></a><a name="outargtype"></a>카틀어레이레이::아웃라그타입

배열에서 요소를 검색하는 데 사용할 데이터 형식입니다.

```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```

## <a name="catlarrayremoveall"></a><a name="removeall"></a>카틀어레이레이::모두 제거

배열 개체에서 모든 요소를 제거 하려면이 메서드를 호출 합니다.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>설명

배열 개체에서 모든 요소를 제거합니다.

이 메서드는 [CAtlArray::SetCount를](#setcount) 호출하여 배열의 크기를 조정하고 이후에 할당된 메모리를 해제합니다.

### <a name="example"></a>예제

[CAtlArray::IsEmpty](#isempty)에 대한 예제를 참조하십시오.

## <a name="catlarrayremoveat"></a><a name="removeat"></a>카틀어레이레이::리무트앳

배열에서 하나 이상의 요소를 제거 하려면이 메서드를 호출 합니다.

```
void RemoveAt(size_t iElement, size_t nCount = 1);
```

### <a name="parameters"></a>매개 변수

*아이 엘리먼트*<br/>
제거할 첫 번째 요소의 인덱스입니다.

*nCount*<br/>
제거할 요소의 수입니다.

### <a name="remarks"></a>설명

배열에서 하나 이상의 요소를 제거합니다. 나머지 요소는 아래로 이동됩니다. 상한은 감소되지만 [CAtlArray::FreeExtra를](#freeextra) 호출할 때까지 메모리가 해제되지 않습니다.

디버그 빌드에서 `CAtlArray` 개체가 유효하지 않거나 *iElement* 및 *nCount의* 결합된 합계가 배열의 총 요소 수를 초과하는 경우 ATLASSERT가 발생합니다. 소매 빌드에서 잘못된 매개 변수로 인해 예기치 않은 결과가 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]

## <a name="catlarraysetat"></a><a name="setat"></a>카틀어레이레이::세팅

배열 개체에서 요소의 값을 설정 하려면이 메서드를 호출 합니다.

```
void SetAt(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>매개 변수

*아이 엘리먼트*<br/>
설정할 배열 요소를 가리키는 인덱스입니다.

*요소*<br/>
지정된 요소의 새 값입니다.

### <a name="remarks"></a>설명

디버그 빌드에서 *iElement가* 배열의 요소 수를 초과하면 ATLASSERT가 발생합니다. 소매 빌드에서 잘못된 매개 변수로 인해 예기치 않은 결과가 발생할 수 있습니다.

### <a name="example"></a>예제

[CAtlArray::GetAt에](#getat)대한 예제를 참조하십시오.

## <a name="catlarraysetcount"></a><a name="setcount"></a>카틀어레이어이치::셋카운트

배열 개체의 크기를 설정 하려면이 메서드를 호출 합니다.

```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```

### <a name="parameters"></a>매개 변수

*nNewSize*<br/>
배열의 필요한 크기입니다.

*nGrowBy*<br/>
버퍼를 만드는 큰 값을 결정하는 데 사용되는 값입니다. 값이 -1이면 내부적으로 계산된 값이 사용됩니다.

### <a name="return-value"></a>Return Value

배열의 크기가 성공적으로 조정된 경우 true를 반환합니다.

### <a name="remarks"></a>설명

배열의 크기를 늘리거나 줄수 있습니다. 증가하면 추가 빈 요소가 배열에 추가됩니다. 감소하면 가장 큰 인덱스를 가진 요소가 삭제되고 메모리가 해제됩니다.

이 메서드를 사용 하 여 배열을 사용 하기 전에 배열의 크기를 설정 합니다. 사용하지 `SetCount` 않으면 요소를 추가하는 프로세스와 후속 메모리 할당이 수행되면 성능과 조각 메모리가 줄어듭니다.

### <a name="example"></a>예제

[CAtlArray::GetData](#getdata)에 대한 예제를 참조하십시오.

## <a name="catlarraysetatgrow"></a><a name="setatgrow"></a>카틀어레이::세터그로우

이 메서드를 호출하여 배열 개체에서 요소의 값을 설정하고 필요에 따라 배열을 확장합니다.

```
void SetAtGrow(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>매개 변수

*아이 엘리먼트*<br/>
설정할 배열 요소를 가리키는 인덱스입니다.

*요소*<br/>
지정된 요소의 새 값입니다.

### <a name="remarks"></a>설명

인덱스가 가리키는 요소의 값을 대체합니다. *iElement가* 배열의 현재 크기보다 크면 [CAtlArray::SetCount](#setcount)에 대한 호출을 사용하여 배열이 자동으로 증가합니다. 디버그 빌드에서 개체가 유효하지 않은 경우 `CAtlArray` ATLASSERT가 발생합니다. 소매 빌드에서 잘못된 매개 변수로 인해 예기치 않은 결과가 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]

## <a name="see-also"></a>참고 항목

[MMXSwarm 샘플](../../overview/visual-cpp-samples.md)<br/>
[동적 소비자 샘플](../../overview/visual-cpp-samples.md)<br/>
[업데이트PV 샘플](../../overview/visual-cpp-samples.md)<br/>
[선택 윤곽 샘플](../../overview/visual-cpp-samples.md)<br/>
[CArray 클래스](../../mfc/reference/carray-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
