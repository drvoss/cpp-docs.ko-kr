---
title: '레코드 집합: 대량 레코드 페치(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- bulk row fetching, implementing
- ODBC recordsets, bulk row fetching
- bulk record field exchange
- bulk row fetching
- bulk RFX functions
- recordsets, bulk row fetching
- DoBulkFieldExchange method
- fetching ODBC records in bulk
- RFX (ODBC), bulk
- rowsets, bulk row fetching
- RFX (ODBC), bulk row fetching
ms.assetid: 20d10fe9-c58a-414a-b675-cdf9aa283e4f
ms.openlocfilehash: ec4d83481f6335d4c40ffb8f004b617f2ee09c62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367022"
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>레코드 집합: 대량 레코드 페치(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

클래스는 `CRecordset` 대량 행 가져오기에 대한 지원을 제공하므로 데이터 원본에서 한 번에 하나의 레코드를 검색하는 대신 단일 가져오기 중에 여러 레코드를 한 번에 검색할 수 있습니다. 파생 `CRecordset` 클래스에서만 대량 행 페칭을 구현할 수 있습니다. 데이터 원본에서 레코드 집합 개체로 데이터를 전송하는 프로세스를 대량 레코드 필드 교환(대량 RFX)이라고 합니다. `CRecordset`-derived 클래스에서 대량 행 페칭을 사용하지 않는 경우 RFX(레코드 필드 교환)를 통해 데이터가 전송됩니다. 자세한 내용은 [RFX(레코드 필드 교환)를](../../data/odbc/record-field-exchange-rfx.md)참조하십시오.

이 토픽에서는 다음 내용을 설명합니다.

- [CRecordset이 대량 행 가져오기를 지원하는 방법.](#_core_how_crecordset_supports_bulk_row_fetching)

- [벌크 행 페칭을 사용할 때 몇 가지 특별한 고려 사항](#_core_special_considerations).

- [대량 레코드 필드 교환을 구현 하는 방법](#_core_how_to_implement_bulk_record_field_exchange).

## <a name="how-crecordset-supports-bulk-row-fetching"></a><a name="_core_how_crecordset_supports_bulk_row_fetching"></a>CRecordset이 대량 행 가져오기를 지원하는 방법

레코드 집합 개체를 열기 전에 멤버 함수를 `SetRowsetSize` 통해 행 집합 크기를 정의할 수 있습니다. 행 집합 크기는 단일 가져오기 중에 검색해야 하는 레코드 수를 지정합니다. 벌크 행 가져오기가 구현되면 기본 행 집합 크기는 25입니다. 대량 행 가져오기가 구현되지 않으면 행 집합 크기는 1로 고정된 상태로 유지됩니다.

행 집합 크기를 초기화한 후 [Open](../../mfc/reference/crecordset-class.md#open) 멤버 함수를 호출합니다. 여기서 대량 행 `CRecordset::useMultiRowFetch` 가져오기를 구현하기 위해 *dwOptions* 매개 변수의 옵션을 지정해야 합니다. 옵션을 추가로 `CRecordset::userAllocMultiRowBuffers` 설정할 수 있습니다. 대량 레코드 필드 교환 메커니즘은 배열을 사용하여 가져오기 중에 검색된 여러 데이터 행을 저장합니다. 이러한 저장소 버퍼는 프레임워크에서 자동으로 할당하거나 수동으로 할당할 수 있습니다. `CRecordset::userAllocMultiRowBuffers` 옵션을 지정하면 할당을 수행할 수 있습니다.

다음 표에는 대량 행 가져오기를 지원하기 `CRecordset` 위해 제공된 멤버 함수가 나열됩니다.

|멤버 함수|Description|
|---------------------|-----------------|
|[검사행집합오류](../../mfc/reference/crecordset-class.md#checkrowseterror)|페칭 하는 동안 발생 하는 모든 오류를 처리 하는 가상 함수입니다.|
|[도벌필드익스체인지](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|대량 레코드 필드 교환을 구현합니다. 데이터 원본에서 레코드 집합 개체로 여러 데이터 행을 전송하기 위해 자동으로 호출됩니다.|
|[겟로우셋사이즈](../../mfc/reference/crecordset-class.md#getrowsetsize)|행 집합 크기에 대한 현재 설정을 검색합니다.|
|[겟로우스페치](../../mfc/reference/crecordset-class.md#getrowsfetched)|지정된 가져오기 후에 실제로 검색된 행 수를 알려줍니다. 대부분의 경우 불완전한 행 집합을 가져오지 않는 한 행 집합 크기입니다.|
|[겟로우 상태](../../mfc/reference/crecordset-class.md#getrowstatus)|행 집합 내의 특정 행에 대한 가져오기 상태를 반환합니다.|
|[새로 고침행 세트](../../mfc/reference/crecordset-class.md#refreshrowset)|행 집합 내에서 특정 행의 데이터 및 상태를 새로 고칩니다.|
|[세트Rowset커서 포지션](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|커서를 행 집합 내의 특정 행으로 이동합니다.|
|[세트로셋크기](../../mfc/reference/crecordset-class.md#setrowsetsize)|행 집합 크기에 대한 설정을 지정된 값으로 변경하는 가상 함수입니다.|

## <a name="special-considerations"></a><a name="_core_special_considerations"></a>특별 고려 사항

대량 행 페칭은 성능 향상이지만 특정 기능은 다르게 작동합니다. 대량 행 가져오기를 구현하기 전에 다음사항을 고려하십시오.

- 프레임워크는 자동으로 멤버 `DoBulkFieldExchange` 함수를 호출하여 데이터 원본에서 레코드 집합 개체로 데이터를 전송합니다. 그러나 데이터는 레코드 집합에서 데이터 원본으로 다시 전송되지 않습니다. `AddNew` `Edit`을 `Delete`호출하거나 `Update` 멤버 함수를 호출하면 어설션이 실패합니다. 현재 `CRecordset` 대량 데이터 행을 업데이트하는 메커니즘을 제공하지는 않지만 ODBC API 함수를 `SQLSetPos`사용하여 사용자 고유의 함수를 작성할 수 있습니다. 자세한 `SQLSetPos`내용은 MSDN *설명서의 ODBC SDK 프로그래머 참조를* 참조하십시오.

- 멤버는 `IsDeleted` `IsFieldDirty` `IsFieldNull` `IsFieldNullable`및 대량 행 가져오기를 구현하는 레코드 집합에서 사용할 `SetFieldNull` 수 `SetFieldDirty`없습니다. `GetRowStatus` 그러나 `IsDeleted`을 대신 호출할 `GetODBCFieldInfo` `IsFieldNullable`수 있습니다.

- 연산은 `Move` 레코드 집합을 행 집합별로 재배치합니다. 예를 들어 초기 행 집합 크기가 10인 레코드가 100개인 레코드집합을 여는 가정입니다. `Open`현재 레코드가 행 1에 위치하여 행 1에서 10까지의 행을 가져옵니다. 다음 행이 `MoveNext` 아닌 다음 행 집합을 가져오는 호출입니다. 이 행 집합은 행 11부터 20까지의 행으로 구성되며 현재 레코드는 행 11에 배치됩니다. `MoveNext` 대량 행 `Move( 1 )` 가져오기가 구현될 때와 동일하지 않습니다. `Move( 1 )`현재 레코드에서 1행을 시작하는 행 집합을 가져옵니다. 이 예제에서는 `Move( 1 )` 호출 `Open` 후 호출이 행 2에서 11까지로 구성된 행 집합을 가져오고 현재 레코드는 행 2에 배치됩니다. 자세한 내용은 멤버 [이동](../../mfc/reference/crecordset-class.md#move) 기능을 참조하십시오.

- 레코드 필드 교환과 달리 마법사는 대량 레코드 필드 교환을 지원하지 않습니다. 즉, 필드 데이터 멤버를 수동으로 선언하고 대량 `DoBulkFieldExchange` RFX 함수에 대한 호출을 작성하여 수동으로 재정의해야 합니다. 자세한 내용은 *클래스 라이브러리 참조의* [레코드 필드 교환 함수를](../../mfc/reference/record-field-exchange-functions.md) 참조하십시오.

## <a name="how-to-implement-bulk-record-field-exchange"></a><a name="_core_how_to_implement_bulk_record_field_exchange"></a>대량 레코드 필드 교환을 구현하는 방법

대량 레코드 필드 교환은 데이터 원본에서 레코드 집합 개체로 데이터 행 집합을 전송합니다. 대량 RFX 함수는 배열을 사용하여 이 데이터와 배열을 사용하여 행 집합에 각 데이터 항목의 길이를 저장합니다. 클래스 정의에서 필드 데이터 멤버를 데이터 배열에 액세스하는 포인터로 정의해야 합니다. 또한 길이 배열에 액세스하려면 포인터 집합을 정의해야 합니다. 모든 매개 변수 데이터 멤버는 포인터로 선언해서는 안 됩니다. 대량 레코드 필드 교환을 사용할 때 매개 변수 데이터 멤버를 선언하는 것은 레코드 필드 교환을 사용할 때 선언하는 것과 같습니다. 다음 코드는 간단한 예제를 보여 주며 다음과 같은 간단한 예제를 보여 주며 다음과 같은 간단한 예제를 보여 주며 다음과

```cpp
class MultiRowSet : public CRecordset
{
public:
   // Field/Param Data
      // field data members
      long* m_rgID;
      LPSTR m_rgName;

      // pointers for the lengths
      // of the field data
      long* m_rgIDLengths;
      long* m_rgNameLengths;

      // input parameter data member
      CString m_strNameParam;

   .
   .
   .
}
```

이러한 저장소 버퍼를 수동으로 할당하거나 프레임워크에서 할당을 수행하게 할 수 있습니다. 버퍼를 직접 할당하려면 `CRecordset::userAllocMultiRowBuffers` `Open` 멤버 함수에서 *dwOptions* 매개 변수 옵션을 지정해야 합니다. 배열의 크기를 행 집합 크기와 최소한 같아야 합니다. 프레임워크가 할당을 수행하도록 하려면 NULL에 대한 포인터를 초기화해야 합니다. 이 작업은 일반적으로 레코드 집합 개체의 생성자에서 수행됩니다.

```cpp
MultiRowSet::MultiRowSet( CDatabase* pDB )
   : CRecordset( pDB )
{
   m_rgID = NULL;
   m_rgName = NULL;
   m_rgIDLengths = NULL;
   m_rgNameLengths = NULL;
   m_strNameParam = "";

   m_nFields = 2;
   m_nParams = 1;

   .
   .
   .
}
```

마지막으로 멤버 함수를 `DoBulkFieldExchange` 재정의해야 합니다. 필드 데이터 멤버의 경우 대량 RFX 함수를 호출합니다. 모든 매개 변수 데이터 멤버에 대해 RFX 함수를 호출합니다. SQL 문 또는 저장 프로시저를 `Open`전달하여 레코드 집합을 연 경우 대량 RFX 호출을 하는 순서는 레코드 집합의 열 순서와 일치해야 합니다. 마찬가지로 RFX 매개 변수에 대 한 호출 순서는 SQL 문 또는 저장 프로시저의 매개 변수 순서와 일치 해야 합니다.

```cpp
void MultiRowSet::DoBulkFieldExchange( CFieldExchange* pFX )
{
   // call the Bulk RFX functions
   // for field data members
   pFX->SetFieldType( CFieldExchange::outputColumn );
   RFX_Long_Bulk( pFX, _T( "[colRecID]" ),
                  &m_rgID, &m_rgIDLengths );
   RFX_Text_Bulk( pFX, _T( "[colName]" ),
                  &m_rgName, &m_rgNameLengths, 30 );

   // call the RFX functions for
   // for parameter data members
   pFX->SetFieldType( CFieldExchange::inputParam );
   RFX_Text( pFX, "NameParam", m_strNameParam );
}
```

> [!NOTE]
> 파생 `CRecordset` 클래스가 `Close` 범위를 벗어나기 전에 멤버 함수를 호출해야 합니다. 이렇게 하면 프레임워크에서 할당된 모든 메모리가 해제됩니다. 대량 행 가져오기를 구현했는지 `Close`여부에 관계없이 항상 명시적으로 호출하는 것이 좋습니다.

RFX(레코드 필드 교환)에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식을](../../data/odbc/record-field-exchange-how-rfx-works.md)참조하십시오. 매개 변수 사용에 대한 자세한 내용은 [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) 및 [레코드 집합: 레코드 집합(ODBC) 매개 변수화를](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[C레코드 집합::m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)<br/>
[C레코드 집합::m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)
