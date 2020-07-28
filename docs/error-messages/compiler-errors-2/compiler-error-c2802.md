---
title: 컴파일러 오류 C2802
ms.date: 11/04/2016
f1_keywords:
- C2802
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
ms.openlocfilehash: f872a4753907cd78c9118c22498777d5acc5b2fd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214583"
---
# <a name="compiler-error-c2802"></a>컴파일러 오류 C2802

' operator operator ' 정적 멤버에 정식 매개 변수가 없습니다.

멤버 함수에 의해 선언 된 연산자에는 **`static`** 매개 변수가 하나 이상 있어야 합니다.

다음 샘플에서는 C2802를 생성 합니다.

```cpp
// C2802.cpp
// compile with: /clr /c
ref class A {
   static operator+ ();   // C2802
   static operator+ (A^, A^);   // OK
};
```
