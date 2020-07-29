---
title: C++ 시작하기 - 최신 C++
description: 최신 c + +의 새로운 프로그래밍 관용구 및 해당 근거에 대해 설명 합니다.
ms.date: 05/17/2020
ms.topic: conceptual
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
ms.openlocfilehash: f2b9159e74ba7ce37c7eab1513826da939a3be49
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232198"
---
# <a name="welcome-back-to-c---modern-c"></a>C++ 시작하기 - 최신 C++

C + +는 생성 되기 때문에 전 세계에서 가장 널리 사용 되는 프로그래밍 언어 중 하나입니다. 잘 작성된 C++ 프로그램은 빠르고 효율적입니다. 이 언어는 다른 언어 보다 더 유연 합니다. 가장 높은 수준의 추상화에서 작동 하 고 실리콘 수준에서 아래로 작동할 수 있습니다. C + +는 매우 최적화 된 표준 라이브러리를 제공 합니다. 이를 통해 하위 수준 하드웨어 기능에 액세스 하 여 속도를 최대화 하 고 메모리 요구 사항을 최소화할 수 있습니다. C + +를 사용 하 여 다양 한 범위의 앱을 만들 수 있습니다. 게임, 장치 드라이버 및 고성능 과학 소프트웨어 포함 된 프로그램. Windows 클라이언트 앱. 다른 프로그래밍 언어에 대 한 라이브러리와 컴파일러는 c + +로 작성 됩니다.

C++의 본래 요구 사항 중 하나는 C 언어와의 역 호환성이었습니다. 결과적으로 c + +에서는 원시 포인터, 배열, null 종료 문자열 및 기타 기능을 사용 하 여 C 스타일 프로그래밍을 항상 허용 했습니다. 이렇게 하면 성능이 향상 될 수 있지만 버그 및 복잡성을 생성할 수도 있습니다. C + +의 진화에는 C 스타일 관용구를 사용 해야 하는 필요성을 크게 줄여 주는 기능이 강조 되어 있습니다. 이전 C + + 코드는 필요할 때 있지만 최신 c + + 코드를 사용 하는 경우에는 더 작고 작아야 합니다. 최신 c + + 코드는 보다 간단 하 고, 안전 하 고, 세련 되며, 계속 해 서 신속 하 게 진행 됩니다.

다음 섹션에서는 최신 c + +의 주요 기능에 대 한 개요를 제공 합니다. 별도로 언급 하지 않는 한 여기에 나열 된 기능은 c + + 11 이상에서 사용할 수 있습니다. Microsoft c + + 컴파일러에서는 컴파일러 옵션을 설정 [`/std`](../build/reference/std-specify-language-standard-version.md) 하 여 프로젝트에 사용할 표준 버전을 지정할 수 있습니다.

## <a name="resources-and-smart-pointers"></a>리소스 및 스마트 포인터

C 스타일 프로그래밍의 주요 버그 클래스 중 하나는 *메모리 누수*입니다. 누수는 일반적 **`delete`** 으로에 할당 된 메모리에 대 한 호출 실패로 인해 발생 **`new`** 합니다. 최신 c + +는 RAII ( *리소스 획득) 초기화* 의 원칙을 강조 합니다. 이 개념은 간단 합니다. 개체에서 리소스 (힙 메모리, 파일 핸들, 소켓 등)를 *소유* 해야 합니다. 해당 개체는 생성자에서 새로 할당 된 리소스를 만들거나 받고 해당 소멸자에서 삭제 합니다. RAII의 원칙은 소유 하는 개체가 범위를 벗어날 때 모든 리소스가 운영 체제에 제대로 반환 되도록 보장 합니다.

RAII 원칙을 쉽게 채택할 수 있도록 c + + 표준 라이브러리는 세 가지 스마트 포인터 형식인 [`std::unique_ptr`](../standard-library/unique-ptr-class.md) , 및를 제공 합니다. [`std::shared_ptr`](../standard-library/shared-ptr-class.md) [`std::weak_ptr`](../standard-library/weak-ptr-class.md) 스마트 포인터는 소유 하 고 있는 메모리의 할당 및 삭제를 처리 합니다. 다음 예제에서는에 대 한 호출에서 힙에 할당 된 배열 멤버가 있는 클래스를 보여 줍니다 `make_unique()` . 및에 대 **`new`** 한 호출은 **`delete`** 클래스에 의해 캡슐화 됩니다 `unique_ptr` . `widget`개체가 범위를 벗어나면 unique_ptr 소멸자가 호출 되 고 배열에 할당 된 메모리가 해제 됩니다.  

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

