---
title: Concurrency 네임스페이스 연산자(AMP)
ms.date: 11/04/2016
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
ms.openlocfilehash: 3b536f75e4ef6405b60d45e89290a7d97a01707d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883731"
---
# <a name="concurrency-namespace-operators-amp"></a>Concurrency 네임스페이스 연산자(AMP)

||||
|-|-|-|
|[operator!=](#operator_neq)|[operator%](#operator_mod)|[operator*](#operator_star)|
|[operator+](#operator_add)|[operator-](#operator-)|[operator/](#operator_div)|
|[연산자==](#operator_eq_eq)|

## <a name="operator_eq_eq"></a>  operator==

지정 된 인수가 같은지 여부를 확인 합니다.

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
비교할 튜플 중 하나입니다.

*_Rhs*<br/>
비교할 튜플 중 하나입니다.

### <a name="return-value"></a>반환 값

튜플이 같으면 **true** 이 고, 그렇지 않으면입니다. 그렇지 않으면 **false**입니다.

## <a name="operator_neq"></a>  operator!=

지정 된 인수가 같지 않은지 여부를 확인 합니다.

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
비교할 튜플 중 하나입니다.

*_Rhs*<br/>
비교할 튜플 중 하나입니다.

### <a name="return-value"></a>반환 값

튜플이 다르면 **true** 이 고, 그렇지 않으면입니다. 그렇지 않으면 **false**입니다.

## <a name="operator_add"></a>  operator+

지정 된 인수의 구성 요소 단위 합계를 계산 합니다.

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

### <a name="return-value"></a>반환 값

지정 된 인수의 구성 요소 단위 합계입니다.

## <a name="operator-"></a>  operator-

지정 된 인수 사이의 구성 요소 단위 차이를 계산 합니다.

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
뺄 인수입니다.

*_Rhs*<br/>
뺄 인수입니다.

### <a name="return-value"></a>반환 값

지정 된 인수 사이의 구성 요소 단위 차이입니다.

## <a name="operator_star"></a>  operator*

지정 된 인수의 구성 요소 단위 곱을 계산 합니다.

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
곱할 튜플 중 하나입니다.

*_Rhs*<br/>
곱할 튜플 중 하나입니다.

### <a name="return-value"></a>반환 값

지정 된 인수의 구성 요소 단위 곱입니다.

## <a name="operator_div"></a>  operator/

지정 된 인수의 구성 요소별 몫을 계산 합니다.

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
나눌 튜플입니다.

*_Rhs*<br/>
나눌 튜플입니다.

### <a name="return-value"></a>반환 값

지정 된 인수의 구성 요소별 몫입니다.

## <a name="operator_mod"></a>  operator%

지정 된 두 번째 인수를 기준으로 지정 된 첫 번째 인수의 모듈러스를 계산 합니다.

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
모듈로 계산 되는 튜플입니다.

*_Rhs*<br/>
모듈로 이동할 튜플입니다.

### <a name="return-value"></a>반환 값

지정 된 첫 번째 인수 모듈러스의 결과는 두 번째 지정 된 인수입니다.

## <a name="see-also"></a>참고 항목

[Concurrency 네임 스페이스](concurrency-namespace-cpp-amp.md)
