---
title: '함수 호출 연산자: ()'
ms.date: 11/04/2016
helpviewer_keywords:
- ( ) function call operator
- function calls, C++ functions
- () function call operator
- postfix operators [C++]
- function calls, operator
- functions [C++], function-call operator
- function call operator ()
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
ms.openlocfilehash: 08c60ff261e944ed5b54b51a013a6d331f212154
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179772"
---
# <a name="function-call-operator-"></a>함수 호출 연산자: ()

후 위 식 뒤에 함수 호출 연산자 **()** 가 오는 경우 함수 호출이 지정 됩니다.

## <a name="syntax"></a>구문

```
postfix-expression
( [argument-expression-list ] )
```

## <a name="remarks"></a>설명

함수 호출 연산자의 인수는 쉼표로 구분된 0개 이상의 식(함수의 실제 인수)입니다.

*후 위 식은* 함수 식별자 또는 함수 포인터 값과 같은 함수 주소로 계산 되어야 하 고, *인수 식 목록은* 값 (인수)이 함수로 전달 되는 식 목록 (쉼표로 구분)입니다. *argument-expression-list* 인수는 비워둘 수 있습니다.

*후 위 식은* 다음 형식 중 하나 여야 합니다.

- `T` 형식을 반환하는 함수. 선언 예제:

    ```cpp
    T func( int i )
    ```

- `T` 형식을 반환하는 함수의 포인터. 선언 예제:

    ```cpp
    T (*func)( int i )
    ```

- `T` 형식을 반환하는 함수의 참조. 선언 예제:

    ```cpp
    T (&func)(int i)
    ```

- `T` 형식을 반환하는 멤버 포인터 함수 역참조. 함수 호출 예제:

    ```cpp
    (pObject->*pmf)();
    (Object.*pmf)();
    ```

## <a name="example"></a>예제

다음 예제에서는 3개의 인수로 표준 라이브러리 함수 `strcat_s`를 호출합니다.

```cpp
// expre_Function_Call_Operator.cpp
// compile with: /EHsc

#include <iostream>
#include <string>

// C++ Standard Library name space
using namespace std;

int main()
{
    enum
    {
        sizeOfBuffer = 20
    };

    char s1[ sizeOfBuffer ] = "Welcome to ";
    char s2[ ] = "C++";

    strcat_s( s1, sizeOfBuffer, s2 );

    cout << s1 << endl;
}
```

```Output
Welcome to C++
```

## <a name="function-call-results"></a>함수 호출 결과

함수가 참조 형식으로 선언되지 않은 경우 함수 호출은 r-value로 평가됩니다. 참조가 있는 함수는 l-values로 평가하고 대입문의 왼쪽에서 다음과 같이 사용될 수 있습니다.

```cpp
// expre_Function_Call_Results.cpp
// compile with: /EHsc
#include <iostream>
class Point
{
public:
    // Define "accessor" functions as
    // reference types.
    unsigned& x() { return _x; }
    unsigned& y() { return _y; }
private:
    unsigned _x;
    unsigned _y;
};

using namespace std;
int main()
{
    Point ThePoint;

    ThePoint.x() = 7;           // Use x() as an l-value.
    unsigned y = ThePoint.y();  // Use y() as an r-value.

    // Use x() and y() as r-values.
    cout << "x = " << ThePoint.x() << "\n"
         << "y = " << ThePoint.y() << "\n";
}
```

위의 코드는 *x* 및 *y* 좌표를 나타내는 전용 데이터 개체를 포함 하는 `Point`라는 클래스를 정의 합니다. 이러한 데이터 개체를 수정하고 해당 값을 검색해야 합니다. 이 프로그램은 이러한 클래스를 위한 여러 디자인 중 하나이며, `GetX`와 `SetX` 또는 `GetY`와 `SetY` 함수는 사용할 수 있는 디자인입니다.

클래스 형식, 클래스 형식에 대한 포인터 또는 클래스 형식에 대한 참조를 반환하는 함수는 멤버 선택 연산자에 대한 왼쪽 피연산자로 사용할 수 있습니다. 따라서 다음 코드를 사용할 수 있습니다.

```cpp
// expre_Function_Results2.cpp
class A {
public:
   A() {}
   A(int i) {}
   int SetA( int i ) {
      return (I = i);
   }

   int GetA() {
      return I;
   }

private:
   int I;
};

A func1() {
   A a = 0;
   return a;
}

A* func2() {
   A *a = new A();
   return a;
}

A& func3() {
   A *a = new A();
   A &b = *a;
   return b;
}

int main() {
   int iResult = func1().GetA();
   func2()->SetA( 3 );
   func3().SetA( 7 );
}
```

함수를 재귀적으로 호출할 수 있습니다. 함수 선언에 대 한 자세한 내용은 [함수](functions-cpp.md)를 참조 하세요. 관련 자료는 [변환 단위와 링크](../cpp/program-and-linkage-cpp.md)에 있습니다.

## <a name="see-also"></a>참고 항목

[후위 식](../cpp/postfix-expressions.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[함수 호출](../c-language/function-call-c.md)
