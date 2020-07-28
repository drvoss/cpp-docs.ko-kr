---
title: 컴파일러 오류 C2150
ms.date: 11/04/2016
f1_keywords:
- C2150
helpviewer_keywords:
- C2150
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
ms.openlocfilehash: 419aa8229e0fe60d391345556c5fbd8be17558d8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214739"
---
# <a name="compiler-error-c2150"></a>컴파일러 오류 C2150

> '*identifier*': 비트 필드의 형식은 ' int ', ' signed int ' 또는 ' unsigned i n t ' 여야 합니다.

비트 필드의 기본 형식은 **`int`** , 또는 이어야 합니다 **`signed int`** **`unsigned int`** .

## <a name="example"></a>예제

이 샘플에서는 C2150를 발생 시킬 수 있는 방법과이를 해결 하는 방법을 보여 줍니다.

```cpp
// C2150.cpp
// compile with: /c
struct A {
   float a : 8;    // C2150
   int i : 8;      // OK
};
```
