---
title: C데이터베이스 클래스
ms.date: 11/04/2016
f1_keywords:
- CDatabase
- AFXDB/CDatabase
- AFXDB/CDatabase::CDatabase
- AFXDB/CDatabase::BeginTrans
- AFXDB/CDatabase::BindParameters
- AFXDB/CDatabase::Cancel
- AFXDB/CDatabase::CanTransact
- AFXDB/CDatabase::CanUpdate
- AFXDB/CDatabase::Close
- AFXDB/CDatabase::CommitTrans
- AFXDB/CDatabase::ExecuteSQL
- AFXDB/CDatabase::GetBookmarkPersistence
- AFXDB/CDatabase::GetConnect
- AFXDB/CDatabase::GetCursorCommitBehavior
- AFXDB/CDatabase::GetCursorRollbackBehavior
- AFXDB/CDatabase::GetDatabaseName
- AFXDB/CDatabase::IsOpen
- AFXDB/CDatabase::OnSetOptions
- AFXDB/CDatabase::Open
- AFXDB/CDatabase::OpenEx
- AFXDB/CDatabase::Rollback
- AFXDB/CDatabase::SetLoginTimeout
- AFXDB/CDatabase::SetQueryTimeout
- AFXDB/CDatabase::m_hdbc
helpviewer_keywords:
- CDatabase [MFC], CDatabase
- CDatabase [MFC], BeginTrans
- CDatabase [MFC], BindParameters
- CDatabase [MFC], Cancel
- CDatabase [MFC], CanTransact
- CDatabase [MFC], CanUpdate
- CDatabase [MFC], Close
- CDatabase [MFC], CommitTrans
- CDatabase [MFC], ExecuteSQL
- CDatabase [MFC], GetBookmarkPersistence
- CDatabase [MFC], GetConnect
- CDatabase [MFC], GetCursorCommitBehavior
- CDatabase [MFC], GetCursorRollbackBehavior
- CDatabase [MFC], GetDatabaseName
- CDatabase [MFC], IsOpen
- CDatabase [MFC], OnSetOptions
- CDatabase [MFC], Open
- CDatabase [MFC], OpenEx
- CDatabase [MFC], Rollback
- CDatabase [MFC], SetLoginTimeout
- CDatabase [MFC], SetQueryTimeout
- CDatabase [MFC], m_hdbc
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
ms.openlocfilehash: bc920307e09179dc214710a3b6b19ff27a82749d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754633"
---
# <a name="cdatabase-class"></a>C데이터베이스 클래스

데이터 소스 작업을 할 수 있는 통로인 데이터 소스에 대한 연결을 나타냅니다.

## <a name="syntax"></a>구문

