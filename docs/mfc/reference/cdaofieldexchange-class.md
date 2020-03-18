---
title: CDaoFieldExchange 클래스
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldExchange
- AFXDAO/CDaoFieldExchange
- AFXDAO/CDaoFieldExchange::IsValidOperation
- AFXDAO/CDaoFieldExchange::SetFieldType
- AFXDAO/CDaoFieldExchange::m_nOperation
- AFXDAO/CDaoFieldExchange::m_prs
helpviewer_keywords:
- CDaoFieldExchange [MFC], IsValidOperation
- CDaoFieldExchange [MFC], SetFieldType
- CDaoFieldExchange [MFC], m_nOperation
- CDaoFieldExchange [MFC], m_prs
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
ms.openlocfilehash: cfffebd16c3c1d62dc4084b962c22911e4b46ae5
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426086"
---
# <a name="cdaofieldexchange-class"></a>CDaoFieldExchange 클래스

DAO 데이터베이스 클래스에서 사용하는 DAO 레코드 필드 교환(DFX) 루틴을 지원합니다.

DAO는 Office 2013을 통해 지원 됩니다. DAO 3.6은 최종 버전이 며 사용 되지 않는 것으로 간주 됩니다.

## <a name="syntax"></a>구문

```
class CDaoFieldExchange
```

