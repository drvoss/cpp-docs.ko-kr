---
title: return 문 (C)
description: C 언어 return 문은 함수 실행을 종료하고 필요한 경우 호출자에 값을 반환합니다.
ms.date: 06/10/2020
helpviewer_keywords:
- ( ) parentheses in return statements
ms.assetid: 18cd82cf-f899-4b28-83ad-4eff353ddcb4
ms.openlocfilehash: 7d518aa17185c96de15c8f9aa9b65ae5c72bd014
ms.sourcegitcommit: 01b911613606c3fc92cbd9ca48cca6046a7e8258
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2020
ms.locfileid: "84716296"
---
# <a name="return-statement-c"></a>return 문 (C)

**`return`** 문은 함수 실행을 종료하고 호출 함수로 컨트롤을 반환합니다. 호출 바로 다음 지점의 호출 함수에서 실행을 다시 시작합니다. **`return`** 문은 호출 함수로 값을 반환할 수 있습니다. 자세한 내용은 [반환 형식](../c-language/return-type.md)을 참조하세요.

## <a name="syntax"></a>구문

> *jump-statement*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`return`** *expression*&#8203;<sub>opt</sub> **`;`**

*expression*의 값(있는 경우)이 호출 함수로 반환됩니다. *expression*을 생략하면 함수의 반환 값이 정의되지 않습니다. 식이 있는 경우 평가된 다음 함수에서 반환한 형식으로 변환됩니다. **`return`** 문에 **`void`** 반환 형식을 사용하는 함수의 식이 포함되면 컴파일러는 경고를 생성하고 식은 평가되지 않습니다.

함수 정의에 **`return`** 문이 표시되지 않으면 호출된 함수의 마지막 문이 실행된 후 호출 함수에 컨트롤이 자동으로 반환됩니다. 이 경우 호출된 함수의 반환 값은 정의되지 않습니다. 함수에 **`void`** 반환 형식을 사용하지 않으면 이것은 심각한 버그이며 컴파일러가 경고 진단 메시지를 출력합니다. 함수에 **`void`** 반환 형식을 사용하면 이 동작은 정상이지만 좋지 않은 스타일로 간주될 수 있습니다. 일반 **`return`** 문을 사용하여 의도를 명확하게 합니다.

엔지니어링 측면에서는 항상 함수의 반환 형식을 지정하는 것이 좋습니다. 반환 값이 필요하지 않으면 **`void`** 반환 형식을 사용하도록 함수를 선언합니다. 반환 형식이 지정되지 않으면 C 컴파일러는 **`int`** 의 기본 반환 형식으로 간주합니다.

대부분의 프로그래머는 **`return`** 문의 *expression* 인수를 괄호로 묶습니다. 그러나 C에서는 괄호가 필요하지 않습니다.

컴파일러는 **`return`** 문 뒤에 배치된 문을 찾으면 접근할 수 없는 코드에 대한 경고 진단 메시지를 실행할 수 있습니다.

**`main`** 함수에서 **`return`** 문과 식은 선택 사항입니다. 반환 값이 지정된 경우 발생하는 동작은 구현에 따라 다릅니다. **Microsoft 전용**: Microsoft C 구현은 *`cmd.exe`* 와 같이 프로그램을 호출한 프로세스에 식 값을 반환합니다. **`return`** 식이 제공되지 않으면 Microsoft C 런타임은 성공(0) 또는 실패(0이 아닌 값)를 나타내는 값을 반환합니다.

## <a name="example"></a>예제

이 예제는 여러 부분으로 구성된 하나의 프로그램입니다. **`return`** 문을 보여 주며 함수 실행을 종료하고 선택적으로 값을 반환하는 방법을 둘 다 보여 줍니다.

```C
// C_return_statement.c
// Compile using: cl /W4 C_return_statement.c
#include <limits.h>      // for INT_MAX
#include <stdio.h>       // for printf

long long square( int value )
{
    // Cast one operand to long long to force the
    // expression to be evaluated as type long long.
    // Note that parentheses around the return expression
    // are allowed, but not required here.
    return ( value * (long long) value );
}
```

