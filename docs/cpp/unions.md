---
title: union
description: 표준 c + + union class 형식 및 키워드, 사용 및 제한 사항에 대 한 설명입니다.
ms.date: 08/18/2020
f1_keywords:
- union_cpp
helpviewer_keywords:
- class type [C++], union as
- union keyword [C++]
ms.assetid: 25c4e219-fcbb-4b7b-9b64-83f3252a92ca
no-loc:
- union
- struct
- enum
- class
- static
ms.openlocfilehash: a4dc07df5e7858dffe62478509ee1d8dc759ce96
ms.sourcegitcommit: f1752bf90b4f869633a859ace85439ca19e208b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "88722182"
---
# `union`

> [!NOTE]
> C + + 17 이상에서는에 `std::variant` class 대 한 형식 안전 대안입니다 union .

는 **`union`** 모든 멤버가 동일한 메모리 위치를 공유 하는 사용자 정의 형식입니다. 이 정의는 지정 된 시간에의 union 멤버 목록에서 둘 이상의 개체를 포함할 수 있음을 의미 합니다. 또한 멤버의 수에 관계 없이 union 항상 가장 큰 멤버를 저장 하는 데 충분 한 메모리를 사용 한다는 것을 의미 합니다.

는 union 많은 개체와 제한 된 메모리가 있는 경우 메모리를 절약 하는 데 유용할 수 있습니다. 그러나를 union 올바르게 사용 하려면 추가 주의가 필요 합니다. 사용자는 할당 한 동일한 멤버에 항상 액세스할 수 있는지 확인 해야 합니다. 멤버 형식에 특수 con 또는이 있는 경우에 struct 는 해당 멤버를 명시적으로 con 하 고 제거 하는 추가 코드를 작성 해야 합니다 struct . 를 사용 하기 전에 union 해결 하려는 문제가 기본 class 및 파생 형식을 사용 하 여 더 잘 표현 될 수 있는지를 고려 하세요 class .

## <a name="syntax"></a>구문

> **`union`***`tag`* <sub>opt</sub> **`{`** opt *`member-list`***`};`**

### <a name="parameters"></a>매개 변수

*`tag`*<br/>
에 지정 된 형식 이름 union 입니다.

*`member-list`*<br/>
에 union 포함 될 수 있는 멤버입니다.

## <a name="declare-a-no-locunion"></a>선언 union

union키워드를 사용 하 여의 선언을 시작 **`union`** 하 고 멤버 목록을 중괄호로 묶습니다.

```cpp
// declaring_a_union.cpp
union RecordType    // Declare a simple union type
{
    char   ch;
    int    i;
    long   l;
    float  f;
    double d;
    int *int_ptr;
};

int main()
{
    RecordType t;
    t.i = 5; // t holds an int
    t.f = 7.25; // t now holds a float
}
```

## <a name="use-a-no-locunion"></a>사용 union

이전 예제에서에 액세스 하는 모든 코드는 union 데이터를 보유 하는 멤버를 알고 있어야 합니다. 이 문제에 대 한 가장 일반적인 해결책을 *구분 union *된 이라고 합니다. 에를 union 포함 하 고에 현재 저장 되어 있는 struct enum 멤버 형식을 나타내는 멤버를 포함 합니다 union . 다음 예제에서는 기본 패턴을 보여 줍니다.

```cpp
#include <queue>

using namespace std;

enum class WeatherDataType
{
    Temperature, Wind
};

struct TempData
{
    int StationId;
    time_t time;
    double current;
    double max;
    double min;
};

struct WindData
{
    int StationId;
    time_t time;
    int speed;
    short direction;
};

struct Input
{
    WeatherDataType type;
    union
    {
        TempData temp;
        WindData wind;
    };
};

// Functions that are specific to data types
void Process_Temp(TempData t) {}
void Process_Wind(WindData w) {}

void Initialize(std::queue<Input>& inputs)
{
    Input first;
    first.type = WeatherDataType::Temperature;
    first.temp = { 101, 1418855664, 91.8, 108.5, 67.2 };
    inputs.push(first);

    Input second;
    second.type = WeatherDataType::Wind;
    second.wind = { 204, 1418859354, 14, 27 };
    inputs.push(second);
}

int main(int argc, char* argv[])
{
    // Container for all the data records
    queue<Input> inputs;
    Initialize(inputs);
    while (!inputs.empty())
    {
        Input const i = inputs.front();
        switch (i.type)
        {
        case WeatherDataType::Temperature:
            Process_Temp(i.temp);
            break;
        case WeatherDataType::Wind:
            Process_Wind(i.wind);
            break;
        default:
            break;
        }
        inputs.pop();

    }
    return 0;
}
```

