---
title: CDaoQueryDef 클래스
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDef
- AFXDAO/CDaoQueryDef
- AFXDAO/CDaoQueryDef::CDaoQueryDef
- AFXDAO/CDaoQueryDef::Append
- AFXDAO/CDaoQueryDef::CanUpdate
- AFXDAO/CDaoQueryDef::Close
- AFXDAO/CDaoQueryDef::Create
- AFXDAO/CDaoQueryDef::Execute
- AFXDAO/CDaoQueryDef::GetConnect
- AFXDAO/CDaoQueryDef::GetDateCreated
- AFXDAO/CDaoQueryDef::GetDateLastUpdated
- AFXDAO/CDaoQueryDef::GetFieldCount
- AFXDAO/CDaoQueryDef::GetFieldInfo
- AFXDAO/CDaoQueryDef::GetName
- AFXDAO/CDaoQueryDef::GetODBCTimeout
- AFXDAO/CDaoQueryDef::GetParameterCount
- AFXDAO/CDaoQueryDef::GetParameterInfo
- AFXDAO/CDaoQueryDef::GetParamValue
- AFXDAO/CDaoQueryDef::GetRecordsAffected
- AFXDAO/CDaoQueryDef::GetReturnsRecords
- AFXDAO/CDaoQueryDef::GetSQL
- AFXDAO/CDaoQueryDef::GetType
- AFXDAO/CDaoQueryDef::IsOpen
- AFXDAO/CDaoQueryDef::Open
- AFXDAO/CDaoQueryDef::SetConnect
- AFXDAO/CDaoQueryDef::SetName
- AFXDAO/CDaoQueryDef::SetODBCTimeout
- AFXDAO/CDaoQueryDef::SetParamValue
- AFXDAO/CDaoQueryDef::SetReturnsRecords
- AFXDAO/CDaoQueryDef::SetSQL
- AFXDAO/CDaoQueryDef::m_pDAOQueryDef
- AFXDAO/CDaoQueryDef::m_pDatabase
helpviewer_keywords:
- CDaoQueryDef [MFC], CDaoQueryDef
- CDaoQueryDef [MFC], Append
- CDaoQueryDef [MFC], CanUpdate
- CDaoQueryDef [MFC], Close
- CDaoQueryDef [MFC], Create
- CDaoQueryDef [MFC], Execute
- CDaoQueryDef [MFC], GetConnect
- CDaoQueryDef [MFC], GetDateCreated
- CDaoQueryDef [MFC], GetDateLastUpdated
- CDaoQueryDef [MFC], GetFieldCount
- CDaoQueryDef [MFC], GetFieldInfo
- CDaoQueryDef [MFC], GetName
- CDaoQueryDef [MFC], GetODBCTimeout
- CDaoQueryDef [MFC], GetParameterCount
- CDaoQueryDef [MFC], GetParameterInfo
- CDaoQueryDef [MFC], GetParamValue
- CDaoQueryDef [MFC], GetRecordsAffected
- CDaoQueryDef [MFC], GetReturnsRecords
- CDaoQueryDef [MFC], GetSQL
- CDaoQueryDef [MFC], GetType
- CDaoQueryDef [MFC], IsOpen
- CDaoQueryDef [MFC], Open
- CDaoQueryDef [MFC], SetConnect
- CDaoQueryDef [MFC], SetName
- CDaoQueryDef [MFC], SetODBCTimeout
- CDaoQueryDef [MFC], SetParamValue
- CDaoQueryDef [MFC], SetReturnsRecords
- CDaoQueryDef [MFC], SetSQL
- CDaoQueryDef [MFC], m_pDAOQueryDef
- CDaoQueryDef [MFC], m_pDatabase
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
ms.openlocfilehash: ed298c40daa9485683d0b989e47b97fdce9f6562
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754705"
---
# <a name="cdaoquerydef-class"></a>CDaoQueryDef 클래스

일반적으로 데이터베이스에 저장되는 쿼리 정의 또는 "querydef"를 나타냅니다.

## <a name="syntax"></a>구문

