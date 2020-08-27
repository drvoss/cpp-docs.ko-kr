---
title: 컴파일러 오류 C2703
description: Microsoft C/c + + 컴파일러 오류 C2703에 대해 설명 합니다.
ms.date: 08/24/2020
f1_keywords:
- C2703
helpviewer_keywords:
- C2703
ms.assetid: 384295c3-643d-47ae-a9a6-865b3036aa84
ms.openlocfilehash: 4d5b5ccad1cd15c1a107c81423e2372e14165776
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898601"
---
# <a name="compiler-error-c2703"></a>컴파일러 오류 C2703

> 잘못 된 `__leave` 문

## <a name="remarks"></a>설명

**`__leave`** 문은 블록 내에 있어야 합니다 **`__try`** .

## <a name="example"></a>예

다음 샘플에서는 C2703를 생성 합니다.

```cpp
// C2703.cpp
int main() {
   __leave;   // C2703
   __try {
      // try the following line instead
      __leave;
   }
   __finally {}
}
```

## <a name="see-also"></a>참조

[`__leave`키워드](../../cpp/try-except-statement.md#__leave)\
[`try-except` 선언문](../../cpp/try-except-statement.md)\
[`try-finally` statement](../../cpp/try-finally-statement.md)
