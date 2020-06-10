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
ms.openlocfilehash: 50e3a3f8c064b2a054f0018e87c4e8782a5dc363
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618840"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>예외: 예외 Catch 및 삭제

다음 지침 및 예제에서는 예외를 catch 하 고 삭제 하는 방법을 보여 줍니다. **Try**, **catch**및 **throw** 키워드에 대 한 자세한 내용은 [최신 c + + 모범 사례 예외 및 오류 처리](../cpp/errors-and-exception-handling-modern-cpp.md)를 참조 하세요.

예외를 삭제 하지 못하면 코드가 예외를 catch 할 때마다 예외 처리기가 처리 하는 예외 개체를 삭제 해야 합니다.

**Catch** 블록은 다음과 같은 경우 예외를 삭제 해야 합니다.

- **Catch** 블록은 새 예외를 throw 합니다.

   물론 동일한 예외를 다시 throw 하는 경우 예외를 삭제 하면 안 됩니다.

   [!code-cpp[NVC_MFCExceptions#3](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- **Catch** 블록 내에서 실행이 반환 됩니다.

> [!NOTE]
> 를 삭제할 때 `CException` `Delete` 멤버 함수를 사용 하 여 예외를 삭제 합니다. 예외가 힙에 없는 경우 실패할 수 있으므로 **delete** 키워드를 사용 하지 마십시오.

#### <a name="to-catch-and-delete-exceptions"></a>예외를 catch 하 고 삭제 하려면

1. **Try 키워드를** 사용 하 여 **try** 블록을 설정 합니다. **Try** 블록 내에서 예외를 throw 할 수 있는 모든 프로그램 문을 실행 합니다.

   **Catch 키워드를** 사용 하 여 **catch** 블록을 설정 합니다. **Catch** 블록에 예외 처리 코드를 추가 합니다. **Catch** 블록의 코드는 **try** 블록 내의 코드가 **catch** 문에 지정 된 형식의 예외를 throw 하는 경우에만 실행 됩니다.

   다음 기본 구조는 **try** 블록과 **catch** 블록을 일반적으로 정렬 하는 방법을 보여 줍니다.

   [!code-cpp[NVC_MFCExceptions#4](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   예외가 throw 되 면 예외 선언이 예외 형식과 일치 하는 첫 번째 **catch** 블록으로 제어가 전달 됩니다. 아래에 나열 된 대로 순차 **catch** 블록을 사용 하 여 다양 한 유형의 예외를 선택적으로 처리할 수 있습니다.

   [!code-cpp[NVC_MFCExceptions#5](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

자세한 내용은 [예외: MFC 예외 매크로에서 변환](exceptions-converting-from-mfc-exception-macros.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

[예외 처리](exception-handling-in-mfc.md)
