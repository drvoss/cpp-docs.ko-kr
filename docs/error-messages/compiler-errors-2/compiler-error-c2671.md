---
title: 컴파일러 오류 C2671
ms.date: 11/04/2016
f1_keywords:
- C2671
helpviewer_keywords:
- C2671
ms.assetid: fc0ee40f-c8f3-408f-b89d-745d149c4169
ms.openlocfilehash: 795c3413699a2af0ae587980a658baa2bbcdd887
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216130"
---
# <a name="compiler-error-c2671"></a>컴파일러 오류 C2671

' function ': 정적 멤버 함수에 ' this ' 포인터가 없습니다.

**`static`** 멤버 함수가에 액세스 하려고 했습니다 **`this`** .

다음 샘플에서는 C2671를 생성 합니다.

```cpp
// C2671.cpp
struct S {
   static S* const func() { return this; }  // C2671
};
```
