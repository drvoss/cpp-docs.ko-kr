---
title: 컴파일러 오류 C2255
ms.date: 11/04/2016
f1_keywords:
- C2255
helpviewer_keywords:
- C2255
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
ms.openlocfilehash: 2cb2fd5a673fd44e2b06f8675cfc3ae8e418c290
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87208748"
---
# <a name="compiler-error-c2255"></a>컴파일러 오류 C2255

'element': 클래스 정의 외부에서 사용할 수 없습니다.

예를 들어 비멤버 함수는로 선언 됩니다 **`friend`** .

다음 샘플에서는 C2255를 생성합니다.

```cpp
// C2255.cpp
// compile with: /c
class A {
private:
   void func1();
   friend void func2();
};

friend void func1() {}   // C2255
void func2(){}
```
