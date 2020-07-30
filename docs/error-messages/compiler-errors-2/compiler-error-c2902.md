---
title: 컴파일러 오류 C2902
ms.date: 11/04/2016
f1_keywords:
- C2902
helpviewer_keywords:
- C2902
ms.assetid: 89d78d0e-78e5-4c2c-a0f9-a60110e9395e
ms.openlocfilehash: 287ca42be0f1c09a6438af067feb299e7a01df6b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230885"
---
# <a name="compiler-error-c2902"></a>컴파일러 오류 C2902

'token': 'template' 다음에 예기치 않은 토큰이 있습니다. 식별자가 필요합니다.

키워드 뒤의 토큰이 **`template`** 식별자가 아닙니다.

다음 샘플에서는 C2902를 생성합니다.

```cpp
// C2902.cpp
// compile with: /c
namespace N {
   template<class T> class X {};
   class Y {};
}
void g() {
   N::template + 1;   // C2902
}

void f() {
   N::template X<int> x1;   // OK
}
```

C2902는 제네릭을 사용하는 경우에도 발생할 수 있습니다.

```cpp
// C2902b.cpp
// compile with: /clr /c
namespace N {
   generic<class T> ref class GC {};
}

void f() {
   N::generic + 1;   // C2902
   N::generic GC<int>^ x;
}
```
