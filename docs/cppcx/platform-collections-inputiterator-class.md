---
title: Platform::Collections::InputIterator 클래스
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
ms.openlocfilehash: 92f9b15f474a5aa3d063f0ccfb663f56baf8de31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354556"
---
# <a name="platformcollectionsinputiterator-class"></a>Platform::Collections::InputIterator 클래스

Windows 런타임에서 파생된 컬렉션에 대한 표준 템플릿 라이브러리 입력을 제공합니다.

## <a name="syntax"></a>구문

```
template <typename X>
class InputIterator;
```

#### <a name="parameters"></a>매개 변수

*Ⅹ*<br/>
InputIterator 템플릿 클래스의 형식 이름입니다.

### <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|`difference_type`|포인터 차이(ptrdiff_t)입니다.|
|`iterator_category`|입력 반복기의 범주(::std::input_iterator_tag)입니다.|
|`pointer`|에 대한 포인터`const X`|
|`reference`|`const X`에 대한 참조입니다.|
|`value_type`|`X` 형식 이름입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[입력이터::입력이터](#ctor)|InputIterator 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[입력이터::연산자!= 연산자](#operator-inequality)|현재 InputIterator가 지정된 InputIterator와 같지 않은지 여부를 나타냅니다.|
|[InputIterator::operator* 연산자](#operator-dereference)|현재 InputIterator가 지정하는 요소에 대한 참조를 검색합니다.|
|[입력이터::연산자++ 연산자](#operator-increment)|현재 InputIterator를 증가시킵니다.|
|[입력이터::연산자== 연산자](#operator-equality)|현재 InputIterator가 지정된 InputIterator와 같은지 여부를 나타냅니다.|
|[입력이터:운영자-> 연산자](#operator-arrow)|현재 InputIterator가 참조하는 요소의 주소를 검색합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`InputIterator`

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Platform::Collections

## <a name="inputiteratorinputiterator-constructor"></a><a name="ctor"></a>입력이터::입력이터 생성자

InputIterator 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```
InputIterator();
explicit InputIterator(Windows::Foundation::Collections<X>^ iterator);
```

### <a name="parameters"></a>매개 변수

*반복기*<br/>
반복기 개체입니다.

## <a name="inputiteratoroperator-gt-operator"></a><a name="operator-arrow"></a>입력이터::연산자-&gt; 연산자

현재 InputIterator가 지정하는 요소의 주소를 검색합니다.

### <a name="syntax"></a>구문

```
pointer operator->() const;
```

### <a name="return-value"></a>Return Value

현재 InputIterator가 지정하는 요소의 주소입니다.

## <a name="inputiteratoroperator-operator"></a><a name="operator-dereference"></a>입력이터::연산자\*

현재 InputIterator가 지정하는 요소에 대한 참조를 검색합니다.

### <a name="syntax"></a>구문

```
reference operator*() const;
```

### <a name="return-value"></a>Return Value

현재 InputIterator가 지정하는 요소입니다.

## <a name="inputiteratoroperator-operator"></a><a name="operator-equality"></a>입력이터::연산자== 연산자

현재 InputIterator가 지정된 InputIterator와 같은지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```
bool operator== (const InputIterator& other) const;
```

### <a name="parameters"></a>매개 변수

*다른*<br/>
다른 InputIterator입니다.

### <a name="return-value"></a>Return Value

**true** 현재 InputIterator가 *다른*입력과 같으면; 그렇지 **않으면, 거짓**.

## <a name="inputiteratoroperator-operator"></a><a name="operator-increment"></a>입력이터::연산자++ 연산자

현재 InputIterator를 증가시킵니다.

### <a name="syntax"></a>구문

```
InputIterator& operator++();
InputIterator operator++(int);
```

### <a name="return-value"></a>Return Value

첫 번째 구문은 현재 InputIterator를 증가시킨 다음 반환합니다. 두 번째 구문은 현재 InputIterator의 복사본을 반환한 다음 현재 InputIterator를 증가시킵니다.

### <a name="remarks"></a>설명

첫 번째 InputIterator 구문은 현재 InputIterator를 사전에 증가시킵니다.

두 번째 구문은 현재 InputIterator를 사후에 증가시킵니다. 두 번째 구문의 `int` 형식은 실제 정수 연산자가 아니라 후위 증가 연산을 나타냅니다.

## <a name="inputiteratoroperator-operator"></a><a name="operator-inequality"></a>입력이터::연산자!= 연산자

현재 InputIterator가 지정된 InputIterator와 같지 않은지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```
bool operator!=(const InputIterator& other) const;
```

### <a name="parameters"></a>매개 변수

*다른*<br/>
다른 InputIterator입니다.

### <a name="return-value"></a>Return Value

**true 현재** InputIterator가 *다른*입력과 같지 않은 경우; 그렇지 **않으면, 거짓**.

## <a name="see-also"></a>참고 항목

[플랫폼 네임스페이스](platform-namespace-c-cx.md)