## <a name="members"></a>구성원

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDaoFieldExchange:: IsValidOperation](#isvalidoperation)|현재 작업이 업데이트 되는 필드의 형식에 적합 한 경우 0이 아닌 값을 반환 합니다.|
|[CDaoFieldExchange:: SetFieldType](#setfieldtype)|`SetFieldType`에 대 한 다음 호출이 발생할 때까지 DFX 함수에 대 한 모든 후속 호출로 표시 되는 레코드 집합 데이터 멤버 (열 또는 매개 변수)의 유형을 지정 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDaoFieldExchange:: m_nOperation](#m_noperation)|레코드 집합의 `DoFieldExchange` 멤버 함수에 대 한 현재 호출에 의해 수행 되는 DFX 작업입니다.|
|[CDaoFieldExchange:: m_prs](#m_prs)|DFX 연산이 수행 되는 레코드 집합에 대 한 포인터입니다.|

## <a name="remarks"></a>설명

`CDaoFieldExchange`에 기본 클래스가 없습니다.

사용자 지정 데이터 형식에 대 한 데이터 교환 루틴을 작성 하는 경우이 클래스를 사용 합니다. 그렇지 않으면이 클래스를 직접 사용 하지 않습니다. DFX는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체의 필드 데이터 멤버와 데이터 소스에 있는 현재 레코드의 해당 필드 간에 데이터를 교환 합니다. DFX는 데이터 원본 및 데이터 원본에서 양방향으로 교환을 관리 합니다. 사용자 지정 DFX 루틴을 작성 하는 방법에 대 한 자세한 내용은 [기술 정보 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) 을 참조 하세요.

> [!NOTE]
>  DAO 데이터베이스 클래스는 ODBC (Open Database Connectivity)를 기반으로 하는 MFC 데이터베이스 클래스와는 다릅니다. 모든 DAO 데이터베이스 클래스 이름에는 "CDao" 접두사가 있습니다. 여전히 DAO 클래스를 사용 하 여 ODBC 데이터 원본에 액세스할 수 있습니다. 일반적으로 DAO 기반의 MFC 클래스는 ODBC를 기반으로 하는 MFC 클래스 보다 더 사용할 수 있습니다. DAO 기반 클래스는 자체 데이터베이스 엔진을 통해 ODBC 드라이버를 포함 하 여 데이터에 액세스할 수 있습니다. 또한 DAO를 직접 호출 하는 대신 클래스를 통해 테이블을 추가 하는 등의 DDL (데이터 정의 언어) 작업을 지원 합니다.

> [!NOTE]
>  DAO DFX (레코드 필드 교환)는 ODBC 기반 MFC 데이터베이스 클래스 (`CDatabase`, `CRecordset`)의 RFX (레코드 필드 교환)와 매우 비슷합니다. RFX를 이해 하는 경우 DFX를 쉽게 사용할 수 있습니다.

`CDaoFieldExchange` 개체는 DAO 레코드 필드 교환이 수행 되는 데 필요한 컨텍스트 정보를 제공 합니다. `CDaoFieldExchange` 개체는 바인딩 매개 변수 및 필드 데이터 멤버를 비롯 한 여러 작업을 지원 하 고 현재 레코드의 필드에 다양 한 플래그를 설정 합니다. DFX 연산은 `CDaoFieldExchange`의 **enum** **FieldType** 에서 정의한 형식의 레코드 집합 클래스 데이터 멤버에 대해 수행 됩니다. 가능한 **FieldType** 값은 다음과 같습니다.

- 필드 데이터 멤버에 대 한 `CDaoFieldExchange::outputColumn`입니다.

- 매개 변수 데이터 멤버에 대 한 `CDaoFieldExchange::param`입니다.

[IsValidOperation](#isvalidoperation) 멤버 함수는 고유한 사용자 지정 DFX 루틴을 작성 하는 데 제공 됩니다. [CDaoRecordset::D ofieldexchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) 함수에서 [SetFieldType](#setfieldtype) 를 자주 사용 합니다. DFX 전역 함수에 대 한 자세한 내용은 [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md)를 참조 하세요. 사용자 지정 데이터 형식에 대 한 사용자 지정 DFX 루틴을 작성 하는 방법에 대 한 자세한 내용은 [Technical Note 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)을 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

`CDaoFieldExchange`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao

##  <a name="isvalidoperation"></a>CDaoFieldExchange:: IsValidOperation

사용자 고유의 DFX 함수를 작성 하는 경우 함수의 시작 부분에 있는 `IsValidOperation`를 호출 하 여 현재 작업을 특정 필드 데이터 멤버 형식 (`CDaoFieldExchange::outputColumn` 또는 `CDaoFieldExchange::param`)에 대해 수행할 수 있는지 여부를 확인 합니다.

```
BOOL IsValidOperation();
```

### <a name="return-value"></a>Return Value

현재 작업이 업데이트 되는 필드의 형식에 적합 한 경우 0이 아닙니다.

### <a name="remarks"></a>설명

DFX 메커니즘에서 수행 하는 일부 작업은 가능한 필드 형식 중 하나에만 적용 됩니다. 기존 DFX 함수의 모델을 따릅니다.

사용자 지정 DFX 루틴을 작성 하는 방법에 대 한 자세한 내용은 [Technical Note 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)을 참조 하세요.

##  <a name="m_noperation"></a>CDaoFieldExchange:: m_nOperation

필드 교환 개체와 연결 된 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 대해 수행할 작업을 식별 합니다.

### <a name="remarks"></a>설명

`CDaoFieldExchange` 개체는 레코드 집합에 대 한 다양 한 DFX 작업의 컨텍스트를 제공 합니다.

> [!NOTE]
>  아래의 MarkForAddNew 및 SetFieldNull 작업에 설명 된 PSEUDONULL 값은 필드 Null을 표시 하는 데 사용 되는 값입니다. DAO 레코드 필드 교환 메커니즘 (DFX)은이 값을 사용 하 여 Null로 명시적으로 표시 된 필드를 확인 합니다. [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 및 [COleCurrency](../../mfc/reference/colecurrency-class.md) 필드에는 PSEUDONULL가 필요 하지 않습니다.

`m_nOperation` 가능한 값은 다음과 같습니다.

|작업(Operation)|Description|
|---------------|-----------------|
|`AddToParameterList`|SQL 문의 **PARAMETERS** 절을 작성 합니다.|
|`AddToSelectList`|SQL 문의 **SELECT** 절을 작성 합니다.|
|`BindField`|데이터베이스의 필드를 응용 프로그램의 메모리 위치에 바인딩합니다.|
|`BindParam`|레코드 집합의 쿼리에 대 한 매개 변수 값을 설정 합니다.|
|`Fixup`|필드에 대 한 Null 상태를 설정 합니다.|
|`AllocCache`|레코드 집합에서 "더티" 필드를 확인 하는 데 사용 되는 캐시를 할당 합니다.|
|`StoreField`|현재 레코드를 캐시에 저장 합니다.|
|`LoadField`|레코드 집합의 캐시 된 데이터 멤버 변수를 복원 합니다.|
|`FreeCache`|레코드 집합에서 "더티" 필드를 확인 하는 데 사용 되는 캐시를 해제 합니다.|
|`SetFieldNull`|필드의 상태를 Null로 설정 하 고 값을 PSEUDONULL로 설정 합니다.|
|`MarkForAddNew`|PSEUDONULL 하지 않는 경우 "더티" 필드를 표시 합니다.|
|`MarkForEdit`|캐시와 일치 하지 않는 경우 "더티" 필드를 표시 합니다.|
|`SetDirtyField`|"더티"로 표시 되는 필드 값을 설정 합니다.|
|`DumpField`|필드의 내용을 덤프 합니다 (디버그에만 해당).|
|`MaxDFXOperation`|입력 검사에 사용 됩니다.|

##  <a name="m_prs"></a>CDaoFieldExchange:: m_prs

`CDaoFieldExchange` 개체와 연결 된 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 대 한 포인터를 포함 합니다.

### <a name="remarks"></a>설명

##  <a name="setfieldtype"></a>CDaoFieldExchange:: SetFieldType

`CDaoRecordset` 클래스 `DoFieldExchange` 재정의에서 `SetFieldType`를 호출 합니다.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>매개 변수

*nFieldType*<br/>
`CDaoFieldExchange`에 선언 된 **열거형 FieldType**값으로, 다음 중 하나일 수 있습니다.

- `CDaoFieldExchange::outputColumn`

- `CDaoFieldExchange::param`

### <a name="remarks"></a>설명

일반적으로 클래스 마법사는이 호출을 작성 합니다. 사용자 고유의 함수를 작성 하 고 마법사를 사용 하 여 `DoFieldExchange` 함수를 작성 하는 경우 필드 맵 외부의 함수에 대 한 호출을 추가 합니다. 마법사를 사용 하지 않는 경우에는 필드 맵이 표시 되지 않습니다. 이 호출은 클래스의 각 필드 데이터 멤버에 대 한 DFX 함수 호출 보다 앞에 오고 필드 형식을 `CDaoFieldExchange::outputColumn`으로 식별 합니다.

레코드 집합 클래스를 매개 변수화 하는 경우 모든 매개 변수 데이터 멤버 (필드 맵 외부)에 대해 DFX 호출을 추가 하 고 `SetFieldType`를 호출 하 여 이러한 호출 앞에와 야 합니다. `CDaoFieldExchange::param`값을 전달 합니다. 대신 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 를 사용 하 고 매개 변수 값을 설정할 수 있습니다.

일반적으로 필드 데이터 멤버 또는 매개 변수 데이터 멤버와 연결 된 DFX 함수 호출의 각 그룹 앞에는 `SetFieldType`를 호출 해야 합니다. 각 `SetFieldType` 호출의 *nFieldType* 매개 변수는 `SetFieldType` 호출을 따르는 DFX 함수 호출로 표시 되는 데이터 멤버의 형식을 식별 합니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset 클래스](../../mfc/reference/cdaorecordset-class.md)
