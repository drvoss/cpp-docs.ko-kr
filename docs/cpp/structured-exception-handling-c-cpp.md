---
title: Structured Exception Handling (C/C++)
description: Microsoft C/c + +에서 구조적 예외 처리에 대 한 개요입니다.
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
ms.openlocfilehash: 142e89bc82adbe7938e8825029908e814df6055c
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898636"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)

SEH (구조적 예외 처리)는 하드웨어 오류와 같은 특정 예외 코드 상황을 정상적으로 처리 하기 위해 C에 대 한 Microsoft 확장입니다. Windows 및 Microsoft c + +가 SEH를 지원 하지만 ISO 표준 c + + 예외 처리를 사용 하는 것이 좋습니다. 이를 통해 코드를 더 이식 하 고 유연 하 게 만들 수 있습니다. 그러나 기존 코드 또는 특정 종류의 프로그램을 유지 하려면 SEH를 사용 해야 할 수도 있습니다.

**Microsoft 전용:**

## <a name="grammar"></a>문법

> *`try-except-statement`* :<br/>
> &emsp;**`__try`** *`compound-statement`* **`__except`** **`(`** *`expression`* **`)`** *`compound-statement`*
>
> *`try-finally-statement`* :<br/>
> &emsp;**`__try`** *`compound-statement`* **`__finally`** *`compound-statement`*

## <a name="remarks"></a>설명

SEH를 사용 하면 실행이 예기치 않게 종료 되는 경우 메모리 블록 및 파일과 같은 리소스가 올바르게 해제 되도록 할 수 있습니다. 문을 사용 하지 **`goto`** 않거나 반환 코드의 정교한 테스트를 사용 하지 않는 간결한 구조화 된 코드를 사용 하 여 특정 문제 (예: 메모리 부족)를 처리할 수도 있습니다.

`try-except` `try-finally` 이 문서에서 참조 하는 및 문은 C 언어에 대 한 Microsoft 확장입니다. 둘 다 애플리케이션이 그렇지 않을 경우 실행을 종료하는 이벤트 후에 프로그램을 제어할 수 있도록 하여 SEH를 지원합니다. SEH는 C++ 소스 파일에서 작동하지만 C++용으로 특별히 설계된 것은 아닙니다. [ `/EHa` 또는 `/EHsc` ](../build/reference/eh-exception-handling-model.md) 옵션을 사용 하 여 컴파일하는 c + + 프로그램에서 SEH를 사용 하는 경우 로컬 개체에 대 한 소멸자가 호출 되지만 다른 실행 동작이 필요한 것은 아닐 수 있습니다. 예시를 보려면이 문서의 뒷부분에 나오는 예제를 참조 하세요. 대부분의 경우 SEH 대신 Microsoft c + + 컴파일러에서 지 원하는 ISO 표준 [c + + 예외 처리](../cpp/try-throw-and-catch-statements-cpp.md)를 사용 하는 것이 좋습니다. C++ 예외 처리를 사용하면 코드 포팅 가능성이 향상되며 모든 형식의 예외를 처리할 수 있습니다.

SEH를 사용 하는 C 코드를 사용 하는 경우 c + + 예외 처리를 사용 하는 c + + 코드를 혼합할 수 있습니다. 자세한 내용은 [c + +에서 구조적 예외 처리](../cpp/exception-handling-differences.md)를 참조 하세요.

SEH 메커니즘에는 다음 두 가지가 있습니다.

- 예외 [처리기](../cpp/writing-an-exception-handler.md)또는 **`__except`** 예외에 응답 하거나 해제할 수 있는 블록입니다.

- [Termination handlers](../cpp/writing-a-termination-handler.md) **`__finally`** 예외가 종료를 발생 시키는 지 여부에 관계 없이 항상 호출 되는 종료 처리기 또는 블록

이러한 두 종류의 처리기는 고유 하지만 *스택*해제 라는 프로세스를 통해 밀접 하 게 관련 되어 있습니다. 구조화 된 예외가 발생 하면 Windows는 현재 활성 상태인 가장 최근에 설치 된 예외 처리기를 찾습니다. 처리기는 다음 세 가지 작업 중 하나를 수행할 수 있습니다.

