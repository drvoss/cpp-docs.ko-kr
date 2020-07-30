---
title: 컴파일러 경고(수준 4) C4932
ms.date: 11/04/2016
f1_keywords:
- C4932
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
ms.openlocfilehash: 992e047f31e4a30edd29ba6110bf119d2bc8928b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230599"
---
# <a name="compiler-warning-level-4-c4932"></a>컴파일러 경고(수준 4) C4932

__identifier (식별자)와 \_ _identifier (식별자)를 구별할 수 없습니다.

컴파일러는 **_finally** 및 **`__finally`** 또는 `__try` **_try** 를 [__identifier](../../extensions/identifier-cpp-cli.md)에 전달 된 매개 변수로 구분할 수 없습니다. [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) 오류가 발생하므로 동일한 프로그램에서 둘 다를 식별자로 사용해서는 안 됩니다.

다음 샘플에서는 C4932를 생성합니다.

```cpp
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```
