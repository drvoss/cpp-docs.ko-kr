---
title: constexpr(C++)
description: C++ Language constexpr 키워드에 대 한 지침입니다.
ms.date: 01/28/2020
f1_keywords:
- constexpr_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
no-loc:
- constexpr
- const
- inline
- goto
- try
- if
- switch
- for
- while
ms.openlocfilehash: 4f34eef3217377ab50a2d80d42b5bea4b054c5be
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821781"
---
# <a name="opno-locconstexpr-c"></a>constexpr(C++)

**constexpr** 키워드는 c + + 11에서 도입 되었으며 c + + 14에서 향상 되었습니다. *상수 식*을 뜻합니다. **const** 와 같이 변수에 적용할 수 있습니다. 코드에서 값을 수정 하려고 하면 컴파일러 오류가 발생 합니다. **const** 와 달리 **constexpr** 는 함수와 클래스 생성자에도 적용 될 수 있습니다. **constexpr** 값 또는 반환 값이 상수이 고 가능 하면 컴파일 시간에 계산 됨을 나타냅니다.

**constexpr** 정수 계열 값은 템플릿 인수 및 배열 선언과 같이 const 정수가 필요한 모든 곳에서 사용할 수 있습니다. 런타임 대신 컴파일 시간에 값을 계산 하는 경우에는 프로그램을 더 빠르게 실행 하 고 메모리를 절약 하는 데 도움이 됩니다.

