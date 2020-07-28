---
title: __noop
ms.date: 09/02/2019
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: e12855127e417472eb88c951b71881240b808013
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214206"
---
# <a name="__noop"></a>__noop

**Microsoft 전용**

**`__noop`** 내장 함수는 함수를 무시 하도록 지정 합니다. 인수 목록은 구문 분석 되지만 인수에 대해서는 코드가 생성 되지 않습니다. 가변 개수의 인수를 사용 하는 전역 디버그 함수에서 사용 하기 위한 것입니다.

컴파일러는 **`__noop`** 컴파일 타임에 내장 함수를 0으로 변환 합니다.

## <a name="example"></a>예제

다음 코드에서는를 사용 하는 방법을 보여 줍니다 **`__noop`** .

```cpp
// compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

int main() {
   PRINT("\nhello\n");
}
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[C++ 키워드](../cpp/keywords-cpp.md)
