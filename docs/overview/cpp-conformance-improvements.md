---
title: C++ 규칙 향상
ms.date: 12/04/2019
description: Visual Studio의 Microsoft C++는 C++20 언어 표준을 완전하게 준수하기 위해 점점 향상되고 있습니다.
ms.technology: cpp-language
ms.openlocfilehash: e9c2a69c8d33ea692a76a5642a15b581567c2c63
ms.sourcegitcommit: 5f276064779d90a4cfda758f89e0c0f1e4d1a188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75793845"
---
# <a name="c-conformance-improvements-in-visual-studio"></a>Visual Studio의 C++ 규칙 향상

Microsoft C++는 모든 릴리스에서 규칙 및 버그 수정을 향상합니다. 이 문서에는 주 릴리스와 버전별 개선 사항이 나와 있습니다. 버전별로 주요 버그 수정도 나와 있습니다. 특정 버전의 변경 내용으로 바로 이동하려면 **이 문서의 내용** 목록을 사용합니다.

::: moniker range="vs-2019"

## <a name="improvements_160"></a> Visual Studio 2019 RTW(버전 16.0)의 규칙 향상

Visual Studio 2019 RTW에는 다음과 같은 Microsoft C++ 컴파일러(MSVC)의 규칙 향상, 버그 수정 및 동작 변경이 포함되어 있습니다.

**참고:** C++20 기능은 컴파일러와 IntelliSense 모두에 대해 C++20 구현이 완료될 때까지 `/std:c++latest` 모드에서 사용할 수 있습니다. 이때 `/std:c++20` 컴파일러 모드가 도입됩니다.

### <a name="improved-modules-support-for-templates-and-error-detection"></a>템플릿 및 오류 검색에 대한 향상된 모듈 지원

모듈은 이제 공식적으로 C++20 표준에 속합니다. Visual Studio 2017 버전 15.9에는 향상된 지원이 추가되었습니다. 자세한 내용은 [MSVC 2017 버전 15.9를 사용하여 C++ 모듈의 템플릿 지원 및 오류 검색 향상](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/)을 참조하세요.

### <a name="modified-specification-of-aggregate-type"></a>집계 유형의 수정된 사양

