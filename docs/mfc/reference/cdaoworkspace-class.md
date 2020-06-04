---
title: CDao워크스페이스 클래스
ms.date: 11/04/2016
f1_keywords:
- CDaoWorkspace
- AFXDAO/CDaoWorkspace
- AFXDAO/CDaoWorkspace::CDaoWorkspace
- AFXDAO/CDaoWorkspace::Append
- AFXDAO/CDaoWorkspace::BeginTrans
- AFXDAO/CDaoWorkspace::Close
- AFXDAO/CDaoWorkspace::CommitTrans
- AFXDAO/CDaoWorkspace::CompactDatabase
- AFXDAO/CDaoWorkspace::Create
- AFXDAO/CDaoWorkspace::GetDatabaseCount
- AFXDAO/CDaoWorkspace::GetDatabaseInfo
- AFXDAO/CDaoWorkspace::GetIniPath
- AFXDAO/CDaoWorkspace::GetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::GetLoginTimeout
- AFXDAO/CDaoWorkspace::GetName
- AFXDAO/CDaoWorkspace::GetUserName
- AFXDAO/CDaoWorkspace::GetVersion
- AFXDAO/CDaoWorkspace::GetWorkspaceCount
- AFXDAO/CDaoWorkspace::GetWorkspaceInfo
- AFXDAO/CDaoWorkspace::Idle
- AFXDAO/CDaoWorkspace::IsOpen
- AFXDAO/CDaoWorkspace::Open
- AFXDAO/CDaoWorkspace::RepairDatabase
- AFXDAO/CDaoWorkspace::Rollback
- AFXDAO/CDaoWorkspace::SetDefaultPassword
- AFXDAO/CDaoWorkspace::SetDefaultUser
- AFXDAO/CDaoWorkspace::SetIniPath
- AFXDAO/CDaoWorkspace::SetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::SetLoginTimeout
- AFXDAO/CDaoWorkspace::m_pDAOWorkspace
helpviewer_keywords:
- CDaoWorkspace [MFC], CDaoWorkspace
- CDaoWorkspace [MFC], Append
- CDaoWorkspace [MFC], BeginTrans
- CDaoWorkspace [MFC], Close
- CDaoWorkspace [MFC], CommitTrans
- CDaoWorkspace [MFC], CompactDatabase
- CDaoWorkspace [MFC], Create
- CDaoWorkspace [MFC], GetDatabaseCount
- CDaoWorkspace [MFC], GetDatabaseInfo
- CDaoWorkspace [MFC], GetIniPath
- CDaoWorkspace [MFC], GetIsolateODBCTrans
- CDaoWorkspace [MFC], GetLoginTimeout
- CDaoWorkspace [MFC], GetName
- CDaoWorkspace [MFC], GetUserName
- CDaoWorkspace [MFC], GetVersion
- CDaoWorkspace [MFC], GetWorkspaceCount
- CDaoWorkspace [MFC], GetWorkspaceInfo
- CDaoWorkspace [MFC], Idle
- CDaoWorkspace [MFC], IsOpen
- CDaoWorkspace [MFC], Open
- CDaoWorkspace [MFC], RepairDatabase
- CDaoWorkspace [MFC], Rollback
- CDaoWorkspace [MFC], SetDefaultPassword
- CDaoWorkspace [MFC], SetDefaultUser
- CDaoWorkspace [MFC], SetIniPath
- CDaoWorkspace [MFC], SetIsolateODBCTrans
- CDaoWorkspace [MFC], SetLoginTimeout
- CDaoWorkspace [MFC], m_pDAOWorkspace
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
ms.openlocfilehash: c492c806d64b1cfe0e4f73b3bb880ec7bd0a7e80
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754671"
---
# <a name="cdaoworkspace-class"></a>CDao워크스페이스 클래스

단일 사용자가 로그인부터 로그인까지 암호로 보호되고 명명된 데이터베이스 세션을 관리합니다. DAO는 Office 2013을 통해 지원됩니다. DAO 3.6은 최종 버전이며 더 이상 사용되지 않는 것으로 간주됩니다.

## <a name="syntax"></a>구문

