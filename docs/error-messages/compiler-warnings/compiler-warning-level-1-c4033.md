---
title: 컴파일러 경고(수준 1) C4033
ms.date: 11/04/2016
f1_keywords:
- C4033
helpviewer_keywords:
- C4033
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
ms.openlocfilehash: bace6057a7a2981bba2d628d8eb21c67f01c3a22
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230755"
---
# <a name="compiler-warning-level-1-c4033"></a>컴파일러 경고(수준 1) C4033

'function'은 값을 반환해야 합니다.

함수가 값을 반환하지 않습니다. 정의되지 않은 값이 반환됩니다.

반환 값 없이을 사용 하는 함수를 **`return`** 형식으로 선언 해야 합니다 **`void`** .

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
