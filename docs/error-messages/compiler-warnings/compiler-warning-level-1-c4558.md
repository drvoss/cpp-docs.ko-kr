---
title: 컴파일러 경고(수준 1) C4558
ms.date: 11/04/2016
f1_keywords:
- C4558
helpviewer_keywords:
- C4558
ms.assetid: 52bb0324-7bec-468c-b35b-13a08d38e578
ms.openlocfilehash: 26bf1603588f522e2bec366586984896190f2d65
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162298"
---
# <a name="compiler-warning-level-1-c4558"></a>컴파일러 경고(수준 1) C4558

' value ' 피연산자의 값이 ' lowerbound-상한값 ' 범위를 벗어났습니다.

어셈블리 언어 명령에 전달 된 값이 매개 변수에 지정 된 범위를 벗어났습니다. 값이 잘립니다.

다음 샘플에서는 C4558를 생성 합니다.

```cpp
// C4558.cpp
// compile with: /W1
// processor: x86
void asm_test() {
   __asm pinsrw   mm1, eax, 8;   // C4558
}

int main() {
}
```
