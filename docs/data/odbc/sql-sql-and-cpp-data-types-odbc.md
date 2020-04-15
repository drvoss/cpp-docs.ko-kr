---
title: 'SQL: SQL 및 C++ 데이터 형식(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: cffe44b832ac1eb28d368072b8f0e92ea9f57feb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374475"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL 및 C++ 데이터 형식(ODBC)

> [!NOTE]
> 이 정보는 MFC ODBC 클래스에 적용됩니다. MFC DAO 클래스로 작업하는 경우 DAO 도움말의 "Microsoft Jet 데이터베이스 엔진 SQL 및 ANSI SQL 비교" 항목을 참조하십시오.

다음 표는 ANSI SQL 데이터 형식을 C++ 데이터 형식에 매핑합니다. 이렇게 하면 MSDN 라이브러리 CD에 있는 *ODBC SDK* *프로그래머의 참조* 부록 D에 제공된 C 언어 정보가 보강됩니다. 마법사는 대부분의 데이터 형식 매핑을 관리합니다. 마법사를 사용하지 않는 경우 매핑 정보를 사용하여 필드 교환 코드를 수동으로 작성할 수 있습니다.

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>C++ 데이터 유형에 매핑된 ANSI SQL 데이터 유형

|ANSI SQL 데이터 유형|C++ 데이터 형식|
|------------------------|---------------------|
|**Char**|`CString`|
|**10 진수**|`CString`1|
|**Smallint**|**Int**|
|**진짜**|**플 로트**|
|**정수**|**긴**|
|**플 로트**|**double**|
|**더블**|**double**|
|**숫자**|`CString`1|
|**VARCHAR**|`CString`|
|**롱바르차르**|`CLongBinary`, `CString` 2|
|**비트**|**Bool**|
|**Tinyint**|**바이트**|
|**Bigint**|`CString`1|
|**이진**|`CByteArray`|
|**Varbinary**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|
|**날짜**|`CTime`, `CString`|
|**시간**|`CTime`, `CString`|
|**TIMESTAMP**|`CTime`, `CString`|

1. anSI **소수점** 및 **숫자** `CString` 맵은 **SQL_C_CHAR** 기본 ODBC 전송 유형이기 때문입니다.

2. 에 매핑될 때 255자를 초과하는 문자 데이터는 `CString`기본적으로 잘립니다. *의 nMaxLength* 인수를 명시적으로 설정하여 잘림 길이를 `RFX_Text`연장할 수 있습니다.

3. 에 매핑될 때 255자를 초과하는 이진 데이터는 `CByteArray`기본적으로 잘립니다. *의 nMaxLength* 인수를 명시적으로 설정하여 잘림 길이를 `RFX_Binary`연장할 수 있습니다.

ODBC 커서 라이브러리를 사용하지 않는 경우 Microsoft SQL Server ODBC 드라이버와 MFC ODBC 데이터베이스 클래스를 사용하여 두 개 이상의 긴 가변 길이 필드를 업데이트하려고 할 때 문제가 발생할 수 있습니다. ODBC 유형, **SQL_LONGVARCHAR** 및 **SQL_LONGVARBINARY**텍스트 및 이미지 SQL Server 유형에 매핑됩니다. 동일한 `CDBException` 호출에서 두 개 이상의 긴 가변 길이 필드를 `CRecordset::Update`업데이트하면 A가 throw됩니다. 따라서 `CRecordset::Update`여러 긴 열을 와 동시에 업데이트하지 마십시오. ODBC API와 `SQLPutData`동시에 여러 긴 열을 업데이트할 수 있습니다. ODBC 커서 라이브러리를 사용할 수도 있지만 커서를 지원하고 커서 라이브러리가 필요하지 않은 SQL Server 드라이버와 같은 드라이버에는 사용하지 않는 것이 좋습니다.

MFC ODBC 데이터베이스 클래스 및 Microsoft SQL Server ODBC 드라이버와 함께 ODBC 커서 라이브러리를 `CDBException` 사용하는 경우 `CRecordset::Update` `CRecordset::Requery`에 대한 호출을 따르는 경우 **ASSERT가** 발생할 수 있습니다. 대신 에 `CRecordset::Close` `CRecordset::Open` 전화하는 `CRecordset::Requery`대신 에 전화하십시오. 또 다른 해결책은 SQL Server 및 SQL Server ODBC 드라이버가 기본적으로 커서에 대한 기본 지원을 제공하고 ODBC 커서 라이브러리가 필요하지 않기 때문에 ODBC 커서 라이브러리를 사용하지 않는 것입니다.

## <a name="see-also"></a>참고 항목

[SQL](../../data/odbc/sql.md)<br/>
[SQL: SQL 직접 호출(ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
