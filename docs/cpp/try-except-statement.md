---
title: try-except 문
description: Microsoft C++는 __try 및 구조화된 예외 처리 문을 __except 참조합니다.
ms.date: 04/03/2020
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- _exception_info
- __except
- _except
- _exception_code
- __except_cpp
- _exception_info_cpp
helpviewer_keywords:
- __try keyword [C++]
- EXCEPTION_CONTINUE_EXECUTION macro
- EXCEPTION_CONTINUE_SEARCH macro
- EXCEPTION_EXECUTE_HANDLER macro
- GetExceptionCode function
- try-catch keyword [C++], try-except keyword [C++]
- _exception_code keyword [C++]
- try-except keyword [C++]
- _exception_info keyword [C++]
- _abnormal_termination keyword [C++]
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
ms.openlocfilehash: 132edf7cc9819637fafa3947686972d311924b99
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366230"
---
# <a name="try-except-statement"></a>try-except 문

**try-except** 문은 C 및 C++ 언어에서 구조화 된 예외 처리를 지원하는 Microsoft 확장입니다. 이 확장은 **Microsoft에 특정합니다.**

## <a name="syntax"></a>구문

> **\_\_시도**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;보호된 코드<br/>
> }<br/>
> (식) ** \_ \_** *expression*<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;예외 처리기 코드<br/>
> }

## <a name="remarks"></a>설명

**try-except** 문은 C 및 C++ 언어에 대한 Microsoft 확장입니다. 이를 통해 대상 응용 프로그램은 일반적으로 프로그램 실행을 종료하는 이벤트가 발생할 때 제어할 수 있습니다. 이러한 이벤트를 *구조화 된 예외*또는 짧은 *예외라고 합니다.* 이러한 예외를 처리하는 메커니즘을 *SEH(구조화 된 예외 처리)라고* 합니다.

관련 정보는 [try-finally 문을](../cpp/try-finally-statement.md)참조하십시오.

예외는 하드웨어 기반 또는 소프트웨어 기반일 수 있습니다. 구조화 된 예외 처리는 응용 프로그램이 하드웨어 또는 소프트웨어 예외에서 완전히 복구 할 수없는 경우에도 유용합니다. SEH를 사용하면 오류 정보를 표시하고 응용 프로그램의 내부 상태를 트래피머하여 문제를 진단할 수 있습니다. 재현하기 쉽지 않은 간헐적인 문제에 특히 유용합니다.

> [!NOTE]
> 구조적 예외 처리는 Win32에서 C 및 C++ 소스 파일에 대해 작동하지만 그러나 C++를 위해 특별히 설계된 것은 아닙니다. C++ 예외 처리를 사용하여 코드의 이식성이 향상되는지 확인할 수 있습니다. 또한 C++ 예외 처리는 모든 형식의 예외를 처리할 수 있다는 점에서 보다 유연합니다. C++ 프로그램의 경우 기본 C++ 예외 처리인 [try, catch 및 throw](../cpp/try-throw-and-catch-statements-cpp.md) 문을 사용하는 것이 좋습니다.

**__try** 절 다음의 복합 문은 *본문* 또는 *보호된* 섹션입니다. **__except** 식을 *필터* 식이라고도 합니다. 이 값은 예외를 처리하는 방법을 결정합니다. **__except** 절 다음의 복합 문은 예외 처리기입니다. 처리기는 본문 섹션을 실행 하는 동안 예외가 발생 하는 경우 수행할 작업을 지정 합니다. 다음과 같이 실행됩니다.

1. 보호된 섹션이 실행됩니다.

1. 보호된 섹션을 실행하는 동안 예외가 발생하지 않으면 **__except** 절 다음의 명령문에서 실행이 계속됩니다.

1. 보호된 섹션을 실행하는 동안 또는 보호된 섹션이 호출하는 루틴에서 예외가 발생하는 경우 **__except** 표현식이 평가됩니다. 세 가지 값을 사용할 수 있습니다.

   - `EXCEPTION_CONTINUE_EXECUTION`(-1) 예외는 해제됩니다. 예외가 발생한 지점에서 계속 실행합니다.

   - `EXCEPTION_CONTINUE_SEARCH`(0) 예외가 인식되지 않습니다. **try-except** 문을 포함하는 처리기를 먼저 검색한 후, 그 다음으로 우선 순위가 높은 처리기를 검색하는 순으로 처리기 스택을 계속 검색합니다.

   - `EXCEPTION_EXECUTE_HANDLER`(1) 예외가 인정됩니다. **__except** 복합 문을 실행 하여 예외 처리기로 제어를 전송한 다음 **__except** 블록 이후에 실행을 계속합니다.

**__except** 식은 C 식으로 평가됩니다. 단일 값, 조건식 연산자 또는 쉼표 연산자로 제한됩니다. 더 광범위한 처리가 필요한 경우 식은 위에 나열된 세 값 중 하나를 반환하는 루틴을 호출할 수 있습니다.

