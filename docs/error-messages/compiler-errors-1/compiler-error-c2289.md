---
title: 컴파일러 오류 C2289
ms.date: 11/04/2016
f1_keywords:
- C2289
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
ms.openlocfilehash: 239552eb383197e57fcc6285cbf416c7c71c858b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216273"
---
# <a name="compiler-error-c2289"></a>컴파일러 오류 C2289

동일한 형식 한정자를 두 번 이상 사용했습니다.

형식 선언 또는 정의에서 형식 한정자 (,, **`const`** 또는)를 두 번 이상 사용 하 여 **`volatile`** **`signed`** **`unsigned`** ANSI 호환성 (**/za**)에서 오류를 발생 시킵니다.

다음 샘플에서는 C2286을 생성합니다.

```cpp
// C2289.cpp
// compile with: /Za /c
volatile volatile int i;   // C2289
volatile int j;   // OK
```