컴파일 시간 상수 계산의 복잡성 및 컴파일 시간에 대 한 잠재적 영향을 제한 하기 위해 c + + 14 표준에서는 상수 식의 형식이 [리터럴 형식](trivial-standard-layout-and-pod-types.md#literal_types)이어야 합니다.

## <a name="syntax"></a>구문

> *상수 식* **=** *리터럴 형식* *식별자* 를 **constexpr** \
> *리터럴 형식* *식별자* **{** *상수 식* **}** **;** 을 (를)constexpr\
> **constexpr** *리터럴 형식* *식별자* **(** *params* **)** **;** \
> **constexpr** *ctor* **(** *params* **)** **;**

## <a name="parameters"></a>매개 변수

*params*\
하나 이상의 매개 변수입니다. 각 매개 변수는 리터럴 형식 이어야 하며 자체적으로 상수 식 이어야 합니다.

## <a name="return-value"></a>반환 값

**constexpr** 변수나 함수는 [리터럴 형식을](trivial-standard-layout-and-pod-types.md#literal_types)반환 해야 합니다.

## <a name="opno-locconstexpr-variables"></a>constexpr 변수

**const** 와 **constexpr** 변수 간의 주요 차이점은 **const** 변수 초기화가 런타임까지 지연 될 수 있다는 것입니다. 컴파일 시간에 **constexpr** 변수를 초기화 해야 합니다.  모든 **constexpr** 변수가 **const** 됩니다.

- 리터럴 형식이 있고 초기화 되는 경우 **constexpr** 를 사용 하 여 변수를 선언할 수 있습니다. 생성자가 초기화를 수행 하는 경우 생성자를 **constexpr** 으로 선언 해야 합니다.

- 두 조건이 모두 충족 되는 경우 참조를 **constexpr** 로 선언할 수 있습니다. 참조 된 개체가 상수 식으로 초기화 되 고 초기화 중에 호출 되는 모든 암시적 변환은 상수 식일 수도 있습니다.

- **constexpr** 변수 또는 함수의 모든 선언에는 **constexpr** 지정 자가 있어야 합니다.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a>constexpr 함수

**constexpr** 함수는 코드를 사용 하는 데 필요한 반환 값이 컴파일 타임에 계산할 수 함수입니다. 코드를 사용 하려면 컴파일 시간에 **constexpr** 변수를 초기화 하거나 형식이 아닌 템플릿 인수를 제공 하는 반환 값이 필요 합니다. 인수가 **constexpr** 값 이면 **constexpr** 함수는 컴파일 시간 상수를 생성 합니다. **constexpr** 되지 않은 인수를 사용 하 여 호출 하거나 컴파일 시간에 해당 값이 필요 하지 않은 경우 일반 함수 처럼 런타임에 값을 생성 합니다. 이 이중 동작을 통해 동일한 함수의 **constexpr** 및 **constexpr** 되지 않은 버전을 작성할 필요가 없습니다.

**constexpr** 함수 또는 생성자는 암시적으로 **inline** .

constexpr 함수에 적용 되는 규칙은 다음과 같습니다.

- **constexpr** 함수는 [리터럴 형식만](trivial-standard-layout-and-pod-types.md#literal_types)수락 하 고 반환 해야 합니다.

- **constexpr** 함수는 재귀적 일 수 있습니다.

- [가상](../cpp/virtual-cpp.md)일 수 없습니다. 바깥쪽 클래스에 가상 기본 클래스가 있으면 생성자를 **constexpr** 으로 정의할 수 없습니다.

- 본문은 `= default` 또는 `= delete`로 정의할 수 있습니다.

- 본문은 **goto** 문이나 **try** 블록을 포함할 수 없습니다.

- **constexpr** 되지 않은 템플릿의 명시적 특수화는 **constexpr** 으로 선언할 수 있습니다.

- **constexpr** 템플릿의 명시적 특수화도 **constexpr** 필요가 없습니다.

다음 규칙은 Visual Studio 2017 이상에서 **constexpr** 함수에 적용 됩니다.

- 여기에는 **if** 및 **switch** 문과 **for** , 범위 기반 **for** , **while** 및 **dowhile** 를 비롯 한 모든 루핑 문이 포함 될 수 있습니다.

- 지역 변수 선언을 포함할 수 있지만 변수를 초기화 해야 합니다. 리터럴 형식 이어야 하며 **정적** 또는 스레드 로컬 일 수 없습니다. 로컬로 선언 된 변수는 **const** 필요 하지 않으며 변경할 수 있습니다.

- **constexpr** **비정적** 멤버 함수는 암시적으로 **const** 필요가 없습니다.

```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Visual Studio 디버거에서는 최적화 되지 않은 디버그 빌드를 디버그할 때 컴파일 타임에 중단점을 배치 하 여 **constexpr** 함수를 평가할지 여부를 확인할 수 있습니다. 중단점을 적중할 경우 함수가 런타임에 호출되었습니다.  그렇지 않을 경우 함수가 컴파일 타임에 호출되었습니다.

## <a name="extern-opno-locconstexpr"></a>extern constexpr

[/Zc: externConstexpr](../build/reference/zc-externconstexpr.md) 컴파일러 옵션을 사용 하면 컴파일러가 **extern constexpr** 를 사용 하 여 선언 된 변수에 [외부 링크](../c-language/external-linkage.md) 를 적용 합니다. 이전 버전의 Visual Studio에서는 기본적으로 또는 **/zc: externConstexpr-** 가 지정 된 경우 **extern** 키워드가 사용 되는 경우에도 visual studio에서 **constexpr** 변수에 내부 링크를 적용 합니다. **/Zc: externConstexpr** 옵션은 Visual Studio 2017 업데이트 15.6부터 사용할 수 있으며 기본적으로 해제 되어 있습니다. [/Permissive-](../build/reference/permissive-standards-conformance.md) 옵션은 **/zc: externConstexpr**를 사용 하지 않습니다.

## <a name="example"></a>예

다음 예에서는 **constexpr** 변수, 함수 및 사용자 정의 형식을 보여 줍니다. `main()`의 마지막 문에서 **constexpr** 멤버 함수 `GetValue()`는 컴파일 타임에 값을 알 필요가 없기 때문에 런타임 호출입니다.

```cpp
// constexpr.cpp
// Compile with: cl /EHsc /W4 constexpr.cpp
#include <iostream>

using namespace std;

// Pass by value
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};

// Pass by reference
constexpr float exp2(const float& x, const int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
};

// Compile-time computation of array length
template<typename T, int N>
constexpr int length(const T(&)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n * fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue() const
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    // foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    // Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    // Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;
}
```

## <a name="requirements"></a>요구 사항

Visual Studio 2015 이상.

## <a name="see-also"></a>참조

[선언 및 정의](../cpp/declarations-and-definitions-cpp.md)\
[const](../cpp/const-cpp.md)
