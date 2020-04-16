---
title: switch명령문(C++)
description: Microsoft 비주얼 스튜디오 C++의 표준 C++ switch 문을 참조하십시오.
ms.date: 04/15/2020
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
no-loc:
- switch
- case
- default
- break
- while
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: 1f65d4699423d74be9c75a9be47e543a9a1256e2
ms.sourcegitcommit: 9266fc76ac2e872e35a208b4249660dfdfc87cba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81480830"
---
# <a name="opno-locswitch-statement-c"></a>switch명령문(C++)

정수 계열 식의 값에 따라 코드의 여러 섹션 중에서 선택할 수 있습니다.

## <a name="syntax"></a>구문

> **`switch (`**\[ *초기화* **`;`**] *표현식***`)`**\
> **`{`**\
> &nbsp;&nbsp;&nbsp;&nbsp;**`case`***상수 식* **`:`** *문*\
> &nbsp;&nbsp;&nbsp;&nbsp;\[**`default :`***문*] \
> **`}`**

## <a name="remarks"></a>설명

*식에는* 정수 형식이 있거나 정수 형식에 대한 명확한 변환이 있는 클래스 형식이어야 합니다. 통합 승격은 표준 변환에 설명된 대로 [수행됩니다.](standard-conversions.md)

**switch** 문 본문은 일련의 **case** 레이블과 선택적 **default** 레이블로 구성됩니다. 전체적으로 레이블 다음에 있는 문을 *레이블이 있는* 문이라고 합니다. 레이블이 지정된 문은 구문 요구 **switch** 사항이 아니지만 문이 없으면 의미가 없습니다. 문에서 **case** 두 개의 상수 식은 동일한 값으로 평가할 수 없습니다. 레이블은 **default** 한 번만 나타날 수 있습니다. 문은 **default** 종종 끝에 배치되지만 **switch** 명령문 본문에 아무 곳에나 나타날 수 있습니다. A **case** **default** 또는 레이블은 **switch** 명령문 내에서만 나타날 수 있습니다.

각 **case** 레이블의 *상수 표현식은* *식의*유형으로 변환됩니다. 그런 다음 같음 *표현식과* 비교합니다. 컨트롤은 **case** *상수 식이* *식의*값과 일치하는 문을 전달합니다. 결과적으로 발생하는 동작은 다음 표에 나와 있습니다.

### <a name="switch-statement-behavior"></a>문 비헤이비어 전환

| 조건 | 작업 |
|--|--|
| 변환된 값이 승격된 제어 식의 값과 일치합니다. | 제어가 해당 레이블 뒤에 오는 문으로 전송됩니다. |
| **case** 상수는 레이블의 상수와 일치하지 않습니다. 레이블이 **default** 있습니다. | 컨트롤이 레이블로 **default** 전송됩니다. |
| **case** 상수는 레이블의 상수와 일치하지 않습니다. 레이블이 없습니다. **default** | 컨트롤은 명령문 다음의 **switch** 명령문으로 전송됩니다. |

일치하는 식이 발견되면 이후 **case** 또는 **default** 레이블을 통해 실행을 계속할 수 있습니다. 문은 [`break`](../cpp/break-statement-cpp.md) 실행을 중지하고 **switch** 명령문 다음의 명령문으로 제어를 전송하는 데 사용됩니다. **break** 문이 없으면 일치하는 **case** 레이블에서 의 끝까지 의 **switch** **default** 모든 문이 실행됩니다. 다음은 그 예입니다.

```cpp
// switch_statement1.cpp
#include <stdio.h>

int main() {
   const char *buffer = "Any character stream";
   int uppercase_A, lowercase_a, other;
   char c;
   uppercase_A = lowercase_a = other = 0;

   while ( c = *buffer++ )   // Walks buffer until NULL
   {
      switch ( c )
      {
         case 'A':
            uppercase_A++;
            break;
         case 'a':
            lowercase_a++;
            break;
         default:
            other++;
      }
   }
   printf_s( "\nUppercase A: %d\nLowercase a: %d\nTotal: %d\n",
      uppercase_A, lowercase_a, (uppercase_A + lowercase_a + other) );
}
```

