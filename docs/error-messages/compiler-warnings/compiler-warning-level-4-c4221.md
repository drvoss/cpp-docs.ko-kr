---
title: 컴파일러 경고(수준 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: e925f315e8506453403b0a0eda75b7c2956cc05c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219939"
---
# <a name="compiler-warning-level-4-c4221"></a>컴파일러 경고(수준 4) C4221

비표준 확장이 사용 됨: ' identifier ': 자동 변수의 주소를 사용 하 여 초기화할 수 없습니다.

기본 Microsoft 확장 (/Ze)을 사용 하면**array** **`struct`** **`union`** 로컬 (자동) 변수의 주소를 사용 하 여 집계 형식 (배열, 또는)을 초기화할 수 있습니다.

## <a name="example"></a>예제

```c
// C4221.c
// compile with: /W4
struct S
{
   int *i;
};

void func()
{
   int j;
   struct S s1 = { &j };   // C4221
}

int main()
{
}
```

이러한 초기화는 ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 유효 하지 않습니다.
