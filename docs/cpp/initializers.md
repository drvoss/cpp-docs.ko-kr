---
title: 이니셜라이저
ms.date: 07/29/2019
description: 에서 C++클래스, 구조체, 배열 및 기본 형식을 초기화 하는 방법입니다.
helpviewer_keywords:
- arrays [C++], array-element initializers
- aggregate initializers [C++]
ms.assetid: ce301ed8-aa1c-47b2-bb39-9f0541b4af85
ms.openlocfilehash: 2cc68f2384402ce1eb3ac06b414f597a6b3951f0
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423743"
---
# <a name="initializers"></a>이니셜라이저

이니셜라이저는 변수의 초기 값을 지정합니다. 변수를 초기화할 수 있는 컨텍스트는 다음과 같습니다.

- 변수 정의

    ```cpp
    int i = 3;
    Point p1{ 1, 2 };
    ```

- 함수 매개 변수 중 하나

    ```cpp
    set_point(Point{ 5, 6 });
    ```

- 함수의 반환 값으로서 초기화

    ```cpp
    Point get_new_point(int x, int y) { return { x, y }; }
    Point get_new_point(int x, int y) { return Point{ x, y }; }
    ```

이니셜라이저가 사용할 수 있는 폼은 다음과 같습니다.

- 괄호 안에 있는 식(또는 쉼표로 구분된 식 목록)

    ```cpp
    Point p1(1, 2);
    ```

- 등호 뒤에 식

    ```cpp
    string s = "hello";
    ```

- 중괄호로 묶인 이니셜라이저 목록 목록은 다음 예제와 같이 비어 있을 수도 있고, 목록 집합으로 구성될 수도 있습니다.

    ```cpp
    struct Point{
        int x;
        int y;
    };
    class PointConsumer{
    public:
        void set_point(Point p){};
        void set_points(initializer_list<Point> my_list){};
    };
    int main() {
        PointConsumer pc{};
        pc.set_point({});
        pc.set_point({ 3, 4 });
        pc.set_points({ { 3, 4 }, { 5, 6 } });
    }
    ```

## <a name="kinds-of-initialization"></a>초기화 종류

초기화는 여러 종류가 있으며 프로그램 실행의 여러 지점에서 발생할 수 있습니다. 다양한 종류의 초기화는 상호 배타적이지 않습니다. 예를 들어 목록 초기화는 값 초기화를 트리거할 수 있고 다른 상황에서는 집합체 초기화를 트리거할 수 있습니다.

### <a name="zero-initialization"></a>0 초기화

0 초기화는 변수를 암시적으로 형식으로 변환된 0으로 설정하는 것입니다.

- 숫자 변수는 0(또는 0.0 또는 0.0000000000 등)으로 초기화됩니다.

- Char 변수는 `'\0'`으로 초기화 됩니다.

- 포인터는 **nullptr**로 초기화 됩니다.

- 배열, [POD](../standard-library/is-pod-class.md) 클래스, 구조체 및 공용 구조체의 멤버는 0 값으로 초기화 됩니다.

0 초기화는 다음과 같은 다양한 시간에 수행됩니다.

- 프로그램 시작 시 - 정적 지속 시간이 있는 명명된 모든 변수 이러한 변수는 나중에 다시 초기화할 수 있습니다.

- 값을 초기화하는 동안 - 빈 중괄호를 사용하여 초기화된 스칼라 형식 및 POD 클래스 형식

- 멤버의 하위 집합만 초기화된 어레이

0 초기화의 몇 가지 예제는 다음과 같습니다.

```cpp
struct my_struct{
    int i;
    char c;
};

int i0;              // zero-initialized to 0
int main() {
    static float f1;  // zero-initialized to 0.000000000
    double d{};     // zero-initialized to 0.00000000000000000
    int* ptr{};     // initialized to nullptr
    char s_array[3]{'a', 'b'};  // the third char is initialized to '\0'
    int int_array[5] = { 8, 9, 10 };  // the fourth and fifth ints are initialized to 0
    my_struct a_struct{};   // i = 0, c = '\0'
}
```

### <a name="default_initialization"></a>기본 초기화

기본 생성자를 사용하는 클래스, 구조체 및 공용 구조체에 대한 기본 초기화입니다. 기본 생성자는 초기화 식이나 **new** 키워드를 사용 하 여 호출할 수 있습니다.

```cpp
MyClass mc1;
MyClass* mc3 = new MyClass;
```

