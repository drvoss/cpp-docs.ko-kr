---
title: 컴파일러 오류 C2734
ms.date: 11/04/2016
f1_keywords:
- C2734
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
ms.openlocfilehash: b4952f4705ad94133000fe6d84117cb04a5aa850
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206824"
---
# <a name="compiler-error-c2734"></a>컴파일러 오류 C2734

' identifier ': extern이 아닌 경우에는 const 개체를 초기화 해야 합니다.

식별자가 선언 **`const`** 되었지만 초기화 되지 않았습니다 **`extern`** .

다음 샘플에서는 C2734를 생성 합니다.

```cpp
// C2734.cpp
const int j;   // C2734
extern const int i;   // OK, declared as extern
```
