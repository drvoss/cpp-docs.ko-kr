---
title: 'SQL: 레코드 집합의 SQL 문 사용자 지정(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, SQL statements
- ODBC recordsets, SQL statements
- SQL statements, customizing
- SQL statements, recordset
- customizing SQL statements
- overriding, SQL statements
- SQL, opening recordsets
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
ms.openlocfilehash: 083d268d2b2f2eef072809b1afde9d6ea34f6996
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374512"
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: 레코드 집합의 SQL 문 사용자 지정(ODBC)

이 토픽에서는 다음 내용을 설명합니다.

- 프레임워크가 SQL 문을 구성하는 방법

- SQL 문을 재정의하는 방법

> [!NOTE]
> 이 정보는 MFC ODBC 클래스에 적용됩니다. MFC DAO 클래스로 작업하는 경우 DAO 도움말의 "Microsoft Jet 데이터베이스 엔진 SQL 및 ANSI SQL 비교" 항목을 참조하십시오.

## <a name="sql-statement-construction"></a>SQL 문 구성

레코드 집합은 주로 SQL **SELECT** 문을 기반으로 레코드 선택을 기반으로 합니다. 마법사로 클래스를 선언하면 다음과 같은 `GetDefaultSQL` 멤버 함수의 재정의 버전을 씁니다(레코드 집합 클래스의 `CAuthors`경우).

```cpp
CString CAuthors::GetDefaultSQL()
{
    return "AUTHORS";
}
```

기본적으로 이 재정의는 마법사로 지정한 테이블 이름을 반환합니다. 예제에서 테이블 이름은 "AUTHORS"입니다. 나중에 레코드 집합의 `Open` 멤버 함수를 `Open` 호출하면 양식의 최종 **SELECT** 문을 생성합니다.

```
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]
       [ORDER BY m_strSort]
```

여기서 `table-name` 호출을 `GetDefaultSQL` 통해 `rfx-field-list` 가져오고 에서 RFX 함수 `DoFieldExchange`호출에서 가져옵니다. 매개 변수 또는 필터로 기본 문을 수정할 수도 있지만 런타임에 재정의 버전으로 변경하지 않는 한 **SELECT** 문에 대해 얻을 수 있습니다.

> [!NOTE]
> 공백을 포함하거나 포함할 수 있는 열 이름을 지정하는 경우 이름을 대괄호로 둘러싸야 합니다. 예를 들어 이름 "이름"은 "[이름]"이어야 합니다.

기본 **SELECT** 문을 재정의하려면 을 호출할 `Open`때 전체 **SELECT** 문이 포함된 문자열을 전달합니다. 레코드 집합은 자체 기본 문자열을 생성하는 대신 제공하는 문자열을 사용합니다. 대체 문에 **WHERE** 절이 포함되어 있는 경우 `m_strFilter` 두 개의 필터 문이 있으므로 필터를 지정하지 마십시오. 마찬가지로 대체 문에 ORDER **BY** 절이 포함되어 있는 경우 `m_strSort` 두 개의 정렬 문이 없도록 정렬을 지정하지 마십시오.

> [!NOTE]
> 필터(또는 SQL 문의 다른 부분)에서 리터럴 문자열을 사용하는 경우 DBMS 별 리터럴 접두사 및 리터럴 접미사 문자(또는 문자)가 있는 문자열을 "quote"(지정된 구분 기호로 묶음)해야 할 수 있습니다.

DBMS에 따라 외부 조인과 같은 작업에 대한 특별한 구문 요구 사항이 발생할 수도 있습니다. ODBC 함수를 사용하여 DBMS에 대한 드라이버에서 이 정보를 가져옵니다. 예를 들어 `::SQLGetTypeInfo` 에 와 같은 `SQL_VARCHAR`특정 데이터 형식을 호출하여 LITERAL_PREFIX 문자를 요청하고 문자를 LITERAL_SUFFIX. 데이터베이스 독립적 코드를 작성하는 경우 자세한 구문 정보는 [ODBC 프로그래머의 참조에서](/sql/odbc/reference/odbc-programmer-s-reference) [부록 C: SQL 문법을](/sql/odbc/reference/appendixes/appendix-c-sql-grammar) 참조하십시오.

