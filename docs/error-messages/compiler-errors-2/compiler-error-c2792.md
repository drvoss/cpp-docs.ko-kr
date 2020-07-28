---
title: 컴파일러 오류 C2792
ms.date: 11/04/2016
f1_keywords:
- C2792
helpviewer_keywords:
- C2792
ms.assetid: 392cf748-4f5e-4e62-a364-3118d5658408
ms.openlocfilehash: 70a1f483aa48b45847306a668a11446a6bb599e7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220225"
---
# <a name="compiler-error-c2792"></a>컴파일러 오류 C2792

' super ':이 키워드 다음에는 ':: '이와 야 합니다.

키워드 뒤에 올 수 있는 유일한 토큰 **`__super`** 은 `::` 입니다.

다음 샘플에서는 C2792를 생성 합니다.

```cpp
// C2792.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super.();   // C2792

      // try the following line instead
      // __super::mf();
   }
};
```
