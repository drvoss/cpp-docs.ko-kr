---
title: '예외: 자체 함수에서 예외 Throw'
ms.date: 11/04/2016
helpviewer_keywords:
- throwing exceptions [MFC], from functions
- functions [MFC], throwing exceptions
- exceptions [MFC], throwing
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
ms.openlocfilehash: 6484594df7636fd52ac46ab1cc212c8e2ec0278e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359284"
---
# <a name="exceptions-throwing-exceptions-from-your-own-functions"></a>예외: 자체 함수에서 예외 Throw

MFC 예외 처리 패러다임을 사용하여 MFC 또는 다른 라이브러리의 함수에서 throw된 예외를 catch할 수 있습니다. 라이브러리 코드에서 throw된 예외를 catch하는 것 외에도 예외적인 조건이 발생할 수 있는 함수를 작성하는 경우 고유한 코드에서 예외를 throw할 수 있습니다.

예외가 throw되면 현재 함수의 실행이 중지되고 가장 안쪽 예외 프레임의 **catch** 블록으로 직접 이동합니다. 예외 메커니즘은 함수에서 법선 종료 경로를 무시합니다. 따라서 일반 엑시트에서 삭제되는 메모리 블록을 삭제해야 합니다.

#### <a name="to-throw-an-exception"></a>예외를 throw하려면

1. 와 같은 `AfxThrowMemoryException`MFC 도우미 기능 중 하나를 사용합니다. 이러한 함수는 적절한 형식의 preallocated 예외 개체를 throw합니다.

   다음 예제에서 함수는 두 개의 메모리 블록을 할당하려고 시도하고 할당이 실패할 경우 예외를 throw합니다.

   [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]

   첫 번째 할당이 실패하면 메모리 예외를 throw하기만 하면 됩니다. 첫 번째 할당이 성공했지만 두 번째 할당이 실패하면 예외를 throw하기 전에 첫 번째 할당 블록을 해제해야 합니다. 두 할당이 모두 성공하면 정상적으로 진행하고 함수를 종료할 때 블록을 해제할 수 있습니다.

     - 또는-

1. 사용자 정의 예외를 사용하여 문제 조건을 나타냅니다. 예외로 모든 유형의 항목, 심지어 전체 클래스를 throw할 수 있습니다.

   다음 예제에서는 웨이브 장치를 통해 사운드를 재생하려고 시도하고 오류가 있는 경우 예외를 throw합니다.

   [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]

> [!NOTE]
> MFC의 기본 예외 처리는 개체(및 `CException` -derived 클래스의 `CException`개체)에 대해서만 적용됩니다. 위의 예제는 MFC의 예외 메커니즘을 우회합니다.

## <a name="see-also"></a>참고 항목

[예외 처리](../mfc/exception-handling-in-mfc.md)
