---
title: 컴파일러 경고(수준 1) C4224
ms.date: 11/04/2016
f1_keywords:
- C4224
helpviewer_keywords:
- C4224
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
ms.openlocfilehash: c58b003e43e74886c65d41e9abd6e49d15825653
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220095"
---
# <a name="compiler-warning-level-1-c4224"></a>컴파일러 경고(수준 1) C4224

비표준 확장이 사용 됨: ' identifier ' 정식 매개 변수가 이전에 형식으로 정의 되었습니다.

식별자는 이전에로 사용 되었습니다 **`typedef`** . 이렇게 하면 ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 경고가 발생 합니다.

## <a name="example"></a>예제

```cpp
// C4224.cpp
// compile with: /Za /W1 /LD
typedef int I;
void func ( int I );  // C4224
```
