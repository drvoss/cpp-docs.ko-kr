---
title: CDB예외 클래스
ms.date: 11/04/2016
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
ms.openlocfilehash: 1ab7daeb3af55c92985c951c632b1d4050681474
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321900"
---
# <a name="cdbexception-class"></a>CDB예외 클래스

데이터베이스 클래스에서 발생하는 예외 상태를 나타냅니다.

## <a name="syntax"></a>구문

```
class CDBException : public CException
```

## <a name="members"></a>멤버

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDB예외:m_nRetCode](#m_nretcode)|형식 RETCODE의 개방형 데이터베이스 연결(ODBC) 반환 코드를 포함합니다.|
|[CDB예외:m_strError](#m_strerror)|상숫자 용어로 오류를 설명하는 문자열이 포함되어 있습니다.|
|[CDB예외:m_strStateNativeOrigin](#m_strstatenativeorigin)|ODBC에서 반환하는 오류 코드측면에서 오류를 설명하는 문자열이 포함되어 있습니다.|

## <a name="remarks"></a>설명

클래스에는 예외의 원인을 확인하거나 예외를 설명하는 문자 메시지를 표시하는 데 사용할 수 있는 두 개의 공용 데이터 멤버가 포함됩니다. `CDBException`개체는 데이터베이스 클래스의 멤버 함수에 의해 생성되고 throw됩니다.

> [!NOTE]
> 이 클래스는 MFC의 ODBC(개방형 데이터베이스 연결) 클래스 중 하나입니다. 대신 최신 DAO(데이터 액세스 개체) 클래스를 사용하는 경우 [대신 CDaoException을](../../mfc/reference/cdaoexception-class.md) 사용합니다. 모든 DAO 클래스 이름에는 접두사로 "CDao"가 있습니다. 자세한 내용은 [문서 개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)을 참조하십시오.

예외는 데이터 원본 또는 네트워크 I/O 오류와 같이 프로그램의 제어 외부 조건과 관련된 비정상적인 실행의 경우입니다. 프로그램을 실행하는 일반적인 과정에서 발생할 수 있는 오류는 일반적으로 예외로 간주되지 않습니다.

**CATCH** 식의 범위 내에서 이러한 개체에 액세스할 수 있습니다. 전역 함수를 `CDBException` 통해 사용자 고유의 `AfxThrowDBException` 코드에서 개체를 throw할 수도 있습니다.

일반적으로 예외 처리 또는 개체에 `CDBException` 대한 자세한 내용은 [MFC(예외 처리)](../../mfc/exception-handling-in-mfc.md) 및 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDBException`

## <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="cdbexceptionm_nretcode"></a><a name="m_nretcode"></a>CDB예외:m_nRetCode

ODBC 응용 프로그램 프로그래밍 인터페이스(API) 함수에서 반환되는 RETCODE 형식의 ODBC 오류 코드를 포함합니다.

### <a name="remarks"></a>설명

이 형식에는 ODBC에 의해 정의된 SQL 접두사 코드와 데이터베이스 클래스에서 정의한 AFX_SQL 접두사 코드가 포함됩니다. 에 `CDBException`대 한 이 멤버는 다음 값 중 하나를 포함 합니다.

- AFX_SQL_ERROR_API_CONFORMANCE `CDatabase::OpenEx` 또는 `CDatabase::Open` 호출에 대한 드라이버가 필요한 ODBC API 준수 수준 1(SQL_OAC_LEVEL1)을 준수하지 않습니다.

- AFX_SQL_ERROR_CONNECT_FAIL 데이터 원본에 대한 연결이 실패했습니다. 레코드 집합`CDatabase` 생성자 및 `GetDefaultConnect` 실패에 따라 연결을 만들려는 후속 시도에 NULL 포인터를 전달했습니다.

- AFX_SQL_ERROR_DATA_TRUNCATED 저장소를 제공한 것보다 더 많은 데이터를 요청했습니다. `CString` 제공된 데이터 저장소 또는 `CByteArray` 데이터 형식의 증가에 `nMaxLength` 대한 자세한 내용은 ["매크로](record-field-exchange-functions.md#rfx_text) 및 전역"에서 RFX_Text 및 [RFX_Binary](record-field-exchange-functions.md#rfx_binary) 대한 인수를 참조하십시오.

- AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED 다이너셋 `CRecordset::Open` 을 요청하는 호출이 실패했습니다. 다이너셋은 드라이버에서 지원되지 않습니다.

- AFX_SQL_ERROR_EMPTY_COLUMN_LIST 테이블을 열려고 시도했지만(또는 프로시저 호출 또는 **SELECT** 문으로 식별할 수 없음) `DoFieldExchange` 재정의에서 레코드 필드 교환(RFX) 함수 호출에서 식별된 열이 없습니다.

- AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH `DoFieldExchange` 재정의에서 RFX 함수 유형이 레코드 집합의 열 데이터 형식과 호환되지 않습니다.

- AFX_SQL_ERROR_ILLEGAL_MODE 이전에 `CRecordset::Update` 호출하거나 `CRecordset::AddNew` `CRecordset::Edit`.

- AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED ODBC 드라이버가 잠금을 지원하지 않으므로 업데이트에 대한 레코드 잠금 요청을 이행할 수 없습니다.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED 고유 `CRecordset::Update` `Delete` 키가 없는 테이블을 호출하거나 여러 레코드를 변경했습니다.

- AFX_SQL_ERROR_NO_CURRENT_RECORD 이전에 삭제된 레코드를 편집하거나 삭제하려고 시도한 것입니다. 삭제 한 후 새 현재 레코드로 스크롤해야합니다.

- AFX_SQL_ERROR_NO_POSITIONED_UPDATES ODBC 드라이버가 위치 업데이트를 지원하지 않으므로 다이너셋에 대한 요청을 이행할 수 없습니다.

- AFX_SQL_ERROR_NO_ROWS_AFFECTED `CRecordset::Update` 또는 `Delete`, 하지만 작업이 시작되면 레코드를 더 이상 찾을 수 없습니다.

- AFX_SQL_ERROR_ODBC_LOAD_FAILED ODBC를 로드하려고 합니다. DLL이 실패했습니다. Windows에서 이 DLL을 찾을 수 없거나 로드할 수 없습니다. 이 오류는 치명적입니다.

- AFX_SQL_ERROR_ODBC_V2_REQUIRED 레벨 2를 준수하는 ODBC 드라이버가 필요하기 때문에 다이너셋에 대한 요청을 이행할 수 없습니다.

- AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY 데이터 원본이 뒤로 스크롤을 지원하지 않기 때문에 스크롤 시도가 성공하지 못했습니다.

- AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED 스냅숏 `CRecordset::Open` 요청에 대한 호출이 실패했습니다. 스냅샷은 드라이버에서 지원되지 않습니다. 이 문제는 ODBC 커서 라이브러리 ODBCCURS 경우에만 발생합니다. DLL이 없습니다.)

- AFX_SQL_ERROR_SQL_CONFORMANCE `CDatabase::OpenEx` 또는 `CDatabase::Open` 호출에 대한 드라이버가 필요한 ODBC SQL 준수 수준 "최소"(SQL_OSC_MINIMUM)를 준수하지 않습니다.

- AFX_SQL_ERROR_SQL_NO_TOTAL ODBC 드라이버가 `CLongBinary` 데이터 값의 총 크기를 지정할 수 없습니다. 전역 메모리 블록을 할당할 수 없기 때문에 작업이 실패했을 수 있습니다.

- AFX_SQL_ERROR_RECORDSET_READONLY 읽기 전용 레코드 집합을 업데이트하려고 했거나 데이터 원본이 읽기 전용인 AFX_SQL_ERROR_RECORDSET_READONLY. 레코드 집합 또는 연결된 `CDatabase` 개체를 사용하면 업데이트 작업을 수행할 수 없습니다.

- SQL_ERROR 함수가 실패했습니다. ODBC 함수에서 `SQLError` 반환되는 오류 메시지가 `m_strError` 데이터 멤버에 저장됩니다.

- SQL_INVALID_HANDLE 잘못된 환경 핸들, 연결 핸들 또는 명령문 핸들로 인해 함수가 실패했습니다. 프로그래밍 오류를 나타냅니다. ODBC 함수에서 `SQLError`추가 정보를 사용할 수 없습니다.

SQL 접두사 코드는 ODBC에 의해 정의됩니다. AFX 접두사 코드는 AFXDB에 정의되어 있습니다. H, MFC\INCLUDE에서 발견.

## <a name="cdbexceptionm_strerror"></a><a name="m_strerror"></a>CDB예외:m_strError

예외를 발생 시킨 오류를 설명 하는 문자열을 포함 합니다.

### <a name="remarks"></a>설명

문자열은 상숫자 용어로 오류를 설명합니다. 자세한 정보 및 예제는 `m_strStateNativeOrigin`을 참조하십시오.

## <a name="cdbexceptionm_strstatenativeorigin"></a><a name="m_strstatenativeorigin"></a>CDB예외:m_strStateNativeOrigin

예외를 발생 시킨 오류를 설명 하는 문자열을 포함 합니다.

### <a name="remarks"></a>설명

문자열은 "State:%s,Native:%ld,Origin:%s"라는 형식의 형식 코드순서대로 다음을 설명하는 값으로 대체됩니다.

- SQLSTATE, ODBC 함수의 `SQLError` *szSqlState* 매개 변수에 반환 된 5 자 오류 코드를 포함 하는 null-종료 된 문자열 . SQLSTATE 값은 ODBC *프로그래머의 참조에*부록 A, [ODBC 오류 코드에](/sql/odbc/reference/appendixes/appendix-a-odbc-error-codes)나열됩니다. 예: "S0022".

- 함수의 *pfNativeError* 매개 변수에서 반환되는 데이터 원본과 `SQLError` 관련된 기본 오류 코드입니다. 예: 207.

- 함수의 *szErrorMsg* 매개 변수에 반환 `SQLError` 된 오류 메시지 텍스트입니다. 이 메시지는 여러 괄호로 묶인 이름으로 구성됩니다. 오류가 소스에서 사용자에게 전달되면 각 ODBC 구성 요소(데이터 원본, 드라이버, 드라이버 관리자)가 자체 이름을 추가합니다. 이 정보는 오류의 원인을 정확히 파악하는 데 도움이 됩니다. 예: [마이크로소프트][ODBC SQL 서버 드라이버][SQL 서버]

프레임워크는 오류 문자열을 해석하고 해당 `m_strStateNativeOrigin`구성 요소를 에 넣습니다. 둘 `m_strStateNativeOrigin` 이상의 오류에 대한 정보가 포함된 경우 오류는 줄 바호로 구분됩니다. 프레임워크는 에 참숫자 오류 `m_strError`텍스트를 넣습니다.

이 문자열을 구성하는 데 사용되는 코드에 대한 자세한 내용은 *ODBC 프로그래머의 참조에서* [SQLError](/sql/odbc/reference/syntax/sqlerror-function) 함수를 참조하십시오.

### <a name="example"></a>예제

ODBC에서:\["상태:S00222,네이티브:207,출처:\[마이크로소프트] ODBC\[SQL 서버 드라이버] SQL 서버] 잘못 된 열 이름 '콜 네임'"

`m_strStateNativeOrigin`에서 : "상태 : S0022,기본 :\[기원\[: 마이크로 소프트\[] ODBC SQL 서버 드라이버 ] SQL 서버]"

`m_strError`에서 : "잘못된 열 이름 'ColName'"

## <a name="see-also"></a>참고 항목

[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C데이터베이스 클래스](../../mfc/reference/cdatabase-class.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)<br/>
[C필드익스체인지 클래스](../../mfc/reference/cfieldexchange-class.md)<br/>
[C레코드 집합::업데이트](../../mfc/reference/crecordset-class.md#update)<br/>
[C레코드 집합::D](../../mfc/reference/crecordset-class.md#delete)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)
