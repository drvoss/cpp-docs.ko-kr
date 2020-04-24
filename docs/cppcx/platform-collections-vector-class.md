---
title: Platform::Collections::Vector 클래스
ms.date: 12/04/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::Vector::Vector
- COLLECTION/Platform::Collections::Vector::Append
- COLLECTION/Platform::Collections::Vector::Clear
- COLLECTION/Platform::Collections::Vector::First
- COLLECTION/Platform::Collections::Vector::GetAt
- COLLECTION/Platform::Collections::Vector::GetMany
- COLLECTION/Platform::Collections::Vector::GetView
- COLLECTION/Platform::Collections::Vector::IndexOf
- COLLECTION/Platform::Collections::Vector::InsertAt
- COLLECTION/Platform::Collections::Vector::ReplaceAll
- COLLECTION/Platform::Collections::Vector::RemoveAt
- COLLECTION/Platform::Collections::Vector::RemoveAtEnd
- COLLECTION/Platform::Collections::Vector::SetAt
- COLLECTION/Platform::Collections::Vector::Size
- COLLECTION/Platform::Collections::Vector::VectorChanged
helpviewer_keywords:
- Vector Class (C++/Cx)
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
ms.openlocfilehash: 60c82a113bc19e9652af8c1ad531e1c479077f20
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032124"
---
# <a name="platformcollectionsvector-class"></a>Platform::Collections::Vector 클래스

개별적으로 인덱스에 의해 액세스될 수 있는 개체의 순차적인 컬렉션을 나타냅니다. [Windows:::Foundation::컬렉션::IObservableVector](/uwp/api/windows.foundation.collections.iobservablevector-1) XAML [데이터 바인딩에](/windows/uwp/data-binding/data-binding-in-depth)대 한 도움말을 구현 합니다.

## <a name="syntax"></a>구문

```
template <typename T, typename E>
   ref class Vector sealed;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
Vector 개체에 포함된 요소의 형식입니다.

*전자*<br/>
*형식 T의*값으로 같음을 테스트하기 위한 이진 조건자 지정. 기본값은 `std::equal_to<T>`.

### <a name="remarks"></a>설명

허용 유형은 다음과 같습니다.

1. 정수

1. 인터페이스 클래스^

1. public ref 클래스 ^

1. value struct

1. public enum 클래스

**벡터** 클래스는 [Windows:::Foundation::Collection::IVector](/uwp/api/windows.foundation.collections.ivector-1) 인터페이스의 C++ 구체적인 구현입니다.

공용 반환 값 또는 매개 변수에서 **Vector** 형식을 사용하려고 하면 컴파일러 오류 C3986이 발생합니다. 매개 변수나 반환 값 형식을 [Windows::Foundation::Collections::IVector](/uwp/api/windows.foundation.collections.ivector-1)로 변경하여 오류를 수정할 수 있습니다. 자세한 내용은 [컬렉션(C++/CX)](../cppcx/collections-c-cx.md)을 참조하세요.

### <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[벡터::벡터](#ctor)|Vector 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[Vector::Append](#append)|현재 Vector의 마지막 항목 다음에 지정된 항목을 삽입합니다.|
|[벡터 :: 지우기](#clear)|현재 Vector의 모든 요소를 삭제합니다.|
|[벡터 :: 첫 번째](#first)|Vector의 첫 번째 요소를 지정하는 반복기를 반환합니다.|
|[벡터 :: GetAt](#getat)|지정된 인덱스로 식별되는 현재 Vector의 요소를 검색합니다.|
|[벡터 :: GetMany](#getmany)|현재 Vector에서 지정된 인덱스부터 시작하여 일련의 항목을 검색합니다.|
|[벡터::GetView](#getview)|Vector의 읽기 전용 보기, 즉 [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md)를 반환합니다.|
|[벡터::인덱스](#indexof)|현재 Vector에서 지정한 항목을 검색하고 있는 경우 항목의 인덱스를 반환합니다.|
|[Vector::InsertAt](#insertat)|지정된 인덱스로 식별된 요소에서 지정된 항목을 현재 벡터에 삽입합니다.|
|[Vector::ReplaceAll](#replaceall)|현재 Vector에서 요소를 삭제한 다음 지정된 배열의 요소를 삽입합니다.|
|[Vector::RemoveAt](#removeat)|현재 Vector에서 지정된 인덱스로 식별되는 요소를 삭제합니다.|
|[Vector::RemoveAtEnd](#removeatend)|현재 Vector의 끝에 있는 요소를 삭제합니다.|
|[Vector::SetAt](#setat)|현재 Vector에서 지정된 인덱스로 식별되는 요소에 지정된 값을 할당합니다.|
|[벡터 :: 크기](#size)|현재 Vector 개체의 요소 수를 반환합니다.|

### <a name="events"></a>이벤트

|||
|-|-|
|속성|Description|
|이벤트 [윈도우::파운데이션::컬렉션::벡터변경이벤트핸들러\<T>^ 벡터 변경](/uwp/api/windows.foundation.collections.vectorchangedeventhandler-1)|Vector가 변경될 때 발생합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Vector`

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Platform::Collections

