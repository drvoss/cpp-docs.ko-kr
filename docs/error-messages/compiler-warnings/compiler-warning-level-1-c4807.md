---
title: 컴파일러 경고(수준 1) C4807
ms.date: 11/04/2016
f1_keywords:
- C4807
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
ms.openlocfilehash: 2424d076be0914a68c3227566cb851b7ab64cc0f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175040"
---
# <a name="compiler-warning-level-1-c4807"></a>컴파일러 경고(수준 1) C4807

'operation': 'type' 형식과 'type' 형식의 부호 있는 비트 필드를 함께 사용하는 것은 안전하지 않습니다.

이 경고는 1비트 부호 있는 비트 필드를 `bool` 변수와 비교할 때 생성됩니다. 1비트 부호 있는 비트 필드에는 -1 또는 0 값만 포함할 수 있으므로 `bool`과 비교하는 것은 위험합니다. 1비트 부호 없는 비트 필드는 `bool` 과 동일하며 0 또는 1만 포함할 수 있으므로 `bool` 과 함께 사용해도 경고가 생성되지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4807을 생성합니다.

```cpp
// C4807.cpp
// compile with: /W1
typedef struct bitfield {
   signed mybit : 1;
} mybitfield;

int main() {
   mybitfield bf;
   bool b = true;

   // try..
   // int b = true;

   bf.mybit = -1;
   if (b == bf.mybit) {   // C4807
      b = false;
   }
}
```