가능한 경우 힙 메모리를 할당할 때 스마트 포인터를 사용 합니다. New 및 delete 연산자를 명시적으로 사용 해야 하는 경우 RAII의 원칙을 따릅니다. 자세한 내용은 [RAII (개체 수명 및 리소스 관리)](object-lifetime-and-resource-management-modern-cpp.md)를 참조 하세요.

## <a name="stdstring-and-stdstring_view"></a>`std::string` 및 `std::string_view`

C 스타일 문자열은 버그의 또 다른 주요 소스입니다. [ `std::string` 및 `std::wstring` ](../standard-library/basic-string-class.md)를 사용 하 여 C 스타일 문자열과 관련 된 모든 오류를 거의 제거할 수 있습니다. 또한 검색, 추가, 앞으로 등의 멤버 함수에 대 한 혜택을 얻을 수 있습니다. 두 가지 모두 속도에 최적화 되어 있습니다. 읽기 전용 액세스만 필요한 함수에 문자열을 전달 하는 경우 c + + 17에서는를 사용 하 여 [`std::string_view`](../standard-library/basic-string-view-class.md) 성능 향상을 높일 수 있습니다.

## <a name="stdvector-and-other-standard-library-containers"></a>`std::vector`및 기타 표준 라이브러리 컨테이너

표준 라이브러리 컨테이너는 모두 RAII의 원칙을 따릅니다. 요소를 안전 하 게 순회 하기 위한 반복기를 제공 합니다. 또한 성능에 최적화 되어 있으며 정확성을 철저 하 게 테스트 했습니다. 이러한 컨테이너를 사용 하 여 사용자 지정 데이터 구조에 도입 될 수 있는 버그 또는 비효율성의 가능성을 없앨 수 있습니다. 원시 배열 대신 [`vector`](../standard-library/vector-class.md) c + +에서 순차 컨테이너로를 사용 합니다.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

[`map`](../standard-library/map-class.md) `unordered_map` 기본 결합형 컨테이너로 (not)를 사용 합니다. [`set`](../standard-library/set-class.md)중복 제거 [`multimap`](../standard-library/multimap-class.md) [`multiset`](../standard-library/multiset-class.md) 및 다중 사례에는, 및를 사용 합니다.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

성능 최적화가 필요한 경우 다음을 사용 하십시오.

- 예를 들어 [`array`](../standard-library/array-class-stl.md) 를 클래스 멤버로 포함 하는 경우 형식을 포함 하는 것이 중요 합니다.

- 와 같은 순서가 지정 되지 않은 연관 컨테이너 [`unordered_map`](../standard-library/unordered-map-class.md) 입니다. 이러한 요소는 요소 당 오버 헤드와 일정 시간 조회의 하위 요소를 갖지만 올바르고 효율적으로 사용 하기가 어려울 수 있습니다.

- 정렬 `vector` 되었습니다. 자세한 내용은 [알고리즘](../cpp/algorithms-modern-cpp.md)을 참조하세요.

