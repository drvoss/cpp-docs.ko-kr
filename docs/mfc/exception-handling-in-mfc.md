---
title: MFC의 예외 처리
ms.date: 11/19/2019
helpviewer_keywords:
- DAO [MFC], exceptions
- assertions [MFC], When to use exceptions
- exception handling [MFC], MFC
- resource allocation exception
- resources [MFC], allocating
- keywords [MFC], exception handling
- errors [MFC], detected by assertions
- ODBC exceptions [MFC]
- serialization [MFC], exceptions
- Automation [MFC], exceptions
- exception macros [MFC]
- predefined exceptions [MFC]
- C++ exception handling [MFC], enabling
- C++ exception handling [MFC], MFC applications
- requests for unsupported services [MFC]
- database exceptions [MFC]
- archive exceptions [MFC]
- MFC, exceptions
- C++ exception handling [MFC], types of
- macros [MFC], exception handling
- abnormal program execution [MFC]
- OLE exceptions [MFC], MFC exception handling
- error handling [MFC], exceptions and
- class libraries [MFC], exception support
- exceptions [MFC], MFC macros vs. C++ keywords
- memory [MFC], out-of-memory exceptions
- Windows [MFC], resource allocation exceptions
- macros [MFC], MFC exception macros
- function calls [MFC], results
- out-of-memory exceptions [MFC]
ms.assetid: 0926627d-2ba7-44a6-babe-d851a4a2517c
ms.openlocfilehash: d339ec98dabc6cb24fc7106c4c7238cd6a14a71b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365532"
---
# <a name="exception-handling-in-mfc"></a>MFC의 예외 처리

이 문서에서는 MFC에서 사용할 수 있는 예외 처리 메커니즘에 대해 설명합니다. 두 가지 메커니즘을 사용할 수 있습니다.

- C++ 예외, MFC 버전 3.0 이상에서 사용 가능

- MFC 버전 1.0 이상에서 사용할 수 있는 MFC 예외 매크로

MFC를 사용하여 새 응용 프로그램을 작성하는 경우 C++ 메커니즘을 사용해야 합니다. 기존 응용 프로그램에서 이미 해당 메커니즘을 광범위하게 사용하는 경우 매크로 기반 메커니즘을 사용할 수 있습니다.

MFC 예외 매크로 대신 기존 코드를 C++ 예외를 사용하도록 쉽게 변환할 수 있습니다. 이를 위해 코드 및 지침을 변환하는 이점은 [예외: MFC 예외 매크로에서 변환하는 문서에 설명되어 있습니다.](../mfc/exceptions-converting-from-mfc-exception-macros.md)

MFC 예외 매크로를 사용하여 응용 프로그램을 이미 개발한 경우 새 코드에서 C++ 예외를 사용하는 동안 기존 코드에서 이러한 매크로를 계속 사용할 수 있습니다. 예외 [조항: 버전 3.0의 예외 매크로 변경](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) 사항은 예외 매크로에 대한 지침을 제공합니다.

