---
title: C필드익스체인지 클래스
ms.date: 11/04/2016
f1_keywords:
- CFieldExchange
- AFXDB/CFieldExchange
- AFXDB/CFieldExchange::IsFieldType
- AFXDB/CFieldExchange::SetFieldType
helpviewer_keywords:
- CFieldExchange [MFC], IsFieldType
- CFieldExchange [MFC], SetFieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
ms.openlocfilehash: de9db2713a25b232bbd7f936958d1c10e96c511a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753172"
---
# <a name="cfieldexchange-class"></a>C필드익스체인지 클래스

데이터베이스 클래스에서 사용되는 RFX(레코드 필드 교환) 및 대량 RFX(레코드 필드 교환) 루틴을 지원합니다.

## <a name="syntax"></a>구문

```
class CFieldExchange
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C필드 익스체인지::이필드타입](#isfieldtype)|현재 작업이 업데이트되는 필드 유형에 적합한 경우 0이 아닌 것을 반환합니다.|
|[C필드 익스체인지::세트필드타입](#setfieldtype)|다음에 호출될 때까지 RFX 함수에 대한 모든 다음 호출로 표시되는 레코드 집합 데이터 `SetFieldType`멤버(열 또는 매개 변수)의 유형을 지정합니다.|

## <a name="remarks"></a>설명

`CFieldExchange`기본 클래스가 없습니다.

사용자 지정 데이터 형식에 대한 데이터 교환 루틴을 작성하거나 대량 행 가져오기를 구현하는 경우 이 클래스를 사용합니다. 그렇지 않으면 이 클래스를 직접 사용하지 않습니다. RFX 및 대량 RFX는 레코드 집합 개체의 필드 데이터 멤버와 데이터 원본의 현재 레코드의 해당 필드 간에 데이터를 교환합니다.

> [!NOTE]
> ODBC(개방형 데이터베이스 연결) 클래스가 아닌 DAO(데이터 액세스 개체) 클래스로 작업하는 경우 대신 [클래스 CDaoFieldExchange를](../../mfc/reference/cdaofieldexchange-class.md) 사용합니다. 자세한 내용은 [문서 개요:데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)을 참조하십시오.

개체는 `CFieldExchange` 레코드 필드 교환 또는 대량 레코드 필드 교환이 수행되는 데 필요한 컨텍스트 정보를 제공합니다. `CFieldExchange`개체는 바인딩 매개 변수 및 필드 데이터 멤버를 비롯한 여러 작업을 지원하고 현재 레코드필드에 다양한 플래그를 설정합니다. RFX 및 대량 RFX 작업은 **에서 열거형** **FieldType에** 의해 정의된 `CFieldExchange`형식의 레코드 집합 클래스 데이터 멤버에서 수행됩니다. 가능한 필드타입 값은 다음과 **같습니다.**

- `CFieldExchange::outputColumn`필드 데이터 멤버에 대한 정보입니다.

- `CFieldExchange::inputParam`또는 `CFieldExchange::param` 입력 매개 변수 데이터 멤버에 대한.

- `CFieldExchange::outputParam`출력 매개 변수 데이터 멤버에 대한 것입니다.

- `CFieldExchange::inoutParam`입력/출력 매개변수 데이터 멤버용입니다.

클래스의 멤버 함수 및 데이터 멤버의 대부분은 사용자 지정 RFX 루틴을 작성하기 위해 제공됩니다. 자주 사용 `SetFieldType` 하실 수 있습니다. 자세한 내용은 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md) 및 [레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)문서를 참조하십시오. 대량 행 가져오기에 대한 자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오. RFX 및 대량 RFX 글로벌 함수에 대한 자세한 내용은 이 참조의 MFC 매크로 및 글로벌 섹션에서 [필드 교환 함수 레코드를](../../mfc/reference/record-field-exchange-functions.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CFieldExchange`

## <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="cfieldexchangeisfieldtype"></a><a name="isfieldtype"></a>C필드 익스체인지::이필드타입

