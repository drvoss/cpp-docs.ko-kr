---
title: '레코드 집합: 업데이트에 대한 추가 정보(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records, updating
- transactions, updating recordsets
- ODBC recordsets, updating
- multiuser environments, updates to recordsets
- scrolling, updates to recordsets
- updating recordsets
- recordsets, updating
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
ms.openlocfilehash: 955b26137ce976514d84f95f4d819779b93bd78a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368682"
---
# <a name="recordset-more-about-updates-odbc"></a>레코드 집합: 업데이트에 대한 추가 정보(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

이 토픽에서는 다음 내용을 설명합니다.

- [트랜잭션과 같은 다른 작업이 업데이트에 미치는 영향](#_core_how_transactions_affect_updates).

- [귀하의 업데이트 및 다른 사용자의 .](#_core_your_updates_and_the_updates_of_other_users)

- [멤버 업데이트 및 삭제 기능에 대한 자세한 내용은](#_core_more_about_update_and_delete)

> [!NOTE]
> 이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다. 벌크 행 가져오기를 구현한 경우 일부 정보가 적용되지 않습니다. 예를 `AddNew`들어 , " `Edit` `Delete`및 `Update` 멤버 함수를 호출할 수 없습니다. 그러나 트랜잭션을 수행할 수 있습니다. 대량 행 가져오기에 대한 자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

## <a name="how-other-operations-affect-updates"></a><a name="_core_how_other_operations_affect_updates"></a>다른 작업이 업데이트에 미치는 영향

업데이트는 업데이트 당시의 트랜잭션, 트랜잭션을 완료하기 전에 레코드 집합을 닫고 트랜잭션을 완료하기 전에 스크롤하여 영향을 받습니다.

### <a name="how-transactions-affect-updates"></a><a name="_core_how_transactions_affect_updates"></a>트랜잭션이 업데이트에 미치는 영향

의 `AddNew` `Edit`및 `Delete` 작동 방법을 이해하는 것 외에도 [CDatabase의](../../mfc/reference/cdatabase-class.md) `Rollback` `BeginTrans`의 및 `CommitTrans`멤버 함수가 [CRecordset의](../../mfc/reference/crecordset-class.md)업데이트 함수에서 작동하는 방법을 이해하는 것이 중요합니다.

기본적으로 호출할 `AddNew` 때 `Edit` 즉시 데이터 원본에 `Update`호출하고 영향을 미칩니다. `Delete`통화가 즉시 적용됩니다. 그러나 트랜잭션을 설정하고 이러한 호출의 일괄 처리를 실행할 수 있습니다. 업데이트는 커밋할 때까지 영구적이지 않습니다. 마음이 바뀌면 트랜잭션을 커밋하는 대신 롤백할 수 있습니다.

트랜잭션에 대한 자세한 내용은 [트랜잭션(ODBC)을](../../data/odbc/transaction-odbc.md)참조하십시오.

### <a name="how-closing-the-recordset-affects-updates"></a><a name="_core_how_closing_the_recordset_affects_updates"></a>레코드 집합 닫기가 업데이트에 미치는 영향

트랜잭션이 진행 중인 레코드 집합 `CDatabase` 또는 관련 개체를 닫는 경우(CDatabase::CommitTrans 또는 [CDatabase::Rollback라고](../../mfc/reference/cdatabase-class.md#rollback)하지 않음) 데이터베이스 백엔드가 Microsoft Jet 데이터베이스 엔진이 아닌 경우 트랜잭션이 자동으로 롤백됩니다. [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans)

> [!CAUTION]
> Microsoft Jet 데이터베이스 엔진을 사용하는 경우 명시적 트랜잭션 내에서 레코드 집합을 닫으면 명시적 트랜잭션이 커밋되거나 롤백될 때까지 수정된 행이나 잠금이 해제되지 않습니다. 명시적 Jet 트랜잭션 내부 또는 외부에서 레코드 집합을 항상 열고 닫는 것이 좋습니다.

### <a name="how-scrolling-affects-updates"></a><a name="_core_how_scrolling_affects_updates"></a>스크롤이 업데이트에 미치는 영향

레코드 집합: 레코드 집합에서 [ODBC(스크롤)하면](../../data/odbc/recordset-scrolling-odbc.md) 편집 버퍼가 각 새 현재 레코드로 채워지습니다(이전 레코드가 먼저 저장되지 않음). 스크롤은 이전에 삭제된 레코드를 건너뛰습니다. `AddNew` 호출하지 `Edit` `Update`않고 또는 호출 후 스크롤하거나 `Rollback` 먼저 새 레코드가 편집 버퍼로 가져오면 변경 내용이 손실됩니다(경고 없음). `CommitTrans` 편집 버퍼는 스크롤된 레코드로 채워지고 저장된 레코드가 해제되며 데이터 원본에서 변경이 발생하지 않습니다. 이 두 `AddNew` 가지 `Edit`모두에 적용 됩니다.

## <a name="your-updates-and-the-updates-of-other-users"></a><a name="_core_your_updates_and_the_updates_of_other_users"></a>사용자의 업데이트 및 다른 사용자의 업데이트

레코드 집합을 사용하여 데이터를 업데이트하면 업데이트가 다른 사용자에게 영향을 줍니다. 마찬가지로 레코드 집합의 수명 동안 다른 사용자의 업데이트가 사용자에게 영향을 미칩니다.

다중 사용자 환경에서 다른 사용자는 레코드 집합에서 선택한 것과 동일한 레코드중 일부를 포함하는 레코드 집합을 열 수 있습니다. 레코드를 검색하기 전에 변경한 내용이 레코드 집합에 반영됩니다. 다이너셋은 스크롤할 때마다 레코드를 검색하므로 다이너셋은 레코드로 스크롤할 때마다 변경 내용을 반영합니다. 스냅샷은 처음 스크롤할 때 레코드를 검색하므로 스냅숏은 처음에 레코드로 스크롤하기 전에 발생하는 변경 내용만 반영합니다.

레코드 집합을 연 후 다른 사용자가 추가한 레코드는 다시 쿼리하지 않는 한 레코드 집합에 표시되지 않습니다. 레코드 집합이 다이너셋인 경우 영향을 받는 레코드로 스크롤할 때 다른 사용자가 기존 레코드를 편집하면 다이너셋에 표시됩니다. 레코드 집합이 스냅샷인 경우 스냅숏을 다시 쿼리할 때까지 편집이 표시되지 않습니다. 스냅샷의 다른 사용자가 추가하거나 삭제한 레코드또는 다이너셋의 다른 사용자가 추가한 레코드를 보려면 [CRecordset::Requery를](../../mfc/reference/crecordset-class.md#requery) 호출하여 레코드 집합을 다시 빌드합니다. 다른 사용자의 삭제는 다이너셋에 표시됩니다. 추가한 레코드를 보려면 전화를 걸 `Requery` 수도 있지만 삭제는 볼 수 없습니다.

> [!TIP]
> 전체 스냅숏을 한 번에 캐싱하려면 스냅숏을 연 직후에 호출합니다. `MoveLast` 그런 `MoveFirst` 다음 호출하여 레코드 작업을 시작합니다. `MoveLast`모든 레코드를 스크롤하는 것과 동일하지만 한 번에 모두 검색합니다. 그러나 이 경우 성능이 저하될 수 있으며 일부 드라이버에서는 필요하지 않을 수 있습니다.

업데이트가 다른 사용자에게 미치는 영향은 업데이트가 사용자에게 미치는 영향과 유사합니다.

## <a name="more-about-update-and-delete"></a><a name="_core_more_about_update_and_delete"></a>업데이트 및 삭제에 대한 자세한 내용은

이 섹션에서는 및 `Update` `Delete`을 사용하여 작업하는 데 도움이 되는 추가 정보를 제공합니다.

### <a name="update-success-and-failure"></a>업데이트 성공 및 실패

성공하면 `Update` 또는 `AddNew` `Edit` 모드가 종료됩니다. `AddNew` 또는 `Edit` 모드를 다시 시작하려면 `AddNew` `Edit`또는 에 전화하거나

실패(FALSE를 반환하거나 예외를 throw)하는 경우 `Update` 마지막으로 호출한 기능에 따라 `AddNew` `Edit` 또는 모드에 남아 있습니다. 그러면 다음 중 하나를 수행합니다.

- 필드 데이터 멤버를 수정하고 다시 시도합니다. `Update`

- 필드 `AddNew` 데이터 멤버를 Null로 재설정하고 필드 데이터 멤버의 값을 설정한 `Update` 다음 다시 호출합니다.

- 호출을 `Edit` 호출하여 첫 번째 호출 전에 레코드 집합에 있던 값을 다시 `AddNew` 로드하거나, `Edit`필드 `Update` 데이터 멤버의 값을 설정한 다음 다시 호출합니다. 성공적인 `Update` 호출 `AddNew` 후(호출 후 제외) 필드 데이터 멤버는 새 값을 유지합니다.

- 모든 `Move` 변경 `Move` 내용을 플러시하고 적용 중인 모든 `AddNew` 모드 또는 `Edit` 모드를 종료하는 호출(AFX_MOVE_REFRESH 또는 0의 매개 변수 포함).

### <a name="update-and-delete"></a>업데이트 및 삭제

이 섹션은 `Update` 모두 `Delete`및 에 적용됩니다.

또는 `Delete` `Update` 작업에서 하나만 레코드를 업데이트해야 합니다. 해당 레코드는 레코드 집합 필드의 데이터 값에 해당하는 현재 레코드입니다. 어떤 이유로 든 레코드가 영향을 받지 않거나 둘 이상의 레코드가 영향을 받는 경우 다음 **RETCODE** 값 중 하나를 포함하는 예외가 throw됩니다.

- AFX_SQL_ERROR_NO_ROWS_AFFECTED

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED

`AddNew` 이러한 예외가 throw되면 호출할 `Edit` `Update` 때 또는 에 있던 상태 `Delete`또는 상태로 유지됩니다. 다음은 이러한 예외가 표시되는 가장 일반적인 시나리오입니다. 다음과 같은 가능성이 높습니다.

- AFX_SQL_ERROR_NO_ROWS_AFFECTED 낙관적 잠금 모드를 사용하는 경우 다른 사용자가 업데이트하거나 삭제할 올바른 레코드를 식별하지 못하도록 하는 방식으로 레코드를 수정했습니다.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED 업데이트하는 테이블에 기본 키 또는 고유 인덱스가 없고 레코드 집합에 테이블 행을 고유하게 식별할 수 있는 열이 충분하지 않은 경우입니다.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 레코드 집합의 레코드 선택 방법(ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[레코드 필드 교환(RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)
