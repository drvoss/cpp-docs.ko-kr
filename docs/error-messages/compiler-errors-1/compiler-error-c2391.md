---
title: 컴파일러 오류 C2391
ms.date: 11/04/2016
f1_keywords:
- C2391
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
ms.openlocfilehash: f000287c5934a39d56342bce0f6c9ca2c69e2297
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212737"
---
# <a name="compiler-error-c2391"></a>컴파일러 오류 C2391

' identifier ': 형식 정의 중에는 ' friend '를 사용할 수 없습니다.

선언에는 **`friend`** 완전 한 클래스 선언이 포함 됩니다. **`friend`** 선언은 멤버 함수 또는 상세 형식 지정자를 지정할 수 있지만 전체 클래스 선언은 지정할 수 없습니다.

다음 샘플에서는 C2326을 생성합니다.

```cpp
// C2391.cpp
// compile with: /c
class D {
   void func( int );
};

class A {
   friend class B { int i; };   // C2391

   // OK
   friend class C;
   friend void D::func(int);
};
```