```
class CDatabase : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C데이터베이스::C데이터베이스](#cdatabase)|`CDatabase` 개체를 생성합니다. 호출하거나 `OpenEx` `Open`.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C데이터베이스::시작트랜스](#begintrans)|연결된 데이터 원본에서 클래스의 `AddNew` `Edit` `Delete` `Update` `CRecordset` 및 멤버 함수에 대한 일련의 되돌릴 수 있는 호출인 "트랜잭션"을 시작합니다. 데이터 원본이 영향을 `BeginTrans` 미치려면 트랜잭션을 지원해야 합니다.|
|[C데이터베이스::바인드매개 변수](#bindparameters)|을 호출하기 `CDatabase::ExecuteSQL`전에 매개 변수를 바인딩할 수 있습니다.|
|[C데이터베이스::취소](#cancel)|두 번째 스레드에서 비동기 작업 또는 프로세스를 취소합니다.|
|[C데이터베이스::수거래](#cantransact)|데이터 원본이 트랜잭션을 지원하는 경우 0이 아닌 것을 반환합니다.|
|[C데이터베이스::캔업데이트](#canupdate)|개체가 `CDatabase` 업데이터(읽기 전용이 아님)인 경우 0이 아님을 반환합니다.|
|[C데이터베이스::닫기](#close)|데이터 원본 연결을 닫습니다.|
|[C데이터베이스::커밋트랜스](#committrans)|에서 시작된 트랜잭션을 `BeginTrans`완료합니다. 데이터 원본을 변경하는 트랜잭션의 명령이 수행됩니다.|
|[C데이터베이스::실행 SQL](#executesql)|SQL 문을 실행합니다. 데이터 레코드가 반환되지 않습니다.|
|[C데이터베이스::Getbookmark지속성](#getbookmarkpersistence)|책갈피레코드 집합 개체에 유지되는 작업을 식별합니다.|
|[CDatabase::GetConnect](#getconnect)|개체를 데이터 원본에 연결하는 `CDatabase` 데 사용되는 ODBC 연결 문자열을 반환합니다.|
|[C데이터베이스::GetCursor커커비헤이비어](#getcursorcommitbehavior)|열려 있는 레코드 집합 개체에 트랜잭션을 커밋하는 효과를 식별합니다.|
|[C데이터베이스::GetCursor롤백 동작](#getcursorrollbackbehavior)|열려 있는 레코드 집합 개체에서 트랜잭션을 롤백하는 효과를 식별합니다.|
|[C데이터베이스::데이터베이스 이름](#getdatabasename)|현재 사용 중인 데이터베이스의 이름을 반환합니다.|
|[C데이터베이스::오픈](#isopen)|개체가 현재 `CDatabase` 데이터 원본에 연결되어 있는 경우 0이 아닌 것을 반환합니다.|
|[C데이터베이스::시작 옵션](#onsetoptions)|표준 연결 옵션을 설정하려면 프레임워크에서 호출합니다. 기본 구현은 쿼리 시간 시간 값을 설정합니다. 을 호출하여 `SetQueryTimeout`이러한 옵션을 미리 설정할 수 있습니다.|
|[C데이터베이스::열기](#open)|ODBC 드라이버를 통해 데이터 원본에 대한 연결을 설정합니다.|
|[C데이터베이스::오픈엑스](#openex)|ODBC 드라이버를 통해 데이터 원본에 대한 연결을 설정합니다.|
|[C데이터베이스::롤백](#rollback)|현재 트랜잭션 중에 변경한 내용을 반전합니다. 데이터 원본은 `BeginTrans` 호출에 정의된 대로 변경되지 않고 이전 상태로 돌아갑니다.|
|[C데이터베이스::Setlogin시간 설정](#setlogintimeout)|데이터 원본 연결 시도가 시간 중지되는 시간(초) 수를 설정합니다.|
|[C데이터베이스::Set쿼리 시간 설정](#setquerytimeout)|데이터베이스 쿼리 작업이 시간 중지되는 시간(초) 수를 설정합니다. 모든 후속 레코드 `Open` `AddNew`집합 `Edit`, `Delete` 및 호출에 영향을 줍니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C데이터베이스::m_hdbc](#m_hdbc)|데이터 원본에 대한 ODBC(데이터베이스 연결) 연결 핸들을 엽니다. 입력 *HDBC*.|

## <a name="remarks"></a>설명

데이터 원본은 일부 DBMS(데이터베이스 관리 시스템)에서 호스팅하는 데이터의 특정 인스턴스입니다. 예를 들어 마이크로소프트 SQL 서버, 마이크로소프트 액세스, 볼랜드 dBASE, 그리고 xBASE. 응용 프로그램에서 한 `CDatabase` 번에 하나 이상의 개체를 활성화할 수 있습니다.

> [!NOTE]
> ODBC(개방형 데이터베이스 연결) 클래스가 아닌 DAO(데이터 액세스 개체) 클래스로 작업하는 경우 대신 [클래스 CDaoDatabase를](../../mfc/reference/cdaodatabase-class.md) 사용합니다. 자세한 내용은 [문서 개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)을 참조하십시오.

사용하려면 `CDatabase`개체를 `CDatabase` 생성하고 `OpenEx` 해당 멤버 함수를 호출합니다. 그러면 연결이 열립니다. 그런 다음 `CRecordset` 연결된 데이터 원본에서 작동하기 위한 개체를 생성할 때 `CDatabase` 레코드 집합 생성자 포인터를 개체에 전달합니다. 연결 사용을 마치면 멤버 `Close` 함수를 호출하고 `CDatabase` 개체를 삭제합니다. `Close`이전에 닫지 않은 레코드 집합을 닫습니다.

자세한 내용은 문서 데이터 [원본(ODBC)](../../data/odbc/data-source-odbc.md) 및 [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)을 참조하십시오. `CDatabase`

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDatabase`

## <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="cdatabasebegintrans"></a><a name="begintrans"></a>C데이터베이스::시작트랜스

연결된 데이터 원본과의 트랜잭션을 시작하려면 이 멤버 함수를 호출합니다.

```
BOOL BeginTrans();
```

### <a name="return-value"></a>Return Value

호출이 성공하고 변경 내용이 수동으로만 커밋된 경우 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

트랜잭션은 개체의 `AddNew`" `Edit`및 `Delete` `Update` 멤버 함수에 대한 하나 `CRecordset` 이상의 호출로 구성됩니다. 트랜잭션을 시작하기 전에 `CDatabase` 개체가 `OpenEx` 해당 함수 또는 `Open` 멤버 함수를 호출하여 데이터 원본에 이미 연결되어 있어야 합니다. 트랜잭션을 종료하려면 [CommitTrans를](#committrans) 호출하여 데이터 원본에 대한 모든 변경 내용을 수락하고 수행하거나 [롤백을](#rollback) 호출하여 전체 트랜잭션을 중단합니다. 트랜잭션과 관련된 레코드 집합을 열고 가능한 한 실제 업데이트 작업에 가깝게 호출합니다. `BeginTrans`

> [!CAUTION]
> ODBC 드라이버에 따라 호출하기 `BeginTrans` 전에 레코드 집합을 `Rollback`열면 을 호출할 때 문제가 발생할 수 있습니다. 사용 중인 특정 드라이버를 확인해야 합니다. 예를 들어 Microsoft ODBC 데스크톱 드라이버 팩 3.0에 포함된 Microsoft Access 드라이버를 사용하는 경우 개방형 커서가 있는 데이터베이스에서 트랜잭션을 시작하지 않아야 한다는 Jet 데이터베이스 엔진의 요구 사항을 고려해야 합니다. MFC 데이터베이스 클래스에서 열린 커서는 열린 `CRecordset` 개체를 의미합니다. 자세한 내용은 [기술 참고 68을](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md)참조하십시오.

`BeginTrans`또한 요청된 동시성 및 데이터 원본의 기능에 따라 서버의 데이터 레코드를 잠글 수도 있습니다. 데이터 잠금에 대한 자세한 내용은 [레코드 집합: 잠금 레코드(ODBC)](../../data/odbc/recordset-locking-records-odbc.md)을 참조하십시오.

사용자 정의 트랜잭션은 [ODBC(트랜잭션)](../../data/odbc/transaction-odbc.md)문서에 설명되어 있습니다.

