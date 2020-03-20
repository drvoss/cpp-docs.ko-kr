---
title: '트랜잭션: 트랜잭션이 업데이트에 미치는 영향(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
ms.openlocfilehash: d03ec3f71c38f7790d66fbf6f800b7647e080147
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "79544425"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>트랜잭션: 트랜잭션이 업데이트에 미치는 영향(ODBC)

[데이터 원본](../../data/odbc/data-source-odbc.md) 에 대 한 업데이트는 편집 버퍼 (트랜잭션 외부에서 사용 되는 것과 동일한 메서드)를 사용 하 여 트랜잭션 중에 관리 됩니다. 레코드 집합의 필드 데이터 멤버는 현재 레코드를 포함 하는 편집 버퍼로 사용 됩니다 .이 버퍼는 레코드 집합이 `AddNew` 또는 `Edit`중에 일시적으로 백업 됩니다. `Delete` 작업 중에는 트랜잭션 내에서 현재 레코드가 백업 되지 않습니다. 편집 버퍼 및 업데이트에서 현재 레코드를 저장 하는 방법에 대 한 자세한 내용은 [레코드 집합: 레코드 집합의 레코드 업데이트 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)을 참조 하세요.

> [!NOTE]
>  대량 행 페치를 구현한 경우 `AddNew`, `Edit`또는 `Delete`를 호출할 수 없습니다. 대신 사용자 고유의 함수를 작성 하 여 데이터 소스에 대 한 업데이트를 수행 해야 합니다. 대량 행 페치에 대 한 자세한 내용은 [레코드 집합: 대량 레코드 페치 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조 하세요.

트랜잭션을 수행 하는 동안 `AddNew`, `Edit`및 `Delete` 작업을 커밋하거나 롤백할 수 있습니다. `CommitTrans` 및 `Rollback`의 영향으로 인해 현재 레코드가 편집 버퍼로 복원 되지 않을 수 있습니다. 현재 레코드가 제대로 복원 되었는지 확인 하려면 `CDatabase`의 `CommitTrans` 및 `Rollback` 멤버 함수가 `CRecordset`의 업데이트 함수를 사용 하는 방법을 이해 하는 것이 중요 합니다.

##  <a name="how-committrans-affects-updates"></a><a name="_core_how_committrans_affects_updates"></a>CommitTrans가 업데이트에 미치는 영향

다음 표에서는 트랜잭션에 `CommitTrans`의 영향을 설명 합니다.

### <a name="how-committrans-affects-updates"></a>CommitTrans가 업데이트에 미치는 영향

|작업(Operation)|데이터 원본 상태|
|---------------|---------------------------|
|`AddNew` 하 고 `Update`한 다음 `CommitTrans`|새 레코드가 데이터 원본에 추가 됩니다.|
|`AddNew` (`Update`하지 않음)을 `CommitTrans`|새 레코드가 손실 됩니다. 레코드가 데이터 원본에 추가 되지 않았습니다.|
|`Edit` 하 고 `Update`한 다음 `CommitTrans`|데이터 소스에 대 한 편집 내용이 커밋됩니다.|
|`Edit` (`Update`하지 않음)을 `CommitTrans`|레코드에 대 한 편집 내용이 손실 됩니다. 레코드는 데이터 원본에서 변경 되지 않은 상태로 유지 됩니다.|
|`Delete` 다음 `CommitTrans`|데이터 원본에서 삭제 된 레코드입니다.|

##  <a name="how-rollback-affects-transactions"></a><a name="_core_how_rollback_affects_updates"></a>롤백이 트랜잭션에 미치는 영향

다음 표에서는 트랜잭션에 `Rollback`의 영향을 설명 합니다.

### <a name="how-rollback-affects-transactions"></a>롤백이 트랜잭션에 미치는 영향

|작업(Operation)|현재 레코드의 상태|또한|데이터 원본 상태|
|---------------|------------------------------|-------------------|---------------------------|
|`AddNew` 하 고 `Update`다음 `Rollback`|현재 레코드의 콘텐츠는 새 레코드를 위한 공간을 만들기 위해 임시로 저장 됩니다. 새 레코드가 편집 버퍼에 입력 됩니다. `Update`를 호출 하면 현재 레코드가 편집 버퍼로 복원 됩니다.||`Update`에 의해 생성 된 데이터 원본에 대 한 추가가 반대로 바뀝니다.|
|`AddNew` (`Update`하지 않음)를 `Rollback`|현재 레코드의 콘텐츠는 새 레코드를 위한 공간을 만들기 위해 임시로 저장 됩니다. 버퍼 편집은 새 레코드를 포함 합니다.|`AddNew`를 다시 호출 하 여 편집 버퍼를 빈 새 레코드로 복원 합니다. 또는 `Move`(0)을 호출 하 여 이전 값을 편집 버퍼에 복원 합니다.|`Update`가 호출 되지 않았기 때문에 데이터 원본에 대 한 변경 내용이 없습니다.|
|`Edit` 하 고 `Update`다음 `Rollback`|현재 레코드의 편집 되지 않은 버전이 일시적으로 저장 됩니다. 편집 버퍼의 내용을 편집 합니다. `Update`를 호출한 후에는 편집 되지 않은 버전의 레코드가 여전히 임시로 저장 됩니다.|*다이너셋*: 현재 레코드를 끄고 뒤로 이동 하 여 편집 되지 않은 버전의 레코드를 편집 버퍼로 복원 합니다.<br /><br /> *Snapshot*: `Requery`를 호출 하 여 데이터 원본에서 레코드 집합을 새로 고칩니다.|`Update`에서 변경한 데이터 원본의 변경 내용이 되돌려집니다.|
|`Edit` (`Update`하지 않음)를 `Rollback`|현재 레코드의 편집 되지 않은 버전이 일시적으로 저장 됩니다. 편집 버퍼의 내용을 편집 합니다.|`Edit`를 다시 호출 하 여 편집 되지 않은 버전의 레코드를 편집 버퍼로 복원 합니다.|`Update`가 호출 되지 않았기 때문에 데이터 원본에 대 한 변경 내용이 없습니다.|
|`Delete` 다음 `Rollback`|현재 레코드의 내용이 삭제 됩니다.|`Requery`를 호출 하 여 데이터 소스에서 현재 레코드의 콘텐츠를 복원 합니다.|데이터 원본에서 데이터를 삭제 하는 것이 반대입니다.|

## <a name="see-also"></a>참고 항목

[트랜잭션(ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[트랜잭션: 레코드 집합에서 트랜잭션 수행(ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)<br/>
[CDatabase 클래스](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)