레코드 집합 개체는 사용자 지정 SQL 문을 전달하지 않는 한 레코드를 선택하는 데 사용하는 SQL 문을 생성합니다. 이 작업을 수행하는 방법은 주로 멤버 함수의 *lpszSQL* `Open` 매개 변수에 전달하는 값에 따라 달라집니다.

SQL **SELECT** 문의 일반적인 형태는 다음과 같은 것입니다.

```
SELECT [ALL | DISTINCT] column-list FROM table-list
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]
```

레코드 집합의 SQL 문에 **DISTINCT** 키워드를 추가하는 한 가지 방법은 `DoFieldExchange`에서 첫 번째 RFX 함수 호출에 키워드를 포함합니다. 다음은 그 예입니다.

```
...
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);
...
```

> [!NOTE]
> 레코드 집합이 읽기 전용으로 열린 경우에만 이 기술을 사용합니다.

## <a name="overriding-the-sql-statement"></a>SQL 문 재정의

다음 표에서는 *lpszSQL* 매개 변수의 `Open`가능성을 보여 줍니다. 표의 사례는 표 다음에 설명되어 있습니다.

**lpszSQL 매개 변수 및 결과 SQL 문자열**

|사례|lpszSQL에서 전달하는 내용|결과 SELECT 문|
|----------|------------------------------|------------------------------------|
|1|NULL|테이블 **이름에서** *table-name* *rfx 필드 목록* **선택**<br /><br /> `CRecordset::Open`을 `GetDefaultSQL` 호출하여 테이블 이름을 가져옵니다. 결과 문자열은 반환되는 항목에 `GetDefaultSQL` 따라 2~5의 경우 중 하나입니다.|
|2|테이블 이름|테이블 **이름에서** *table-name* *rfx 필드 목록* **선택**<br /><br /> 필드 목록은 의 RFX 문에서 `DoFieldExchange`가져온 것입니다. 비어 `m_strFilter` `m_strSort` 있지 않은 경우 **WHERE** 및/또는 **ORDER BY** 절을 추가합니다.|
|3\*|**WHERE** 또는 **ORDER BY** 절이 없는 완전한 **SELECT** 문|통과로. 비어 `m_strFilter` `m_strSort` 있지 않은 경우 **WHERE** 및/또는 **ORDER BY** 절을 추가합니다.|
|4\*|**WHERE** 및/또는 **ORDER BY** 절이 포함된 완전한 **SELECT** 명령문|통과로. `m_strFilter`또는 비어 `m_strSort` 있어야 하거나 두 개의 필터 및/또는 정렬 문이 생성됩니다.|
|5\*|저장 프로시저에 대한 호출|통과로.|

\*`m_nFields` **SELECT** 문에 지정된 열 수보다 적거나 같아야 합니다. **SELECT** 문에 지정된 각 열의 데이터 형식은 해당 RFX 출력 열의 데이터 형식과 같아야 합니다.

### <a name="case-1---lpszsql--null"></a>사례 1 lpszSQL = NULL

레코드 집합 선택은 호출할 `GetDefaultSQL` `CRecordset::Open` 때 반환되는 내용에 따라 달라집니다. 사례 2에서 5까지의 경우 가능한 문자열을 설명합니다.

### <a name="case-2---lpszsql--a-table-name"></a>케이스 2 lpszSQL = 테이블 이름

레코드 집합은 레코드 필드 교환(RFX)을 사용하여 레코드 집합 클래스의 `DoFieldExchange`재정의에서 RFX 함수 호출에 제공된 열 이름에서 열 목록을 작성합니다. 마법사를 사용하여 레코드 집합 클래스를 선언한 경우 이 경우 이 경우 는 사례 1과 동일한 결과를 가지며(마법사에서 지정한 테이블 이름을 전달하는 경우). 마법사를 사용하여 클래스를 작성하지 않는 경우 사례 2는 SQL 문을 생성하는 가장 간단한 방법입니다.

다음 예제는 MFC 데이터베이스 응용 프로그램에서 레코드를 선택 하는 SQL 문을 생성 합니다. 프레임워크가 멤버 `GetDefaultSQL` 함수를 호출하면 함수는 테이블의 `SECTION`이름을 반환합니다.

```cpp
CString CEnrollSet::GetDefaultSQL()
{
    return "SECTION";
}
```

