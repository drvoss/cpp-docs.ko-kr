---
title: 컴파일러 경고(수준 1) C4329
ms.date: 11/04/2016
f1_keywords:
- C4329
helpviewer_keywords:
- C4329
ms.assetid: 4316f51a-2c56-4b3f-831e-65d24b83b65c
ms.openlocfilehash: ed68b0b2bbbf4a08b4bcd1e2eea4f84346902b62
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230690"
---
# <a name="compiler-warning-level-1-c4329"></a>컴파일러 경고(수준 1) C4329

열거형에서 __declspec (align ())은 무시 됩니다.

[__Declspec](../../cpp/declspec.md) 한정자의 [align](../../cpp/align-cpp.md) 키워드를 사용할 수 없습니다 **`enum`** . 다음 샘플에서는 C4329를 생성 합니다.

```cpp
// C4329.cpp
// compile with: /W1 /LD
enum __declspec(align(256)) TestEnum {   // C4329
   TESTVAL1,
   TESTVAL2,
   TESTVAL3
};
__declspec(align(256)) enum TestEnum1;
```
