---
title: 타원 및 변종 템플릿
ms.date: 11/04/2016
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
ms.openlocfilehash: 8326a6b9e75db6adc37a68aa5d5741b004d27d30
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031526"
---
# <a name="ellipsis-and-variadic-templates"></a>타원 및 변종 템플릿

이 문서에서는 C++ variadic 템플릿을 사용하여 타원()을`...`사용하는 방법을 보여 주며, 타원은 C와 C ++에서 많은 용도를 가졌습니다. 여기에는 함수에 대한 변수 인수 목록이 포함됩니다. C `printf()` 런타임 라이브러리의 함수는 가장 잘 알려진 예제 중 하나입니다.

*variadic 템플릿은* 임의의 수의 인수를 지원하는 클래스 또는 함수 템플릿입니다. 이 메커니즘은 클래스 템플릿과 함수 템플릿 모두에 적용할 수 있으므로 C++ 라이브러리 개발자에게 특히 유용하며, 따라서 다양한 형식 안전 및 비사소한 기능및 유연성을 제공합니다.

## <a name="syntax"></a>구문

타원은 variadic 템플릿에 의해 두 가지 방법으로 사용됩니다. 매개 변수 이름의 왼쪽에 매개 변수 *팩을*의미 하 고 매개 변수 이름의 오른쪽에 매개 변수 팩을 별도 이름으로 확장 합니다.

다음은 *variadic 템플릿 클래스* 정의 구문의 기본 예입니다.

```cpp
template<typename... Arguments> class classname;
```

팩 및 확장 매개 변수의 경우 다음 예에서 같이 기본 설정에 따라 줄임표 주위에 공백을 추가할 수 있습니다.

```cpp
template<typename ...Arguments> class classname;
```

또는 다음을 사용하세요.

```cpp
template<typename ... Arguments> class classname;
```

이 문서에서는 첫 번째 예제에 표시된 규칙(줄임표가 `typename`에 연결)을 사용합니다.

앞의 예제에서 *인수는* 매개 변수 팩입니다. 클래스는 `classname` 다음과 같은 예에서와 같이 가변 수의 인수를 허용할 수 있습니다.

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
vtclass<long, std::vector<int>, std::string> vtinstance4;
```

variadic 템플릿 클래스 정의를 사용 하 여 하나 이상의 매개 변수를 요구할 수도 있습니다.

```cpp
template <typename First, typename... Rest> class classname;
```

다음은 *variadic 템플릿 함수* 구문의 기본 예입니다.

```cpp
template <typename... Arguments> returntype functionname(Arguments... args);
```

그런 다음 다음 섹션인 **variadic 템플릿 이해에**표시된 것처럼 *인수* 매개 변수 팩이 확장되어 사용이 확장됩니다.

다음과 같은 다른 형태의 다양한 템플릿 함수 구문이 가능합니다.

```cpp
template <typename... Arguments> returntype functionname(Arguments&... args);
template <typename... Arguments> returntype functionname(Arguments&&... args);
template <typename... Arguments> returntype functionname(Arguments*... args);
```

**const와** 같은 지정자도 허용됩니다.

```cpp
template <typename... Arguments> returntype functionname(const Arguments&... args);
```

variadic 템플릿 클래스 정의와 마찬가지로 하나 이상의 매개 변수가 필요한 함수를 만들 수 있습니다.

```cpp
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);
```

Variadic 템플릿은 `sizeof...()` 연산자(이전 `sizeof()` 연산자와 관련이 없음)를 사용합니다.

```cpp
template<typename... Arguments>
void tfunc(const Arguments&... args)
{
    constexpr auto numargs{ sizeof...(Arguments) };

    X xobj[numargs]; // array of some previously defined type X

    helper_func(xobj, args...);
}
```

## <a name="more-about-ellipsis-placement"></a>줄임표 배치에 대한 자세한 내용

이 문서의 앞 부분에서 "매개 변수 이름의 왼쪽은 매개 변수 팩을 나타내고 매개 변수 이름 오른쪽은 매개 변수 팩을 별도의 이름으로 확장"한다고 매개 변수 팩과 확장을 정의하는 줄임표 배치에 대해 설명했습니다. 이는 기술적으로는 맞지만 코드로 변환할 때 혼동될 수 있습니다. 고려 사항:

- 템플릿 매개 변수 목록`template <parameter-list>`()에서 `typename...` 템플릿 매개 변수 팩을 소개합니다.

- 매개 변수-선언-절`func(parameter-list)`() 에서 "최상위" 타원은 함수 매개 변수 팩을 도입하고 타원 위치는 중요합니다.

    ```cpp
    // v1 is NOT a function parameter pack:
    template <typename... Types> void func1(std::vector<Types...> v1);

    // v2 IS a function parameter pack:
    template <typename... Types> void func2(std::vector<Types>... v2);
    ```

- 매개 변수 이름 바로 뒤에 줄임표가 표시된 경우 매개 변수 팩 확장이 있는 것입니다.

## <a name="example"></a>예제

variadic 템플릿 함수 메커니즘을 설명하는 좋은 방법은 `printf`다음 기능 중 일부를 다시 쓰는 데 사용하는 것입니다.

```cpp
#include <iostream>

using namespace std;

void print() {
    cout << endl;
}

template <typename T> void print(const T& t) {
    cout << t << endl;
}

template <typename First, typename... Rest> void print(const First& first, const Rest&... rest) {
    cout << first << ", ";
    print(rest...); // recursive call using pack expansion syntax
}

int main()
{
    print(); // calls first overload, outputting only a newline
    print(1); // calls second overload

    // these call the third overload, the variadic template,
    // which uses recursion as needed.
    print(10, 20);
    print(100, 200, 300);
    print("first", 2, "third", 3.14159);
}
```

## <a name="output"></a>출력

```Output
1
10, 20
100, 200, 300
first, 2, third, 3.14159
```

> [!NOTE]
> variadic 템플릿 함수를 통합하는 대부분의 구현은 일부 형식의 재귀화를 사용하지만 기존의 재귀와는 약간 다릅니다.  기존의 재귀에는 동일한 서명을 사용하여 자체를 호출하는 함수가 포함됩니다. 오버로드되거나 템플릿화될 수 있지만 매번 동일한 서명이 선택됩니다. Variadic 재귀는 다른 (거의 항상 감소) 인수 수를 사용하여 variadic 함수 템플릿을 호출하여 매번 다른 서명을 스탬핑하는 것을 포함합니다. "기본 케이스"는 여전히 필요하지만 재귀의 특성은 다릅니다.