- 예외를 인식하지 못하고 다른 처리기에 제어를 전달합니다.

- 예외를 인식하지만 해제합니다.

- 예외를 인식하고 처리합니다.

예외가 발생할 때 실행 중이던 함수에 예외를 인식하는 예외 처리기가 없을 수 있습니다. 스택에서 훨씬 더 높은 함수에 있을 수 있습니다. 현재 실행 중인 함수 및 스택 프레임의 다른 모든 함수가 종료됩니다. 이 과정 *에서 스택이 해제 됩니다.* 즉, 종료 된 함수의 로컬 비정적 변수는 스택에서 지워집니다.

스택을 해제할 때 운영 체제는 각 함수에 대해 작성된 종료 처리기를 모두 호출합니다. 종료 처리기를 사용 하 여 비정상적인 종료로 인해 열린 상태를 유지 하는 리소스를 정리 합니다. 임계 영역을 입력 한 경우 종료 처리기에서 종료할 수 있습니다. 프로그램이 종료 되 면 임시 파일을 닫고 제거 하는 등의 다른 정리 작업을 수행할 수 있습니다.

## <a name="next-steps"></a>다음 단계

- [예외 처리기 작성](../cpp/writing-an-exception-handler.md)

- [종료 처리기 작성](../cpp/writing-a-termination-handler.md)

- [C++에서 구조적 예외 처리](../cpp/exception-handling-differences.md)

## <a name="example"></a>예

앞서 설명한 것 처럼, c + + 프로그램에서 SEH를 사용 하 고 또는 옵션을 사용 하 여 컴파일하는 경우 로컬 개체에 대 한 소멸자가 호출 됩니다 **`/EHa`** **`/EHsc`** . 그러나 c + + 예외를 사용 하는 경우 실행 중에 의도 하지 않은 동작이 발생할 수 있습니다. 이 예제에서는 이러한 동작의 차이점을 보여 줍니다.

```cpp
#include <stdio.h>
#include <Windows.h>
#include <exception>

class TestClass
{
public:
    ~TestClass()
    {
        printf("Destroying TestClass!\r\n");
    }
};

__declspec(noinline) void TestCPPEX()
{
#ifdef CPPEX
    printf("Throwing C++ exception\r\n");
    throw std::exception("");
#else
    printf("Triggering SEH exception\r\n");
    volatile int *pInt = 0x00000000;
    *pInt = 20;
#endif
}

__declspec(noinline) void TestExceptions()
{
    TestClass d;
    TestCPPEX();
}

int main()
{
    __try
    {
        TestExceptions();
    }
    __except(EXCEPTION_EXECUTE_HANDLER)
    {
        printf("Executing SEH __except block\r\n");
    }

    return 0;
}
```

**`/EHsc`** 를 사용 하 여이 코드를 컴파일할 때 로컬 테스트 컨트롤 매크로가 정의 되지 않은 경우 `CPPEX` 소멸자가 `TestClass` 실행 되지 않습니다. 출력은 다음과 같습니다.

```Output
Triggering SEH exception
Executing SEH __except block
```

**`/EHsc`** 를 사용 하 여 코드를 컴파일하고 `CPPEX` c + + 예외가 throw 되도록를 사용 하 여 정의 된 경우 `/DCPPEX` 소멸자가 실행 되 `TestClass` 고 출력은 다음과 같습니다.

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

를 사용 하 여 **`/EHa`** 코드를 컴파일하는 경우 소멸자는를 사용 하 여 `TestClass` 예외가 throw 되었는지 `std::throw` 또는 SEH를 사용 하 여 예외를 트리거하기 때문에 예외가 throw 되었는지 여부를 실행 합니다. 즉,가 정의 되었는지 여부를 나타냅니다 `CPPEX` . 출력은 다음과 같습니다.

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

자세한 내용은 [ `/EH` (예외 처리 모델)](../build/reference/eh-exception-handling-model.md)를 참조 하세요.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[예외 처리](../cpp/exception-handling-in-visual-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[`<exception>`](../standard-library/exception.md)<br/>
[오류 및 예외 처리](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[구조적 예외 처리 (Windows)](/windows/win32/debug/structured-exception-handling)