```
class CDaoQueryDef : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDao쿼리데프::CDaoQueryDef](#cdaoquerydef)|`CDaoQueryDef` 개체를 생성합니다. 다음 `Open` 전화 `Create`또는 , 필요에 따라.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDao쿼리데프::부속](#append)|쿼리 def를 데이터베이스의 QueryDefs 컬렉션에 저장된 쿼리로 보냅니다.|
|[CDao쿼리데프::캔업데이트](#canupdate)|쿼리가 데이터베이스를 업데이트할 수 있는 경우 0이 아닌 것을 반환합니다.|
|[CDao쿼리데프::닫기](#close)|쿼리 def 개체를 닫습니다. 당신이 그것을 완료하면 C ++ 개체를 파괴한다.|
|[CDao쿼리데프::만들기](#create)|기본 DAO 쿼리 def 개체를 만듭니다. 쿼리 def를 임시 쿼리로 사용하거나 호출하여 `Append` 데이터베이스에 저장합니다.|
|[CDao쿼리데프::실행](#execute)|querydef 개체에 의해 정의된 쿼리를 실행합니다.|
|[CDao쿼리데프::GetConnect](#getconnect)|쿼리 def와 연결된 연결 문자열을 반환합니다. 연결 문자열은 데이터 원본을 식별합니다. (SQL 통과 쿼리에만, 그렇지 않으면 빈 문자열입니다.)|
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|저장된 쿼리가 만들어진 날짜를 반환합니다.|
|[CDao쿼리데프::GetDateLast업데이트](#getdatelastupdated)|저장된 쿼리가 마지막으로 업데이트된 날짜를 반환합니다.|
|[CDao쿼리데프::겟필드카운트](#getfieldcount)|쿼리 def에 의해 정의된 필드 수를 반환합니다.|
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|쿼리에 정의된 지정된 필드에 대한 정보를 반환합니다.|
|[CDao쿼리데프::GetName](#getname)|쿼리 def의 이름을 반환합니다.|
|[CDao쿼리데프::GetODBC타임아웃](#getodbctimeout)|쿼리 def가 실행될 때 ODBC(ODBC 쿼리의 경우)에서 사용하는 시간 시간 값을 반환합니다. 이렇게 하면 쿼리의 작업이 완료될 수 있는 길이가 결정됩니다.|
|[CDao쿼리데프::GetParameterCount](#getparametercount)|쿼리에 대해 정의된 매개 변수 수를 반환합니다.|
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|지정된 매개 변수에 대한 정보를 쿼리에 반환합니다.|
|[CDao쿼리데프::겟파라임밸류](#getparamvalue)|지정된 매개 변수의 값을 쿼리에 반환합니다.|
|[CDao쿼리데프::겟레코드영향](#getrecordsaffected)|작업 쿼리의 영향을 받는 레코드 수를 반환합니다.|
|[CDao쿼리데프::겟리턴스레코드](#getreturnsrecords)|querydef에 의해 정의된 쿼리가 레코드를 반환하는 경우 0이 아닌 것을 반환합니다.|
|[CDao쿼리데프::겟SQL](#getsql)|querydef에 의해 정의된 쿼리를 지정하는 SQL 문자열을 반환합니다.|
|[CDao쿼리데프::GetType](#gettype)|삭제, 업데이트, 추가, 테이블 만들기 등과 같은 쿼리 유형을 반환합니다.|
|[CDao쿼리데프::이스오픈](#isopen)|쿼리 def가 열려 있고 실행할 수 있는 경우 0이 아닌 것을 반환합니다.|
|[CDao쿼리데프::열기](#open)|데이터베이스의 QueryDefs 컬렉션에 저장된 기존 쿼리 def를 엽니다.|
|[CDao쿼리데프::세트커넥트](#setconnect)|ODBC 데이터 원본에서 SQL 통과 쿼리에 대한 연결 문자열을 설정합니다.|
|[CDao쿼리데프::세트네임](#setname)|쿼리 def를 만들 때 사용 되는 이름을 대체 하는 저장 된 쿼리의 이름을 설정 합니다.|
|[CDao쿼리데프::SetODBC타임아웃](#setodbctimeout)|쿼리 def가 실행될 때 ODBC(ODBC 쿼리의 경우)에서 사용하는 시간 시간 값을 설정합니다.|
|[CDao쿼리데프::세트파라임밸류](#setparamvalue)|지정된 매개 변수의 값을 쿼리에 설정합니다.|
|[CDao쿼리데프::세트리턴스레코드](#setreturnsrecords)|querydef 레코드를 반환 하는지 여부를 지정 합니다. 이 특성을 TRUE로 설정하면 SQL 통과 쿼리에만 유효합니다.|
|[CDao쿼리데프::SetSQL](#setsql)|쿼리 def에 의해 정의된 쿼리를 지정하는 SQL 문자열을 설정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDao쿼리데프::m_pDAOQueryDef](#m_pdaoquerydef)|기본 DAO 쿼리 def 개체에 대한 OLE 인터페이스에 대한 포인터입니다.|
|[CDao쿼리데프::m_pDatabase](#m_pdatabase)|쿼리def가 `CDaoDatabase` 연결된 개체에 대한 포인터입니다. 쿼리 def가 데이터베이스에 저장되거나 저장되지 않을 수 있습니다.|

## <a name="remarks"></a>설명

querydef는 쿼리를 설명하는 SQL 문과 "만든 날짜" 및 "ODBC 시간 지정"과 같은 해당 속성을 포함하는 데이터 액세스 개체입니다. 또한 임시 querydef 개체를 저장하지 않고 만들 수 있지만 일반적으로 재사용되는 쿼리를 데이터베이스에 저장하는 것이 편리하고 훨씬 효율적입니다. [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체는 저장된 쿼리 defs를 포함하는 QueryDefs 컬렉션이라는 컬렉션을 유지 관리합니다.

> [!NOTE]
> DAO 데이터베이스 클래스는 ODBC(개방형 데이터베이스 연결)를 기반으로 하는 MFC 데이터베이스 클래스와 구별됩니다. 모든 DAO 데이터베이스 클래스 이름에는 "CDao" 접두사가 있습니다. DAO 클래스를 사용하여 ODBC 데이터 원본에 계속 액세스할 수 있습니다. 일반적으로 DAO를 기반으로 하는 MFC 클래스는 ODBC를 기반으로 하는 MFC 클래스보다 더 유능합니다. DAO 기반 클래스는 자체 데이터베이스 엔진을 통해 ODBC 드라이버를 통해 데이터에 액세스할 수 있습니다. 또한 DAO 기반 클래스는 DAO를 직접 호출하지 않고도 클래스를 통해 테이블을 추가하는 것과 같은 DDL(데이터 정의 언어) 작업을 지원합니다.

## <a name="usage"></a>사용

querydef 개체를 사용하여 기존저장된 쿼리로 작업하거나 새 저장된 쿼리 또는 임시 쿼리를 만듭니다.

1. 모든 경우에 먼저 쿼리가 `CDaoQueryDef` 속한 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체에 대한 포인터를 제공하는 개체를 생성합니다.

1. 그런 다음 원하는 항목에 따라 다음을 수행합니다.

   - 기존에 저장된 쿼리를 사용하려면 querydef 개체의 [Open](#open) 멤버 함수를 호출하여 저장된 쿼리의 이름을 제공합니다.

   - 저장된 새 쿼리를 만들려면 querydef 개체의 멤버 [만들기](#create) 함수를 호출하여 쿼리 이름을 제공합니다. 그런 다음 데이터베이스의 QueryDefs 컬렉션에 쿼리를 더하여 쿼리를 저장하려면 [Append를](#append) 호출합니다. `Create`querydef를 열린 상태로 전환하므로 호출 `Create` 한 후에는 호출하지 `Open`않습니다.

   - 임시 쿼리 def를 만들려면 을 호출합니다. `Create` 쿼리 이름에 대한 빈 문자열을 전달합니다. `Append`를 호출하지 마세요.

querydef 개체 사용을 완료하면 [해당 닫기](#close) 멤버 함수를 호출합니다. 그런 다음 querydef 개체를 삭제합니다.

> [!TIP]
> 저장된 쿼리를 만드는 가장 쉬운 방법은 Microsoft Access를 사용하여 쿼리를 만들고 데이터베이스에 저장하는 것입니다. 그런 다음 MFC 코드에서 열고 사용할 수 있습니다.

## <a name="purposes"></a>목적

다음 용도로 querydef 개체를 사용할 수 있습니다.

- 개체를 `CDaoRecordset` 만들려면

- 개체의 `Execute` 멤버 함수를 호출하여 작업 쿼리 또는 SQL 통과 쿼리를 직접 실행하려면

select, 작업, 크로스탭, 삭제, 업데이트, 추가, 메이크 테이블, 데이터 정의, SQL 통과, 공용 구조체 및 대량 쿼리를 비롯한 모든 유형의 쿼리에 querydef 개체를 사용할 수 있습니다. 쿼리 유형은 제공하는 SQL 문의 내용에 따라 결정됩니다. 쿼리 유형에 대한 자세한 `Execute` 내용은 및 [GetType](#gettype) 멤버 함수를 참조하십시오. 레코드 집합은 일반적으로 SELECT를 사용하는 쿼리인 행 반환 쿼리에 사용됩니다. ** 에서** 키워드입니다. `Execute`대량 작업에 가장 일반적으로 사용됩니다. 자세한 내용은 [실행](#execute) 및 [CDaoRecordset을](../../mfc/reference/cdaorecordset-class.md)참조하십시오.

## <a name="querydefs-and-recordsets"></a>쿼리 데프 및 레코드 집합

querydef 개체를 사용하여 `CDaoRecordset` 개체를 만들려면 일반적으로 위에서 설명한 대로 querydef를 만들거나 엽니다. 그런 다음 [CDaoRecordset::Open을](../../mfc/reference/cdaorecordset-class.md#open)호출할 때 querydef 개체에 대한 포인터를 전달하여 레코드 집합 개체를 생성합니다. 전달하는 쿼리 def는 열린 상태여야 합니다. 자세한 내용은 클래스 [CDaoRecordset을](../../mfc/reference/cdaorecordset-class.md)참조하십시오.

열려 있는 상태가 아니면 querydef를 사용하여 레코드 집합(querydef에 가장 많이 사용)을 만들 수 없습니다. 또는 을 `Open` 호출하여 querydef를 열린 `Create`상태로 넣습니다.

## <a name="external-databases"></a>외부 데이터베이스

Querydef 개체는 외부 데이터베이스 엔진의 기본 SQL 방언을 사용하는 기본 방법입니다. 예를 들어 Microsoft SQL Server에서 사용되는 Transact SQL 쿼리를 만들어 쿼리 def 개체에 저장할 수 있습니다. Microsoft Jet 데이터베이스 엔진을 기반으로 하지 않는 SQL 쿼리를 사용해야 하는 경우 외부 데이터 원본을 가리키는 연결 문자열을 제공해야 합니다. 유효한 연결 문자열이 있는 쿼리는 데이터베이스 엔진을 우회하고 처리를 위해 쿼리를 외부 데이터베이스 서버로 직접 전달합니다.

> [!TIP]
> ODBC 테이블을 사용하여 작업하는 기본 방법은 Microsoft Jet(에 연결하는 것입니다. MDB) 데이터베이스.

관련 정보는 DAO SDK의 "쿼리데프 개체", "쿼리데프 컬렉션" 및 "CdbDatabase 개체" 항목을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDaoQueryDef`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="cdaoquerydefappend"></a><a name="append"></a>CDao쿼리데프::부속