> [!NOTE]
> 코드에서 C++ 예외 처리를 활성화하려면 프로젝트의 [속성 페이지](../build/reference/property-pages-visual-cpp.md) 대화 상자의 C/C++ 폴더의 코드 생성 페이지에서 C++ 예외 활성화를 선택하거나 [/EHsc](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 사용합니다.

이 문서는 다음 항목을 설명합니다.

- [예외 사용 시기](#_core_when_to_use_exceptions)

- [MFC 예외 지원](#_core_mfc_exception_support)

- [예외에 대한 추가 읽기](#_core_further_reading_about_exceptions)

## <a name="when-to-use-exceptions"></a><a name="_core_when_to_use_exceptions"></a>예외를 사용해야 하는 경우

프로그램 실행 중에 함수가 호출될 때 정상적인 실행, 잘못된 실행 또는 비정상적인 실행이라는 세 가지 범주의 결과가 발생할 수 있습니다. 각 범주는 아래에 설명되어 있습니다.

- 일반 실행

   함수가 정상적으로 실행되고 반환될 수 있습니다. 일부 함수는 함수의 결과를 나타내는 호출자에게 결과 코드를 반환합니다. 가능한 결과 코드는 함수에 대해 엄격하게 정의되며 함수의 가능한 결과 범위를 나타냅니다. 결과 코드는 성공 또는 실패를 나타낼 수도 있고 정상 예상 범위 내에 있는 특정 유형의 실패를 나타낼 수도 있습니다. 예를 들어 파일 상태 함수는 파일이 존재하지 않음을 나타내는 코드를 반환할 수 있습니다. 결과 코드는 많은 예상 결과 중 하나를 나타내므로 "오류 코드"라는 용어는 사용되지 않습니다.

- 잘못된 실행

   호출자는 함수에 인수를 전달하는 실수를 하거나 부적절한 컨텍스트에서 함수를 호출합니다. 이 경우 오류가 발생하며 프로그램 개발 중에 어설션으로 검색해야 합니다. 어설션에 대한 자세한 내용은 [C/C++ 어설션을](/visualstudio/debugger/c-cpp-assertions)참조하십시오.

- 비정상적인 실행

   비정상적인 실행에는 메모리 부족 또는 I/O 오류와 같이 프로그램의 제어 외부 조건이 함수의 결과에 영향을 미치는 상황이 포함됩니다. 비정상적인 상황은 예외를 catch하고 throw하여 처리해야 합니다.

예외를 사용하는 것은 비정상적인 실행에 특히 적합합니다.

## <a name="mfc-exception-support"></a><a name="_core_mfc_exception_support"></a>MFC 예외 지원

C++ 예외를 직접 사용하든 MFC 예외 매크로를 사용하든 프레임워크 또는 `CException`응용 프로그램에서 throw될 수 있는 [CException 클래스](../mfc/reference/cexception-class.md) 또는 -파생 개체를 사용합니다.

다음 표에서는 MFC에서 제공하는 미리 정의된 예외를 보여 주며 있습니다.

|Exception 클래스|의미|
|---------------------|-------------|
|[C메모리예외 클래스](../mfc/reference/cmemoryexception-class.md)|메모리 부족|
|[CFile예외 클래스](../mfc/reference/cfileexception-class.md)|파일 예외|
|[CArchive예외 클래스](../mfc/reference/carchiveexception-class.md)|아카이브/직렬화 예외|
|[CNot지원 예외 클래스](../mfc/reference/cnotsupportedexception-class.md)|지원되지 않는 서비스 요청에 대한 응답|
|[CResource예외 클래스](../mfc/reference/cresourceexception-class.md)|Windows 리소스 할당 예외|
|[CDaoException 클래스](../mfc/reference/cdaoexception-class.md)|데이터베이스 예외(DAO 클래스)|
|[CDB예외 클래스](../mfc/reference/cdbexception-class.md)|데이터베이스 예외(ODBC 클래스)|
|[COleException 클래스](../mfc/reference/coleexception-class.md)|OLE 예외|
|[콜레디스패치예외 클래스](../mfc/reference/coledispatchexception-class.md)|디스패치(자동화) 예외|
|[CUserException 클래스](../mfc/reference/cuserexception-class.md)|사용자에게 메시지 상자를 경고한 다음 제네릭 [CException 클래스를](../mfc/reference/cexception-class.md) throw하는 예외|

버전 3.0 이상에서는 MFC가 C++ 예외를 사용했으나 형식에서 C++ 예외와 유사한 이전 예외 처리 매크로를 여전히 지원합니다. 이러한 매크로는 새 프로그래밍에는 권장되지 않지만 여전히 역 호환성에 대해 지원됩니다. 매크로를 이미 사용하는 프로그램에서 자유롭게 C++ 예외를 사용할 수 있습니다. 전처리하는 동안 매크로는 Visual C++ 버전 2.0의 C++ 언어의 MSVC 구현에 정의된 예외 처리 키워드를 평가합니다. C++ 예외를 사용하는 동안 기존 예외 매크로를 남겨둘 수 있습니다. 매크로 및 C++ 예외 처리 및 새 메커니즘을 사용하도록 이전 코드를 변환하는 방법에 대한 자세한 내용은 [예외: MFC 매크로 및 C++ 예외](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) 및 [예외 사용: MFC 예외 매크로에서 변환하는](../mfc/exceptions-converting-from-mfc-exception-macros.md)방법에 대한 참조. 이전 MFC 예외 매크로를 계속 사용하는 경우 C++ 예외 키워드로 평가합니다. [예외: 버전 3.0의 예외 매크로 변경](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)사항 참조. MFC는 [구조화](/windows/win32/debug/structured-exception-handling)된 예외 처리에서 설명한 대로 Windows NT 구조식 예외 처리기 (SEH)를 직접 지원 하지 않습니다.

## <a name="further-reading-about-exceptions"></a><a name="_core_further_reading_about_exceptions"></a>예외에 대한 추가 읽기

다음 문서에서는 예외 전달을 위해 MFC 라이브러리를 사용하는 것에 대해 설명합니다.

- [예외: 예외 Catch 및 삭제](../mfc/exceptions-catching-and-deleting-exceptions.md)

- [예외: 예외 내용 검사](../mfc/exceptions-examining-exception-contents.md)

- [예외: 예외의 개체 해제](../mfc/exceptions-freeing-objects-in-exceptions.md)

- [예외: 자체 함수에서 예외 Throw](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)

- [예외: 데이터베이스 예외](../mfc/exceptions-database-exceptions.md)

- [예외: OLE 예외](../mfc/exceptions-ole-exceptions.md)

다음 문서에서는 MFC 예외 매크로를 C++ 예외 키워드와 비교하고 코드를 조정하는 방법을 설명합니다.

- [예외: 버전 3.0의 예외 매크로 변경 사항](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)

- [예외: MFC 예외 매크로에서 변환](../mfc/exceptions-converting-from-mfc-exception-macros.md)

- [예외: MFC 매크로 및 C++ 예외 사용](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>참고 항목

[예외 및 오류 처리를 위한 최신 C++ 모범 사례](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[어떻게 합니까: 사용자 지정 예외 클래스 를 직접 만듭니다.](https://go.microsoft.com/fwlink/p/?linkid=128045)
