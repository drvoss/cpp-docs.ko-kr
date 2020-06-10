---
title: _1 개체
ms.date: 11/04/2016
f1_keywords:
- _1
- std::_1
- functional/std::_1
helpviewer_keywords:
- _1 object
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
ms.openlocfilehash: 8fdb53ea03031f2bf1634a105275c72263ee20e3
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620921"
---
# <a name="_1-object"></a>_1 개체

대체 가능한 인수에 대한 자리 표시자입니다.

## <a name="syntax"></a>구문

```cpp
namespace placeholders {
    extern unspecified _1, _2, ... _M
} // namespace placeholders (within std)
```

## <a name="remarks"></a>설명

개체는 `_1, _2, ... _M` [bind](functional-functions.md#bind)에서 반환 하는 개체에 대 한 함수 호출에서 각각 첫 번째, 두 번째, ..., mth 인수를 지정 하는 자리 표시자입니다. bind 식을 평가할 때 N번째 인수를 삽입해야 하는 위치를 지정하려면 `_N`을 사용합니다.

이 구현에서 `M`의 값은 20입니다.

## <a name="example"></a>예제

```cpp
// std__functional_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std::placeholders;

void square(double x)
    {
    std::cout << x << "^2 == " << x * x << std::endl;
    }

void product(double x, double y)
    {
    std::cout << x << "*" << y << " == " << x * y << std::endl;
    }

int main()
    {
    double arg[] = {1, 2, 3};

    std::for_each(&arg[0], &arg[3], square);
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(square, _1));

    return (0);
    }
```

```Output
1^2 == 1
2^2 == 4
3^2 == 9

1*2 == 2
2*2 == 4
3*2 == 6

1^2 == 1
2^2 == 4
3^2 == 9
```
