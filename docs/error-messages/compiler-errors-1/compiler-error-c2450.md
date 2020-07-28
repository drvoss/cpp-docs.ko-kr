---
title: 컴파일러 오류 C2450
ms.date: 11/04/2016
f1_keywords:
- C2450
helpviewer_keywords:
- C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
ms.openlocfilehash: 55c7f7ba8708e1475404a474f85df7dbe37fcec0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220355"
---
# <a name="compiler-error-c2450"></a>컴파일러 오류 C2450

' type ' 형식의 switch 식이 잘못 되었습니다.

**`switch`** 식이 잘못 된 형식으로 평가 됩니다. 정수 형식 또는 정수 형식으로의 명확한 변환이 있는 클래스 형식으로 계산 되어야 합니다. 사용자 정의 형식으로 계산 되는 경우 변환 연산자를 제공 해야 합니다.

다음 샘플에서는 C2450를 생성 합니다.

```cpp
// C2450.cpp
class X {
public:
   int i;
} x;

class Y {
public:
   int i;
   operator int() { return i; }   // conversion operator
} y;

int main() {
   int j = 1;
   switch ( x ) {   // C2450, x is not type int
   // try the following line instead
   // switch ( y ) {
      default:  ;
   }
}
```
