---
title: Platform::Collections::Map 클래스
ms.date: 10/01/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::Map::Map
- COLLECTION/Platform::Collections::Map::Clear
- COLLECTION/Platform::Collections::Map::First
- COLLECTION/Platform::Collections::Map::GetView
- COLLECTION/Platform::Collections::Map::HasKey
- COLLECTION/Platform::Collections::Map::Insert
- COLLECTION/Platform::Collections::Map::Lookup
- COLLECTION/Platform::Collections::Map::Remove
- COLLECTION/Platform::Collections::Map::Size
helpviewer_keywords:
- Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
ms.openlocfilehash: ff27f6c543a2326dd4318f66aae51b89092b28e2
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032449"
---
# <a name="platformcollectionsmap-class"></a>Platform::Collections::Map 클래스

키/값 쌍의 컬렉션인 *맵*을 나타냅니다. [Windows:::Foundation::컬렉션::IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2) XAML [데이터 바인딩에](/windows/uwp/data-binding/data-binding-in-depth)대 한 도움말을 구현 합니다.

## <a name="syntax"></a>구문

```cpp
template <
   typename K,
   typename V,
   typename C = std::less<K>>
ref class Map sealed;
```

### <a name="parameters"></a>매개 변수

*K (주)*<br/>
키/값 쌍의 키 형식입니다.

*Ⅴ*<br/>
키/값 쌍의 값 형식입니다.

*C*<br/>
두 요소 값을 정렬 키로 비교하여 맵에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다. 기본적으로 [\<std::less K>](../standard-library/less-struct.md).

*__is_valid_winrt_type()* *K와* *V의* 형식을 확인하고 형식을 맵에 저장할 수 없는 경우 친숙한 오류 메시지를 제공하는 컴파일러 생성 함수입니다.

### <a name="remarks"></a>설명

허용 유형은 다음과 같습니다.

- 정수

- 인터페이스 클래스^

- public ref 클래스 ^

- value struct

- public enum 클래스

Map은 기본적으로 [std::map](../standard-library/map-class.md)에 대한 래퍼입니다. [Windows::Foundation::컬렉션:IMap<Windows:::Foundation::컬렉션::IKeyValuePair\<K, V>>](/uwp/api/windows.foundation.collections.imap-2) 및 공용 Windows 런타임 인터페이스를 통해 전달되는 [IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2) 형식의 C++ 구체적인 구현입니다. 공용 반환 값 또는 매개 변수에서 `Platform::Collections::Map` 형식을 사용하려고 하면 컴파일러 오류 C3986이 발생합니다. 매개 변수의 형식을 변경 하 여 오류를 해결 하거나 [Windows::Foundation::컬렉션:::IMap\<K,V>](/uwp/api/windows.foundation.collections.imap-2)값을 반환 할 수 있습니다.

자세한 내용은 [컬렉션 을](../cppcx/collections-c-cx.md)참조하십시오.

