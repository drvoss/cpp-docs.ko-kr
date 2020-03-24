---
title: 'SQL: SQL 및 C++ 데이터 형식(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: 1c1ce908b5c8d345906d49adc79e322225ed49f5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212617"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL 및 C++ 데이터 형식(ODBC)

> [!NOTE]
>  이 정보는 MFC ODBC 클래스에 적용됩니다. MFC DAO 클래스를 사용 하는 경우 DAO 도움말의 "Microsoft Jet 데이터베이스 엔진 SQL 및 ANSI SQL의 비교" 항목을 참조 하십시오.

다음 표에서는 ANSI SQL 데이터 형식을 데이터 형식 C++ 에 매핑합니다. 이는 MSDN Library CD에 있는 *ODBC SDK* *프로그래머 참조* 의 부록 D에 제공 된 C 언어 정보를 보강 합니다. 마법사에서 대부분의 데이터 형식 매핑을 관리 합니다. 마법사를 사용 하지 않는 경우 매핑 정보를 사용 하 여 필드 교환 코드를 수동으로 작성 하는 데 도움이 됩니다.

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>데이터 형식에 C++ 매핑되는 ANSI SQL 데이터 형식

|ANSI SQL 데이터 형식|C++ 데이터 형식|
|------------------------|---------------------|
|**CHAR**|`CString`|
|**DECIMAL**|`CString` 1|
|**SMALLINT**|**int**|
|**REAL**|**float**|
|**INTEGER**|**long**|
|**FLOAT**|**double**|
|**DOUBLE**|**double**|
|**NUMERIC**|`CString` 1|
|**VARCHAR**|`CString`|
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|
|**BIT**|**BOOL**|
|**TINYINT**|**BYTE**|
|**BIGINT**|`CString` 1|
|**바이너리**|`CByteArray`|
|**VARBINARY**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|
|**DATE**|`CTime`, `CString`|
|**TIME**|`CTime`, `CString`|
|**TIMESTAMP**|`CTime`, `CString`|

1. **SQL_C_CHAR** 가 기본 ODBC 전송 형식이 기 때문에 `CString` ANSI **DECIMAL** 및 **NUMERIC** map입니다.

2. 255 자를 초과 하는 문자 데이터는 `CString`에 매핑될 때 기본적으로 잘립니다. `RFX_Text`의 *Nmaxlength* 인수를 명시적으로 설정 하 여 잘림 길이를 확장할 수 있습니다.

3. 255 자를 초과 하는 이진 데이터는 `CByteArray`에 매핑될 때 기본적으로 잘립니다. `RFX_Binary`의 *Nmaxlength* 인수를 명시적으로 설정 하 여 잘림 길이를 확장할 수 있습니다.

ODBC 커서 라이브러리를 사용 하지 않는 경우 Microsoft SQL Server ODBC 드라이버 및 MFC ODBC 데이터베이스 클래스를 사용 하 여 두 개 이상의 긴 가변 길이 필드를 업데이트 하려고 할 때 문제가 발생할 수 있습니다. ODBC 형식 **SQL_LONGVARCHAR** 및 **SQL_LONGVARBINARY**는 텍스트 및 이미지 SQL Server 형식에 매핑됩니다. `CRecordset::Update`에 대 한 동일한 호출에서 두 개 이상의 긴 가변 길이 필드를 업데이트 하는 경우 `CDBException` throw 됩니다. 따라서 `CRecordset::Update`를 사용 하 여 여러 개의 long 열을 동시에 업데이트 하지 마십시오. ODBC API `SQLPutData`를 사용 하 여 여러 개의 긴 열을 동시에 업데이트할 수 있습니다. ODBC 커서 라이브러리를 사용할 수도 있지만 커서를 지 원하는 SQL Server 드라이버와 같은 드라이버에는 커서 라이브러리가 필요 하지 않습니다.

Odbc 커서 라이브러리를 MFC ODBC 데이터베이스 클래스 및 Microsoft SQL Server ODBC 드라이버와 함께 사용 하는 경우 `CRecordset::Update`에 대 한 호출이 `CRecordset::Requery`에 대 한 호출을 따르는 경우 `CDBException`와 함께 **어설션이** 발생할 수 있습니다. 대신 `CRecordset::Close`를 호출 하 고 `CRecordset::Requery`대신 `CRecordset::Open` 합니다. 다른 솔루션은 odbc 커서 라이브러리를 사용 하지 않는 것이 좋습니다. SQL Server 및 SQL Server ODBC 드라이버는 기본적으로 커서를 기본적으로 지원 하며 ODBC 커서 라이브러리가 필요 하지 않기 때문입니다.

## <a name="see-also"></a>참고 항목

[SQL](../../data/odbc/sql.md)<br/>
[SQL: SQL 직접 호출(ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