## <a name="vectorappend-method"></a><a name="append"></a>벡터::부속 방법

현재 Vector의 마지막 항목 다음에 지정된 항목을 삽입합니다.

### <a name="syntax"></a>구문

```cpp
virtual void Append(T item);
```

### <a name="parameters"></a>매개 변수

*index*<br/>
Vector에 삽입할 항목입니다. *항목의* 형식은 *T* 형식 이름으로 정의됩니다.

## <a name="vectorclear-method"></a><a name="clear"></a>벡터::명확한 방법

현재 Vector의 모든 요소를 삭제합니다.

### <a name="syntax"></a>구문

```cpp
virtual void Clear();
```

## <a name="vectorfirst-method"></a><a name="first"></a>벡터::첫 번째 방법

Vector의 첫 번째 요소를 가리키는 반복기를 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual Windows::Foundation::Collections::IIterator <T>^ First();
```

### <a name="return-value"></a>Return Value

Vector의 첫 번째 요소를 가리키는 반복기입니다.

### <a name="remarks"></a>설명

First()에서 반환되는 이터레이터를 유지하는 편리한 방법은 **자동** 형식 공제 키워드로 선언된 변수에 반환 값을 할당하는 것입니다. `auto x = myVector->First();`)을 입력합니다. 이 반복기는 컬렉션의 길이를 알고 있습니다.

STL 함수에 전달하기 위해 한 쌍의 이터레이터가 필요한 경우 무료 함수를 사용하여 [Windows::Foundation::Collection::시작](../cppcx/begin-function.md) 및 [Windows::Foundation::Collection:::컬렉션:::끝](../cppcx/end-function.md)

## <a name="vectorgetat-method"></a><a name="getat"></a>벡터::GetAt 방법

지정된 인덱스로 식별되는 현재 Vector의 요소를 검색합니다.

### <a name="syntax"></a>구문

```cpp
virtual T GetAt(unsigned int index);
```

### <a name="parameters"></a>매개 변수

*index*<br/>
Vector 개체의 특정 요소를 지정하는 0부터 시작하는 부호 없는 정수입니다.

### <a name="return-value"></a>Return Value

*인덱스* 매개 변수에 의해 지정된 요소입니다. 요소 형식은 *T* 형식 이름으로 정의됩니다.

## <a name="vectorgetmany-method"></a><a name="getmany"></a>벡터 ::GetMany 방법

현재 Vector에서 지정된 인덱스부터 시작해 일련의 항목을 검색해서 호출자가 할당한 배열에 복사합니다.

### <a name="syntax"></a>구문

```cpp
virtual unsigned int GetMany(
    unsigned int startIndex,
    Platform::WriteOnlyArray<T>^ dest);
```

### <a name="parameters"></a>매개 변수

*startIndex*<br/>
검색할 항목 시작 부분의 0부터 시작하는 인덱스입니다.

*dest*<br/>
*startIndex에* 의해 지정된 요소에서 시작하고 벡터의 마지막 요소에서 끝나는 호출자 할당 된 항목 배열입니다.

### <a name="return-value"></a>Return Value

검색된 항목의 수입니다.

### <a name="remarks"></a>설명

이 함수는 클라이언트 코드에서 직접 사용하지 않습니다. 플랫폼::벡터 intances를 std::벡터 인스턴스로 효율적으로 변환할 수 있도록 [to_vector 함수에서](../cppcx/to-vector-function.md) 내부적으로 사용됩니다.

## <a name="vectorgetview-method"></a><a name="getview"></a>벡터::GetView 방법

Vector의 읽기 전용 보기, 즉 IVectorView를 반환합니다.

### <a name="syntax"></a>구문

```cpp
Windows::Foundation::Collections::IVectorView<T>^ GetView();
```

### <a name="return-value"></a>Return Value

IVectorView 개체입니다.

## <a name="vectorindexof-method"></a><a name="indexof"></a>벡터::인덱스오브 메소드

현재 Vector에서 지정한 항목을 검색하고 있는 경우 항목의 인덱스를 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual bool IndexOf(T value, unsigned int* index);
```

### <a name="parameters"></a>매개 변수

*value*<br/>
찾을 항목입니다.

*index*<br/>
매개 변수 *값이* 발견되면 항목의 0기반 인덱스입니다. 그렇지 않으면 0입니다.

*항목이* Vector의 첫 번째 요소이거나 항목을 찾을 수 없는 경우 인덱스 매개변수는 0입니다. 반환 값이 **true이면**항목이 발견되었으며 첫 번째 요소입니다. 그렇지 않으면 항목을 찾을 수 없습니다.

### <a name="return-value"></a>Return Value

지정된 항목이 발견되면 **true;** 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

IndexOf는 std::find_if를 사용하여 항목을 찾습니다. 그러므로 find_if에 필요한 같음 비교를 사용하려면 사용자 지정 요소 형식이 == 및 != 연산자를 오버로드해야 합니다.

## <a name="vectorinsertat-method"></a><a name="insertat"></a>벡터::삽입 방법

지정된 인덱스로 식별된 요소에서 지정된 항목을 현재 벡터에 삽입합니다.

