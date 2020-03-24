---
title: false (C++)
ms.date: 11/04/2016
f1_keywords:
- false_cpp
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
ms.openlocfilehash: f363e309b91e44472447d040aa36752750afec6f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188937"
---
# <a name="false-c"></a>false (C++)

키워드는 [bool](../cpp/bool-cpp.md) 또는 조건식 형식의 변수에 대 한 두 값 중 하나입니다. 조건식은 이제 **진정한** 부울 식입니다. 예를 들어 `i`가 **bool**형식의 변수인 경우 `i = false;` 문은 `i`에 **false** 를 할당 합니다.

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

[키워드](../cpp/keywords-cpp.md)
