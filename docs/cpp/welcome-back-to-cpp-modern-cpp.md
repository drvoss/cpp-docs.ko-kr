---
title: C++에 다시 오신 것을 환영합니다 - 현대 C ++
description: 현대 C ++의 새로운 프로그래밍 숙어와 그 근거에 대해 설명합니다.
ms.date: 01/10/2020
ms.topic: conceptual
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
ms.openlocfilehash: 7d0fcb623162713b845107bbf00669af7ae5ca98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369499"
---
# <a name="welcome-back-to-c---modern-c"></a>C++에 다시 오신 것을 환영합니다 - 현대 C ++

C++는 창작 이래 세계에서 가장 널리 사용되는 프로그래밍 언어 중 하나가 되었습니다. 잘 작성된 C++ 프로그램은 빠르고 효율적입니다. 언어는 다른 언어보다 더 유연합니다 : 그것은 추상화의 가장 높은 수준에서 작동 할 수 있습니다, 실리콘의 수준에서 아래로. C++는 고도로 최적화된 표준 라이브러리를 제공합니다. 저수준 하드웨어 기능에 액세스하여 속도를 최대화하고 메모리 요구 사항을 최소화할 수 있습니다. C++를 사용하여 다양한 앱을 만들 수 있습니다. 게임, 장치 드라이버 및 고성능 과학 소프트웨어. 임베디드 프로그램. Windows 클라이언트 앱입니다. 다른 프로그래밍 언어에 대한 라이브러리와 컴파일러도 C++로 작성됩니다.

C++의 본래 요구 사항 중 하나는 C 언어와의 역 호환성이었습니다. 따라서 C++는 원시 포인터, 배열, null 종료 된 문자 문자열 및 기타 기능을 갖춘 C 스타일 프로그래밍을 항상 허용했습니다. 성능이 뛰어나지만 버그와 복잡성을 생성할 수도 있습니다. C++의 진화는 C 스타일 숙어를 사용할 필요성을 크게 줄이는 기능을 강조했습니다. 기존 C-프로그래밍 시설은 필요할 때 사용할 수 있지만 최신 C++ 코드를 사용하면 필요도 줄어듭니다. 최신 C++ 코드는 더 간단하고 안전하며 우아하며 그 어느 때보다 빠릅니다.

