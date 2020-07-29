---
title: dynamic_cast 연산자
description: C + + 언어 dynamic_cast 연산자의 개요입니다.
ms.date: 02/03/2020
f1_keywords:
- dynamic_cast_cpp
helpviewer_keywords:
- dynamic_cast keyword [C++]
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
ms.openlocfilehash: 15609aeaef815ff89ca196876e1143090c65221b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221642"
---
# <a name="dynamic_cast-operator"></a>dynamic_cast 연산자

피연산자를 `expression` 형식의 개체로 변환 합니다 `type-id` .

## <a name="syntax"></a>구문

```
dynamic_cast < type-id > ( expression )
```

## <a name="remarks"></a>설명

는 `type-id` 포인터 이거나 이전에 정의 된 클래스 형식에 대 한 참조 또는 "void에 대 한 포인터" 여야 합니다. `type-id`이 포인터인 경우 `expression`의 형식은 포인터여야 하며 `type-id`이 참조인 경우에는 l 값이어야 합니다.

정적 변환과 동적 캐스팅 간의 차이점에 대 한 설명과 각각을 사용 하는 것이 적절 한 경우 [static_cast](../cpp/static-cast-operator.md) 를 참조 하세요.

관리 코드에서의 동작에는 다음과 같은 두 가지 주요 변경 사항이 있습니다 **`dynamic_cast`** .

- **`dynamic_cast`** boxed 열거형의 기본 형식에 대 한 포인터는 런타임에 실패 하 여 변환 된 포인터 대신 0을 반환 합니다.

- **`dynamic_cast`**`type-id`가 런타임에 캐스팅이 실패 하는 값 형식에 대 한 내부 포인터인 경우에서 더 이상 예외를 throw 하지 않습니다.  이제 cast는를 throw 하는 대신 0 포인터 값을 반환 합니다.

`type-id`이의 모호 하 게 액세스할 수 있는 직접 또는 간접 기본 클래스에 대 한 포인터인 경우 `expression` 형식의 고유 하위 개체에 대 한 포인터가 `type-id` 결과입니다. 예를 들면 다음과 같습니다.

```cpp
// dynamic_cast_1.cpp
// compile with: /c
class B { };
class C : public B { };
class D : public C { };

void f(D* pd) {
   C* pc = dynamic_cast<C*>(pd);   // ok: C is a direct base class
                                   // pc points to C subobject of pd
   B* pb = dynamic_cast<B*>(pd);   // ok: B is an indirect base class
                                   // pb points to B subobject of pd
}
```

이러한 형식의 변환은 파생 클래스에서 파생 된 클래스에 대 한 클래스 계층 구조를 포인터로 이동 하기 때문에 "업 캐스트" 이라고 합니다. 업 캐스트는 암시적 변환입니다.

`type-id`가 void * 인 경우의 실제 형식을 결정 하는 런타임 검사가 수행 됩니다 `expression` . 결과는가 가리키는 전체 개체에 대 한 포인터입니다 `expression` . 예를 들면 다음과 같습니다.

```cpp
// dynamic_cast_2.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};

void f() {
   A* pa = new A;
   B* pb = new B;
   void* pv = dynamic_cast<void*>(pa);
   // pv now points to an object of type A

   pv = dynamic_cast<void*>(pb);
   // pv now points to an object of type B
}
```

`type-id`이 void *가 아닌 경우에는에서 가리키는 개체가 `expression` 가 가리키는 형식으로 변환 될 수 있는지 확인 하는 런타임 검사가 수행 됩니다 `type-id` .

의 형식이 형식의 `expression` 기본 클래스인 경우 `type-id` `expression` 실제로 형식의 전체 개체를 가리키는지 여부를 확인 하는 런타임 검사가 수행 됩니다 `type-id` . True 이면 결과는 형식의 전체 개체에 대 한 포인터입니다 `type-id` . 예를 들면 다음과 같습니다.

```cpp
// dynamic_cast_3.cpp
// compile with: /c /GR
class B {virtual void f();};
class D : public B {virtual void f();};

void f() {
   B* pb = new D;   // unclear but ok
   B* pb2 = new B;

   D* pd = dynamic_cast<D*>(pb);   // ok: pb actually points to a D
   D* pd2 = dynamic_cast<D*>(pb2);   // pb2 points to a B not a D
}
```