SQL **SELECT** 문에 대 한 열의 이름을 가져오려면 `DoFieldExchange` 프레임 워크는 멤버 함수를 호출 합니다.

```cpp
void CEnrollSet::DoFieldExchange(CFieldExchange* pFX)
{
    pFX->SetFieldType(CFieldExchange::outputColumn);
    RFX_Text(pFX, "CourseID", m_strCourseID);
    RFX_Text(pFX, "InstructorID", m_strInstructorID);
    RFX_Text(pFX, "RoomNo", m_strRoomNo);
    RFX_Text(pFX, "Schedule", m_strSchedule);
    RFX_Text(pFX, "SectionNo", m_strSectionNo);
}
```

완료되면 SQL 문은 다음과 같습니다.

```sql
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo
    FROM SECTION
```

### <a name="case-3---lpszsql--a-selectfrom-statement"></a>대/소문자 3 lpszSQL = SELECT/FROM 문

RFX에 의존하지 않고 수동으로 열 목록을 지정하여 자동으로 구성합니다. 다음과 같은 경우 이 작업을 수행할 수 있습니다.

- **SELECT**에 따라 **고유** 키워드를 지정하려고 합니다.

   열 목록은 `DoFieldExchange`에 나열된 것과 동일한 순서로 열 이름과 형식을 일치시켜야 합니다.

- RFX에 의존하여 열을 바인딩하고 검색하는 `::SQLGetData` 대신 ODBC 함수를 사용하여 열 값을 수동으로 검색해야 하는 이유가 있습니다.

   예를 들어 응용 프로그램이 배포된 후 응용 프로그램의 고객이 데이터베이스 테이블에 추가한 새 열을 수용할 수 있습니다. 마법사를 사용하여 클래스를 선언할 때 알려지지 않은 이러한 추가 필드 데이터 멤버를 추가해야 합니다.

   열 목록은 열 이름과 형식이 `DoFieldExchange`다음에 수동으로 바인딩된 열의 이름과 함께 나열된 순서와 일치해야 합니다. 자세한 내용은 [레코드 집합: ODBC(동적으로 바인딩된 데이터 열)를](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)참조하십시오.

- **FROM** 절에 여러 테이블을 지정하여 테이블을 조인하려고 합니다.

   정보 및 예제는 [레코드 집합: ODBC(조인 수행)를](../../data/odbc/recordset-performing-a-join-odbc.md)참조하십시오.

### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>케이스 4 lpszSQL = 선택/에서 플러스 위치 및/또는 주문별

열 목록(RFX 호출 `DoFieldExchange`기준), 테이블 목록 및 **WHERE** 및/또는 ORDER **BY** 절의 내용을 모두 지정합니다. 이러한 방식으로 **WHERE** 및/또는 **ORDER BY** 절을 지정하는 경우 `m_strSort`를 사용하지 `m_strFilter` 마십시오.

### <a name="case-5---lpszsql--a-stored-procedure-call"></a>사례 5 lpszSQL = 저장 프로시저 호출

미리 정의된 쿼리(예: Microsoft SQL Server 데이터베이스의 저장 프로시저)를 호출해야 하는 경우 *lpszSQL*에 전달하는 문자열에 **CALL** 문을 작성해야 합니다. 마법사는 미리 정의된 쿼리를 호출하기 위해 레코드 집합 클래스선언을 지원하지 않습니다. 미리 정의된 모든 쿼리가 레코드를 반환하지는 않습니다.

미리 정의된 쿼리가 레코드를 반환하지 않는 `CDatabase` 경우 `ExecuteSQL` 멤버 함수를 직접 사용할 수 있습니다. 레코드를 반환하는 미리 정의된 쿼리의 경우 프로시저가 반환하는 `DoFieldExchange` 모든 열에 대해 RFX 호출을 수동으로 작성해야 합니다. RFX 호출은 순서가 같아야 하며 미리 정의된 쿼리와 동일한 형식을 반환해야 합니다. 자세한 내용은 [레코드 집합: 미리 정의된 쿼리(ODBC)에 대한 클래스 선언을](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[SQL: SQL 및 C++ 데이터 형식(ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)<br/>
[SQL: SQL 직접 호출(ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
