---
title: 컴파일러 오류 C2165
ms.date: 11/04/2016
f1_keywords:
- C2165
helpviewer_keywords:
- C2165
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
ms.openlocfilehash: 29637dd9cb2b1faab537a970df9ef3d76fc26e0c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216351"
---
# <a name="compiler-error-c2165"></a>컴파일러 오류 C2165

'keyword': 데이터에 대한 포인터를 수정할 수 없습니다.

**`__stdcall`**, **`__cdecl`** 또는 **`__fastcall`** 키워드가 데이터에 대 한 포인터를 수정 하려고 합니다.

다음 샘플에서는 C2165를 생성합니다.

```cpp
// C2165.cpp
// compile with: /c
char __cdecl *p;   // C2165
char *p;   // OK
```
