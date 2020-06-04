---
title: 컴파일러 오류 C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: c1a5b6edbc87e14de267cf962dc2b1a71dd6be12
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200540"
---
# <a name="compiler-error-c3615"></a>컴파일러 오류 C3615

> constexpr 함수 '*function*'은 상수 식이 될 수 없습니다.

컴파일 시간에 `constexpr` 함수 *함수* 를 계산할 수 없습니다. `constexpr`하기 위해 함수는 다른 `constexpr` 함수를 호출할 수 있습니다.

## <a name="example"></a>예제

조건적으로 평가 하는 작업의 왼쪽 피연산자가 `constexpr` 컨텍스트에서 유효 하지 않은 경우 Visual Studio 2017에서 오류를 올바르게 발생 시킵니다. 다음 코드는 visual studio 2015에서 컴파일되지만 Visual Studio 2017에서는 컴파일되지 않습니다.

```cpp
// C3615.cpp
// Compile with: /c

template<int N>
struct myarray
{
    int size() const { return N; }
};

constexpr bool f(const myarray<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615 starting in Visual Studio 2017
}
```

이 문제를 해결 하려면 `array::size()` 함수를 `constexpr`으로 선언 하거나 `f`에서 `constexpr` 한정자를 제거 합니다.
