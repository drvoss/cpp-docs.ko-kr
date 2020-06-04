---
title: 사용자 정의 형식 변환(C++)
ms.date: 11/04/2016
f1_keywords:
- explicit_cpp
helpviewer_keywords:
- constructors [C++], and constants
- conversion functions [C++]
- explicit keyword [C++]
- type conversion
- constructors [C++], drawbacks
- conversion constructors
- type conversion [C++], explicit conversion
- coercion [C++]
- conversions [C++], explicit
- objects [C++], converting
- conversion functions [C++], rules for declaring
- declaring functions [C++], conversion functions
- functions [C++], conversion
- converting objects
- constructors [C++], conversion
- conversions [C++], by constructors
- data type conversion [C++], explicit
ms.assetid: d40e4310-a190-4e95-a34c-22c5c20aa0b9
ms.openlocfilehash: e74d5b3a748a9aab22a6a9d83c4d6c4bd3379df4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374690"
---
# <a name="user-defined-type-conversions-c"></a>사용자 정의 형식 변환(C++)

*변환은* 다른 형식의 값에서 일부 형식의 새 값을 생성합니다. *표준 변환은* C++ 언어에 기본 제공되며 기본 제공 형식을 지원하며 *사용자 정의 변환을* 만들어 사용자 정의 형식간 변환을 수행할 수 있습니다.

