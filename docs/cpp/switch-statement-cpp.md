---
title: :::no-loc(switch):::문 (c + +)
description: 'Microsoft Visual Studio c + +의 표준 c + + 문에 대 한 참조 :::no-loc(switch)::: 입니다.'
ms.date: 04/25/2020
f1_keywords:
- :::no-loc(default):::_cpp
- :::no-loc(switch):::_cpp
- :::no-loc(case):::_cpp
helpviewer_keywords:
- ':::no-loc(switch)::: keyword [C++]'
- ':::no-loc(case)::: keyword [C++], in :::no-loc(switch)::: statements'
- ':::no-loc(default)::: keyword [C++]'
no-loc:
- ':::no-loc(switch):::'
- ':::no-loc(case):::'
- ':::no-loc(default):::'
- ':::no-loc(break):::'
- ':::no-loc(while):::'
- ':::no-loc(opt):::'
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: d71989b6d8af0213c4cd6d4fbd8d5a84b318701a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223592"
---
# <a name="no-locswitch-statement-c"></a>`:::no-loc(switch):::`문 (c + +)

정수 계열 식의 값에 따라 코드의 여러 섹션 중에서 선택할 수 있습니다.

## <a name="syntax"></a>구문

> *`selection-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp;**`:::no-loc(switch):::`**&nbsp;**`(`**&nbsp;*`init-statement`*<sub>:::no-loc(opt):::</sub> <sup>C + + 17</sup>&nbsp;*`condition`*&nbsp;**`)`**&nbsp;*`statement`*

> *`init-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression-statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`simple-declaration`*

> *`condition`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`attribute-specifier-seq`*<sub>:::no-loc(opt):::</sub>&nbsp;*`decl-specifier-seq`*&nbsp;*`declarator`*&nbsp;*`brace-or-equal-initializer`*

> *`labeled-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(case):::`**&nbsp;*`constant-expression`*&nbsp;**`:`**&nbsp;*`statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(default):::`**&nbsp;**`:`**&nbsp;*`statement`*

## <a name="remarks"></a>설명

**`:::no-loc(switch):::`** 문을 통해 컨트롤은 *`condition`* 의 값에 따라 문 본문에서 하나의 *`labeled-statement`* 로 전송됩니다.

는 *`condition`* 정수 계열 형식 이거나 정수 계열 형식으로의 명확한 변환이 있는 클래스 형식 이어야 합니다. 정수 계열 확장은 [표준 변환](standard-conversions.md)에 설명 된 대로 발생 합니다.

**`:::no-loc(switch):::`** 문 본문은 일련의 **`:::no-loc(case):::`** 레이블과 :::no-loc(opt)::: ional 레이블로 구성 됩니다 **`:::no-loc(default):::`** . 는 *`labeled-statement`* 다음과 같은 레이블 및 문 중 하나입니다. 레이블이 지정 된 문은 구문 요구 사항이 아니지만 **`:::no-loc(switch):::`** 문은 필요 하지 않습니다. 문의 두 *`constant-expression`* 값 **`:::no-loc(case):::`** 은 동일한 값으로 계산 될 수 없습니다. **`:::no-loc(default):::`** 레이블은 한 번만 나타날 수 있습니다. **`:::no-loc(default):::`** 문은 종종 끝에 배치 되지만 문 본문의 어디에 나 나타날 수 있습니다 **`:::no-loc(switch):::`** . **`:::no-loc(case):::`** 또는 **`:::no-loc(default):::`** 레이블은 **`:::no-loc(switch):::`** 문 안에만 나타날 수 있습니다.

*`constant-expression`* 각 레이블의는 **`:::no-loc(case):::`** 와 동일한 형식의 상수 값으로 변환 됩니다 *`condition`* . 그런 다음와 비교 하 여 *`condition`* 같은지 비교 합니다. 컨트롤은 **`:::no-loc(case):::`** *`constant-expression`* 의 값과 일치 하는 값 뒤의 첫 번째 문으로 전달 *`condition`* 됩니다. 결과적으로 발생하는 동작은 다음 표에 나와 있습니다.

