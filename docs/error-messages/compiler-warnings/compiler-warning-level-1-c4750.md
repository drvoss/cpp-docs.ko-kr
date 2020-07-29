---
title: 컴파일러 경고(수준 1) C4750
description: 가능한 스택 오버플로에 대 한 MSVC 컴파일러 경고 C4750을 설명 합니다.
ms.date: 07/08/2020
f1_keywords:
- C4750
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
ms.openlocfilehash: a02b69981d3cf1d35a6700261fc5142cfa8ec8e6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225360"
---
# <a name="compiler-warning-level-1-c4750"></a>컴파일러 경고(수준 1) C4750

> '*identifier*': 루프에 인라이닝 된 _alloca ()를 사용 하는 함수입니다.

## <a name="remarks"></a>설명

'*Identifier*' 함수는 루프 내에서 함수의 인라인 확장을 강제로 수행 하 여 [`_alloca`](../../c-runtime-library/reference/alloca.md) 루프가 실행 될 때 스택 오버플로가 발생할 수 있습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. '*Identifier*' 함수가 지정자를 사용 하 여 수정 되지 않았는지 확인 하세요 [`__forceinline`](../../cpp/inline-functions-cpp.md) .

1. '*Identifier*' 함수가 [`_alloca`](../../c-runtime-library/reference/alloca.md) 루프에 포함 된 함수를 포함 하지 않는지 확인 하십시오.

1. [`/O1`](../../build/reference/o1-o2-minimize-size-maximize-speed.md),, [`/O2`](../../build/reference/o1-o2-minimize-size-maximize-speed.md) [`/Ox`](../../build/reference/ox-full-optimization.md) 또는 [`/Og`](../../build/reference/og-global-optimizations.md) 컴파일 스위치를 지정 하지 마세요.

1. [`_alloca`](../../c-runtime-library/reference/alloca.md)스택 오버플로를 catch 하는 [try except 문에](../../cpp/try-except-statement.md) 함수를 추가 합니다.

## <a name="example"></a>예제

다음 코드 예제는 루프에서 `MyFunction` 을 호출하고 `MyFunction` 은 `_alloca` 함수를 호출합니다. **`__forceinline`** 한정자로 인해 함수의 인라인 확장이 발생 합니다 `_alloca` .

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
