---
title: 컴파일러 오류 C2933
ms.date: 11/04/2016
f1_keywords:
- C2933
helpviewer_keywords:
- C2933
ms.assetid: 394891e3-6b52-4b61-83d2-a1c5125d9bd5
ms.openlocfilehash: 51889ababd646edebbaf1d0d1a1c608e7b068009
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233420"
---
# <a name="compiler-error-c2933"></a>컴파일러 오류 C2933

'class': type-class-id가 'identifier'의 typedef 멤버로 다시 정의되었습니다.

제네릭 또는 템플릿 클래스를 멤버로 사용할 수 없습니다 **`typedef`** .

다음 샘플에서는 C2933을 생성합니다.

```cpp
// C2933.cpp
// compile with: /c
template<class T> struct TC { };
struct MyStruct {
   typedef int TC<int>;   // C2933
};

struct TC2 { };
struct MyStruct2 {
   typedef int TC2;
};
```

제네릭을 사용할 때도 C2933이 발생할 수 있습니다.

```cpp
// C2933b.cpp
// compile with: /clr /c
generic<class T> ref struct GC { };
struct MyStruct {
   typedef int GC<int>;   // C2933
};

ref struct GC2 { };
struct MyStruct2 {
   typedef int GC2;
};
```
