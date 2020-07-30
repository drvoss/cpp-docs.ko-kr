---
title: 컴파일러 오류 C2635
ms.date: 11/04/2016
f1_keywords:
- C2635
helpviewer_keywords:
- C2635
ms.assetid: 9deca2a8-2d61-42eb-9783-6578132ee3fb
ms.openlocfilehash: 7d3fc71a331d13416f65d841502fdd1d908653bd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225451"
---
# <a name="compiler-error-c2635"></a>컴파일러 오류 C2635

' identifier1 * '를 ' identifier2 '로 변환할 수 없습니다 \* . 가상 기본 클래스에서의 변환이 암시 됩니다.

변환 하려면 기본 클래스에서 파생 클래스로 캐스트를 사용 해야 **`virtual`** 합니다 .이는 허용 되지 않습니다.

다음 샘플에서는 C2635를 생성 합니다.

```cpp
// C2635.cpp
class B {};
class D : virtual public B {};
class E : public B {};

int main() {
   B b;
   D d;
   E e;

   D * pD = &d;
   E * pE = &e;
   pD = (D*)&b;   // C2635
   pE = (E*)&b;   // OK
}
```
