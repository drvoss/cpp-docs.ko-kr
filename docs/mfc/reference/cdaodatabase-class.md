---
title: CDao데이터베이스 클래스
ms.date: 09/17/2019
f1_keywords:
- CDaoDatabase
- AFXDAO/CDaoDatabase
- AFXDAO/CDaoDatabase::CDaoDatabase
- AFXDAO/CDaoDatabase::CanTransact
- AFXDAO/CDaoDatabase::CanUpdate
- AFXDAO/CDaoDatabase::Close
- AFXDAO/CDaoDatabase::Create
- AFXDAO/CDaoDatabase::CreateRelation
- AFXDAO/CDaoDatabase::DeleteQueryDef
- AFXDAO/CDaoDatabase::DeleteRelation
- AFXDAO/CDaoDatabase::DeleteTableDef
- AFXDAO/CDaoDatabase::Execute
- AFXDAO/CDaoDatabase::GetConnect
- AFXDAO/CDaoDatabase::GetName
- AFXDAO/CDaoDatabase::GetQueryDefCount
- AFXDAO/CDaoDatabase::GetQueryDefInfo
- AFXDAO/CDaoDatabase::GetQueryTimeout
- AFXDAO/CDaoDatabase::GetRecordsAffected
- AFXDAO/CDaoDatabase::GetRelationCount
- AFXDAO/CDaoDatabase::GetRelationInfo
- AFXDAO/CDaoDatabase::GetTableDefCount
- AFXDAO/CDaoDatabase::GetTableDefInfo
- AFXDAO/CDaoDatabase::GetVersion
- AFXDAO/CDaoDatabase::IsOpen
- AFXDAO/CDaoDatabase::Open
- AFXDAO/CDaoDatabase::SetQueryTimeout
- AFXDAO/CDaoDatabase::m_pDAODatabase
- AFXDAO/CDaoDatabase::m_pWorkspace
helpviewer_keywords:
- CDaoDatabase [MFC], CDaoDatabase
- CDaoDatabase [MFC], CanTransact
- CDaoDatabase [MFC], CanUpdate
- CDaoDatabase [MFC], Close
- CDaoDatabase [MFC], Create
- CDaoDatabase [MFC], CreateRelation
- CDaoDatabase [MFC], DeleteQueryDef
- CDaoDatabase [MFC], DeleteRelation
- CDaoDatabase [MFC], DeleteTableDef
- CDaoDatabase [MFC], Execute
- CDaoDatabase [MFC], GetConnect
- CDaoDatabase [MFC], GetName
- CDaoDatabase [MFC], GetQueryDefCount
- CDaoDatabase [MFC], GetQueryDefInfo
- CDaoDatabase [MFC], GetQueryTimeout
- CDaoDatabase [MFC], GetRecordsAffected
- CDaoDatabase [MFC], GetRelationCount
- CDaoDatabase [MFC], GetRelationInfo
- CDaoDatabase [MFC], GetTableDefCount
- CDaoDatabase [MFC], GetTableDefInfo
- CDaoDatabase [MFC], GetVersion
- CDaoDatabase [MFC], IsOpen
- CDaoDatabase [MFC], Open
- CDaoDatabase [MFC], SetQueryTimeout
- CDaoDatabase [MFC], m_pDAODatabase
- CDaoDatabase [MFC], m_pWorkspace
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
ms.openlocfilehash: 0fbc4ee3f2033f7507a1ed68493fa7e48bc62c51
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754747"
---
# <a name="cdaodatabase-class"></a>CDao데이터베이스 클래스

DAO(데이터 액세스 개체)를 사용하여 액세스 데이터베이스에 대한 연결을 나타냅니다. DAO는 Office 2013을 통해 지원됩니다. DAO 3.6은 최종 버전이며 더 이상 사용되지 않는 것으로 간주됩니다.

## <a name="syntax"></a>구문

