---
title: 컴파일러 경고(수준 1) C4293
ms.date: 11/04/2016
f1_keywords:
- C4293
helpviewer_keywords:
- C4293
ms.assetid: babecd96-eb51-41a5-9835-462c7a46dbad
ms.openlocfilehash: 6f224996904c583001496e04c020de97bc932738
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175690"
---
# <a name="compiler-warning-level-1-c4293"></a>컴파일러 경고(수준 1) C4293

' operator ': 시프트 횟수가 음수 이거나 너무 큽니다. 정의 되지 않은 동작입니다.

시프트 횟수가 음수 이거나 너무 크면 결과 이미지의 동작이 정의 되지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4293를 생성 합니다.

```cpp
// C4293.cpp
// compile with: /c /W1
unsigned __int64 combine (unsigned lo, unsigned hi) {

   return (hi << 32) | lo;   // C4293

   // try the following line instead
   // return ( (unsigned __int64)hi << 32) | lo;
}
```