### <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[지도::지도](#ctor)|Map 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[지도::지우기](#clear)|현재 Map 개체에서 모든 키/값 쌍을 제거합니다.|
|[지도::첫 번째](#first)|맵의 첫 번째 요소를 지정하는 반복기를 반환합니다.|
|[지도::GetView](#getview)|현재 Map의 읽기 전용 보기, 즉 [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md)를 반환합니다.|
|[지도::하스키](#haskey)|현재 Map에 지정한 키가 들어 있는지 여부를 확인합니다.|
|[지도:::삽입](#insert)|지정한 키/값 쌍을 현재 Map 개체에 추가합니다.|
|[지도::조회](#lookup)|현재 Map 개체의 지정된 키에 있는 요소를 검색합니다.|
|[Map::Remove](#remove)|지정한 키/값 쌍을 현재 Map 개체에서 삭제합니다.|
|[지도::크기](#size)|현재 Map 개체의 요소 수를 반환합니다.|

### <a name="events"></a>이벤트

|||
|-|-|
|속성|Description|
|[지도::맵 변경](#mapchanged) 이벤트|Map이 변경될 때 발생합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Map`

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Platform::Collections

## <a name="mapclear-method"></a><a name="clear"></a>지도::명확한 방법

현재 Map 개체에서 모든 키/값 쌍을 제거합니다.

### <a name="syntax"></a>구문

```cpp
virtual void Clear();
```

## <a name="mapfirst-method"></a><a name="first"></a>지도::첫 번째 방법

맵의 첫 번째 요소를 지정하는 반복기 또는 `nullptr`(맵이 비어 있는 경우)을 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Return Value

맵의 첫 번째 요소를 지정하는 반복기입니다.

### <a name="remarks"></a>설명

First()에서 반환되는 이터레이터를 유지하는 편리한 방법은 **자동** 형식 공제 키워드로 선언된 변수에 반환 값을 할당하는 것입니다. `auto x = myMap->First();`)을 입력합니다.

## <a name="mapgetview-method"></a><a name="getview"></a>지도::GetView 방법

현재 맵의 읽기 전용 보기를 반환합니다. 즉, [플랫폼::컬렉션::MapView 클래스,](../cppcx/platform-collections-mapview-class.md) [Windows:::Foundation::컬렉션::IMapView\<K,V>인터페이스를](/uwp/api/windows.foundation.collections.imapview-2) 구현 합니다.

### <a name="syntax"></a>구문

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Return Value

`MapView` 개체입니다.

## <a name="maphaskey-method"></a><a name="haskey"></a>지도::하스키 방법

현재 Map에 지정한 키가 들어 있는지 여부를 확인합니다.

### <a name="syntax"></a>구문

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
Map 요소를 찾는 데 사용되는 키입니다. *키의* 유형은 *K*.

### <a name="return-value"></a>Return Value

키가 발견되면 **true;** 그렇지 **않으면, 거짓**.

## <a name="mapinsert-method"></a><a name="insert"></a>지도::삽입 방법

지정한 키/값 쌍을 현재 Map 개체에 추가합니다.

### <a name="syntax"></a>구문

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키-값 쌍의 키 부분입니다. *키의* 유형은 *K*.

*value*<br/>
키-값 쌍의 값 부분입니다. *값의* 형식은 형식 이름 *V입니다.*

### <a name="return-value"></a>Return Value

**true** 현재 맵에 있는 기존 요소의 키가 *키와* 일치하고 해당 요소의 값 부분이 *값으로*설정된 경우 true입니다. false **는** 현재 맵에 기존 요소가 *키와* 일치하지 않고 *키* 및 *값* 매개 변수가 키-값 쌍으로 만들어진 다음 현재 맵에 추가되는 경우 false입니다.

## <a name="maplookup-method"></a><a name="lookup"></a>지도::조회 방법

K 형식의 지정된 키(해당 키가 있는 경우)와 연결된 V 형식의 값을 검색합니다.

### <a name="syntax"></a>구문

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
지도에서 요소를 찾는 데 사용되는 키입니다. *키의* 유형은 *K*.

### <a name="return-value"></a>Return Value

*키와*페어링된 값입니다. 반환 값의 형식은 형식 이름 *V입니다.*

### <a name="remarks"></a>설명

키가 없으면 [플랫폼::OutOfBoundsException이](../cppcx/platform-outofboundsexception-class.md) throw됩니다.

## <a name="mapmap-constructor"></a><a name="ctor"></a>지도::맵 생성자

Map 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
explicit Map(const C& comp = C());
explicit Map(const StdMap& m);
explicit Map(StdMap&& m ;
template <typename InIt>
Map(
   InItfirst,
   InItlast,
   const C& comp = C());
```

### <a name="parameters"></a>매개 변수

*Init*<br/>
현재 Map의 형식 이름입니다.

*광고*<br/>
두 요소 값을 정렬 키로 비교하여 맵에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다.

*M*<br/>
현재 맵을 초기화하는 데 사용되는 에 `map Class` 대한 참조 또는 [rvalue입니다.](../cpp/lvalues-and-rvalues-visual-cpp.md)

*첫 번째*<br/>
현재 Map를 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.

*마지막*<br/>
현재 Map를 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.

## <a name="mapmapchanged-event"></a><a name="mapchanged"></a>지도::맵 변경 이벤트

맵에서 항목이 삽입되거나 제거될 때 발생합니다.

### <a name="syntax"></a>구문

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>속성 값/반환 값

이벤트를 발생시킨 개체 및 발생한 변경 종류에 대한 정보가 포함된 [MapChangedEventHandler\<K,V>.](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) 또한 [IMapChangedEventArgs\<K>](/uwp/api/windows.foundation.collections.imapchangedeventargs-1) 및 [컬렉션변경 열거.](/uwp/api/windows.foundation.collections.collectionchange)

## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값

C# 또는 시각적 기본 프로젝트 IMap\<K,V 를 iDictionary\<K,V> 사용> 하는 Windows 런타임 응용 프로그램.

## <a name="mapremove-method"></a><a name="remove"></a>지도::제거 방법

지정한 키/값 쌍을 현재 Map 개체에서 삭제합니다.

### <a name="syntax"></a>구문

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키-값 쌍의 키 부분입니다. *키의* 유형은 *K*.

## <a name="mapsize-method"></a><a name="size"></a>지도::크기 방법

[Windows::Foundation::컬렉션::IKeyValuePair\<K,V>](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) 맵 요소 수를 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Return Value

Map의 요소 수입니다.

## <a name="see-also"></a>참조

[컬렉션(C++/CX)](collections-c-cx.md)<br/>
[플랫폼 네임스페이스](platform-namespace-c-cx.md)<br/>
[C++로 Windows Runtime 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
