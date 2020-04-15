---
title: 생성자 위임(C++)
description: C++에서 위임 생성기를 사용하여 다른 생성자 호출을 호출하고 코드 반복을 줄입니다.
ms.date: 11/19/2019
ms.openlocfilehash: f26a013aa3c081d900ffc3eb32649acc77505db0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316666"
---
# <a name="delegating-constructors"></a>위임 생성자

대부분의 클래스에는 매개 변수의 유효성을 검사하는 것과 같은 유사한 작업을 수행하는 여러 생성자가 있습니다.

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c() {}
    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
        middle = my_middle < max && my_middle > min ? my_middle : 5;
    }
};
```

모든 유효성 검사를 수행하는 함수를 추가하여 반복 코드를 줄일 수 있지만 한 `class_c` 생성자가 일부 작업을 다른 생성자로 위임할 수 있는 경우 코드를 이해하고 유지 관리하는 것이 더 쉽습니다. 위임 생성자 추가하려면 구문을 `constructor (. . .) : constructor (. . .)` 사용합니다.

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) : class_c(my_max) {
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) : class_c (my_max, my_min){
        middle = my_middle < max && my_middle > min ? my_middle : 5;
}
};
int main() {

    class_c c1{ 1, 3, 2 };
}
```

이전 예제를 단계별로 살펴보면 생성자가 `class_c(int, int, int)` 먼저 생성자 `class_c(int, int)`호출을 호출하여 `class_c(int)`생성자가 호출됩니다. 각 생성자는 다른 생성자가 수행하지 않는 작업만 수행합니다.

호출된 첫 번째 생성자는 해당 시점에서 모든 멤버가 초기화되도록 개체를 초기화합니다. 다음과 같이 다른 생성자를 위임하는 생성자에서는 멤버 초기화를 수행할 수 없습니다.

```cpp
class class_a {
public:
    class_a() {}
    // member initialization here, no delegate
    class_a(string str) : m_string{ str } {}

    //can’t do member initialization here
    // error C3511: a call to a delegating constructor shall be the only member-initializer
    class_a(string str, double dbl) : class_a(str) , m_double{ dbl } {}

    // only member assignment
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string;
};
```

다음 예제에서는 비정적 데이터 멤버 초기화자의 사용을 보여 주며 있습니다. 생성자가 지정된 데이터 멤버를 초기화하는 경우 멤버 초기화가 재정의됩니다.

```cpp
class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string{ m_double < 10.0 ? "alpha" : "beta" };
};

int main() {
    class_a a{ "hello", 2.0 };  //expect a.m_double == 2.0, a.m_string == "hello"
    int y = 4;
}
```

생성자 위임 구문은 생성자 재귀의 실수로 생성을 방지 하지 않습니다-Constructor1 생성자1 을 호출 하는 Constructor2 호출 생성자 1-스택 오버플로가 있을 때까지 오류가 throw 되지 않습니다. 그것은 주기를 피하기 위해 귀하의 책임.

```cpp
class class_f{
public:
    int max;
    int min;

    // don't do this
    class_f() : class_f(6, 3){ }
    class_f(int my_max, int my_min) : class_f() { }
};
```