```
class CDaoWorkspace : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDao워크스페이스::CDao워크스페이스](#cdaoworkspace)|작업 영역 개체를 생성합니다. 그 후, 전화 `Create` 또는 `Open`.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDao워크스페이스::부속](#append)|새로 생성된 작업 영역을 데이터베이스 엔진의 작업 영역 컬렉션에 보겠습니다.|
|[CDaoWorkspace::BeginTrans](#begintrans)|작업 영역에서 열려 있는 모든 데이터베이스에 적용되는 새 트랜잭션을 시작합니다.|
|[CDaoWorkspace::Close](#close)|작업 영역과 작업 영역에 포함된 모든 개체를 닫습니다. 보류 중인 트랜잭션은 롤백됩니다.|
|[CDaoWorkspace::CommitTrans](#committrans)|현재 트랜잭션을 완료 하 고 변경 내용을 저장 합니다.|
|[CDaoWorkspace::CompactDatabase](#compactdatabase)|데이터베이스를 압축(또는 복제)합니다.|
|[CDao워크스페이스::만들기](#create)|새 DAO 작업 영역 개체를 만듭니다.|
|[CDaoWorkspace::GetDatabaseCount](#getdatabasecount)|작업 영역의 데이터베이스 컬렉션에서 DAO 데이터베이스 개체 수를 반환합니다.|
|[CDaoWorkspace::GetDatabaseInfo](#getdatabaseinfo)|작업 영역의 데이터베이스 컬렉션에 정의된 지정된 DAO 데이터베이스에 대한 정보를 반환합니다.|
|[CDao워크스페이스::겟시니패스](#getinipath)|Windows 레지스트리에서 Microsoft Jet 데이터베이스 엔진의 초기화 설정 위치를 반환합니다.|
|[CDao워크스페이스::게아솔레이트ODBCTrans](#getisolateodbctrans)|동일한 ODBC 데이터 원본을 포함하는 여러 트랜잭션이 데이터 원본에 대한 강제 다중 연결을 통해 격리되는지 여부를 나타내는 값을 반환합니다.|
|[CDaoWorkspace::GetLoginTimeout](#getlogintimeout)|사용자가 ODBC 데이터베이스에 로그인하려고 할 때 오류가 발생하기 전의 초(초)를 반환합니다.|
|[CDao워크스페이스::GetName](#getname)|작업 영역 개체에 대한 사용자 정의 이름을 반환합니다.|
|[CDao워크 스페이스::GetUserName](#getusername)|작업 영역을 만들 때 지정된 사용자 이름을 반환합니다. 작업 영역 소유자의 이름입니다.|
|[CDaoWorkspace::GetVersion](#getversion)|작업 영역과 연결된 데이터베이스 엔진 의 버전을 포함하는 문자열을 반환합니다.|
|[CDaoWorkspace::GetWorkspaceCount](#getworkspacecount)|데이터베이스 엔진의 작업 영역 컬렉션에서 DAO 작업 영역 개체 수를 반환합니다.|
|[CDaoWorkspace::GetWorkspaceInfo](#getworkspaceinfo)|데이터베이스 엔진의 작업 영역 컬렉션에 정의된 지정된 DAO 작업 영역에 대한 정보를 반환합니다.|
|[CDaoWorkspace::Idle](#idle)|데이터베이스 엔진이 백그라운드 작업을 수행할 수 있도록 합니다.|
|[CDaoWorkspace::IsOpen](#isopen)|작업 영역이 열려 있으면 0이 아닌 것을 반환합니다.|
|[CDaoWorkspace::Open](#open)|DAO의 기본 작업 영역과 연결된 작업 영역 개체를 명시적으로 엽니다.|
|[CDaoWorkspace::RepairDatabase](#repairdatabase)|손상된 데이터베이스를 복구하려고 시도합니다.|
|[CDao워크스페이스::롤백](#rollback)|현재 트랜잭션을 종료 하 고 변경 내용을 저장 하지 않습니다.|
|[CDaoWorkspace::SetDefaultPassword](#setdefaultpassword)|작업 영역 개체가 특정 암호 없이 만들 때 데이터베이스 엔진에서 사용하는 암호를 설정합니다.|
|[CDaoWorkspace::SetDefaultUser](#setdefaultuser)|데이터베이스 엔진이 특정 사용자 이름 없이 작업 영역 개체를 만들 때 사용하는 사용자 이름을 설정합니다.|
|[CDaoWorkspace::SetIniPath](#setinipath)|Windows 레지스트리에서 Microsoft Jet 데이터베이스 엔진의 초기화 설정 위치를 설정합니다.|
|[CDaoWorkspace::SetIsolateODBCTrans](#setisolateodbctrans)|동일한 ODBC 데이터 원본을 포함하는 여러 트랜잭션이 데이터 원본에 대한 여러 연결을 강제로 격리하는지 여부를 지정합니다.|
|[CDaoWorkspace::SetLoginTimeout](#setlogintimeout)|사용자가 ODBC 데이터 원본에 로그인하려고 할 때 오류가 발생하기 전의 초(초)를 설정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDaoWorkspace::m_pDAOWorkspace](#m_pdaoworkspace)|기본 DAO 작업 영역 개체를 가리킵니다.|

## <a name="remarks"></a>설명

대부분의 경우 여러 작업 영역이 필요하지 않으며 명시적 작업 영역 개체를 만들 필요가 없습니다. 데이터베이스 및 레코드 집합 개체를 열 때 DAO의 기본 작업 영역을 사용합니다. 그러나 필요한 경우 추가 작업 영역 개체를 만들어 한 번에 여러 세션을 실행할 수 있습니다. 각 작업 영역 개체에는 자체 데이터베이스 컬렉션에 열려 있는 여러 데이터베이스 개체가 포함될 수 있습니다. MFC에서 작업 영역은 주로 트랜잭션 관리자로, 모두 동일한 "트랜잭션 공간"에 열려 있는 데이터베이스 집합을 지정합니다.

> [!NOTE]
> DAO 데이터베이스 클래스는 ODBC(개방형 데이터베이스 연결)를 기반으로 하는 MFC 데이터베이스 클래스와 구별됩니다. 모든 DAO 데이터베이스 클래스 이름에는 "CDao" 접두사가 있습니다. 일반적으로 DAO를 기반으로 하는 MFC 클래스는 ODBC를 기반으로 하는 MFC 클래스보다 더 유능합니다. DAO 기반 클래스는 ODBC 드라이버를 포함하여 Microsoft Jet 데이터베이스 엔진을 통해 데이터에 액세스합니다. 또한 DAO를 직접 호출하지 않고도 데이터베이스를 만들고 클래스를 통해 테이블과 필드를 추가하는 것과 같은 DDL(데이터 정의 언어) 작업을 지원합니다.

## <a name="capabilities"></a>기능

클래스는 `CDaoWorkspace` 다음을 제공합니다.

- 필요한 경우 데이터베이스 엔진을 초기화하여 만든 기본 작업 영역에 대한 명시적 액세스입니다. 일반적으로 데이터베이스 및 레코드 집합 개체를 만들어 DAO의 기본 작업 영역을 암시적으로 사용합니다.

- 트랜잭션이 작업 영역에서 열려 있는 모든 데이터베이스에 적용되는 트랜잭션 공간입니다. 별도의 트랜잭션 공간을 관리하기 위해 추가 작업 영역을 만들 수 있습니다.

- 기본 Microsoft Jet 데이터베이스 엔진의 여러 속성에 대한 인터페이스입니다(정적 멤버 함수 참조). 작업 영역을 열거나 만들거나 열기 또는 만들기 전에 정적 멤버 함수를 호출하면 데이터베이스 엔진이 초기화됩니다.

- 데이터베이스 엔진의 Workspaces 컬렉션에 액세스하여 추가된 모든 활성 작업 영역을 저장합니다. 컬렉션에 추가하지 않고도 작업 영역을 만들고 작업할 수 있습니다.

## <a name="security"></a>보안

MFC는 보안 제어에 사용되는 DAO에서 사용자 및 그룹 컬렉션을 구현하지 않습니다. DAO의 이러한 측면이 필요한 경우 DAO 인터페이스에 대한 직접 호출을 통해 직접 프로그래밍해야 합니다. 자세한 내용은 [기술 참고 54를](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)참조하십시오.

## <a name="usage"></a>사용

클래스를 `CDaoWorkspace` 사용하여 다음을 수행할 수 있습니다.

- 기본 작업 영역을 명시적으로 엽니다.

   일반적으로 새 [CDaoDatabase 또는 CDaoRecordset](../../mfc/reference/cdaodatabase-class.md) 개체를 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 열 때 기본 작업 영역의 사용은 암시적입니다. 그러나 데이터베이스 엔진 속성 또는 Workspaces 컬렉션에 액세스하려면 명시적으로 액세스해야 할 수 있습니다. 아래의 "기본 작업 영역의 암시적 사용"을 참조하십시오.

- 새 작업 영역을 만듭니다. 작업 영역 컬렉션에 추가하려면 [추가를](#append) 호출합니다.

- 작업 영역 컬렉션에서 기존 작업 영역을 엽니다.

Workspaces 컬렉션에 아직 존재하지 않는 새 작업 영역만들기는 멤버 [만들기](#create) 함수아래에 설명되어 있습니다. 작업 영역 개체는 datababase 엔진 세션 간에 어떤 방식으로도 유지되지 않습니다. 응용 프로그램이 MFC를 정적으로 연결하는 경우 응용 프로그램을 종료하면 데이터베이스 엔진이 초기화되지 않습니다. 응용 프로그램이 MFC와 동적으로 링크되는 경우 MFC DLL을 언로드할 때 데이터베이스 엔진이 초기화되지 않습니다.

기본 작업 영역을 명시적으로 열거나 Workspaces 컬렉션에서 기존 작업 영역을 여는 것은 [Open](#open) 멤버 함수 아래에 설명되어 있습니다.

[닫기](#close) 멤버 함수로 작업 영역을 닫아 작업 영역 세션을 종료합니다. `Close`이전에 닫지 않은 데이터베이스를 닫고 커밋되지 않은 트랜잭션을 롤백합니다.

## <a name="transactions"></a>트랜잭션

DAO는 작업 영역 수준에서 트랜잭션을 관리합니다. 따라서 여러 개의 열린 데이터베이스가 있는 작업 영역의 트랜잭션이 모든 데이터베이스에 적용됩니다. 예를 들어 두 데이터베이스에 커밋되지 않은 업데이트가 있고 [CommitTrans를](#committrans)호출하면 모든 업데이트가 커밋됩니다. 트랜잭션을 단일 데이터베이스로 제한하려면 트랜잭션에 대한 별도의 작업 영역 개체가 필요합니다.

## <a name="implicit-use-of-the-default-workspace"></a>기본 작업 영역의 암시적 사용

MFC는 다음과 같은 상황에서 DAO의 기본 작업 영역을 암시적으로 사용합니다.

- 새 `CDaoDatabase` 객체를 만들었지만 기존 `CDaoWorkspace` 객체를 통해 만들지 않으면 MFC는 DAO의 기본 작업 공간에 해당하는 임시 작업 공간 개체를 만듭니다. 여러 데이터베이스에 대해 이렇게 하면 모든 데이터베이스 개체가 기본 작업 영역과 연결됩니다. 데이터 멤버를 통해 데이터베이스의 작업 `CDaoDatabase` 영역에 액세스할 수 있습니다.

- 마찬가지로 개체에 대한 `CDaoRecordset` 포인터를 `CDaoDatabase` 제공하지 않고 개체를 만드는 경우 MFC는 임시 데이터베이스 개체를 만들고 확장하여 임시 작업 영역 개체를 만듭니다. 데이터 멤버를 통해 레코드 집합의 데이터베이스와 간접적으로 해당 `CDaoRecordset` 작업 영역에 액세스할 수 있습니다.

## <a name="other-operations"></a>기타 작업

손상된 데이터베이스를 복구하거나 데이터베이스를 압축하는 등의 다른 데이터베이스 작업도 제공됩니다.

DAO를 직접 호출하고 DAO 보안에 대한 자세한 내용은 [기술 참고 54를](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDaoWorkspace`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="cdaoworkspaceappend"></a><a name="append"></a>CDao워크스페이스::부속

