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
ms.openlocfilehash: 6d8bd56c0bfe4f9b35e34d067dd1042ed11066d5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751664"
---
# <a name="database-macros-and-globals"></a>데이터베이스 매크로 및 전역

아래에 나열된 매크로 및 전역은 ODBC 기반 데이터베이스 응용 프로그램에 적용됩니다. DAO 기반 응용 프로그램과 함께 사용되지 않습니다.

MFC 4.2 이전에는 `AFX_SQL_ASYNC` 매크로와 `AFX_SQL_SYNC` 비동기 연산이 다른 프로세스에 시간을 할애할 수 있는 기회를 제공했습니다. MFC 4.2부터 MFC ODBC 클래스는 동기 작업만 사용했기 때문에 이러한 매크로의 구현이 변경되었습니다. 매크로는 `AFX_ODBC_CALL` MFC 4.2에 새로운 것이었습니다.

### <a name="database-macros"></a>데이터베이스 매크로

|||
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|반환하는 ODBC API `SQL_STILL_EXECUTING`함수를 호출합니다. `AFX_ODBC_CALL`더 이상 반환되지 `SQL_STILL_EXECUTING`않을 때까지 함수를 반복적으로 호출합니다.|
|[AFX_SQL_ASYNC](#afx_sql_async)|`AFX_ODBC_CALL`.|
|[AFX_SQL_SYNC](#afx_sql_sync)|반환되지 `SQL_STILL_EXECUTING`않는 ODBC API 함수를 호출합니다.|

### <a name="database-globals"></a>데이터베이스 글로벌

|||
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|MFC에 동적으로 연결된 일반 MFC DLL에 대한 데이터베이스 지원을 추가합니다.|
|[AfxGetHENV](#afxgethenv)|MFC에서 현재 사용 중인 ODBC 환경에 대한 핸들을 검색합니다. 직접 ODBC 호출에서 이 핸들을 사용할 수 있습니다.|

## <a name="afxdbinitmodule"></a><a name="afxdbinitmodule"></a>아fxDbInit모듈

MFC 에 동적으로 연결된 일반 MFC DLL의 MFC 데이터베이스(또는 DAO) 지원의 `CWinApp::InitInstance` 경우 일반 MFC DLL 함수에서 이 함수에 대한 호출을 추가하여 MFC 데이터베이스 DLL을 초기화합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>설명

기본 클래스 호출 또는 MFC 데이터베이스 DLL에 액세스하는 추가 된 코드 전에이 호출이 발생 해야 합니다. MFC 데이터베이스 DLL은 MFC 확장 DLL입니다. MFC 확장 DLL이 `CDynLinkLibrary` 체인에 연결되려면 이를 사용할 모든 `CDynLinkLibrary` 모듈의 컨텍스트에서 개체를 만들어야 합니다. `AfxDbInitModule``CDynLinkLibrary` 을 사용하면 일반 MFC DLL의 컨텍스트에서 `CDynLinkLibrary` 개체를 만듭니다.

### <a name="requirements"></a>요구 사항

**헤더:** \<afxdll_.h>

## <a name="afx_odbc_call"></a><a name="afx_odbc_call"></a>AFX_ODBC_CALL

이 매크로를 사용하여 반환할 `SQL_STILL_EXECUTING`수 있는 모든 ODBC API 함수를 호출합니다.

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>매개 변수

*SQLFunc*<br/>
ODBC API 함수입니다. ODBC API 기능에 대한 자세한 내용은 Windows SDK를 참조하십시오.

### <a name="remarks"></a>설명

`AFX_ODBC_CALL`더 이상 반환되지 `SQL_STILL_EXECUTING`않는 함수를 호출합니다.

호출하기 `AFX_ODBC_CALL`전에 RETCODE 형식의 `nRetCode`변수를 선언해야 합니다.

이제 MFC ODBC 클래스는 동기 처리만 사용합니다. 비동기 작업을 수행하려면 ODBC API 함수를 `SQLSetConnectOption`호출해야 합니다. 자세한 내용은 Windows SDK의 "비동기적으로 기능 실행" 항목을 참조하십시오.

### <a name="example"></a>예제

이 예제에서는 `AFX_ODBC_CALL` `SQLColumns` ODBC API 함수를 호출하는 데 사용되며, 이 `strTableName`함수는 로 명명된 테이블의 열 목록을 반환합니다. 함수에 매개 `nRetCode` 변수를 전달하기 위해 레코드 집합 데이터 멤버의 선언 및 사용에 유의하십시오. 이 예제에서는 클래스의 멤버 함수를 `Check`사용하여 호출 결과를 `CRecordset`확인하는 방법도 보여 줍니다. 변수는 `prs` 다른 곳에서 `CRecordset` 선언된 개체에 대한 포인터입니다.

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="afx_sql_async"></a><a name="afx_sql_async"></a>AFX_SQL_ASYNC

이 매크로의 구현은 MFC 4.2에서 변경되었습니다.

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>매개 변수

*Prs*<br/>
`CRecordset` 개체 또는 `CDatabase` 개체에 대한 포인터입니다. MFC 4.2부터는 이 매개 변수 값이 무시됩니다.

*SQLFunc*<br/>
ODBC API 함수입니다. ODBC API 기능에 대한 자세한 내용은 Windows SDK를 참조하십시오.

### <a name="remarks"></a>설명

`AFX_SQL_ASYNC`단순히 매크로 [AFX_ODBC_CALL](#afx_odbc_call) 호출하고 *prs* 매개 변수를 무시합니다. MFC 4.2 이전 버전에서, `AFX_SQL_ASYNC`는 `SQL_STILL_EXECUTING`를 반환할 수 있는 ODBC API 함수를 호출하기 위해 사용되었습니다. ODBC API 함수가 `SQL_STILL_EXECUTING`을 반환한 경우, `AFX_SQL_ASYNC`가 `prs->OnWaitForDataSource`를 호출합니다.

> [!NOTE]
> MFC ODBC 클래스에는 이제 동기적 처리만 사용됩니다. 비동기 작업을 수행하려면 ODBC API 함수를 `SQLSetConnectOption`호출해야 합니다. 자세한 내용은 Windows SDK의 "비동기적으로 기능 실행" 항목을 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdb.h

## <a name="afx_sql_sync"></a><a name="afx_sql_sync"></a>AFX_SQL_SYNC

매크로는 `AFX_SQL_SYNC` 함수를 `SQLFunc`호출하기만 하면 됩니다.

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>매개 변수

*SQLFunc*<br/>
ODBC API 함수입니다. 이러한 기능에 대한 자세한 내용은 Windows SDK를 참조하십시오.

### <a name="remarks"></a>설명

이 매크로를 사용하여 반환되지 `SQL_STILL_EXECUTING`않는 ODBC API 함수를 호출합니다.

호출하기 `AFX_SQL_SYNC`전에 RETCODE `nRetCode`형식의 변수를 선언해야 합니다. 매크로 호출 후의 `nRetCode` 값을 확인할 수 있습니다.

MFC 4.2에서 `AFX_SQL_SYNC` 변경된 구현을 유의하십시오. 서버 상태를 확인하는 것이 더 `AFX_SQL_SYNC` 이상 필요하지 않으므로 `nRetCode`에 값을 할당하기만 하면 됩니다. 예를 들어, 전화를 걸지 않고

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

당신은 단순히 과제를 할 수 있습니다

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdb.h

## <a name="afxgethenv"></a><a name="afxgethenv"></a>아fx게첸프

반환된 핸들을 직접 ODBC 호출에서 사용할 수 있지만 핸들을 닫거나 기존 `CDatabase`또는 `CRecordset`파생 된 개체가 소멸 된 후에도 핸들이 여전히 유효하고 사용할 수 있다고 가정해서는 안됩니다.

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>Return Value

MFC에서 현재 사용 중인 ODBC 환경에 대한 핸들입니다. 사용 `SQL_HENV_NULL` 중인 [CDatabase](../../mfc/reference/cdatabase-class.md) 개체가 없고 [CRecordset](../../mfc/reference/crecordset-class.md) 개체가 없는 경우 일 수 있습니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdb.h

## <a name="see-also"></a>참조

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
