---
title: 컴파일러 오류 C2583
ms.date: 11/04/2016
f1_keywords:
- C2583
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
ms.openlocfilehash: 0cb021dcba4d050afb943c03ba6b4dca053bcbb8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206850"
---
# <a name="compiler-error-c2583"></a>컴파일러 오류 C2583

' identifier ': ' const/volatile ' ' this ' 포인터는 생성자/소멸자에 사용할 수 없습니다.

생성자 또는 소멸자가 또는로 선언 되었습니다 **`const`** **`volatile`** . 이것은 허용되지 않습니다.

다음 샘플에서는 C2583를 생성 합니다.

```cpp
// C2583.cpp
// compile with: /c
class A {
public:
   int i;
   A() const;   // C2583

   // try the following line instead
   // A();
};
```
