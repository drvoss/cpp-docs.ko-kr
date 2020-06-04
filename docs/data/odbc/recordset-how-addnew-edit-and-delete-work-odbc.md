---
title: '레코드 집합: AddNew, Edit 및 Delete의 작동 방식(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- AddNew method
- ODBC recordsets [C++], deleting records
- records [C++], deleting in recordsets
- data in recordsets [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: cab43d43-235a-4bed-ac05-67d10e94f34e
ms.openlocfilehash: 63718a6be3a9ce19ddbce923a84def21448c42a0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366998"
---
# <a name="recordset-how-addnew-edit-and-delete-work-odbc"></a>레코드 집합: AddNew, Edit 및 Delete의 작동 방식(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

이 항목에서는 `AddNew`클래스의 `CRecordset` `Delete` 의 및 `Edit`멤버 함수가 작동하는 방법을 설명합니다. 다음 내용을 다룹니다.

- [레코드 추가 작동 방식](#_core_adding_a_record)

- [추가된 레코드의 가시성](#_core_visibility_of_added_records)

- [레코드 편집 작동 방식](#_core_editing_an_existing_record)

- [레코드 삭제 작동 방식](#_core_deleting_a_record)

> [!NOTE]
> 이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다. 대량 행 가져오기를 사용하는 경우 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

또한 업데이트 작업에서 RFX의 해당 역할을 설명하는 [레코드 필드 교환: RFX 작동 방식을](../../data/odbc/record-field-exchange-how-rfx-works.md)읽을 수 있습니다.

## <a name="adding-a-record"></a><a name="_core_adding_a_record"></a>레코드 추가

레코드 집합에 새 레코드를 추가하려면 레코드 집합의 [AddNew](../../mfc/reference/crecordset-class.md#addnew) 멤버 함수를 호출하고, 새 레코드의 필드 데이터 멤버 값을 설정하고, [Update](../../mfc/reference/crecordset-class.md#update) 멤버 함수를 호출하여 데이터 원본에 레코드를 작성합니다.

호출의 `AddNew`전제 조건으로 레코드 집합이 읽기 전용으로 열리지 않아야 합니다. `CanUpdate` 및 `CanAppend` 멤버 함수를 사용하면 이러한 조건을 확인할 수 있습니다.

전화 `AddNew`할 때 :

- 편집 버퍼의 레코드가 저장되므로 작업이 취소된 경우 해당 내용을 복원할 수 있습니다.

- 필드 데이터 멤버에 플래그가 지정되므로 나중에 변경 내용을 검색할 수 있습니다. 필드 데이터 멤버도 변경되지 않음으로 표시되고 Null로 설정됩니다.

호출 `AddNew`한 후 편집 버퍼는 값으로 채울 준비가된 새 빈 레코드를 나타냅니다. 이렇게 하려면 값을 할당하여 수동으로 설정합니다. 필드에 대한 실제 데이터 값을 지정하는 대신 `SetFieldNull` 호출하여 Null 값을 지정할 수 있습니다.

변경 내용을 커밋하려면 `Update`을 호출합니다. 새 레코드를 호출할 `Update` 때:

- ODBC 드라이버가 `::SQLSetPos` ODBC API 기능을 지원하는 경우 MFC는 이 함수를 사용하여 데이터 원본에 레코드를 추가합니다. 을 `::SQLSetPos`사용하면 SQL 문을 생성하고 처리할 필요가 없으므로 MFC에서 레코드를 보다 효율적으로 추가할 수 있습니다.

- 사용할 `::SQLSetPos` 수 없는 경우 MFC는 다음을 수행합니다.

   1. 변경 내용이 검색되지 `Update` 않으면 아무 것도 수행하지 않고 0을 반환합니다.

   1. 변경 사항이 있는 `Update` 경우 SQL **INSERT** 문을 생성합니다. 모든 더러운 필드 데이터 멤버로 표시되는 열은 **INSERT** 문에 나열됩니다. 열을 포함하도록 강제하려면 [SetFieldDirty](../../mfc/reference/crecordset-class.md#setfielddirty) 멤버 함수를 호출합니다.

        ```cpp
        SetFieldDirty( &m_dataMember, TRUE );
        ```

   1. `Update`새 레코드를 커밋합니다 - **INSERT** 문이 실행되고 트랜잭션이 진행되지 않는 한 레코드가 데이터 원본의 테이블에 커밋됩니다(스냅샷이 아닌 경우 레코드 집합).

   1. 저장된 레코드가 편집 버퍼로 복원됩니다. INSERT 문이 성공적으로 실행되었는지 여부에 관계없이 `AddNew` **호출** 전에 현재 의 레코드가 다시 최신 상태로 표시됩니다.

   > [!TIP]
   > 새 레코드를 완전히 제어하려면 값이 있는 필드의 값을 설정한 다음 필드와 TRUE 매개 변수(기본값)를 `SetFieldNull` 호출하여 Null로 유지되는 필드를 명시적으로 설정합니다. 필드가 데이터 원본에 기록되지 않도록 하려면 필드와 `SetFieldDirty` FALSE 매개 변수에 대한 포인터를 사용하여 호출하고 필드의 값을 수정하지 마십시오. 필드가 Null이 될 수 있는지 `IsFieldNullable`여부를 확인하려면 을 호출합니다.

   > [!TIP]
   > 레코드 집합 데이터 멤버가 값을 변경하는 시기를 감지하기 위해 MFC는 레코드 집합에 저장할 수 있는 각 데이터 형식에 적합한 PSEUDO_NULL 값을 사용합니다. 필드를 PSEUDO_NULL 값으로 명시적으로 설정해야 하고 필드가 이미 Null로 표시되어야 `SetFieldNull`하는 경우 첫 번째 매개 변수의 필드 주소를 전달하고 두 번째 매개 변수에서 FALSE를 호출해야 합니다.

## <a name="visibility-of-added-records"></a><a name="_core_visibility_of_added_records"></a>추가된 레코드의 가시성

추가된 레코드가 레코드 집합에 언제 표시되나요? 추가된 레코드는 다음 두 가지에 따라 표시되고 표시되지 않는 경우도 있습니다.

- 드라이버 파트너가 할 수 있는 것.

- 프레임워크가 활용할 수 있는 내용입니다.

ODBC 드라이버가 `::SQLSetPos` ODBC API 기능을 지원하는 경우 MFC는 이 함수를 사용하여 레코드를 추가합니다. 을 `::SQLSetPos`사용하여 추가된 레코드는 모든 업데이터 MFC 레코드 집합에 표시됩니다. 함수에 대한 지원이 없으면 추가된 레코드가 `Requery` 표시되지 않으며 호출하여 함수를 보아야 합니다. 사용도 `::SQLSetPos` 더 효율적입니다.

## <a name="editing-an-existing-record"></a><a name="_core_editing_an_existing_record"></a>기존 레코드 편집

레코드 집합에서 기존 레코드를 편집하려면 레코드로 스크롤하고, 레코드 집합의 [편집](../../mfc/reference/crecordset-class.md#edit) 멤버 함수를 호출하고, 새 레코드의 필드 데이터 멤버 값을 설정하고, [Update](../../mfc/reference/crecordset-class.md#update) 멤버 함수를 호출하여 변경된 레코드를 데이터 원본에 작성합니다.

호출의 `Edit`전제 조건으로 레코드 집합은 업데이터 및 레코드에 있어야 합니다. `CanUpdate` 및 `IsDeleted` 멤버 함수를 사용하면 이러한 조건을 확인할 수 있습니다. 현재 레코드도 이미 삭제되지 않아야 하며 레코드 집합에 레코드가 `IsBOF` 있어야 `IsEOF` 합니다(모두 및 반환 0).

호출할 `Edit`때 편집 버퍼의 레코드(현재 레코드)가 저장됩니다. 저장된 레코드의 값은 나중에 필드가 변경되었는지 여부를 검색하는 데 사용됩니다.

호출한 `Edit`후에도 편집 버퍼는 여전히 현재 레코드를 나타내지만 이제 필드 데이터 멤버에 대한 변경 내용을 수락할 준비가 되었습니다. 레코드를 변경하려면 편집하려는 필드 데이터 멤버의 값을 수동으로 설정합니다. 필드에 대한 실제 데이터 값을 지정하는 대신 `SetFieldNull` 호출하여 Null 값을 지정할 수 있습니다. 변경 내용을 커밋하려면 을 호출하십시오. `Update`

> [!TIP]
> 나가기 `AddNew` 또는 `Edit` 모드를 얻으려면 `Move` 매개 변수 *AFX_MOVE_REFRESH*호출합니다.

호출의 `Update`전제 조건으로 레코드 집합이 비어 있어야 하며 현재 레코드가 삭제되지 않아야 합니다. `IsBOF`및 `IsEOF` `IsDeleted` 모두 0을 반환해야 합니다.

편집된 `Update` 레코드를 호출할 때:

- ODBC 드라이버가 `::SQLSetPos` ODBC API 기능을 지원하는 경우 MFC는 이 함수를 사용하여 데이터 원본의 레코드를 업데이트합니다. 을 `::SQLSetPos`사용하면 드라이버가 편집 버퍼를 서버의 해당 레코드와 비교하여 둘이 다른 경우 서버의 레코드를 업데이트합니다. 을 `::SQLSetPos`사용하면 SQL 문을 생성하고 처리할 필요가 없으므로 레코드를 보다 효율적으로 업데이트할 수 있습니다.

   \- 또는-

- 사용할 `::SQLSetPos` 수 없는 경우 MFC는 다음을 수행합니다.

   1. 변경 사항이 없는 경우 `Update` 아무 것도 수행하지 않고 0을 반환합니다.

   1. 변경 사항이 있는 `Update` 경우 SQL **UPDATE** 문을 생성합니다. **UPDATE** 문에 나열된 열은 변경된 필드 데이터 멤버를 기반으로 합니다.

   1. `Update`변경 내용을 커밋 - **UPDATE** 문을 실행하고 레코드는 데이터 원본에서 변경되지만 트랜잭션이 진행 중인 경우 커밋되지 않습니다(트랜잭션이 업데이트에 미치는 영향에 대한 자세한 내용은 [레코드 집합(ODBC)에서 트랜잭션 수행](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md) 참조). ODBC는 레코드의 복사본을 유지하며, 이 복사본도 변경됩니다.

   1. 에 대 `AddNew`한 `Edit` 프로세스와 달리 프로세스는 저장된 레코드를 복원 하지 않습니다. 편집된 레코드는 현재 레코드로 유지됩니다.

   > [!CAUTION]
   > 호출하여 `Update`레코드 집합을 업데이트할 때 레코드 집합에 테이블의 기본 키를 구성하는 모든 열(또는 테이블의 고유한 인덱스의 모든 열 또는 행을 고유하게 식별하기에 충분한 열)이 포함되어 있는지 주의하십시오. 경우에 따라 프레임워크는 레코드 집합에서 선택한 열만 사용하여 업데이트할 테이블의 레코드를 식별할 수 있습니다. 필요한 모든 열이 없으면 테이블에서 여러 레코드가 업데이트될 수 있습니다. 이 경우 프레임 워크는 호출 `Update`할 때 예외를 throw합니다.

   > [!TIP]
   > 이전에 함수를 호출하거나 `AddNew` `Edit` 호출한 후 호출하기 `Update`전에 편집 버퍼가 저장된 레코드로 새로 고쳐져 진행 중인 새 레코드 또는 편집된 레코드를 대체합니다. 이 동작은 진행 중인 기록의 `AddNew` `Edit` 결함이 있다고 판단되면 단순히 호출하거나 `Edit` `AddNew` 다시 호출하는 방법을 제공합니다.

## <a name="deleting-a-record"></a><a name="_core_deleting_a_record"></a>레코드 삭제

레코드 집합에서 레코드를 삭제하려면 레코드로 스크롤하고 레코드 집합의 [멤버 삭제](../../mfc/reference/crecordset-class.md#delete) 함수를 호출해야 합니다. 와 `AddNew` `Edit`달리 `Delete` `Update`에 대한 일치하는 호출이 필요하지 않습니다.

호출의 `Delete`전제 조건으로 레코드 집합은 업데이터 처리용이어야 하며 레코드에 있어야 합니다. 의 `CanUpdate` `IsBOF`에서 `IsEOF`및 `IsDeleted` 멤버 함수를 사용하면 이러한 조건을 확인할 수 있습니다.

전화 `Delete`할 때 :

- ODBC 드라이버가 `::SQLSetPos` ODBC API 기능을 지원하는 경우 MFC는 이 기능을 사용하여 데이터 원본의 레코드를 삭제합니다. 일반적으로 `::SQLSetPos` 사용하는 것이 SQL을 사용하는 것보다 더 효율적입니다.

   \- 또는-

- 사용할 `::SQLSetPos` 수 없는 경우 MFC는 다음을 수행합니다.

   1. 편집 버퍼의 현재 레코드가 에서와 `AddNew` `Edit`같이 백업되지 않습니다.

   1. `Delete`레코드를 제거하는 SQL **DELETE** 문을 생성합니다.

      편집 버퍼의 현재 레코드는 에 `AddNew` 저장되지 `Edit`않습니다.

   1. `Delete`삭제를 커밋합니다 . **DELETE** 레코드가 데이터 원본에서 삭제된 것으로 표시되고 레코드가 스냅숏인 경우 ODBC에서 삭제됩니다.

   1. 삭제된 레코드의 값은 레코드 집합의 필드 데이터 멤버에 남아 있지만 필드 데이터 멤버는 `IsDeleted` Null로 표시되고 레코드 집합의 멤버 함수는 0이 아닌 값을 반환합니다.

   > [!NOTE]
   > 레코드를 삭제한 후 다른 레코드로 스크롤하여 편집 버퍼를 새 레코드의 데이터로 다시 채워야 합니다. 다시 호출하거나 `Delete` 호출하는 `Edit`오류입니다.

업데이트 작업에 사용되는 SQL 문에 대한 자세한 내용은 [SQL](../../data/odbc/sql.md)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 업데이트에 대한 추가 정보(ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md)<br/>
[레코드 필드 교환(RFX)](../../data/odbc/record-field-exchange-rfx.md)
