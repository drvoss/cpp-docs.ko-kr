---
title: 컴파일러 경고(수준 1) C4552
ms.date: 11/04/2016
f1_keywords:
- C4552
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
ms.openlocfilehash: 8435abc60a7ba93800858b22cfd4c5e1778f8587
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186116"
---
# <a name="compiler-warning-level-1-c4552"></a>컴파일러 경고(수준 1) C4552

' operator ': 연산자는 영향을 주지 않습니다. 부작용이 있는 연산자가 필요 합니다.

식 문에 부작용이 없는 연산자가 있는 경우에는 실수가 될 수 있습니다.

이 경고를 무시 하려면 식을 괄호 안에 넣습니다.

다음 샘플에서는 C4552를 생성 합니다.

```cpp
// C4552.cpp
// compile with: /W1
int main() {
   int i, j;
   i + j;   // C4552
   // try the following line instead
   // (i + j);
}
```
