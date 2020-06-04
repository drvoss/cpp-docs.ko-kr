---
title: '예외: MFC 매크로 및 C++ 예외 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- exception objects [MFC]
- memory leaks [MFC], exception object not deleted
- exception handling [MFC], MFC
- try-catch exception handling [MFC], mixing MFC macros and C++ keywords
- exception objects [MFC], deleting
- exceptions [MFC], MFC macros vs. C++ keywords
- catch blocks [MFC], mixed
- exception handling [MFC], mixed-language
- nested try blocks [MFC]
- catch blocks [MFC], explicitly deleting code in
- try-catch exception handling [MFC], nested try blocks
- heap corruption [MFC]
- nested catch blocks [MFC]
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
ms.openlocfilehash: afad5335bedf001329ecb401a8a16c663afb5571
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371585"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>예외: MFC 매크로 및 C++ 예외 사용

이 문서에서는 MFC 예외 처리 매크로와 C++ 예외 처리 키워드를 모두 사용하는 코드를 작성하는 데 대한 고려 사항에 대해 설명합니다.

이 문서는 다음 항목을 설명합니다.

- [예외 키워드와 매크로 혼합](#_core_mixing_exception_keywords_and_macros)

- [캐치 블록 내부 블록을 시도](#_core_try_blocks_inside_catch_blocks)

## <a name="mixing-exception-keywords-and-macros"></a><a name="_core_mixing_exception_keywords_and_macros"></a>예외 키워드와 매크로 혼합

동일한 프로그램에서 MFC 예외 매크로 및 C++ 예외 키워드를 혼합할 수 있습니다. 그러나 매크로가 범위를 벗어날 때 예외 개체를 자동으로 삭제하지만 예외 처리 키워드를 사용하는 코드는 그렇지 않으므로 동일한 블록에서 MFC 매크로를 C++ 예외 키워드와 혼합할 수 없습니다. 자세한 내용은 [예외: 예외 catch 및 삭제 예외](../mfc/exceptions-catching-and-deleting-exceptions.md)문서를 참조하십시오.

매크로와 키워드의 주요 차이점은 예외가 범위를 벗어날 때 매크로가 "자동으로" catch된 예외를 삭제한다는 것입니다. 키워드를 사용하는 코드는 그렇지 않습니다. catch 블록에서 catch된 예외는 명시적으로 삭제해야 합니다. 매크로와 C++ 예외 키워드를 혼합하면 예외 개체가 삭제되지 않을 때 메모리 누수가 발생하거나 예외가 두 번 삭제될 때 힙 이 손상될 수 있습니다.

예를 들어 다음 코드는 예외 포인터를 무효화합니다.

[!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

이 문제는 `e` 실행이 "내부" **CATCH** 블록에서 전달될 때 삭제되므로 발생합니다. **throw** 문 대신 **THROW_LAST** 매크로를 사용하면 "외부" **CATCH** 블록이 유효한 포인터를 받게 됩니다.

[!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

## <a name="try-blocks-inside-catch-blocks"></a><a name="_core_try_blocks_inside_catch_blocks"></a>캐치 블록 내부 블록 시도

**CATCH** 블록 내에 있는 **try** 블록 내에서 현재 예외를 다시 throw할 수 없습니다. 다음 예제는 유효하지 않습니다.

[!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

자세한 내용은 [예외: 예외 내용 검사](../mfc/exceptions-examining-exception-contents.md)를 참조하십시오.

## <a name="see-also"></a>참고 항목

[예외 처리](../mfc/exception-handling-in-mfc.md)
