---
title: 데이터베이스 매크로 및 전역
ms.date: 11/04/2016
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
helpviewer_keywords:
- global database functions [MFC]
- database macros [MFC]
- database globals [MFC]
- global functions [MFC], database functions
- macros [MFC], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
ms.openlocfilehash: 47a1bb434801c24ab8eee048d9ef8f93793101cc
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426272"
---
# <a name="database-macros-and-globals"></a>데이터베이스 매크로 및 전역

아래에 나열 된 매크로와 전역은 ODBC 기반 데이터베이스 응용 프로그램에 적용 됩니다. 이러한 응용 프로그램은 DAO 기반 응용 프로그램에서 사용 되지 않습니다.

MFC 4.2 이전에는 매크로 `AFX_SQL_ASYNC` 및 `AFX_SQL_SYNC`는 비동기 작업에 다른 프로세스에 대 한 시간을 산출 하는 기회를 제공 했습니다. Mfc 4.2부터 이러한 매크로의 구현은 MFC ODBC 클래스에서 동기 작업만 사용 하기 때문에 변경 되었습니다. 매크로 `AFX_ODBC_CALL`는 MFC 4.2에 처음 이었습니다.

### <a name="database-macros"></a>데이터베이스 매크로

|||
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|`SQL_STILL_EXECUTING`를 반환 하는 ODBC API 함수를 호출 합니다. `AFX_ODBC_CALL`는 더 이상 `SQL_STILL_EXECUTING`을 반환 하지 않을 때까지 함수를 반복적으로 호출 합니다.|
|[AFX_SQL_ASYNC](#afx_sql_async)|`AFX_ODBC_CALL`.|
|[AFX_SQL_SYNC](#afx_sql_sync)|`SQL_STILL_EXECUTING`를 반환 하지 않는 ODBC API 함수를 호출 합니다.|

### <a name="database-globals"></a>데이터베이스 전역

|||
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|MFC에 동적으로 연결 되는 일반 MFC DLL에 대 한 데이터베이스 지원을 추가 합니다.|
|[AfxGetHENV](#afxgethenv)|MFC에서 현재 사용 중인 ODBC 환경에 대 한 핸들을 검색 합니다. 이 핸들은 직접 ODBC 호출에서 사용할 수 있습니다.|

## <a name="afxdbinitmodule"></a>AfxDbInitModule

Mfc에 동적으로 연결 되는 일반 MFC DLL의 MFC 데이터베이스 (또는 DAO) 지원의 경우, MFC 데이터베이스 DLL을 초기화 하기 위해 일반 MFC DLL의 `CWinApp::InitInstance` 함수에이 함수에 대 한 호출을 추가 합니다.

### <a name="syntax"></a>구문

```
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>설명

이 호출이 기본 클래스 호출이 나 MFC 데이터베이스 DLL에 액세스 하는 추가 된 코드 보다 먼저 발생 하는지 확인 합니다. MFC 데이터베이스 DLL은 MFC 확장명 DLL입니다. MFC 확장 DLL이 `CDynLinkLibrary` 체인에 유선으로 연결 되도록 하려면이를 사용 하는 모든 모듈의 컨텍스트에서 `CDynLinkLibrary` 개체를 만들어야 합니다. `AfxDbInitModule`은 일반 mfc dll의 `CDynLinkLibrary` 개체 체인에 유선으로 연결 되도록 일반 MFC DLL의 컨텍스트에 `CDynLinkLibrary` 개체를 만듭니다.

### <a name="requirements"></a>요구 사항

**헤더:** \<afxdll_ >

##  <a name="afx_odbc_call"></a>AFX_ODBC_CALL

이 매크로를 사용 하 여 `SQL_STILL_EXECUTING`를 반환할 수 있는 ODBC API 함수를 호출 합니다.

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>매개 변수

*SQLFunc*<br/>
ODBC API 함수입니다. ODBC API 함수에 대 한 자세한 내용은 Windows SDK를 참조 하십시오.

### <a name="remarks"></a>설명

`AFX_ODBC_CALL`는 더 이상 `SQL_STILL_EXECUTING`를 반환 하지 않을 때까지 함수를 반복적으로 호출 합니다.

`AFX_ODBC_CALL`를 호출 하기 전에 RETCODE 형식의 변수 `nRetCode`를 선언 해야 합니다.

이제 MFC ODBC 클래스에서 동기 처리만 사용 합니다. 비동기 작업을 수행 하려면 `SQLSetConnectOption`ODBC API 함수를 호출 해야 합니다. 자세한 내용은 Windows SDK에서 "비동기적으로 함수 실행" 항목을 참조 하세요.

### <a name="example"></a>예제

이 예에서는 `AFX_ODBC_CALL`를 사용 하 여 `SQLColumns` ODBC API 함수를 호출 합니다 .이 함수는 `strTableName`으로 이름이 지정 된 테이블의 열 목록을 반환 합니다. `nRetCode` 선언 및 레코드 집합 데이터 멤버를 사용 하 여 매개 변수를 함수에 전달 합니다. 또한이 예제에서는 `Check`를 사용 하 여 호출 결과를 확인 하는 방법을 보여 줍니다. `CRecordset`클래스의 멤버 함수입니다. `prs` 변수는 다른 곳에서 선언 된 `CRecordset` 개체에 대 한 포인터입니다.

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afxdb

##  <a name="afx_sql_async"></a>AFX_SQL_ASYNC

이 매크로의 구현은 MFC 4.2에서 변경되었습니다.

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>매개 변수

*pr*<br/>
`CRecordset` 개체 또는 `CDatabase` 개체에 대한 포인터입니다. MFC 4.2부터는 이 매개 변수 값이 무시됩니다.

*SQLFunc*<br/>
ODBC API 함수입니다. ODBC API 함수에 대 한 자세한 내용은 Windows SDK를 참조 하십시오.

### <a name="remarks"></a>설명

`AFX_SQL_ASYNC`는 단순히 매크로 [AFX_ODBC_CALL](#afx_odbc_call) 를 호출 하 고 *pr* 매개 변수를 무시 합니다. MFC 4.2 이전 버전에서, `AFX_SQL_ASYNC`는 `SQL_STILL_EXECUTING`를 반환할 수 있는 ODBC API 함수를 호출하기 위해 사용되었습니다. ODBC API 함수가 `SQL_STILL_EXECUTING`을 반환한 경우, `AFX_SQL_ASYNC`가 `prs->OnWaitForDataSource`를 호출합니다.

> [!NOTE]
>  MFC ODBC 클래스에는 이제 동기적 처리만 사용됩니다. 비동기 작업을 수행 하려면 `SQLSetConnectOption`ODBC API 함수를 호출 해야 합니다. 자세한 내용은 Windows SDK에서 "비동기적으로 함수 실행" 항목을 참조 하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdb

##  <a name="afx_sql_sync"></a>AFX_SQL_SYNC

`AFX_SQL_SYNC` 매크로는 단순히 `SQLFunc`함수를 호출 합니다.

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>매개 변수

*SQLFunc*<br/>
ODBC API 함수입니다. 이러한 함수에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

### <a name="remarks"></a>설명

이 매크로를 사용 하 여 `SQL_STILL_EXECUTING`을 반환 하지 않는 ODBC API 함수를 호출 합니다.

`AFX_SQL_SYNC`를 호출 하기 전에 RETCODE 형식의 변수 `nRetCode`를 선언 해야 합니다. 매크로 호출 후 `nRetCode`의 값을 확인할 수 있습니다.

`AFX_SQL_SYNC`의 구현은 MFC 4.2에서 변경 되었습니다. 서버 상태 검사는 더 이상 필요 하지 않기 때문에 `AFX_SQL_SYNC` `nRetCode`에 값을 할당 합니다. 예를 들어를 호출 하는 대신

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

단순히 할당을 만들 수 있습니다.

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdb

##  <a name="afxgethenv"></a>AfxGetHENV

직접 ODBC 호출에서 반환 된 핸들을 사용할 수 있지만 핸들을 닫지 않아야 하거나 기존 `CDatabase`또는 `CRecordset`파생 개체가 제거 된 후에도 핸들이 여전히 유효 하 고 사용할 수 있는 것으로 가정 합니다.

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>Return Value

MFC에서 현재 사용 중인 ODBC 환경에 대 한 핸들입니다. 는 [CDatabase](../../mfc/reference/cdatabase-class.md) 개체가 없고 사용 중인 [CRecordset](../../mfc/reference/crecordset-class.md) 개체가 없는 경우 `SQL_HENV_NULL` 수 있습니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdb

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
