---
title: /EH(예외 처리 모델)
description: Visual Studio의 Microsoft C++ /EH(예외 처리 모델) 컴파일러 옵션에 대한 참조 가이드입니다.
ms.date: 04/14/2020
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
ms.openlocfilehash: 68d6af657e7c20c0f5e84674dd91803beb35fba0
ms.sourcegitcommit: 0e4feb35b47c507947262d00349d4a893863a6d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81396292"
---
# <a name="eh-exception-handling-model"></a>/EH(예외 처리 모델)

컴파일러에서 생성된 예외 처리 모델 지원을 지정합니다. 인수는 구조화 `catch(...)` 된 및 표준 C ++ 예외 모두에 구문을 적용할지 여부, ** extern "C"** 코드가 throw 예외로 가정되는지 여부 및 특정 **noexcept** 검사를 최적화할지 여부를 지정합니다.

## <a name="syntax"></a>구문

> **`/EHa`**[**`-`**]\
> **`/EHs`**[**`-`**]\
> **`/EHc`**[**`-`**]\
> **`/EHr`**[**`-`**]

## <a name="arguments"></a>인수

**`a`**\
표준 C++ 스택 해제를 활성화합니다. 구문을 사용할 `catch(...)` 때 구조화(비동기) 및 표준 C++ (동기식) 예외를 모두 catch합니다. **`/EHa`** 과 인수를 **`/EHs`** 모두 재정의합니다. **`/EHc`**

**`s`**\
표준 C++ 스택 해제를 활성화합니다. 구문을 사용할 `catch(...)` 때 표준 C++ 예외만 catch합니다. 또한 **`/EHc`** 지정되지 않는 한 컴파일러는 ** extern "C"로** 선언된 throw 함수가 C++ 예외일 수 있다고 가정합니다.

**`c`**\
와 함께 **`/EHs`** 사용할 때 컴파일러는 ** extern "C"로** 선언 throw 된 함수가 C ++ 예외가 되지 않는 것으로 가정합니다. (즉, **`/EHa`** **`/EHca`** 에 **`/EHa`** 해당)와 함께 사용할 때 아무런 효과가 없습니다. **`/EHc`** 지정되지 **`/EHa`** **`/EHs`** 않았거나 지정되지 않은 경우 무시됩니다.

**`r`**\
컴파일러에 모든 **noexcept** 함수에 대한 런타임 종료 검사를 항상 생성하도록 지시합니다. 기본적으로 컴파일러에서 함수가 throw되지 않는 함수만 호출하는 것을 결정하는 경우 런타임 검사가 최적화될 **noexcept** 수 있습니다. 이 옵션은 몇 가지 추가 코드의 비용으로 엄격한 C ++ 준수를 제공합니다. **`/EHr`** 지정되지 **`/EHa`** **`/EHs`** 않았거나 지정되지 않은 경우 무시됩니다.

**`-`**\
이전 옵션 인수를 지웁니다. 예를 들어 **`/EHsc-`** **`/EHs /EHc-`** 로 해석되며 에 **`/EHs`** 해당합니다.

**`/EH`** 인수는 별도로 지정하거나 임의의 순서로 결합할 수 있습니다. 동일한 인수의 인스턴스를 두 개 이상 지정하면 마지막 인스턴스가 이전 인수를 재정의합니다.  예를 들어 **`/EHr- /EHc /EHs`** **`/EHscr-`** 은 과 동일하며 **`/EHscr- /EHr`** **`/EHscr`** 효과는 과 동일합니다.

## <a name="remarks"></a>설명

### <a name="default-exception-handling-behavior"></a>기본 예외 처리 동작

