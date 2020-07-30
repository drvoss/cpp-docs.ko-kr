---
title: 컴파일러 오류 C2574
ms.date: 11/04/2016
f1_keywords:
- C2574
helpviewer_keywords:
- C2574
ms.assetid: 3e1c5c18-ee8b-4dbb-bfc0-d3b8991af71b
ms.openlocfilehash: 28e674b9788a8fa9135460e547f743cb2b0075ee
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212711"
---
# <a name="compiler-error-c2574"></a>컴파일러 오류 C2574

' 소멸자 ': static으로 선언할 수 없습니다.

소멸자와 생성자는 모두 선언할 수 **`static`** 없습니다.

다음 샘플에서는 C2574를 생성 합니다.

```cpp
// C2574.cpp
// compile with: /c
class A {
   virtual static ~A();   // C2574
   //  try the following line instead
   // virtual ~A();
};
```
