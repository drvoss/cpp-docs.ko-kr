---
title: 컴파일러 경고(수준 3) C4357
ms.date: 11/04/2016
f1_keywords:
- C4357
helpviewer_keywords:
- C4357
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
ms.openlocfilehash: 3af2e742bde40bc3787603e32efbc34e59dcb419
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198707"
---
# <a name="compiler-warning-level-3-c4357"></a>컴파일러 경고(수준 3) C4357

' function '을 생성할 때 ' del ' 대리자의 형식 인수 목록에 있는 param 배열 인수가 무시 되었습니다.

`ParamArray` 특성이 무시 되 고 `function` 변수 인수로 호출할 수 없습니다.

다음 샘플에서는 C4357를 생성 합니다.

```cpp
// C4357.cpp
// compile with: /clr /W3 /c
using namespace System;
public delegate void f(int i, ... array<Object^>^ varargs);   // C4357

public delegate void g(int i, array<Object^>^ varargs);   // OK
```
