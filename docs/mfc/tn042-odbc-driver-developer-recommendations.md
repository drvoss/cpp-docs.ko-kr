---
title: 'TN042: ODBC 드라이버 개발자 권장 사항'
ms.date: 11/04/2016
f1_keywords:
- vc.odbc
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
ms.openlocfilehash: 67f7a86a247b60be66dabb0a89f04d39ce76222b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372132"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042: ODBC 드라이버 개발자 권장 사항

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 참고 는 ODBC 드라이버 작성기에 대 한 지침을 설명 합니다. MFC Database 클래스가 만드는 ODBC 기능의 일반적인 요구 사항 및 가정과 다양한 예상 의미 체계 세부 사항에 대해 간략하게 설명합니다. 세 `CRecordset` 가지 열기**모드(forwardOnly,** **스냅샷** 및 **다이너셋)를**지원하는 데 필요한 드라이버 기능이 설명되어 있습니다.

## <a name="odbcs-cursor-library"></a>ODBC의 커서 라이브러리

MFC Database 클래스는 대부분의 경우 대부분의 수준 1 ODBC 드라이버에서 제공하는 기능을 능가하는 기능을 사용자에게 제공합니다. 다행히 ODBC의 커서 라이브러리는 데이터베이스 클래스와 드라이버 간에 자체적으로 계층화되며 이러한 추가 기능의 대부분을 자동으로 제공합니다.

예를 들어 대부분의 1.0 드라이버는 뒤로 스크롤을 지원하지 않습니다. 커서 라이브러리는 이를 감지할 수 있으며 드라이버에서 행을 캐시하고 `SQLExtendedFetch`에서 FETCH_PREV 호출시 요청된 대로 표시합니다.

커서 라이브러리 종속성의 또 다른 중요한 예는 위치 업데이트입니다. 대부분의 1.0 드라이버는 포지셔닝된 업데이트도 없지만 커서 라이브러리는 현재 캐시된 데이터 값 또는 캐시된 타임스탬프 값을 기반으로 데이터 원본의 대상 행을 식별하는 업데이트 문을 생성합니다.

클래스 라이브러리는 여러 행 집합을 사용하지 않습니다. 따라서 몇 `SQLSetPos` 문은 항상 행 집합의 행 1에 적용됩니다.

## <a name="cdatabases"></a>C데이터베이스

