---
title: 컴파일러 경고 (수준 1) C4114
ms.date: 11/04/2016
f1_keywords:
- C4114
helpviewer_keywords:
- C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
ms.openlocfilehash: 8d2b0339ff3cce9a68dce57a5f2b4efac076c5c2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233316"
---
# <a name="compiler-warning-level-1-c4114"></a>컴파일러 경고 (수준 1) C4114

동일한 형식 한정자를 두 번 이상 사용했습니다.

형식 선언 또는 정의에서 형식 한정자 (,, **`const`** **`volatile`** **`signed`** 또는 **`unsigned`** )를 두 번 이상 사용 합니다. 이로 인해 Microsoft 확장 (/Ze)과 ANSI 호환성 (/Za)에서 오류가 발생 합니다.

다음 샘플에서는 C4114를 생성 합니다.

```cpp
// C4114.cpp
// compile with: /W1 /c
volatile volatile int i;   // C4114
```

다음 샘플에서는 C4114를 생성 합니다.

```cpp
// C4114_b.cpp
// compile with: /W1 /c
static const int const * ii;   // C4114
static const int * const iii;   // OK
```
