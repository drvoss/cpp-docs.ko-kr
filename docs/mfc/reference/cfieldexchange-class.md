---
title: CFieldExchange 클래스
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
ms.openlocfilehash: e66b3ed16d4f21d46567c37bfaf7929d32f63b8e
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425900"
---
# <a name="cfieldexchange-class"></a>CFieldExchange 클래스

데이터베이스 클래스에서 사용되는 RFX(레코드 필드 교환) 및 대량 RFX(레코드 필드 교환) 루틴을 지원합니다.

## <a name="syntax"></a>구문

```
class CFieldExchange
```

## <a name="members"></a>구성원

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CFieldExchange::IsFieldType](#isfieldtype)|현재 작업이 업데이트 되는 필드의 형식에 적합 한 경우 0이 아닌 값을 반환 합니다.|
|[CFieldExchange::SetFieldType](#setfieldtype)|`SetFieldType`에 대 한 다음 호출이 수행 될 때까지 RFX 함수에 대 한 모든 다음 호출로 표시 되는 레코드 집합 데이터 멤버 (열 또는 매개 변수)의 유형을 지정 합니다.|

## <a name="remarks"></a>설명

`CFieldExchange`에 기본 클래스가 없습니다.

사용자 지정 데이터 형식에 대 한 데이터 교환 루틴을 작성 하거나 대량 행 페치를 구현 하는 경우이 클래스를 사용 합니다. 그렇지 않으면이 클래스를 직접 사용 하지 않습니다. RFX 및 Bulk RFX는 레코드 집합 개체의 필드 데이터 멤버와 데이터 소스에 있는 현재 레코드의 해당 필드 간에 데이터를 교환 합니다.

> [!NOTE]
>  ODBC (Open Database Connectivity) 클래스 대신 DAO (Data Access Objects) 클래스를 사용 하 여 작업 하는 경우 [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) 클래스를 대신 사용 합니다. 자세한 내용은 [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)문서를 참조 하세요.

`CFieldExchange` 개체는 레코드 필드 교환 또는 대량 레코드 필드 교환을 수행 하는 데 필요한 컨텍스트 정보를 제공 합니다. `CFieldExchange` 개체는 바인딩 매개 변수 및 필드 데이터 멤버를 비롯 한 여러 작업을 지원 하 고 현재 레코드의 필드에 다양 한 플래그를 설정 합니다. RFX 및 대량 RFX 작업은 `CFieldExchange`의 **enum** **FieldType** 에서 정의한 형식의 레코드 집합 클래스 데이터 멤버에 대해 수행 됩니다. 가능한 **FieldType** 값은 다음과 같습니다.

- 필드 데이터 멤버에 대 한 `CFieldExchange::outputColumn`입니다.

- 입력 매개 변수 데이터 멤버에 대 한 `CFieldExchange::inputParam` 또는 `CFieldExchange::param`입니다.

- 출력 매개 변수 데이터 멤버에 대 한 `CFieldExchange::outputParam`입니다.

- 입력/출력 매개 변수 데이터 멤버에 대 한 `CFieldExchange::inoutParam`입니다.

클래스의 멤버 함수 및 데이터 멤버는 대부분 사용자 지정 RFX 루틴을 작성 하는 데 제공 됩니다. `SetFieldType`를 자주 사용 합니다. 자세한 내용은 [RFX (레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md) 및 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)문서를 참조 하세요. 대량 행 페치에 대 한 자세한 내용은 [레코드 집합: 대량 레코드 페치 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조 하세요. RFX 및 Bulk RFX 전역 함수에 대 한 자세한 내용은이 참조의 MFC 매크로 및 전역 섹션에서 [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md) 를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

`CFieldExchange`

## <a name="requirements"></a>요구 사항

**헤더:** afxdb

##  <a name="isfieldtype"></a>CFieldExchange::IsFieldType

사용자 고유의 RFX 함수를 작성 하는 경우 함수 시작 부분에 있는 `IsFieldType`를 호출 하 여 현재 작업이 특정 필드 또는 매개 변수 데이터 멤버 형식 (`CFieldExchange::outputColumn`, `CFieldExchange::inputParam`, `CFieldExchange::param`, `CFieldExchange::outputParam`또는 `CFieldExchange::inoutParam`)에 대해 수행 될 수 있는지 여부를 확인 합니다.

```
BOOL IsFieldType(UINT* pnField);
```

### <a name="parameters"></a>매개 변수

*pnField*<br/>
이 매개 변수에는 필드 또는 매개 변수 데이터 멤버의 순차 숫자가 반환 됩니다. 이 숫자는 [crecordset::D ofieldexchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 또는 [Crecordset::D obulkfieldexchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) 함수에서 데이터 멤버의 순서에 해당 합니다.

### <a name="return-value"></a>Return Value

현재 필드 또는 매개 변수 형식에 대해 현재 작업을 수행할 수 있는 경우 0이 아닙니다.

### <a name="remarks"></a>설명

기존 RFX 함수의 모델을 따릅니다.

##  <a name="setfieldtype"></a>CFieldExchange::SetFieldType

레코드 집합 클래스의 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 또는 [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) override에 `SetFieldType`를 호출 해야 합니다.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>매개 변수

*nFieldType*<br/>
`CFieldExchange`에 선언 된 `enum FieldType`값으로, 다음 중 하나일 수 있습니다.

- `CFieldExchange::outputColumn`

- `CFieldExchange::inputParam`

- `CFieldExchange::param`

- `CFieldExchange::outputParam`

- `CFieldExchange::inoutParam`

### <a name="remarks"></a>설명

필드 데이터 멤버의 경우 `CFieldExchange::outputColumn`의 매개 변수와 RFX 또는 Bulk RFX 함수를 호출 하 여 `SetFieldType`를 호출 해야 합니다. 대량 행 페치를 구현 하지 않은 경우 클래스 마법사는 `DoFieldExchange`의 필드 맵 섹션에서이 `SetFieldType` 호출을 배치 합니다.

레코드 집합 클래스를 매개 변수화 하는 경우 모든 필드 맵 섹션 외부에서 `SetFieldType`를 다시 호출한 다음 모든 매개 변수 데이터 멤버에 대 한 RFX 호출을 수행 해야 합니다. 매개 변수 데이터 멤버의 각 형식에는 자체 `SetFieldType` 호출이 있어야 합니다. 다음 표에서는 클래스의 매개 변수 데이터 멤버를 나타내기 위해 `SetFieldType`에 전달할 수 있는 다양 한 값을 구분 합니다.

|SetFieldType 매개 변수 값|매개 변수 데이터 멤버의 형식입니다.|
|----------------------------------|-----------------------------------|
|`CFieldExchange::inputParam`|입력 매개 변수입니다. 레코드 집합의 쿼리 또는 저장 프로시저에 전달 되는 값입니다.|
|`CFieldExchange::param` | `CFieldExchange::inputParam`와 동일 합니다.|
|`CFieldExchange::outputParam`|출력 매개 변수입니다. 레코드 집합의 저장 프로시저에 대 한 반환 값입니다.|
|`CFieldExchange::inoutParam`|입/출력 매개 변수입니다. 레코드 집합의 저장 프로시저에 전달 되 고 반환 되는 값입니다.|

일반적으로 필드 데이터 멤버 또는 매개 변수 데이터 멤버와 연결 된 RFX 함수 호출의 각 그룹 앞에는 `SetFieldType`를 호출 해야 합니다. 각 `SetFieldType` 호출의 *nFieldType* 매개 변수는 `SetFieldType` 호출을 따르는 RFX 함수 호출로 표시 되는 데이터 멤버의 형식을 식별 합니다.

출력 및 입/출력 매개 변수를 처리 하는 방법에 대 한 자세한 내용은 멤버 함수 [Flushresultset](../../mfc/reference/crecordset-class.md#flushresultset)`CRecordset`를 참조 하세요. RFX 및 대량 RFX 함수에 대 한 자세한 내용은 [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md)항목을 참조 하세요. 대량 행 페치에 대 한 관련 정보는 [레코드 집합: 대량 레코드 페치 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조 하세요.

### <a name="example"></a>예제

이 예제에서는 `SetFieldType`에 대 한 호출을 통해 RFX 함수를 여러 번 호출 하는 방법을 보여 줍니다. `SetFieldType`는 `CFieldExchange` 개체에 대 한 `pFX` 포인터를 통해 호출 됩니다.

[!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)
