---
title: 헤더 파일(C++)
ms.date: 12/11/2019
helpviewer_keywords:
- header files [C++]
ms.openlocfilehash: 4ab6a2b2626cde94f35678bc9ec789b80d493b8f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367236"
---
# <a name="header-files-c"></a>헤더 파일(C++)

변수, 함수, 클래스 등과 같은 프로그램 요소의 이름을 사용하려면 먼저 선언해야 합니다. 예를 들어 먼저 'x'를 선언하지 않고는 쓸 `x = 42` 수 없습니다.

```cpp
int x; // declaration
x = 42; // use x
```

이 선언은 요소가 **int,** **double,** **함수,** **클래스** 또는 다른 요소인지 를 컴파일러에 알려줍니다.  또한 각 이름은 사용되는 모든 .cpp 파일에 직접 또는 간접적으로 선언되어야 합니다. 프로그램을 컴파일할 때 각 .cpp 파일은 컴파일 단위로 독립적으로 컴파일됩니다. 컴파일러는 다른 컴파일 단위에서 선언되는 이름을 알지 못했습니다. 즉, 클래스 또는 함수 또는 전역 변수를 정의하는 경우 클래스 또는 함수 또는 전역 변수를 사용하는 각 추가 .cpp 파일에 해당 변수에 해당 사물의 선언을 제공해야 합니다. 해당 사물의 각 선언은 모든 파일에서 정확히 동일해야 합니다. 링커가 모든 컴파일 단위를 단일 프로그램으로 병합하려고 할 때 약간의 불일치로 인해 오류 또는 의도하지 않은 동작이 발생합니다.

오류 가능성을 최소화하기 위해 C++는 *헤더 파일을* 사용하여 선언을 포함하는 규칙을 채택했습니다. 헤더 파일에서 선언을 한 다음 모든 .cpp 파일 또는 해당 선언이 필요한 다른 헤더 파일에서 #include 지시문을 사용합니다. #include 지시문은 컴파일하기 전에 .cpp 파일에 헤더 파일의 복사본을 직접 삽입합니다.

> [!NOTE]
> Visual Studio 2019에서는 C++20 *모듈* 기능이 헤더 파일을 개선하고 최종 교체하는 기능으로 도입되었습니다. 자세한 내용은 [C++의 모듈 개요를](modules-cpp.md)참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 클래스를 선언 한 다음 다른 소스 파일에서 사용하는 일반적인 방법을 보여 주며 있습니다. 먼저 헤더 파일부터 `my_class.h`시작하겠습니다. 클래스 정의를 포함하지만 정의가 불완전합니다. 멤버 함수가 `do_something` 정의되지 않았습니다.

```cpp
// my_class.h
namespace N
{
    class my_class
    {
    public:
        void do_something();
    };

}
```

다음으로 구현 파일(일반적으로 .cpp 또는 이와 유사한 확장자가 있음)을 만듭니다. 파일을 my_class.cpp라고 부르고 멤버 선언에 대한 정의를 제공합니다. .cpp `#include` 파일의 이 시점에서 my_class 선언을 삽입하기 위해 "my_class.h" 파일에 대한 지시문을 `<iostream>` 추가하고 에 대한 `std::cout`선언을 끌어오기 위해 포함합니다. 따옴표는 소스 파일과 동일한 디렉터리에서 헤더 파일에 사용되며 각도 대괄호는 표준 라이브러리 헤더에 사용됩니다. 또한 많은 표준 라이브러리 헤더에는 .h 또는 다른 파일 확장자가 없습니다.

구현 파일에서 선택적으로 **using** 문을 사용하여 "my_class" 또는 "cout"에 대한 모든 언급을 "N::"또는 "std::"로 한정할 필요가 없습니다.  헤더 파일에 문을 **사용하지** 마십시오!

```cpp
// my_class.cpp
#include "my_class.h" // header in local directory
#include <iostream> // header in standard library

using namespace N;
using namespace std;

void my_class::do_something()
{
    cout << "Doing something!" << endl;
}
```

이제 다른 `my_class` .cpp 파일에서 사용할 수 있습니다. 컴파일러가 선언을 가져오게 되도록 헤더 파일을 #include. 컴파일러가 알아야 할 모든 것은 my_class `do_something()`라는 공용 멤버 함수가 있는 클래스입니다.

```cpp
// my_program.cpp
#include "my_class.h"

using namespace N;

int main()
{
    my_class mc;
    mc.do_something();
    return 0;
}
```

컴파일러가 각 .cpp 파일을 .obj 파일로 컴파일한 후 .obj 파일을 링커에 전달합니다. 링커가 개체 파일을 병합하면 my_class 대한 정의가 정확히 하나 있습니다. my_class.cpp용으로 생성된 .obj 파일에 있으며 빌드가 성공합니다.

## <a name="include-guards"></a>가드 포함

일반적으로 헤더 파일에는 단일 .cpp 파일에 여러 번 삽입되지 않도록 하는 *포함 가드* 또는 `#pragma once` 지시문이 있습니다.

```cpp
// my_class.h
#ifndef MY_CLASS_H // include guard
#define MY_CLASS_H

namespace N
{
    class my_class
    {
    public:
        void do_something();
    };
}

#endif /* MY_CLASS_H */
```

## <a name="what-to-put-in-a-header-file"></a>헤더 파일에 넣을 내용

헤더 파일은 여러 파일에 포함될 수 있으므로 동일한 이름의 여러 정의를 생성할 수 있는 정의를 포함할 수 없습니다. 다음은 허용되지 않거나 매우 나쁜 관행으로 간주됩니다.

- 네임스페이스 또는 전역 범위에서 기본 제공 형식 정의
- 비인라인 함수 정의
- 비 const 변수 정의
- 집계 정의
- 명명되지 않은 네임스페이스
- using 지시문

**using** 지시문을 사용하면 반드시 오류가 발생할 필요는 없지만 해당 헤더를 직접 또는 간접적으로 포함하는 모든 .cpp 파일의 범위로 네임스페이스를 가져오기 때문에 문제가 발생할 수 있습니다.

## <a name="sample-header-file"></a>샘플 헤더 파일

다음 예제에서는 헤더 파일에 허용되는 다양한 종류의 선언 및 정의를 보여 주며 있습니다.

```cpp
// sample.h
#pragma once
#include <vector> // #include directive
#include <string>

namespace N  // namespace declaration
{
    inline namespace P
    {
        //...
    }

    enum class colors : short { red, blue, purple, azure };

    const double PI = 3.14;  // const and constexpr definitions
    constexpr int MeaningOfLife{ 42 };
    constexpr int get_meaning()
    {
        static_assert(MeaningOfLife == 42, "unexpected!"); // static_assert
        return MeaningOfLife;
    }
    using vstr = std::vector<int>;  // type alias
    extern double d; // extern variable

#define LOG   // macro definition

#ifdef LOG   // conditional compilation directive
    void print_to_log();
#endif

    class my_class   // regular class definition,
    {                // but no non-inline function definitions

        friend class other_class;
    public:
        void do_something();   // definition in my_class.cpp
        inline void put_value(int i) { vals.push_back(i); } // inline OK

    private:
        vstr vals;
        int i;
    };

    struct RGB
    {
        short r{ 0 };  // member initialization
        short g{ 0 };
        short b{ 0 };
    };

    template <typename T>  // template definition
    class value_store
    {
    public:
        value_store<T>() = default;
        void write_value(T val)
        {
            //... function definition OK in template
        }
    private:
        std::vector<T> vals;
    };

    template <typename T>  // template declaration
    class value_widget;
}
```
