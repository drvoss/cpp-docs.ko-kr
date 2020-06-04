---
title: '범위 해결 연산자: ::'
ms.date: 11/04/2016
f1_keywords:
- '::'
helpviewer_keywords:
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- ':: operator'
ms.assetid: fd5de9d3-c716-4e12-bae9-03a16fd79a50
ms.openlocfilehash: 07c2884ed0ba114c22a0c71bbaf7268d6f6931a4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178888"
---
# <a name="scope-resolution-operator-"></a>범위 해결 연산자: ::

범위 확인 연산자 **::** 는 여러 범위에서 사용 되는 식별자를 식별 하 고 구분 하는 데 사용 됩니다. 범위에 대 한 자세한 내용은 [범위](../cpp/scope-visual-cpp.md)를 참조 하세요.

## <a name="syntax"></a>구문

```
:: identifier
class-name :: identifier
namespace :: identifier
enum class :: identifier
enum struct :: identifier
```

## <a name="remarks"></a>주의

`identifier`에는 변수, 함수 또는 열거형 값이 해당됩니다.

## <a name="with-classes-and-namespaces"></a>클래스 및 네임스페이스에 사용

다음 예제에서는 범위 확인 연산자가 네임스페이스 및 클래스에 사용되는 방법을 보여줍니다.

```cpp
namespace NamespaceA{
    int x;
    class ClassA {
    public:
        int x;
    };
}

int main() {

    // A namespace name used to disambiguate
    NamespaceA::x = 1;

    // A class name used to disambiguate
    NamespaceA::ClassA a1;
    a1.x = 2;
}
```

범위 한정자가 없는 범위 확인 연산자는 전역 네임스페이스를 참조합니다.

```cpp
namespace NamespaceA{
    int x;
}

int x;

int main() {
    int x;

    // the x in main()
    x = 0;
    // The x in the global namespace
    ::x = 1;

    // The x in the A namespace
    NamespaceA::x = 2;
}
```

범위 확인 연산자를 사용하여 네임스페이스 멤버를 식별하거나 using 지시문으로 멤버의 네임스페이스를 지명하는 네임스페이스를 식별할 수 있습니다. 아래 예제에서는 `NamespaceC`가 네임스페이스 `ClassB`에 선언되었지만 using 지시문을 사용하여 `ClassB`가 `NamespaceB`에서 지명되었으므로 `NamespaceB`를 사용하여 `NamespaceC`를 한정할 수 있습니다.

```cpp
namespace NamespaceB {
    class ClassB {
    public:
        int x;
    };
}

namespace NamespaceC{
    using namespace B;
}
int main() {
    NamespaceB::ClassB c_b;
    NamespaceC::ClassB c_c;

    c_b.x = 3;
    c_c.x = 4;
}
```

범위 확인 연산자를 연쇄적으로 사용할 수 있습니다. 다음 예제에서 `NamespaceD::NamespaceD1`은 중첩된 네임스페이스 `NamespaceD1`을 식별하고 `NamespaceE::ClassE::ClassE1`은 중첩된 클래스 `ClassE1`을 식별합니다.

```cpp
namespace NamespaceD{
    namespace NamespaceD1{
        int x;
    }
}

namespace NamespaceE{
    class ClassE{
    public:
        class ClassE1{
        public:
            int x;
        };
    };
}

int main() {
    NamespaceD:: NamespaceD1::x = 6;
    NamespaceE::ClassE::ClassE1 e1;
    e1.x = 7  ;
}
```

## <a name="with-static-members"></a>정적 멤버에 사용

클래스의 정적 멤버를 호출하려면 범위 확인 연산자를 사용해야 합니다.

```cpp
class ClassG {
public:
    static int get_x() { return x;}
    static int x;
};

int ClassG::x = 6;

int main() {

    int gx1 = ClassG::x;
    int gx2 = ClassG::get_x();
}
```

## <a name="with-scoped-enumerations"></a>범위가 지정된 열거형에 사용

범위가 지정 된 확인 연산자는 다음 예제와 같이 범위가 지정 된 열거형 [열거형](../cpp/enumerations-cpp.md)의 값에도 사용 됩니다.

```cpp
enum class EnumA{
    First,
    Second,
    Third
};

int main() {
    EnumA enum_value = EnumA::First;
}
```

## <a name="see-also"></a>참고 항목

[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[네임스페이스](../cpp/namespaces-cpp.md)