이전 예제에서의에는 union `Input` struct 이름이 없으므로 *익명* 이라고 합니다 union . 해당 멤버는의 멤버인 것 처럼 직접 액세스할 수 있습니다 struct . 익명을 사용 하는 방법에 대 한 자세한 내용은 union [anonymous union ](#anonymous_unions) 섹션을 참조 하십시오.

이전 예제에서는 class 공통 기반에서 파생 되는 형식을 사용 하 여 해결할 수 있는 문제를 보여 줍니다 class . 컨테이너에 있는 각 개체의 런타임 형식에 따라 코드를 분기할 수 있습니다. 코드를 유지 관리 하 고 이해 하는 것이 더 쉬울 수도 있지만를 사용 하는 것 보다 속도가 느릴 수 있습니다 union . 또한를 사용 하 여 union 관련이 없는 형식을 저장할 수 있습니다. 를 union 사용 하면 변수 자체의 형식을 변경 하지 않고 저장 된 값의 형식을 동적으로 변경할 수 있습니다 union . 예를 들어 `MyUnionType` 요소가 다른 형식의 다른 값을 저장 하는의 다른 배열을 만들 수 있습니다.

예제에서를 악용 하는 것이 쉽습니다 `Input` struct . 사용자는 판별자를 올바르게 사용 하 여 데이터를 보유 하는 멤버에 액세스 하는 것이 좋습니다. union **`private`** 다음 예제와 같이를 만들고 특수 액세스 기능을 제공 하 여 오용 으로부터 보호할 수 있습니다.

## <a name="unrestricted-no-locunion-c11"></a>무제한 union (c + + 11)

C + + 03 및 이전 버전에서는 union static class 형식에 사용자가 제공 하는 con struct ors, de struct ors 또는 대입 연산자가 없는 한 형식이 있는 비 데이터 멤버가 포함 될 수 있습니다. C++ 11에서는 이러한 제한이 제거됩니다. 이러한 멤버를에 포함 하는 경우 union 컴파일러는 사용자가 제공 하지 않는 특수 멤버 함수를 자동으로로 표시 **`deleted`** 합니다. union이 또는 내부에 있는 경우 union class struct class struct 사용자가 제공 하지 않은 또는의 특수 멤버 함수는로 표시 됩니다 **`deleted`** . 다음 예제에서는이 경우를 처리 하는 방법을 보여 줍니다. 의 멤버 중 하나 union 에이 특수 처리가 필요한 멤버가 있습니다.

```cpp
// for MyVariant
#include <crtdbg.h>
#include <new>
#include <utility>

// for sample objects and output
#include <string>
#include <vector>
#include <iostream>

using namespace std;

struct A
{
    A() = default;
    A(int i, const string& str) : num(i), name(str) {}

    int num;
    string name;
    //...
};

struct B
{
    B() = default;
    B(int i, const string& str) : num(i), name(str) {}

    int num;
    string name;
    vector<int> vec;
    // ...
};

enum class Kind { None, A, B, Integer };

#pragma warning (push)
#pragma warning(disable:4624)
class MyVariant
{
public:
    MyVariant()
        : kind_(Kind::None)
    {
    }

    MyVariant(Kind kind)
        : kind_(kind)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A();
            break;
        case Kind::B:
            new (&b_) B();
            break;
        case Kind::Integer:
            i_ = 0;
            break;
        default:
            _ASSERT(false);
            break;
        }
    }

    ~MyVariant()
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            a_.~A();
            break;
        case Kind::B:
            b_.~B();
            break;
        case Kind::Integer:
            break;
        default:
            _ASSERT(false);
            break;
        }
        kind_ = Kind::None;
    }

    MyVariant(const MyVariant& other)
        : kind_(other.kind_)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A(other.a_);
            break;
        case Kind::B:
            new (&b_) B(other.b_);
            break;
        case Kind::Integer:
            i_ = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
    }

    MyVariant(MyVariant&& other)
        : kind_(other.kind_)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A(move(other.a_));
            break;
        case Kind::B:
            new (&b_) B(move(other.b_));
            break;
        case Kind::Integer:
            i_ = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
        other.kind_ = Kind::None;
    }

    MyVariant& operator=(const MyVariant& other)
    {
        if (&other != this)
        {
            switch (other.kind_)
            {
            case Kind::None:
                this->~MyVariant();
                break;
            case Kind::A:
                *this = other.a_;
                break;
            case Kind::B:
                *this = other.b_;
                break;
            case Kind::Integer:
                *this = other.i_;
                break;
            default:
                _ASSERT(false);
                break;
            }
        }
        return *this;
    }

    MyVariant& operator=(MyVariant&& other)
    {
        _ASSERT(this != &other);
        switch (other.kind_)
        {
        case Kind::None:
            this->~MyVariant();
            break;
        case Kind::A:
            *this = move(other.a_);
            break;
        case Kind::B:
            *this = move(other.b_);
            break;
        case Kind::Integer:
            *this = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
        other.kind_ = Kind::None;
        return *this;
    }

    MyVariant(const A& a)
        : kind_(Kind::A), a_(a)
    {
    }

    MyVariant(A&& a)
        : kind_(Kind::A), a_(move(a))
    {
    }

    MyVariant& operator=(const A& a)
    {
        if (kind_ != Kind::A)
        {
            this->~MyVariant();
            new (this) MyVariant(a);
        }
        else
        {
            a_ = a;
        }
        return *this;
    }

    MyVariant& operator=(A&& a)
    {
        if (kind_ != Kind::A)
        {
            this->~MyVariant();
            new (this) MyVariant(move(a));
        }
        else
        {
            a_ = move(a);
        }
        return *this;
    }

    MyVariant(const B& b)
        : kind_(Kind::B), b_(b)
    {
    }

    MyVariant(B&& b)
        : kind_(Kind::B), b_(move(b))
    {
    }

    MyVariant& operator=(const B& b)
    {
        if (kind_ != Kind::B)
        {
            this->~MyVariant();
            new (this) MyVariant(b);
        }
        else
        {
            b_ = b;
        }
        return *this;
    }

    MyVariant& operator=(B&& b)
    {
        if (kind_ != Kind::B)
        {
            this->~MyVariant();
            new (this) MyVariant(move(b));
        }
        else
        {
            b_ = move(b);
        }
        return *this;
    }

    MyVariant(int i)
        : kind_(Kind::Integer), i_(i)
    {
    }

    MyVariant& operator=(int i)
    {
        if (kind_ != Kind::Integer)
        {
            this->~MyVariant();
            new (this) MyVariant(i);
        }
        else
        {
            i_ = i;
        }
        return *this;
    }

    Kind GetKind() const
    {
        return kind_;
    }

    A& GetA()
    {
        _ASSERT(kind_ == Kind::A);
        return a_;
    }

    const A& GetA() const
    {
        _ASSERT(kind_ == Kind::A);
        return a_;
    }

    B& GetB()
    {
        _ASSERT(kind_ == Kind::B);
        return b_;
    }

    const B& GetB() const
    {
        _ASSERT(kind_ == Kind::B);
        return b_;
    }

    int& GetInteger()
    {
        _ASSERT(kind_ == Kind::Integer);
        return i_;
    }

    const int& GetInteger() const
    {
        _ASSERT(kind_ == Kind::Integer);
        return i_;
    }

private:
    Kind kind_;
    union
    {
        A a_;
        B b_;
        int i_;
    };
};
#pragma warning (pop)

int main()
{
    A a(1, "Hello from A");
    B b(2, "Hello from B");

    MyVariant mv_1 = a;

    cout << "mv_1 = a: " << mv_1.GetA().name << endl;
    mv_1 = b;
    cout << "mv_1 = b: " << mv_1.GetB().name << endl;
    mv_1 = A(3, "hello again from A");
    cout << R"aaa(mv_1 = A(3, "hello again from A"): )aaa" << mv_1.GetA().name << endl;
    mv_1 = 42;
    cout << "mv_1 = 42: " << mv_1.GetInteger() << endl;

    b.vec = { 10,20,30,40,50 };

    mv_1 = move(b);
    cout << "After move, mv_1 = b: vec.size = " << mv_1.GetB().vec.size() << endl;

    cout << endl << "Press a letter" << endl;
    char c;
    cin >> c;
}
```

는 union 참조를 저장할 수 없습니다. union또한는 상속을 지원 하지 않습니다. 즉,을 union 기본으로 사용 class 하거나 다른에서 상속 class 하거나 가상 함수를 사용할 수 없습니다.

## <a name="initialize-a-no-locunion"></a>를 초기화합니다.union

union중괄호로 묶인 식을 할당 하 여 동일한 문에서을 선언 하 고 초기화할 수 있습니다. 식이 평가 되 고의 첫 번째 필드에 할당 됩니다 union .

```cpp
#include <iostream>
using namespace std;

union NumericType
{
    short       iValue;
    long        lValue;
    double      dValue;
};

int main()
{
    union NumericType Values = { 10 };   // iValue = 10
    cout << Values.iValue << endl;
    Values.dValue = 3.1416;
    cout << Values.dValue << endl;
}
/* Output:
10
3.141600
*/
```

는 `NumericType` union 다음 그림과 같이 개념적으로 메모리에 정렬 됩니다.

![숫자 형식으로 데이터 저장::: no loc (union):::](../cpp/media/vc38ul1.png "NumericType::: no loc (union):::에 데이터를 저장 합니다.") <br/>
데이터 `NumericType` 저장소 union

## <a name="anonymous-no-locunion"></a><a name="anonymous_unions"></a> 익명 union

익명 union 은 또는 없이 선언 된 하나 *`class-name`* 입니다 *`declarator-list`* .

> **`union  {`**  *`member-list`*  **`}`**

익명에 선언 된 이름은 union 비멤버 변수와 같이 직접 사용 됩니다. 익명의 선언 된 이름이 union 주변 범위에서 고유 해야 함을 의미 합니다.

익명에 union 는 다음과 같은 추가 제한이 적용 됩니다.

- 파일 또는 네임 스페이스 범위에서 선언 된 경우로도 선언 해야 합니다 **`static`** .

- 멤버는 하나만 포함할 수 있습니다 **`public`** . **`private`** **`protected`** 익명의 및 멤버는 union 오류를 생성 합니다.

- 멤버 함수를 포함할 수 없습니다.

## <a name="see-also"></a>참조

[클래스 및 구조체](../cpp/classes-and-structs-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[`class`](../cpp/class-cpp.md)<br/>
[`struct`](../cpp/struct-cpp.md)
