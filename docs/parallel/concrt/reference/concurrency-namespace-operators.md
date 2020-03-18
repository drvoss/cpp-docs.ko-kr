---
title: concurrency 네임스페이스 연산자
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
ms.openlocfilehash: 676e1936af317a6ab19959f8fd09b1de06dfaf69
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79427376"
---
# <a name="concurrency-namespace-operators"></a>concurrency 네임스페이스 연산자

||||
|-|-|-|
|[operator!=](#operator_neq)|[operator&amp;&amp;](#operator_amp_amp)|[operator&gt;](#operator_gt)|
|[operator&gt;=](#operator_gt_eq)|[operator&lt;](#operator_lt)|[operator&lt;=](#operator_lt_eq)|
|[연산자==](#operator_eq_eq)|[operator&#124;&#124;](#operator_lor)| |

## <a name="operator_lor"></a>operator&#124; &#124; 연산자

인수로 제공된 작업 중 하나가 성공적으로 완료될 경우 완료되는 작업을 만듭니다.

```cpp
template<typename ReturnType>
task<ReturnType> operator||(
    const task<ReturnType>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>> operator||(
    const task<std::vector<ReturnType>>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>> operator||(
    const task<ReturnType>& lhs,
    const task<std::vector<ReturnType>>& rhs);

inline task<void> operator||(
    const task<void>& lhs,
    const task<void>& rhs);
```

### <a name="parameters"></a>매개 변수

*ReturnType*<br/>
반환되는 작업의 형식입니다.

*lhs*<br/>
결과 작업으로 결합할 첫 번째 작업입니다.

*rhs*<br/>
결과 작업으로 결합할 두 번째 작업입니다.

### <a name="return-value"></a>Return Value

입력 작업 중 하나가 성공적으로 완료 되 면 완료 되는 작업입니다. 입력 작업이 `T` 형식이면 이 함수의 출력은 `task<std::vector<T>`가 됩니다. 입력 작업이 `void` 형식이면 이 함수의 출력 작업도 `task<void>`가 됩니다.

### <a name="remarks"></a>설명

두 작업이 모두 취소되거나 예외를 throw하는 경우 반환된 작업은 취소된 상태로 완료되고, 예외가 발생한 경우 예외 중 하나가 해당 작업에 대해 `get()` 또는 `wait()`를 호출할 때 throw됩니다.

## <a name="operator_amp_amp"></a>연산자&amp;&amp; 연산자

인수로 제공 된 두 작업이 모두 성공적으로 완료 되 면 완료 되는 작업을 만듭니다.

```cpp
template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,
    const task<std::vector<ReturnType>>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,
    const task<std::vector<ReturnType>>& rhs);

inline task<void>  operator&&(
    const task<void>& lhs,
    const task<void>& rhs);
```

### <a name="parameters"></a>매개 변수

*ReturnType*<br/>
반환되는 작업의 형식입니다.

*lhs*<br/>
결과 작업으로 결합할 첫 번째 작업입니다.

*rhs*<br/>
결과 작업으로 결합할 두 번째 작업입니다.

### <a name="return-value"></a>Return Value

두 입력 작업이 모두 성공적으로 완료되는 경우 완료되는 작업입니다. 입력 작업이 `T` 형식이면 이 함수의 출력은 `task<std::vector<T>>`가 됩니다. 입력 작업이 `void` 형식이면 이 함수의 출력 작업도 `task<void>`가 됩니다.

### <a name="remarks"></a>설명

작업 중 하나가 취소 되거나 예외를 throw 하는 경우 반환 된 작업은 취소 된 상태에서 일찍 완료 되 고 해당 작업에서 `get()` 또는 `wait()`를 호출 하면 예외가 발생 합니다.

## <a name="operator_eq_eq"></a>operator = = 연산자

연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체와 같은지 테스트합니다.

```cpp
template<typename T, class A1, class A2>
inline bool operator== (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
동시 벡터에 저장 된 요소의 데이터 형식입니다.

*A1*<br/>
첫 번째 `concurrent_vector` 개체의 할당자 형식입니다.

*A2*<br/>
두 번째 `concurrent_vector` 개체의 할당자 형식입니다.

*_A*<br/>
`concurrent_vector` 형식의 개체입니다.

*_B*<br/>
`concurrent_vector` 형식의 개체입니다.

### <a name="return-value"></a>Return Value

연산자 좌 변의 동시 벡터가 연산자 우변의 동시 벡터와 같으면 **true** 이 고, 그렇지 않으면입니다. 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

요소 수가 같고 해당 요소의 값이 같으면 두 동시 벡터가 동일 합니다. 그렇지 않으면 목록은 같지 않은 것입니다.

이 메서드는 `_A` 또는 `_B`동시 벡터 중 하나를 수정할 수 있는 다른 메서드와 관련 하 여 동시성이 보장 되지 않습니다.

## <a name="operator_neq"></a>operator! = 연산자

연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체와 같지 않은지 테스트합니다.

```cpp
template<typename T, class A1, class A2>
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
동시 벡터에 저장 된 요소의 데이터 형식입니다.

*A1*<br/>
첫 번째 `concurrent_vector` 개체의 할당자 형식입니다.

*A2*<br/>
두 번째 `concurrent_vector` 개체의 할당자 형식입니다.

*_A*<br/>
`concurrent_vector` 형식의 개체입니다.

*_B*<br/>
`concurrent_vector` 형식의 개체입니다.

### <a name="return-value"></a>Return Value

동시 벡터가 같지 않으면 **true** 이 고, 동시 벡터가 같으면 **false** 입니다.

### <a name="remarks"></a>설명

요소 수가 같고 해당 요소의 값이 같으면 두 동시 벡터가 동일 합니다. 그렇지 않으면 목록은 같지 않은 것입니다.

이 메서드는 `_A` 또는 `_B`동시 벡터 중 하나를 수정할 수 있는 다른 메서드와 관련 하 여 동시성이 보장 되지 않습니다.

## <a name="operator_lt"></a>operator&lt; 연산자

연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체보다 작은지 테스트합니다.

```cpp
template<typename T, class A1, class A2>
inline bool operator<(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
동시 벡터에 저장 된 요소의 데이터 형식입니다.

*A1*<br/>
첫 번째 `concurrent_vector` 개체의 할당자 형식입니다.

*A2*<br/>
두 번째 `concurrent_vector` 개체의 할당자 형식입니다.

*_A*<br/>
`concurrent_vector` 형식의 개체입니다.

*_B*<br/>
`concurrent_vector` 형식의 개체입니다.

### <a name="return-value"></a>Return Value

연산자 좌 변의 동시 벡터가 연산자 우변의 동시 벡터 보다 작은 경우 **true** 입니다. 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

이 연산자의 동작은 `std` 네임 스페이스의 `vector` 클래스에 대 한 해당 연산자와 동일 합니다.

이 메서드는 `_A` 또는 `_B`동시 벡터 중 하나를 수정할 수 있는 다른 메서드와 관련 하 여 동시성이 보장 되지 않습니다.

## <a name="operator_lt_eq"></a>operator&lt;= 연산자

연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체보다 작거나 같은지 테스트합니다.

```cpp
template<typename T, class A1, class A2>
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
동시 벡터에 저장 된 요소의 데이터 형식입니다.

*A1*<br/>
첫 번째 `concurrent_vector` 개체의 할당자 형식입니다.

*A2*<br/>
두 번째 `concurrent_vector` 개체의 할당자 형식입니다.

*_A*<br/>
`concurrent_vector` 형식의 개체입니다.

*_B*<br/>
`concurrent_vector` 형식의 개체입니다.

### <a name="return-value"></a>Return Value

연산자 좌 변의 동시 벡터가 연산자 우변의 동시 벡터 보다 작거나 같으면 **true** 이 고, 그렇지 않으면입니다. 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

이 연산자의 동작은 `std` 네임 스페이스의 `vector` 클래스에 대 한 해당 연산자와 동일 합니다.

이 메서드는 `_A` 또는 `_B`동시 벡터 중 하나를 수정할 수 있는 다른 메서드와 관련 하 여 동시성이 보장 되지 않습니다.

## <a name="operator_gt"></a>operator&gt; 연산자

연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체보다 큰지 테스트합니다.

```cpp
template<typename T, class A1, class A2>
inline bool operator>(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
동시 벡터에 저장 된 요소의 데이터 형식입니다.

*A1*<br/>
첫 번째 `concurrent_vector` 개체의 할당자 형식입니다.

*A2*<br/>
두 번째 `concurrent_vector` 개체의 할당자 형식입니다.

*_A*<br/>
`concurrent_vector` 형식의 개체입니다.

*_B*<br/>
`concurrent_vector` 형식의 개체입니다.

### <a name="return-value"></a>Return Value

연산자 좌 변의 동시 벡터가 연산자 우변의 동시 벡터 보다 크면 **true** 이 고, 그렇지 않으면입니다. 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

이 연산자의 동작은 `std` 네임 스페이스의 `vector` 클래스에 대 한 해당 연산자와 동일 합니다.

이 메서드는 `_A` 또는 `_B`동시 벡터 중 하나를 수정할 수 있는 다른 메서드와 관련 하 여 동시성이 보장 되지 않습니다.

## <a name="operator_gt_eq"></a>operator&gt;= 연산자

연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체보다 크거나 같은지 테스트합니다.

```cpp
template<typename T, class A1, class A2>
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
동시 벡터에 저장 된 요소의 데이터 형식입니다.

*A1*<br/>
첫 번째 `concurrent_vector` 개체의 할당자 형식입니다.

*A2*<br/>
두 번째 `concurrent_vector` 개체의 할당자 형식입니다.

*_A*<br/>
`concurrent_vector` 형식의 개체입니다.

*_B*<br/>
`concurrent_vector` 형식의 개체입니다.

### <a name="return-value"></a>Return Value

연산자 좌 변의 동시 벡터가 연산자 우변의 동시 벡터 보다 크거나 같으면 **true** 이 고, 그렇지 않으면입니다. 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

이 연산자의 동작은 `std` 네임 스페이스의 `vector` 클래스에 대 한 해당 연산자와 동일 합니다.

이 메서드는 `_A` 또는 `_B`동시 벡터 중 하나를 수정할 수 있는 다른 메서드와 관련 하 여 동시성이 보장 되지 않습니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)
