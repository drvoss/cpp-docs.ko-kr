---
title: Platform::Array 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Array
- VCCORLIB/Platform::Array::Value
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
ms.openlocfilehash: d625d80df67a3c8207467ad629afd4c2bf88db18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318662"
---
# <a name="platformarray-class"></a>Platform::Array 클래스

ABI(애플리케이션 이진 인터페이스)를 통해 받고 전달할 수 있는 수정 가능한 1차원 배열을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template <typename T>
private ref class Array<TArg, 1> :
    public WriteOnlyArray<TArg, 1>,
    public IBoxArray<TArg>
```

### <a name="members"></a>멤버

플랫폼::배열은 [플랫폼::WriteOnlyArray 클래스에서](../cppcx/platform-writeonlyarray-class.md) 모든 메서드를 `Value` 상속 하 고 [플랫폼::IBoxArray 인터페이스의](../cppcx/platform-iboxarray-interface.md)속성을 구현 합니다.

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[Array 생성자](#ctor)|클래스 템플릿 매개 변수 *T에*의해 지정된 형식의 1차원 수정 가능한 배열을 초기화합니다.|

### <a name="methods"></a>메서드

[플랫폼:::WriteOnlyArray 클래스](../cppcx/platform-writeonlyarray-class.md)를 참조하십시오.

### <a name="properties"></a>속성

|||
|-|-|
|[배열 ::값](#value)|현재 배열에 대한 핸들을 검색합니다.|

### <a name="remarks"></a>설명

Array 클래스는 봉인되므로 상속할 수 없습니다.

Windows 런타임 형식 시스템은 들쭉날쭉한 배열의 개념을 지원하지 않으므로 IVector<\<플랫폼::배열 T>> 반환 값 또는 메서드 매개 변수로 전달할 수 없습니다. ABI 전반에서 가변 배열 또는 시퀀스의 시퀀스를 전달하려면 `IVector<IVector<T>^>`를 사용합니다.

플랫폼:::Array를 사용하는 시기와 방법에 대한 자세한 내용은 [배열 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)를 참조하십시오.

이 클래스는 컴파일러가 자동으로 포함하는 vccorlib.h 헤더에 정의됩니다. IntelliSense에는 표시되지만 platform.winmd에 정의된 공용 형식이 아니기 때문에 개체 브라우저에서는 볼 수 없습니다.

### <a name="requirements"></a>요구 사항

컴파일러 옵션: **/ZW**

## <a name="array-constructors"></a><a name="ctor"></a>배열 생성자

클래스 템플릿 매개 변수 *T에*의해 지정된 형식의 1차원 수정 가능한 배열을 초기화합니다.

## <a name="syntax"></a>구문

```cpp
Array(unsigned int size);
Array(T* data, unsigned int size);
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스 템플릿 매개 변수입니다.

*크기*<br/>
배열의 요소 수입니다.

*데이터*<br/>
이 Array 개체를 초기화하는 데 사용되는 `T` 형식 데이터의 배열에 대한 포인터입니다.

### <a name="remarks"></a>설명

플랫폼::배열의 인스턴스를 만드는 방법에 대한 자세한 내용은 [배열 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)를 참조하십시오.

## <a name="arrayget-method"></a><a name="get"></a>배열 ::get 방법

지정된 인덱스 위치에서 배열 요소에 대한 참조를 검색합니다.

## <a name="syntax"></a>구문

```cpp
T& get(unsigned int index)  const;
```

#### <a name="parameters"></a>매개 변수

*index*<br/>
배열에서 요소를 식별하는 0부터 시작하는 인덱스를 확인합니다. 최소 인덱스는 0이고 최대 인덱스는 Array `size` [생성자의](#ctor)매개 변수에 의해 지정된 값입니다.

### <a name="return-value"></a>Return Value

`index` 매개 변수로 지정된 배열 요소입니다.

## <a name="arrayvalue-property"></a><a name="value"></a>배열::값 속성

현재 배열에 대한 핸들을 검색합니다.

## <a name="syntax"></a>구문

```cpp
property Array^ Value;
```

### <a name="return-value"></a>Return Value

현재 배열에 대한 핸들입니다.

## <a name="see-also"></a>참고 항목

[Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)<br/>
[Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
