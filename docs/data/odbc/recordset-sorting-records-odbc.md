---
title: '레코드 집합: 레코드 정렬(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
ms.openlocfilehash: 8b4deea1d8cbd4abe01ccc7a4114131378abe463
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366920"
---
# <a name="recordset-sorting-records-odbc"></a>레코드 집합: 레코드 정렬(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

이 항목에서는 레코드 집합을 정렬하는 방법을 설명합니다. 정렬을 기반으로 하는 열을 하나 이상 지정할 수 있으며 오름차순 또는**ASC** 내림차순(ASC 또는 **DESC)** **ASC는** 지정된 각 열에 대한 기본값)입니다. 예를 들어 두 개의 열을 지정하면 첫 번째 열에서 먼저 레코드가 정렬되고 두 번째 열은 이름이 지정됩니다. SQL **ORDER BY** 절은 정렬을 정의합니다. 프레임워크가 RECORDset의 SQL 쿼리에 **ORDER BY** 절을 적용하면 절이 선택 항목의 순서를 제어합니다.

개체를 생성한 후 `Open` 해당 멤버 함수를 호출하기 전에 레코드 집합의 정렬 순서를 설정해야 합니다(또는 이전에 `Requery` `Open` 멤버 함수가 호출된 기존 레코드 집합 개체에 대해 멤버 함수를 호출하기 전에).

#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>레코드 집합 개체에 대한 정렬 순서를 지정하려면

1. 새 레코드 집합 개체를 생성하거나 `Requery` 기존 레코드 개체를 호출할 준비를 합니다.

1. 개체의 [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) 데이터 멤버의 값을 설정합니다.

   정렬은 null 종료 된 문자열입니다. **ORDER BY** 절의 내용을 포함하지만 **ORDER BY**키워드는 포함하지 않습니다. 예를 들어 이에 해당하는 서비스는 다음과 같습니다.

    ```
    recordset.m_strSort = "LastName DESC, FirstName DESC";
    ```

   not

    ```
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";
    ```

1. 필터, 잠금 모드 또는 매개 변수와 같이 필요한 다른 옵션을 설정합니다.

1. 새 `Open` 개체(또는 `Requery` 기존 개체)를 호출합니다.

선택한 레코드는 지정된 순서대로 정렬됩니다. 예를 들어 학생 레코드 집합을 성순으로 정렬한 다음 이름을 정렬하려면 다음을 수행합니다.

```cpp
// Construct the recordset
CStudentSet rsStudent( NULL );
// Set the sort
rsStudent.m_strSort = "LastName DESC, FirstName DESC";
// Run the query with the sort in place
rsStudent.Open( );
```

레코드 집합에는 모든 학생 레코드가 포함되고, 내림차순(Z에서 A)으로 성으로 정렬된 다음 이름으로 정렬됩니다.

> [!NOTE]
> 사용자 지정 문자열에 ORDER `Open` **BY** 절이 있는 경우 를 설정 하지 마십시오.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 레코드 집합 매개 변수화(ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[레코드 집합: 레코드 필터링(ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