각각은 `CDatabase` 하나의 **HDBC를**할당합니다. `CDatabase`('함수를 `ExecuteSQL` 사용하는 경우 **HSTMT가** 일시적으로 할당됩니다.) 따라서 여러's가 `CDatabase`필요한 경우 **HENV당** 여러 **HDBC를**지원해야 합니다.

데이터베이스 클래스에는 커서 라이브러리가 필요합니다. 이는 `SQLSetConnections` **SQL_CUR_USE_ODBC** **SQL_ODBC_CURSORS**호출에 반영됩니다.

`SQLDriverConnect`, **데이터** 원본에 `CDatabase::Open` 대한 연결을 설정하는 데 SQL_DRIVER_COMPLETE 사용됩니다.

드라이버는 **SQL_OAC_LEVEL1** `SQLGetInfo SQL_ODBC_API_CONFORMANCE`  >= SQL_OSC_MINIMUM `SQLGetInfo SQL_ODBC_SQL_CONFORMANCE`  >=  **SQL_OSC_MINIMUM**지원해야 합니다.

`CDatabase` 트랜잭션이 해당 레코드 집합 및 해당 종속 `SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR` 레코드 집합에 대해 지원되고 **SQL_CURSOR_ROLLBACK_BEHAVIOR** **SQL_CR_PRESERVE.** 그렇지 않으면 트랜잭션 제어를 수행하려는 시도가 무시됩니다.

`SQLGetInfo SQL_DATA_SOURCE_READ_ONLY`지원되어야 합니다. "Y"를 반환하면 데이터 원본에서 업데이트 작업이 수행되지 않습니다.

ReadOnly를 `CDatabase` 열면 데이터 원본 읽기만 설정하려고 시도하면 `SQLSetConnectOption SQL_ACCESS_MODE`SQL_MODE_READ_ONLY **SQL_MODE_READ_ONLY**.

식별자가 견적을 필요로 하는 경우 이 정보는 호출이 있는 `SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR` 드라이버에서 반환되어야 합니다.

디버깅을 위해 `SQLGetInfo SQL_DBMS_VER` **드라이버에서 SQL_DBMS_NAME** 검색됩니다.

`SQLSetStmtOption SQL_QUERY_TIMEOUT`SQL_ASYNC_ENABLE **SQL_ASYNC_ENABLE** `CDatabase` **HDBC에**호출 할 수 있습니다.

`SQLError`NULL로 호출될 수 있습니다.

물론, `SQLAllocEnv`에 `SQLAllocConnect` `SQLDisconnect` 지원되어야 `SQLFreeConnect` 합니다.

## <a name="executesql"></a>ExecuteSQL

임시 **HSTMT를**할당하고 해제하는 것 `ExecuteSQL` `SQLExecDirect`외에도 `SQLFetch` `SQLNumResultCol` , `SQLMoreResults`호출 및 . `SQLCancel`**HSTMT에서**호출될 수 있습니다.

## <a name="getdatabasename"></a>데이터베이스 이름 얻기

`SQLGetInfo SQL_DATABASE_NAME`호출됩니다.

## <a name="begintrans-committrans-rollback"></a>시작트랜스, 커밋트랜스, 롤백

`SQLSetConnectOption SQL_AUTOCOMMIT`트랜잭션 `SQLTransact SQL_COMMIT`요청이 이루어지면 **SQL_ROLLBACK** 및 **SQL_AUTOCOMMIT** 호출됩니다.

## <a name="crecordsets"></a>C레코드 집합

`SQLAllocStmt`( `SQLPrepare` `SQLExecute` `Open` for `Requery`and), `SQLExecDirect` (업데이트 작업의 `SQLFreeStmt` 경우)를 지원해야 합니다. `SQLNumResultCols`설정된 `SQLDescribeCol` 결과에 대해 호출됩니다.

`SQLSetParam`매개 변수 데이터 바인딩 및 **DATA_AT_EXEC** 기능을 광범위하게 사용합니다.

`SQLBindCol`을 사용하여 ODBC를 사용하여 출력 열 데이터 저장소 위치를 등록합니다.

두 `SQLGetData` 호출은 **SQL_LONG_VARCHAR** 및 **SQL_LONG_VARBINARY** 데이터를 검색하는 데 사용됩니다. 첫 번째 호출은 cbMaxValue 0을 사용하여 `SQLGetData` 열 값의 총 길이를 찾으려고 시도하지만 유효한 pcbValue를 사용하여 호출합니다. pcbValueSQL_NO_TOTAL **SQL_NO_TOTAL**보유 하는 경우 예외가 throw 됩니다. 그렇지 않으면 **HGLOBAL이** 할당되고 `SQLGetData` 전체 결과를 검색하기 위해 다른 호출이 할당됩니다.

## <a name="updating"></a>업데이트하는 중

비관적 잠금이 요청되면 `SQLGetInfo SQL_LOCK_TYPES` 쿼리됩니다. **SQL_LCK_EXCLUSIVE** 지원되지 않으면 예외가 throw됩니다.

`CRecordset` **(스냅샷** 또는 **다이너셋)을**업데이트하려고 하면 두 번째 **HSTMT가** 할당됩니다. 두 번째 **HSTMT를**지원하지 않는 드라이버의 경우 커서 라이브러리에서 이 기능을 시뮬레이션합니다. 안타깝게도 이는 두 **번째**HSTMT 요청을 처리하기 전에 첫 번째 **HSTMT의** 현재 쿼리를 강제로 완료해야 하는 경우도 있습니다.

`SQLFreeStmt SQL_CLOSE`**SQL_RESET_PARAMS** 업데이트 `SQLGetCursorName` 작업 중에 호출됩니다.

출력에 **CLongBinarys가** 있는 **경우열,** ODBC의 **DATA_AT_EXEC** 기능이 지원되어야 합니다. 여기에는 **SQL_NEED_DATA** `SQLExecDirect`에서 SQL_NEED_DATA `SQLParamData` `SQLPutData`반환하는 것이 포함됩니다.

`SQLRowCount`실행 한 후 호출되어 1개의 레코드만 에 `SQLExecDirect`의해 업데이트되었는지 확인합니다.

## <a name="forwardonly-cursors"></a>앞으로만 커서

`Move` 작업에만 `SQLFetch` 필요합니다. **전달전용** 커서는 업데이트를 지원하지 않습니다.

## <a name="snapshot-cursors"></a>스냅샷 커서

스냅샷 `SQLExtendedFetch` 기능에는 지원이 필요합니다. 위에서 설명한 것처럼 ODBC 커서 라이브러리는 드라이버가 `SQLExtendedFetch`지원하지 않는 시기를 감지하고 필요한 지원 자체를 제공합니다.

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** **SQL_SO_STATIC**지원해야합니다.

## <a name="dynaset-cursors"></a>다이나셋 커서

다음은 다이너셋을 여는 데 필요한 최소 지원입니다.

`SQLGetInfo`SQL_ODBC_VER **SQL_ODBC_VER** "01"> 반환해야 합니다.

`SQLGetInfo`SQL_SCROLL_OPTIONS **SQL_SCROLL_OPTIONS** **SQL_SO_KEYSET_DRIVEN**지원해야 합니다.

`SQLGetInfo`SQL_ROW_UPDATES **SQL_ROW_UPDATES** "Y"를 반환해야 합니다.

`SQLGetInfo`SQL_POSITIONED_UPDATES **SQL_POSITIONED_UPDATES** **SQL_PS_POSITIONED_DELETE** **SQL_PS_POSITIONED_UPDATE**지원해야합니다.

또한 비관적 잠금이 요청된 경우 irow 1, fRefresh FALSE 및 fLock `SQLSetPos` **SQL_LCK_EXCLUSIVE** 호출합니다.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
