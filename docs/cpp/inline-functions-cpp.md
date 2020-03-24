---
title: 인라인 함수(C++)
ms.date: 10/09/2018
f1_keywords:
- __forceinline_cpp
- __inline_cpp
- inline_cpp
- __inline
- _inline
- __forceinline
- _forceinline
helpviewer_keywords:
- inline functions [C++], class members
ms.assetid: 355f120c-2847-4608-ac04-8dda18ffe10c
ms.openlocfilehash: b13007211857d84e4f3b33c80ed6b5beaf6f0bcf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178239"
---
# <a name="inline-functions-c"></a>인라인 함수(C++)

클래스 선언의 본문에 정의된 함수는 인라인 함수입니다.

## <a name="example"></a>예제

다음 클래스 선언에서 `Account` 생성자는 인라인 함수입니다. `GetBalance`, `Deposit`및 `Withdraw` 멤버 함수는 **인라인으로** 지정 되지 않지만 인라인 함수로 구현할 수 있습니다.

```cpp
// Inline_Member_Functions.cpp
class Account
{
public:
    Account(double initial_balance) { balance = initial_balance; }
    double GetBalance();
    double Deposit( double Amount );
    double Withdraw( double Amount );
private:
    double balance;
};

inline double Account::GetBalance()
{
    return balance;
}

inline double Account::Deposit( double Amount )
{
    return ( balance += Amount );
}

inline double Account::Withdraw( double Amount )
{
    return ( balance -= Amount );
}
int main()
{
}
```

> [!NOTE]
>  클래스 선언에서 함수는 **inline** 키워드를 사용 하지 않고 선언 되었습니다. **Inline** 키워드는 클래스 선언에서 지정할 수 있습니다. 결과는 동일 합니다.

주어진 인라인 멤버 함수는 모든 컴파일 단위에서 동일한 방식으로 선언되어야 합니다. 이 제한 사항으로 인해 인라인 함수는 마치 인스턴스화된 함수처럼 동작합니다. 또한 인라인 함수의 정의는 정확히 하나만 있어야 합니다.

클래스 멤버 함수는 해당 함수의 정의가 **인라인** 지정자를 포함 하지 않는 한 기본적으로 외부 링크로 설정 됩니다. 앞의 예제에서는 이러한 함수를 **인라인** 지정자를 사용 하 여 명시적으로 선언 하지 않아도 되는 것을 보여 줍니다. 함수 정의에서 **inline** 을 사용 하면 인라인 함수가 됩니다. 그러나 함수를 호출한 후에는 함수를 **인라인으로** 다시 선언할 수 없습니다.

## <a name="inline-__inline-and-__forceinline"></a>인라인, __inline 및 \__forceinline

**Inline** 및 **__inline** 지정자는 함수가 호출 되는 각 장소에 함수 본문의 복사본을 삽입 하도록 컴파일러에 지시 합니다.

삽입(인라인 확장 또는 인라인 처리라고 함)은 컴파일러의 비용/이익 분석에서 수익성이 있는 것으로 표시되는 경우에만 수행됩니다. 인라인 확장을 사용하면 더 큰 코드 크기를 줄여 함수 호출 오버헤드를 줄일 수 있습니다.

**__Forceinline** 키워드는 비용/혜택 분석을 재정의 하 고 대신 프로그래머의 판단에 의존 합니다. **__Forceinline**를 사용 하는 경우 주의 해야 합니다. **__Forceinline** 를 무분별 사용 하면 성능이 크게 향상 되거나 경우에 따라 더 큰 실행 파일의 페이징이 증가 하 여 성능 손실이 발생할 수 있습니다.

인라인 함수를 사용하면 함수 호출과 연관된 오버헤드가 제거되어 프로그램 속도가 더 빨라질 수 있습니다. 인라인으로 확장된 함수에는 일반 함수에 사용할 수 없는 코드 최적화가 적용됩니다.

컴파일러는 인라인 확장 옵션과 키워드를 제안으로 처리합니다. 함수가 인라인으로 처리된다는 보장은 없습니다. 컴파일러가 **__forceinline** 키워드를 사용 하는 경우에도 특정 함수를 인라인 하도록 강제할 수 없습니다. **/Clr**을 사용 하 여 컴파일하는 경우 함수에 적용 되는 보안 특성이 있으면 컴파일러가 함수를 인라인 하지 않습니다.

