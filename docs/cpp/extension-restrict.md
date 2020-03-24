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
ms.openlocfilehash: cb340554bc20516175400c4d14a5d0dba934a313
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188963"
---
# <a name="__restrict"></a>__restrict

**__Declspec ( [restrict](../cpp/restrict.md) )** 한정자와 마찬가지로 **__restrict** 키워드는 기호가 현재 범위에서 별칭이 지정 되지 않음을 나타냅니다. **__Restrict** 키워드는 다음과 같은 점에서 `__declspec ( restrict )` 한정자와 다릅니다.

- **__Restrict** 키워드는 변수에만 유효 하며 `__declspec ( restrict )`는 함수 선언 및 정의에만 사용할 수 있습니다.

- **__restrict** 는 C99 사양에서 **제한** 하는 것과 유사 하지만 **__restrict** 또는 C 프로그램 C++ 에서 사용할 수 있습니다.

- **__Restrict** 를 사용 하는 경우 컴파일러는 변수의 별칭 없음 속성을 전파 하지 않습니다. 즉, **__restrict** 되지 않은 변수에 **__restrict** 변수를 할당 하는 경우 컴파일러는 여전히 __restrict 되지 않는 변수를 별칭으로 지정할 수 있습니다. 이는 C99 사양의 **restrict** 키워드 동작과 다릅니다.

일반적으로 전체 함수의 동작을 변경하려면 키워드보다는 `__declspec ( restrict )`를 사용하는 것이 효율적입니다.

이전 버전과의 호환성을 위해 **_restrict** 는 컴파일러 옵션 [/za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 이 지정 된 경우를 제외 하 고 **__restrict** 의 동의어입니다.

Visual Studio 2015 이상에서는 참조 C++ 에 **__restrict** 를 사용할 수 있습니다.

> [!NOTE]
>  [Volatile](../cpp/volatile-cpp.md) 키워드를 포함 하는 변수에 사용 하는 경우 **volatile** 이 우선적으로 적용 됩니다.

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