집계 유형의 사양이 C++20에서 변경되었습니다([사용자가 선언한 생성자로 집계 금지](https://wg21.link/p1008r1) 참조). Visual Studio 2019의 `/std:c++latest`에서 사용자가 선언한 생성자가 있는 클래스(예: `= default` 또는 `= delete`로 선언된 생성자 포함)는 집계가 아닙니다. 이전에는 사용자가 제공한 생성자만 클래스가 집계되지 못하도록 합니다. 이 변경으로 인해 이러한 형식을 초기화할 수 있는 방법이 제한됩니다.

다음 코드는 Visual Studio 2017에서 오류 없이 컴파일되지만 `/std:c++latest` 아래의 Visual Studio 2019에서는 C2280 및 C2440 오류를 발생시킵니다.

```cpp
struct A
{
    A() = delete; // user-declared ctor
};

struct B
{
    B() = default; // user-declared ctor
    int i = 0;
};

A a{}; // ill-formed in C++20, previously well-formed
B b = { 1 }; // ill-formed in C++20, previously well-formed
```

### <a name="partial-support-for-operator-"></a>`operator <=>`에 대한 부분 지원

[P0515R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0515r3.pdf) C++20에서는 "우주선 연산자"라고도 하는 `<=>` 3방향 비교 연산자를 소개합니다. `/std:c++latest` 모드의 Visual Studio 2019는 현재 허용되지 않는 구문 오류를 발생시켜 연산자에 대한 부분 지원을 도입합니다. 예를 들어 다음 코드는 Visual Studio 2017에서 오류 없이 컴파일되지만 `/std:c++latest` 아래의 Visual Studio 2019에서는 여러 오류가 발생합니다.

```cpp
struct S
{
    bool operator<=(const S&) const { return true; }
};

template <bool (S::*)(const S&) const>
struct U { };

int main(int argc, char** argv)
{
    U<&S::operator<=> u; // In Visual Studio 2019 raises C2039, 2065, 2146.
}
```

오류를 방지하려면, 위반하는 줄에서 최종 꺾쇠괄호 앞에 공백을 삽입합니다. `U<&S::operator<= > u;`

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>일치하지 않는 cv 한정자가 있는 유형에 대한 참조

이전에는 MSVC에서 최상위 수준 아래에 일치하지 않는 cv 한정자가 있는 형식의 참조를 직접 바인딩할 수 있었습니다. 이 바인딩은 참조가 나타내는 것으로 추정되는 const 데이터의 수정을 허용할 수 있었습니다. 이제 컴파일러에서 표준에 따라 임시 바인딩을 만듭니다. Visual Studio 2017에서 다음 코드는 경고 없이 컴파일됩니다. Visual Studio 2019에서 컴파일러는 *경고 C4172: \<func:#1 "?PData@X@@QBEABQBXXZ"> 로컬 변수 또는 임시*  주소를 반환합니다.

```cpp
struct X
{
    const void* const& PData() const
    {
        return _pv;
    }

    void* _pv;
};

int main()
{
    X x;
    auto p = x.PData(); // C4172
}
```

### <a name="reinterpret_cast-from-an-overloaded-function"></a>`reinterpret_cast` 오버로드된 함수에서

`reinterpret_cast`의 인수는 오버로드된 함수의 주소가 허용되는 컨텍스트 중 하나가 아닙니다. 다음 코드는 Visual Studio 2017에서 오류 없이 컴파일되지만 Visual Studio 2019에서는 *C2440: '오버로드된 함수'에서 'fp'로 변환될 수 없음*을 발생시킵니다.

```cpp
int f(int) { return 1; }
int f(float) { return .1f; }
using fp = int(*)(int);

int main()
{
    fp r = reinterpret_cast<fp>(&f);
}
```

오류를 방지하려면 이 시나리오에 허용된 캐스트를 사용합니다.

```cpp
int f(int);
int f(float);
using fp = int(*)(int);

int main()
{
    fp r = static_cast<fp>(&f); // or just &f;
}
```

### <a name="lambda-closures"></a>람다 클로저

C++14에서 람다 클로저 형식은 리터럴이 아닙니다. 이 규칙의 기본 결과는 람다가 **constexpr** 변수에 할당되지 않을 수 있다는 것입니다. 다음 코드는 Visual Studio 2017에서 오류 없이 컴파일되지만, Visual Studio 2019에서는 ‘C2127: ‘l’: 비상수 식으로 ‘constexpr’ 엔터티 초기화가 잘못되었습니다.’가 발생합니다. 

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

오류를 방지하려면 **constexpr** 한정자를 제거하거나 규칙 모드를 `/std:c++17`로 변경합니다.

### <a name="stdcreate_directory-failure-codes"></a>`std::create_directory` 실패 코드

C++20에서 [P1164](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1164r1.pdf)를 무조건으로 구현했습니다. 이렇게 하면 대상이 이미 실패한 디렉터리인지 여부를 확인하기 위해 `std::create_directory`가 변경됩니다. 이전에는 모든 ERROR_ALREADY_EXISTS 형식 오류가 success-but-directory-not-created 코드로 변경되었습니다.

### `operator<<(std::ostream, nullptr_t)`

[LWG 2221](https://cplusplus.github.io/LWG/issue2221)당 스크림에 nullptrs를 쓰기 위해 `operator<<(std::ostream, nullptr_t)`을 추가했습니다.

### <a name="additional-parallel-algorithms"></a>추가 병렬 알고리즘

`is_sorted`, `is_sorted_until`, `is_partitioned`, `set_difference`, `set_intersection`, `is_heap` 및 `is_heap_until`의 새 병렬 버전.

### <a name="atomic-initialization"></a>원자성 초기화

[P0883 "원자성 초기화 수정"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0883r1.pdf)은 `std::atomic`을 변경하여 포함된 T를 기본 초기화하는 대신 값을 초기화합니다. 이 수정 내용은 Microsoft 표준 라이브러리에서 Clang/LLVM을 사용할 때 활성화됩니다. 현재 Microsoft C++ 컴파일러에서 **constexpr** 처리 중인 버그에 대한 해결 방법으로 사용할 수 없습니다.

### <a name="remove_cvref-and-remove_cvref_t"></a>`remove_cvref` 및 `remove_cvref_t`

[P0550](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf)에서 `remove_cvref` 및 `remove_cvref_t` 형식 특성을 구현했습니다. 이러한 특성은 함수 및 배열이 손상되지 않는 유형에서 포인터(`std::decay` 및 `std::decay_t`와는 달리)로 참조 및 cv 한정자를 제거합니다.

### <a name="feature-test-macros"></a>기능 테스트 매크로

[P0941R2 - feature-test 매크로](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html)는 `__has_cpp_attribute`에 대한 지원으로 완료되었습니다. 기능 테스트 매크로는 모든 표준 모드에서 지원됩니다.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>사용자 선언 생성자를 사용하여 집계 금지

[C++20 P1008R1 - 사용자 선언 생성자를 사용하여 집계 금지](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf)가 완료되었습니다.

## <a name="improvements_161"></a> 16.1의 규칙 향상

### <a name="char8_t"></a>char8_t

[P0482r6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html). C++20은 UTF-8 코드 단위를 나타내는 데 사용되는 새로운 문자 형식을 추가합니다. C++20의 `u8` 문자열 리터럴에는 이전의 `const char[N]` 대신 `const char8_t[N]` 형식이 있습니다. [N2231](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n2231.htm)에서 C 표준에 대해 유사한 변경이 제안되었습니다. `char8_t` 이전 버전과의 호환성 수정에 대한 제안은 [P1423r0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1423r0.html)에서 제공됩니다. Microsoft C++ 컴파일러는 **/Zc:char8_t** 컴파일러 옵션을 지정할 때 Visual Studio 2019 버전 16.1에서 `char8_t` 지원을 추가합니다. 향후 **/Zc:char8_t-** 를 통해 C++17 동작으로 되돌릴 수 있는 [/std:c++latest](../build/reference/std-specify-language-standard-version.md)로 지원될 예정입니다. IntelliSense를 지원하는 EDG 컴파일러는 이 기능을 아직 지원하지 않으므로 실제 컴파일에 영향을 주지 않는 IntelliSense 전용 의사 오류가 표시됩니다.

#### <a name="example"></a>예제

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtype_identity-metafunction-and-stdidentity-function-object"></a>std::type_identity 메타 함수 및 std:: identity 함수 개체

[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf). 사용되지 않는 `std::identity` 클래스 템플릿 확장이 제거되었으며 C++20 `std::type_identity` 메타 함수 및 `std::identity` 함수 개체로 대체되었습니다. 둘 다 [/std:c++latest](../build/reference/std-specify-language-standard-version.md)에서만 사용할 수 있습니다.

다음 예제에서는 Visual Studio 2017에서 `std::identity`(\<type_traits>에서 정의됨)에 대한 사용 중단 경고 C4996을 생성합니다.

```cpp
#include <type_traits>

using T = std::identity<int>::type;
T x, y = std::identity<T>{}(x);
int i = 42;
long j = std::identity<long>{}(i);
```

다음 예제에서는 새 `std::identity`(\<functional>에서 정의됨)를 `std::type_identity`와 함께 사용하는 방법을 보여줍니다.

```cpp
#include <type_traits>
#include <functional>

using T = std::type_identity<int>::type;
T x, y = std::identity{}(x);
int i = 42;
long j = static_cast<long>(i);
```

### <a name="syntax-checks-for-generic-lambdas"></a>일반 람다에 대한 구문 검사

새 람다 프로세서는 [/std:c++latest](../build/reference/std-specify-language-standard-version.md) 또는 **/experimental:newLambdaProcessor**를 사용하는 다른 언어 모드 아래의 일반 람다에서 몇 가지 규칙 모드 구문 검사를 활성화합니다.

Visual Studio 2017에서 이 코드는 경고 없이 컴파일되지만 Visual Studio 2019에서는 *C2760 구문 오류: 예기치 않은 토큰 '\<id-expr>', expected 'id-expression'* 오류가 생성됩니다.

```cpp
void f() {
    auto a = [](auto arg) {
        decltype(arg)::Type t;
    };
}
```

다음 예제는 올바른 구문을 보여주고, 이제 컴파일러에 의해 적용됩니다.

```cpp
void f() {
    auto a = [](auto arg) {
        typename decltype(arg)::Type t;
    };
}
```

### <a name="argument-dependent-lookup-for-function-calls"></a>함수 호출에 대한 인수 종속 조회

[P0846R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0846r0.html)(C++20) 명시적 템플릿 인수를 사용하는 함수 호출 식에 대한 인수 종속 조회를 통해 함수 템플릿을 찾는 기능이 향상되었습니다. **/std:c++latest**가 필요합니다.

### <a name="designated-initialization"></a>지정된 초기화

[P0329R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf)(C++20) 지정된 초기화를 통해 `Type t { .member = expr }` 구문을 사용하여 지정된 멤버를 집계 초기화에서 선택할 수 있습니다. **/std:c++latest**가 필요합니다.

### <a name="new-and-updated-standard-library-functions-c20"></a>신규 및 업데이트된 표준 라이브러리 함수(C++20)

- `basic_string` 및 `basic_string_view`에 대한 `starts_with()` 및 `ends_with()`.
- 연관 컨테이너에 대한 `contains()`.
- `list` 및 `forward_list`에 대한 `remove()`, `remove_if()` 및 `unique()`가 이제 `size_type`을 반환합니다.
- `shift_left()` 및 `shift_right()`가 \<algorithm>에 추가되었습니다.


## <a name="improvements_162"></a> 16.2의 규칙 향상

### <a name="noexcept-constexpr-functions"></a>noexcept constexpr 함수

constexpr 함수는 상수 식에서 사용될 때 더 이상 기본적으로 **noexcept**로 고려되지 않습니다. 이 동작 변경은 [CWG 1351](http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_defects.html#1351) 문제의 해결로 인한 것이며, [/permissive-](../build/reference/permissive-standards-conformance.md)에서 사용 설정됩니다. 다음 예제는 Visual Studio 2019 버전 16.1 이전 버전에서 컴파일되지만 Visual Studio 2019 버전 16.2에서 C2338을 생성합니다.

```cpp
constexpr int f() { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept"); // C2338 in 16.2
}
```

오류를 해결하려면 함수 선언에 **noexcept** 식을 추가합니다.

```cpp
constexpr int f() noexcept { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept");
}
```

### <a name="binary-expressions-with-different-enum-types"></a>열거형 형식이 다른 이진 식

하나는 열거형 형식이고 다른 하나는 다른 열거형 형식이거나 부동 소수점 형식인 피연산자에 일반적인 산술 변환을 적용하는 기능은 C++20에서 더 이상 사용되지 않습니다([P1120R0](https://wg21.link/p1120r0)). Visual Studio 2019 버전 16.2 이상에서 [/std:c++latest](../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션을 사용하는 경우 다음 코드는 수준 4 경고를 생성합니다.

```cpp
enum E1 { a };
enum E2 { b };
int main() {
    int i = a | b; // warning C5054: operator '|': deprecated between enumerations of different types
}
```

이 경고를 방지하려면 [static_cast](../cpp/static-cast-operator.md)를 사용하여 두 번째 피연산자를 변환합니다.

```cpp
enum E1 { a };
enum E2 { b };
int main() {
  int i = a | static_cast<int>(b);
}
```

### <a name="binary-expressions-with-enumeration-and-floating-point-types"></a>열거형 및 부동 소수점 형식을 사용하는 이진 식

하나는 열거형 형식이고 다른 하나는 다른 열거형 형식이거나 부동 소수점 형식인 피연산자에 일반적인 산술 변환을 적용하는 기능은 C++20에서 더 이상 사용되지 않습니다([P1120R0](https://wg21.link/p1120r0)). 즉, 열거형과 부동 소수점 형식 간에 이진 연산을 사용하면 [/std:c++latest](../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션이 사용 설정된 경우 경고가 발생합니다.

```cpp
enum E1 { a };
int main() {
  double i = a * 1.1;
}
```

이 경고를 방지하려면 [static_cast](../cpp/static-cast-operator.md)를 사용하여 두 번째 피연산자를 변환합니다.

```cpp
enum E1 { a };
int main() {
   double i = static_cast<int>(a) * 1.1;
}
```

### <a name="equality-and-relational-comparisons-of-arrays"></a>배열의 같음 및 관계 비교

배열 형식의 두 피연산자 간 같음 및 관계 비교는 C++20에서 사용되지 않습니다([P1120R0](https://wg21.link/p1120r0)). 즉, 두 배열 간의 비교 연산(순위 및 범위 유사성과 관계없이)을 사용하면 경고가 발생합니다. Visual Studio 2019 버전 16.2부터 [/std:c++latest](../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션이 사용 설정된 경우 다음 코드는 *C5056: operator '==': deprecated for array types*를 생성합니다.

```cpp
int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 1, 2, 3 };
    if (a == b) { return 1; }
}
```

이 경고를 방지하기 위해 첫 번째 요소의 주소를 비교할 수 있습니다.

```cpp
int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 1, 2, 3 };
    if (&a[0] == &b[0]) { return 1; }
}
```

두 배열의 콘텐츠가 동일한지 여부를 확인하려면 [std::equal](../standard-library/algorithm-functions.md#equal) 함수를 사용합니다.

```cpp
std::equal(std::begin(a), std::end(a), std::begin(b), std::end(b));
```

### <a name="effect-of-defining-spaceship-operator-on--and-"></a>우주선 연산자 정의가 == 및 !=에 미치는 영향

우주선 연산자가 `= default`로 표시되지 않는 한 우주선 연산자 정의( **<=>** )만으로는 더 이상 **==** 또는 **!=** 을 포함하는 식을 다시 생성하지 않습니다([P1185R2](https://wg21.link/p1185r2)). 다음 예제는 Visual Studio 2019 RTW 및 버전 16.1에서 컴파일되지만 Visual Studio 2019 버전 16.2에서 C2678을 생성합니다.

```cpp
#include <compare>

struct S {
  int a;
  auto operator<=>(const S& rhs) const {
    return a <=> rhs.a;
  }
};
bool eq(const S& lhs, const S& rhs) {
  return lhs == rhs;
}
bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

이 오류를 방지하려면 == 연산자를 정의하거나 기본값으로 선언합니다.

```cpp
#include <compare>

struct S {
  int a;
  auto operator<=>(const S& rhs) const {
    return a <=> rhs.a;
  }
  bool operator==(const S&) const = default;
};
bool eq(const S& lhs, const S& rhs) {
  return lhs == rhs;
}
bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

### <a name="standard-library-improvements"></a>표준 라이브러리 향상

- 고정/지수 전체 자릿수를 가진 \<charconv> `to_chars()`. (버전 16.4에서는 일반 전체 자릿수를 사용할 계획입니다.)
- [P0020R6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0020r6.html): atomic\<float>, atomic\<double>, atomic\<long double>
- [P0463R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0463r1.html): endian
- [P0482R6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html): char8_t에 대한 라이브러리 지원
- [P0600R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0600r1.pdf): STL, 파트 1에 대한 [\[nodiscard]]
- [P0653R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0653r2.html): to_address()
- [P0754R2](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0754r2.pdf): \<version>
- [P0771R1](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0771r1.pdf): std::function의 이동 생성자에 대한 noexcept

## <a name="improvements_163"></a> Visual Studio 2019 버전 16.3의 규칙 향상

### <a name="stream-extraction-operators-for-char-removed"></a>Char*의 스트림 추출 연산자가 제거됨

포인터와 문자 간에 대한 스트림 추출 연산자가 제거되고 문자 배열에 대한 추출 연산자로 바뀌었습니다([P0487R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0487r1.html)에 따라). WG21은 제거된 오버로드를 안전하지 않은 것으로 간주합니다. [/std:c++latest](../build/reference/std-specify-language-standard-version.md) 모드에서 다음 예제는 이제 *C2679: binary '>>': 'char\*' 형식의 오른쪽 피연산자를 사용하는 연산자를 찾을 수 없음(또는 허용되는 변환이 없음)* 을 생성합니다.

```cpp
   char x[42];
   char* p = x;
   std::cin >> std::setw(42);
   std::cin >> p;
```

오류를 방지하려면 char[] 변수와 함께 추출 연산자를 사용합니다.

```cpp
char x[42];
std::cin >> x;
```

### <a name="new-keywords-requires-and-concept"></a>새 키워드 **requires** 및 **concept**

새 키워드 **requires** 및 **concept**가 Microsoft C++ 컴파일러에 추가되었습니다. [/std:c++latest](../build/reference/std-specify-language-standard-version.md) 모드에서 두 키워드 중 하나를 식별자로 사용하려고 하면 컴파일러는 *C2059: 구문 오류*를 발생시킵니다.

### <a name="constructors-as-type-names-disallowed"></a>생성자를 형식 이름으로 사용할 수 없음

생성자 이름이 클래스 템플릿 특수화에 대한 별칭 뒤의 정규화된 이름에 표시되는 경우에는 더 이상 삽입된 클래스 이름으로 간주하지 않습니다. 이전에는 생성자를 형식 이름으로 사용하여 다른 엔터티를 선언할 수 있었습니다. 다음 예제에서는 *C3646: ‘TotalDuration’: 알 수 없는 재정의 지정자*를 생성합니다.

```cpp
#include <chrono>

class Foo {
   std::chrono::milliseconds::duration TotalDuration{};
};

```

오류를 방지하려면 다음과 같이 `TotalDuration`을 선언합니다.

```cpp
#include <chrono>

class Foo {
  std::chrono::milliseconds TotalDuration {};
};
```

### <a name="stricter-checking-of-extern-c-functions"></a>Extern “C” 함수에 대해 더 엄격해진 검사

**extern "C"** 함수가 다른 네임스페이스에서 선언된 경우 이전 버전의 Microsoft C++ 컴파일러는 선언이 호환되는지 여부를 확인하지 않았습니다. Visual Studio 2019 버전 16.3에서는 컴파일러가 이러한 검사를 수행합니다. [/permissive-](../build/reference/permissive-standards-conformance.md) 모드에서 다음 코드는 *C2371 : 재정의; 다른 기본 형식* 및 *C2733 C 링크로 함수를 오버로드할 수 없음*을 생성합니다.

```cpp
using BOOL = int;

namespace N
{
   extern "C" void f(int, int, int, bool);
}

void g()
{
   N::f(0, 1, 2, false);
}

extern "C" void f(int, int, int, BOOL){}
```

앞의 예제에서 오류를 방지하려면 두 `f` 선언 모두에서 일관적으로 **BOOL** 대신 **bool**을 사용합니다.

### <a name="standard-library-improvements"></a>표준 라이브러리 향상

비표준 헤더 \<stdexcpt.h> 및 \<typeinfo.h>가 제거되었습니다. 이러한 비표준 헤더를 포함하는 코드는 대신 표준 헤더 \<exception> 및 \<typeinfo>를 각각 포함해야 합니다.

## <a name="improvements_164"></a> Visual Studio 2019 버전 16.4의 규칙 개선

### <a name="better-enforcement-of-two-phase-name-lookup-for-qualified-ids-in-permissive-"></a>한층 개선된 /permissive-에서의 정규화된 ID에 대한 2단계 이름 조회

2단계 이름 조회를 위해서는 템플릿 본문에 사용된 종속되지 않은 이름이 정의 시점에 템플릿에 표시될 수 있어야 합니다. 이전에는 템플릿이 인스턴스화될 때 이러한 이름이 발견되었을 수 있습니다. 이번 변경을 통해 MSVC에서 이식 가능하고 규칙에 맞는 코드를 [/permissive-](../build/reference/permissive-standards-conformance.md) 플래그 아래에서 더 쉽게 작성할 수 있습니다.

**/permissive-** 플래그 집합이 설정된 Visual Studio 2019 버전 16.4의 다음 예에서는 `f<T>` 템플릿이 정의될 때 `N::f`이(가) 표시되지 않기 때문에 오류가 생성됩니다.

```cpp
template <class T>
int f() {
    return N::f() + T{}; // error C2039: 'f': is not a member of 'N'
}

namespace N {
    int f() { return 42; }
}
```

일반적으로 이 오류는 다음 예와 같이 누락된 헤더나 전달 선언 함수 또는 변수를 포함하여 해결할 수 있습니다.

```cpp
namespace N {
    int f();
}

template <class T>
int f() {
    return N::f() + T{};
}

namespace N {
    int f() { return 42; }
}
```

### <a name="implicit-conversion-of-integral-constant-expressions-to-null-pointer"></a>정수 계열 상수 식에서 Null 포인터로의 암시적 변환

MSVC 컴파일러는 이제 규칙 모드(/permissive-)에서 [CWG 이슈 903](http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_defects.html#903)을 구현합니다. 이 규칙은 정수 계열 상수 식에서 Null 포인터 상수로의 암시적 변환(정수 리터럴 '0'은 제외)을 허용하지 않습니다. 다음 예에서는 규칙 모드에서 C2440을 생성합니다.

```cpp
int* f(bool* p) {
    p = false; // error C2440: '=': cannot convert from 'bool' to 'bool *'
    p = 0; // OK
    return false; // error C2440: 'return': cannot convert from 'bool' to 'int *'
}
```

오류를 해결하려면 **false** 대신 **nullptr**을 사용합니다. 리터럴 0은 다음과 같이 계속 허용됩니다.

```cpp
int* f(bool* p) {
    p = nullptr; // OK
    p = 0; // OK
    return nullptr; // OK
}
```

### <a name="standard-rules-for-types-of-integer-literals"></a>정수 리터럴 형식에 대한 표준 규칙

규칙 모드([/permissive-](../build/reference/permissive-standards-conformance.md)로 사용)에서는 MSVC에 정수 리터럴 형식에 대한 표준 규칙이 사용됩니다. 이전에는 너무 커서 부호 있는 'int'에 맞지 않는 10진 리터럴에는 'unsigned int' 형식이 제공되었습니다. 이제 이러한 리터럴에는 두 번째로 큰 부호 있는 정수 형식 'long long'이 제공됩니다. 또한 너무 커서 부호 있는 형식에 맞지 않는 'll' 접미사가 포함된 리터럴에는 'unsigned long long' 형식이 제공됩니다.

이로 인해 다른 경고 진단이 생성될 수 있으며 리터럴에 대해 수행되는 산술 연산에 대한 동작이 달라질 수 있습니다.

다음 예에서는 Visual Studio 2019, 버전 16.4의 새 동작을 보여줍니다. `i` 변수는 **unsigned int** 형식이므로 경고가 발생합니다. 변수 `j`의 상위 비트는 0으로 설정됩니다.

```cpp
void f(int r) {
    int i = 2964557531; // warning C4309: truncation of constant value
    long long j = 0x8000000000000000ll >> r; // literal is now unsigned, shift will fill high-order bits with 0
}
```

다음 예에서는 이전 동작을 유지하여 경고 및 런타임 동작이 변경되지 않도록 하는 방법을 보여줍니다.

```cpp
void f(int r) {
int i = 2964557531u; // OK
long long j = (long long)0x8000000000000000ll >> r; // shift will keep high-order bits
}
```

### <a name="function-parameters-that-shadow-template-parameters"></a>템플릿 매개 변수를 숨기는 함수 매개 변수

MSVC 컴파일러는 이제 함수 매개 변수가 다음 템플릿 매개 변수를 숨기는 경우 오류를 표시합니다.

```cpp
template<typename T>
void f(T* buffer, int size, int& size_read);

template<typename T, int Size>
void f(T(&buffer)[Size], int& Size) // error C7576: declaration of 'Size' shadows a template parameter
{
    return f(buffer, Size, Size);
}
```

오류를 해결하려면 다음 매개 변수 중 하나의 이름을 변경합니다.

```cpp
template<typename T>
void f(T* buffer, int size, int& size_read);

template<typename T, int Size>
void f(T (&buffer)[Size], int& size_read)
{
    return f(buffer, Size, size_read);
}
```

### <a name="user-provided-specializations-of-type-traits"></a>형식 특성의 사용자 제공 특수화

표준의 *meta.rqmts* 하위 절에 따라 MSVC 컴파일러는 이제 `std` 네임스페이스에서 지정된 type_traits 템플릿 중 하나의 사용자 정의 특수화를 발견하면 오류를 표시합니다. 달리 지정하지 않은 경우 이러한 특수화로 인해 정의되지 않은 동작이 발생됩니다. 다음 예에서는 정의되지 않은 동작이 규칙을 위반하여 `static_assert`이(가) **C2338** 오류로 인해 실패합니다.

```cpp
#include <type_traits>
struct S;

template<>
struct std::is_fundamental<S> : std::true_type {};

static_assert(std::is_fundamental<S>::value, "fail");
```

이 오류를 방지하려면 원하는 type_trait에서 상속하는 구조체를 정의하고 다음을 특수화합니다.

```cpp
#include <type_traits>

struct S;

template<typename T>
struct my_is_fundamental : std::is_fundamental<T> {};

template<>
struct my_is_fundamental<S> : std::true_type { };

static_assert(my_is_fundamental<S>::value, "fail");
```

### <a name="changes-to-compiler-provided-comparison-operators"></a>컴파일러에서 제공되는 비교 연산자에 대한 변경 내용

MSVC 컴파일러는 이제 [/std:c++latest](../build/reference/std-specify-language-standard-version.md) 옵션이 설정되어 있는 경우 [P1630R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1630r1.html)에 따라 비교 연산자에 대해 다음과 같은 변경 내용을 구현합니다.

**bool**이 아닌 반환 형식이 포함된 경우 컴파일러는 더 이상 `operator==`이(가) 포함된 식을 다시 쓰지 않습니다. 다음 코드는 *error C2088: '!=': illegal for struct*를 생성합니다.

```cpp
struct U {
  operator bool() const;
};

struct S {
  U operator==(const S&) const;
};

bool neq(const S& lhs, const S& rhs) {
  return lhs != rhs;
}
```

이 오류를 방지하려면 다음과 같이 필요한 연산자를 명시적으로 정의해야 합니다.

```cpp
struct U {
    operator bool() const;
};

struct S {
    U operator==(const S&) const;
    U operator!=(const S&) const;
};

bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

컴파일러가 공용 구조체와 같은 클래스의 구성원인 경우 더 이상 기본 비교 연산자를 정의하지 않습니다. 다음 예에서는 이제 *C2120: 'void' illegal with all types*가 생성됩니다.

```cpp
#include <compare>

union S {
    int a;
    char b;
    auto operator<=>(const S&) const = default;
};

bool lt(const S& lhs, const S& rhs) {
    return lhs < rhs;
}
```

이 오류를 방지하려면 다음 연산자에 대한 본문을 정의합니다.

```cpp
#include <compare>

union S {
  int a;
  char b;
  auto operator<=>(const S&) const { ... }
}; 

bool lt(const S& lhs, const S& rhs) {
  return lhs < rhs;
}
```

컴파일러는 클래스에 참조 구성원이 포함된 경우 더 이상 기본 비교 연산자를 정의하지 않습니다. 다음과 같은 코드를 입력하면 이제 *error C2120: 'void' illegal with all types*가 생성됩니다.

```cpp
#include <compare>

struct U {
    int& a;
    auto operator<=>(const U&) const = default;
};

bool lt(const U& lhs, const U& rhs) {
    return lhs < rhs;
}
```

이 오류를 방지하려면 다음 연산자에 대한 본문을 정의합니다.

```cpp
#include <compare>

struct U {
    int& a;
    auto operator<=>(const U&) const { ... };
};

bool lt(const U& lhs, const U& rhs) {
    return lhs < rhs;
}
```

## <a name="update_160"></a> Visual Studio 2019의 버그 수정 및 동작 변경

### <a name="reinterpret_cast-in-a-constexpr-function"></a>constexpr 함수의 reinterpret_cast

**reinterpret_cast**는 **constexpr** 함수에서 사용할 수 없습니다. Microsoft C++ 컴파일러는 이전에 **constexpr** 컨텍스트에서 사용되는 경우에만 **reinterpret_cast**를 거부했습니다. Visual Studio 2019에서는 모든 언어 표준 모드에서 컴파일러가 **constexpr** 함수의 정의에서 **reinterpret_cast**를 정확히 진단합니다. 이제 다음 코드는 *C3615: constexpr 함수 ‘f’는 상수 식이 될 수 없음*을 생성합니다.

```cpp
long long i = 0;
constexpr void f() {
    int* a = reinterpret_cast<int*>(i);
}
```

오류를 방지하려면 함수 선언에서 **constexpr** 한정자를 제거합니다.

### <a name="correct-diagnostics-for-basic_string-range-constructor"></a>Basic_string 범위 생성자에 대한 올바른 진단

Visual Studio 2019에서 `basic_string` 범위 생성자는 더 이상 `static_cast`를 사용하여 컴파일러 진단을 표시하지 않습니다. 다음 코드는 `out`을 초기화할 때 `wchar_t`에서 **char**로 데이터가 손실될 수 있음에도 불구하고 Visual Studio 2017에서 경고 없이 컴파일됩니다.

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end());
```

Visual Studio 2019에서 *C4244: 'argument': 데이터 손실이 가능한 'wchar_t'에서 'const _Elem'으로 변환*이 발생합니다. 경고를 방지하려면 다음 예제와 같이 std::string을 초기화할 수 있습니다.

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>/clr 또는 /ZW 아래에 += 및 -=에 대한 잘못된 호출 이제 올바르게 검색됩니다.

Visual Studio 2017에서는 컴파일러가 자동으로 오류를 무시하고 `/clr` 또는 `/ZW` 아래의 잘못된 += 및 -= 호출에 대한 코드를 생성하지 않는 버그가 도입되었습니다. 다음 코드는 Visual Studio 2017에서 오류 없이 컴파일되지만 Visual Studio 2019에서는 *오류 C2845: 'System::string ^': 이 형식에서는 포인터 산술이 허용되지 않음*을 올바르게 발생시킵니다.

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // C2845 in VS2019
}
```

이 예제에서 오류를 방지하려면 ToString() 메서드(`s += E::e.ToString();`)와 함께 연산자를 사용합니다.

### <a name="initializers-for-inline-static-data-members"></a>인라인 정적 데이터 멤버에 대한 이니셜라이저

이제 **인라인** 및 **정적 constexpr** 이니셜라이저 내에서 잘못된 멤버 액세스가 올바르게 검색됩니다. 다음 예제에서는 Visual Studio 2017에서 오류 없이 컴파일되지만 `/std:c++17` 모드 아래에 Visual Studio 2019에서는 *오류 C2248: 'X' 클래스에 선언된 프라이빗 멤버에 액세스할 수 없음*을 발생시킵니다.

```cpp
struct X
{
    private:
        static inline const int c = 1000;
};

struct Y : X
{
    static inline int d = c; // C2248 in Visual Studio 2019
};
```

오류를 방지하려면 `X::c` 멤버를 보호됨으로 선언합니다.

```cpp
struct X
{
    protected:
        static inline const int c = 1000;
};
```

### <a name="c4800-reinstated"></a>C4800 복원

MSVC에서는 **bool**로의 암시적 변환에 대해 성능 경고 C4800을 사용했습니다. 이 경고는 너무 번거롭고 표시되지 않도록 설정할 수 없어 Visual Studio 2017에서 제거되었습니다. 그러나 Visual Studio 2017의 수명 주기 동안 이 경고를 통해 해결되었던 유용한 사례에 대한 많은 피드백을 받았습니다. Visual Studio 2019에서는 설명을 포함하는 C4165와 함께 신중하게 조정된 C4800이 다시 추가되었습니다. 두 경고는 명시적 캐스트 또는 적절한 형식의 0 비교를 사용하여 표시되지 않도록 쉽게 설정할 수 있습니다. C4800은 off-by-default 수준 4 경고이고 C4165는 off-by-default 수준 3 경고입니다. 둘 다 `/Wall` 컴파일러 옵션을 사용하여 검색할 수 있습니다.

다음 예제에서는 `/Wall`에서 C4800 및 C4165를 발생시킵니다.

```cpp
bool test(IUnknown* p)
{
    bool valid = p; // warning C4800: Implicit conversion from 'IUnknown*' to bool. Possible information loss
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return hr; // warning C4165: 'HRESULT' is being converted to 'bool'; are you sure this is what you want?
}
```

이전 예제에서 경고를 방지하려면 다음과 같은 코드를 작성하면 됩니다.

```cpp
bool test(IUnknown* p)
{
    bool valid = p != nullptr; // OK
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return SUCCEEDED(hr);  // OK
}
```

### <a name="local-class-member-function-doesnt-have-a-body"></a>로컬 클래스 멤버 함수에 본문이 없습니다.

Visual Studio 2017에서 *C4822: 로컬 클래스 멤버 함수에 본문이 없음*은 컴파일러 옵션 `/w14822`가 명시적으로 설정된 경우에만 발생합니다. `/Wall`에는 표시되지 않습니다. Visual Studio 2019에서 C4822는 `/w14822`를 명시적으로 설정하지 않고도 `/Wall`에서 검색할 수 있도록 하는 off-by-default 경고입니다.

```cpp
void example()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-constexpr-if-statements"></a>constexpr if 문을 포함하는 함수 템플릿 본문

**if constexpr** 문을 포함하는 템플릿 함수 본문에 일부 [/permissive-](../build/reference/permissive-standards-conformance.md) 구문 분석 관련 검사가 활성화되어 있습니다. 예를 들어 Visual Studio 2017에서 다음 코드는 *C7510: ‘Type’: 종속 형식 이름을 사용하는 경우 ‘typename’으로 시작해야 합니다.* 를 생성합니다. 단, **/permissive-** 옵션이 설정되지 않은 경우에만 해당합니다. Visual Studio 2019에서는 **/permissive-** 옵션이 설정된 경우에도 동일한 코드에서 오류가 발생합니다.

```cpp
template <typename T>

int f()
{
    T::Type a; // error C7510

    if constexpr (T::val)
    {
        return 1;
    }
    else
    {
        return 2;
    }
}

struct X
{
    using Type = X;
    constexpr static int val = 1;
};

int main()
{
    return f<X>();
}
```

이 오류를 방지하려면 `a` 선언 **typename** 키워드를 추가합니다.`typename T::Type a;`

### <a name="inline-assembly-code-isnt-supported-in-a-lambda-expression"></a>인라인 어셈블리 코드는 람다 식에서 지원되지 않음

Microsoft C++ 팀은 최근 람다 내에서 인라인 어셈블러를 사용하면 런타임 시 `ebp`(반환 주소 레지스터)가 손상될 수 있는 보안 문제를 인식하게 되었습니다. 악의적인 공격자가 이 시나리오를 활용할 수 있었습니다. 이 문제의 특성, 인라인 어셈블러가 x86에서만 지원된다는 팩트, 인라인 어셈블러와 다른 컴파일러 부분 간의 상호 작용 부족 등을 고려할 때, 이 문제의 가장 안전한 솔루션은 람다 식 내에서 인라인 어셈블러를 허용하지 않는 것이었습니다.

발견된 ‘실제’ 사례에서 인라인 어셈블러가 람다 식 내에서 사용되는 유일한 목적은 반환 주소를 캡처하기 위한 것이었습니다. 이 시나리오에서는 컴파일러 고유의 `_ReturnAddress()`를 사용하여 모든 플랫폼에서 반환 주소를 캡처할 수 있습니다.

다음 코드는 Visual Studio 2017 15.9 및 Visual Studio 2019에서 *C7552: 인라인 어셈블러는 람다에서 지원되지 않음*을 생성합니다.

```cpp
#include <cstdio>

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;

    auto lambda = [&]
    {
        __asm {

            mov eax, x
            mov y, eax
        }
    };

    lambda();
    return y;
}
```

오류를 방지하려면 다음 예제와 같이 어셈블리 코드를 명명된 함수로 이동합니다.

```cpp
#include <cstdio>

void g(int& x, int& y)
{
    __asm {
        mov eax, x
        mov y, eax
    }
}

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;
    auto lambda = [&]
    {
        g(x, y);
    };
    lambda();
    return y;
}

int main()
{
    std::printf("%d\n", f());
}
```

### <a name="iterator-debugging-and-stdmove_iterator"></a>반복기 디버깅 및 `std::move_iterator`

반복기 디버깅 기능이 `std::move_iterator`를 적절하게 래핑 해제하도록 학습되었습니다. 예를 들어 `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)`는 이제 `memcpy` 빠른 경로에 참여할 수 있습니다.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>\<xkeycheck.h> 키워드 적용 수정

키워드 적용 \<xkeycheck.h>를 대체하는 표준 라이브러리의 매크로가 일반 메시지 대신 검색된 실제 문제 키워드를 내보내도록 수정되었습니다. 또한 C++20 키워드를 지원하고 IntelliSense를 속여 임의의 키워드를 매크로로 가리키는 것을 방지합니다.

### <a name="allocator-types-no-longer-deprecated"></a>더 이상 사용되지 않는 할당자 형식

`std::allocator<void>`, `std::allocator::size_type`, `std::allocator::difference_type`은 더 이상 사용되지 않습니다.

### <a name="correct-warning-for-narrowing-string-conversions"></a>문자열 변환을 좁히기 위한 올바른 경고

표준에서 요청되지 않았으며, C4244 축소 경고가 표시되지 않도록 하는 의사 `static_cast`가 `std::string`에서 제거되었습니다. 이제 `std::string::string(const wchar_t*, const wchar_t*)`를 호출하려고 하면 *C4244 "wchar_t를 char로 축소합니다."* 를 적절히 내보냅니다.

### <a name="various-filesystem-correctness-fixes"></a>다양한 \<filesystem> 정확성 수정

- 디렉터리의 마지막 쓰기 시간을 변경하려고 할 때 `std::filesystem::last_write_time` 오류가 수정되었습니다.
- 존재하지 않는 대상 경로를 제공할 때 `std::filesystem::directory_entry` 생성자는 이제 예외를 throw하는 대신 실패한 결과를 저장합니다.
- `existing_p`가 symlink인 경우 기본 `CreateDirectoryExW` 함수가 `copy_symlink`를 사용하므로 `std::filesystem::create_directory` 2-매개 변수 버전이 1-매개 변수 버전을 호출하도록 변경되었습니다.
- 손상된 symlink가 발견될 때 `std::filesystem::directory_iterator`에서 더 이상 오류가 발생하지 않습니다.
- `std::filesystem::space`는 이제 상대 경로를 허용합니다.
- `std::filesystem::path::lexically_relative`는 [LWG 3096](https://cplusplus.github.io/LWG/issue3096)으로 보고된 후행 슬래시로 더 이상 혼동하지 않습니다.
- `std::filesystem::create_symlink`에서 슬래시가 있는 경로를 거부하는 `CreateSymbolicLinkW`를 해결했습니다.
- Windows 10 LTSB 1609에 존재하지만 실제로 파일을 삭제할 수 없는 POSIX 삭제 모드 `delete` 함수가 해결되었습니다.
- `std::boyer_moore_searcher` 및 `std::boyer_moore_horspool_searcher`의 복사 생성자 및 복사 할당 연산자는 이제 실제로 항목을 복사합니다.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Windows 8 이상의 병렬 알고리즘

병렬 알고리즘 라이브러리는 이제 Windows 7 및 이전 가짜 버전을 항상 사용하는 대신 Windows 8 이상에서 실제 `WaitOnAddress` 제품군을 올바르게 사용합니다.

### <a name="stdsystem_categorymessage-whitespace"></a>`std::system_category::message()` 공백

`std::system_category::message()`는 이제 반환된 메시지에서 후행 공백을 삭제합니다.

### <a name="stdlinear_congruential_engine-divide-by-zero"></a>`std::linear_congruential_engine` 0으로 나누기

`std::linear_congruential_engine`이 0으로 나누도록 트리거하는 일부 조건이 수정되었습니다.

### <a name="fixes-for-iterator-unwrapping"></a>반복기 래핑 해제를 위한 수정

C++ 팀 블로그 문서 [STL Features and Fixes in VS 2017 15.8](https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/)(VS 2017 15.8의 STL 기능 및 수정 사항)에 설명된 대로 Visual Studio 2017 15.8에서 프로그래머와 사용자 통합을 위해 처음 공개된 반복기 래핑 해제 동작은 표준 라이브러리 반복기에서 파생된 반복기를 더 이상 래핑 해제하지 않습니다. 예를 들어 `std::vector<int>::iterator`에서 파생되고 동작을 사용자 지정하려는 사용자는 이제 포인터의 동작 대신 표준 라이브러리 알고리즘을 호출할 때 사용자 지정된 동작을 가져옵니다.

순서가 지정되지 않은 컨테이너 `reserve` 함수가 이제 [LWG 2156](https://cplusplus.github.io/LWG/issue2156)에 설명된 대로 N개 요소를 실제로 예약합니다.

### <a name="time-handling"></a>시간 처리

- 이전에는 동시성 라이브러리에 전달된 일부 시간 값이 오버플로되었습니다(예: `condition_variable::wait_for(seconds::max())`). 현재 수정된 이 오버플로는 임의의 29일 주기로 동작을 변경했습니다(기본 Win32 API에서 허용된 uint32_t 밀리초가 오버플로된 경우).

- 이제 \<ctime> 헤더가 전역 네임스페이스에서 선언하는 것 외에 `std` 네임스페이스에서도 `timespec` 및 `timespec_get`을(를) 올바르게 선언합니다.

### <a name="various-fixes-for-containers"></a>컨테이너에 대한 다양한 수정

- 향상된 IntelliSense 환경을 위해 프라이빗으로 설정된 표준 라이브러리 내부 컨테이너 함수가 많습니다. 이후 MSVC 릴리스에서는 멤버를 프라이빗으로 표시하기 위한 추가 수정이 예상됩니다.

- `list`, `map` 및 `unordered_map`과 같은 노드 기반 컨테이너가 손상되는 예외 안전 정확성 문제가 해결되었습니다. `propagate_on_container_copy_assignment` 또는 `propagate_on_container_move_assignment` 재할당 작업 중에 컨테이너의 sentinel 노드를 이전 할당자로 해제하고 이전 할당자를 통해 POCCA/POCMA 할당을 수행한 다음, 새 할당자에서 sentinel 노드를 가져오려고 시도합니다. 이 할당에 실패하면 컨테이너가 손상되었지만, sentinel 노드 소유가 고정된 하드 데이터 구조이기 때문에 컨테이너를 제거할 수도 없었습니다. 이 코드가 기존 sentinel 노드를 제거하기 전에 소스 컨테이너의 할당자에서 새 sentinel 노드를 할당하도록 수정되었습니다.

- 컨테이너는 `is_always_equal`로 선언된 할당자에 대해서도 `propagate_on_container_copy_assignment`, `propagate_on_container_move_assignment` 및 `propagate_on_container_swap`에 따라 할당자를 항상 복사/이동/스왑하도록 수정되었습니다.

- [P0083 "맵 및 집합 스플라이스"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)에 따라 rvalue 컨테이너를 허용하는 컨테이너 병합 및 추출 멤버 함수에 대한 오버로드 추가

### <a name="stdbasic_istreamread-processing-of-rn--n"></a>\\r\\n => \\n의 `std::basic_istream::read` 처리

`std::basic_istream::read`가 \\r\\n => \\n 처리 과정에서 일시적으로 제공된 버퍼 파트에 쓰지 않도록 수정되었습니다. 이 변경으로 인해 Visual Studio 2017 15.8에서 4K보다 큰 읽기에 대해 얻은 성능 향상이 일부 손실됩니다. 하지만 문자당 3회의 가상 호출 방지를 통한 효율성 향상은 유지됩니다.

### <a name="stdbitset-constructor"></a>`std::bitset` 생성자

`std::bitset` 생성자는 큰 비트 세트에 대해 더 이상 1과 0을 역순으로 읽지 않습니다.

### <a name="stdpairoperator-regression"></a>`std::pair::operator=` 재발

[LWG 2729 "Missing SFINAE on std::pair::operator=";](https://cplusplus.github.io/LWG/issue2729)를 구현할 때 도입된 `std::pair`의 할당 연산자의 회귀가 수정되었습니다. 이제 `std::pair`로 변환할 수 있는 형식을 다시 올바르게 허용합니다.

### <a name="non-deduced-contexts-for-add_const_t"></a>`add_const_t`에 대해 추론되지 않은 컨텍스트

`add_const_t` 및 관련 함수가 추론되지 않은 컨텍스트로 간주되는 부 형식 특성 버그를 수정했습니다. 즉, `add_const_t`는 `const T`가 아니라 `typename add_const<T>::type`의 별칭이어야 합니다.

## <a name="update_162"></a> 16.2의 버그 수정 및 동작 변경

### <a name="const-comparators-for-associative-containers"></a>연관 컨테이너에 대한 Const 비교 연산자

코드 크기 축소를 위해 [set](../standard-library/set-class.md), [map](../standard-library/map-class.md), [multiset](../standard-library/multiset-class.md) 및 [multimap](../standard-library/multimap-class.md)에 검색 및 삽입을 위한 코드가 병합되었습니다. 이제 삽입 작업은 검색 작업이 이전에 수행한 것과 동일한 방식으로 **const** 비교 함수에서 보다 작음 비교를 호출합니다. 다음 코드는 Visual Studio 2019 버전 16.1 이전 버전에서 컴파일되지만 Visual Studio 2019 버전 16.2에서 C3848을 생성합니다.

```cpp
#include <iostream>
#include <map>

using namespace std;

struct K
{
   int a;
   string b = "label";
};

struct Comparer  {
   bool operator() (K a, K b) {
      return a.a < b.a;
   }
};

map<K, double, Comparer> m;

K const s1{1};
K const s2{2};
K const s3{3};

int main() {

   m.emplace(s1, 1.08);
   m.emplace(s2, 3.14);
   m.emplace(s3, 5.21);

}
```

오류를 방지하려면 비교 연산자 **const**를 설정합니다.

```cpp
struct Comparer  {
   bool operator() (K a, K b) const {
      return a.a < b.a;
   }
};

```

::: moniker-end

::: moniker range="vs-2017"

## <a name="improvements_150"></a> Visual Studio 2017 RTW(버전 15.0)의 규칙 향상

집계를 위한 일반화된 **constexpr** 및 NSDMI(비정적 데이터 멤버 초기화) 지원이 추가되면서, 이제 Visual Studio 2017의 Microsoft C++ 컴파일러는 C++14 표준에 추가된 기능을 완벽하게 갖췄습니다. 하지만 C++11 및 C++98 표준의 몇 가지 기능은 아직 컴파일러에 구현되지 않았습니다. 컴파일러의 현재 상태를 보여 주는 테이블은 [Microsoft C++ 언어 규칙 테이블](../visual-cpp-language-conformance.md)을 참조하세요.

### <a name="c11-expression-sfinae-support-in-more-libraries"></a>C++11: 더 많은 라이브러리의 SFINAE 식 지원

Visual C++ 컴파일러는 **decltype** 및 **constexpr** 식이 템플릿 매개 변수로 나타날 수 있는 템플릿 인수 감소 및 대체에 필요한 SFINAE 식에 대한 지원을 계속 개선하고 있습니다. 자세한 내용은 [Expression SFINAE improvements in Visual Studio 2017 RC](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3)(Visual Studio 2017 RC의 SFINAE 식 향상)를 참조하세요.

### <a name="c14-nsdmi-for-aggregates"></a>C++14: 집계용 NSDMI

집계는 사용자 제공 생성자가 없고, 개인 또는 보호된 비정적 데이터 멤버가 없고, 기본 클래스가 없고, 가상 함수가 없는 배열 또는 클래스입니다. C++14부터 집계에 멤버 이니셜라이저가 포함될 수 있습니다. 자세한 내용은 [Member initializers and aggregates](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html)(멤버 이니셜라이저 및 집계)를 참조하세요.

### <a name="c14-extended-constexpr"></a>C++14: 확장된 **constexpr**

**constexpr**로 선언된 식은 이제 특정 종류의 선언, if 및 switch 문, loop 문 및 수명이 constexpr 식 계산 내에서 시작된 개체의 변형을 포함할 수 있습니다. 또한 더 이상 **constexpr** 비정적 멤버 함수가 암시적으로 **const**가 될 필요가 없습니다. 자세한 내용은 [Relaxing constraints on constexpr functions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)(constexpr 함수에 대한 제약 조건 완화)를 참조하세요.

### <a name="c17-terse-static_assert"></a>C++17: 간결한 `static_assert`

`static_assert`용 메시지 매개 변수는 선택 사항입니다. 자세한 내용은 [Extending static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)(static_assert 확장, v2)를 참조하세요.

### <a name="c17-fallthrough-attribute"></a>C++17: `[[fallthrough]]` 특성

**/std:c++17** 모드에서 `[[fallthrough]]` 특성은 switch 문의 컨텍스트에서 제어 이동 동작이 의도된 컴파일러에 대한 힌트로 사용될 수 있습니다. 이 특성을 사용하면 컴파일러가 이러한 경우에 경고를 실행하지 않습니다. 자세한 내용은 [Wording for \[\[fallthrough\]\] attribute](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf)([[fallthrough]] 특성의 표현)를 참조하세요.

### <a name="generalized-range-based-for-loops"></a>일반화된 범위 기반 for 루프

범위 기반 for 루프에 동일한 형식의 `begin()` 및 `end()` 반환 개체가 더 이상 필요하지 않습니다. 이 변경으로 인해 `end()`가 [range-v3](https://github.com/ericniebler/range-v3) 및 완료되었지만 아직 게시되지 않은 범위 기술 사양의 범위에서 사용된 sentinel을 반환할 수 있습니다. 자세한 내용은 [Generalizing the Range-Based For Loop](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)(범위 기반 for 루프 일반화)를 참조하세요.

## <a name="improvements_153"></a> 15.3의 규칙 향상

### <a name="constexpr-lambdas"></a>constexpr 람다

이제 상수 식에서 람다 식을 사용할 수 있습니다. 자세한 내용은 [C++의 constexpr 람다 식](../cpp/lambda-expressions-constexpr.md)을 참조하세요.

### <a name="if-constexpr-in-function-templates"></a>함수 템플릿의 **if constexpr**

함수 템플릿에 컴파일 시간 분기가 가능하도록 **if constexpr** 문이 포함될 수 있습니다. 자세한 내용은 [if constexpr 문](../cpp/if-else-statement-cpp.md#if_constexpr)을 참조하세요.

### <a name="selection-statements-with-initializers"></a>이니셜라이저를 사용하는 선택 문

**if** 문은 문 자체 내의 블록 범위에서 변수를 소개하는 이니셜라이저를 포함할 수 있습니다. 자세한 내용은 [이니셜라이저가 있는 if 문](../cpp/if-else-statement-cpp.md#if_with_init)을 참조하세요.

### <a name="maybe_unused-and-nodiscard-attributes"></a>`[[maybe_unused]]` 및 `[[nodiscard]]` 특성

새 특성 `[[maybe_unused]]`는 엔터티가 사용되지 않는 경우 경고를 해제합니다. `[[nodiscard]]` 특성은 함수 호출의 반환 값이 무시되는 경우 경고를 만듭니다. 자세한 내용은 [C++ 특성](../cpp/attributes.md)을 참조하세요.

### <a name="using-attribute-namespaces-without-repetition"></a>반복 없이 특성 네임스페이스 사용

특성 목록에서 단일 네임스페이스 식별자만 사용하는 새 구문입니다. 자세한 내용은 [C++ 특성](../cpp/attributes.md)을 참조하세요.

### <a name="structured-bindings"></a>구조적 바인딩

이제 값이 배열, `std::tuple` 또는 `std::pair`이거나 모두 공용 비정적 데이터 멤버만 포함하는 경우 단일 선언에서 구성 요소의 값을 개별 이름으로 저장할 수 있습니다. 자세한 내용은 [구조적 바인딩](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf) 및 [함수에서 여러 값 반환](../cpp/functions-cpp.md#multi_val)을 참조하세요.

### <a name="construction-rules-for-enum-class-values"></a>**열거형 클래스** 값에 대한 생성 규칙

이제 해당 정의에서 열거자를 소개하지 않고 소스에서 목록 초기화 구문을 사용하는 경우 범위가 지정된 열거형의 기본 형식에서 열거형 자체로의 암시적/비축소 변환 기능이 있습니다. 자세한 내용은 [enum 클래스 값의 생성 규칙](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf) 및 [열거형](../cpp/enumerations-cpp.md#no_enumerators)을 참조하세요.

### <a name="capturing-this-by-value"></a>값 기준 `*this` 캡처

람다 식의 `*this` 개체는 이제 값을 기준으로 캡처할 수 있습니다. 이 변경으로 인해 특히 최신 머신 아키텍처에서 병렬 및 비동기 작업을 통해 람다가 호출되는 시나리오를 사용할 수 있습니다. 자세한 내용은 [Lambda Capture of \*this by Value as \[=,\*this\]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)([=,*this]로 값 기준 this 람다 캡처)를 참조하세요.

### <a name="removing-operator-for-bool"></a>**bool**에 대해 `operator++` 제거

`operator++`는 더 이상 **bool** 형식에서 지원되지 않습니다. 자세한 내용은 [사용되지 않는 operator++(bool) 제거(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html)를 참조하세요.

### <a name="removing-deprecated-register-keyword"></a>사용되지 않는 **register** 키워드 제거

이전에 더 이상 사용되지 않고(컴파일러에서 무시된) **register** 키워드가 이제 언어에서 제거되었습니다. 자세한 내용은 [사용되지 않는 register 키워드 제거(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html)를 참조하세요.

## <a name="improvements_155"></a> 15.5의 규칙 향상

\[14]로 표시된 기능은 **/std:c++14** 모드에서도 무조건 사용할 수 있습니다.

### <a name="new-compiler-switch-for-extern-constexpr"></a>**extern constexpr**을 위한 새로운 컴파일러 스위치

이전 버전의 Visual Studio에서는 **constexpr** 변수에 **extern**이 표시된 경우에도 컴파일러가 항상 해당 변수에 내부 연결을 제공했습니다. Visual Studio 2017 15.5 버전에서 새 컴파일러 스위치[/Zc:externConstexpr](../build/reference/zc-externconstexpr.md)는 올바른 표준 준수 동작을 활성화합니다. 자세한 내용은 [extern constexpr 링크](#extern_linkage)를 참조하세요.

### <a name="removing-dynamic-exception-specifications"></a>동적 예외 사양 제거

[P0003R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html) C++11에서는 동적 예외 사양이 사용되지 않았습니다. 이 기능은 C++17에서 제거되었지만 사용되지 않는 `throw()` 사양이 여전히 `noexcept(true)`의 별칭으로 엄격히 유지됩니다. 자세한 내용은 [동적 예외 사양 제거 및 noexcept](#noexcept_removal)를 참조하세요.

### `not_fn()`

[P0005R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html) `not_fn`은 `not1` 및 `not2`를 대체합니다.

### <a name="rewording-enable_shared_from_this"></a>`enable_shared_from_this` 표현 수정

C++11에 [P0033R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html) `enable_shared_from_this`가 추가되었습니다. C++17 표준은 비정상적인 특정 사례를 더 잘 처리하도록 사양을 업데이트합니다. [14]

### <a name="splicing-maps-and-sets"></a>맵과 집합 스플라이스

[P0083R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf) 이 기능은 연관 컨테이너에서 `map`, `set`, `unordered_map`, `unordered_set` 등의 노드 추출을 지원하며, 추출된 노드는 수정한 뒤 동일한 컨테이너나 동일한 노드 형식을 사용하는 다른 컨테이너에 다시 삽입할 수 있습니다. (일반적인 사용 사례는 `std::map`에서 노드를 추출하고 키를 변경하고 다시 삽입하는 것입니다.)

### <a name="deprecating-vestigial-library-parts"></a>남아 있는 라이브러리 파트 사용 중단

[P0174R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html) C++ 표준 라이브러리의 몇 가지 기능은 여러 해 동안 새로운 기능으로 대체되었거나, 유용하지 않거나 문제가 있는 것으로 확인되었습니다. 이러한 기능은 공식적으로 C++17에서 사용되지 않습니다.

### <a name="removing-allocator-support-in-stdfunction"></a>`std::function`에서 할당자 지원 제거

[P0302R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html) C++17 이전에는 클래스 템플릿 `std::function`에 할당자 인수를 사용하는 몇 가지 생성자가 있었습니다. 그러나 이 컨텍스트에서 할당자를 사용하는 것이 문제가 되었고, 의미 체계는 불확실했습니다. 문제 생성자가 제거되었습니다.

### <a name="fixes-for-not_fn"></a>`not_fn()` 수정

[P0358R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html)`std::not_fn`의 표현이 래퍼 호출에 사용 시 값 범주의 전파가 지원됨을 나타내도록 수정되었습니다.

### <a name="shared_ptrt-shared_ptrtn"></a>`shared_ptr<T[]>`, `shared_ptr<T[N]>`

[P0414R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html) 라이브러리 기본 사항에서 C++17로 `shared_ptr` 변경 사항 병합. [14]

### <a name="fixing-shared_ptr-for-arrays"></a>배열에 대한 `shared_ptr` 수정

[P0497R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html) 배열에 대한 shared_ptr 지원 해결입니다. [14]

### <a name="clarifying-insert_return_type"></a>`insert_return_type`의 명확한 정의

[P0508R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html) 고유한 키가 포함된 연관 컨테이너와 고유한 키가 포함된 불규칙 컨테이너에는 중첩 형식 `insert_return_type`을 반환하는 멤버 함수 `insert`가 있습니다. 이 반환 형식은 이제 컨테이너의 반복기와 노드 형식에서 매개 변수화되는 형식의 특수화로 정의됩니다.

### <a name="inline-variables-for-the-standard-library"></a>표준 라이브러리의 인라인 변수

[P0607R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)

### <a name="annex-d-features-deprecated"></a>부록 D 기능 사용 중단

C++ 표준의 부록 D에는 사용이 중단된 모든 기능이 포함되어 있습니다(`shared_ptr::unique()`, `<codecvt>` 및 `namespace std::tr1` 포함). **/std:c++17** 컴파일러 스위치를 설정하면 부록 D의 거의 모든 표준 라이브러리 기능이 사용되지 않는 것으로 표시됩니다. 자세한 내용은 [부록 D의 표준 라이브러리 기능이 사용되지 않는 것으로 표시됨](#annex_d)을 참조하세요.

`<experimental/filesystem>`의 `std::tr2::sys` 네임스페이스는 이제 기본적으로 **/std:c++14** 하에서 사용 중단 경고를 생성하며, **/std:c++17** 하에서 기본적으로 제거됩니다.

비표준 확장(클래스 내 명시적 특수화)을 방지하여 `<iostream>`의 규칙이 개선되었습니다.

이제 표준 라이브러리에서 변수 템플릿을 내부적으로 사용합니다.

형식 시스템의 **noexcept** 추가 및 dynamic-exception-specifications 제거를 포함한 C++17 컴파일러 변경 사항에 따라 표준 라이브러리가 업데이트되었습니다.

## <a name="improvements_156"></a> 15.6의 규칙 향상

### <a name="c17-library-fundamentals-v1"></a>C++17 라이브러리 기본 사항 V1

[P0220R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html)은 C++17에 대한 라이브러리 기본 사항 기술 사양을 표준으로 통합합니다. \<experimental/tuple>, \<experimental/optional>, \<experimental/functional>, \<experimental/any>, \<experimental/string_view>, \<experimental/memory>, \<experimental/memory_resource> 및 \<experimental/algorithm>의 업데이트를 다룹니다.

### <a name="c17-improving-class-template-argument-deduction-for-the-standard-library"></a>C++17: 표준 라이브러리의 클래스 템플릿 인수 추론 향상

[P0739R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html)`adopt_lock_t`를 `scoped_lock`에 대한 매개 변수 목록의 앞으로 이동하여 `scoped_lock`의 일관된 사용을 활성화합니다. 복사 할당을 사용할 수 있도록 `std::variant` 생성자가 더 많은 사례에서 오버로드 해결에 참여하도록 허용합니다.

## <a name="improvements_157"></a> 15.7의 규칙 향상

### <a name="c17-rewording-inheriting-constructors"></a>C++17: 상속 생성자 표현 수정

[P0136R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html) 생성자의 이름을 지정하는 **using** 선언에서 이제 파생 클래스 생성자를 추가로 선언하는 대신 파생 클래스의 초기화에 해당 기본 클래스 생성자가 표시되도록 합니다. 이 표현 수정은 C++14의 변경 내용입니다. Visual Studio 2017 버전 15.7 이상의 **/std:c++17** 모드에서는, C++14에서 유효하고 상속 생성자를 사용하는 코드가 유효하지 않거나 다른 의미 체계를 가질 수 있습니다.

다음 예제에서는 C++14 동작을 보여 줍니다.

```cpp
struct A {
    template<typename T>
    A(T, typename T::type = 0);
    A(int);
};

struct B : A {
    using A::A;
    B(int n) = delete; // Error C2280
};

B b(42L); // Calls B<long>(long), which calls A(int)
          //  due to substitution failure in A<long>(long).
```

다음 예제에서는 Visual Studio 15.7에서 **/std:c++17** 동작을 보여 줍니다.

```cpp
struct A {
    template<typename T>
    A(T, typename T::type = 0);
    A(int);
};

struct B : A {
    using A::A;
    B(int n)
    {
        //do something
    }
};

B b(42L); // now calls B(int)
```

자세한 내용은 [생성자](../cpp/constructors-cpp.md#inheriting_constructors)를 참조하세요.

### <a name="c17-extended-aggregate-initialization"></a>C++17: 확장된 집계 초기화

[P0017R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)

기본 클래스의 생성자가 공용이 아니지만 파생된 클래스에 액세스할 수 있는 경우, Visual Studio 2017 버전 15.7의 **/std:c++17** 모드에서 파생된 형식의 개체를 초기화하기 위해 더 이상 빈 중괄호를 사용할 수 없습니다.
다음 예제에서는 C++14 준수 동작을 보여 줍니다.

```cpp
struct Derived;
struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {};
Derived d1; // OK. No aggregate init involved.
Derived d2 {}; // OK in C++14: Calls Derived::Derived()
               // which can call Base ctor.
```

C++17에서 `Derived`는 이제 집계 형식으로 간주되므로 프라이빗 기본 생성자를 통한 `Base`의 초기화가 확장된 집계 초기화 규칙의 일부로 직접 발생합니다. 이전에는 `Base` 프라이빗 생성자가 `Derived` 생성자를 통해 호출되었으며, friend 선언 때문에 성공했습니다.
다음 예제에서는 **/std:c++17** 모드의 Visual Studio 버전 15.7에서 C++17 동작을 보여 줍니다.

```cpp
struct Derived;
struct Base {
    friend struct Derived;
private:
    Base() {}
};
struct Derived : Base {
    Derived() {} // add user-defined constructor
                 // to call with {} initialization
};
Derived d1; // OK. No aggregate init involved.
Derived d2 {}; // error C2248: 'Base::Base': cannot access
               // private member declared in class 'Base'
```

### <a name="c17-declaring-non-type-template-parameters-with-auto"></a>C++17: 자동으로 비형식 템플릿 매개 변수 선언

[P0127R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)

**/std:c++17** 모드에서 컴파일러는 이제 **자동**으로 선언된 비형식 템플릿 인수의 형식을 추론할 수 있습니다.

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

이 새로운 기능의 한가지 영향은 유효한 C++14 코드는 유효하지 않을 수 있거나 서로 다른 의미 체계를 가질 수 있다는 것입니다. 예를 들어 이전에 유효하지 않았던 일부 오버로드가 이제 유효합니다. 다음 예제에서는 `example(p)`에 대한 호출이 `example(void*);`로 바인딩되기 때문에 컴파일하는 C++14 코드를 보여 줍니다. Visual Studio 2017 버전 15.7의 **/std:c++17** 모드에서 `example` 함수 템플릿은 가장 일치하는 것입니다.

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*) = delete;

void example(void *);

void sample(A<0> *p)
{
    example(p); // OK in C++14
}
```

다음 예제에서는 **/std:c++17** 모드의 Visual Studio 15.7에서 C++17 코드를 보여 줍니다.

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*);

void example(void *);

void sample(A<0> *p)
{
    example(p); // C2280: 'int example<int,0>(A<0>*)': attempting to reference a deleted function
}
```

### <a name="c17-elementary-string-conversions-partial"></a>C++17: 기본 문자열 변환(부분)

[P0067R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html) 정수와 문자열 간 및 부동 소수점 숫자와 문자열 간의 전환에 대한 하위 수준, 로캘 무관 함수입니다.

### <a name="c20-avoiding-unnecessary-decay-partial"></a>C++20: 불필요한 decay 방지(부분)

[P0777R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf) "decay"의 개념과 const 또는 참조 한정자의 단순한 제거 간의 차이를 추가합니다.  새 형식 특성 `remove_reference_t`는 일부 컨텍스트에서 `decay_t`를 대체합니다. `remove_cvref_t` 지원은 Visual Studio 2019에서 구현되었습니다.

### <a name="c17-parallel-algorithms"></a>C++17: 병렬 알고리즘

[P0024R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html) 병렬 처리 TS는 약간의 수정으로 표준으로 통합됩니다.

### <a name="c17-hypotx-y-z"></a>C++17: `hypot(x, y, z)`

[P0030R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf) 각각 세 개의 입력 매개 변수를 갖는 **float**, **double** 및 **long double** 형식에 대해 `std::hypot`로 세 개의 새로운 오버로드를 추가합니다.

### <a name="c17-filesystem"></a>C++17: \<filesystem>

[P0218R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html) 몇 가지 단어 수정으로 파일 시스템 TS를 표준으로 채택합니다.

### <a name="c17-mathematical-special-functions"></a>C++17: 수학 특수 함수

[P0226R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) 수학 특수 함수에 대한 이전 기술 사양을 표준 \<cmath> 헤더로 채택합니다.

### <a name="c17-deduction-guides-for-the-standard-library"></a>C++17: 표준 라이브러리에 대한 추론 가이드

[P0433R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html) 클래스 탬플릿 인수 추론에 대한 지원을 추가하는 [P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)의 C++17 도입의 이점을 활용하기 위해 STL로 업데이트합니다.

### <a name="c17-repairing-elementary-string-conversions"></a>C++17: 기본 문자열 변환 복구

[P0682R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0682r1.html) P0067R5의 새 기본 문자열 변환 기능에서 새 헤더 \<charconv>로 이동하고 `std::error_code` 대신 `std::errc`를 사용하여 오류 처리 변경을 포함하는 다른 개선 사항을 만듭니다.

### <a name="c17-constexpr-for-char_traits-partial"></a>C++17: `char_traits`에 대한 **constexpr**(부분)

[P0426R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html) 상수 식에서 `std::string_view`를 사용할 수 있도록 `std::traits_type` 멤버 함수 `length`, `compare` 및 `find`를 변경합니다. (Visual Studio 2017 버전 15.6에서 Clang/LLVM에 대해서만 지원됩니다. 버전 15.7 미리 보기 2에서 ClXX에 대해서도 지원이 거의 완료되었습니다.)

## <a name="improvements_159"></a> 15.9의 규칙 향상

### <a name="left-to-right-evaluation-order-for-operators-----and-"></a>`->*`, `[]`, `>>`, `<<` 연산자의 왼쪽에서 오른쪽 계산 순서

C++17부터 `->*`, `[]`, `>>`, `<<` 연산자의 피연산자가 왼쪽에서 오른쪽 순으로 계산되어야 합니다. 컴파일러가 이 순서를 보장할 수 없는 두 가지 경우는 다음과 같습니다.

- 피연산자 식 중 하나가 값으로 전달된 개체이거나 값으로 전달된 개체를 포함하는 경우, 또는

- **/clr**을 사용하여 컴파일할 때 피연산자 중 하나가 개체 또는 배열 요소의 필드인 경우.

컴파일러는 왼쪽에서 오른쪽으로 계산을 보장할 수 없는 경우 경고 [C4866](https://docs.microsoft.com/cpp/error-messages/compiler-warnings/c4866?view=vs-2017)을 생성합니다. 이러한 연산자의 왼쪽에서 오른쪽 순서 요구 사항이 C++17에서 도입되었기 때문에, **/std:c++17** 이상을 지정한 경우에만 컴파일러에서 이 경고를 생성합니다.

이 경고를 해결하려면 먼저 피연산자 계산으로 순서에 종속되는 부작용이 발생하는 경우처럼 피연산자의 왼쪽에서 오른쪽으로 계산이 필요한지 고려합니다. 대부분의 경우 피연산자가 계산되는 순서는 눈에 띄는 영향을 미치지 않습니다. 계산 순서가 왼쪽에서 오른쪽이어야 하는 경우, 대신 const 참조로 피연산자를 전달할 수 있는지 여부를 고려합니다. 이렇게 변경하면 다음 코드 샘플에서 경고가 제거됩니다.

```cpp
// C4866.cpp
// compile with: /w14866 /std:c++17

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x) : x(x) {}
    HasCopyConstructor(const HasCopyConstructor& h) : x(h.x) { }
};

int operator>>(HasCopyConstructor a, HasCopyConstructor b) { return a.x >> b.x; }

// This version of operator>> does not trigger the warning:
// int operator>>(const HasCopyConstructor& a, const HasCopyConstructor& b) { return a.x >> b.x; }

int main()
{
    HasCopyConstructor a{ 1 };
    HasCopyConstructor b{ 2 };

    a>>b;        // C4866 for call to operator>>
};
```

## <a name="update_150"></a> Visual Studio 2017 RTW(버전 15.0)의 버그 수정

### <a name="copy-list-initialization"></a>Copy-list-initialization

Visual Studio 2017에서는 Visual Studio 2015에서 catch되지 않았으며 크래시나 정의되지 않은 런타임 동작을 일으킬 수 있었던, 이니셜라이저 목록을 사용한 개체 만들기와 관련된 컴파일러 오류를 올바르게 발생시킵니다. N4594 13.3.1.7p1을 기준으로, copy-list-initialization에서 컴파일러는 오버로드 해결을 위해 명시적 생성자를 고려해야 하지만 이 특정 오버로드가 선택되면 오류를 발생시켜야 합니다.

다음 두 가지 예제는 Visual Studio 2015에서 컴파일되지만 Visual Studio 2017에서 컴파일되지 않습니다.

```cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 }; // error C3445: copy-list-initialization of 'A' cannot use an explicit constructor
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot convert from 'int' to 'const A &'

}
```

오류를 수정하려면 직접 초기화를 사용합니다.

```cpp
A a1{ 1 };
const A& a2{ 1 };
```

Visual Studio 2015에서 컴파일러는 일반 copy-initialization과 같은 방식으로 copy-list-initialization을 잘못 처리했고 오버로드 확인을 위해 생성자 변환만 고려했습니다. 다음 예제에서 Visual Studio 2015에서는 MyInt(23)를 선택하지만 Visual Studio 2017에서는 정확히 오류를 발생시킵니다.

```cpp
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyStore {
    explicit MyStore(int initialCapacity);
};

struct MyInt {
    MyInt(int i);
};

struct Printer {
    void operator()(MyStore const& s);
    void operator()(MyInt const& i);
};

void f() {
    Printer p;
    p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```

이 예제는 이전 예제와 비슷하지만 다른 오류를 발생시킵니다. 이 예제는 Visual Studio 2015에서는 성공하지만 Visual Studio 2017(C2668 포함)에서는 실패합니다.

```cpp
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```

### <a name="deprecated-typedefs"></a>사용되지 않는 형식 정의

Visual Studio 2017에서는 이제 클래스 또는 구조체에서 선언된 사용되지 않는 형식 정의에 대한 올바른 경고를 실행합니다. 다음 예제는 Visual Studio 2015에서는 경고 없이 컴파일되지만 Visual Studio 2017에서는 C4996를 생성합니다.

```cpp
struct A
{
    // also for __declspec(deprecated)
    [[deprecated]] typedef int inttype;
};

int main()
{
    A::inttype a = 0; // C4996 'A::inttype': was declared deprecated
}
```

### <a name="constexpr"></a>**constexpr**

Visual Studio 2017에서는 조건부 계산 연산의 왼쪽 피연산자가 constexpr 컨텍스트에서 유효하지 않을 경우 올바르게 오류를 발생시킵니다. 다음 코드는 Visual Studio 2017이 아닌 Visual Studio 2015에서 컴파일합니다(C3615 constexpr 함수 ‘f’는 상수 식이 될 수 없음).

```cpp
template<int N>
struct array
{
    int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615
}
```

오류를 수정하려면 `array::size()` 함수를 **constexpr**로 선언하거나 `f`에서 **constexpr** 한정자를 제거합니다.

### <a name="class-types-passed-to-variadic-functions"></a>variadic 함수에 전달된 클래스 형식

Visual Studio 2017에서 printf와 같이 variadic 함수에 전달된 클래스 또는 구조체는 일반적으로 복사 가능합니다. 해당 개체를 전달할 때 컴파일러는 비트 복사본을 만들기만 하고 생성자 또는 소멸자를 호출하지 않습니다.

```cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function.
                        // note: the constructor and destructor will not be called;
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```

오류를 수정하려면 일반적으로 복사 가능한 형식을 반환하는 멤버 함수를 호출하거나

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

정적 캐스트를 사용하여 개체를 변환한 후 전달합니다.

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

CString을 사용하여 빌드 및 관리되는 문자열의 경우 제공된 `operator LPCTSTR()`를 사용하여 CString 개체를 서식 문자열에 필요한 C 포인터에 캐스트해야 합니다.

```cpp
CString str1;
CString str2 = _T("hello!");
str1.Format(_T("%s"), static_cast<LPCTSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>클래스 생성의 cv 한정자

Visual Studio 2015에서는 컴파일러가 생성자 호출을 통해 클래스 개체를 생성할 때 cv 한정자를 잘못 무시하는 경우가 있습니다. 이 문제로 인해 잠재적으로 크래시 또는 예기치 않은 런타임 동작이 발생할 수 있습니다. 다음 예제는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017에서는 컴파일러 오류를 발생시킵니다.

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

오류를 수정하려면 `operator int()`를 **const**로 선언합니다.

### <a name="access-checking-on-qualified-names-in-templates"></a>템플릿의 정규화된 이름에 대한 액세스 검사

이전 버전의 컴파일러는 일부 템플릿 컨텍스트에서 정규화된 이름에 대한 액세스를 검사하지 않았습니다. 이 문제는 이름에 액세스할 수 없어 대체에 실패할 것으로 예상되는 경우의 SFINAE 동작을 방해할 수 있습니다. 컴파일러가 연산자의 틀린 오버로드를 잘못 호출했기 때문에 잠재적으로 런타임에 크래시나 예기치 않은 동작이 발생할 수 있었습니다. Visual Studio 2017에서는 컴파일러 오류가 발생합니다. 구체적인 오류는 달라질 수 있지만 일반적으로 오류는 “C2672 일치하는 오버로드된 함수가 없습니다.”입니다. 다음 코드는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017에서는 오류를 발생시킵니다.

```cpp
#include <type_traits>

template <class T> class S {
    typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x);

int main()
{
    f(10); // C2672: No matching overloaded function found.
}
```

### <a name="missing-template-argument-lists"></a>누락된 템플릿 인수 목록

Visual Studio 2015 및 이전 버전에서는 템플릿이 기본 템플릿 인수 또는 비형식 템플릿 매개 변수의 일부 등으로 템플릿 매개 변수 목록에 표시될 때 컴파일러가 누락된 템플릿 인수 목록을 진단하지 않았습니다. 이 문제로 인해 컴파일러 크래시나 예기치 않은 런타임 동작을 포함하여 예기치 않은 동작이 발생할 수 있습니다. 다음 코드는 Visual Studio 2015에서 컴파일되지만 Visual Studio 2017에서는 오류를 생성합니다.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>SFINAE 식

SFINAE 식을 지원하기 위해 이제 컴파일러는 템플릿이 인스턴스화가 아니라 선언될 때 **decltype** 인수를 구문 분석합니다. 따라서 decltype 인수에 비종속 특수화가 있는 경우 이 특수화는 인스턴스화 시점까지 지연되지 않고 즉시 처리되며, 모든 결과 오류가 그 시점에 진단됩니다.

다음 예제에서는 선언 시점에 발생한 컴파일러 오류를 보여 줍니다.

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT>
class IsCallable
{
public:
    struct BadType {};

    template <class U>
    static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>

    template <class U>
    static BadType Test(...);

    static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

### <a name="classes-declared-in-anonymous-namespaces"></a>익명 네임스페이스에 선언된 클래스

C++ 표준에 따라 익명 네임스페이스 내에 선언된 클래스는 내부 연결이 있으므로 내보낼 수 없습니다. Visual Studio 2015 및 이전 버전에서는 이 규칙이 적용되지 않았습니다. Visual Studio 2017에서는 이 규칙이 부분적으로 적용됩니다. 다음 예제에서는 Visual Studio 2017에서 "오류 C2201: const anonymous namespace::S1::vftable: 가져오거나 내보내려면 외부 링크가 있어야 합니다." 오류를 발생시킵니다.

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>값 클래스 멤버에 대한 기본 이니셜라이저(C++/CLI)

Visual Studio 2015 이하에서는 컴파일러가 값 클래스 멤버에 대한 기본 멤버 이니셜라이저를 허용하지만 무시했습니다. 값 클래스의 기본 초기화는 항상 멤버를 0으로 초기화합니다. 기본 생성자는 허용되지 않습니다. Visual Studio 2017에서는 기본 멤버 이니셜라이저가 이 예제에 표시된 대로 컴파일러 오류를 발생시킵니다.

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // isn't allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>기본 인덱서(C++/CLI)

Visual Studio 2015 이하에서는 컴파일러가 기본 속성을 기본 인덱서로 잘못 식별하는 경우가 있었습니다. 속성에 액세스하는 데 식별자 **default**를 사용하여 문제를 해결할 수 있었습니다. **default**가 C++11에서 키워드로 도입된 이후 해결 방법 자체가 문제가 되었습니다. Visual Studio 2017에서는 해결 방법이 필요했던 버그가 수정되었고 이제 컴파일러는 **default**가 클래스에 대한 기본 속성에 액세스하는 데 사용될 경우 오류를 발생시킵니다.

```cpp
//class1.cs

using System.Reflection;
using System.Runtime.InteropServices;

namespace ClassLibrary1
{
    [DefaultMember("Value")]
    public class Class1
    {
        public int Value
        {
            // using attribute on the return type triggers the compiler bug
            [return: MarshalAs(UnmanagedType.I4)]
            get;
        }
    }
    [DefaultMember("Value")]
    public class Class2
    {
        public int Value
        {
            get;
        }
    }
}

// code.cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value; // error
       r1->default;
       r2->Value;
       r2->default; // error
}
```

Visual Studio 2017에서는 이름을 사용하여 값 속성에 둘 다 액세스할 수 있습니다.

```cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="update_153"></a> 15.3의 버그 수정

### <a name="calls-to-deleted-member-templates"></a>삭제된 멤버 템플릿에 대한 호출

이전 버전의 Visual Studio에서는 컴파일러가 런타임에 크래시를 일으킬 수 있는, 삭제된 멤버 템플릿에 대한 잘못된 양식의 호출에 대한 오류를 내보내지 못하는 경우가 있었습니다. 다음 코드는 C2280 "'int S\<int>::f\<int>(void)': 삭제된 함수를 참조하려고 합니다."를 생성합니다.

```cpp
template<typename T>
struct S {
   template<typename U> static int f() = delete;
};

void g()
{
   decltype(S<int>::f<int>()) i; // this should fail
}
```

오류를 수정하려면 `i`를 **int**로 선언합니다.

### <a name="pre-condition-checks-for-type-traits"></a>형식 특성에 대한 전제 조건 검사

Visual Studio 2017 버전 15.3에서는 표준을 더 엄격하게 따르도록 형식 특성에 대한 전제 조건 검사가 향상되었습니다. 해당 검사는 할당 가능합니다. 다음 코드는 Visual Studio 2017 버전 15.3에서 C2139를 생성합니다.

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>네이티브에서 관리로의 마샬링에 대한 새로운 컴파일러 경고 및 런타임 검사

관리형 함수에서 네이티브 함수로 호출하려면 마샬링이 필요합니다. CLR은 마샬링을 수행하지만 C++ 의미 체계를 이해하지 못합니다. 네이티브 개체를 값으로 전달하면 CLR은 개체의 복사 생성자를 호출하거나, 런타임에 정의되지 않은 동작을 유발할 수 있는 `BitBlt`를 사용합니다.

이제 컴파일러는 컴파일 시간에 삭제된 복사 생성자를 포함하는 네이티브 개체가 네이티브 경계와 관리되는 경계 사이에 값으로 전달됨을 알 수 있는 경우 경고를 내보냅니다. 컴파일러는 컴파일 시간에 알 수 없는 이러한 경우를 위해 잘못된 양식의 마양샬링이 수행될 때 프로그램에서 즉시 `std::terminate`를 호출하도록 런타임 검사를 삽입합니다. Visual Studio 2017 15.3에서 다음 코드는 경고 C4606을 생성합니다. "'A': 네이티브 및 관리 경계에서 인수를 값별로 전달하려면 유효한 복사 생성자가 필요합니다. 이 생성자가 없으면 런타임 동작이 정의되지 않습니다.”

```cpp
class A
{
public:
   A() : p_(new int) {}
   ~A() { delete p_; }

   A(A const &) = delete;
   A(A &&rhs) {
   p_ = rhs.p_;
}

private:
   int *p_;
};

#pragma unmanaged

void f(A a)
{
}

#pragma managed

int main()
{
    f(A()); // This call from managed to native requires marshaling. The CLR doesn't understand C++ and uses BitBlt, which results in a double-free later.
}
```

오류를 수정하려면 `#pragma managed` 지시문을 제거하여 호출자를 네이티브로 표시하고 마샬링을 방지합니다.

### <a name="experimental-api-warning-for-winrt"></a>WinRT에 대한 실험적 API 경고

실험 및 피드백용으로 릴리스된 WinRT API는 `Windows.Foundation.Metadata.ExperimentalAttribute`로 데코레이트됩니다. Visual Studio 2017 버전 15.3에서는 컴파일러에서 특성을 발견하면 C4698 경고를 생성합니다. 이전 Windows SDK 버전의 몇몇 API는 이미 특성으로 데코레이트되었고 이러한 API를 호출하면 이제 이 컴파일러 경고가 트리거됩니다. 최신 Windows SDK에서는 모든 제공된 형식에서 이 특성이 제거되었지만, 이전 SDK를 사용 중인 경우 모든 제공된 형식 호출에 대해 이러한 경고가 표시되지 않도록 해야 합니다.

다음 코드는 경고 C4698을 생성합니다. “‘Windows::Storage::IApplicationDataStatics2::GetForUserAsync’는 평가 목적으로만 제공되며 향후 업데이트에서 변경되거나 제거될 수 있습니다.”

```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync(); //C4698
```

이 경고를 사용하지 않도록 설정하려면 #pragma를 추가합니다.

```cpp
#pragma warning(push)
#pragma warning(disable:4698)

Windows::Storage::IApplicationDataStatics2::GetForUserAsync();

#pragma warning(pop)
```

### <a name="out-of-line-definition-of-a-template-member-function"></a>템플릿 멤버 함수의 확장 정의

Visual Studio 2017 버전 15.3에서는 클래스에 선언되지 않은 템플릿 멤버 함수의 확장 정의를 발견할 경우 오류를 생성합니다. 다음 코드는 오류 C2039를 생성합니다. ‘f’:이 ‘S’의 멤버가 아닙니다.

```cpp
struct S {};

template <typename T>
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
```

오류를 해결하려면 클래스에 선언을 추가합니다.

```cpp
struct S {
    template <typename T>
    void f(T t);
};
template <typename T>
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>**this** 포인터의 주소 사용 시도

C++에서 **this**는 X에 대한 형식 포인터의 prvalue입니다. **this** 의 주소를 가져오거나 lvalue 참조에 바인딩할 수 없습니다. 이전 버전의 Visual Studio에서는 컴파일러를 통해 캐스트를 사용하여 이 제한 사항을 회피할 수 있었습니다. Visual Studio 2017 버전 15.3에서는 컴파일러에서 C2664 오류를 생성합니다.

### <a name="conversion-to-an-inaccessible-base-class"></a>액세스할 수 없는 기본 클래스로의 변환

Visual Studio 2017 버전 15.3에서 형식을 액세스할 수 없는 기본 클래스로 변환하려고 하면 오류가 발생합니다. 이제는 컴파일러에서 "오류 C2243: 'type cast': 변환('D *'에서 'B *'(으)로)이 있지만 액세스할 수 없습니다."를 발생시킵니다. 다음 코드는 형식이 잘못되었고 런타임에 충돌을 일으킬 수 있습니다. 이제 컴파일러는 다음과 같은 코드를 발견할 때 C2243을 생성합니다.

```cpp
#include <memory>

class B { };
class D : B { }; // C2243. should be public B { };

void f()
{
   std::unique_ptr<B>(new D());
}
```

### <a name="default-arguments-arent-allowed-on-out-of-line-definitions-of-member-functions"></a>기본 인수는 멤버 함수의 확장 정의에서 허용되지 않음

기본 인수는 템플릿 클래스에 있는 멤버 함수의 확장 정의에서 허용되지 않습니다. 컴파일러는 **/permissive** 아래에 경고를 실행하고, [/permissive-](../build/reference/permissive-standards-conformance.md) 아래에 하드 오류를 실행합니다.

이전 버전의 Visual Studio에서는 다음과 같은 잘못된 코드로 인해 잠재적으로 런타임 크래시가 발생할 수 있었습니다. Visual Studio 2017 버전 15.3은 경고 C5034를 생성합니다. 'A\<T>::f': 클래스 템플릿 멤버의 확장 정의에는 기본 인수가 포함될 수 없습니다.

```cpp
template <typename T>
struct A {
    T f(T t, bool b = false);
};

template <typename T>
T A<T>::f(T t, bool b = false) // C5034
{
    // ...
}
```

오류를 해결하려면 `= false` 기본 인수를 제거합니다.

### <a name="use-of-offsetof-with-compound-member-designator"></a>복합 멤버 지정자와 함께 `offsetof` 사용

Visual Studio 2017 버전 15.3에서 *m*이 "복합 멤버 지정자"인 `offsetof(T, m)`를 사용하면 **/Wall** 옵션으로 컴파일할 때 경고가 발생합니다. 다음 코드는 형식이 잘못되었고 런타임에 크래시가 발생할 수 있습니다. Visual Studio 2017 버전 15.3에서 "경고 C4841: 비표준 확장이 사용됨: 복합 멤버 지정자가 offsetof에 사용되었습니다."를 생성합니다.

```cpp
struct A {
   int arr[10];
};

// warning C4841: non-standard extension used: compound member designator in offsetof
constexpr auto off = offsetof(A, arr[2]);
```

코드를 수정하려면 pragma를 사용하여 경고를 사용하지 않도록 설정하거나 `offsetof`를 사용하지 않도록 코드를 변경합니다.

```cpp
#pragma warning(push)
#pragma warning(disable: 4841)
constexpr auto off = offsetof(A, arr[2]);
#pragma warning(pop)
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>정적 데이터 멤버 또는 멤버 함수와 함께 `offsetof` 사용

Visual Studio 2017 버전 15.3에서 *m*이 정적 데이터 멤버 또는 멤버 함수를 참조하는 `offsetof(T, m)`를 사용하면 오류가 발생합니다. 다음 코드는 “오류 C4597: 정의되지 않은 동작: offsetof가 멤버 함수 ‘example’에 적용되었습니다.” 및 “오류 C4597: 정의되지 않은 동작: offsetof가 정적 데이터 멤버 ‘sample’에 적용되었습니다.”를 생성합니다.

```cpp
#include <cstddef>

struct A {
   int ten() { return 10; }
   static constexpr int two = 2;
};

constexpr auto off = offsetof(A, ten);
constexpr auto off2 = offsetof(A, two);
```

이 코드는 형식이 잘못되었고 런타임에 크래시가 발생할 수 있습니다. 오류를 해결하려면 정의되지 않은 동작을 더 이상 호출하지 않도록 코드를 변경합니다. C++ 표준에서 허용되지 않는, 포팅할 수 없는 코드입니다.

### <a name="declspec"></a>`__declspec` 특성에 대한 새로운 경고

Visual Studio 2017 버전 15.3에서는 `__declspec(...)`가 `extern "C"` 링크 사양 앞에 적용되면 컴파일러에서 더 이상 특성을 무시하지 않습니다. 이전 버전에서는 컴파일러가 런타임 의미를 가질 수 있는 특성을 무시합니다. **/Wall** 및 **/WX** 옵션이 설정되면 다음 코드는 “경고 C4768: 링크 사양 앞의 __declspec 특성은 무시됩니다.”를 생성합니다.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

경고를 수정하려면 `extern "C"`를 먼저 배치합니다.

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

이 경고는 15.3에서 기본적으로 꺼져 있지만 15.5에서는 기본적으로 켜져 있으며, **/Wall** **/WX**로 컴파일된 코드에만 영향을 줍니다.

### <a name="decltype-and-calls-to-deleted-destructors"></a>**decltype** 및 삭제된 소멸자 호출

이전 버전의 Visual Studio에서 컴파일러는 삭제된 소멸자 호출이 **decltype**과 연결된 식의 컨텍스트에서 발생한 시점을 검색하지 않았습니다. Visual Studio 2017 버전 15.3에서 다음 코드는 "오류 C2280: 'A\<T>::~A(void)': 삭제된 함수를 참조하려고 시도 중"을 생성합니다.

```cpp
template<typename T>
struct A
{
   ~A() = delete;
};

template<typename T>
auto f() -> A<T>;

template<typename T>
auto g(T) -> decltype((f<T>()));

void h()
{
   g(42);
}
```

### <a name="uninitialized-const-variables"></a>초기화되지 않은 const 변수

Visual Studio 2017 RTW 릴리스에는 **const** 변수가 초기화되지 않은 경우 C++ 컴파일러가 진단을 실행하지 않는 재발 문제가 있었습니다. 이 재발 문제는 Visual Studio 2017 버전 15.3에서 수정되었습니다. 다음 코드는 이제 "경고 C4132: 'Value': const 개체를 초기화해야 합니다."를 생성합니다.

```cpp
const int Value; //C4132
```

오류를 해결하려면 `Value`에 값을 할당합니다.

### <a name="empty-declarations"></a>빈 선언

Visual Studio 2017 버전 15.3에서는 이제 기본 제공 형식이 아닌 모든 형식의 빈 선언에 대해 경고를 생성합니다. 다음 코드는 모든 네 가지 선언에 대한 수준 2 C4091 경고를 생성합니다.

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };

int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

경고를 제거하려면 빈 선언을 주석으로 처리하거나 제거합니다. 명명되지 않은 개체에 부작용(예: RAII)을 포함하려는 경우 개체에 이름을 지정해야 합니다.

경고는 **/Wv:18**에서는 제외되고 기본적으로 경고 수준 W2에서 켜집니다.

### <a name="stdis_convertible-for-array-types"></a>배열 형식에 대한 `std::is_convertible`

이전 버전의 컴파일러는 배열 형식에 대한 [std::is_convertible](../standard-library/is-convertible-class.md)에 대해 잘못된 결과를 제공했습니다. 따라서 라이브러리 작성자는 `std::is_convertible<...>` 형식 특성을 사용할 때 특별히 Microsoft C++ 컴파일러를 사용해야 했습니다. 다음 예제에서는 정적 어설션이 이전 버전의 Visual Studio에서는 통과하지만 Visual Studio 2017 업데이트 버전 15.3에서는 실패합니다.

```cpp
#include <type_traits>

using Array = char[1];

static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

가상의 함수 정의가 올바른 형식으로 되어 있는지 확인하는 방법으로 `std::is_convertible<From, To>`가 계산됩니다.

```cpp
   To test() { return std::declval<From>(); }
```

### <a name="private-destructors-and-stdis_constructible"></a>프라이빗 소멸자 및 `std::is_constructible`

이전 버전의 컴파일러에서는 [std::is_constructible](../standard-library/is-constructible-class.md)의 결과를 결정할 때 소멸자가 비공개인지 여부를 무시했습니다. 그러나 지금은 비공개 여부를 고려합니다. 다음 예제에서는 정적 어설션이 이전 버전의 Visual Studio에서는 통과하지만 Visual Studio 2017 업데이트 버전 15.3에서는 실패합니다.

```cpp
#include <type_traits>

class PrivateDtor {
   PrivateDtor(int) { }
private:
   ~PrivateDtor() { }
};

// This assertion used to succeed. It now correctly fails.
static_assert(std::is_constructible<PrivateDtor, int>::value);
```

비공개 소멸자는 형식을 non-constructible로 만듭니다. 다음 선언이 작성된 것처럼 `std::is_constructible<T, Args...>`가 계산됩니다.

```cpp
   T obj(std::declval<Args>()...)
```

이 호출은 소멸자 호출을 의미합니다.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: 모호한 오버로드 확인

이전 버전의 컴파일러에서는 선언 및 인수 종속성 조회를 모두 사용하여 여러 후보를 찾을 때 모호성을 검색하지 못하는 경우가 종종 있었습니다. 이 오류로 인해 잘못된 오버로드를 선택하고 예기치 않은 런타임 동작이 발생할 수 있습니다. 다음 예제에서는 Visual Studio 2017 버전 15.3에서 "C2668 'f': 오버로드된 함수에 대한 호출이 모호합니다."를 정확히 발생시킵니다.

```cpp
namespace N {
   template<class T>
   void f(T&, T&);

   template<class T>
   void f();
}

template<class T>
void f(T&, T&);

struct S {};
void f()
{
   using N::f;

   S s1, s2;
   f(s1, s2); // C2668
}
```

`::f()`를 호출하려는 경우 코드를 수정하려면 사용 중인 `N::f` 문을 제거합니다.

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: 로컬 함수 선언 및 인수 종속성 조회

로컬 함수 선언은 바깥쪽 범위에 있는 함수 선언을 숨기고 인수 종속성 조회를 사용하지 않도록 설정합니다. 그러나 이 경우에는 이전 버전의 컴파일러가 인수 종속성 조회를 수행했으므로 잘못된 오버로드를 선택하고 예기치 않은 런타임 동작이 발생할 가능성이 있습니다. 일반적으로 이 오류는 로컬 함수 선언의 잘못된 시그니처 때문입니다. 다음 예제에서는 Visual Studio 2017 버전 15.3이 “C2660 ‘f’: 함수는 2개의 매개 변수를 사용하지 않습니다.”를 올바르게 발생시킵니다.

```cpp
struct S {};
void f(S, int);

void g()
{
   void f(S); // C2660 'f': function does not take 2 arguments:
   // or void f(S, int);
   S s;
   f(s, 0);
}
```

이 문제를 해결하려면 `f(S)` 시그니처를 변경하거나 제거합니다.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: 이니셜라이저 목록에서 초기화 순서

클래스 멤버는 이니셜라이저 목록에 표시되는 순서가 아니라 선언된 순서대로 초기화됩니다. 이전 버전의 컴파일러는 이니셜라이저 목록의 순서가 선언 순서와 다른 경우 경고를 표시하지 않았습니다. 이 문제로 인해 한 멤버의 초기화가 이미 초기화되고 있는 목록의 다른 멤버에 종속된 경우 정의되지 않은 런타임 동작이 발생할 수 있었습니다. 다음 예제에서는 Visual Studio 2017 버전 15.3( **/Wall** 포함)에서 "C5038: 'A::y' 데이터 멤버가 'A::y' 데이터 멤버 다음에 초기화됩니다."라는 경고를 발생시킵니다.

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

문제를 해결하려면 선언과 같은 순서가 되도록 이니셜라이저 목록을 정렬합니다. 하나 또는 두 이니셜라이저가 기본 클래스 구성원을 참조하는 경우 유사한 경고가 발생합니다.

이 경고는 기본적으로 꺼져 있으며, **/Wall**로 컴파일된 코드에만 영향을 줍니다.

## <a name="update_155"></a> 15.5의 버그 수정 및 기타 동작 변경

### <a name="partial-ordering-change"></a>부분 순서 변경

컴파일러는 이제 다음 코드를 올바르게 거부하고 올바른 오류 메시지를 제공합니다.

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(const T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);    // C2668
}
```

```Output
t161.cpp
t161.cpp(16): error C2668: 'f': ambiguous call to overloaded function
t161.cpp(8): note: could be 'int f<int*>(const T &)'
        with
        [
            T=int*
        ]
t161.cpp(2): note: or       'int f<int>(int*)'
t161.cpp(16): note: while trying to match the argument list '(int*)'
```

위의 예에서 문제는 형식에 두 가지 차이점이 있다는 것입니다(const 및 non-const와 pack 및 non-pack). 컴파일러 오류를 제거하려면 차이점 중 하나를 제거합니다. 이렇게 하면 컴파일러가 함수의 순서를 명확하게 지정할 수 있습니다.

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);
}
```

### <a name="exception-handlers"></a>예외 처리기

배열 또는 함수 형식에 대한 참조 처리기는 모든 예외 개체에 일치하지 않습니다. 컴파일러는 이제 이 규칙을 올바르게 적용하고 수준 4 경고를 생성합니다. 또한 **/Zc:strictStrings**가 사용될 경우 `char*` 또는 `wchar_t*` 처리기를 더 이상 문자열 리터럴에 일치시키지 않습니다.

```cpp
int main()
{
    try {
        throw "";
    }
    catch (int (&)[1]) {} // C4843 (This should always be dead code.)
    catch (void (&)()) {} // C4843 (This should always be dead code.)
    catch (char*) {} // This should not be a match under /Zc:strictStrings
}
```

```Output
warning C4843: 'int (&)[1]': An exception handler of reference to array or function type is unreachable, use 'int*' instead
warning C4843: 'void (__cdecl &)(void)': An exception handler of reference to array or function type is unreachable, use 'void (__cdecl*)(void)' instead
```

다음 코드에서는 오류를 방지합니다.

```cpp
catch (int (*)[1]) {}
```

### <a name="tr1"></a> `std::tr1` 네임스페이스는 사용되지 않음

이제 비표준 `std::tr1` 네임스페이스가 C++14 및 C++17 모드에서 모두 사용되지 않는 것으로 표시됩니다. Visual Studio 2017 15.5 버전에서 다음 코드를 실행하면 C4996이 발생합니다.

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::tr1::function<int (int, int)> f = std::plus<int>(); //C4996
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

```Output
warning C4996: 'std::tr1': warning STL4002: The non-standard std::tr1 namespace and TR1-only machinery are deprecated and will be REMOVED. You can define _SILENCE_TR1_NAMESPACE_DEPRECATION_WARNING to acknowledge that you have received this warning.
```

이 오류를 해결하려면 `tr1` 네임스페이스에 대한 참조를 제거합니다.

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::function<int (int, int)> f = std::plus<int>();
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

### <a name="annex_d"></a> 부록 D의 표준 라이브러리 기능이 사용되지 않는 것으로 표시됨

**/std:c++17** 모드 컴파일러 스위치를 설정하면 부록 D의 거의 모든 표준 라이브러리 기능이 사용되지 않는 것으로 표시됩니다.

Visual Studio 2017 15.5 버전에서 다음 코드를 실행하면 C4996이 발생합니다.

```cpp
#include <iterator>

class MyIter : public std::iterator<std::random_access_iterator_tag, int> {
public:
    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

```Output
warning C4996: 'std::iterator<std::random_access_iterator_tag,int,ptrdiff_t,_Ty*,_Ty &>::pointer': warning STL4015: The std::iterator class template (used as a base class to provide typedefs) is deprecated in C++17. (The <iterator> header is NOT deprecated.) The C++ standard has never required user-defined iterators to derive from std::iterator. To fix this warning, stop deriving from std::iterator and start providing publicly accessible typedefs named iterator_category, value_type, difference_type, pointer, and reference. Note that value_type is required to be non-const, even for constant iterators. You can define _SILENCE_CXX17_ITERATOR_BASE_CLASS_DEPRECATION_WARNING or _SILENCE_ALL_CXX17_DEPRECATION_WARNINGS to acknowledge that you have received this warning.
```

이 오류를 해결하려면 다음 코드에 설명된 것처럼 경고 텍스트의 지침을 따르세요.

```cpp
#include <iterator>

class MyIter {
public:
    typedef std::random_access_iterator_tag iterator_category;
    typedef int value_type;
    typedef ptrdiff_t difference_type;
    typedef int* pointer;
    typedef int& reference;

    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

### <a name="unreferenced-local-variables"></a>참조되지 않은 지역 변수

Visual Studio 15.5에서는 다음 코드에 표시된 것처럼 C4189 경고가 더 많은 경우에 내보내집니다.

```cpp
void f() {
    char s[2] = {0}; // C4189. Either use the variable or remove it.
}
```

```Output
warning C4189: 's': local variable is initialized but not referenced
```

이 오류를 해결하려면 사용되지 않는 변수를 제거합니다.

### <a name="single-line-comments"></a>한 줄로 된 주석

Visual Studio 2017 15.5 버전에서는 C 컴파일러에서 더 이상 C4001 및 C4179 경고를 내보내지 않습니다. 이전에는 이러한 경고가 **/Za** 컴파일러 스위치하에서만 내보내졌습니다.  C99 이후로 한 줄로 된 주석이 C 표준에 포함되었으므로 이러한 경고는 더 이상 필요하지 않습니다.

```cpp
/* C only */
#pragma warning(disable:4001) //C4619
#pragma warning(disable:4179)
// single line comment
//* single line comment */
```

```Output
warning C4619: #pragma warning: there is no warning number '4001'
```

코드가 이전 버전과 호환될 필요가 없는 경우 C4001/C4179 비표시 오류(Suppression)를 제거하여 경고를 방지할 수 있습니다. 코드가 이전 버전과 호환되어야 할 경우 C4619만 표시되지 않게 합니다.

```C

/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```

### <a name="__declspec-attributes-with-extern-c-linkage"></a>`extern "C"` 연결이 있는 `__declspec` 특성

이전 버전의 Visual Studio에서는 `extern "C"` 링크 사양 앞에 `__declspec(...)` 가 적용된 경우 컴파일러가 `__declspec(...)` 특성을 무시했습니다. 이 동작은 사용자가 의도하지 않은 코드 생성을 유발했으며 런타임에도 영향을 줄 가능성이 있었습니다. 이 경고는 Visual Studio 15.3 버전에서 추가되었지만 기본적으로 꺼져 있었습니다. Visual Studio 2017 15.5 버전에서 이 경고는 기본적으로 활성화되어 있습니다.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

```Output
warning C4768: __declspec attributes before linkage specification are ignored
```

이 오류를 해결하려면 __declspec 특성 앞에 링크 사양을 추가하세요.

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

이 새로운 경고 C4768은 Visual Studio 2017 15.3 이하 버전과 함께 제공된 일부 Windows SDK 헤더에서 표시됩니다(예: RS2 SDK라고도 하는 10.0.15063.0 버전). 그러나 이후 버전의 Windows SDK 헤더(특히 ShlObj.h 및 ShlObj_core.h)는 이 경고를 생성하지 않도록 수정되었습니다. Windows SDK 헤더에서 이 경고가 발생하면 이러한 작업을 수행할 수 있습니다.

1. Visual Studio 2017 버전 15.5 릴리스와 함께 제공된 최신 Windows SDK로 전환합니다.

1. Windows SDK 헤더 문의 #include 주위에 있는 경고를 끕니다.

```cpp
   #pragma warning (push)
   #pragma warning(disable:4768)
   #include <shlobj.h>
   #pragma warning (pop)
   ```

### <a name="extern_linkage"></a>extern constexpr 링크

이전 버전의 Visual Studio에서는 **constexpr** 변수에 **extern**이 표시된 경우에도 컴파일러가 항상 해당 변수에 내부 연결을 제공했습니다. Visual Studio 2017 15.5 버전에서 새 컴파일러 스위치( **/Zc:externConstexpr**)는 올바른 표준 준수 동작을 활성화합니다. 결국 이 동작이 기본값이 됩니다.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

헤더 파일에 **extern constexpr**로 선언된 변수가 포함되어 있으면 중복 선언을 올바르게 결합하기 위해 해당 변수에 `__declspec(selectany)`를 표시해야 합니다.

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>불완전한 클래스 형식에는 **typeid**를 사용할 수 없습니다.

이전 버전의 Visual Studio에서는 컴파일러가 다음 코드를 잘못 허용하여 형식 정보가 잘못될 가능성이 있었습니다. Visual Studio 2017 15.5 버전에서는 컴파일러에서 오류를 올바르게 생성합니다.

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdis_convertible-target-type"></a>`std::is_convertible` 대상 유형

`std::is_convertible`에서는 대상 유형이 유효한 반환 형식이어야 합니다. 이전 버전의 Visual Studio에서는 컴파일러가 추상 형식을 잘못 허용하여 오버로드 확인이 잘못되고 의도하지 않은 런타임 동작이 발생할 가능성이 있었습니다.  이제 다음 코드는 C2338을 올바르게 생성합니다.

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D, B>::value, "fail"); // C2338 in 15.5
```

오류를 방지하려면 `is_convertible` 사용 시 포인터 형식을 비교해야 합니다. 하나의 형식이 추상적일 경우 non-pointer-type 비교가 실패할 수 있기 때문입니다.

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D *, B *>::value, "fail");
```

### <a name="noexcept_removal"></a> 동적 예외 사양 제거 및 **noexcept**

C++17에서 `throw()`는 **noexcept**에 대한 별칭이고, `throw(<type list>)` 및 `throw(...)`가 제거되었으며 특정 형식에 **noexcept**가 포함될 수 있습니다. 이 변경으로 인해 C++14 또는 이전 버전을 준수하는 코드와 소스 호환성 문제가 발생할 수 있습니다. 전체적으로 C++17 모드를 사용 중일 때 **/Zc:noexceptTypes-** 스위치를 사용하여 **noexcept** 의 C++14 버전으로 되돌릴 수 있습니다. 이렇게 하면 모든 `throw()` 코드를 동시에 다시 작성하지 않고도 C++17을 준수하도록 소스 코드를 업데이트할 수 있습니다.

또한 컴파일러는 이제 새로운 경고 C5043과 관련하여 C++17 모드의 선언이나 [/permissive-](../build/reference/permissive-standards-conformance.md)를 사용하여 더 많은 불일치 예외 사양을 진단합니다.

다음 코드는 Visual Studio 2017 버전 15.5에서 **/std:c++17** 스위치가 적용될 때 C5043 및 C5040을 생성합니다.

```cpp
void f() throw(); // equivalent to void f() noexcept;
void f() {} // warning C5043
void g() throw(); // warning C5040

struct A {
    virtual void f() throw();
};

struct B : A {
    virtual void f() { } // error C2694
};
```

여전히 **/std:c++17**을 사용 중일 때 오류를 제거하려면 명령줄에 **/Zc:noexceptTypes-** 스위치를 추가하거나 다음 예제에 나와 있는 것처럼 **noexcept**를 사용하도록 코드를 업데이트하세요.

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A {
    virtual void f() noexcept;
};

struct B : A {
    virtual void f() noexcept { }
};
```

### <a name="inline-variables"></a>인라인 변수

constexpr 정적 데이터 멤버는 이제 암시적으로 인라인이므로 이제 클래스 내 선언으로 정의됩니다. constexpr 정적 데이터 멤버에 대한 확장 정의는 이제 중복되며 사용되지 않습니다. Visual Studio 2017 버전 15.5에서 **/std:c++17** 스위치를 적용하면, 이제 다음 코드에서 경고 C5041 ‘‘size’: constexpr 정적 데이터 멤버에 대한 확장 정의는 C++17에서 필요하지 않거나 사용되지 않습니다.’가 발생합니다. 

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-__declspec-warning-c4768-now-on-by-default"></a>`extern "C" __declspec(...)` 경고 C4768이 이제 기본적으로 켜짐

이 경고는 Visual Studio 2017 버전 15.3에서 추가되었지만 기본적으로 꺼져 있었습니다. Visual Studio 2017 버전 15.5에서는 이 경고가 기본적으로 켜집니다. 자세한 내용은 [\_\_declspec 특성에 대한 새로운 경고](#declspec)를 참조하세요.

### <a name="defaulted-functions-and-__declspecnothrow"></a>기본값으로 설정된 함수 및 `__declspec(nothrow)`

컴파일러는 이전에 해당 기본/멤버 함수가 예외를 허용할 경우 기본값으로 설정된 함수를 `__declspec(nothrow)`로 선언하도록 허용했습니다. 이 동작은 C++ 표준과 반대되며, 런타임 시 정의되지 않은 동작을 유발할 수 있습니다. 표준에 따라, 예외 사양 불일치가 있을 경우 이러한 함수를 삭제된 것으로 정의해야 합니다.  **/std:c++17** 하에서 다음 모드는 C2280 *삭제된 함수를 참조하려고 합니다. 명시적 예외 사양이 암시적 선언의 명시적 예외 사양과 호환되지 않으므로 함수가 암시적으로 삭제되었습니다.’를 발생시킵니다.*

```cpp
struct A {
    A& operator=(const A& other) { // No exception specification; this function may throw.
        ...
    }
};

struct B : public A {
    __declspec(nothrow) B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1; // error C2280
}
```

이 코드를 수정하려면 기본값으로 설정된 함수에서 __declspec(nothrow)를 제거하거나 `= default`를 제거하고 필요한 모든 예외 처리와 함께 함수에 대한 정의를 제공합니다.

```cpp
struct A {
    A& operator=(const A& other) {
        // ...
    }
};

struct B : public A {
    B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1;
}
```

### <a name="noexcept-and-partial-specializations"></a>**noexcept** 및 부분 특수화

형식 시스템에서 **noexcept**를 사용하면 pointers-to-noexcept-functions에 대한 부분 특수화가 누락되어 일치하는 특정 “호출 가능” 형식이 컴파일되지 않거나 기본 템플릿을 선택하지 못할 수 있습니다.

이러한 경우 **noexcept** 함수 포인터 및 멤버 함수에 대한 **noexcept** 포인터를 처리할 추가 부분 특수화를 추가해야 합니다. 이러한 오버로드는 **/std:c++17** 모드에서만 적합합니다. C++14와 호환성을 유지해야 하고, 다른 사람이 사용할 코드를 작성 중인 경우 `#ifdef` 지시문 내에서 이러한 새 오버로드를 보호해야 합니다. 자체 포함 모듈에서 작업 중인 경우 `#ifdef` 가드를 사용하는 대신 **/Zc:noexceptTypes-** 스위치를 사용하여 컴파일할 수 있습니다.

다음 코드는 **/std:c++14** 하에서 컴파일하지만 "오류 C2027:정의되지 않은 형식 'A\<T>'"와 함께 **/std:c++17** 하에서 실패합니다.

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // C2027
}
```

다음 코드는 컴파일러가 새로운 부분 특수화 `A<void (*)() noexcept>`를 선택하기 때문에 **/std:c++17** 하에서 성공합니다.

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <>
struct A<void(*)() noexcept>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // OK
}
```

## <a name="update_157"></a> 15.7의 버그 수정 및 기타 동작 변경

### <a name="c17-default-argument-in-the-primary-class-template"></a>C++17: 기본 클래스 템플릿의 기본 인수

이 동작 변경은 [클래스 템플릿에 대한 템플릿 인수 추론 - P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)의 사전 조건입니다.

이전에는 컴파일러가 기본 클래스 템플릿의 기본 인수를 무시했습니다.

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int = 0) {} // Re-definition necessary
```

Visual Studio 2017 버전 15.7의 **/std:c++17** 모드에서는 기본 인수가 무시되지 않습니다.

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int) {} // Default argument is used
```

### <a name="dependent-name-resolution"></a>종속 이름 확인

이 동작 변경은 [클래스 템플릿에 대한 템플릿 인수 추론 - P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)의 사전 조건입니다.

다음 예제에서 Visual Studio 15.6 이하 버전의 컴파일러는 기본 클래스 템플릿에서 `D::type`을 `B<T>::type`으로 확인합니다.

```cpp
template<typename T>
struct B {
    using type = T;
};

template<typename T>
struct D : B<T*> {
    using type = B<T*>::type;
};
```

Visual Studio 2017 버전 15.7의 **/std:c++17** 모드에서는 D의 **using** 문에 **typename** 키워드가 필요합니다. **typename**이 없으면 컴파일러가 경고 C4346: *'B<T\*>::type': 종속 이름은 type이 아님* 및 오류 C2061: *구문 오류: 식별자 'type'* 을 발생시킵니다.

```cpp
template<typename T>
struct B {
    using type = T;
};

template<typename T>
struct D : B<T*> {
    using type = typename B<T*>::type;
};
```

### <a name="c17-nodiscard-attribute---warning-level-increase"></a>C++17: `[[nodiscard]]` 특성 - 경고 수준 증가

Visual Studio 2017 버전 15.7의 **/std:c++17** 모드에서 C4834의 경고 레벨("'nodiscard' 특성이 포함된 함수의 반환 값을 버리는 중")은 W3에서 W1로 증가되었습니다. **void**로 캐스트하거나 **/wd:4834**를 컴파일러로 전달하여 경고를 해제할 수 있습니다.

```cpp
[[nodiscard]] int f() { return 0; }

int main() {
    f(); // warning: discarding return value
         // of function with 'nodiscard'
}
```

### <a name="variadic-template-constructor-base-class-initialization-list"></a>Variadic 템플릿 생성자 기본 클래스 초기화 목록

Visual Studio의 이전 버전에서는 템플릿 인수가 누락된 variadic 템플릿 생성자 기본 클래스 초기화 목록이 오류 없이 잘못 허용되었습니다. Visual Studio 2017 버전 15.7에서는 컴파일러 오류가 발생합니다.

Visual Studio 2017 버전 15.7의 다음 코드 예제에서는 *오류 C2614: D\<int>: 잘못된 멤버 초기화: 'B'는 기본 또는 멤버가 아님*이 발생합니다.

```cpp
template<typename T>
struct B {};

template<typename T>
struct D : B<T>
{

    template<typename ...C>
    D() : B() {} // C2614. Missing template arguments to B.
};

D<int> d;
```

오류를 수정하려면 B() 식을 B\<T>()로 변경하세요.

### <a name="constexpr-aggregate-initialization"></a>**constexpr** 집계 초기화

이전 버전의 C++ 컴파일러가 **constexpr** 집계 초기화를 잘못 처리했습니다. aggregate-init-list에 요소가 너무 많은 잘못된 코드를 허용했으며 잘못된 codegen을 생성했습니다. 다음 코드는 이러한 코드의 예제입니다.

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = {
        { 1, 2 },
        { 3, 4 }
    };
    return 0;
}
```

Visual Studio 2017 버전 15.7 업데이트 3 이상에서는 이전 예제에서 현재 ‘C2078 이니셜라이저가 너무 많음’이 발생합니다.  다음 예제는 코드를 수정하는 방법을 보여 줍니다. 중첩된 brace-init-lists를 사용하여 `std::array`를 초기화할 때 내부 배열에 자체 braced-list를 제공합니다.

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = {{ // note double braces
        { 1, 2 },
        { 3, 4 }
    }}; // note double braces
    return 0;
}
```

## <a name="update_158"></a> 15.8의 버그 수정 및 동작 변경

Visual Studio 2017 버전 15.8의 모든 컴파일러 변경 사항은 버그 수정 및 동작 변경의 범주에 속하며, 아래에 나열되어 있습니다.

###<a name="typename-on-unqualified-identifiers"></a>정규화되지 않은 식별자의 **typename**

[/permissive-](../build/reference/permissive-standards-conformance.md) 모드에서는 별칭 템플릿 정의의 정규화되지 않은 식별자에 있는 의사 **typename** 키워드가 컴파일러에서 더 이상 허용되지 않습니다. 이제 C7511 *'T': 'typename' 키워드 뒤에는 정규화된 이름이 와야 합니다* 코드가 생성됩니다.

```cpp
template <typename T>
using  X = typename T;
```

이 오류를 수정하려면 두 번째 줄을 `using  X = T;`로 변경합니다.

### <a name="__declspec-on-right-side-of-alias-template-definitions"></a>별칭 템플릿 정의 오른쪽의 `__declspec()`

[__declspec](../cpp/declspec.md)은 별칭 템플릿 정의의 오른쪽에 더 이상 허용되지 않습니다. 이 코드는 이전에 컴파일러에서 허용되었지만 무시되었으며, 별칭을 사용한 경우에도 사용 중단 경고가 발생하지 않았습니다.

표준 C++ 특성 [\[\[deprecated\]\]](../cpp/attributes.md)를 대신 사용할 수 있으며, Visual Studio 2017 버전 15.6에서 적용됩니다. 이제 C2760 *구문 오류: '__declspec'은 예기치 않은 토큰입니다. 필요한 토큰은 'type specifier'입니다.* 코드가 생성됩니다.

```cpp
template <typename T>
using X = __declspec(deprecated("msg")) T;
```

오류를 수정하려면 코드를 다음으로 변경합니다('=' 별칭 정의 앞에 속성 배치).

```cpp
template <typename T>
using  X [[deprecated("msg")]] = T;
```

### <a name="two-phase-name-lookup-diagnostics"></a>2단계 이름 조회 진단

2단계 이름 조회를 위해서는 템플릿 본문에 사용된 종속되지 않은 이름이 정의 시점에 템플릿에 표시될 수 있어야 합니다. 이전에는 Microsoft C++ 컴파일러가 인스턴스화 시점까지 찾을 수 없는 이름을 조회되지 않는 것으로 남겨 두었습니다. 이제, 종속되지 않은 이름을 템플릿 본문에 바인드해야 합니다.

이것을 나타낼 수 있는 한 가지 방법은 종속 기본 클래스를 조회하는 것입니다. 이전에는 모든 형식이 확인되는 인스턴스화 시간 동안 이름이 조회되었기 때문에 컴파일러가 종속 기본 클래스에 정의된 이름을 사용할 수 있도록 허용했습니다. 이제 해당 코드가 오류로 처리됩니다. 이러한 경우 기본 클래스 형식으로 한정하거나 `this->` 포인터 추가 등으로 종속으로 지정하여 인스턴스화 시점에 변수가 조회되도록 강제 적용할 수 있습니다.

[/permissive-](../build/reference/permissive-standards-conformance.md) 모드에서는 다음 C3861: *'base_value': 식별자를 찾을 수 없습니다.* 코드가 발생합니다.

```cpp
template <class T>
struct Base {
    int base_value = 42;
};

template <class T>
struct S : Base<T> {
    int f() {
        return base_value;
    }
};
```

이 오류를 해결하려면 `return` 문을 `return this->base_value;`로 변경합니다.

**참고:** Boost python 라이브러리에는 오랫동안 [unwind_type.hpp](https://github.com/boostorg/python/blame/develop/include/boost/python/detail/unwind_type.hpp)의 템플릿 정방향 선언에 대한 MSVC 관련 해결 방법이 있었습니다. Visual Studio 2017 버전 15.8(_MSC_VER=1915)부터 [/permissive-](../build/reference/permissive-standards-conformance.md) 모드에서 MSVC 컴파일러가 ADL(인수 종속성 이름 조회)을 올바로 수행하고 다른 컴파일러와 일치하므로 이 해결 방법 보호가 필요 없어졌습니다. ‘C3861: ‘unwind_type’: 식별자를 찾을 수 없습니다.’ 오류를 방지하려면 Boostorg 리포지토리에서 [PR 229](https://github.com/boostorg/python/pull/229)를 참조하여 헤더 파일을 업데이트합니다.  [vcpkg](../build/vcpkg.md) Boost 패키지를 이미 패치했으므로 vcpkg에서 Boost 소스를 가져오거나 업그레이드한 경우 패치를 별도로 적용할 필요가 없습니다.

### <a name="forward-declarations-and-definitions-in-namespace-std"></a>`std` 네임스페이스에서 정방향 선언 및 정의

C++ 표준에서는 사용자가 `std` 네임스페이스에 정방향 선언 또는 정의를 추가할 수 없습니다. `std` 네임스페이스 또는 `std` 네임스페이스 내의 네임스페이스에 선언 또는 정의를 추가하면 정의되지 않은 동작이 발생합니다.

향후 Microsoft는 일부 표준 라이브러리 형식이 정의된 위치를 변경할 예정입니다. 이 변경으로 인해 `std` 네임스페이스에 정방향 선언을 추가하는 기존 코드의 호환성이 손상됩니다. 새로운 경고, C4643을 통해 이러한 소스 문제를 파악할 수 있습니다. 이 경고는 **/default** 모드에서 사용하도록 설정되며 기본적으로 해제되어 있습니다. 이것은 **/Wall** 또는 **/WX**로 컴파일되는 프로그램에 영향을 줍니다.

이제 다음 코드는 C4643: *C++ 표준에서는 네임스페이스 std에서 'vector' 정방향 선언이 허용되지 않습니다*를 생성합니다.

```cpp
namespace std {
    template<typename T> class vector;
}
```

이 오류를 해결하려면 정방향 선언보다는 **include** 지시문을 사용합니다.

```cpp
#include <vector>
```

### <a name="constructors-that-delegate-to-themselves"></a>자신을 위임하는 생성자

C++ 표준에서는 위임하는 생성자가 해당 생성자에 위임하는 경우 컴파일러가 진단을 내보내도록 제안합니다. [/std:c++17](../build/reference/std-specify-language-standard-version.md) 및 [/std:c++latest](../build/reference/std-specify-language-standard-version.md) 모드의 Microsoft C++ 컴파일러는 이제 C7535: *'X::X': 위임하는 생성자는 자신을 호출합니다*를 생성합니다.

이 오류가 없으면 다음 프로그램이 컴파일되지만 무한 루프가 생성됩니다.

```cpp
class X {
public:
    X(int, int);
    X(int v) : X(v){}
};
```

무한 루프를 방지하려면 다른 생성자에 위임합니다.

```cpp
class X {
public:

    X(int, int);
    X(int v) : X(v, 0) {}
};
```

### <a name="offsetof-with-constant-expressions"></a>상수 식을 사용한 `offsetof`

지금까지 [offsetof](../c-runtime-library/reference/offsetof-macro.md)는 [reinterpret_cast](../cpp/reinterpret-cast-operator.md)가 필요한 매크로를 사용하여 구현되었습니다. 이 사용법은 상수 식을 필요로 하는 컨텍스트에서 올바르지 않지만, Microsoft C++ 컴파일러에서는 일반적으로 허용되었습니다. 표준 라이브러리의 일부로 제공되는 `offsetof` 매크로는 컴파일러 내장 함수( **__builtin_offsetof**)를 올바르게 사용하지만, 매크로 트릭을 사용하여 고유한 `offsetof`를 정의하는 사람이 많았습니다.

Visual Studio 2017 버전 15.8에서 컴파일러는 `reinterpret_cast` 연산자가 기본 모드로 표시될 수 있는 영역을 제한하여 코드가 표준 C++ 동작을 준수하도록 합니다. [/permissive-](../build/reference/permissive-standards-conformance.md) 아래에서는 제약 조건이 더욱 엄격합니다. 상수 식이 필요한 위치에 `offsetof`의 결과를 사용하면 C4644 ‘상수 식에 매크로 기반 offsetof 패턴을 사용하는 것은 표준이 아닙니다. 대신 C++ 표준 라이브러리에 정의된 offsetof를 사용하세요.’ 또는 C2975 ‘템플릿 인수가 잘못되었습니다. 컴파일 시간 상수 식이 필요합니다.’라는 경고를 실행하는 코드가 생성될 수 있습니다.  

**/default** 및 **/std:c++17** 모드에서는 C4644가, [/permissive-](../build/reference/permissive-standards-conformance.md) 모드에서는 C2975 코드가 발생합니다.

```cpp
struct Data {
    int x;
};

// Common pattern of user-defined offsetof
#define MY_OFFSET(T, m) (unsigned long long)(&(((T*)nullptr)->m))

int main()

{
    switch (0) {
    case MY_OFFSET(Data, x): return 0;
    default: return 1;
    }
}
```

이 오류를 해결하려면 \<cstddef>를 통해 정의된 대로 `offsetof`를 사용합니다.

```cpp
#include <cstddef>

struct Data {
    int x;
};

int main()
{
    switch (0) {
    case offsetof(Data, x): return 0;
    default: return 1;
    }
}
```

### <a name="cv-qualifiers-on-base-classes-subject-to-pack-expansion"></a>팩 확장의 대상이 되는 기본 클래스의 CV 한정자

이전 버전의 Microsoft C++ 컴파일러는 기본 클래스에 팩 확장도 적용되는 경우 기본 클래스에 cv 한정자가 있음을 검색하지 못했습니다.

Visual Studio 2017 버전 15.8의 [/permissive-](../build/reference/permissive-standards-conformance.md) 모드에서는 C3770 *'const S': 유효한 기본 클래스가 아닙니다.* 코드가 발생합니다.

```cpp
template<typename... T>
class X : public T... { };

class S { };

int main()
{
    X<const S> x;
}
```

### <a name="template-keyword-and-nested-name-specifiers"></a>**template** 키워드 및 중첩된 이름 지정자

[/permissive-](../build/reference/permissive-standards-conformance.md) 모드의 컴파일러에서 이제 종속된 중첩 이름 지정자 뒤에 오는 템플릿 이름을 **template** 키워드로 시작해야 합니다.

[/permissive-](../build/reference/permissive-standards-conformance.md) 모드의 다음 코드에서 이제 C7510: ‘’example’: 종속 템플릿 이름을 사용하는 경우 ‘template’로 시작해야 합니다. 참고: 컴파일되는 클래스 템플릿 인스턴스화 ‘X<T>’에 대한 참조를 확인하세요. 

```cpp
template<typename T> struct Base
{
    template<class U> void example() {}
};

template<typename T>
struct X : Base<T>
{
    void example()
    {
        Base<T>::example<int>();
    }
};
```

이 오류를 해결하려면 다음 예제에서 표시된 대로 **template** 키워드를 `Base<T>::example<int>();` 문에 추가합니다.

```cpp
template<typename T> struct Base
{
    template<class U> void example() {}
};

template<typename T>
struct X : Base<T>
{
    void example()
    {
        // Add template keyword here:
        Base<T>::template example<int>();
    }
};
```

## <a name="update_159"></a> 15.9의 버그 수정 및 동작 변경

### <a name="identifiers-in-member-alias-templates"></a>멤버 별칭 템플릿의 식별자

멤버 별칭 템플릿 정의에서 사용된 식별자를 사용하기 전에 선언해야 합니다.

이전 버전의 컴파일러에서 다음 코드가 허용되었습니다.

```cpp
template <typename... Ts>
struct A
{
  public:
    template <typename U>
    using from_template_t = decltype(from_template(A<U>{}));

  private:
    template <template <typename...> typename Type, typename... Args>
    static constexpr A<Args...> from_template(A<Type<Args...>>);
};

A<>::from_template_t<A<int>> a;
```

Visual Studio 2017 버전 15.9의 [/permissive-](../build/reference/permissive-standards-conformance.md) 모드에서 컴파일러는 C3861: *'from_template': 식별자를 찾을 수 없음*을 발생시킵니다.

오류를 해결하려면 `from_template_t` 전에 `from_template`를 선언합니다.

### <a name="modules-changes"></a>모듈 변경

Visual Studio 2017 버전 15.9에서 컴파일러는 모듈의 명령줄 옵션이 모듈 생성 쪽과 모듈 사용 쪽에서 일치하지 않을 때마다 C5050을 발생시킵니다. 다음 예제에서는 두 가지 문제가 있습니다.

- 사용 쪽(main.cpp)에서 **/EHsc** 옵션을 지정하지 않았습니다.

- C++ 버전이 생성 쪽에서는 **/std:c++17**이고, 사용 쪽에서는 **/std:c++14**입니다.

```cmd
cl /EHsc /std:c++17 m.ixx /experimental:module
cl /experimental:module /module:reference m.ifc main.cpp /std:c++14
```

컴파일러는 다음 두 경우 모두에 대해 C5050을 생성합니다. *경고 C5050: 'm' 모듈을 가져오는 동안 호환되지 않는 환경: C++ 버전이 일치하지 않습니다.  현재 "201402" 모듈 버전 "201703"*

또한 컴파일러는 .ifc 파일이 변조될 때마다 C7536을 발생시킵니다. 모듈 인터페이스의 헤더에는 아래 내용의 SHA2 해시가 포함됩니다. 가져올 때 .ifc 파일을 동일한 방식으로 해시한 다음, 헤더에 제공된 해시와 비교합니다. 해시가 일치하지 않으면 오류 C7536이 발생합니다. *ifc에서 무결성 검사에 실패했습니다.  예상된 SHA2: '66d5c8154df0c71d4cab7665bab4a125c7ce5cb9a401a4d8b461b706ddd771c6'* .

### <a name="partial-ordering-involving-aliases-and-non-deduced-contexts"></a>별칭 및 추론되지 않은 컨텍스트와 관련된 부분 순서

추론되지 않은 컨텍스트에서 별칭을 포함하는 부분 순서 지정 규칙의 구현에 차이가 있습니다. 다음 예제에서 Clang이 코드를 허용하는 반면 [/permissive-](../build/reference/permissive-standards-conformance.md) 모드의 GCC 및 Microsoft C++ 컴파일러는 오류를 발생시킵니다.

```cpp
#include <utility>
using size_t = std::size_t;

template <typename T>
struct A {};
template <size_t, size_t>
struct AlignedBuffer {};
template <size_t len>
using AlignedStorage = AlignedBuffer<len, 4>;

template <class T, class Alloc>
int f(Alloc &alloc, const AlignedStorage<T::size> &buffer)
{
    return 1;
}

template <class T, class Alloc>
int f(A<Alloc> &alloc, const AlignedStorage<T::size> &buffer)
{
    return 2;
}

struct Alloc
{
    static constexpr size_t size = 10;
};

int main()
{
    A<void> a;
    AlignedStorage<Alloc::size> buf;
    if (f<Alloc>(a, buf) != 2)
    {
        return 1;
    }

    return 0;
}
```

이전 예제는 C2668을 발생시킵니다.

```Output
partial_alias.cpp(32): error C2668: 'f': ambiguous call to overloaded function
partial_alias.cpp(18): note: could be 'int f<Alloc,void>(A<void> &,const AlignedBuffer<10,4> &)'
partial_alias.cpp(12): note: or       'int f<Alloc,A<void>>(Alloc &,const AlignedBuffer<10,4> &)'
        with
        [
            Alloc=A<void>
        ]
partial_alias.cpp(32): note: while trying to match the argument list '(A<void>, AlignedBuffer<10,4>)'
```

구현 차이는 C++ 표준의 표현 회귀로 인한 것입니다. 핵심 문제 2235가 해결되면서 이러한 오버로드의 순서를 지정할 수 있는 일부 텍스트가 제거되었습니다. 현재 C++ 표준은 이러한 함수의 순서를 부분적으로 지정하는 메커니즘을 제공하지 않으므로 함수가 모호하다고 여겨집니다.

임시 해결책으로, 이 문제를 해결하는 데 부분 순서 지정을 사용하지 않고 SFINAE를 사용하여 특정 오버로드를 제거하는 것이 좋습니다. 다음 예제에서 `Alloc`가 `A`의 특수화인 경우 `IsA` 도우미 클래스를 사용하여 첫 번째 오버로드를 제거합니다.

```cpp
#include <utility>
using size_t = std::size_t;

template <typename T>
struct A {};
template <size_t, size_t>
struct AlignedBuffer {};
template <size_t len>
using AlignedStorage = AlignedBuffer<len, 4>;

template <typename T> struct IsA : std::false_type {};
template <typename T> struct IsA<A<T>> : std::true_type {};

template <class T, class Alloc, typename = std::enable_if_t<!IsA<Alloc>::value>>
int f(Alloc &alloc, const AlignedStorage<T::size> &buffer)
{
    return 1;
}

template <class T, class Alloc>
int f(A<Alloc> &alloc, const AlignedStorage<T::size> &buffer)
{
    return 2;
}

struct Alloc
{
    static constexpr size_t size = 10;
};

int main()
{
    A<void> a;
    AlignedStorage<Alloc::size> buf;
    if (f<Alloc>(a, buf) != 2)
    {
        return 1;
    }

    return 0;
}
```

### <a name="illegal-expressions-and-non-literal-types-in-templated-function-definitions"></a>템플릿 지정된 함수 정의의 잘못된 식 및 비 리터럴 형식

잘못된 식 및 비 리터럴 형식은 이제 명시적으로 특수화된 템플릿 지정된 함수의 정의에서 바르게 진단됩니다. 이전에는 함수 정의에 대해 이러한 오류를 내보내지 않았습니다. 그러나 잘못된 식 또는 비 리터럴 형식은 상수 식의 일부로 평가되는 경우에 진단됩니다.

이전 버전의 Visual Studio에서 다음 코드는 경고 없이 컴파일됩니다.

```cpp
void g();

template<typename T>
struct S
{
    constexpr void f();
};

template<>
constexpr void S<int>::f()
{
    g(); // C3615 in 15.9
}
```

Visual Studio 2017 버전 15.9에서 다음 코드를 실행하면 이 오류가 발생합니다.

```Output
error C3615: constexpr function 'S<int>::f' cannot result in a constant expression.
note: failure was caused by call of undefined function or one not declared 'constexpr'
note: see usage of 'g'.
```

이 오류를 방지하려면 `f()` 함수의 명시적 인스턴스화에서 **constexpr** 한정자를 제거합니다.

::: moniker-end

::: moniker range="vs-2015"

## <a name="c-conformance-improvements-in-visual-studio-2015"></a>Visual Studio 2015의 C++ 규칙 향상

Visual Studio 2015, 업데이트 3까지 규칙 향상의 전체 목록은 [Visual C++ What's New 2003 through 2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015)(2003부터 2015까지 Visual C++의 새로운 기능)를 참조하세요.

::: moniker-end

## <a name="see-also"></a>참조

[Microsoft C++ 언어 규칙 테이블](../visual-cpp-language-conformance.md)