C 스타일 배열을 사용 하지 마세요. 데이터에 직접 액세스 해야 하는 이전 Api의 경우와 같은 접근자 메서드를 `f(vec.data(), vec.size());` 대신 사용 합니다. 컨테이너에 대 한 자세한 내용은 [c + + 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조 하세요.

## <a name="standard-library-algorithms"></a>표준 라이브러리 알고리즘

프로그램에 대 한 사용자 지정 알고리즘을 작성 해야 한다고 가정 하기 전에 먼저 c + + 표준 라이브러리 [알고리즘](../standard-library/algorithm.md)을 검토 합니다. 표준 라이브러리에는 검색, 정렬, 필터링, 임의로 선택할 등의 여러 일반적인 작업에 대해 점점 확장 된 알고리즘 모음이 포함 되어 있습니다. 수학 라이브러리는 광범위 합니다. C + + 17부터 많은 알고리즘의 병렬 버전이 제공 됩니다.

다음은 몇 가지 중요 한 예입니다.

- `for_each`, 기본 순회 알고리즘 (범위 기반 루프와 함께 `for` )

- `transform`-컨테이너 요소를 바로 수정할 수 없습니다.

- `find_if`-기본 검색 알고리즘입니다.

- `sort`, `lower_bound` 및 기타 기본 정렬 및 검색 알고리즘

비교 연산자를 작성 하려면 가능 하면 strict를 사용 하 **`<`** 고 *명명 된 람다* 를 사용 합니다.

```cpp
auto comp = [](const widget& w1, const widget& w2)
     { return w1.weight() < w2.weight(); }

sort( v.begin(), v.end(), comp );

auto i = lower_bound( v.begin(), v.end(), comp );
```

## <a name="auto-instead-of-explicit-type-names"></a>`auto`명시적 형식 이름 대신

C + + 11에는 [`auto`](auto-cpp.md) 변수, 함수 및 템플릿 선언에 사용할 키워드가 도입 되었습니다. **`auto`** 는 명시적으로 입력할 필요가 없도록 개체의 형식을 추론 하도록 컴파일러에 지시 합니다. **`auto`** 는 추론 된 형식이 중첩 된 템플릿인 경우 특히 유용 합니다.

```cpp
map<int,list<string>>::iterator i = m.begin(); // C-style
auto i = m.begin(); // modern C++
```

## <a name="range-based-for-loops"></a>범위 기반 `for` 루프

배열 및 컨테이너에 대 한 C 스타일 반복은 인덱싱 오류가 발생 하기 쉬우므로 형식에도 지루한 것입니다. 이러한 오류를 제거 하 고 코드를 더 읽기 쉽게 만들려면 **`for`** 표준 라이브러리 컨테이너와 원시 배열 모두에 범위 기반 루프를 사용 합니다. 자세한 내용은 [범위 기반 `for` 문](../cpp/range-based-for-statement-cpp.md)을 참조 하세요.

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

## <a name="constexpr-expressions-instead-of-macros"></a>`constexpr`매크로가 아닌 식

C 및 c + +의 매크로는 컴파일 전에 전처리기에 의해 처리 되는 토큰입니다. 매크로 토큰의 각 인스턴스는 파일이 컴파일되기 전에 정의 된 값 또는 식으로 바뀝니다. 매크로는 일반적으로 C 스타일 프로그래밍에서 컴파일 타임 상수 값을 정의 하는 데 사용 됩니다. 그러나 매크로는 오류가 발생 하기 쉬우며 디버깅 하기 어렵습니다. 최신 c + +에서는 [`constexpr`](constexpr-cpp.md) 컴파일 시간 상수인 변수를 선호 해야 합니다.

```cpp
#define SIZE 10 // C-style
constexpr int size = 10; // modern C++
```

### <a name="uniform-initialization"></a>균일 초기화

최신 c + +에서는 모든 형식에 대해 중괄호 초기화를 사용할 수 있습니다. 이러한 형태의 초기화는 배열, 벡터 또는 다른 컨테이너를 초기화할 때 특히 편리 합니다. 다음 예에서는 `v2` 의 세 가지 인스턴스를 사용 하 여를 초기화 `S` 합니다. `v3`는 `S` 중괄호를 사용 하 여 초기화 되는의 세 인스턴스를 사용 하 여 초기화 됩니다. 컴파일러는의 선언 된 형식을 기반으로 각 요소의 형식을 유추 합니다 `v3` .

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

자세한 내용은 [중괄호 초기화](initializing-classes-and-structs-without-constructors-cpp.md)를 참조 하세요.

## <a name="move-semantics"></a>의미 체계 이동

최신 c + +는 불필요 한 메모리 복사본을 제거할 수 있도록 하는 *이동 의미 체계*를 제공 합니다. 이전 버전의 언어에서는 특정 상황에서 복사본이 피할 였습니다. *이동* 작업은 복사를 수행 하지 않고 한 개체에서 다음 개체로 리소스 소유권을 전송 합니다. 일부 클래스는 힙 메모리, 파일 핸들 등의 리소스를 소유 합니다. 리소스 소유 클래스를 구현 하는 경우 해당 클래스에 대 한 *이동 생성자* 및 *이동 할당 연산자* 를 정의할 수 있습니다. 컴파일러가 복사본이 필요 하지 않은 경우 오버 로드 확인 중에 이러한 특수 멤버를 선택 합니다. 표준 라이브러리 컨테이너 형식은 개체에 대해 이동 생성자를 호출 합니다 (정의 된 경우). 자세한 내용은 [이동 생성자 및 이동 할당 연산자 (c + +)](move-constructors-and-move-assignment-operators-cpp.md)를 참조 하세요.

## <a name="lambda-expressions"></a>람다 식

C 스타일 프로그래밍에서 함수 *포인터*를 사용 하 여 함수를 다른 함수에 전달할 수 있습니다. 함수 포인터는 유지 관리 및 이해 하기가 불편할 수 있습니다. 참조 하는 함수는 소스 코드에서 호출 되는 지점에서 멀리 떨어진 위치에 정의 될 수 있습니다. 또한 형식이 안전 하지 않습니다. 최신 c + +에서는 연산자를 재정의 하는 *함수 개체*를 제공 [`operator()`](function-call-operator-parens.md) 합니다 .이를 통해 함수는 함수 처럼 호출 될 수 있습니다. 함수 개체를 만드는 가장 편리한 방법은 인라인 [람다 식](../cpp/lambda-expressions-in-cpp.md)을 사용 하는 것입니다. 다음 예제에서는 람다 식을 사용 하 여 함수 개체를 전달 하는 방법을 보여 줍니다 `for_each` . 함수가 vector의 각 요소에 대해 호출 됩니다.

```cpp
    std::vector<int> v {1,2,3,4,5};
    int x = 2;
    int y = 4;
    auto result = find_if(begin(v), end(v), [=](int i) { return i > x && i < y; });
```

람다 식은 `[=](int i) { return i > x && i < y; }` 형식의 단일 인수를 사용 하 **`int`** 고 인수가 보다 큰지 여부를 나타내는 부울을 반환 하는 "함수"로 읽을 수 있습니다 `x` `y` . 주변 컨텍스트의 변수와 변수 `x` 는 `y` 람다에서 사용할 수 있습니다. 는 `[=]` 이러한 변수를 값으로 *캡처하도록* 지정 합니다. 즉, 람다 식에는 해당 값의 자체 복사본이 있습니다.

## <a name="exceptions"></a>예외

최신 c + +에서는 오류를 보고 하 고 처리 하는 가장 좋은 방법으로 오류 코드가 아닌 예외를 강조 합니다. 자세한 내용은 [예외 및 오류 처리에 대 한 최신 c + + 모범 사례](errors-and-exception-handling-modern-cpp.md)를 참조 하세요.

## `std::atomic`

스레드 간 통신 메커니즘에는 c + + 표준 라이브러리 [`std::atomic`](../standard-library/atomic-structure.md) 구조체 및 관련 형식을 사용 합니다.

## <a name="stdvariant-c17"></a>`std::variant`(C + + 17)

공용 구조체는 여러 형식의 멤버가 동일한 메모리 위치를 차지할 수 있도록 하 여 메모리를 절약 하는 C 스타일 프로그래밍에서 일반적으로 사용 됩니다. 그러나 공용 구조체는 형식이 안전 하지 않으며 프로그래밍 오류가 발생 하기 쉽습니다. C + + 17은 [`std::variant`](../standard-library/variant-class.md) 공용 구조체에 대 한 보다 강력 하 고 안전한 방법으로 클래스를 도입 합니다. [`std::visit`](../standard-library/variant-functions.md#visit)함수를 사용 하 여 형식이 안전한 방식으로 형식의 멤버에 액세스할 수 있습니다 `variant` .

## <a name="see-also"></a>참조

[C++ 언어 참조](../cpp/cpp-language-reference.md)\
[람다 식](../cpp/lambda-expressions-in-cpp.md)\
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)\
[Microsoft C++ 언어 규칙 테이블](../overview/visual-cpp-language-conformance.md)
