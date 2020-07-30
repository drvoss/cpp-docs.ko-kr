---
title: 대입 연산자
description: C + + 표준 언어 할당 연산자 구문 및를 사용 합니다.
ms.date: 07/24/2020
f1_keywords:
- =
- '*='
- /=
- '%='
- +=
- -=
- <<=
- '>>='
- '&='
- ^=
- '|='
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], C++
- '&= operator'
- ^= operator
- += operator
- '>>= operator'
- '|= operator'
- operator>>=
- '*= operator'
- '%= operator'
- ^= operator
- operator >>=
- = operator
- -= operator
- /= operator
- <<= operator
ms.assetid: b028cf35-2ff1-4f14-9027-fd53ebec8aa0
ms.openlocfilehash: 91346d06c6fab4f3cd83c5318c88e738daf8d249
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229222"
---
# <a name="assignment-operators"></a>대입 연산자

## <a name="syntax"></a>구문

*식* *대입 연산자* *식*

*assignment-operator*: 다음 중 하나<br/>
&emsp;**`=`**&emsp;**`*=`**&emsp;**`/=`**&emsp;**`%=`**&emsp;**`+=`**&emsp;**`-=`**&emsp;**`<<=`**&emsp;**`>>=`**&emsp;**`&=`**&emsp;**`^=`**&emsp;**`|=`**

## <a name="remarks"></a>설명

할당 연산자는 왼쪽 피연산자로 지정 된 개체에 값을 저장 합니다. 할당 작업에는 다음과 같은 두 가지 종류가 있습니다.

- *단순 할당*-두 번째 피연산자의 값이 첫 번째 피연산자가 지정한 개체에 저장 됩니다.

- 결과를 저장 하기 전에 산술, 시프트 또는 비트 연산을 수행 하는 *복합 할당*입니다.

연산자를 제외 하 고 다음 표의 모든 할당 연산자 **`=`** 는 복합 할당 연산자입니다.

### <a name="assignment-operators-table"></a>할당 연산자 표

| 연산자 | 의미 |
|--|--|
| **`=`** | 첫 번째 피연산자에서 지정한 개체에 두 번째 피연산자의 값을 저장합니다(단순 할당). |
| **`*=`** | 첫 번째 피연산자의 값과 두 번째 피연산자의 값을 곱하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다. |
| **`/=`** | 첫 번째 피연산자의 값을 두 번째 피연산자의 값으로 나누어 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다. |
| **`%=`** | 두 번째 피연산자의 값에서 지정한 첫 번째 피연산자의 모듈러스를 가져와서 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다. |
| **`+=`** | 두 번째 연산자의 값과 첫 번째 연산자의 값을 더하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다. |
| **`-=`** | 첫 번째 피연산자의 값에서 두 번째 피연산자의 값을 빼서 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다. |
| **`<<=`** | 두 번째 피연산자의 값에서 지정한 비트 수만큼 첫 번째 피연산자의 값을 왼쪽으로 이동하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다. |
| **`>>=`** | 두 번째 피연산자의 값에서 지정한 비트 수만큼 첫 번째 피연산자의 값을 오른쪽으로 이동하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다. |
| **`&=`** | 첫 번째 및 두 번째 피연산자의 비트 AND를 구하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다. |
| **`^=`** | 첫 번째 및 두 번째 피연산자의 비트 배타적 OR를 구하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다. |
| **`|=`** | 첫 번째 및 두 번째 피연산자의 비트 포함 OR를 구하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다. |

### <a name="operator-keywords"></a>연산자 키워드

세 개의 복합 할당 연산자에는 해당 하는 키워드가 있습니다. 아래에 이 계정과 키의 예제가 나와 있습니다.

| 연산자 | 해당 |
|--|--|
| **`&=`** | **`and_eq`** |
| **`|=`** | **`or_eq`** |
| **`^=`** | **`xor_eq`** |

C + +에서는 이러한 연산자 키워드를 복합 할당 연산자에 대 한 대체 철자로 지정 합니다. C에서는 대체 철자를 헤더에 매크로로 제공 합니다 \<iso646.h> . C + +에서 대체 철자는 키워드입니다. \<iso646.h>또는이에 해당 하는 c + +는 사용 \<ciso646> 되지 않습니다. Microsoft c + +에서 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 또는 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션은 대체 철자를 사용 하도록 설정 하는 데 필요 합니다.

## <a name="example"></a>예제

```cpp
// expre_Assignment_Operators.cpp
// compile with: /EHsc
// Demonstrate assignment operators
#include <iostream>
using namespace std;
int main() {
   int a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555;

   a += b;      // a is 9
   b %= a;      // b is 6
   c >>= 1;      // c is 5
   d |= e;      // Bitwise--d is 0xFFFF

   cout  << "a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555" << endl
         << "a += b yields " << a << endl
         << "b %= a yields " << b << endl
         << "c >>= 1 yields " << c << endl
         << "d |= e yields " << hex << d << endl;
}
```

## <a name="simple-assignment"></a>단순 할당

