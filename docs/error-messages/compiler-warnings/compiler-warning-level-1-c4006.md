---
title: 컴파일러 경고(수준 1) C4006
ms.date: 11/04/2016
f1_keywords:
- C4006
helpviewer_keywords:
- C4006
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
ms.openlocfilehash: b589a4bd6b9e14ec926f634f12883e02bf450514
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164718"
---
# <a name="compiler-warning-level-1-c4006"></a>컴파일러 경고(수준 1) C4006

\#undef에 식별자가 필요 합니다.

`#undef` 지시문에서 정의 해제할 식별자를 지정하지 않았습니다. 지시문이 무시됩니다. 이 경고를 해결하려면 식별자를 지정해야 합니다. 다음 샘플에서는 C4006을 생성합니다.

```cpp
// C4006.cpp
// compile with: /W1
#undef   // C4006

// try..
// #undef TEST

int main() {
}
```