이러한 형식의 변환을 지정 된 클래스에서 파생 된 클래스로 클래스 계층 구조 아래로 이동 하기 때문에 "다운 캐스트" 라고 합니다.

여러 상속의 경우 모호성에 대 한 가능성이 도입 됩니다. 다음 그림에 표시 된 클래스 계층 구조를 살펴보겠습니다.

CLR 형식의 경우 **`dynamic_cast`** 변환이 암시적으로 수행 될 수 있는 경우 또는 `isinst` 동적 검사를 수행 하 고 변환에 실패 하는 경우를 반환 하는 MSIL 명령으로 발생 합니다 **`nullptr`** .

다음 샘플에서는 **`dynamic_cast`** 를 사용 하 여 클래스가 특정 형식의 인스턴스인지 여부를 확인 합니다.

```cpp
// dynamic_cast_clr.cpp
// compile with: /clr
using namespace System;

void PrintObjectType( Object^o ) {
   if( dynamic_cast<String^>(o) )
      Console::WriteLine("Object is a String");
   else if( dynamic_cast<int^>(o) )
      Console::WriteLine("Object is an int");
}

int main() {
   Object^o1 = "hello";
   Object^o2 = 10;

   PrintObjectType(o1);
   PrintObjectType(o2);
}
```

![여러 상속을 보여 주는 클래스 계층 구조](../cpp/media/vc39011.gif "여러 상속을 보여 주는 클래스 계층 구조") <br/>
여러 상속을 보여 주는 클래스 계층 구조

형식의 개체에 대 한 포인터는 `D` 또는로 안전 하 게 캐스팅 될 수 있습니다 `B` `C` . 그러나 `D` 가 개체를 가리키도록 캐스팅 된 경우 `A` 의 인스턴스는 `A` 어떻게 되나요? 이렇게 하면 캐스팅 오류가 모호해 집니다. 이 문제를 해결 하기 위해 두 가지 명확한 캐스트를 수행할 수 있습니다. 예를 들면 다음과 같습니다.

```cpp
// dynamic_cast_4.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A {virtual void f();};
class D : public B, public C {virtual void f();};

void f() {
   D* pd = new D;
   A* pa = dynamic_cast<A*>(pd);   // C4540, ambiguous cast fails at runtime
   B* pb = dynamic_cast<B*>(pd);   // first cast to B
   A* pa2 = dynamic_cast<A*>(pb);   // ok: unambiguous
}
```

가상 기본 클래스를 사용 하는 경우 추가 모호성을 도입할 수 있습니다. 다음 그림에 표시 된 클래스 계층 구조를 살펴보겠습니다.

![가상 기본 클래스를 보여 주는 클래스 계층 구조](../cpp/media/vc39012.gif "가상 기본 클래스를 보여 주는 클래스 계층 구조") <br/>
가상 기본 클래스를 보여 주는 클래스 계층 구조

이 계층에서 `A` 는 가상 기본 클래스입니다. 클래스의 인스턴스와 하위 개체에 대 한 포인터를 지정 하면 `E` `A` **`dynamic_cast`** 에 대 한 포인터는 `B` 모호성으로 인해 실패 합니다. 먼저 전체 개체로 다시 캐스팅 `E` 한 다음 명확한 방법으로 계층을 백업 하 여 올바른 개체에 연결 해야 합니다 `B` .

다음 그림에 표시 된 클래스 계층 구조를 살펴보겠습니다.

![중복된 기본 클래스를 보여 주는 클래스 계층 구조](../cpp/media/vc39013.gif "중복된 기본 클래스를 보여 주는 클래스 계층 구조") <br/>
중복된 기본 클래스를 보여 주는 클래스 계층 구조

형식의 개체와 하위 개체에 대 한 포인터를 지정 하 여 하위 개체 `E` `D` 에서 맨 왼쪽 하위 개체로 이동할 때 `D` `A` 세 가지 변환을 수행할 수 있습니다. 포인터를 포인터로 변환 하 고, **`dynamic_cast`** `D` 에서로의 변환 `E` ( **`dynamic_cast`** 또는 암시적 변환)을 수행한 다음 `E` `B` ,에서로의 암시적 변환을 `B` `A` 수행할 수 있습니다. 예를 들면 다음과 같습니다.