클래스, 구조체 또는 공용 구조체에 기본 생성자가 있으면 컴파일러가 오류를 내보냅니다.

스칼라 변수는 초기화 식 없이 정의할 경우 기본값으로 초기화됩니다. 비활성화 상태 값입니다.

```cpp
int i1;
float f;
char c;
```

배열은 초기화 식 없이 정의할 경우 기본값으로 초기화됩니다. 배열이 기본값으로 초기화되면 다음 예제와 같이 멤버가 기본값으로 초기화되고 비활성화 상태 값을 가집니다.

```cpp
int int_arr[3];
```

배열에 기본 생성자가 없는 경우, 컴파일러가 오류를 내보냅니다.

#### <a name="default-initialization-of-constant-variables"></a>상수 변수의 기본 초기화

상수 변수는 이니셜라이저와 함께 선언해야 합니다. 스칼라 형식인 경우 컴파일러 오류가 발생되고 기본 생성자가 있는 클래스 형식인 경우 경고가 발생됩니다.

```cpp
class MyClass{};
int main() {
    //const int i2;   // compiler error C2734: const object must be initialized if not extern
    //const char c2;  // same error
    const MyClass mc1; // compiler error C4269: 'const automatic data initialized with compiler generated default constructor produces unreliable results
}
```

#### <a name="default-initialization-of-static-variables"></a>정적 변수의 기본 초기화

이니셜라이저 없이 선언된 정적 변수는 0으로 초기화됩니다(형식으로 암시적으로 변환).

```cpp
class MyClass {
private:
    int m_int;
    char m_char;
};

int main() {
    static int int1;       // 0
    static char char1;     // '\0'
    static bool bool1;   // false
    static MyClass mc1;     // {0, '\0'}
}
```

전역 정적 개체의 초기화에 대 한 자세한 내용은 [main 함수 및 명령줄 인수](main-function-command-line-args.md)를 참조 하세요.

### <a name="value-initialization"></a>값 초기화

값 초기화는 다음과 같은 경우에 발생합니다.

- 명명된 값이 빈 중괄호 초기화를 사용하여 초기화됩니다.

- 익명의 임시 개체가 빈 괄호나 중괄호를 사용하여 초기화됩니다.

- **새** 키워드와 빈 괄호 또는 중괄호를 사용 하 여 개체를 초기화 합니다.

값 초기화가 수행하는 작업은 다음과 같습니다.

- 하나 이상의 공용 생성자가 있는 클래스의 경우 기본 생성자가 호출됩니다.

- 선언된 생성자가 없는 공용 구조체가 아닌 클래스의 경우 개체가 0으로 초기화되고 기본 생성자가 호출됩니다.

- 배열의 경우 모든 요소의 값이 초기화됩니다.

- 다른 모든 경우에는 변수가 0으로 초기화됩니다.

```cpp
class BaseClass {
private:
    int m_int;
};

int main() {
    BaseClass bc{};     // class is initialized
    BaseClass*  bc2 = new BaseClass();  // class is initialized, m_int value is 0
    int int_arr[3]{};  // value of all members is 0
    int a{};     // value of a is 0
    double b{};  // value of b is 0.00000000000000000
}
```

### <a name="copy-initialization"></a>복사 초기화

복사 초기화는 하나의 개체를 다른 개체로 초기화하는 것입니다. 다음과 같은 경우에 발생합니다.

- 변수가 등호를 사용하여 초기화됩니다.

- 인수가 함수에 전달됩니다.

- 개체가 함수에서 반환됩니다.

- 예외가 발생하거나 catch됩니다.

- 비정적 데이터 멤버가 등호를 사용하여 초기화됩니다.

