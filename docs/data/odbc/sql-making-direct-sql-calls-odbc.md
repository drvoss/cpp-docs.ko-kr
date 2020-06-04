---
title: 'SQL: SQL 직접 호출(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- SQL, direct calls from ODBC
- SQL, calling directly from ODBC
- ODBC, SQL calls
- SQL calls
- direct SQL calls from ODBC
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
ms.openlocfilehash: e2421e047d217fdc7a138509385399fa37d36a1f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374506"
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL: SQL 직접 호출(ODBC)

이 토픽에서는 다음 내용을 설명합니다.

- 직접 SQL 호출을 사용하는 경우.

- [데이터 원본에 직접 SQL 을 호출하는 방법 .](#_core_making_direct_sql_function_calls)

> [!NOTE]
> 이 정보는 MFC ODBC 클래스에 적용됩니다. MFC DAO 클래스로 작업하는 경우 DAO 도움말의 "Microsoft Jet 데이터베이스 엔진 SQL 및 ANSI SQL 비교" 항목을 참조하십시오.

## <a name="when-to-call-sql-directly"></a><a name="_core_when_to_call_sql_directly"></a>SQL을 직접 호출하는 경우

새 테이블을 만들고, 테이블을 삭제(삭제)하고, 기존 테이블을 변경하고, 인덱스를 만들고, [ODBC(데이터 원본)](../../data/odbc/data-source-odbc.md) 스키마를 변경하는 다른 SQL 함수를 수행하려면 데이터베이스 정의 언어(DDL)를 사용하여 데이터 원본에 직접 SQL 문을 발행해야 합니다. 마법사를 사용하여 테이블에 대한 레코드 집합을 만들 때(디자인 시) 레코드 집합에서 나타낼 테이블의 열을 선택할 수 있습니다. 이렇게 하면 프로그램이 컴파일된 후 사용자 또는 데이터 원본의 다른 사용자가 나중에 테이블에 추가하는 열은 허용되지 않습니다. 데이터베이스 클래스는 DDL을 직접 지원하지 않지만 런타임에 새 열을 레코드 집합에 동적으로 바인딩하는 코드를 작성할 수 있습니다. 이 바인딩을 수행하는 방법에 대한 자세한 내용은 [레코드 집합: ODBC(동적으로 바인딩된 데이터 열)를](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)참조하십시오.

DBMS 자체를 사용하여 스키마 또는 DDL 기능을 수행할 수 있는 다른 도구를 변경할 수 있습니다. 레코드를 반환하지 않는 미리 정의된 쿼리(저장 프로시저)를 호출하는 등 SQL 문을 보내기 위해 ODBC 함수 호출을 사용할 수도 있습니다.

## <a name="making-direct-sql-function-calls"></a><a name="_core_making_direct_sql_function_calls"></a>직접 SQL 함수 호출 하기

[CDatabase 클래스](../../mfc/reference/cdatabase-class.md) 개체를 사용하여 SQL 호출을 직접 실행할 수 있습니다. SQL 문 문자열을 설정하고 (일반적으로)에 `CString`개체의 [CDatabase::ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) 멤버 `CDatabase` 함수에 전달합니다. ODBC 함수 호출을 사용하여 일반적으로 레코드를 반환하는 SQL 문을 보내는 경우 레코드는 무시됩니다.

## <a name="see-also"></a>참고 항목

[SQL](../../data/odbc/sql.md)