다음 섹션에서는 최신 C++의 주요 기능에 대한 개요를 제공합니다. 별도로 명시되지 않는 한 여기에 나열된 기능은 C++11 이상에서 사용할 수 있습니다. Microsoft C++ 컴파일러에서 [/std](../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션을 설정하여 프로젝트에 사용할 표준 버전을 지정할 수 있습니다.

## <a name="resources-and-smart-pointers"></a>리소스 및 스마트 포인터

C 스타일 프로그래밍에서 버그의 주요 클래스 중 하나는 *메모리 누수입니다.* 새누수로 인해 **새**것으로 할당된 메모리에 대해 **delete를** 호출하지 못하여 발생하는 경우가 많습니다. 현대 C++는 자원 *획득의 원리가 초기화(RAII)임을* 강조합니다. 아이디어는 간단합니다. 리소스(힙 메모리, 파일 핸들, 소켓 등)는 개체가 *소유해야* 합니다. 해당 개체는 생성자에서 새로 할당된 리소스를 만들거나 수신하고 소멸자에서 삭제합니다. RAII 원칙은 소유 개체가 범위를 벗어날 때 모든 리소스가 운영 체제로 제대로 반환되도록 보장합니다.

RAII 원칙을 쉽게 채택할 수 있도록 C++ 표준 라이브러리는 세 가지 스마트 포인터 유형을 제공합니다: [std:unique_ptr](../standard-library/unique-ptr-class.md), [std:shared_ptr](../standard-library/shared-ptr-class.md)및 [std:weak_ptr](../standard-library/weak-ptr-class.md). 스마트 포인터는 소유한 메모리의 할당 및 삭제를 처리합니다. 다음 예제에서는 에 대한 호출의 힙에 할당된 배열 멤버가 `make_unique()`있는 클래스를 보여 주며 있습니다. **새** 및 **삭제에** 대한 호출은 클래스에 `unique_ptr` 의해 캡슐화됩니다. 개체가 `widget` 범위를 벗어나면 unique_ptr 소멸자가 호출되고 배열에 할당된 메모리가 해제됩니다.  

```cpp
#include <memory>
class widget
{
private:
    std::unique_ptr<int> data;
public:
    widget(const int size) { data = std::make_unique<int>(size); }
    void do_something() {}
};

void functionUsingWidget() {
    widget w(1000000);   // lifetime automatically tied to enclosing scope
                // constructs w, including the w.data gadget member
    // ...
    w.do_something();
    // ...
} // automatic destruction and deallocation for w and w.data

```

가능하면 힙 메모리를 할당할 때 스마트 포인터를 사용합니다. 새 연산자 및 삭제 연산을 명시적으로 사용해야 하는 경우 RAII 원칙을 따르십시오. 자세한 내용은 [개체 수명 및 리소스 관리(RAII)를](object-lifetime-and-resource-management-modern-cpp.md)참조하십시오.

## <a name="stdstring-and-stdstring_view"></a>std:문자열 및 std:string_view

C 스타일 문자열은 버그의 또 다른 주요 소스입니다. [std::string 및 std::wstring을](../standard-library/basic-string-class.md)사용하면 C 스타일 문자열과 관련된 거의 모든 오류를 제거할 수 있습니다. 또한 검색, 추가, 사전 보류 등을 위한 멤버 기능의 이점을 얻을 수 있습니다. 둘 다 속도에 매우 최적화되어 있습니다. 읽기 전용 액세스만 필요한 함수에 문자열을 전달할 때 C++17에서 [std::string_view](../standard-library/basic-string-view-class.md) 사용하면 성능이 훨씬 향상됩니다.

## <a name="stdvector-and-other-standard-library-containers"></a>std::벡터 및 기타 표준 라이브러리 컨테이너

표준 라이브러리 컨테이너는 모두 RAII 의 원칙을 따릅니다. 요소의 안전한 통과를 위한 이터레이터를 제공합니다. 또한 성능에 최적화되어 있으며 정확성에 대한 테스트를 철저히 거쳤습니다. 이러한 컨테이너를 사용하면 사용자 지정 데이터 구조에 발생할 수 있는 버그 나 비효율성이 발생할 수 있습니다. 원시 배열 대신 C++에서 순차 컨테이너로 [벡터를](../standard-library/vector-class.md) 사용합니다.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

맵(아님)을 [map](../standard-library/map-class.md) `unordered_map`기본 연관 컨테이너로 사용합니다. 퇴화 및 다중 사례에 대해 [집합,](../standard-library/set-class.md) [다중 맵](../standard-library/multimap-class.md)및 [다중 집합을](../standard-library/multiset-class.md) 사용합니다.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

성능 최적화가 필요한 경우 다음을 사용하는 것이 좋습니다.

- 포함 할 때 [배열](../standard-library/array-class-stl.md) 유형은 클래스 멤버와 같이 중요합니다.

- [unordered_map](../standard-library/unordered-map-class.md)와 같은 정렬되지 않은 연관 컨테이너. 요소당 오버헤드와 일정한 시간 조회가 낮지만 정확하고 효율적으로 사용하기가 더 어려울 수 있습니다.

- 정렬된 `vector`. 자세한 내용은 [알고리즘](../cpp/algorithms-modern-cpp.md)을 참조하세요.

C 스타일 배열을 사용하지 마십시오. 데이터에 직접 액세스해야 하는 이전 API의 경우 대신 `f(vec.data(), vec.size());` 액세스 자 메서드를 사용합니다. 컨테이너에 대한 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하십시오.

## <a name="standard-library-algorithms"></a>표준 라이브러리 알고리즘

프로그램에 대한 사용자 지정 알고리즘을 작성해야 한다고 가정하기 전에 먼저 C++ 표준 라이브러리 [알고리즘을 검토합니다.](../standard-library/algorithm.md) 표준 라이브러리에는 검색, 정렬, 필터링 및 무작위화와 같은 많은 일반적인 작업에 대한 알고리즘이 계속 증가하고 있습니다. 수학 라이브러리는 광범위합니다. C++17부터는 많은 알고리즘의 병렬 버전이 제공됩니다.

다음은 몇 가지 중요한 예입니다.

- **for_each**기본 다량 알고리즘(범위 기반 for 루프)입니다.

- **변환**, 컨테이너 요소의 장소 내 수정

- **find_if**기본 검색 알고리즘입니다.

- **정렬**, **lower_bound**및 기타 기본 정렬 및 검색 알고리즘입니다.

비교기를 작성하려면, 엄격하게 **<** 사용하고 당신이 할 수있는 경우 명명 된 *람다를* 사용합니다.

```cpp
auto comp = [](const widget& w1, const widget& w2)
     { return w1.weight() < w2.weight(); }

sort( v.begin(), v.end(), comp );

auto i = lower_bound( v.begin(), v.end(), comp );
```

## <a name="auto-instead-of-explicit-type-names"></a>명시적 형식 이름 대신 자동

C++11은 변수, 함수 및 템플릿 선언에 사용할 [자동](auto-cpp.md) 키워드를 도입했습니다. **auto는** 컴파일러에 개체의 형식을 추론하여 명시적으로 입력할 필요가 없도록 지시합니다. **auto는** 추론된 형식이 중첩된 템플릿인 경우에 특히 유용합니다.

```cpp
map<int,list<string>>::iterator i = m.begin(); // C-style
auto i = m.begin(); // modern C++
```

## <a name="range-based-for-loops"></a>루프에 대한 범위 기반

배열 및 컨테이너에 대한 C 스타일 반복은 인덱싱 오류가 발생하기 쉽고 입력하기도 지루합니다. 이러한 오류를 제거하고 코드를 더 읽기 쉽게 만들려면 표준 라이브러리 컨테이너 및 원시 배열이 모두 있는 범위 기반 루프를 사용합니다. 자세한 내용은 [문 범위 기반](../cpp/range-based-for-statement-cpp.md)을 참조하십시오.

```cpp
#include <iostream>
#include <vector>

int main()
{
    std::vector<int> v {1,2,3};

    // C-style
    for(int i = 0; i < v.size(); ++i)
    {
        std::cout << v[i];
    }

    // Modern C++:
    for(auto& num : v)
    {
        std::cout << num;
    }
}
```

## <a name="constexpr-expressions-instead-of-macros"></a>매크로 대신 constexpr 식

C 및 C++의 매크로는 컴파일 하기 전에 전처리기에서 처리 되는 토큰입니다. 매크로 토큰의 각 인스턴스는 파일을 컴파일하기 전에 정의된 값 또는 식으로 대체됩니다. 매크로는 일반적으로 C 스타일 프로그래밍에서 컴파일 타임 상수 값을 정의하는 데 사용됩니다. 그러나 매크로는 오류가 발생하기 쉽고 디버깅이 어렵습니다. 최신 C++에서는 컴파일 타임 상수에 대해 [constexpr](constexpr-cpp.md) 변수를 선호해야 합니다.

```cpp
#define SIZE 10 // C-style
constexpr int size = 10; // modern C++
```

### <a name="uniform-initialization"></a>균일 한 초기화

최신 C++에서는 모든 유형에 중괄호 초기화를 사용할 수 있습니다. 이 초기화 형식은 배열, 벡터 또는 기타 컨테이너를 초기화할 때 특히 편리합니다. 다음 예제에서는 `v2` `S`의 세 인스턴스로 초기화됩니다. `v3`중괄호를 사용하여 `S` 초기화되는 세 가지 인스턴스로 초기화됩니다. 컴파일러는 선언된 형식에 따라 각 요소의 형식을 `v3`유추합니다.

```cpp
#include <vector>

struct S
{
    std::string name;
    float num;
    S(std::string s, float f) : name(s), num(f) {}
};

int main()
{
    // C-style initialization
    std::vector<S> v;
    S s1("Norah", 2.7);
    S s2("Frank", 3.5);
    S s3("Jeri", 85.9);

    v.push_back(s1);
    v.push_back(s2);
    v.push_back(s3);

    // Modern C++:
    std::vector<S> v2 {s1, s2, s3};

    // or...
    std::vector<S> v3{ {"Norah", 2.7}, {"Frank", 3.5}, {"Jeri", 85.9} };

}
```

자세한 내용은 [중괄호 초기화를](initializing-classes-and-structs-without-constructors-cpp.md)참조하십시오.

## <a name="move-semantics"></a>의미 체계 이동

최신 C++는 *이동 의미 체계를*제공하여 불필요한 메모리 복사본을 제거할 수 있습니다. 이전 버전의 언어에서는 특정 상황에서 복사본이 불가피했습니다. *이동* 작업은 복사본을 만들지 않고 리소스의 소유권을 한 개체에서 다음 개체로 이전합니다. 리소스를 소유 하는 클래스를 구현할 때 (힙 메모리, 파일 핸들 등) *이동 생성자* 및 *이동 할당 연산자* 를 정의할 수 있습니다. 컴파일러는 복사본이 필요하지 않은 상황에서 오버로드 해결 중에 이러한 특수 멤버를 선택합니다. 표준 라이브러리 컨테이너 유형이 정의된 경우 개체에 이동 생성자가 호출됩니다. 자세한 내용은 [생성자 이동 및 할당 연산자 이동(C++)을](move-constructors-and-move-assignment-operators-cpp.md)참조하십시오.

## <a name="lambda-expressions"></a>람다 식

C 스타일 프로그래밍에서는 함수 *포인터를*사용하여 함수를 다른 함수로 전달할 수 있습니다. 함수 포인터는 유지 관리 및 이해하기가 불편합니다. 참조하는 함수는 호출되는 지점에서 멀리 떨어진 소스 코드의 다른 위치에 정의될 수 있습니다. 또한 형식이 안전하지 않습니다. 현대 C ++는 *함수 객체*, [()](function-call-operator-parens.md) 연산자 재정의하는 클래스를 제공하여 함수처럼 호출 할 수 있습니다. 함수 개체를 만드는 가장 편리한 방법은 인라인 [람다 식을 사용하는 것입니다.](../cpp/lambda-expressions-in-cpp.md) 다음 예제에서는 lambda 식을 사용하여 함수 개체를 전달하는 `for_each` 방법을 보여 주며, 함수는 벡터의 각 요소에 대해 호출됩니다.

```cpp
    std::vector<int> v {1,2,3,4,5};
    int x = 2;
    int y = 4;
    auto result = find_if(begin(v), end(v), [=](int i) { return i > x && i < y; });
```

lambda `[=](int i) { return i > x && i < y; }` 식은 `int` "형식의 단일 인수를 취하고 인수가 보다 `x` 크고 작은지 여부를 나타내는 부울을 `y`반환하는 함수"로 읽을 수 있습니다. `x` 변수와 `y` 주변 컨텍스트에서 람다에서 사용할 수 있습니다. 는 `[=]` 이러한 변수가 값으로 *캡처되도록* 지정합니다. 즉, 람다 식에는 해당 값의 자체 복사본이 있습니다.

## <a name="exceptions"></a>예외

최신 C++는 오류 조건을 보고하고 처리하는 가장 좋은 방법으로 오류 코드가 아닌 예외를 강조합니다. 자세한 내용은 [예외 및 오류 처리에 대한 최신 C++ 모범 사례를](errors-and-exception-handling-modern-cpp.md)참조하십시오.

## <a name="stdatomic"></a>std::원자성

스레드 간 통신 메커니즘에 대한 C ++ 표준 라이브러리 [std::원자](../standard-library/atomic-structure.md) 구조체 및 관련 형식을 사용합니다.

## <a name="stdvariant-c17"></a>std::변형(C++17)

공용 구조체는 일반적으로 C 스타일 프로그래밍에서 서로 다른 유형의 구성원이 동일한 메모리 위치를 차지할 수 있도록 하여 메모리를 보존하는 데 사용됩니다. 그러나 공용 구조체는 형식이 안전하지 않으며 프로그래밍 오류가 발생하기 쉽습니다. C++17은 [std::variant](../standard-library/variant-class.md) 클래스를 보다 강력하고 안전한 조합으로 소개합니다. [std::visit](../standard-library/variant-functions.md#visit) 함수는 형식에 안전한 방식으로 `variant` 형식의 멤버에 액세스하는 데 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[C++ 언어 참조](../cpp/cpp-language-reference.md)\
[람다 표현식](../cpp/lambda-expressions-in-cpp.md)\
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)\
[Microsoft C++ 언어 규칙 테이블](../overview/visual-cpp-language-conformance.md)
