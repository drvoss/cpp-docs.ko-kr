---
title: '트랜잭션: 레코드 집합에서 트랜잭션 수행(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: 94177a27a1f99a8c9c37b7fce3f697fd0088b7c6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212591"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>트랜잭션: 레코드 집합에서 트랜잭션 수행(ODBC)

이 항목에서는 레코드 집합에서 트랜잭션을 수행 하는 방법에 대해 설명 합니다.

> [!NOTE]
>  한 수준의 트랜잭션만 지원 됩니다. 트랜잭션을 중첩할 수 없습니다.

#### <a name="to-perform-a-transaction-in-a-recordset"></a>레코드 집합에서 트랜잭션을 수행 하려면

1. `CDatabase` 개체의 `BeginTrans` 멤버 함수를 호출 합니다.

1. 대량 행 페치를 구현 하지 않은 경우 필요에 따라 동일한 데이터베이스의 하나 이상의 레코드 집합 개체에 대 한 `AddNew/Update`, `Edit/Update`및 `Delete` 멤버 함수를 호출 합니다. 자세한 내용은 레코드 [집합: 레코드 추가, 업데이트 및 삭제 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)를 참조 하세요. 대량 행 페치를 구현한 경우 고유한 함수를 작성 하 여 데이터 원본을 업데이트 해야 합니다.

1. 마지막으로 `CDatabase` 개체의 `CommitTrans` 멤버 함수를 호출 합니다. 업데이트 중 하나에서 오류가 발생 하거나 변경 내용을 취소 하기로 결정 한 경우 해당 `Rollback` 멤버 함수를 호출 합니다.

다음 예에서는 두 개의 레코드 집합을 사용 하 여 학교 등록 데이터베이스에서 학생의 등록을 삭제 하 고 학생이 등록 된 모든 클래스에서 학생을 제거 합니다. 두 레코드 집합의 `Delete` 호출은 모두 성공 해야 하므로 트랜잭션이 필요 합니다. 이 예제에서는 `m_dbStudentReg`의 존재 여부, 데이터 소스에 이미 연결 된 `CDatabase` 형식의 멤버 변수 및 레코드 집합 클래스 `CEnrollmentSet` 및 `CStudentSet`를 가정 합니다. `strStudentID` 변수는 사용자 로부터 가져온 값을 포함 합니다.

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
>  `CommitTrans` 또는 `Rollback`를 호출 하지 않고 `BeginTrans`을 다시 호출 하는 것은 오류입니다.

## <a name="see-also"></a>참고 항목

[트랜잭션(ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[트랜잭션: 트랜잭션이 업데이트에 미치는 영향(ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[CDatabase 클래스](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)
