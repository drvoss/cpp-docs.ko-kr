---
title: 컴파일러 경고(수준 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: fa948865685af4cbd6a865cfbf1d8546b29ab280
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161141"
---
# <a name="compiler-warning-level-4-c4221"></a>컴파일러 경고(수준 4) C4221

비표준 확장이 사용 됨: ' identifier ': 자동 변수의 주소를 사용 하 여 초기화할 수 없습니다.

기본 Microsoft 확장 (/Ze)을 사용 하면 로컬 (자동) 변수의 주소를 사용 하 여 집계 형식 (**array**, `struct`또는 **union**)을 초기화할 수 있습니다.

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
