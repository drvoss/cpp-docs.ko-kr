---
title: 컴파일러 오류 C2317
ms.date: 11/04/2016
f1_keywords:
- C2317
helpviewer_keywords:
- C2317
ms.assetid: e44d129b-8d3e-4ce9-9d79-6791ee77f25e
ms.openlocfilehash: 95444951106d74d01efe84f829b606eb2c547c99
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221265"
---
# <a name="compiler-error-c2317"></a>컴파일러 오류 C2317

줄 'number'에서 시작하는 'try' 블록에 catch 처리기가 없습니다.

블록에는 **`try`** 하나 이상의 catch 처리기가 있어야 합니다.

다음 샘플에서는 C2317을 생성합니다.

```cpp
// C2317.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   // C2317, no catch handler
}
```

해결 방법:

```cpp
// C2317b.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   catch(char*) {}
}
```