```cpp
// dynamic_cast_5.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A { };
class D {virtual void f();};
class E : public B, public C, public D {virtual void f();};

void f(D* pd) {
   E* pe = dynamic_cast<E*>(pd);
   B* pb = pe;   // upcast, implicit conversion
   A* pa = pb;   // upcast, implicit conversion
}
```

**`dynamic_cast`** 연산자를 사용 하 여 "교차 캐스트"를 수행할 수도 있습니다. 같은 클래스 계층 구조를 사용 하는 경우 `B` 전체 개체가 형식이 면 하위 개체에서 하위 개체로 포인터를 캐스팅할 수 있습니다 `D` `E` .

교차 캐스트를 고려 하 여 `D` 두 단계에서 가장 왼쪽에 있는 하위 개체에 대 한 포인터로 포인터를 변환 하는 것이 실제로 가능 `A` 합니다. 에서로의 교차 캐스트를 수행한 `D` `B` 다음에서로의 암시적 변환을 수행할 수 있습니다 `B` `A` . 예를 들면 다음과 같습니다.

```cpp
// dynamic_cast_6.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A { };
class D {virtual void f();};
class E : public B, public C, public D {virtual void f();};

void f(D* pd) {
   B* pb = dynamic_cast<B*>(pd);   // cross cast
   A* pa = pb;   // upcast, implicit conversion
}
```

Null 포인터 값은에 의해 대상 형식의 null 포인터 값으로 변환 됩니다 **`dynamic_cast`** .

를 사용 하 `dynamic_cast < type-id > ( expression )` 는 경우를 `expression` 형식으로 안전 하 게 변환할 수 없는 경우 `type-id` 런타임 검사로 인해 캐스팅이 실패 합니다. 예를 들면 다음과 같습니다.

```cpp
// dynamic_cast_7.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};

void f() {
   A* pa = new A;
   B* pb = dynamic_cast<B*>(pa);   // fails at runtime, not safe;
   // B not derived from A
}
```

포인터 형식으로의 실패 한 캐스트 값은 null 포인터입니다. 참조 형식으로의 캐스팅이 실패 하면 [Bad_cast 예외가](../cpp/bad-cast-exception.md)throw 됩니다.   `expression`가 유효한 개체를 가리키지 않거나 참조 하지 않는 경우 `__non_rtti_object` 예외가 throw 됩니다.

예외에 대 한 설명은 [typeid](../cpp/typeid-operator.md) 를 참조 하십시오 `__non_rtti_object` .

## <a name="example"></a>예제

다음 샘플에서는 개체 (구조체 C)에 대 한 기본 클래스 (구조체 A) 포인터를 만듭니다.  여기에는 가상 함수를 비롯 하 여 런타임 다형성이 있습니다.

또한이 샘플에서는 계층에서 비가상 함수를 호출 합니다.

```cpp
// dynamic_cast_8.cpp
// compile with: /GR /EHsc
#include <stdio.h>
#include <iostream>

struct A {
    virtual void test() {
        printf_s("in A\n");
   }
};

struct B : A {
    virtual void test() {
        printf_s("in B\n");
    }

    void test2() {
        printf_s("test2 in B\n");
    }
};

struct C : B {
    virtual void test() {
        printf_s("in C\n");
    }

    void test2() {
        printf_s("test2 in C\n");
    }
};

void Globaltest(A& a) {
    try {
        C &c = dynamic_cast<C&>(a);
        printf_s("in GlobalTest\n");
    }
    catch(std::bad_cast) {
        printf_s("Can't cast to C\n");
    }
}

int main() {
    A *pa = new C;
    A *pa2 = new B;

    pa->test();

    B * pb = dynamic_cast<B *>(pa);
    if (pb)
        pb->test2();

    C * pc = dynamic_cast<C *>(pa2);
    if (pc)
        pc->test2();

    C ConStack;
    Globaltest(ConStack);

   // will fail because B knows nothing about C
    B BonStack;
    Globaltest(BonStack);
}
```

```Output
in C
test2 in B
in GlobalTest
Can't cast to C
```

## <a name="see-also"></a>참고 항목

[캐스팅 연산자](../cpp/casting-operators.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)
