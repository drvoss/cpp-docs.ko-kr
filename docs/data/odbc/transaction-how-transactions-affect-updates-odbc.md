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
ms.openlocfilehash: 8a87176ecb20beaf46583e1190b0ad458d508b31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376426"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>트랜잭션: 트랜잭션이 업데이트에 미치는 영향(ODBC)

[데이터 원본에](../../data/odbc/data-source-odbc.md) 대한 업데이트는 편집 버퍼(트랜잭션 외부에서 사용되는 방법과 동일한 방법)를 사용하여 트랜잭션 중에 관리됩니다. 레코드 집합의 필드 데이터 멤버는 집합적으로 현재 레코드를 포함하는 편집 버퍼로 작동하며, `AddNew` 레코드 `Edit`집합은 또는 . `Delete` 작업 중에 현재 레코드가 트랜잭션 내에 백업되지 않습니다. 편집 버퍼 및 업데이트가 현재 레코드를 저장하는 방법에 대한 자세한 내용은 [레코드 집합: 레코드 집합 업데이트 레코드(ODBC)를](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)참조하십시오.

> [!NOTE]
> 대량 행 가져오기를 구현한 경우 `AddNew`를 `Edit`호출할 수 없습니다. `Delete` 대신 데이터 원본에 대한 업데이트를 수행하려면 고유한 함수를 작성해야 합니다. 대량 행 가져오기에 대한 자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

트랜잭션 중에 `AddNew` `Edit`및 `Delete` 작업을 커밋하거나 롤백할 수 있습니다. `CommitTrans` 현재 레코드가 `Rollback` 편집 버퍼로 복원되지 않을 수 있습니다. 현재 레코드가 제대로 복원되었는지 `CommitTrans` 확인하려면 `Rollback` `CDatabase` `CRecordset`의 업데이트 함수를 사용하여 의 및 멤버 함수가 어떻게 작동하는지 이해하는 것이 중요합니다.

## <a name="how-committrans-affects-updates"></a><a name="_core_how_committrans_affects_updates"></a>커밋트랜스가 업데이트에 미치는 영향

다음 표는 트랜잭션이 `CommitTrans` 미치는 영향을 설명합니다.

### <a name="how-committrans-affects-updates"></a>커밋트랜스가 업데이트에 미치는 영향

|작업(Operation)|데이터 원본의 상태|
|---------------|---------------------------|
|`AddNew`및, `Update`그리고 나서`CommitTrans`|새 레코드가 데이터 원본에 추가됩니다.|
|`AddNew`(무) `Update`그리고`CommitTrans`|새 레코드가 손실됩니다. 레코드가 데이터 원본에 추가되지 않았습니다.|
|`Edit`및, `Update`그리고 나서`CommitTrans`|데이터 원본에 커밋된 편집.|
|`Edit`(무) `Update`그리고`CommitTrans`|레코드에 대한 편집이 손실됩니다. 레코드는 데이터 원본에서 변경되지 않습니다.|
|`Delete`다음`CommitTrans`|데이터 원본에서 삭제된 레코드입니다.|

## <a name="how-rollback-affects-transactions"></a><a name="_core_how_rollback_affects_updates"></a>롤백이 트랜잭션에 미치는 영향

다음 표는 트랜잭션이 `Rollback` 미치는 영향을 설명합니다.

### <a name="how-rollback-affects-transactions"></a>롤백이 트랜잭션에 미치는 영향

|작업(Operation)|현재 레코드의 상태|또한|데이터 원본의 상태|
|---------------|------------------------------|-------------------|---------------------------|
|`AddNew`그리고, `Update``Rollback`|현재 레코드의 내용은 새 레코드를 위한 공간을 확보하기 위해 일시적으로 저장됩니다. 새 레코드가 편집 버퍼에 입력됩니다. 호출 `Update` 후 현재 레코드가 편집 버퍼로 복원됩니다.||에 의해 `Update` 만들어진 데이터 원본에 추가 반전됩니다.|
|`AddNew`(무) `Update``Rollback`|현재 레코드의 내용은 새 레코드를 위한 공간을 확보하기 위해 일시적으로 저장됩니다. 편집 버퍼에는 새 레코드가 포함되어 있습니다.|편집 `AddNew` 버퍼를 빈 새 레코드로 복원하려면 다시 호출합니다. 또는 `Move`(0)를 호출하여 이전 값을 편집 버퍼에 복원합니다.|호출되지 않았기 때문에 `Update` 데이터 원본에 대한 변경 사항이 없습니다.|
|`Edit`그리고, `Update``Rollback`|현재 레코드의 편집되지 않은 버전이 일시적으로 저장됩니다. 편집 버퍼의 내용을 편집합니다. 호출된 후에도 `Update` 편집되지 않은 레코드 버전은 여전히 일시적으로 저장됩니다.|*Dynaset*: 현재 레코드를 스크롤한 다음 다시 스크롤하여 편집 버퍼에 레코드의 편집되지 않은 버전을 복원합니다.<br /><br /> *스냅샷* `Requery` : 호출하여 데이터 원본에서 레코드 집합을 새로 고칩니다.|데이터 원본에 대한 `Update` 변경 내용은 반대로 변경됩니다.|
|`Edit`(무) `Update``Rollback`|현재 레코드의 편집되지 않은 버전이 일시적으로 저장됩니다. 편집 버퍼의 내용을 편집합니다.|편집 `Edit` 버퍼에 레코드의 편집되지 않은 버전을 복원하려면 다시 호출합니다.|호출되지 않았기 때문에 `Update` 데이터 원본에 대한 변경 사항이 없습니다.|
|`Delete`다음`Rollback`|현재 레코드의 콘텐츠가 삭제됩니다.|데이터 `Requery` 원본에서 현재 레코드의 내용을 복원하려면 호출합니다.|데이터 원본에서 데이터를 삭제하는 것은 반대로 처리됩니다.|

## <a name="see-also"></a>참고 항목

[트랜잭션(ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[트랜잭션: 레코드 집합에서 트랜잭션 수행(ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)<br/>
[C데이터베이스 클래스](../../mfc/reference/cdatabase-class.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)
