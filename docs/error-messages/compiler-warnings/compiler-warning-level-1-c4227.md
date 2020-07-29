---
title: 컴파일러 경고(수준 1) C4227
ms.date: 11/04/2016
f1_keywords:
- C4227
helpviewer_keywords:
- C4227
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
ms.openlocfilehash: f5cc9e67c06443a73692ce663a2106dacff6035c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221018"
---
# <a name="compiler-warning-level-1-c4227"></a>컴파일러 경고(수준 1) C4227

오래 된 사용: 참조에 대 한 한정자는 무시 됩니다.

**`const`** **`volatile`** C + + 참조와 같은 한정자를 사용 하는 것은 오래 된 방법입니다.

## <a name="example"></a>예제

```cpp
// C4227.cpp
// compile with: /W1 /c
int j = 0;
int &const i = j;   // C4227
```
