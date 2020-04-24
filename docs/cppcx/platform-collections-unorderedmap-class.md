---
title: Platform::Collections::UnorderedMap 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
ms.openlocfilehash: 80b46cb95f2fdb83922ca22e8aa06a89aca4bfde
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031500"
---
# <a name="platformcollectionsunorderedmap-class"></a>Platform::Collections::UnorderedMap 클래스

키-값 쌍의 컬렉션인 순서가 지정되지 않은 *맵*을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template <
   typename K,
   typename V,
   typename C = std::equal_to<K>
>
ref class Map sealed;
```

#### <a name="parameters"></a>매개 변수

*K (주)*<br/>
키/값 쌍의 키 형식입니다.

*Ⅴ*<br/>
키/값 쌍의 값 형식입니다.

*C*<br/>
두 요소 값을 정렬 키로 비교하여 맵에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다. 기본적으로 [std:equal_to\<K>](../standard-library/equal-to-struct.md).

### <a name="remarks"></a>설명

허용 유형은 다음과 같습니다.

- 정수

- 인터페이스 클래스^

- public ref 클래스 ^

- value struct

- public enum 클래스

**정렬되지 않은 Map은** 기본적으로 Windows 런타임 형식의 저장소를 지원하는 [std:unordered_map](../standard-library/unordered-map-class.md) 래퍼입니다. 공용 Windows 런타임 인터페이스를 통해 전달되는 [Windows::Foundation::Collection::IMap](/uwp/api/windows.foundation.collections.imap-2) 및 [IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2) 형식의 구체적인 구현입니다. 공용 반환 값 또는 매개 변수에서 `Platform::Collections::UnorderedMap` 형식을 사용하려고 하면 컴파일러 오류 C3986이 발생합니다. 매개 변수나 반환 값 형식을 [Windows::Foundation::Collections::IMap](/uwp/api/windows.foundation.collections.imap-2)으로 변경하여 오류를 수정할 수 있습니다.

자세한 내용은 [컬렉션 을](../cppcx/collections-c-cx.md)참조하십시오.

### <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[정렬되지 않은 맵::정렬되지 않은 맵](#ctor)|Map 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[정렬되지 않은 맵::지우기](#clear)|현재 Map 개체에서 모든 키/값 쌍을 제거합니다.|
|[정렬되지 않은 맵::첫 번째](#first)|맵의 첫 번째 요소를 지정하는 반복기를 반환합니다.|
|[정렬되지 않은 맵::GetView](#getview)|현재 Map의 읽기 전용 뷰, 즉 Platform::Collections::UnorderedMapView 클래스를 반환합니다.|
|[정렬되지 않은 맵::하스키](#haskey)|현재 Map에 지정한 키가 들어 있는지 여부를 확인합니다.|
|[정렬되지 않은 맵::삽입](#insert)|지정한 키/값 쌍을 현재 Map 개체에 추가합니다.|
|[정렬되지 않은 맵::조회](#lookup)|현재 Map 개체의 지정된 키에 있는 요소를 검색합니다.|
|[정렬되지 않은 맵::제거](#remove)|지정한 키/값 쌍을 현재 Map 개체에서 삭제합니다.|
|[정렬되지 않은 맵::크기](#size)|현재 Map 개체의 요소 수를 반환합니다.|

### <a name="events"></a>이벤트

|||
|-|-|
|속성|Description|
|[지도::맵 변경](#mapchanged) 이벤트|Map이 변경될 때 발생합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`UnorderedMap`

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Platform::Collections

## <a name="unorderedmapclear-method"></a><a name="clear"></a>정렬되지 않은 맵::지우기 방법

현재 UnorderedMap 개체에서 모든 키-값 쌍을 제거합니다.

### <a name="syntax"></a>구문

```cpp
virtual void Clear();
```

## <a name="unorderedmapfirst-method"></a><a name="first"></a>정렬되지 않은 맵::첫 번째 방법

첫 번째 [Windows::Foundation::컬렉션::IKeyValuePair\<K,V>](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) 순서가 지정되지 않은 맵의 요소를 지정하는 이터레이터를 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
   First();
```

### <a name="return-value"></a>Return Value

맵의 첫 번째 요소를 지정하는 반복기입니다.

### <a name="remarks"></a>설명

First()에서 반환되는 이터레이터를 유지하는 편리한 방법은 **자동** 형식 공제 키워드로 선언된 변수에 반환 값을 할당하는 것입니다. `auto x = myUnorderedMap->First();`)을 입력합니다.

## <a name="unorderedmapgetview-method"></a><a name="getview"></a>정렬되지 않은 맵::GetView 방법

현재 정렬되지 않은 맵의 읽기 전용 보기를 반환합니다. 즉, [플랫폼::컬렉션:::정렬되지 않은 MapView 클래스는](../cppcx/platform-collections-unorderedmapview-class.md) [Windows:::Foundation::Collection::IMapView::IMapView 인터페이스를 구현합니다.](/uwp/api/windows.foundation.collections.imapview-2)

### <a name="syntax"></a>구문

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Return Value

`UnorderedMapView` 개체입니다.

## <a name="unorderedmaphaskey-method"></a><a name="haskey"></a>정렬되지 않은 맵::하스키 방법

현재 UnorderedMap에 지정한 키가 들어 있는지 여부를 확인합니다.

### <a name="syntax"></a>구문

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
UnorderedMap 요소를 찾는 데 사용되는 키입니다. *키의* 유형은 *K*.