`BeginTrans`은 트랜잭션 시퀀스를 롤백할 수 있는 상태를 설정합니다(반전). 롤백에 대한 새 상태를 설정하려면 현재 트랜잭션을 `BeginTrans` 커밋한 다음 다시 호출합니다.

> [!CAUTION]
> 호출하지 `CommitTrans` 않고 `Rollback` 다시 호출하거나 `BeginTrans` 오류입니다.

[CanTransact](#cantransact) 멤버 함수를 호출하여 드라이버가 지정된 데이터베이스에 대한 트랜잭션을 지원하는지 확인합니다. 또한 [GetCursorCommitBehavior](#getcursorcommitbehavior) 및 [GetCursorRollbackBehavior를](#getcursorrollbackbehavior) 호출하여 커서 보존에 대한 지원을 결정해야 합니다.

트랜잭션에 대한 자세한 내용은 [ODBC(트랜잭션)](../../data/odbc/transaction-odbc.md)문서를 참조하십시오.

### <a name="example"></a>예제

  문서 [트랜잭션: 레코드 집합(ODBC)에서 트랜잭션 수행 을](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)참조하십시오.

## <a name="cdatabasebindparameters"></a><a name="bindparameters"></a>C데이터베이스::바인드매개 변수

`BindParameters` [CDatabase::ExecuteSQL](#executesql)을 호출하기 전에 매개 변수를 바인딩해야 하는 경우 재정의합니다.

```
virtual void BindParameters(HSTMT hstmt);
```

### <a name="parameters"></a>매개 변수

*hstmt*<br/>
매개 변수를 바인딩할 ODBC 문 핸들입니다.

### <a name="remarks"></a>설명

이 방법은 저장 프로시저의 결과 집합이 필요하지 않은 경우에 유용합니다.

재정의에서 호출 `SQLBindParameters` 및 관련 ODBC 함수에서 매개 변수를 바인딩합니다. MFC는 로 연결하기 전에 `ExecuteSQL`재정의를 호출합니다. 당신은 호출 `SQLPrepare`할 필요가 없습니다; `ExecuteSQL` 한 `SQLExecDirect` 번만 사용되는 *hstmt를*호출하고 파괴합니다.

## <a name="cdatabasecancel"></a><a name="cancel"></a>C데이터베이스::취소

이 멤버 함수를 호출하여 데이터 원본이 진행 중인 비동기 작업 또는 두 번째 스레드의 프로세스를 취소하도록 요청합니다.

```cpp
void Cancel();
```

### <a name="remarks"></a>설명

MFC ODBC 클래스는 더 이상 비동기 처리를 사용하지 않습니다. 비동기 작업을 수행하려면 ODBC API 함수 [SQLSetConnectOption을](/sql/odbc/reference/syntax/sqlsetconnectoption-function)직접 호출해야 합니다. 자세한 내용은 [비동기 실행](/sql/odbc/reference/develop-app/asynchronous-execution)을 참조하십시오.

## <a name="cdatabasecantransact"></a><a name="cantransact"></a>C데이터베이스::수거래

이 멤버 함수를 호출하여 데이터베이스가 트랜잭션을 허용하는지 여부를 확인합니다.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Return Value

이 `CDatabase` 개체를 사용하는 레코드 집합이 트랜잭션을 허용하는 경우 0이 아닌 경우 그렇지 않으면 0.

### <a name="remarks"></a>설명

트랜잭션에 대한 자세한 내용은 [ODBC(트랜잭션)](../../data/odbc/transaction-odbc.md)문서를 참조하십시오.

## <a name="cdatabasecanupdate"></a><a name="canupdate"></a>C데이터베이스::캔업데이트

이 멤버 함수를 호출하여 개체가 `CDatabase` 업데이트를 허용하는지 여부를 확인합니다.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Return Value

개체가 업데이트를 `CDatabase` 허용하는 경우 0이 아닙니다. 그렇지 않으면 0을 사용하면 `CDatabase` 개체를 열 때 *true를 전달했음을* 나타내거나 데이터 원본 자체가 읽기 전용임을 나타냅니다. SQL_DATASOURCE_READ_ONLY 대한 ODBC API 함수호출이 `SQLGetInfo` "y"를 반환하는 경우 데이터 원본은 읽기 전용입니다.

### <a name="remarks"></a>설명

모든 드라이버가 업데이트를 지원하는 것은 아닙니다.

## <a name="cdatabasecdatabase"></a><a name="cdatabase"></a>C데이터베이스::C데이터베이스

`CDatabase` 개체를 생성합니다.

```
CDatabase();
```

### <a name="remarks"></a>설명

개체를 생성한 후 해당 `OpenEx` 함수 `Open` 또는 멤버 함수를 호출하여 지정된 데이터 원본에 대한 연결을 설정해야 합니다.

문서 클래스에 개체를 `CDatabase` 포함하는 것이 편리할 수 있습니다.

### <a name="example"></a>예제

이 예제에서는 `CDatabase` `CDocument`-derived 클래스에서 사용 하 여 보여 줍니다.

[!code-cpp[NVC_MFCDatabase#9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]

[!code-cpp[NVC_MFCDatabase#10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]

## <a name="cdatabaseclose"></a><a name="close"></a>C데이터베이스::닫기

데이터 원본에서 연결을 끊으려면 이 멤버 함수를 호출합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

이 멤버 함수를 `CDatabase` 호출하기 전에 개체와 연결된 레코드 집합을 닫아야 합니다. 개체가 `Close` `CDatabase` 파괴되지 않으므로 동일한 데이터 원본 또는 다른 데이터 원본에 대한 새 연결을 열어 개체를 다시 사용할 수 있습니다.

데이터베이스를 `AddNew` 사용하는 `Edit` 레코드 집합의 보류 중 또는 명령문이 모두 취소되고 보류 중인 모든 트랜잭션이 롤백됩니다. 개체에 종속된 `CDatabase` 모든 레코드 집합은 정의되지 않은 상태로 남아 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]

## <a name="cdatabasecommittrans"></a><a name="committrans"></a>C데이터베이스::커밋트랜스

트랜잭션을 완료할 때 이 멤버 함수를 호출합니다.

```
BOOL CommitTrans();
```

### <a name="return-value"></a>Return Value

업데이트가 성공적으로 커밋된 경우 비영; 그렇지 않으면 0. 실패하면 `CommitTrans` 데이터 원본의 상태가 정의되지 않습니다. 데이터를 확인하여 상태를 확인해야 합니다.

### <a name="remarks"></a>설명

트랜잭션은 [BeginTrans](#begintrans) 멤버 함수에 `Edit`대한 `Delete`호출로 시작된 `Update` `CRecordset` 개체의 `AddNew`" 및 멤버 함수에 대한 일련의 호출로 구성됩니다. `CommitTrans`트랜잭션을 커밋합니다. 기본적으로 업데이트는 즉시 커밋됩니다. 호출하면 `BeginTrans` 호출될 때까지 `CommitTrans` 업데이트 약속이 지연됩니다.

트랜잭션을 `CommitTrans` 종료하기 위해 호출할 때까지 [Rollback](#rollback) 멤버 함수를 호출하여 트랜잭션을 중단하고 데이터 원본을 원래 상태로 둘 수 있습니다. 새 트랜잭션을 시작하려면 `BeginTrans` 다시 호출하십시오.

트랜잭션에 대한 자세한 내용은 [ODBC(트랜잭션)](../../data/odbc/transaction-odbc.md)문서를 참조하십시오.

### <a name="example"></a>예제

  문서 [트랜잭션: 레코드 집합(ODBC)에서 트랜잭션 수행 을](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)참조하십시오.

## <a name="cdatabaseexecutesql"></a><a name="executesql"></a>C데이터베이스::실행 SQL

SQL 명령을 직접 실행해야 하는 경우 이 멤버 함수를 호출합니다.

```cpp
void ExecuteSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>매개 변수

*lpszSQL*<br/>
실행할 유효한 SQL 명령을 포함하는 null-종단 문자열에 대한 포인터입니다. [CString](../../atl-mfc-shared/reference/cstringt-class.md)을 전달할 수 있습니다.

### <a name="remarks"></a>설명

명령을 null 종료 문자열로 만듭니다. `ExecuteSQL`데이터 레코드를 반환하지 않습니다. 레코드에서 작업하려면 레코드 집합 개체를 대신 사용합니다.

데이터 원본에 대한 대부분의 명령은 데이터 선택, 새 레코드 삽입, 레코드 삭제 및 레코드 편집에 대한 명령을 지원하는 레코드 집합 개체를 통해 발급됩니다. 그러나 모든 ODBC 기능이 데이터베이스 클래스에서 직접 지원되는 것은 아니므로 때때로 을 `ExecuteSQL`사용하여 직접 SQL을 호출해야 할 수도 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#13](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]

## <a name="cdatabasegetbookmarkpersistence"></a><a name="getbookmarkpersistence"></a>C데이터베이스::Getbookmark지속성

특정 작업 후 레코드 집합 개체에 책갈피가 유지되는지 확인하려면 이 멤버 함수를 호출합니다.

```
DWORD GetBookmarkPersistence() const;
```

### <a name="return-value"></a>Return Value

레코드 집합 개체에 책갈피를 유지하는 작업을 식별하는 비트 마스크입니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

예를 들어 `CRecordset::GetBookmark`와 `CRecordset::Requery`를 차례로 호출하면 `GetBookmark`에서 가져온 책갈피가 더 이상 유효하지 않게 될 수 있습니다. `GetBookmarkPersistence`를 호출하기 전에 `CRecordset::SetBookmark`를 호출해야 합니다.

다음 테이블에는 `GetBookmarkPersistence`의 반환 값에 대해 결합할 수 있는 비트 마스크 값이 나와 있습니다.

|비트 마스크 값|책갈피 유지|
|-------------------|--------------------------|
|SQL_BP_CLOSE|책갈피는 작업 `Requery` 후 유효합니다.|
|SQL_BP_DELETE|행의 책갈피는 해당 `Delete` 행에서 작업한 후에 유효합니다.|
|SQL_BP_DROP|책갈피는 작업 `Close` 후 유효합니다.|
|SQL_BP_SCROLL|책갈피는 모든 `Move` 작업 후에 유효합니다. 따라서 `CRecordset::CanBookmark`에서 반환되는 책갈피가 레코드 집합에서 지원되는지를 쉽게 파악할 수 있습니다.|
|SQL_BP_TRANSACTION|트랜잭션이 커밋되거나 롤백된 후에 책갈피가 유효합니다.|
|SQL_BP_UPDATE|행의 책갈피는 해당 `Update` 행에서 작업한 후에 유효합니다.|
|SQL_BP_OTHER_HSTMT|레코드 집합 개체 하나와 연결된 책갈피가 두 번째 레코드 집합에서도 유효합니다.|

이 반환 값에 대한 자세한 내용은 Windows `SQLGetInfo` SDK의 ODBC API 함수를 참조하십시오. 북마크에 대한 자세한 내용은 [문서 레코드 집합: 북마크 및 절대 위치(ODBC)를](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)참조하십시오.

## <a name="cdatabasegetconnect"></a><a name="getconnect"></a>C데이터베이스::연결 받기

이 멤버 함수를 호출하여 호출 하는 `OpenEx` 동안 `Open` 사용 `CDatabase` 되거나 개체를 데이터 원본에 연결 하는 연결 문자열을 검색 합니다.

```
const CString GetConnect() const;
```

### <a name="return-value"></a>Return Value

`OpenEx` 호출되거나 `Open` 호출된 경우 연결 문자열을 포함하는 **const**[CString입니다.](../../atl-mfc-shared/reference/cstringt-class.md) 그렇지 않으면 빈 문자열이 됩니다.

### <a name="remarks"></a>설명

연결 문자열을 만들 수 있는 방법에 대한 설명은 [CDatabase::Open을](#open) 참조하십시오.

## <a name="cdatabasegetcursorcommitbehavior"></a><a name="getcursorcommitbehavior"></a>C데이터베이스::GetCursor커커비헤이비어

이 멤버 함수를 호출하여 [CommitTrans](#committrans) 작업이 열린 레코드 집합 개체의 커서에 미치는 영향을 확인합니다.

```
int GetCursorCommitBehavior() const;
```

### <a name="return-value"></a>Return Value

열린 레코드 집합 개체에 대한 트랜잭션의 영향을 나타내는 값입니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

다음 표에는 열려 있는 `GetCursorCommitBehavior` 레코드 집합에 대한 가능한 반환 값과 해당 효과가 나열되어 있습니다.

|반환 값|C레코드집합 개체에 미치는 영향|
|------------------|----------------------------------|
|SQL_CB_CLOSE|트랜잭션 `CRecordset::Requery` 커밋 직후에 호출합니다.|
|SQL_CB_DELETE|트랜잭션 `CRecordset::Close` 커밋 직후에 호출합니다.|
|SQL_CB_PRESERVE|작업을 정상적으로 `CRecordset` 진행합니다.|

이 반환 값에 대한 자세한 내용은 Windows `SQLGetInfo` SDK의 ODBC API 함수를 참조하십시오. 트랜잭션에 대한 자세한 내용은 [ODBC(트랜잭션)](../../data/odbc/transaction-odbc.md)문서를 참조하십시오.

## <a name="cdatabasegetcursorrollbackbehavior"></a><a name="getcursorrollbackbehavior"></a>C데이터베이스::GetCursor롤백 동작

이 멤버 함수를 호출하여 [롤백](#rollback) 작업이 열린 레코드 집합 개체의 커서에 미치는 영향을 확인합니다.

```
int GetCursorRollbackBehavior() const;
```

### <a name="return-value"></a>Return Value

열린 레코드 집합 개체에 대한 트랜잭션의 영향을 나타내는 값입니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

다음 표에는 열려 있는 `GetCursorRollbackBehavior` 레코드 집합에 대한 가능한 반환 값과 해당 효과가 나열되어 있습니다.

|반환 값|C레코드집합 개체에 미치는 영향|
|------------------|----------------------------------|
|SQL_CB_CLOSE|트랜잭션 `CRecordset::Requery` 롤백 직후에 호출합니다.|
|SQL_CB_DELETE|트랜잭션 `CRecordset::Close` 롤백 직후에 호출합니다.|
|SQL_CB_PRESERVE|작업을 정상적으로 `CRecordset` 진행합니다.|

이 반환 값에 대한 자세한 내용은 Windows `SQLGetInfo` SDK의 ODBC API 함수를 참조하십시오. 트랜잭션에 대한 자세한 내용은 [ODBC(트랜잭션)](../../data/odbc/transaction-odbc.md)문서를 참조하십시오.

## <a name="cdatabasegetdatabasename"></a><a name="getdatabasename"></a>C데이터베이스::데이터베이스 이름

데이터 원본이 "데이터베이스"라는 명명된 개체를 정의하는 경우 이 멤버 함수를 호출하여 현재 연결된 데이터베이스의 이름을 검색합니다.

```
CString GetDatabaseName() const;
```

### <a name="return-value"></a>Return Value

성공하면 데이터베이스 이름을 포함하는 [CString;](../../atl-mfc-shared/reference/cstringt-class.md) 그렇지 않으면 `CString`빈 .

### <a name="remarks"></a>설명

이는 `OpenEx` 또는 호출에 지정된 DSN(데이터 원본 이름)과 동일하지 `Open` 않습니다. 반환은 `GetDatabaseName` ODBC에 따라 다릅니다. 일반적으로 데이터베이스는 테이블의 컬렉션입니다. 이 엔터티에 이름이 `GetDatabaseName` 있으면 반환합니다.

예를 들어 이 이름을 제목에 표시하려고 할 수 있습니다. ODBC에서 이름을 검색하는 동안 오류가 `GetDatabaseName` 발생하면 빈 `CString`을 반환합니다.

## <a name="cdatabaseisopen"></a><a name="isopen"></a>C데이터베이스::오픈

이 멤버 함수를 호출하여 개체가 `CDatabase` 현재 데이터 원본에 연결되어 있는지 확인합니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Return Value

개체가 현재 `CDatabase` 연결되어 있는 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="cdatabasem_hdbc"></a><a name="m_hdbc"></a>C데이터베이스::m_hdbc

ODBC 데이터 원본 연결에 대한 공용 핸들("연결 핸들")이 포함되어 있습니다.

### <a name="remarks"></a>설명

일반적으로 이 멤버 변수에 직접 액세스할 필요가 없습니다. 대신 프레임워크는 호출하거나 `OpenEx` `Open`을 호출할 때 핸들을 할당합니다. 프레임워크는 개체에서 **delete** 연산자호출시 핸들을 `CDatabase` 할당 합니다. 멤버 함수는 `Close` 핸들을 할당 하지 않습니다.

그러나 경우에 따라 핸들을 직접 사용해야 할 수도 있습니다. 예를 들어 클래스를 `CDatabase`통하지 않고 ODBC API 함수를 직접 호출해야 하는 경우 매개 변수로 전달하기 위해 연결 핸들이 필요할 수 있습니다. 아래 코드 예제를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]

## <a name="cdatabaseonsetoptions"></a><a name="onsetoptions"></a>C데이터베이스::시작 옵션

프레임워크는 멤버 함수를 통해 SQL 문을 직접 실행할 때 이 멤버 함수를 `ExecuteSQL` 호출합니다.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>매개 변수

*hstmt*<br/>
ODBC 문은 설정 중인 옵션을 처리합니다.

### <a name="remarks"></a>설명

`CRecordset::OnSetOptions`또한 이 멤버 함수를 호출합니다.

`OnSetOptions`로그인 시간 시간 값을 설정합니다. `SetQueryTimeout` 및 멤버 함수에 대한 이전 호출이 있는 경우 현재 값을 `OnSetOptions` 반영합니다. 그렇지 않으면 기본값을 설정합니다.

> [!NOTE]
> MFC 4.2 이전에는 `OnSetOptions` 처리 모드를 snychronous 또는 비동기로 설정합니다. MFC 4.2부터 모든 작업은 동기적입니다. 비동기 작업을 수행하려면 ODBC API 함수를 `SQLSetPos`직접 호출해야 합니다.

시간 초과 값을 변경하기 위해 재정의할 `OnSetOptions` 필요가 없습니다. 대신 쿼리 시간 지정 값을 사용자 `SetQueryTimeout` 지정하려면 레코드 집합을 만들기 전에 호출합니다. `OnSetOptions` 새 값을 사용합니다. 설정된 값은 모든 레코드 집합 또는 직접 SQL 호출의 후속 작업에 적용됩니다.

추가 `OnSetOptions` 옵션을 설정하려면 재정의합니다. 재정의는 ODBC API `OnSetOptions` 함수를 `SQLSetStmtOption`호출하기 전이나 후에 기본 클래스를 호출해야 합니다. 프레임 워크의 기본 구현에 설명 `OnSetOptions`된 메서드를 따르십시오.

## <a name="cdatabaseopen"></a><a name="open"></a>C데이터베이스::열기

이 멤버 함수를 호출하여 `CDatabase` 새로 생성된 개체를 초기화합니다.

```
virtual BOOL Open(
    LPCTSTR lpszDSN,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T("ODBC;"),
    BOOL bUseCursorLib = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszDSN*<br/>
ODBC 관리자 프로그램을 통해 ODBC에 등록된 이름인 데이터 원본 이름을 지정합니다. DSN 값이 *lpszConnect("DSN=* \<데이터 원본>" 형식)에 지정된 경우 *lpszDSN에*다시 지정하면 안 됩니다. 이 경우 *lpszDSN은* NULL이어야 합니다. 그렇지 않으면 사용자가 데이터 원본을 선택할 수 있는 데이터 원본 대화 상자를 사용자에게 표시하려는 경우 NULL을 전달할 수 있습니다. 자세한 내용은 비고를 참조하십시오.

*bExclusive*<br/>
이 클래스 라이브러리 버전에서는 지원되지 않습니다. 현재 이 매개 변수가 TRUE인 경우 어설션이 실패합니다. 데이터 원본은 항상 공유로 열립니다(배타적이지 않음).

*bReadOnly*<br/>
TRUE 연결을 읽기 전용으로 만들고 데이터 원본에 대한 업데이트를 금지하려는 경우 모든 종속 레코드 집합은 이 특성을 상속합니다. 기본값은 FALSE입니다.

*lpszConnect*<br/>
연결 문자열을 지정합니다. 연결 문자열은 데이터 원본 이름, 데이터 원본에서 유효한 사용자 ID, 사용자 인증 문자열(암호, 데이터 원본이 필요한 경우 암호) 및 기타 정보를 포함하여 정보를 연결합니다. 전체 연결 문자열은 문자열 "ODBC;" 접두사에 의해 접두사되어야 합니다. (대문자 또는 소문자)를 참조하십시오. "ODBC;" 문자열은 ODBC 데이터 원본에 대한 연결이 있음을 나타내는 데 사용됩니다. 이는 이후 버전의 클래스 라이브러리가 비 ODBC 데이터 원본을 지원할 수 있는 경우 상향 호환성을 위한 것입니다.

*bUseCursorLib*<br/>
ODBC 커서 라이브러리 DLL을 로드하려면 TRUE입니다. 커서 라이브러리는 기본 ODBC 드라이버의 일부 기능을 마스킹하여 드라이버가 지원하는 경우 다이너셋사용을 효과적으로 방지합니다. 커서 라이브러리가 로드된 경우 지원되는 커서만 정적 스냅숏과 정방향 전용 커서입니다. 기본값은 TRUE입니다. 레코드 집합 개체를 `CRecordset` 파생하지 않고 직접 만들려는 경우 커서 라이브러리를 로드해서는 안 됩니다.

### <a name="return-value"></a>Return Value

연결이 성공적으로 이루어지면 0이 아닙니다. 그렇지 않으면 0을 선택하면 추가 연결 정보를 요청하는 대화 상자가 표시될 때 취소를 선택합니다. 다른 모든 경우에는 프레임워크에서 예외를 throw합니다.

### <a name="remarks"></a>설명

데이터베이스 개체를 초기화하려면 먼저 데이터베이스 개체를 사용하여 레코드 집합 개체를 생성할 수 있습니다.

> [!NOTE]
> [OpenEx](#openex) 멤버 함수를 호출하는 것은 데이터 원본에 연결하고 데이터베이스 개체를 초기화하는 기본 방법입니다.

`Open` 호출의 매개 변수에 연결을 만들기에 충분한 정보가 없는 경우 ODBC 드라이버는 대화 상자를 열어 사용자로부터 필요한 정보를 얻습니다. 호출할 `Open`때 연결 문자열 *lpszConnect는* `CDatabase` 개체에 개인적으로 저장되며 [GetConnect](#getconnect) 멤버 함수를 호출하여 사용할 수 있습니다.

원하는 경우 호출하기 `Open` 전에 자신의 대화 상자를 열어 암호와 같은 사용자 정보를 얻은 다음 해당 정보를 에 전달하는 `Open`연결 문자열에 추가할 수 있습니다. 또는 다음에 응용 프로그램에서 개체를 호출할 `Open` 때 다시 사용할 수 있도록 전달하는 `CDatabase` 연결 문자열을 저장할 수 있습니다.

또한 여러 수준의 로그인 권한 부여(각 개체에 대해) `CDatabase` 연결 문자열을 사용하거나 다른 데이터 원본별 정보를 전달할 수도 있습니다. 연결 문자열에 대한 자세한 내용은 Windows SDK의 5장을 참조하십시오.

예를 들어 DBMS 호스트를 사용할 수 없는 경우 연결 시도가 시간 지정될 수 있습니다. 연결 시도가 실패하면 `Open` `CDBException`를 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]

## <a name="cdatabaseopenex"></a><a name="openex"></a>C데이터베이스::오픈엑스

이 멤버 함수를 호출하여 `CDatabase` 새로 생성된 개체를 초기화합니다.

```
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,
    DWORD dwOptions = 0);
```

### <a name="parameters"></a>매개 변수

*lpsz커넥트스트링*<br/>
ODBC 연결 문자열을 지정합니다. 여기에는 데이터 원본 이름뿐만 아니라 사용자 ID 및 암호와 같은 기타 선택적 정보가 포함됩니다. 예를 들어 , "DSN=SQLServer_Source; UID=SA; PWD=abc123"은 가능한 연결 문자열입니다. *lpszConnectString에*대해 NULL을 전달하면 데이터 원본 대화 상자가 사용자에게 데이터 원본을 선택하라는 메시지를 표시합니다.

*dwOptions*<br/>
다음 값의 조합을 지정하는 비트 마스크입니다. 기본값은 0으로, 데이터베이스가 쓰기 액세스와 함께 공유됨으로 열리고, ODBC 커서 라이브러리 DLL이 로드되지 않으며, ODBC 연결 대화 상자가 연결을 하기에 충분한 정보가 없는 경우에만 표시됩니다.

- `CDatabase::openExclusive`이 클래스 라이브러리 버전에서는 지원되지 않습니다. 데이터 원본은 항상 공유로 열립니다(배타적이지 않음). 현재 이 옵션을 지정하면 어설션이 실패합니다.

- `CDatabase::openReadOnly`데이터 원본을 읽기 전용으로 엽니다.

- `CDatabase::useCursorLib`ODBC 커서 라이브러리 DLL을 로드합니다. 커서 라이브러리는 기본 ODBC 드라이버의 일부 기능을 마스킹하여 드라이버가 지원하는 경우 다이너셋사용을 효과적으로 방지합니다. 커서 라이브러리가 로드된 경우 지원되는 커서만 정적 스냅숏과 정방향 전용 커서입니다. 레코드 집합 개체를 `CRecordset` 파생하지 않고 직접 만들려는 경우 커서 라이브러리를 로드해서는 안 됩니다.

- `CDatabase::noOdbcDialog`충분한 연결 정보가 제공되었는지 여부에 관계없이 ODBC 연결 대화 상자를 표시하지 마십시오.

- `CDatabase::forceOdbcDialog`항상 ODBC 연결 대화 상자를 표시합니다.

### <a name="return-value"></a>Return Value

연결이 성공적으로 이루어지면 0이 아닙니다. 그렇지 않으면 0을 선택하면 추가 연결 정보를 요청하는 대화 상자가 표시될 때 취소를 선택합니다. 다른 모든 경우에는 프레임워크에서 예외를 throw합니다.

### <a name="remarks"></a>설명

데이터베이스 개체를 초기화하려면 먼저 데이터베이스 개체를 사용하여 레코드 집합 개체를 생성할 수 있습니다.

`OpenEx` 호출의 `CDatabase::noOdbcDialog` *lpszConnectString* 매개 변수에 연결을 만들기에 충분한 정보가 없는 경우 ODBC 드라이버는 사용자가 설정하지 `CDatabase::forceOdbcDialog` 않았거나 *dwOptions* 매개 변수에 필요한 정보를 얻기 위해 대화 상자를 엽니다. 호출할 `OpenEx`때 연결 문자열 *lpszConnectString은* `CDatabase` 개체에 개인적으로 저장되며 [GetConnect](#getconnect) 멤버 함수를 호출하여 사용할 수 있습니다.

원하는 경우 호출하기 `OpenEx` 전에 사용자 자신의 대화 상자를 열어 암호와 같은 정보를 얻은 다음 해당 정보를 에 전달하는 연결 `OpenEx`문자열에 추가할 수 있습니다. 또는 다음에 응용 프로그램에서 개체를 호출할 `OpenEx` 때 다시 사용할 수 있도록 전달하는 `CDatabase` 연결 문자열을 저장할 수 있습니다.

또한 여러 수준의 로그인 권한 부여(각 개체에 대해) `CDatabase` 연결 문자열을 사용하거나 다른 데이터 원본별 정보를 전달할 수도 있습니다. 연결 문자열에 대한 자세한 내용은 *ODBC 프로그래머 의 참조*에서 6장을 참조하십시오.

예를 들어 DBMS 호스트를 사용할 수 없는 경우 연결 시도가 시간 지정될 수 있습니다. 연결 시도가 실패하면 `OpenEx` `CDBException`를 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]

## <a name="cdatabaserollback"></a><a name="rollback"></a>C데이터베이스::롤백

트랜잭션 중에 변경 한 내용을 되돌리려면 이 멤버 함수를 호출합니다.

```
BOOL Rollback();
```

### <a name="return-value"></a>Return Value

트랜잭션이 성공적으로 반전된 경우 비영; 그렇지 않으면 0. 호출에 `Rollback` 실패하면 데이터 원본 및 트랜잭션 상태가 정의되지 않습니다. 0을 반환하는 경우 `Rollback` 데이터 원본을 확인하여 상태를 확인해야 합니다.

### <a name="remarks"></a>설명

All `CRecordset` `AddNew` `Edit`, `Delete`및 `Update` 마지막 [BeginTrans](#begintrans) 이후 실행된 호출은 해당 호출 시 존재 했던 상태로 롤백됩니다.

호출 후 `Rollback`트랜잭션이 끝나고 다른 트랜잭션을 `BeginTrans` 다시 호출해야 합니다. 호출하기 `BeginTrans` 전에 현재 상태가 었던 레코드는 `Rollback`다음의 현재 레코드가 다시 됩니다.

롤백 후 롤백 이전의 현재 레코드는 현재 상태로 유지됩니다. 롤백 후 레코드 집합 및 데이터 원본의 상태에 대한 자세한 내용은 [ODBC(트랜잭션)](../../data/odbc/transaction-odbc.md)문서를 참조하십시오.

### <a name="example"></a>예제

  문서 [트랜잭션: 레코드 집합(ODBC)에서 트랜잭션 수행 을](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)참조하십시오.

## <a name="cdatabasesetlogintimeout"></a><a name="setlogintimeout"></a>C데이터베이스::Setlogin시간 설정

이 멤버 함수를 호출하기 `Open` 전에 또는 호출하기 `OpenEx` 전에 시도된 데이터 원본 연결 시간이 초과되기 전에 허용되는 기본 초 수를 재정의합니다.

```cpp
void SetLoginTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>매개 변수

*dw초*<br/>
연결 시도가 시간 배회하기 전에 허용할 수 있는 시간(초)입니다.

### <a name="remarks"></a>설명

예를 들어 DBMS를 사용할 수 없는 경우 연결 시도가 시간 지정될 수 있습니다. 초기화되지 `SetLoginTimeout` `CDatabase` 않은 개체를 생성한 후 `OpenEx` `Open`호출하거나 .

로그인 시간 설정의 기본값은 15초입니다. 모든 데이터 원본이 로그인 시간 지정 값을 지정하는 기능을 지원하지는 않습니다. 데이터 원본이 시간 시간을 지원하지 않는 경우 추적 출력을 얻지만 예외는 아닙니다. 값이 0이면 "무한"을 의미합니다.

## <a name="cdatabasesetquerytimeout"></a><a name="setquerytimeout"></a>C데이터베이스::Set쿼리 시간 설정

연결된 데이터 원본 시간 초과에 대한 후속 작업이 시작되기 전에 허용하도록 기본 초 수를 재정의하려면 이 멤버 함수를 호출합니다.

```cpp
void SetQueryTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>매개 변수

*dw초*<br/>
쿼리 시도가 시간 배회하기 전에 허용할 수 있는 시간(초)입니다.

### <a name="remarks"></a>설명

네트워크 액세스 문제, 과도한 쿼리 처리 시간 등으로 인해 작업이 시간 중지될 수 있습니다. 쿼리 `SetQueryTimeout` 시간 시간 값을 변경하려는 경우 레코드 집합을 열기 전에 또는 레코드 집합의 `AddNew`또는 `Update` `Delete` 멤버 함수를 호출하기 전에 호출합니다. 이 설정은 `Open`이 `AddNew` `CDatabase` `Update`개체와 `Delete` 연결된 모든 레코드 집합에 대한 모든 후속 . 및 호출에 영향을 줍니다. 개봉 후 레코드 집합에 대한 쿼리 시간 시간 값을 변경해도 레코드 집합의 값은 변경되지 않습니다. 예를 들어 `Move` 후속 작업은 새 값을 사용하지 않습니다.

쿼리 시간 설정의 기본값은 15초입니다. 모든 데이터 원본이 쿼리 시간 시간 값을 설정하는 기능을 지원하지는 않습니다. 쿼리 시간 지정 값을 0으로 설정하면 시간 지정이 발생하지 않습니다. 데이터 원본과의 통신이 응답하지 않을 수 있습니다. 이 동작은 개발 중에 유용할 수 있습니다. 데이터 원본이 시간 시간을 지원하지 않는 경우 추적 출력을 얻지만 예외는 아닙니다.

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)
