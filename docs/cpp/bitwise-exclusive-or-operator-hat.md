---
title: '배타적 비트 OR 연산자: ^'
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
ms.openlocfilehash: 9a44dc60a985729aae79ed0e2e48c44adace647b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190718"
---
# <a name="bitwise-exclusive-or-operator-"></a>배타적 비트 OR 연산자: ^

## <a name="syntax"></a>구문

```
expression ^ expression
```

## <a name="remarks"></a>설명

배타적 비트 OR 연산자 ( **^** )는 첫 번째 피연산자의 각 비트를 두 번째 피연산자의 해당 비트와 비교 합니다. 두 비트 중 하나가 0이고 다른 비트가 1이면 해당 결과 비트는 1로 설정됩니다. 그렇지 않으면 해당 결과 비트가 0으로 설정됩니다.

배타적 비트 OR 연산자에 대한 피연산자는 둘 다 정수 계열 형식이어야 합니다. [표준 변환](standard-conversions.md) 에서 다루는 일반적인 산술 변환은 피연산자에 적용 됩니다.

## <a name="operator-keyword-for-"></a>^에 대한 연산자 키워드

**Xor** 연산자는 **^** 에 해당 하는 텍스트입니다. 프로그램에서 **xor** 연산자에 액세스 하는 두 가지 방법이 있습니다. 헤더 파일 `iso646.h`포함 하거나 [/za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장 사용 안 함) 컴파일러 옵션을 사용 하 여 컴파일합니다.

## <a name="example"></a>예제

```cpp
// expre_Bitwise_Exclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise exclusive OR
#include <iostream>
using namespace std;
int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xFFFF;      // pattern 1111 ...

   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...
}
```

## <a name="see-also"></a>참고 항목

[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
