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
ms.openlocfilehash: 3d65cd6b6b8549fd9964f6c5bb6d8b2d3c0a27b6
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78875895"
---
# <a name="ltarraygt-operators"></a>&lt;array&gt; 연산자

\<배열 > 헤더에는 이러한 **배열의** 비 멤버 비교 템플릿 함수가 포함 됩니다.

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[연산자==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

배열 비교, 같지 않음

```cpp
template <Ty, std::size_t N>
bool operator!=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*Ty*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
비교할 왼쪽 컨테이너입니다.

*오른쪽*\
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

템플릿 함수가 `!(left == right)`를 반환합니다.

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

## <a name="op_lt"></a>  operator&lt;

배열 비교, 보다 작음

```cpp
template <Ty, std::size_t N>
bool operator<(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*Ty*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
비교할 왼쪽 컨테이너입니다.

*오른쪽*\
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

템플릿 함수 오버 로드는 클래스 템플릿 [배열 클래스](../standard-library/array-class-stl.md)의 두 개체를 비교 하는 `operator<` 합니다. 함수에서 `lexicographical_compare(left.begin(), left.end(), right.begin())`을 반환합니다.

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

## <a name="op_lt_eq"></a>  operator&lt;=

배열 비교, 보다 작거나 같음

```cpp
template <Ty, std::size_t N>
bool operator<=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*Ty*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
비교할 왼쪽 컨테이너입니다.

*오른쪽*\
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

템플릿 함수가 `!(right < left)`를 반환합니다.

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

## <a name="op_eq_eq"></a>  operator==

배열 비교, 같음

```cpp
template <Ty, std::size_t N>
bool operator==(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*Ty*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
비교할 왼쪽 컨테이너입니다.

*오른쪽*\
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

템플릿 함수 오버 로드는 클래스 템플릿 [배열 클래스](../standard-library/array-class-stl.md)의 두 개체를 비교 하는 `operator==` 합니다. 함수에서 `equal(left.begin(), left.end(), right.begin())`을 반환합니다.

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

## <a name="op_gt"></a>  operator&gt;

배열 비교, 보다 큼

```cpp
template <Ty, std::size_t N>
bool operator>(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*Ty*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
비교할 왼쪽 컨테이너입니다.

*오른쪽*\
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

템플릿 함수가 `(right < left)`를 반환합니다.

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

## <a name="op_gt_eq"></a>  operator&gt;=

배열 비교, 보다 크거나 같음

```cpp
template <Ty, std::size_t N>
bool operator>=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*Ty*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
비교할 왼쪽 컨테이너입니다.

*오른쪽*\
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

템플릿 함수가 `!(left < right)`를 반환합니다.

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

[\<array>](../standard-library/array.md)