### <a name="syntax"></a>구문

```cpp
virtual void InsertAt(unsigned int index, T item)
```

### <a name="parameters"></a>매개 변수

*index*<br/>
Vector 개체의 특정 요소를 지정하는 0부터 시작하는 부호 없는 정수입니다.

*item*<br/>
*인덱스로*지정된 요소에서 벡터에 삽입할 항목입니다. *항목의* 형식은 *T* 형식 이름으로 정의됩니다.

## <a name="vectorremoveat-method"></a><a name="removeat"></a>벡터::RemoveAt 방법

현재 Vector에서 지정된 인덱스로 식별되는 요소를 삭제합니다.

### <a name="syntax"></a>구문

```cpp
virtual void RemoveAt(unsigned int index);
```

### <a name="parameters"></a>매개 변수

*index*<br/>
Vector 개체의 특정 요소를 지정하는 0부터 시작하는 부호 없는 정수입니다.

## <a name="vectorremoveatend-method"></a><a name="removeatend"></a>벡터::제거끝 방법

현재 Vector의 끝에 있는 요소를 삭제합니다.

### <a name="syntax"></a>구문

```cpp
virtual void RemoveAtEnd();
```

## <a name="vectorreplaceall-method"></a><a name="replaceall"></a>벡터::모든 방법 바꾸기

현재 Vector에서 요소를 삭제한 다음 지정된 배열의 요소를 삽입합니다.

### <a name="syntax"></a>구문

```cpp
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);
```

### <a name="parameters"></a>매개 변수

*도착*<br/>
*T* 형식이름으로 정의된 개체의 배열입니다.

## <a name="vectorsetat-method"></a><a name="setat"></a>벡터::SetAt 방법

현재 Vector에서 지정된 인덱스로 식별되는 요소에 지정된 값을 할당합니다.

### <a name="syntax"></a>구문

```cpp
virtual void SetAt(unsigned int index, T item);
```

### <a name="parameters"></a>매개 변수

*index*<br/>
Vector 개체의 특정 요소를 지정하는 0부터 시작하는 부호 없는 정수입니다.

*item*<br/>
지정된 요소에 할당할 값입니다. *항목의* 형식은 *T* 형식 이름으로 정의됩니다.

## <a name="vectorsize-method"></a><a name="size"></a>벡터::크기 방법

현재 Vector 개체의 요소 수를 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Return Value

현재 Vector의 요소 수입니다.

## <a name="vectorvector-constructor"></a><a name="ctor"></a>벡터::벡터 생성자

Vector 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
Vector();

explicit Vector(unsigned int size);
Vector( unsigned int size, T value);
template <typename U> explicit Vector( const ::std::vector<U>& v);
template <typename U> explicit Vector( std::vector<U>&& v);

Vector( const T * ptr, unsigned int size);
template <size_t N> explicit Vector(const T(&arr)[N]);
template <size_t N> explicit Vector(const std::array<T, N>& a);
explicit Vector(const Array<T>^ arr);

template <typename InIt> Vector(InIt first, InIt last);
Vector(std::initializer_list<T> il);
```

### <a name="parameters"></a>매개 변수

*a.*<br/>
벡터를 초기화하는 데 사용되는 [std::배열입니다.](../standard-library/array-class-stl.md)

*도착*<br/>
[플랫폼::벡터를](../cppcx/platform-array-class.md) 초기화하는 데 사용되는 배열입니다.

*Init*<br/>
현재 Vector를 초기화하는 데 사용되는 개체 컬렉션의 형식입니다.

*Il*<br/>
[std::벡터를](../standard-library/initializer-list-class.md) 초기화하는 데 사용되는 *T* 형식 의 개체의 initializer_list.

*N*<br/>
현재 Vector를 초기화하는 데 사용되는 개체 컬렉션의 요소 수입니다.

*size*<br/>
Vector의 요소 수입니다.

*value*<br/>
현재 Vector의 각 요소를 초기화하는 데 사용되는 값입니다.

*Ⅴ*<br/>
현재 벡터를 초기화하는 데 사용되는 [std::벡터에](../standard-library/vector-class.md) 대한 [Lvalues 및 Rvalues값입니다.](../cpp/lvalues-and-rvalues-visual-cpp.md)

*Ptr*<br/>
현재 Vector를 초기화하는 데 사용되는 `std::vector`에 대한 포인터입니다.

*첫 번째*<br/>
현재 Vector를 초기화하는 데 사용되는 개체 시퀀스의 첫 번째 요소입니다. *첫 번째* 유형은 완벽한 전달을 통해 *전달됩니다.* 자세한 내용은 [RValue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.

*마지막*<br/>
현재 Vector를 초기화하는 데 사용되는 개체 시퀀스의 마지막 요소입니다. *마지막의* 유형은 완벽한 전달을 통해 *전달됩니다.* 자세한 내용은 [RValue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.

## <a name="see-also"></a>참조

[컬렉션(C++/CX)](collections-c-cx.md)<br/>
[플랫폼 네임스페이스](platform-namespace-c-cx.md)<br/>
[C++로 Windows Runtime 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
