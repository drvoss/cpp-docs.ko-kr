---
title: 컴파일러 오류 C2293
ms.date: 11/04/2016
f1_keywords:
- C2293
helpviewer_keywords:
- C2293
ms.assetid: 17e7b4e2-368b-4dd7-a01b-d82be60f8e56
ms.openlocfilehash: 8b65c4f57cf566c17defe77e5664affe3744ba9c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212776"
---
# <a name="compiler-error-c2293"></a>컴파일러 오류 C2293

'identifier': 멤버 변수를 __based 지정자로 사용할 수 없습니다.

한정자에 대 한 지정자는 **`__based`** 비멤버 포인터 여야 합니다.

다음 샘플에서는 C2293을 생성합니다.

```cpp
// C2293.cpp
// compile with: /c
class A {
   static int *i;
   void __based(i) *bp;   // C2293
   void *bp2;   // OK
};
```
