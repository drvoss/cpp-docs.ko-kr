---
title: 컴파일러 오류 C2575
ms.date: 11/04/2016
f1_keywords:
- C2575
helpviewer_keywords:
- C2575
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
ms.openlocfilehash: c00ae519f5e6b595ec07d6a617813a3ae79ab72d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221135"
---
# <a name="compiler-error-c2575"></a>컴파일러 오류 C2575

' identifier ': 멤버 함수와 기본만 virtual 일 수 있습니다.

전역 함수 또는 클래스가 선언 됩니다 **`virtual`** . 이것은 허용되지 않습니다.

다음 샘플에서는 C2575를 생성 합니다.

```cpp
// C2575.cpp
// compile with: /c
virtual void func() {}   // C2575

void func2() {}
struct A {
   virtual void func2(){}
};
```
