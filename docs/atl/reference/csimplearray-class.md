---
title: CSimpleArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
ms.openlocfilehash: d3386687757412d09e4df29e84f691f1615c472a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746479"
---
# <a name="csimplearray-class"></a>CSimpleArray 클래스

이 클래스는 간단한 배열을 관리하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>
class CSimpleArray
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
배열에 저장할 데이터 유형입니다.

*TEqual*<br/>
특성 개체, 형식 *T의*요소에 대 한 같음 테스트를 정의 합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C심플어레이::C심플레이어](#csimplearray)|단순 배열의 생성자입니다.|
|[CSimpleArray::~CSimpleArray](#dtor)|단순 배열에 대한 소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C심플어레이::추가](#add)|배열에 새 요소를 추가합니다.|
|[C심플어레이::찾기](#find)|배열에서 요소를 찾습니다.|
|[C심플레이레이::겟데이터](#getdata)|배열에 저장된 데이터에 대한 포인터를 반환합니다.|
|[C심플어레이::겟사이즈](#getsize)|배열에 저장된 요소 수를 반환합니다.|
|[C심플어레이::제거](#remove)|배열에서 지정된 요소를 제거합니다.|
|[C심플어레이::모두 제거](#removeall)|배열에서 모든 요소를 제거합니다.|
|[C심플어레이::리무트](#removeat)|배열에서 지정된 요소를 제거합니다.|
|[C심플이어레이::세타인덱스](#setatindex)|배열에서 지정된 요소를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CSimpleArray::operator\[\]](#operator_at)|배열에서 요소를 검색합니다.|
|[C심플이어레이::연산자 =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

`CSimpleArray`지정된 형식의 `T`간단한 배열을 만들고 관리하는 메서드를 제공합니다.

매개 `TEqual` 변수는 형식의 `T`두 요소에 대한 같음 함수를 정의하는 수단을 제공합니다. [CSimpleArrayEqualHelp도우미와](../../atl/reference/csimplearrayequalhelper-class.md)유사한 클래스를 만들어 지정된 배열에 대한 같음 테스트의 동작을 변경할 수 있습니다. 예를 들어 포인터 배열을 처리할 때 포인터참조 값에 따라 같음을 정의하는 것이 유용할 수 있습니다. 기본 구현은 **operator=()를**사용합니다.

둘 `CSimpleArray` 다 [소수의](../../atl/reference/csimplemap-class.md) 요소에 대 한 설계 되었습니다. 배열에 많은 수의 요소가 포함되어 있는 경우 [CAtlArray](../../atl/reference/catlarray-class.md) 및 [CAtlMap을](../../atl/reference/catlmap-class.md) 사용해야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 아시프콜.h

## <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]

## <a name="csimplearrayadd"></a><a name="add"></a>C심플어레이::추가

배열에 새 요소를 추가합니다.

```
BOOL Add(const T& t);
```

### <a name="parameters"></a>매개 변수

*t*<br/>
배열에 추가할 요소입니다.

### <a name="return-value"></a>Return Value

요소가 배열에 성공적으로 추가된 경우 TRUE를 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]

## <a name="csimplearraycsimplearray"></a><a name="csimplearray"></a>C심플어레이::C심플레이어

배열 개체의 생성자입니다.

```
CSimpleArray(const CSimpleArray<T, TEqual>& src);
CSimpleArray();
```

### <a name="parameters"></a>매개 변수

*src*<br/>
기존 `CSimpleArray` 개체입니다.

### <a name="remarks"></a>설명

데이터 멤버를 초기화하여 새 `CSimpleArray` 빈 개체 또는 기존 `CSimpleArray` 개체의 복사본을 만듭니다.

## <a name="csimplearraycsimplearray"></a><a name="dtor"></a>CSimpleArray::~CSimpleArray

소멸자입니다.

```
~CSimpleArray();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제합니다.

## <a name="csimplearrayfind"></a><a name="find"></a>C심플어레이::찾기

배열에서 요소를 찾습니다.

```
int Find(const T& t) const;
```

### <a name="parameters"></a>매개 변수

*t*<br/>
검색할 요소입니다.

### <a name="return-value"></a>Return Value

요소를 찾을 수 없는 경우 found 요소또는 -1의 인덱스를 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]

## <a name="csimplearraygetdata"></a><a name="getdata"></a>C심플레이레이::겟데이터

배열에 저장된 데이터에 대한 포인터를 반환합니다.

```
T* GetData() const;
```

### <a name="return-value"></a>Return Value

배열의 데이터에 대한 포인터를 반환합니다.

## <a name="csimplearraygetsize"></a><a name="getsize"></a>C심플어레이::겟사이즈

배열에 저장된 요소 수를 반환합니다.

```
int GetSize() const;
```

### <a name="return-value"></a>Return Value

배열에 저장된 요소 수를 반환합니다.

## <a name="csimplearrayoperator-"></a><a name="operator_at"></a>C심플이어레이::연산자\[\]

배열에서 요소를 검색합니다.

```
T& operator[](int nindex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
요소 인덱스입니다.

### <a name="return-value"></a>Return Value

*nIndex*에서 참조하는 배열의 요소를 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]

## <a name="csimplearrayoperator-"></a><a name="operator_eq"></a>C심플이어레이::연산자 =

대입 연산자입니다.

```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
복사할 배열입니다.

### <a name="return-value"></a>Return Value

업데이트된 `CSimpleArray` 개체에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

*src에서* 참조하는 `CSimpleArray` 개체의 모든 요소를 현재 배열 개체에 복사하여 모든 기존 데이터를 대체합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]

## <a name="csimplearrayremove"></a><a name="remove"></a>C심플어레이::제거

배열에서 지정된 요소를 제거합니다.

```
BOOL Remove(const T& t);
```

### <a name="parameters"></a>매개 변수

*t*<br/>
배열에서 제거할 요소입니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 요소가 발견되고 제거된 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

요소가 제거되면 배열의 나머지 요소의 번호가 다시 매겨빈 공간을 채웁니다.

## <a name="csimplearrayremoveall"></a><a name="removeall"></a>C심플어레이::모두 제거

배열에서 모든 요소를 제거합니다.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>설명

현재 배열에 저장된 모든 요소를 제거합니다.

## <a name="csimplearrayremoveat"></a><a name="removeat"></a>C심플어레이::리무트

배열에서 지정된 요소를 제거합니다.

```
BOOL RemoveAtint nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
제거할 요소를 가리키는 인덱스입니다.

### <a name="return-value"></a>Return Value

요소가 제거된 경우 TRUE를 반환하고 인덱스가 유효하지 않은 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

요소가 제거되면 배열의 나머지 요소의 번호가 다시 매겨빈 공간을 채웁니다.

## <a name="csimplearraysetatindex"></a><a name="setatindex"></a>C심플이어레이::세타인덱스

배열에서 지정된 요소를 설정합니다.

```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
변경할 요소의 인덱스입니다.

*t*<br/>
지정된 요소에 할당할 값입니다.

### <a name="return-value"></a>Return Value

인덱스가 유효하지 않은 경우 TRUE, FALSE를 반환합니다.

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)