[Create를](#create)호출한 후 이 멤버 함수를 호출합니다.

```
virtual void Append();
```

### <a name="remarks"></a>설명

`Append`은 데이터베이스 엔진의 작업 영역 컬렉션에 새로 만든 작업 영역 개체를 가합니다. 작업 영역은 데이터베이스 엔진 세션 간에 유지되지 않습니다. 디스크가 아닌 메모리에만 저장됩니다. 작업 영역을 더할 필요가 없습니다. 그렇지 않으면 계속 사용할 수 있습니다.

추가된 작업 영역은 [닫기](#close) 멤버 함수를 호출할 때까지 활성 열린 상태로 Workspaces 컬렉션에 남아 있습니다.

관련 정보는 DAO 도움말의 "방법 부화" 항목을 참조하십시오.

## <a name="cdaoworkspacebegintrans"></a><a name="begintrans"></a>CDao워크스페이스::시작트랜스

트랜잭션을 시작 하려면이 멤버 함수를 호출 합니다.

```cpp
void BeginTrans();
```

### <a name="remarks"></a>설명

호출 `BeginTrans`한 후 , 데이터 또는 데이터베이스 구조에 대한 업데이트는 트랜잭션을 커밋 할 때 적용됩니다. 작업 영역은 단일 트랜잭션 공간을 정의하므로 트랜잭션은 작업 영역의 열려 있는 모든 데이터베이스에 적용됩니다. 트랜잭션을 완료하는 방법에는 두 가지가 있습니다.

- [CommitTrans](#committrans) 멤버 함수를 호출하여 트랜잭션을 커밋하고 변경 내용을 데이터 원본에 저장합니다.

- 또는 [롤백](#rollback) 멤버 함수를 호출하여 트랜잭션을 취소합니다.

트랜잭션이 보류 중인 동안 작업 영역 개체 또는 데이터베이스 개체를 닫으면 보류 중인 모든 트랜잭션이 롤백됩니다.

한 ODBC 데이터 원본의 트랜잭션을 다른 ODBC 데이터 원본의 트랜잭션과 격리해야 하는 경우 [SetIsolateODBCTrans](#setisolateodbctrans) 멤버 함수를 참조하십시오.

## <a name="cdaoworkspacecdaoworkspace"></a><a name="cdaoworkspace"></a>CDao워크스페이스::CDao워크스페이스

`CDaoWorkspace` 개체를 생성합니다.

```
CDaoWorkspace();
```

### <a name="remarks"></a>설명

C++ 오브젝트를 생성한 후 다음 두 가지 옵션이 있습니다.

- 개체의 [Open](#open) 멤버 함수를 호출하여 기본 작업 영역을 열거나 Workspaces 컬렉션에서 기존 개체를 엽니다.

- 또는 개체의 멤버 [만들기](#create) 함수를 호출하여 새 DAO 작업 영역 개체를 만듭니다. 이렇게 하면 개체를 통해 참조할 수 있는 `CDaoWorkspace` 새 작업 영역 세션이 명시적으로 시작됩니다. 호출 `Create`한 후 데이터베이스 엔진의 작업 영역 컬렉션에 작업 영역을 추가 하려는 경우 [추가](#append) 호출할 수 있습니다.

개체를 명시적으로 만들어야 하는 시기에 대한 정보는 [CDaoWorkspace의](../../mfc/reference/cdaoworkspace-class.md) 클래스 개요를 `CDaoWorkspace` 참조하십시오. 일반적으로 작업 영역을 지정하지 않고 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체를 열거나 데이터베이스 개체를 지정하지 않고 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체를 열 때 암시적으로 생성된 작업 영역을 사용합니다. 이러한 방식으로 만든 MFC DAO 개체는 한 번 생성되고 다시 사용되는 DAO의 기본 작업 영역을 사용합니다.

작업 영역 및 포함된 개체를 해제하려면 작업 영역 개체의 [닫기](#close) 멤버 함수를 호출합니다.

## <a name="cdaoworkspaceclose"></a><a name="close"></a>CDao워크스페이스::닫기

이 멤버 함수를 호출하여 작업 영역 개체를 닫습니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

열린 작업 영역 개체를 닫으면 기본 DAO 개체가 해제되고 작업 영역이 Workspaces 컬렉션의 멤버인 경우 컬렉션에서 제거됩니다. 호출은 `Close` 좋은 프로그래밍 방법입니다.

> [!CAUTION]
> 작업 영역 개체를 닫으면 작업 영역의 열린 데이터베이스가 닫힙입니다. 이렇게 하면 데이터베이스에서 열려 있는 레코드 집합도 닫히고 보류 중인 편집 또는 업데이트가 롤백됩니다. 관련 정보는 [CDaoDatabase::Close](../../mfc/reference/cdaodatabase-class.md#close), [CDaoRecordset::Close,](../../mfc/reference/cdaorecordset-class.md#close) [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close)및 [CDaoQueryDef::Close](../../mfc/reference/cdaoquerydef-class.md#close) 멤버 함수를 참조하십시오.

작업 영역 개체는 영구적이지 않습니다. 그들은 그들에 대한 참조가 존재하는 동안만 존재합니다. 즉, 데이터베이스 엔진 세션이 종료되면 작업 영역 및 해당 데이터베이스 컬렉션이 유지되지 않습니다. 작업 영역 및 데이터베이스를 다시 열어 다음 세션에 다시 만들어야 합니다.

관련 정보는 DAO 도움말의 "방법 닫기" 항목을 참조하십시오.

## <a name="cdaoworkspacecommittrans"></a><a name="committrans"></a>CDao워크스페이스::커밋트랜스

이 멤버 함수를 호출하여 트랜잭션을 커밋합니다 - 편집 및 업데이트 그룹을 작업 영역에서 하나 이상의 데이터베이스에 저장합니다.

```cpp
void CommitTrans();
```

### <a name="remarks"></a>설명

트랜잭션은 [BeginTrans](#begintrans)에 대한 호출로 시작하여 데이터베이스의 데이터 또는 해당 구조에 대한 일련의 변경 내용으로 구성됩니다. 트랜잭션을 완료하면 [롤백](#rollback)을 통해 커밋하거나 롤백(변경 내용 취소)합니다. 기본적으로 트랜잭션이 없으면 레코드에 대한 업데이트가 즉시 커밋됩니다. 호출하면 `BeginTrans` 호출할 `CommitTrans`때까지 업데이트 약정이 지연됩니다.

> [!CAUTION]
> 하나의 작업 영역 내에서 트랜잭션은 항상 작업 영역으로 전역되며 하나의 데이터베이스 또는 레코드 집합으로만 제한되지 않습니다. 작업 영역 트랜잭션 내에서 두 개 이상의 데이터베이스 또는 `CommitTrans` 레코드 집합에서 작업을 `Rollback` 수행하는 경우 보류 중인 모든 업데이트를 커밋하고 해당 데이터베이스 및 레코드 집합에 대한 모든 작업을 복원합니다.

보류 중인 트랜잭션으로 데이터베이스 또는 작업 영역을 닫으면 트랜잭션이 모두 롤백됩니다.

> [!NOTE]
> 이 메커니즘은 2단계 커밋 메커니즘이 아닙니다. 하나의 업데이트가 커밋에 실패해도 다른 업데이트는 여전히 커밋됩니다.

## <a name="cdaoworkspacecompactdatabase"></a><a name="compactdatabase"></a>CDao워크스페이스::컴팩트 데이터베이스

지정된 Microsoft Jet(를 압축하려면 이 멤버 함수를 호출합니다. MDB) 데이터베이스.

```
static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,
    LPCTSTR lpszDestName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int nOptions = 0);

static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,
    LPCTSTR lpszDestName,
    LPCTSTR lpszLocale,
    int nOptions,
    LPCTSTR lpszPassword);
```

### <a name="parameters"></a>매개 변수

*lpszSrcName*<br/>
닫힌 기존 데이터베이스의 이름입니다. "C:\\\MYDB와 같은 전체 경로 및 파일 이름일 수 있습니다. MDB". 파일 이름에 확장이 있는 경우 지정해야 합니다. 네트워크가 UNC(통일 명명 규칙)를 지원하는\\\\\\경우\\"\MYSERVER \MYSHARE\\\MYDIR\\\MYDB"와 같은 네트워크 경로를 지정할 수도 있습니다. MDB". ("C++\\이스케이프 문자이기 때문에 경로 문자열에 이중 백슬래시가 필요합니다.)

*lpszDestName*<br/>
만드는 압축된 데이터베이스의 전체 경로입니다. *lpszSrcName*. *lpszDestName* 인수를 사용하여 *lpszSrcName과*동일한 데이터베이스 파일을 지정할 수 없습니다.

*lpszPassword*<br/>
암호로 보호된 데이터베이스를 압축하려는 경우 사용되는 암호입니다. 암호를 사용하는 경우 `CompactDatabase` 모든 매개 변수를 제공해야 합니다. 또한 이 매개 변수는 연결 매개 변수이므로 다음과 같이 특수 한 서식이 필요합니다. PWD = *lpsz암호*. 예를 들어: ; PWD ="행복". (최고의 세미콜론이 필요합니다.)

*lpszLocale*<br/>
*lpszDestName*을 만들기 위한 정렬 순서를 지정 하는 데 사용 되는 문자열 식입니다. (아래 참조)의 `dbLangGeneral` 기본값을 수락하여 이 인수를 생략하면 새 데이터베이스의 로캘은 이전 데이터베이스의 로캘과 동일합니다. 가능한 값은 다음과 같습니다.

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

*nOptions*<br/>
대상 *데이터베이스lpszDestName에*대한 하나 이상의 옵션을 나타냅니다. 기본값을 수락하여 이 인수를 생략하면 *lpszDestName은* 동일한 암호화와 *lpszSrcName과*동일한 버전을 갖습니다. `dbEncrypt` 또는 `dbDecrypt` 옵션을 비트와이즈 OR 연산자를 사용하여 버전 옵션 중 하나와 결합할 수 있습니다. 데이터베이스 엔진 버전이 아닌 데이터베이스 형식을 지정하는 가능한 값은 다음과 같습니다.

- `dbEncrypt`압축하는 동안 데이터베이스를 암호화합니다.

- `dbDecrypt`압축하는 동안 데이터베이스의 암호를 해독합니다.

- `dbVersion10`압축하는 동안 Microsoft Jet 데이터베이스 엔진 버전 1.0을 사용하는 데이터베이스를 만듭니다.

- `dbVersion11`압축하는 동안 Microsoft Jet 데이터베이스 엔진 버전 1.1을 사용하는 데이터베이스를 만듭니다.

- `dbVersion20`압축하는 동안 Microsoft Jet 데이터베이스 엔진 버전 2.0을 사용하는 데이터베이스를 만듭니다.

- `dbVersion30`압축하는 동안 Microsoft Jet 데이터베이스 엔진 버전 3.0을 사용하는 데이터베이스를 만듭니다.

옵션 인수를 `dbEncrypt` `dbDecrypt` 사용하여 데이터베이스를 압축할 때 데이터베이스를 암호화할지 해독할지 지정할 수 있습니다. 암호화 상수를 생략하거나 둘 다 `dbDecrypt` `dbEncrypt`포함하면 *lpszDestName은* *lpszSrcName과*동일한 암호화를 갖습니다. 옵션 인수에서 버전 상수 중 하나를 사용하여 압축된 데이터베이스에 대한 데이터 형식의 버전을 지정할 수 있습니다. 이 상수는 *lpszDestName의*데이터 형식 버전에만 영향을 줍니다. 하나의 버전 상수만 지정할 수 있습니다. 버전 상수를 생략하는 경우 *lpszDestName은* *lpszSrcName*. *lpszDestName은* *lpszSrcName보다*동일하거나 그 이후버전에만 압축할 수 있습니다.

> [!CAUTION]
> 데이터베이스가 암호화되지 않은 경우 사용자/암호 보안을 구현하더라도 데이터베이스를 구성하는 바이너리 디스크 파일을 직접 읽을 수 있습니다.

### <a name="remarks"></a>설명

데이터베이스의 데이터를 변경하면 데이터베이스 파일이 조각화되어 필요 이상으로 많은 디스크 공간을 사용할 수 있습니다. 주기적으로 데이터베이스를 압축하여 데이터베이스 파일조각 모음을 해야 합니다. 압축된 데이터베이스는 일반적으로 더 작습니다. 데이터베이스를 복사하고 압축하는 동안 데이터 형식의 정렬 순서, 암호화 또는 버전을 변경할 수도 있습니다.

> [!CAUTION]
> 멤버 `CompactDatabase` 함수는 전체 Microsoft Access 데이터베이스를 한 버전에서 다른 버전으로 올바르게 변환하지 않습니다. 데이터 형식만 변환됩니다. 양식 및 보고서와 같은 Microsoft Access 정의 개체는 변환되지 않습니다. 그러나 데이터가 올바르게 변환됩니다.

> [!TIP]
> 데이터베이스 파일을 `CompactDatabase` 복사하는 데 사용할 수도 있습니다.

데이터베이스 압축에 대한 자세한 내용은 DAO 도움말의 "CompactDatabase 방법" 항목을 참조하십시오.

## <a name="cdaoworkspacecreate"></a><a name="create"></a>CDao워크스페이스::만들기

이 멤버 함수를 호출하여 새 DAO 작업 영역 개체를 만들고 MFC `CDaoWorkspace` 개체와 연결합니다.

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszUserName,
    LPCTSTR lpszPassword);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
새 작업 영역 개체의 이름을 고유하게 지정하는 최대 14자의 문자열입니다. 이름을 제공해야 합니다. 관련 정보는 DAO 도움말의 "이름 속성" 항목을 참조하십시오.

*lpszUserName*<br/>
작업 영역 소유자의 사용자 이름입니다. 요구 사항은 [setDefaultUser](#setdefaultuser) 멤버 함수에 대한 *lpszDefaultUser* 매개 변수를 참조하십시오. 관련 정보는 DAO 도움말의 "사용자 이름 속성" 항목을 참조하십시오.

*lpszPassword*<br/>
새 작업 영역 개체의 암호입니다. 암호는 최대 14자까지 사용할 수 있으며 ASCII 0(null)을 제외한 모든 문자를 포함할 수 있습니다. 암호는 대소문자를 구분합니다. 관련 정보는 DAO 도움말의 "암호 속성" 항목을 참조하십시오.

### <a name="remarks"></a>설명

전체 생성 프로세스는 다음과 입니다.

1. [CDaoWorkspace](#cdaoworkspace) 오브젝트를 생성합니다.

1. 개체의 `Create` 멤버 함수를 호출하여 기본 DAO 작업 영역을 만듭니다. 작업 영역 이름을 지정해야 합니다.

1. 데이터베이스 엔진의 작업 영역 컬렉션에 작업 영역을 추가하려는 경우 선택적으로 [추가를](#append) 호출합니다. 작업 영역을 추가하지 않고도 작업 영역으로 작업할 수 있습니다.

호출 `Create` 후 작업 영역 개체는 열린 상태로 사용 준비가 됩니다. 다음으로 전화를 `Open` 걸지 않습니다. `Create` 작업 영역컬렉션에 작업 영역이 이미 있는 경우 호출하지 `Create` 않습니다. `Create`응용 프로그램에 대해 아직 초기화되지 않은 경우 데이터베이스 엔진을 초기화합니다.

## <a name="cdaoworkspacegetdatabasecount"></a><a name="getdatabasecount"></a>CDaoWorkspace::GetDatabaseCount

이 멤버 함수를 호출하여 작업 영역의 데이터베이스 컬렉션에서 DAO 데이터베이스 개체 수(작업 공간의 열린 데이터베이스 수)를 검색합니다.

```
short GetDatabaseCount();
```

### <a name="return-value"></a>Return Value

작업 영역의 열린 데이터베이스 수입니다.

### <a name="remarks"></a>설명

`GetDatabaseCount`는 작업 영역의 데이터베이스 컬렉션에서 정의된 모든 데이터베이스를 반복해야 하는 경우에 유용합니다. 컬렉션에서 지정된 데이터베이스에 대한 정보를 얻으려면 [GetDatabaseInfo](#getdatabaseinfo)를 참조하십시오. 일반적인 용도는 `GetDatabaseCount` 열려 있는 데이터베이스 의 수를 호출한 다음 해당 번호를 반복 `GetDatabaseInfo`호출에 대한 루프 인덱스로 사용하는 것입니다.

## <a name="cdaoworkspacegetdatabaseinfo"></a><a name="getdatabaseinfo"></a>CDaoWorkspace::GetDatabaseInfo

이 멤버 함수를 호출하여 작업 영역에서 열린 데이터베이스에 대한 다양한 종류의 정보를 가져옵니다.

```cpp
void GetDatabaseInfo(
    int nIndex,
    CDaoDatabaseInfo& dbinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetDatabaseInfo(
    LPCTSTR lpszName,
    CDaoDatabaseInfo& dbinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스별 조회를 위해 작업 영역의 데이터베이스 컬렉션에 있는 데이터베이스 개체의 0기반 인덱스입니다.

*dbinfo*<br/>
요청한 정보를 반환하는 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) 개체에 대한 참조입니다.

*dwInfoOptions*<br/>
검색할 데이터베이스에 대한 정보를 지정하는 옵션입니다. 사용 가능한 옵션은 함수가 반환되는 원인과 함께 여기에 나열됩니다.

- AFX_DAO_PRIMARY_INFO(기본값) 이름, 업데이트 블렌더블, 트랜잭션

- AFX_DAO_SECONDARY_INFO 기본 정보 플러스: 버전, 정렬 순서 정렬, 쿼리 시간 시간

- AFX_DAO_ALL_INFO 기본 및 보조 정보 플러스: 연결

*lpszName*<br/>
이름으로 조회할 데이터베이스 개체의 이름입니다. 이름은 새 작업 영역 개체의 이름을 고유하게 지정하는 최대 14자로 구성된 문자열입니다.

### <a name="remarks"></a>설명

함수의 한 버전을 사용하면 인덱스별로 데이터베이스를 조회할 수 있습니다. 다른 버전에서는 이름으로 데이터베이스를 조회할 수 있습니다.

*dbinfo에서*반환되는 정보에 대한 설명은 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) 구조를 참조하십시오. 이 구조에는 *dwInfoOptions*에 대한 설명에 위에 나열된 정보 항목에 해당하는 멤버가 있습니다. 한 수준에서 정보를 요청하면 이전 수준에 대한 정보도 얻을 수 있습니다.

## <a name="cdaoworkspacegetinipath"></a><a name="getinipath"></a>CDao워크스페이스::겟시니패스

Windows 레지스트리에서 Microsoft Jet 데이터베이스 엔진의 초기화 설정 위치를 얻으려면 이 멤버 함수를 호출합니다.

```
static CString PASCAL GetIniPath();
```

### <a name="return-value"></a>Return Value

레지스트리 위치를 포함하는 [CString입니다.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>설명

위치를 사용하여 데이터베이스 엔진의 설정에 대한 정보를 얻을 수 있습니다. 반환되는 정보는 실제로 레지스트리 하위 키의 이름입니다.

관련 정보는 DAO 도움말의 "IniPath 속성" 및 "데이터 액세스를 위한 Windows 레지스트리 설정 사용자 지정" 항목을 참조하십시오.

## <a name="cdaoworkspacegetisolateodbctrans"></a><a name="getisolateodbctrans"></a>CDao워크스페이스::게아솔레이트ODBCTrans

이 멤버 함수를 호출하여 작업 영역에 대한 DAO IsolateODBCTrans 속성의 현재 값을 가져옵니다.

```
BOOL GetIsolateODBCTrans();
```

### <a name="return-value"></a>Return Value

ODBC 트랜잭션이 격리된 경우 비영점; 그렇지 않으면 0.

### <a name="remarks"></a>설명

경우에 따라 동일한 ODBC 데이터베이스에 계류 중인 여러 개의 동시 트랜잭션이 필요할 수 있습니다. 이렇게 하려면 각 트랜잭션에 대해 별도의 작업 영역을 열어야 합니다. 각 작업 영역이 데이터베이스에 자체 ODBC 연결을 가질 수 있지만 시스템 성능이 느려집니다. 트랜잭션 격리는 일반적으로 필요하지 않으므로 동일한 사용자가 연 여러 작업 영역 개체의 ODBC 연결은 기본적으로 공유됩니다.

Microsoft SQL Server와 같은 일부 ODBC 서버는 단일 연결에서 동시 트랜잭션을 허용하지 않습니다. 이러한 데이터베이스에 대해 보류 중인 한 번에 두 개 이상의 트랜잭션이 필요한 경우 IsolateODBCTrans 속성을 열자마자 각 작업 영역에서 TRUE로 설정합니다. 이렇게 하면 각 작업 영역에 대해 별도의 ODBC 연결이 강제로 연결됩니다.

관련 정보는 DAO 도움말의 "IsolateODBCTrans 속성" 항목을 참조하십시오.

## <a name="cdaoworkspacegetlogintimeout"></a><a name="getlogintimeout"></a>CDao워크스페이스::겟로그인 타임아웃

이 멤버 함수를 호출하여 작업 영역에 대한 DAO LoginTimeout 속성의 현재 값을 가져옵니다.

```
static short PASCAL GetLoginTimeout();
```

### <a name="return-value"></a>Return Value

ODBC 데이터베이스에 로그인하려고 할 때 오류가 발생하기 전의 시간(초)입니다.

### <a name="remarks"></a>설명

이 값은 ODBC 데이터베이스에 로그인하려고 할 때 오류가 발생하기 전의 초 를 나타냅니다. 기본 로그인 시간 설정은 20초입니다. LoginTimeout이 0으로 설정되면 시간 설정이 발생하지 않으며 데이터 원본과의 통신이 응답하지 않을 수 있습니다.

Microsoft SQL Server와 같은 ODBC 데이터베이스에 로그인하려고 하면 네트워크 오류또는 서버가 실행중이기 때문에 연결이 실패할 수 있습니다. 기본 20초가 연결될 때까지 기다리는 대신 데이터베이스 엔진이 오류를 생성하기 전에 대기하는 데 걸리는 시간까지 지정할 수 있습니다. 서버에 로그인하는 것은 외부 서버 데이터베이스에서 쿼리를 실행하는 것과 같은 여러 가지 이벤트의 일부로 암시적으로 발생합니다.

관련 정보는 DAO 도움말의 "로그인 시간 부족 속성" 항목을 참조하십시오.

## <a name="cdaoworkspacegetname"></a><a name="getname"></a>CDao워크스페이스::GetName

개체의 기본을 기본으로 하는 DAO 작업 영역 개체의 `CDaoWorkspace` 사용자 정의 이름을 얻으려면 이 멤버 함수를 호출합니다.

```
CString GetName();
```

### <a name="return-value"></a>Return Value

DAO 작업 영역 개체의 사용자 정의 이름을 포함하는 [CString입니다.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>설명

이름은 데이터베이스 엔진의 Workspaces 컬렉션에서 이름으로 DAO 작업 영역 개체에 액세스하는 데 유용합니다.

관련 정보는 DAO 도움말의 "이름 속성" 항목을 참조하십시오.

## <a name="cdaoworkspacegetusername"></a><a name="getusername"></a>CDao워크 스페이스::GetUserName

이 멤버 함수를 호출하여 작업 영역 의 소유자 이름을 가져옵니다.

```
CString GetUserName();
```

### <a name="return-value"></a>Return Value

작업 영역 개체의 소유자를 나타내는 [CString입니다.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>설명

작업 영역 소유자에 대한 사용 권한을 얻거나 설정하려면 DAO에 직접 전화하여 권한 속성 설정을 확인합니다. 그러면 사용자가 가지고 있는 사용 권한이 결정됩니다. 사용 권한으로 작업하려면 SYSTEM이 필요합니다. MDA 파일.

DAO에 직접 전화하는 것에 대한 자세한 내용은 [기술 참고 54를](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)참조하십시오. 관련 정보는 DAO 도움말의 "사용자 이름 속성" 항목을 참조하십시오.

## <a name="cdaoworkspacegetversion"></a><a name="getversion"></a>CDao워크 스페이스::GetVersion

사용 중Microsoft Jet 데이터베이스 엔진의 버전을 확인하려면 이 멤버 함수를 호출합니다.

```
static CString PASCAL GetVersion();
```

### <a name="return-value"></a>Return Value

개체와 연결된 데이터베이스 엔진의 버전을 나타내는 [CString입니다.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>설명

반환된 값은 "major.minor" 형식의 버전 번호를 나타냅니다. 예를 들어 "3.0"입니다. 제품 버전 번호(예: 3.0)는 버전 번호(3), 마침표 및 릴리스 번호(0)로 구성됩니다.

관련 정보는 DAO 도움말의 "버전 속성" 항목을 참조하십시오.

## <a name="cdaoworkspacegetworkspacecount"></a><a name="getworkspacecount"></a>CDao워크스페이스::겟워크스페이스카운트

이 멤버 함수를 호출하여 데이터베이스 엔진의 작업 영역 컬렉션에서 DAO 작업 영역 개체 수를 검색합니다.

```
short GetWorkspaceCount();
```

### <a name="return-value"></a>Return Value

작업 영역 컬렉션의 열린 작업 영역 수입니다.

### <a name="remarks"></a>설명

이 개수에는 컬렉션에 추가되지 않은 열린 작업 영역이 포함되지 않습니다. `GetWorkspaceCount`는 Workspaces 컬렉션에서 정의된 모든 작업 영역을 반복해야 하는 경우에 유용합니다. 컬렉션에서 지정된 작업 영역에 대한 정보를 얻으려면 [GetWorkspaceInfo](#getworkspaceinfo)를 참조하십시오. 일반적인 용도는 `GetWorkspaceCount` 열린 작업 영역의 수를 호출한 다음 해당 번호를 반복 `GetWorkspaceInfo`호출에 대한 루프 인덱스로 사용하는 것입니다.

## <a name="cdaoworkspacegetworkspaceinfo"></a><a name="getworkspaceinfo"></a>CDao워크스페이스::겟워크스페이스정보

이 멤버 함수를 호출하여 세션에서 열린 작업 영역에 대한 다양한 종류의 정보를 가져옵니다.

```cpp
void GetWorkspaceInfo(
    int nIndex,
    CDaoWorkspaceInfo& wkspcinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetWorkspaceInfo(
    LPCTSTR lpszName,
    CDaoWorkspaceInfo& wkspcinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스별 조회를 위해 Workspaces 컬렉션의 데이터베이스 개체의 0기반 인덱스입니다.

*wkspcinfo*<br/>
요청한 정보를 반환하는 [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) 개체에 대한 참조입니다.

*dwInfoOptions*<br/>
검색할 작업 영역에 대한 정보를 지정하는 옵션입니다. 사용 가능한 옵션은 함수가 반환되는 원인과 함께 여기에 나열됩니다.

- AFX_DAO_PRIMARY_INFO(기본값) 이름

- AFX_DAO_SECONDARY_INFO 기본 정보 플러스: 사용자 이름

- AFX_DAO_ALL_INFO 기본 및 보조 정보 플러스: ODBCTrans 격리

*lpszName*<br/>
이름으로 조회할 작업 영역 개체의 이름입니다. 이름은 새 작업 영역 개체의 이름을 고유하게 지정하는 최대 14자로 구성된 문자열입니다.

### <a name="remarks"></a>설명

*wkspcinfo에서*반환되는 정보에 대한 설명은 [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) 구조를 참조하십시오. 이 구조에는 *dwInfoOptions*에 대한 설명에 위에 나열된 정보 항목에 해당하는 멤버가 있습니다. 한 수준에서 정보를 요청하면 이전 수준에 대한 정보도 얻을 수 있습니다.

## <a name="cdaoworkspaceidle"></a><a name="idle"></a>CDao워크스페이스::유휴 상태

강력한 `Idle` 데이터 처리로 인해 최신이 아닐 수 있는 백그라운드 작업을 수행할 수 있는 기회를 데이터베이스 엔진에 제공하기 위해 호출합니다.

```
static void PASCAL Idle(int nAction = dbFreeLocks);
```

### <a name="parameters"></a>매개 변수

*nAction*<br/>
유휴 처리 중에 수행해야 하는 작업입니다. 현재 유효한 유일한 `dbFreeLocks`작업은 .

### <a name="remarks"></a>설명

이는 모든 레코드를 레코드 집합 의 최신 상태로 유지하기에 충분한 백그라운드 처리 시간이 없는 다중 사용자 멀티태스킹 환경에서도 마찬가지입니다.

> [!NOTE]
> Microsoft `Idle` Jet 데이터베이스 엔진의 버전 3.0으로 만든 데이터베이스는 호출이 필요하지 않습니다. 이전 `Idle` 버전으로 만든 데이터베이스에만 사용합니다.

일반적으로 읽기 잠금이 제거되고 로컬 다이너셋 형식 레코드 집합 개체의 데이터는 다른 작업(마우스 이동 포함)이 발생하지 않는 경우에만 업데이트됩니다. 주기적으로 호출하는 `Idle`경우 데이터베이스 엔진에 불필요한 읽기 잠금을 해제하여 백그라운드 처리 작업을 처리할 시간을 제공합니다. `dbFreeLocks` 상수를 인수로 지정하면 모든 읽기 잠금이 해제될 때까지 처리가 지연됩니다.

응용 프로그램의 여러 인스턴스가 실행되지 않는 한 단일 사용자 환경에서는 이 멤버 함수가 필요하지 않습니다. 멤버 `Idle` 함수는 데이터베이스 엔진이 데이터를 디스크로 플러시하도록 강제하여 메모리에 대한 잠금을 해제하기 때문에 다중 사용자 환경에서 성능을 높일 수 있습니다. 작업을 트랜잭션의 일부로 만들어 읽기 잠금을 해제할 수도 있습니다.

관련 정보는 DAO 도움말의 "유휴 방법" 항목을 참조하십시오.

## <a name="cdaoworkspaceisopen"></a><a name="isopen"></a>CDao워크스페이스::이스오픈

이 멤버 함수를 호출하여 개체가 `CDaoWorkspace` 열려 있는지 여부(즉, MFC 개체가 [Open](#open) 에 대한 호출에 의해 초기화되었는지 또는 [Create](#create)에 대한 호출)를 결정합니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Return Value

작업 영역 개체가 열려 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

열려 있는 상태인 작업 영역의 멤버 함수를 호출할 수 있습니다.

## <a name="cdaoworkspacem_pdaoworkspace"></a><a name="m_pdaoworkspace"></a>CDao워크스페이스::m_pDAOWorkspace

기본 DAO 작업 영역 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

기본 DAO 개체에 직접 액세스해야 하는 경우 이 데이터 멤버를 사용합니다. 이 포인터를 통해 DAO 개체의 인터페이스를 호출할 수 있습니다.

DAO 개체에 직접 액세스하는 방법에 대한 자세한 내용은 [기술 참고 54를](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)참조하십시오.

## <a name="cdaoworkspaceopen"></a><a name="open"></a>CDao워크스페이스::열기

DAO의 기본 작업 영역과 연결된 작업 영역 개체를 명시적으로 엽니다.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
열 DAO 작업 영역 개체의 이름- 작업 영역의 고유한 이름을 지정하는 최대 14자문자열입니다. 기본값 NULL을 수락하여 기본 작업 영역을 명시적으로 엽니다. 명명 요구 사항은 [만들기에](#create)대한 *lpszName* 매개 변수를 참조하십시오. 관련 정보는 DAO 도움말의 "이름 속성" 항목을 참조하십시오.

### <a name="remarks"></a>설명

개체를 생성한 `CDaoWorkspace` 후 이 멤버 함수를 호출하여 다음 중 하나를 수행합니다.

- 기본 작업 영역을 명시적으로 엽니다. *lpszName에*대해 NULL을 전달합니다.

- Workspaces `CDaoWorkspace` 컬렉션의 멤버인 기존 개체를 이름으로 엽니다. 기존 작업 영역 개체에 대해 유효한 이름을 전달합니다.

`Open`작업 영역 개체를 열린 상태로 만들고 응용 프로그램에 대해 아직 초기화되지 않은 경우 데이터베이스 엔진을 초기화합니다.

많은 `CDaoWorkspace` 멤버 함수는 작업 영역을 연 후에만 호출할 수 있지만 데이터베이스 엔진에서 작동하는 다음 멤버 함수는 C++ 개체를 `Open`빌드한 후 다음을 호출하기 전에 사용할 수 있습니다.

||||
|-|-|-|
|[만들기](#create)|[GetVersion](#getversion)|[SetDefaultUser](#setdefaultuser)|
|[GetIniPath](#getinipath)|[유휴 상태](#idle)|[SetIniPath](#setinipath)|
|[겟로그인 타임아웃](#getlogintimeout)|[SetDefaultPassword](#setdefaultpassword)|[세트로그인 시간 설정](#setlogintimeout)|

## <a name="cdaoworkspacerepairdatabase"></a><a name="repairdatabase"></a>CDao작업 공간::복구 데이터베이스

Microsoft Jet 데이터베이스 엔진에 액세스하는 손상된 데이터베이스를 복구해야 하는 경우 이 멤버 함수를 호출합니다.

```
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
기존 Microsoft Jet 엔진 데이터베이스 파일의 경로 및 파일 이름입니다. 경로를 생략하면 현재 디렉터리만 검색됩니다. 시스템이 UNC(통일 명명 규칙)를 지원하는\\\\\\경우 다음과\\\\\\같은 네트워크 경로를 지정할 수도 있습니다. MDB". ("C++\\이스케이프 문자이기 때문에 경로 문자열에 이중 백슬래시가 필요합니다.)

### <a name="remarks"></a>설명

*lpszName에* 의해 지정된 데이터베이스를 복구하려면 닫아야 합니다. 다중 사용자 환경에서는 복구하는 동안 다른 사용자가 *lpszName을* 열 수 없습니다. *lpszName이* 닫히지 않거나 단독으로 사용할 수 없는 경우 오류가 발생합니다.

이 멤버 함수는 불완전한 쓰기 작업으로 인해 손상된 것으로 표시된 데이터베이스를 복구하려고 시도합니다. 이 문제는 정전이나 컴퓨터 하드웨어 문제로 인해 Microsoft Jet 데이터베이스 엔진을 사용하는 응용 프로그램이 예기치 않게 닫히면 발생할 수 있습니다. 작업을 완료하고 [Close](../../mfc/reference/cdaodatabase-class.md#close) member 함수를 호출하거나 일반적인 방법으로 응용 프로그램을 종료하면 데이터베이스가 손상된 것으로 표시되지 않습니다.

> [!NOTE]
> 데이터베이스를 복구한 후 [CompactDatabase](#compactdatabase) 멤버 함수를 사용하여 압축하여 파일 조각 모음하고 디스크 공간을 복구하는 것도 좋습니다.

데이터베이스 복구에 대한 자세한 내용은 DAO 도움말의 "RepairDatabase 방법" 항목을 참조하십시오.

## <a name="cdaoworkspacerollback"></a><a name="rollback"></a>CDao워크스페이스::롤백

이 멤버 함수를 호출하여 현재 트랜잭션을 종료하고 트랜잭션이 시작되기 전에 작업 영역의 모든 데이터베이스를 해당 상태로 복원합니다.

```cpp
void Rollback();
```

### <a name="remarks"></a>설명

> [!CAUTION]
> 하나의 작업 영역 개체 내에서 트랜잭션은 항상 작업 영역으로 전역되며 하나의 데이터베이스 또는 레코드 집합으로만 제한되지 않습니다. 작업 영역 트랜잭션 내에서 두 개 이상의 데이터베이스 또는 `Rollback` 레코드 집합에서 작업을 수행하는 경우 이러한 모든 데이터베이스 및 레코드 집합에 대한 모든 작업을 복원합니다.

보류 중인 트랜잭션을 저장하거나 롤백하지 않고 작업 영역 개체를 닫으면 트랜잭션이 자동으로 롤백됩니다. [BeginTrans](#begintrans)를 먼저 호출하지 않고 [CommitTrans](#committrans) 및 `Rollback`를 호출하면 오류가 발생합니다.

> [!NOTE]
> 트랜잭션을 시작하면 데이터베이스 엔진은 워크스테이션의 TEMP 환경 변수가 지정한 디렉터리에 보관된 파일에 해당 작업을 기록합니다. 트랜잭션 로그 파일이 TEMP 드라이브에서 사용 가능한 저장소를 모두 소모하면 `CDaoException` 데이터베이스 엔진으로 인해 MFC가 DAO 오류 2004를 throw합니다. 이 시점에서 호출하는 `CommitTrans`경우 확정되지 않은 작업 수가 커밋되지만 완료되지 않은 나머지 작업은 손실되고 작업을 다시 시작해야 합니다. 호출은 `Rollback` 트랜잭션 로그를 해제하고 트랜잭션의 모든 작업을 롤백합니다.

## <a name="cdaoworkspacesetdefaultpassword"></a><a name="setdefaultpassword"></a>CDao워크스페이스::설정기본암호

이 멤버 함수를 호출하여 특정 암호 없이 작업 영역 개체를 만들 때 데이터베이스 엔진에서 사용하는 기본 암호를 설정합니다.

```
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```

### <a name="parameters"></a>매개 변수

*lpszPassword*<br/>
기본 암호입니다. 암호는 최대 14자까지 사용할 수 있으며 ASCII 0(null)을 제외한 모든 문자를 포함할 수 있습니다. 암호는 대소문자를 구분합니다.

### <a name="remarks"></a>설명

설정한 기본 암호는 호출 후 만든 새 작업 영역에 적용됩니다. 후속 작업 영역을 만들 때 호출 [만들기에서](#create) 암호를 지정할 필요가 없습니다.

이 멤버 함수를 사용하려면 다음을 수행하십시오.

1. 개체를 `CDaoWorkspace` 생성하지만 호출하지 `Create`않습니다.

1. 호출 `SetDefaultPassword` 및 원하는 경우 [SetDefaultUser](#setdefaultuser).

1. 암호를 `Create` 지정하지 않고 이 작업 영역 개체 또는 후속 개체를 호출합니다.

기본적으로 DefaultUser 속성은 "admin"으로 설정되고 DefaultPassword 속성은 빈 문자열("")으로 설정됩니다.

보안에 대한 자세한 내용은 DAO 도움말의 "사용 권한 속성" 항목을 참조하십시오. 관련 정보는 DAO 도움말의 "DefaultPassword 속성" 및 "기본 사용자 속성" 항목을 참조하십시오.

## <a name="cdaoworkspacesetdefaultuser"></a><a name="setdefaultuser"></a>CDao워크스페이스::설정기본유저

이 멤버 함수를 호출하여 데이터베이스 엔진이 특정 사용자 이름 없이 작업 영역 개체를 만들 때 사용하는 기본 사용자 이름을 설정합니다.

```
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```

### <a name="parameters"></a>매개 변수

*lpszDefaultUser*<br/>
기본 사용자 이름입니다. 사용자 이름은 1 - 20 자 길이일 수 있으며 알파벳 문자, 악센트 문자, 숫자, 공백 및 기호를 포함할 수 있습니다: \[ \] "(따옴표), / 앞으로 \< 슬래시), \(백슬래시), (대괄호), : (콜론), &#124; (파이프), (기호 미만), > (기호보다 큰), + (플러스 기호), = (동등한 기호), (세미콜론), (쉼표), (물음표), \* (별표), 선행 공백 및 제어 문자 (ASCII 00 ~ ASCII 31). 관련 정보는 DAO 도움말의 "사용자 이름 속성" 항목을 참조하십시오.

### <a name="remarks"></a>설명

설정한 기본 사용자 이름은 호출 후 만든 새 작업 영역에 적용됩니다. 후속 작업 영역을 만들 때 호출 [만들기에서](#create) 사용자 이름을 지정할 필요가 없습니다.

이 멤버 함수를 사용하려면 다음을 수행하십시오.

1. 개체를 `CDaoWorkspace` 생성하지만 호출하지 `Create`않습니다.

1. 전화 `SetDefaultUser` 및, 당신이 좋아하는 경우에, [SetDefaultPassword](#setdefaultpassword).

1. 사용자 `Create` 이름을 지정하지 않고 이 작업 영역 개체 또는 후속 개체를 호출합니다.

기본적으로 DefaultUser 속성은 "admin"으로 설정되고 DefaultPassword 속성은 빈 문자열("")으로 설정됩니다.

관련 정보는 DAO 도움말의 "기본 사용자 속성" 및 "기본 암호 속성" 항목을 참조하십시오.

## <a name="cdaoworkspacesetinipath"></a><a name="setinipath"></a>CDao워크스페이스::세티니패스

이 멤버 함수를 호출하여 Microsoft Jet 데이터베이스 엔진의 Windows 레지스트리 설정 위치를 지정합니다.

```
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```

### <a name="parameters"></a>매개 변수

*lpszRegistrySubkey*<br/>
설치 가능한 ISAM 데이터베이스에 필요한 Microsoft Jet 데이터베이스 엔진 설정 또는 매개 변수의 위치에 대한 Windows 레지스트리 하위 키의 이름이 포함된 문자열입니다.

### <a name="remarks"></a>설명

특수 `SetIniPath` 설정을 지정해야 하는 경우에만 호출합니다. 자세한 내용은 DAO 도움말의 "IniPath 속성" 항목을 참조하십시오.

> [!NOTE]
> 응용 `SetIniPath` 프로그램이 실행될 때가 아니라 응용 프로그램 설치 중에 호출합니다. `SetIniPath`작업 영역, 데이터베이스 또는 레코드 집합을 열기 전에 호출해야 합니다. 그렇지 않으면 MFC에서 예외를 throw합니다.

이 메커니즘을 사용하여 사용자가 제공한 레지스트리 설정으로 데이터베이스 엔진을 구성할 수 있습니다. 이 특성의 범위는 응용 프로그램으로 제한되며 응용 프로그램을 다시 시작하지 않고는 변경할 수 없습니다.

## <a name="cdaoworkspacesetisolateodbctrans"></a><a name="setisolateodbctrans"></a>CDao워크스페이스::세티솔레이트ODBCTrans

이 멤버 함수를 호출하여 작업 영역에 대한 DAO IsolateODBCTrans 속성의 값을 설정합니다.

```cpp
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```

### <a name="parameters"></a>매개 변수

*bIsolateODBCTrans*<br/>
ODBC 트랜잭션을 격리하려면 TRUE를 전달합니다. ODBC 트랜잭션 격리를 중지하려면 FALSE를 전달합니다.

### <a name="remarks"></a>설명

경우에 따라 동일한 ODBC 데이터베이스에 계류 중인 여러 개의 동시 트랜잭션이 필요할 수 있습니다. 이렇게 하려면 각 트랜잭션에 대해 별도의 작업 영역을 열어야 합니다. 각 작업 영역은 데이터베이스에 대한 자체 ODBC 연결을 가질 수 있지만 시스템 성능이 느려집니다. 트랜잭션 격리는 일반적으로 필요하지 않으므로 동일한 사용자가 연 여러 작업 영역 개체의 ODBC 연결은 기본적으로 공유됩니다.

Microsoft SQL Server와 같은 일부 ODBC 서버는 단일 연결에서 동시 트랜잭션을 허용하지 않습니다. 이러한 데이터베이스에 대해 보류 중인 한 번에 두 개 이상의 트랜잭션이 필요한 경우 IsolateODBCTrans 속성을 열자마자 각 작업 영역에서 TRUE로 설정합니다. 이렇게 하면 각 작업 영역에 대해 별도의 ODBC 연결이 강제로 연결됩니다.

## <a name="cdaoworkspacesetlogintimeout"></a><a name="setlogintimeout"></a>CDao워크스페이스::세트로그인 타임아웃

이 멤버 함수를 호출하여 작업 영역에 대한 DAO LoginTimeout 속성의 값을 설정합니다.

```
static void PASCAL SetLoginTimeout(short nSeconds);
```

### <a name="parameters"></a>매개 변수

*nSeconds*<br/>
ODBC 데이터베이스에 로그인하려고 할 때 오류가 발생하기 전의 시간(초)입니다.

### <a name="remarks"></a>설명

이 값은 ODBC 데이터베이스에 로그인하려고 할 때 오류가 발생하기 전의 초 를 나타냅니다. 기본 로그인 시간 설정은 20초입니다. LoginTimeout이 0으로 설정되면 시간 설정이 발생하지 않으며 데이터 원본과의 통신이 응답하지 않을 수 있습니다.

Microsoft SQL Server와 같은 ODBC 데이터베이스에 로그인하려고 하면 네트워크 오류또는 서버가 실행중이기 때문에 연결이 실패할 수 있습니다. 기본 20초가 연결될 때까지 기다리는 대신 데이터베이스 엔진이 오류를 생성하기 전에 대기하는 데 걸리는 시간까지 지정할 수 있습니다. 서버에 로그온하는 것은 외부 서버 데이터베이스에서 쿼리를 실행하는 것과 같은 여러 가지 이벤트의 일부로 암시적으로 발생합니다. 시간 시간 값은 LoginTimeout 속성의 현재 설정에 의해 결정됩니다.

관련 정보는 DAO 도움말의 "로그인 시간 부족 속성" 항목을 참조하십시오.

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDao데이터베이스 클래스](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDao레코드 집합 클래스](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoException 클래스](../../mfc/reference/cdaoexception-class.md)
