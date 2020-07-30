---
title: 인라인 함수(C++)
description: C + + inline 키워드를 사용 하 여 컴파일러에 인라인 함수를 제안할 수 있습니다.
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
ms.openlocfilehash: d2356d7813167f3973ac2748423c6af7f0b5573b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227415"
---
# <a name="inline-functions-c"></a>인라인 함수(C++)

클래스 선언의 본문에 정의된 함수는 인라인 함수입니다.

## <a name="example"></a>예제

다음 클래스 선언에서 `Account` 생성자는 인라인 함수입니다. 멤버 함수 `GetBalance` , 및은 (는) `Deposit` `Withdraw` 로 지정 되지 **`inline`** 않지만 인라인 함수로 구현할 수 있습니다.

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
> 클래스 선언에서 함수는 키워드를 사용 하지 않고 선언 되었습니다 **`inline`** . **`inline`** 키워드는 클래스 선언에서 지정할 수 있습니다. 결과는 동일 합니다.

주어진 인라인 멤버 함수는 모든 컴파일 단위에서 동일한 방식으로 선언되어야 합니다. 이 제한 사항으로 인해 인라인 함수는 마치 인스턴스화된 함수처럼 동작합니다. 또한 인라인 함수의 정의는 정확히 하나만 있어야 합니다.

클래스 멤버 함수는 해당 함수에 대 한 정의에 지정자를 포함 하지 않는 한 기본적으로 외부 링크로 설정 **`inline`** 됩니다. 앞의 예제에서는 지정자를 사용 하 여 이러한 함수를 명시적으로 선언 하지 않아도 되는 것을 보여 줍니다 **`inline`** . **`inline`** 함수 정의에서를 사용 하면 해당 함수가 인라인 함수가 됩니다. 그러나 함수를 호출한 후에는 함수를 다시 선언할 수 없습니다 **`inline`** .

## <a name="inline-__inline-and-__forceinline"></a>`inline`, `__inline`, `__forceinline`

**`inline`** 및 지정자는 함수가 **`__inline`** 호출 되는 각 장소에 함수 본문의 복사본을 삽입 하도록 컴파일러에 지시 합니다.

*인라인 확장* 또는 *인라이닝*이라고 하는 삽입은 컴파일러의 비용 혜택 분석에서 유용한 것으로 표시 되는 경우에만 발생 합니다. 인라인 확장은 보다 큰 코드 크기의 잠재적 비용으로 함수 호출 오버 헤드를 최소화 합니다.

**`__forceinline`** 키워드는 비용 혜택 분석을 재정의 하 고 대신 프로그래머의 판단에 의존 합니다. 을 사용할 때는 주의 해야 **`__forceinline`** 합니다. 무분별를 사용 **`__forceinline`** 하면 성능이 크게 향상 되거나 경우에 따라 더 큰 실행 파일의 페이징이 증가 하 여 성능이 저하 될 수 있습니다.

인라인 함수를 사용하면 함수 호출과 연관된 오버헤드가 제거되어 프로그램 속도가 더 빨라질 수 있습니다. 인라인으로 확장된 함수에는 일반 함수에 사용할 수 없는 코드 최적화가 적용됩니다.

컴파일러는 인라인 확장 옵션과 키워드를 제안으로 처리합니다. 함수가 인라인 될 수 있는 것은 아닙니다. 컴파일러가 키워드를 사용 하는 경우에도 특정 함수를 인라인 하도록 강제할 수 없습니다 **`__forceinline`** . 를 사용 하 여 컴파일할 때 **`/clr`** 컴파일러는 함수에 적용 되는 보안 특성이 있는 경우 함수를 인라인 하지 않습니다.