컴파일러는 항상 비동기 구조화된 예외 처리()를SEH지원하는 코드를 생성합니다. 기본적으로(즉, 아니요 , **`/EHsc`** **`/EHs`** 또는 **`/EHa`** 옵션이 지정된 경우) SEH 컴파일러는 네이티브 C++ `catch(...)` 절에서 처리기를 지원합니다. 그러나 C++ 예외만 부분적으로 만 지원하는 코드도 생성합니다. 기본 예외 해제 코드는 예외로 인해 범위를 벗어난 [try](../../cpp/try-throw-and-catch-statements-cpp.md) 블록 외부의 자동 C++ 개체를 파괴하지 않습니다. C++ 예외가 throw될 때 리소스 누수 및 정의되지 않은 동작이 발생할 수 있습니다.

### <a name="standard-c-exception-handling"></a>표준 C++ 예외 처리

스택 개체를 안전하게 해제하는 표준 C++ 예외 처리 모델에 **`/EHsc`** 대한 **`/EHs`** 전체 **`/EHa`** 컴파일러 지원은 필요(권장) 또는 .

또는 **`/EHs`** **`/EHsc`** 을 사용하는 경우 `catch(...)` 절은 비동기 구조화 된 예외를 사용하지 catch 않습니다. 모든 액세스 위반 <xref:System.Exception?displayProperty=fullName> 및 관리되는 예외는 잡히지 않습니다. 또한 비동기 예외가 발생하는 범위의 개체는 코드가 비동기 예외를 처리하는 경우에도 소멸되지 않습니다. 이 동작은 구조화 된 예외를 처리 하지 않은 상태로 두기 위한 인수입니다. 대신 이러한 예외가 치명적이라고 생각하십시오.

**`/EHs`** 컴파일러는 사용 **`/EHsc`** 하거나 , 컴파일러는 **throw** 명령문 또는 함수 호출에서만 예외가 발생할 수 있다고 가정합니다. 이 가정을 통해 컴파일러는 많은 해제 가능한 개체의 수명을 추적하기 위한 코드를 제거하여 코드 크기를 크게 줄일 수 있습니다. 을 사용하는 **`/EHa`** 경우 컴파일러가 블록을 적극적으로 최적화하지 **try** 않으므로 실행 이미지가 더 크고 느려질 수 있습니다. 또한 컴파일러에 C++ 예외가 있는 코드가 표시되지 않더라도 로컬 개체를 자동으로 throw 정리하는 예외 필터가 남습니다.

### <a name="structured-and-standard-c-exception-handling"></a>구조화 및 표준 C++ 예외 처리

**`/EHa`** 컴파일러 옵션을 사용하면 비동기 예외와 C++ 예외 모두에 대해 안전한 스택 해제가 가능합니다. 기본 C++ `catch(...)` 절을 사용하여 표준 C++ 및 구조화 된 예외의 처리를 지원합니다. **`/EHa`** 을 SEH 지정하지 않고 구현하려면 **__try** **__except**및 __finally 구문을 사용할 수 **있습니다.** 자세한 내용은 [구조화 된 예외 처리를](../../cpp/structured-exception-handling-c-cpp.md)참조하십시오.

> [!IMPORTANT]
> 모든 **`/EHa`** 예외를 지정하고 사용하여 `catch(...)` 처리하려고 하면 위험할 수 있습니다. 대부분의 경우 비동기 예외는 복구할 수 없고 치명적인 것으로 간주해야 합니다. Catch하고 진행하면 프로세스가 손상되고 찾아 수정할 수 없는 버그를 일으킬 수 있습니다.
>
> Windows 및 Visual C++를 지원하더라도 SEHISO 표준 C++ 예외 처리(또는**`/EHsc`** **`/EHs`**)를 사용하는 것이 좋습니다. 그것은 당신의 코드를 더 이식가능하고 유연하게 만듭니다. 레거시 코드 나 특정 종류의 SEH 프로그램에 사용해야 하는 경우도 있을 수 있습니다. 예를 들어 공통 언어[런타임(/clr)을](clr-common-language-runtime-compilation.md)지원하기 위해 컴파일된 코드에 필요합니다. 자세한 내용은 [구조화 된 예외 처리를](../../cpp/structured-exception-handling-c-cpp.md)참조하십시오.
>
> 동일한 실행 모듈을 사용하여 **`/EHa`** 컴파일된 개체 **`/EHs`** 파일이나 **`/EHsc`** 컴파일된 개체 파일에 연결하지 않는 것이 좋습니다. 모듈의 아무 곳이나 사용하여 **`/EHa`** 비동기 예외를 처리해야 **`/EHa`** 하는 경우 모듈의 모든 코드를 컴파일하는 데 사용합니다. 을 사용하여 컴파일된 코드와 동일한 모듈에서 구조화된 예외 처리 **`/EHs`** 구문을 사용할 수 있습니다. 그러나 SEH 구문을 C ++ **try** 및 **throw** 동일한 **catch** 함수와 혼합 할 수 없습니다.

