---
title: 컴파일러 오류 C2992
ms.date: 11/04/2016
f1_keywords:
- C2992
helpviewer_keywords:
- C2992
ms.assetid: 01b16447-43fe-4e91-9a5a-af884a166a31
ms.openlocfilehash: a51e87980eba90eb4e543a3d07a44c1b170334e9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214557"
---
# <a name="compiler-error-c2992"></a>컴파일러 오류 C2992

'class': 형식 매개 변수 목록이 잘못되었거나 없습니다.

클래스 앞에 **`template`** 또는 **제네릭** 키워드가 없거나 잘못 된 매개 변수가 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2992를 생성합니다.

```cpp
// C2992.cpp
// compile with: /c
template <class T>
struct TC1 {
   template <class U>
   struct TC2;
};

template <class T>   struct TC1<T>::TC2 {};   // C2992

// OK
template <class T>
template <class U>
struct TC1<T>::TC2 {};
// C2992 can also occur when using generics:
// C2992c.cpp
// compile with: /clr /c
generic <class T>
ref struct GC1 {
   generic <class U>
   ref struct GC2;
};

generic <class T> ref struct GC1<T>::GC2 {};   // C2992

// OK
generic <class T>
generic <class U>
ref struct GC1<T>::GC2 {};
```
