---
title: C (구조적) 및 c + + 예외 혼합
description: 구조적 예외 처리와 c + + 예외 및 몇 가지 잠재적인 문제를 혼합 하는 방법입니다.
ms.date: 08/24/2020
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
ms.openlocfilehash: 98ce2335ff3b08b7a5d71e03305c481ba068e5e6
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898413"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>C (구조적) 및 c + + 예외 혼합

이식 가능한 코드를 작성 하려는 경우 c + + 프로그램에서 SEH (구조적 예외 처리)를 사용 하지 않는 것이 좋습니다. 그러나 경우에 따라 [`/EHa`](../build/reference/eh-exception-handling-model.md) 구조화 된 예외와 c + + 소스 코드를 사용 하 여 컴파일 하 고 두 종류의 예외를 처리 하기 위한 기능이 필요 합니다. 구조적 예외 처리기에는 개체 또는 형식이 지정 된 예외의 개념이 없으므로 c + + 코드에서 throw 된 예외를 처리할 수 없습니다. 그러나 c + + **`catch`** 처리기는 구조화 된 예외를 처리할 수 있습니다. C + + 예외 처리 구문 ( **`try`** , **`throw`** , **`catch`** )은 c 컴파일러에서 허용 되지 않지만 구조화 된 예외 처리 구문 ( **`__try`** , **`__except`** , **`__finally`** )은 c + + 컴파일러에서 지원 됩니다.

[`_set_se_translator`](../c-runtime-library/reference/set-se-translator.md)구조적 예외를 c + + 예외로 처리 하는 방법에 대 한 자세한 내용은을 참조 하세요.

구조화 된 예외와 c + + 예외를 혼합 하 여 사용할 경우 다음과 같은 잠재적 문제에 주의 하십시오.

- C + + 예외 및 구조적 예외는 동일한 함수 내에서 혼합할 수 없습니다.

- 종료 처리기 ( **`__finally`** 블록)는 예외가 throw 된 후 해제 하는 동안에도 항상 실행 됩니다.

- C + + 예외 처리는 [`/EH`](../build/reference/eh-exception-handling-model.md) 해제 의미 체계를 사용 하는 컴파일러 옵션으로 컴파일된 모든 모듈에서 해제 의미 체계를 catch 하 고 유지할 수 있습니다.

- 모든 개체에 대해 소멸자 함수가 호출 되지 않는 경우가 있을 수 있습니다. 예를 들어 초기화 되지 않은 함수 포인터를 통해 함수 호출을 수행 하려고 하는 동안 구조화 된 예외가 발생할 수 있습니다. 함수 매개 변수가 호출 전에 생성 된 개체인 경우에는 스택 해제 중에 해당 개체의 소멸자가 호출 되지 않습니다.

## <a name="next-steps"></a>다음 단계

- [`setjmp` `longjmp` C + + 프로그램에서 또는 사용](../cpp/using-setjmp-longjmp.md)

  `setjmp` `longjmp` C + + 프로그램에서 및 사용에 대 한 자세한 내용을 참조 하세요.

- [C++에서 구조적 예외 처리](../cpp/exception-handling-differences.md)

  C + +를 사용 하 여 구조화 된 예외를 처리 하는 방법의 예를 참조 하세요.

## <a name="see-also"></a>참조

[예외 및 오류 처리에 대 한 최신 c + + 모범 사례](../cpp/errors-and-exception-handling-modern-cpp.md)
