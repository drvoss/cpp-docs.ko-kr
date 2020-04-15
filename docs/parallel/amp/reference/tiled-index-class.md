---
title: tiled_index 클래스
ms.date: 03/27/2019
f1_keywords:
- tiled_index
- AMP/tiled_index
- AMP/Concurrency::tiled_index::tiled_index
- AMP/Concurrency::tiled_index::get_tile_extent
- AMP/Concurrency::tiled_index::barrier
- AMP/Concurrency::tiled_index::global
- AMP/Concurrency::tiled_index::local
- AMP/Concurrency::tiled_index::rank
- AMP/Concurrency::tiled_index::tile
- AMP/Concurrency::tiled_index::tile_dim0
- AMP/Concurrency::tiled_index::tile_dim1
- AMP/Concurrency::tiled_index::tile_dim2
- AMP/Concurrency::tiled_index::tile_origin
- AMP/Concurrency::tiled_index::tile_extent
helpviewer_keywords:
- tiled_index class
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
ms.openlocfilehash: 46a6b3548526f0917c4e022a12bf859242e70b20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375476"
---
# <a name="tiled_index-class"></a>tiled_index 클래스

[tiled_extent](tiled-extent-class.md) 개체에 인덱스를 제공합니다. 이 클래스에는 로컬 타일 원본을 기준으로 하고 전역 원본을 기준으로 하는 요소에 액세스하는 속성이 있습니다. 타일로 배열된 공간에 대한 자세한 내용은 [타일 사용을](../../../parallel/amp/using-tiles.md)참조하십시오.

## <a name="syntax"></a>구문

```cpp
template <
    int _Dim0,
    int _Dim1 = 0,
    int _Dim2 = 0
>
class tiled_index : public _Tiled_index_base<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;

template <
    int _Dim0
>
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;
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
|[tiled_index 생성자](#ctor)|`tile_index` 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[get_tile_extent](#tiled_index__get_tile_extent)|`tiled_index` 템플릿 인수 `_Dim0`및 `_Dim1` `_Dim2`의 값이 있는 [익스텐트](extent-class.md) 개체를 반환합니다.|

### <a name="public-constants"></a>공용 상수

|속성|Description|
|----------|-----------------|
|[배리어 상수](#tiled_index__barrier)|현재 스레드 타일에 장벽을 나타내는 [tile_barrier](tile-barrier-class.md) 개체를 저장합니다.|
|||
|[글로벌 상수](#tiled_index__global)|그리드 [개체의](index-class.md) 전역 인덱스를 나타내는 순위 1, 2 또는 3의 인덱스 개체를 저장합니다.|
|[local 상수](#tiled_index__local)|tiled_extent `index` 개체의 현재 타일에서 상대 인덱스를 나타내는 순위 1, [tiled_extent](tiled-extent-class.md) 2 또는 3의 개체를 저장합니다.|
|[순위 상수](#tiled_index__rank)|개체의 순위를 `tiled_index` 저장합니다.|
|[타일 상수](#tiled_index__tile)|객체의 `index` 현재 타일의 좌표를 나타내는 1, 2 또는 3의 `tiled_extent` 객체를 저장합니다.|
|[tile_dim0 상수](#tiled_index__tile_dim0)|가장 중요한 차원의 길이를 저장합니다.|
|[tile_dim1 상수](#tiled_index__tile_dim1)|가장 중요한 차원의 길이를 저장합니다.|
|[tile_dim2 상수](#tiled_index__tile_dim2)|가장 중요한 차원의 길이를 저장합니다.|
|[tile_origin 상수](#tiled_index__tile_origin)|`index` 현재 타일의 원점의 전역 좌표를 나타내는 1, 2 또는 3의 `tiled_extent` 객체를 개체에 저장합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[tile_extent](#tile_extent)|`tiled_index` 템플릿 인수 `tiled_index` 템플릿 인수 `_Dim0`의 값이 있는 [익스텐트](extent-class.md) 개체를 가져옵니다. `_Dim1` `_Dim2`|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_Tiled_index_base`

`tiled_index`

## <a name="requirements"></a>요구 사항

**헤더:** amp.h

**네임스페이스:** 동시성

## <a name="tiled_index-constructor"></a><a name="ctor"></a>tiled_index 생성자

`tiled_index` 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
tiled_index(
    const index<rank>& _Global,
    const index<rank>& _Local,
    const index<rank>& _Tile,
    const index<rank>& _Tile_origin,
    const tile_barrier& _Barrier ) restrict(amp,cpu);

