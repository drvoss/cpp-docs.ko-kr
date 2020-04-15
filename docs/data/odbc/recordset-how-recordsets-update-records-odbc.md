---
title: '레코드 집합: 레코드 집합의 레코드 업데이트 방법(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records, updating
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
ms.openlocfilehash: 03fb696c1fadd834962d37c8e75b5f8910af819e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366975"
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>레코드 집합: 레코드 집합의 레코드 업데이트 방법(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

레코드 집합은 데이터 원본에서 레코드를 선택하는 기능 외에도 선택한 레코드를 업데이트하거나 삭제하거나 새 레코드를 추가할 수 있습니다. 연결된 데이터 원본을 업데이트할 수 있는지 여부, 레코드 집합 개체를 만들 때 지정한 옵션 및 생성된 SQL의 세 가지 요소가 레코드 집합의 업데이트 가능성을 결정합니다.

> [!NOTE]
> `CRecordset` 개체의 기반이 되는 SQL은 레코드 집합의 업데이트 가능성에 영향을 줄 수 있습니다. 예를 들어 SQL에 조인 또는 **GROUP BY** 절이 포함된 경우 MFC는 업데이트 가능성을 FALSE로 설정합니다.

> [!NOTE]
> 이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다. 대량 행 가져오기를 사용하는 경우 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

이 토픽에서는 다음 내용을 설명합니다.

- [레코드 집합 업데이트에서 사용자의 역할과](#_core_your_role_in_recordset_updating) 프레임워크가 수행하는 작업을 수행합니다.

- [편집 버퍼로 레코드 집합및](#_core_the_edit_buffer) [다이너셋과 스냅숏 간의 차이점](#_core_dynasets_and_snapshots).

[레코드 집합: ODBC(추가 작업, 편집 및 삭제)는](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) 레코드 집합의 관점에서 이러한 함수의 동작을 설명하는 방법입니다.

[레코드 집합: ODBC(업데이트에 대한 자세한 내용)는](../../data/odbc/recordset-more-about-updates-odbc.md) 트랜잭션이 업데이트에 미치는 영향, 레코드 집합 또는 스크롤을 닫는 것이 진행 중인 업데이트에 미치는 영향 및 업데이트가 다른 사용자의 업데이트와 상호 작용하는 방법을 설명하여 레코드 집합 업데이트 스토리를 완료합니다.

## <a name="your-role-in-recordset-updating"></a><a name="_core_your_role_in_recordset_updating"></a>레코드 집합 업데이트에서의 역할

다음 표에서는 레코드 집합을 사용하여 레코드를 추가, 편집 또는 삭제하는 역할과 프레임워크가 수행하는 작업을 보여 줍니다.

### <a name="recordset-updating-you-and-the-framework"></a>레코드 집합 업데이트: 자신과 프레임워크

|이러한 항목을|프레임워크|
|---------|-------------------|
|데이터 원본을 업데이트 할 수 있는지 (또는 부속 가능)인지 확인합니다.|데이터 원본의 업데이트 가능성 또는 부속성을 테스트하기 위해 [CDatabase](../../mfc/reference/cdatabase-class.md) 멤버 함수를 제공합니다.|
|모든 유형의 업데이터 레코드 집합을 엽니다.||
|또는 와 `CanAppend`같은 업데이트 함수를 `CRecordset` 호출하여 레코드 집합이 업데이터인지 여부를 결정합니다. `CanUpdate`||
|레코드 집합 멤버 함수를 호출하여 레코드를 추가, 편집 및 삭제합니다.|레코드 집합 개체와 데이터 원본 간에 데이터를 교환하는 메커니즘을 관리합니다.|
|선택적으로 트랜잭션을 사용하여 업데이트 프로세스를 제어합니다.|트랜잭션을 지원하기 위해 멤버 함수를 제공합니다. `CDatabase`|

트랜잭션에 대한 자세한 내용은 [트랜잭션(ODBC)을](../../data/odbc/transaction-odbc.md)참조하십시오.

## <a name="the-edit-buffer"></a><a name="_core_the_edit_buffer"></a>편집 버퍼

전체적으로 레코드 집합의 필드 데이터 멤버는 현재 레코드인 하나의 레코드를 포함하는 편집 버퍼역할을 합니다. 업데이트 작업은 이 버퍼를 사용하여 현재 레코드에서 작동합니다.

- 레코드를 추가하면 편집 버퍼가 새 레코드를 빌드하는 데 사용됩니다. 레코드 추가를 완료하면 이전에 현재였던 레코드가 다시 현재 상태가 됩니다.

- 레코드를 업데이트(편집)하면 편집 버퍼가 레코드 집합의 필드 데이터 멤버를 새 값으로 설정하는 데 사용됩니다. 업데이트가 완료되면 업데이트된 레코드는 여전히 최신 상태로 유지됩니다.

[AddNew](../../mfc/reference/crecordset-class.md#addnew) 또는 [Edit을](../../mfc/reference/crecordset-class.md#edit)호출하면 현재 레코드가 저장되므로 나중에 필요에 따라 복원할 수 있습니다. [Delete를](../../mfc/reference/crecordset-class.md#delete)호출할 때 현재 레코드는 저장되지 않지만 삭제된 것으로 표시되어 다른 레코드로 스크롤해야 합니다.

> [!NOTE]
> 편집 버퍼는 레코드 삭제에서 아무런 역할을 하지 않습니다. 현재 레코드를 삭제하면 레코드가 삭제된 것으로 표시되고 다른 레코드로 스크롤할 때까지 레코드 집합이 "레코드에 없습니다".

## <a name="dynasets-and-snapshots"></a><a name="_core_dynasets_and_snapshots"></a>다이너셋 및 스냅샷

레코드로 스크롤할 때 [Dynaset은](../../data/odbc/dynaset.md) 레코드의 내용을 새로 고칩니다. [스냅숏은](../../data/odbc/snapshot.md) 레코드의 정적 표현이므로 [Requery](../../mfc/reference/crecordset-class.md#requery)를 호출하지 않는 한 레코드의 내용이 새로 고쳐지지 않습니다. 다이너셋의 모든 기능을 사용하려면 올바른 수준의 ODBC API 지원을 준수하는 ODBC 드라이버로 작업해야 합니다. 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md) 및 [다이너셋](../../data/odbc/dynaset.md)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: AddNew, Edit 및 Delete의 작동 방식(ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)