위의 예제에서 `uppercase_A`는 `c`가 대문자 `'A'`인 경우 증가됩니다. 문 본문 및 컨트롤의 실행을 종료 한 **while** 후 **break** `uppercase_A++` 문은 루프에 전달됩니다. **switch** **break** 문이 없으면 실행이 다음 레이블이 지정된 문으로 "넘어지므로" `lowercase_a` 증가될 `other` 수 있습니다. 비슷한 목적은 에 **break** 대한 `case 'a'`명령문에 의해 제공됩니다. 소문자인 `c` `'a'` `lowercase_a` 경우 증분되고 **break** 문은 **switch** 명령문 본문을 종료합니다. `'a'` 또는 `c` `'A'`하지 않으면 **default** 문이 실행 됩니다.

**Visual Studio 2017 이상:** [(/std:c++17)](../build/reference/std-specify-language-standard-version.md) `[[fallthrough]]` 특성은 C++17 표준에 지정됩니다. **switch** 명령문에서 사용할 수 있습니다. 컴파일러 또는 코드를 읽는 모든 사람이 의도적인 가을 스루 동작에 대한 힌트입니다. 현재 Microsoft C++ 컴파일러는 잘못된 동작에 대해 경고하지 않으므로 이 특성은 컴파일러 동작에 영향을 주지 않습니다. 이 예제에서는 특성이 종료되지 않은 레이블이 지정되지 않은 문 내의 빈 문에 적용됩니다. 즉, 세미콜론이 필요합니다.

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

**Visual Studio 2017 버전 15.3** [이상(/std:c++17).](../build/reference/std-specify-language-standard-version.md) switch *문에초기화* 절이 있을 수 있습니다. switch 문이 블록으로 제한되는 변수를 소개하고 초기화합니다.

```cpp
    switch (Gadget gadget(args); auto s = gadget.get_status())
    {
    case status::good:
        gadget.zip();
        break;
    case status::bad:
        throw BadGadget();
    };
```

명령문의 내부 블록에는 가능한 모든 실행 경로에 의해 우회되지 않는 *도달 가능한*한 초기화가 있는 정의가 포함될 수 있습니다. **switch** 이러한 선언을 사용하여 정의된 이름에는 로컬 범위가 있습니다. 다음은 그 예입니다.

```cpp
// switch_statement2.cpp
// C2360 expected
#include <iostream>
using namespace std;
int main(int argc, char *argv[])
{
    switch( tolower( *argv[1] ) )
    {
        // Error. Unreachable declaration.
        char szChEntered[] = "Character entered was: ";

    case 'a' :
        {
        // Declaration of szChEntered OK. Local scope.
        char szChEntered[] = "Character entered was: ";
        cout << szChEntered << "a\n";
        }
        break;

    case 'b' :
        // Value of szChEntered undefined.
        cout << szChEntered << "b\n";
        break;

    default:
        // Value of szChEntered undefined.
        cout << szChEntered << "neither a nor b\n";
        break;
    }
}
```

**switch** 문을 중첩할 수 있습니다. 중첩되면 **case** 또는 **default** 레이블은 해당 문을 **switch** 둘러싸는 가장 가까운 문과 연결됩니다.

### <a name="microsoft-specific-behavior"></a>Microsoft 관련 동작

Microsoft C는 **case** **switch** 명령문의 값 수를 제한하지 않습니다. 이 수는 사용 가능한 메모리에 의해서만 제한됩니다. ANSI C는 성명서에 **case** 최소 257개의 **switch** 레이블을 허용해야 합니다.

마이크로 default 소프트 C에 대한 마이크로 소프트 확장이 활성화되어 있다는 것입니다. [/Za](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션을 사용하여 이러한 확장을 사용하지 않도록 설정합니다.

## <a name="see-also"></a>참고 항목

[선택문](../cpp/selection-statements-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)