tiled_index(
    const tiled_index& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Global*<br/>
구성된 `tiled_index`의 글로벌 [인덱스입니다.](index-class.md)

*_Local*<br/>
구성된 로컬 [인덱스](index-class.md)`tiled_index`

*_Tile*<br/>
구성된 타일 [인덱스](index-class.md)`tiled_index`

*_Tile_origin*<br/>
구성된 타일 원원 [인덱스](index-class.md)`tiled_index`

*_Barrier*<br/>
구성된 [tile_barrier](tile-barrier-class.md) `tiled_index`tile_barrier 개체입니다.

*_Other*<br/>
생성된 `tile_index` `tiled_index`에 복사할 개체입니다.

### <a name="overloads"></a>Overloads

|||
|-|-|
|속성|Description|
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|전역 좌표의 타일 `tile_index` 인덱스와 로컬 좌표의 타일의 상대 위치에서 클래스의 새 인스턴스를 초기화합니다. `_Global` 및 `_Tile_origin` 매개 변수가 계산됩니다.|
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|지정된 `tiled_index` 개체를 복사하여 `tile_index` 클래스의 새 인스턴스를 초기화합니다.|

## <a name="get_tile_extent"></a><a name="tiled_index__get_tile_extent"></a>get_tile_extent

`tiled_index` 템플릿 인수 `_Dim0`및 `_Dim1` `_Dim2`의 값이 있는 [익스텐트](extent-class.md) 개체를 반환합니다.

### <a name="syntax"></a>구문

```cpp
extent<rank> get_tile_extent()restrict(amp,cpu);
```

### <a name="return-value"></a>Return Value

`extent` 템플릿 인수 `tiled_index`, `_Dim0` 및 `_Dim1`의 값을 가진 `_Dim2` 개체입니다.

## <a name="barrier"></a><a name="tiled_index__barrier"></a>장벽

현재 스레드 타일에 장벽을 나타내는 [tile_barrier](tile-barrier-class.md) 개체를 저장합니다.

### <a name="syntax"></a>구문

```cpp
const tile_barrier barrier;
```

## <a name="global"></a><a name="tiled_index__global"></a>글로벌

[개체의](index-class.md) 전역 인덱스를 나타내는 순위 1, 2 또는 3의 인덱스 개체를 저장합니다.

### <a name="syntax"></a>구문

```cpp
const index<rank> global;
```

## <a name="local"></a><a name="tiled_index__local"></a>로컬

[tiled_extent](tiled-extent-class.md) 개체의 현재 타일에서 상대 인덱스를 나타내는 순위 1, 2 또는 3의 [인덱스](index-class.md) 개체를 저장합니다.

### <a name="syntax"></a>구문

```cpp
const index<rank> local;
```

## <a name="rank"></a><a name="tiled_index__rank"></a>순위

개체의 순위를 `tiled_index` 저장합니다.

### <a name="syntax"></a>구문

```cpp
static const int rank = _Rank;
```

## <a name="tile"></a><a name="tiled_index__tile"></a>타일

tiled_extent 개체의 현재 타일의 좌표를 나타내는 [인덱스](index-class.md) 개체를 [1,](tiled-extent-class.md) 2 또는 3으로 저장합니다.

### <a name="syntax"></a>구문

```cpp
const index<rank> tile;
```

## <a name="tile_dim0"></a><a name="tiled_index__tile_dim0"></a>tile_dim0

가장 중요한 차원의 길이를 저장합니다.

### <a name="syntax"></a>구문

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a><a name="tiled_index__tile_dim1"></a>tile_dim1

가장 중요한 차원의 길이를 저장합니다.

### <a name="syntax"></a>구문

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a><a name="tiled_index__tile_dim2"></a>tile_dim2

가장 중요한 차원의 길이를 저장합니다.

### <a name="syntax"></a>구문

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_origin"></a><a name="tiled_index__tile_origin"></a>tile_origin

tiled_extent 개체 내에 현재 타일의 원점의 전역 좌표를 나타내는 [인덱스](index-class.md) 개체를 [1,](tiled-extent-class.md) 2 또는 3으로 저장합니다.

### <a name="syntax"></a>구문

```cpp
const index<rank> tile_origin
```

## <a name="tile_extent"></a><a name="tile_extent"></a>tile_extent

`tiled_index` 템플릿 인수 `tiled_index` 템플릿 인수 `_Dim0`의 값이 있는 [익스텐트](extent-class.md) 개체를 가져옵니다. `_Dim1` `_Dim2`

### <a name="syntax"></a>구문

```cpp
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;
```

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
