---
title: 트랜잭션(ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets [C++], updating
- transactions [C++], MFC ODBC classes
- ODBC [C++], transactions
- recordsets [C++], updating
- databases [C++], transactions
- recordsets [C++], transactions
- ODBC recordsets [C++], transactions
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
ms.openlocfilehash: 56629f8c5ff74aff4e0df589cda1e7b988fb5fd3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376409"
---
# <a name="transaction-odbc"></a>트랜잭션(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

트랜잭션은 [데이터 원본에](../../data/odbc/data-source-odbc.md) 대한 일련의 업데이트를 그룹화하거나 일괄 처리하여 트랜잭션을 롤백할 경우 모두 한 번에 커밋되거나 커밋되지 않도록 하는 방법입니다. 트랜잭션을 사용하지 않는 경우 요청 시 커밋되는 대신 데이터 원본에 대한 변경 내용이 자동으로 커밋됩니다.

> [!NOTE]
> 모든 ODBC 데이터베이스 드라이버가 트랜잭션을 지원하지는 않습니다. `CanTransact` [CDatabase](../../mfc/reference/cdatabase-class.md) 또는 [CRecordset](../../mfc/reference/crecordset-class.md) 개체의 멤버 함수를 호출하여 드라이버가 지정된 데이터베이스에 대한 트랜잭션을 지원하는지 확인합니다. 데이터 `CanTransact` 원본이 전체 트랜잭션 지원을 제공하는지 여부는 알려주지 않습니다. 또한 호출 `CDatabase::GetCursorCommitBehavior` 후 `CDatabase::GetCursorRollbackBehavior` `CommitTrans` 열려 `Rollback` `CRecordset` 있는 개체에 트랜잭션의 효과 확인 해야 합니다.

개체의 `AddNew` 및 `Edit` 멤버 함수에 대한 호출은 를 호출할 `Update`때 즉시 데이터 원본에 영향을 미칩니다. `CRecordset` `Delete`통화도 즉시 적용됩니다. 반대로 `CommitTrans` 명시적으로 호출할 때까지 수행되지만 커밋되지 `Edit` `Update`않은 `Delete`에 대한 `AddNew`여러 호출로 구성된 트랜잭션을 사용할 수 있습니다. 트랜잭션을 설정하여 롤백할 수 있는 기능을 유지하면서 일련의 호출을 실행할 수 있습니다. 중요한 리소스를 사용할 수 없거나 다른 조건으로 인해 전체 트랜잭션이 완료되지 않는 경우 트랜잭션을 커밋하는 대신 롤백할 수 있습니다. 이 경우 트랜잭션에 속한 변경 내용이 데이터 원본에 영향을 주지 않습니다.

> [!NOTE]
> 현재 클래스는 `CRecordset` 대량 행 가져오기를 구현한 경우 데이터 원본에 대한 업데이트를 지원하지 않습니다. 즉, `AddNew`에 `Edit` `Delete` `Update`대해 호출할 수 없습니다. 그러나 업데이트를 수행 하기 위해 자신의 함수를 작성 하 고 주어진된 트랜잭션 내에서 해당 함수를 호출할 수 있습니다. 대량 행 가져오기에 대한 자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

> [!NOTE]
> 레코드 집합에 영향을 주는 것 외에도 `CDatabase` 트랜잭션은 개체와 연결된 ODBC **HDBC** 또는 해당 **HDBC를**기반으로 하는 ODBC **HSTMT를** 사용하는 한 직접 실행하는 SQL 문에 영향을 줍니다.

트랜잭션은 동시에 업데이트해야 하는 레코드가 여러 개 있는 경우에 특히 유용합니다. 이 경우 마지막 업데이트가 이루어지기 전에 예외가 throw된 경우와 같이 반쯤 완료된 트랜잭션을 방지하려고 합니다. 이러한 업데이트를 트랜잭션으로 그룹화하면 변경 내용의 복구(롤백)가 허용되고 레코드를 사전 트랜잭션 상태로 반환할 수 있습니다. 예를 들어, 은행이 계좌 A에서 계좌 B로 송금하는 경우 A에서 인출하고 B에 대한 입금은 모두 자금을 올바르게 처리하는 데 성공해야 하거나 전체 거래가 실패해야 합니다.

데이터베이스 클래스에서 개체를 통해 `CDatabase` 트랜잭션을 수행 합니다. 개체는 `CDatabase` 데이터 원본에 대한 연결을 나타내며 해당 `CDatabase` 개체와 연결된 하나 이상의 레코드 집합은 레코드 집합 멤버 함수를 통해 데이터베이스 테이블에서 작동합니다.

> [!NOTE]
> 한 수준의 트랜잭션만 지원됩니다. 트랜잭션을 중첩할 수도 트랜잭션은 여러 데이터베이스 개체에 걸쳐 있을 수 없습니다.

다음 항목에서는 트랜잭션이 수행되는 방법에 대한 자세한 정보를 제공합니다.

- [트랜잭션: 레코드 집합에서 트랜잭션 수행(ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

- [트랜잭션: 트랜잭션이 업데이트에 미치는 영향(ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)

## <a name="see-also"></a>참고 항목

[개방형 데이터베이스 연결(ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
