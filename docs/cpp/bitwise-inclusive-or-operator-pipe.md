---
title: '포괄적 비트 OR 연산자: |'
ms.date: 06/14/2018
f1_keywords:
- '|'
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
ms.openlocfilehash: 38def2b1ac585c751699227d2a065b45145d290d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190757"
---
# <a name="bitwise-inclusive-or-operator-"></a>포괄적 비트 OR 연산자: |

## <a name="syntax"></a>구문

> *expression1* **|** *식 2*

## <a name="remarks"></a>설명

비트 포함 OR 연산자 ( **&#124;** )는 첫 번째 피연산자의 각 비트를 두 번째 피연산자의 해당 비트와 비교 합니다. 두 비트 중 하나가 1이면 해당 결과 비트가 1로 설정되고, 그렇지 않으면 해당 결과 비트가 0으로 설정됩니다.

포괄적 비트 OR 연산자에 대한 두 피연산자는 모두 정수 계열 형식이어야 합니다. [표준 변환](standard-conversions.md) 에서 다루는 일반적인 산술 변환은 피연산자에 적용 됩니다.

## <a name="operator-keyword-for-124"></a>&#124;에 대한 연산자 키워드

**Bitor** 연산자는에 **&#124;** 해당 하는 텍스트입니다. 프로그램에서 **bitor** 연산자에 액세스 하는 두 가지 방법이 있습니다. 헤더 파일 \<iso646 > 포함 하거나 [/za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장 사용 안 함) 컴파일러 옵션을 사용 하 여 컴파일합니다.

## <a name="example"></a>예제

```cpp
// expre_Bitwise_Inclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise inclusive OR
#include <iostream>
using namespace std;

int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...
}
```

## <a name="see-also"></a>참고 항목

[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 비트 연산자](../c-language/c-bitwise-operators.md)
