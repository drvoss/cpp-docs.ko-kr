---
title: 컴파일러 경고 (수준 1) C4090
ms.date: 11/04/2016
f1_keywords:
- C4090
helpviewer_keywords:
- C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
ms.openlocfilehash: 551309757f5e76e230d0a275da94ac94ec30fb13
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163925"
---
# <a name="compiler-warning-level-1-c4090"></a>컴파일러 경고 (수준 1) C4090

' operation ': 다른 ' modifier ' 한정자입니다.

작업에 사용 되는 변수는 컴파일러가 검색 하지 않고 수정 되지 않도록 지정 된 한정자로 정의 됩니다. 식은 수정 하지 않고 컴파일됩니다.

이 경고는 **const 또는 `volatile`** 항목에 대 한 포인터가 **const** 또는 `volatile`를 가리키는 것으로 선언 되지 않은 포인터에 할당 된 경우에 발생할 수 있습니다.

이 경고는 C 프로그램에 대해 실행 됩니다. C++ 프로그램에서 컴파일러는 오류를 발생 시킵니다. [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md).

다음 샘플에서는 C4090를 생성 합니다.

```c
// C4090.c
// compile with: /W1
int *volatile *p;
int *const *q;
int **r;

int main() {
   p = q;   // C4090
   p = r;
   q = p;   // C4090
   q = r;
   r = p;   // C4090
   r = q;   // C4090
}
```
