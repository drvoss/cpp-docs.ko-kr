---
title: CDaoField익스체인지 클래스
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
ms.openlocfilehash: 86f12f78338d1c60e3dd13614ccedc2868f28d81
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754713"
---
# <a name="cdaofieldexchange-class"></a>CDaoField익스체인지 클래스

DAO 데이터베이스 클래스에서 사용하는 DAO 레코드 필드 교환(DFX) 루틴을 지원합니다.

DAO는 Office 2013을 통해 지원됩니다. DAO 3.6은 최종 버전이며 더 이상 사용되지 않는 것으로 간주됩니다.

## <a name="syntax"></a>구문

```
class CDaoFieldExchange
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDaoFieldExchange::유효 작업](#isvalidoperation)|현재 작업이 업데이트되는 필드 유형에 적합한 경우 0이 아닌 것을 반환합니다.|
|[CDao필드익스체인지::세트필드타입](#setfieldtype)|다음에 호출될 때까지 DFX 함수에 대한 모든 후속 호출로 표시되는 레코드 집합 데이터 `SetFieldType`멤버(열 또는 매개 변수)의 유형을 지정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDao필드익스체인지:m_nOperation](#m_noperation)|레코드 집합의 `DoFieldExchange` 멤버 함수에 대한 현재 호출에 의해 수행되는 DFX 작업입니다.|
|[CDaoFieldExchange::m_prs](#m_prs)|DFX 작업이 수행되는 레코드 집합에 대한 포인터입니다.|

## <a name="remarks"></a>설명

`CDaoFieldExchange`기본 클래스가 없습니다.

사용자 지정 데이터 형식에 대한 데이터 교환 루틴을 작성하는 경우 이 클래스를 사용합니다. 그렇지 않으면 이 클래스를 직접 사용하지 않습니다. DFX는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체의 필드 데이터 멤버와 데이터 원본에 있는 현재 레코드의 해당 필드 간에 데이터를 교환합니다. DFX는 데이터 원본과 데이터 원본에 이르기까지 양방향으로 교환을 관리합니다. 사용자 지정 DFX 루틴 작성에 대한 자세한 내용은 [기술 참고 53을](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) 참조하십시오.

> [!NOTE]
> DAO 데이터베이스 클래스는 ODBC(개방형 데이터베이스 연결)를 기반으로 하는 MFC 데이터베이스 클래스와 구별됩니다. 모든 DAO 데이터베이스 클래스 이름에는 "CDao" 접두사가 있습니다. DAO 클래스를 사용하여 ODBC 데이터 원본에 계속 액세스할 수 있습니다. 일반적으로 DAO를 기반으로 하는 MFC 클래스는 ODBC를 기반으로 하는 MFC 클래스보다 더 유능합니다. DAO 기반 클래스는 자체 데이터베이스 엔진을 통해 ODBC 드라이버를 비롯한 데이터에 액세스할 수 있습니다. 또한 DAO를 직접 호출하지 않고 클래스를 통해 테이블을 추가하는 등 DDL(데이터 정의 언어) 작업을 지원합니다.

> [!NOTE]
> DAO 레코드 필드 교환(DFX)은 ODBC 기반 MFC 데이터베이스 클래스(, `CDatabase` `CRecordset`)에서 레코드 필드 교환(RFX)과 매우 유사합니다. RFX를 이해한다면 DFX를 쉽게 사용할 수 있습니다.

개체는 `CDaoFieldExchange` DAO 레코드 필드 교환이 수행되는 데 필요한 컨텍스트 정보를 제공합니다. `CDaoFieldExchange`개체는 바인딩 매개 변수 및 필드 데이터 멤버를 비롯한 여러 작업을 지원하고 현재 레코드필드에 다양한 플래그를 설정합니다. DFX 작업은 **에서 열거형** **FieldType에** 의해 정의된 형식의 `CDaoFieldExchange`레코드 집합 클래스 데이터 멤버에서 수행됩니다. 가능한 필드타입 값은 다음과 **같습니다.**

- `CDaoFieldExchange::outputColumn`필드 데이터 멤버에 대한 정보입니다.

- `CDaoFieldExchange::param`매개 변수 데이터 멤버에 대 한.

[IsValidOperation](#isvalidoperation) 멤버 함수는 사용자 지정 DFX 루틴을 작성하기 위해 제공됩니다. [CDao레코드 집합::DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) 함수에서 [SetFieldType을](#setfieldtype) 자주 사용합니다. DFX 전역 함수에 대한 자세한 내용은 [레코드 필드 교환 함수를](../../mfc/reference/record-field-exchange-functions.md)참조하십시오. 사용자 고유의 데이터 형식에 대한 사용자 지정 DFX 루틴 작성에 대한 자세한 내용은 [기술 참고 53을](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CDaoFieldExchange`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="cdaofieldexchangeisvalidoperation"></a><a name="isvalidoperation"></a>CDaoFieldExchange::유효 작업

고유한 DFX 함수를 작성하는 `IsValidOperation` 경우 함수 시작 시 호출하여 특정 필드 데이터 멤버 유형(a `CDaoFieldExchange::outputColumn` 또는 `CDaoFieldExchange::param`a)에서 현재 작업을 수행할 수 있는지 여부를 확인합니다.

```
BOOL IsValidOperation();
```

### <a name="return-value"></a>Return Value

