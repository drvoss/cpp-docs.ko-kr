---
title: :::no-loc(constexpr):::(C++)
description: 'C + + 언어 키워드에 대 한 지침 :::no-loc(constexpr)::: 입니다.'
ms.date: 01/28/2020
f1_keywords:
- :::no-loc(constexpr):::_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
no-loc:
- ':::no-loc(constexpr):::'
- ':::no-loc(const):::'
- ':::no-loc(inline):::'
- ':::no-loc(goto):::'
- ':::no-loc(try):::'
- ':::no-loc(if):::'
- ':::no-loc(switch):::'
- ':::no-loc(for):::'
- ':::no-loc(while):::'
ms.openlocfilehash: d66dc333b7ac9fba94221dc4efa723c7919ef88f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229027"
---
# <a name="no-locconstexpr-c"></a>:::no-loc(constexpr):::(C++)

키워드는 c + + **`:::no-loc(constexpr):::`** 11에서 도입 되었으며 c + + 14에서 향상 되었습니다. 이것은 * :::no-loc(const)::: ant 식*입니다. 마찬가지로 **`:::no-loc(const):::`** 변수에 적용할 수 있습니다. 코드에서 값을 mod로 시도 하면 컴파일러 오류가 발생 :::no-loc(if)::: 합니다. 와 달리 **`:::no-loc(const):::`** 는 **`:::no-loc(constexpr):::`** 함수와 클래스 ructors에도 적용 될 수 있습니다 :::no-loc(const)::: . **`:::no-loc(constexpr):::`** 값 또는 반환 값이 :::no-loc(const)::: ant 이며 가능 하면 컴파일 시간에 계산 됨을 나타냅니다.

**`:::no-loc(constexpr):::`** 정수 값은 :::no-loc(const)::: 템플릿 인수 및 배열 선언과 같이 정수를 필요로 하는 모든 곳에서 사용할 수 있습니다. 런타임 대신 컴파일 시간에 값을 계산 하는 경우에는 프로그램을 더 빠르게 실행 하 고 메모리를 절약 하는 데 도움이 됩니다.

