---
title: CDaoTableDef 클래스
ms.date: 11/04/2016
f1_keywords:
- CDaoTableDef
- AFXDAO/CDaoTableDef
- AFXDAO/CDaoTableDef::CDaoTableDef
- AFXDAO/CDaoTableDef::Append
- AFXDAO/CDaoTableDef::CanUpdate
- AFXDAO/CDaoTableDef::Close
- AFXDAO/CDaoTableDef::Create
- AFXDAO/CDaoTableDef::CreateField
- AFXDAO/CDaoTableDef::CreateIndex
- AFXDAO/CDaoTableDef::DeleteField
- AFXDAO/CDaoTableDef::DeleteIndex
- AFXDAO/CDaoTableDef::GetAttributes
- AFXDAO/CDaoTableDef::GetConnect
- AFXDAO/CDaoTableDef::GetDateCreated
- AFXDAO/CDaoTableDef::GetDateLastUpdated
- AFXDAO/CDaoTableDef::GetFieldCount
- AFXDAO/CDaoTableDef::GetFieldInfo
- AFXDAO/CDaoTableDef::GetIndexCount
- AFXDAO/CDaoTableDef::GetIndexInfo
- AFXDAO/CDaoTableDef::GetName
- AFXDAO/CDaoTableDef::GetRecordCount
- AFXDAO/CDaoTableDef::GetSourceTableName
- AFXDAO/CDaoTableDef::GetValidationRule
- AFXDAO/CDaoTableDef::GetValidationText
- AFXDAO/CDaoTableDef::IsOpen
- AFXDAO/CDaoTableDef::Open
- AFXDAO/CDaoTableDef::RefreshLink
- AFXDAO/CDaoTableDef::SetAttributes
- AFXDAO/CDaoTableDef::SetConnect
- AFXDAO/CDaoTableDef::SetName
- AFXDAO/CDaoTableDef::SetSourceTableName
- AFXDAO/CDaoTableDef::SetValidationRule
- AFXDAO/CDaoTableDef::SetValidationText
- AFXDAO/CDaoTableDef::m_pDAOTableDef
- AFXDAO/CDaoTableDef::m_pDatabase
helpviewer_keywords:
- CDaoTableDef [MFC], CDaoTableDef
- CDaoTableDef [MFC], Append
- CDaoTableDef [MFC], CanUpdate
- CDaoTableDef [MFC], Close
- CDaoTableDef [MFC], Create
- CDaoTableDef [MFC], CreateField
- CDaoTableDef [MFC], CreateIndex
- CDaoTableDef [MFC], DeleteField
- CDaoTableDef [MFC], DeleteIndex
- CDaoTableDef [MFC], GetAttributes
- CDaoTableDef [MFC], GetConnect
- CDaoTableDef [MFC], GetDateCreated
- CDaoTableDef [MFC], GetDateLastUpdated
- CDaoTableDef [MFC], GetFieldCount
- CDaoTableDef [MFC], GetFieldInfo
- CDaoTableDef [MFC], GetIndexCount
- CDaoTableDef [MFC], GetIndexInfo
- CDaoTableDef [MFC], GetName
- CDaoTableDef [MFC], GetRecordCount
- CDaoTableDef [MFC], GetSourceTableName
- CDaoTableDef [MFC], GetValidationRule
- CDaoTableDef [MFC], GetValidationText
- CDaoTableDef [MFC], IsOpen
- CDaoTableDef [MFC], Open
- CDaoTableDef [MFC], RefreshLink
- CDaoTableDef [MFC], SetAttributes
- CDaoTableDef [MFC], SetConnect
- CDaoTableDef [MFC], SetName
- CDaoTableDef [MFC], SetSourceTableName
- CDaoTableDef [MFC], SetValidationRule
- CDaoTableDef [MFC], SetValidationText
- CDaoTableDef [MFC], m_pDAOTableDef
- CDaoTableDef [MFC], m_pDatabase
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
ms.openlocfilehash: adc31ccbf2be34aa1df1fa56111d1990701a6329
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754695"
---
# <a name="cdaotabledef-class"></a>CDaoTableDef 클래스

기본 테이블 또는 연결된 테이블의 저장된 정의를 나타냅니다.

## <a name="syntax"></a>구문

