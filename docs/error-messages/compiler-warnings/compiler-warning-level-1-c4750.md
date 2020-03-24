---
title: 컴파일러 경고(수준 1) C4750
ms.date: 11/04/2016
f1_keywords:
- C4750
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
ms.openlocfilehash: 9ba0a37d2c213c35002b8e09d4377869a868d401
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175170"
---
# <a name="compiler-warning-level-1-c4750"></a>컴파일러 경고(수준 1) C4750

'identifier': 루프에 인라이닝된 _alloca()를 사용하는 함수

'Identifier' 함수가 루프 안에서 [_alloca](../../c-runtime-library/reference/alloca.md) 함수의 인라인 확장을 강제로 수행하여 루프가 실행될 때 스택 오버플로가 발생할 수 있습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 'identifier' 함수가 [__forceinline](../../cpp/inline-functions-cpp.md) 지정자로 수정되었는지 확인합니다.

1. 'Identifier' 함수가 루프에 포함되지 않은 [_alloca](../../c-runtime-library/reference/alloca.md) 함수를 포함하고 있지 않은지 확인합니다.

1. [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/Ox](../../build/reference/ox-full-optimization.md)또는 [/Og](../../build/reference/og-global-optimizations.md) 컴파일 스위치를 지정하지 마세요.

1. 스택 오버플로를 catch하는 [try-excep 문](../../c-runtime-library/reference/alloca.md) 에 [_alloca](../../cpp/try-except-statement.md) 함수를 배치합니다.

## <a name="example"></a>예제

다음 코드 예제는 루프에서 `MyFunction` 을 호출하고 `MyFunction` 은 `_alloca` 함수를 호출합니다. `__forceinline` 한정자로 인해 `_alloca` 함수의 인라인 확장이 발생합니다.

```cpp
// c4750.cpp
// compile with: /O2 /W1 /c
#include <intrin.h>

char * volatile newstr;

__forceinline void myFunction(void) // C4750 warning
{
// The _alloca function does not require a __try/__except
// block because the example uses compiler option /c.
    newstr = (char * volatile) _alloca(1000);
}

int main(void)
{
    for (int i=0; i<50000; i++)
       myFunction();
    return 0;
}
```

## <a name="see-also"></a>참고 항목

[_alloca](../../c-runtime-library/reference/alloca.md)
