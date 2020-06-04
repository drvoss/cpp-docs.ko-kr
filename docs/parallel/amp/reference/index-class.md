---
title: index 클래스
ms.date: 03/27/2019
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
ms.openlocfilehash: 50222015e6b365dc161fd4334067c26c7f288337
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365161"
---
# <a name="index-class"></a>index 클래스

*N*차원 인덱스 벡터를 정의합니다.

## <a name="syntax"></a>구문

```cpp
template <int _Rank>
class index;
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
순위 또는 차원 의 수입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[인덱스 생성자](#index_ctor)|`index` 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[연산자-](#operator--)|개체의 각 요소를 감소시입니다. `index`|
|[연산자==](#operator_mod_eq)|해당 요소가 숫자로 분할될 때 `index` 오브젝트의 각 요소의 모듈러스(나머지)를 계산합니다.|
|[연산자*=](#operator_star_eq)|`index` 개체의 각 요소에 숫자를 곱합니다.|
|[연산자/=](#operator_div_eq)|개체의 `index` 각 요소를 숫자로 나눕니다.|
|[인덱스::연산자\[\]](#operator_at)|지정된 인덱스에 있는 요소를 반환합니다.|
|[연산자++](#operator_add_add)|개체의 각 요소를 증분합니다. `index`|
|[연산자+=](#operator_add_eq)|개체의 각 요소에 지정된 `index` 숫자를 추가합니다.|
|[연산자 =](#operator_eq)|지정된 `index` 개체의 내용을 이 개체에 복사합니다.|
|[연산자-=](#operator_-_eq)|`index` 개체의 각 요소에서 지정된 숫자를 뺍니다.|

### <a name="public-constants"></a>공용 상수

|속성|Description|
|----------|-----------------|
|[순위 상수](#rank)|개체의 순위를 `index` 저장합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`index`

## <a name="remarks"></a>설명

구조는 `index` *N* 차원 공간에서 고유한 위치를 지정하는 *N*정수의 좌표 벡터를 나타냅니다. 벡터의 값은 가장 중요한 값에서 가장 중요하지 않은 값으로 정렬됩니다. [연산자=를](#operator_eq)사용하여 구성 요소의 값을 검색할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** amp.h

**네임스페이스:** 동시성

## <a name="index-constructor"></a><a name="index_ctor"></a>인덱스 생성자

인덱스 클래스의 새 인스턴스를 초기화합니다.

```cpp
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Array*<br/>
순위 값이 있는 1차원 배열입니다.

*_I*<br/>
1차원 인덱스의 인덱스 위치입니다.

*_I0*<br/>
가장 중요한 차원의 길이입니다.

*_I1*<br/>
다음으로 가장 중요한 차원의 길이입니다.

*_I2*<br/>
가장 유의한 차원의 길이입니다.

*_Other*<br/>
새 인덱스 개체의 기반이 되는 인덱스 개체입니다.

## <a name="operator--"></a><a name="operator--"></a>연산자-

인덱스 개체의 각 요소를 감소합니다.

```cpp
index<_Rank>& operator--() restrict(amp,cpu);

index operator--(
   int
) restrict(amp,cpu);
```

### <a name="return-values"></a>반환 값

접두사 연산자의 경우 인덱스 개체(*this)입니다. 접미사 연산자의 경우 새 인덱스 개체입니다.

## <a name="operator"></a><a name="operator_mod_eq"></a>연산자==

index 개체의 각 요소를 지정된 숫자로 나눌 때의 모듈러스(나머지)를 계산합니다.

```cpp
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
모듈러스(나머지)를 찾기 위해 나눌 숫자입니다.

## <a name="return-value"></a>Return Value

index 개체입니다.

## <a name="operator"></a><a name="operator_star_eq"></a>연산자*=

인덱스 개체의 각 요소에 지정된 숫자에 곱합니다.

```cpp
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
곱할 수 입니다.

## <a name="operator"></a><a name="operator_div_eq"></a>연산자/=

인덱스 개체의 각 요소를 지정된 숫자로 나눕니다.

```cpp
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
나눌 수 있습니다.

## <a name="operator"></a><a name="operator_at"></a>연산자\[\]

지정된 위치에서 인덱스의 구성 요소를 반환합니다.

```cpp
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
0에서 계급을 뺀 1의 정수입니다.

### <a name="return-value"></a>Return Value

지정된 인덱스에 있는 요소입니다.

### <a name="remarks"></a>설명

다음 예제에는 인덱스의 구성 요소 값이 표시됩니다.

```cpp
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator"></a><a name="operator_add_add"></a>연산자++

인덱스 개체의 각 요소를 증분합니다.

```cpp
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```

### <a name="return-value"></a>Return Value

접두사 연산자의 경우 인덱스 개체(*this)입니다. 접미사 연산자의 경우 새 인덱스 개체입니다.

## <a name="operator"></a><a name="operator_add_eq"></a>연산자+=

인덱스 개체의 각 요소에 지정된 숫자를 추가합니다.

```cpp
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
추가할 번호입니다.

### <a name="return-value"></a>Return Value

index 개체입니다.

## <a name="operator"></a><a name="operator_eq"></a>연산자 =

지정된 인덱스 개체의 내용을 이 개체에 복사합니다.

```cpp
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
복사할 인덱스 개체입니다.

### <a name="return-value"></a>Return Value

이 인덱스 개체에 대한 참조입니다.

## <a name="operator-"></a><a name="operator_-_eq"></a>연산자-=

인덱스 개체의 각 요소에서 지정된 숫자를 뺍니다.

```cpp
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
빼는 숫자입니다.

### <a name="return-value"></a>Return Value

index 개체입니다.

## <a name="rank"></a><a name="rank"></a>순위

index 개체의 차수를 가져옵니다.

```cpp
static const int rank = _Rank;
```

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