컴파일 시간 :::no-loc(const)::: ant 계산의 복잡성 및 컴파일 시간에 대 한 잠재적 영향을 제한 하려면 c + + 14 표준에서 ant 식의 형식이 :::no-loc(const)::: [리터럴 형식](trivial-standard-layout-and-pod-types.md#literal_types)이어야 합니다.

## <a name="syntax"></a>구문

> **`:::no-loc(constexpr):::`***리터럴 형식의* *ident :::no-loc(if)::: * **=** * :::no-loc(const)::: 식 ant-식* **;**\
> **`:::no-loc(constexpr):::`***리터럴 형식* *ident :::no-loc(if)::: * **{** * :::no-loc(const)::: ant-expression* **}** **;**\
> **`:::no-loc(constexpr):::`***리터럴 형식* *ident :::no-loc(if)::: * **(** *params* **)** **;**\
> **`:::no-loc(constexpr):::`***ctor* **(** *params* **)** **;**

## <a name="parameters"></a>매개 변수

*params*\
하나 이상의 매개 변수입니다. 각 매개 변수는 리터럴 형식 이어야 하며 그 자체가 ant 식일 수 있어야 합니다 :::no-loc(const)::: .

## <a name="return-value"></a>반환 값

**`:::no-loc(constexpr):::`** 변수나 함수는 [리터럴 형식을](trivial-standard-layout-and-pod-types.md#literal_types)반환 해야 합니다.

## <a name="no-locconstexpr-variables"></a>:::no-loc(constexpr)::: 변수

:::no-loc(if):::및 변수 간의 주 d f)은 런타임까지 **`:::no-loc(const):::`** **`:::no-loc(constexpr):::`** 변수 초기화가 **`:::no-loc(const):::`** 지연 될 수 있다는 것입니다. **`:::no-loc(constexpr):::`** 변수는 컴파일 타임에 초기화 되어야 합니다.  모든 **`:::no-loc(constexpr):::`** 변수는 **`:::no-loc(const):::`** 입니다.

- 변수는 **`:::no-loc(constexpr):::`** 리터럴 형식이 있고 초기화 될 때를 사용 하 여 선언할 수 있습니다. 초기화가 ructor에 의해 med-v 당 인 경우 :::no-loc(for)::: :::no-loc(const)::: ructor를 :::no-loc(const)::: 로 선언 해야 합니다 **`:::no-loc(constexpr):::`** .

- 참조는 두 조건이 모두 충족 되는 경우로 선언할 수 있습니다 **`:::no-loc(constexpr):::`** . 참조 된 개체가 ant 식에 의해 초기화 되 :::no-loc(const)::: 고 초기화 중에 호출 되는 모든 암시적 변환도 :::no-loc(const)::: ant 식입니다.

- **`:::no-loc(constexpr):::`** 변수 또는 함수의 모든 선언에는 spec이 있어야 **`:::no-loc(constexpr):::`** 합니다 :::no-loc(if)::: .

```cpp
:::no-loc(constexpr)::: float x = 42.0;
:::no-loc(constexpr)::: float y{108};
:::no-loc(constexpr)::: float z = exp(5, 3);
:::no-loc(constexpr)::: int i; // Error! Not initialized
int j = 0;
:::no-loc(constexpr)::: int k = j + 1; //Error! j not a :::no-loc(const):::ant expression
```

## <a name="no-locconstexpr-functions"></a><a name=":::no-loc(constexpr):::_functions"></a>:::no-loc(constexpr):::함수

**`:::no-loc(constexpr):::`** 함수는 코드를 사용 하는 경우 컴파일 시간에 반환 값이 계산할 수 함수입니다. 코드를 사용 하려면 컴파일 시간에 변수를 초기화 하기 위한 반환 값 **`:::no-loc(constexpr):::`** 이 필요 하거나 비 형식 템플릿 인수를 제공 해야 합니다. 인수가 **`:::no-loc(constexpr):::`** 값인 경우 **`:::no-loc(constexpr):::`** 함수는 컴파일 타임 ant를 생성 :::no-loc(const)::: 합니다. 인수가 아닌를 사용 하 여 호출 **`:::no-loc(constexpr):::`** 하거나 컴파일 타임에 해당 값이 필요 하지 않은 경우 일반 함수 처럼 런타임에 값을 생성 합니다. 이 이중 동작을 통해 동일한 함수를 작성 하 **`:::no-loc(constexpr):::`** 고 버전이 아닌 것을 방지할 수 있습니다 **`:::no-loc(constexpr):::`** .

**`:::no-loc(constexpr):::`** 함수나 :::no-loc(const)::: ructor는 암시적 **`:::no-loc(inline):::`** 입니다.

함수에 적용 되는 규칙은 :::no-loc(constexpr)::: 다음과 같습니다.

- **`:::no-loc(constexpr):::`** 함수는 [리터럴 형식만](trivial-standard-layout-and-pod-types.md#literal_types)수락 하 고 반환 해야 합니다.

- **`:::no-loc(constexpr):::`** 함수는 재귀적 일 수 있습니다.

- [가상](../cpp/virtual-cpp.md)일 수 없습니다. :::no-loc(const):::Ructor는 **`:::no-loc(constexpr):::`** 바깥쪽 클래스에 가상 기본 클래스가 있는 경우로 정의할 수 없습니다.

- 본문은 `= default` 또는 `= delete`로 정의할 수 있습니다.

- 본문은 문이나 블록을 포함할 수 없습니다 **`:::no-loc(goto):::`** **`:::no-loc(try):::`** .

- 비템플릿의 명시적 특수화는 **`:::no-loc(constexpr):::`** 다음과 같이 선언할 수 있습니다 **`:::no-loc(constexpr):::`** .

- 또한 템플릿의 명시적 특수화는 **`:::no-loc(constexpr):::`** 다음과 같을 필요가 없습니다 **`:::no-loc(constexpr):::`** .

다음 규칙은 **`:::no-loc(constexpr):::`** Visual Studio 2017 이상 버전의 함수에 적용 됩니다.

- **`:::no-loc(if):::`** 및 **`:::no-loc(switch):::`** 문과 **`:::no-loc(for):::`** , 범위 기반 **`:::no-loc(for):::`** , **`:::no-loc(while):::`** 및 **do :::no-loc(while)::: **를 비롯 한 모든 루핑 문을 포함할 수 있습니다.

- 지역 변수 선언을 포함할 수 있지만 변수를 초기화 해야 합니다. 리터럴 형식 이어야 하며, 또는 스레드 로컬이 될 수 없습니다 **`static`** . 로컬로 선언 된 변수는 일 필요는 **`:::no-loc(const):::`** 없으며 변경할 수도 있습니다.

- 비멤버 함수는 암시적이 지 않아도 **`:::no-loc(constexpr):::`** **`static`** 됩니다 **`:::no-loc(const):::`** .

```cpp
:::no-loc(constexpr)::: float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Visual Studio 디버거에서는 최적화 되지 않은 디버그 빌드를 디버그할 때 **`:::no-loc(constexpr):::`** 함수 안에 중단점을 배치 하 여 컴파일 시간에 함수가 계산 되는지 여부를 확인할 수 있습니다. 중단점을 적중할 경우 함수가 런타임에 호출되었습니다.  그렇지 않을 경우 함수가 컴파일 타임에 호출되었습니다.

## <a name="extern-no-locconstexpr"></a>시키거나:::no-loc(constexpr):::

[/Zc: externConstexpr](../build/reference/zc-extern:::no-loc(constexpr):::.md) 컴파일러 옵션을 사용 하면 컴파일러가 ** :::no-loc(constexpr)::: extern **을 사용 하 여 선언 된 변수에 [외부 링크](../c-language/external-linkage.md) 를 적용 합니다. 이전 버전의 Visual Studio에서는 기본적으로 또는 **/zc: externConstexpr-** 가 spec 인 경우 :::no-loc(if)::: 키워드가 사용 되는 경우에도 visual studio에서 변수에 내부 링크를 적용 **`:::no-loc(constexpr):::`** **`extern`** 합니다. **/Zc: externConstexpr** 옵션은 Visual Studio 2017 업데이트 15.6부터 사용할 수 있으며 기본적으로 해제 되어 있습니다. [/Permissive-](../build/reference/permissive-standards-con:::no-loc(for):::mance.md) 옵션은 **/zc: externConstexpr**를 사용 하지 않습니다.

## <a name="example"></a>예제

다음 예에서는 **`:::no-loc(constexpr):::`** 변수, 함수 및 사용자 정의 형식을 보여 줍니다. 의 마지막 문에서 `main()` **`:::no-loc(constexpr):::`** 멤버 함수는 `GetValue()` 컴파일 시간에 값을 알 필요가 없기 때문에 런타임 호출입니다.

```cpp
// :::no-loc(constexpr):::.cpp
// Compile with: cl /EHsc /W4 :::no-loc(constexpr):::.cpp
#include <iostream>

using namespace std;

// Pass by value
:::no-loc(constexpr)::: float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};

// Pass by reference
:::no-loc(constexpr)::: float exp2(:::no-loc(const)::: float& x, :::no-loc(const)::: int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
};

// Compile-time computation of array length
template<typename T, int N>
:::no-loc(constexpr)::: int length(:::no-loc(const)::: T(&)[N])
{
    return N;
}

// Recursive :::no-loc(constexpr)::: function
:::no-loc(constexpr)::: int fac(int n)
{
    return n == 1 ? 1 : n * fac(n - 1);
}

// User-defined type
class Foo
{
public:
    :::no-loc(constexpr)::: explicit Foo(int i) : _i(i) {}
    :::no-loc(constexpr)::: int GetValue() :::no-loc(const):::
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    // foo is :::no-loc(const)::::
    :::no-loc(constexpr)::: Foo foo(5);
    // foo = Foo(6); //Error!

    // Compile time:
    :::no-loc(constexpr)::: float x = exp(5, 3);
    :::no-loc(constexpr)::: float y { exp(2, 5) };
    :::no-loc(constexpr)::: int val = foo.GetValue();
    :::no-loc(constexpr)::: int f5 = fac(5);
    :::no-loc(const)::: int nums[] { 1, 2, 3, 4 };
    :::no-loc(const)::: int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    // Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;
}
```

## <a name="requirements"></a>요구 사항

Visual Studio 2015 이상.

## <a name="see-also"></a>참고 항목

[선언 및 정의](../cpp/declarations-and-definitions-cpp.md)\
[:::no-loc(const):::](../cpp/:::no-loc(const):::-cpp.md)
