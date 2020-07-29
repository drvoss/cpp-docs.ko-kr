---
title: 컴파일러 오류 C2180
ms.date: 11/04/2016
f1_keywords:
- C2180
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
ms.openlocfilehash: 3794a1ce0fcbe60c06cb3efca45a3081e85c17ce
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87210022"
---
# <a name="compiler-error-c2180"></a>컴파일러 오류 C2180

제어 식이 'type' 형식입니다.

**`if`**, **`while`** , **`for`** 또는 문의 제어 식은 **`do`** 로 캐스팅 되는 식입니다 **`void`** . 이 문제를 해결 하려면 제어 식을 또는로 변환할 수 있는 형식을 생성 하는 식으로 변경 **`bool`** **`bool`** 합니다.

다음 샘플에서는 C2180 오류가 발생하는 경우를 보여 줍니다.

```c
// C2180.c

int main() {
   while ((void)1)   // C2180
      return 1;
   while (1)         // OK
      return 0;
}
```