**Inline** 키워드는 에서만 사용할 수 있습니다 C++. **__Inline** 및 **__Forceinline** 키워드는 C와 C++모두에서 사용할 수 있습니다. 이전 버전과의 호환성을 위해 **_inline** 및 **_forceinline** 는 **__inline**에 대 한 동의어 이며, 컴파일러 옵션 [/za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 이 지정 되지 않은 경우 **__forceinline** .

**Inline** 키워드는 인라인 확장의 기본 설정에 대해 컴파일러에 지시 합니다. 그러나 컴파일러는 함수의 별도 인스턴스를 만들고(인스턴스화) 인라인으로 코드를 삽입하는 대신 표준 호출 링크를 만들 수 있습니다. 다음은 이런 상황이 발생할 수 있는 두 가지 경우입니다.

- 재귀 함수.

- 변환 단위의 다른 위치에서 포인터를 통해 참조되는 함수.

이러한 이유는 컴파일러의 재량에 *따라 다른 것 처럼*인라인 처리에 방해가 될 수 있습니다. 함수가 인라인 되도록 하려면 **인라인** 지정자를 의존해 서는 안 됩니다.

일반 함수에서처럼 인라인 함수에 대한 인수의 계산 순서는 정의되어 있지 않습니다. 실제로 일반 함수 호출 프로토콜을 사용하여 전달될 때 인수가 계산되는 순서와 다를 수 있습니다.

[/Ob](../build/reference/ob-inline-function-expansion.md) 컴파일러 최적화 옵션은 인라인 함수 확장이 실제로 발생 하는지 여부를 확인 하는 데 도움이 됩니다.

[/Ltcg](../build/reference/ltcg-link-time-code-generation.md) 는 소스 코드에서 요청 되었는지 여부에 관계 없이 크로스 모듈 인라인 처리를 수행 합니다.

### <a name="example-1"></a>예 1

```cpp
// inline_keyword1.cpp
// compile with: /c
inline int max( int a , int b ) {
   if( a > b )
      return a;
   return b;
}
```

클래스의 멤버 함수는 **인라인** 키워드를 사용 하거나 클래스 정의 내에 함수 정의를 배치 하 여 인라인으로 선언할 수 있습니다.

### <a name="example-2"></a>예 2

```cpp
// inline_keyword2.cpp
// compile with: /EHsc /c
#include <iostream>
using namespace std;

class MyClass {
public:
   void print() { cout << i << ' '; }   // Implicitly inline
private:
   int i;
};
```

**Microsoft 전용**

**__Inline** 키워드는 **인라인으로**와 동일 합니다.

**__Forceinline**경우에도 컴파일러는 모든 상황에서 코드를 인라인 할 수 없습니다. 다음과 같은 경우 컴파일러에서 함수를 인라인 처리할 수 없습니다.

- 함수 또는 해당 호출자가 /Ob0(디버그 빌드에 대한 기본 옵션)으로 컴파일됩니다.

- 함수 및 호출자가 다양한 형식의 예외 처리(한 경우 C++ 예외 처리, 다른 경우 구조적 예외 처리)를 사용합니다.

- 함수에 가변 인수 목록이 있습니다.

- /Og, /Ox, /O1 또는 /O2로 컴파일되지 않은 경우 함수에서 인라인 어셈블리를 사용합니다.

- 함수는 재귀적 이며 **#pragma inline_recursion (on)** 와 함께 제공 되지 않습니다. pragma를 사용하면 재귀 함수가 기본 깊이 16번 호출로 인라인 처리됩니다. 인라인 깊이를 줄이려면 [inline_depth](../preprocessor/inline-depth.md) pragma를 사용 합니다.

- 가상 함수이며 실제로 호출됩니다. 가상 함수에 대한 직접 호출은 인라인 처리할 수 있습니다.

- 프로그램에서 함수의 주소를 사용하고 함수에 대한 포인터를 통해 호출합니다. 주소가 사용된 함수에 대한 직접 호출은 인라인 처리할 수 있습니다.

- 또한 함수는 [naked](../cpp/naked-cpp.md) [__declspec](../cpp/declspec.md) 한정자로 표시 됩니다.

컴파일러가 **__forceinline**로 선언 된 함수를 인라인 할 수 없는 경우 다음과 같은 경우를 제외 하 고 수준 1 경고를 생성 합니다.

- 함수는/Od 또는/Ob0.를 사용 하 여 컴파일됩니다. 이러한 경우에는 인라이닝이 필요 하지 않습니다.

- 함수는 외부에서 포함 된 라이브러리나 다른 변환 단위에서 정의 되거나 가상 호출 대상 또는 간접 호출 대상입니다. 컴파일러가 현재 변환 단위에서 찾을 수 없는 인라인 되지 않은 코드를 식별할 수 없습니다.

재귀 함수는 최대 16 개의 호출까지 [inline_depth](../preprocessor/inline-depth.md) pragma로 지정 된 깊이에 인라인으로 대체할 수 있습니다. 해당 깊이 이후 재귀 함수 호출은 함수의 인스턴스 호출로 처리됩니다.  인라인 추론에서 재귀 함수를 검사하는 깊이는 16을 초과할 수 없습니다. [Inline_recursion](../preprocessor/inline-recursion.md) pragma는 현재 확장 중인 함수의 인라인 확장을 제어 합니다. 관련 정보는/Ob ( [인라인 함수 확장](../build/reference/ob-inline-function-expansion.md) ) 컴파일러 옵션을 참조 하세요.

**Microsoft 전용 종료**

**인라인** 지정자 사용에 대 한 자세한 내용은 다음을 참조 하세요.

- [인라인 클래스 멤버 함수](../cpp/inline-functions-cpp.md)

- [dllexport 및 dllimport로 인라인 C++ 함수 정의](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

## <a name="when-to-use-inline-functions"></a>인라인 함수 사용 시기

인라인 함수는 전용 데이터 멤버에 액세스하는 것처럼 작은 함수에서 가장 적합하게 사용됩니다. 한 줄 또는 두 줄 "접근자" 함수의 주요 목적은 개체에 대한 상태 정보를 반환하는 것입니다. 간단한 함수는 함수 호출의 오버헤드에 민감합니다. 긴 함수는 호출/반환 시퀀스에서 상당히 시간이 적게 소요되며 인라이닝으로 인한 이점이 크지 않습니다.

`Point` 클래스는 다음과 같이 정의할 수 있습니다.

```cpp
// when_to_use_inline_functions.cpp
class Point
{
public:
    // Define "accessor" functions as
    //  reference types.
    unsigned& x();
    unsigned& y();
private:
    unsigned _x;
    unsigned _y;
};

inline unsigned& Point::x()
{
    return _x;
}
inline unsigned& Point::y()
{
    return _y;
}
int main()
{
}
```

이러한 클래스의 클라이언트에서 좌표 조작이 상대적으로 일반적인 작업 이라고 가정 하면 일반적으로 두 접근자 함수 (위 예제의`x` 및 `y`)를 **인라인으로** 지정 하 여 오버 헤드를 저장 합니다.

- 함수 호출(개체의 주소를 스택에 전달 및 배치하는 매개 변수 포함)

- 호출자의 스택 프레임의 보존

- 새 스택 프레임 설정

- 반환 값 전달

- 기존 스택 프레임 복원

- 반환 값

## <a name="inline-functions-vs-macros"></a>인라인 함수와 매크로 비교

컴파일할 때 호출 시점에 함수 코드가 확장된다는 점에서 인라인 함수는 매크로와 비슷하지만 인라인 함수는 컴파일러에 의해 구문이 분석되며 매크로는 전처리기에 의해 확장됩니다. 그 결과 몇 가지 중요한 차이가 생깁니다.

- 인라인 함수는 일반 함수에 적용되는 모든 형식 안전성 프로토콜을 따릅니다.

- 인라인 함수는 함수 선언에 **inline** 키워드를 포함 한다는 점을 제외 하 고 다른 함수와 동일한 구문을 사용 하 여 지정 됩니다.

- 인라인 함수에 인수로 전달된 식은 한 번 계산됩니다. 매크로에 인수로 전달된 식은 경우에 따라 여러 번 계산할 수 있습니다.

다음 예제에서는 소문자를 대문자로 변환하는 매크로를 보여 줍니다.

```cpp
// inline_functions_macro.c
#include <stdio.h>
#include <conio.h>

#define toupper(a) ((a) >= 'a' && ((a) <= 'z') ? ((a)-('a'-'A')):(a))

int main() {
   char ch;
   printf_s("Enter a character: ");
   ch = toupper( getc(stdin) );
   printf_s( "%c", ch );
}
//  Sample Input:  xyz
// Sample Output:  Z
```

식 `toupper(getc(stdin))`의 의도는 콘솔 장치 (`stdin`)에서 문자를 읽고 필요한 경우 대문자로 변환 하는 것입니다.

매크로 구현으로 인해 문자가 "a"보다 크거나 같은지 확인하기 위해 한 번, "z"보다 작거나 같은지 확인하기 위해 한 번 `getc`를 실행합니다. 해당 범위에 속할 경우 문자를 대문자로 변환하기 위해 `getc`가 다시 실행됩니다. 즉, 문자를 1개만 기다려야 하는데 프로그램이 문자를 2개나 3개 기다립니다.

인라인 함수는 전에 설명한 문제를 해결합니다.

```cpp
// inline_functions_inline.cpp
#include <stdio.h>
#include <conio.h>

inline char toupper( char a ) {
   return ((a >= 'a' && a <= 'z') ? a-('a'-'A') : a );
}

int main() {
   printf_s("Enter a character: ");
   char ch = toupper( getc(stdin) );
   printf_s( "%c", ch );
}
```

```Output
Sample Input: a
Sample Output: A
```

## <a name="see-also"></a>참고 항목

[noinline](../cpp/noinline.md)<br/>
[auto_inline](../preprocessor/auto-inline.md)