`square` 함수는 산술 오류를 방지하기 위해 더 광범위한 형식으로 인수의 제곱을 반환합니다. **Microsoft 전용**: Microsoft C 구현에서 **`long long`** 형식은 오버플로 없이 **`int`** 값 두 개의 곱을 저장할 만큼 커야 합니다.

`square`의 **`return`** 식을 둘러싼 괄호는 식의 부분으로 평가되며 **`return`** 명령문에 필요하지 않습니다.

```C
double ratio( int numerator, int denominator )
{
    // Cast one operand to double to force floating-point
    // division. Otherwise, integer division is used,
    // then the result is converted to the return type.
    return numerator / (double) denominator;
}
```

`ratio` 함수는 두 **`int`** 인수의 비율을 부동 소수점 **`double`** 값으로 반환합니다. **`return`** 식은 피연산자 중 하나를 **`double`** 로 캐스팅하여 부동 소수점 연산을 사용해야 합니다. 그러지 않으면 정수 나누기 연산자가 사용되며 소수 부분이 손실됩니다.

```C
void report_square( void )
{
    int value = INT_MAX;
    long long squared = 0LL;
    squared = square( value );
    printf( "value = %d, squared = %lld\n", value, squared );
    return; // Use an empty expression to return void.
}
```

`report_square` 함수는 **`int`** 에 맞는 가장 큰 부호 있는 정수 값인 `INT_MAX` 매개 변수 값을 사용하여 `square`를 호출합니다. **`long long`** 결과는 `squared`에 저장된 후 출력됩니다. `report_square` 함수는 **`void`** 반환 형식을 사용하므로 **`return`** 문에 식을 포함하지 않습니다.

```C
void report_ratio( int top, int bottom )
{
    double fraction = ratio( top, bottom );
    printf( "%d / %d = %.16f\n", top, bottom, fraction );
    // It's okay to have no return statement for functions
    // that have void return types.
}
```

`report_ratio` 함수는 `1` 및 `INT_MAX`의 매개 변수 값을 사용하여 `ratio`를 호출합니다. **`double`** 결과는 `fraction`에 저장된 후 출력됩니다. `report_ratio` 함수는 **`void`** 반환 형식을 사용하므로 값을 명시적으로 반환할 필요가 없습니다. `report_ratio` 실행은 “종료”되며 호출자에 값을 반환하지 않습니다.

```C
int main()
{
    int n = 1;
    int x = INT_MAX;

    report_square();
    report_ratio( n, x );

    return 0;
}
```

**`main`** 함수는 두 개의 함수인 `report_square` 및 `report_ratio`를 호출합니다. `report_square`는 매개 변수를 사용하지 않고 **`void`** 를 반환하므로 결과를 변수에 할당하지 않습니다. 마찬가지로 `report_ratio`는 **`void`** 를 반환하므로 반환 값을 저장하지 않습니다. 이 함수를 각각 호출한 후 다음 문에서 실행이 계속됩니다. 그런 다음, **`main`** 은 `0` 값(일반적으로 성공을 보고하는 데 사용됨)을 반환하여 프로그램을 종료합니다.

예제를 컴파일하려면 *`C_return_statement.c`* 라는 소스 코드 파일을 만듭니다. 그런 다음, 모든 예제 코드를 표시된 순서대로 복사합니다. 파일을 저장하고 다음 명령을 사용하여 개발자 명령 프롬프트 창에서 컴파일합니다.

**`cl /W4 C_return_statement.c`**

그런 다음, 예제 코드를 실행하려면 명령 프롬프트에서 **`C_return_statement.exe`** 를 입력합니다. 예를 들어 다음과 같이 출력됩니다.

```Output
value = 2147483647, squared = 4611686014132420609
1 / 2147483647 = 0.0000000004656613
```

## <a name="see-also"></a>참조

[문](../c-language/statements-c.md)
