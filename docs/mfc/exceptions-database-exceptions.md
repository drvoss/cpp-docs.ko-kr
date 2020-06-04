---
title: '예외: 데이터베이스 예외'
ms.date: 09/17/2019
helpviewer_keywords:
- DAO [MFC], exceptions
- exceptions [MFC], database
- exception handling [MFC], databases
- ODBC exceptions [MFC]
- ODBC [MFC], exceptions
- database exceptions [MFC]
- databases [MFC], exception handling
- error codes [MFC], database exception handling
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
ms.openlocfilehash: 894960338a7e8c293054ade00e0cdf3295648bb7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366618"
---
# <a name="exceptions-database-exceptions"></a>예외: 데이터베이스 예외

이 문서에서는 데이터베이스 예외를 처리하는 방법을 설명합니다. 이 문서의 대부분의 자료는 개방형 데이터베이스 연결(ODBC)에 대한 MFC 클래스또는 DAO(데이터 액세스 개체에 대한 MFC 클래스)로 작업하든 관계없이 적용됩니다. 하나 또는 다른 모델에 특정한 재질이 명시적으로 표시됩니다. 다룰 주제는 다음과 같습니다.

- [예외 처리에 대한 접근 방식](#_core_approaches_to_exception_handling)

- [데이터베이스 예외 처리 예제](#_core_a_database_exception.2d.handling_example)

## <a name="approaches-to-exception-handling"></a><a name="_core_approaches_to_exception_handling"></a>예외 처리에 대한 접근 방식

이 방법은 DAO(사용되지 않음) 또는 ODBC로 작업하든 동일합니다.

예외 조건을 처리하기 위해 항상 예외 처리기를 작성해야 합니다.

데이터베이스 예외를 catch하는 가장 실용적인 방법은 예외 시나리오를 사용하여 응용 프로그램을 테스트하는 것입니다. 코드의 작업에 대해 발생할 수 있는 예외를 확인하고 예외가 발생하도록 합니다. 그런 다음 추적 출력을 검사하여 throw되는 예외를 확인하거나 디버거에서 반환된 오류 정보를 검사합니다. 이렇게 하면 사용 중인 예외 시나리오에 대해 표시되는 반환 코드를 알 수 있습니다.

### <a name="error-codes-used-for-odbc-exceptions"></a>ODBC 예외에 사용되는 오류 코드

**양식**AFX_SQL_ERROR_XXX 이름이 있는 프레임워크에서 정의한 코드를 반환하는 것 외에도 일부 [CDBExceptions는](../mfc/reference/cdbexception-class.md) [ODBC](../data/odbc/odbc-basics.md) 반환 코드를 기반으로 합니다. 이러한 예외에 대한 반환 코드에는 **SQL_ERROR_XXX**양식 이름이 있습니다.

데이터베이스 클래스가 반환할 수 있는 반환 코드(프레임워크 정의 및 ODBC [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) 정의 모두)는 클래스의 `CDBException`m_nRetCode 데이터 멤버 아래에 문서화되어 있습니다. ODBC에 의해 정의된 반환 코드에 대한 추가 정보는 MSDN 라이브러리의 ODBC SDK *프로그래머 참조에서* 확인할 수 있습니다.

### <a name="error-codes-used-for-dao-exceptions"></a>DAO 예외에 사용되는 오류 코드

DAO 예외의 경우 일반적으로 더 많은 정보를 사용할 수 있습니다. catch된 [CDaoException](../mfc/reference/cdaoexception-class.md) 개체의 세 가지 데이터 멤버를 통해 오류 정보에 액세스할 수 있습니다.

- [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) 데이터베이스와 연결된 오류 개체의 DAO 컬렉션에 오류 정보를 캡슐화하는 [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) 개체에 대한 포인터가 포함되어 있습니다.

- [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) MFC DAO 클래스의 확장 된 오류 코드가 포함되어 있습니다. **AFX_DAO_ERROR_XXX**양식의 이름이 있는 이러한 오류 코드는 `CDaoException`의 데이터 멤버 아래에 문서화됩니다.

- [m_scode](../mfc/reference/cdaoexception-class.md#m_scode) 해당하는 경우 DAO의 OLE **SCODE를** 포함합니다. 그러나 이 오류 코드로 작업할 필요는 거의 없습니다. 일반적으로 다른 두 데이터 멤버에서 더 많은 정보를 사용할 수 있습니다. **SCODE** 값에 대한 자세한 내용은 데이터 멤버를 참조하십시오.

DAO 오류, DAO 오류 개체 유형 및 DAO 오류 컬렉션에 대한 추가 정보는 [클래스 CDaoException에서](../mfc/reference/cdaoexception-class.md)사용할 수 있습니다.

## <a name="a-database-exception-handling-example"></a><a name="_core_a_database_exception.2d.handling_example"></a>데이터베이스 예외 처리 예제

다음 예제에서는 **새** 연산자와 함께 힙에 [CRecordset-파생](../mfc/reference/crecordset-class.md)개체를 생성한 다음 레코드 집합을 엽니다(ODBC 데이터 원본의 경우). DAO 클래스에 대한 유사한 예제는 아래의 "DAO 예외 예제"를 참조하십시오.

### <a name="odbc-exception-example"></a>ODBC 예외 예

[Open](../mfc/reference/crecordset-class.md#open) 멤버 함수는 예외(ODBC 클래스에 대한 [CDBException](../mfc/reference/cdbexception-class.md) 형식)를 throw할 수 있으므로 이 코드는 `Open` **try** 블록으로 호출을 괄호로 묶습니다. 후속 **캐치** 블록은 `CDBException`. 라는 `e`예외 개체 자체를 검사할 수 있지만 이 경우 레코드 집합을 만들려는 시도가 실패했는지 알 수 있습니다. **catch** 블록은 메시지 상자를 표시하고 레코드 집합 개체를 삭제하여 정리합니다.

[!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>DAO 예외 예

DAO 예제는 ODBC의 예제와 유사하지만 일반적으로 더 많은 종류의 정보를 검색할 수 있습니다. 다음 코드는 레코드 집합을 열려고 시도합니다. 이 시도가 예외를 throw하는 경우 예외 개체의 데이터 멤버에 대한 오류 정보를 검사할 수 있습니다. 이전 ODBC 예제와 마찬가지로 레코드 집합을 만들려는 시도가 실패했다는 것을 아는 것으로 충분합니다.

[!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

이 코드는 예외 개체의 [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) 멤버에서 오류 메시지 문자열을 가져옵니다. MFC는 예외를 throw할 때 이 멤버를 채웁니다.

개체에서 반환되는 오류 정보에 대한 설명은 [클래스 CDaoException](../mfc/reference/cdaoexception-class.md) 및 [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md)를 참조하십시오. `CDaoException`

Microsoft Jet(.mdb) 데이터베이스로 작업하는 경우 대부분의 경우 ODBC로 작업하는 경우 오류 개체가 하나만 있습니다. 드문 경우지만 ODBC 데이터 원본을 사용하고 여러 오류가 있는 경우 [CDaoException::GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount)에서 반환되는 오류 수에 따라 DAO의 오류 컬렉션을 반복할 수 있습니다. 루프를 통해 때마다 [CDaoException::GetErrorInfo를](../mfc/reference/cdaoexception-class.md#geterrorinfo) 호출하여 `m_pErrorInfo` 데이터 멤버를 다시 채웁니다.

## <a name="see-also"></a>참고 항목

[예외 처리](../mfc/exception-handling-in-mfc.md)
