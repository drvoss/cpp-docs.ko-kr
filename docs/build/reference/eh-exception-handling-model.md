---
title: /EH(예외 처리 모델)
description: Visual Studio의 Microsoft c + +/EH (예외 처리 모델) 컴파일러 옵션에 대 한 참조 가이드입니다.
ms.date: 08/25/2020
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExceptionHandling
- /eh
- VC.Project.VCCLCompilerTool.ExceptionHandling
helpviewer_keywords:
- exception handling, compiler model
- cl.exe compiler, exception handling
- EH compiler option [C++]
- -EH compiler option [C++]
- /EH compiler option [C++]
no-loc:
- SEH
- try
- catch
- throw
- extern
- finally
- noexcept
ms.assetid: 754b916f-d206-4472-b55a-b6f1b0f2cb4d
ms.openlocfilehash: 0d18d0f1d73b1de46b12262deecb2436c34e6176
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898380"
---
# <a name="eh-exception-handling-model"></a>`/EH` (예외 처리 모델)

컴파일러에서 생성 하는 예외 처리 모델 지원을 지정 합니다. 인수는 `catch(...)` 구조적 및 표준 c + + 예외에 구문을 적용할지 여부, ** extern "C"** 코드를 예외로 간주 하는지 여부 throw 및 특정 검사를 최적화할지 여부를 지정 **`noexcept`** 합니다.

## <a name="syntax"></a>구문

> **`/EHa`**[**`-`**]\
> **`/EHs`**[**`-`**]\
> **`/EHc`**[**`-`**]\
> **`/EHr`**[**`-`**]

## <a name="arguments"></a>인수

**`a`**\
표준 c + + 스택 해제를 사용 합니다. 구문을 사용 하는 경우 구조적 (비동기) 및 표준 c + + (동기) 예외를 모두 catch `catch(...)` 합니다. **`/EHa`** 는 **`/EHs`** 및 인수를 모두 재정의 **`/EHc`** 합니다.

**`s`**\
표준 c + + 스택 해제를 사용 합니다. 구문을 사용 하는 경우 표준 c + + 예외만 catch `catch(...)` 합니다. 을 지정 하지 않은 경우 **`/EHc`** 컴파일러는 ** extern "c"** 로 선언 된 함수가 throw c + + 예외 라고 가정 합니다.

**`c`**\
에서 사용 하는 경우 **`/EHs`** 컴파일러는 ** extern "c"** 로 선언 된 함수가 throw c + + 예외가 아닌 것으로 간주 합니다. 과 함께 사용 하는 경우에는 영향을 주지 않습니다 **`/EHa`** . 즉, **`/EHca`** 는와 동일 **`/EHa`** 합니다. **`/EHc`** 또는이 지정 되지 않은 경우는 무시 됩니다 **`/EHs`** **`/EHa`** .

**`r`**\
모든 함수에 대해 항상 런타임 종료 검사를 생성 하도록 컴파일러에 지시 **`noexcept`** 합니다. 기본적으로 런타임 검사 **`noexcept`** 는 컴파일러에서 함수가 아닌 함수만 호출 하는 것으로 확인 되 면 최적화 될 수 있습니다 throw . 이 옵션은 몇 가지 추가 코드의 비용으로 엄격한 c + + 규칙을 제공 합니다. **`/EHr`** 또는이 지정 되지 않은 경우는 무시 됩니다 **`/EHs`** **`/EHa`** .

**`-`**\
이전 옵션 인수를 지웁니다. 예를 들어 **`/EHsc-`** 은로 해석 되 **`/EHs /EHc-`** 고는와 동일 **`/EHs`** 합니다.

**`/EH`** 인수를 순서에 관계 없이 별도로 지정 하거나 결합할 수 있습니다. 동일한 인수의 인스턴스를 두 개 이상 지정 하는 경우 마지막 인스턴스는 이전 항목을 재정의 합니다.  예를 들어,는와 같으며와 동일한 **`/EHr- /EHc /EHs`** **`/EHscr-`** 결과를 **`/EHscr- /EHr`** 가집니다 **`/EHscr`** .

## <a name="remarks"></a>설명

### <a name="default-exception-handling-behavior"></a>기본 예외 처리 동작

컴파일러는 항상 비동기 구조적 예외 처리 ()를 지 원하는 코드를 생성 SEH 합니다. 기본적으로, 또는 옵션을 지정 하지 않은 경우 **`/EHsc`** **`/EHs`** **`/EHa`** 컴파일러는 SEH 네이티브 c + + 절에서 처리기를 지원 합니다 `catch(...)` . 그러나 c + + 예외만 부분적 으로만 지 원하는 코드도 생성 됩니다. 기본 예외 해제 코드는 예외로 인해 범위를 벗어나는 블록 외부에서 자동 c + + 개체를 제거 하지 않습니다 [`try`](../../cpp/try-throw-and-catch-statements-cpp.md) . C + + 예외가 n 인 경우 리소스 누수 및 정의 되지 않은 동작이 발생할 수 있습니다 throw .