```
class CDaoTableDef : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|`CDaoTableDef` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDaoTableDef::부속](#append)|데이터베이스에 새 테이블을 추가합니다.|
|[CDaoTableDef::캔업데이트](#canupdate)|테이블을 업데이트할 수 있는 경우 0이 아닌 것을 반환합니다(필드 또는 테이블 속성의 정의를 수정할 수 있음).|
|[CDaoTableDef::닫기](#close)|열린 테이블def를 닫습니다.|
|[CDaoTableDef::만들기](#create)|[추가 를](#append)사용하여 데이터베이스에 추가할 수 있는 테이블을 만듭니다.|
|[CDaoTableDef::만들기필드](#createfield)|테이블에 대한 필드를 만들기 위해 호출됩니다.|
|[CDaoTableDef::만들기 인덱스](#createindex)|테이블에 대한 인덱스를 만들기 위해 호출됩니다.|
|[CDaoTableDef::DeleteField](#deletefield)|테이블에서 필드를 삭제하기 위해 호출되었습니다.|
|[CDaoTableDef::DeleteIndex](#deleteindex)|테이블에서 인덱스를 삭제하기 위해 호출되었습니다.|
|[CDaoTableDef::Get특성](#getattributes)|개체의 하나 이상의 특성을 나타내는 `CDaoTableDef` 값을 반환합니다.|
|[CDaoTableDef::GetConnect](#getconnect)|테이블의 원본에 대한 정보를 제공하는 값을 반환합니다.|
|[CDaoTableDef::GetDateCreated](#getdatecreated)|개체의 기본 을 기본으로 `CDaoTableDef` 하는 기본 테이블을 만든 날짜 및 시간을 반환 합니다.|
|[CDaoTableDef::GetDateLast업데이트](#getdatelastupdated)|기본 테이블의 디자인에 대한 가장 최근 변경 된 날짜와 시간을 반환 합니다.|
|[CDaoTableDef::겟필드카운트](#getfieldcount)|테이블의 필드 수를 나타내는 값을 반환합니다.|
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|테이블의 필드에 대한 특정 종류의 정보를 반환합니다.|
|[CDaoTableDef::GetIndexCount](#getindexcount)|테이블에 대한 인덱스 수를 반환합니다.|
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|테이블에 대한 인덱스에 대한 특정 종류의 정보를 반환합니다.|
|[CDaoTableDef::GetName](#getname)|테이블의 사용자 정의 이름을 반환합니다.|
|[CDaoTableDef::GetRecordCount](#getrecordcount)|테이블의 레코드 수를 반환합니다.|
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|원본 데이터베이스에서 연결된 테이블의 이름을 지정하는 값을 반환합니다.|
|[CDaoTableDef::Getvalidation규칙](#getvalidationrule)|필드가 변경되었거나 테이블에 추가될 때 필드의 데이터의 유효성을 검사하는 값을 반환합니다.|
|[CDaoTableDef::Getvalidation텍스트](#getvalidationtext)|Field 개체의 값이 지정된 유효성 검사 규칙을 충족하지 않는 경우 응용 프로그램에 표시되는 메시지 텍스트를 지정하는 값을 반환합니다.|
|[CDaoTableDef::이스오픈](#isopen)|테이블이 열려 있으면 0이 아닌 것을 반환합니다.|
|[CDaoTableDef::열기](#open)|데이터베이스의 TableDef 컬렉션에 저장된 기존 테이블def를 엽니다.|
|[CDaoTableDef::새로 고침 링크](#refreshlink)|연결된 테이블에 대한 연결 정보를 업데이트합니다.|
|[CDaoTableDef::설정 속성](#setattributes)|개체의 하나 이상의 특성을 나타내는 `CDaoTableDef` 값을 설정합니다.|
|[CDaoTableDef::세트커넥트](#setconnect)|테이블의 원본에 대한 정보를 제공하는 값을 설정합니다.|
|[CDaoTableDef::SetName](#setname)|테이블의 이름을 설정합니다.|
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|원본 데이터베이스에서 연결된 테이블의 이름을 지정하는 값을 설정합니다.|
|[CDaoTableDef::집합 유효성 검사규칙](#setvalidationrule)|필드가 변경되었거나 테이블에 추가될 때 필드의 데이터의 유효성을 검사하는 값을 설정합니다.|
|[CDaoTableDef::집합 유효성 검사 텍스트](#setvalidationtext)|Field 개체의 값이 지정된 유효성 검사 규칙을 충족하지 않는 경우 응용 프로그램이 표시하는 메시지 텍스트를 지정하는 값을 설정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|tabledef 개체의 기본 DAO 인터페이스에 대한 포인터입니다.|
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|이 테이블의 원본 데이터베이스입니다.|

## <a name="remarks"></a>설명

각 DAO 데이터베이스 개체는 저장된 모든 DAO tabledef 개체를 포함하는 TableDefs라는 컬렉션을 유지 관리합니다.

개체를 사용하여 테이블 정의를 `CDaoTableDef` 조작합니다. 예를 들어, 다음을 수행할 수 있습니다.

- 데이터베이스의 로컬, 연결된 테이블 또는 외부 테이블의 필드 및 인덱스 구조를 검사합니다.

- 연결된 `SetConnect` 테이블에 `SetSourceTableName` 대해 및 멤버 함수를 `RefreshLink` 호출하고 멤버 함수를 사용하여 연결된 테이블에 대한 연결을 업데이트합니다.

- 멤버 `CanUpdate` 함수를 호출하여 테이블에서 필드 정의를 편집할 수 있는지 확인합니다.

- `GetValidationRule` `SetValidationRule`및 `GetValidationText` 및 `SetValidationText` 멤버 함수를 사용하여 유효성 검사 조건을 얻거나 설정합니다.

- 멤버 `Open` 함수를 사용하여 테이블, 다이나식 또는 스냅숏 `CDaoRecordset` 형식 개체를 만듭니다.

    > [!NOTE]
    >  DAO 데이터베이스 클래스는 ODBC(개방형 데이터베이스 연결)를 기반으로 하는 MFC 데이터베이스 클래스와 구별됩니다. 모든 DAO 데이터베이스 클래스 이름에는 "CDao" 접두사가 있습니다. DAO 클래스를 사용하여 ODBC 데이터 원본에 계속 액세스할 수 있습니다. DAO 클래스는 일반적으로 Microsoft Jet 데이터베이스 엔진에 만기되어 있기 때문에 우수한 기능을 제공합니다.

### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>tabledef 개체를 사용하여 기존 테이블로 작업하거나 새 테이블을 만들려면

1. 모든 경우에 먼저 `CDaoTableDef` 테이블을 속한 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체에 대한 포인터를 제공하는 개체를 생성합니다.

1. 그런 다음 원하는 항목에 따라 다음을 수행합니다.

   - 기존 저장된 테이블을 사용하려면 tabledef 개체의 [Open](#open) 멤버 함수를 호출하여 저장된 테이블의 이름을 제공합니다.

   - 새 테이블을 만들려면 tabledef 개체의 멤버 [만들기](#create) 함수를 호출하여 테이블 이름을 제공합니다. [CreateField](#createfield) 및 [CreateIndex를](#createindex) 호출하여 테이블에 필드와 인덱스를 추가합니다.

   - 데이터베이스의 TableDefs 컬렉션에 테이블을 더하여 테이블을 저장하려면 [부가 를 호출합니다.](#append) `Create`테이블def를 열린 상태로 두므로 호출 `Create` 한 후에는 호출하지 `Open`않습니다.

        > [!TIP]
        >  저장된 테이블을 만드는 가장 쉬운 방법은 저장된 테이블을 만들고 Microsoft Access를 사용하여 데이터베이스에 저장하는 것입니다. 그런 다음 MFC 코드에서 열고 사용할 수 있습니다.

열어놓았거나 만든 tabledef 개체를 사용하려면 *nOpenType* 매개 변수에 `CDaoRecordset` `dbOpenTable` 값이 있는 tabledef의 이름을 지정하여 개체를 만들고 엽니다.

tabledef 개체를 사용하여 `CDaoRecordset` 개체를 만들려면 일반적으로 위에서 설명한 대로 tabledef를 만들거나 연 다음 [CDaoRecordset::Open을](../../mfc/reference/cdaorecordset-class.md#open)호출할 때 tabledef 개체에 포인터를 전달하여 레코드 집합 개체를 생성합니다. 통과하는 테이블def는 열린 상태여야 합니다. 자세한 내용은 클래스 [CDaoRecordset을](../../mfc/reference/cdaorecordset-class.md)참조하십시오.

tabledef 개체 사용을 완료하면 [해당 닫기](../../mfc/reference/cdaorecordset-class.md#close) 멤버 함수를 호출합니다. 그런 다음 tabledef 개체를 파괴합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDaoTableDef`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="cdaotabledefappend"></a><a name="append"></a>CDaoTableDef::부속

