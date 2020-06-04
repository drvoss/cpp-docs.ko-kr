---
title: '&lt;array&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- array/std::array::operator!=
- array/std::array::operator<
- array/std::array::operator<=
- array/std::array::operator>
- array/std::array::operator>=
- array/std::array::operator==
ms.assetid: c8f46282-f179-4909-9a01-639cb8e18c27
ms.openlocfilehash: 531ad2936322f90a38631a9450e0ad8a210fdd87
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364905"
---
# <a name="ltarraygt-operators"></a>&lt;array&gt; 연산자

배열 \<> 헤더에는 이러한 **배열** 비멤버 비교 템플릿 함수가 포함됩니다.

||||
|-|-|-|
|[연산자!=](#op_neq)|[연산자&gt;](#op_gt)|[연산자&gt;=](#op_gt_eq)|
|[연산자&lt;](#op_lt)|[연산자&lt;=](#op_lt_eq)|[연산자==](#op_eq_eq)|

## <a name="operator"></a><a name="op_neq"></a>연산자!=

배열 비교, 같지 않음

```cpp
template <Ty, std::size_t N>
bool operator!=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*타이*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
비교할 왼쪽 컨테이너입니다.

*오른쪽*\
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

템플릿 함수가 `!(left == right)`을 반환합니다.

### <a name="example"></a>예제

```cpp
// std__array__operator_ne.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 != c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 != c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
false
true
```

## <a name="operatorlt"></a><a name="op_lt"></a>연산자&lt;

배열 비교, 보다 작음

```cpp
template <Ty, std::size_t N>
bool operator<(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*타이*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
비교할 왼쪽 컨테이너입니다.

*오른쪽*\
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

템플릿 함수 오버로드를 `operator<` 사용하여 클래스 템플릿 배열 [클래스의](../standard-library/array-class-stl.md)두 개체를 비교합니다. 함수에서 `lexicographical_compare(left.begin(), left.end(), right.begin())`을 반환합니다.

### <a name="example"></a>예제

```cpp
// std__array__operator_lt.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 < c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 < c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
false
true
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a>연산자&lt;=

배열 비교, 보다 작거나 같음

```cpp
template <Ty, std::size_t N>
bool operator<=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*타이*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
비교할 왼쪽 컨테이너입니다.

*오른쪽*\
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

템플릿 함수가 `!(right < left)`을 반환합니다.

### <a name="example"></a>예제

```cpp
// std__array__operator_le.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 <= c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c1 <= c0);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
true
false
```

## <a name="operator"></a><a name="op_eq_eq"></a>연산자==

배열 비교, 같음

```cpp
template <Ty, std::size_t N>
bool operator==(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*타이*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
비교할 왼쪽 컨테이너입니다.

*오른쪽*\
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

템플릿 함수 오버로드를 `operator==` 사용하여 클래스 템플릿 배열 [클래스의](../standard-library/array-class-stl.md)두 개체를 비교합니다. 함수에서 `equal(left.begin(), left.end(), right.begin())`을 반환합니다.

### <a name="example"></a>예제

```cpp
// std__array__operator_eq.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 == c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 == c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
true
false
```

## <a name="operatorgt"></a><a name="op_gt"></a>연산자&gt;

배열 비교, 보다 큼

```cpp
template <Ty, std::size_t N>
bool operator>(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*타이*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
비교할 왼쪽 컨테이너입니다.

*오른쪽*\
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

템플릿 함수가 `(right < left)`을 반환합니다.

### <a name="example"></a>예제

```cpp
// std__array__operator_gt.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 > c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c1 > c0);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
false
true
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a>연산자&gt;=

배열 비교, 보다 크거나 같음

```cpp
template <Ty, std::size_t N>
bool operator>=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*타이*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
비교할 왼쪽 컨테이너입니다.

*오른쪽*\
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

템플릿 함수가 `!(left < right)`을 반환합니다.

### <a name="example"></a>예제

```cpp
// std__array__operator_ge.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 >= c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 >= c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
true
false
```

## <a name="see-also"></a>참고 항목

[\<배열>](../standard-library/array.md)
