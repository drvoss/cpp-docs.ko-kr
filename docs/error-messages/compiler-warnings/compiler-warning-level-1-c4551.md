---
title: 컴파일러 경고(수준 1) C4551
ms.date: 11/04/2016
f1_keywords:
- C4551
helpviewer_keywords:
- C4551
ms.assetid: 458b59bd-e2d7-425f-9ba6-268ff200424f
ms.openlocfilehash: 2f2a47ea318bb0a27495d195c61f410d9cc711fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186155"
---
# <a name="compiler-warning-level-1-c4551"></a>컴파일러 경고(수준 1) C4551

함수 호출에 인수 목록이 없습니다.

함수 호출은 함수에서 매개 변수를 사용 하지 않는 경우에도 함수 이름 뒤에 여는 괄호와 닫는 괄호를 포함 해야 합니다.

다음 샘플에서는 C4551를 생성 합니다.

```cpp
// C4551.cpp
// compile with: /W1
void function1() {
}

int main() {
   function1;   // C4551
   function1();   // OK
}
```
