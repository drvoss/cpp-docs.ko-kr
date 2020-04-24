---
title: Platform::Collections::VectorView 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorView::VectorView
- COLLECTION/Platform::Collections::VectorView::First
- COLLECTION/Platform::Collections::VectorView::GetAt
- COLLECTION/Platform::Collections::VectorView::GetMany
- COLLECTION/Platform::Collections::VectorView::IndexOf
- COLLECTION/Platform::Collections::VectorView::Size
helpviewer_keywords:
- VectorView Class
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
ms.openlocfilehash: 7f12c7b926cd8d3d8fc892cff6f2245e7c216219
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032228"
---
# <a name="platformcollectionsvectorview-class"></a>Platform::Collections::VectorView 클래스

인덱스로 각각 액세스할 수 있는 순차 개체 컬렉션의 읽기 전용 보기를 나타냅니다. 템플릿 매개 변수로 지정된 컬렉션의 각 개체 형식입니다.

## <a name="syntax"></a>구문

```
template <typename T, typename E>
   ref class VectorView sealed;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
`VectorView` 개체에 포함된 요소의 형식입니다.

*전자*<br/>
`T`형식의 값을 사용하여 같음을 테스트하기 위한 이진 조건자를 지정합니다. 기본값은 `std::equal_to<T>`입니다.

### <a name="remarks"></a>설명

클래스는 `VectorView` [Windows::Foundation::컬렉션::IVectorView\<T>](/uwp/api/windows.foundation.collections.ivectorview-1) 인터페이스 및 표준 템플릿 라이브러리 이터레이터에 대 한 지원을 구현 합니다.

### <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[벡터뷰::벡터뷰](#ctor)|VectorView 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[벡터뷰::첫 번째](#first)|VectorView의 첫 번째 요소를 지정하는 반복기를 반환합니다.|
|[벡터뷰::GetAt](#getat)|지정된 인덱스가 나타내는 현재 VectorView의 요소를 검색합니다.|
|[벡터뷰::GetMany](#getmany)|현재 VectorView에서 지정된 인덱스부터 시작하여 일련의 항목을 검색합니다.|
|[벡터뷰::인덱스](#indexof)|현재 VectorView에서 지정한 항목을 검색하고 있는 경우 항목의 인덱스를 반환합니다.|
|[VectorView::Size](#size)|현재 VectorView 개체의 요소 수를 반환합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`VectorView`

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Platform::Collections

## <a name="vectorviewfirst-method"></a><a name="first"></a>벡터뷰::첫 번째 방법

VectorView의 첫 번째 요소를 지정하는 반복기를 반환합니다.

### <a name="syntax"></a>구문

```

virtual Windows::Foundation::Collections::IIterator<T>^
   First();
```

### <a name="return-value"></a>Return Value

VectorView의 첫 번째 요소를 지정하는 반복기입니다.

### <a name="remarks"></a>설명

First()에서 반환되는 이터레이터를 유지하는 편리한 방법은 **자동** 형식 공제 키워드로 선언된 변수에 반환 값을 할당하는 것입니다. `auto x = myVectorView->First();`)을 입력합니다.

## <a name="vectorviewgetat-method"></a><a name="getat"></a>벡터뷰::GetAt 방법

지정된 인덱스가 나타내는 현재 VectorView의 요소를 검색합니다.

### <a name="syntax"></a>구문

```

T GetAt(
   UInt32 index
);
```

### <a name="parameters"></a>매개 변수

*index*<br/>
VectorView 개체의 특정 요소를 지정하는 0부터 시작하는 부호 없는 정수입니다.

### <a name="return-value"></a>Return Value

`index` 매개 변수로 지정된 요소입니다. 요소 유형은 VectorView 템플릿 매개 변수 *T에*의해 지정됩니다.

## <a name="vectorviewgetmany-method"></a><a name="getmany"></a>벡터뷰::GetMany 방법

현재 VectorView에서 지정된 인덱스부터 시작하여 일련의 항목을 검색합니다.

### <a name="syntax"></a>구문

```

