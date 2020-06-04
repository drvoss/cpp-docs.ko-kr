---
title: MSVC의 예외 처리
description: C ++ 언어 참조 예외 처리 개요.
ms.date: 04/15/2020
helpviewer_keywords:
- try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
ms.openlocfilehash: 0d60f49c6f1412925c19aaf497352940411b5d92
ms.sourcegitcommit: 0e4feb35b47c507947262d00349d4a893863a6d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81396279"
---
# <a name="exception-handling-in-msvc"></a>MSVC의 예외 처리

예외는 프로그램이 일반적인 실행 경로를 따라 계속 진행하는 것을 방해하며 프로그램의 제어를 벗어날 수 있는 오류 상태입니다. 개체 생성, 파일 입력/출력 및 다른 모듈에서 만든 함수 호출을 비롯한 특정 작업은 프로그램이 올바르게 실행되는 경우에도 예외의 모든 잠재적인 소스입니다. 강력한 코드는 예외를 예상하고 처리합니다. 논리 오류를 검색하려면 예외가 아닌 어설션을 [사용합니다(어설션 사용](/visualstudio/debugger/c-cpp-assertions)참조).

## <a name="kinds-of-exceptions"></a>예외의 종류

Microsoft C++ 컴파일러(MSVC)는 세 가지 종류의 예외 처리를 지원합니다.

- [C++ 예외 처리](errors-and-exception-handling-modern-cpp.md)

   대부분의 C++ 프로그램의 경우 C++ 예외 처리를 사용해야 합니다. 형식이 안전하며 스택 해제 중에 개체 소멸자가 호출되도록 합니다.

- [구조화 된 예외 처리](structured-exception-handling-c-cpp.md)

   Windows는 SEH(구조화된 예외 처리)라는 자체 예외 메커니즘을 제공합니다. C++ 또는 MFC 프로그래밍은 권장되지 않습니다. 비 MFC C 프로그램에만 SEH를 사용합니다.

- [MFC 예외](../mfc/exception-handling-in-mfc.md)

   버전 3.0 이후 MFC는 C++ 예외를 사용했습니다. 양식의 C++ 예외와 유사한 이전 예외 처리 매크로를 계속 지원합니다. MFC 매크로 및 C++ 예외 를 혼합하는 것에 대한 조언은 [예외: MFC 매크로 및 C++ 예외 사용.](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

[/EH](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 사용하여 C++ 프로젝트에서 사용할 예외 처리 모델을 지정합니다. 표준 C++ 예외**처리(/EHsc)는**Visual Studio의 새 C++ 프로젝트의 기본값입니다.

예외 처리 메커니즘을 혼합하지 않는 것이 좋습니다. 예를 들어 구조화 된 예외 처리와 함께 C ++ 예외를 사용 하지 마십시오. C++ 예외 처리를 단독으로 사용하면 코드의 이식성이 높아지며 모든 유형의 예외를 처리할 수 있습니다. 구조화 된 예외 처리의 단점에 대 한 자세한 내용은 [구조화 된 예외 처리](structured-exception-handling-c-cpp.md)를 참조 하십시오.

## <a name="in-this-section"></a>섹션 내용

- [예외 및 오류 처리를 위한 최신 C++ 모범 사례](errors-and-exception-handling-modern-cpp.md)

- [예외 안전을 위한 설계 방법](how-to-design-for-exception-safety.md)

- [예외 코드와 예외가 아닌 코드 간에 인터페이싱하는 방법](how-to-interface-between-exceptional-and-non-exceptional-code.md)

- [Try, Catch 및 Throw 문](try-throw-and-catch-statements-cpp.md)

- [Catch 블록의 평가 방법](how-catch-blocks-are-evaluated-cpp.md)

- [예외 및 스택 해제](exceptions-and-stack-unwinding-in-cpp.md)

- [예외 사양](exception-specifications-throw-cpp.md)

- [noexcept](noexcept-cpp.md)

- [처리되지 않은 C++ 예외](unhandled-cpp-exceptions.md)

- [C(구조적) 및 C++ 예외 혼합](mixing-c-structured-and-cpp-exceptions.md)

- [구조적 예외 처리(SEH)(C/C++)](structured-exception-handling-c-cpp.md)

## <a name="see-also"></a>참고 항목

[C++ 언어 참조](cpp-language-reference.md)</br>
[x64 예외 처리](../build/exception-handling-x64.md)</br>
[예외 처리(C++/CLI 및 C++/CX)](../extensions/exception-handling-cpp-component-extensions.md)