### <a name="standard-c-exception-handling"></a>표준 c + + 예외 처리

스택 개체를 안전 하 게 해제 하는 표준 c + + 예외 처리 모델에 대 한 전체 컴파일러 지원에는 **`/EHsc`** (권장), 또는이 필요 **`/EHs`** **`/EHa`** 합니다.

**`/EHs`** 또는를 사용 하 **`/EHsc`** 는 경우 절은 `catch(...)` catch 비동기 구조적 예외를 나타내지 않습니다. 모든 액세스 위반 및 관리 되는 <xref:System.Exception?displayProperty=fullName> 예외가 catch 되지 않은 상태가 됩니다. 그리고 비동기 예외가 발생 한 경우에는 코드가 비동기 예외를 처리 하는 경우에도 범위 내의 개체가 제거 되지 않습니다. 이 동작은 구조화 된 예외를 처리 되지 않은 상태로 유지 하기 위한 인수입니다. 대신 이러한 예외를 심각 하 게 고려해 야 합니다.

또는를 사용 하는 경우 **`/EHs`** **`/EHsc`** 컴파일러는 예외가 **`throw`** 문 또는 함수 호출 에서만 발생할 수 있다고 가정 합니다. 이러한 가정을 통해 컴파일러는 코드 크기를 크게 줄일 수 있는 많은 unwindable 개체의 수명을 추적 하는 코드를 제거할 수 있습니다. 를 사용 하 **`/EHa`** 는 경우 컴파일러에서 블록을 적극적으로 최적화 하지 않으므로 실행 가능 이미지가 더 크고 느릴 수 있습니다 **`try`** . 또한 컴파일러가 throw c + + 예외를 발생 시킬 수 있는 코드를 볼 수 없는 경우에도 로컬 개체를 자동으로 정리 하는 예외 필터를 유지 합니다.

### <a name="structured-and-standard-c-exception-handling"></a>구조적 및 표준 c + + 예외 처리

**`/EHa`** 컴파일러 옵션을 사용 하면 비동기 예외와 c + + 예외 모두에 대해 안전 스택 해제를 사용할 수 있습니다. 네이티브 c + + 절을 사용 하 여 표준 c + + 및 구조적 예외 처리를 모두 지원 `catch(...)` 합니다. 를 SEH 지정 하지 않고 구현 하려면 **`/EHa`** **`__try`** , **`__except`** 및 구문을 사용할 수 있습니다 **`__finally`** . 자세한 내용은 [구조적 예외 처리](../../cpp/structured-exception-handling-c-cpp.md)를 참조 하세요.

> [!IMPORTANT]
> 를 **`/EHa`** try 사용 하 여 모든 예외를 처리 하도록 지정 하 고을 지정 하는 `catch(...)` 것은 위험할 수 있습니다. 대부분의 경우 비동기 예외는 복구할 수 없고 치명적인 것으로 간주해야 합니다. Catch하고 진행하면 프로세스가 손상되고 찾아 수정할 수 없는 버그를 일으킬 수 있습니다.
>
> Windows 및 Visual C++ 지원 되더라도 SEH ISO 표준 c + + 예외 처리 (또는)를 사용 하는 것이 좋습니다 **`/EHsc`** **`/EHs`** . 이를 통해 코드를 더 이식 하 고 유연 하 게 만들 수 있습니다. SEH레거시 코드 또는 특정 종류의 프로그램에서를 사용 해야 하는 경우도 있습니다. 예를 들어 공용 언어 런타임 ()을 지원 하기 위해 컴파일된 코드에 필요 [`/clr`](clr-common-language-runtime-compilation.md) 합니다. 자세한 내용은 [구조적 예외 처리](../../cpp/structured-exception-handling-c-cpp.md)를 참조 하세요.
>
> 를 사용 하 여 컴파일된 개체 파일 **`/EHa`** 을 **`/EHs`** **`/EHsc`** 동일한 실행 모듈에서 또는를 사용 하 여 컴파일된 개체 파일에 연결 하지 않는 것이 좋습니다. 모듈의 아무 곳 이나 사용 하 여 비동기 예외를 처리 해야 하는 경우를 **`/EHa`** 사용 **`/EHa`** 하 여 모듈의 모든 코드를 컴파일합니다. 를 사용 하 여 컴파일된 코드와 동일한 모듈에서 구조적 예외 처리 구문을 사용할 수 있습니다 **`/EHs`** . 그러나 SEH **`try`** **`throw`** 동일한 함수에서 c + +, 및를 함께 사용 하 여 구문을 혼합할 수 없습니다 **`catch`** .

