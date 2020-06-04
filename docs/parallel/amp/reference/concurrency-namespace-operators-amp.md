---
title: Concurrency 네임스페이스 연산자(AMP)
ms.date: 11/04/2016
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
ms.openlocfilehash: c4086029b71d71091a12b9b6023cc6098faf2f85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376297"
---
# <a name="concurrency-namespace-operators-amp"></a>Concurrency 네임스페이스 연산자(AMP)

||||
|-|-|-|
|[연산자!=](#operator_neq)|[연산자 비율](#operator_mod)|[연산자*](#operator_star)|
|[연산자+](#operator_add)|[연산자-](#operator-)|[연산자/](#operator_div)|
|[연산자==](#operator_eq_eq)|

## <a name="operator"></a><a name="operator_eq_eq"></a>연산자==

지정된 인수가 같는지 여부를 결정합니다.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
bool operator== (
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
비교할 수 있는 틀 중 하나입니다.

*_Rhs*<br/>
비교할 수 있는 틀 중 하나입니다.

### <a name="return-value"></a>Return Value

tuples가 같으면 **true;** 그렇지 **않으면, 거짓**.

## <a name="operator"></a><a name="operator_neq"></a>연산자!=

지정된 인수가 같지 않은지 여부를 결정합니다.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
bool operator!= (
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
비교할 수 있는 틀 중 하나입니다.

*_Rhs*<br/>
비교할 수 있는 틀 중 하나입니다.

### <a name="return-value"></a>Return Value

tuples가 같지 않은 경우 **true;** 그렇지 **않으면, 거짓**.

## <a name="operator"></a><a name="operator_add"></a>연산자+

지정된 인수의 구성 요소 별 합계를 계산합니다.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
추가할 인수 중 하나입니다.

*_Rhs*<br/>
추가할 인수 중 하나입니다.

### <a name="return-value"></a>Return Value

지정된 인수의 구성 요소 별 합계입니다.

## <a name="operator-"></a><a name="operator-"></a>연산자-

지정된 인수 간의 구성 요소 별 차이를 계산합니다.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
빼는 인수입니다.

*_Rhs*<br/>
빼는 인수입니다.

### <a name="return-value"></a>Return Value

지정된 인수 간의 구성 요소 별 차이입니다.

## <a name="operator"></a><a name="operator_star"></a>연산자*

지정된 인수의 구성 요소 별 곱을 계산합니다.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator*(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator*(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp, cpu);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
곱할 수 있는 투플 중 하나입니다.

*_Rhs*<br/>
곱할 수 있는 투플 중 하나입니다.

### <a name="return-value"></a>Return Value

지정된 인수의 구성 요소 별 제품입니다.

## <a name="operator"></a><a name="operator_div"></a>연산자/

지정된 인수의 구성 요소 별 몫을 계산합니다.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator/(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator/(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
나눌 튜플.

*_Rhs*<br/>
로 나눌 튜플.

### <a name="return-value"></a>Return Value

지정된 인수의 구성 요소 별 몫입니다.

## <a name="operator"></a><a name="operator_mod"></a>연산자 비율

두 번째 지정된 인수에 의해 첫 번째 지정된 인수의 계수를 계산합니다.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator%(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator%(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
조절자가 계산되는 튜플입니다.

*_Rhs*<br/>
튜플에 의해 조절.

### <a name="return-value"></a>Return Value

첫 번째 지정된 인수의 결과는 두 번째 지정된 인수를 계수합니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace-cpp-amp.md)
