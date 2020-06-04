---
title: '레코드 집합: 레코드 추가, 업데이트 및 삭제(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- records [C++], deleting
- AddNew method
- ODBC recordsets [C++], deleting records
- data in recordsets [C++]
- record editing [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: 760c8889-bec4-482b-a8f2-319792a6af98
ms.openlocfilehash: 628ffb2feee385a4114b0dbea074f81678c529d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367101"
---
# <a name="recordset-adding-updating-and-deleting-records-odbc"></a>레코드 집합: 레코드 추가, 업데이트 및 삭제(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

> [!NOTE]
> 이제 레코드를 보다 효율적으로 대량으로 추가할 수 있습니다. 자세한 내용은 [레코드 집합: 대량(ODBC)으로 레코드 추가를](../../data/odbc/recordset-adding-records-in-bulk-odbc.md)참조하십시오.

> [!NOTE]
> 이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다. 대량 행 가져오기를 사용하는 경우 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

업데이트 가능한 스냅샷 및 다이너셋을 사용하면 레코드를 추가, 편집(업데이트) 및 삭제할 수 있습니다. 이 토픽에서는 다음 내용을 설명합니다.

- [레코드 집합이 업데이터인지 확인하는 방법](#_core_determining_whether_your_recordset_is_updatable).

- [새 레코드를 추가하는 방법](#_core_adding_a_record_to_a_recordset).

- [기존 레코드를 편집하는 방법](#_core_editing_a_record_in_a_recordset).

- [레코드를 삭제하는 방법](#_core_deleting_a_record_from_a_recordset).

업데이트수행 방법 및 업데이트가 다른 사용자에게 표시되는 방식에 대한 자세한 내용은 [레코드 집합: 레코드 집합 업데이트 레코드(ODBC) 를](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)참조하십시오. 일반적으로 레코드를 추가, 편집 또는 삭제하면 레코드 집합이 데이터 원본을 즉시 변경합니다. 대신 관련 업데이트 그룹을 트랜잭션으로 일괄 처리할 수 있습니다. 트랜잭션이 진행 중인 경우 트랜잭션을 커밋할 때까지 업데이트가 최종으로 지정되지 않습니다. 이렇게 하면 변경 내용을 되돌리거나 롤백할 수 있습니다. 트랜잭션에 대한 자세한 내용은 [트랜잭션(ODBC)을](../../data/odbc/transaction-odbc.md)참조하십시오.

다음 표에는 업데이트 특성이 다른 레코드 집합에 사용할 수 있는 옵션이 요약되어 있습니다.

### <a name="recordset-readupdate-options"></a>레코드 집합 읽기/업데이트 옵션

|Type|읽기|레코드 편집|레코드 삭제|새 추가(추가)|
|----------|----------|-----------------|-------------------|------------------------|
|읽기 전용|Y|N|N|N|
|부속 전용|Y|N|N|Y|
|완전 업데이터|Y|Y|Y|Y|

## <a name="determining-whether-your-recordset-is-updateable"></a><a name="_core_determining_whether_your_recordset_is_updatable"></a>레코드 집합을 업데이트할 수 있는지 여부 확인

데이터 원본을 업데이트할 수 있고 업데이트 가능한 레코드 집합을 연 경우 레코드 집합 개체를 업데이트할 수 있습니다. 업데이트 가능성은 사용하는 SQL 문, ODBC 드라이버의 기능 및 ODBC 커서 라이브러리가 메모리에 있는지 여부에 따라 달라집니다. 읽기 전용 레코드 집합 또는 데이터 원본은 업데이트할 수 없습니다.

#### <a name="to-determine-whether-your-recordset-is-updatable"></a>레코드 집합이 업데이터 인지 확인하려면

1. 레코드 집합 개체의 [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) 멤버 함수를 호출합니다.

   `CanUpdate`은 레코드 집합을 업데이트할 수 있는 경우 비영값을 반환합니다.

기본적으로 레코드 집합은 완전히 업데이트 할 `AddNew`수 `Edit`있습니다 `Delete` (을 수행할 수 있습니다 및 작업). 그러나 업데이트 가능한 레코드 집합을 여는 [부록만](../../mfc/reference/crecordset-class.md#open) 옵션을 사용할 수도 있습니다. 이 방법으로 열린 레코드 집합은 `AddNew`을 통해 새 레코드를 추가할 수만 허용합니다. 기존 레코드를 편집하거나 삭제할 수 없습니다. [CanAppend](../../mfc/reference/crecordset-class.md#canappend) 멤버 함수를 호출하여 추가할 때만 레코드 집합이 열려 있는지 여부를 테스트할 수 있습니다. `CanAppend`레코드 집합이 완전히 업데이트 가능하거나 부가에 의한 경우에만 열려 있는 경우 비영값을 반환합니다.

다음 코드는 다음과 같은 `CanUpdate` `rsStudentSet`레코드 집합 개체에 사용할 수 있는 방법을 보여 주며 다음과 같은

```cpp
if( !rsStudentSet.Open( ) )
    return FALSE;
if( !rsStudentSet.CanUpdate( ) )
{
    AfxMessageBox( "Unable to update the Student recordset." );
    return;
}
```

> [!CAUTION]
> 호출하여 `Update`레코드 집합을 업데이트할 때 레코드 집합에 테이블의 기본 키(또는 테이블의 고유한 인덱스의 모든 열)를 구성하는 모든 열이 포함되어 있는지 주의하십시오. 경우에 따라 프레임워크는 레코드 집합에서 선택한 열만 사용하여 업데이트할 테이블의 레코드를 식별할 수 있습니다. 필요한 모든 열이 없으면 테이블에서 여러 레코드가 업데이트되어 테이블의 참조 무결성이 손상될 수 있습니다. 이 경우 프레임 워크는 호출 `Update`할 때 예외를 throw합니다.

## <a name="adding-a-record-to-a-recordset"></a><a name="_core_adding_a_record_to_a_recordset"></a>레코드 집합에 레코드 추가

[CanAppend](../../mfc/reference/crecordset-class.md#canappend) 멤버 함수가 영하지 않은 값을 반환하는 경우 레코드 집합에 새 레코드를 추가할 수 있습니다.

#### <a name="to-add-a-new-record-to-a-recordset"></a>레코드 집합에 새 레코드를 추가하려면

1. 레코드 집합을 더할 수 있는지 확인합니다.

1. 레코드 집합 개체의 [AddNew](../../mfc/reference/crecordset-class.md#addnew) 멤버 함수를 호출합니다.

   `AddNew`레코드 집합이 편집 버퍼역할을 하도록 준비합니다. 모든 필드 데이터 멤버는 Null 라는 특수 값으로 설정 되 고 변경 된 (더러운) 값만 [Update를](../../mfc/reference/crecordset-class.md#update)호출할 때 데이터 원본에 기록 되도록 변경 되지 않은 것으로 표시 됩니다.

1. 새 레코드의 필드 데이터 멤버 값을 설정합니다.

   필드 데이터 멤버에 값을 할당합니다. 할당하지 않은 것은 데이터 원본에 기록되지 않습니다.

1. 레코드 집합 개체의 `Update` 멤버 함수를 호출합니다.

   `Update`데이터 원본에 새 레코드를 작성하여 추가를 완료합니다. 호출하지 `Update`않을 경우 발생하는 방법에 대한 자세한 내용은 [레코드 집합: 레코드 집합 업데이트 레코드(ODBC)를](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)참조합니다.

레코드 추가 방법 및 추가 된 레코드가 레코드 집합에 표시되는 시기에 대한 자세한 내용은 [레코드 집합: AddNew, 편집 및 ODBC(작업 삭제)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)을 참조하십시오.

다음 예제에서는 새 레코드를 추가하는 방법을 보여 주며 있습니다.

```cpp
if( !rsStudent.Open( ) )
    return FALSE;
if( !rsStudent.CanAppend( ) )
    return FALSE;                      // no field values were set
rsStudent.AddNew( );
rsStudent.m_strName = strName;
rsStudent.m_strCity = strCity;
rsStudent.m_strStreet = strStreet;
if( !rsStudent.Update( ) )
{
    AfxMessageBox( "Record not added; no field values were set." );
    return FALSE;
}
```

> [!TIP]
> `AddNew` `Edit` 또는 통화를 취소하려면 *AFX_MOVE_REFRESH* 매개 `AddNew` 변수를 사용하여 다른 호출을 하거나 `Edit` 호출하면 `Move` 됩니다. 데이터 멤버가 이전 값으로 재설정되고 여전히 `Edit` `Add` 또는 모드에 있습니다.

## <a name="editing-a-record-in-a-recordset"></a><a name="_core_editing_a_record_in_a_recordset"></a>레코드 집합에서 레코드 편집

레코드 집합의 [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) 멤버 함수가 영하지 않은 값을 반환하는 경우 기존 레코드를 편집할 수 있습니다.

#### <a name="to-edit-an-existing-record-in-a-recordset"></a>레코드 집합에서 기존 레코드를 편집하려면

1. 레코드 집합을 업데이트할 수 있는지 확인합니다.

1. 업데이트할 레코드로 스크롤합니다.

1. 레코드 집합 개체의 [멤버 편집](../../mfc/reference/crecordset-class.md#edit) 함수를 호출합니다.

   `Edit`레코드 집합이 편집 버퍼역할을 하도록 준비합니다. 레코드 집합이 나중에 변경되었는지 여부를 알 수 있도록 모든 필드 데이터 멤버가 표시됩니다. 변경된 필드 데이터 멤버에 대한 새 값은 [Update](../../mfc/reference/crecordset-class.md#update)를 호출할 때 데이터 원본에 기록됩니다.

1. 새 레코드의 필드 데이터 멤버 값을 설정합니다.

   필드 데이터 멤버에 값을 할당합니다. 값을 할당하지 않은 값은 변경되지 않습니다.

1. 레코드 집합 개체의 `Update` 멤버 함수를 호출합니다.

   `Update`변경된 레코드를 데이터 원본에 작성하여 편집을 완료합니다. 호출하지 `Update`않을 경우 발생하는 방법에 대한 자세한 내용은 [레코드 집합: 레코드 집합 업데이트 레코드(ODBC)를](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)참조합니다.

레코드를 편집한 후 편집된 레코드는 현재 레코드로 유지됩니다.

다음 예제에서는 `Edit` 작업을 보여 주고 있습니다. 사용자가 편집하려는 레코드로 이동했다고 가정합니다.

```cpp
rsStudent.Edit( );
rsStudent.m_strStreet = strNewStreet;
rsStudent.m_strCity = strNewCity;
rsStudent.m_strState = strNewState;
rsStudent.m_strPostalCode = strNewPostalCode;
if( !rsStudent.Update( ) )
{
    AfxMessageBox( "Record not updated; no field values were set." );
    return FALSE;
}
```

> [!TIP]
> `AddNew` `Edit` 또는 통화를 취소하려면 *AFX_MOVE_REFRESH* 매개 `AddNew` 변수를 사용하여 다른 호출을 하거나 `Edit` 호출하면 `Move` 됩니다. 데이터 멤버가 이전 값으로 재설정되고 여전히 `Edit` `Add` 또는 모드에 있습니다.

## <a name="deleting-a-record-from-a-recordset"></a><a name="_core_deleting_a_record_from_a_recordset"></a>레코드 집합에서 레코드 삭제

레코드 집합의 [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) 멤버 함수가 영하지 않은 값을 반환하는 경우 레코드를 삭제할 수 있습니다.

#### <a name="to-delete-a-record"></a>레코드를 삭제하려면

1. 레코드 집합을 업데이트할 수 있는지 확인합니다.

1. 업데이트할 레코드로 스크롤합니다.

1. 레코드 집합 개체의 [멤버 삭제](../../mfc/reference/crecordset-class.md#delete) 함수를 호출합니다.

   `Delete`즉시 레코드 집합과 데이터 원본 모두에서 레코드를 삭제된 것으로 표시합니다.

   및 `AddNew` `Edit`와 `Delete` 는 `Update` 달리 해당 호출이 없습니다.

1. 다른 레코드로 스크롤합니다.

   > [!NOTE]
   >  레코드 집합을 이동할 때 삭제된 레코드를 건너뛸 수 없습니다. 자세한 내용은 [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) 멤버 함수를 참조하십시오.

다음 예제에서는 `Delete` 작업을 보여 주고 있습니다. 사용자가 삭제하려는 레코드로 이동했다고 가정합니다. 호출된 후에는 `Delete` 새 레코드로 이동하는 것이 중요합니다.

```
rsStudent.Delete( );
rsStudent.MoveNext( );
```

`AddNew` `Edit`의 `Delete` 효과에 대한 자세한 내용은 [레코드 집합: 레코드 집합 업데이트 레코드(ODBC)를](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)참조하세요.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 레코드 잠금(ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
