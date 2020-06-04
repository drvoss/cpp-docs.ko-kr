---
title: 컴파일러 오류 C2150
ms.date: 11/04/2016
f1_keywords:
- C2150
helpviewer_keywords:
- C2150
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
ms.openlocfilehash: 57c21f7ee9435220a9ca0b50bb85567506b6ad3e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80207222"
---
# <a name="compiler-error-c2150"></a>컴파일러 오류 C2150

> '*identifier*': 비트 필드의 형식은 ' int ', ' signed int ' 또는 ' unsigned i n t ' 여야 합니다.

비트 필드의 기본 형식은 `int`, `signed int`또는 `unsigned int`해야 합니다.

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
