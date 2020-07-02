---
title: 클래스 멤버 개요
ms.date: 11/04/2016
helpviewer_keywords:
- members [C++], types of class members
- members [C++]
- class members [C++], types of
- class members
ms.assetid: 8802cfa9-705d-4f37-acde-245d6838010c
ms.openlocfilehash: cb978434707a9a7808b3388fc541ce4e0d996b0f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366671"
---
# <a name="class-member-overview"></a>클래스 멤버 개요

클래스 또는 구조체는 멤버로 구성됩니다. 클래스가 수행하는 작업은 해당 멤버 함수에 의해 수행됩니다. 클래스가 유지하는 상태는 해당 데이터 멤버에 저장됩니다. 멤버의 초기화는 생성자가 수행하며 메모리 해제 및 리소스 해제와 같은 정리 작업은 소멸자가 수행합니다. C++11 이상에서는 선언 지점에 데이터 멤버를 초기화할 수 있으며 일반적으로 초기화해야 합니다.

## <a name="kinds-of-class-members"></a>클래스 멤버 종류

멤버 범주 전체 목록은 다음과 같습니다.

- [특수 멤버 기능](special-member-functions.md).

- [멤버 함수 의 개요](overview-of-member-functions.md).

- 기본 제공 형식 및 기타 사용자 정의 형식을 포함한 [데이터 멤버입니다.](static-members-cpp.md)

- 연산자

- [중첩 된 클래스 선언](nested-class-declarations.md) 및.)

- [공용 구조체](unions.md)

- [열거](../cpp/enumerations-cpp.md).

- [비트 필드](../cpp/cpp-bit-fields.md).

- [친구](../cpp/friend-cpp.md).

- [별칭 및 형식 defs](../cpp/aliases-and-typedefs-cpp.md).

    > [!NOTE]
    >  Friends는 클래스 선언에 포함되므로 앞의 목록에 포함됩니다. 그러나 클래스 범위에 속하지 않으므로 true 클래스 멤버가 아닙니다.

## <a name="example-class-declaration"></a>예제 클래스 선언

다음 예제에서는 간단한 구조체 선언을 보여 줍니다.

```cpp
// TestRun.h

class TestRun
{
    // Start member list.

    //The class interface accessible to all callers.
public:
    // Use compiler-generated default constructor:
    TestRun() = default;
    // Don't generate a copy constructor:
    TestRun(const TestRun&) = delete;
    TestRun(std::string name);
    void DoSomething();
    int Calculate(int a, double d);
    virtual ~TestRun();
    enum class State { Active, Suspended };

    // Accessible to this class and derived classes only.
protected:
    virtual void Initialize();
    virtual void Suspend();
    State GetState();

    // Accessible to this class only.
private:
    // Default brace-initialization of instance members:
    State _state{ State::Suspended };
    std::string _testName{ "" };
    int _index{ 0 };

    // Non-const static member:
    static int _instances;
    // End member list.
};

// Define and initialize static member.
int TestRun::_instances{ 0 };
```

## <a name="member-accessibility"></a>멤버 접근성

클래스의 멤버는 멤버 목록에 선언됩니다. 클래스의 구성원 목록은 액세스 지정자라고 하는 키워드를 사용하여 **개인,** **보호** 및 **공용** 섹션의 수에 관계없이 나눌 수 있습니다.  콜론 **:** 액세스 지정기를 따라야 합니다.  이 섹션은 인접해 있을 필요가 없으므로 이 키워드가 멤버 목록에서 여러 번 나올 수 있습니다.  다음 액세스 지정자나 닫는 중괄호가 나올 때까지 키워드가 모든 멤버의 액세스를 지정합니다. 자세한 내용은 [멤버 액세스 제어(C++)를](../cpp/member-access-control-cpp.md)참조하십시오.

## <a name="static-members"></a>정적 멤버

데이터 멤버는 정적 멤버로 선언할 수 있습니다. 이 경우 클래스의 모든 개체가 동일한 복사본에 액세스할 수 있게 됩니다. 멤버 함수는 정적 함수로 선언될 수 있으며, 이 경우 클래스의 정적 데이터 멤버만 액세스할 수 있으며 *이* 포인터가 없습니다. 자세한 내용은 [정적 데이터 멤버](../cpp/static-members-cpp.md)를 참조하십시오.

## <a name="special-member-functions"></a>특수 멤버 함수

특수 멤버 함수는 소스 코드에서 지정하지 않으면 컴파일러에 의해 자동으로 제공되는 함수입니다.

1. 기본 생성자

1. 복사 생성자

1. **(C++11)** 생성자 이동

1. 복사 할당 연산자

1. **(C++11)** 할당 연산자 이동

1. 소멸자

자세한 내용은 [특수 멤버 기능을](../cpp/special-member-functions.md)참조하십시오.

## <a name="memberwise-initialization"></a>멤버 수준 초기화

C++11 이상에서는 비정적 멤버 선언자에 이니셜라이저를 포함할 수 있습니다.

```cpp
class CanInit
{
public:
    long num {7};       // OK in C++11
    int k = 9;          // OK in C++11
    static int i = 9; // Error: must be defined and initialized
                      // outside of class declaration.

    // initializes num to 7 and k to 9
    CanInit(){}

    // overwrites original initialized value of num:
    CanInit(int val) : num(val) {}
};
int main()
{
}
```

생성자서 멤버에 값이 할당되는 경우 이 값은 선언 시점에 멤버를 초기화할 때 사용된 값을 덮어씁니다.

주어진 클래스 형식의 모든 개체에 대해 정적 데이터 멤버의 공유 복사본이 한 개만 있습니다. 정적 데이터 멤버를 정의해야 하며 파일 범위에서 초기화할 수 있습니다. 정적 데이터 멤버에 대한 자세한 내용은 [정적 데이터 멤버를](../cpp/static-members-cpp.md)참조하십시오. 다음 예제에서는 이러한 초기화를 수행하는 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주시면 됩니다.

```cpp
// class_members2.cpp
class CanInit2
{
public:
    CanInit2() {} // Initializes num to 7 when new objects of type
                 //  CanInit are created.
    long     num {7};
    static int i;
    static int j;
};

// At file scope:

// i is defined at file scope and initialized to 15.
// The initializer is evaluated in the scope of CanInit.
int CanInit2::i = 15;

// The right side of the initializer is in the scope
// of the object being initialized
int CanInit2::j = i;
```

> [!NOTE]
> 정의할 `CanInit2`가 `i` 클래스의 멤버가 되도록 지정하려면 클래스 이름 `i`가 `CanInit2` 앞에 와야 합니다.

## <a name="see-also"></a>참고 항목

[클래스 및 구조체](../cpp/classes-and-structs-cpp.md)
