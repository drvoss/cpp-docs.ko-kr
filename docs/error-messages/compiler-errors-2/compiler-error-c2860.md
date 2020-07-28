---
title: 컴파일러 오류 C2860
ms.date: 11/04/2016
f1_keywords:
- C2860
helpviewer_keywords:
- C2860
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
ms.openlocfilehash: 25ae5f0ffee659dee2e0ac388da207a5165ecc8e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214570"
---
# <a name="compiler-error-c2860"></a>컴파일러 오류 C2860

' void '는 ' (void) '를 제외한 인수 형식일 수 없습니다.

형식은 **`void`** 다른 인수를 사용 하는 인수 형식으로 사용할 수 없습니다.

다음 샘플에서는 C2860를 생성 합니다.

```cpp
// C2860.cpp
// compile with: /c
void profunc1(void, int i);   // C2860
void func10(void);   // OK
```
