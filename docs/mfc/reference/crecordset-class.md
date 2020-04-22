---
title: C레코드 집합 클래스
ms.date: 11/04/2016
f1_keywords:
- CRecordset
- AFXDB/CRecordset
- AFXDB/CRecordset::CRecordset
- AFXDB/CRecordset::AddNew
- AFXDB/CRecordset::CanAppend
- AFXDB/CRecordset::CanBookmark
- AFXDB/CRecordset::Cancel
- AFXDB/CRecordset::CancelUpdate
- AFXDB/CRecordset::CanRestart
- AFXDB/CRecordset::CanScroll
- AFXDB/CRecordset::CanTransact
- AFXDB/CRecordset::CanUpdate
- AFXDB/CRecordset::CheckRowsetError
- AFXDB/CRecordset::Close
- AFXDB/CRecordset::Delete
- AFXDB/CRecordset::DoBulkFieldExchange
- AFXDB/CRecordset::DoFieldExchange
- AFXDB/CRecordset::Edit
- AFXDB/CRecordset::FlushResultSet
- AFXDB/CRecordset::GetBookmark
- AFXDB/CRecordset::GetDefaultConnect
- AFXDB/CRecordset::GetDefaultSQL
- AFXDB/CRecordset::GetFieldValue
- AFXDB/CRecordset::GetODBCFieldCount
- AFXDB/CRecordset::GetODBCFieldInfo
- AFXDB/CRecordset::GetRecordCount
- AFXDB/CRecordset::GetRowsetSize
- AFXDB/CRecordset::GetRowsFetched
- AFXDB/CRecordset::GetRowStatus
- AFXDB/CRecordset::GetSQL
- AFXDB/CRecordset::GetStatus
- AFXDB/CRecordset::GetTableName
- AFXDB/CRecordset::IsBOF
- AFXDB/CRecordset::IsDeleted
- AFXDB/CRecordset::IsEOF
- AFXDB/CRecordset::IsFieldDirty
- AFXDB/CRecordset::IsFieldNull
- AFXDB/CRecordset::IsFieldNullable
- AFXDB/CRecordset::IsOpen
- AFXDB/CRecordset::Move
- AFXDB/CRecordset::MoveFirst
- AFXDB/CRecordset::MoveLast
- AFXDB/CRecordset::MoveNext
- AFXDB/CRecordset::MovePrev
- AFXDB/CRecordset::OnSetOptions
- AFXDB/CRecordset::OnSetUpdateOptions
- AFXDB/CRecordset::Open
- AFXDB/CRecordset::RefreshRowset
- AFXDB/CRecordset::Requery
- AFXDB/CRecordset::SetAbsolutePosition
- AFXDB/CRecordset::SetBookmark
- AFXDB/CRecordset::SetFieldDirty
- AFXDB/CRecordset::SetFieldNull
- AFXDB/CRecordset::SetLockingMode
- AFXDB/CRecordset::SetParamNull
- AFXDB/CRecordset::SetRowsetCursorPosition
- AFXDB/CRecordset::SetRowsetSize
- AFXDB/CRecordset::Update
- AFXDB/CRecordset::m_hstmt
- AFXDB/CRecordset::m_nFields
- AFXDB/CRecordset::m_nParams
- AFXDB/CRecordset::m_pDatabase
- AFXDB/CRecordset::m_strFilter
- AFXDB/CRecordset::m_strSort
helpviewer_keywords:
- CRecordset [MFC], CRecordset
- CRecordset [MFC], AddNew
- CRecordset [MFC], CanAppend
- CRecordset [MFC], CanBookmark
- CRecordset [MFC], Cancel
- CRecordset [MFC], CancelUpdate
- CRecordset [MFC], CanRestart
- CRecordset [MFC], CanScroll
- CRecordset [MFC], CanTransact
- CRecordset [MFC], CanUpdate
- CRecordset [MFC], CheckRowsetError
- CRecordset [MFC], Close
- CRecordset [MFC], Delete
- CRecordset [MFC], DoBulkFieldExchange
- CRecordset [MFC], DoFieldExchange
- CRecordset [MFC], Edit
- CRecordset [MFC], FlushResultSet
- CRecordset [MFC], GetBookmark
- CRecordset [MFC], GetDefaultConnect
- CRecordset [MFC], GetDefaultSQL
- CRecordset [MFC], GetFieldValue
- CRecordset [MFC], GetODBCFieldCount
- CRecordset [MFC], GetODBCFieldInfo
- CRecordset [MFC], GetRecordCount
- CRecordset [MFC], GetRowsetSize
- CRecordset [MFC], GetRowsFetched
- CRecordset [MFC], GetRowStatus
- CRecordset [MFC], GetSQL
- CRecordset [MFC], GetStatus
- CRecordset [MFC], GetTableName
- CRecordset [MFC], IsBOF
- CRecordset [MFC], IsDeleted
- CRecordset [MFC], IsEOF
- CRecordset [MFC], IsFieldDirty
- CRecordset [MFC], IsFieldNull
- CRecordset [MFC], IsFieldNullable
- CRecordset [MFC], IsOpen
- CRecordset [MFC], Move
- CRecordset [MFC], MoveFirst
- CRecordset [MFC], MoveLast
- CRecordset [MFC], MoveNext
- CRecordset [MFC], MovePrev
- CRecordset [MFC], OnSetOptions
- CRecordset [MFC], OnSetUpdateOptions
- CRecordset [MFC], Open
- CRecordset [MFC], RefreshRowset
- CRecordset [MFC], Requery
- CRecordset [MFC], SetAbsolutePosition
- CRecordset [MFC], SetBookmark
- CRecordset [MFC], SetFieldDirty
- CRecordset [MFC], SetFieldNull
- CRecordset [MFC], SetLockingMode
- CRecordset [MFC], SetParamNull
- CRecordset [MFC], SetRowsetCursorPosition
- CRecordset [MFC], SetRowsetSize
- CRecordset [MFC], Update
- CRecordset [MFC], m_hstmt
- CRecordset [MFC], m_nFields
- CRecordset [MFC], m_nParams
- CRecordset [MFC], m_pDatabase
- CRecordset [MFC], m_strFilter
- CRecordset [MFC], m_strSort
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
ms.openlocfilehash: ab6cde9f478dc6f2e3cb0ba5bb338a3852f083fd
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750511"
---
# <a name="crecordset-class"></a>C레코드 집합 클래스

데이터 소스에서 선택한 레코드 집합을 나타냅니다.

## <a name="syntax"></a>구문

```
class CRecordset : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C레코드 집합::C레코드 집합](#crecordset)|`CRecordset` 개체를 생성합니다. 파생 클래스는 이 클래스를 호출하는 생성자(생성자)를 제공해야 합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C레코드 집합::새 새](#addnew)|새 레코드를 추가할 준비를 합니다. 추가를 완료하려면 호출합니다. `Update`|
|[C레코드 집합:::캔아플렌드](#canappend)|멤버 함수를 통해 레코드 집합에 새 레코드를 추가할 수 있는 경우 0이 아닌 레코드를 `AddNew` 반환합니다.|
|[C레코드 집합::캔북마크](#canbookmark)|레코드 집합이 책갈피를 지원하는 경우 0이 아닌 것을 반환합니다.|
|[C레코드 집합::취소](#cancel)|두 번째 스레드에서 비동기 작업 또는 프로세스를 취소합니다.|
|[C레코드 집합::취소 업데이트](#cancelupdate)|`AddNew` 또는 `Edit` 작업으로 인해 보류 중인 업데이트를 취소합니다.|
|[C레코드 집합::다시 시작할 수 있습니다.](#canrestart)|레코드 집합의 `Requery` 쿼리를 다시 실행하기 위해 호출할 수 있는 경우 0이 아닌 것을 반환합니다.|
|[C레코드 집합::수스크롤](#canscroll)|레코드를 스크롤할 수 있는 경우 0이 아닌 것을 반환합니다.|
|[C레코드 집합::수](#cantransact)|데이터 원본이 트랜잭션을 지원하는 경우 0이 아닌 것을 반환합니다.|
|[C레코드 집합::수 있습니다.](#canupdate)|레코드 집합을 업데이트할 수 있는 경우 0이 아닌 것을 반환합니다(레코드추가, 업데이트 또는 삭제할 수 있음).|
|[C레코드 집합::검사행집합오류](#checkrowseterror)|레코드 가져오기 중에 생성된 오류를 처리하기 위해 호출됩니다.|
|[C레코드 집합::닫기](#close)|레코드 집합과 연결된 ODBC HSTMT를 닫습니다.|
|[C레코드 집합::D](#delete)|레코드 집합에서 현재 레코드를 삭제합니다. 삭제 후 다른 레코드로 명시적으로 스크롤해야 합니다.|
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|데이터 원본에서 레코드 집합으로 대량 데이터 행을 교환하기 위해 호출됩니다. 대량 레코드 필드 교환(대량 RFX)을 구현합니다.|
|[CRecordset::DoFieldExchange](#dofieldexchange)|레코드 집합의 필드 데이터 멤버와 데이터 원본의 해당 레코드 간에 양방향으로 데이터를 교환하도록 호출됩니다. 레코드 필드 교환(RFX)을 구현합니다.|
|[C레코드 집합::편집](#edit)|현재 레코드에 대한 변경 내용을 준비합니다. 호출하여 `Update` 편집을 완료합니다.|
|[C레코드 집합::플러시 결과 집합](#flushresultset)|미리 정의된 쿼리를 사용할 때 검색할 다른 결과 집합이 있는 경우 0이 아닌 것을 반환합니다.|
|[C레코드 집합::GetBookmark](#getbookmark)|매개 변수 개체에 레코드의 책갈피 값을 할당합니다.|
|[C레코드 집합::GetDefaultConnect](#getdefaultconnect)|기본 연결 문자열을 얻으려면 호출됩니다.|
|[C레코드 집합::GetDefaultSQL](#getdefaultsql)|실행할 기본 SQL 문자열을 얻으려면 호출됩니다.|
|[C레코드 집합::겟필드밸류](#getfieldvalue)|레코드 집합에서 필드 값을 반환합니다.|
|[C레코드 집합::GetODBC필드카운트](#getodbcfieldcount)|레코드 집합의 필드 수를 반환합니다.|
|[C레코드 집합::GetODBCFieldInfo](#getodbcfieldinfo)|레코드 집합의 필드에 대한 특정 종류의 정보를 반환합니다.|
|[C레코드 집합::GetRecordCount](#getrecordcount)|레코드 집합의 레코드 수를 반환합니다.|
|[C레코드 집합::GetRowsetSize](#getrowsetsize)|단일 가져오기 중에 검색할 레코드 수를 반환합니다.|
|[C레코드 집합::GetRowsFetched](#getrowsfetched)|가져오기 중에 검색된 실제 행 수를 반환합니다.|
|[C레코드 집합::GetRowStatus](#getrowstatus)|가져오기 후 행의 상태를 반환합니다.|
|[C레코드 집합::GetSQL](#getsql)|레코드 집합에 대한 레코드를 선택하는 데 사용되는 SQL 문자열을 가져옵니다.|
|[C레코드 집합::GetStatus](#getstatus)|레코드 집합의 상태: 현재 레코드의 인덱스 및 레코드의 최종 개수를 얻었는지 여부를 가져옵니다.|
|[C레코드 집합::GetTableName](#gettablename)|레코드 집합의 기반이 되는 테이블의 이름을 가져옵니다.|
|[C레코드 집합::IsBOF](#isbof)|레코드 집합이 첫 번째 레코드 앞에 위치한 경우 0이 아닌 것을 반환합니다. 현재 레코드가 없습니다.|
|[C레코드 집합::삭제됨](#isdeleted)|레코드 집합이 삭제된 레코드에 배치된 경우 0이 아닌 것을 반환합니다.|
|[C레코드 집합::IsEOF](#iseof)|레코드 집합이 마지막 레코드 다음으로 배치된 경우 0이 아닌 것을 반환합니다. 현재 레코드가 없습니다.|
|[C레코드 집합::IsFieldDirty](#isfielddirty)|현재 레코드의 지정된 필드가 변경된 경우 0이 아닌 필드를 반환합니다.|
|[C레코드 집합::IsFieldNull](#isfieldnull)|현재 레코드의 지정된 필드가 null인 경우 비영을 반환합니다(값이 없음).|
|[C레코드 집합::필드Nullable](#isfieldnullable)|현재 레코드의 지정된 필드를 null로 설정할 수 있는 경우 0이 아닌 필드를 반환합니다(값이 없음).|
|[C레코드 집합::이 열기](#isopen)|이전에 호출된 `Open` 경우 0이 아닌 것을 반환합니다.|
|[C레코드 집합::이동](#move)|레코드 집합을 현재 레코드의 지정된 레코드 수에 어느 방향으로든 배치합니다.|
|[C레코드 집합::이동우선](#movefirst)|레코드 집합의 첫 번째 레코드에 현재 레코드를 배치합니다. 먼저 `IsBOF` 테스트합니다.|
|[C레코드 집합::이동마지막](#movelast)|현재 레코드를 마지막 레코드 또는 마지막 행 집합에 배치합니다. 먼저 `IsEOF` 테스트합니다.|
|[C레코드 집합::이동 다음](#movenext)|현재 레코드를 다음 레코드 또는 다음 행 집합에 배치합니다. 먼저 `IsEOF` 테스트합니다.|
|[C레코드 집합::무브프레프](#moveprev)|현재 레코드를 이전 레코드 또는 이전 행 집합의 위치입니다. 먼저 `IsBOF` 테스트합니다.|
|[C레코드 집합::설정 옵션](#onsetoptions)|지정된 ODBC 문에 대한 옵션 설정(선택 시 사용)을 호출합니다.|
|[C레코드 집합::온셋 업데이트 옵션](#onsetupdateoptions)|지정된 ODBC 문에 대한 옵션(업데이트시 사용)을 설정하도록 호출됩니다.|
|[C레코드 집합::열기](#open)|테이블을 검색하거나 레코드 집합이 나타내는 쿼리를 수행하여 레코드 집합을 엽니다.|
|[C레코드 집합::새로 고침행세트](#refreshrowset)|지정된 행의 데이터 및 상태를 새로 고칩니다.|
|[C레코드 집합::다시 쿼리](#requery)|레코드 집합의 쿼리를 다시 실행하여 선택한 레코드를 새로 고칩니다.|
|[C레코드 집합::설정절대위치](#setabsoluteposition)|지정된 레코드 번호에 해당하는 레코드의 레코드 집합을 배치합니다.|
|[C레코드 집합::세트북마크](#setbookmark)|책갈피에서 지정한 레코드에 레코드 집합을 배치합니다.|
|[C레코드 집합::셋필드더티](#setfielddirty)|현재 레코드에서 지정된 필드를 변경된 것으로 표시합니다.|
|[C레코드 집합::세트필드널](#setfieldnull)|현재 레코드에서 지정된 필드의 값을 null로 설정합니다(값이 없음).|
|[C레코드 집합::설정 잠금 모드](#setlockingmode)|잠금 모드를 "낙관적" 잠금(기본값) 또는 "비관적" 잠금으로 설정합니다. 업데이트에 대해 레코드가 잠기는 방법을 결정합니다.|
|[C레코드 집합::SetParamNull](#setparamnull)|지정된 매개 변수를 null로 설정합니다(값이 없음).|
|[C레코드 집합::세트Rowset커서 포지션](#setrowsetcursorposition)|행 집합 내에서 지정된 행에 커서를 배치합니다.|
|[C레코드 집합::세트로셋크기](#setrowsetsize)|가져오기 중에 검색할 레코드 수를 지정합니다.|
|[C레코드 집합::업데이트](#update)|데이터 `AddNew` 원본에 `Edit` 새 데이터 또는 편집된 데이터를 저장하여 또는 작업을 완료합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C레코드 집합:m_hstmt](#m_hstmt)|레코드 집합에 대한 ODBC 문 핸들을 포함합니다. `HSTMT`을 입력합니다.|
|[C레코드 집합::m_nFields](#m_nfields)|레코드 집합에 필드 데이터 멤버 수를 포함합니다. `UINT`을 입력합니다.|
|[C레코드 집합::m_nParams](#m_nparams)|레코드 집합에 매개 변수 데이터 멤버 수를 포함합니다. `UINT`을 입력합니다.|
|[C레코드 집합::m_pDatabase](#m_pdatabase)|레코드 집합이 `CDatabase` 데이터 원본에 연결된 개체에 대한 포인터를 포함합니다.|
|[C레코드 집합:m_strFilter](#m_strfilter)|SQL(구조화 쿼리 언어) `CString` `WHERE` 절을 지정하는 을 포함합니다. 특정 기준을 충족하는 레코드만 선택하는 필터로 사용됩니다.|
|[C레코드 집합:m_strSort](#m_strsort)|SQL `ORDER BY` `CString` 절을 지정하는 것을 포함합니다. 레코드를 정렬하는 방법을 제어하는 데 사용됩니다.|

## <a name="remarks"></a><a name="remarks"></a> 주의 사항

"레코드 집합"이라고 `CRecordset` 하는 개체는 일반적으로 다이너셋과 스냅숏의 두 가지 형태로 사용됩니다. 다이너셋은 다른 사용자가 만든 데이터 업데이트와 동기화된 상태로 유지됩니다. 스냅숏은 데이터의 정적 보기입니다. 각 양식은 레코드 집합이 열릴 때 고정된 레코드 집합을 나타내지만 다이너셋의 레코드로 스크롤할 때 다른 사용자 나 응용 프로그램의 다른 레코드 집합에 의해 레코드에 대한 변경 내용을 반영합니다.

> [!NOTE]
> ODBC(개방형 데이터베이스 연결) 클래스가 아닌 DAO(데이터 액세스 개체) 클래스로 작업하는 경우 대신 [클래스 CDaoRecordset을](../../mfc/reference/cdaorecordset-class.md) 사용합니다. 자세한 내용은 [문서 개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)을 참조하십시오.

두 종류의 레코드 집합으로 작업하려면 일반적으로 에서 `CRecordset`응용 프로그램별 레코드 집합 클래스를 파생합니다. 레코드 집합은 데이터 원본에서 레코드를 선택하고 다음을 수행할 수 있습니다.

- 레코드를 스크롤합니다.

- 레코드를 업데이트하고 잠금 모드를 지정합니다.

- 레코드 집합을 필터링하여 데이터 원본에서 사용할 수 있는 레코드 중에서 선택한 레코드를 제한합니다.

- 레코드 집합을 정렬합니다.

- 레코드 집합을 매개 변수화하여 런타임까지 알려지지 않은 정보로 선택 영역을 사용자 지정합니다.

클래스를 사용하려면 데이터베이스를 열고 레코드 집합 개체를 생성자가 `CDatabase` 개체에 포인터를 전달하여 생성자 개체를 생성합니다. 그런 다음 레코드 집합의 `Open` 멤버 함수를 호출하여 개체가 다이너셋인지 스냅숏인지 지정할 수 있습니다. 호출은 `Open` 데이터 원본에서 데이터를 선택합니다. 레코드 집합 개체가 열리면 해당 멤버 함수 및 데이터 멤버를 사용하여 레코드를 스크롤하고 작동합니다. 사용 가능한 작업은 개체가 다이너셋인지 스냅숏인지, 업데이터 가능인지 읽기 전용인지(ODBC(개방형 데이터베이스 연결) 데이터 원본의 기능에 따라 다름) 및 대량 행 가져오기를 구현했는지 여부에 따라 달라집니다. 호출 이후 변경되거나 추가된 레코드를 `Open` 새로 고치려면 `Requery` 개체의 멤버 함수를 호출합니다. 개체의 `Close` 멤버 함수를 호출하고 개체를 완료하면 개체를 삭제합니다.

파생 `CRecordset` 클래스에서 레코드 필드 교환(RFX) 또는 대량 레코드 필드 교환(대량 RFX)은 레코드 필드의 읽기 및 업데이트를 지원하는 데 사용됩니다.

레코드 집합 및 레코드 필드 교환에 대한 자세한 내용은 [문서 개요: 데이터베이스 프로그래밍,](../../data/data-access-programming-mfc-atl.md) [레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)및 [레코드 집합: 대량 레코드 가져오기(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)및 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)참조. 다이너셋 및 스냅숏에 대한 자세한 내용은 [다이나셋](../../data/odbc/dynaset.md) 및 [스냅숏](../../data/odbc/snapshot.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CRecordset`