**`/EHa`** 이 catch 아닌 다른 항목에 의해 발생 한 예외를 원하는 경우를 사용 **`throw`** 합니다. 이 예제에서는 catch 구조화 된 예외가 생성 됩니다.

```cpp
// compiler_options_EHA.cpp
// compile with: /EHa
#include <iostream>
#include <excpt.h>
using namespace std;

void fail()
{
    // generates SE and attempts to catch it using catch(...)
    try
    {
        int i = 0, j = 1;
        j /= i;   // This will throw a SE (divide by zero).
        printf("%d", j);
    }
    catch(...)
    {
        // catch block will only be executed under /EHa
        cout << "Caught an exception in catch(...)." << endl;
    }
}

int main()
{
    __try
    {
        fail();
    }

    // __except will only catch an exception here
    __except(EXCEPTION_EXECUTE_HANDLER)
    {
        // if the exception was not caught by the catch(...) inside fail()
        cout << "An exception was caught in __except." << endl;
    }
}
```

### <a name="exception-handling-under-clr"></a>/Clr에서 예외 처리

**`/clr`** 옵션은 **`/EHa`** (즉, **`/clr /EHa`** 중복 됨)를 의미 합니다. **`/EHs`** 뒤에 또는가 사용 되 면 컴파일러에서 오류가 발생 합니다 **`/EHsc`** **`/clr`** . 최적화는이 동작에 영향을 주지 않습니다. 예외가 catch 되 면 컴파일러는 예외와 동일한 범위에 있는 모든 개체에 대 한 클래스 소멸자를 호출 합니다. 예외가 catch 되지 않으면 해당 소멸자가 실행 되지 않습니다.

의 예외 처리 제한에 대 한 자세한 내용은 **`/clr`** [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)를 참조 하세요.

### <a name="runtime-exception-checks"></a>런타임 예외 검사

**`/EHr`** 옵션은 특성이 있는 모든 함수에서 런타임 종료 검사를 강제로 실행 합니다 **`noexcept`** . 기본적으로 런타임 검사는 컴파일러 백 엔드에서 함수가 *비 throw * 함수 함수만 호출 하는 것으로 확인 되는 경우 최적화 될 수 있습니다. 비 throw 함수 함수는 n 일 수 있는 예외가 없음을 지정 하는 특성을 갖는 모든 함수입니다 throw . 여기에는,, 및로 표시 되는 함수, **`noexcept`** `throw()` `__declspec(nothrow)` **`/EHc`** 가 지정 된 경우 **`extern "C"`** 함수가 포함 됩니다. 비 기능 함수에는 컴파일러에서 확인 하는 것 throw 으로 확인 된 함수가 포함 되지 않습니다 throw . 를 사용 하 여 기본 동작을 명시적으로 설정할 수 있습니다 **`/EHr-`** .

비 throw 특성 특성은 예외가 함수에 의해 n 일 수 없음을 보장 하지 않습니다 throw . 함수의 동작과 달리 **`noexcept`** MSVC 컴파일러는 throw , 또는를 사용 하 여 선언 된 함수에 의해 예외 n `throw()` 을 `__declspec(nothrow)` **`extern "C"`** 정의 되지 않은 동작으로 간주 합니다. 이러한 세 선언 특성을 사용 하는 함수는 예외에 대해 런타임 종료 검사를 적용 하지 않습니다. 옵션을 사용 하면 **`/EHr`** 컴파일러에서 함수를 이스케이프 하는 처리 되지 않은 예외에 대해 런타임 검사를 생성 하도록 하 여이 정의 되지 않은 동작을 쉽게 식별할 수 있습니다 **`noexcept`** .

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>Visual Studio에서 옵션을 설정 하거나 프로그래밍 방식으로

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**  >  **C/c + +**  >  **코드 생성**을 선택 합니다.

1. **C++ 예외 처리 가능** 속성을 변경합니다.

   또는 **C++ 예외 처리 가능** 을 **아니요**로 설정하고, **명령줄** 속성 페이지에서, **추가 옵션** 상자에 컴파일러 옵션을 추가합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>을 참조하세요.

## <a name="see-also"></a>참조

[MSVC 컴파일러 옵션](compiler-options.md)\
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)\
[오류 및 예외 처리](../../cpp/errors-and-exception-handling-modern-cpp.md)\
[예외 사양 ( throw )](../../cpp/exception-specifications-throw-cpp.md)\
[구조적 예외 처리(C/C++)](../../cpp/structured-exception-handling-c-cpp.md)
