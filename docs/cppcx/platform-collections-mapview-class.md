---
title: Platform::Collections::MapView 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::MapView::MapView
- COLLECTION/Platform::Collections::MapView::First
- COLLECTION/Platform::Collections::MapView::HasKey
- COLLECTION/Platform::Collections::MapView::Lookup
- COLLECTION/Platform::Collections::MapView::Size
- COLLECTION/Platform::Collections::MapView::Split
helpviewer_keywords:
- MapView Class
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
ms.openlocfilehash: 98c146cec2febefee9c16528bee8f6be83f2a026
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032436"
---
# <a name="platformcollectionsmapview-class"></a>Platform::Collections::MapView 클래스

읽기 전용 보기를 키/값 쌍의 컬렉션인 *맵*으로 나타냅니다.

## <a name="syntax"></a>구문

```
template <
   typename K,
   typename V,
   typename C = ::std::less<K>>
ref class MapView sealed;
```

#### <a name="parameters"></a>매개 변수

*K (주)*<br/>
키/값 쌍의 키 형식입니다.

*Ⅴ*<br/>
키/값 쌍의 값 형식입니다.

*C*<br/>
두 요소 값을 정렬 키로 비교하여 MapView에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다. 기본적으로 [\<std::less K>](../standard-library/less-struct.md).

### <a name="remarks"></a>설명

MapView는 [Windows::Foundation::Collection::IMapView \<K,V>](/uwp/api/windows.foundation.collections.imapview-2) 응용 프로그램 바이너리 인터페이스(ABI)를 통해 전달되는 인터페이스의 구체적인 C++ 구현입니다. 자세한 내용은 [컬렉션(C++/CX)](../cppcx/collections-c-cx.md)을 참조하세요.

### <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[지도보기::맵뷰](#ctor)|MapView 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[지도 보기::첫 번째](#first)|맵 뷰의 첫 번째 요소로 초기화하는 반복기를 반환합니다.|
|[지도 보기::하스키](#haskey)|현재 MapView에 지정한 키가 들어 있는지 여부를 확인합니다.|
|[지도 보기::조회](#lookup)|현재 MapView 개체의 지정된 키에 있는 요소를 검색합니다.|
|[MapView::Size](#size)|현재 MapView 개체의 요소 수를 반환합니다.|
|[지도 보기::분할](#split)|원래 MapView 개체를 두 개의 MapView 개체로 분할합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`MapView`

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Platform::Collections

## <a name="mapviewfirst-method"></a><a name="first"></a>맵뷰::첫 번째 방법

맵 뷰의 첫 번째 요소를 지정하는 반복기를 반환합니다.

### <a name="syntax"></a>구문

```
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Return Value

맵 뷰의 첫 번째 요소를 지정하는 반복기입니다.

### <a name="remarks"></a>설명

First()에서 반환되는 이터레이터를 유지하는 편리한 방법은 **자동** 형식 공제 키워드로 선언된 변수에 반환 값을 할당하는 것입니다. `auto x = myMapView->First();`)을 입력합니다.

## <a name="mapviewhaskey-method"></a><a name="haskey"></a>맵뷰::하스키 방법

현재 MapView에 지정한 키가 들어 있는지 여부를 확인합니다.

### <a name="syntax"></a>구문

```

bool HasKey(K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
MapView 요소를 찾는 데 사용되는 키입니다. *키의* 유형은 *K*.

### <a name="return-value"></a>Return Value

키가 발견되면 **true;** 그렇지 **않으면, 거짓**.

## <a name="mapviewlookup-method"></a><a name="lookup"></a>맵뷰::조회 방법

K 형식의 지정된 키와 연결된 V 형식의 값을 검색합니다.

### <a name="syntax"></a>구문

```
V Lookup(K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
MapView에서 요소를 찾는 데 사용되는 키입니다. 유형은 `key` *K*.

### <a name="return-value"></a>Return Value

`key`와 쌍을 이루는 값입니다. 반환 값의 형식은 형식 이름 *V입니다.*

## <a name="mapviewmapview-constructor"></a><a name="ctor"></a>맵뷰::맵뷰 생성자

MapView 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
explicit MapView(const C& comp = C());

explicit MapView(const ::std::map<K, V, C>& m);

explicit MapView(std::map<K, V, C>&& m);

template <typename InIt> MapView(
    InIt first,
    InIt last,
    const C& comp = C());

MapView(
    ::std::initializer_list<std::pair<const K, V>> il,
    const C& comp = C());
```

### <a name="parameters"></a>매개 변수

*Init*<br/>
현재 MapView의 형식 이름입니다.

*광고*<br/>
두 요소 값을 정렬 키로 비교하여 MapView에서 해당 상대 순서를 확인할 수 있는 함수 개체입니다.

*M*<br/>
현재 MapView를 초기화하는 `map Class` 데 사용되는 에 대한 참조 또는 [Lvalues 및 Rvalues입니다.](../cpp/lvalues-and-rvalues-visual-cpp.md)

*첫 번째*<br/>
현재 MapView를 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.

*마지막*<br/>
현재 MapView를 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.

*Il*<br/>
[std:initializer_list<std::pair\<K,V>>](../standard-library/initializer-list-class.md) 그 요소가 MapView에 삽입됩니다.

## <a name="mapviewsize-method"></a><a name="size"></a>지도보기::크기 방법

현재 MapView 개체의 요소 수를 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Return Value

현재 MapView의 요소 수입니다.

## <a name="mapviewsplit-method"></a><a name="split"></a>맵뷰::분할 방법

현재 MapView 개체를 두 개의 MapView 개체로 분할합니다. 이 메서드는 작동하지 않습니다.

### <a name="syntax"></a>구문

```cpp
void Split(
   Windows::Foundation::Collections::IMapView<
                         K, V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K, V>^ * secondPartition);
```

### <a name="parameters"></a>매개 변수

*첫 번째파티션*<br/>
원래 MapView 개체의 첫 번째 부분입니다.

*두 번째파티션*<br/>
원래 MapView 개체의 두 번째 부분입니다.

### <a name="remarks"></a>설명

이 메서드는 작동하지 않으며, 아무 작업도 수행하지 않습니다.

## <a name="see-also"></a>참조

[플랫폼 네임스페이스](platform-namespace-c-cx.md)
