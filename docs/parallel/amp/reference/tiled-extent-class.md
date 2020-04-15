---
title: tiled_extent 클래스
ms.date: 11/04/2016
f1_keywords:
- tiled_extent
- AMP/tiled_extent
- AMP/Concurrency::tiled_extent::tiled_extent
- AMP/Concurrency::tiled_extent::get_tile_extent
- AMP/Concurrency::tiled_extent::pad
- AMP/Concurrency::tiled_extent::truncate
- AMP/Concurrency::tiled_extent::tile_dim0
- AMP/Concurrency::tiled_extent::tile_dim1
- AMP/Concurrency::tiled_extent::tile_dim2
- AMP/Concurrency::tiled_extent::tile_extent
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
ms.openlocfilehash: ce2710da1a745efedcd6e9e524355eda41e26de2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374705"
---
# <a name="tiled_extent-class"></a>tiled_extent 클래스

개체는 `tiled_extent` 익스텐트 공간을 1차원, 2차원 또는 3차원 타일로 세분화하는 1~3차원 `extent` 객체입니다.

## <a name="syntax"></a>구문

```cpp
template <
    int _Dim0,
    int _Dim1,
    int _Dim2
>
class tiled_extent : public Concurrency::extent<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;

template <
    int _Dim0
>
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;
```

### <a name="parameters"></a>매개 변수

*_Dim0*<br/>
가장 중요한 차원의 길이입니다.

*_Dim1*<br/>
다음으로 가장 중요한 차원의 길이입니다.

*_Dim2*<br/>
가장 유의한 차원의 길이입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[tiled_extent 생성자](#ctor)|`tiled_extent` 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[get_tile_extent](#get_tile_extent)|`tiled_extent` 템플릿 `extent` 인수 및 `_Dim1` `_Dim2`의 값을 캡처하는 `_Dim0`개체를 반환합니다.|
|[패드](#pad)|익스텐션이 타일 치수에 따라 균등하게 나눌 수 있도록 조정된 새 `tiled_extent` 객체를 반환합니다.|
|[truncate](#truncate)|익스텐션이 타일 치수에 따라 균등하게 나눌 수 있도록 조정된 새 `tiled_extent` 객체를 반환합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[연산자 =](#operator_eq)|지정된 `tiled_index` 개체의 내용을 이 개체에 복사합니다.|

### <a name="public-constants"></a>공용 상수

|속성|Description|
|----------|-----------------|
|[tile_dim0 상수](#tile_dim0)|가장 중요한 차원의 길이를 저장합니다.|
|[tile_dim1 상수](#tile_dim1)|가장 중요한 차원의 길이를 저장합니다.|
|[tile_dim2 상수](#tile_dim2)|가장 중요한 차원의 길이를 저장합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[tile_extent](#tile_extent)|`tiled_extent` 템플릿 `extent` 인수 의 값을 캡처하는 개체를 `_Dim0` `_Dim1`가져옵니다. `_Dim2`|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`extent`

`tiled_extent`

## <a name="requirements"></a>요구 사항

**헤더:** amp.h

**네임스페이스:** 동시성

## <a name="tiled_extent-constructor"></a><a name="ctor"> </a> tiled_extent 생성자

`tiled_extent` 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
tiled_extent();

tiled_extent(
    const Concurrency::extent<rank>& _Other );

tiled_extent(
    const tiled_extent& _Other );
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
`extent` 복사할 `tiled_extent` 개체입니다.

## <a name="get_tile_extent"></a><a name="get_tile_extent"> </a> get_tile_extent

`tiled_extent` 템플릿 `extent` 인수 및 `_Dim1` `_Dim2`의 값을 캡처하는 `_Dim0`개체를 반환합니다.

### <a name="syntax"></a>구문

```cpp
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>Return Value

이 `extent` `tiled_extent` 인스턴스의 차원을 캡처하는 개체입니다.

## <a name="pad"></a><a name="pad"> </a> 패드

익스텐션이 타일 치수에 따라 균등하게 나눌 수 있도록 조정된 새 `tiled_extent` 객체를 반환합니다.

### <a name="syntax"></a>구문

```cpp
tiled_extent pad() const;
```

### <a name="return-value"></a>Return Value

값별로 `tiled_extent` 새 개체입니다.

## <a name="truncate"></a><a name="truncate"> </a> 트런케이트

익스텐션이 타일 치수에 따라 균등하게 나눌 수 있도록 조정된 새 `tiled_extent` 객체를 반환합니다.

### <a name="syntax"></a>구문

```cpp
tiled_extent truncate() const;
```

### <a name="return-value"></a>Return Value

익스텐션이 타일 치수에 따라 균등하게 나눌 수 있도록 조정된 새 `tiled_extent` 객체를 반환합니다.

## <a name="operator"></a><a name="operator_eq"> </a> 연산자 =

지정된 `tiled_index` 개체의 내용을 이 개체에 복사합니다.

### <a name="syntax"></a>구문

```cpp
tiled_extent&  operator= (
    const tiled_extent& _Other ) restrict (amp, cpu);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
복사할 `tiled_index` 개체입니다.

### <a name="return-value"></a>Return Value

이 `tiled_index` 인스턴스에 대한 참조입니다.

## <a name="tile_dim0"></a><a name="tile_dim0"> </a> tile_dim0

가장 중요한 차원의 길이를 저장합니다.

### <a name="syntax"></a>구문

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a><a name="tile_dim1"> </a> tile_dim1

가장 중요한 차원의 길이를 저장합니다.

### <a name="syntax"></a>구문

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a><a name="tile_dim2"> </a> tile_dim2

가장 중요한 차원의 길이를 저장합니다.

### <a name="syntax"></a>구문

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_extent"></a><a name="tile_extent"> </a> tile_extent

`tiled_extent` 템플릿 `extent` 인수 의 값을 캡처하는 개체를 `_Dim0` `_Dim1`가져옵니다. `_Dim2`

### <a name="syntax"></a>구문

```cpp
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;
```

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