### <a name="return-value"></a>Return Value

키가 발견되면 **true;** 그렇지 **않으면, 거짓**.

## <a name="unorderedmapinsert-method"></a><a name="insert"></a>정렬되지 않은 맵::삽입 방법

지정한 키-값 쌍을 현재 UnorderedMap 개체에 추가합니다.

### <a name="syntax"></a>구문

```cpp
virtual bool Insert(
   K key,
   V value
);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키-값 쌍의 키 부분입니다. *키의* 유형은 *K*.

*value*<br/>
키-값 쌍의 값 부분입니다. *값의* 형식은 형식 이름 *V입니다.*

### <a name="return-value"></a>Return Value

**true** 현재 맵에 있는 기존 요소의 키가 *키와* 일치하고 해당 요소의 값 부분이 *값으로*설정된 경우 true입니다. false **는** 현재 맵에 기존 요소가 *키와* 일치하지 않고 *키* 및 *값* 매개 변수가 키-값 쌍으로 만들어진 다음 현재 UnorderedMap에 추가되는 경우 false입니다.

## <a name="unorderedmaplookup-method"></a><a name="lookup"></a>정렬되지 않은 맵::조회 방법

K 형식의 지정된 키와 연결된 V 형식의 값을 검색합니다.

### <a name="syntax"></a>구문

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
UnorderedMap에서 요소를 찾는 데 사용되는 키입니다. *키의* 유형은 *K*.

### <a name="return-value"></a>Return Value

*키와*페어링된 값입니다. 반환 값의 형식은 형식 이름 *V입니다.*

## <a name="unorderedmapmapchanged"></a><a name="mapchanged"></a>정렬되지 않은 맵::맵 변경

맵에서 항목이 삽입되거나 제거될 때 발생합니다.

### <a name="syntax"></a>구문

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>속성 값/반환 값

이벤트를 발생시킨 개체 및 발생한 변경 종류에 대한 정보가 포함된 [MapChangedEventHandler\<K,V>.](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) 또한 [IMapChangedEventArgs\<K>](/uwp/api/windows.foundation.collections.imapchangedeventargs-1) 및 [컬렉션변경 열거.](/uwp/api/windows.foundation.collections.collectionchange)

## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값

윈도우 런타임 애플 리 케이 션 우리\<C # 또는\<비주얼 기본 프로젝트 IMap K, V iDictionary K, V>>.

## <a name="unorderedmapremove-method"></a><a name="remove"></a>정렬되지 않은 맵::제거 방법

지정한 키-값 쌍을 UnorderedMap 개체에서 삭제합니다.

### <a name="syntax"></a>구문

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키-값 쌍의 키 부분입니다. *키의* 유형은 *K*.

## <a name="unorderedmapsize-method"></a><a name="size"></a>정렬되지 않은 맵::크기 방법

[Windows::Foundation::컬렉션::IKeyValuePair\<K,V>](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) 정렬되지 않은 맵의 요소를 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Return Value

UnorderedMap의 요소 수입니다.

## <a name="unorderedmapunorderedmap-constructor"></a><a name="ctor"></a>정렬되지 않은 맵::정렬되지 않은 맵 생성자

UnorderedMap 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
UnorderedMap();

explicit UnorderedMap(
    size_t n
    );

UnorderedMap(
    size_t n,
    const H& h
    );

UnorderedMap(
    size_t n,
    const H& h,
    const P& p
    );

explicit UnorderedMap(
    const std::unordered_map<K, V, H, P>& m
    );

explicit UnorderedMap(
    std::unordered_map<K, V, H, P>&& m
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p
    );
```

### <a name="parameters"></a>매개 변수

*Init*<br/>
현재 UnorderedMap의 형식 이름입니다.

*P*<br/>
같은지 여부를 확인하기 위해 두 키를 비교할 수 있는 함수 개체입니다. 이 매개 변수는 기본적으로 [std:equal_to\<K>. ](../standard-library/equal-to-struct.md)

*H*<br/>
키에 대한 해시 값을 생성하는 함수 개체입니다. 이 매개 변수는 클래스가 지원하는 키 유형에 대해 [클래스 1을 해시로](../standard-library/hash-class.md) 기본설정합니다.

*M*<br/>
현재 정렬되지 않은 맵을 초기화하는 데 사용되는 [std:unordered_map](../standard-library/unordered-map-class.md) 대한 참조 또는 [Lvalues 및 Rvalues입니다.](../cpp/lvalues-and-rvalues-visual-cpp.md)

*Il*<br/>
[std:std:initializer_list](../standard-library/initializer-list-class.md) [std::pair](../standard-library/pair-structure.md) 객체는 맵을 초기화하는 데 사용됩니다.

*첫 번째*<br/>
현재 UnorderedMap을 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.

*마지막*<br/>
현재 UnorderedMap을 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.

## <a name="see-also"></a>참조

[플랫폼 네임스페이스](platform-namespace-c-cx.md)<br/>
[Platform::Collections 네임스페이스](../cppcx/platform-collections-namespace.md)<br/>
[플랫폼::컬렉션::맵 클래스](../cppcx/platform-collections-map-class.md)<br/>
[Platform::Collections::UnorderedMapView 클래스](../cppcx/platform-collections-unorderedmapview-class.md)<br/>
[컬렉션](../cppcx/collections-c-cx.md)<br/>
[C++로 Windows Runtime 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
