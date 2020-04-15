---
title: '예외: 예외 Catch 및 삭제'
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
ms.openlocfilehash: 74022c8bc6af1d2cdf74fa452d4e0483637e542e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365523"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>예외: 예외 Catch 및 삭제

다음 지침 및 예제에서는 예외를 catch하고 삭제하는 방법을 보여 주며 **try**, **catch**및 **throw** 키워드에 대한 자세한 내용은 예외 및 [오류 처리에 대한 Modern C++ 모범 사례를](../cpp/errors-and-exception-handling-modern-cpp.md)참조하십시오.

예외 처리기는 예외를 삭제하지 않으면 해당 코드가 예외를 catch할 때마다 메모리 누수가 발생하기 때문에 처리하는 예외 개체를 삭제해야 합니다.

**catch** 블록은 다음과 같은 경우 예외를 삭제해야 합니다.

- **catch** 블록은 새 예외를 throw합니다.

   물론 동일한 예외를 다시 throw하는 경우 예외를 삭제해서는 안 됩니다.

   [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- 실행은 **catch** 블록 내에서 반환됩니다.

> [!NOTE]
> 을 `CException`삭제할 때 멤버 `Delete` 함수를 사용하여 예외를 삭제합니다. 예외가 힙에 없는 경우 실패할 수 있으므로 **delete** 키워드를 사용하지 마십시오.

#### <a name="to-catch-and-delete-exceptions"></a>예외를 catch하고 삭제하려면

1. **try** 키워드를 사용하여 **try** 블록을 설정합니다. **try** 블록 내에서 예외를 throw할 수 있는 프로그램 문을 실행합니다.

   **catch** 키워드를 사용하여 **catch** 블록을 설정합니다. **catch** 블록에 예외 처리 코드를 배치합니다. **catch** 블록의 코드는 **try** 블록 내의 코드가 **catch** 문에 지정된 형식의 예외를 throw하는 경우에만 실행됩니다.

   다음 스켈레톤에서는 **시도** 및 **캐치** 블록이 일반적으로 정렬되는 방법을 보여 주며 다음과 같습니다.

   [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   예외가 throw되면 컨트롤은 예외 선언이 예외 유형과 일치하는 첫 번째 **catch** 블록으로 전달됩니다. 아래 나열된 **순차적 catch** 블록을 통해 다양한 유형의 예외를 선택적으로 처리할 수 있습니다.

   [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

자세한 내용은 [예외: MFC 예외 매크로에서 변환을](../mfc/exceptions-converting-from-mfc-exception-macros.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[예외 처리](../mfc/exception-handling-in-mfc.md)