현재 작업이 업데이트되는 필드 유형에 적합한 경우 0이 아닙니다.

### <a name="remarks"></a>설명

DFX 메커니즘에 의해 수행되는 일부 작업은 가능한 필드 유형 중 하나에만 적용됩니다. 기존 DFX 함수의 모델을 따릅니다.

사용자 지정 DFX 루틴 작성에 대한 자세한 내용은 [기술 참고 53을](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)참조하십시오.

## <a name="cdaofieldexchangem_noperation"></a><a name="m_noperation"></a>CDao필드익스체인지:m_nOperation

필드 교환 개체와 연결된 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에서 수행할 작업을 식별합니다.

### <a name="remarks"></a>설명

개체는 `CDaoFieldExchange` 레코드 집합에서 여러 가지 다른 DFX 작업에 대한 컨텍스트를 제공합니다.

> [!NOTE]
> 아래 MarkForAddNew 및 SetFieldNull 작업 아래에 설명된 PSEUDONULL 값은 Null 필드를 표시하는 데 사용되는 값입니다. DAO 레코드 필드 교환 메커니즘(DFX)은 이 값을 사용하여 Null로 명시적으로 표시된 필드를 확인합니다. [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 및 [COleCurrency](../../mfc/reference/colecurrency-class.md) 필드에는 PSEUDONULL이 필요하지 않습니다.

가능한 `m_nOperation` 값은 다음과 같습니다.

|작업(Operation)|Description|
|---------------|-----------------|
|`AddToParameterList`|SQL 문의 **매개 변수 절을** 빌드합니다.|
|`AddToSelectList`|SQL 문의 **SELECT** 절을 작성합니다.|
|`BindField`|데이터베이스의 필드를 응용 프로그램의 메모리 위치에 바인딩합니다.|
|`BindParam`|레코드 집합 쿼리에 대한 매개 변수 값을 설정합니다.|
|`Fixup`|필드에 대한 Null 상태를 설정합니다.|
|`AllocCache`|레코드 집합에서 "더티" 필드를 확인하는 데 사용되는 캐시를 할당합니다.|
|`StoreField`|현재 레코드를 캐시에 저장합니다.|
|`LoadField`|레코드 집합에서 캐시된 데이터 멤버 변수를 복원합니다.|
|`FreeCache`|레코드 집합에서 "더티" 필드를 확인하는 데 사용되는 캐시를 해제합니다.|
|`SetFieldNull`|필드의 상태를 Null로 설정하고 값을 PSEUDONULL로 설정합니다.|
|`MarkForAddNew`|PSEUDONULL이 아니라면 필드를 "더티"로 표시합니다.|
|`MarkForEdit`|캐시와 일치하지 않으면 필드를 "더티"로 표시합니다.|
|`SetDirtyField`|필드 값을 "더티"로 표시합니다.|
|`DumpField`|필드의 내용을 덤프합니다(디버그만).|
|`MaxDFXOperation`|입력 검사에 사용됩니다.|

## <a name="cdaofieldexchangem_prs"></a><a name="m_prs"></a>CDaoFieldExchange::m_prs

개체와 연결된 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 `CDaoFieldExchange` 대한 포인터를 포함합니다.

### <a name="remarks"></a>설명

## <a name="cdaofieldexchangesetfieldtype"></a><a name="setfieldtype"></a>CDao필드익스체인지::세트필드타입

클래스의 `DoFieldExchange` `CDaoRecordset` 재정의를 요청합니다. `SetFieldType`

```cpp
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>매개 변수

*n필드 타입*<br/>
에 선언된 **열거형 FieldType의**값은 다음 중 하나일 수 `CDaoFieldExchange`있습니다.

- `CDaoFieldExchange::outputColumn`

- `CDaoFieldExchange::param`

### <a name="remarks"></a>설명

일반적으로 ClassWizard는 이 호출을 작성합니다. 사용자 고유의 함수를 작성하고 마법사를 사용하여 `DoFieldExchange` 함수를 작성하는 경우 필드 맵 외부에서 고유한 함수에 호출을 추가합니다. 마법사를 사용하지 않으면 필드 맵이 없습니다. 호출 앞에 DFX 함수( 클래스의 각 필드 데이터 멤버에 대해 하나씩)가 `CDaoFieldExchange::outputColumn`호출되고 필드 형식을 로 식별합니다.

레코드 집합 클래스를 매개변수화하는 경우 모든 매개 변수 데이터 멤버(필드 맵 외부)에 대한 DFX 호출을 추가하고 에 대한 `SetFieldType`호출을 사용하여 이러한 호출 앞에 와야 합니다. 값을 `CDaoFieldExchange::param`전달합니다. 대신 [CDaoQueryDef를](../../mfc/reference/cdaoquerydef-class.md) 사용하고 매개 변수 값을 설정할 수 있습니다.

일반적으로 필드 데이터 멤버 또는 매개 변수 데이터 멤버와 연결된 DFX 함수 호출의 각 그룹에 대한 호출 앞에 있어야 `SetFieldType`합니다. 각 `SetFieldType` 호출의 `SetFieldType` *nFieldType* 매개 변수는 호출 다음에 DFX 함수 호출로 표시되는 데이터 멤버의 형식을 식별합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDao레코드 집합 클래스](../../mfc/reference/cdaorecordset-class.md)