Create를 [호출한](#create) 후 이 멤버 함수를 호출하여 새 querydef 개체를 만듭니다.

```
virtual void Append();
```

### <a name="remarks"></a>설명

`Append`데이터베이스의 QueryDefs 컬렉션에 개체를 더하여 데이터베이스에 쿼리 def를 저장합니다. querydef를 추가하지 않고 임시 개체로 사용할 수 있지만 유지하려면 을 호출해야 `Append`합니다.

임시 쿼리 def 개체를 추가하려고 하면 MFC는 [CDaoException](../../mfc/reference/cdaoexception-class.md)형식의 예외를 throw합니다.

## <a name="cdaoquerydefcanupdate"></a><a name="canupdate"></a>CDao쿼리데프::캔업데이트

이 멤버 함수를 호출하여 이름 또는 SQL 문자열 변경과 같이 querydef를 수정할 수 있는지 여부를 결정합니다.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Return Value

쿼리 def를 수정할 수 있는 경우 0이 아닌 경우; 그렇지 않으면 0.

### <a name="remarks"></a>설명

다음과 같은 경우 쿼리 def를 수정할 수 있습니다.

- 열려 있는 읽기 전용 데이터베이스를 기반으로 하지 않습니다.

- 데이터베이스에 대한 업데이트 권한이 있습니다.

   보안 기능을 구현했는지 여부에 따라 다릅니다. MFC는 보안에 대한 지원을 제공하지 않습니다. DAO에 직접 전화하거나 Microsoft Access를 사용하여 직접 구현해야 합니다. DAO 도움말에서 "사용 권한 속성" 항목을 참조하십시오.

## <a name="cdaoquerydefcdaoquerydef"></a><a name="cdaoquerydef"></a>CDao쿼리데프::CDaoQueryDef

`CDaoQueryDef` 개체를 생성합니다.

```
CDaoQueryDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>매개 변수

*p데이터베이스*<br/>
열려 있는 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

개체는 데이터베이스의 QueryDefs 컬렉션에 저장된 기존 쿼리def, 컬렉션에 저장할 새 쿼리 또는 저장할 임시 쿼리를 나타낼 수 있습니다. 다음 단계는 쿼리 def유형에 따라 다릅니다.

- 개체가 기존 쿼리 def를 나타내는 경우 개체의 [Open](#open) 멤버 함수를 호출하여 초기화합니다.

- 개체가 저장할 새 쿼리 def를 나타내는 경우 개체의 멤버 [만들기](#create) 함수를 호출합니다. 이렇게 하면 데이터베이스의 QueryDefs 컬렉션에 개체가 추가됩니다. 그런 `CDaoQueryDef` 다음 멤버 함수를 호출하여 개체의 특성을 설정합니다. 마지막으로, [호출 부속](#append).

- 개체가 임시 쿼리 def(데이터베이스에 저장되지 않음)를 `Create`나타내는 경우 쿼리 이름에 대한 빈 문자열을 전달합니다. 호출 `Create`한 후 해당 특성을 직접 설정하여 쿼리 def를 초기화합니다. `Append`를 호출하지 마세요.

쿼리 def의 특성을 설정하려면 [SetName,](#setname) [SetSQL,](#setsql) [SetConnect,](#setconnect) [SetODBCTimeout](#setodbctimeout)및 [SetReturnsRecords](#setreturnsrecords) 멤버 함수를 사용할 수 있습니다.

querydef 개체로 완료하면 해당 [멤버 닫기](#close) 함수를 호출합니다. querydef에 대한 포인터가 있는 경우 **delete** 연산자를 사용하여 C++ 개체를 삭제합니다.

## <a name="cdaoquerydefclose"></a><a name="close"></a>CDao쿼리데프::닫기

querydef 개체 사용을 완료할 때 이 멤버 함수를 호출합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

querydef를 닫으면 기본 DAO 개체가 해제되지만 저장된 DAO 쿼리 def `CDaoQueryDef` 개체 또는 C++ 개체는 삭제되지 않습니다. 이는 DAO의 데이터베이스 의 QueryDefs 컬렉션에서 쿼리 def를 삭제하는 [CDaoDatabase::DeleteQueryDef와](../../mfc/reference/cdaodatabase-class.md#deletequerydef)동일하지 않습니다(임시 쿼리def가 아닌 경우).

## <a name="cdaoquerydefcreate"></a><a name="create"></a>CDao쿼리데프::만들기

이 멤버 함수를 호출하여 저장된 새 쿼리 또는 새 임시 쿼리를 만듭니다.

```
virtual void Create(
    LPCTSTR lpszName = NULL,
    LPCTSTR lpszSQL = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
데이터베이스에 저장된 쿼리의 고유한 이름입니다. 문자열에 대한 자세한 내용은 DAO 도움말의 "CreateQueryDef 메서드" 항목을 참조하십시오. 기본값인 빈 문자열을 수락하면 임시 쿼리def가 만들어집니다. 이러한 쿼리는 QueryDefs 컬렉션에 저장 되지 않습니다.

*lpszSQL*<br/>
쿼리를 정의하는 SQL 문자열입니다. NULL의 기본값을 허용하는 경우 나중에 [SetSQL을](#setsql) 호출하여 문자열을 설정해야 합니다. 그때까지 쿼리는 정의되지 않습니다. 그러나 정의되지 않은 쿼리를 사용하여 레코드 집합을 열 수 있습니다. 자세한 내용은 비고를 참조하십시오. 쿼리 Defs 컬렉션에 쿼리 def를 추가하려면 먼저 SQL 문을 정의해야 합니다.

### <a name="remarks"></a>설명

*lpszName에*이름을 전달하는 경우 다음 데이터베이스의 QueryDefs 컬렉션에 쿼리 def를 저장 하려면 [Append를](#append) 호출할 수 있습니다. 그렇지 않으면 개체는 임시 쿼리def이며 저장되지 않습니다. 두 경우 모두 쿼리 def가 열려 있는 상태이며 이를 사용하여 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체를 만들거나 querydef의 [Execute](#execute) 멤버 함수를 호출할 수 있습니다.

*lpszSQL에서*SQL 문을 제공하지 않으면 쿼리를 실행할 수는 `Execute` 없지만 이를 사용하여 레코드 집합을 만들 수 있습니다. 이 경우 MFC는 레코드 집합의 기본 SQL 문을 사용합니다.

## <a name="cdaoquerydefexecute"></a><a name="execute"></a>CDao쿼리데프::실행

querydef 개체에 의해 정의 된 쿼리를 실행 하려면이 멤버 함수를 호출 합니다.

```
virtual void Execute(int nOptions = dbFailOnError);
```

### <a name="parameters"></a>매개 변수

*nOptions*<br/>
쿼리의 특성을 결정하는 정수입니다. 관련 정보는 DAO 도움말의 "방법 실행" 항목을 참조하십시오. 비트-OR 연산자(&#124;)를 사용하여 이 인수에 대한 다음 상수를 결합할 수 있습니다. ** **

- `dbDenyWrite`다른 사용자에게 쓰기 권한을 거부합니다.

- `dbInconsistent`일관되지 않은 업데이트.

- `dbConsistent`일관된 업데이트.

- `dbSQLPassThrough`SQL 통과. SQL 문을 처리를 위해 ODBC 데이터베이스에 전달합니다.

- `dbFailOnError`기본값입니다. 오류가 발생하면 업데이트를 롤백하고 사용자에게 오류를 보고합니다.

- `dbSeeChanges`다른 사용자가 편집중인 데이터를 변경하는 경우 런타임 오류를 생성합니다.

> [!NOTE]
> "일치하지 않음" 및 "일관성"이라는 용어에 대한 설명은 DAO 도움말의 "방법 실행" 항목을 참조하십시오.

### <a name="remarks"></a>설명

이러한 방식으로 실행에 사용되는 Querydef 개체는 다음 쿼리 유형 중 하나만 나타낼 수 있습니다.

- 작업 쿼리

- SQL 통과 쿼리

`Execute`선택 쿼리와 같은 레코드를 반환하는 쿼리에는 작동하지 않습니다. `Execute`일반적으로 **업데이트,** **INSERT**또는 **SELECT INTO와**같은 대량 작업 쿼리 또는 DDL(데이터 정의 언어) 작업에 사용됩니다.

> [!TIP]
> ODBC 데이터 원본으로 작업하는 기본 방법은 테이블을 Microsoft Jet(( MDB) 데이터베이스. 자세한 내용은 DAO 도움말의 "DAO를 사용하여 외부 데이터베이스에 액세스" 항목을 참조하십시오.

querydef 개체의 [GetRecords영향을 받는](#getrecordsaffected) 멤버 함수를 호출하여 가장 최근 `Execute` 호출의 영향을 받는 레코드 수를 확인합니다. 예를 들어 `GetRecordsAffected` 작업 쿼리를 실행할 때 삭제, 업데이트 또는 삽입된 레코드 수에 대한 정보를 반환합니다. 반환된 개수는 계단식 업데이트 또는 삭제가 적용되는 경우 관련 테이블의 변경 내용을 반영하지 않습니다.

둘 다 `dbInconsistent` 포함하거나 `dbConsistent` 둘 다 포함하지 않는 경우 `dbInconsistent`결과는 기본값입니다.

`Execute`레코드 집합을 반환하지 않습니다. 레코드를 선택하는 쿼리에서 사용하면 `Execute` MFC가 [CDaoException](../../mfc/reference/cdaoexception-class.md)형식의 예외를 throw합니다.

## <a name="cdaoquerydefgetconnect"></a><a name="getconnect"></a>CDao쿼리데프::GetConnect

이 멤버 함수를 호출하여 querydef의 데이터 원본과 연결된 연결 문자열을 가져옵니다.

```
CString GetConnect();
```

### <a name="return-value"></a>Return Value

쿼리 def에 대한 연결 문자열을 포함하는 [CString입니다.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>설명

이 함수는 ODBC 데이터 원본 및 특정 ISAM 드라이버에서만 사용됩니다. 그것은 마이크로 소프트 제트와 함께 사용되지 않습니다 (. MDB) 데이터베이스; 이 경우 `GetConnect` 빈 문자열을 반환합니다. 자세한 내용은 [SetConnect](#setconnect)을 참조하십시오.

> [!TIP]
> ODBC 테이블을 사용하여 작업하는 기본 방법은 에 연결하는 것입니다. MDB 데이터베이스. 자세한 내용은 DAO 도움말의 "DAO를 사용하여 외부 데이터베이스에 액세스" 항목을 참조하십시오.

연결 문자열에 대한 자세한 내용은 DAO 도움말의 "속성 연결" 항목을 참조하십시오.

## <a name="cdaoquerydefgetdatecreated"></a><a name="getdatecreated"></a>CDaoQueryDef::GetDateCreated

이 멤버 함수를 호출하여 querydef 개체가 만들어진 날짜를 가져옵니다.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Return Value

쿼리 def가 만들어진 날짜와 시간을 포함하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체입니다.

### <a name="remarks"></a>설명

관련 정보는 DAO 도움말의 "DateCreated, 마지막으로 업데이트된 속성" 항목을 참조하십시오.

## <a name="cdaoquerydefgetdatelastupdated"></a><a name="getdatelastupdated"></a>CDao쿼리데프::GetDateLast업데이트

이 멤버 함수를 호출하여 쿼리def 개체가 마지막으로 업데이트된 날짜(이름, SQL 문자열 또는 연결 문자열과 같은 속성이 변경된 경우)를 가져옵니다.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Return Value

쿼리 def가 마지막으로 업데이트된 날짜와 시간을 포함하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체입니다.

### <a name="remarks"></a>설명

관련 정보는 DAO 도움말의 "DateCreated, 마지막으로 업데이트된 속성" 항목을 참조하십시오.

## <a name="cdaoquerydefgetfieldcount"></a><a name="getfieldcount"></a>CDao쿼리데프::겟필드카운트

이 멤버 함수를 호출하여 쿼리의 필드 수를 검색합니다.

```
short GetFieldCount();
```

### <a name="return-value"></a>Return Value

쿼리에 정의된 필드 수입니다.

### <a name="remarks"></a>설명

`GetFieldCount`는 쿼리 def의 모든 필드를 반복하는 데 유용합니다. 이를 `GetFieldCount` 위해 [GetFieldInfo](#getfieldinfo).

## <a name="cdaoquerydefgetfieldinfo"></a><a name="getfieldinfo"></a>CDao쿼리데프::겟필드정보

이 멤버 함수를 호출하여 querydef에 정의된 필드에 대한 다양한 종류의 정보를 가져옵니다.

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
인덱스별 조회에 대한 querydef의 필드 컬렉션에서 원하는 필드의 0기반 인덱스입니다.

*Fieldinfo*<br/>
요청된 `CDaoFieldInfo` 정보를 반환하는 개체에 대한 참조입니다.

*dwInfoOptions*<br/>
검색할 필드에 대한 정보를 지정하는 옵션입니다. 사용 가능한 옵션은 함수가 반환되는 원인과 함께 여기에 나열됩니다.

- AFX_DAO_PRIMARY_INFO(기본값) 이름, 유형, 크기, 속성

- AFX_DAO_SECONDARY_INFO 기본 정보 플러스: 서수 위치, 필수, 제로 길이 허용, 소스 필드, 외국 이름, 소스 테이블, 정렬 순서

- AFX_DAO_ALL_INFO 기본 및 보조 정보 더하기: 기본값, 유효성 검사 텍스트, 유효성 검사 규칙

*lpszName*<br/>
이름으로 조회하기 위해 원하는 필드의 이름을 포함하는 문자열입니다. [CString](../../atl-mfc-shared/reference/cstringt-class.md)을 사용할 수 있습니다.

### <a name="remarks"></a>설명

*fieldinfo에서*반환되는 정보에 대한 설명은 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조를 참조하십시오. 이 구조에는 위의 *dwInfoOptions* 아래의 설명 정보에 해당하는 멤버가 있습니다. 한 수준의 정보를 요청하는 경우 이전 수준의 정보도 얻을 수 있습니다.

## <a name="cdaoquerydefgetname"></a><a name="getname"></a>CDao쿼리데프::GetName

이 멤버 함수를 호출하여 querydef로 표시되는 쿼리 이름을 검색합니다.

```
CString GetName();
```

### <a name="return-value"></a>Return Value

쿼리의 이름입니다.

### <a name="remarks"></a>설명

Querydef 이름은 고유한 사용자 정의 이름입니다. querydef 이름에 대한 자세한 내용은 DAO 도움말의 "이름 속성" 항목을 참조하십시오.

## <a name="cdaoquerydefgetodbctimeout"></a><a name="getodbctimeout"></a>CDao쿼리데프::GetODBC타임아웃

이 멤버 함수를 호출하여 ODBC 데이터 원본에 대한 쿼리 시간이 초과되기 전에 현재 시간 제한을 검색합니다.

```
short GetODBCTimeout();
```

### <a name="return-value"></a>Return Value

쿼리 시간이 초과될 때까지 걸리는 시간(초)입니다.

### <a name="remarks"></a>설명

이 시간 제한에 대한 자세한 내용은 DAO 도움말의 "ODBCTimeout 속성" 항목을 참조하십시오.

> [!TIP]
> ODBC 테이블을 사용하여 작업하는 기본 방법은 Microsoft Jet(에 연결하는 것입니다. MDB) 데이터베이스. 자세한 내용은 DAO 도움말의 "DAO를 사용하여 외부 데이터베이스에 액세스" 항목을 참조하십시오.

## <a name="cdaoquerydefgetparametercount"></a><a name="getparametercount"></a>CDao쿼리데프::GetParameterCount

저장된 쿼리에서 매개 변수 수를 검색하려면 이 멤버 함수를 호출합니다.

```
short GetParameterCount();
```

### <a name="return-value"></a>Return Value

쿼리에 정의된 매개 변수 수입니다.

### <a name="remarks"></a>설명

`GetParameterCount`는 쿼리 def의 모든 매개 변수를 반복하는 데 유용합니다. 이를 `GetParameterCount` 위해 [GetParameterInfo](#getparameterinfo).

관련 정보는 DAO 도움말의 "매개 변수 개체", "매개 변수 컬렉션" 및 "매개 변수 선언(SQL))" 항목을 참조하십시오.

## <a name="cdaoquerydefgetparameterinfo"></a><a name="getparameterinfo"></a>CDaoQueryDef::GetParameterInfo

이 멤버 함수를 호출하여 querydef에 정의된 매개 변수에 대한 정보를 가져옵니다.

```cpp
void GetParameterInfo(
    int nIndex,
    CDaoParameterInfo& paraminfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetParameterInfo(
    LPCTSTR lpszName,
    CDaoParameterInfo& paraminfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스별 조회에 대한 querydef의 매개 변수 컬렉션에서 원하는 매개 변수의 0기반 인덱스입니다.

*파라미포*<br/>
요청한 정보를 반환하는 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) 개체에 대한 참조입니다.

*dwInfoOptions*<br/>
검색할 매개 변수에 대한 정보를 지정하는 옵션입니다. 사용 가능한 옵션은 함수가 반환되는 원인과 함께 여기에 나열됩니다.

- AFX_DAO_PRIMARY_INFO(기본값) 이름, 유형

*lpszName*<br/>
이름으로 조회하기 위해 원하는 매개 변수의 이름을 포함하는 문자열입니다. [CString](../../atl-mfc-shared/reference/cstringt-class.md)을 사용할 수 있습니다.

### <a name="remarks"></a>설명

*paraminfo에서*반환된 정보에 대한 설명은 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) 구조를 참조하십시오. 이 구조에는 위의 *dwInfoOptions* 아래의 설명 정보에 해당하는 멤버가 있습니다.

관련 정보는 DAO 도움말의 "매개 변수 선언(SQL))" 항목을 참조하십시오.

## <a name="cdaoquerydefgetparamvalue"></a><a name="getparamvalue"></a>CDao쿼리데프::겟파라임밸류

이 멤버 함수를 호출하여 querydef의 매개 변수 컬렉션에 저장된 지정된 매개 변수의 현재 값을 검색합니다.

```
virtual COleVariant GetParamValue(LPCTSTR lpszName);
virtual COleVariant GetParamValue(int nIndex);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
이름을 조회하기 위해 원하는 값을 사용하는 매개 변수의 이름입니다.

*nIndex*<br/>
인덱스별 조회에 대한 querydef의 매개 변수 컬렉션에서 매개 변수의 0기반 인덱스입니다. [GetParameterCount](#getparametercount) 및 [GetParameterInfo](#getparameterinfo)에 대한 호출을 사용하여 이 값을 얻을 수 있습니다.

### <a name="return-value"></a>Return Value

매개 변수의 값을 포함 하는 클래스 [COleVariant의](../../mfc/reference/colevariant-class.md) 개체입니다.

### <a name="remarks"></a>설명

이름 또는 컬렉션의 서수 위치로 매개 변수에 액세스할 수 있습니다.

관련 정보는 DAO 도움말의 "매개 변수 선언(SQL))" 항목을 참조하십시오.

## <a name="cdaoquerydefgetrecordsaffected"></a><a name="getrecordsaffected"></a>CDao쿼리데프::겟레코드영향

이 멤버 함수를 호출하여 [Execute](#execute)의 마지막 호출에 의해 영향을 받은 레코드 수를 확인합니다.

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Return Value

영향을 받은 레코드 수입니다.

### <a name="remarks"></a>설명

반환된 개수는 계단식 업데이트 또는 삭제가 적용되는 경우 관련 테이블의 변경 내용을 반영하지 않습니다.

관련 정보는 DAO 도움말의 "레코드 영향을 받는 속성" 항목을 참조하십시오.

## <a name="cdaoquerydefgetreturnsrecords"></a><a name="getreturnsrecords"></a>CDao쿼리데프::겟리턴스레코드

이 멤버 함수를 호출하여 querydef가 레코드를 반환하는 쿼리를 기반으로 하는지 여부를 확인합니다.

```
BOOL GetReturnsRecords();
```

### <a name="return-value"></a>Return Value

querydef가 레코드를 반환하는 쿼리를 기반으로 하는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수는 SQL 통과 쿼리에만 사용됩니다. SQL 쿼리에 대한 자세한 내용은 멤버 [실행](#execute) 함수를 참조하십시오. SQL 통과 쿼리 작업에 대한 자세한 내용은 [SetReturnsRecords](#setreturnsrecords) 멤버 함수를 참조하십시오.

관련 정보는 DAO 도움말의 "ReturnsRecords 속성" 항목을 참조하십시오.

## <a name="cdaoquerydefgetsql"></a><a name="getsql"></a>CDao쿼리데프::겟SQL

이 멤버 함수를 호출하여 쿼리 def의 기반이 되는 쿼리를 정의하는 SQL 문을 검색합니다.

```
CString GetSQL();
```

### <a name="return-value"></a>Return Value

쿼리 def의 기반이 되는 쿼리를 정의하는 SQL 문입니다.

### <a name="remarks"></a>설명

그런 다음 키워드, 테이블 이름 등의 문자열을 구문 분석할 수 있습니다.

관련 정보는 DAO 도움말에서 "SQL 속성", "Microsoft Jet 데이터베이스 엔진 및 ANSI SQL 비교" 항목 및 "코드에서 SQL로 데이터베이스 쿼리" 항목을 참조하십시오.

## <a name="cdaoquerydefgettype"></a><a name="gettype"></a>CDao쿼리데프::GetType

이 멤버 함수를 호출하여 쿼리 def의 쿼리 유형을 확인합니다.

```
short GetType();
```

### <a name="return-value"></a>Return Value

쿼리def에 의해 정의된 쿼리 의 유형입니다. 값에 대 한 비고를 참조 합니다.

### <a name="remarks"></a>설명

쿼리 형식은 쿼리 def를 만들거나 기존 querydef의 [SetSQL](#setsql) 멤버 함수를 호출할 때 querydef의 SQL 문자열에 지정한 내용으로 설정됩니다. 이 함수에서 반환되는 쿼리 형식은 다음 값 중 하나일 수 있습니다.

- `dbQSelect`선택

- `dbQAction` 동작

- `dbQCrosstab`크로스탭

- `dbQDelete`삭제

- `dbQUpdate` Update

- `dbQAppend`추가

- `dbQMakeTable`메이크 테이블

- `dbQDDL`데이터 정의

- `dbQSQLPassThrough`통과

- `dbQSetOperation`연합

- `dbQSPTBulk`레코드를 `dbQSQLPassThrough` 반환 하지 않는 쿼리를 지정 하는 데 사용 됩니다.

> [!NOTE]
> SQL 통과 쿼리를 만들려면 `dbSQLPassThrough` 상수를 설정하지 마십시오. 이 설정은 쿼리 def 개체를 만들고 연결 문자열을 설정할 때 Microsoft Jet 데이터베이스 엔진에 의해 자동으로 설정됩니다.

SQL 문자열에 대한 자세한 내용은 [GetSQL](#getsql)을 참조하십시오. 쿼리 유형에 대한 자세한 내용은 [실행](#execute)을 참조하십시오.

## <a name="cdaoquerydefisopen"></a><a name="isopen"></a>CDao쿼리데프::이스오픈

이 멤버 함수를 호출하여 개체가 `CDaoQueryDef` 현재 열려 있는지 확인합니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Return Value

개체가 현재 `CDaoQueryDef` 열려 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

querydef는 [Execute를](#execute) 호출하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체를 만드는 데 사용하기 전에 열려 있는 상태여야 합니다. 쿼리 def를 새 쿼리 def의 경우 [만들기](#create) 또는 [Open(기존](#open) 쿼리 def의 경우) 열린 상태 호출에 넣습니다.

## <a name="cdaoquerydefm_pdatabase"></a><a name="m_pdatabase"></a>CDao쿼리데프::m_pDatabase

쿼리 def 개체와 연결된 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체에 대한 포인터를 포함합니다.

### <a name="remarks"></a>설명

데이터베이스에 직접 액세스해야 하는 경우(예: 데이터베이스 컬렉션의 다른 쿼리 def 또는 레코드 집합 개체에 대한 포인터를 가져오는 경우)를 사용하여 이 포인터를 사용합니다.

## <a name="cdaoquerydefm_pdaoquerydef"></a><a name="m_pdaoquerydef"></a>CDao쿼리데프::m_pDAOQueryDef

기본 DAO 쿼리 def 개체에 대 한 OLE 인터페이스에 대 한 포인터를 포함 합니다.

### <a name="remarks"></a>설명

이 포인터는 다른 클래스와의 완전성과 일관성을 위해 제공됩니다. 그러나 MFC는 DAO 쿼리defs를 완전히 캡슐화하기 때문에 필요하지 않습니다. 당신이 그것을 사용하는 경우, 그렇게 신중하게 - 특히, 당신이 무엇을하고 있는지 모르는 한 포인터의 값을 변경하지 마십시오.

## <a name="cdaoquerydefopen"></a><a name="open"></a>CDao쿼리데프::열기

이 멤버 함수를 호출하여 이전에 데이터베이스의 QueryDefs 컬렉션에 저장된 쿼리 def를 엽니다.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
열 수 있는 저장된 쿼리 def의 이름을 포함하는 문자열입니다. [CString](../../atl-mfc-shared/reference/cstringt-class.md)을 사용할 수 있습니다.

### <a name="remarks"></a>설명

쿼리 def가 열리면 [Execute](#execute) 멤버 함수를 호출하거나 쿼리 def를 사용하여 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체를 만들 수 있습니다.

## <a name="cdaoquerydefsetconnect"></a><a name="setconnect"></a>CDao쿼리데프::세트커넥트

이 멤버 함수를 호출하여 querydef 개체의 연결 문자열을 설정합니다.

```cpp
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>매개 변수

*lpszConnect*<br/>
연결된 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체에 대한 연결 문자열을 포함하는 문자열입니다.

### <a name="remarks"></a>설명

연결 문자열은 필요에 따라 ODBC 및 특정 ISAM 드라이버에 추가 정보를 전달하는 데 사용됩니다. 그것은 마이크로 소프트 제트 (. MDB) 데이터베이스.

> [!TIP]
> ODBC 테이블을 사용하여 작업하는 기본 방법은 에 연결하는 것입니다. MDB 데이터베이스.

ODBC 데이터 원본에 대한 SQL 통과 쿼리를 나타내는 쿼리 def를 실행하기 전에 `SetConnect` 연결 문자열을 설정하고 [SetReturnsRecords를](#setreturnsrecords) 호출하여 쿼리가 레코드를 반환하는지 여부를 지정합니다.

연결 문자열의 구조 및 연결 문자열 구성 요소의 예에 대한 자세한 내용은 DAO 도움말의 "속성 연결" 항목을 참조하십시오.

## <a name="cdaoquerydefsetname"></a><a name="setname"></a>CDao쿼리데프::세트네임

임시가 아닌 querydef의 이름을 변경하려는 경우 이 멤버 함수를 호출합니다.

```cpp
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
연결된 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체의 비임시 쿼리에 대한 새 이름을 포함하는 문자열입니다.

### <a name="remarks"></a>설명

Querydef 이름은 고유한 사용자 정의 이름입니다. querydef `SetName` 개체가 QueryDefs 컬렉션에 추가되기 전에 호출할 수 있습니다.

## <a name="cdaoquerydefsetodbctimeout"></a><a name="setodbctimeout"></a>CDao쿼리데프::SetODBC타임아웃

이 멤버 함수를 호출하여 ODBC 데이터 원본에 대한 쿼리 시간이 초과되기 전에 시간 제한을 설정합니다.

```cpp
void SetODBCTimeout(short nODBCTimeout);
```

### <a name="parameters"></a>매개 변수

*nODBC타임아웃*<br/>
쿼리 시간이 초과될 때까지 걸리는 시간(초)입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 사용하면 연결된 데이터 원본의 후속 작업 "시간 초과"에 대한 기본 초 수를 재정의할 수 있습니다. 네트워크 액세스 문제, 과도한 쿼리 처리 시간 등으로 인해 작업이 시간 중지될 수 있습니다. 쿼리 `SetODBCTimeout` 시간 시간 값을 변경하려는 경우 이 쿼리 def를 사용하여 쿼리를 실행하기 전에 호출합니다. (ODBC가 연결을 다시 사용하므로 시간 시간 값은 동일한 연결의 모든 클라이언트에 대해 동일합니다.)

쿼리 시간 설정의 기본값은 60초입니다.

## <a name="cdaoquerydefsetparamvalue"></a><a name="setparamvalue"></a>CDao쿼리데프::세트파라임밸류

런타임에 querydef에서 매개 변수의 값을 설정 하려면이 멤버 함수를 호출 합니다.

```
virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
설정할 값을 지정하려는 매개 변수의 이름입니다.

*varValue*<br/>
설정할 값; 비고를 참조하십시오.

*nIndex*<br/>
querydef의 매개 변수 컬렉션에서 매개 변수의 서수 위치입니다. [GetParameterCount](#getparametercount) 및 [GetParameterInfo](#getparameterinfo)에 대한 호출을 사용하여 이 값을 얻을 수 있습니다.

### <a name="remarks"></a>설명

쿼리 def의 SQL 문자열의 일부로 매개 변수가 이미 설정되어 있어야 합니다. 이름 또는 컬렉션의 서수 위치로 매개 변수에 액세스할 수 있습니다.

개체로 설정할 값을 `COleVariant` 지정합니다. 개체에서 원하는 값 및 형식을 설정하는 자세한 내용은 [클래스 COleVariant](../../mfc/reference/colevariant-class.md)을 참조하십시오. `COleVariant`

## <a name="cdaoquerydefsetreturnsrecords"></a><a name="setreturnsrecords"></a>CDao쿼리데프::세트리턴스레코드

외부 데이터베이스에 SQL 통과 쿼리를 설정하는 프로세스의 일부로 이 멤버 함수를 호출합니다.

```cpp
void SetReturnsRecords(BOOL bReturnsRecords);
```

### <a name="parameters"></a>매개 변수

*bReturns레코드*<br/>
외부 데이터베이스의 쿼리가 레코드를 반환하는 경우 TRUE를 전달합니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이러한 경우 쿼리 def를 만들고 다른 `CDaoQueryDef` 멤버 함수를 사용하여 해당 속성을 설정해야 합니다. 외부 데이터베이스에 대한 설명은 [SetConnect](#setconnect)을 참조하십시오.

## <a name="cdaoquerydefsetsql"></a><a name="setsql"></a>CDao쿼리데프::SetSQL

이 멤버 함수를 호출하여 querydef가 실행하는 SQL 문을 설정합니다.

```cpp
void SetSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>매개 변수

*lpszSQL*<br/>
실행에 적합한 전체 SQL 문을 포함하는 문자열입니다. 이 문자열의 구문은 쿼리가 대상으로 하는 DBMS에 따라 다릅니다. Microsoft Jet 데이터베이스 엔진에서 사용되는 구문에 대한 설명은 DAO 도움말의 "코드에서 SQL 문 작성" 항목을 참조하십시오.

### <a name="remarks"></a>설명

일반적으로 SQL `SetSQL` 통과 쿼리에 사용할 쿼리def 개체를 설정하는 것이 일반적입니다. 대상 DBMS에 대한 SQL 통과 쿼리 구문은 DBMS에 대한 설명서를 참조하십시오.

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDao레코드 집합 클래스](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDao데이터베이스 클래스](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoException 클래스](../../mfc/reference/cdaoexception-class.md)
