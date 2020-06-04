---
title: '예외: 버전 3.0의 예외 매크로 변경 사항'
ms.date: 11/04/2016
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
ms.openlocfilehash: 82320b0c7ccd6766e016f0437633339f8f8f61d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365490"
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>예외: 버전 3.0의 예외 매크로 변경 사항

이 항목은 고급 항목입니다.

MFC 버전 3.0 이상에서는 예외 처리 매크로가 C++ 예외를 사용하도록 변경되었습니다. 이 문서에서는 이러한 변경 내용이 매크로를 사용하는 기존 코드의 동작에 어떤 영향을 줄 수 있는지 설명합니다.

이 문서는 다음 항목을 설명합니다.

- [예외 유형 및 CATCH 매크로](#_core_exception_types_and_the_catch_macro)

- [예외 다시 throw](#_core_re.2d.throwing_exceptions)

## <a name="exception-types-and-the-catch-macro"></a><a name="_core_exception_types_and_the_catch_macro"></a>예외 유형 및 CATCH 매크로

이전 버전의 MFC에서 **CATCH** 매크로는 MFC 런타임 형식 정보를 사용하여 예외의 형식을 확인했습니다. 예외의 형식은 catch 사이트에서 결정됩니다. 그러나 C++ 예외의 경우 예외 형식은 throw된 예외 개체의 형식에 따라 throw 사이트에서 항상 결정됩니다. 이렇게 하면 throw된 개체에 대한 포인터 형식이 throw된 개체의 형식과 다른 드문 경우에 비호환성이 발생합니다.

다음 예제에서는 MFC 버전 3.0과 이전 버전 간의 이러한 차이의 결과를 보여 줍니다.

[!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]

컨트롤은 항상 일치하는 예외 선언을 사용하여 첫 번째 **catch** 블록으로 전달되므로 이 코드는 버전 3.0에서 다르게 행동합니다. throw 식의 결과

[!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]

`CException*`로 생성되더라도 에 대해 `CCustomException`throw됩니다. MFC 버전 2.5의 **CATCH** 매크로는 `CObject::IsKindOf` 이전 버전에서 런타임에 형식을 테스트하는 데 사용합니다. 식은

[!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]

true, 첫 번째 캐치 블록 예외를 catch 합니다. C++ 예외를 사용하여 많은 예외 처리 매크로를 구현하는 버전 3.0에서 두 번째 catch `CException`블록은 throw된 catch 블록과 일치합니다.

이와 같은 코드는 드물다. 일반적으로 예외 개체가 제네릭을 `CException*`허용하는 다른 함수로 전달되고 "사전 throw" 처리를 수행하고 마지막으로 예외를 throw할 때 나타납니다.

이 문제를 해결하려면 throw 식을 함수에서 호출 코드로 이동하고 예외가 생성될 때 컴파일러에 알려진 실제 형식의 예외를 throw합니다.

## <a name="re-throwing-exceptions"></a><a name="_core_re.2d.throwing_exceptions"></a>예외 다시 throw

catch 블록은 잡은 것과 동일한 예외 포인터를 throw할 수 없습니다.

예를 들어 이 코드는 이전 버전에서 유효했지만 버전 3.0에서 예기치 않은 결과가 발생합니다.

[!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]

catch 블록에서 **THROW를** 사용하면 `e` 외부 catch 사이트에서 잘못된 포인터를 받을 수 있도록 포인터가 삭제됩니다. **THROW_LAST** 사용하여 다시 `e`throw합니다.

자세한 내용은 [예외: 예외 catch 및 삭제 예외를](../mfc/exceptions-catching-and-deleting-exceptions.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[예외 처리](../mfc/exception-handling-in-mfc.md)
