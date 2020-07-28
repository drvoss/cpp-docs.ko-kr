---
title: 컴파일러 오류 C2131
ms.date: 02/28/2019
f1_keywords:
- C2131
helpviewer_keywords:
- C2131
ms.openlocfilehash: 9e5dc328375f720ad39ce57a3da500e0bedcb468
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220420"
---
# <a name="compiler-error-c2131"></a>컴파일러 오류 C2131

> 식이 상수로 계산 되지 않았습니다.

로 선언 된 식이 **`const`** **`constexpr`** 컴파일 타임에 상수로 계산 되지 않았습니다. 컴파일러가 사용 된 시점에서 식의 값을 확인할 수 있어야 합니다.

## <a name="example"></a>예제

이 예에서는 오류 C2131를 발생 시키는 방법 및 문제를 해결 하는 방법을 보여 줍니다.

```cpp
// c2131.cpp
// compile by using: cl /EHsc /W4 /c c2131.cpp

struct test
{
    static const int array_size; // To fix, init array_size here.
    int size_array[array_size];  // C2131
};

const int test::array_size = 42;
```

```Output
c2131.cpp
c2131.cpp(7): error C2131: expression did not evaluate to a constant
c2131.cpp(7): note: failure was caused by non-constant arguments or reference to a non-constant symbol
c2131.cpp(7): note: see usage of 'array_size'
```

## <a name="see-also"></a>참고 항목

[const](../../cpp/const-cpp.md)<br/>
[constexpr](../../cpp/constexpr-cpp.md)<br/>
