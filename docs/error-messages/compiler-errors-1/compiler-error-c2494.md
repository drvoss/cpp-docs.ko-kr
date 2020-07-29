---
title: 컴파일러 오류 C2494
ms.date: 11/04/2016
f1_keywords:
- C2494
helpviewer_keywords:
- C2494
ms.assetid: 5dfd07ab-351d-49c9-b54e-f0a104776ab8
ms.openlocfilehash: e337e5b54706c1ae9d566131c98fd178c523f87e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216182"
---
# <a name="compiler-error-c2494"></a>컴파일러 오류 C2494

> 필터 식 또는 __finally/finally 블록 내에서 '*keyword*'를 호출할 수 없습니다.

또는 블록에서 *키워드* 를 사용할 수 없습니다 **`__finally`** **`finally`** .

다음 샘플에서는 C2494를 생성 합니다.

```cpp
// C2494.cpp
#include <malloc.h>

int main() {
   __try {}
   __except ( _alloca(100), 1 ) {}   // C2494
   __try {}
   __finally {
      _alloca(100);   // C2494
   }
}
```

C2494는 **/clr**을 사용 하는 경우에도 발생할 수 있습니다.

```cpp
// C2494b.cpp
// compile with: /clr
#include <malloc.h>

int main() {
   char * buf;
   try {}
   catch (char * buf2) {}
   finally {
      _alloca(100);   // C2494
   }
}
```
