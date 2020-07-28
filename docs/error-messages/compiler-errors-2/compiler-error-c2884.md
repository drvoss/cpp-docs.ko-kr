---
title: 컴파일러 오류 C2884
ms.date: 11/04/2016
f1_keywords:
- C2884
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
ms.openlocfilehash: d6014aa44dd1c2a5f1b0418a7171b239a754ec33
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220199"
---
# <a name="compiler-error-c2884"></a>컴파일러 오류 C2884

' name ': using 선언에 의해 정의 된 ' function ' 지역 함수와 충돌 합니다.

함수를 두 번 이상 정의 하려고 했습니다. 첫 번째 정의는 로컬 정의입니다. 두 번째는 선언이 포함 된 네임 스페이스에서 가져온 것입니다 **`using`** .

다음 샘플에서는 C2884를 생성 합니다.

```cpp
// C2884.cpp
namespace A {
   void z(int);
}

void f() {
   void z(int);
   using A::z;   // C2884 z is already defined
}
```
