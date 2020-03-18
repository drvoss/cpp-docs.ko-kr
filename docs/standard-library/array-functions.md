---
title: '&lt;array&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- array/std::array::get
- array/std::get
- array/std::swap
ms.assetid: e0700a33-a833-4655-8735-16e71175efc8
helpviewer_keywords:
- std::array [C++], get
- std::get [C++]
- std::swap [C++]
ms.openlocfilehash: 61b5404d0f22cd902e35f6bee680df3c719804f2
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424070"
---
# <a name="ltarraygt-functions"></a>&lt;array&gt; 함수

\<배열 > 헤더에는 **배열** 개체에 대해 작동 하는 멤버 함수 두 개 (`get` 및 `swap`)가 포함 되어 있습니다.

|||
|-|-|
|[get](#get)|[swap](#swap)|

## <a name="get"></a>  get

배열의 지정된 요소에 대한 참조를 반환합니다.

```cpp
template <int Index, class T, size_t N>
constexpr T& get(array<T, N>& arr) noexcept;

template <int Index, class T, size_t N>
constexpr const T& get(const array<T, N>& arr) noexcept;

template <int Index, class T, size_t N>
constexpr T&& get(array<T, N>&& arr) noexcept;
```

### <a name="parameters"></a>매개 변수

*인덱스*\
요소 오프셋입니다.

*T*\
요소의 형식입니다.

*N*\
배열의 요소 수입니다.

*arr*\
선택할 배열입니다.

### <a name="example"></a>예제

```cpp
#include <array>
#include <iostream>

using namespace std;

typedef array<int, 4> MyArray;

int main()
{
    MyArray c0 { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& e : c0)
    {
        cout << " " << e;
    }
    cout << endl;

    // display odd elements " 1 3"
    cout << " " << get<1>(c0);
    cout << " " << get<3>(c0) << endl;
}
```

```Output
0 1 2 3
1 3
```

## <a name="swap"></a>  swap

두 **배열** 개체를 바꾸는 `std::swap`의 멤버가 아닌 템플릿 특수화입니다.

```cpp
template <class Ty, std::size_t N>
void swap(array<Ty, N>& left, array<Ty, N>& right);
```

### <a name="parameters"></a>매개 변수

*Ty*\
요소의 형식입니다.

*N*\
배열의 크기입니다.

*왼쪽*\
교환할 첫 번째 배열입니다.

*오른쪽*\
교환할 두 번째 배열입니다.

### <a name="remarks"></a>설명

이 템플릿 함수는 `left.swap(right)`을 실행합니다.

### <a name="example"></a>예제

```cpp
// std__array__swap.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = { 4, 5, 6, 7 };
    c0.swap(c1);

    // display swapped contents " 4 5 6 7"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    swap(c0, c1);

    // display swapped contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
4 5 6 7
0 1 2 3
```

## <a name="see-also"></a>참고 항목

[\<array>](../standard-library/array.md)
