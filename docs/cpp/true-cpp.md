---
title: true (C++)
ms.date: 11/04/2016
f1_keywords:
- true_cpp
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
ms.openlocfilehash: f6420d0abea8bac1d385c1cfdfd58a5500cf5bd3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87185842"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>구문

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>설명

이 키워드는 [bool](../cpp/bool-cpp.md) 형식의 변수 또는 조건식의 두 값 중 하나입니다. 조건식은 이제 진정한 부울 식입니다. `i`가 형식이 면 **`bool`** 문은 `i = true;` **`true`** 를에 할당 `i` 합니다.

## <a name="example"></a>예제

```cpp
// bool_true.cpp
#include <stdio.h>
int main()
{
    bool bb = true;
    printf_s("%d\n", bb);
    bb = false;
    printf_s("%d\n", bb);
}
```

```Output
1
0
```

## <a name="see-also"></a>참고 항목

[C++ 키워드](../cpp/keywords-cpp.md)
