---
title: 컴파일러 오류 C2273
ms.date: 11/04/2016
f1_keywords:
- C2273
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
ms.openlocfilehash: f5780c299eb4da03ece3611ee55062ee7ebcdaae
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212789"
---
# <a name="compiler-error-c2273"></a>컴파일러 오류 C2273

' type ': '-> ' 연산자의 오른쪽에 사용할 수가 잘못 되었습니다.

연산자의 오른쪽 피연산자로 형식이 표시 됩니다 `->` .

이 오류는 사용자 정의 형식 변환에 액세스 하려고 할 때 발생할 수 있습니다. **`operator`**->와 사이에 키워드를 사용 `type` 합니다.

다음 샘플에서는 C2273를 생성 합니다.

```cpp
// C2273.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};
int main() {
   MyClass * ClassPtr = new MyClass;
   int i = ClassPtr->int();   // C2273
   int j = ClassPtr-> operator int();   // OK
}
```
