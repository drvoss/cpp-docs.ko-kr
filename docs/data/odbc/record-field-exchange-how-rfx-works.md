---
title: '레코드 필드 교환: RFX 작동 방식'
ms.date: 11/04/2016
helpviewer_keywords:
- record editing [C++], using RFX
- RFX (ODBC) [C++], updating data in recordsets
- scrolling [C++]
- ODBC [C++], RFX
- data binding [C++], DFX
- scrolling [C++], RFX
- RFX (ODBC) [C++], binding fields and parameters
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
ms.openlocfilehash: 903acf4f55fb2708f4998a2babf3f143c895429b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367169"
---
# <a name="record-field-exchange-how-rfx-works"></a>레코드 필드 교환: RFX 작동 방식

이 항목에서는 RFX 프로세스에 대해 설명합니다. 다음은 고급 항목입니다.

- [RFX 및 레코드 집합](#_core_rfx_and_the_recordset)

- [RFX 프로세스](#_core_the_record_field_exchange_process)

> [!NOTE]
> 이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 클래스에 적용됩니다. 대량 행 페치를 사용하는 경우 대량 레코드 필드 교환(대량 RFX)이 구현됩니다. 대량 RFX는 RFX와 비슷합니다. 차이점을 이해하려면 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

## <a name="rfx-and-the-recordset"></a><a name="_core_rfx_and_the_recordset"></a>RFX 및 레코드 집합

레코드 집합 개체의 필드 데이터 멤버는 함께 수행되어 하나의 레코드의 선택한 열을 포함하는 편집 버퍼를 구성합니다. 레코드 집합이 처음 열리고 첫 번째 레코드를 읽으려고 할 때 RFX는 선택한 각 열을 해당 필드 데이터 멤버의 주소에 바인딩합니다. 레코드 집합이 레코드를 업데이트하면 RFX는 ODBC API 함수를 호출하여 SQL **UPDATE** 또는 **INSERT** 문을 드라이버에 보냅니다. RFX는 필드 데이터 멤버에 대한 지식을 사용하여 쓸 열을 지정합니다.

프레임워크는 특정 단계에서 편집 버퍼를 백업하여 필요한 경우 내용을 복원할 수 있습니다. RFX는 새 레코드를 추가하기 전에 기존 레코드를 편집하기 전에 편집 버퍼를 백업합니다. 예를 들어 다음 `Update` `AddNew`호출 후 편집 버퍼를 복원합니다. 새로 변경된 편집 버퍼를 포기하는 경우 편집 버퍼가 복원되지 않습니다(예: 호출하기 `Update`전에 다른 레코드로 이동).

RFX는 데이터 원본과 레코드 집합의 필드 데이터 멤버 간에 데이터를 교환하는 것 외에도 바인딩 매개 변수를 관리합니다. 레코드 집합이 열리면 모든 매개 변수 데이터 멤버는 `CRecordset::Open` 구성되는 SQL 문의 "?" 자리 표시자 순서로 바인딩됩니다. 자세한 내용은 [레코드 집합: 레코드 집합(ODBC) 매개 변수화를](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)참조하십시오.

레코드 집합 클래스의 `DoFieldExchange` 재정의는 모든 작업을 수행하여 양방향으로 데이터를 이동합니다. 대화 상자 데이터 교환(DDX)과 마찬가지로 RFX에는 클래스의 데이터 멤버에 대한 정보가 필요합니다. 마법사는 마법사로 지정한 필드 데이터 멤버 `DoFieldExchange` 이름 및 데이터 형식에 따라 레코드 집합별 구현을 작성하여 필요한 정보를 제공합니다.

## <a name="record-field-exchange-process"></a><a name="_core_the_record_field_exchange_process"></a>레코드 필드 교환 프로세스

이 섹션에서는 레코드 집합 개체가 열리고 레코드를 추가, 업데이트 및 삭제할 때 RFX 이벤트의 시퀀스를 설명합니다. 레코드 [집합 을 여는 동안 RFX 작업 의 테이블 시퀀스와](#_core_sequence_of_rfx_operations_during_recordset_open) 이 항목에서 스크롤 하는 `Move` 동안 RFX 작업 의 테이블 [시퀀스](#_core_sequence_of_rfx_operations_during_scrolling) 는 RFX 레코드 집합에서 명령을 처리 하 고 RFX 업데이트를 관리 하는 프로세스를 보여 준다. 이러한 프로세스 동안 [DoFieldExchange는](../../mfc/reference/crecordset-class.md#dofieldexchange) 여러 가지 작업을 수행하도록 호출됩니다. `m_nOperation` [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 개체의 데이터 멤버는 요청되는 작업을 결정합니다. [레코드 집합: 레코드 집합 선택 레코드(ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) 및 레코드 집합: 레코드 [집합 업데이트 레코드(ODBC)를](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) 이 자료를 읽기 전에 읽는 것이 유용할 수 있습니다.

### <a name="rfx-initial-binding-of-columns-and-parameters"></a><a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a>RFX: 열 및 매개 변수의 초기 바인딩

레코드 집합 개체의 [Open](../../mfc/reference/crecordset-class.md#open) 멤버 함수를 호출할 때 다음 RFX 활동이 표시된 순서대로 수행됩니다.

- 레코드 집합에 매개 변수 데이터 멤버가 있는 경우 프레임워크는 `DoFieldExchange` 레코드 집합의 SQL 문 문자열의 매개 변수 자리 표시자에 매개 변수를 바인딩합니다. 매개 변수 값의 데이터 형식 종속 표현은 **SELECT** 문에 있는 각 자리 표시자에 사용됩니다. 이 문제는 SQL 문이 준비된 후에 실행되기 전에 발생합니다. 명령문 준비에 대한 `::SQLPrepare` 자세한 내용은 ODBC 프로그래머 의 참조 에서 *함수를*참조하십시오.

- 프레임워크는 `DoFieldExchange` 선택한 열의 값을 레코드 집합의 해당 필드 데이터 멤버에 바인딩하기 위해 두 번째 호출합니다. 이렇게 하면 레코드 집합 개체가 첫 번째 레코드의 열을 포함하는 편집 버퍼로 설정됩니다.

- 레코드 집합은 SQL 문을 실행하고 데이터 원본은 첫 번째 레코드를 선택합니다. 레코드의 열은 레코드 집합의 필드 데이터 멤버에 로드됩니다.

다음 표에서는 레코드 집합을 열 때 RFX 작업 의 시퀀스를 보여 주며 있습니다.

### <a name="sequence-of-rfx-operations-during-recordset-open"></a><a name="_core_sequence_of_rfx_operations_during_recordset_open"></a>레코드 집합 을 여는 동안 RFX 작업 시퀀스

|[operationName]|도필드익스체인지 운영|데이터베이스/SQL 작업|
|--------------------|-------------------------------|-----------------------------|
|1. 레코드 집합을 엽니다.|||
||2. SQL 문을 작성합니다.||
|||3. SQL을 보냅니다.|
||4. 매개 변수 데이터 멤버를 바인딩합니다.||
||5. 필드 데이터 멤버를 열에 바인딩합니다.||
|||6. ODBC는 데이터를 이동하고 채웁니다.|
||7. C ++에 대한 데이터를 수정합니다.||

레코드 집합은 ODBC의 준비된 실행을 사용하여 동일한 SQL 문으로 빠르게 다시 쿼리할 수 있도록 합니다. 준비된 실행에 대한 자세한 내용은 MSDN 라이브러리의 ODBC SDK *프로그래머 참조를* 참조하십시오.

### <a name="rfx-scrolling"></a><a name="_mfc_rfx.3a_.scrolling"></a>RFX: 스크롤

한 레코드에서 다른 레코드로 스크롤할 `DoFieldExchange` 때 프레임워크는 필드 데이터 멤버에 이전에 저장된 값을 새 레코드에 대한 값으로 바꾸기 위해 호출됩니다.

다음 표에서는 사용자가 레코드에서 레코드로 이동할 때 RFX 작업 순서를 보여 주며 있습니다.

### <a name="sequence-of-rfx-operations-during-scrolling"></a><a name="_core_sequence_of_rfx_operations_during_scrolling"></a>스크롤 하는 동안 RFX 작업 의 시퀀스

|[operationName]|도필드익스체인지 운영|데이터베이스/SQL 작업|
|--------------------|-------------------------------|-----------------------------|
|1. `MoveNext` 호출 또는 다른 이동 기능 중 하나.|||
|||2. ODBC는 데이터를 이동하고 채웁니다.|
||3. C ++에 대한 데이터를 수정합니다.||

### <a name="rfx-adding-new-records-and-editing-existing-records"></a><a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a>RFX: 새 레코드 추가 및 기존 레코드 편집

새 레코드를 추가하면 레코드 집합이 편집 버퍼로 작동하여 새 레코드의 내용을 작성합니다. 레코드 를 추가하는 것과 마찬가지로 레코드 편집에는 레코드 집합의 필드 데이터 멤버 의 값이 변경됩니다. RFX 관점에서 시퀀스는 다음과 같습니다.

1. 레코드 집합의 [AddNew](../../mfc/reference/crecordset-class.md#addnew) 또는 [편집](../../mfc/reference/crecordset-class.md#edit) 멤버 함수를 호출하면 RFX가 현재 편집 버퍼를 저장하여 나중에 복원할 수 있습니다.

1. `AddNew`또는 `Edit` RFX가 변경된 필드 데이터 멤버를 검색할 수 있도록 편집 버퍼의 필드를 준비합니다.

   새 레코드에 새 레코드와 비교할 이전 `AddNew` 값이 없으므로 각 필드 데이터 멤버의 값을 PSEUDO_NULL 값으로 설정합니다. 나중에 `Update`호출할 때 RFX는 각 데이터 멤버의 값을 PSEUDO_NULL 값과 비교합니다. 차이가 있으면 데이터 멤버가 설정되었습니다. (PSEUDO_NULL 진정한 Null 값이 있는 레코드 열과 같지 않으며 C++ NULL과 동일하지도 않습니다.)

   에 `Update` 대 `AddNew`한 `Update` 호출과 `Edit` 달리 업데이트 된 값에 대 한 호출 PSEUDO_NULL 사용 하는 대신 이전에 저장 된 값과 비교 합니다. 차이점은 비교를 `AddNew` 위해 이전에 저장된 값이 없다는 것입니다.

1. 편집할 값이 있거나 새 레코드에 대해 채우려는 필드 데이터 멤버의 값을 직접 설정합니다. 여기에는 호출이 `SetFieldNull`포함될 수 있습니다.

1. [업데이트](../../mfc/reference/crecordset-class.md#update) 호출은 2단계에서 설명한 대로 변경된 필드 데이터 [멤버를 확인합니다(스크롤 중 RFX 작업 시퀀스](#_core_sequence_of_rfx_operations_during_scrolling)표 참조). 변경되지 않은 경우 `Update` 0을 반환합니다. 일부 필드 데이터 멤버가 `Update` 변경된 경우 레코드의 모든 업데이트된 필드에 대한 값을 포함하는 SQL **INSERT** 문을 준비하고 실행합니다.

1. 의 `AddNew` `Update` 경우 호출 전에 현재 레코드의 이전에 저장된 값을 `AddNew` 복원하여 결론을 내립니다. 의 `Edit`경우 편집된 새 값은 제자리에 유지됩니다.

다음 표에서는 새 레코드를 추가하거나 기존 레코드를 편집할 때 RFX 작업 순서를 보여 주며, 이 순서는 다음과 같은 것입니다.

### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>새로 추가 및 편집하는 동안 RFX 작업 시퀀스

|[operationName]|도필드익스체인지 운영|데이터베이스/SQL 작업|
|--------------------|-------------------------------|-----------------------------|
|1. `AddNew` 전화 `Edit`또는 .|||
||2. 편집 버퍼를 백업합니다.||
||3. `AddNew`의 경우 필드 데이터 멤버를 "정리" 및 Null로 표시합니다.||
|4. 레코드 집합 필드 데이터 멤버에 값을 할당합니다.|||
|5. `Update`전화 .|||
||6. 변경된 필드를 확인합니다.||
||7. `Edit`에 **INSERT** 대한 `AddNew` SQL INSERT 명령문 또는 **UPDATE** 문을 작성합니다.||
|||8. SQL을 보냅니다.|
||9. `AddNew`에 대 한 백업 된 내용에 편집 버퍼를 복원 합니다. 에 `Edit`대 한 백업을 삭제 합니다.||

### <a name="rfx-deleting-existing-records"></a>RFX: 기존 레코드 삭제

레코드를 삭제하면 RFX는 레코드가 삭제되고 레코드를 이동해야 한다는 알림을 알리기 위해 모든 필드를 NULL로 설정합니다. 다른 RFX 시퀀스 정보는 필요하지 않습니다.

## <a name="see-also"></a>참고 항목

[레코드 필드 교환(RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[MFC ODBC 사용](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[매크로, 전역 함수 및 전역 변수](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[C필드익스체인지 클래스](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)