표준 변환은 기본 제공 형식 간의 변환, 상속별로 관련된 형식에 대한 포인터 또는 참조 간의 변환, void 포인터와의 양방향 변환, null 포인터로의 변환을 수행합니다. 자세한 내용은 [표준 변환 을](../cpp/standard-conversions.md)참조하십시오. 사용자 정의 변환은 사용자 정의 형식 간의 변환이나 사용자 정의 형식과 기본 제공 형식 간의 변환을 수행합니다. [변환 생성자](#ConvCTOR) 또는 [변환 함수로 구현할](#ConvFunc)수 있습니다.

변환은 명시적으로(프로그래머가 형식을 다른 형식으로 변환하기 위해 호출하는 경우 캐스트 또는 직접 초기화에서) 수행하거나 암시적으로(언어나 프로그램에서 프로그래머가 지정한 형식 이외의 다른 형식에 대해 호출하는 경우) 수행할 수 있습니다.

다음과 같은 경우에 암시적 변환이 시도됩니다.

- 함수에 제공된 인수의 형식이 일치하는 매개 변수의 형식과 다릅니다.

- 함수에서 반환된 값의 형식이 함수 반환 형식과 다릅니다.

- 이니셜라이저 식의 형식이 초기화되는 개체의 형식과 다릅니다.

- 조건 문, 루프 구문 또는 스위치를 제어하는 식의 결과 형식이 이러한 제어에 필요한 결과 형식이 아닙니다.

- 연산자에 제공된 피연산자의 형식이 일치하는 피연산자 매개 변수의 형식과 다릅니다. 기본 제공 연산자의 경우 양쪽 피연산자는 같은 형식이어야 하며 양쪽 피연산자를 나타낼 수 있는 공용 형식으로 변환됩니다. 자세한 내용은 [표준 변환 을](standard-conversions.md)참조하십시오. 사용자 정의 연산자의 경우 각 피연산자는 일치하는 피연산자 매개 변수와 같은 형식이어야 합니다.

한 개의 표준 변환이 암시적 변환을 완료할 수 없는 경우 컴파일러는 사용자 정의 변환을 사용하여(필요에 따라 표준 변환을 추가적으로 수행하여) 암시적 변환을 완료할 수 있습니다.

변환 사이트에 동일한 변환을 수행하는 사용자 정의 변환이 둘 이상 있는 경우에는 변환이 모호합니다. 이러한 모호성은 컴파일러가 어떤 변환을 선택해야 할지 결정할 수 없으므로 오류입니다. 하지만 사용 가능한 변환 집합은 소스 코드의 여러 위치에서 다르게 사용될 수 있으므로(예: 소스 파일에 포함된 헤더 파일에 따라) 동일한 변환을 수행하는 여러 방법을 정의하는 경우라면 이러한 모호성은 오류는 아닙니다. 변환 사이트에 사용 가능한 변환이 하나만 있다면 모호성이 없습니다. 모호한 변환은 여러 가지 경우에 발생될 수 있지만 가장 일반적인 경우는 다음과 같습니다.

- 다중 상속. 변환이 둘 이상의 기본 클래스에서 정의됩니다.

- 모호한 함수 호출. 변환이 대상 형식의 변환 생성자 및 소스 형식의 변환 함수로 정의됩니다. 자세한 내용은 [변환 함수를](#ConvFunc)참조하십시오.

일반적으로, 포함된 형식의 이름을 더욱 완벽하게 한정하거나 명시적 캐스트를 수행하여 의도를 분명하게 밝힘으로써 모호성을 해결할 수 있습니다.

변환 생성자와 변환 함수는 멤버 액세스 제어 규칙을 따르지만 변환 액세스 가능성은 모호하지 않은 변환을 확인할 수 있는 경우에만 고려됩니다. 즉, 변환은 경쟁 변환의 액세스 수준으로 인해 사용되지 못하게 되더라도 모호해질 수 있습니다. 멤버 내게 필요한 옵션에 대한 자세한 내용은 [구성원 액세스 제어](../cpp/member-access-control-cpp.md)를 참조하십시오.

## <a name="the-explicit-keyword-and-problems-with-implicit-conversion"></a>explicit 키워드 및 암시적 변환 문제

기본적으로, 사용자 정의 변환을 만들면 컴파일러가 이를 사용하여 암시적 변환을 수행할 수 있습니다. 이러한 방식을 원할 수도 있지만, 때로는 암시적 변환을 만드는 컴파일러를 안내하는 단순 규칙으로 인해 개발자가 의도하지 않은 코드가 컴파일러에 적용되는 결과가 발생할 수 있습니다.

문제를 일으킬 수 있는 암시적 변환의 잘 알려진 한 가지 예는 **bool로**변환하는 것입니다. 예를 들어 **if** 문 또는 루프를 제어하는 데 사용할 수 있도록 부울 컨텍스트에서 사용할 수 있는 클래스 형식을 만들려는 데는 여러 가지 이유가 있지만 컴파일러가 사용자 정의 변환을 기본 제공 유형으로 변환하면 컴파일러가 나중에 추가 표준 변환을 적용할 수 있습니다. 이 추가 표준 변환의 목적은 **짧은** 에서 **int로**승격과 같은 것을 허용하는 것이지만, 예를 들어 **bool에서** **int로,** 클래스 유형을 의도하지 않은 정수 컨텍스트에서 사용할 수 있도록 하는 등 덜 명백한 변환을 위한 문을 엽니다. 이 특정 문제를 *안전 부울 문제로*알려져 있습니다. 이러한 종류의 문제는 **명시적** 키워드가 도움이 될 수 있는 부분입니다.

**explicit** 키워드는 컴파일러에게 지정된 변환을 사용하여 암시적 변환을 수행할 수 없다는 것을 알려줍니다. **명시적** 키워드가 도입되기 전에 암시적 변환의 구문적 편의를 원한다면 암시적 변환이 때때로 생성되는 의도하지 않은 결과를 받아들이거나 덜 편리한 명명된 변환 함수를 해결 해결 대상으로 사용해야 했습니다. 이제 **명시적** 키워드를 사용하여 명시적 캐스트 또는 직접 초기화를 수행하는 데만 사용할 수 있는 편리한 변환을 만들 수 있으며, 이는 안전 Bool 문제에서 예시된 문제의 종류로 이어지지 않습니다.

**명시적** 키워드는 C++98 이후의 변환 생성자와 C++11 이후의 변환 함수에 적용할 수 있습니다. 다음 섹션에는 **명시적** 키워드를 사용하는 방법에 대한 자세한 정보가 포함되어 있습니다.

## <a name="conversion-constructors"></a><a name="ConvCTOR"></a>변환 생성자

변환 생성자는 사용자 정의 또는 기본 제공 형식에서 사용자 정의 형식으로의 변환을 정의합니다. 다음 예제에서는 기본 제공 형식 **이중에서** 사용자 정의 형식으로 `Money`변환 하는 변환 생성자를 보여 줍니다.

```cpp
#include <iostream>

class Money
{
public:
    Money() : amount{ 0.0 } {};
    Money(double _amount) : amount{ _amount } {};

    double amount;
};

void display_balance(const Money balance)
{
    std::cout << "The balance is: " << balance.amount << std::endl;
}

int main(int argc, char* argv[])
{
    Money payable{ 79.99 };

    display_balance(payable);
    display_balance(49.95);
    display_balance(9.99f);

    return 0;
}
```

`display_balance` 형식의 인수를 사용하는 `Money` 함수에 대한 첫 번째 호출의 경우 인수가 올바른 형식이므로 변환이 필요하지 않습니다. 그러나 두 번째 호출에서 `display_balance`는 인수의 형식인 **double** `49.95`값이 두 배가 함수가 기대하는 것이 아니기 때문에 변환이 필요합니다. 함수는 이 값을 직접 사용할 수 없지만 인수 형식(이중-두**배)에서**일치하는 매개 변수의`Money`유형으로 변환되기 `Money` 때문에 형식의 임시 값은 인수에서 생성되어 함수 호출을 완료하는 데 사용됩니다. `display_balance`에 대한 세 번째 호출에서 인수는 **두 배가**아니라 -의 `9.99`값을 가진 **float이며,** 이 경우 컴파일러가 표준 변환을 수행할 수 있기 때문에 함수 호출을 완료할 수 있습니다.이 경우 **float에서** **double로**표준 변환을 수행한 다음 사용자 정의 변환을 **두 번에서** 필요한 변환으로 완료할 `Money` 수 있습니다.

### <a name="declaring-conversion-constructors"></a>변환 생성자 선언

변환 생성자 선언에는 다음의 규칙이 적용됩니다.

- 변환 대상 형식은 생성 중인 사용자 정의 형식입니다.

- 일반적으로 변환 생성자에는 소스 형식에 대한 단 하나의 인수만 사용됩니다. 하지만 각각의 추가 매개 변수에 기본값이 있는 경우에는 변환 생성자가 추가 매개 변수를 지정할 수 있습니다. 소스 형식에는 첫 번째 매개 변수의 형식이 유지됩니다.

- 모든 생성자와 마찬가지로 변환 생성자는 반환 형식을 지정하지 않습니다. 선언에 반환 형식을 지정하는 것은 오류입니다.

- 변환 생성자는 명시적일 수 있습니다.

### <a name="explicit-conversion-constructors"></a>명시적 변환 생성자

변환 생성자가 **명시적이라고**선언하면 개체의 직접 초기화를 수행하거나 명시적 캐스트를 수행하는 데만 사용할 수 있습니다. 이를 통해, 클래스 형식 인수를 사용하는 함수가 변환 생성자의 소스 형식 인수를 암시적으로 사용할 수 없도록 하고 클래스 형식이 소스 형식 값을 통해 복사 초기화되지 않도록 할 수 있습니다. 다음 예제에서는 명시적 변환 생성자를 정의하는 방법과 올바른 형식의 코드에서의 그 효과를 보여줍니다.

```cpp
#include <iostream>

class Money
{
public:
    Money() : amount{ 0.0 } {};
    explicit Money(double _amount) : amount{ _amount } {};

    double amount;
};

void display_balance(const Money balance)
{
    std::cout << "The balance is: " << balance.amount << std::endl;
}

int main(int argc, char* argv[])
{
    Money payable{ 79.99 };        // Legal: direct initialization is explicit.

    display_balance(payable);      // Legal: no conversion required
    display_balance(49.95);        // Error: no suitable conversion exists to convert from double to Money.
    display_balance((Money)9.99f); // Legal: explicit cast to Money

    return 0;
}
```

이 예제에서는 명시적 변환 생성자를 사용하여 `payable`에 대한 직접 초기화를 수행할 수도 있습니다. 대신, `Money payable = 79.99;`을 복사 초기화하려는 경우에는 오류가 됩니다. `display_balance`에 대한 첫 번째 호출의 경우 인수의 형식이 올바르므로 오류가 아닙니다. `display_balance`에 대한 두 번째 호출의 경우에는 암시적 변환을 수행하는 데 변환 생성자를 사용할 수 없으므로 오류입니다. 세 번째 `display_balance` 호출은 명시적 캐스트로 `Money`인해 합법적이지만 컴파일러가 **float에서** **두 배로**암시적 캐스트를 삽입하여 캐스트를 완료하는 데 여전히 도움이 됩니다.

암시적 변환을 유도할 수 있다는 편리함이 있긴 하지만 찾기 어려운 버그가 발생할 수도 있습니다. 경험에 따르면, 암시적으로 발생될 특정 변환을 원하는 것이 확실한 경우 이외에는 모든 변환 생성자를 명시적으로 사용하는 것이 좋습니다.

## <a name="conversion-functions"></a><a name="ConvFunc"></a>변환 기능

변환 함수는 사용자 정의 형식에서 다른 형식으로의 변환을 정의합니다. 변환 생성자와 함께 이러한 함수는 값이 다른 형식으로 캐스트될 때 호출되기 때문에 종종 "캐스트 연산자"라고 합니다. 다음 예제에서는 사용자 정의 형식에서 `Money`기본 제공 형식으로 변환하는 변환 함수를 **double:**

```cpp
#include <iostream>

class Money
{
public:
    Money() : amount{ 0.0 } {};
    Money(double _amount) : amount{ _amount } {};

    operator double() const { return amount; }
private:
    double amount;
};

void display_balance(const Money balance)
{
    std::cout << "The balance is: " << balance << std::endl;
}
```

멤버 변수는 `amount` 비공개로 만들어지고 **double을** 입력하는 공용 변환 함수가 `amount`의 값을 반환하기 위해 도입됩니다. `display_balance` 함수에서는 스트림 삽입 연산자 `balance`를 통해 `<<`의 값이 표준 출력에 스트리밍될 때 암시적 변환이 발생합니다. `Money`사용자 정의 형식에 대해 스트림 삽입 연산자가 정의되지 않지만 기본 제공 형식 **이중에**대해 하나가 있으므로 `Money` 컴파일러는 변환 함수를 **두 배로** 변환함수를 사용하여 스트림 삽입 연산자를 만족시킬 수 있습니다.

변환 함수는 파생 클래스에 의해 상속됩니다. 파생 클래스의 변환 함수는 완전히 같은 형식으로 변환될 경우에만 상속된 변환 함수를 재정의합니다. 예를 들어 파생 클래스 **연산자 int의** 사용자 정의 변환 함수는 표준 변환이 **int와** **short**간의 변환 관계를 정의하더라도 기본 클래스 **연산자의**사용자 정의 변환 함수를 재정의하거나 영향을 받지 않습니다.

### <a name="declaring-conversion-functions"></a>변환 함수 선언

변환 함수 선언에는 다음의 규칙이 적용됩니다.

- 변환 대상 형식은 변환 함수 선언 전에 선언되어야 합니다. 클래스, 구조체, 열거형 및 typedef는 변환 함수 선언 내에서 선언할 수 없습니다.

    ```cpp
    operator struct String { char string_storage; }() // illegal
    ```

- 변환 함수는 인수를 사용하지 않습니다. 선언에 매개 변수를 지정하는 것은 오류입니다.

- 변환 함수에는 변환 함수의 이름(변환 대상 형식의 이름이기도 함)에 의해 지정되는 반환 유형이 있습니다. 선언에 반환 형식을 지정하는 것은 오류입니다.

- 변환 함수는 가상일 수 있습니다.

- 변환 함수는 명시적일 수 있습니다.

### <a name="explicit-conversion-functions"></a>명시적 변환 함수

변환 함수가 명시적 변환 함수로 선언되면 명시적 캐스트를 수행하는 데만 사용할 수 있습니다. 이를 통해, 변환 함수의 대상 형식에 대한 인수를 사용하는 함수가 클래스 형식에 대한 인수를 암시적으로 사용할 수 없도록 하고 대상 형식 인스턴스가 클래스 형식 값을 통해 복사 초기화되지 않도록 할 수 있습니다. 다음 예제에서는 명시적 변환 함수를 정의하는 방법과 올바른 형식의 코드에서의 그 효과를 보여줍니다.

```cpp
#include <iostream>

class Money
{
public:
    Money() : amount{ 0.0 } {};
    Money(double _amount) : amount{ _amount } {};

    explicit operator double() const { return amount; }
private:
    double amount;
};

void display_balance(const Money balance)
{
    std::cout << "The balance is: " << (double)balance << std::endl;
}
```

여기서 변환 함수 **연산자는 두 배로** 명시적으로 만들어졌으며 변환을 수행하기 `display_balance` 위해 함수에 **double을** 입력하는 명시적 캐스트가 도입되었습니다. 이 캐스트가 생략되었다면 컴파일러는 `<<` 형식에 대한 적절한 스트림 삽입 연산자 `Money`를 찾지 못하고 오류가 발생됩니다.