```
class CDaoDatabase : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|`CDaoDatabase` 개체를 생성합니다. 호출하여 `Open` 개체를 데이터베이스에 연결합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDaoDatabase::CanTransact](#cantransact)|데이터베이스가 트랜잭션을 지원하는 경우 0이 아닌 것을 반환합니다.|
|[CDaoDatabase::CanUpdate](#canupdate)|개체가 `CDaoDatabase` 업데이터(읽기 전용이 아님)인 경우 0이 아님을 반환합니다.|
|[CDaoDatabase::Close](#close)|데이터베이스 연결을 닫습니다.|
|[CDao데이터베이스::만들기](#create)|기본 DAO 데이터베이스 개체를 만들고 `CDaoDatabase` 개체를 초기화합니다.|
|[CDao데이터베이스::만들기관계](#createrelation)|데이터베이스의 테이블 간에 새 관계를 정의합니다.|
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|데이터베이스의 QueryDefs 컬렉션에 저장된 쿼리 def 개체를 삭제합니다.|
|[CDao데이터베이스::DeleteRelation](#deleterelation)|데이터베이스의 테이블 간의 기존 관계를 삭제합니다.|
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|데이터베이스에서 테이블의 정의를 삭제합니다. 이렇게 하면 실제 테이블과 모든 데이터가 삭제됩니다.|
|[CDaoDatabase::Execute](#execute)|작업 쿼리를 실행합니다. 결과를 `Execute` 반환하는 쿼리를 호출하면 예외가 발생합니다.|
|[CDaoDatabase::GetConnect](#getconnect)|개체를 데이터베이스에 연결하는 데 `CDaoDatabase` 사용되는 연결 문자열을 반환합니다. ODBC에 사용됩니다.|
|[CDaoDatabase::GetName](#getname)|현재 사용 중인 데이터베이스의 이름을 반환합니다.|
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|데이터베이스에 대해 정의된 쿼리 수를 반환합니다.|
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|데이터베이스에 정의된 지정된 쿼리에 대한 정보를 반환합니다.|
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|데이터베이스 쿼리 작업이 시간 중지되는 시간(초) 수를 반환합니다. `Execute` ODBC 데이터 원본(만 해당)에서 모든 후속 열기, 추가, 새 작업 추가 및 편집 작업 및 ODBC 데이터 원본에 대한 기타 작업에 영향을 줍니다.|
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|마지막 업데이트, 편집 또는 작업 추가 또는 에 대한 호출에 `Execute`의해 영향을 받는 레코드 수를 반환합니다.|
|[CDao데이터베이스::관계 관계 카운트](#getrelationcount)|데이터베이스의 테이블 간에 정의된 관계 수를 반환합니다.|
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|데이터베이스의 테이블 간에 정의된 지정된 관계에 대한 정보를 반환합니다.|
|[CDao데이터베이스::GettableDefCount](#gettabledefcount)|데이터베이스에 정의된 테이블 수를 반환합니다.|
|[CDao데이터베이스::GettableDefInfo](#gettabledefinfo)|데이터베이스에서 지정된 테이블에 대한 정보를 반환합니다.|
|[CDao데이터베이스::GetVersion](#getversion)|데이터베이스와 연결된 데이터베이스 엔진의 버전을 반환합니다.|
|[CDaoDatabase::IsOpen](#isopen)|개체가 `CDaoDatabase` 현재 데이터베이스에 연결되어 있는 경우 0이 아닌 것을 반환합니다.|
|[CDaoDatabase::Open](#open)|데이터베이스에 대한 연결을 설정합니다.|
|[CDao데이터베이스::SetQuery시간 설정](#setquerytimeout)|ODBC 데이터 원본에서만 데이터베이스 쿼리 작업이 시간 중지되는 시간(초) 이후의 시간을 설정합니다. 이후의 모든 열기, 새 추가, 업데이트 및 삭제 작업에 영향을 줍니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDao데이터베이스::m_pDAODatabase](#m_pdaodatabase)|기본 DAO 데이터베이스 개체에 대한 포인터입니다.|
|[CDao데이터베이스:m_pWorkspace](#m_pworkspace)|데이터베이스를 포함 하 고 해당 트랜잭션 공간을 정의 하는 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체에 대 한 포인터입니다.|

## <a name="remarks"></a>설명

지원되는 데이터베이스 형식에 대한 자세한 내용은 [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) 멤버 함수를 참조하십시오. [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체로 표시되는 지정된 "작업 영역"에서 한 번에 하나 이상의 `CDaoDatabase` 개체를 활성화할 수 있습니다. 작업 영역은 데이터베이스 컬렉션이라고 하는 열린 데이터베이스 개체의 컬렉션을 유지 관리합니다.

## <a name="usage"></a>사용

레코드 집합 개체를 만들 때 데이터베이스 개체를 암시적으로 만들 수 있습니다. 그러나 데이터베이스 개체를 명시적으로 만들 수도 있습니다. 을 사용하여 `CDaoDatabase`기존 데이터베이스를 명시적으로 사용하려면 다음 중 하나를 수행합니다.

- `CDaoDatabase` 개체를 생성하여 열려 있는 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체에 대한 포인터를 전달합니다.

- 또는 작업 `CDaoDatabase` 영역을 지정하지 않고 개체를 생성합니다(MFC는 임시 작업 영역 개체를 만듭니다).

새 Microsoft Jet(를 만들려면) MDB) 데이터베이스를 구성하고 개체 만들기 [함수를](#create) `CDaoDatabase` 호출합니다. 후 `Create` *호출하지* `Open` 마십시오.

기존 데이터베이스를 열려면 개체를 `CDaoDatabase` 생성하고 [Open](#open) 멤버 함수를 호출합니다.

이러한 기술은 DAO 데이터베이스 개체를 작업 영역의 데이터베이스 컬렉션에 추가하고 데이터에 대한 연결을 엽니다. 그런 다음 연결된 데이터베이스에서 작동하기 위해 [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)또는 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 개체를 생성할 때 `CDaoDatabase` 이러한 개체에 대한 생성자에게 개체에 대한 포인터를 전달합니다. 연결 사용을 마치면 멤버 [닫기](#close) 함수를 `CDaoDatabase` 호출하고 개체를 삭제합니다. `Close`이전에 닫지 않은 레코드 집합을 닫습니다.

## <a name="transactions"></a>트랜잭션

데이터베이스 트랜잭션 처리는 작업 영역 수준에서 [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans)제공됩니다. [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans) [Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) `CDaoWorkspace`

## <a name="odbc-connections"></a>ODBC 연결

ODBC 데이터 원본으로 작업하는 권장 방법은 외부 테이블을 Microsoft Jet(( MDB) 데이터베이스.

## <a name="collections"></a>컬렉션

각 데이터베이스는 tabledef, 쿼리 def, 레코드 집합 및 관계 개체의 자체 컬렉션을 유지 관리합니다. 클래스는 `CDaoDatabase` 이러한 개체를 조작하기 위한 멤버 함수를 제공합니다.

> [!NOTE]
> 개체는 MFC 데이터베이스 개체가 아닌 DAO에 저장됩니다. MFC는 테이블def, 쿼리 def 및 레코드 집합 개체에 대한 클래스를 제공하지만 관계 객체는 제공하지 않습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDaoDatabase`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="cdaodatabasecantransact"></a><a name="cantransact"></a>CDao데이터베이스::캔트랜스액트

이 멤버 함수를 호출하여 데이터베이스가 트랜잭션을 허용하는지 여부를 확인합니다.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Return Value

데이터베이스가 트랜잭션을 지원하는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

트랜잭션은 데이터베이스의 작업 영역에서 관리됩니다.

## <a name="cdaodatabasecanupdate"></a><a name="canupdate"></a>CDao데이터베이스::캔업데이트

이 멤버 함수를 호출하여 개체가 `CDaoDatabase` 업데이트를 허용하는지 여부를 확인합니다.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Return Value

