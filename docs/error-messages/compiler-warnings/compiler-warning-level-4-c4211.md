---
title: 컴파일러 경고(수준 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: df19f90e17d6737a2639eb1245da197881e35c96
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218106"
---
# <a name="compiler-warning-level-4-c4211"></a>컴파일러 경고(수준 4) C4211

비표준 확장이 사용 됨: extern에서 static으로 재정의 되었습니다.

기본 Microsoft 확장 (/Ze)을 사용 하면 식별자를로 재정의할 수 있습니다 **`extern`** **`static`** .

## <a name="example"></a>예제

```c
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

이러한 재정의는 ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 유효 하지 않습니다.