단순 할당 연산자 ( **`=`** )는 두 번째 피연산자의 값이 첫 번째 피연산자로 지정 된 개체에 저장 되도록 합니다. 두 개체가 모두 산술 형식이 면 오른쪽 피연산자는 값을 저장 하기 전에 왼쪽의 형식으로 변환 됩니다.

및 형식의 개체는 또는이 아닌 **`const`** **`volatile`** 형식의 l-value에 할당할 수 있습니다 **`volatile`** **`const`** **`volatile`** .

클래스 형식 (, 및 형식)의 개체에 대 한 할당 **`struct`** **`union`** **`class`** 은 라는 함수에 의해 수행 됩니다 `operator=` . 이 연산자 함수의 기본 동작은 비트 복사를 수행하는 것이지만, 이 동작은 오버로드된 연산자를 사용하여 수정할 수 있습니다. 자세한 내용은 [연산자 오버로드](../cpp/operator-overloading.md)를 참조하세요. 클래스 형식에는 *복사 할당* 및 *이동 할당* 연산자도 있을 수 있습니다. 자세한 내용은 [복사 생성자 및 복사 할당 연산자](copy-constructors-and-copy-assignment-operators-cpp.md) 와 [이동 생성자 및 이동 할당 연산자](move-constructors-and-move-assignment-operators-cpp.md)를 참조 하세요.

지정된 기본 클래스에서 명확히 파생된 모든 클래스의 개체는 기본 클래스의 개체에 할당될 수 있습니다. 파생 클래스에서 기본 클래스로의 암시적 변환이 있지만 기본 클래스에서 파생 클래스로의 암시적 변환이 없기 때문에 반대의 경우도 마찬가지입니다. 예를 들면 다음과 같습니다.

```cpp
// expre_SimpleAssignment.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
class ABase
{
public:
    ABase() { cout << "constructing ABase\n"; }
};

class ADerived : public ABase
{
public:
    ADerived() { cout << "constructing ADerived\n"; }
};

int main()
{
    ABase aBase;
    ADerived aDerived;

    aBase = aDerived; // OK
    aDerived = aBase; // C2679
}
```

참조 형식에 대한 할당은 참조가 가리키는 개체에 할당이 수행되는 것처럼 작동합니다.

클래스 형식 개체의 경우 할당은 초기화와 다릅니다. 할당과 초기화가 어떻게 다를 수 있는지를 알아보려면 다음 코드를 살펴보세요.

```cpp
UserType1 A;
UserType2 B = A;
```

위의 코드에서는 이니셜라이저를 보여 줍니다. 여기에서는 `UserType2` 형식의 인수를 사용하는 `UserType1`의 생성자를 호출합니다. 다음 코드에서

```cpp
UserType1 A;
UserType2 B;

B = A;
```

아래의 할당 문은

```cpp
B = A;
```

다음과 같은 결과 중 하나를 생성할 수 있습니다.

- `operator=` `UserType2` `operator=` 인수를 사용 하 여 제공 되는 경우에 대 한 함수를 호출 합니다 `UserType1` .

- 명시적 변환 함수 `UserType1::operator UserType2`를 호출합니다(이러한 함수가 있는 경우).

- `UserType2::UserType2` 인수를 사용하고 결과를 복사하는 생성자 `UserType1`를 호출합니다(이러한 생성자가 있는 경우).

## <a name="compound-assignment"></a>복합 할당

복합 할당 연산자는 [할당 연산자 테이블](#assignment-operators-table)에 표시 됩니다. 이러한 연산자에는 *e1* *op* =  *e2*형식이 있습니다. 여기서 *e1* 은 수정할 수 없는 **`const`** l-value이 고 *e2* 는 다음과 같습니다.

- 산술 형식

- 포인터 ( *op* 가 또는 인 경우) **`+`****`-`**

*E1* *op* =  *e2* 폼은 *e1* **`=`** *e1* *op* *e2*로 동작 하지만 *e1* 은 한 번만 평가 됩니다.

열거 형식에 대한 복합 할당은 오류 메시지를 생성합니다. 왼쪽 피연산자가 포인터 형식이 면 오른쪽 피연산자가 포인터 형식 이어야 합니다. 그렇지 않으면 0으로 계산 되는 상수 식 이어야 합니다. 왼쪽 피연산자가 정수 계열 형식이 면 오른쪽 피연산자가 포인터 형식이 아니어야 합니다.

## <a name="result-of-assignment-operators"></a>할당 연산자의 결과

대입 연산자는 할당된 후 왼쪽 피연산자에서 지정한 개체 값을 반환합니다. 결과 형식은 왼쪽 피연산자의 형식입니다. 할당 식의 결과는 항상 l-value입니다. 이러한 연산자는 오른쪽에서 왼쪽으로 결합됩니다. 왼쪽 피연산자는 수정 가능한 l-value여야 합니다.

ANSI C에서 대입 식의 결과는 l-value가 아닙니다. 즉, C에서는 유효한 c + + 식이 `(a += b) += c` 허용 되지 않습니다.

## <a name="see-also"></a>참고 항목

[이항 연산자로 구성된 식](../cpp/expressions-with-binary-operators.md)<br/>
[C + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 할당 연산자](../c-language/c-assignment-operators.md)
