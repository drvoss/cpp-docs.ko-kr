---
title: false (C++)
ms.date: 11/04/2016
f1_keywords:
- false_cpp
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
ms.openlocfilehash: d6162bdde3dea0d245a0c83c1d52b06003fee16c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227493"
---
# <a name="false-c"></a>false (C++)

키워드는 [bool](../cpp/bool-cpp.md) 형식의 변수 또는 조건식 (이제 조건식이 **`true`** 부울 식) 인 두 값 중 하나입니다. 예를 들어 `i` 가 형식의 변수인 경우 **`bool`** `i = false;` 문은 **`false`** 에를 할당 `i` 합니다.

## <a name="example"></a>예제

```cpp
// bool_false.cpp
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
