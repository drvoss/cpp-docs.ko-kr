---
title: try-finally 문
ms.date: 11/19/2018
f1_keywords:
- __try
- _try
- __leave_cpp
- __leave
- __finally_cpp
- __try_cpp
- __finally
- _finally
helpviewer_keywords:
- __try keyword [C++]
- __finally keyword [C++]
- __leave keyword [C++]
- try-catch keyword [C++], try-finally keyword
- try-finally keyword [C++]
- __finally keyword [C++], try-finally statement syntax
- __leave keyword [C++], try-finally statement
- structured exception handling [C++], try-finally
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
ms.openlocfilehash: 17f7fb415303ab74f588a2205bc9430127091e96
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825898"
---
# <a name="try-finally-statement"></a>try-finally 문

**Microsoft 전용**

다음 구문에서는 **try-finally** 문을 설명 합니다.

> **\_\_try**<br/>
> {\
> &nbsp;&nbsp;&nbsp;&nbsp;보호 된 코드 \
> }\
> **\_\_마지막으로**\
> {\
> &nbsp;&nbsp;&nbsp;&nbsp;종료 코드 \
> }

## <a name="grammar"></a>문법

*try-finally-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;try 복합 *compound-statement* **문 \_finally \_** *문* ** \_ \_**

**Try finally** 문은 코드 블록 실행이 중단 될 때 대상 응용 프로그램이 정리 코드의 실행을 보장할 수 있도록 하는 c 및 c + + 언어의 Microsoft 확장입니다. 정리는 메모리 할당 해제, 파일 닫기 및 파일 핸들 해제와 같은 작업으로 구성됩니다. **Try finally** 문은 루틴에서 중간에 반환 될 수 있는 오류에 대 한 검사가 수행 되는 여러 위치가 있는 루틴에 특히 유용 합니다.

관련 정보 및 코드 샘플은 [try-Except 문](../cpp/try-except-statement.md)을 참조 하십시오. 일반적인 구조적 예외 처리에 대 한 자세한 내용은 [구조적 예외 처리](../cpp/structured-exception-handling-c-cpp.md)를 참조 하세요. C + +/CLI를 사용 하 여 관리 되는 응용 프로그램의 예외 처리에 대 한 자세한 내용은 [/clr에서 예외 처리](../extensions/exception-handling-cpp-component-extensions.md)를 참조 하세요.

> [!NOTE]
> 구조적 예외 처리는 Win32에서 C 및 C++ 소스 파일에 대해 작동하지만 특별히 C++용으로 설계되지는 않았습니다. C++ 예외 처리를 사용하여 코드의 이식성이 향상되는지 확인할 수 있습니다. 또한 C++ 예외 처리는 모든 형식의 예외를 처리할 수 있다는 점에서 보다 유연합니다. C + + 프로그램의 경우 c + + 예외 처리 메커니즘 ([try, catch 및 throw](../cpp/try-throw-and-catch-statements-cpp.md) 문)을 사용 하는 것이 좋습니다.

**__Try** 절 뒤의 복합 문은 보호 된 섹션입니다. **__Finally** 절 뒤의 복합 문은 종료 처리기입니다. 처리기는 보호된 섹션이 예외(비정상적인 종료)로 인해 종료되건 표준 이동(정상적인 종료)으로 인해 종료되건 간에 보호된 섹션이 끝나면 실행되는 작업 집합을 지정합니다.

제어는 단순한 순차적 실행 (제어)을 통해 **__try** 문에 도달 합니다. 컨트롤이 **__try**들어가면 연결 된 처리기가 활성화 됩니다. 제어 흐름이 try 블록 끝에 도달하면 다음과 같이 실행됩니다.

1. 종료 처리기가 호출됩니다.

