---
title: '레코드 집합: 레코드 필터링(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data [MFC], filtering
- recordsets [C++], filtering
- filtering recordsets
- ODBC recordsets [C++], filtering records
- filters [C++], recordset object
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
ms.openlocfilehash: 56b8c4f52ec294f58a760e1309d32aa81286ddec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367008"
---
# <a name="recordset-filtering-records-odbc"></a>레코드 집합: 레코드 필터링(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

이 항목에서는 사용 가능한 레코드의 특정 하위 집합만 선택하도록 레코드 집합을 필터링하는 방법을 설명합니다. 예를 들어 MATH101과 같은 특정 코스의 클래스 섹션만 선택할 수 있습니다. 필터는 SQL **WHERE** 절의 내용에 의해 정의된 검색 조건입니다. 프레임워크가 레코드 집합의 SQL 문에 이 프레임워크를 추가하여 **WHERE** 절은 선택을 제한합니다.

개체를 생성한 후 `Open` 해당 멤버 함수를 호출하기 전에 레코드 집합 개체의 필터를 설정해야 합니다(또는 이전에 `Requery` `Open` 멤버 함수가 호출된 기존 레코드 집합 개체에 대해 멤버 함수를 호출하기 전에).

#### <a name="to-specify-a-filter-for-a-recordset-object"></a>레코드 집합 개체에 대한 필터를 지정하려면

1. 새 레코드 집합 개체를 생성하거나 `Requery` 기존 개체를 호출할 준비를 합니다.

1. 개체의 [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) 데이터 멤버의 값을 설정합니다.

   필터는 SQL **WHERE** 절의 내용을 포함하지만 키워드 **WHERE는**포함하지 않는 null-terminate된 문자열입니다. 예를 들어 이에 해당하는 서비스는 다음과 같습니다.

    ```
    m_pSet->m_strFilter = "CourseID = 'MATH101'";
    ```

   not

    ```
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";
    ```

    > [!NOTE]
    >  리터럴 문자열 "MATH101"은 위의 단일 따옴표로 표시됩니다. ODBC SQL 사양에서 단일 따옴표는 문자 문자열 리터럴을 나타내는 데 사용됩니다. 이 경우 DBMS의 인용 요구 사항에 대한 ODBC 드라이버 설명서를 확인하십시오. 이 구문은 이 항목의 끝 부분에서 더 자세히 설명합니다.

1. 정렬 순서, 잠금 모드 또는 매개 변수와 같이 필요한 다른 옵션을 설정합니다. 매개 변수를 지정하는 것이 특히 유용합니다. 필터 매개 변수화에 대한 자세한 내용은 [레코드 집합: 레코드 집합(ODBC) 매개 변수화를](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)참조하십시오.

1. 새 `Open` 개체(또는 `Requery` 이전에 열린 개체)를 호출합니다.

> [!TIP]
> 필터에서 매개 변수를 사용하는 것이 레코드를 검색하는 가장 효율적인 방법입니다.

> [!TIP]
> 레코드 집합 필터는 테이블을 [조인하고](../../data/odbc/recordset-performing-a-join-odbc.md) 런타임에 획득하거나 계산된 정보를 기반으로 [매개 변수를](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) 사용하는 데 유용합니다.

레코드 집합은 지정한 검색 조건을 충족하는 레코드만 선택합니다. 예를 들어 위에서 설명한 코스 필터를 `strCourseID` 지정하려면(예: 현재 설정된 변수를 "MATH101"로 가정) 다음을 수행합니다.

```
// Using the recordset pointed to by m_pSet

// Set the filter
m_pSet->m_strFilter = "CourseID = " + strCourseID;

// Run the query with the filter in place
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )

// Use the recordset
```

레코드 집합에는 MATH101의 모든 클래스 섹션에 대한 레코드가 포함됩니다.

문자열 변수를 사용하여 위의 예제에서 필터 문자열이 설정된 방법을 확인합니다. 이것은 일반적인 사용법입니다. 그러나 코스 ID에 리터럴 값 100을 지정하려고 한다고 가정합니다. 다음 코드는 리터럴 값으로 필터 문자열을 올바르게 설정하는 방법을 보여 주며 있습니다.

```
m_strFilter = "StudentID = '100'";   // correct
```

단일 따옴표 문자를 사용합니다. 필터 문자열을 직접 설정하면 필터 문자열은 **다음과 다 되지 않습니다.**

```
m_strFilter = "StudentID = 100";   // incorrect for some drivers
```

위에 표시된 인용문은 ODBC 사양을 따르지만 일부 DBMS에는 다른 견적 문자가 필요할 수 있습니다. 자세한 내용은 [SQL: 레코드 집합의 SQL 문(ODBC) 사용자 지정을](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)참조하십시오.

> [!NOTE]
> 사용자 `Open`지정 문자열에 **WHERE** 절이 있는 경우 필터를 설정 하지 않아야 합니다. 기본 SQL 재정의에 대한 자세한 내용은 [SQL: 레코드 집합의 SQL 문(ODBC) 사용자 지정을](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 레코드 정렬(ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)<br/>
[레코드 집합: 레코드 집합의 레코드 선택 방법(ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[레코드 집합: 레코드 집합의 레코드 업데이트 방법(ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[레코드 집합: 레코드 잠금(ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
