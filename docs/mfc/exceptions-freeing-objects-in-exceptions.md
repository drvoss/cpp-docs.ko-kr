---
title: '예외: 예외의 개체 해제'
ms.date: 11/04/2016
helpviewer_keywords:
- throwing exceptions [MFC], freeing objects in exceptions
- local exception handling
- memory leaks, caused by exception
- try-catch exception handling [MFC], destroying objects
- destroying objects [MFC]
- freeing objects [MFC]
- throwing exceptions [MFC], after destroying
- exception handling [MFC], destroying objects
ms.assetid: 3b14b4ee-e789-4ed2-b8e3-984950441d97
ms.openlocfilehash: 49c7c6b0481f90baa23609c1bb1596deda49f7bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371993"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>예외: 예외의 개체 해제

이 문서에서는 예외가 발생할 때 개체를 해제하는 필요성과 방법을 설명합니다. 다룰 주제는 다음과 같습니다.

- [예외를 로컬로 처리](#_core_handling_the_exception_locally)

- [개체를 파괴한 후 예외 throw](#_core_throwing_exceptions_after_destroying_objects)

프레임워크 또는 응용 프로그램에서 throw하는 예외는 정상적인 프로그램 흐름을 방해합니다. 따라서 예외가 throw된 경우 제대로 삭제할 수 있도록 개체를 면밀히 추적하는 것이 매우 중요합니다.

이 작업을 수행하는 두 가지 기본 방법이 있습니다.

- **try** 및 **catch** 키워드를 사용하여 예외를 로컬로 처리한 다음 하나의 문으로 모든 개체를 삭제합니다.

- 추가 처리를 위해 블록 외부에 예외를 throw하기 전에 **catch** 블록의 모든 개체를 삭제합니다.

이러한 두 가지 방법은 다음과 같은 문제가 있는 예제에 대한 솔루션으로 아래에 설명되어 있습니다.

[!code-cpp[NVC_MFCExceptions#14](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]

위에 기록된 `myPerson` 바와 같이 에 의해 `SomeFunc`예외가 throw된 경우 삭제되지 않습니다. 실행은 일반 함수 엑시트와 개체를 삭제하는 코드를 우회하여 다음 외부 예외 처리기로 직접 이동합니다. 예외가 함수를 떠날 때 개체에 대한 포인터가 범위를 벗어나고 프로그램이 실행되는 동안 개체가 차지하는 메모리는 복구되지 않습니다. 메모리 누수입니다. 메모리 진단을 사용하여 검색됩니다.

## <a name="handling-the-exception-locally"></a><a name="_core_handling_the_exception_locally"></a>예외를 로컬로 처리

**try/catch** 패러다임은 메모리 누수 방지 및 예외 발생 시 개체가 소멸되도록 하는 방어적인 프로그래밍 방법을 제공합니다. 예를 들어 이 문서의 앞에 표시된 예제를 다음과 같이 다시 작성할 수 있습니다.

[!code-cpp[NVC_MFCExceptions#15](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]

이 새로운 예제에서는 예외를 catch 하 고 로컬로 처리 하는 예외 처리기를 설정 합니다. 그런 다음 함수를 정상적으로 종료하고 개체를 삭제합니다. 이 예제의 중요한 측면은 예외를 catch하는 컨텍스트가 **try/catch** 블록으로 설정된다는 것입니다. 로컬 예외 프레임이 없으면 함수는 예외가 throw되었다는 것을 알 지 못하며 정상적으로 종료되어 개체를 파괴할 수 없습니다.

## <a name="throwing-exceptions-after-destroying-objects"></a><a name="_core_throwing_exceptions_after_destroying_objects"></a>객체 를 파괴 한 후 예외 를 throw

예외를 처리하는 또 다른 방법은 예외를 다음 외부 예외 처리 컨텍스트로 전달하는 것입니다. **catch** 블록에서 로컬로 할당된 개체를 일부 정리한 다음 추가 처리를 위해 예외를 throw할 수 있습니다.

throw 함수는 힙 개체를 할당 할당할 수도 또는 필요하지 않을 수도 있습니다. 함수가 항상 일반 케이스에서 반환하기 전에 힙 개체를 할당 할당 하는 경우 함수는 예외를 throw 하기 전에 힙 개체를 할당 할당 해야 합니다. 반면에 함수가 일반적인 경우에 반환하기 전에 개체를 할당 지정하지 않는 경우 힙 개체를 할당 할당 지정할지 여부를 사례별로 결정해야 합니다.

다음 예제에서는 로컬로 할당된 개체를 정리하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFCExceptions#16](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]

예외 메커니즘은 프레임 객체를 자동으로 할당 할당 합니다. 프레임 오브젝트의 소멸자도 호출됩니다.

예외를 throw할 수 있는 함수를 호출하는 경우 **try/catch** 블록을 사용하여 예외를 catch하고 만든 개체를 삭제할 수 있습니다. 특히 많은 MFC 함수가 예외를 throw할 수 있습니다.

자세한 내용은 [예외: 예외 catch 및 삭제 예외를](../mfc/exceptions-catching-and-deleting-exceptions.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[예외 처리](../mfc/exception-handling-in-mfc.md)