고유한 RFX 함수를 작성하는 `IsFieldType` 경우 함수의 시작 부분에 호출하여 특정 필드 또는 매개 변수 데이터 멤버 `CFieldExchange::outputColumn`유형(a `CFieldExchange::outputParam`. `CFieldExchange::inoutParam` `CFieldExchange::inputParam`. `CFieldExchange::param`

```
BOOL IsFieldType(UINT* pnField);
```

### <a name="parameters"></a>매개 변수

*pn필드*<br/>
필드 또는 매개 변수 데이터 멤버의 순차 번호가 이 매개 변수에 반환됩니다. 이 숫자는 [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 또는 [CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) 함수에서 데이터 멤버의 순서에 해당합니다.

### <a name="return-value"></a>Return Value

현재 필드 또는 매개 변수 유형에서 현재 작업을 수행할 수 있는 경우 0이 아닙니다.

### <a name="remarks"></a>설명

기존 RFX 함수의 모델을 따릅니다.

## <a name="cfieldexchangesetfieldtype"></a><a name="setfieldtype"></a>C필드 익스체인지::세트필드타입

레코드 집합 클래스의 `SetFieldType` [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 또는 [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) 재정의에 대한 호출이 필요합니다.

```cpp
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>매개 변수

*n필드 타입*<br/>
의 값은 `enum FieldType`다음 `CFieldExchange`중 하나일 수 있습니다.

- `CFieldExchange::outputColumn`

- `CFieldExchange::inputParam`

- `CFieldExchange::param`

- `CFieldExchange::outputParam`

- `CFieldExchange::inoutParam`

### <a name="remarks"></a>설명

필드 데이터 멤버의 `SetFieldType` `CFieldExchange::outputColumn`경우 의 매개 변수를 호출한 다음 RFX 또는 대량 RFX 함수에 대한 호출을 수행해야 합니다. 대량 행 가져오기를 구현하지 않은 경우 ClassWizard는 `SetFieldType` `DoFieldExchange`의 필드 맵 섹션에서 이 호출을 배치합니다.

레코드 집합 클래스를 매개변수화하는 `SetFieldType` 경우 필드 맵 섹션 외부에서 다시 호출한 다음 RFX가 모든 매개 변수 데이터 멤버를 호출해야 합니다. 각 매개 변수 데이터 멤버 `SetFieldType` 유형에는 자체 호출이 있어야 합니다. 다음 표에서는 클래스의 매개 변수 `SetFieldType` 데이터 멤버를 나타내기 위해 전달할 수 있는 다른 값을 구분합니다.

|SetFieldType 매개 변수 값|매개 변수 데이터 멤버의 유형|
|----------------------------------|-----------------------------------|
|`CFieldExchange::inputParam`|입력 매개 변수입니다. 레코드 집합의 쿼리 또는 저장 프로시저에 전달되는 값입니다.|
|`CFieldExchange::param` | 와 `CFieldExchange::inputParam`동일합니다.|
|`CFieldExchange::outputParam`|출력 매개 변수입니다. 레코드 집합의 저장 프로시저의 반환 값입니다.|
|`CFieldExchange::inoutParam`|입력/출력 매개 변수입니다. 레코드 집합의 저장 프로시저에서 전달되고 반환되는 값입니다.|

일반적으로 필드 데이터 멤버 또는 매개 변수 데이터 멤버와 연결된 각 RFX 함수 `SetFieldType`호출 그룹에 대한 호출 앞에 있어야 합니다. 각 `SetFieldType` 호출의 `SetFieldType` *nFieldType* 매개 변수는 호출 다음에 RFX 함수 호출로 표시되는 데이터 멤버의 형식을 식별합니다.

출력 및 입력/출력 매개 변수 처리에 `CRecordset` 대한 자세한 내용은 멤버 함수 [FlushResultSet을](../../mfc/reference/crecordset-class.md#flushresultset)참조하십시오. RFX 및 대량 RFX 함수에 대한 자세한 내용은 [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md)항목을 참조하십시오. 대량 행 가져오기에 대한 관련 정보는 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

### <a name="example"></a>예제

이 예제에서는 에 대한 호출이 함께 `SetFieldType`제공되는 RFX 함수에 대한 여러 호출을 보여 주며 있습니다. 개체에 `SetFieldType` 대한 포인터를 `pFX` 통해 `CFieldExchange` 호출됩니다.

[!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)
