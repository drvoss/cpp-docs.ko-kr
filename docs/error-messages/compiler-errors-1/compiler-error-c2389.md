---
title: 컴파일러 오류 C2389
ms.date: 11/04/2016
f1_keywords:
- C2389
helpviewer_keywords:
- C2389
ms.assetid: 6122dc81-4ee3-49a5-a67d-d867808c9bac
ms.openlocfilehash: 50fa514222b7f51ea28ffdb87bf09a870b80dff7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216247"
---
# <a name="compiler-error-c2389"></a>컴파일러 오류 C2389

'operator': 'nullptr'는 잘못된 피연산자입니다.

**`nullptr`** 는 피연산자 일 수 없습니다.

다음 샘플에서는 C2389를 생성합니다.

```cpp
// C2389.cpp
// compile with: /clr
int main() {
   throw nullptr;   // C2389
}
```
