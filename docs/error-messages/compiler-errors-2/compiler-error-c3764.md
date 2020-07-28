---
title: 컴파일러 오류 C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: 657cb6598eedf8abd050b47c124c78c3a028509f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214505"
---
# <a name="compiler-error-c3764"></a>컴파일러 오류 C3764

' override_function ': 기본 클래스 메서드 ' base_class_function '을 (를) 재정의할 수 없습니다.

컴파일러가 잘못 된 형식의 재정의를 검색 했습니다. 예를 들어 기본 클래스 함수는이 아닙니다 **`virtual`** . 자세한 내용은 [override](../../extensions/override-cpp-component-extensions.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3764를 생성 합니다.

```cpp
// C3764.cpp
// compile with: /clr /c
public ref struct A {
   void g(int);
   virtual void h(int);
};

public ref struct B : A {
   virtual void g(int) override {}   // C3764
   virtual void h(int) override {}   // OK
};
```

## <a name="example"></a>예제

C3764 기본 클래스 메서드가 명시적이 고 이름이 재정의 된 경우에도 발생할 수 있습니다. 다음 샘플에서는 C3764를 생성 합니다.

```cpp
// C3764_b.cpp
// compile with: /clr /c
ref struct A {
   virtual void Test() {}
};

ref struct B : public A {
   virtual void Test() override {}
   virtual void Test2() = A::Test {}   // C3764
};
```
