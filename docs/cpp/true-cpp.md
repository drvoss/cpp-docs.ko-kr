---
title: true (C++)
ms.date: 11/04/2016
f1_keywords:
- true_cpp
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
ms.openlocfilehash: b497c3c9eb1b30074c9b7286c438d0077525e05b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188040"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>구문

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>설명

이 키워드는 [bool](../cpp/bool-cpp.md) 형식의 변수 또는 조건식의 두 값 중 하나입니다. 조건식은 이제 진정한 부울 식입니다. `i` **부울**형식이 면 문은 `i`에 **true** 를 할당 `i = true;`.

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

[키워드](../cpp/keywords-cpp.md)
