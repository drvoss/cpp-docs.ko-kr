---
title: 컴파일러 경고(수준 1) C4553
ms.date: 11/04/2016
f1_keywords:
- C4553
helpviewer_keywords:
- C4553
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
ms.openlocfilehash: 43ee844f3d6a3d55fae1ac65043e543998571894
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186103"
---
# <a name="compiler-warning-level-1-c4553"></a>컴파일러 경고(수준 1) C4553

' operator ': 연산자는 영향을 주지 않습니다. ' operator '를 의도 했습니까?

식 문에 부작용이 없는 연산자가 있는 경우에는 실수가 될 수 있습니다.

다음 샘플에서는 C4553를 생성 합니다.

```cpp
// C4553.cpp
// compile with: /W1
int func()
{
   return 0;
}

int main()
{
   int i;
   i == func();   // C4553
   // try the following line instead
   // i = func();
}
```