을 제외한 다른 것으로 인해 발생하는 예외를 사용하십시오. catch **`/EHa`** **throw** 이 예제는 구조적 예외를 생성 및 catch합니다.

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

### <a name="exception-handling-under-clr"></a>/clr에서 예외 처리

이 **`/clr`** 옵션은 **`/EHa`** (즉, **`/clr /EHa`** 중복)을 의미합니다. 컴파일러는 에 이후에도 **`/EHs`** **`/EHsc`** **`/clr`** 사용되는 경우 오류를 생성합니다. 최적화는 이 동작에 영향을 주지 않습니다. 예외가 catch되면 컴파일러는 예외와 동일한 범위에 있는 모든 개체에 대해 클래스 소멸자를 호출합니다. 예외가 catch되지 않으면 해당 소멸자가 실행되지 않습니다.

예외 처리 제한에 **`/clr`** 대한 자세한 내용은 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)을 참조하십시오.

### <a name="runtime-exception-checks"></a>런타임 예외 검사

이 **`/EHr`** 옵션은 **noexcept** 특성이 있는 모든 함수에서 런타임 종료 검사를 강제로 합니다. 기본적으로 컴파일러 백 엔드에서 함수가 *throw되지 않는* 함수만 호출한다고 판단하는 경우 런타임 검사가 최적화될 수 있습니다. throw되지 않는 함수는 예외가 throw될 수 없음을 지정하는 특성을 갖는 모든 함수입니다. 여기에는 `throw()`" C" `__declspec(nothrow)`함수를 **`/EHc`** 지정하면 " 및 ** extern 이에** 표시된 **noexcept** 함수가 포함됩니다. throw되지 않는 함수에는 컴파일러에서 검사에 의해 throw되지 않는 것으로 확인한 모든 함수도 포함됩니다. 을 사용하여 **`/EHr-`** 기본 동작을 명시적으로 설정할 수 있습니다.

throw되지 않는 특성은 함수에서 예외를 throw할 수 없다는 보장이 아닙니다. **noexcept** 함수의 동작과 달리 MSVC 컴파일러는 ** extern "C"를** `throw()` `__declspec(nothrow)`사용하여 선언된 함수에서 throw된 예외를 정의되지 않은 동작으로 간주합니다. 이러한 세 가지 선언 특성을 사용하는 함수는 예외에 대한 런타임 종료 검사를 적용하지 않습니다. 이 **`/EHr`** 옵션을 사용하면 컴파일러에서 **noexcept** 함수를 이스케이프하는 처리되지 않은 예외에 대한 런타임 검사를 생성하도록 하여 정의되지 않은 동작을 식별할 수 있습니다.

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>비주얼 스튜디오 또는 프로그래밍 방식으로 옵션 설정

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **구성 속성** > **C/C++** > 코드**생성을 선택합니다.**

1. **C++ 예외 처리 가능** 속성을 변경합니다.

   또는 **C++ 예외 처리 가능** 을 **아니요**로 설정하고, **명령줄** 속성 페이지에서, **추가 옵션** 상자에 컴파일러 옵션을 추가합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)\
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)\
[오류 및 예외 처리](../../cpp/errors-and-exception-handling-modern-cpp.md)\
[예외 사양throw()](../../cpp/exception-specifications-throw-cpp.md)\
[구조적 예외 처리(C/C++)](../../cpp/structured-exception-handling-c-cpp.md)