- 클래스, 구조체 및 공용 구조체 멤버가 집합체 초기화 중에 복사 초기화로 초기화됩니다. 예제는 [집합체 초기화](#agginit) 를 참조 하세요.

다음 코드는 복사 초기화의 몇 가지 예를 보여 줍니다.

```cpp
#include <iostream>
using namespace std;

class MyClass{
public:
    MyClass(int myInt) {}
    void set_int(int myInt) { m_int = myInt; }
    int get_int() const { return m_int; }
private:
    int m_int = 7; // copy initialization of m_int

};
class MyException : public exception{};
int main() {
    int i = 5;              // copy initialization of i
    MyClass mc1{ i };
    MyClass mc2 = mc1;      // copy initialization of mc2 from mc1
    MyClass mc1.set_int(i);    // copy initialization of parameter from i
    int i2 = mc2.get_int(); // copy initialization of i2 from return value of get_int()

    try{
        throw MyException();
    }
    catch (MyException ex){ // copy initialization of ex
        cout << ex.what();
    }
}
```

복사 초기화는 명시적 생성자를 호출할 수 없습니다.

```cpp
vector<int> v = 10; // the constructor is explicit; compiler error C2440: cannot convert from 'int' to 'std::vector<int,std::allocator<_Ty>>'
regex r = "a.*b"; // the constructor is explicit; same error
shared_ptr<int> sp = new int(1729); // the constructor is explicit; same error
```

경우에 따라 클래스의 복사 생성자가 삭제되거나 액세스할 수 없는 경우 복사 초기화로 컴파일러 오류가 발생합니다.

### <a name="direct-initialization"></a>직접 초기화

직접 초기화는 (비어 있지 않은) 중괄호 또는 괄호를 사용한 초기화입니다. 복사 초기화와는 달리 명시적 생성자를 호출할 수 있습니다. 다음과 같은 경우에 발생합니다.

- 변수가 비어 있지 않은 중괄호 또는 괄호를 사용하여 초기화됩니다.

- 변수가 **new** 키워드와 비어 있지 않은 중괄호 또는 괄호를 사용 하 여 초기화 됩니다.

- 변수는를 사용 하 여 초기화 됩니다 **static_cast**

- 생성자에서 기본 클래스 및 비정적 멤버가 이니셜라이저 목록을 사용하여 초기화됩니다.

- 람다 식 내의 캡처된 변수 복사본에서

다음 코드는 직접 초기화의 몇 가지 예를 보여 줍니다.

```cpp
class BaseClass{
public:
    BaseClass(int n) :m_int(n){} // m_int is direct initialized
private:
    int m_int;
};

class DerivedClass : public BaseClass{
public:
    // BaseClass and m_char are direct initialized
    DerivedClass(int n, char c) : BaseClass(n), m_char(c) {}
private:
    char m_char;
};
int main(){
    BaseClass bc1(5);
    DerivedClass dc1{ 1, 'c' };
    BaseClass* bc2 = new BaseClass(7);
    BaseClass bc3 = static_cast<BaseClass>(dc1);

    int a = 1;
    function<int()> func = [a](){  return a + 1; }; // a is direct initialized
    int n = func();
}
```

### <a name="list-initialization"></a>목록 초기화

목록 초기화는 변수가 중괄호로 묶인 이니셜라이저 목록을 사용하여 초기화될 때 발생합니다. 중괄호로 묶인 이니셜라이저 목록이 사용되는 경우는 다음과 같습니다.

- 변수가 초기화됩니다.

- 클래스가 **new** 키워드를 사용 하 여 초기화 됩니다.

- 개체가 함수에서 반환됩니다.

- 인수가 함수에 전달됩니다.

- 직접 초기화의 인수 중 하나

- 비정적 데이터 멤버 이니셜라이저에서

- 생성자 이니셜라이저 목록에서

다음 코드는 목록 초기화의 몇 가지 예를 보여 줍니다.

```cpp
class MyClass {
public:
    MyClass(int myInt, char myChar) {}
private:
    int m_int[]{ 3 };
    char m_char;
};
class MyClassConsumer{
public:
    void set_class(MyClass c) {}
    MyClass get_class() { return MyClass{ 0, '\0' }; }
};
struct MyStruct{
    int my_int;
    char my_char;
    MyClass my_class;
};
int main() {
    MyClass mc1{ 1, 'a' };
    MyClass* mc2 = new MyClass{ 2, 'b' };
    MyClass mc3 = { 3, 'c' };

    MyClassConsumer mcc;
    mcc.set_class(MyClass{ 3, 'c' });
    mcc.set_class({ 4, 'd' });

    MyStruct ms1{ 1, 'a', { 2, 'b' } };
}
```

### <a name="agginit"></a>집합체 초기화

집합체 초기화는 다음과 같은 일종의 배열 또는 클래스 형식(대개 구조체 또는 공용 구조체) 목록 초기화입니다.

- 전용 또는 보호된 멤버 없음

- 명시적으로 기본값으로 설정되었거나 삭제된 생성자를 제외하고 사용자 제공 생성자 없음

- 기본 클래스 없음

- 가상 멤버 함수 없음

> [!NOTE]
> <!--conformance note-->Visual Studio 2015 이전 버전에서 집계는 비정적 멤버에 대 한 중괄호 또는 등호 이니셜라이저를 사용할 수 없습니다. 이 제한은 c + + 14 표준에서 제거 되었으며 Visual Studio 2017에 구현 되었습니다.

집합체 이니셜라이저는 다음 예제와 같이 중괄호로 묶은 초기화 목록으로 구성되며, 등호가 있을 수도 있고 없을 수도 있습니다.

```cpp
#include <iostream>
using namespace std;

struct MyAggregate{
    int myInt;
    char myChar;
};

struct MyAggregate2{
    int myInt;
    char myChar = 'Z'; // member-initializer OK in C++14
};

int main() {
    MyAggregate agg1{ 1, 'c' };
    MyAggregate2 agg2{2};
    cout << "agg1: " << agg1.myChar << ": " << agg1.myInt << endl;
    cout << "agg2: " << agg2.myChar << ": " << agg2.myInt << endl;

    int myArr1[]{ 1, 2, 3, 4 };
    int myArr2[3] = { 5, 6, 7 };
    int myArr3[5] = { 8, 9, 10 };

    cout << "myArr1: ";
    for (int i : myArr1){
        cout << i << " ";
    }
    cout << endl;

    cout << "myArr3: ";
    for (auto const &i : myArr3) {
        cout << i << " ";
    }
    cout << endl;
}
```

다음 출력이 표시됩니다.

```Output
agg1: c: 1
agg2: Z: 2
myArr1: 1 2 3 4
myArr3: 8 9 10 0 0
```

> [!IMPORTANT]
> 위의 `myArr3` 같이 집계 초기화 중에 선언 되었지만 명시적으로 초기화 되지 않은 배열 멤버는 0으로 초기화 됩니다.

#### <a name="initializing-unions-and-structs"></a>공용 구조체 및 구조체 초기화

공용 구조체에 생성자가 없는 경우 단일 값을 사용하여(또는 공용 구조체의 다른 인스턴스를 사용하여) 초기화할 수 있습니다. 값을 사용하여 첫 번째 비정적 필드를 초기화합니다. 이는 구조체 초기화와는 다릅니다. 구조체 초기화는 이니셜라이저의 첫 번째 값을 사용하여 첫 번째 필드를 초기화하고, 두 번째 값을 사용하여 두 번째 필드를 초기화하는 식으로 이루어집니다. 다음 예제에서 구조체와 공용 구조체 초기화를 비교해 보세요.

```cpp
struct MyStruct {
    int myInt;
    char myChar;
};
union MyUnion {
    int my_int;
    char my_char;
    bool my_bool;
    MyStruct my_struct;
};

int main() {
    MyUnion mu1{ 'a' };  // my_int = 97, my_char = 'a', my_bool = true, {myInt = 97, myChar = '\0'}
    MyUnion mu2{ 1 };   // my_int = 1, my_char = 'x1', my_bool = true, {myInt = 1, myChar = '\0'}
    MyUnion mu3{};      // my_int = 0, my_char = '\0', my_bool = false, {myInt = 0, myChar = '\0'}
    MyUnion mu4 = mu3;  // my_int = 0, my_char = '\0', my_bool = false, {myInt = 0, myChar = '\0'}
    //MyUnion mu5{ 1, 'a', true };  // compiler error: C2078: too many initializers
    //MyUnion mu6 = 'a';            // compiler error: C2440: cannot convert from 'char' to 'MyUnion'
    //MyUnion mu7 = 1;              // compiler error: C2440: cannot convert from 'int' to 'MyUnion'

    MyStruct ms1{ 'a' };            // myInt = 97, myChar = '\0'
    MyStruct ms2{ 1 };              // myInt = 1, myChar = '\0'
    MyStruct ms3{};                 // myInt = 0, myChar = '\0'
    MyStruct ms4{1, 'a'};           // myInt = 1, myChar = 'a'
    MyStruct ms5 = { 2, 'b' };      // myInt = 2, myChar = 'b'
}
```

#### <a name="initializing-aggregates-that-contain-aggregates"></a>집합체가 포함된 집합체 초기화

집합체 형식은 배열의 배열, 구조체의 배열 등 다른 집합체 형식을 포함할 수 있습니다. 이러한 형식은 중첩된 중괄호 집합을 사용하여 초기화됩니다. 예:

```cpp
struct MyStruct {
    int myInt;
    char myChar;
};
int main() {
    int intArr1[2][2]{{ 1, 2 }, { 3, 4 }};
    int intArr3[2][2] = {1, 2, 3, 4};
    MyStruct structArr[]{ { 1, 'a' }, { 2, 'b' }, {3, 'c'} };
}
```

### <a name="reference-initialization"></a>참조 초기화

참조 형식의 변수는 참조 형식이 파생된 형식의 개체 또는 참조 형식이 파생된 형식으로 변환될 수 있는 형식의 개체를 사용하여 초기화되어야 합니다. 다음은 그 예입니다.

```cpp
// initializing_references.cpp
int iVar;
long lVar;
int main()
{
    long& LongRef1 = lVar;        // No conversion required.
    long& LongRef2 = iVar;        // Error C2440
    const long& LongRef3 = iVar;  // OK
    LongRef1 = 23L;               // Change lVar through a reference.
    LongRef2 = 11L;               // Change iVar through a reference.
    LongRef3 = 11L;               // Error C3892
}
```

임시 개체를 사용하여 참조를 초기화하는 유일한 방법은 상수 임시 개체를 초기화하는 것입니다. 참조 형식 변수는 초기화되면 항상 동일한 개체를 가리키며, 다른 개체를 가리키도록 수정될 수 없습니다.

구문은 동일할 수 있지만 참조 형식 변수의 초기화와 참조 형식 변수에 대한 할당은 의미 체계가 서로 다릅니다. 위의 예제에서 `iVar` 및 `lVar`을 변경하는 할당은 초기화와 유사해 보이지만 결과가 다릅니다. 초기화는 참조 형식 변수가 가리키는 개체를 지정하고, 할당은 참조를 통해 참조된 개체에 할당합니다.

참조 형식의 인수를 함수에 전달하는 것과 함수에서 참조 형식의 값을 반환하는 것은 둘 다 초기화이기 때문에 함수에 대한 형식 인수는 참조가 반환됨에 따라 올바르게 초기화됩니다.

참조 형식 변수는 다음에서만 이니셜라이저 없이 선언될 수 있습니다.

- 함수 선언(프로토타입). 다음은 그 예입니다.

    ```cpp
    int func( int& );
    ```

- 함수 반환 형식 선언. 다음은 그 예입니다.

    ```cpp
    int& func( int& );
    ```

- 참조 형식 클래스 멤버의 선언. 다음은 그 예입니다.

    ```cpp
    class c {public:   int& i;};
    ```

- **Extern**으로 명시적으로 지정 된 변수 선언입니다. 다음은 그 예입니다.

    ```cpp
    extern int& iVal;
    ```

참조 형식 변수를 초기화할 때 컴파일러는 다음 그림과 같은 결정 그래프를 사용하여 개체에 대한 참조 만들기 또는 참조가 가리키는 임시 개체 만들기 중에서 선택합니다.

![참조 형식 초기화에 대 한 의사 결정 그래프](../cpp/media/vc38s71.gif "참조 형식 초기화에 대 한 의사 결정 그래프") <br/>
참조 형식 초기화에 대 한 의사 결정 그래프

**Volatile 형식에 대** 한 참조 ( **volatile** *typename* <strong>&</strong> *identifier*로 선언 됨)는 동일한 형식의 **volatile** 개체 또는 **volatile**로 선언 되지 않은 개체를 사용 하 여 초기화할 수 있습니다. 그러나 해당 형식의 **const** 개체를 사용 하 여 초기화할 수는 없습니다. 마찬가지로 **const 형식 (** **const** *typename* <strong>&</strong> *identifier*로 선언 됨)에 대 한 참조는 동일한 형식의 **const** 개체를 사용 하 여 초기화 될 수 있습니다 (또는 해당 형식에 대 한 변환이 있는 모든 항목 또는 **const**로 선언 되지 않은 개체를 사용 하 여). 그러나 해당 형식의 **volatile** 개체를 사용 하 여 초기화할 수는 없습니다.

**Const** 또는 **volatile** 키워드를 사용 하 여 정규화 되지 않은 참조는 **const** 또는 **volatile**이 아닌 개체로 선언 된 개체만 초기화할 수 있습니다.

### <a name="initialization-of-external-variables"></a>외부 변수 초기화

자동, 정적 및 외부 변수의 선언에는 이니셜라이저가 포함 될 수 있습니다. 그러나 외부 변수의 선언에는 변수가 **extern**으로 선언 되지 않은 경우에만 이니셜라이저가 포함 될 수 있습니다.