## <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="crecordsetaddnew"></a><a name="addnew"></a>C레코드 집합::새 새

테이블에 새 레코드를 추가할 준비를 합니다.

```
virtual void AddNew();
```

### <a name="remarks"></a>설명

새로 추가된 레코드를 보려면 [Requery](#requery) 멤버 함수를 호출해야 합니다. 레코드의 필드는 처음에 Null입니다. (데이터베이스 용어에서 Null은 "값이 없음"을 의미하며 C++에서 NULL과 동일하지 않습니다. 작업을 완료하려면 [멤버 업데이트](#update) 함수를 호출해야 합니다. `Update`변경 내용을 데이터 원본에 저장합니다.

> [!NOTE]
> 대량 행 가져오기를 구현한 경우 `AddNew`를 호출할 수 없습니다. 이렇게 하면 어설션이 실패합니다. 클래스는 `CRecordset` 대량 데이터 행을 업데이트하는 메커니즘을 제공하지는 않지만 ODBC API 함수를 `SQLSetPos`사용하여 사용자 고유의 함수를 작성할 수 있습니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

`AddNew`레코드 집합의 필드 데이터 멤버를 사용하여 새 빈 레코드를 준비합니다. 호출한 `AddNew`후 레코드 집합의 필드 데이터 멤버에서 원하는 값을 설정합니다. (이 목적을 위해 [멤버 편집](#edit) 함수를 호출할 `Edit` 필요는 없으며 기존 레코드에만 사용하십시오.) 이후에 호출할 `Update`때 필드 데이터 멤버의 변경된 값이 데이터 원본에 저장됩니다.

> [!CAUTION]
> 호출하기 `Update`전에 새 레코드로 스크롤하면 새 레코드가 손실되고 경고가 제공되지 않습니다.

데이터 원본이 트랜잭션을 지원하는 경우 `AddNew` 트랜잭션의 일부로 호출할 수 있습니다. 트랜잭션에 대한 자세한 내용은 [클래스 CDatabase](../../mfc/reference/cdatabase-class.md)를 참조하십시오. 호출하기 전에 [CDatabase::BeginTrans를](../../mfc/reference/cdatabase-class.md#begintrans) `AddNew`호출해야 합니다.

> [!NOTE]
> 다이너셋의 경우 새 레코드가 레코드 집합에 마지막 레코드로 추가됩니다. 추가된 레코드는 스냅숏에 추가되지 않습니다. 레코드 집합을 새로 고치려면 호출해야 `Requery` 합니다.

멤버 함수가 `AddNew` 호출되지 않은 레코드 집합을 호출하는 것은 불법입니다. `Open` 추가할 수 없는 `AddNew` 레코드 집합을 호출하면 A가 `CDBException` throw됩니다. [에서](#canappend)호출하여 레코드 집합이 업데이터인지 여부를 확인할 수 있습니다.

자세한 내용은 다음 문서를 참조하십시오: [레코드 집합: 레코드 집합 업데이트 레코드(ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)및 [레코드 집합: 레코드 추가, 업데이트 및 삭제 레코드(ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)및 [트랜잭션(ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>예제

문서 [트랜잭션: 레코드 집합(ODBC)에서 트랜잭션 수행 을](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)참조하십시오.

## <a name="crecordsetcanappend"></a><a name="canappend"></a>C레코드 집합:::캔아플렌드

이전에 연 레코드 집합을 통해 새 레코드를 추가할 수 있는지 여부를 확인합니다.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Return Value

레코드 집합에서 새 레코드를 추가할 수 있는 경우 0이 아닙니다. 그렇지 않으면 0. `CanAppend`레코드 집합을 읽기 전용으로 열면 0이 반환됩니다.

## <a name="crecordsetcanbookmark"></a><a name="canbookmark"></a>C레코드 집합::캔북마크

레코드 집합을 사용하여 레코드를 표시할 수 있는지 여부를 확인합니다.

```
BOOL CanBookmark() const;
```

### <a name="return-value"></a>Return Value

레코드 집합이 책갈피를 지원하는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 `CRecordset::useBookmarks` [Open](#open) 멤버 함수의 *dwOptions* 매개 변수의 옵션과 독립적입니다. `CanBookmark`은 지정된 ODBC 드라이버 및 커서 유형 지원 북마크를 나타냅니다. `CRecordset::useBookmarks`은 지원되는 경우 책갈피를 사용할 수 있는지 여부를 나타냅니다.

> [!NOTE]
> 책갈피는 정방향 전용 레코드 집합에서 지원되지 않습니다.

책갈피 및 레코드 집합 탐색에 대한 자세한 내용은 [레코드 집합: 북마크 및 절대 위치(ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) 및 [레코드 집합: 스크롤(ODBC)](../../data/odbc/recordset-scrolling-odbc.md)문서를 참조하십시오.

## <a name="crecordsetcancel"></a><a name="cancel"></a>C레코드 집합::취소

데이터 원본이 진행 중인 비동기 작업 또는 두 번째 스레드의 프로세스를 취소해 달라는 요청입니다.

```cpp
void Cancel();
```

### <a name="remarks"></a>설명

MFC ODBC 클래스는 더 이상 비동기 처리를 사용하지 않습니다. asychronous 작업을 수행하려면 ODBC API 함수를 `SQLSetConnectOption`직접 호출해야 합니다. 자세한 내용은 *ODBC SDK 프로그래머 가이드의*"비동기적으로 기능 실행" 항목을 참조하십시오.

## <a name="crecordsetcancelupdate"></a><a name="cancelupdate"></a>C레코드 집합::취소 업데이트

[업데이트가](#update) 호출되기 전에 [편집](#edit) 또는 [AddNew](#addnew) 작업으로 인해 발생하는 보류 중인 업데이트를 취소합니다.

```cpp
void CancelUpdate();
```

### <a name="remarks"></a>설명

> [!NOTE]
> 이 멤버 함수는 이러한 레코드 집합을 호출할 `Edit`수 없으므로 대량 행 `AddNew`가져오기를 사용하는 레코드 집합에는 적용되지 `Update`않습니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

자동 더티 필드 검사가 `CancelUpdate` 활성화된 경우 멤버 변수를 이전에 `Edit` `AddNew` 가지고 있거나 호출된 값으로 복원합니다. 그렇지 않으면 값 변경 내용이 유지됩니다. 기본적으로 레코드 집합을 열 때 자동 필드 검사가 활성화됩니다. 비활성화하려면 `CRecordset::noDirtyFieldCheck` [Open](#open) 멤버 함수의 *dwOptions* 매개 변수를 지정해야 합니다.

데이터 업데이트에 대한 자세한 내용은 [레코드 집합: 레코드 추가, 업데이트 및 삭제 레코드(ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)문서를 참조하십시오.

## <a name="crecordsetcanrestart"></a><a name="canrestart"></a>C레코드 집합::다시 시작할 수 있습니다.

`Requery` 레코드 집합이 멤버 함수를 호출하여 쿼리를 다시 시작할 수 있는지 여부를 결정합니다(레코드 새로 고침).

```
BOOL CanRestart() const;
```

### <a name="return-value"></a>Return Value

재쿼리가 허용되는 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="crecordsetcanscroll"></a><a name="canscroll"></a>C레코드 집합::수스크롤

레코드 집합이 스크롤을 허용하는지 여부를 결정합니다.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Return Value

레코드 집합이 스크롤을 허용하는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

스크롤에 대한 자세한 내용은 [레코드 집합: 스크롤(ODBC)](../../data/odbc/recordset-scrolling-odbc.md)문서를 참조하십시오.

## <a name="crecordsetcantransact"></a><a name="cantransact"></a>C레코드 집합::수

레코드 집합이 트랜잭션을 허용하는지 여부를 결정합니다.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Return Value

레코드 집합이 트랜잭션을 허용하는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

자세한 내용은 [ODBC(트랜잭션)](../../data/odbc/transaction-odbc.md)문서를 참조하십시오.

## <a name="crecordsetcanupdate"></a><a name="canupdate"></a>C레코드 집합::수 있습니다.

레코드 집합을 업데이트할 수 있는지 여부를 결정합니다.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Return Value

레코드 집합을 업데이트할 수 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

레코드 집합은 기본 데이터 원본이 읽기 전용이거나 레코드 집합을 `CRecordset::readOnly` 열 때 *dwOptions* 매개 변수에 지정한 경우 읽기 전용일 수 있습니다.

## <a name="crecordsetcheckrowseterror"></a><a name="checkrowseterror"></a>C레코드 집합::검사행집합오류

레코드 가져오기 중에 생성된 오류를 처리하기 위해 호출됩니다.

```
virtual void CheckRowsetError(RETCODE nRetCode);
```

### <a name="parameters"></a>매개 변수

*nRetCode*<br/>
ODBC API 함수는 코드를 반환합니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

이 가상 멤버 함수는 레코드를 가져올 때 발생하는 오류를 처리하며 대량 행 을 가져오는 동안 유용합니다. 사용자 고유의 오류 `CheckRowsetError` 처리를 구현하기 위해 재정의를 고려할 수 있습니다.

`CheckRowsetError`는 커서 탐색 작업(예: `Open`" 또는 `Requery`모든 `Move` 작업)에서 자동으로 호출됩니다. ODBC API 함수의 `SQLExtendedFetch`반환 값을 전달합니다. 다음 표에는 *nRetCode* 매개 변수에 대한 가능한 값이 나열되어 있습니다.

|nRetCode|Description|
|--------------|-----------------|
|SQL_SUCCESS|함수가 성공적으로 완료되었습니다. 추가 정보를 사용할 수 없습니다.|
|SQL_SUCCESS_WITH_INFO|치명적이지 않은 오류로 함수가 성공적으로 완료되었습니다. 추가 정보는 호출하여 `SQLError`얻을 수 있습니다.|
|SQL_NO_DATA_FOUND|결과 집합의 모든 행이 인출되었습니다.|
|SQL_ERROR|함수가 실패했습니다. 추가 정보는 호출하여 `SQLError`얻을 수 있습니다.|
|SQL_INVALID_HANDLE|잘못된 환경 핸들, 연결 핸들 또는 명령문 핸들로 인해 함수가 실패했습니다. 프로그래밍 오류를 나타냅니다. 에서 추가 정보를 `SQLError`사용할 수 없습니다.|
|SQL_STILL_EXECUTING|비동기적으로 시작된 함수는 여전히 실행 중입니다. 기본적으로 MFC는 이 값을 다음값에 `CheckRowsetError`전달하지 않습니다. MFC는 더 `SQLExtendedFetch` 이상 SQL_STILL_EXECUTING 반환되지 않을 때까지 통화를 계속합니다.|

자세한 `SQLError`내용은 Windows SDK를 참조하십시오. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

## <a name="crecordsetclose"></a><a name="close"></a>C레코드 집합::닫기

레코드 집합을 닫습니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

레코드 집합에 할당된 ODBC HSTMT 및 모든 메모리는 할당된 것입니다. 일반적으로 호출 `Close`후 **새**로 할당된 경우 C++ 레코드 집합 개체를 삭제합니다.

호출한 `Close` `Open` 후 다시 호출할 수 있습니다. 이렇게 하면 레코드 집합 개체를 다시 사용할 수 있습니다. 다른 방법은 를 `Requery`호출하는 것입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]

## <a name="crecordsetcrecordset"></a><a name="crecordset"></a>C레코드 집합::C레코드 집합

`CRecordset` 개체를 생성합니다.

```
CRecordset(CDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>매개 변수

*p데이터베이스*<br/>
개체 또는 NULL `CDatabase` 값에 대한 포인터를 포함합니다. NULL이 아니고 `CDatabase` 개체의 `Open` 멤버 함수가 데이터 원본에 연결하기 위해 호출되지 않은 경우 레코드 집합은 자체 `Open` 호출 중에 해당 함수를 열려고 시도합니다. NULL을 통과하면 `CDatabase` ClassWizard를 사용하여 레코드 집합 클래스를 파생할 때 지정한 데이터 원본 정보를 사용하여 개체가 생성되고 연결됩니다.

### <a name="remarks"></a>설명

에서 응용 `CRecordset` 프로그램 별 클래스를 직접 사용하거나 파생시킬 수 있습니다. `CRecordset` ClassWizard를 사용하여 레코드 집합 클래스를 파생할 수 있습니다.

> [!NOTE]
> 파생 된 클래스는 자체 생성자 제공 *해야 합니다.* 파생 클래스의 생성자에서 생성자 `CRecordset::CRecordset`호출 하여 해당 매개 변수를 전달합니다.

NULL을 레코드 집합 생성자로 `CDatabase` 전달하여 개체를 자동으로 생성하고 연결합니다. 레코드 집합을 생성하기 전에 개체를 `CDatabase` 생성하고 연결할 필요가 없는 유용한 약식입니다.

### <a name="example"></a>예제

자세한 내용은 [레코드 집합: ODBC(테이블)에 대한 클래스 선언 문서를](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)참조하십시오.

## <a name="crecordsetdelete"></a><a name="delete"></a>C레코드 집합::D

현재 레코드를 삭제합니다.

```
virtual void Delete();
```

### <a name="remarks"></a>설명

성공적으로 삭제되면 레코드 집합의 필드 데이터 멤버가 Null 값으로 설정되고 삭제된 레코드를 `Move` 이동하려면 함수 중 하나를 명시적으로 호출해야 합니다. 삭제된 레코드를 이동한 후에는 레코드로 되돌릴 수 없습니다. 데이터 원본이 트랜잭션을 지원하는 경우 `Delete` 트랜잭션의 일부로 호출할 수 있습니다. 자세한 내용은 [ODBC(트랜잭션)](../../data/odbc/transaction-odbc.md)문서를 참조하십시오.

> [!NOTE]
> 대량 행 가져오기를 구현한 경우 `Delete`를 호출할 수 없습니다. 이렇게 하면 어설션이 실패합니다. 클래스는 `CRecordset` 대량 데이터 행을 업데이트하는 메커니즘을 제공하지는 않지만 ODBC API 함수를 `SQLSetPos`사용하여 사용자 고유의 함수를 작성할 수 있습니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

> [!CAUTION]
> 레코드 집합은 업데이터 처리용이어야 하며 호출할 `Delete`때 레코드 집합에 유효한 레코드 전류가 있어야 합니다. 그렇지 않으면 오류가 발생합니다. 예를 들어 레코드를 삭제하지만 다시 호출하기 `Delete` 전에 새 레코드로 `Delete` 스크롤하지 않으면 [CDBException](../../mfc/reference/cdbexception-class.md)을 throw합니다.

[AddNew](#addnew) 및 [편집과](#edit)달리 `Delete` 호출다음에 [업데이트](#update)에 대한 호출이 수행되지 않습니다. 호출에 `Delete` 실패하면 필드 데이터 멤버는 변경되지 않습니다.

### <a name="example"></a>예제

이 예제에서는 함수 프레임에서 만든 레코드 집합을 보여 주며, 이 예제에서는 함수 프레임에서 생성된 레코드 집합을 보여 주며, 이 예제에서는 이 예제에서는 데이터 `m_dbCust`원본에 이미 연결된 `CDatabase` 형식의 멤버 변수가 있다고 가정합니다.

[!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]

## <a name="crecordsetdobulkfieldexchange"></a><a name="dobulkfieldexchange"></a>C레코드 집합::DoBulkFieldExchange

데이터 원본에서 레코드 집합으로 대량 데이터 행을 교환하기 위해 호출됩니다. 대량 레코드 필드 교환(대량 RFX)을 구현합니다.

```
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 필드 교환 작업에 대한 컨텍스트를 지정하도록 이 개체를 이미 설정했습니다.

### <a name="remarks"></a>설명

대량 행 가져오기가 구현되면 프레임워크는 이 멤버 함수를 호출하여 데이터 원본에서 레코드 집합 개체로 데이터를 자동으로 전송합니다. `DoBulkFieldExchange`또한 레코드 집합의 선택을 위해 SQL 문 문자열의 매개 변수 자리 표시자에 매개 변수 데이터 멤버(있는 경우)를 바인딩합니다.

대량 행 가져오기가 구현되지 않은 경우 프레임워크는 [DoFieldExchange](#dofieldexchange)를 호출합니다. 대량 행 가져오기를 구현하려면 `CRecordset::useMultiRowFetch` [Open](#open) 멤버 함수에서 *dwOptions* 매개 변수 옵션을 지정해야 합니다.

> [!NOTE]
> `DoBulkFieldExchange`에서 파생된 클래스를 사용하는 경우에만 `CRecordset`사용할 수 있습니다. 에서 `CRecordset`직접 레코드 집합 개체를 만든 경우 [GetFieldValue](#getfieldvalue) 멤버 함수를 호출하여 데이터를 검색해야 합니다.

대량 레코드 필드 교환(대량 RFX)은 레코드 필드 교환(RFX)과 유사합니다. 데이터는 데이터 원본에서 레코드 집합 개체로 자동으로 전송됩니다. 그러나 `AddNew`을 `Edit` `Delete`호출하거나 `Update` 변경 내용을 데이터 원본으로 다시 전송할 수는 없습니다. 클래스는 `CRecordset` 현재 대량 데이터 행을 업데이트하는 메커니즘을 제공하지 않습니다. 그러나 ODBC API 함수를 `SQLSetPos`사용하여 사용자 고유의 함수를 작성할 수 있습니다.

ClassWizard는 대량 레코드 필드 교환을 지원하지 않습니다. 따라서 대량 RFX `DoBulkFieldExchange` 함수에 대한 호출을 작성하여 수동으로 재정의해야 합니다. 이러한 함수에 대한 자세한 내용은 [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md)항목을 참조하십시오.

대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요. 관련 정보는 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)문서를 참조하십시오.

## <a name="crecordsetdofieldexchange"></a><a name="dofieldexchange"></a>C레코드 세트::DoFieldExchange

레코드 집합의 필드 데이터 멤버와 데이터 원본의 해당 레코드 간에 양방향으로 데이터를 교환하도록 호출됩니다. 레코드 필드 교환(RFX)을 구현합니다.

```
virtual void DoFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 필드 교환 작업에 대한 컨텍스트를 지정하도록 이 개체를 이미 설정했습니다.

### <a name="remarks"></a>설명

대량 행 가져오기가 구현되지 않은 경우 프레임워크는 이 멤버 함수를 호출하여 레코드 집합 개체의 필드 데이터 멤버와 데이터 원본의 현재 레코드의 해당 열 간에 데이터를 자동으로 교환합니다. `DoFieldExchange`또한 레코드 집합의 선택을 위해 SQL 문 문자열의 매개 변수 자리 표시자에 매개 변수 데이터 멤버(있는 경우)를 바인딩합니다.

대량 행 가져오기가 구현된 경우 프레임워크는 [DoBulkFieldExchange](#dobulkfieldexchange)를 호출합니다. 대량 행 가져오기를 구현하려면 `CRecordset::useMultiRowFetch` [Open](#open) 멤버 함수에서 *dwOptions* 매개 변수 옵션을 지정해야 합니다.

> [!NOTE]
> `DoFieldExchange`에서 파생된 클래스를 사용하는 경우에만 `CRecordset`사용할 수 있습니다. 에서 `CRecordset`직접 레코드 집합 개체를 만든 경우 [GetFieldValue](#getfieldvalue) 멤버 함수를 호출하여 데이터를 검색해야 합니다.

RFX(레코드 필드 교환)라고 하는 필드 데이터 교환은 레코드 집합 개체의 필드 데이터 멤버에서 데이터 원본의 레코드 필드, 데이터 원본의 레코드에서 레코드 집합 개체에 이르기까지 양방향으로 작동합니다.

파생 된 레코드 집합 클래스에 대해 구현하기 `DoFieldExchange` 위해 일반적으로 수행해야 하는 유일한 작업은 ClassWizard를 사용하여 클래스를 만들고 필드 데이터 멤버의 이름과 데이터 형식을 지정하는 것입니다. ClassWizard가 작성하는 내용에 코드를 추가하여 매개 변수 데이터 멤버를 지정하거나 동적으로 바인딩하는 열을 처리할 수도 있습니다. 자세한 내용은 [레코드 집합: ODBC(동적으로 바인딩된 데이터 열)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)문서를 참조하십시오.

ClassWizard를 사용 하 여 파생 된 레코드 집합 클래스를 `DoFieldExchange` 선언 하는 경우 마법사는 다음 예제와 유사한 재정의를 씁니다.

[!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]

RFX 함수에 대한 자세한 내용은 [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md)항목을 참조하십시오.

에 대한 `DoFieldExchange`자세한 예 및 자세한 내용은 RFX 작동 방식 의 문서 [레코드 필드 교환을](../../data/odbc/record-field-exchange-how-rfx-works.md)참조하십시오. RFX에 대한 일반적인 정보는 [레코드 필드 교환](../../data/odbc/record-field-exchange-rfx.md)문서를 참조하십시오.

## <a name="crecordsetedit"></a><a name="edit"></a>C레코드 집합::편집

현재 레코드를 변경할 수 있습니다.

```
virtual void Edit();
```

### <a name="remarks"></a>설명

호출한 `Edit`후 해당 값을 직접 재설정하여 필드 데이터 멤버를 변경할 수 있습니다. 이후에 [Update](#update) 멤버 함수를 호출하여 데이터 원본에 변경 내용을 저장하면 작업이 완료됩니다.

> [!NOTE]
> 대량 행 가져오기를 구현한 경우 `Edit`를 호출할 수 없습니다. 이렇게 하면 어설션이 실패합니다. 클래스는 `CRecordset` 대량 데이터 행을 업데이트하는 메커니즘을 제공하지는 않지만 ODBC API 함수를 `SQLSetPos`사용하여 사용자 고유의 함수를 작성할 수 있습니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

`Edit`레코드 집합의 데이터 멤버 의 값을 저장합니다. 호출하는 `Edit`경우 변경한 다음 `Edit` 다시 호출하면 레코드 값이 첫 번째 `Edit` 호출 이전의 값으로 복원됩니다.

경우에 따라 Null(데이터가 포함되지 않은)으로 열을 업데이트할 수 있습니다. 이렇게 하려면 TRUE 매개 변수를 사용하여 [SetFieldNull을](#setfieldnull) 호출하여 Null 필드를 표시합니다. 이렇게 하면 열이 업데이트됩니다. 값이 변경되지 않은 경우에도 데이터 원본에 필드를 작성하려면 TRUE 매개 변수를 사용하여 [SetFieldDirty를](#setfielddirty) 호출합니다. 필드에 Null 값이 있는 경우에도 작동합니다.

데이터 원본이 트랜잭션을 지원하는 경우 `Edit` 트랜잭션의 일부로 호출할 수 있습니다. [CDatabase::BeginTrans를](../../mfc/reference/cdatabase-class.md#begintrans) 호출하기 전에 `Edit` 레코드 집합이 열린 후에 호출해야 합니다. 또한 [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) 호출은 작업을 완료하기 `Update` 위해 `Edit` 호출하는 대신 사용할 수 없습니다. 트랜잭션에 대한 자세한 내용은 [클래스 CDatabase](../../mfc/reference/cdatabase-class.md)를 참조하십시오.

현재 잠금 모드에 따라 업데이트중인 레코드는 다른 `Edit` 레코드로 `Update` 전화하거나 스크롤할 때까지 잠길 수 `Edit` 있거나 통화 중에만 잠길 수 있습니다. [SetLockingMode를](#setlockingmode)사용하면 잠금 모드를 변경할 수 있습니다.

을 호출하기 `Update`전에 새 레코드로 스크롤하면 현재 레코드의 이전 값이 복원됩니다. 업데이트할 수 없는 `Edit` 레코드 집합을 호출하거나 현재 레코드가 없는 경우 A가 `CDBException` throw됩니다.

자세한 내용은 [문서 트랜잭션(ODBC)](../../data/odbc/transaction-odbc.md) 및 [레코드 집합: 잠금 레코드(ODBC)를](../../data/odbc/recordset-locking-records-odbc.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]

## <a name="crecordsetflushresultset"></a><a name="flushresultset"></a>C레코드 집합::플러시 결과 집합

여러 결과 집합이 있는 경우 미리 정의된 쿼리(저장 프로시저)의 다음 결과 집합을 검색합니다.

```
BOOL FlushResultSet();
```

### <a name="return-value"></a>Return Value

검색할 결과 집합이 더 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

현재 결과 `FlushResultSet` 집합의 커서가 완전히 완료된 경우에만 호출해야 합니다. 호출하여 `FlushResultSet`설정된 다음 결과를 검색할 때 해당 결과 집합에서 커서가 유효하지 않습니다. 호출한 `FlushResultSet`후 [MoveNext](#movenext) 멤버 함수를 호출해야 합니다.

미리 정의된 쿼리가 출력 매개 변수 또는 입력/출력 `FlushResultSet` 매개 변수를 사용하는 경우 이러한 매개 변수 값을 얻으려면 반환(값 0)이 될 `FALSE` 때까지 호출해야 합니다.

`FlushResultSet`ODBC API 함수를 `SQLMoreResults`호출합니다. SQL_ERROR `SQLMoreResults` 반환하거나 SQL_INVALID_HANDLE `FlushResultSet` 경우 예외가 throw됩니다. 자세한 `SQLMoreResults`내용은 Windows SDK를 참조하십시오.

을 호출하려면 `FlushResultSet`저장 프로시저에 바인딩된 필드가 있어야 합니다.

### <a name="example"></a>예제

다음 코드는 입력 `COutParamRecordset` 매개 `CRecordset`변수와 출력 매개 변수가 있는 미리 정의된 쿼리를 기반으로 -derived 개체이고 여러 결과 집합이 있다고 가정합니다. [DoFieldExchange](#dofieldexchange) 재정의의 구조를 기록합니다.

[!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]

[!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]

## <a name="crecordsetgetbookmark"></a><a name="getbookmark"></a>C레코드 집합::GetBookmark

현재 레코드의 책갈피 값을 가져옵니다.

```cpp
void GetBookmark(CDBVariant& varBookmark);
```

### <a name="parameters"></a>매개 변수

*바북마크*<br/>
현재 레코드의 책갈피를 나타내는 [CDBVariant](../../mfc/reference/cdbvariant-class.md) 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

레코드 집합에서 책갈피가 지원되는지 확인하려면 [CanBookmark를](#canbookmark)호출합니다. 북마크가 지원되는 경우 책갈피를 사용할 `CRecordset::useBookmarks` 수 있도록 하려면 [Open](#open) 멤버 함수의 *dwOptions* 매개 변수에서 옵션을 설정해야 합니다.

> [!NOTE]
> 책갈피를 지원하지 않거나 사용할 `GetBookmark` 수 없는 경우 호출하면 예외가 throw됩니다. 책갈피는 정방향 전용 레코드 집합에서 지원되지 않습니다.

`GetBookmark`현재 레코드의 책갈피 값을 개체에 `CDBVariant` 할당합니다. 다른 레코드로 이동한 후 언제든지 해당 레코드로 돌아가려면 해당 `CDBVariant` 개체를 사용하여 [SetBookmark를](#setbookmark) 호출합니다.

> [!NOTE]
> 특정 레코드 집합 작업 후 책갈피는 더 이상 유효하지 않을 수 있습니다. 예를 들어 다음에 `GetBookmark` 호출하는 `Requery`경우 `SetBookmark`을 사용하여 레코드로 돌아가지 못할 수 있습니다. [CDatabase::GetBookmark지속성으로](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) 안전하게 호출할 `SetBookmark`수 있는지 확인합니다.

책갈피 및 레코드 집합 탐색에 대한 자세한 내용은 [레코드 집합: 북마크 및 절대 위치(ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) 및 [레코드 집합: 스크롤(ODBC)](../../data/odbc/recordset-scrolling-odbc.md)문서를 참조하십시오.

## <a name="crecordsetgetdefaultconnect"></a><a name="getdefaultconnect"></a>C레코드 집합::GetDefaultConnect

기본 연결 문자열을 얻으려면 호출됩니다.

```
virtual CString GetDefaultConnect();
```

### <a name="return-value"></a>Return Value

기본 `CString` 연결 문자열을 포함하는 A입니다.

### <a name="remarks"></a>설명

프레임워크는 이 멤버 함수를 호출하여 레코드 집합의 기반이 되는 데이터 원본에 대한 기본 연결 문자열을 가져옵니다. ClassWizard는 테이블 및 열에 대한 정보를 얻기 위해 ClassWizard에서 사용하는 것과 동일한 데이터 원본을 식별하여 이 함수를 구현합니다. 응용 프로그램을 개발하는 동안 이 기본 연결을 사용하면 편리할 수 있습니다. 그러나 기본 연결은 응용 프로그램의 사용자에게 적합하지 않을 수 있습니다. 이 경우 ClassWizard 의 버전을 삭제하여 이 함수를 다시 구현해야 합니다. 연결 문자열에 대한 자세한 내용은 [ODBC(데이터 원본)](../../data/odbc/data-source-odbc.md)문서를 참조하십시오.

## <a name="crecordsetgetdefaultsql"></a><a name="getdefaultsql"></a>C레코드 집합::GetDefaultSQL

실행할 기본 SQL 문자열을 얻으려면 호출됩니다.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Return Value

기본 `CString` SQL 문을 포함하는 A입니다.

### <a name="remarks"></a>설명

프레임워크는 이 멤버 함수를 호출하여 레코드 집합의 기반이 되는 기본 SQL 문을 가져옵니다. 테이블 이름 또는 SQL **SELECT** 문일 수 있습니다.

ClassWizard를 사용 하 여 레코드 집합 클래스를 선언 하 여 기본 SQL 문을 간접적으로 정의 하 고 ClassWizard는이 작업을 수행 합니다.

직접 사용하기 위해 SQL 문 문자열이 `GetSQL`필요한 경우 레코드 집합이 열릴 때 레코드 집합의 레코드를 선택하는 데 사용되는 SQL 문을 반환하는 call을 호출합니다. 클래스의 재정의에서 기본 SQL 문자열을 편집할 `GetDefaultSQL`수 있습니다. 예를 들어 **CALL** 문을 사용하여 미리 정의된 쿼리에 대한 호출을 지정할 수 있습니다. 그러나 편집하는 `GetDefaultSQL`경우 데이터 원본의 열 수와 `m_nFields` 일치하도록 수정해야 합니다.

자세한 내용은 [레코드 집합: ODBC(테이블)에 대한 클래스 선언 문서를](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)참조하십시오.

> [!CAUTION]
> 프레임워크에서 테이블 이름을 식별할 수 없거나 여러 테이블 이름이 제공된 경우 또는 CALL 문을 해석할 수 없는 경우 **테이블** 이름이 비어 있습니다. **CALL** 문을 사용하는 경우 중괄호와 **CALL** 키워드 사이에 공백을 삽입해서는 안 되며, SELECT **문에서** 중괄호 앞이나 **SELECT** 키워드 앞에 공백을 삽입해서는 안 됩니다.

## <a name="crecordsetgetfieldvalue"></a><a name="getfieldvalue"></a>C레코드 집합::겟필드밸류

현재 레코드에서 필드 데이터를 검색합니다.

```cpp
void GetFieldValue(
    LPCTSTR lpszName,
    CDBVariant& varValue,
    short nFieldType = DEFAULT_FIELD_TYPE);

void GetFieldValue(
    short nIndex,
    CDBVariant& varValue,
    short nFieldType = DEFAULT_FIELD_TYPE);

void GetFieldValue(
    short nIndex,
    CStringA& strValue);

void GetFieldValue(
    short nIndex,
    CStringW& strValue);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
필드의 이름입니다.

*varValu*e 필드의 값을 저장할 [CDBVariant](../../mfc/reference/cdbvariant-class.md) 개체에 대한 참조입니다.

*n필드 타입*<br/>
필드의 ODBC C 데이터 형식입니다. 기본값을 DEFAULT_FIELD_TYPE 다음 `GetFieldValue` 표를 기반으로 SQL 데이터 형식에서 C 데이터 형식을 결정합니다. 그렇지 않으면 데이터 형식을 직접 지정하거나 호환되는 데이터 형식을 선택할 수 있습니다. 예를 들어 모든 데이터 형식을 SQL_C_CHAR 저장할 수 있습니다.

|C 데이터 형식|SQL 데이터 형식|
|-----------------|-------------------|
|SQL_C_BIT|SQL_BIT|
|SQL_C_UTINYINT|SQL_TINYINT|
|SQL_C_SSHORT|SQL_SMALLINT|
|SQL_C_SLONG|SQL_INTEGER|
|SQL_C_FLOAT|SQL_REAL|
|SQL_C_DOUBLE|SQL_FLOATSQL_DOUBLE|
|SQL_C_TIMESTAMP|SQL_DATESQL_TIMESQL_TIMESTAMP|
|SQL_C_CHAR|SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR|
|SQL_C_BINARY|SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY|

ODBC 데이터 형식에 대한 자세한 내용은 Windows SDK의 부록 D에서 "SQL 데이터 유형" 및 "C 데이터 유형" 항목을 참조하십시오.

*nIndex*<br/>
필드의 0기반 인덱스입니다.

*strValue*<br/>
필드의 데이터 형식에 관계없이 텍스트로 변환된 필드의 값을 저장하는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이름을 또는 인덱스로 필드를 조회할 수 있습니다. 필드 값을 `CDBVariant` 개체 또는 개체에 저장할 `CString` 수 있습니다.

벌크 행 페칭을 구현한 경우 현재 레코드는 항상 행 집합의 첫 번째 레코드에 배치됩니다. 지정된 `GetFieldValue` 행 집합 내의 레코드에서 사용하려면 먼저 [SetRowsetCursorPosition](#setrowsetcursorposition) 함수를 호출하여 커서를 해당 행 집합 내의 원하는 행으로 이동해야 합니다. 그런 `GetFieldValue` 다음 해당 행을 호출합니다. 대량 행 가져오기를 구현하려면 `CRecordset::useMultiRowFetch` [Open](#open) 멤버 함수에서 *dwOptions* 매개 변수 옵션을 지정해야 합니다.

디자인 타임에 정적으로 바인딩하는 대신 런타임에 필드를 동적으로 가져오는 데 사용할 `GetFieldValue` 수 있습니다. 예를 들어 `CRecordset`에서 레코드 집합 개체를 직접 선언한 `GetFieldValue` 경우 필드 데이터를 검색하는 데 사용해야 합니다. 레코드 필드 교환(RFX) 또는 대량 레코드 필드 교환(대량 RFX)은 구현되지 않습니다.

> [!NOTE]
> `CRecordset`에서 파생되지 않고 레코드 집합 개체를 선언하는 경우 ODBC 커서 라이브러리가 로드되지 않습니다. 커서 라이브러리에는 레코드 집합에 하나 이상의 바인딩된 열이 있어야 합니다. 그러나 직접 사용하면 `CRecordset` 열이 바인딩되지 않습니다. 멤버는 [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) 및 [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) 컨트롤 커서 라이브러리로드 여부를 제어합니다.

`GetFieldValue`ODBC API 함수를 `SQLGetData`호출합니다. 드라이버가 필드 값의 실제 길이에 대해 SQL_NO_TOTAL `GetFieldValue` 값을 출력하는 경우 예외를 throw합니다. 자세한 `SQLGetData`내용은 Windows SDK를 참조하십시오.

### <a name="example"></a>예제

다음 샘플 코드는 에서 `GetFieldValue` 직접 선언된 레코드 `CRecordset`집합 개체에 대한 호출을 보여 줍니다.

[!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]

> [!NOTE]
> DAO 클래스와 `CDaoRecordset` `CRecordset` 달리 멤버 `SetFieldValue` 함수가 없습니다. 에서 `CRecordset`직접 개체를 만드는 경우 효과적으로 읽기 전용입니다.

대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

## <a name="crecordsetgetodbcfieldcount"></a><a name="getodbcfieldcount"></a>C레코드 집합::GetODBC필드카운트

레코드 집합 개체의 총 필드 수를 검색합니다.

```
short GetODBCFieldCount() const;
```

### <a name="return-value"></a>Return Value

레코드 집합의 필드 수입니다.

### <a name="remarks"></a>설명

레코드 집합 을 만드는 것에 대한 자세한 내용은 [레코드 집합: 레코드 집합 만들기 및 종료 레코드 집합(ODBC)을](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)참조하십시오.

## <a name="crecordsetgetodbcfieldinfo"></a><a name="getodbcfieldinfo"></a>C레코드 집합::GetODBCFieldInfo

레코드 집합의 필드에 대한 정보를 가져옵니다.

```cpp
void GetODBCFieldInfo(
    LPCTSTR lpszName,
    CODBCFieldInfo& fieldinfo);

void GetODBCFieldInfo(
    short nIndex,
    CODBCFieldInfo& fieldinfo);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
필드의 이름입니다.

*Fieldinfo*<br/>
구조에 대한 `CODBCFieldInfo` 참조입니다.

*nIndex*<br/>
필드의 0기반 인덱스입니다.

### <a name="remarks"></a>설명

함수의 한 버전을 사용하면 이름으로 필드를 조회할 수 있습니다. 다른 버전에서는 인덱스별로 필드를 조회할 수 있습니다.

반환된 정보에 대한 설명은 [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md) 구조를 참조하십시오.

레코드 집합 을 만드는 것에 대한 자세한 내용은 [레코드 집합: 레코드 집합 만들기 및 종료 레코드 집합(ODBC)을](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)참조하십시오.

## <a name="crecordsetgetrecordcount"></a><a name="getrecordcount"></a>C레코드 집합::GetRecordCount

레코드 집합의 크기를 결정합니다.

```
long GetRecordCount() const;
```

### <a name="return-value"></a>Return Value

레코드 집합의 레코드 수입니다. 레코드 집합에 레코드가 없는 경우 0입니다. 또는 -1 을 확인할 수 없는 경우

### <a name="remarks"></a>설명

> [!CAUTION]
> 레코드 수는 사용자가 레코드를 통과할 때 가장 높은 번호의 레코드인 "하이 워터 마크"로 유지됩니다. 총 레코드 수는 사용자가 마지막 레코드를 넘어 이동한 후에만 알 수 있습니다. 성능상의 이유로 을 호출할 `MoveLast`때 개수가 업데이트되지 않습니다. 레코드를 직접 계산하려면 `MoveNext` 0이 아닌 레코드를 반환할 때까지 `IsEOF` 반복적으로 호출합니다. 를 통해 `CRecordset:AddNew` 레코드를 추가하고 수를 `Update` 증가; 을 통해 `CRecordset::Delete` 레코드를 삭제하면 수가 줄어듭니다.

## <a name="crecordsetgetrowsetsize"></a><a name="getrowsetsize"></a>C레코드 집합::GetRowsetSize

지정된 가져오기 중에 검색할 행 수에 대한 현재 설정을 가져옵니다.

```
DWORD GetRowsetSize() const;
```

### <a name="return-value"></a>Return Value

지정된 가져오기 중에 검색할 행 수입니다.

### <a name="remarks"></a>설명

대량 행 페칭을 사용하는 경우 레코드 집합이 열릴 때기본 행 집합 크기는 25입니다. 그렇지 않으면 1입니다.

대량 행 가져오기를 구현하려면 `CRecordset::useMultiRowFetch` [Open](#open) 멤버 함수의 *dwOptions* 매개 변수에 옵션을 지정해야 합니다. 행 집합 크기에 대한 설정을 변경하려면 [SetRowsetSize를](#setrowsetsize)호출합니다.

대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

## <a name="crecordsetgetrowsfetched"></a><a name="getrowsfetched"></a>C레코드 집합::GetRowsFetched

가져오기 후 실제로 검색된 레코드 수를 결정합니다.

```
DWORD GetRowsFetched() const;
```

### <a name="return-value"></a>Return Value

지정된 가져오기 후 데이터 원본에서 검색된 행 수입니다.

### <a name="remarks"></a>설명

이 기능은 대량 행 가져오기를 구현한 경우에 유용합니다. 행 집합 크기는 일반적으로 가져오기에서 검색할 행 수를 나타냅니다. 그러나 레코드 집합의 총 행 수는 행 집합에서 검색할 행 수에도 영향을 줍니다. 예를 들어 레코드 집합에 행 크기 설정이 4인 레코드가 10개 있는 경우 `MoveNext` 호출하여 레코드 집합을 반복하면 최종 행 집합에 레코드가 2개만 표시됩니다.

대량 행 가져오기를 구현하려면 `CRecordset::useMultiRowFetch` [Open](#open) 멤버 함수의 *dwOptions* 매개 변수에 옵션을 지정해야 합니다. 행 집합 크기를 지정하려면 [SetRowsetSize를](#setrowsetsize)호출합니다.

대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]

## <a name="crecordsetgetrowstatus"></a><a name="getrowstatus"></a>C레코드 집합::GetRowStatus

현재 행 집합에서 행에 대한 상태를 가져옵니다.

```
WORD GetRowStatus(WORD wRow) const;
```

### <a name="parameters"></a>매개 변수

*wRow*<br/>
현재 행 집합에서 행의 한 기반 위치입니다. 이 값은 1에서 행 집합의 크기까지 다양합니다.

### <a name="return-value"></a>Return Value

행의 상태 값입니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

`GetRowStatus`데이터 원본에서 마지막으로 검색된 이후 상태의 변경 사항이 행에 변경되었거나 *wRow에* 해당하는 행이 가져오지 않은 값을 반환합니다. 다음 표에서는 가능한 반환 값을 보여 줍니다.

|상태 값|Description|
|------------------|-----------------|
|SQL_ROW_SUCCESS|행은 변경되지 않습니다.|
|SQL_ROW_UPDATED|행이 업데이트되었습니다.|
|SQL_ROW_DELETED|행이 삭제된 경우|
|SQL_ROW_ADDED|행이 추가되었습니다.|
|SQL_ROW_ERROR|오류로 인해 행을 복구할 수 없습니다.|
|SQL_ROW_NOROW|*wRow*에 해당하는 행이 없습니다.|

자세한 내용은 Windows SDK의 `SQLExtendedFetch` ODBC API 함수를 참조하십시오.

## <a name="crecordsetgetstatus"></a><a name="getstatus"></a>C레코드 집합::GetStatus

레코드 집합에서 현재 레코드의 인덱스와 마지막 레코드가 보였는지 여부를 결정합니다.

```cpp
void GetStatus(CRecordsetStatus& rStatus) const;
```

### <a name="parameters"></a>매개 변수

*r 상태 지정*<br/>
`CRecordsetStatus` 개체에 대한 참조입니다. 자세한 내용은 주의 섹션을 참조하십시오.

### <a name="remarks"></a>설명

`CRecordset`인덱스를 추적하려고 시도하지만 경우에 따라 불가능할 수 있습니다. 설명은 [GetRecordCount를](#getrecordcount) 참조하십시오.

구조에는 `CRecordsetStatus` 다음과 같은 양식이 있습니다.

```cpp
struct CRecordsetStatus
{
    long m_lCurrentRecord;
    BOOL m_bRecordCountFinal;
};
```

두 구성원의 `CRecordsetStatus` 의미는 다음과 같은 의미를 갖습니다.

- `m_lCurrentRecord`알려진 경우 레코드 집합에 현재 레코드의 0기반 인덱스를 포함합니다. 인덱스를 확인할 수 없는 경우 이 멤버에는 AFX_CURRENT_RECORD_UNDEFINED(-2)이 포함됩니다. TRUE(빈 레코드 집합 또는 첫 번째 레코드 `m_lCurrentRecord` 전에 스크롤시도)인 경우 `IsBOF` AFX_CURRENT_RECORD_BOF(-1)로 설정됩니다. 첫 번째 레코드의 경우 0, 두 번째 레코드 1 등으로 설정됩니다.

- `m_bRecordCountFinal`레코드 집합의 총 레코드 수가 결정된 경우 0이 아닙니다. 일반적으로 이 작업은 레코드 집합의 시작 부분에서 시작하여 `MoveNext` 0이 아닌 반환될 때까지 `IsEOF` 호출하여 수행해야 합니다. 이 멤버가 0이면 레코드 수가 `GetRecordCount`-1이 아니라면 반환되는 레코드 수는 레코드의 "높은 워터 마크" 수입니다.

## <a name="crecordsetgetsql"></a><a name="getsql"></a>C레코드 집합::GetSQL

이 멤버 함수를 호출하여 레코드 집합이 열릴 때 레코드 집합의 레코드를 선택하는 데 사용된 SQL 문을 가져옵니다.

```
const CString& GetSQL() const;
```

### <a name="return-value"></a>Return Value

SQL 문을 포함하는 `CString` 에 대한 **const** 참조입니다.

### <a name="remarks"></a>설명

일반적으로 SQL **SELECT** 문이 됩니다. 반환되는 `GetSQL` 문자열은 읽기 전용입니다.

반환되는 `GetSQL` 문자열은 일반적으로 `Open` *멤버 함수에 lpszSQL* 매개 변수의 레코드 집합에 전달한 문자열과 다릅니다. 이는 레코드 집합이 ClassWizard로 지정한 내용, `Open` `m_strFilter` 및 `m_strSort` 데이터 멤버에 지정한 내용 및 지정한 매개 변수를 기반으로 전체 SQL 문을 생성하기 때문입니다. 레코드 집합이 이 SQL 문을 구성하는 방법에 대한 자세한 내용은 [레코드 집합: 레코드 집합(ODBC)을 선택하는 방법](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)문서를 참조하십시오.

> [!NOTE]
> [Open](#open)을 호출한 후에만 이 멤버 함수를 호출합니다.

## <a name="crecordsetgettablename"></a><a name="gettablename"></a>C레코드 집합::GetTableName

레코드 집합의 쿼리의 기반이 되는 SQL 테이블의 이름을 가져옵니다.

```
const CString& GetTableName() const;
```

### <a name="return-value"></a>Return Value

레코드 집합이 테이블을 `CString` 기반으로 하는 경우 테이블 이름을 포함하는 **const** 참조입니다. 그렇지 않으면 빈 문자열이 됩니다.

### <a name="remarks"></a>설명

`GetTableName`레코드 집합이 여러 테이블이나 미리 정의된 쿼리(저장 프로시저)의 조인이 아닌 테이블을 기반으로 하는 경우에만 유효합니다. 이름은 읽기 전용입니다.

> [!NOTE]
> [Open](#open)을 호출한 후에만 이 멤버 함수를 호출합니다.

## <a name="crecordsetisbof"></a><a name="isbof"></a>C레코드 집합::IsBOF

레코드 집합이 첫 번째 레코드 앞에 위치한 경우 0이 아닌 것을 반환합니다. 현재 레코드가 없습니다.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Return Value

레코드 집합에 레코드가 없거나 첫 번째 레코드 앞에 뒤로 스크롤한 경우 Nonzero입니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

레코드에서 레코드로 스크롤하기 전에 이 멤버 함수를 호출하여 레코드 집합의 첫 번째 레코드 보다 먼저 갔는지 여부를 알아봅니다. 레코드 집합에 `IsBOF` 레코드가 포함되어 있는지 또는 비어 있는지 여부를 확인하는 데 함께 `IsEOF` 사용할 수도 있습니다. 호출 `Open`직후 에 레코드 집합에 레코드가 `IsBOF` 없는 경우 0이 아닌 반환합니다. 레코드가 하나 이상 있는 레코드 집합을 열면 첫 번째 `IsBOF` 레코드가 현재 레코드이고 0을 반환합니다.

첫 번째 레코드가 현재 레코드이고 `MovePrev` `IsBOF` 호출하면 이후에 0이 아닌 레코드가 반환됩니다. 0이 아닌 것을 `MovePrev`반환하고 호출하면 `IsBOF` 오류가 발생합니다. 0이 아닌 것을 반환하면 `IsBOF` 현재 레코드가 정의되지 않으며 현재 레코드가 필요한 모든 작업에 오류가 발생합니다.

### <a name="example"></a>예제

이 `IsBOF` `IsEOF` 예제에서는 코드가 양방향으로 레코드 집합을 스크롤할 때 레코드 집합의 한계를 검색하고 검색합니다.

[!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]

## <a name="crecordsetisdeleted"></a><a name="isdeleted"></a>C레코드 집합::삭제됨

현재 레코드가 삭제되었는지 여부를 확인합니다.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Return Value

레코드 집합이 삭제된 레코드에 배치된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

레코드로 스크롤하여 `IsDeleted` TRUE(영하지 않은)를 반환하는 경우 다른 레코드 집합 작업을 수행하려면 먼저 다른 레코드로 스크롤해야 합니다.

레코드 `IsDeleted` 집합 유형, 레코드 집합이 업데이터인지 여부, 레코드 집합을 열 때 `CRecordset::skipDeletedRecords` 옵션을 지정했는지 여부, 드라이버팩 삭제된 레코드 팩 여부, 여러 사용자 여부 등 여러 요인에 따라 결과가 달라집니다.

드라이버 패킹 `CRecordset::skipDeletedRecords` 및 드라이버 패킹에 대한 자세한 내용은 [Open](#open) 멤버 기능을 참조하십시오.

> [!NOTE]
> 대량 행 가져오기를 구현한 경우 을 `IsDeleted`호출해서는 안 됩니다. 대신 GetRowStatus 멤버 함수를 [호출합니다.](#getrowstatus) 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

## <a name="crecordsetiseof"></a><a name="iseof"></a>C레코드 집합::IsEOF

레코드 집합이 마지막 레코드 다음으로 배치된 경우 0이 아닌 것을 반환합니다. 현재 레코드가 없습니다.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Return Value

레코드 집합에 레코드가 없거나 마지막 레코드 를 넘어 스크롤한 경우 Nonzero입니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

레코드에서 레코드로 스크롤할 때 이 멤버 함수를 호출하여 레코드 집합의 마지막 레코드를 초과했는지 여부를 알아봅니다. 레코드 집합에 `IsEOF` 레코드가 포함되어 있는지 또는 비어 있는지 여부를 확인하는 데 사용할 수도 있습니다. 호출 `Open`직후 에 레코드 집합에 레코드가 `IsEOF` 없는 경우 0이 아닌 반환합니다. 레코드가 하나 이상 있는 레코드 집합을 열면 첫 번째 `IsEOF` 레코드가 현재 레코드이고 0을 반환합니다.

마지막 레코드가 호출할 `MoveNext`때 현재 `IsEOF` 레코드인 경우 이후에 0이 아닌 레코드가 반환됩니다. 0이 아닌 것을 `MoveNext`반환하고 호출하면 `IsEOF` 오류가 발생합니다. 0이 아닌 것을 반환하면 `IsEOF` 현재 레코드가 정의되지 않으며 현재 레코드가 필요한 모든 작업에 오류가 발생합니다.

### <a name="example"></a>예제

[IsBOF](#isbof)에 대한 예제를 참조하십시오.

## <a name="crecordsetisfielddirty"></a><a name="isfielddirty"></a>C레코드 집합::IsFieldDirty

[편집](#edit) 또는 [AddNew가](#addnew) 호출된 이후 지정된 필드 데이터 멤버가 변경되었는지 여부를 결정합니다.

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
확인하려는 상태 또는 NULL을 사용하여 필드가 더러워진지 여부를 확인하는 필드 데이터 멤버에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

호출 한 후 지정된 필드 데이터 `AddNew` 멤버가 변경된 경우 Nonzero 또는 `Edit`; 그렇지 않으면 0.

### <a name="remarks"></a>설명

모든 더러운 필드 데이터 멤버의 데이터는 현재 레코드가 [의 Update](#update) 멤버 함수에 대한 호출(호출 `CRecordset` 후 또는)에 `Edit` `AddNew`의해 업데이트될 때 데이터 원본의 레코드로 전송됩니다.

> [!NOTE]
> 이 멤버 함수는 대량 행 가져오기를 사용하는 레코드 집합에는 적용되지 않습니다. 대량 행 가져오기를 구현한 `IsFieldDirty` 경우 항상 FALSE를 반환하고 어설션에 실패합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

필드의 `IsFieldDirty` 더러운 상태가 다시 평가되므로 [호출은 SetFieldDirty에](#setfielddirty) 대한 이전 호출의 효과를 재설정합니다. 이 `AddNew` 경우 현재 필드 값이 의사 null 값과 다른 경우 필드 상태가 더러워집니다. 이 `Edit` 경우 필드 값이 캐시된 값과 다른 경우 필드 상태가 더러워지게 됩니다.

`IsFieldDirty`[DoFieldExchange를](#dofieldexchange)통해 구현됩니다.

더티 플래그에 대한 자세한 내용은 [레코드 집합: 레코드 집합이 레코드(ODBC)를 선택하는 방법](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)문서를 참조하십시오.

## <a name="crecordsetisfieldnull"></a><a name="isfieldnull"></a>C레코드 집합::IsFieldNull

현재 레코드의 지정된 필드가 Null인 경우 비영을 반환합니다(값이 없음).

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
확인하려는 상태 또는 NULL을 사용하여 필드가 Null인지 여부를 확인하는 필드 데이터 멤버에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

지정된 필드 데이터 멤버에 Null로 플래그가 지정된 경우 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수를 호출하여 레코드 집합의 지정된 필드 데이터 멤버가 Null로 플래그가 지정되었는지 확인합니다. (데이터베이스 용어에서 Null은 "값이 없음"을 의미하며 C++에서 NULL과 동일하지 않습니다. 필드 데이터 멤버에 Null플래그가 지정되면 값이 없는 현재 레코드의 열로 해석됩니다.

> [!NOTE]
> 이 멤버 함수는 대량 행 가져오기를 사용하는 레코드 집합에는 적용되지 않습니다. 대량 행 가져오기를 구현한 `IsFieldNull` 경우 항상 FALSE를 반환하고 어설션에 실패합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

`IsFieldNull`[DoFieldExchange를](#dofieldexchange)통해 구현됩니다.

## <a name="crecordsetisfieldnullable"></a><a name="isfieldnullable"></a>C레코드 집합::필드Nullable

현재 레코드의 지정된 필드를 Null로 설정할 수 있는 경우 0이 아닌 필드를 반환합니다(값이 없음).

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
확인하려는 상태 또는 NULL을 사용하여 필드를 Null 값으로 설정할 수 있는지 여부를 확인하는 필드 데이터 멤버에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 호출하여 지정된 필드 데이터 멤버가 "null"인지 여부를 결정합니다(Null 값으로 설정할 수 있습니다. C++ NULL은 Null과 같지 않으며 데이터베이스 용어에서 "값이 없음"을 의미합니다.

> [!NOTE]
> 대량 행 가져오기를 구현한 경우 `IsFieldNullable`를 호출할 수 없습니다. 대신 [GetODBCFieldInfo](#getodbcfieldinfo) 멤버 함수를 호출하여 필드를 Null 값으로 설정할 수 있는지 여부를 확인합니다. 대량 행 가져오기를 `GetODBCFieldInfo`구현했는지 여부에 관계없이 항상 호출할 수 있습니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

Null이 될 수 없는 필드에는 값이 있어야 합니다. 레코드를 추가하거나 업데이트할 때 이러한 필드를 Null로 설정하려고 하면 데이터 원본이 추가 또는 업데이트를 거부하고 [Update에서](#update) 예외가 발생합니다. 예외는 `Update` [SetFieldNull](#setfieldnull)을 호출할 때가 아니라 호출할 때 발생합니다.

함수의 첫 번째 인수에 NULL을 사용하면 `outputColumn` 필드가 `param` 아닌 필드에만 함수가 적용됩니다. 예를 들어,

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

필드만 `outputColumn` NULL로 설정합니다. `param` 필드는 영향을 받지 않습니다.

`param` 필드에서 작업하려면 다음과 같이 작업하려는 개인의 `param` 실제 주소를 제공해야 합니다.

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

즉, 필드를 사용하여 `param` 모든 필드를 NULL로 `outputColumn` 설정할 수 없습니다.

`IsFieldNullable`[DoFieldExchange를](#dofieldexchange)통해 구현됩니다.

## <a name="crecordsetisopen"></a><a name="isopen"></a>C레코드 집합::이 열기

레코드 집합이 이미 열려 있는지 확인합니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Return Value

레코드 집합 개체의 [열기](#open) 또는 [다시 쿼리](#requery) 멤버 함수가 이전에 호출되었으며 레코드 집합이 닫히지 않은 경우 Nonzero입니다. 그렇지 않으면 0.

## <a name="crecordsetm_hstmt"></a><a name="m_hstmt"></a>C레코드 집합:m_hstmt

레코드 집합과 연결된 HSTMT 형식의 ODBC 문 데이터 구조에 대한 핸들을 포함합니다.

### <a name="remarks"></a>설명

ODBC 데이터 원본에 대한 각 쿼리는 HSTMT와 연결됩니다.

> [!CAUTION]
> [Open이](#open) `m_hstmt` 호출되기 전에는 사용하지 마십시오.

일반적으로 HSTMT에 직접 액세스할 필요는 없지만 SQL 문을 직접 실행하려면 HSTMT가 필요할 수 있습니다. 클래스의 `ExecuteSQL` `CDatabase` 멤버 함수는 을 `m_hstmt`사용하는 예제를 제공합니다.

## <a name="crecordsetm_nfields"></a><a name="m_nfields"></a>C레코드 집합::m_nFields

레코드 집합 클래스의 필드 데이터 멤버 수를 포함합니다. 즉, 데이터 원본에서 레코드 집합에서 선택한 열 수입니다.

### <a name="remarks"></a>설명

레코드 집합 클래스의 생성자는 올바른 `m_nFields` 숫자로 초기화해야 합니다. 대량 행 가져오기를 구현하지 않은 경우 ClassWizard는 레코드 집합 클래스를 선언하는 데 사용할 때 이 초기화를 작성합니다. 수동으로 작성할 수도 있습니다.

프레임워크는 이 번호를 사용하여 필드 데이터 멤버와 데이터 원본의 현재 레코드의 해당 열 간의 상호 작용을 관리합니다.

> [!CAUTION]
> `DoFieldExchange` 이 번호는 매개 변수가 `DoBulkFieldExchange` `CFieldExchange::outputColumn`있는 [SetFieldType에](../../mfc/reference/cfieldexchange-class.md#setfieldtype) 대한 호출 또는 이후에 등록된 "출력 열"의 수와 일치해야 합니다.

"레코드 집합: 동적으로 바인딩된 데이터 열"에 설명된 대로 열을 동적으로 바인딩할 수 있습니다. 이렇게 하면 동적으로 바인딩된 열에 대 한 또는 `m_nFields` `DoFieldExchange` `DoBulkFieldExchange` 멤버 함수에서 RFX 또는 대량 RFX 함수 호출 수를 반영 하도록 수를 늘려야 합니다.

자세한 내용은 [레코드 집합: 동적으로 바인딩된 데이터 열(ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) 및 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

### <a name="example"></a>예제

[RFX](../../data/odbc/record-field-exchange-using-rfx.md)를 사용하여 레코드 필드 교환 문서를 참조하십시오.

## <a name="crecordsetm_nparams"></a><a name="m_nparams"></a>C레코드 집합::m_nParams

레코드 집합 클래스의 매개 변수 데이터 멤버 수를 포함합니다. 즉, 레코드 집합의 쿼리와 함께 전달된 매개 변수 의 수입니다.

### <a name="remarks"></a>설명

레코드 집합 클래스에 매개 변수 데이터 멤버가 있는 경우 `m_nParams` 클래스의 생성자는 올바른 숫자로 초기화해야 합니다. `m_nParams` 기본값값은 0입니다. 매개 변수 데이터 멤버를 추가하는 경우(수동으로 수행해야 하는) 매개 변수 수를 반영하기 위해 클래스 생성자에 초기화를 수동으로 추가해야 `m_strFilter` 합니다(사용자 또는 `m_strSort` 문자열의 '자리 표시자 수만큼 이상).

프레임워크는 레코드 집합의 쿼리를 매개변수화할 때 이 번호를 사용합니다.

> [!CAUTION]
> 이 번호는 [SetFieldType에](../../mfc/reference/cfieldexchange-class.md#setfieldtype) 대한 호출 `DoFieldExchange` `DoBulkFieldExchange` 후에 등록된 "params" 수에 해당해야 `CFieldExchange::outputParam`하며 `CFieldExchange::inoutParam`의 매개 변수 값이 `CFieldExchange::inputParam` `CFieldExchange::param`있습니다.

### <a name="example"></a>예제

  [레코드 집합: 레코드 집합(ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) 및 [레코드 필드 교환: RFX 사용](../../data/odbc/record-field-exchange-using-rfx.md)매개 변수화 문서 참조.

## <a name="crecordsetm_pdatabase"></a><a name="m_pdatabase"></a>C레코드 집합::m_pDatabase

레코드 집합이 `CDatabase` 데이터 원본에 연결된 개체에 대한 포인터를 포함합니다.

### <a name="remarks"></a>설명

이 변수는 두 가지 방법으로 설정됩니다. 일반적으로 레코드 집합 개체를 생성할 때 이미 연결된 `CDatabase` 개체에 대한 포인터를 전달합니다. 대신 NULL을 전달하면 `CRecordset` `CDatabase` 개체를 만들고 연결합니다. 두 경우 `CRecordset` 모두 이 변수에 포인터를 저장합니다.

일반적으로 `m_pDatabase`에 저장된 포인터를 직접 사용할 필요가 없습니다. 그러나 `CRecordset`에 대한 사용자 고유의 확장을 작성하는 경우 포인터를 사용해야 할 수 있습니다. 예를 들어, 자신의 `CDBException`포인터를 throw하는 경우 포인터가 필요할 수 있습니다. 또는 트랜잭션 실행, 시간 시간 설정 또는 `CDatabase` SQL 문을 직접 실행하기 위해 클래스의 `CDatabase` `ExecuteSQL` 멤버 함수를 호출하는 등 동일한 개체를 사용하여 작업을 수행해야 하는 경우 필요할 수 있습니다.

## <a name="crecordsetm_strfilter"></a><a name="m_strfilter"></a>C레코드 집합:m_strFilter

레코드 집합 개체를 생성하지만 해당 `Open` 멤버 함수를 호출하기 전에 이 `CString` 데이터 멤버를 사용하여 SQL **WHERE** 절을 포함하는 것을 저장합니다.

### <a name="remarks"></a>설명

레코드 집합은 이 문자열을 사용하여 `Open` 또는 `Requery` 호출 중에 선택한 레코드를 제한(또는 필터링)합니다. 이 기능은 "캘리포니아에 기반을 둔 모든 영업 사원"("상태 = CA")과 같은 레코드의 하위 집합을 선택하는 데 유용합니다. **WHERE** 절에 대한 ODBC SQL 구문은

`WHERE search-condition`

문자열에 **WHERE** 키워드는 포함되지 않습니다. 프레임워크가 제공합니다.

또한 '' 자리 표시자를 배치하고, 각 자리 표시자에 대해 클래스의 매개 변수 데이터 멤버를 선언하고, 매개 변수를 런타임에 레코드 집합에 전달하여 필터 문자열을 매개 변수화할 수도 있습니다. 이렇게 하면 런타임에 필터를 생성할 수 있습니다. 자세한 내용은 [레코드 집합: 레코드 집합(ODBC) 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)문서를 참조하십시오.

SQL **WHERE** 절에 대한 자세한 내용은 [SQL](../../data/odbc/sql.md)을 참조하십시오. 레코드 선택 및 필터링에 대한 자세한 내용은 [레코드 집합: 필터 레코드(ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)을 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]

## <a name="crecordsetm_strsort"></a><a name="m_strsort"></a>C레코드 집합:m_strSort

레코드 집합 개체를 생성하지만 해당 `Open` 멤버 함수를 호출하기 전에 이 `CString` 데이터 멤버를 사용하여 SQL **ORDER BY** 절을 포함하는 것을 저장합니다.

### <a name="remarks"></a>설명

레코드 집합은 이 문자열을 사용하여 `Open` 또는 `Requery` 호출 중에 선택한 레코드를 정렬합니다. 이 기능을 사용하여 하나 이상의 열에서 레코드 집합을 정렬할 수 있습니다. **ORDER BY** 절에 대한 ODBC SQL 구문은

`ORDER BY sort-specification [, sort-specification]...`

여기서 정렬 사양이 정수 또는 열 이름입니다. 정렬 문자열의 열 목록에 "ASC" 또는 "DESC"를 추가하여 오름차순 또는 내림차순(순서가 기본적으로 오름차순)을 지정할 수도 있습니다. 선택한 레코드는 나열된 첫 번째 열에 의해 먼저 정렬된 다음 두 번째 열로 정렬됩니다. 예를 들어 성, 이름으로 "고객" 레코드 집합을 정렬할 수 있습니다. 나열할 수 있는 열 수는 데이터 원본에 따라 다릅니다. 자세한 내용은 Windows SDK를 참조하십시오.

문자열에는 **ORDER BY** 키워드가 포함되지 않습니다. 프레임워크가 제공합니다.

SQL 절에 대한 자세한 내용은 [SQL](../../data/odbc/sql.md)문서를 참조하십시오. 레코드 정렬에 대한 자세한 내용은 [레코드 집합: 레코드 정렬(ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)을 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]

## <a name="crecordsetmove"></a><a name="move"></a>C레코드 집합::이동

현재 레코드 포인터를 레코드 집합 내에서 앞으로 또는 뒤로 이동합니다.

```
virtual void Move(
    long nRows,
    WORD wFetchType = SQL_FETCH_RELATIVE);
```

### <a name="parameters"></a>매개 변수

*nRows*<br/>
앞으로 또는 뒤로 이동할 행 수입니다. 양수 값은 레코드 집합의 끝을 향해 앞으로 이동합니다. 음수 값은 시작 부분으로 뒤로 이동합니다.

*wFetchType*<br/>
가져올 행 집합을 `Move` 결정합니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

*nRows에*대해 0값을 전달하면 `Move` 현재 레코드를 새로 고칩니다. `Move` 현재 `AddNew` 또는 `Edit` 모드를 종료하고 호출되기 전에 `AddNew` 현재 `Edit` 레코드의 값을 복원합니다.

> [!NOTE]
> 레코드 집합을 통해 이동하면 삭제된 레코드를 건너뛸 수 없습니다. 자세한 내용은 [CRecordset::IsDeleted를](#isdeleted) 참조하십시오. 옵션 집합을 `CRecordset` `skipDeletedRecords` 통해 a를 `Move` 열면 *nRows* 매개 변수가 0인 경우 어설션합니다. 이 동작은 동일한 데이터를 사용하여 다른 클라이언트 응용 프로그램에서 삭제된 행을 새로 고치는 것을 방지합니다. 에 대한 설명은 [열기의](#open) `skipDeletedRecords` *dwOption* 매개 변수를 참조하십시오.

`Move`레코드 집합을 행 집합별로 재배치합니다. *nRows* 및 *wFetchType에*대한 `Move` 값을 기반으로 적절한 행 집합을 가져온 다음 해당 행 집합의 첫 번째 레코드를 현재 레코드로 만듭니다. 벌크 행 가져오기를 구현하지 않은 경우 행 집합 크기는 항상 1입니다. 행 집합을 `Move` 가져올 때 [직접 호출는 CheckRowsetError](#checkrowseterror) 함수를 호출하여 가져오기로 인한 오류를 처리합니다.

전달하는 `Move` 값에 따라 다른 `CRecordset` 멤버 함수와 동일합니다. 특히 *wFetchType* 값은 현재 레코드를 이동하는 데 보다 직관적이고 종종 선호되는 멤버 함수를 나타낼 수 있습니다.

다음 표에는 *wFetchType, wFetchType*및 `Move` *nRows를*기반으로 가져올 행 집합 및 *wFetchType에*해당하는 모든 동등한 멤버 함수에 대한 가능한 값이 나열됩니다. *wFetchType*

|wFetchType|가져온 행 집합|등가 멤버 기능|
|----------------|--------------------|--------------------------------|
|SQL_FETCH_RELATIVE(기본값)|현재 행 집합의 첫 번째 행에서 *nRows* 행을 시작하는 행 집합입니다.||
|SQL_FETCH_NEXT|다음 행 집합; *nRows는* 무시됩니다.|[MoveNext](#movenext)|
|SQL_FETCH_PRIOR|이전 행 집합; *nRows는* 무시됩니다.|[무브프레프](#moveprev)|
|SQL_FETCH_FIRST|레코드 집합의 첫 번째 행 집합입니다. *nRows는* 무시됩니다.|[이동우선](#movefirst)|
|SQL_FETCH_LAST|레코드 집합의 마지막 전체 행 집합입니다. *nRows는* 무시됩니다.|[Movelast](#movelast)|
|SQL_FETCH_ABSOLUTE|*nRows가* 0으로 > 경우 레코드 집합의 시작 부분에서 *nRows* 행을 시작하는 행 집합이 시작됩니다. *nRows가* 0으로 < 경우 레코드 집합의 끝에서 *nRows* 행을 시작하는 행 집합이 시작됩니다. *nRows* = 0이면 BOF(파일 시작) 조건이 반환됩니다.|[설정절대위치](#setabsoluteposition)|
|SQL_FETCH_BOOKMARK|책갈피 값이 *nRows에*해당하는 행 집합에서 시작하는 행 집합입니다.|[세트북마크](#setbookmark)|

> [!NOTE]
> 정방향 전용 레코드 `Move` 집합의 경우 *wFetchType*에 대한 SQL_FETCH_NEXT 값으로만 유효합니다.

> [!CAUTION]
> 호출은 `Move` 레코드 집합에 레코드가 없는 경우 예외를 throw합니다. 레코드 집합에 레코드가 있는지 확인하려면 [IsBOF](#isbof) 및 [IsEOF를](#iseof)호출합니다.

> [!NOTE]
> 레코드 집합의 시작 또는 끝을 지나 스크롤한`IsBOF` `IsEOF` 경우(또는 0이 `Move` 아닌 것을 `CDBException`반환) 함수를 호출하면 . 예를 들어 `IsEOF` 0이 아닌 `IsBOF` 것을 반환하고 반환하지 `MoveNext` 않으면 `MovePrev` 예외를 throw하지만 그렇지 않습니다.

> [!NOTE]
> 현재 레코드가 업데이트되거나 추가되는 동안 호출하면 `Move` 경고 없이 업데이트가 손실됩니다.

레코드 집합 탐색에 대한 자세한 내용은 [레코드 집합: 스크롤(ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 및 [레코드 집합: 책갈피 및 절대 위치(ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)문서를 참조하십시오. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요. 관련 정보는 Windows SDK의 `SQLExtendedFetch` ODBC API 함수를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]

## <a name="crecordsetmovefirst"></a><a name="movefirst"></a>C레코드 집합::이동우선

첫 번째 행 집합의 첫 번째 레코드를 현재 레코드로 만듭니다.

```cpp
void MoveFirst();
```

### <a name="remarks"></a>설명

대량 행 페칭이 구현되었는지 여부에 관계없이 레코드 집합의 첫 번째 레코드가 항상 됩니다.

레코드 집합을 연 `MoveFirst` 직후에 호출할 필요가 없습니다. 이 때 첫 번째 레코드(있는 경우)는 자동으로 현재 레코드입니다.

> [!NOTE]
> 이 멤버 함수는 정방향 전용 레코드 집합에 대해 유효하지 않습니다.

> [!NOTE]
> 레코드 집합을 통해 이동하면 삭제된 레코드를 건너뛸 수 없습니다. 자세한 내용은 [IsDeleted](#isdeleted) 멤버 함수를 참조하십시오.

> [!CAUTION]
> 레코드 집합에 `Move` 레코드가 없는 경우 함수를 호출하면 예외가 발생합니다. 레코드 집합에 레코드가 있는지 여부를 `IsBOF` `IsEOF`확인하려면 호출 및 .

> [!NOTE]
> 현재 레코드가 `Move` 업데이트되거나 추가되는 동안 함수를 호출하면 경고 없이 업데이트가 손실됩니다.

레코드 집합 탐색에 대한 자세한 내용은 [레코드 집합: 스크롤(ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 및 [레코드 집합: 책갈피 및 절대 위치(ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)문서를 참조하십시오. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

### <a name="example"></a>예제

  [IsBOF](#isbof)에 대한 예제를 참조하십시오.

## <a name="crecordsetmovelast"></a><a name="movelast"></a>C레코드 집합::이동마지막

마지막 전체 행 집합의 첫 번째 레코드를 현재 레코드로 만듭니다.

```cpp
void MoveLast();
```

### <a name="remarks"></a>설명

대량 행 가져오기를 구현하지 않은 경우 레코드 집합의 행 크기가 1이므로 `MoveLast` 레코드 집합의 마지막 레코드로 이동하기만 하면 됩니다.

> [!NOTE]
> 이 멤버 함수는 정방향 전용 레코드 집합에 대해 유효하지 않습니다.

> [!NOTE]
> 레코드 집합을 통해 이동하면 삭제된 레코드를 건너뛸 수 없습니다. 자세한 내용은 [IsDeleted](#isdeleted) 멤버 함수를 참조하십시오.

> [!CAUTION]
> 레코드 집합에 `Move` 레코드가 없는 경우 함수를 호출하면 예외가 발생합니다. 레코드 집합에 레코드가 있는지 여부를 `IsBOF` `IsEOF`확인하려면 호출 및 .

> [!NOTE]
> 현재 레코드가 `Move` 업데이트되거나 추가되는 동안 함수를 호출하면 경고 없이 업데이트가 손실됩니다.

레코드 집합 탐색에 대한 자세한 내용은 [레코드 집합: 스크롤(ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 및 [레코드 집합: 책갈피 및 절대 위치(ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)문서를 참조하십시오. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

### <a name="example"></a>예제

  [IsBOF](#isbof)에 대한 예제를 참조하십시오.

## <a name="crecordsetmovenext"></a><a name="movenext"></a>C레코드 집합::이동 다음

다음 행 집합의 첫 번째 레코드를 현재 레코드로 만듭니다.

```cpp
void MoveNext();
```

### <a name="remarks"></a>설명

대량 행 가져오기를 구현하지 않은 경우 레코드 집합의 행 크기가 1이므로 `MoveNext` 다음 레코드로 이동하기만 하면 됩니다.

> [!NOTE]
> 레코드 집합을 통해 이동하면 삭제된 레코드를 건너뛸 수 없습니다. 자세한 내용은 [IsDeleted](#isdeleted) 멤버 함수를 참조하십시오.

> [!CAUTION]
> 레코드 집합에 `Move` 레코드가 없는 경우 함수를 호출하면 예외가 발생합니다. 레코드 집합에 레코드가 있는지 여부를 `IsBOF` `IsEOF`확인하려면 호출 및 .

> [!NOTE]
> 또한 호출하기 `MoveNext`전에 `IsEOF` 전화하는 것이 좋습니다. 예를 들어 레코드 집합의 끝을 지나 스크롤한 `IsEOF` 경우 0이 아닌 것을 반환합니다. 후속 호출은 `MoveNext` 예외를 throw합니다.

> [!NOTE]
> 현재 레코드가 `Move` 업데이트되거나 추가되는 동안 함수를 호출하면 경고 없이 업데이트가 손실됩니다.

레코드 집합 탐색에 대한 자세한 내용은 [레코드 집합: 스크롤(ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 및 [레코드 집합: 책갈피 및 절대 위치(ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)문서를 참조하십시오. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

### <a name="example"></a>예제

  [IsBOF](#isbof)에 대한 예제를 참조하십시오.

## <a name="crecordsetmoveprev"></a><a name="moveprev"></a>C레코드 집합::무브프레프

이전 행 집합의 첫 번째 레코드를 현재 레코드로 만듭니다.

```cpp
void MovePrev();
```

### <a name="remarks"></a>설명

대량 행 가져오기를 구현하지 않은 경우 레코드 집합의 행 크기가 1이므로 `MovePrev` 이전 레코드로 이동하기만 하면 됩니다.

> [!NOTE]
> 이 멤버 함수는 정방향 전용 레코드 집합에 대해 유효하지 않습니다.

> [!NOTE]
> 레코드 집합을 통해 이동하면 삭제된 레코드를 건너뛸 수 없습니다. 자세한 내용은 [IsDeleted](#isdeleted) 멤버 함수를 참조하십시오.

> [!CAUTION]
> 레코드 집합에 `Move` 레코드가 없는 경우 함수를 호출하면 예외가 발생합니다. 레코드 집합에 레코드가 있는지 여부를 `IsBOF` `IsEOF`확인하려면 호출 및 .

> [!NOTE]
> 또한 호출하기 `MovePrev`전에 `IsBOF` 전화하는 것이 좋습니다. 예를 들어 레코드 집합의 시작 부분에 앞서 스크롤한 `IsBOF` 경우 0이 아닌 것으로 반환됩니다. 후속 호출은 `MovePrev` 예외를 throw합니다.

> [!NOTE]
> 현재 레코드가 `Move` 업데이트되거나 추가되는 동안 함수를 호출하면 경고 없이 업데이트가 손실됩니다.

레코드 집합 탐색에 대한 자세한 내용은 [레코드 집합: 스크롤(ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 및 [레코드 집합: 책갈피 및 절대 위치(ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)문서를 참조하십시오. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

### <a name="example"></a>예제

  [IsBOF](#isbof)에 대한 예제를 참조하십시오.

## <a name="crecordsetonsetoptions"></a><a name="onsetoptions"></a>C레코드 집합::설정 옵션

지정된 ODBC 문에 대한 옵션 설정(선택 시 사용)을 호출합니다.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>매개 변수

*hstmt*<br/>
옵션을 설정해야 하는 ODBC 문의 HSTMT입니다.

### <a name="remarks"></a>설명

지정된 `OnSetOptions` ODBC 문에 대한 옵션 설정(선택 시 사용)을 호출합니다. 프레임워크는 이 멤버 함수를 호출하여 레코드 집합에 대한 초기 옵션을 설정합니다. `OnSetOptions`은 데이터 원본의 스크롤 가능한 커서 및 커서 동시성 지원을 결정하고 그에 따라 레코드 집합의 옵션을 설정합니다. (선택 `OnSetOptions` 작업에 는 사용되지만 `OnSetUpdateOptions` 업데이트 작업에 사용됩니다.)

드라이버 `OnSetOptions` 또는 데이터 원본에 특정옵션을 설정하려면 재정의합니다. 예를 들어 데이터 원본이 단독 액세스에 대한 열기를 지원하는 경우 해당 기능을 활용하기 위해 재정의할 `OnSetOptions` 수 있습니다.

커서에 대한 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md)문서를 참조하십시오.

## <a name="crecordsetonsetupdateoptions"></a><a name="onsetupdateoptions"></a>C레코드 집합::온셋 업데이트 옵션

지정된 ODBC 문에 대한 옵션(업데이트시 사용)을 설정하도록 호출됩니다.

```
virtual void OnSetUpdateOptions(HSTMT hstmt);
```

### <a name="parameters"></a>매개 변수

*hstmt*<br/>
옵션을 설정해야 하는 ODBC 문의 HSTMT입니다.

### <a name="remarks"></a>설명

지정된 `OnSetUpdateOptions` ODBC 문에 대한 옵션 설정(업데이트 시 사용)을 호출합니다. 프레임워크는 레코드 집합의 레코드를 업데이트하기 위해 HSTMT를 생성한 후 이 멤버 함수를 호출합니다. (선택 `OnSetOptions` 작업에 는 사용되지만 `OnSetUpdateOptions` 업데이트 작업에 사용됩니다.) `OnSetUpdateOptions` 은 데이터 원본의 스크롤 가능한 커서 및 커서 동시성 지원을 결정하고 그에 따라 레코드 집합의 옵션을 설정합니다.

해당 `OnSetUpdateOptions` 문이 데이터베이스에 액세스하는 데 사용되기 전에 ODBC 문의 옵션을 설정하도록 재정의합니다.

커서에 대한 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md)문서를 참조하십시오.

## <a name="crecordsetopen"></a><a name="open"></a>C레코드 집합::열기

테이블을 검색하거나 레코드 집합이 나타내는 쿼리를 수행하여 레코드 집합을 엽니다.

```
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    DWORD dwOptions = none);
```

### <a name="parameters"></a>매개 변수

*n오픈타입*<br/>
기본값을 AFX_DB_USE_DEFAULT_TYPE 수락하거나 `enum OpenType`다음 값 중 하나를 사용합니다.

- `CRecordset::dynaset`양방향 스크롤이 있는 레코드 집합입니다. 레코드의 멤버 자격 및 순서는 레코드 집합을 열 때 결정되지만 다른 사용자가 데이터 값에 변경한 내용은 가져오기 작업 후 표시됩니다. 다이나셋은 키집합 기반 레코드 집합이라고도 합니다.

- `CRecordset::snapshot`양방향 스크롤이 있는 정적 레코드 집합입니다. 레코드의 멤버 자격 및 순서는 레코드 집합이 열릴 때 결정됩니다. 데이터 값은 레코드를 가져올 때 결정됩니다. 다른 사용자가 변경한 내용은 레코드 집합이 닫힌 다음 다시 열릴 때까지 표시되지 않습니다.

- `CRecordset::dynamic`양방향 스크롤이 있는 레코드 집합입니다. 다른 사용자가 멤버 자격, 순서 및 데이터 값에 변경한 내용은 가져오기 작업 다음에 표시됩니다. 많은 ODBC 드라이버는 이러한 유형의 레코드 집합을 지원하지 않습니다.

- `CRecordset::forwardOnly`앞으로 스크롤만 있는 읽기 전용 레코드 집합입니다.

   의 `CRecordset`경우 기본값은 `CRecordset::snapshot`입니다. 기본값 메커니즘을 사용하면 Visual C++ 마법사가 기본값이 `CRecordset` 다른 ODBC 및 DAO와 `CDaoRecordset`상호 작용할 수 있습니다.

이러한 레코드 집합 유형에 대한 자세한 내용은 [ODBC(레코드 집합)](../../data/odbc/recordset-odbc.md)문서를 참조하십시오. 관련 정보는 Windows SDK의 "블록 및 스크롤 가능한 커서 사용" 문서를 참조하십시오.

> [!CAUTION]
> 요청된 형식이 지원되지 않으면 프레임워크에서 예외를 throw합니다.

*lpszSQL*<br/>
다음 중 하나를 포함하는 문자열 포인터:

- NULL 포인터입니다.

- 테이블의 이름입니다.

- SQL **SELECT** 문(선택적으로 SQL **WHERE** 또는 **ORDER BY** 절 포함).

- 미리 정의된 쿼리(저장 프로시저)의 이름을 지정하는 **CALL** 문입니다. 곱슬 받침대와 **CALL** 키워드 사이에 공백을 삽입하지 않도록 주의하십시오.

이 문자열에 대한 자세한 내용은 설명 [섹션에서](#remarks) ClassWizard의 역할에 대한 테이블 및 토론을 참조하십시오.

> [!NOTE]
> 결과 집합의 열 순서는 [DoFieldExchange](#dofieldexchange) 또는 [DoBulkFieldExchange](#dobulkfieldexchange) 함수 재정의에서 RFX 또는 대량 RFX 함수 호출의 순서와 일치해야 합니다.

*dwOptions*<br/>
아래에 나열된 값의 조합을 지정할 수 있는 비트 마스크입니다. 이들 중 일부는 상호 배타적입니다. 기본값은 **none입니다.**

- `CRecordset::none`옵션 집합이 없습니다. 이 매개 변수 값은 다른 모든 값과 상호 배타적입니다. 기본적으로 레코드 집합은 [편집](#edit) 또는 [삭제로](#delete) 업데이트할 수 있으며 [AddNew](#addnew)을 사용 하 여 새 레코드를 추가할 수 있습니다. 업데이터 가능성은 지정한 *nOpenType* 옵션뿐만 아니라 데이터 원본에 따라 달라집니다. 대량 추가에 대한 최적화는 사용할 수 없습니다. 대량 행 페칭은 구현되지 않습니다. 삭제된 레코드는 레코드 집합 탐색 중에 건너뛸 수 없습니다. 책갈피를 사용할 수 없습니다. 자동 더티 필드 검사가 구현됩니다.

- `CRecordset::appendOnly`레코드 집합을 허용하지 `Edit` 마십시오. `Delete` 만 `AddNew` 허용합니다. 이 옵션은 에서 만일의 옵션입니다. `CRecordset::readOnly`

- `CRecordset::readOnly`레코드 집합을 읽기 전용으로 엽니다. 이 옵션은 에서 만일의 옵션입니다. `CRecordset::appendOnly`

- `CRecordset::optimizeBulkAdd`준비된 SQL 문을 사용하여 한 번에 많은 레코드를 추가하는 것을 최적화합니다. 레코드 집합을 업데이트하기 위해 ODBC `SQLSetPos` API 함수를 사용하지 않는 경우에만 적용됩니다. 첫 번째 업데이트는 더티로 표시된 필드를 결정합니다. 이 옵션은 에서 만일의 옵션입니다. `CRecordset::useMultiRowFetch`

- `CRecordset::useMultiRowFetch`단일 가져오기 작업에서 여러 행을 검색할 수 있도록 대량 행 가져오기를 구현합니다. 이 기능은 성능을 향상시키기 위해 설계된 고급 기능입니다. 그러나 대량 레코드 필드 교환은 ClassWizard에서 지원되지 않습니다. 이 옵션은 에서 만일의 옵션입니다. `CRecordset::optimizeBulkAdd` 을 지정하면 `CRecordset::useMultiRowFetch`옵션이 `CRecordset::noDirtyFieldCheck` 자동으로 켜집니다(이중 버퍼링을 사용할 수 없음). 정방향 전용 레코드 집합에서 `CRecordset::useExtendedFetch` 옵션이 자동으로 켜집니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

- `CRecordset::skipDeletedRecords`레코드 집합을 탐색할 때 삭제된 모든 레코드를 건너뜁니다. 이렇게 하면 특정 상대 인출에서 성능이 저하됩니다. 이 옵션은 정방향 전용 레코드 집합에서 유효하지 않습니다. *nRows* 매개 변수가 0으로 설정된 [Move를](#move) 호출하면 `Move` 옵션 집합이 `CRecordset::skipDeletedRecords` 어설션됩니다. `CRecordset::skipDeletedRecords` 삭제된 행이 레코드 집합에서 제거됨을 의미하는 *드라이버 압축과*유사합니다. 그러나 드라이버가 레코드를 압축하면 삭제한 레코드만 건너뜁니다. 레코드 집합이 열려 있는 동안 다른 사용자가 삭제한 레코드를 건너뛰지 않습니다. `CRecordset::skipDeletedRecords`다른 사용자가 삭제한 행을 건너뜁니다.

- `CRecordset::useBookmarks`지원되는 경우 레코드 집합에 책갈피를 사용할 수 있습니다. 책갈피는 데이터 검색 속도가 느리지만 데이터 탐색의 성능을 향상시킵니다. 정방향 전용 레코드 집합에서 유효하지 않습니다. 자세한 내용은 [문서 레코드 집합: 북마크 및 절대 위치 (ODBC)를](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)참조 하십시오.

- `CRecordset::noDirtyFieldCheck`자동 더티 필드 검사(이중 버퍼링)를 끕니다. 이렇게 하면 성능이 향상됩니다. 그러나 `SetFieldDirty` 및 `SetFieldNull` 멤버 함수를 호출하여 필드를 더티로 수동으로 표시해야 합니다. 클래스의 `CRecordset` 이중 버퍼링은 클래스의 `CDaoRecordset`이중 버퍼링과 유사합니다. 그러나 에서 `CRecordset`개별 필드에 이중 버퍼링을 사용할 수 없습니다. 모든 필드에 대해 사용하도록 설정하거나 모든 필드에 대해 사용하지 않도록 설정합니다. 옵션을 `CRecordset::useMultiRowFetch` `CRecordset::noDirtyFieldCheck` 지정하면 자동으로 켜집니다. `SetFieldDirty` 그러나 대량 `SetFieldNull` 행 가져오기를 구현하는 레코드 집합에는 사용할 수 없습니다.

- `CRecordset::executeDirect`준비된 SQL 문을 사용하지 마십시오. 성능 향상을 위해 멤버 `Requery` 함수가 호출되지 않을 경우 이 옵션을 지정합니다.

- `CRecordset::useExtendedFetch`을 `SQLExtendedFetch` 대신 `SQLFetch`구현합니다. 이는 정방향 전용 레코드 집합에서 대량 행 페칭을 구현하기 위해 설계되었습니다. 정방향 전용 `CRecordset::useMultiRowFetch` 레코드 집합에서 `CRecordset::useExtendedFetch` 옵션을 지정하면 자동으로 켜집니다.

- `CRecordset::userAllocMultiRowBuffers`사용자는 데이터에 대한 저장소 버퍼를 할당합니다. 자신의 저장소를 할당하려는 경우 와 `CRecordset::useMultiRowFetch` 함께 이 옵션을 사용합니다. 그렇지 않으면 프레임워크가 필요한 저장소를 자동으로 할당합니다. 자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하십시오. `CRecordset::userAllocMultiRowBuffers` 지정하지 않고 `CRecordset::useMultiRowFetch` 지정하면 어설션이 실패합니다.

### <a name="return-value"></a>Return Value

개체가 성공적으로 `CRecordset` 열린 경우 0이 아닙니다. 그렇지 않으면 0 [CDatabase::Open(호출된](../../mfc/reference/cdatabase-class.md#open) 경우)이 0을 반환합니다.

### <a name="remarks"></a>설명

레코드 집합에 의해 정의된 쿼리를 실행하려면 이 멤버 함수를 호출해야 합니다. 호출하기 `Open`전에 레코드 집합 개체를 생성해야 합니다.

이 레코드 집합의 데이터 원본에 대한 연결은 호출하기 `Open`전에 레코드 집합을 생성하는 방법에 따라 다릅니다. [CDatabase](../../mfc/reference/cdatabase-class.md) 개체를 데이터 원본에 연결되지 않은 레코드 집합 생성자에게 전달하는 경우 이 멤버 함수는 [GetDefaultConnect를](#getdefaultconnect) 사용하여 데이터베이스 개체를 엽니다. 레코드 집합 생성자에 NULL을 전달하면 생성자는 `CDatabase` 개체를 생성하고 `Open` 데이터베이스 개체를 연결하려고 시도합니다. 이러한 다양한 상황에서 레코드 집합 및 연결을 닫는 방법에 대한 자세한 내용은 [닫기](#close)를 참조하십시오.

> [!NOTE]
> `CRecordset` 개체를 통해 데이터 원본에 대한 액세스는 항상 공유됩니다. 클래스와 `CDaoRecordset` 달리 개체를 `CRecordset` 사용하여 단독 액세스 권한이 있는 데이터 원본을 열 수 없습니다.

호출할 때 쿼리(일반적으로 SQL SELECT 문)는 다음 표에 표시된 조건을 기반으로 레코드를 선택합니다. **SELECT** `Open`

|lpszSQL 매개 변수값|선택한 레코드는|예제|
|------------------------------------|----------------------------------------|-------------|
|NULL|에서 반환된 `GetDefaultSQL`문자열입니다.||
|SQL 테이블 이름|테이블 목록의 모든 열 `DoFieldExchange` 또는 `DoBulkFieldExchange`.|`"Customer"`|
|미리 정의된 쿼리(저장 프로시저) 이름|쿼리가 반환하도록 정의된 열입니다.|`"{call OverDueAccts}"`|
|**테이블** 목록에서 열 목록 **선택**|지정된 테이블의 지정된 열입니다.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|

> [!CAUTION]
> SQL 문자열에 여분의 공백을 삽입하지 않도록 주의하십시오. 예를 들어, 중괄호와 **CALL** 키워드 사이에 공백을 삽입하는 경우 MFC는 SQL 문자열을 테이블 이름으로 잘못 해석하고 **SELECT** 문에 통합하여 예외가 throw됩니다. 마찬가지로 미리 정의된 쿼리에서 출력 매개 변수를 사용하는 경우 중괄호와 '' 기호 사이에 공백을 삽입하지 마십시오. 마지막으로 **CALL** 문에 중괄호 앞에 공백을 삽입하거나 **SELECT** 문의 **SELECT** 키워드 앞에 공백을 삽입해서는 안 됩니다.

일반적인 절차는 NULL을 에 `Open`전달하는 것입니다. 이 경우 `Open` [GetDefaultSQL](#getdefaultsql)을 호출합니다. 파생 클래스를 `CRecordset` 사용하는 경우 `GetDefaultSQL` ClassWizard에서 지정한 테이블 이름을 지정합니다. 대신 매개 변수에서 다른 `lpszSQL` 정보를 지정할 수 있습니다.

전달하는 것이 `Open` 무엇이든 간에 쿼리에 대한 최종 SQL 문자열을 생성합니다(문자열에 전달한 `lpszSQL` 문자열에 SQL **WHERE** 및 **ORDER BY** 절이 추가될 수 있음) 쿼리를 실행합니다. 호출 `Open`한 후 [GetSQL을](#getsql) 호출하여 생성 된 문자열을 검사 할 수 있습니다. 레코드 집합이 SQL 문을 구성하고 레코드를 선택하는 방법에 대한 자세한 내용은 [레코드 집합: 레코드 집합(ODBC)을 선택하는 방법 문서를](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)참조하십시오.

레코드 집합 클래스의 필드 데이터 멤버는 선택한 데이터의 열에 바인딩됩니다. 레코드가 반환되면 첫 번째 레코드가 현재 레코드가 됩니다.

필터 또는 정렬과 같은 레코드 집합에 대한 옵션을 설정하려면 레코드 집합 개체를 생성한 `Open`후 호출하기 전에 이러한 옵션을 지정합니다. 레코드 집합이 이미 열려 있는 후 레코드 집합의 레코드를 새로 고치려면 [Requery](#requery)를 호출합니다.

추가 예제를 포함한 자세한 내용은 [레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)및 [레코드 집합: 레코드 집합 선택 방법(ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)및 [레코드 집합: 레코드 집합 만들기 및 종료 레코드 집합(ODBC)을](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)참조하십시오.

### <a name="example"></a>예제

다음 코드 예제는 다른 형태의 `Open` 호출을 보여 준다.

[!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]

## <a name="crecordsetrefreshrowset"></a><a name="refreshrowset"></a>C레코드 집합::새로 고침행세트

현재 행 집합의 행에 대한 데이터와 상태를 업데이트합니다.

```cpp
void RefreshRowset(
    WORD wRow,
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>매개 변수

*wRow*<br/>
현재 행 집합에서 행의 한 기반 위치입니다. 이 값은 0부터 행 집합 크기까지 다양합니다.

*wLockType*<br/>
행을 새로 고쳐진 후 행을 잠그는 방법을 나타내는 값입니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

*wRow에*대해 0값을 전달하면 행 집합의 모든 행이 새로 고쳐집니다.

을 `RefreshRowset`사용하려면 `CRecordset::useMulitRowFetch` [Open](#open) 멤버 함수에서 옵션을 지정하여 대량 행 가져오기를 구현해야 합니다.

`RefreshRowset`ODBC API 함수를 `SQLSetPos`호출합니다. *wLockType* 매개 변수는 실행된 후 `SQLSetPos` 행의 잠금 상태를 지정합니다. 다음 표는 *wLockType에*대 한 가능한 값을 설명 합니다.

|wLockType|Description|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE(기본값)|드라이버 또는 데이터 원본은 행이 호출되기 전과 `RefreshRowset` 동일한 잠금 또는 잠금 해제 상태인지 확인합니다.|
|SQL_LOCK_EXCLUSIVE|드라이버 또는 데이터 원본은 행을 단독으로 잠그습니다. 모든 데이터 원본이 이러한 유형의 잠금을 지원하는 것은 아닙니다.|
|SQL_LOCK_UNLOCK|드라이버 또는 데이터 원본이 행의 잠금을 해제합니다. 모든 데이터 원본이 이러한 유형의 잠금을 지원하는 것은 아닙니다.|

자세한 `SQLSetPos`내용은 Windows SDK를 참조하십시오. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

## <a name="crecordsetrequery"></a><a name="requery"></a>C레코드 집합::다시 쿼리

레코드 집합을 다시 빌드(새로 고침)합니다.

```
virtual BOOL Requery();
```

### <a name="return-value"></a>Return Value

레코드 집합이 성공적으로 다시 빌드된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

레코드가 반환되면 첫 번째 레코드가 현재 레코드가 됩니다.

레코드 집합이 사용자 또는 다른 사용자가 데이터 원본에 만드는 추가 및 삭제를 반영하려면 를 호출하여 `Requery`레코드 집합을 다시 빌드해야 합니다. 레코드 집합이 다이너셋인 경우 사용자 또는 다른 사용자가 기존 레코드에 대해 하는 업데이트는 자동으로 반영되지만 추가는 포함되지 않습니다. 레코드 집합이 스냅샷인 경우 `Requery` 다른 사용자의 편집 및 추가 및 삭제를 반영하기 위해 호출해야 합니다.

다이너셋 또는 스냅숏의 `Requery` 경우 새 필터 또는 정렬 또는 새 매개 변수 값을 사용하여 레코드 집합을 다시 빌드할 때마다 호출합니다. `m_strSort` 호출하기 `Requery`전에 새 값을 할당하여 `m_strFilter` 새 필터 또는 정렬 속성을 설정합니다. 을 호출하기 `Requery`전에 매개 변수 데이터 멤버에 새 값을 할당하여 새 매개 변수를 설정합니다. 필터 및 정렬 문자열이 변경되지 않은 경우 쿼리를 다시 사용하여 성능을 향상시킬 수 있습니다.

레코드 집합을 다시 빌드하려는 시도가 실패하면 레코드 집합이 닫힙됩니다. 호출하기 `Requery`전에 `CanRestart` 멤버 함수를 호출하여 레코드 집합을 다시 쿼리할 수 있는지 여부를 확인할 수 있습니다. `CanRestart`성공할 것이라는 `Requery` 보장은 없습니다.

> [!CAUTION]
> `Requery` [열기를](#open)호출한 후에만 호출합니다.

### <a name="example"></a>예제

이 예제는 레코드 집합을 다시 빌드하여 다른 정렬 순서를 적용합니다.

[!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]

## <a name="crecordsetsetabsoluteposition"></a><a name="setabsoluteposition"></a>C레코드 집합::설정절대위치

지정된 레코드 번호에 해당하는 레코드의 레코드 집합을 배치합니다.

```cpp
void SetAbsolutePosition(long nRows);
```

### <a name="parameters"></a>매개 변수

*nRows*<br/>
레코드 집합의 현재 레코드에 대한 한 가지 기반 서수 위치입니다.

### <a name="remarks"></a>설명

`SetAbsolutePosition`은 이 서수 위치를 기준으로 현재 레코드 포인터를 이동합니다.

> [!NOTE]
> 이 멤버 함수는 정방향 전용 레코드 집합에서 유효하지 않습니다.

ODBC 레코드 집합의 경우 절대 위치 설정이 1이면 레코드 집합의 첫 번째 레코드를 참조합니다. 0으로 설정하면 BOF(파일 시작 위치)를 나타냅니다.

음수 값을 `SetAbsolutePosition`에 전달할 수도 있습니다. 이 경우 레코드 집합의 위치는 레코드 집합의 끝에서 평가됩니다. 예를 들어 `SetAbsolutePosition( -1 )` 현재 레코드 포인터를 레코드 집합의 마지막 레코드로 이동합니다.

> [!NOTE]
> 절대 위치는 서로게이트 레코드 번호로 사용할 수 없습니다. 이전 레코드가 삭제될 때 레코드의 위치가 변경되므로 책갈피는 여전히 지정된 위치를 유지하고 반환하는 권장 방법입니다. 또한 **ORDER BY** 절을 사용하여 SQL 문으로 만들지 않는 한 레코드 집합 내의 개별 레코드 순서가 보장되지 않으므로 레코드 집합이 다시 만들어지면 지정된 레코드의 절대 위치가 동일합니다.

레코드 집합 탐색 및 책갈피에 대한 자세한 내용은 [레코드 집합: 스크롤(ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 및 [레코드 집합: 책갈피 및 절대 위치(ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)문서를 참조하십시오.

## <a name="crecordsetsetbookmark"></a><a name="setbookmark"></a>C레코드 집합::세트북마크

지정된 책갈피를 포함하는 레코드의 레코드 집합을 배치합니다.

```cpp
void SetBookmark(const CDBVariant& varBookmark);
```

### <a name="parameters"></a>매개 변수

*바북마크*<br/>
특정 레코드에 대한 책갈피 값을 포함하는 [CDBVariant](../../mfc/reference/cdbvariant-class.md) 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

레코드 집합에서 책갈피가 지원되는지 확인하려면 [CanBookmark를](#canbookmark)호출합니다. 북마크가 지원되는 경우 책갈피를 사용할 `CRecordset::useBookmarks` 수 있도록 하려면 [Open](#open) 멤버 함수의 *dwOptions* 매개 변수에서 옵션을 설정해야 합니다.

> [!NOTE]
> 책갈피를 지원하지 않거나 사용할 `SetBookmark` 수 없는 경우 호출하면 예외가 throw됩니다. 책갈피는 정방향 전용 레코드 집합에서 지원되지 않습니다.

먼저 현재 레코드의 책갈피를 검색하려면 [GetBookmark를](#getbookmark)호출하여 책갈피 `CDBVariant` 값을 개체에 저장합니다. 나중에 저장된 책갈피 값을 `SetBookmark` 사용하여 호출하여 해당 레코드로 돌아갈 수 있습니다.

> [!NOTE]
> 특정 레코드 집합 작업 후 호출하기 `SetBookmark`전에 책갈피 지속성을 확인해야 합니다. 예를 들어, 책갈피를 `GetBookmark` 검색한 다음 `Requery`호출하면 책갈피가 더 이상 유효하지 않을 수 있습니다. [CDatabase::GetBookmark지속성으로](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) 안전하게 호출할 `SetBookmark`수 있는지 확인합니다.

책갈피 및 레코드 집합 탐색에 대한 자세한 내용은 [레코드 집합: 북마크 및 절대 위치(ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) 및 [레코드 집합: 스크롤(ODBC)](../../data/odbc/recordset-scrolling-odbc.md)문서를 참조하십시오.

## <a name="crecordsetsetfielddirty"></a><a name="setfielddirty"></a>C레코드 집합::셋필드더티

레코드 집합의 필드 데이터 멤버를 변경된 것으로 또는 변경되지 않은 것으로 플래그를 표시합니다.

```cpp
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
레코드 집합 또는 NULL에 필드 데이터 멤버의 주소를 포함합니다. NULL이면 레코드 집합의 모든 필드 데이터 멤버에 플래그가 지정됩니다. (C++ NULL은 데이터베이스 용어에서 Null과 같지 않습니다. 즉 "값이 없음")

*bDirty*<br/>
TRUE 필드 데이터 멤버를 "더티"(변경됨)로 플래그를 지정하는 경우 그렇지 않으면 필드 데이터 멤버를 "정리"(변경되지 않음)로 플래그를 지정하는 경우 FALSE입니다.

### <a name="remarks"></a>설명

필드를 변경되지 않은 것으로 표시하면 필드가 업데이트되지 않고 SQL 트래픽이 줄어듭니다.

> [!NOTE]
> 이 멤버 함수는 대량 행 가져오기를 사용하는 레코드 집합에는 적용되지 않습니다. 대량 행 가져오기를 구현한 `SetFieldDirty` 경우 어설션이 실패합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

프레임워크는 변경된 필드 데이터 멤버를 표시하여 RFX(레코드 필드 교환) 메커니즘에 의해 데이터 원본의 레코드에 기록되도록 합니다. 필드 값을 변경하면 일반적으로 필드가 자동으로 더러워지므로 직접 `SetFieldDirty` 호출할 필요가 거의 없지만 필드 데이터 멤버에 있는 값에 관계없이 열이 명시적으로 업데이트되거나 삽입되도록 할 수도 있습니다.

> [!CAUTION]
> [편집](#edit) 또는 AddNew 를 호출한 후에만 이 멤버 [함수를](#addnew)호출합니다.

함수의 첫 번째 인수에 NULL을 사용하면 `outputColumn` 필드가 `param` 아닌 필드에만 함수가 적용됩니다. 예를 들어,

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

필드만 `outputColumn` NULL로 설정합니다. `param` 필드는 영향을 받지 않습니다.

`param` 필드에서 작업하려면 다음과 같이 작업하려는 개인의 `param` 실제 주소를 제공해야 합니다.

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

즉, 필드를 사용하여 `param` 모든 필드를 NULL로 `outputColumn` 설정할 수 없습니다.

## <a name="crecordsetsetfieldnull"></a><a name="setfieldnull"></a>C레코드 집합::세트필드널

레코드 집합의 필드 데이터 멤버를 Null(특히 값이 없음)으로 플래그를 표시하거나 Null이 아닌 것으로 플래그를 표시합니다.

```cpp
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
레코드 집합 또는 NULL에 필드 데이터 멤버의 주소를 포함합니다. NULL이면 레코드 집합의 모든 필드 데이터 멤버에 플래그가 지정됩니다. (C++ NULL은 데이터베이스 용어에서 Null과 같지 않습니다. 즉 "값이 없음")

*bNull*<br/>
필드 데이터 멤버가 값(Null)이 없는 것으로 플래그가 지정되는 경우 Nonzero입니다. 그렇지 않으면 필드 데이터 멤버가 Null이 아닌 것으로 플래그가 지정되는 경우 0입니다.

### <a name="remarks"></a>설명

레코드 집합에 새 레코드를 추가하면 모든 필드 데이터 멤버가 처음에 Null 값으로 설정되고 "더티"(변경됨)로 플래그가 지정됩니다. 데이터 원본에서 레코드를 검색하면 해당 열에 이미 값이 있거나 Null입니다.

> [!NOTE]
> 대량 행 가져오기를 사용하는 레코드 집합에서 이 멤버 함수를 호출하지 마십시오. 대량 행 가져오기를 구현한 `SetFieldNull` 경우 호출하면 어설션이 실패합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

현재 레코드의 필드를 값이 없는 것으로 지정하려면 `SetFieldNull` *bNull을* 사용하여 TRUE로 설정하여 Null로 플래그를 지정합니다. 필드가 이전에 Null로 표시되어 있고 이제 값을 지정하려는 경우 새 값을 설정하기만 하면 됩니다. `SetFieldNull`을 사용하여 Null 플래그를 제거할 필요가 없습니다. 필드가 Null이 될 수 있는지 `IsFieldNullable`여부를 확인하려면 을 호출합니다.

> [!CAUTION]
> [편집](#edit) 또는 AddNew 를 호출한 후에만 이 멤버 [함수를](#addnew)호출합니다.

함수의 첫 번째 인수에 NULL을 사용하면 `outputColumn` 필드가 `param` 아닌 필드에만 함수가 적용됩니다. 예를 들어,

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

필드만 `outputColumn` NULL로 설정합니다. `param` 필드는 영향을 받지 않습니다.

`param` 필드에서 작업하려면 다음과 같이 작업하려는 개인의 `param` 실제 주소를 제공해야 합니다.

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

즉, 필드를 사용하여 `param` 모든 필드를 NULL로 `outputColumn` 설정할 수 없습니다.

> [!NOTE]
> 매개 변수를 Null로 설정할 `SetFieldNull` 때 레코드 집합이 열리기 전에 호출하면 어설션이 생성됩니다. 이 경우 [SetParamNull](#setparamnull)을 호출합니다.

`SetFieldNull`[DoFieldExchange를](#dofieldexchange)통해 구현됩니다.

## <a name="crecordsetsetlockingmode"></a><a name="setlockingmode"></a>C레코드 집합::설정 잠금 모드

잠금 모드를 "낙관적" 잠금(기본값) 또는 "비관적" 잠금으로 설정합니다. 업데이트에 대해 레코드가 잠기는 방법을 결정합니다.

```cpp
void SetLockingMode(UINT nMode);
```

### <a name="parameters"></a>매개 변수

*nMode*<br/>
`enum LockMode`다음 값 중 하나를 포함합니다.

- `optimistic`낙관적 잠금은 을 호출하는 동안에만 `Update`업데이트되는 레코드를 잠급전지 합니다.

- `pessimistic`비관적 잠금은 호출되는 즉시 `Edit` 레코드를 잠그고 `Update` 호출이 완료될 때까지 잠겨 있거나 새 레코드로 이동합니다.

### <a name="remarks"></a>설명

레코드 집합이 업데이트에 사용하는 두 가지 레코드 잠금 전략을 지정해야 하는 경우 이 멤버 함수를 호출합니다. 기본적으로 레코드 집합의 잠금 모드는 `optimistic`. 더 신중한 `pessimistic` 잠금 전략으로 변경할 수 있습니다. 레코드 `SetLockingMode` 집합 개체를 생성하고 열기 전에 `Edit`호출합니다.

## <a name="crecordsetsetparamnull"></a><a name="setparamnull"></a>C레코드 집합::SetParamNull

매개 변수를 Null(특히 값이 없음)으로 플래그를 표시하거나 Null이 아닌 것으로 플래그를 표시합니다.

```cpp
void SetParamNull(
    int nIndex,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
이 매개 변수의 0부터 시작하는 인덱스입니다.

*bNull*<br/>
TRUE(기본값)이면 매개 변수가 Null로 플래그가 지정됩니다. 그렇지 않으면 매개 변수가 Null이 아닌 것으로 플래그가 지정됩니다.

### <a name="remarks"></a>설명

[SetFieldNull과](#setfieldnull)달리 레코드 `SetParamNull` 집합을 열기 전에 호출할 수 있습니다.

`SetParamNull`일반적으로 미리 정의된 쿼리(저장 프로시저)와 함께 사용됩니다.

## <a name="crecordsetsetrowsetcursorposition"></a><a name="setrowsetcursorposition"></a>C레코드 집합::세트Rowset커서 포지션

커서를 현재 행 집합 내의 행으로 이동합니다.

```cpp
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>매개 변수

*wRow*<br/>
현재 행 집합에서 행의 한 기반 위치입니다. 이 값은 1에서 행 집합의 크기까지 다양합니다.

*wLockType*<br/>
행을 새로 고쳐진 후 행을 잠그는 방법을 나타내는 값입니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

대량 행 페칭을 구현할 때 레코드는 로크세트에 의해 검색되며, 여기서 가져온 행 집합의 첫 번째 레코드는 현재 레코드입니다. 행 집합 내의 다른 레코드를 현재 레코드로 만들려면 을 호출합니다. `SetRowsetCursorPosition` 예를 들어 `SetRowsetCursorPosition` [GetFieldValue](#getfieldvalue) 멤버 함수와 결합하여 레코드 집합의 레코드에서 데이터를 동적으로 검색할 수 있습니다.

을 `SetRowsetCursorPosition`사용하려면 `CRecordset::useMultiRowFetch` [Open](#open) 멤버 함수에서 *dwOptions* 매개 변수 옵션을 지정하여 대량 행 페칭을 구현해야 합니다.

`SetRowsetCursorPosition`ODBC API 함수를 `SQLSetPos`호출합니다. *wLockType* 매개 변수는 실행된 후 `SQLSetPos` 행의 잠금 상태를 지정합니다. 다음 표는 *wLockType에*대 한 가능한 값을 설명 합니다.

|wLockType|Description|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE(기본값)|드라이버 또는 데이터 원본은 행이 호출되기 전과 `SetRowsetCursorPosition` 동일한 잠금 또는 잠금 해제 상태인지 확인합니다.|
|SQL_LOCK_EXCLUSIVE|드라이버 또는 데이터 원본은 행을 단독으로 잠그습니다. 모든 데이터 원본이 이러한 유형의 잠금을 지원하는 것은 아닙니다.|
|SQL_LOCK_UNLOCK|드라이버 또는 데이터 원본이 행의 잠금을 해제합니다. 모든 데이터 원본이 이러한 유형의 잠금을 지원하는 것은 아닙니다.|

자세한 `SQLSetPos`내용은 Windows SDK를 참조하십시오. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

## <a name="crecordsetsetrowsetsize"></a><a name="setrowsetsize"></a>C레코드 집합::세트로셋크기

가져오기 중에 검색할 레코드 수를 지정합니다.

```
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```

### <a name="parameters"></a>매개 변수

*dwNewRowsetSize*<br/>
지정된 가져오기 중에 검색할 행 수입니다.

### <a name="remarks"></a>설명

이 가상 멤버 함수는 대량 행 가져오기를 사용할 때 단일 가져오기 중에 검색할 행 수를 지정합니다. 대량 행 페칭을 구현하려면 `CRecordset::useMultiRowFetch` [Open](#open) 멤버 함수의 *dwOptions* 매개 변수에서 옵션을 설정해야 합니다.

> [!NOTE]
> 대량 `SetRowsetSize` 행 가져오기를 구현하지 않고 호출하면 어설션이 실패합니다.

호출하기 `SetRowsetSize` `Open` 전에 호출하여 레코드 집합의 행 집합 크기를 처음 설정합니다. 벌크 행 페칭을 구현할 때의 기본 행 집합 크기는 25입니다.

> [!NOTE]
> 을 호출할 `SetRowsetSize`때는 주의하십시오. 데이터에 대 한 저장소를 수동으로 할당 하는 경우 `CRecordset::userAllocMultiRowBuffers` (dwOptions 매개 `Open`변수의 옵션에 의해 지정 된 대로), 호출 `SetRowsetSize`후 이러한 저장소 버퍼를 다시 할당 해야 하는지 여부를 확인 해야 합니다 .하지만 커서 탐색 작업을 수행 하기 전에.

행 집합 크기에 대한 현재 설정을 가져오려면 [GetRowsetSize를](#getrowsetsize)호출합니다.

대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

## <a name="crecordsetupdate"></a><a name="update"></a>C레코드 집합::업데이트

데이터 `AddNew` 원본에 `Edit` 새 데이터 또는 편집된 데이터를 저장하여 또는 작업을 완료합니다.

```
virtual BOOL Update();
```

### <a name="return-value"></a>Return Value

하나의 레코드가 성공적으로 업데이트된 경우 비영; 그렇지 않으면 0을 변경하지 않은 경우 레코드가 업데이트되지 않았거나 둘 이상의 레코드가 업데이트된 경우 예외가 throw됩니다. 데이터 원본의 다른 오류에 대해서도 예외가 throw됩니다.

### <a name="remarks"></a>설명

[AddNew](#addnew) 또는 [편집](#edit) 멤버 함수를 호출한 후 이 멤버 함수를 호출합니다. 또는 `Edit` 작업을 완료하려면 `AddNew` 이 호출이 필요합니다.

> [!NOTE]
> 대량 행 가져오기를 구현한 경우 `Update`를 호출할 수 없습니다. 이렇게 하면 어설션이 실패합니다. 클래스는 `CRecordset` 대량 데이터 행을 업데이트하는 메커니즘을 제공하지는 않지만 ODBC API 함수를 `SQLSetPos`사용하여 사용자 고유의 함수를 작성할 수 있습니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

둘 `AddNew` `Edit` 다 데이터 원본에 저장하기 위해 추가되거나 편집된 데이터가 배치되는 편집 버퍼를 준비합니다. `Update`데이터를 저장합니다. 변경된 것으로 표시되거나 검색된 필드만 업데이트됩니다.

데이터 원본이 트랜잭션을 지원하는 경우 `Update` 트랜잭션의 호출(및 해당 `AddNew` 또는 `Edit` 통화) 부분을 만들 수 있습니다. 트랜잭션에 대한 자세한 내용은 [ODBC(트랜잭션)](../../data/odbc/transaction-odbc.md)문서를 참조하십시오.

> [!CAUTION]
> 먼저 호출하지 `Update` 않고 `AddNew` 호출하거나 `Edit` `Update` `CDBException`을 throw합니다. 또는 `AddNew` `Edit`에 전화하는 경우 `Update` 작업을 호출하기 전에 또는 레코드 집합 또는 데이터 원본 연결을 닫기 전에 호출해야 합니다. `Move` 그렇지 않으면 변경 내용이 알림 없이 손실됩니다.

오류 처리에 `Update` 대한 자세한 내용은 [레코드 집합: 레코드 집합 업데이트 레코드(ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)방법을 참조하세요.

### <a name="example"></a>예제

문서 [트랜잭션: 레코드 집합(ODBC)에서 트랜잭션 수행 을](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)참조하십시오.

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C데이터베이스 클래스](../../mfc/reference/cdatabase-class.md)<br/>
[C레코드뷰 클래스](../../mfc/reference/crecordview-class.md)
