---
title: 컴파일러 경고(수준 1) C4228
ms.date: 11/04/2016
f1_keywords:
- C4228
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
ms.openlocfilehash: 3a89d5c0924e6fd12a4ccf8afa957f8908670d49
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223241"
---
# <a name="compiler-warning-level-1-c4228"></a>컴파일러 경고(수준 1) C4228

비표준 확장이 사용 됨: 선언 자 목록에서 쉼표 뒤의 한정자가 무시 됩니다.

변수를 선언할 때 쉼표와 같은 한정자를 사용 하는 **`const`** **`volatile`** 것은 Microsoft 확장 ([/ze](../../build/reference/za-ze-disable-language-extensions.md))입니다.

## <a name="example"></a>예제

```cpp
// C4228.cpp
// compile with: /W1
int j, const i = 0;  // C4228
int k;
int const m = 0;  // ok
int main()
{
}
```
