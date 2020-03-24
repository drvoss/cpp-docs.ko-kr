---
title: 컴파일러 경고(수준 1) C4602
ms.date: 11/04/2016
f1_keywords:
- C4602
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
ms.openlocfilehash: f93af5b37c87e30891dd09009b53e73c7d384b1c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162129"
---
# <a name="compiler-warning-level-1-c4602"></a>컴파일러 경고(수준 1) C4602

\#pragma pop_macro: ' 매크로 이름 '이 식별자에 대 한 이전 #pragma push_macro 없습니다.

특정 매크로 대해 [pop_macro](../../preprocessor/pop-macro.md) 를 사용하는 경우 먼저 해당 매크로 이름을 [push_macro](../../preprocessor/push-macro.md)에 전달했어야 합니다. 예를 들어 다음 샘플에서는 C4602를 생성합니다.

```cpp
// C4602.cpp
// compile with: /W1
int main()
{
   #pragma pop_macro("x")   // C4602 x is not on the stack
}
```
