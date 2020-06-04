---
title: '트랜잭션: 레코드 집합에서 트랜잭션 수행(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: 45ae414c318376b2c4d787498e9a288a0037af83
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358089"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>트랜잭션: 레코드 집합에서 트랜잭션 수행(ODBC)

이 항목에서는 레코드 집합에서 트랜잭션을 수행하는 방법을 설명합니다.

> [!NOTE]
> 한 수준의 트랜잭션만 지원됩니다. 트랜잭션을 중첩할 수 없습니다.

#### <a name="to-perform-a-transaction-in-a-recordset"></a>레코드 집합에서 트랜잭션을 수행하려면

1. 개체의 `CDatabase` `BeginTrans` 멤버 함수를 호출합니다.

1. 대량 행 페칭을 구현하지 않은 `AddNew/Update` `Edit/Update`경우 `Delete` 동일한 데이터베이스의 하나 이상의 레코드 집합 개체의 "? 및 멤버 함수"를 필요한 횟수만큼 호출합니다. 자세한 내용은 [레코드 집합: 레코드 추가, 업데이트 및 삭제 레코드(ODBC)를](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)참조하십시오. 대량 행 페칭을 구현한 경우 데이터 원본을 업데이트하려면 고유한 함수를 작성해야 합니다.

1. 마지막으로 개체의 `CDatabase` `CommitTrans` 멤버 함수를 호출합니다. 업데이트 중 하나에서 오류가 발생하거나 변경 내용을 취소하기로 결정한 `Rollback` 경우 해당 멤버 함수를 호출합니다.

다음 예제에서는 두 개의 레코드 집합을 사용하여 학교 등록 데이터베이스에서 학생의 등록을 삭제하고 학생이 등록된 모든 수업에서 학생을 제거합니다. 두 `Delete` 레코드 집합의 호출이 모두 성공해야 하므로 트랜잭션이 필요합니다. 이 예제에서는 데이터 `m_dbStudentReg`원본에 이미 연결된 `CDatabase` 형식의 멤버 변수와 레코드 집합 `CEnrollmentSet` `CStudentSet`클래스 및 의 존재를 가정합니다. 변수에는 `strStudentID` 사용자로부터 얻은 값이 포함됩니다.

```
BOOL CEnrollDoc::RemoveStudent( CString strStudentID )
{
    // remove student from all the classes
    // the student is enrolled in

    if ( !m_dbStudentReg.BeginTrans( ) )
        return FALSE;

    CEnrollmentSet rsEnrollmentSet(&m_dbStudentReg);
    rsEnrollmentSet.m_strFilter = "StudentID = " + strStudentID;

    if ( !rsEnrollmentSet.Open(CRecordset::dynaset) )
        return FALSE;

    CStudentSet rsStudentSet(&m_dbStudentReg);
    rsStudentSet.m_strFilter = "StudentID = " + strStudentID;

    if ( !rsStudentSet.Open(CRecordset::dynaset) )
        return FALSE;

    TRY
    {
        while ( !rsEnrollmentSet.IsEOF( ) )
        {
            rsEnrollmentSet.Delete( );
            rsEnrollmentSet.MoveNext( );
        }

        // delete the student record
        rsStudentSet.Delete( );

        m_dbStudentReg.CommitTrans( );
    }

    CATCH_ALL(e)
    {
        m_dbStudentReg.Rollback( );
        return FALSE;
    }
    END_CATCH_ALL

    rsEnrollmentSet.Close( );
    rsStudentSet.Close( );

    return TRUE;

}
```

> [!NOTE]
> 호출하지 `CommitTrans` 않고 `Rollback` 다시 호출하거나 `BeginTrans` 오류입니다.

## <a name="see-also"></a>참고 항목

[트랜잭션(ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[트랜잭션: 트랜잭션이 업데이트에 미치는 영향(ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[C데이터베이스 클래스](../../mfc/reference/cdatabase-class.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)
