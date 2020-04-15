---
title: __restrict
ms.date: 10/10/2018
f1_keywords:
- __restrict_cpp
- __restrict
- _restrict
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
ms.openlocfilehash: 27ac76251456d9a0bf5908ad6d1fc2bee7534e9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360809"
---
# <a name="__restrict"></a>__restrict

__declspec ** [(제한)](../cpp/restrict.md) ** 수정자처럼 **__restrict** 키워드는 기호가 현재 범위에서 별칭이 아님을 나타냅니다. **__restrict** 키워드는 다음과 같은 `__declspec ( restrict )` 방법으로 수정자마다 다릅니다.

- **__restrict** 키워드는 변수에서만 유효하며 `__declspec ( restrict )` 함수 선언 및 정의에만 유효합니다.

- **__restrict** C99 사양에서 **제한하는** 것과 유사하지만 **__restrict** C++ 또는 C 프로그램에서 사용할 수 있습니다.

- **__restrict** 사용하면 컴파일러는 변수의 별칭 없음 속성을 전파하지 않습니다. 즉, **__restrict** 변수를 __restrict 변수가 아닌**변수에** 할당하는 경우에도 컴파일러는 __restrict 아닌 변수를 별칭으로 지정할 수 있습니다. 이는 C99 사양에서 **제한** 키워드의 동작과 다릅니다.

일반적으로 전체 함수의 동작을 변경하려면 키워드보다는 `__declspec ( restrict )`를 사용하는 것이 효율적입니다.

이전 버전과의 호환성을 위해 컴파일러 옵션 [/Za \(비활성화 언어 확장)이](../build/reference/za-ze-disable-language-extensions.md) 지정되지 않는 한 **_restrict** **__restrict** 동의어입니다.

Visual Studio 2015 이상에서는 **C++** 참조에서 __restrict 사용할 수 있습니다.

> [!NOTE]
> [휘발성](../cpp/volatile-cpp.md) 키워드가 있는 변수에 사용하면 **휘발성이** 우선됩니다.

## <a name="example"></a>예제

```cpp
// __restrict_keyword.c
// compile with: /LD
// In the following function, declare a and b as disjoint arrays
// but do not have same assurance for c and d.
void sum2(int n, int * __restrict a, int * __restrict b,
          int * c, int * d) {
   int i;
   for (i = 0; i < n; i++) {
      a[i] = b[i] + c[i];
      c[i] = b[i] + d[i];
    }
}

// By marking union members as __restrict, tell compiler that
// only z.x or z.y will be accessed in any given scope.
union z {
   int * __restrict x;
   double * __restrict y;
};
```

## <a name="see-also"></a>참고 항목

[키워드](../cpp/keywords-cpp.md)