virtual unsigned int GetMany(
   unsigned int startIndex,
   ::Platform::WriteOnlyArray<T>^ dest
);
```

### <a name="parameters"></a>매개 변수

*startIndex*<br/>
검색할 항목 시작 부분의 0부터 시작하는 인덱스입니다.

*dest*<br/>
이 작업이 완료되면 `startIndex`로 지정된 요소에서 시작해 VectorView의 마지막 요소에서 끝나는 항목의 배열입니다.

### <a name="return-value"></a>Return Value

검색된 항목의 수입니다.

## <a name="vectorviewindexof-method"></a><a name="indexof"></a>벡터뷰::인덱스오브 메소드

현재 VectorView에서 지정한 항목을 검색하고 있는 경우 항목의 인덱스를 반환합니다.

### <a name="syntax"></a>구문

```

virtual bool IndexOf(
   T value,
   unsigned int* index
);
```

### <a name="parameters"></a>매개 변수

*value*<br/>
찾을 항목입니다.

*index*<br/>
매개 변수 `value`가 있으면 0부터 시작하는 항목의 인덱스이고, 그렇지 않으면 0입니다.

*항목이* 항목의 첫 번째 `VectorView` 요소이거나 항목을 찾을 수 없는 경우 인덱스 매개 변수는 0입니다. 반환 값이 **true이면**항목이 발견되었으며 첫 번째 요소입니다. 그렇지 않으면 항목을 찾을 수 없습니다.

### <a name="return-value"></a>Return Value

지정된 항목이 발견되면 **true;** 그렇지 **않으면, 거짓**.

## <a name="vectorviewsize-method"></a><a name="size"></a>벡터뷰::크기 방법

현재 VectorView 개체의 요소 수를 반환합니다.

### <a name="syntax"></a>구문

```

virtual property unsigned int Size;
```

### <a name="return-value"></a>Return Value

현재 VectorView의 요소 수입니다.

## <a name="vectorviewvectorview-constructor"></a><a name="ctor"></a>벡터뷰::벡터뷰 생성자

VectorView 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```
VectorView();
explicit VectorView(
   UInt32 size
);
VectorView(
   UInt32 size,
   T value
);
explicit VectorView(
   const ::std::vector<T>& v
);
explicit VectorView(
   ::std::vector<T>&& v
);
VectorView(
   const T * ptr,
   UInt32 size
);

template <
   size_t N
>
explicit VectorView(
   const T (&arr)[N]
);

template <
   size_t N
>
explicit VectorView(
   const ::std::array<T,
   N>& a
);

explicit VectorView(
   const ::Platform::Array<T>^ arr
);

template <
   typename InIt
>
VectorView(
   InItfirst,
   InItlast
);

VectorView(
   std::initializer_list<T> il
);
```

### <a name="parameters"></a>매개 변수

*Init*<br/>
현재 VectorView를 초기화하는 데 사용되는 개체 컬렉션의 형식입니다.

*Il*<br/>
[std::initializer_list](../standard-library/initializer-list-class.md) 그 요소가 VectorView를 초기화하는 데 사용됩니다.

*N*<br/>
현재 VectorView를 초기화하는 데 사용되는 개체 컬렉션의 요소 수입니다.

*size*<br/>
VectorView의 요소 수입니다.

*value*<br/>
현재 VectorView의 각 요소를 초기화하는 데 사용되는 값입니다.

*Ⅴ*<br/>
현재 VectorView를 초기화하는 데 사용되는 [std::벡터에](../standard-library/vector-class.md) 대한 [Lvalues 및 Rvalues값입니다.](../cpp/lvalues-and-rvalues-visual-cpp.md)

*Ptr*<br/>
현재 VectorView를 초기화하는 데 사용되는 `std::vector`에 대한 포인터입니다.

*도착*<br/>
[플랫폼::현재](../cppcx/platform-array-class.md) VectorView를 초기화하는 데 사용되는 배열 개체입니다.

*a.*<br/>
현재 VectorView를 초기화하는 데 사용되는 [std::배열](../standard-library/array-class-stl.md) 개체입니다.

*첫 번째*<br/>
현재 VectorView를 초기화하는 데 사용되는 개체 시퀀스의 첫 번째 요소입니다. 유형은 `first` 완벽한 전달을 통해 *전달됩니다.* 자세한 내용은 [RValue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.

*마지막*<br/>
현재 VectorView를 초기화하는 데 사용되는 개체 시퀀스의 마지막 요소입니다. 유형은 `last` 완벽한 전달을 통해 *전달됩니다.* 자세한 내용은 [RValue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.

## <a name="see-also"></a>참조

[플랫폼 네임스페이스](platform-namespace-c-cx.md)<br/>
[C++로 Windows Runtime 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
