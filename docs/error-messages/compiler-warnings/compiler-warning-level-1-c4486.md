---
title: 컴파일러 경고(수준 1) C4486
ms.date: 11/04/2016
f1_keywords:
- C4486
helpviewer_keywords:
- C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
ms.openlocfilehash: 0ba3a8f9e60ab0b84266dd25b6b9ccfe10f75561
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186714"
---
# <a name="compiler-warning-level-1-c4486"></a>컴파일러 경고(수준 1) C4486

' function ': ref 클래스 또는 값 클래스의 전용 가상 메서드는 ' sealed '로 표시 되어야 합니다.

관리 되는 클래스 또는 구조체의 전용 가상 멤버 함수는 액세스 하거나 재정의할 수 없으므로 [sealed](../../extensions/sealed-cpp-component-extensions.md)로 표시 되어야 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4486를 생성 합니다.

```cpp
// C4486.cpp
// compile with: /clr /c /W1
ref class B {
private:
   virtual void f() {}   // C4486
   virtual void f1() sealed {}   // OK
};
```

## <a name="example"></a>예제

다음 샘플에서는 전용 sealed 가상 함수를 사용 하는 한 가지 방법을 보여 줍니다.

```cpp
// C4486_b.cpp
// compile with: /clr /c
ref class B {};

ref class D : B {};

interface class I {
   B^ mf();
};

ref class E : I {
private:
   virtual B^ g() sealed = I::mf {
      return gcnew B;
   }

public:
   virtual D^ mf() {
      return gcnew D;
   }
};
```
