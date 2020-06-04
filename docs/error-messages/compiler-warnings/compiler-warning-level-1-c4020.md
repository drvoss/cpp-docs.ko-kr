---
title: 컴파일러 경고 (수준 1) C4020
ms.date: 11/04/2016
f1_keywords:
- C4020
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
ms.openlocfilehash: 2136e94a261b2f767165e43acfd66583e8d15e9f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164588"
---
# <a name="compiler-warning-level-1-c4020"></a>컴파일러 경고 (수준 1) C4020

' function ': 실제 매개 변수가 너무 많습니다.

함수 호출의 실제 매개 변수 수가 함수 프로토타입 또는 정의의 정식 매개 변수 개수를 초과 합니다. 컴파일러는 함수의 호출 규칙에 따라 추가 실제 매개 변수를 전달 합니다.

다음 샘플에서는 C4020를 생성 합니다.

```c
// C4020.c
// compile with: /W1 /c
void f(int);
int main() {
   f(1,2);   // C4020
}
```

가능한 해결 방법:

```c
// C4020b.c
// compile with: /c
void f(int);
int main() {
   f(1);
}
```
