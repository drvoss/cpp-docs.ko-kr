---
title: 컴파일러 경고(수준 1) C4033
ms.date: 11/04/2016
f1_keywords:
- C4033
helpviewer_keywords:
- C4033
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
ms.openlocfilehash: d5bee2eb874b965ff99e3dc0038d63d65b346318
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164354"
---
# <a name="compiler-warning-level-1-c4033"></a>컴파일러 경고(수준 1) C4033

'function'은 값을 반환해야 합니다.

함수가 값을 반환하지 않습니다. 정의되지 않은 값이 반환됩니다.

반환 값 없이 `return` 을 사용하는 함수를 `void`형식으로 선언해야 합니다.

이 오류는 C 언어 코드용입니다.

다음 샘플에서는 C4033을 생성합니다.

```c
// C4033.c
// compile with: /W1 /LD
int test_1(int x)   // C4033 expected
{
   if (x)
   {
      return;   // C4033
   }
}
```
