---
title: 템플릿 (C++)
ms.date: 12/27/2019
f1_keywords:
- template_cpp
helpviewer_keywords:
- templates, C++
- templates [C++]
ms.assetid: 90fcc14a-2092-47af-9d2e-dba26d25b872
ms.openlocfilehash: e47f00c7e387974c7d1756cf3ee3865f892e6951
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032345"
---
# <a name="templates-c"></a>템플릿 (C++)

템플릿은 C++의 일반 프로그래밍의 기초입니다. 강력한 형식의 언어인 C++는 모든 변수에 프로그래머가 명시적으로 선언하거나 컴파일러에서 추론하는 특정 형식을 갖도록 요구합니다. 그러나 많은 데이터 구조와 알고리즘은 어떤 형식에서 작동하든 동일하게 보입니다. 템플릿을 사용하면 클래스 또는 함수의 작업을 정의하고 사용자가 해당 작업에서 작업해야 하는 구체적인 유형을 지정할 수 있습니다.

## <a name="defining-and-using-templates"></a>템플릿 정의 및 사용

템플릿은 사용자가 템플릿 매개 변수에 대해 제공하는 인수를 기반으로 컴파일 타임에 일반 형식 또는 함수를 생성하는 구문입니다. 예를 들어 다음과 같은 함수 템플릿을 정의할 수 있습니다.

