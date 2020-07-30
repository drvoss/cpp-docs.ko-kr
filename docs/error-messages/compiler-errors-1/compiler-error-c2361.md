---
title: 컴파일러 오류 C2361
ms.date: 11/04/2016
f1_keywords:
- C2361
helpviewer_keywords:
- C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
ms.openlocfilehash: b95c6459c0ff093d22f3e754f2c7fd6564d2b296
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221200"
---
# <a name="compiler-error-c2361"></a>컴파일러 오류 C2361

' identifier ' 초기화는 ' default ' 레이블에 의해 생략 됩니다.

문에서의 초기화를 `identifier` 건너뛸 수 있습니다 **`switch`** . 선언이 블록에 포함 되지 않은 경우 이니셜라이저를 사용 하 여 선언을 건너뛸 수 없습니다. 블록 내에서 선언 되지 않은 경우 변수는 문이 끝날 때까지 범위 내에 **`switch`** 있습니다.

다음 샘플에서는 C2361를 생성 합니다.

```cpp
// C2361.cpp
void func( void ) {
   int x;
   switch (x) {
   case 0 :
      int i = 1;
      { int j = 1; }
   default :   // C2361 error
      int k = 1;
   }
}
```

해결 방법:

```cpp
// C2361b.cpp
// compile with: /c
void func( void ) {
   int x = 0;
   switch (x) {
   case 0 :
      { int j = 1; int i = 1;}
   default :
      int k = 1;
   }
}
```
