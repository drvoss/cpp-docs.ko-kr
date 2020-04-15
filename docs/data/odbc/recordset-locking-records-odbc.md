---
title: '레코드 집합: 레코드 잠금(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- locks [C++], recordsets
- optimistic locking
- pessimistic locking in ODBC
- recordsets [C++], locking records
- optimistic locking, ODBC
- ODBC recordsets [C++], locking records
- data [C++], locking
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
ms.openlocfilehash: abd5f817ad321241df2d8565bd6bf346c0792088
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366958"
---
# <a name="recordset-locking-records-odbc"></a>레코드 집합: 레코드 잠금(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

이 토픽에서는 다음 내용을 설명합니다.

- [사용 가능한 레코드 잠금의 종류입니다.](#_core_record.2d.locking_modes)

- [업데이트 하는 동안 레코드 집합에 레코드를 잠그는 방법.](#_core_locking_records_in_your_recordset)

레코드 집합을 사용하여 데이터 원본의 레코드를 업데이트하면 응용 프로그램이 레코드를 잠그므로 다른 사용자가 동시에 레코드를 업데이트할 수 없습니다. 시스템에서 두 사용자가 동시에 레코드를 업데이트할 수 없다고 보장할 수 없는 경우 두 사용자가 동시에 업데이트하는 레코드의 상태는 정의되지 않습니다.

> [!NOTE]
> 이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다. 벌크 행 가져오기를 구현한 경우 일부 정보가 적용되지 않습니다. 예를 들어 `Edit` 및 `Update` 멤버 함수를 호출할 수 없습니다. 대량 행 가져오기에 대한 자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

## <a name="record-locking-modes"></a><a name="_core_record.2d.locking_modes"></a>레코드 잠금 모드

데이터베이스 클래스는 두 [가지 레코드 잠금 모드를](../../mfc/reference/crecordset-class.md#setlockingmode)제공합니다.

- 낙관적 잠금(기본값)

- 비관적 잠금

레코드 업데이트는 다음 세 단계로 수행됩니다.

1. [멤버 편집](../../mfc/reference/crecordset-class.md#edit) 함수를 호출하여 작업을 시작합니다.

1. 현재 레코드의 해당 필드를 변경합니다.

1. [Update](../../mfc/reference/crecordset-class.md#update) 멤버 함수를 호출하여 작업을 종료하고 일반적으로 업데이트를 커밋합니다.

낙관적 잠금은 호출 중에만 데이터 원본의 레코드를 잠급전지 `Update` 않습니다. 다중 사용자 환경에서 낙관적 잠금을 사용하는 경우 응용 `Update` 프로그램은 오류 조건을 처리해야 합니다. `Edit` 비관적 잠금은 호출하자마자 레코드를 잠그고 호출할 `Update` 때까지 레코드를 해제하지 `CDBException` 않습니다(오류는 메커니즘을 통해 `Update`표시되며 FALSE 값이 반환됨). 비관적 잠금은 응용 프로그램 `Update` 프로세스가 완료될 때까지 동일한 레코드에 대한 동시 액세스가 필요할 수 있으므로 다른 사용자에게 성능 저하가 발생할 수 있습니다.

## <a name="locking-records-in-your-recordset"></a><a name="_core_locking_records_in_your_recordset"></a>레코드 집합의 레코드 잠금

레코드 집합 개체의 [잠금 모드를](#_core_record.2d.locking_modes) 기본값에서 변경하려면 호출하기 `Edit`전에 모드를 변경해야 합니다.

#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>레코드 집합의 현재 잠금 모드를 변경하려면

1. [SetLockingMode](../../mfc/reference/crecordset-class.md#setlockingmode) 멤버 함수를 호출하여 `CRecordset::pessimistic` `CRecordset::optimistic`또는 을 지정합니다.

새 잠금 모드는 다시 변경하거나 레코드 집합이 닫혀있을 때까지 유효합니다.

> [!NOTE]
> 현재 비관적 잠금을 지원하는 ODBC 드라이버는 상대적으로 적습니다.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 조인 수행(ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)<br/>
[레코드 집합: 레코드 추가, 업데이트 및 삭제(ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)
