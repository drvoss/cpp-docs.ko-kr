---
title: 컴파일러 경고(수준 2) C4307
ms.date: 11/04/2016
f1_keywords:
- C4307
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
ms.openlocfilehash: f6e06acaf43708d6c0da6d67531b6c4b9f202971
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161882"
---
# <a name="compiler-warning-level-2-c4307"></a>컴파일러 경고(수준 2) C4307

' operator ': 정수 계열 상수 오버플로입니다.

연산자는 할당 된 공간을 오버플로 하는 정수 상수를 반환 하는 식에 사용 됩니다. 상수에 대해 더 큰 형식을 사용 해야 할 수도 있습니다. 부호 **있는 정수는** **부호 있는 int** 에서 부호를 나타내기 위해 1 비트를 사용 하기 때문에 `unsigned int` 보다 더 작은 값을 보유 합니다.

다음 샘플에서는 C4307를 생성 합니다.

```cpp
// C4307.cpp
// compile with: /W2
int i = 2000000000 + 2000000000;   // C4307
int j = (unsigned)2000000000 + 2000000000;   // OK

int main()
{
}
```
