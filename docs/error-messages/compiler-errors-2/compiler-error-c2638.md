---
title: 컴파일러 오류 C2638
ms.date: 11/04/2016
f1_keywords:
- C2638
helpviewer_keywords:
- C2638
ms.assetid: 9d4275e8-406d-455e-afee-3a37799230e0
ms.openlocfilehash: 863537c60584ba836c6605f31249ada95a88a1bf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212698"
---
# <a name="compiler-error-c2638"></a>컴파일러 오류 C2638

' identifier ': 멤버에 대 한 포인터에 __based 한정자가 잘못 되었습니다.

**`__based`** 한정자는 멤버에 대 한 포인터에 사용할 수 없습니다.

다음 샘플에서는 C2638를 생성 합니다.

```cpp
// C2638.cpp
void *a;

class C {
public:
   int i;
   int j;
   int func();
};
int __based (a) C::* cpi = &C::i;  // C2638
int (__based (a) C::* cpf)() = &C::func; // c2638
```
