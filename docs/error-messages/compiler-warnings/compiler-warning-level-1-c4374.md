---
title: 컴파일러 경고(수준 1) C4374
ms.date: 11/04/2016
f1_keywords:
- C4374
helpviewer_keywords:
- C4374
ms.assetid: 4ac9aaec-d815-4b6e-825f-fa872092dd3b
ms.openlocfilehash: a0dbfbe931ec30c0bde2e82718e0817dcfa243b7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187039"
---
# <a name="compiler-warning-level-1-c4374"></a>컴파일러 경고(수준 1) C4374

' function1 ': 인터페이스 메서드는 비가상 메서드 ' function2 '에 의해 구현 되지 않습니다.

컴파일러는 메서드 정의에서 [가상](../../cpp/virtual-specifier.md) 키워드를 찾아야 합니다.

다음 샘플에서는 C4374를 생성 합니다.

```cpp
// C4374.cpp
// compile with: /clr /W1 /c /WX
public interface class I {
   void f();
};

public ref struct B {
   void f() {
      System::Console::WriteLine("B::f()");
   }
};

public ref struct C {
   virtual void f() {
      System::Console::WriteLine("C::f()");
   }
};

public ref struct D : B, I {};   // C4374
public ref struct E : C, I {};   // OK
```