```cpp
template <typename T>
T minimum(const T& lhs, const T& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

위의 코드는 반환 값 및 호출 매개 변수(lh및 rhs)가 모두 이 형식인 단일 형식 매개 변수 *T를*가진 제네릭 함수에 대한 템플릿을 설명합니다. 원하는 모든 형식 매개 변수의 이름을 지정할 수 있지만 규칙에 따라 단일 대문자가 가장 일반적으로 사용됩니다. *T는* 템플릿 매개 변수입니다. **typename** 키워드는 이 매개 변수가 형식의 자리 표시자임을 말합니다. 함수가 호출되면 컴파일러는 모든 인스턴스를 `T` 사용자가 지정하거나 컴파일러에서 추론하는 구체적인 형식 인수로 바꿉습니다. 컴파일러가 템플릿에서 클래스 또는 함수를 생성하는 프로세스를 *템플릿 인스턴스화라고*합니다. `minimum<int>` 은 템플릿의 `minimum<T>`인스턴스화입니다.

다른 곳에서는 int get_b get_a.에 특화된 템플릿의 인스턴스를 선언할 수 있습니다.

```cpp
int a = get_a();
int b = get_b();
int i = minimum<int>(a, b);
```

그러나 이 템플릿은 함수 템플릿이고 컴파일러는 인수 `T` *a와* *b에서*형식을 추론할 수 있으므로 일반 함수처럼 호출할 수 있습니다.

```cpp
int i = minimum(a, b);
```

컴파일러가 마지막 문을 만나면 템플릿에서 *T의* 모든 발생이 **int로**대체되는 새 함수를 생성합니다.

```cpp
int minimum(const int& lhs, const int& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

컴파일러가 함수 템플릿에서 형식 공제를 수행하는 방법에 대한 규칙은 일반 함수에 대한 규칙을 기반으로 합니다. 자세한 내용은 [함수 템플릿 호출의 오버로드 해결을](../cpp/overload-resolution-of-function-template-calls.md)참조하십시오.

## <a name="type-parameters"></a><a id="type_parameters"></a>형식 매개 변수

위의 `minimum` 템플릿에서 형식 매개 변수 *T는* const 및 참조 한정자가 추가되는 함수 호출 매개 변수에 사용될 때까지 어떤 방식으로도 정규화되지 않습니다.

형식 매개 변수 의 수에는 실질적인 제한이 없습니다. 쉼표로 여러 매개 변수를 구분합니다.

```cpp
template <typename T, typename U, typename V> class Foo{};
```

키워드 **클래스는** 이 컨텍스트의 **형식 이름과** 동일합니다. 이전 예제를 다음과 같이 표현할 수 있습니다.

```cpp
template <class T, class U, class V> class Foo{};
```

타원 연산자(...)를 사용하여 임의의 수의 0 개 이상의 형식 매개 변수를 사용하는 템플릿을 정의할 수 있습니다.

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
```

모든 기본 제공 또는 사용자 정의 형식은 형식 인수로 사용할 수 있습니다. 예를 들어 표준 라이브러리에서 [std::vector를](../standard-library/vector-class.md) 사용하여 **int,** double , [std::string](../standard-library/basic-string-class.md) `MyClass`, **const** `MyClass` `MyClass&`*, 등의 변수를 저장할 수 있습니다. **double** 템플릿을 사용할 때의 주요 제한사항은 형식 인수가 형식 매개 변수에 적용되는 모든 작업을 지원해야 한다는 것입니다. 예를 들어, 이 `minimum` `MyClass` 예제에서와 같이 사용하여 호출하는 경우:

```cpp
class MyClass
{
public:
    int num;
    std::wstring description;
};

int main()
{
    MyClass mc1 {1, L"hello"};
    MyClass mc2 {2, L"goodbye"};
    auto result = minimum(mc1, mc2); // Error! C2678
}
```

연산자에 대한 오버로드를 제공하지 않기 때문에 `MyClass` 컴파일러 오류가 생성됩니다. **<**

이러한 제한을 적용하는 템플릿을 정의할 수 있지만 특정 템플릿에 대한 형식 인수가 모두 동일한 개체 계층 구조에 속한다는 고유한 요구 사항은 없습니다. 개체 지향 기술을 템플릿과 결합할 수 있습니다. 예를 들어 벡터\<베이스\*> Derived*를 저장할 수 있습니다.    인수는 포인터여야 합니다.

```cpp
vector<MyClass*> vec;
   MyDerived d(3, L"back again", time(0));
   vec.push_back(&d);

   // or more realistically:
   vector<shared_ptr<MyClass>> vec2;
   vec2.push_back(make_shared<MyDerived>());
```

다른 표준 `std::vector` 라이브러리 컨테이너가 요소에 부과하는 `T` 기본 `T` 요구 사항은 복사 할당 가능하고 복사 구성가능해야 한다는 것입니다.

## <a name="non-type-parameters"></a>비유형 매개 변수

C# 및 Java와 같은 다른 언어의 제네릭 형식과 달리 C++ 템플릿은 값 매개 변수라고도 하는 *비형식 매개 변수를*지원합니다. 예를 들어 표준 라이브러리의 [std:::array](../standard-library/array-class-stl.md) 클래스와 유사한 이 예제와 마찬가지로 배열의 길이를 지정하는 상수 정수 값을 제공할 수 있습니다.

```cpp
template<typename T, size_t L>
class MyArray
{
    T arr[L];
public:
    MyArray() { ... }
};
```

템플릿 선언의 구문을 기록합니다. 값은 `size_t` 컴파일 타임에 템플릿 인수로 전달되며 **const** 또는 **constexpr** 식이어야 합니다. 다음과 같이 사용합니다.

```cpp
MyArray<MyClass*, 10> arr;
```

포인터 및 참조를 포함한 다른 종류의 값은 형식이 아닌 매개 변수로 전달할 수 있습니다. 예를 들어 함수 또는 함수 개체에 대한 포인터를 전달하여 템플릿 코드 내에서 일부 작업을 사용자 지정할 수 있습니다.

### <a name="type-deduction-for-non-type-template-parameters"></a>형식이 아닌 템플릿 매개 변수에 대한 형식 공제

Visual Studio 2017 이상에서 **/std:c++17** 모드에서 컴파일러는 **auto로**선언된 형식이 아닌 템플릿 인수의 형식을 추론합니다.

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

## <a name="templates-as-template-parameters"></a><a id="template_parameters"></a>템플릿 매개 변수로 사용

템플릿은 템플릿 매개 변수일 수 있습니다. 이 예제에서 MyClass2에는 두 가지 템플릿 매개 변수인 형식 이름 매개 변수 *T와* 템플릿 매개 변수 *Arr:*

```cpp
template<typename T, template<typename U, int I> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
    U u; //Error. U not in scope
};
```

*Arr* 매개 변수 자체에는 본문이 없으므로 매개 변수 이름이 필요하지 않습니다. 실제로 `MyClass2`의 본문 내에서 *Arr의*형식 이름 또는 클래스 매개 변수 이름을 참조하는 것은 오류입니다. 이러한 이유로 이 예제와 같이 *Arr의*형식 매개 변수 이름을 생략할 수 있습니다.

```cpp
template<typename T, template<typename, int> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
};
```

## <a name="default-template-arguments"></a>기본 템플릿 인수

클래스 및 함수 템플릿에는 기본 인수가 있을 수 있습니다. 템플릿에 기본 인수가 있는 경우 템플릿을 사용할 때 지정되지 않은 상태로 둘 수 있습니다. 예를 들어 std::vector 템플릿에는 할당자에 대한 기본 인수가 있습니다.

```cpp
template <class T, class Allocator = allocator<T>> class vector;
```

대부분의 경우 기본 std::allocator 클래스는 허용되므로 다음과 같은 벡터를 사용합니다.

```cpp
vector<int> myInts;
```

그러나 필요한 경우 다음과 같은 사용자 지정 할당을 지정할 수 있습니다.

```cpp
vector<int, MyAllocator> ints;
```

템플릿 인수가 여러 개인 경우 첫 번째 기본 인수 다음의 모든 인수에는 기본 인수가 있어야 합니다.

매개 변수가 모두 기본값인 템플릿을 사용하는 경우 빈 각도 대괄호를 사용합니다.

```cpp
template<typename A = int, typename B = double>
class Bar
{
    //...
};
...
int main()
{
    Bar<> bar; // use all default type arguments
}
```

## <a name="template-specialization"></a>템플릿 특수화

경우에 따라 템플릿이 모든 형식에 대해 정확히 동일한 코드를 정의하는 것은 불가능하거나 바람직하지 않습니다. 예를 들어 형식 인수가 포인터 또는 std::wstring 또는 특정 기본 클래스에서 파생된 형식인 경우에만 실행할 코드 경로를 정의할 수 있습니다.  이러한 경우 특정 형식에 대한 템플릿의 *특수화를* 정의할 수 있습니다. 사용자가 해당 형식으로 템플릿을 인스턴스화하면 컴파일러는 특수화를 사용하여 클래스를 생성하고 다른 모든 형식의 경우 컴파일러는 보다 일반적인 템플릿을 선택합니다. 모든 매개 변수가 특수화되는 전문화는 *완전한 전문화입니다.* 일부 매개 변수만 특수화된 경우 부분 *전문화라고*합니다.

```cpp
template <typename K, typename V>
class MyMap{/*...*/};

// partial specialization for string keys
template<typename V>
class MyMap<string, V> {/*...*/};
...
MyMap<int, MyClass> classes; // uses original template
MyMap<string, MyClass> classes2; // uses the partial specialization
```

각 특수 형식 매개 변수가 고유하면 템플릿에 여러 개의 특수화가 있을 수 있습니다. 클래스 템플릿만 부분적으로 특수할 수 있습니다. 템플릿의 모든 완전 및 부분 전문화 영역은 원래 템플릿과 동일한 네임스페이스에 선언해야 합니다.

자세한 내용은 [템플릿 특수화](../cpp/template-specialization-cpp.md)를 참조하십시오.
