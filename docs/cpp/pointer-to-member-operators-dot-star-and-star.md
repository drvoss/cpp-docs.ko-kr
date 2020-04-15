---
title: '포인터-멤버 연산자: .* 및 -&gt;*'
ms.date: 11/04/2016
f1_keywords:
- .*
- ->*
helpviewer_keywords:
- expressions [C++], pointer
- pointer-to-member operators [C++]
- .* operator
- expressions [C++], operators
- ->* operator
ms.assetid: 2632be3f-1c81-4523-b56c-982a92a68688
ms.openlocfilehash: 2100933bf525f0717978528301049085eaecd4f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320334"
---
# <a name="pointer-to-member-operators--and--gt"></a>포인터-멤버 연산자: .* 및 -&gt;*

## <a name="syntax"></a>구문

```
expression .* expression
expression ->* expression
```

## <a name="remarks"></a>설명

멤버 간 포인터 연산자 .* 및 \*->식의 왼쪽에 지정된 개체에 대한 특정 클래스 멤버의 값을 반환합니다.  오른쪽에는 클래스 멤버를 지정해야 합니다.  다음 예제에서는 이러한 연산자를 사용하는 방법을 보여 줍니다.

```cpp
// expre_Expressions_with_Pointer_Member_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

class Testpm {
public:
   void m_func1() { cout << "m_func1\n"; }
   int m_num;
};

// Define derived types pmfn and pmd.
// These types are pointers to members m_func1() and
// m_num, respectively.
void (Testpm::*pmfn)() = &Testpm::m_func1;
int Testpm::*pmd = &Testpm::m_num;

int main() {
   Testpm ATestpm;
   Testpm *pTestpm = new Testpm;

// Access the member function
   (ATestpm.*pmfn)();
   (pTestpm->*pmfn)();   // Parentheses required since * binds
                        // less tightly than the function call.

// Access the member data
   ATestpm.*pmd = 1;
   pTestpm->*pmd = 2;

   cout  << ATestpm.*pmd << endl
         << pTestpm->*pmd << endl;
   delete pTestpm;
}
```

## <a name="output"></a>출력

```Output
m_func1
m_func1
1
2
```

앞의 예제에서는 멤버 함수 `pmfn`을 호출하기 위해 `m_func1` 멤버에 대한 포인터가 사용되었습니다. 또 다른 멤버 포인터, `pmd`는 `m_num` 멤버에 액세스하는 데 사용됩니다.

.* 이항 연산자는 첫 번째 피연산자(반드시 클래스 형식의 개체)와 두 번째 피연산자(반드시 멤버 포인터 형식)를 결합합니다.

이진 연산자 ->*는 첫 번째 피연산자(s)를 결합하며, 이 피연산자는 클래스 형식의 개체에 대한 포인터여야 하며 두 번째 피연산자는 포인터-멤버 형식이어야 합니다.

.* 연산자가 포함된 식에서 첫 번째 피연산자는 두 번째 피연산자에 지정된 멤버 포인터의 클래스 형식이면서 해당 멤버 포인터에 액세스할 수 있거나 해당 클래스에서 명확히 파생되고 해당 클래스에 액세스할 수 있는 형식이어야 합니다.

->* 연산자가 포함된 식에서 첫 번째 발각자는 두 번째 익연산에 지정된 형식의 "클래스 형식에 대한 포인터"이거나 해당 클래스에서 명확하게 파생된 형식이어야 합니다.

## <a name="example"></a>예제

다음 클래스와 프로그램 부분을 살펴보십시오.

```cpp
// expre_Expressions_with_Pointer_Member_Operators2.cpp
// C2440 expected
class BaseClass {
public:
   BaseClass(); // Base class constructor.
   void Func1();
};

// Declare a pointer to member function Func1.
void (BaseClass::*pmfnFunc1)() = &BaseClass::Func1;

class Derived : public BaseClass {
public:
   Derived();  // Derived class constructor.
   void Func2();
};

// Declare a pointer to member function Func2.
void (Derived::*pmfnFunc2)() = &Derived::Func2;

int main() {
   BaseClass ABase;
   Derived ADerived;

   (ABase.*pmfnFunc1)();   // OK: defined for BaseClass.
   (ABase.*pmfnFunc2)();   // Error: cannot use base class to
                           // access pointers to members of
                           // derived classes.

   (ADerived.*pmfnFunc1)();   // OK: Derived is unambiguously
                              // derived from BaseClass.
   (ADerived.*pmfnFunc2)();   // OK: defined for Derived.
}
```

.* 또는 ->\* 포인터-멤버 연산자의 결과는 멤버에 대한 포인터 선언에 지정된 형식의 개체 또는 함수입니다. 따라서 앞의 예제에서 `ADerived.*pmfnFunc1()` 식의 결과는 void를 반환하는 함수 포인터입니다. 두 번째 피연산자가 l-value인 경우 이 결과는 l-value입니다.

> [!NOTE]
> 멤버 포인터 연산자 중 하나의 결과가 함수인 경우 결과는 함수 호출 연산자에 대한 피연산자로만 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
