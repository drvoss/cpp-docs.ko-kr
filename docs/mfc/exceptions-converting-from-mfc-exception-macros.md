---
title: '예외: MFC 예외 매크로에서 변환'
ms.date: 08/27/2018
helpviewer_keywords:
- converting exceptions [MFC]
- exception objects [MFC]
- conversions [MFC], code written with MFC macros
- keywords [MFC], macros
- macrosv, C++ keywords
- exception objects [MFC], deleting
- CException class [MFC], deleting CException class objects
- exceptions [MFC], converting
- exceptions [MFC], deleting exception objects
- catch blocks [MFC], delimiting
- exception handling [MFC], converting exceptions
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
ms.openlocfilehash: 330f66b1f46542082637645ad53da016b434d4a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372025"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>예외: MFC 예외 매크로에서 변환

이 항목은 고급 항목입니다.

이 문서에서는 Microsoft Foundation Class 매크로로 작성된 기존 코드를 변환하는 **방법(TRY**, **CATCH**, **THROW**등)을 사용하여 C++ 예외 처리 키워드 **try,** **catch**및 **throw를**사용하는 방법에 대해 설명합니다. 다룰 주제는 다음과 같습니다.

- [변환 이점](#_core_advantages_of_converting)

- [예외 매크로가 있는 코드를 C++ 예외를 사용하도록 변환](#_core_doing_the_conversion)

## <a name="advantages-of-converting"></a><a name="_core_advantages_of_converting"></a>변환의 장점

MFC 버전 3.0의 매크로 구현과 이전 버전의 구현 간의 차이점을 알고 있어야 하지만 기존 코드를 변환할 필요는 없습니다. 이러한 차이점과 코드 동작의 후속 변경 사항은 [예외: 버전 3.0의 예외 매크로 변경사항에서](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)설명합니다.

변환의 주요 장점은 다음과 같습니다.

- C++ 예외 처리 키워드를 사용하는 코드는 약간 더 작은 으로 컴파일됩니다. EXE 또는 . Dll.

- C++ 예외 처리 키워드는 더 다양합니다: 복사할 수 있는 모든 데이터 형식의 예외를 **char**처리할 수 있습니다(int, **float,** char 등) 매크로는 클래스**int** `CException` 및 이에서 파생된 클래스의 예외만 처리합니다.

매크로와 키워드의 가장 큰 차이점은 매크로를 사용하는 코드가 예외가 범위를 벗어날 때 "자동으로" catch된 예외를 삭제한다는 것입니다. 키워드를 사용하는 코드는 그렇지 않으므로 catch된 예외를 명시적으로 삭제해야 합니다. 자세한 내용은 [예외: 예외 catch 및 삭제 예외](../mfc/exceptions-catching-and-deleting-exceptions.md)문서를 참조하십시오.

또 다른 차이점은 구문입니다. 매크로 및 키워드에 대한 구문은 세 가지 면에서 다릅니다.

1. 매크로 인수 및 예외 선언:

   **CATCH** 매크로 호출에는 다음과 같은 구문이 있습니다.

   **캐치** *(exception_class,* *exception_object_pointer_name)* **)**

   클래스 이름과 개체 포인터 이름 사이의 쉼표를 확인합니다.

   **catch** 키워드에 대한 예외 선언은 이 구문을 사용합니다.

   **캐치(exception_type** *exception_type* *exception_name)* **)**

   이 예외 선언 문은 catch 블록이 처리하는 예외 유형을 나타냅니다.

2. 캐치 블록의 구분:

   매크로를 사용하면 **CATCH** 매크로(인수)가 첫 번째 catch 블록을 시작합니다. **AND_CATCH** 매크로는 후속 캐치 블록을 시작하고 **END_CATCH** 매크로는 캐치 블록의 시퀀스를 종료합니다.

   키워드를 사용하면 **catch** 키워드(예외 선언)가 각 catch 블록을 시작합니다. **END_CATCH** 매크로에 대응하는 것은 없습니다. 캐치 블록은 닫는 중괄호로 끝납니다.

3. throw 식:

   매크로는 **THROW_LAST** 사용하여 현재 예외를 다시 throw합니다. 인수없이 **throw** 키워드는 동일한 효과를 가합니다.

## <a name="doing-the-conversion"></a><a name="_core_doing_the_conversion"></a>개종하기

#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>매크로를 사용하여 코드를 변환하여 C++ 예외 처리 키워드를 사용하려면

1. MFC 매크로 **TRY,** catch , **AND_CATCH,** **END_CATCH,** **throw**및 **THROW_LAST**모든 발생을 찾습니다. **AND_CATCH**

2. 다음 매크로의 모든 발생을 바꾸거나 삭제합니다.

   **TRY** **(시도로**교체)

   **캐치** **(캐치로**교체)

   **AND_CATCH** **(캐치로**교체)

   **END_CATCH(삭제)**

   **던지기** **(던지기로**교체)

   **THROW_LAST** **(던지기로**교체)

3. 유효한 예외 선언을 형성할 수 있도록 매크로 인수를 수정합니다.

   예를 들어 다음을 변경합니다.

   [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]

   to

   [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]

4. 필요에 따라 예외 개체를 삭제할 수 있도록 catch 블록의 코드를 수정합니다. 자세한 내용은 [예외: 예외 catch 및 삭제 예외](../mfc/exceptions-catching-and-deleting-exceptions.md)문서를 참조하십시오.

다음은 MFC 예외 매크로를 사용하는 예외 처리 코드의 예입니다. 다음 예제의 코드에서 매크로를 사용 하므로 예외가 `e` 자동으로 삭제 됩니다.

[!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]

다음 예제의 코드는 C++ 예외 키워드를 사용하므로 예외를 명시적으로 삭제해야 합니다.

[!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]

자세한 내용은 [예외: MFC 매크로 및 C++ 예외 사용.](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>참고 항목

[예외 처리](../mfc/exception-handling-in-mfc.md)<br/>
