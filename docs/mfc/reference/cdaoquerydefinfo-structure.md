---
title: CDaoQueryDefInfo 구조체
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDefInfo
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
ms.openlocfilehash: e2f0325237a30989637821464c63a4d8b8000b1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368943"
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo 구조체

구조에는 `CDaoQueryDefInfo` DAO(데이터 액세스 개체)에 대해 정의된 쿼리 def 개체에 대한 정보가 포함되어 있습니다.

## <a name="syntax"></a>구문

```
struct CDaoQueryDefInfo
{
    CString m_strName;               // Primary
    short m_nType;   // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    BOOL m_bUpdatable;               // Secondary
    BOOL m_bReturnsRecords;          // Secondary
    CString m_strSQL;                // All
    CString m_strConnect;            // All
    short m_nODBCTimeout;            // All
};
```

#### <a name="parameters"></a>매개 변수

*m_strName*<br/>
쿼리 def 개체의 이름을 고유하게 지정합니다. 자세한 내용은 DAO 도움말의 "이름 속성" 항목을 참조하십시오. [CDaoQueryDef::GetName을](../../mfc/reference/cdaoquerydef-class.md#getname) 호출하여 이 속성을 직접 검색합니다.

*m_nType*<br/>
쿼리 def 개체의 작동 유형을 나타내는 값입니다. 이 값은

- `dbQSelect`선택 — 쿼리가 레코드를 선택합니다.

- `dbQAction`작업 — 쿼리가 데이터를 이동하거나 변경하지만 레코드를 반환하지 는 않습니다.

- `dbQCrosstab`Crosstab — 쿼리는 스프레드시트와 같은 형식으로 데이터를 반환합니다.

- `dbQDelete`삭제 — 쿼리는 지정된 행 집합을 삭제합니다.

- `dbQUpdate`업데이트 — 쿼리가 레코드 집합을 변경합니다.

- `dbQAppend`추가 - 쿼리는 테이블 또는 쿼리의 끝에 새 레코드를 추가합니다.

- `dbQMakeTable`테이블 만들기 — 쿼리는 레코드 집합에서 새 테이블을 만듭니다.

- `dbQDDL`데이터 정의 - 쿼리는 테이블 또는 해당 부분의 구조에 영향을 줍니다.

- `dbQSQLPassThrough`통과 - SQL 문은 중간 처리 없이 데이터베이스 백 엔드에 직접 전달됩니다.

- `dbQSetOperation`Union — 쿼리는 중복 레코드가 제거된 두 개 이상의 테이블에 지정된 모든 레코드의 데이터를 포함하는 스냅숏 형식 레코드 집합 개체를 만듭니다. 중복을 포함하려면 querydef의 SQL 문에 **ALL** 키워드를 추가합니다.

- `dbQSPTBulk`레코드를 `dbQSQLPassThrough` 반환 하지 않는 쿼리를 지정 하는 데 사용 됩니다.

> [!NOTE]
> SQL 통과 쿼리를 만들려면 `dbQSQLPassThrough` 상수를 설정하지 않습니다. 이 설정은 쿼리 def 개체를 만들고 Connect 속성을 설정할 때 Microsoft Jet 데이터베이스 엔진에 의해 자동으로 설정됩니다.

자세한 내용은 DAO 도움말의 "속성 유형" 항목을 참조하십시오.

*m_dateCreated*<br/>
쿼리 def가 만들어진 날짜 및 시간입니다. 쿼리 def가 만들어진 날짜를 직접 검색하려면 테이블과 연결된 `CDaoTableDef` 개체의 [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) 멤버 함수를 호출합니다. 자세한 내용은 아래의 코멘트를 참조하십시오. 또한 DAO 도움말에서 "DateCreated, 마지막으로 업데이트된 속성" 항목을 참조하십시오.

*m_dateLastUpdated*<br/>
querydef에 대한 가장 최근 변경된 날짜 및 시간입니다. 테이블이 마지막으로 업데이트된 날짜를 직접 검색하려면 쿼리 def의 [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) 멤버 함수를 호출합니다. 자세한 내용은 아래의 코멘트를 참조하십시오. DAO 도움말에서 "DateCreated, 마지막으로 업데이트된 속성" 항목을 참조하십시오.

*m_bUpdatable*<br/>
querydef 개체를 변경할 수 있는지 여부를 나타냅니다. 이 속성이 TRUE이면 쿼리 def가 업데이터입니다. 그렇지 않으면 그렇지 않습니다. 업데이터 블은 쿼리 def 개체의 쿼리 정의를 변경할 수 있다는 것을 의미합니다. 쿼리 def 개체의 Updatable 속성은 결과 레코드 집합이 업데이터로 지정되지 않은 경우에도 쿼리 정의를 업데이트할 수 있는 경우 TRUE로 설정됩니다. 이 속성을 직접 검색하려면 querydef의 [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) 멤버 함수를 호출합니다. 자세한 내용은 DAO 도움말의 "업데이터 속성" 항목을 참조하십시오.

*m_bReturnsRecords*<br/>
외부 데이터베이스에 대한 SQL 통과 쿼리가 레코드를 반환하는지 여부를 나타냅니다. 이 속성이 TRUE이면 쿼리가 레코드를 반환합니다. 이 속성을 직접 검색하려면 [CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords)를 호출합니다. 외부 데이터베이스에 대한 모든 SQL 통과 쿼리가 레코드를 반환하는 것은 아닙니다. 예를 들어 SQL **UPDATE** 문은 레코드를 반환하지 않고 레코드를 업데이트하고 SQL **SELECT** 문은 레코드를 반환합니다. 자세한 내용은 DAO 도움말의 "ReturnsRecords 속성" 항목을 참조하십시오.

*m_strSQL*<br/>
querydef 개체에 의해 실행 된 쿼리를 정의 하는 SQL 문입니다. SQL 속성에는 쿼리를 실행할 때 레코드를 선택, 그룹화 및 정렬하는 방법을 결정하는 SQL 문이 포함되어 있습니다. 쿼리를 사용하여 다이너셋 또는 스냅숏 형식 레코드 집합 개체에 포함할 레코드를 선택할 수 있습니다. 레코드를 반환하지 않고 데이터를 수정하기 위해 대량 쿼리를 정의할 수도 있습니다. querydef의 [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) 멤버 함수를 호출 하 여 직접이 속성의 값을 검색할 수 있습니다.

*m_strConnect*<br/>
통과 쿼리에 사용되는 데이터베이스의 원본에 대한 정보를 제공합니다. 이 정보는 연결 문자열의 형태를 취합니다. 연결 문자열에 대한 자세한 정보 및 이 속성의 값을 직접 검색하는 자세한 내용은 [CDaoDatabase:GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) 멤버 함수를 참조하십시오.

*m_nODBCTimeout*<br/>
ODBC 데이터베이스에서 쿼리를 실행할 때 시간 시간 오류가 발생하기 전에 Microsoft Jet 데이터베이스 엔진이 대기하는 시간(초)입니다. Microsoft SQL Server와 같은 ODBC 데이터베이스를 사용하는 경우 네트워크 트래픽이나 ODBC 서버의 사용량이 많기 때문에 지연이 있을 수 있습니다. Microsoft Jet 엔진이 오류를 생성하기 전에 대기하는 데 걸리는 시간도 무기한 대기하는 대신 지정할 수 있습니다. 기본 시간 시간 값은 60초입니다. 쿼리 def의 [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) 멤버 함수를 호출하여 이 속성의 값을 직접 검색할 수 있습니다. 자세한 내용은 DAO 도움말의 "ODBCTimeout 속성" 항목을 참조하십시오.

## <a name="remarks"></a>설명

쿼리 def는 [클래스 CDaoQueryDef의](../../mfc/reference/cdaoquerydef-class.md)개체입니다. 위의 기본, 보조 및 모든 에 대한 참조는 클래스의 `CDaoDatabase` [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) 멤버 함수에서 정보를 반환하는 방법을 나타냅니다.

[CDaoDatabase에서 검색한 정보::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) 멤버 함수는 `CDaoQueryDefInfo` 구조체에 저장됩니다. QueryDefs 컬렉션 쿼리 def 개체가 저장 되는 데이터베이스 개체에 대 한 호출 `GetQueryDefInfo` 합니다. `CDaoQueryDefInfo`또한 디버그 `Dump` 빌드에서 멤버 함수를 정의합니다. 개체의 `Dump` 내용을 덤프하는 데 사용할 수 있습니다. `CDaoQueryDefInfo` 또한 `CDaoDatabase` 클래스는 개체에서 반환되는 모든 속성에 직접 `CDaoQueryDefInfo` 액세스하기 위한 멤버 함수를 `GetQueryDefInfo`제공하므로 을 호출할 필요가 거의 없습니다.

querydef 개체의 필드 또는 매개 변수 컬렉션에 새 필드 또는 매개 변수 개체를 추가 하는 경우 기본 데이터베이스 새 개체에 대 한 지정 된 데이터 형식을 지원 하지 않는 경우 예외가 throw 됩니다.

날짜 및 시간 설정은 querydef가 만들어지거나 마지막으로 업데이트된 컴퓨터에서 파생됩니다. 다중 사용자 환경에서 사용자는 Net **TIME** 명령을 사용하여 파일 서버에서 직접 이러한 설정을 가져옵니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고 항목

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDao데이터베이스 클래스](../../mfc/reference/cdaodatabase-class.md)