### <a name="no-locswitch-statement-behavior"></a>`:::no-loc(switch):::`문 동작

| 조건 | 작업 |
|--|--|
| 변환된 값이 승격된 제어 식의 값과 일치합니다. | 제어가 해당 레이블 뒤에 오는 문으로 전송됩니다. |
| 레이블의 상수와 일치 하는 모든 상수는 없습니다 **`:::no-loc(case):::`** **`:::no-loc(default):::`** . 레이블이 있습니다. | 컨트롤이 레이블로 전송 됩니다 **`:::no-loc(default):::`** . |
| 모든 상수는 레이블의 상수와 일치 하지 않습니다 **`:::no-loc(case):::`** **`:::no-loc(default):::`** . 레이블이 없습니다. | 제어가 문 뒤의 문으로 전달 됩니다 **`:::no-loc(switch):::`** . |

일치 하는 식이 있는 경우 나중에 또는 레이블을 통해 실행을 계속할 수 있습니다 **`:::no-loc(case):::`** **`:::no-loc(default):::`** . 문은 [`:::no-loc(break):::`](../cpp/:::no-loc(break):::-statement-cpp.md) 실행을 중지 하 고 문 뒤의 문으로 제어를 전송 하는 데 사용 됩니다 **`:::no-loc(switch):::`** . 문이 없으면를 비롯 하 여의 **`:::no-loc(break):::`** **`:::no-loc(case):::`** 끝 부분에 대 한 일치 하는 레이블의 모든 문이 **`:::no-loc(switch):::`** **`:::no-loc(default):::`** 실행 됩니다. 예를 들면 다음과 같습니다.

```cpp
// :::no-loc(switch):::_statement1.cpp
#include <stdio.h>

int main() {
   const char *buffer = "Any character stream";
   int upper:::no-loc(case):::_A, lower:::no-loc(case):::_a, other;
   char c;
   upper:::no-loc(case):::_A = lower:::no-loc(case):::_a = other = 0;

   :::no-loc(while)::: ( c = *buffer++ )   // Walks buffer until NULL
   {
      :::no-loc(switch)::: ( c )
      {
         :::no-loc(case)::: 'A':
            upper:::no-loc(case):::_A++;
            :::no-loc(break):::;
         :::no-loc(case)::: 'a':
            lower:::no-loc(case):::_a++;
            :::no-loc(break):::;
         :::no-loc(default)::::
            other++;
      }
   }
   printf_s( "\nUpper:::no-loc(case)::: A: %d\nLower:::no-loc(case)::: a: %d\nTotal: %d\n",
      upper:::no-loc(case):::_A, lower:::no-loc(case):::_a, (upper:::no-loc(case):::_A + lower:::no-loc(case):::_a + other) );
}
```

위의 예제에서 `upper:::no-loc(case):::_A` 가 upper 이면가 증가 `c` :::no-loc(case)::: `'A'` 합니다. **`:::no-loc(break):::`** 뒤의 문은 `upper:::no-loc(case):::_A++` 문 본문의 실행을 종료 **`:::no-loc(switch):::`** 하 고 제어를 **`:::no-loc(while):::`** 루프로 전달 합니다. 문 없이 **`:::no-loc(break):::`** 실행은 레이블이 지정 된 다음 문으로 "이동" 하므로 `lower:::no-loc(case):::_a` 및 `other` 도 증가 합니다. 의 문에서는 이와 유사한 용도로 제공 됩니다 **`:::no-loc(break):::`** `:::no-loc(case)::: 'a'` . `c`가 낮을수록가 :::no-loc(case)::: `'a'` `lower:::no-loc(case):::_a` 증가 하 고 **`:::no-loc(break):::`** 문이 문 본문을 종료 합니다 **`:::no-loc(switch):::`** . 이 `c` 또는가 아닌 경우 `'a'` `'A'` **`:::no-loc(default):::`** 문이 실행 됩니다.