**`inline`** 키워드는 c + + 에서만 사용할 수 있습니다. **`__inline`** 및 **`__forceinline`** 키워드는 c 및 c + +에서 사용할 수 있습니다. 이전 버전과의 호환성을 위해 **`_inline`** 및 **`_forceinline`** 은에 대 한 동의어이 **`__inline`** 고, **`__forceinline`** 컴파일러 옵션 [ `/Za` \( 사용 안 함 언어 확장 사용 안 함](../build/reference/za-ze-disable-language-extensions.md) 을 지정 하지 않으면입니다.

**`inline`** 키워드는 인라인 확장의 기본 설정에 대해 컴파일러에 지시 합니다. 그러나 컴파일러는 함수의 별도 인스턴스를 만들고(인스턴스화) 인라인으로 코드를 삽입하는 대신 표준 호출 링크를 만들 수 있습니다. 이러한 동작이 발생할 수 있는 두 가지 경우는 다음과 같습니다.

- 재귀 함수.

- 변환 단위의 다른 위치에서 포인터를 통해 참조되는 함수.

이러한 이유는 컴파일러의 재량에 *따라 다른 것 처럼*인라인 처리에 방해가 될 수 있습니다. **`inline`** 함수가 인라인 되도록 하려면 지정자에 종속 되지 않아야 합니다.

일반 함수와 마찬가지로 인라인 함수에서 인수 계산에 대 한 순서는 정의 되어 있지 않습니다. 실제로 일반적인 함수 호출 프로토콜을 사용 하 여 전달 되는 경우 인수 계산 순서와 다를 수 있습니다.

[`/Ob`](../build/reference/ob-inline-function-expansion.md)컴파일러 최적화 옵션은 인라인 함수 확장이 실제로 발생 하는지 여부를 확인 하는 데 도움이 됩니다.

[`/LTCG`](../build/reference/ltcg-link-time-code-generation.md)는 소스 코드에서 요청 되었는지 여부에 관계 없이 크로스 모듈을 인라인 합니다.

### <a name="example-1"></a>예제 1

```cpp
// inline_keyword1.cpp
// compile with: /c
inline int max( int a , int b ) {
   if( a > b )
      return a;
   return b;
}
```

클래스의 멤버 함수는 키워드를 사용 하 여 인라인으로 선언 **`inline`** 하거나 클래스 정의 내에 함수 정의를 배치할 수 있습니다.

### <a name="example-2"></a>예제 2

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

**`__inline`** 키워드는와 동일 **`inline`** 합니다.

를 사용 하는 경우에도 **`__forceinline`** 컴파일러는 모든 상황에서 코드를 인라인 할 수 없습니다. 컴파일러는 다음과 같은 경우 함수를 인라인 할 수 없습니다.

- 함수 또는 해당 호출자는 **`/Ob0`** (디버그 빌드에 대 한 기본 옵션)를 사용 하 여 컴파일됩니다.

- 함수 및 호출자가 다양한 형식의 예외 처리(한 경우 C++ 예외 처리, 다른 경우 구조적 예외 처리)를 사용합니다.

- 함수에 가변 인수 목록이 있습니다.

- 함수는, 또는로 컴파일되지 않은 경우 인라인 어셈블리를 사용 **`/Ox`** **`/O1`** **`/O2`** 합니다.

- 함수는 재귀적 이며를 설정 하지 않습니다 **`#pragma inline_recursion(on)`** . pragma를 사용하면 재귀 함수가 기본 깊이 16번 호출로 인라인 처리됩니다. 인라인 깊이를 줄이려면 pragma를 사용 [`inline_depth`](../preprocessor/inline-depth.md) 합니다.

- 가상 함수이며 실제로 호출됩니다. 가상 함수에 대한 직접 호출은 인라인 처리할 수 있습니다.

- 프로그램에서 함수의 주소를 사용하고 함수에 대한 포인터를 통해 호출합니다. 주소가 사용된 함수에 대한 직접 호출은 인라인 처리할 수 있습니다.

- 함수는 한정자로도 표시 됩니다 [`naked`](../cpp/naked-cpp.md) [`__declspec`](../cpp/declspec.md) .

컴파일러가로 선언 된 함수를 인라인 할 수 없는 경우 **`__forceinline`** 다음과 같은 경우를 제외 하 고 수준 1 경고가 생성 됩니다.

- 함수는/Od 또는/Ob0.를 사용 하 여 컴파일됩니다. 이러한 경우에는 인라이닝이 필요 하지 않습니다.

- 함수는 외부에서 포함 된 라이브러리나 다른 변환 단위에서 정의 되거나 가상 호출 대상 또는 간접 호출 대상입니다. 컴파일러가 현재 변환 단위에서 찾을 수 없는 인라인 되지 않은 코드를 식별할 수 없습니다.

재귀 함수는 [`inline_depth`](../preprocessor/inline-depth.md) 최대 16 개의 호출까지 pragma로 지정 된 깊이까지 인라인 코드로 바꿀 수 있습니다. 해당 깊이 이후 재귀 함수 호출은 함수의 인스턴스 호출로 처리됩니다.  인라인 추론에서 재귀 함수를 검사 하는 깊이는 16을 초과할 수 없습니다. [`inline_recursion`](../preprocessor/inline-recursion.md)Pragma는 현재 확장 중인 함수의 인라인 확장을 제어 합니다. 관련 정보는/Ob ( [인라인 함수 확장](../build/reference/ob-inline-function-expansion.md) ) 컴파일러 옵션을 참조 하세요.

**Microsoft 전용 종료**

지정자 사용에 대 한 자세한 내용은 **`inline`** 다음을 참조 하세요.

- [인라인 클래스 멤버 함수](../cpp/inline-functions-cpp.md)

- [Dllexport 및 dllimport를 사용 하 여 인라인 c + + 함수 정의](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

## <a name="when-to-use-inline-functions"></a>인라인 함수 사용 시기

인라인 함수는 전용 데이터 멤버에 액세스하는 것처럼 작은 함수에서 가장 적합하게 사용됩니다. 이러한 한 줄 또는 두 줄 "접근자" 함수의 주요 목적은 개체에 대 한 상태 정보를 반환 하는 것입니다. Short 함수는 함수 호출의 오버 헤드를 구분 합니다. 더 긴 함수는를 호출 하 고 시퀀스를 반환 하는 데 걸리는 시간을 줄이고 인라인에서 더 많은 이점을 제공 합니다.

클래스는 다음과 `Point` 같이 정의할 수 있습니다.

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

좌표 조작이 이러한 클래스의 클라이언트에서 상대적으로 일반적인 작업 이라고 가정 하 `x` 고, `y` 일반적으로 **`inline`** 오버 헤드를 저장 하는 두 접근자 함수 (앞의 예제에서는)를 지정 합니다.

- 함수 호출(개체의 주소를 스택에 전달 및 배치하는 매개 변수 포함)

- 호출자의 스택 프레임의 보존

- 새 스택 프레임 설정

- 반환 값 전달

- 이전 스택 프레임 복원

- 반환 값

## <a name="inline-functions-vs-macros"></a>인라인 함수와 매크로 비교

인라인 함수는 컴파일 시간에 호출 지점에서 함수 코드가 확장 되기 때문에 매크로와 비슷합니다. 그러나 인라인 함수는 컴파일러에 의해 구문 분석 되 고 매크로는 전처리기에 의해 확장 됩니다. 그 결과 몇 가지 중요한 차이가 생깁니다.

- 인라인 함수는 일반 함수에 적용되는 모든 형식 안전성 프로토콜을 따릅니다.

- 인라인 함수는 **`inline`** 함수 선언에 키워드를 포함 한다는 점을 제외 하 고 다른 함수와 동일한 구문을 사용 하 여 지정 됩니다.

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

식의 의도는 `toupper(getc(stdin))` 콘솔 장치 ()에서 문자를 읽고 `stdin` 필요한 경우 대문자로 변환 하는 것입니다.

매크로의 구현으로 인해 `getc` 은 한 번 실행 되어 문자가 "a" 보다 크거나 같은지 확인 하 고, "z" 보다 작거나 같은지 여부를 확인 합니다. 해당 범위에 속할 경우 문자를 대문자로 변환하기 위해 `getc`가 다시 실행됩니다. 즉, 프로그램은 한 번만 기다려야 하는 경우 두 개 또는 세 개의 문자를 대기 합니다.

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

[`noinline`](../cpp/noinline.md)<br/>
[`auto_inline`](../preprocessor/auto-inline.md)
