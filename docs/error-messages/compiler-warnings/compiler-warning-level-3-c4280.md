---
title: 컴파일러 경고 (수준 3) C4280
ms.date: 11/04/2016
f1_keywords:
- C4280
helpviewer_keywords:
- C4280
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
ms.openlocfilehash: eb1d37d3b18563f6c443ae728318eeaf816e9353
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174156"
---
# <a name="compiler-warning-level-3-c4280"></a>컴파일러 경고 (수준 3) C4280

' operator-> '는 ' type ' 형식을 통해 자체 재귀적입니다.

코드에서 > 자신을 호출 하는 **연산자** 를 잘못 허용 합니다.

다음 샘플에서는 C4280를 생성 합니다.

```cpp
// C4280.cpp
// compile with: /W3 /WX
struct A
{
   int z;
   A& operator ->();
};

void f(A y)
{
   int i = y->z; // C4280
}
```
