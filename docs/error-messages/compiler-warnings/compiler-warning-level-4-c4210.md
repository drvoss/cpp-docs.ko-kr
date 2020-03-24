---
title: 컴파일러 경고(수준 4) C4210
ms.date: 11/04/2016
f1_keywords:
- C4210
helpviewer_keywords:
- C4210
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
ms.openlocfilehash: e37ff1fbcfd2ad4088a94204374b33c2c103797c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161323"
---
# <a name="compiler-warning-level-4-c4210"></a>컴파일러 경고(수준 4) C4210

비표준 확장이 사용 됨: 함수에서 지정 된 파일 범위를 사용 합니다.

기본 Microsoft 확장 ([/ze](../../build/reference/za-ze-disable-language-extensions.md))을 사용 하는 함수 선언에는 파일 범위가 있습니다.

```c
// C4210.c
// compile with: /W4 /c
void func1()
{
   extern int func2( double );   // C4210 expected
}

int main()
{
   func2( 4 );   //  /Ze passes 4 as type double
}                //  /Za passes 4 as type int
```

이 확장을 통해 코드를 다른 컴파일러로 이식할 수 없게 될 수 있습니다.
