---
title: 컴파일러 경고(수준 4) C4932
description: Microsoft C/c + + 컴파일러 경고 C4932에 대해 설명 합니다.
ms.date: 08/25/2020
f1_keywords:
- C4932
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
ms.openlocfilehash: ece2ae14fd8e1198a97f5e772fcce52c47464878
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898290"
---
# <a name="compiler-warning-level-4-c4932"></a>컴파일러 경고(수준 4) C4932

> `__identifier(identifier_1)` 및 `__identifier(identifier_2)` 는 구별할 수 없습니다.

컴파일러는 **`_finally`** 와 **`__finally`** 또는를 **`__try`** **`_try`** 에 전달 된 매개 변수로 [`__identifier`](../../extensions/identifier-cpp-cli.md) 구분할 수 없습니다. [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) 오류가 발생하므로 동일한 프로그램에서 둘 다를 식별자로 사용해서는 안 됩니다.

다음 샘플에서는 C4932를 생성합니다.

```cpp
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```