각 애플리케이션에는 자체 예외 처리기를 사용할 수 있습니다.

**__try** 문으로 이동하는 것은 유효하지 않지만 하나에서 뛰어 내리는 것은 유효합니다. **try-except** 문을 실행하는 도중에 프로세스가 종료되는 경우 예외 처리기가 호출되지 않습니다.

이전 버전과의 호환성을 위해 **_try** **_except**및 **_leave** **__try**동의어입니다. **__except**및 컴파일러 옵션 [ \(/Za Disable 언어 확장)이](../build/reference/za-ze-disable-language-extensions.md) 지정되지 않는 한 **__leave.**

### <a name="the-__leave-keyword"></a>__leave 키워드

**__leave** 키워드는 **try-except** 문의 보호된 섹션 내에서만 유효하며 그 효과는 보호된 섹션의 끝으로 이동하는 것입니다. 실행은 예외 처리기 뒤에 나오는 첫 번째 문에서 계속 됩니다.

**goto** 문은 보호된 섹션에서 벗어날 수도 있으며 **try-finally** 문에서와 마찬가지로 성능이 저하되지 않습니다. 스택 해제가 발생하지 않기 때문입니다. 그러나 **goto** 문 대신 **__leave** 키워드를 사용하는 것이 좋습니다. 그 이유는 보호된 섹션이 크거나 복잡한 경우 프로그래밍 실수를 할 가능성이 적기 때문입니다.

### <a name="structured-exception-handling-intrinsic-functions"></a>구조적 예외 처리 내장 함수

구조화 된 예외 처리 는 **try-except** 문과 함께 사용할 수 있는 두 [GetExceptionInformation](/windows/win32/Debug/getexceptioninformation)가지 내장 [함수를](/windows/win32/Debug/getexceptioncode) 제공 합니다.

`GetExceptionCode`예외의 코드(32비트 정수)를 반환합니다.

내장 함수는 `GetExceptionInformation` 예외에 대한 추가 정보를 포함하는 [EXCEPTION_POINTERS](/windows/win32/api/winnt/ns-winnt-exception_pointers) 구조에 대한 포인터를 반환합니다. 이 포인터를 통하여, 하드웨어 예외 발생 시의 컴퓨터 상태에 액세스할 수 있습니다. 구조는 다음과 같습니다.

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

포인터 `PEXCEPTION_RECORD` 유형은 `PCONTEXT` 포함 파일 \<winnt.h> `_EXCEPTION_RECORD` 정의되며, `_CONTEXT` 포함 파일 \<excpt.h>

예외 처리기 내에서 사용할 `GetExceptionCode` 수 있습니다. 그러나 예외 필터 `GetExceptionInformation` 식 내에서만 사용할 수 있습니다. 가리키는 정보는 일반적으로 스택에 있으며 컨트롤이 예외 처리기로 전송될 때 더 이상 사용할 수 없습니다.

내재 함수 [비정상적인 Termination는](/windows/win32/Debug/abnormaltermination) 종료 처리기 내에서 사용할 수 있습니다. **try-finally** 문의 본문이 순차적으로 종료되면 0을 반환합니다. 다른 모든 경우에는 1이 반환됩니다.

\<excpt.h> 이러한 내장 함수에 대한 몇 가지 대체 이름을 정의합니다.

`GetExceptionCode`는 `_exception_code`와 같습니다.

`GetExceptionInformation`는 `_exception_info`와 같습니다.

`AbnormalTermination`는 `_abnormal_termination`와 같습니다.

## <a name="example"></a>예제

```cpp
// exceptions_try_except_Statement.cpp
// Example of try-except and try-finally statements
#include <stdio.h>
#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION
#include <excpt.h>

int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep)
{
    puts("in filter.");
    if (code == EXCEPTION_ACCESS_VIOLATION)
    {
        puts("caught AV as expected.");
        return EXCEPTION_EXECUTE_HANDLER;
    }
    else
    {
        puts("didn't catch AV, unexpected.");
        return EXCEPTION_CONTINUE_SEARCH;
    };
}

int main()
{
    int* p = 0x00000000;   // pointer to NULL
    puts("hello");
    __try
    {
        puts("in try");
        __try
        {
            puts("in try");
            *p = 13;    // causes an access violation exception;
        }
        __finally
        {
            puts("in finally. termination: ");
            puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");
        }
    }
    __except(filter(GetExceptionCode(), GetExceptionInformation()))
    {
        puts("in except");
    }
    puts("world");
}
```

### <a name="output"></a>출력

```Output
hello
in try
in try
in filter.
caught AV as expected.
in finally. termination:
        abnormal
in except
world
```

## <a name="see-also"></a>참고 항목

[예외 처리기 작성](../cpp/writing-an-exception-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)
