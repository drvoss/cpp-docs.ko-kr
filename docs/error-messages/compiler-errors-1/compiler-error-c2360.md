---
title: 컴파일러 오류 C2360
ms.date: 11/04/2016
f1_keywords:
- C2360
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
ms.openlocfilehash: a2a164f919dc7535a4587d51f4f7dba8653a1760
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214687"
---
# <a name="compiler-error-c2360"></a>컴파일러 오류 C2360

' case ' 레이블에서 ' identifier ' 초기화를 건너뛰었습니다.

문에서의 초기화를 `identifier` 건너뛸 수 있습니다 **`switch`** . 선언이 블록에 포함 되지 않은 경우 이니셜라이저를 사용 하 여 선언을 건너뛸 수 없습니다. 블록 내에서 선언 되지 않은 경우 변수는 문이 끝날 때까지 범위 내에 **`switch`** 있습니다.

다음 샘플에서는 C2360를 생성 합니다.

```cpp
// C2360.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      int i = 1;
      { int j = 1; }
   case 1 :   // C2360
      int k = 1;
   }
}
```

해결 방법:

```cpp
// C2360b.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      { int j = 1; int i = 1;}
   case 1 :
      int k = 1;
   }
}
```