**Visual Studio 2017 이상:** ( [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)과 함께 사용 가능) `[[fallthrough]]` 특성은 c + + 17 표준에 지정 되어 있습니다. 문에서 사용할 수 있습니다 **`:::no-loc(switch):::`** . 컴파일러에 대 한 힌트 또는 코드를 읽는 모든 사용자가 의도적으로 동작을 제어 합니다. Microsoft c + + 컴파일러는 현재 fallthrough 동작에 대 한 경고를 표시 하지 않으므로이 특성은 컴파일러 동작에 영향을 주지 않습니다. 이 예제에서 특성은 종결 되지 않은 레이블 문 내의 빈 문에 적용 됩니다. 즉, 세미콜론이 필요 합니다.

```cpp
int main()
{
    int n = 5;
    :::no-loc(switch)::: (n)
    {

    :::no-loc(case)::: 1:
        a();
        :::no-loc(break):::;
    :::no-loc(case)::: 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    :::no-loc(case)::: 3:
        c();
        :::no-loc(break):::;
    :::no-loc(default)::::
        d();
        :::no-loc(break):::;
    }

    return 0;
}
```

**Visual Studio 2017 버전 15.3 이상** ( [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)과 함께 사용 가능). **`:::no-loc(switch):::`** 문에는 *`init-statement`* 세미콜론으로 끝나는 절이 있을 수 있습니다. 범위가 문의 블록으로 제한 되는 변수를 소개 하 고 초기화 합니다 **`:::no-loc(switch):::`** .

```cpp
    :::no-loc(switch)::: (Gadget gadget(args); auto s = gadget.get_status())
    {
    :::no-loc(case)::: status::good:
        gadget.zip();
        :::no-loc(break):::;
    :::no-loc(case)::: status::bad:
        throw BadGadget();
    };
```

문의 내부 블록은 **`:::no-loc(switch):::`** 사용 가능한 모든 실행 경로에 의해 바이패스 되지 않는 경우 이니셜라이저 *reachable*를 사용 하는 정의를 포함할 수 있습니다. 이러한 선언을 사용하여 정의된 이름에는 로컬 범위가 있습니다. 예를 들면 다음과 같습니다.

```cpp
// :::no-loc(switch):::_statement2.cpp
// C2360 expected
#include <iostream>
using namespace std;
int main(int argc, char *argv[])
{
    :::no-loc(switch):::( tolower( *argv[1] ) )
    {
        // Error. Unreachable declaration.
        char szChEntered[] = "Character entered was: ";

    :::no-loc(case)::: 'a' :
        {
        // Declaration of szChEntered OK. Local scope.
        char szChEntered[] = "Character entered was: ";
        cout << szChEntered << "a\n";
        }
        :::no-loc(break):::;

    :::no-loc(case)::: 'b' :
        // Value of szChEntered undefined.
        cout << szChEntered << "b\n";
        :::no-loc(break):::;

    :::no-loc(default)::::
        // Value of szChEntered undefined.
        cout << szChEntered << "neither a nor b\n";
        :::no-loc(break):::;
    }
}
```

**`:::no-loc(switch):::`** 문은 중첩 될 수 있습니다. 중첩 **`:::no-loc(case):::`** 된 경우 또는 **`:::no-loc(default):::`** 레이블은이를 포함 하는 가장 가까운 문과 연결 **`:::no-loc(switch):::`** 됩니다.

### <a name="microsoft-specific-behavior"></a>Microsoft 전용 동작

Microsoft c + +는 문의 값 수를 제한 하지 않습니다 **`:::no-loc(case):::`** **`:::no-loc(switch):::`** . 이 수는 사용 가능한 메모리에 의해서만 제한됩니다.

## <a name="see-also"></a>참고 항목

[선택문](../cpp/selection-statements-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)
