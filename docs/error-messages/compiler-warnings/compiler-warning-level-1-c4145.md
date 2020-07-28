---
title: 컴파일러 경고(수준 1) C4145
ms.date: 11/04/2016
f1_keywords:
- C4145
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
ms.openlocfilehash: 19d2d1a018c7ee981f83aa6fa0914f1241c55538
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220108"
---
# <a name="compiler-warning-level-1-c4145"></a>컴파일러 경고(수준 1) C4145

'expression1': 관계식을 switch 식으로 사용했습니다. 'expression2'와 혼동할 수 있습니다.

**`switch`** 문은 관계식을 제어 식으로 사용 하 여 문에 부울 값을 반환 **`case`** 합니다. *expression2*를 사용하시겠어요?

## <a name="example"></a>예제

다음 샘플에서는 C4145를 생성합니다.

```cpp
// C4145.cpp
// compile with: /W1
int main() {
   int i = 0;
   switch(i == 1) {   // C4145, use i instead of i == 1 to resolve
      case 1:
         break;
      default:
         break;
   }
}
```
