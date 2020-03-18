---
title: try-except 문
ms.date: 10/09/2018
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
ms.openlocfilehash: 7d3a92aa8c6d1f77a1795eabde0ae1e575bb5770
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444123"
---
# <a name="try-except-statement"></a>try-except 문

**Microsoft 전용**

**Try except** 문은 구조화 된 예외 처리를 지 원하는 C 및 C++ 언어에 대 한 Microsoft 확장입니다.

## <a name="syntax"></a>구문

> **\_\_시도**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;//보호 코드<br/>
> }<br/>
> **\_\_except** ( *expression* )<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;//예외 처리기 코드<br/>
> }

## <a name="remarks"></a>설명

**Try except** 문은 일반적으로 프로그램 실행을 종료 하는 이벤트가 발생 C++ 하는 경우 대상 응용 프로그램에서 제어할 수 있는 C 및 언어의 Microsoft 확장입니다. 이러한 이벤트를 *예외*라고 하 고, 예외를 처리 하는 메커니즘을 SEH ( *구조적 예외 처리* ) 라고 합니다.

관련 정보는 [try-finally 문을](../cpp/try-finally-statement.md)참조 하세요.

예외는 하드웨어 기반 또는 소프트웨어 기반일 수 있습니다. 애플리케이션을 하드웨어 또는 소프트웨어 예외로부터 완전히 복구할 수 없더라도 구조적 예외 처리를 통해 오류 정보를 표시하고 애플리케이션의 내부 상태를 트래핑하여 문제를 진단하는 데 도움이 되도록 합니다. 이것은 쉽게 재현할 수 없는 간헐적인 문제에 특히 유용합니다.

> [!NOTE]
> 구조적 예외 처리는 Win32에서 C 및 C++ 소스 파일에 대해 작동하지만 특별히 C++용으로 설계되지는 않았습니다. C++ 예외 처리를 사용하여 코드의 이식성이 향상되는지 확인할 수 있습니다. 또한 C++ 예외 처리는 모든 형식의 예외를 처리할 수 있다는 점에서 보다 유연합니다. 프로그램 C++ 의 경우 C++ 예외 처리 메커니즘 ([try, catch 및 throw](../cpp/try-throw-and-catch-statements-cpp.md) 문)을 사용 하는 것이 좋습니다.

**__Try** 절 뒤의 복합 문은 본문 또는 보호 된 섹션입니다. **__Except** 절 뒤에 오는 복합 문은 예외 처리기입니다. 처리기는 보호된 섹션 본문을 실행하는 동안 예외가 발생하는 경우 수행할 일련의 작업을 지정합니다. 다음과 같이 실행됩니다.

1. 보호된 섹션이 실행됩니다.

1. 보호 된 섹션을 실행 하는 동안 예외가 발생 하지 않는 경우 **__except** 절 다음의 문에서 실행이 계속 됩니다.

1. 보호 된 섹션을 실행 하는 동안 또는 보호 된 섹션에서 호출 하는 루틴에서 예외가 발생 하는 경우에는 **__except** *식* ( *필터* 식 이라고 함)이 평가 되 고 값은 예외 처리 방법을 결정 합니다. 세 가지 값을 사용할 수 있습니다.

   - EXCEPTION_CONTINUE_EXECUTION (-1) 예외를 해제 합니다. 예외가 발생한 지점에서 계속 실행합니다.

   - EXCEPTION_CONTINUE_SEARCH (0) 예외를 인식할 수 없습니다. **try-except** 문을 포함하는 처리기를 먼저 검색한 후, 그 다음으로 우선 순위가 높은 처리기를 검색하는 순으로 처리기 스택을 계속 검색합니다.

   - EXCEPTION_EXECUTE_HANDLER (1) 예외를 인식할 수 없습니다. **__Except** 복합 문을 실행 하 여 예외 처리기로 제어를 전송한 다음 **__except** 블록 후 실행을 계속 합니다.

**__Except** 식은 C 식으로 계산 되기 때문에 단일 값, 조건식 연산자 또는 쉼표 연산자로 제한 됩니다. 더 광범위한 처리가 필요한 경우 식은 위에 나열된 세 값 중 하나를 반환하는 루틴을 호출할 수 있습니다.

각 애플리케이션에는 자체 예외 처리기를 사용할 수 있습니다.

**__Try** 문으로 이동 하는 것은 유효 하지 않지만 하나 밖으로 이동할 수 있습니다. **Try except** 문을 실행 하는 도중에 프로세스가 종료 되 면 예외 처리기가 호출 되지 않습니다.

이전 버전과의 호환성을 위해 **_try**, **_except**및 **_leave** 는 컴파일러 옵션 [/za __except 언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 이 지정 된 경우를 제외 하 고 **__try**, **__leave**및 **\(** 의 동의어입니다.

### <a name="the-__leave-keyword"></a>__leave 키워드

**__Leave** 키워드는 **try except** 문의 보호 된 섹션 내 에서만 유효 하며, 보호 된 섹션의 끝으로 이동 하는 것과 같은 효과가 있습니다. 실행은 예외 처리기 뒤에 나오는 첫 번째 문에서 계속 됩니다.

**Goto** 문은 보호 된 섹션 밖으로 이동할 수도 있으며, 스택 해제가 발생 하지 않기 때문에 **try finally** 문에서와 같이 성능이 저하 되지 않습니다. 그러나 보호 된 섹션이 크거나 복잡 한 경우 프로그래밍 실수를 내릴 가능성이 적으므로 **goto** 문 대신 **__leave** 키워드를 사용 하는 것이 좋습니다.

### <a name="structured-exception-handling-intrinsic-functions"></a>구조적 예외 처리 내장 함수

구조적 예외 처리는 `GetExceptionCode` 및 `GetExceptionInformation`를 사용 하 여 **try except** 문과 함께 사용할 수 있는 두 가지 내장 함수를 제공 합니다.

`GetExceptionCode`은 예외에 대 한 코드 (32 비트 정수)를 반환 합니다.

내장 함수 `GetExceptionInformation`은 예외에 대 한 추가 정보를 포함 하는 구조체에 대 한 포인터를 반환 합니다. 이 포인터를 통하여, 하드웨어 예외 발생 시의 컴퓨터 상태에 액세스할 수 있습니다. 구조는 다음과 같습니다.

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

포인터 유형 `PEXCEPTION_RECORD` 및 `PCONTEXT`는 \<winnt. h >에 정의 되며 `_EXCEPTION_RECORD` 및 `_CONTEXT`는 포함 파일 \<excpt.h에 정의 됩니다 >

예외 처리기 내에서 `GetExceptionCode`를 사용할 수 있습니다. 그러나 `GetExceptionInformation`는 예외 필터 식 내 에서만 사용할 수 있습니다. 해당 내장 함수가 가리키는 정보는 일반적으로 스택에 있으며, 예외 처리기로 제어가 전달되면 더 이상 사용할 수 없습니다.

내장 함수 `AbnormalTermination`는 종료 처리기 내에서 사용할 수 있습니다. **Try-finally** 문의 본문이 순차적으로 종료 되는 경우 0을 반환 합니다. 다른 모든 경우에는 1이 반환됩니다.

excpt.h은 이러한 내장 함수에 대해 다음과 같은 몇 가지 대체 이름을 정의 합니다.

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

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[예외 처리기 작성](../cpp/writing-an-exception-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)
