---
title: 컴파일러 경고(수준 1) C4155
ms.date: 11/04/2016
f1_keywords:
- C4155
helpviewer_keywords:
- C4155
ms.assetid: ba233353-09e3-4195-8127-13a27ddd8d70
ms.openlocfilehash: 74369ce9eae123143caf15434506acf6e6e2e50e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223293"
---
# <a name="compiler-warning-level-1-c4155"></a>컴파일러 경고(수준 1) C4155

'delete' 배열 형식을 사용하지 않고 배열 식을 삭제했습니다.

배열을 삭제 하려면의 배열 형식을 **`delete`** 사용 해야 합니다. 이 경고는 ANSI 호환성(/Za)에서만 발생합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4155를 생성합니다.

```cpp
// C4155.cpp
// compile with: /Za /W1
#include <stdio.h>

int main(void)
{
    int (*array)[ 10 ] = new int[ 5 ] [ 10 ];
    array[0][0] = 8;

    printf_s("%d\n", array[0][0]);

   delete array;   // C4155
    // try the following line instead
    // delete [] array;   // C4155
}
```
