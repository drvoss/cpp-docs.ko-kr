---
title: 컴파일러 오류 C2046
ms.date: 11/04/2016
f1_keywords:
- C2046
helpviewer_keywords:
- C2046
ms.assetid: f0c8f9dd-dbd7-4c4a-8838-fde54208ec71
ms.openlocfilehash: b95aa6fd7ef8a1ce2a5fc45e47cfea20e4c38f8c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87210919"
---
# <a name="compiler-error-c2046"></a>컴파일러 오류 C2046

대/소문자가 잘못되었습니다.

키워드는 `case` 문에만 나타날 수 있습니다 **`switch`** .

다음 샘플에서는 C2046을 생성합니다.

```cpp
// C2046.cpp
int main() {
   case 0:   // C2046
}
```

해결 방법:

```cpp
// C2046b.cpp
int main() {
   int i = 0;

   switch(i) {
      case 0:
      break;

      default:
      break;
   }
}
```
