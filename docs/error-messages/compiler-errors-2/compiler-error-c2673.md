---
title: 컴파일러 오류 C2673
ms.date: 11/04/2016
f1_keywords:
- C2673
helpviewer_keywords:
- C2673
ms.assetid: 780230c0-619b-4a78-b01d-ff5886306741
ms.openlocfilehash: 1a27b41c11905a509889d46da655900b69070445
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216117"
---
# <a name="compiler-error-c2673"></a>컴파일러 오류 C2673

' function ': 전역 함수에는 ' this ' 포인터가 없습니다.

전역 함수에서 액세스 하려고 했습니다 **`this`** .

다음 샘플에서는 C2673를 생성 합니다.

```cpp
// C2673.cpp
int main() {
   this = 0;   // C2673
}
```
