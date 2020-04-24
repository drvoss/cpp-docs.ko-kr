---
title: Platform::Collections::UnorderedMapView 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMapView
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
ms.openlocfilehash: f0096982ad5d11b9ea394c9f02ba748a52e4216b
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031487"
---
# <a name="platformcollectionsunorderedmapview-class"></a>Platform::Collections::UnorderedMapView 클래스

읽기 전용 보기를 키/값 쌍의 컬렉션인 *맵*으로 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template <
   typename K,
   typename V,
   typename C = ::std::equal_to<K>>
ref class UnorderedMapView sealed;
```

#### <a name="parameters"></a>매개 변수

*K (주)*<br/>
키/값 쌍의 키 형식입니다.

*Ⅴ*<br/>
키/값 쌍의 값 형식입니다.

*C*<br/>
같은지 확인하기 위해 두 키 값을 비교할 수 있는 함수 개체를 제공하는 형식입니다. 기본적으로 [std:equal_to\<K>](../standard-library/equal-to-struct.md)

### <a name="remarks"></a>설명

정렬되지 않은 MapView는 [Windows::Foundation::Collection::IMapView\<K,V>](/uwp/api/windows.foundation.collections.imapview-2) 인터페이스의 구체적인 C++ 구현으로 응용 프로그램 바이너리 인터페이스(ABI)를 통해 전달됩니다. 자세한 내용은 [컬렉션(C++/CX)](../cppcx/collections-c-cx.md)을 참조하세요.

### <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[정렬되지 않은 MapView::정렬되지 않은 맵뷰](#ctor)|UnorderedMapView 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[정렬되지 않은 MapView::첫 번째](#first)|맵 뷰의 첫 번째 요소로 초기화하는 반복기를 반환합니다.|
|[정렬되지 않은 맵뷰::하스키](#haskey)|현재 UnorderedMapView에 지정한 키가 들어 있는지 여부를 확인합니다.|
|[정렬되지 않은 MapView::조회](#lookup)|현재 UnorderedMapView 개체의 지정된 키에 있는 요소를 검색합니다.|
|[정렬되지 않은 MapView::크기](#size)|현재 UnorderedMapView 개체의 요소 수를 반환합니다.|
|[정렬되지 않은 MapView::분할](#split)|원래 UnorderedMapView 개체를 두 개의 UnorderedMapView 개체로 분할합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`UnorderedMapView`

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Platform::Collections

## <a name="unorderedmapviewfirst-method"></a><a name="first"></a>정렬되지 않은 MapView::첫 번째 방법

첫 번째 [Windows::Foundation::컬렉션::IKeyValuePair\<K,V>](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) 순서가 지정되지 않은 맵의 요소를 지정하는 이터레이터를 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual Windows::Foundation::Collections::IIterator<
    Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
    First();
```

### <a name="return-value"></a>Return Value

맵 뷰의 첫 번째 요소를 지정하는 반복기입니다.

### <a name="remarks"></a>설명

First()에서 반환되는 이터레이터를 유지하는 편리한 방법은 **자동** 형식 공제 키워드로 선언된 변수에 반환 값을 할당하는 것입니다. `auto x = myMapView->First();`)을 입력합니다.

## <a name="unorderedmapviewhaskey-method"></a><a name="haskey"></a>정렬되지 않은 MapView::하스키 방법

현재 UnorderedMap에 지정한 키가 들어 있는지 여부를 확인합니다.

### <a name="syntax"></a>구문

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
요소를 찾는 데 사용되는 키입니다. 유형은 `key` *K*.

### <a name="return-value"></a>Return Value

키가 발견되면 **true;** 그렇지 **않으면, 거짓**.

## <a name="unorderedmapviewlookup-method"></a><a name="lookup"></a>정렬되지 않은 MapView::조회 방법

K 형식의 지정된 키와 연결된 V 형식의 값을 검색합니다.

### <a name="syntax"></a>구문

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
UnorderedMapView에서 요소를 찾는 데 사용되는 키입니다. 유형은 `key` *K*.

### <a name="return-value"></a>Return Value

`key`와 쌍을 이루는 값입니다. 반환 값의 형식은 형식 이름 *V입니다.*

## <a name="unorderedmapviewsize-method"></a><a name="size"></a>정렬되지 않은 MapView::크기 방법

[Windows::Foundation:컬렉션::IKeyValuePair\<K,V>](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) 정렬되지 않은 MapView의 요소를 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Return Value

UnorderedMapView의 요소 수입니다.

## <a name="unorderedmapviewsplit-method"></a><a name="split"></a>정렬되지 않은 MapView::분할 방법

현재 UnorderedMapView 개체를 두 개의 UnorderedMapView 개체로 나눕니다. 이 메서드는 작동하지 않습니다.

### <a name="syntax"></a>구문

```cpp
void Split(
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * secondPartition);
```

### <a name="parameters"></a>매개 변수

*첫 번째파티션*<br/>
원래 UnorderedMapView 개체의 첫 번째 부분입니다.

*두 번째파티션*<br/>
원래 UnorderedMapView 개체의 두 번째 부분입니다.

### <a name="remarks"></a>설명

이 메서드는 작동하지 않으며, 아무 작업도 수행하지 않습니다.

## <a name="unorderedmapviewunorderedmapview-constructor"></a><a name="ctor"></a>정렬되지 않은 MapView::정렬되지 않은 MapView 생성자

UnorderedMapView 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
UnorderedMapView();
explicit UnorderedMapView(size_t n);
UnorderedMapView(size_t n, const H& h);
UnorderedMapView(size_t n, const H& h, const P& p);

explicit UnorderedMapView(
    const std::unordered_map<K, V, H, P>& m);
explicit UnorderedMapView(
    std::unordered_map<K, V, H, P>&& m);

template <typename InIt> UnorderedMapView(InIt first, InIt last );
template <typename InIt> UnorderedMapView(InIt first, InIt last, size_t n );

template <typename InIt> UnorderedMapView(
    InIt first,
    InIt last,
    size_t n,
    const H& h );

template <typename InIt> UnorderedMapView(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p );

UnorderedMapView(std::initializer_list<std::pair<const K, V>);

UnorderedMapView(std::initializer_list< std::pair<const K, V>> il, size_t n

UnorderedMapView(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h);

UnorderedMapView(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p );
```

### <a name="parameters"></a>매개 변수

*n*<br/>
공간을 미리 할당할 요소의 수입니다.

*Init*<br/>
UnorderedMapView의 형식 이름입니다.

*H*<br/>
키에 해시 값을 사용할 수 있는 함수 개체입니다. `std::hash` [std::해시\<K를](../standard-library/hash-class.md) 지원하는 형식에 대해>.

*P*<br/>
같은지 확인하기 위해 두 키를 비교할 수 있는 함수 개체를 제공하는 형식입니다. [std:equal_to\<K>](../standard-library/equal-to-struct.md)기본값 .

*M*<br/>
정렬되지 않은 MapView를 초기화하는 데 사용되는 [std::unordered_map](../standard-library/unordered-map-class.md) 대한 참조 또는 [Lvalues 및 Rvalues입니다.](../cpp/lvalues-and-rvalues-visual-cpp.md)

*첫 번째*<br/>
UnorderedMapView를 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.

*마지막*<br/>
UnorderedMapView를 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.

## <a name="see-also"></a>참조

[Platform::Collections 네임스페이스](../cppcx/platform-collections-namespace.md)<br/>
[Windows::Foundation::IMapView](/uwp/api/windows.foundation.collections.imapview-2)
