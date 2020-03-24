---
title: switch 문 (C++)
ms.date: 05/06/2019
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: 6b09c0eac939f7ca6a12b68ce5deb3fb83ad27c6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160816"
---
# <a name="switch-statement-c"></a>switch 문 (C++)

정수 계열 식의 값에 따라 코드의 여러 섹션 중에서 선택할 수 있습니다.

## <a name="syntax"></a>구문

```
   switch ( init; expression )
   case constant-expression : statement
   [default  : statement]
```

## <a name="remarks"></a>설명

*식은* 정수 계열 형식 또는 정수 계열 형식으로의 명확한 변환이 있는 클래스 형식 이어야 합니다. 정수 계열 확장은 [표준 변환](standard-conversions.md)에 설명 된 대로 수행 됩니다.

**Switch** 문 본문은 일련의 **case** 레이블과 선택적 **default** 레이블로 구성 됩니다. **Case** 문에서 두 개의 상수 식이 동일한 값으로 계산 될 수 없습니다. **기본** 레이블은 한 번만 나타날 수 있습니다. 레이블이 지정 된 문은 구문 요구 사항은 아니지만 **switch** 문에는 의미가 없습니다.   기본 문은 끝에 오지 않아도 되며 switch 문의 본문 중 어느 위치에나 나타날 수 있습니다. case 또는 default 레이블은 switch 문 내에만 나타날 수 있습니다.

각 **case** 레이블의 *상수 식은* *식* 의 형식으로 변환 되 고 *식* 과 같은지 비교 됩니다. **Case** *상수 식이* *식*의 값과 일치 하는 문으로 제어가 전달 됩니다. 결과적으로 발생하는 동작은 다음 표에 나와 있습니다.

### <a name="switch-statement-behavior"></a>switch 문 동작

|조건|작업|
|---------------|------------|
|변환된 값이 승격된 제어 식의 값과 일치합니다.|제어가 해당 레이블 뒤에 오는 문으로 전송됩니다.|
|**Case** 레이블의 상수와 일치 하는 상수가 없습니다. **기본** 레이블이 있습니다.|컨트롤은 **기본** 레이블로 전송 됩니다.|
|**Case** 레이블의 상수와 일치 하는 상수가 없습니다. **기본** 레이블이 없습니다.|**Switch** 문 뒤의 문으로 제어가 전송 됩니다.|

일치 하는 식이 발견 되 면 방해가는 다음 **case** 또는 **default** 레이블에 의해 제어 되지 않습니다. [Break](../cpp/break-statement-cpp.md) 문은 **switch** 문 뒤의 문으로 실행을 중지 하 고 제어를 전달 하는 데 사용 됩니다. **Break** 문이 없으면 **기본값**을 포함 하는 **스위치**끝에 대 한 일치 하는 **case** 레이블의 모든 문이 실행 됩니다. 다음은 그 예입니다.

```cpp
// switch_statement1.cpp
#include <stdio.h>

int main() {
   char *buffer = "Any character stream";
   int capa, lettera, nota;
   char c;
   capa = lettera = nota = 0;

   while ( c = *buffer++ )   // Walks buffer until NULL
   {
      switch ( c )
      {
         case 'A':
            capa++;
            break;
         case 'a':
            lettera++;
            break;
         default:
            nota++;
      }
   }
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",
      capa, lettera, (capa + lettera + nota) );
}
```

위의 예제에서 `capa`는 `c`가 대문자 `A`인 경우 증가됩니다. `capa++` after **break** 문은 **switch** 문 본문의 실행을 종료 하 고 컨트롤을 **while** 루프로 전달 합니다. **Break** 문이 없으면 실행이 레이블 지정 된 다음 문으로 "이동" 하 여 `lettera` 및 `nota`도 증가 합니다. 이와 비슷한 용도는 `case 'a'`에 대 한 **break** 문으로 제공 됩니다. `c` 소문자 `a`경우 `lettera` 증가 하 고 **break** 문은 **switch** 문 본문을 종료 합니다. `c` `a` 또는 `A`아닌 경우 **기본** 문이 실행 됩니다.

**Visual Studio 2017 이상:** ( [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)에서 사용 가능) `[[fallthrough]]` 특성은 c + + 17 표준에 지정 되어 있습니다. **Switch** 문에는 컴파일러에 대 한 힌트로 사용 될 수 있습니다 (또는 코드를 읽는 사람에 대 한 힌트). Microsoft C++ 컴파일러는 현재 fallthrough 동작에 대해 경고 하지 않으므로이 특성은 컴파일러 동작에 영향을 주지 않습니다. 특성은 레이블 문 내의 빈 문에 적용 됩니다. 즉, 세미콜론이 필요 합니다.

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

**Visual Studio 2017 버전 15.3 이상** ( [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)과 함께 사용 가능): switch 문은 해당 범위가 switch 문의 블록으로 제한 되는 변수를 도입 하 고 초기화할 수 있습니다.

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

**Switch** 문의 내부 블록은 사용 가능한 모든 실행 경로에서 무시 되지 않는, 연결 가능한 한 초기화를 포함 하는 정의를 포함할 수 있습니다. 이러한 선언을 사용하여 정의된 이름에는 로컬 범위가 있습니다. 다음은 그 예입니다.

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

**Switch** 문은 중첩 될 수 있습니다. 이러한 경우 **case** 또는 **default** 레이블은 해당 레이블을 묶는 가장 가까운 **switch** 문에 연결 됩니다.

**Microsoft 전용**

Microsoft C는 **switch** 문의 case 값 수를 제한 하지 않습니다. 이 수는 사용 가능한 메모리에 의해서만 제한됩니다. ANSI C를 사용 하려면 **switch** 문에 최소 257의 case 레이블이 허용 되어야 합니다.

기본적으로 Microsoft C에는 Microsoft 확장을 사용하도록 설정되어 있습니다. 이러한 확장을 사용 하지 않도록 설정 하려면 [/za](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션을 사용 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[선택 문](../cpp/selection-statements-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)
