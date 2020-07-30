---
title: 컴파일러 오류 C2428
ms.date: 11/04/2016
f1_keywords:
- C2428
helpviewer_keywords:
- C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
ms.openlocfilehash: 2a85e1874a03882ca8497eeff379d377a585fe06
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216234"
---
# <a name="compiler-error-c2428"></a>컴파일러 오류 C2428

' operation ': ' bool ' 형식의 피연산자에 사용할 수 없습니다.

유형의 개체에 감소 연산자를 적용할 수 없습니다 **`bool`** .

다음 샘플에서는 C2428를 생성 합니다.

```cpp
// C2428.cpp
void g(bool fFlag) {
   --fFlag;   // C2428
   fFlag--;   // C2428
}
```