개체가 업데이트를 `CDaoDatabase` 허용하는 경우 0이 아닙니다. 그렇지 않으면 0을 사용하면 `CDaoDatabase` 개체를 열 때 *true를 bReadOnly로* 전달했거나 데이터베이스 자체가 읽기 전용임을 나타냅니다. 멤버 [열기](#open) 기능을 참조하십시오.

### <a name="remarks"></a>설명

데이터베이스 업데이터 가능성에 대한 자세한 내용은 DAO 도움말의 "업데이터 속성" 항목을 참조하십시오.

## <a name="cdaodatabasecdaodatabase"></a><a name="cdaodatabase"></a>CDao데이터베이스::CDao데이터베이스

`CDaoDatabase` 개체를 생성합니다.

```
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```

### <a name="parameters"></a>매개 변수

*pWorkspace*<br/>
새 데이터베이스 `CDaoWorkspace` 개체를 포함 하는 개체에 대 한 포인터입니다. NULL의 기본값을 수락하면 생성자는 기본 DAO 작업 공간을 사용하는 임시 `CDaoWorkspace` 개체를 만듭니다. [m_pWorkspace](#m_pworkspace) 데이터 멤버를 통해 작업 영역 개체에 대한 포인터를 얻을 수 있습니다.

### <a name="remarks"></a>설명

개체를 생성한 후 새 Microsoft Jet(를 만드는 경우) MDB) 데이터베이스, 개체의 멤버 [만들기](#create) 함수를 호출합니다. 대신 기존 데이터베이스를 여는 경우 개체의 [Open](#open) 멤버 함수를 호출합니다.

개체를 완료하면 [해당 닫기](#close) 멤버 함수를 호출한 `CDaoDatabase` 다음 개체를 삭제해야 합니다.

문서 클래스에 개체를 `CDaoDatabase` 포함하는 것이 편리할 수 있습니다.

> [!NOTE]
> 기존 `CDaoDatabase` `CDaoDatabase` 개체에 대한 포인터를 전달하지 않고 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체를 여는 경우에도 개체가 암시적으로 만들어집니다. 이 데이터베이스 개체는 레코드 집합 개체를 닫을 때 닫힙습니다.

## <a name="cdaodatabaseclose"></a><a name="close"></a>CDao데이터베이스::닫기

이 멤버 함수를 호출하여 데이터베이스연결을 끊고 데이터베이스와 연결된 열려 있는 레코드 집합, 테이블defs 및 쿼리 defs를 닫습니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

이 멤버 함수를 호출하기 전에 이러한 개체를 직접 닫는 것이 좋습니다. 개체를 `CDaoDatabase` 닫으면 연결된 [작업 영역의](../../mfc/reference/cdaoworkspace-class.md)데이터베이스 컬렉션에서 개체가 제거됩니다. 개체가 `Close` `CDaoDatabase` 파괴되지 않으므로 동일한 데이터베이스 또는 다른 데이터베이스를 열어 개체를 다시 사용할 수 있습니다.

> [!CAUTION]
> 데이터베이스를 닫기 전에 [업데이트](../../mfc/reference/cdaorecordset-class.md#update) 멤버 함수(보류 `Close` 중인 편집이 있는 경우)와 열려 있는 모든 레코드 집합 개체의 멤버 함수를 호출합니다. [스택의 CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 또는 `CDaoDatabase` 개체를 선언하는 함수를 종료하면 데이터베이스가 닫히고, 저장되지 않은 변경 내용이 손실되고, 보류 중인 트랜잭션이 롤백되고, 데이터에 대한 보류 중인 편집 내용이 손실됩니다.

> [!CAUTION]
> 레코드 집합 개체가 열려 있는 동안 데이터베이스 개체를 닫으려고 하거나 특정 작업 영역에 속한 데이터베이스 개체가 열려 있는 동안 작업 영역 개체를 닫으려고 하면 해당 레코드 집합 개체가 닫히고 보류 중인 업데이트 또는 편집 내용이 롤백됩니다. 작업 영역 개체에 속한 데이터베이스 개체가 열려 있는 동안 작업 영역 개체를 닫으려고 하면 해당 특정 작업 영역 개체에 속한 모든 데이터베이스 개체가 닫히므로 닫히지 않은 레코드 집합 개체가 닫히게 될 수 있습니다. 데이터베이스 개체를 닫지 않으면 MFC는 디버그 빌드에서 어설션 오류를 보고합니다.

데이터베이스 개체가 함수의 범위를 벗어나정의 되고 함수를 닫지 않고 함수를 종료하면 데이터베이스 개체가 명시적으로 닫히거나 정의된 모듈이 범위를 벗어날 때까지 열려 있습니다.

## <a name="cdaodatabasecreate"></a><a name="create"></a>CDao데이터베이스::만들기

새 Microsoft Jet(를 만들려면) MDB) 데이터베이스를 사용하여 개체를 생성한 `CDaoDatabase` 후 이 멤버 함수를 호출합니다.

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int dwOptions = 0);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
만드는 데이터베이스 파일의 이름인 문자열 식입니다. "C:\\\MYDB와 같은 전체 경로 및 파일 이름일 수 있습니다. MDB". 이름을 제공해야 합니다. 파일 이름 확장명을 제공하지 않으면 . MDB가 추가됩니다. 네트워크가 UNC(통일 명명 규칙)를 지원하는 경우 "mySERVER\\\\\\\MYSHARE\\\\\MYDIR\\\MYDB"와 같은 네트워크 경로를 지정할 수도 있습니다. 만 마이크로 소프트 제트 (. MDB) 데이터베이스 파일은 이 멤버 함수를 사용하여 만들 수 있습니다. ("C++ 이스케이프 문자이기 때문에\\문자열 리터럴에서 이중 백슬래시가 필요합니다.)

*lpszLocale*<br/>
데이터베이스를 만들기 위한 정렬 순서를 지정하는 데 사용되는 문자열 식입니다. 기본값은 `dbLangGeneral`입니다. 가능한 값은 다음과 같습니다.

- `dbLangGeneral`영어, 독일어, 프랑스어, 포르투갈어, 이탈리아어 및 현대 스페인어

- `dbLangArabic`아랍어

- `dbLangCyrillic`러시아어

- `dbLangCzech`체코어

- `dbLangDutch`네덜란드어

- `dbLangGreek`그리스어

- `dbLangHebrew`히브리어

- `dbLangHungarian`헝가리어

- `dbLangIcelandic`아이슬란드어

- `dbLangNordic`북유럽 언어(마이크로소프트 제트 데이터베이스 엔진 버전 1.0에만)

- `dbLangNorwdan`노르웨이어 및 덴마크어

- `dbLangPolish`폴란드어

- `dbLangSpanish`전통 스페인어

- `dbLangSwedfin`스웨덴어 및 핀란드어

- `dbLangTurkish`터키어

*dwOptions*<br/>
하나 이상의 옵션을 나타내는 정수입니다. 가능한 값은 다음과 같습니다.

- `dbEncrypt`암호화된 데이터베이스를 만듭니다.

- `dbVersion10`Microsoft Jet 데이터베이스 버전 1.0으로 데이터베이스를 만듭니다.

- `dbVersion11`Microsoft Jet 데이터베이스 버전 1.1을 사용하여 데이터베이스를 만듭니다.

- `dbVersion20`Microsoft Jet 데이터베이스 버전 2.0으로 데이터베이스를 만듭니다.

- `dbVersion30`Microsoft Jet 데이터베이스 버전 3.0으로 데이터베이스를 만듭니다.

암호화 상수를 생략하면 암호화되지 않은 데이터베이스가 만들어집니다. 하나의 버전 상수만 지정할 수 있습니다. 버전 상수를 생략하면 Microsoft Jet 데이터베이스 버전 3.0을 사용하는 데이터베이스가 만들어집니다.

> [!CAUTION]
> 데이터베이스가 암호화되지 않은 경우 사용자/암호 보안을 구현하더라도 데이터베이스를 구성하는 바이너리 디스크 파일을 직접 읽을 수 있습니다.

### <a name="remarks"></a>설명

`Create`데이터베이스 파일과 기본 DAO 데이터베이스 개체를 만들고 C++ 개체를 초기화합니다. 개체가 연결된 작업 영역의 데이터베이스 컬렉션에 추가됩니다. 데이터베이스 개체가 열린 상태입니다. 후 `Open*` `Create`호출하지 마십시오.

> [!NOTE]
> 을 `Create`사용하면 Microsoft Jet만 만들 수 있습니다( MDB) 데이터베이스. ISAM 데이터베이스 또는 ODBC 데이터베이스는 만들 수 없습니다.

## <a name="cdaodatabasecreaterelation"></a><a name="createrelation"></a>CDao데이터베이스::만들기관계

이 멤버 함수를 호출하여 데이터베이스의 기본 테이블에 있는 하나 이상의 필드와 외래 테이블(데이터베이스의 다른 테이블)의 하나 이상의 필드 간의 관계를 설정합니다.

```cpp
void CreateRelation(
    LPCTSTR lpszName,
    LPCTSTR lpszTable,
    LPCTSTR lpszForeignTable,
    long lAttributes,
    LPCTSTR lpszField,
    LPCTSTR lpszForeignField);

void CreateRelation(CDaoRelationInfo& relinfo);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
관계 체 객체의 고유한 이름입니다. 이름은 문자로 시작해야 하며 최대 40자를 포함할 수 있습니다. 숫자와 밑줄 문자를 포함할 수 있지만 문장 부호 나 공백을 포함 할 수는 없습니다.

*lpszTable*<br/>
관계에서 기본 테이블의 이름입니다. 테이블이 없는 경우 MFC는 [CDaoException](../../mfc/reference/cdaoexception-class.md)형식의 예외를 throw합니다.

*lpszForeignTable*<br/>
관계에서 외래 테이블의 이름입니다. 테이블이 없는 경우 MFC는 형식의 `CDaoException`예외를 throw합니다.

*lAttributes*<br/>
관계 유형에 대한 정보가 포함된 긴 값입니다. 이 값을 사용하여 참조 무결성을 적용할 수 있습니다. 비트-OR 연산자(&#124;)를 사용하여 다음 값 중 어느 값을 결합할 수 있습니다(조합이 의미가 있는 한). ** **

- `dbRelationUnique`관계는 일대일입니다.

- `dbRelationDontEnforce`관계가 적용되지 않습니다(참조 무결성 없음).

- `dbRelationInherited`관계는 연결된 두 테이블을 포함하는 비최신 데이터베이스에 있습니다.

- `dbRelationUpdateCascade`업데이트가 계단식으로 표시됩니다(계단식에 대한 자세한 내용은 비고참조).

- `dbRelationDeleteCascade`삭제는 계단식으로 배열됩니다.

*lpszField*<br/>
기본 테이블의 필드 이름을 포함하는 null-terminated 문자열에 대한 *포인터입니다(lpszTable).*

*lpszForeignField*<br/>
외래 테이블의 필드 이름을 포함하는 null-terminated 문자열에 대한 *포인터입니다(lpszForeignTable).*

*relinfo*<br/>
만들려는 관계에 대한 정보가 포함된 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

관계에는 외부 데이터베이스의 쿼리 또는 연결된 테이블이 포함될 수 없습니다.

관계에 두 테이블 각각에 하나의 필드가 포함된 경우 함수의 첫 번째 버전을 사용합니다. 관계에 여러 필드가 포함된 경우 두 번째 버전을 사용합니다. 관계말의 최대 필드 수는 14개입니다.

이 작업은 기본 DAO 관계 개체를 생성하지만 MFC의 관계 객체 캡슐화는 클래스 `CDaoDatabase`내에 포함되어 있기 때문에 MFC 구현 세부 정보입니다. MFC는 관계에 대한 클래스를 제공하지 않습니다.

계단식 작업을 활성화하도록 관계 개체의 특성을 설정하면 데이터베이스 엔진은 관련 기본 키 테이블을 변경할 때 하나 이상의 다른 테이블에서 레코드를 자동으로 업데이트하거나 삭제합니다.

예를 들어 Customers 테이블과 Orders 테이블 간에 계단식 삭제 관계를 설정한다고 가정합니다. Customers 테이블에서 레코드를 삭제하면 해당 고객과 관련된 Orders 테이블의 레코드도 삭제됩니다. 또한 Orders 테이블과 다른 테이블 간의 계단식 삭제 관계를 설정하면 Customers 테이블에서 레코드를 삭제하면 해당 테이블의 레코드가 자동으로 삭제됩니다.

관련 정보는 DAO 도움말의 "관계 메서드 만들기" 항목을 참조하십시오.

## <a name="cdaodatabasedeletequerydef"></a><a name="deletequerydef"></a>CDao데이터베이스::DeleteQueryDef

이 멤버 함수를 호출하여 `CDaoDatabase` 개체의 QueryDefs 컬렉션에서 지정된 쿼리def(저장된 쿼리)를 삭제합니다.

```cpp
void DeleteQueryDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
삭제할 저장된 쿼리의 이름입니다.

### <a name="remarks"></a>설명

이후에 해당 쿼리는 더 이상 데이터베이스에 정의되지 않습니다.

쿼리 def 개체를 만드는 방법에 대한 자세한 내용은 [클래스 CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)를 참조하십시오. querydef 개체는 `CDaoDatabase` `CDaoQueryDef` 개체를 생성할 때 특정 개체와 연결되어 데이터베이스 개체에 대한 포인터를 전달합니다.

## <a name="cdaodatabasedeleterelation"></a><a name="deleterelation"></a>CDao데이터베이스::DeleteRelation

이 멤버 함수를 호출하여 데이터베이스 개체의 관계 컬렉션에서 기존 관계를 삭제합니다.

```cpp
void DeleteRelation(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
삭제할 관계의 이름입니다.

### <a name="remarks"></a>설명

이후에 관계가 더 이상 존재하지 않습니다.

관련 정보는 DAO 도움말의 "방법 삭제" 항목을 참조하십시오.

## <a name="cdaodatabasedeletetabledef"></a><a name="deletetabledef"></a>CDao데이터베이스::DeleteTableDef

이 멤버 함수를 호출하여 지정된 테이블과 `CDaoDatabase` 개체의 TableDefs 컬렉션에서 모든 데이터를 삭제합니다.

```cpp
void DeleteTableDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
삭제할 tabledef의 이름입니다.

### <a name="remarks"></a>설명

이후에 해당 테이블은 더 이상 데이터베이스에 정의되지 않습니다.

> [!NOTE]
> 시스템 테이블을 삭제하지 않도록 주의하십시오.

tabledef 개체를 만드는 방법에 대한 자세한 내용은 [클래스 CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)를 참조하십시오. tabledef 개체를 생성할 `CDaoDatabase` `CDaoTableDef` 때 특정 개체와 연결 되어 데이터베이스 개체에 대 한 포인터를 전달 합니다.

관련 정보는 DAO 도움말의 "방법 삭제" 항목을 참조하십시오.

## <a name="cdaodatabaseexecute"></a><a name="execute"></a>CDao데이터베이스::실행

이 멤버 함수를 호출하여 작업 쿼리를 실행하거나 데이터베이스에서 SQL 문을 실행합니다.

```cpp
void Execute(
    LPCTSTR lpszSQL,
    int nOptions = dbFailOnError);
```

### <a name="parameters"></a>매개 변수

*lpszSQL*<br/>
실행할 유효한 SQL 명령을 포함하는 null-종단 문자열에 대한 포인터입니다.

*nOptions*<br/>
쿼리의 무결성과 관련된 옵션을 지정하는 정수입니다. bitwise-OR 연산자 **(&#124;)를 **사용하여 다음 상수 중 어느 것과도 결합 할 수 `dbInconsistent` 있습니다 `dbConsistent`(조합이 의미가 있는 경우 ) :

- `dbDenyWrite`다른 사용자에게 쓰기 권한을 거부합니다.

- `dbInconsistent`(기본값) 일관되지 않은 업데이트.

- `dbConsistent`일관된 업데이트.

- `dbSQLPassThrough`SQL 통과. SQL 문을 처리를 위해 ODBC 데이터 원본에 전달합니다.

- `dbFailOnError`오류가 발생하면 업데이트를 롤백합니다.

- `dbSeeChanges`다른 사용자가 편집중인 데이터를 변경하는 경우 런타임 오류를 생성합니다.

> [!NOTE]
> 둘 `dbInconsistent` 다 `dbConsistent` 포함되거나 둘 다 포함되지 않으면 결과가 기본값입니다. 이러한 상수에 대한 설명은 DAO 도움말의 "방법 실행" 항목을 참조하십시오.

### <a name="remarks"></a>설명

`Execute`결과를 반환하지 않는 작업 쿼리 또는 SQL 통과 쿼리에 대해서만 작동합니다. 레코드를 반환하는 일부 쿼리에는 작동하지 않습니다.

작업 쿼리에 대한 정의 및 정보는 DAO 도움말의 "작업 쿼리" 및 "방법 실행" 항목을 참조하십시오.

> [!TIP]
> 구문적으로 올바른 SQL 문과 적절한 사용 `Execute` 권한이 주어지면 단일 행을 수정하거나 삭제할 수 없는 경우에도 멤버 함수가 실패하지 않습니다. 따라서 멤버 함수를 `dbFailOnError` `Execute` 사용하여 업데이트를 실행하거나 쿼리를 삭제할 때항상 이 옵션을 사용합니다. 이 옵션을 사용하면 MFC가 [CDaoException](../../mfc/reference/cdaoexception-class.md) 형식의 예외를 throw하고 영향을 받는 레코드가 잠겨 있고 업데이트하거나 삭제할 수 없는 경우 성공한 모든 변경 내용을 롤백합니다. 항상 호출하여 `GetRecordsAffected` 영향을 받은 레코드 수를 확인할 수 있습니다.

데이터베이스 개체의 [GetRecords영향](#getrecordsaffected) 멤버 함수를 호출하여 가장 최근 `Execute` 호출의 영향을 받는 레코드 수를 확인합니다. 예를 들어 `GetRecordsAffected` 작업 쿼리를 실행할 때 삭제, 업데이트 또는 삽입된 레코드 수에 대한 정보를 반환합니다. 반환된 개수는 계단식 업데이트 또는 삭제가 적용되는 경우 관련 테이블의 변경 내용을 반영하지 않습니다.

`Execute`레코드 집합을 반환하지 않습니다. 레코드를 선택하는 쿼리에서 사용하면 `Execute` MFC가 형식의 `CDaoException`예외를 throw합니다. `ExecuteSQL` `CDatabase::ExecuteSQL`

## <a name="cdaodatabasegetconnect"></a><a name="getconnect"></a>CDao데이터베이스::GetConnect

이 멤버 함수를 호출하여 개체를 `CDaoDatabase` ODBC 또는 ISAM 데이터베이스에 연결하는 데 사용되는 연결 문자열을 검색합니다.

```
CString GetConnect();
```

### <a name="return-value"></a>Return Value

OPEN이 [Open](#open) ODBC 데이터 원본에서 성공적으로 호출된 경우 연결 문자열; 그렇지 않으면 빈 문자열이 됩니다. 마이크로소프트 제트 (. MDB) 데이터베이스에서 [Execute](#execute) 멤버 함수와 함께 사용하거나 `dbSQLPassThrough` 레코드 집합을 여는 데 사용되는 옵션으로 설정하지 않으면 문자열이 항상 비어 있습니다.

### <a name="remarks"></a>설명

문자열은 열린 데이터베이스의 원본 또는 통과 쿼리에 사용되는 데이터베이스에 대한 정보를 제공합니다. 연결 문자열은 세미콜론으로 구분된 데이터베이스 형식 지정기와 0개 이상의 매개변수로 구성됩니다.

> [!NOTE]
> MFC DAO 클래스를 사용하여 ODBC를 통해 데이터 원본에 연결하는 것은 연결된 테이블을 통해 연결하는 것보다 효율이 낮습니다.

> [!NOTE]
> 연결 문자열은 필요에 따라 ODBC 및 특정 ISAM 드라이버에 추가 정보를 전달하는 데 사용됩니다. 에 사용되지 않습니다. MDB 데이터베이스. Microsoft Jet 데이터베이스 기본 테이블의 경우 연결 문자열은 위의 반환 값 아래에 설명된 SQL 통과 쿼리에 사용할 경우를 제외하고 빈 문자열("")입니다.

연결 문자열이 생성되는 방법에 대한 설명은 [Open](#open) 멤버 함수를 참조하십시오. `Open` 연결 문자열이 호출에서 설정되면 나중에 이 문자열을 사용하여 설정을 확인하여 데이터베이스의 유형, 경로, 사용자 ID, 암호 또는 ODBC 데이터 원본을 확인할 수 있습니다.

## <a name="cdaodatabasegetname"></a><a name="getname"></a>CDao데이터베이스::GetName

이 멤버 함수를 호출하여 현재 열려 있는 데이터베이스의 이름(기존 데이터베이스 파일의 이름 또는 등록된 ODBC 데이터 원본의 이름)을 검색합니다.

```
CString GetName();
```

### <a name="return-value"></a>Return Value

성공하면 데이터베이스의 전체 경로 및 파일 이름입니다. 그렇지 않으면 빈 [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>설명

네트워크가 UNC(통일 명명 규칙)를 지원하는 경우 네트워크 경로(예:\\\\\\"mySERVER\\\MYSHARE\\\MYDIR \MYDB)를\\지정할 수도 있습니다. MDB". ("C++ 이스케이프 문자이기 때문에\\문자열 리터럴에서 이중 백슬래시가 필요합니다.)

예를 들어 이 이름을 제목에 표시하려고 할 수 있습니다. 이름을 검색하는 동안 오류가 발생하면 MFC는 [CDaoException](../../mfc/reference/cdaoexception-class.md)형식의 예외를 throw합니다.

> [!NOTE]
> 외부 데이터베이스에 액세스할 때 성능을 향상하려면 외부 데이터베이스 테이블을 Microsoft Jet 데이터베이스에 연결하는 것이 좋습니다. 데이터 원본에 직접 연결하는 것이 아니라 MDB)를 사용합니다.

데이터베이스 유형은 경로가 가리키는 파일 또는 디렉터리로 다음과 같이 표시됩니다.

|경로 이름을 가리킵니다.|데이터베이스 유형|
|--------------------------|-------------------|
|. MDB 파일|마이크로 소프트 제트 데이터베이스 (마이크로 소프트 액세스)|
|를 포함하는 디렉토리 . DBF 파일|dBASE 데이터베이스|
|를 포함하는 디렉토리 . XLS 파일|마이크로 소프트 엑셀 데이터베이스|
|를 포함하는 디렉토리 . PDX 파일|역설 데이터베이스|
|적절하게 서식이 지정된 텍스트 데이터베이스 파일이 포함된 디렉터리|텍스트 형식 데이터베이스|

SQL Server 및 Oracle과 같은 ODBC 데이터베이스의 경우 데이터베이스의 연결 문자열은 ODBC에 의해 등록된 DSN(데이터 원본 이름)을 식별합니다.

## <a name="cdaodatabasegetquerydefcount"></a><a name="getquerydefcount"></a>CDao데이터베이스::GetQueryDefcount

이 멤버 함수를 호출하여 데이터베이스의 QueryDefs 컬렉션에 정의된 쿼리 수를 검색합니다.

```
short GetQueryDefCount();
```

### <a name="return-value"></a>Return Value

데이터베이스에 정의된 쿼리 수입니다.

### <a name="remarks"></a>설명

`GetQueryDefCount`는 QueryDefs 컬렉션의 모든 쿼리 defs를 반복해야 하는 경우에 유용합니다. 컬렉션에서 지정된 쿼리에 대한 정보를 얻으려면 [GetQueryDefInfo](#getquerydefinfo)를 참조하십시오.

## <a name="cdaodatabasegetquerydefinfo"></a><a name="getquerydefinfo"></a>CDao데이터베이스::GetQueryDefInfo

이 멤버 함수를 호출하여 데이터베이스에 정의된 쿼리에 대한 다양한 종류의 정보를 가져옵니다.

```cpp
void GetQueryDefInfo(
    int nIndex,
    CDaoQueryDefInfo& querydefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetQueryDefInfo(
    LPCTSTR lpszName,
    CDaoQueryDefInfo& querydefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스별 조회를 위해 데이터베이스의 QueryDefs 컬렉션에서 미리 정의된 쿼리의 인덱스입니다.

*querydefinfo*<br/>
요청된 정보를 반환하는 [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) 개체에 대한 참조입니다.

*dwInfoOptions*<br/>
검색할 레코드 집합에 대한 정보를 지정하는 옵션입니다. 사용 가능한 옵션은 함수가 레코드 집합에 대해 반환하는 원인과 함께 여기에 나열됩니다.

- AFX_DAO_PRIMARY_INFO(기본값) 이름, 유형

- AFX_DAO_SECONDARY_INFO 기본 정보 플러스: 만든 날짜, 마지막 업데이트 날짜, 레코드 반환, 업데이터블

- AFX_DAO_ALL_INFO 기본 및 보조 정보 플러스: SQL, 연결, ODBC타임아웃

*lpszName*<br/>
이름으로 조회하기 위해 데이터베이스에 정의된 쿼리 이름을 포함하는 문자열입니다.

### <a name="remarks"></a>설명

데이터베이스의 QueryDefs 컬렉션의 인덱스 또는 쿼리 이름으로 쿼리를 선택할 수 있도록 함수의 두 버전이 제공됩니다.

*querydefinfo에서*반환된 정보에 대한 설명은 [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) 구조를 참조하십시오. 이 구조에는 *dwInfoOptions*에 대한 설명에 위에 나열된 정보 항목에 해당하는 멤버가 있습니다. 한 수준의 정보를 요청하는 경우 이전 수준의 정보도 얻을 수 있습니다.

## <a name="cdaodatabasegetquerytimeout"></a><a name="getquerytimeout"></a>CDao데이터베이스::GetQuery시간 아웃

연결된 데이터베이스의 후속 작업이 시간 만료되기 전에 허용할 현재 시간(초)을 검색하려면 이 멤버 함수를 호출합니다.

```
short GetQueryTimeout();
```

### <a name="return-value"></a>Return Value

시간 시간 값(초)을 포함하는 짧은 정수입니다.

### <a name="remarks"></a>설명

네트워크 액세스 문제, 과도한 쿼리 처리 시간 등으로 인해 작업이 시간 중지될 수 있습니다. 설정이 적용되는 동안이 `CDaoDatabase` 개체와 연결된 모든 레코드 집합에 열려 있는 모든 새 작업, 업데이트 및 삭제 작업에 영향을 줍니다. [SetQueryTimeout을](#setquerytimeout)호출하여 현재 시간 시간 설정을 변경할 수 있습니다. 개봉 후 레코드 집합에 대한 쿼리 시간 시간 값을 변경해도 레코드 집합의 값은 변경되지 않습니다. 예를 들어 후속 [Move](../../mfc/reference/cdaorecordset-class.md#move) 작업은 새 값을 사용하지 않습니다. 기본값은 데이터베이스 엔진이 초기화될 때 처음에 설정됩니다.

쿼리 시간 시간에 대한 기본값은 Windows 레지스트리에서 가져옵니다. 레지스트리 설정이 없는 경우 기본값은 60초입니다. 모든 데이터베이스가 쿼리 시간 시간 값을 설정하는 기능을 지원하지는 않습니다. 쿼리 시간 지정 값을 0으로 설정하면 시간 지정이 발생하지 않습니다. 데이터베이스와의 통신이 응답하지 않을 수 있습니다. 이 동작은 개발 중에 유용할 수 있습니다. 호출이 실패하면 MFC는 [CDaoException](../../mfc/reference/cdaoexception-class.md)형식의 예외를 throw합니다.

관련 정보는 DAO 도움말의 "쿼리 시간 삭제 속성" 항목을 참조하십시오.

## <a name="cdaodatabasegetrecordsaffected"></a><a name="getrecordsaffected"></a>CDao데이터베이스::겟레코드영향

이 멤버 함수를 호출하여 [Execute](#execute) 멤버 함수의 가장 최근 호출에 의해 영향을 받는 레코드 수를 확인합니다.

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Return Value

영향을 받는 레코드 수를 포함하는 긴 정수입니다.

### <a name="remarks"></a>설명

반환된 값에는 을 실행하는 `Execute`작업 쿼리에서 삭제, 업데이트 또는 삽입한 레코드 수가 포함됩니다. 반환된 개수는 계단식 업데이트 또는 삭제가 적용되는 경우 관련 테이블의 변경 내용을 반영하지 않습니다.

관련 정보는 DAO 도움말의 "레코드 영향을 받는 속성" 항목을 참조하십시오.

## <a name="cdaodatabasegetrelationcount"></a><a name="getrelationcount"></a>CDao데이터베이스::관계 관계 카운트

이 멤버 함수를 호출하여 데이터베이스의 테이블 간에 정의된 관계 수를 가져옵니다.

```
short GetRelationCount();
```

### <a name="return-value"></a>Return Value

데이터베이스의 테이블 간에 정의된 관계수입니다.

### <a name="remarks"></a>설명

`GetRelationCount`는 데이터베이스의 관계 컬렉션에서 정의된 모든 관계를 반복해야 하는 경우에 유용합니다. 컬렉션에서 지정된 관계에 대한 정보를 얻으려면 [GetRelationInfo](#getrelationinfo)를 참조하십시오.

관계의 개념을 설명하기 위해 일대다 관계가 있을 수 있는 공급자 테이블과 제품 테이블을 고려합니다. 이 관계에서 한 공급업체는 두 개 이상의 제품을 공급할 수 있습니다. 다른 관계는 일대일 및 다대다입니다.

## <a name="cdaodatabasegetrelationinfo"></a><a name="getrelationinfo"></a>CDao데이터베이스::관계정보

데이터베이스의 관계 컬렉션에서 지정된 관계에 대한 정보를 가져오려면 이 멤버 함수를 호출합니다.

```cpp
void GetRelationInfo(
    int nIndex,
    CDaoRelationInfo& relinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetRelationInfo(
    LPCTSTR lpszName,
    CDaoRelationInfo& relinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스별 조회를 위한 데이터베이스의 관계 컬렉션의 관계 개체 인덱스입니다.

*relinfo*<br/>
요청한 정보를 반환하는 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 개체에 대한 참조입니다.

*dwInfoOptions*<br/>
검색할 관계에 대한 정보를 지정하는 옵션입니다. 사용 가능한 옵션은 함수가 관계에 대해 반환하는 원인과 함께 여기에 나열됩니다.

- AFX_DAO_PRIMARY_INFO(기본값) 이름, 표, 외래 테이블

- AFX_DAO_SECONDARY_INFO 특성, 필드 정보

필드 정보는 관계에 관련된 기본 테이블의 필드를 포함하는 [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) 개체입니다.

*lpszName*<br/>
이름으로 조회하기 위해 관계 개체의 이름을 포함하는 문자열입니다.

### <a name="remarks"></a>설명

이 함수의 두 버전은 인덱스 또는 이름으로 액세스를 제공합니다. *relinfo에서*반환된 정보에 대한 설명은 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 구조를 참조하십시오. 이 구조에는 *dwInfoOptions*에 대한 설명에 위에 나열된 정보 항목에 해당하는 멤버가 있습니다. 한 수준에서 정보를 요청하는 경우 이전 수준에서도 정보를 얻을 수 있습니다.

> [!NOTE]
> 관계 객체의 특성을 설정하여 캐스케이드 작업(또는)을`dbRelationUpdateCascades` `dbRelationDeleteCascades`활성화하는 경우 Microsoft Jet 데이터베이스 엔진은 관련 기본 키 테이블을 변경할 때 하나 이상의 다른 테이블에서 레코드를 자동으로 업데이트하거나 삭제합니다. 예를 들어 Customers 테이블과 Orders 테이블 간에 계단식 삭제 관계를 설정한다고 가정합니다. Customers 테이블에서 레코드를 삭제하면 해당 고객과 관련된 Orders 테이블의 레코드도 삭제됩니다. 또한 Orders 테이블과 다른 테이블 간의 계단식 삭제 관계를 설정하면 Customers 테이블에서 레코드를 삭제하면 해당 테이블의 레코드가 자동으로 삭제됩니다.

## <a name="cdaodatabasegettabledefcount"></a><a name="gettabledefcount"></a>CDao데이터베이스::GettableDefCount

이 멤버 함수를 호출하여 데이터베이스에 정의된 테이블 수를 검색합니다.

```
short GetTableDefCount();
```

### <a name="return-value"></a>Return Value

데이터베이스에 정의된 테이블defs 수입니다.

### <a name="remarks"></a>설명

`GetTableDefCount`데이터베이스의 TableDefs 컬렉션의 모든 테이블defs를 반복해야 하는 경우에 유용합니다. 컬렉션에서 지정된 테이블에 대한 정보를 얻으려면 [GetTableDefInfo](#gettabledefinfo)를 참조하십시오.

## <a name="cdaodatabasegettabledefinfo"></a><a name="gettabledefinfo"></a>CDao데이터베이스::GettableDefInfo

이 멤버 함수를 호출하여 데이터베이스에 정의된 테이블에 대한 다양한 종류의 정보를 가져옵니다.

```cpp
void GetTableDefInfo(
    int nIndex,
    CDaoTableDefInfo& tabledefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetTableDefInfo(
    LPCTSTR lpszName,
    CDaoTableDefInfo& tabledefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스별 조회를 위해 데이터베이스의 TableDefs 컬렉션에 있는 tabledef 개체의 인덱스입니다.

*tabledefinfo*<br/>
요청한 정보를 반환하는 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) 개체에 대한 참조입니다.

*dwInfoOptions*<br/>
검색할 테이블에 대한 정보를 지정하는 옵션입니다. 사용 가능한 옵션은 함수가 관계에 대해 반환하는 원인과 함께 여기에 나열됩니다.

- AFX_DAO_PRIMARY_INFO(기본값) 이름, 업데이터 블, 속성

- AFX_DAO_SECONDARY_INFO 기본 정보 더하기: 생성된 날짜, 마지막으로 업데이트된 날짜, 원본 테이블 이름, 연결

- AFX_DAO_ALL_INFO 기본 및 보조 정보 플러스: 유효성 검사 규칙, 유효성 검사 텍스트, 레코드 수

*lpszName*<br/>
이름으로 조회할 테이블def 개체의 이름입니다.

### <a name="remarks"></a>설명

두 가지 버전의 함수가 제공되므로 데이터베이스의 TableDefs 컬렉션의 인덱스 또는 테이블 이름으로 테이블을 선택할 수 있습니다.

*tabledefinfo에서*반환되는 정보에 대한 설명은 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) 구조를 참조하십시오. 이 구조에는 *dwInfoOptions*에 대한 설명에 위에 나열된 정보 항목에 해당하는 멤버가 있습니다. 한 수준에서 정보를 요청하는 경우 이전 수준에 대한 정보도 얻을 수 있습니다.

> [!NOTE]
> AFX_DAO_ALL_INFO 옵션은 가져오는 속도가 느려질 수 있는 정보를 제공합니다. 이 경우 레코드가 많은 경우 테이블의 레코드를 계산하는 데 시간이 많이 걸릴 수 있습니다.

## <a name="cdaodatabasegetversion"></a><a name="getversion"></a>CDao데이터베이스::GetVersion

이 멤버 함수를 호출하여 Microsoft Jet 데이터베이스 파일의 버전을 확인합니다.

```
CString GetVersion();
```

### <a name="return-value"></a>Return Value

개체와 연결된 데이터베이스 파일의 버전을 나타내는 [CString입니다.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>설명

반환된 값은 "major.minor" 형식의 버전 번호를 나타냅니다. 예를 들어 "3.0"입니다. 제품 버전 번호(예: 3.0)는 버전 번호(3), 마침표 및 릴리스 번호(0)로 구성됩니다. 현재까지의 버전은 1.0, 1.1, 2.0 및 3.0입니다.

관련 정보는 DAO 도움말의 "버전 속성" 항목을 참조하십시오.

## <a name="cdaodatabaseisopen"></a><a name="isopen"></a>CDao데이터베이스::이열기

이 멤버 함수를 호출하여 개체가 `CDaoDatabase` 현재 데이터베이스에서 열려 있는지 확인합니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Return Value

개체가 현재 `CDaoDatabase` 열려 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

## <a name="cdaodatabasem_pdaodatabase"></a><a name="m_pdaodatabase"></a>CDao데이터베이스::m_pDAODatabase

개체의 기본을 기본으로 하는 DAO 데이터베이스 `CDaoDatabase` 개체에 대 한 OLE 인터페이스에 대 한 포인터를 포함 합니다.

### <a name="remarks"></a>설명

DAO 인터페이스에 직접 액세스해야 하는 경우 이 포인터를 사용합니다.

DAO에 직접 전화하는 것에 대한 자세한 내용은 [기술 참고 54를](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)참조하십시오.

## <a name="cdaodatabasem_pworkspace"></a><a name="m_pworkspace"></a>CDao데이터베이스:m_pWorkspace

데이터베이스 개체를 포함하는 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체에 대한 포인터를 포함합니다.

### <a name="remarks"></a>설명

작업 영역에 직접 액세스해야 하는 경우(예: 작업 영역의 데이터베이스 컬렉션의 다른 데이터베이스 개체에 대한 포인터를 가져오는 경우)를 사용하여 이 포인터를 사용합니다.

## <a name="cdaodatabaseopen"></a><a name="open"></a>CDao데이터베이스::열기

기존 데이터베이스를 나타내는 새로 생성된 `CDaoDatabase` 개체를 초기화하려면 이 멤버 함수를 호출해야 합니다.

```
virtual void Open(
    LPCTSTR lpszName,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T(""));
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
기존 Microsoft Jet의 이름인 문자열 식입니다. MDB) 데이터베이스 파일입니다. 파일 이름에 확장이 있는 경우 확장이 필요합니다. 네트워크가 UNC(통일 명명 규칙)를 지원하는\\\\\\경우\\"\MYSERVER \MYSHARE\\\MYDIR\\\MYDB"와 같은 네트워크 경로를 지정할 수도 있습니다. MDB". ("C++ 이스케이프 문자이기 때문에\\문자열 리터럴에서 이중 백슬래시가 필요합니다.)

*lpszName을*사용할 때 몇 가지 고려 사항이 적용됩니다. 이 경우:

- 다른 사용자가 단독 액세스하기 위해 이미 열려 있는 데이터베이스를 참조하면 MFC는 [CDaoException](../../mfc/reference/cdaoexception-class.md)형식의 예외를 throw합니다. 사용자에게 데이터베이스를 사용할 수 없음을 알리기 위해 해당 예외를 트랩합니다.

- 빈 문자열(""")"이고 *lpszConnect는* "ODBC;"이며, 등록된 모든 ODBC 데이터 원본 이름을 나열하는 대화 상자가 표시되므로 사용자가 데이터베이스를 선택할 수 있습니다. ODBC 데이터 원본에 대한 직접 연결을 피해야 합니다. 대신 연결된 테이블을 사용합니다.

- 그렇지 않으면 기존 데이터베이스 또는 유효한 ODBC 데이터 원본 이름을 참조하지 `CDaoException`않으므로 MFC는 형식의 예외를 throw합니다.

> [!NOTE]
> DAO 오류 코드에 대한 자세한 내용은 DAOERR을 참조하십시오. H 파일. 관련 정보는 DAO 도움말의 "트래핑 가능한 데이터 액세스 오류" 항목을 참조하십시오.

*bExclusive*<br/>
데이터베이스를 단독(비공유) 액세스를 위해 열어야 하는 경우 TRUE인 부울 값이고 공유 액세스를 위해 데이터베이스를 열어야 하는 경우 FALSE입니다. 이 인수를 생략하면 공유 액세스를 위해 데이터베이스가 열립니다.

*bReadOnly*<br/>
읽기 전용 액세스를 위해 데이터베이스를 열어야 하는 경우 TRUE인 부울 값이고 읽기/쓰기 액세스를 위해 데이터베이스를 열어야 하는 경우 FALSE입니다. 이 인수를 생략하면 읽기/쓰기 액세스를 위해 데이터베이스가 열립니다. 모든 종속 레코드 집합은 이 특성을 상속합니다.

*lpszConnect*<br/>
데이터베이스를 여는 데 사용되는 문자열 식입니다. 이 문자열은 ODBC 연결 인수를 구성합니다. 원본 문자열을 제공하려면 단독 및 읽기 전용 인수를 제공해야 합니다. 데이터베이스가 Microsoft Jet 데이터베이스인 경우(. MDB), 이 문자열은 비어 있습니다(""). 기본값(_T("")"에 대한 구문은 응용 프로그램의 ANSI 빌드뿐만 아니라 유니코드에 대한 이식성을 제공합니다. **_T**

### <a name="remarks"></a>설명

`Open`데이터베이스를 기본 DAO 개체와 연결합니다. 데이터베이스 개체를 사용하여 레코드 집합, tabledef 또는 querydef 개체를 초기화할 때까지 생성할 수 없습니다. `Open`은 데이터베이스 개체를 연결된 작업 영역의 데이터베이스 컬렉션에 포함시다.

다음과 같이 매개 변수를 사용합니다.

- 마이크로소프트 제트를 여는 경우(. MDB) 데이터베이스, *lpszName* 매개 변수를 사용하고 *lpszConnect* 매개 변수에 대한 빈 문자열을 전달하거나 양식의 암호 문자열을 전달 "; 데이터베이스가 암호로 보호된 경우 PWD=암호" (. MDB 데이터베이스만).

- ODBC 데이터 원본을 여는 경우 *lpszConnect에서* 유효한 ODBC 연결 문자열을 전달하고 *lpszName의*빈 문자열을 전달합니다.

관련 정보는 DAO 도움말의 "OpenDatabase 방법" 항목을 참조하십시오.

> [!NOTE]
> ISAM 데이터베이스 및 ODBC 데이터 원본을 비롯한 외부 데이터베이스에 액세스할 때 성능을 향상하려면 외부 데이터베이스 테이블을 Microsoft Jet 엔진 데이터베이스에 연결하는 것이 좋습니다. 데이터 원본에 직접 연결하는 것이 아니라 MDB)를 사용합니다.

예를 들어 DBMS 호스트를 사용할 수 없는 경우 연결 시도가 시간 지정될 수 있습니다. 연결 시도가 실패하면 `Open` [CDaoException](../../mfc/reference/cdaoexception-class.md)형식의 예외를 throw합니다.

나머지 설명은 ODBC 데이터베이스에만 적용됩니다.

데이터베이스가 ODBC 데이터베이스이고 `Open` 호출의 매개 변수에 연결을 만들기에 충분한 정보가 없는 경우 ODBC 드라이버는 사용자로부터 필요한 정보를 얻기 위해 대화 상자를 엽니다. 호출할 `Open`때 연결 문자열 *lpszConnect는*비공개로 저장되며 [GetConnect](#getconnect) 멤버 함수를 호출하여 사용할 수 있습니다.

원하는 경우 호출하기 `Open` 전에 자신의 대화 상자를 열어 암호와 같은 사용자 정보를 얻은 다음 해당 정보를 에 전달하는 `Open`연결 문자열에 추가할 수 있습니다. 또는 다음에 응용 프로그램에서 `Open` `CDaoDatabase` 개체를 호출할 때 다시 사용할 수 있도록 전달하는 연결 문자열(Windows 레지스트리에)을 저장할 수 있습니다.

또한 여러 수준의 로그인 권한 부여(각 개체에 대해) `CDaoDatabase` 연결 문자열을 사용하거나 다른 데이터베이스 별 정보를 전달할 수도 있습니다.

## <a name="cdaodatabasesetquerytimeout"></a><a name="setquerytimeout"></a>CDao데이터베이스::SetQuery시간 설정

연결된 데이터베이스시간 초과에 대한 후속 작업 전에 허용하도록 기본 초 수를 재정의하려면 이 멤버 함수를 호출합니다.

```cpp
void SetQueryTimeout(short nSeconds);
```

### <a name="parameters"></a>매개 변수

*nSeconds*<br/>
쿼리 시도가 시간 배회하기 전에 허용할 수 있는 시간(초)입니다.

### <a name="remarks"></a>설명

네트워크 액세스 문제, 과도한 쿼리 처리 시간 등으로 인해 작업이 시간 중지될 수 있습니다. 쿼리 `SetQueryTimeout` 시간 지정 값을 변경하려는 경우 레코드 집합을 열기 전에 또는 레코드 집합의 [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew), [업데이트](../../mfc/reference/cdaorecordset-class.md#update)또는 [멤버 삭제](../../mfc/reference/cdaorecordset-class.md#delete) 함수를 호출하기 전에 호출합니다. 이 설정은 이후의 `Update`모든 `Delete` Open 에 `AddNew`영향을 [미치며](../../mfc/reference/cdaorecordset-class.md#open)이 개체와 연결된 모든 레코드 집합에 대한 호출에 `CDaoDatabase` 영향을 줍니다. 개봉 후 레코드 집합에 대한 쿼리 시간 시간 값을 변경해도 레코드 집합의 값은 변경되지 않습니다. 예를 들어 후속 [Move](../../mfc/reference/cdaorecordset-class.md#move) 작업은 새 값을 사용하지 않습니다.

쿼리 시간 설정의 기본값은 60초입니다. 모든 데이터베이스가 쿼리 시간 시간 값을 설정하는 기능을 지원하지는 않습니다. 쿼리 시간 지정 값을 0으로 설정하면 시간 지정이 발생하지 않습니다. 데이터베이스와의 통신이 응답하지 않을 수 있습니다. 이 동작은 개발 중에 유용할 수 있습니다.

관련 정보는 DAO 도움말의 "쿼리 시간 삭제 속성" 항목을 참조하십시오.

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDao워크스페이스 클래스](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDao레코드 집합 클래스](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)<br/>
[C데이터베이스 클래스](../../mfc/reference/cdatabase-class.md)<br/>
[CDaoException 클래스](../../mfc/reference/cdaoexception-class.md)
