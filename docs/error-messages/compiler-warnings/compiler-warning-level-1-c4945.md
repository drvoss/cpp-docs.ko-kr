---
title: 컴파일러 경고(수준 1) C4945
ms.date: 11/04/2016
f1_keywords:
- C4945
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
ms.openlocfilehash: 15a78877dbe70a7f95674092984546219e6a1c78
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199127"
---
# <a name="compiler-warning-level-1-c4945"></a>컴파일러 경고(수준 1) C4945

' symbol ': ' assembly2 '에서 기호를 가져올 수 없습니다. 다른 어셈블리 ' assembly1 '에서 ' 기호 '를 이미 가져왔습니다.

참조 된 어셈블리에서 기호를 가져왔지만 해당 기호를 이미 참조 된 다른 어셈블리에서 가져왔습니다. 어셈블리 중 하나를 참조 하지 않거나 어셈블리 중 하나에서 변경 된 기호 이름을 가져옵니다.

다음 샘플에서는 C4945를 생성 합니다.

```csharp
// C4945a.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

그런 다음

```csharp
// C4945b.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

그런 다음

```cpp
// C4945c.cpp
// compile with: /clr /LD /W1
#using "C4945a.dll"
#using "C4945b.dll"   // C4945
```