[Create를](#create) 호출한 후 이 멤버 함수를 호출하여 새 tabledef 개체를 만들어 데이터베이스에 tabledef를 저장합니다.

```
virtual void Append();
```

### <a name="remarks"></a>설명

이 함수는 개체를 데이터베이스의 TableDefs 컬렉션에 적용합니다. tabledef를 추가하지 않음으로써 정의하는 동안 tabledef를 임시 개체로 사용할 수 있지만 저장하고 `Append`사용하려면 을 호출해야 합니다.

> [!NOTE]
> 명명되지 않은 tabledef(null 또는 빈 문자열 포함)를 추가하려고 하면 MFC가 예외를 throw합니다.

관련 정보는 DAO 도움말의 "방법 부화" 항목을 참조하십시오.

## <a name="cdaotabledefcanupdate"></a><a name="canupdate"></a>CDaoTableDef::캔업데이트

이 멤버 함수를 호출하여 개체의 기본 `CDaoTableDef` 정의를 변경할 수 있는지 여부를 확인합니다.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Return Value

테이블 구조(스키마)를 수정할 수 있는 경우(필드 및 인덱스 추가 또는 삭제), 그렇지 않으면 0이 아닙니다.

### <a name="remarks"></a>설명

기본적으로 개체의 기본을 기본으로 `CDaoTableDef` 새로 만든 테이블을 업데이트할 `CDaoTableDef` 수 있으며 개체의 기본을 기본으로 연결된 테이블을 업데이트할 수 없습니다. 결과 `CDaoTableDef` 레코드 집합이 업데이터 블렌더가 아니더라도 개체가 업데이터 처리될 수 있습니다.

관련 정보는 DAO 도움말의 "업데이터 속성" 항목을 참조하십시오.

## <a name="cdaotabledefcdaotabledef"></a><a name="cdaotabledef"></a>CDaoTableDef::CDaoTableDef

`CDaoTableDef` 개체를 생성합니다.

```
CDaoTableDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>매개 변수

*p데이터베이스*<br/>
[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

개체를 생성한 후 멤버 [만들기](#create) 또는 [열기](#open) 함수를 호출해야 합니다. 개체를 완료하면 [해당 닫기](#close) 멤버 함수를 호출하고 개체를 `CDaoTableDef` 삭제해야 합니다.

## <a name="cdaotabledefclose"></a><a name="close"></a>CDaoTableDef::닫기

이 멤버 함수를 호출하여 tabledef 개체를 닫고 해제합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

일반적으로 호출 `Close`후 **tabledef**개체가 새 로 할당된 경우 삭제합니다.

호출한 `Close`후 [Open을](#open) 다시 호출할 수 있습니다. 이렇게 하면 tabledef 개체를 다시 사용할 수 있습니다.

관련 정보는 DAO 도움말의 "방법 닫기" 항목을 참조하십시오.

## <a name="cdaotabledefcreate"></a><a name="create"></a>CDaoTableDef::만들기

이 멤버 함수를 호출하여 저장된 새 테이블을 만듭니다.

```
virtual void Create(
    LPCTSTR lpszName,
    long lAttributes = 0,
    LPCTSTR lpszSrcTable = NULL,
    LPCTSTR lpszConnect = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
테이블 의 이름을 포함하는 문자열에 대한 포인터입니다.

*lAttributes*<br/>
tabledef 개체로 표시되는 테이블의 특성에 해당하는 값입니다. 비트-OR를 사용하여 다음 상수 중 일부를 결합할 수 있습니다.

|상수|Description|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet 데이터베이스 엔진을 사용하는 데이터베이스의 경우 테이블이 단독으로 사용하기 위해 열린 연결된 테이블임을 나타냅니다.|
|`dbAttachSavePWD`|Microsoft Jet 데이터베이스 엔진을 사용하는 데이터베이스의 경우 연결된 테이블의 사용자 ID와 암호가 연결 정보와 함께 저장됨을 나타냅니다.|
|`dbSystemObject`|테이블이 Microsoft Jet 데이터베이스 엔진에서 제공하는 시스템 테이블임을 나타냅니다.|
|`dbHiddenObject`|테이블이 Microsoft Jet 데이터베이스 엔진에서 제공하는 숨겨진 테이블임을 나타냅니다.|

*lpszSrcTable*<br/>
원본 테이블 이름을 포함하는 문자열에 대한 포인터입니다. 기본적으로 이 값은 NULL로 초기화됩니다.

*lpszConnect*<br/>
기본 연결 문자열을 포함하는 문자열에 대한 포인터입니다. 기본적으로 이 값은 NULL로 초기화됩니다.

### <a name="remarks"></a>설명

tabledef라는 이름을 지정하면 [부가 를](#append) 호출하여 데이터베이스의 TableDefs 컬렉션에 tabledef를 저장할 수 있습니다. 호출 `Append`후 tabledef는 열린 상태이며 이를 사용하여 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체를 만들 수 있습니다.

관련 정보는 DAO 도움말의 "CreateTableDef 방법" 항목을 참조하십시오.

## <a name="cdaotabledefcreatefield"></a><a name="createfield"></a>CDaoTableDef::만들기필드

이 멤버 함수를 호출하여 테이블에 필드를 추가합니다.

```cpp
void CreateField(
    LPCTSTR lpszName,
    short nType,
    long lSize,
    long lAttributes = 0);

void CreateField(CDaoFieldInfo& fieldinfo);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
이 필드의 이름을 지정하는 문자열 식에 대한 포인터입니다.

*nType*<br/>
필드의 데이터 형식을 나타내는 값입니다. 설정은 다음 값 중 하나일 수 있습니다.

|Type|크기(바이트)|Description|
|----------|--------------------|-----------------|
|`dbBoolean`|1바이트|BOOL|
|`dbByte`|BYTE|
|`dbInteger`|2|int|
|`dbLong`|4|long|
|`dbCurrency`|8|화폐 [(COleCurrency)](../../mfc/reference/colecurrency-class.md)|
|`dbSingle`|4|float|
|`dbDouble`|8|double|
|`dbDate`|8|[날짜/시간(콜레데이트 타임)](../../atl-mfc-shared/reference/coledatetime-class.md)|
|`dbText`|1 - 255|텍스트 [(문자열)](../../atl-mfc-shared/reference/cstringt-class.md)|
|`dbLongBinary`|0|긴 이진(OLE 오브젝트), [CLong Binary](../../mfc/reference/clongbinary-class.md) 또는 [CByteArray](../../mfc/reference/cbytearray-class.md)|
|`dbMemo`|0|메모 [(문자열)](../../atl-mfc-shared/reference/cstringt-class.md)|

*l사이즈*<br/>
텍스트가 포함된 필드의 최대 크기(바이트) 또는 텍스트 또는 숫자 값이 포함된 필드의 고정 크기를 나타내는 값입니다. *lSize* 매개 변수는 텍스트 필드를 제외한 모든 필드에 대해 무시됩니다.

*lAttributes*<br/>
필드의 특성에 해당하는 값이며 비트-OR를 사용하여 결합할 수 있습니다.

|상수|Description|
|--------------|-----------------|
|`dbFixedField`|필드 크기가 고정되어 있습니다(숫자 필드의 기본값).|
|`dbVariableField`|필드 크기는 가변적입니다(텍스트 필드만 해당).|
|`dbAutoIncrField`|새 레코드의 필드 값은 변경할 수 없는 고유한 긴 정수로 자동으로 증분됩니다. Microsoft Jet 데이터베이스 테이블에만 지원됩니다.|
|`dbUpdatableField`|필드 값을 변경할 수 있습니다.|
|`dbDescending`|필드는 내림차순(Z - A 또는 100 - 0) 순서로 정렬됩니다(인덱스 개체의 필드 컬렉션의 필드 개체에만 적용). 이 상수를 생략하면 필드는 오름차순(A - Z 또는 0 - 100) 순서(기본값)로 정렬됩니다.|

*Fieldinfo*<br/>
[CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조에 대한 참조입니다.

### <a name="remarks"></a>설명

(OLE) `DAOField` 개체가 만들어지고 (OLE) 개체의 `DAOTableDef` 필드 컬렉션에 추가됩니다. 개체 속성을 `CDaoFieldInfo` 검사하는 데 사용하는 것 외에도 tabledef에서 새 필드를 만들기 위한 입력 매개 변수를 생성할 수도 있습니다. 첫 번째 `CreateField` 버전은 사용하기가 더 간단하지만 더 세밀한 컨트롤을 원한다면 `CreateField` `CDaoFieldInfo` 매개 변수를 사용하는 두 번째 버전의 을 사용할 수 있습니다.

매개 변수를 `CreateField` 사용하는 경우 `CDaoFieldInfo` 구조체의 다음 각 멤버를 신중하게 설정해야 합니다. `CDaoFieldInfo`

- `m_strName`

- `m_nType`

- `m_lSize`

- `m_lAttributes`

- `m_bAllowZeroLength`

의 `CDaoFieldInfo` 나머지 멤버는 **0,** FALSE 또는 빈 문자열로 설정해야 하며 멤버에 적합하거나 a가 `CDaoException` 발생할 수 있습니다.

관련 정보는 DAO 도움말의 "만들기 방법"을 참조하십시오.

## <a name="cdaotabledefcreateindex"></a><a name="createindex"></a>CDaoTableDef::만들기 인덱스

테이블에 인덱스를 추가하려면 이 함수를 호출합니다.

```cpp
void CreateIndex(CDaoIndexInfo& indexinfo);
```

### <a name="parameters"></a>매개 변수

*인덱스 정보*<br/>
[CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조에 대한 참조입니다.

### <a name="remarks"></a>설명

인덱스는 데이터베이스 테이블에서 액세스하는 레코드의 순서와 중복 레코드가 허용되는지 여부를 지정합니다. 인덱스는 또한 데이터에 대한 효율적인 액세스를 제공합니다.

테이블에 대한 인덱스를 만들 필요는 없지만 인덱싱되지 않은 대규모 테이블에서 특정 레코드에 액세스하거나 레코드 집합을 만드는 데 시간이 오래 걸릴 수 있습니다. 반면에 인덱스를 너무 많이 만들면 모든 인덱스가 자동으로 업데이트되면 업데이트, 추가 및 삭제 작업이 느려집니다. 만들 인덱스를 결정할 때 이러한 요소를 고려합니다.

구조의 다음 `CDaoIndexInfo` 멤버를 설정해야 합니다.

- `m_strName`이름을 제공해야 합니다.

- `m_pFieldInfos`구조의 `CDaoIndexFieldInfo` 배열을 가리킨다.

- `m_nFields``CDaoFieldInfo` 구조대 배열의 필드 수를 지정해야 합니다.

FALSE로 설정된 경우 나머지 멤버는 무시됩니다. 또한 인덱스를 `m_lDistinctCount` 만드는 동안 멤버가 무시됩니다.

## <a name="cdaotabledefdeletefield"></a><a name="deletefield"></a>CDaoTableDef::DeleteField

이 멤버 함수를 호출하여 필드를 제거하고 액세스할 수 없게 만듭니다.

```cpp
void DeleteField(LPCTSTR lpszName);
void DeleteField(int nIndex);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
기존 필드의 이름인 문자열 식에 대한 포인터입니다.

*nIndex*<br/>
인덱스별 조회에 대한 테이블의 0기반 필드 컬렉션의 필드 인덱스입니다.

### <a name="remarks"></a>설명

데이터베이스에 추가되지 않은 새 개체또는 [CanUpdate가](#canupdate) 0이 아닌 것을 반환할 때 이 멤버 함수를 사용할 수 있습니다.

관련 정보는 DAO 도움말의 "방법 삭제" 항목을 참조하십시오.

## <a name="cdaotabledefdeleteindex"></a><a name="deleteindex"></a>CDaoTableDef::DeleteIndex

이 멤버 함수를 호출하여 기본 테이블의 인덱스를 삭제합니다.

```cpp
void DeleteIndex(LPCTSTR lpszName);
void DeleteIndex(int nIndex);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
기존 인덱스의 이름인 문자열 식에 대한 포인터입니다.

*nIndex*<br/>
인덱스별 조회를 위해 데이터베이스의 0기반 TableDefs 컬렉션에 있는 인덱스 개체의 배열 인덱스입니다.

### <a name="remarks"></a>설명

데이터베이스에 추가되지 않은 새 개체또는 [CanUpdate가](#canupdate) 영하지 않은 개체를 반환할 때 이 멤버 함수를 사용할 수 있습니다.

관련 정보는 DAO 도움말의 "방법 삭제" 항목을 참조하십시오.

## <a name="cdaotabledefgetattributes"></a><a name="getattributes"></a>CDaoTableDef::Get특성

`CDaoTableDef` 개체의 경우 반환 값은 개체로 표시되는 테이블의 `CDaoTableDef` 특성을 지정하며 이러한 상수의 합계일 수 있습니다.

```
long GetAttributes();
```

### <a name="return-value"></a>Return Value

개체의 하나 이상의 특성을 나타내는 `CDaoTableDef` 값을 반환합니다.

### <a name="remarks"></a>설명

|상수|Description|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet 데이터베이스 엔진을 사용하는 데이터베이스의 경우 테이블이 단독으로 사용하기 위해 열린 연결된 테이블임을 나타냅니다.|
|`dbAttachSavePWD`|Microsoft Jet 데이터베이스 엔진을 사용하는 데이터베이스의 경우 연결된 테이블의 사용자 ID와 암호가 연결 정보와 함께 저장됨을 나타냅니다.|
|`dbSystemObject`|테이블이 Microsoft Jet 데이터베이스 엔진에서 제공하는 시스템 테이블임을 나타냅니다.|
|`dbHiddenObject`|테이블이 Microsoft Jet 데이터베이스 엔진에서 제공하는 숨겨진 테이블임을 나타냅니다.|
|`dbAttachedTable`|테이블이 역설 데이터베이스와 같은 ODBC가 아닌 데이터베이스에서 연결된 테이블임을 나타냅니다.|
|`dbAttachedODBC`|테이블이 Microsoft SQL Server와 같은 ODBC 데이터베이스에서 연결된 테이블임을 나타냅니다.|

시스템 테이블은 다양한 내부 정보를 포함하도록 Microsoft Jet 데이터베이스 엔진에서 만든 테이블입니다.

숨겨진 테이블은 Microsoft Jet 데이터베이스 엔진에서 임시로 사용하기 위해 만든 테이블입니다.

관련 정보는 DAO 도움말의 "속성 속성" 항목을 참조하십시오.

## <a name="cdaotabledefgetconnect"></a><a name="getconnect"></a>CDaoTableDef::GetConnect

이 멤버 함수를 호출하여 데이터 원본에 대한 연결 문자열을 가져옵니다.

```
CString GetConnect();
```

### <a name="return-value"></a>Return Value

테이블의 경로 및 데이터베이스 형식을 포함하는 `CString` 개체입니다.

### <a name="remarks"></a>설명

연결된 `CDaoTableDef` 테이블을 나타내는 개체의 경우 `CString` 개체는 하나 또는 두 개의 부분(데이터베이스 형식 지정자 및 데이터베이스 경로)으로 구성됩니다.

아래 표에 표시된 경로는 데이터베이스 파일을 포함하는 디렉터리에 대한 전체 경로이며 식별자 "DATABASE="앞에 와야 합니다. 경우에 따라(Microsoft Jet 및 Microsoft Excel 데이터베이스와 마찬가지로) 특정 파일 이름이 데이터베이스 경로 인수에 포함됩니다.

[CDaoTableDef::SetConnect의](#setconnect) 표에는 가능한 데이터베이스 유형과 해당 데이터베이스 지정 및 경로가 표시됩니다.

Microsoft Jet 데이터베이스 기본 테이블의 경우 지정기는 빈 문자열("")입니다.

암호가 필요하지만 제공되지 않은 경우 ODBC 드라이버는 테이블에 처음 액세스할 때 로그인 대화 상자를 표시하고 연결이 닫혀 다시 열리면 다시 표시됩니다. 연결된 테이블에 특성이 `dbAttachSavePWD` 있으면 테이블을 다시 열 때 로그인 프롬프트가 나타나지 않습니다.

관련 정보는 DAO 도움말의 "속성 연결" 항목을 참조하십시오.

## <a name="cdaotabledefgetdatecreated"></a><a name="getdatecreated"></a>CDaoTableDef::GetDateCreated

이 함수를 호출하여 개체의 기본 `CDaoTableDef` 테이블이 만들어진 날짜와 시간을 확인합니다.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Return Value

개체의 기본을 기본으로 테이블을 만드는 날짜와 `CDaoTableDef` 시간을 포함하는 값입니다.

### <a name="remarks"></a>설명

날짜 및 시간 설정은 기본 테이블을 만들거나 마지막으로 업데이트된 컴퓨터에서 파생됩니다. 다중 사용자 환경에서 사용자는 불일치를 방지하기 위해 파일 서버에서 직접 이러한 설정을 얻어야 합니다. 즉, 모든 클라이언트는 하나의 서버에서 "표준" 시간 원본을 사용해야 합니다.

관련 정보는 DAO 도움말의 "DateCreated, 마지막으로 업데이트된 속성" 항목을 참조하십시오.

## <a name="cdaotabledefgetdatelastupdated"></a><a name="getdatelastupdated"></a>CDaoTableDef::GetDateLast업데이트

이 함수를 호출하여 개체의 기본 `CDaoTableDef` 테이블이 마지막으로 업데이트된 날짜와 시간을 확인합니다.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Return Value

`CDaoTableDef` 개체의 기본 테이블이 마지막으로 업데이트된 날짜와 시간을 포함하는 값입니다.

### <a name="remarks"></a>설명

날짜 및 시간 설정은 기본 테이블을 만들거나 마지막으로 업데이트된 컴퓨터에서 파생됩니다. 다중 사용자 환경에서 사용자는 불일치를 방지하기 위해 파일 서버에서 직접 이러한 설정을 얻어야 합니다. 즉, 모든 클라이언트는 하나의 서버에서 "표준" 시간 원본을 사용해야 합니다.

관련 정보는 DAO 도움말의 "DateCreated, 마지막으로 업데이트된 속성" 항목을 참조하십시오.

## <a name="cdaotabledefgetfieldcount"></a><a name="getfieldcount"></a>CDaoTableDef::겟필드카운트

이 멤버 함수를 호출하여 테이블에 정의된 필드 수를 검색합니다.

```
short GetFieldCount();
```

### <a name="return-value"></a>Return Value

테이블의 필드 수입니다.

### <a name="remarks"></a>설명

값이 0이면 컬렉션에 개체가 없습니다.

관련 정보는 DAO 도움말의 "재산 수" 항목을 참조하십시오.

## <a name="cdaotabledefgetfieldinfo"></a><a name="getfieldinfo"></a>CDaoTableDef::GetFieldInfo

이 멤버 함수를 호출하여 tabledef에 정의된 필드에 대한 다양한 종류의 정보를 가져옵니다.

```cpp
void GetFieldInfo(
    int nIndex,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetFieldInfo(
    LPCTSTR lpszName,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스별 조회를 위해 테이블의 0기반 필드 컬렉션에 있는 필드 개체의 인덱스입니다.

*Fieldinfo*<br/>
[CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조에 대한 참조입니다.

*dwInfoOptions*<br/>
검색할 필드에 대한 정보를 지정하는 옵션입니다. 사용 가능한 옵션은 함수가 반환되는 원인과 함께 여기에 나열됩니다.

- `AFX_DAO_PRIMARY_INFO`(기본값) 이름, 유형, 크기, 속성. 가장 빠른 성능을 위해 이 옵션을 사용합니다.

- `AFX_DAO_SECONDARY_INFO`기본 정보, 플러스: 서수 위치, 필수, 제로 길이 허용, 정렬 순서, 외국 이름, 소스 필드, 소스 테이블

- `AFX_DAO_ALL_INFO`기본 및 보조 정보, 플러스: 유효성 검사 규칙, 유효성 검사 텍스트, 기본값

*lpszName*<br/>
이름으로 조회하기 위해 필드 개체의 이름에 대한 포인터입니다. 이름은 필드 이름을 고유하게 지정하는 최대 64자로 구성된 문자열입니다.

### <a name="remarks"></a>설명

함수의 한 버전을 사용하면 인덱스별로 필드를 조회할 수 있습니다. 다른 버전에서는 이름으로 필드를 조회할 수 있습니다.

반환된 정보에 대한 설명은 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조를 참조하십시오. 이 구조에는 *dwInfoOptions*에 대한 설명에 위에 나열된 정보 항목에 해당하는 멤버가 있습니다. 한 수준에서 정보를 요청하면 이전 수준에 대한 정보도 얻을 수 있습니다.

관련 정보는 DAO 도움말의 "속성 속성" 항목을 참조하십시오.

## <a name="cdaotabledefgetindexcount"></a><a name="getindexcount"></a>CDaoTableDef::GetIndexCount

이 멤버 함수를 호출하여 테이블의 인덱스 수를 가져옵니다.

```
short GetIndexCount();
```

### <a name="return-value"></a>Return Value

테이블의 인덱스 수입니다.

### <a name="remarks"></a>설명

값이 0이면 컬렉션에 인덱스가 없습니다.

관련 정보는 DAO 도움말의 "재산 수" 항목을 참조하십시오.

## <a name="cdaotabledefgetindexinfo"></a><a name="getindexinfo"></a>CDaoTableDef::GetIndexInfo

이 멤버 함수를 호출하여 tabledef에 정의된 인덱스에 대한 다양한 종류의 정보를 가져옵니다.

```cpp
void GetIndexInfo(
    int nIndex,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetIndexInfo(
    LPCTSTR lpszName,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
컬렉션의 위치에 따라 조회하기 위해 테이블의 0기반 인덱스 컬렉션에 있는 인덱스 개체의 숫자 인덱스입니다.

*인덱스 정보*<br/>
[CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조에 대한 참조입니다.

*dwInfoOptions*<br/>
검색할 인덱스에 대한 정보를 지정하는 옵션입니다. 사용 가능한 옵션은 함수가 반환되는 원인과 함께 여기에 나열됩니다.

- `AFX_DAO_PRIMARY_INFO`이름, 필드 정보, 필드. 가장 빠른 성능을 위해 이 옵션을 사용합니다.

- `AFX_DAO_SECONDARY_INFO`기본 정보 및 추가: 기본, 고유, 클러스터된, Null 무시, 필수, 외국어

- `AFX_DAO_ALL_INFO`기본 및 보조 정보, 플러스: 고유 개수

*lpszName*<br/>
이름으로 조회하기 위해 인덱스 개체의 이름에 대한 포인터입니다.

### <a name="remarks"></a>설명

한 버전의 함수를 사용하면 컬렉션의 위치에 따라 인덱스를 조회할 수 있습니다. 다른 버전에서는 이름으로 인덱스를 조회할 수 있습니다.

반환된 정보에 대한 설명은 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조를 참조하십시오. 이 구조에는 *dwInfoOptions*에 대한 설명에 위에 나열된 정보 항목에 해당하는 멤버가 있습니다. 한 수준에서 정보를 요청하면 이전 수준에 대한 정보도 얻을 수 있습니다.

관련 정보는 DAO 도움말의 "속성 속성" 항목을 참조하십시오.

## <a name="cdaotabledefgetname"></a><a name="getname"></a>CDaoTableDef::GetName

이 멤버 함수를 호출하여 기본 테이블의 사용자 정의 이름을 가져옵니다.

```
CString GetName();
```

### <a name="return-value"></a>Return Value

테이블에 대한 사용자 정의 이름입니다.

### <a name="remarks"></a>설명

이 이름은 문자로 시작하여 최대 64자를 포함할 수 있습니다. 숫자와 밑줄 문자를 포함할 수 있지만 문장 부호 나 공백을 포함 할 수는 없습니다.

관련 정보는 DAO 도움말의 "이름 속성" 항목을 참조하십시오.

## <a name="cdaotabledefgetrecordcount"></a><a name="getrecordcount"></a>CDaoTableDef::GetRecordCount

`CDaoTableDef` 이 멤버 함수를 호출하여 개체에 있는 레코드 수를 확인합니다.

```
long GetRecordCount();
```

### <a name="return-value"></a>Return Value

tabledef 개체에서 액세스하는 레코드 수입니다.

### <a name="remarks"></a>설명

테이블 `GetRecordCount` 형식 `CDaoTableDef` 개체에 대 한 호출은 테이블의 대략적인 레코드 수를 반영 하 고 테이블 레코드가 추가 되 고 삭제 될 때 즉시 영향을 받습니다. 롤백된 트랜잭션은 [CDaoWorkSpace::CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase)를 호출할 때까지 레코드 수의 일부로 표시됩니다. 레코드가 없는 `CDaoTableDef` 개체에는 레코드 개수 속성 설정이 0입니다. 연결된 테이블 또는 ODBC 데이터베이스로 `GetRecordCount` 작업할 때는 항상 -1을 반환합니다.

관련 정보는 DAO 도움말의 "RecordCount 속성" 항목을 참조하십시오.

## <a name="cdaotabledefgetsourcetablename"></a><a name="getsourcetablename"></a>CDaoTableDef::GetSourceTableName

원본 데이터베이스에서 연결된 테이블의 이름을 검색하려면 이 멤버 함수를 호출합니다.

```
CString GetSourceTableName();
```

### <a name="return-value"></a>Return Value

연결된 `CString` 테이블의 소스 이름을 지정하는 개체 또는 네이티브 데이터 테이블인 빈 문자열을 지정합니다.

### <a name="remarks"></a>설명

연결된 테이블은 Microsoft Jet 데이터베이스에 연결된 다른 데이터베이스의 테이블입니다. 연결된 테이블에 대한 데이터는 외부 데이터베이스에 남아 있으며, 여기서 다른 응용 프로그램에서 조작할 수 있습니다.

관련 정보는 DAO 도움말의 "SourceTableName 속성" 항목을 참조하십시오.

## <a name="cdaotabledefgetvalidationrule"></a><a name="getvalidationrule"></a>CDaoTableDef::Getvalidation규칙

이 멤버 함수를 호출하여 tabledef에 대한 유효성 검사 규칙을 검색합니다.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Return Value

필드에 `CString` 있는 데이터가 테이블에 변경또는 추가될 때 데이터의 유효성을 검사하는 개체입니다.

### <a name="remarks"></a>설명

유효성 검사 규칙은 업데이트 작업과 관련하여 사용됩니다. tabledef에 유효성 검사 규칙이 포함된 경우 해당 tabledef에 대한 업데이트는 데이터가 변경되기 전에 미리 지정된 조건과 일치해야 합니다. 변경 내용이 조건과 일치하지 않으면 [GetValidationText](#getvalidationtext) 값을 포함하는 예외가 throw됩니다. 개체의 `CDaoTableDef` 경우 `CString` 연결된 테이블에 대해서만 읽기 전용이고 기본 테이블에 대한 읽기/쓰기입니다.

관련 정보는 DAO 도움말의 "유효성 검사규칙 속성" 항목을 참조하십시오.

## <a name="cdaotabledefgetvalidationtext"></a><a name="getvalidationtext"></a>CDaoTableDef::Getvalidation텍스트

사용자가 유효성 검사 규칙과 일치하지 않는 데이터를 입력할 때 표시할 문자열을 검색하려면 이 함수를 호출합니다.

```
CString GetValidationText();
```

### <a name="return-value"></a>Return Value

사용자가 `CString` 유효성 검사 규칙과 일치하지 않는 데이터를 입력하는 경우 표시되는 텍스트를 지정하는 개체입니다.

### <a name="remarks"></a>설명

개체의 `CDaoTableDef` 경우 `CString` 연결된 테이블에 대해서만 읽기 전용이고 기본 테이블에 대한 읽기/쓰기입니다.

관련 정보는 DAO 도움말의 "유효성 검사텍스트 속성" 항목을 참조하십시오.

## <a name="cdaotabledefisopen"></a><a name="isopen"></a>CDaoTableDef::이스오픈

이 멤버 함수를 호출하여 개체가 `CDaoTableDef` 현재 열려 있는지 확인합니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Return Value

개체가 열려 `CDaoTableDef` 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

## <a name="cdaotabledefm_pdatabase"></a><a name="m_pdatabase"></a>CDaoTableDef::m_pDatabase

이 테이블에 대한 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체에 대한 포인터를 포함합니다.

### <a name="remarks"></a>설명

## <a name="cdaotabledefm_pdaotabledef"></a><a name="m_pdaotabledef"></a>CDaoTableDef::m_pDAOTableDef

개체의 기본을 기본으로 하는 DAO tabledef `CDaoTableDef` 개체에 대 한 OLE 인터페이스에 대 한 포인터를 포함 합니다.

### <a name="remarks"></a>설명

DAO 인터페이스에 직접 액세스해야 하는 경우 이 포인터를 사용합니다.

## <a name="cdaotabledefopen"></a><a name="open"></a>CDaoTableDef::열기

이 멤버 함수를 호출하여 데이터베이스의 TableDef 컬렉션에 이전에 저장된 테이블def를 엽니다.

```
virtual void Open(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
테이블 이름을 지정하는 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cdaotabledefrefreshlink"></a><a name="refreshlink"></a>CDaoTableDef::새로 고침 링크

연결된 테이블에 대한 연결 정보를 업데이트하려면 이 멤버 함수를 호출합니다.

```cpp
void RefreshLink();
```

### <a name="remarks"></a>설명

해당 `CDaoTableDef` 개체에 `RefreshLink` [SetConnect를](#setconnect) 호출 한 다음 멤버 함수를 사용 하 여 정보를 업데이트 하 여 연결 된 테이블에 대 한 연결 정보를 변경 합니다. 호출할 `RefreshLink`때 연결된 테이블의 속성은 변경되지 않습니다.

수정된 연결 정보가 강제로 적용되려면 이 테이블def를 기반으로 열린 모든 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체를 닫아야 합니다.

관련 정보는 DAO 도움말의 "RefreshLink 방법" 항목을 참조하십시오.

## <a name="cdaotabledefsetattributes"></a><a name="setattributes"></a>CDaoTableDef::설정 속성

개체의 하나 이상의 특성을 나타내는 `CDaoTableDef` 값을 설정합니다.

```cpp
void SetAttributes(long lAttributes);
```

### <a name="parameters"></a>매개 변수

*lAttributes*<br/>
테이블의 특성은 `CDaoTableDef` 개체로 표시되며 이러한 상수의 합계일 수 있습니다.

|상수|Description|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet 데이터베이스 엔진을 사용하는 데이터베이스의 경우 테이블이 단독으로 사용하기 위해 열린 연결된 테이블임을 나타냅니다.|
|`dbAttachSavePWD`|Microsoft Jet 데이터베이스 엔진을 사용하는 데이터베이스의 경우 연결된 테이블의 사용자 ID와 암호가 연결 정보와 함께 저장됨을 나타냅니다.|
|`dbSystemObject`|테이블이 Microsoft Jet 데이터베이스 엔진에서 제공하는 시스템 테이블임을 나타냅니다.|
|`dbHiddenObject`|테이블이 Microsoft Jet 데이터베이스 엔진에서 제공하는 숨겨진 테이블임을 나타냅니다.|

### <a name="remarks"></a>설명

여러 특성을 설정할 때 bitwise-OR 연산자사용을 사용하여 적절한 상수를 합산하여 특성을 결합할 수 있습니다. 연결되지 않은 테이블을 설정하면 `dbAttachExclusive` 예외가 발생합니다. 다음 값을 결합하면 예외가 생성됩니다.

- **dbAttach독점 &#124; dbAttachedODBC**

- **dbAttachSavePWD &#124; dbAttachedtable**

관련 정보는 DAO 도움말의 "속성 속성" 항목을 참조하십시오.

## <a name="cdaotabledefsetconnect"></a><a name="setconnect"></a>CDaoTableDef::세트커넥트

연결된 `CDaoTableDef` 테이블을 나타내는 개체의 경우 문자열 개체는 하나 또는 두 개의 부분(데이터베이스 형식 지정자 및 데이터베이스 경로)으로 구성됩니다.

```cpp
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>매개 변수

*lpszConnect*<br/>
ODBC 또는 설치 가능한 ISAM 드라이버에 전달할 추가 매개 변수를 지정하는 문자열 식에 대한 포인터입니다.

### <a name="remarks"></a>설명

아래 표에 표시된 경로는 데이터베이스 파일을 포함하는 디렉터리에 대한 전체 경로이며 식별자 "DATABASE="앞에 와야 합니다. 경우에 따라(Microsoft Jet 및 Microsoft Excel 데이터베이스와 마찬가지로) 특정 파일 이름이 데이터베이스 경로 인수에 포함됩니다.

> [!NOTE]
> "DATABASE=drive:\\\path"라는 형식의 경로 문에 등색 기호 주위에 공백을 포함하지 마십시오. 이렇게 하면 예외가 throw되고 연결이 실패합니다.

다음 표에서는 가능한 데이터베이스 유형과 해당 데이터베이스 지정자 및 경로를 보여 주었습니다.

|데이터베이스 유형|지정자|경로|
|-------------------|---------------|----------|
|Jet 데이터베이스 엔진을 사용하는 데이터베이스|"[ `database`];"|" `drive`\\\ :*경로*\\\ *파일 이름*. MDB"|
|dBASE III|"dBASE III;"|" `drive`\\\ :*경로*"|
|dBASE IV|"dBASE IV;"|" `drive`\\\ :*경로*"|
|dBASE 5|"dBASE 5.0;"|" `drive`\\\ :*경로*"|
|역설 3.x|"역설 3.x;"|" `drive`\\\ :*경로*"|
|역설 4.x|"역설 4.x;"|" `drive`\\\ :*경로*"|
|역설 5.x|"역설 5.x;"|" `drive`\\\ :*경로*"|
|엑셀 3.0|"엑셀 3.0;"|" `drive`\\\ :*경로*\\\ *파일 이름*. "XLS"|
|엑셀 4.0|"엑셀 4.0;"|" `drive`\\\ :*경로*\\\ *파일 이름*. "XLS"|
|엑셀 5.0 또는 엑셀 95|"엑셀 5.0;"|" `drive`\\\ :*경로*\\\ *파일 이름*. "XLS"|
|엑셀 97|"엑셀 8.0;"|" `drive`\\\ :*경로*\ *파일 이름*. "XLS"|
|HTML 가져오기|"HTML 가져오기;"|" `drive`\\\ :*경로*\ *파일 이름*"|
|HTML 내보내기|"HTML 내보내기;"|" `drive`\\\ :*경로*"|
|텍스트|"텍스트;"|"드라이브:\\\경로"|
|ODBC|"ODBC; 데이터베이스= `database`; UID = *사용자*; PWD = *암호;* DSN = *데이터 원본 이름;* 로그인 시간 시간 = *초;*" (모든 서버에 대한 전체 연결 문자열이 아닐 수도 있습니다. 매개 변수 사이에 공백을 두지 않는 것이 매우 중요합니다.|None|
|Exchange|"교환;<br /><br /> MAPILEVEL = *폴더 경로;*<br /><br /> [테이블타이핑={0 &#124; 1};]<br /><br /> [프로필 = *프로필;]*<br /><br /> [PWD = *암호;]*<br /><br /> [데이터베이스 `database`= ;]"|*"드라이브*\\\ :*경로*\\\ *파일 이름*. MDB"|

> [!NOTE]
> Btrieve는 DAO 3.5에서 더 이상 지원되지 않습니다.

연결 문자열에서 이중 백슬래시()를\\\\사용해야 합니다. 을 사용하여 `SetConnect`기존 연결의 속성을 수정한 경우 이후에 [RefreshLink](#refreshlink)를 호출해야 합니다. 을 사용하여 `SetConnect`연결 속성을 초기화하는 경우 `RefreshLink`호출할 필요는 없지만 이렇게 하도록 선택해야 합니다.

암호가 필요하지만 제공되지 않은 경우 ODBC 드라이버는 테이블에 처음 액세스할 때 로그인 대화 상자를 표시하고 연결이 닫혀 다시 열리면 다시 표시됩니다.

멤버 함수에 소스 인수를 `CDaoTableDef` 제공하여 개체에 대한 `Create` 연결 문자열을 설정할 수 있습니다. 설정을 확인하여 데이터베이스의 유형, 경로, 사용자 ID, 암호 또는 ODBC 데이터 원본을 확인할 수 있습니다. 자세한 내용은 특정 드라이버에 대한 설명서를 참조하십시오.

관련 정보는 DAO 도움말의 "속성 연결" 항목을 참조하십시오.

## <a name="cdaotabledefsetname"></a><a name="setname"></a>CDaoTableDef::SetName

이 멤버 함수를 호출하여 테이블에 대한 사용자 정의 이름을 설정합니다.

```cpp
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
테이블의 이름을 지정하는 문자열 식에 대한 포인터입니다.

### <a name="remarks"></a>설명

이름은 문자로 시작해야 하며 최대 64자를 포함할 수 있습니다. 숫자와 밑줄 문자를 포함할 수 있지만 문장 부호 나 공백을 포함 할 수는 없습니다.

관련 정보는 DAO 도움말의 "이름 속성" 항목을 참조하십시오.

## <a name="cdaotabledefsetsourcetablename"></a><a name="setsourcetablename"></a>CDaoTableDef::SetSourceTableName

이 멤버 함수를 호출하여 연결된 테이블의 이름 또는 `CDaoTableDef` 개체의 기반이 되는 기본 테이블의 이름을 데이터의 원래 원본에 있는 대로 지정합니다.

```cpp
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```

### <a name="parameters"></a>매개 변수

*lpszSrcTableName*<br/>
외부 데이터베이스에서 테이블 이름을 지정하는 문자열 식에 대한 포인터입니다. 기본 테이블의 경우 설정은 빈 문자열("")입니다.

### <a name="remarks"></a>설명

그런 다음 [RefreshLink](#refreshlink)를 호출해야 합니다. 이 속성 설정은 기본 테이블에 대해 비어 있으며 연결된 테이블 또는 컬렉션에 추가되지 않은 개체에 대해 읽기/쓰기가 비어 있습니다.

관련 정보는 DAO 도움말의 "SourceTableName 속성" 항목을 참조하십시오.

## <a name="cdaotabledefsetvalidationrule"></a><a name="setvalidationrule"></a>CDaoTableDef::집합 유효성 검사규칙

이 멤버 함수를 호출하여 tabledef에 대한 유효성 검사 규칙을 설정합니다.

```cpp
void SetValidationRule(LPCTSTR lpszValidationRule);
```

### <a name="parameters"></a>매개 변수

*lpsz유효성 검사규칙*<br/>
작업의 유효성을 검사하는 문자열 식에 대한 포인터입니다.

### <a name="remarks"></a>설명

유효성 검사 규칙은 업데이트 작업과 관련하여 사용됩니다. tabledef에 유효성 검사 규칙이 포함된 경우 해당 tabledef에 대한 업데이트는 데이터가 변경되기 전에 미리 지정된 조건과 일치해야 합니다. 변경 내용이 조건과 일치하지 않으면 [GetValidationText](#getvalidationtext) 의 텍스트가 포함된 예외가 표시됩니다.

유효성 검사는 Microsoft Jet 데이터베이스 엔진을 사용하는 데이터베이스에대해서만 지원됩니다. 식은 사용자 정의 함수, 도메인 집계 함수, SQL 집계 함수 또는 쿼리를 참조할 수 없습니다. `CDaoTableDef` 개체에 대한 유효성 검사 규칙은 해당 개체의 여러 필드를 참조할 수 있습니다.

예를 들어 *hire_date* 및 *termination_date*라는 필드의 경우 유효성 검사 규칙은 다음과 같은 것일 수 있습니다.

[!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]

관련 정보는 DAO 도움말의 "유효성 검사규칙 속성" 항목을 참조하십시오.

## <a name="cdaotabledefsetvalidationtext"></a><a name="setvalidationtext"></a>CDaoTableDef::집합 유효성 검사 텍스트

이 멤버 함수를 호출하여 Microsoft Jet 데이터베이스 `CDaoTableDef` 엔진에서 지원하는 기본 기본 테이블이 있는 개체에 대한 유효성 검사 규칙의 예외 텍스트를 설정합니다.

```cpp
void SetValidationText(LPCTSTR lpszValidationText);
```

### <a name="parameters"></a>매개 변수

*lpsz유효성 검사텍스트*<br/>
입력한 데이터가 유효하지 않은 경우 표시되는 텍스트를 지정하는 문자열 식에 대한 포인터입니다.

### <a name="remarks"></a>설명

첨부된 테이블의 유효성 검사 텍스트를 설정할 수 없습니다.

관련 정보는 DAO 도움말의 "유효성 검사텍스트 속성" 항목을 참조하십시오.

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDao데이터베이스 클래스](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDao레코드 집합 클래스](../../mfc/reference/cdaorecordset-class.md)