1. 종료 처리기가 완료 되 면 **__finally** 문 다음에 실행이 계속 됩니다. 보호 된 섹션의 종료 방식 (예: 보호 된 본문 또는 **return** 문으로 **이동** 을 통해)에 관계 없이 제어 흐름이 보호 된 섹션 밖으로 이동 *하기 전에* 종료 처리기가 실행 됩니다.

   **__Finally** 문은 적절 한 예외 처리기를 검색 하는 것을 차단 하지 않습니다.

**__Try** 블록에서 예외가 발생 하면 운영 체제에서 예외에 대 한 처리기를 찾아야 합니다. 그렇지 않으면 프로그램에서 오류가 발생 합니다. 처리기가 있는 경우 모든 **__finally** 블록이 실행 되 고 처리기에서 실행이 다시 시작 됩니다.

예를 들어, 일련의 함수 호출 링크에서는 함수 A를 D에 연결한다고 가정합니다(아래 그림 참조). 각 함수에는 종료 처리기가 하나씩 있습니다. 예외가 D 함수에서 발생하고 A에서 처리될 경우 시스템이 스택 D, C, B를 해제하면 그 순서대로 종료 처리기가 호출됩니다.

![종료&#45;처리기 실행 순서](../cpp/media/vc38cx1.gif "종료&#45;처리기 실행 순서") <br/>
종료 처리기 실행 순서

> [!NOTE]
> Try-finally의 동작은 c #과 같이 **마지막**사용을 지 원하는 다른 언어와 다릅니다.  단일 **__try** 에는 **__finally** 와 **__except**중 하나만 있을 수 있습니다.  모두 함께 사용되는 경우 외부 try-except 문은 내부 try-finally 문을 포함해야 합니다.  또한 각 블록을 실행할 때 지정되는 규칙은 서로 다릅니다.

이전 버전과의 호환성을 위해 **_try**, **_finally**및 **_leave** 는 컴파일러 옵션 [ \(/za 사용 안 함 언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 이 지정 된 경우를 제외 하 고 **__try**, **__finally**및 **__leave** 의 동의어입니다.

## <a name="the-__leave-keyword"></a>__leave 키워드

**__Leave** 키워드는 **try-catch** 문의 보호 된 섹션 내 에서만 유효 하며, 보호 된 섹션의 끝으로 이동 하는 것이 좋습니다. 종료 처리기의 첫 번째 문에서 계속 실행됩니다.

**Goto** 문은 보호 된 섹션 밖으로 이동할 수도 있지만 스택 해제를 호출 하기 때문에 성능이 저하 됩니다. **__Leave** 문은 스택 해제를 발생 시 키 지 않으므로 더 효율적입니다.

## <a name="abnormal-termination"></a>비정상적인 종료

Try [jmp](../c-runtime-library/reference/longjmp.md) 런타임 함수를 사용 하 여 **try-catch** 문을 종료 하는 것은 비정상적인 종료로 간주 됩니다. **__Try** 문으로 이동 하는 것은 유효 하지 않지만 한 문으로 점프할 수는 있습니다. 출발 지점 ( **__try** 블록의 정상적인 종료)과 대상 (예외를 처리 하는 **__except** 블록) 사이에 활성화 된 모든 **__finally** 문이 실행 되어야 합니다. 이것을 로컬 해제라고 합니다.

블록 밖으로 점프를 포함 하 여 어떤 이유로 든 **try** 블록이 중간에 종료 되는 경우 시스템은 스택을 해제 하는 프로세스의 일부로 연결 된 **finally** 블록을 실행 합니다. 이러한 경우, [Abnormaltermination](/windows/win32/Debug/abnormaltermination) 함수는 **finally** 블록 내에서 호출 된 경우 **true** 를 반환 합니다. 그렇지 않으면 **false**를 반환 합니다.

**Try finally** 문을 실행 하는 도중에 프로세스가 종료 되 면 종료 처리기가 호출 되지 않습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[종료 처리기 작성](../cpp/writing-a-termination-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)<br/>
[종료 처리기 구문](/windows/win32/Debug/termination-handler-syntax)
