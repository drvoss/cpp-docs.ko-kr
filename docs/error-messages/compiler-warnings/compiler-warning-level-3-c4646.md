---
title: 컴파일러 경고(수준 3) C4646
ms.date: 11/04/2016
f1_keywords:
- C4646
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
ms.openlocfilehash: 3bbb9214a67284876c55e04485cea796cf9dbc29
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214427"
---
# <a name="compiler-warning-level-3-c4646"></a>컴파일러 경고(수준 3) C4646

__declspec(noreturn)으로 선언된 함수에 void가 아닌 반환 형식이 있습니다.

[Noreturn](../../cpp/noreturn.md) 한정자로 표시 된 함수에는 **`__declspec`** [void](../../cpp/void-cpp.md) 반환 형식이 있어야 합니다.

다음 샘플에서는 C4646을 생성합니다.

```cpp
// C4646.cpp
// compile with: /W3 /WX
int __declspec(noreturn) TestFunction()
{   // C4646  make return type void
}
```
