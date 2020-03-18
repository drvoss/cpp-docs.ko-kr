---
title: CDaoRecordset 클래스
ms.date: 08/27/2018
f1_keywords:
- CDaoRecordset
- AFXDAO/CDaoRecordset
- AFXDAO/CDaoRecordset::CDaoRecordset
- AFXDAO/CDaoRecordset::AddNew
- AFXDAO/CDaoRecordset::CanAppend
- AFXDAO/CDaoRecordset::CanBookmark
- AFXDAO/CDaoRecordset::CancelUpdate
- AFXDAO/CDaoRecordset::CanRestart
- AFXDAO/CDaoRecordset::CanScroll
- AFXDAO/CDaoRecordset::CanTransact
- AFXDAO/CDaoRecordset::CanUpdate
- AFXDAO/CDaoRecordset::Close
- AFXDAO/CDaoRecordset::Delete
- AFXDAO/CDaoRecordset::DoFieldExchange
- AFXDAO/CDaoRecordset::Edit
- AFXDAO/CDaoRecordset::FillCache
- AFXDAO/CDaoRecordset::Find
- AFXDAO/CDaoRecordset::FindFirst
- AFXDAO/CDaoRecordset::FindLast
- AFXDAO/CDaoRecordset::FindNext
- AFXDAO/CDaoRecordset::FindPrev
- AFXDAO/CDaoRecordset::GetAbsolutePosition
- AFXDAO/CDaoRecordset::GetBookmark
- AFXDAO/CDaoRecordset::GetCacheSize
- AFXDAO/CDaoRecordset::GetCacheStart
- AFXDAO/CDaoRecordset::GetCurrentIndex
- AFXDAO/CDaoRecordset::GetDateCreated
- AFXDAO/CDaoRecordset::GetDateLastUpdated
- AFXDAO/CDaoRecordset::GetDefaultDBName
- AFXDAO/CDaoRecordset::GetDefaultSQL
- AFXDAO/CDaoRecordset::GetEditMode
- AFXDAO/CDaoRecordset::GetFieldCount
- AFXDAO/CDaoRecordset::GetFieldInfo
- AFXDAO/CDaoRecordset::GetFieldValue
- AFXDAO/CDaoRecordset::GetIndexCount
- AFXDAO/CDaoRecordset::GetIndexInfo
- AFXDAO/CDaoRecordset::GetLastModifiedBookmark
- AFXDAO/CDaoRecordset::GetLockingMode
- AFXDAO/CDaoRecordset::GetName
- AFXDAO/CDaoRecordset::GetParamValue
- AFXDAO/CDaoRecordset::GetPercentPosition
- AFXDAO/CDaoRecordset::GetRecordCount
- AFXDAO/CDaoRecordset::GetSQL
- AFXDAO/CDaoRecordset::GetType
- AFXDAO/CDaoRecordset::GetValidationRule
- AFXDAO/CDaoRecordset::GetValidationText
- AFXDAO/CDaoRecordset::IsBOF
- AFXDAO/CDaoRecordset::IsDeleted
- AFXDAO/CDaoRecordset::IsEOF
- AFXDAO/CDaoRecordset::IsFieldDirty
- AFXDAO/CDaoRecordset::IsFieldNull
- AFXDAO/CDaoRecordset::IsFieldNullable
- AFXDAO/CDaoRecordset::IsOpen
- AFXDAO/CDaoRecordset::Move
- AFXDAO/CDaoRecordset::MoveFirst
- AFXDAO/CDaoRecordset::MoveLast
- AFXDAO/CDaoRecordset::MoveNext
- AFXDAO/CDaoRecordset::MovePrev
- AFXDAO/CDaoRecordset::Open
- AFXDAO/CDaoRecordset::Requery
- AFXDAO/CDaoRecordset::Seek
- AFXDAO/CDaoRecordset::SetAbsolutePosition
- AFXDAO/CDaoRecordset::SetBookmark
- AFXDAO/CDaoRecordset::SetCacheSize
- AFXDAO/CDaoRecordset::SetCacheStart
- AFXDAO/CDaoRecordset::SetCurrentIndex
- AFXDAO/CDaoRecordset::SetFieldDirty
- AFXDAO/CDaoRecordset::SetFieldNull
- AFXDAO/CDaoRecordset::SetFieldValue
- AFXDAO/CDaoRecordset::SetFieldValueNull
- AFXDAO/CDaoRecordset::SetLockingMode
- AFXDAO/CDaoRecordset::SetParamValue
- AFXDAO/CDaoRecordset::SetParamValueNull
- AFXDAO/CDaoRecordset::SetPercentPosition
- AFXDAO/CDaoRecordset::Update
- AFXDAO/CDaoRecordset::m_bCheckCacheForDirtyFields
- AFXDAO/CDaoRecordset::m_nFields
- AFXDAO/CDaoRecordset::m_nParams
- AFXDAO/CDaoRecordset::m_pDAORecordset
- AFXDAO/CDaoRecordset::m_pDatabase
- AFXDAO/CDaoRecordset::m_strFilter
- AFXDAO/CDaoRecordset::m_strSort
helpviewer_keywords:
- CDaoRecordset [MFC], CDaoRecordset
- CDaoRecordset [MFC], AddNew
- CDaoRecordset [MFC], CanAppend
- CDaoRecordset [MFC], CanBookmark
- CDaoRecordset [MFC], CancelUpdate
- CDaoRecordset [MFC], CanRestart
- CDaoRecordset [MFC], CanScroll
- CDaoRecordset [MFC], CanTransact
- CDaoRecordset [MFC], CanUpdate
- CDaoRecordset [MFC], Close
- CDaoRecordset [MFC], Delete
- CDaoRecordset [MFC], DoFieldExchange
- CDaoRecordset [MFC], Edit
- CDaoRecordset [MFC], FillCache
- CDaoRecordset [MFC], Find
- CDaoRecordset [MFC], FindFirst
- CDaoRecordset [MFC], FindLast
- CDaoRecordset [MFC], FindNext
- CDaoRecordset [MFC], FindPrev
- CDaoRecordset [MFC], GetAbsolutePosition
- CDaoRecordset [MFC], GetBookmark
- CDaoRecordset [MFC], GetCacheSize
- CDaoRecordset [MFC], GetCacheStart
- CDaoRecordset [MFC], GetCurrentIndex
- CDaoRecordset [MFC], GetDateCreated
- CDaoRecordset [MFC], GetDateLastUpdated
- CDaoRecordset [MFC], GetDefaultDBName
- CDaoRecordset [MFC], GetDefaultSQL
- CDaoRecordset [MFC], GetEditMode
- CDaoRecordset [MFC], GetFieldCount
- CDaoRecordset [MFC], GetFieldInfo
- CDaoRecordset [MFC], GetFieldValue
- CDaoRecordset [MFC], GetIndexCount
- CDaoRecordset [MFC], GetIndexInfo
- CDaoRecordset [MFC], GetLastModifiedBookmark
- CDaoRecordset [MFC], GetLockingMode
- CDaoRecordset [MFC], GetName
- CDaoRecordset [MFC], GetParamValue
- CDaoRecordset [MFC], GetPercentPosition
- CDaoRecordset [MFC], GetRecordCount
- CDaoRecordset [MFC], GetSQL
- CDaoRecordset [MFC], GetType
- CDaoRecordset [MFC], GetValidationRule
- CDaoRecordset [MFC], GetValidationText
- CDaoRecordset [MFC], IsBOF
- CDaoRecordset [MFC], IsDeleted
- CDaoRecordset [MFC], IsEOF
- CDaoRecordset [MFC], IsFieldDirty
- CDaoRecordset [MFC], IsFieldNull
- CDaoRecordset [MFC], IsFieldNullable
- CDaoRecordset [MFC], IsOpen
- CDaoRecordset [MFC], Move
- CDaoRecordset [MFC], MoveFirst
- CDaoRecordset [MFC], MoveLast
- CDaoRecordset [MFC], MoveNext
- CDaoRecordset [MFC], MovePrev
- CDaoRecordset [MFC], Open
- CDaoRecordset [MFC], Requery
- CDaoRecordset [MFC], Seek
- CDaoRecordset [MFC], SetAbsolutePosition
- CDaoRecordset [MFC], SetBookmark
- CDaoRecordset [MFC], SetCacheSize
- CDaoRecordset [MFC], SetCacheStart
- CDaoRecordset [MFC], SetCurrentIndex
- CDaoRecordset [MFC], SetFieldDirty
- CDaoRecordset [MFC], SetFieldNull
- CDaoRecordset [MFC], SetFieldValue
- CDaoRecordset [MFC], SetFieldValueNull
- CDaoRecordset [MFC], SetLockingMode
- CDaoRecordset [MFC], SetParamValue
- CDaoRecordset [MFC], SetParamValueNull
- CDaoRecordset [MFC], SetPercentPosition
- CDaoRecordset [MFC], Update
- CDaoRecordset [MFC], m_bCheckCacheForDirtyFields
- CDaoRecordset [MFC], m_nFields
- CDaoRecordset [MFC], m_nParams
- CDaoRecordset [MFC], m_pDAORecordset
- CDaoRecordset [MFC], m_pDatabase
- CDaoRecordset [MFC], m_strFilter
- CDaoRecordset [MFC], m_strSort
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
ms.openlocfilehash: 96118645aa656e97fcb93a0fd223045208ab03a3
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424538"
---
# <a name="cdaorecordset-class"></a>CDaoRecordset 클래스

데이터 소스에서 선택한 레코드 집합을 나타냅니다.

## <a name="syntax"></a>구문

```
class CDaoRecordset : public CObject
```

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDaoRecordset:: CDaoRecordset](#cdaorecordset)|`CDaoRecordset` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDaoRecordset:: AddNew](#addnew)|새 레코드를 추가할 준비를 합니다. [업데이트](#update) 를 호출 하 여 추가를 완료 합니다.|
|[CDaoRecordset:: CanAppend](#canappend)|[AddNew](#addnew) 멤버 함수를 통해 레코드 집합에 새 레코드를 추가할 수 있는 경우 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset:: CanBookmark](#canbookmark)|레코드 집합에서 책갈피를 지 원하는 경우 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset:: CancelUpdate](#cancelupdate)|[편집](#edit) 또는 [AddNew](#addnew) 작업으로 인해 보류 중인 모든 업데이트를 취소 합니다.|
|[CDaoRecordset:: CanRestart](#canrestart)|다시 쿼리를 호출 하 여 레코드 집합의 쿼리를 다시 실행할 수 [있는 경우 0](#requery) 이 아닌 값을 반환 합니다.|
|[CDaoRecordset:: CanScroll](#canscroll)|레코드를 스크롤할 수 있는 경우 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset:: CanTransact](#cantransact)|데이터 원본이 트랜잭션을 지원 하면 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset:: CanUpdate](#canupdate)|레코드 집합을 업데이트할 수 있는 경우 0이 아닌 값을 반환 합니다. 레코드를 추가, 업데이트 또는 삭제할 수 있습니다.|
|[CDaoRecordset:: Close](#close)|레코드 집합을 닫습니다.|
|[CDaoRecordset::D e)](#delete)|레코드 집합에서 현재 레코드를 삭제 합니다. 삭제 한 후에는 다른 레코드로 명시적으로 스크롤해야 합니다.|
|[CDaoRecordset::DoFieldExchange](#dofieldexchange)|레코드 집합의 필드 데이터 멤버와 데이터 소스에 있는 해당 레코드 사이에서 데이터를 양방향으로 교환 하기 위해 호출 됩니다. DAO 레코드 필드 교환 (DFX)을 구현 합니다.|
|[CDaoRecordset:: Edit](#edit)|현재 레코드에 대 한 변경 내용을 준비 합니다. `Update`를 호출 하 여 편집을 완료 합니다.|
|[CDaoRecordset:: FillCache](#fillcache)|ODBC 데이터 원본의 데이터를 포함 하는 레코드 집합 개체에 대 한 로컬 캐시의 전체 또는 일부를 채웁니다.|
|[CDaoRecordset:: Find](#find)|지정 된 조건을 충족 하는 다이너셋 형식 레코드 집합에서 특정 문자열의 첫 번째, 다음, 이전 또는 마지막 위치를 찾은 다음 현재 레코드를 기록 합니다.|
|[CDaoRecordset:: FindFirst](#findfirst)|지정 된 조건을 충족 하는 다이너셋 형식 또는 스냅숏 형식 레코드 집합의 첫 번째 레코드를 찾은 다음 현재 레코드를 기록 합니다.|
|[CDaoRecordset:: FindLast](#findlast)|지정 된 조건을 충족 하는 다이너셋 형식 또는 스냅숏 형식 레코드 집합에서 마지막 레코드를 찾은 다음 현재 레코드를 기록 합니다.|
|[CDaoRecordset:: FindNext](#findnext)|지정 된 조건을 충족 하는 다이너셋 형식 또는 스냅숏 형식 레코드 집합에서 다음 레코드를 찾은 다음 현재 레코드를 기록 합니다.|
|[CDaoRecordset:: FindPrev](#findprev)|지정 된 조건을 충족 하는 다이너셋 형식 또는 스냅숏 형식 레코드 집합에서 이전 레코드를 찾은 다음 현재 레코드를 기록 합니다.|
|[CDaoRecordset:: GetAbsolutePosition](#getabsoluteposition)|레코드 집합 개체의 현재 레코드에 대 한 레코드 번호를 반환 합니다.|
|[CDaoRecordset:: GetBookmark](#getbookmark)|레코드의 책갈피를 나타내는 값을 반환 합니다.|
|[CDaoRecordset:: GetCacheSize](#getcachesize)|ODBC 데이터 원본에서 로컬로 캐시할 데이터를 포함 하는 다이너셋 형식 레코드 집합의 레코드 수를 지정 하는 값을 반환 합니다.|
|[CDaoRecordset:: GetCacheStart](#getcachestart)|캐시 될 레코드 집합에서 첫 번째 레코드의 책갈피를 지정 하는 값을 반환 합니다.|
|[CDaoRecordset:: GetCurrentIndex](#getcurrentindex)|인덱싱된, 테이블 형식 `CDaoRecordset`에서 가장 최근에 사용 된 인덱스의 이름을 포함 하는 `CString`를 반환 합니다.|
|[CDaoRecordset:: GetDateCreated](#getdatecreated)|`CDaoRecordset` 개체의 기본 테이블이 만들어진 날짜와 시간을 반환 합니다.|
|[CDaoRecordset:: GetDateLastUpdated](#getdatelastupdated)|`CDaoRecordset` 개체의 기반이 되는 기본 테이블의 디자인에 대 한 최근 변경 내용의 날짜와 시간을 반환 합니다.|
|[CDaoRecordset:: GetDefaultDBName](#getdefaultdbname)|기본 데이터 원본의 이름을 반환 합니다.|
|[CDaoRecordset:: GetDefaultSQL](#getdefaultsql)|실행할 기본 SQL 문자열을 가져오기 위해 호출 됩니다.|
|[CDaoRecordset:: GetEditMode](#geteditmode)|현재 레코드에 대 한 편집 상태를 나타내는 값을 반환 합니다.|
|[CDaoRecordset:: GetFieldCount](#getfieldcount)|레코드 집합의 필드 수를 나타내는 값을 반환 합니다.|
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|레코드 집합의 필드에 대 한 특정 종류의 정보를 반환 합니다.|
|[CDaoRecordset:: GetFieldValue](#getfieldvalue)|레코드 집합에 있는 필드의 값을 반환 합니다.|
|[CDaoRecordset:: GetIndexCount](#getindexcount)|레코드 집합을 기반으로 하는 테이블의 인덱스 수를 검색 합니다.|
|[CDaoRecordset:: GetIndexInfo](#getindexinfo)|인덱스에 대 한 다양 한 종류의 정보를 반환 합니다.|
|[CDaoRecordset:: GetLastModifiedBookmark](#getlastmodifiedbookmark)|가장 최근에 추가 되거나 업데이트 된 레코드를 확인 하는 데 사용 됩니다.|
|[CDaoRecordset:: GetLockingMode](#getlockingmode)|편집 하는 동안 적용 되는 잠금 유형을 나타내는 값을 반환 합니다.|
|[CDaoRecordset:: GetName](#getname)|레코드 집합의 이름을 포함 하는 `CString`를 반환 합니다.|
|[CDaoRecordset:: GetParamValue](#getparamvalue)|기본 DAOParameter 개체에 저장 된 지정 된 매개 변수의 현재 값을 검색 합니다.|
|[CDaoRecordset:: GetPercentPosition](#getpercentposition)|현재 레코드의 위치를 총 레코드 수에 대 한 백분율로 반환 합니다.|
|[CDaoRecordset:: GetRecordCount](#getrecordcount)|레코드 집합 개체에서 액세스 한 레코드 수를 반환 합니다.|
|[CDaoRecordset:: GetSQL](#getsql)|레코드 집합에 대 한 레코드를 선택 하는 데 사용 되는 SQL 문자열을 가져옵니다.|
|[CDaoRecordset:: GetType](#gettype)|레코드 집합의 형식 (테이블 형식, 다이너셋 형식 또는 스냅숏 형식)을 결정 하기 위해 호출 됩니다.|
|[CDaoRecordset:: GetValidationRule](#getvalidationrule)|필드에 입력 될 때 데이터의 유효성을 검사 하는 값을 포함 하는 `CString`를 반환 합니다.|
|[CDaoRecordset:: GetValidationText](#getvalidationtext)|유효성 검사 규칙이 충족 되지 않을 때 표시 되는 텍스트를 검색 합니다.|
|[CDaoRecordset:: IsBOF](#isbof)|레코드 집합이 첫 번째 레코드 앞에 배치 되 면 0이 아닌 값을 반환 합니다. 현재 레코드가 없습니다.|
|[CDaoRecordset:: IsDeleted](#isdeleted)|레코드 집합이 삭제 된 레코드에 배치 되 면 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset:: IsEOF](#iseof)|레코드 집합이 마지막 레코드 뒤에 배치 된 경우 0이 아닌 값을 반환 합니다. 현재 레코드가 없습니다.|
|[CDaoRecordset:: IsFieldDirty](#isfielddirty)|현재 레코드의 지정 된 필드가 변경 된 경우 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset:: IsFieldNull](#isfieldnull)|현재 레코드의 지정 된 필드가 Null (값이 없는 경우) 이면 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset:: IsFieldNullable](#isfieldnullable)|현재 레코드의 지정 된 필드를 Null로 설정할 수 있으면 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset:: IsOpen](#isopen)|[Open](#open) 이 이전에 호출 된 경우 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset:: Move](#move)|현재 레코드의 지정 된 레코드 수에 레코드 집합을 두 방향으로 배치 합니다.|
|[CDaoRecordset:: MoveFirst](#movefirst)|레코드 집합의 첫 번째 레코드에 현재 레코드를 배치 합니다.|
|[CDaoRecordset:: MoveLast](#movelast)|레코드 집합의 마지막 레코드에 현재 레코드를 배치 합니다.|
|[CDaoRecordset:: MoveNext](#movenext)|레코드 집합의 다음 레코드에 현재 레코드를 배치 합니다.|
|[CDaoRecordset:: MovePrev](#moveprev)|레코드 집합의 이전 레코드에 현재 레코드를 배치 합니다.|
|[CDaoRecordset:: Open](#open)|테이블, 다이너셋 또는 스냅숏에서 새 레코드 집합을 만듭니다.|
|[CDaoRecordset:: Requery](#requery)|레코드 집합의 쿼리를 다시 실행 하 여 선택한 레코드를 새로 고칩니다.|
|[CDaoRecordset:: Seek](#seek)|현재 인덱스에 대해 지정 된 조건을 충족 하는 인덱싱된 테이블 형식 recordset 개체에서 레코드를 찾고 해당 레코드를 현재 레코드로 설정 합니다.|
|[CDaoRecordset:: SetAbsolutePosition](#setabsoluteposition)|레코드 집합 개체의 현재 레코드에 대 한 레코드 번호를 설정 합니다.|
|[CDaoRecordset:: SetBookmark](#setbookmark)|지정 된 책갈피를 포함 하는 레코드에 레코드 집합을 배치 합니다.|
|[CDaoRecordset:: SetCacheSize](#setcachesize)|ODBC 데이터 원본에서 로컬로 캐시할 데이터를 포함 하는 다이너셋 형식 레코드 집합의 레코드 수를 지정 하는 값을 설정 합니다.|
|[CDaoRecordset:: SetCacheStart](#setcachestart)|캐시 될 레코드 집합에서 첫 번째 레코드의 책갈피를 지정 하는 값을 설정 합니다.|
|[CDaoRecordset:: SetCurrentIndex](#setcurrentindex)|테이블 형식 레코드 집합에 대 한 인덱스를 설정 하기 위해 호출 됩니다.|
|[CDaoRecordset:: SetFieldDirty](#setfielddirty)|현재 레코드에서 지정 된 필드를 변경 된 것으로 표시 합니다.|
|[CDaoRecordset:: SetFieldNull](#setfieldnull)|현재 레코드에서 지정 된 필드의 값을 Null (값 없음)으로 설정 합니다.|
|[CDaoRecordset:: SetFieldValue](#setfieldvalue)|레코드 집합에 있는 필드의 값을 설정 합니다.|
|[CDaoRecordset:: SetFieldValueNull](#setfieldvaluenull)|레코드 집합의 필드 값을 Null로 설정 합니다. (값 없음).|
|[CDaoRecordset:: SetLockingMode](#setlockingmode)|편집 하는 동안 적용 될 잠금 유형을 나타내는 값을 설정 합니다.|
|[CDaoRecordset:: SetParamValue](#setparamvalue)|기본 DAOParameter 개체에 저장 된 지정 된 매개 변수의 현재 값을 설정 합니다.|
|[CDaoRecordset:: SetParamValueNull](#setparamvaluenull)|지정 된 매개 변수의 현재 값을 값이 없는 Null로 설정 합니다.|
|[CDaoRecordset:: SetPercentPosition](#setpercentposition)|레코드 집합의 총 레코드 수에 대 한 백분율에 해당 하는 위치로 현재 레코드의 위치를 설정 합니다.|
|[CDaoRecordset:: Update](#update)|새 데이터 또는 편집 된 데이터를 데이터 원본에 저장 하 여 `AddNew` 또는 `Edit` 작업을 완료 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDaoRecordset:: m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|필드를 자동으로 변경 된 것으로 표시할지 여부를 나타내는 플래그를 포함 합니다.|
|[CDaoRecordset:: m_nFields](#m_nfields)|레코드 집합 클래스의 필드 데이터 멤버 수와 데이터 원본의 레코드 집합에서 선택한 열 수를 포함 합니다.|
|[CDaoRecordset:: m_nParams](#m_nparams)|레코드 집합의 쿼리와 함께 전달 되는 매개 변수 수와 같은 레코드 집합 클래스의 매개 변수 데이터 멤버 수를 포함 합니다.|
|[CDaoRecordset:: m_pDAORecordset](#m_pdaorecordset)|레코드 집합 개체의 내부에 있는 DAO 인터페이스에 대 한 포인터입니다.|
|[CDaoRecordset:: m_pDatabase](#m_pdatabase)|이 결과 집합에 대 한 원본 데이터베이스입니다. [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체에 대 한 포인터를 포함 합니다.|
|[CDaoRecordset:: m_strFilter](#m_strfilter)|SQL **WHERE** 문을 생성 하는 데 사용 되는 문자열을 포함 합니다.|
|[CDaoRecordset:: m_strSort](#m_strsort)|SQL **ORDER by** 문을 생성 하는 데 사용 되는 문자열을 포함 합니다.|

## <a name="remarks"></a>설명

"레코드 집합" 이라고 하는 `CDaoRecordset` 개체는 다음 세 가지 형식으로 제공 됩니다.

- 테이블 형식 레코드 집합은 단일 데이터베이스 테이블에서 레코드를 검사, 추가, 변경 또는 삭제 하는 데 사용할 수 있는 기본 테이블을 나타냅니다.

- 다이너셋 형식 레코드 집합은 업데이트 가능한 레코드를 가질 수 있는 쿼리의 결과입니다. 이러한 레코드 집합은 기본 데이터베이스 테이블이 나 테이블에서 레코드를 검사, 추가, 변경 또는 삭제 하는 데 사용할 수 있는 레코드 집합입니다. 다이너셋 형식 레코드 집합은 데이터베이스에 있는 하나 이상의 테이블에 있는 필드를 포함할 수 있습니다.

- 스냅숏 형식 레코드 집합은 데이터를 찾거나 보고서를 생성 하는 데 사용할 수 있는 레코드 집합의 정적 복사본입니다. 이러한 레코드 집합은 데이터베이스에 있는 하나 이상의 테이블에 있는 필드를 포함할 수 있지만 업데이트할 수는 없습니다.

각 레코드 집합의 형태는 레코드 집합을 열 때 고정 된 레코드 집합을 나타냅니다. 테이블 형식 레코드 집합 또는 다이너셋 형식의 레코드 집합에 있는 레코드로 스크롤하면 다른 사용자나 응용 프로그램의 다른 레코드 집합에서 레코드 집합을 연 후 레코드에 대 한 변경 내용이 반영 됩니다. (스냅숏 형식의 레코드 집합은 업데이트할 수 없습니다.) `CDaoRecordset`를 직접 사용 하거나 `CDaoRecordset`에서 응용 프로그램별 레코드 집합 클래스를 파생할 수 있습니다. 그런 다음 아래의 작업을 수행할 수 있습니다.

- 레코드를 스크롤합니다.

- 인덱스를 설정 하 고 [Seek](#seek) 를 사용 하 여 레코드를 빠르게 찾습니다 (테이블 형식 레코드 집합에만 해당).

- 문자열 비교를 기준으로 레코드 찾기: "<", "\<=", "=", "> =", ">" (다이너셋 형식 및 스냅숏 형식 레코드 집합)

- 레코드를 업데이트 하 고 잠금 모드 (스냅숏 유형 레코드 집합 제외)를 지정 합니다.

- 레코드 집합을 필터링 하 여 데이터 원본에서 사용할 수 있는 레코드를 제약 합니다.

- 레코드 집합을 정렬 합니다.

- 런타임에 알려지지 않은 정보를 사용 하 여 선택 항목을 사용자 지정 하려면 레코드 집합을 매개 변수화 합니다.

클래스 `CDaoRecordset`는 클래스 `CRecordset`와 유사한 인터페이스를 제공 합니다. 주요 차이점은 클래스가 OLE 기반 DAO (Data Access Object)를 통해 데이터에 액세스 하 `CDaoRecordset`는 것입니다. 클래스 `CRecordset`는 ODBC (Open Database Connectivity) 및 해당 DBMS에 대 한 ODBC 드라이버를 통해 DBMS에 액세스 합니다.

> [!NOTE]
> DAO 데이터베이스 클래스는 ODBC (Open Database Connectivity)를 기반으로 하는 MFC 데이터베이스 클래스와는 다릅니다. 모든 DAO 데이터베이스 클래스 이름에는 "CDao" 접두사가 있습니다. 여전히 DAO 클래스를 사용 하 여 ODBC 데이터 원본에 액세스할 수 있습니다. 일반적으로 DAO 클래스는 Microsoft Jet 데이터베이스 엔진과 관련 되므로 뛰어난 기능을 제공 합니다.

`CDaoRecordset` 직접 사용 하거나 `CDaoRecordset`에서 클래스를 파생할 수 있습니다. 두 경우 모두 레코드 집합 클래스를 사용 하려면 데이터베이스를 열고 레코드 집합 개체를 생성 한 다음 생성자에 게 `CDaoDatabase` 개체에 대 한 포인터를 전달 합니다. `CDaoRecordset` 개체를 생성 하 고 MFC에서 임시 `CDaoDatabase` 개체를 만들도록 할 수도 있습니다. 그런 다음 레코드 집합의 [Open](#open) 멤버 함수를 호출 하 여 개체가 테이블 형식 레코드 집합 인지, 다이너셋 형식 레코드 집합 인지 또는 스냅숏 형식 레코드 집합 인지를 지정 합니다. `Open`를 호출 하면 데이터베이스에서 데이터를 선택 하 고 첫 번째 레코드를 검색 합니다.

개체의 멤버 함수 및 데이터 멤버를 사용 하 여 레코드를 스크롤하고 작업에 대해 작업을 수행 합니다. 사용 가능한 작업은 개체가 테이블 형식 레코드 집합 인지, 다이너셋 형식 레코드 집합 인지, 스냅숏 형식 레코드 집합 인지, 업데이트 가능한 지, 아니면 읽기 전용인 지에 따라 달라 집니다. 데이터베이스 또는 ODBC (Open Database Connectivity)의 기능에 따라 달라 집니다. 데이터 원본입니다. `Open` 호출 이후 변경 되거나 추가 된 레코드를 새로 고치려면 개체의 [Requery](#requery) 멤버 함수를 호출 합니다. 개체의 `Close` 멤버 함수를 호출 하 고 완료 되 면 개체를 삭제 합니다.

`CDaoRecordset`는 DAO 레코드 필드 교환 (DFX)을 사용 하 여 `CDaoRecordset` 또는 `CDaoRecordset`파생 클래스의 형식이 안전한 C++ 멤버를 통해 레코드 필드의 읽기 및 업데이트를 지원 합니다. [GetFieldValue](#getfieldvalue) 및 [SetFieldValue](#setfieldvalue)를 사용 하 여 DFX 메커니즘을 사용 하지 않고 데이터베이스에서 열의 동적 바인딩을 구현할 수도 있습니다.

관련 내용은 DAO 도움말의 "레코드 집합 개체" 항목을 참조 하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

`CDaoRecordset`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao

##  <a name="addnew"></a>CDaoRecordset:: AddNew

이 멤버 함수를 호출 하 여 테이블 형식 또는 다이너셋 형식의 레코드 집합에 새 레코드를 추가 합니다.

```
virtual void AddNew();
```

### <a name="remarks"></a>설명

레코드의 필드는 처음에 Null입니다. (데이터베이스 용어에서 Null은 "값을 갖지 않음"을 의미 하 고의 C++null과 같지 않습니다.) 작업을 완료 하려면 [Update](#update) 멤버 함수를 호출 해야 합니다. `Update` 데이터 원본에 변경 내용을 저장 합니다.

> [!CAUTION]
>  레코드를 편집 하 고 `Update`를 호출 하지 않고 다른 레코드로 스크롤하면 변경 내용이 경고 없이 손실 됩니다.

[AddNew](#addnew)를 호출 하 여 다이너셋 형식의 레코드 집합에 레코드를 추가 하면 레코드가 레코드 집합에 표시 되 고 기본 테이블에 포함 되어 새 `CDaoRecordset` 개체에 표시 됩니다.

새 레코드의 위치는 레코드 집합의 유형에 따라 달라 집니다.

- 새 레코드가 삽입 되는 다이너셋 형식의 레코드 집합에서 보장 되지 않습니다. 이 동작은 성능 및 동시성의 이유로 Microsoft Jet 3.0로 변경 되었습니다. 새로 추가 된 레코드를 현재 레코드로 설정 하는 것을 목표로 하는 경우 마지막으로 수정 된 레코드의 책갈피를 가져오고 해당 책갈피로 이동 합니다.

[!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]

- 인덱스가 지정 된 테이블 형식 레코드 집합에서 레코드는 정렬 순서에서 적절 한 위치로 반환 됩니다. 인덱스를 지정 하지 않으면 레코드 집합의 끝에 새 레코드가 반환 됩니다.

`AddNew` 사용 하기 전에 현재 레코드는 최신 상태로 유지 됩니다. 새 레코드를 최신 레코드로 설정 하 고 레코드 집합에서 책갈피를 지 원하는 경우 기본 DAO 레코드 집합 개체의 LastModified 속성 설정으로 식별 된 책갈피에 대 한 [Setbookmark](#setbookmark) 를 호출 합니다. 이렇게 하면 추가 된 레코드의 카운터 (자동 증가) 필드에 대 한 값을 결정 하는 데 유용 합니다. 자세한 내용은 [GetLastModifiedBookmark](#getlastmodifiedbookmark)를 참조 하세요.

데이터베이스에서 트랜잭션을 지 원하는 경우에는 `AddNew` 트랜잭션 작업의 일부로 호출할 수 있습니다. 트랜잭션에 대 한 자세한 내용은 클래스 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)를 참조 하세요. `AddNew`를 호출 하기 전에 [CDaoWorkspace:: BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) 를 호출 해야 합니다.

[Open](#open) 멤버 함수가 호출 되지 않은 레코드 집합에 대 한 `AddNew`를 호출할 수 없습니다. 추가할 수 없는 레코드 집합에 대해 `AddNew`를 호출 하는 경우 `CDaoException` throw 됩니다. [CanAppend](#canappend)를 호출 하 여 레코드 집합을 업데이트할 수 있는지 여부를 확인할 수 있습니다.

이 프레임 워크는 변경 된 필드 데이터 멤버를 표시 하 여 DAO 레코드 필드 교환 (DFX) 메커니즘에 의해 데이터 원본의 레코드에 기록 되도록 합니다. 필드의 값을 변경 하는 것은 일반적으로 자동으로 필드를 설정 하지 않으므로 사용자가 직접 [SetFieldDirty](#setfielddirty) 를 호출할 필요가 없지만 필드 데이터 멤버의 값에 관계 없이 열이 명시적으로 업데이트 되거나 삽입 되도록 할 수도 있습니다. 또한 DFX 메커니즘은 **의사 (PSEUDO) NULL**을 사용 합니다. 자세한 내용은 [CDaoFieldExchange:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)를 참조 하세요.

이중 버퍼링 메커니즘이 사용 되지 않는 경우 필드의 값을 변경 해도 필드가 더티로 자동 설정 되지 않습니다. 이 경우 필드를 명확 하 게 설정 해야 합니다. [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 에 포함 된 플래그는이 자동 필드 검사를 제어 합니다.

> [!NOTE]
> 레코드가 이중 버퍼링 되는 경우 (즉, 자동 필드 검사를 사용 하도록 설정 하는 경우) `CancelUpdate`를 호출 하면 `AddNew` 또는 `Edit`를 호출 하기 전의 값으로 멤버 변수가 복원 됩니다.

관련 정보는 DAO 도움말의 "AddNew 메서드", "CancelUpdate 메서드", "LastModified 속성" 및 "EditMode 속성" 항목을 참조 하십시오.

##  <a name="canappend"></a>CDaoRecordset:: CanAppend

이 멤버 함수를 호출 하 여 이전에 열린 레코드 집합에서 [AddNew](#addnew) 멤버 함수를 호출 하 여 새 레코드를 추가할 수 있는지 여부를 확인 합니다.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Return Value

레코드 집합에서 새 레코드 추가를 허용 하는 경우 0이 아닙니다. 그렇지 않으면 0입니다. 레코드 집합을 읽기 전용으로 연 경우 `CanAppend`는 0을 반환 합니다.

### <a name="remarks"></a>설명

관련 내용은 DAO 도움말의 "Append 메서드" 항목을 참조 하십시오.

##  <a name="canbookmark"></a>CDaoRecordset:: CanBookmark

이 멤버 함수를 호출 하 여 이전에 열린 레코드 집합에서 책갈피를 사용 하 여 레코드를 개별적으로 표시할 수 있는지 여부를 확인 합니다.

```
BOOL CanBookmark();
```

### <a name="return-value"></a>Return Value

레코드 집합에서 책갈피를 지원 하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

Microsoft Jet 데이터베이스 엔진 테이블에 전적으로 레코드 집합을 사용 하는 경우에는 앞 으로만 이동 가능한 스크롤 레코드 집합으로 플래그가 지정 된 스냅숏 형식 레코드 집합을 제외 하 고 책갈피를 사용할 수 있습니다. 다른 데이터베이스 제품 (외부 ODBC 데이터 원본)은 책갈피를 지원 하지 않을 수 있습니다.

관련 내용은 DAO 도움말의 "책갈피 가능 속성" 항목을 참조 하십시오.

##  <a name="cancelupdate"></a>CDaoRecordset:: CancelUpdate

`CancelUpdate` 멤버 함수는 [Edit](#edit) 또는 [AddNew](#addnew) 작업으로 인해 보류 중인 모든 업데이트를 취소 합니다.

```
virtual void CancelUpdate();
```

### <a name="remarks"></a>설명

예를 들어 응용 프로그램이 `Edit` 또는 `AddNew` 멤버 함수를 호출 하 고 [Update](#update)를 호출 하지 않은 경우에는 `CancelUpdate` `Edit` 또는 `AddNew`가 호출 된 후에 변경 된 내용을 취소 합니다.

> [!NOTE]
>  레코드가 이중 버퍼링 되는 경우 (즉, 자동 필드 검사를 사용 하도록 설정 하는 경우) `CancelUpdate`를 호출 하면 `AddNew` 또는 `Edit`를 호출 하기 전의 값으로 멤버 변수가 복원 됩니다.

보류 중인 `Edit` 또는 `AddNew` 작업이 없는 경우 `CancelUpdate`는 MFC에서 예외를 throw 합니다. [Geteditmode](#geteditmode) 멤버 함수를 호출 하 여 취소할 수 있는 보류 중인 작업이 있는지 확인 합니다.

관련 내용은 DAO 도움말의 "CancelUpdate 메서드" 항목을 참조 하십시오.

##  <a name="canrestart"></a>CDaoRecordset:: CanRestart

이 멤버 함수를 호출 하 여 레코드 집합에서 `Requery` 멤버 함수를 호출 하 여 쿼리를 다시 시작 하 여 해당 레코드를 새로 고칠 수 있는지 여부를 확인 합니다.

```
BOOL CanRestart();
```

### <a name="return-value"></a>Return Value

`Requery`를 호출 하 여 레코드 집합의 쿼리를 다시 실행할 수 있는 경우 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

테이블 형식 레코드 집합은 `Requery`를 지원 하지 않습니다.

`Requery` 지원 되지 않는 경우 [Close](#close) [를 호출 하 여](#open) 데이터를 새로 고칩니다. 매개 변수 값이 변경 된 후 `Requery`를 호출 하 여 레코드 집합 개체의 기본 매개 변수 쿼리를 업데이트할 수 있습니다.

관련 내용은 DAO 도움말의 "다시 시작 가능한 속성" 항목을 참조 하십시오.

##  <a name="canscroll"></a>CDaoRecordset:: CanScroll

이 멤버 함수를 호출 하 여 레코드 집합에서 스크롤할 수 있는지 여부를 확인 합니다.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Return Value

레코드를 스크롤할 수 있는 경우 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`dbForwardOnly`로 [열기](#open) 를 호출 하는 경우에는 레코드 집합을 앞 으로만 스크롤할 수 있습니다.

관련 내용은 DAO 도움말의 "DAO를 사용 하 여 현재 레코드 포인터 위치 지정" 항목을 참조 하십시오.

##  <a name="cantransact"></a>CDaoRecordset:: CanTransact

이 멤버 함수를 호출 하 여 레코드 집합에서 트랜잭션을 허용 하는지 여부를 확인 합니다.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Return Value

기본 데이터 소스에서 트랜잭션을 지원 하면 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

관련 내용은 DAO 도움말의 "트랜잭션 속성" 항목을 참조 하십시오.

##  <a name="canupdate"></a>CDaoRecordset:: CanUpdate

이 멤버 함수를 호출 하 여 레코드 집합을 업데이트할 수 있는지 여부를 확인 합니다.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Return Value

레코드 집합을 업데이트 (추가, 업데이트 및 삭제) 할 수 있는 경우 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 데이터 원본이 읽기 전용 이거나 레코드 집합에 대해 [Open](#open) 을 호출할 때 *nOptions* 에 대해 `dbReadOnly` 지정한 경우에는 레코드 집합이 읽기 전용일 수 있습니다.

관련 정보는 DAO 도움말의 "AddNew 메서드", "메서드 편집", "메서드 삭제", "업데이트 방법" 및 "업데이트할 수 있는 속성" 항목을 참조 하십시오.

##  <a name="cdaorecordset"></a>CDaoRecordset:: CDaoRecordset

`CDaoRecordset` 개체를 생성합니다.

```
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>매개 변수

*pDatabase*<br/>
[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체에 대 한 포인터 또는 NULL 값을 포함 합니다. NULL이 아니고 `CDaoDatabase` 개체의 `Open` 멤버 함수를 데이터 원본에 연결 하기 위해 호출 하지 않은 경우에는 레코드 집합에서 자체 [열기](#open) 호출 중에 해당 함수를 열려고 시도 합니다. NULL을 전달 하는 경우 `CDaoRecordset`에서 레코드 집합 클래스를 파생 한 경우 지정한 데이터 원본 정보를 사용 하 여 `CDaoDatabase` 개체가 생성 되 고 연결 됩니다.

### <a name="remarks"></a>설명

`CDaoRecordset`를 직접 사용 하거나 `CDaoRecordset`에서 응용 프로그램별 클래스를 파생할 수 있습니다. 클래스 마법사를 사용 하 여 레코드 집합 클래스를 파생할 수 있습니다.

> [!NOTE]
>  `CDaoRecordset` 클래스를 파생 하는 경우 파생 클래스는 자체 생성자를 제공 해야 합니다. 파생 클래스의 생성자에서 적절 한 매개 변수를 전달 하 여 `CDaoRecordset::CDaoRecordset`생성자를 호출 합니다.

`CDaoDatabase` 개체가 자동으로 생성 되 고 연결 되도록 레코드 집합 생성자에 NULL을 전달 합니다. 이는 레코드 집합을 생성 하기 전에 `CDaoDatabase` 개체를 구성 하 고 연결 하지 않아도 되는 유용한 바로 가기입니다. `CDaoDatabase` 개체가 열려 있지 않으면 기본 작업 영역을 사용 하는 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체도 생성 됩니다. 자세한 내용은 [CDaoDatabase:: CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase)를 참조 하세요.

##  <a name="close"></a>CDaoRecordset:: Close

`CDaoRecordset` 개체를 닫으면 연결 된 데이터베이스의 열려 있는 레코드 집합 컬렉션에서 개체가 제거 됩니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

`Close`은 `CDaoRecordset` 개체를 소멸 시 키 지 않으므로 동일한 데이터 소스 또는 다른 데이터 소스에서 `Open`를 호출 하 여 개체를 다시 사용할 수 있습니다.

보류 중인 모든 [AddNew](#addnew) 또는 [Edit](#edit) 문이 취소 되 고 보류 중인 모든 트랜잭션이 롤백됩니다. 보류 중인 추가 또는 편집 내용을 유지 하려면 각 레코드 집합에 대해 `Close`를 호출 하기 전에 [Update](#update) 를 호출 합니다.

`Close`를 호출한 후 `Open`을 다시 호출할 수 있습니다. 이렇게 하면 레코드 집합 개체를 다시 사용할 수 있습니다. 더 나은 방법은 [Requery](#requery)를 호출 하는 것입니다 (가능한 경우).

관련 정보는 DAO 도움말의 "Close 메서드" 항목을 참조 하십시오.

##  <a name="delete"></a>CDaoRecordset::D e)

열려 있는 다이너셋 형식 또는 테이블 형식 레코드 집합 개체에서 현재 레코드를 삭제 하려면이 멤버 함수를 호출 합니다.

```
virtual void Delete();
```

### <a name="remarks"></a>설명

성공적으로 삭제 한 후에는 레코드 집합의 필드 데이터 멤버가 Null 값으로 설정 되 고, 삭제 된 레코드를 이동 하기 위해 레코드 집합 탐색 멤버 함수 ( [move](#move), [Seek](#seek), [setbookmark](#setbookmark)등) 중 하나를 명시적으로 호출 해야 합니다. 레코드 집합에서 레코드를 삭제 하는 경우 `Delete`를 호출 하기 전에 레코드 집합에 현재 레코드가 있어야 합니다. 그렇지 않으면 MFC는 예외를 throw 합니다.

`Delete` 현재 레코드를 제거 하 고 액세스할 수 없게 만듭니다. 삭제 된 레코드는 편집 하거나 사용할 수 없지만 현재는 그대로 남아 있습니다. 그러나 다른 레코드로 이동한 후에는 삭제 된 레코드를 최신 레코드로 다시 설정할 수 없습니다.

> [!CAUTION]
>  레코드 집합은 업데이트 가능 해야 하며 `Delete`를 호출할 때 레코드 집합에 유효한 레코드가 있어야 합니다. 예를 들어 레코드를 삭제 하지만 `Delete`를 다시 호출 하기 전에 새 레코드로 스크롤하지 않는 경우 `Delete`는 [CDaoException](../../mfc/reference/cdaoexception-class.md)을 throw 합니다.

트랜잭션을 사용 하 고 [CDaoWorkspace:: Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) 멤버 함수를 호출 하는 경우 레코드의 삭제를 취소할 수 있습니다. 기본 테이블이 하위 삭제 관계의 주 테이블인 경우 현재 레코드를 삭제 하면 외래 테이블에서 하나 이상의 레코드가 삭제 될 수도 있습니다. 자세한 내용은 DAO 도움말의 "cascade delete" 정의를 참조 하십시오.

`AddNew` 및 `Edit`와 달리 `Delete`에 대 한 호출 뒤에 `Update`를 호출 하지 않습니다.

관련 정보는 DAO 도움말의 "AddNew 메서드", "메서드 편집", "메서드 삭제", "업데이트 방법" 및 "업데이트할 수 있는 속성" 항목을 참조 하십시오.

##  <a name="dofieldexchange"></a>CDaoRecordset::D oFieldExchange

프레임 워크는이 멤버 함수를 호출 하 여 레코드 집합 개체의 필드 데이터 멤버와 데이터 소스에 있는 현재 레코드의 해당 열 간에 데이터를 자동으로 교환 합니다.

```
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```

### <a name="parameters"></a>매개 변수

*pFX*<br/>
`CDaoFieldExchange` 개체에 대 한 포인터를 포함 합니다. 프레임 워크에는 필드 교환 작업의 컨텍스트를 지정 하는이 개체가 이미 설정 되어 있습니다.

### <a name="remarks"></a>설명

또한 매개 변수 데이터 멤버 (있는 경우)를 레코드 집합의 선택에 대 한 SQL 문 문자열의 매개 변수 자리 표시자에 바인딩합니다. DAO 레코드 필드 교환 (DFX) 이라고 하는 필드 데이터 교환은 레코드 집합 개체의 필드 데이터 멤버와 데이터 원본에 있는 레코드의 필드, 데이터 원본의 레코드에서 레코드 집합 개체로의 양방향으로 작동 합니다. 열을 동적으로 바인딩하는 경우에는 `DoFieldExchange`를 구현할 필요가 없습니다.

파생 된 레코드 집합 클래스에 대 한 `DoFieldExchange`를 구현 하기 위해 일반적으로 수행 해야 하는 작업은 클래스 마법사를 사용 하 여 클래스를 만들고 필드 데이터 멤버의 이름과 데이터 형식을 지정 하는 것입니다. 매개 변수 데이터 멤버를 지정 하기 위해 클래스 마법사에서 작성 하는 코드를 추가할 수도 있습니다. 모든 필드를 동적으로 바인딩하는 경우 매개 변수 데이터 멤버를 지정 하지 않으면이 함수는 비활성화 됩니다.

클래스 마법사를 사용 하 여 파생 된 레코드 집합 클래스를 선언 하면 마법사가 다음 예제와 같이 사용자에 대 한 `DoFieldExchange` 재정의를 작성 합니다.

[!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]

##  <a name="edit"></a>CDaoRecordset:: Edit

현재 레코드를 변경할 수 있도록 하려면이 멤버 함수를 호출 합니다.

```
virtual void Edit();
```

### <a name="remarks"></a>설명

`Edit` 멤버 함수를 호출 하면 현재 레코드의 필드에 대 한 변경 내용이 복사 버퍼에 복사 됩니다. 레코드를 원하는 대로 변경한 후 `Update`를 호출 하 여 변경 내용을 저장 합니다. `Edit`은 레코드 집합의 데이터 멤버 값을 저장 합니다. `Edit`를 호출 하 고 변경한 다음 `Edit`를 다시 호출 하는 경우 레코드의 값이 첫 번째 `Edit` 호출 이전의 값으로 복원 됩니다.

> [!CAUTION]
>  레코드를 편집한 다음 먼저 `Update`를 호출 하지 않고 다른 레코드로 이동 하는 작업을 수행 하는 경우 변경 내용이 경고 없이 손실 됩니다. 또한 레코드 집합 또는 부모 데이터베이스를 닫으면 편집 된 레코드는 경고 없이 삭제 됩니다.

일부 경우에는 데이터를 포함 하지 않는 열을 Null로 설정 하 여 열을 업데이트 하는 것이 좋습니다. 이렇게 하려면 TRUE의 매개 변수를 사용 하 여 `SetFieldNull`를 호출 하 여 필드를 Null로 표시 합니다. 이로 인해 열도 업데이트 됩니다. 값이 변경 되지 않은 경우에도 데이터 소스에 필드를 기록 하려면 TRUE의 매개 변수를 사용 하 여 `SetFieldDirty`를 호출 합니다. 필드의 값이 Null 인 경우에도 작동 합니다.

이 프레임 워크는 변경 된 필드 데이터 멤버를 표시 하 여 DAO 레코드 필드 교환 (DFX) 메커니즘에 의해 데이터 원본의 레코드에 기록 되도록 합니다. 필드의 값을 변경 하는 것은 일반적으로 자동으로 필드를 설정 하지 않으므로 사용자가 직접 [SetFieldDirty](#setfielddirty) 를 호출할 필요가 없지만 필드 데이터 멤버의 값에 관계 없이 열이 명시적으로 업데이트 되거나 삽입 되도록 할 수도 있습니다. 또한 DFX 메커니즘은 **의사 (PSEUDO) NULL**을 사용 합니다. 자세한 내용은 [CDaoFieldExchange:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)를 참조 하세요.

이중 버퍼링 메커니즘이 사용 되지 않는 경우 필드의 값을 변경 해도 필드가 더티로 자동 설정 되지 않습니다. 이 경우 필드를 명확 하 게 설정 해야 합니다. [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 에 포함 된 플래그는이 자동 필드 검사를 제어 합니다.

Recordset 개체가 다중 사용자 환경에서 pessimistically 잠긴 경우에는 업데이트가 완료 될 때까지 `Edit` 사용 되는 시점에서 레코드가 잠깁니다. 레코드 집합이 낙관적으로 잠겨 있으면 레코드는 잠기고 데이터베이스에서 업데이트 되기 직전에 미리 편집 된 레코드와 비교 됩니다. `Edit`를 호출한 후에 레코드가 변경 되 면 `Update` 작업이 실패 하 고 MFC에서 예외가 throw 됩니다. `SetLockingMode`를 사용 하 여 잠금 모드를 변경할 수 있습니다.

> [!NOTE]
>  낙관적 잠금은 ODBC 및 설치 가능 ISAM과 같은 외부 데이터베이스 형식에서 항상 사용 됩니다.

`Edit`를 호출한 후 현재 레코드는 최신 상태로 유지 됩니다. `Edit`를 호출 하려면 현재 레코드가 있어야 합니다. 현재 레코드가 없거나 레코드 집합이 열려 있는 테이블 형식 또는 다이너셋 형식의 레코드 집합 개체를 참조 하지 않는 경우 예외가 발생 합니다. `Edit`를 호출 하면 다음과 같은 경우 `CDaoException` throw 됩니다.

- 현재 레코드가 없습니다.

- 데이터베이스 또는 레코드 집합은 읽기 전용입니다.

- 레코드의 필드는 업데이트할 수 없습니다.

- 다른 사용자가 단독으로 사용 하도록 데이터베이스 또는 레코드 집합을 열었습니다.

- 다른 사용자가 레코드를 포함 하는 페이지를 잠 궜 습니다.

데이터 원본에서 트랜잭션을 지 원하는 경우 트랜잭션의 `Edit` 호출을 수행할 수 있습니다. `Edit`를 호출 하기 전에 및 레코드 집합을 연 후에는 `CDaoWorkspace::BeginTrans`를 호출 해야 합니다. 또한 `CDaoWorkspace::CommitTrans` 호출은 `Update`를 호출 하 여 `Edit` 작업을 완료 하는 대신 사용할 수 없습니다. 트랜잭션에 대 한 자세한 내용은 클래스 `CDaoWorkspace`를 참조 하세요.

관련 정보는 DAO 도움말의 "AddNew 메서드", "메서드 편집", "메서드 삭제", "업데이트 방법" 및 "업데이트할 수 있는 속성" 항목을 참조 하십시오.

##  <a name="fillcache"></a>CDaoRecordset:: FillCache

이 멤버 함수를 호출 하 여 레코드 집합에서 지정 된 수의 레코드를 캐시 합니다.

```
void FillCache(
    long* pSize = NULL,
    COleVariant* pBookmark = NULL);
```

### <a name="parameters"></a>매개 변수

*pSize*<br/>
캐시에 채울 행의 수를 지정 합니다. 이 매개 변수를 생략 하면 기본 DAO 개체의 CacheSize 속성 설정에 따라 값이 결정 됩니다.

*pBookmark*<br/>
책갈피를 지정 하는 [COleVariant](../../mfc/reference/colevariant-class.md) 입니다. 캐시는이 책갈피로 표시 된 레코드부터 채워집니다. 이 매개 변수를 생략 하면 기본 DAO 개체의 CacheStart 속성이 나타내는 레코드부터 캐시가 채워집니다.

### <a name="remarks"></a>설명

캐싱은 원격 서버에서 데이터를 검색 하거나 인출 하는 응용 프로그램의 성능을 향상 시킵니다. 캐시는 응용 프로그램이 실행 되는 동안 데이터를 다시 요청 하는 것으로 가정 하 고 서버에서 가장 최근에 인출 된 데이터를 보유 하는 로컬 메모리의 공간입니다. 데이터가 요청 될 때 Microsoft Jet 데이터베이스 엔진은 서버에서 데이터를 인출 하지 않고 먼저 캐시를 검사 하 여 더 많은 시간을 사용 합니다. 데이터가 캐시에 저장 되지 않으므로 비 ODBC 데이터 원본에 대 한 데이터 캐싱을 사용 해도 아무런 효과가 없습니다.

인출 되는 레코드로 캐시가 채워질 때까지 기다리는 대신 `FillCache` 멤버 함수를 호출 하 여 언제 든 지 캐시를 명시적으로 채울 수 있습니다. `FillCache`는 여러 레코드를 한 번에 하나씩 인출 하기 때문에 캐시를 채우는 더 빠른 방법입니다. 예를 들어 레코드의 각가 중에 표시 되는 동안 응용 프로그램 호출을 통해 다음의 `FillCache`의 레코드를 가져올 수 있습니다.

레코드 집합 개체를 사용 하 여 액세스 하는 모든 ODBC 데이터베이스에는 로컬 캐시가 있을 수 있습니다. 캐시를 만들려면 원격 데이터 원본에서 레코드 집합 개체를 연 다음 `SetCacheSize`를 호출 하 고 레코드 집합의 멤버 함수를 `SetCacheStart` 합니다. *Lsize* 및 *lsize* 가 `SetCacheSize` 및 `SetCacheStart`으로 지정 된 범위를 벗어난 범위를 일부 또는 전체적으로 만드는 경우이 범위를 벗어난 레코드 집합 부분은 무시 되 고 캐시로 로드 되지 않습니다. `FillCache`에서 원격 데이터 원본에 남아 있는 것 보다 많은 레코드를 요청 하는 경우 나머지 레코드만 인출 되 고 예외가 throw 되지 않습니다.

캐시에서 가져온 레코드는 다른 사용자가 원본 데이터에 대해 동시에 변경한 내용을 반영 하지 않습니다.

`FillCache`는 아직 캐시 되지 않은 레코드만 페치합니다. 모든 캐시 된 데이터를 강제로 업데이트 하려면 0과 동일한 *Lsize* 매개 변수를 사용 하 여 `SetCacheSize` 멤버 함수를 호출 하 고, 원래 요청한 캐시 크기와 동일한 *lsize* 매개 변수를 사용 하 여 `SetCacheSize`를 다시 호출한 다음 `FillCache`를 호출 합니다.

관련 내용은 DAO 도움말의 "FillCache 메서드" 항목을 참조 하십시오.

##  <a name="find"></a>CDaoRecordset:: Find

비교 연산자를 사용 하 여 다이너셋 또는 스냅숏 형식 레코드 집합에서 특정 문자열을 찾으려면이 멤버 함수를 호출 합니다.

```
virtual BOOL Find(
    long lFindType,
    LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lFindType*<br/>
원하는 찾기 작업의 유형을 나타내는 값입니다. 사용 가능한 값은

- AFX_DAO_NEXT 일치 하는 문자열의 다음 위치를 찾습니다.

- AFX_DAO_PREV 일치 하는 문자열의 이전 위치를 찾습니다.

- AFX_DAO_FIRST 일치 하는 문자열의 첫 번째 위치를 찾습니다.

- 일치 하는 문자열의 마지막 위치를 찾을 AFX_DAO_LAST.

*lpszFilter*<br/>
레코드를 찾는 데 사용 되는 **where**라는 단어가 없는 SQL 문의 **where** 절과 같은 문자열 식입니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]

### <a name="return-value"></a>Return Value

일치 하는 레코드가 있는 경우 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

문자열의 첫 번째, 다음, 이전 또는 마지막 인스턴스를 찾을 수 있습니다. `Find`은 가상 함수 이므로 재정의 하 고 사용자 고유의 구현을 추가할 수 있습니다. `FindFirst`, `FindLast`, `FindNext`및 `FindPrev` 멤버 함수는 `Find` 멤버 함수를 호출 하므로 `Find`를 사용 하 여 모든 찾기 작업의 동작을 제어할 수 있습니다.

테이블 형식 레코드 집합에서 레코드를 찾으려면 [Seek](#seek) 멤버 함수를 호출 합니다.

> [!TIP]
>  보유 하 고 있는 레코드 집합이 작을수록 더 효과적 `Find` 됩니다. 일반적으로 특히 ODBC 데이터를 사용 하는 경우 원하는 레코드만 검색 하는 새 쿼리를 만드는 것이 좋습니다.

관련 정보는 DAO 도움말의 "FindFirst, FindLast, FindNext, Findlast 메서드" 항목을 참조 하십시오.

##  <a name="findfirst"></a>CDaoRecordset:: FindFirst

이 멤버 함수를 호출 하 여 지정 된 조건과 일치 하는 첫 번째 레코드를 찾습니다.

```
BOOL FindFirst(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lpszFilter*<br/>
레코드를 찾는 데 사용 되는 **where**라는 단어가 없는 SQL 문의 **where** 절과 같은 문자열 식입니다.

### <a name="return-value"></a>Return Value

일치 하는 레코드가 있는 경우 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`FindFirst` 멤버 함수는 레코드 집합의 처음부터 검색을 시작 하 고 레코드 집합의 끝을 검색 합니다.

특정 조건을 충족 하는 레코드 뿐만 아니라 검색의 모든 레코드를 포함 하려는 경우 이동 작업 중 하나를 사용 하 여 레코드에서 레코드로 이동 합니다. 테이블 형식 레코드 집합에서 레코드를 찾으려면 `Seek` 멤버 함수를 호출 합니다.

기준과 일치 하는 레코드를 찾을 수 없는 경우 현재 레코드 포인터는 결정 되지 않으며 `FindFirst`는 0을 반환 합니다. 레코드 집합에 조건을 충족 하는 레코드가 두 개 이상 포함 된 경우 `FindFirst`는 첫 번째 항목을 찾고 `FindNext`는 다음 발생을 찾습니다.

> [!CAUTION]
>  현재 레코드를 편집 하는 경우 다른 레코드로 이동 하기 전에 `Update` 멤버 함수를 호출 하 여 변경 내용을 저장 해야 합니다. 업데이트 하지 않고 다른 레코드로 이동 하면 변경 내용이 경고 없이 손실 됩니다.

`Find` 멤버 함수는 위치 및 다음 표에 지정 된 방향에서 검색 합니다.

|찾기 작업|Begin|검색 방향|
|---------------------|-----------|----------------------|
|`FindFirst`|레코드 집합의 시작|레코드 집합의 끝|
|`FindLast`|레코드 집합의 끝|레코드 집합의 시작|
|`FindNext`|현재 레코드|레코드 집합의 끝|
|`FindPrevious`|현재 레코드|레코드 집합의 시작|

> [!NOTE]
>  `FindLast`를 호출 하면 검색을 시작 하기 전에 Microsoft Jet 데이터베이스 엔진에서 레코드 집합을 완전히 채웁니다 (아직 수행 하지 않은 경우). 첫 번째 검색은 후속 검색 보다 더 오래 걸릴 수 있습니다.

그러나 찾기 작업 중 하나를 사용 하는 것은 `MoveFirst` 또는 `MoveNext`호출 하는 것과 동일 하지 않습니다. 그러나 단순히 조건을 지정 하지 않고 첫 번째 또는 다음 레코드를 현재 상태로 만듭니다. 이동 작업을 사용 하 여 찾기 작업을 수행할 수 있습니다.

찾기 작업을 사용할 때는 다음 사항에 유의 하세요.

- `Find`에서 0이 아닌 값을 반환 하는 경우 현재 레코드는 정의 되지 않습니다. 이 경우 현재 레코드 포인터를 올바른 레코드로 다시 배치 해야 합니다.

- 앞 으로만 이동 가능한 스냅숏 형식의 레코드 집합에는 찾기 작업을 사용할 수 없습니다.

- 미국 버전의 Microsoft Jet 데이터베이스 엔진을 사용 하지 않는 경우에도 날짜를 포함 하는 필드를 검색 하는 경우 미국 날짜 형식 (월-일-연도)을 사용 해야 합니다. 그렇지 않으면 일치 하는 레코드를 찾을 수 없습니다.

- ODBC 데이터베이스 및 다량의 다이너셋을 사용할 때 특히 긴 레코드 집합으로 작업 하는 경우 찾기 작업을 사용 하는 속도가 느려지는 것을 알 수 있습니다. 사용자 지정 된 **ORDERBY** 또는 **WHERE** 절, 매개 변수 쿼리 또는 특정 인덱싱된 레코드를 검색 하는 `CDaoQuerydef` 개체를 사용 하 여 SQL 쿼리를 사용 하 여 성능을 향상 시킬 수 있습니다.

관련 정보는 DAO 도움말의 "FindFirst, FindLast, FindNext, Findlast 메서드" 항목을 참조 하십시오.

##  <a name="findlast"></a>CDaoRecordset:: FindLast

지정 된 조건과 일치 하는 마지막 레코드를 찾으려면이 멤버 함수를 호출 합니다.

```
BOOL FindLast(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lpszFilter*<br/>
레코드를 찾는 데 사용 되는 **where**라는 단어가 없는 SQL 문의 **where** 절과 같은 문자열 식입니다.

### <a name="return-value"></a>Return Value

일치 하는 레코드가 있는 경우 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`FindLast` 멤버 함수는 레코드 집합의 끝 부분에서 검색을 시작 하 고 레코드 집합의 시작 부분을 뒤로 검색 합니다.

특정 조건을 충족 하는 레코드 뿐만 아니라 검색의 모든 레코드를 포함 하려는 경우 이동 작업 중 하나를 사용 하 여 레코드에서 레코드로 이동 합니다. 테이블 형식 레코드 집합에서 레코드를 찾으려면 `Seek` 멤버 함수를 호출 합니다.

기준과 일치 하는 레코드를 찾을 수 없는 경우 현재 레코드 포인터는 결정 되지 않으며 `FindLast`는 0을 반환 합니다. 레코드 집합에 조건을 충족 하는 레코드가 두 개 이상 포함 된 경우 `FindFirst`는 `FindNext` 첫 번째 항목을 찾은 다음 첫 번째 발생 후의 다음 항목을 찾습니다.

> [!CAUTION]
>  현재 레코드를 편집 하는 경우 다른 레코드로 이동 하기 전에 `Update` 멤버 함수를 호출 하 여 변경 내용을 저장 해야 합니다. 업데이트 하지 않고 다른 레코드로 이동 하면 변경 내용이 경고 없이 손실 됩니다.

그러나 찾기 작업 중 하나를 사용 하는 것은 `MoveFirst` 또는 `MoveNext`호출 하는 것과 동일 하지 않습니다. 그러나 단순히 조건을 지정 하지 않고 첫 번째 또는 다음 레코드를 현재 상태로 만듭니다. 이동 작업을 사용 하 여 찾기 작업을 수행할 수 있습니다.

찾기 작업을 사용할 때는 다음 사항에 유의 하세요.

- `Find`에서 0이 아닌 값을 반환 하는 경우 현재 레코드는 정의 되지 않습니다. 이 경우 현재 레코드 포인터를 올바른 레코드로 다시 배치 해야 합니다.

- 앞 으로만 이동 가능한 스냅숏 형식의 레코드 집합에는 찾기 작업을 사용할 수 없습니다.

- 미국 버전의 Microsoft Jet 데이터베이스 엔진을 사용 하지 않는 경우에도 날짜를 포함 하는 필드를 검색 하는 경우 미국 날짜 형식 (월-일-연도)을 사용 해야 합니다. 그렇지 않으면 일치 하는 레코드를 찾을 수 없습니다.

- ODBC 데이터베이스 및 다량의 다이너셋을 사용할 때 특히 긴 레코드 집합으로 작업 하는 경우 찾기 작업을 사용 하는 속도가 느려지는 것을 알 수 있습니다. 사용자 지정 된 **ORDERBY** 또는 **WHERE** 절, 매개 변수 쿼리 또는 특정 인덱싱된 레코드를 검색 하는 `CDaoQuerydef` 개체를 사용 하 여 SQL 쿼리를 사용 하 여 성능을 향상 시킬 수 있습니다.

관련 정보는 DAO 도움말의 "FindFirst, FindLast, FindNext, Findlast 메서드" 항목을 참조 하십시오.

##  <a name="findnext"></a>CDaoRecordset:: FindNext

이 멤버 함수를 호출 하 여 지정 된 조건과 일치 하는 다음 레코드를 찾습니다.

```
BOOL FindNext(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lpszFilter*<br/>
레코드를 찾는 데 사용 되는 **where**라는 단어가 없는 SQL 문의 **where** 절과 같은 문자열 식입니다.

### <a name="return-value"></a>Return Value

일치 하는 레코드가 있는 경우 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`FindNext` 멤버 함수는 현재 레코드에서 검색을 시작 하 고 레코드 집합의 끝을 검색 합니다.

특정 조건을 충족 하는 레코드 뿐만 아니라 검색의 모든 레코드를 포함 하려는 경우 이동 작업 중 하나를 사용 하 여 레코드에서 레코드로 이동 합니다. 테이블 형식 레코드 집합에서 레코드를 찾으려면 `Seek` 멤버 함수를 호출 합니다.

기준과 일치 하는 레코드를 찾을 수 없는 경우 현재 레코드 포인터는 결정 되지 않으며 `FindNext`는 0을 반환 합니다. 레코드 집합에 조건을 충족 하는 레코드가 두 개 이상 포함 된 경우 `FindFirst`는 첫 번째 항목을 찾고 `FindNext`는 다음 발생을 찾습니다.

> [!CAUTION]
>  현재 레코드를 편집 하는 경우 다른 레코드로 이동 하기 전에 `Update` 멤버 함수를 호출 하 여 변경 내용을 저장 해야 합니다. 업데이트 하지 않고 다른 레코드로 이동 하면 변경 내용이 경고 없이 손실 됩니다.

그러나 찾기 작업 중 하나를 사용 하는 것은 `MoveFirst` 또는 `MoveNext`호출 하는 것과 동일 하지 않습니다. 그러나 단순히 조건을 지정 하지 않고 첫 번째 또는 다음 레코드를 현재 상태로 만듭니다. 이동 작업을 사용 하 여 찾기 작업을 수행할 수 있습니다.

찾기 작업을 사용할 때는 다음 사항에 유의 하세요.

- `Find`에서 0이 아닌 값을 반환 하는 경우 현재 레코드는 정의 되지 않습니다. 이 경우 현재 레코드 포인터를 올바른 레코드로 다시 배치 해야 합니다.

- 앞 으로만 이동 가능한 스냅숏 형식의 레코드 집합에는 찾기 작업을 사용할 수 없습니다.

- 미국 버전의 Microsoft Jet 데이터베이스 엔진을 사용 하지 않는 경우에도 날짜를 포함 하는 필드를 검색 하는 경우 미국 날짜 형식 (월-일-연도)을 사용 해야 합니다. 그렇지 않으면 일치 하는 레코드를 찾을 수 없습니다.

- ODBC 데이터베이스 및 다량의 다이너셋을 사용할 때 특히 긴 레코드 집합으로 작업 하는 경우 찾기 작업을 사용 하는 속도가 느려지는 것을 알 수 있습니다. 사용자 지정 된 **ORDERBY** 또는 **WHERE** 절, 매개 변수 쿼리 또는 특정 인덱싱된 레코드를 검색 하는 `CDaoQuerydef` 개체를 사용 하 여 SQL 쿼리를 사용 하 여 성능을 향상 시킬 수 있습니다.

관련 정보는 DAO 도움말의 "FindFirst, FindLast, FindNext, Findlast 메서드" 항목을 참조 하십시오.

##  <a name="findprev"></a>CDaoRecordset:: FindPrev

지정 된 조건과 일치 하는 이전 레코드를 찾으려면이 멤버 함수를 호출 합니다.

```
BOOL FindPrev(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lpszFilter*<br/>
레코드를 찾는 데 사용 되는 **where**라는 단어가 없는 SQL 문의 **where** 절과 같은 문자열 식입니다.

### <a name="return-value"></a>Return Value

일치 하는 레코드가 있는 경우 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`FindPrev` 멤버 함수는 현재 레코드에서 검색을 시작 하 고 레코드 집합의 시작 부분을 뒤로 검색 합니다.

특정 조건을 충족 하는 레코드 뿐만 아니라 검색의 모든 레코드를 포함 하려는 경우 이동 작업 중 하나를 사용 하 여 레코드에서 레코드로 이동 합니다. 테이블 형식 레코드 집합에서 레코드를 찾으려면 `Seek` 멤버 함수를 호출 합니다.

기준과 일치 하는 레코드를 찾을 수 없는 경우 현재 레코드 포인터는 결정 되지 않으며 `FindPrev`는 0을 반환 합니다. 레코드 집합에 조건을 충족 하는 레코드가 두 개 이상 포함 된 경우 `FindFirst`는 첫 번째 항목을 찾고 `FindNext`는 다음 발생을 찾습니다.

> [!CAUTION]
>  현재 레코드를 편집 하는 경우 다른 레코드로 이동 하기 전에 `Update` 멤버 함수를 호출 하 여 변경 내용을 저장 해야 합니다. 업데이트 하지 않고 다른 레코드로 이동 하면 변경 내용이 경고 없이 손실 됩니다.

그러나 찾기 작업 중 하나를 사용 하는 것은 `MoveFirst` 또는 `MoveNext`호출 하는 것과 동일 하지 않습니다. 그러나 단순히 조건을 지정 하지 않고 첫 번째 또는 다음 레코드를 현재 상태로 만듭니다. 이동 작업을 사용 하 여 찾기 작업을 수행할 수 있습니다.

찾기 작업을 사용할 때는 다음 사항에 유의 하세요.

- `Find`에서 0이 아닌 값을 반환 하는 경우 현재 레코드는 정의 되지 않습니다. 이 경우 현재 레코드 포인터를 올바른 레코드로 다시 배치 해야 합니다.

- 앞 으로만 이동 가능한 스냅숏 형식의 레코드 집합에는 찾기 작업을 사용할 수 없습니다.

- 미국 버전의 Microsoft Jet 데이터베이스 엔진을 사용 하지 않는 경우에도 날짜를 포함 하는 필드를 검색 하는 경우 미국 날짜 형식 (월-일-연도)을 사용 해야 합니다. 그렇지 않으면 일치 하는 레코드를 찾을 수 없습니다.

- ODBC 데이터베이스 및 다량의 다이너셋을 사용할 때 특히 긴 레코드 집합으로 작업 하는 경우 찾기 작업을 사용 하는 속도가 느려지는 것을 알 수 있습니다. 사용자 지정 된 **ORDERBY** 또는 **WHERE** 절, 매개 변수 쿼리 또는 특정 인덱싱된 레코드를 검색 하는 `CDaoQuerydef` 개체를 사용 하 여 SQL 쿼리를 사용 하 여 성능을 향상 시킬 수 있습니다.

관련 정보는 DAO 도움말의 "FindFirst, FindLast, FindNext, Findlast 메서드" 항목을 참조 하십시오.

##  <a name="getabsoluteposition"></a>CDaoRecordset:: GetAbsolutePosition

레코드 집합 개체의 현재 레코드에 대 한 레코드 번호를 반환 합니다.

```
long GetAbsolutePosition();
```

### <a name="return-value"></a>Return Value

0부터 레코드 집합의 레코드 수 까지의 정수입니다. 레코드 집합에서 현재 레코드의 서 수 위치에 해당 합니다.

### <a name="remarks"></a>설명

기본 DAO 개체의 AbsolutePosition 속성 값은 0부터 시작 합니다. 0의 설정은 레코드 집합의 첫 번째 레코드를 참조 합니다. [Getrecordcount](#getrecordcount)를 호출 하 여 레코드 집합에서 채워진 레코드 수를 확인할 수 있습니다. 모든 레코드에 액세스 하 여 개수를 결정 해야 하므로 `GetRecordCount`를 호출 하는 데 시간이 걸릴 수 있습니다.

레코드 집합에 레코드가 없는 경우와 같이 현재 레코드가 없는 경우-1이 반환 됩니다. 현재 레코드를 삭제 하면 AbsolutePosition 속성 값이 정의 되지 않고 MFC가 참조 되는 경우 예외를 throw 합니다. 다이너셋 형식 레코드 집합의 경우 시퀀스의 끝에 새 레코드가 추가 됩니다.

> [!NOTE]
>  이 속성은 서로게이트 레코드 번호로 사용 하기 위한 것이 아닙니다. 책갈피는 지정 된 위치를 유지 하 고 반환 하는 데 권장 되는 방법 이지만 모든 형식의 레코드 집합 개체에 대해 현재 레코드를 배치 하는 유일한 방법입니다. 특히, 앞의 레코드가 삭제 될 때 지정 된 레코드의 위치가 변경 됩니다. 또한 레코드 집합에 있는 개별 레코드의 순서는 **ORDERBY** 절을 사용 하 여 SQL 문을 사용 하 여 생성 된 경우를 제외 하 고는 다시 생성 될 경우 지정 된 레코드는 동일한 절대 위치를 갖게 됩니다.

> [!NOTE]
>  이 멤버 함수는 다이너셋 형식 및 스냅숏 형식 레코드 집합에 대해서만 유효 합니다.

관련 내용은 DAO 도움말의 "AbsolutePosition 속성" 항목을 참조 하십시오.

##  <a name="getbookmark"></a>CDaoRecordset:: GetBookmark

특정 레코드에서 책갈피 값을 가져오려면이 멤버 함수를 호출 합니다.

```
COleVariant GetBookmark();
```

### <a name="return-value"></a>Return Value

현재 레코드의 책갈피를 나타내는 값을 반환 합니다.

### <a name="remarks"></a>설명

레코드 집합 개체를 만들거나 열 때 각 레코드는 해당 레코드를 지 원하는 경우 이미 고유한 책갈피를 가집니다. `CanBookmark`를 호출 하 여 레코드 집합에서 책갈피를 지원 하는지 여부를 확인 합니다.

책갈피 값을 `COleVariant` 개체에 할당 하 여 현재 레코드에 대 한 책갈피를 저장할 수 있습니다. 다른 레코드로 이동한 후 언제 든 지 해당 레코드로 신속 하 게 돌아가려면 해당 `COleVariant` 개체의 값에 해당 하는 매개 변수를 사용 하 여 `SetBookmark`를 호출 합니다.

> [!NOTE]
>  [Requery](#requery) 를 호출 하면 DAO 책갈피가 변경 됩니다.

관련 내용은 DAO 도움말의 "책갈피 속성" 항목을 참조 하십시오.

##  <a name="getcachesize"></a>CDaoRecordset:: GetCacheSize

이 멤버 함수를 호출 하 여 캐시 된 레코드 수를 가져옵니다.

```
long GetCacheSize();
```

### <a name="return-value"></a>Return Value

ODBC 데이터 원본에서 로컬로 캐시할 데이터를 포함 하는 다이너셋 형식 레코드 집합의 레코드 수를 지정 하는 값입니다.

### <a name="remarks"></a>설명

데이터 캐싱은 다이너셋 형식의 레코드 집합 개체를 통해 원격 서버에서 데이터를 검색 하는 응용 프로그램의 성능을 향상 시킵니다. 캐시는 응용 프로그램이 실행 되는 동안 데이터를 다시 요청 하는 경우 서버에서 가장 최근에 검색 된 데이터를 보관 하는 로컬 메모리의 공간입니다. 데이터가 요청 될 때 Microsoft Jet 데이터베이스 엔진은 서버에서 검색 하는 대신 요청 된 데이터에 대 한 캐시를 먼저 확인 하 여 더 많은 시간을 사용 합니다. ODBC 데이터 원본에서 가져오지 않은 데이터는 캐시에 저장 되지 않습니다.

모든 ODBC 데이터 원본 (예: 연결 된 테이블)에는 로컬 캐시를 사용할 수 있습니다.

관련 내용은 DAO 도움말의 "CacheSize, CacheStart 속성" 항목을 참조 하십시오.

##  <a name="getcachestart"></a>CDaoRecordset:: GetCacheStart

이 멤버 함수를 호출 하 여 캐시 될 레코드 집합에 있는 첫 번째 레코드의 책갈피 값을 가져옵니다.

```
COleVariant GetCacheStart();
```

### <a name="return-value"></a>Return Value

캐시 될 레코드 집합에서 첫 번째 레코드의 책갈피를 지정 하는 `COleVariant`입니다.

### <a name="remarks"></a>설명

Microsoft Jet 데이터베이스 엔진은 캐시 범위 내에서 레코드를 요청 하 고 서버에서 캐시 범위를 벗어난 레코드를 요청 합니다.

> [!NOTE]
>  캐시에서 검색 된 레코드는 다른 사용자가 원본 데이터에 대해 동시에 변경한 내용을 반영 하지 않습니다.

관련 내용은 DAO 도움말의 "CacheSize, CacheStart 속성" 항목을 참조 하십시오.

##  <a name="getcurrentindex"></a>CDaoRecordset:: GetCurrentIndex

인덱싱된 테이블 형식 `CDaoRecordset` 개체에서 현재 사용 중인 인덱스를 확인 하려면이 멤버 함수를 호출 합니다.

```
CString GetCurrentIndex();
```

### <a name="return-value"></a>Return Value

테이블 형식 레코드 집합에서 현재 사용 중인 인덱스의 이름을 포함 하는 `CString`입니다. 인덱스를 설정 하지 않은 경우 빈 문자열을 반환 합니다.

### <a name="remarks"></a>설명

이 인덱스는 테이블 형식 레코드 집합의 레코드를 정렬 하는 데 사용 되며 [Seek](#seek) 멤버 함수에서 레코드를 찾는 데 사용 됩니다.

`CDaoRecordset` 개체는 인덱스를 두 개 이상 포함할 수 있지만 한 번에 하나의 인덱스만 사용할 수 있습니다 ( [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 개체에는 여러 인덱스가 정의 되어 있을 수 있음).

관련 정보는 DAO 도움말의 "인덱스 개체" 및 정의 "현재 인덱스" 항목을 참조 하십시오.

##  <a name="getdatecreated"></a>CDaoRecordset:: GetDateCreated

이 멤버 함수를 호출 하 여 기본 테이블이 생성 된 날짜 및 시간을 검색 합니다.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Return Value

기본 테이블을 만든 날짜와 시간을 포함 하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체입니다.

### <a name="remarks"></a>설명

날짜 및 시간 설정은 기본 테이블이 생성 된 컴퓨터에서 파생 됩니다.

관련 내용은 DAO 도움말에서 "DateCreated, LastUpdated 속성" 항목을 참조 하십시오.

##  <a name="getdatelastupdated"></a>CDaoRecordset:: GetDateLastUpdated

이 멤버 함수를 호출 하 여 스키마가 마지막으로 업데이트 된 날짜 및 시간을 검색 합니다.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Return Value

기본 테이블 구조 (스키마)가 마지막으로 업데이트 된 날짜와 시간을 포함 하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체입니다.

### <a name="remarks"></a>설명

날짜 및 시간 설정은 기본 테이블 구조 (스키마)가 마지막으로 업데이트 된 컴퓨터에서 파생 됩니다.

관련 내용은 DAO 도움말에서 "DateCreated, LastUpdated 속성" 항목을 참조 하십시오.

##  <a name="getdefaultdbname"></a>CDaoRecordset:: GetDefaultDBName

이 멤버 함수를 호출 하 여이 레코드 집합에 대 한 데이터베이스의 이름을 확인 합니다.

```
virtual CString GetDefaultDBName();
```

### <a name="return-value"></a>Return Value

이 레코드 집합이 파생 된 데이터베이스의 경로와 이름을 포함 하는 `CString`입니다.

### <a name="remarks"></a>설명

[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)에 대 한 포인터 없이 레코드 집합을 만드는 경우이 경로는 레코드 집합에서 기본 데이터베이스를 여는 데 사용 됩니다. 기본적으로이 함수는 빈 문자열을 반환 합니다. 클래스 마법사는 `CDaoRecordset`에서 새 레코드 집합을 파생 시킬 때이 함수를 만듭니다.

다음 예제에서는 문자열의 이중 백슬래시 (\\\\)를 사용 하는 방법을 보여 줍니다 .이는 문자열을 올바르게 해석 하는 데 필요 합니다.

[!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]

##  <a name="getdefaultsql"></a>CDaoRecordset:: GetDefaultSQL

프레임 워크는이 멤버 함수를 호출 하 여 레코드 집합의 기반이 되는 기본 SQL 문을 가져옵니다.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Return Value

기본 SQL 문을 포함 하는 `CString`입니다.

### <a name="remarks"></a>설명

테이블 이름 또는 SQL **SELECT** 문이 될 수 있습니다.

클래스 마법사를 사용 하 여 레코드 집합 클래스를 선언 하 여 기본 SQL 문을 간접적으로 정의 하 고 클래스 마법사에서이 작업을 수행 합니다.

[Open](#open)에 null sql 문자열을 전달 하는 경우이 함수를 호출 하 여 레코드 집합에 대 한 테이블 이름 또는 sql을 결정 합니다.

##  <a name="geteditmode"></a>CDaoRecordset:: GetEditMode

다음 값 중 하나인 편집 상태를 확인 하려면이 멤버 함수를 호출 합니다.

```
short GetEditMode();
```

### <a name="return-value"></a>Return Value

현재 레코드에 대 한 편집 상태를 나타내는 값을 반환 합니다.

### <a name="remarks"></a>설명

|값|Description|
|-----------|-----------------|
|`dbEditNone`|편집 작업이 진행 되 고 있지 않습니다.|
|`dbEditInProgress`|`Edit`가 호출된 경우|
|`dbEditAdd`|`AddNew`가 호출된 경우|

관련 내용은 DAO 도움말의 "EditMode 속성" 항목을 참조 하십시오.

##  <a name="getfieldcount"></a>CDaoRecordset:: GetFieldCount

이 멤버 함수를 호출 하 여 레코드 집합에 정의 된 필드 (열) 수를 검색 합니다.

```
short GetFieldCount();
```

### <a name="return-value"></a>Return Value

레코드 집합의 필드 수입니다.

### <a name="remarks"></a>설명

관련 정보는 DAO 도움말의 "Count 속성" 항목을 참조 하십시오.

##  <a name="getfieldinfo"></a>CDaoRecordset:: GetFieldInfo

이 멤버 함수를 호출 하 여 레코드 집합의 필드에 대 한 정보를 가져옵니다.

```
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
인덱스를 기준으로 조회 하기 위해 레코드 집합의 Fields 컬렉션에 있는 미리 정의 된 필드의 인덱스 (0부터 시작)입니다.

*fieldinfo*<br/>
[CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조체에 대 한 참조입니다.

*dwInfoOptions*<br/>
검색할 레코드 집합에 대 한 정보를 지정 하는 옵션입니다. 사용할 수 있는 옵션은 함수에서 반환 하는 항목과 함께 여기에 나열 됩니다. 최상의 성능을 위해 필요한 정보 수준만 검색 합니다.

- `AFX_DAO_PRIMARY_INFO` (기본값) 이름, 형식, 크기, 특성

- 기본 정보를 더하기: 서 수 위치, 필수, 0 길이 허용, 데이터 정렬 순서, 외래 이름, 원본 필드, 원본 테이블 `AFX_DAO_SECONDARY_INFO`

- 기본 및 보조 정보를 비롯 하 여 기본 값, 유효성 검사 규칙, 유효성 검사 텍스트 `AFX_DAO_ALL_INFO`

*lpszName*<br/>
필드 이름입니다.

### <a name="remarks"></a>설명

한 버전의 함수를 사용 하 여 인덱스를 기준으로 필드를 조회할 수 있습니다. 다른 버전에서는 이름을 기준으로 필드를 조회할 수 있습니다.

반환 되는 정보에 대 한 설명은 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조를 참조 하세요. 이 구조에는 위의 정보 항목에 해당 하는 멤버가 포함 되어 *있습니다.* 한 수준에서 정보를 요청 하는 경우 모든 이전 수준에 대 한 정보도 얻을 수 있습니다.

관련 내용은 DAO 도움말의 "Attributes 속성" 항목을 참조 하십시오.

##  <a name="getfieldvalue"></a>CDaoRecordset:: GetFieldValue

이 멤버 함수를 호출 하 여 레코드 집합의 데이터를 검색 합니다.

```
virtual void GetFieldValue(
    LPCTSTR lpszName,
    COleVariant& varValue);

virtual void GetFieldValue(
    int nIndex,
    COleVariant& varValue);

virtual COleVariant GetFieldValue(LPCTSTR lpszName);
virtual COleVariant GetFieldValue(int nIndex);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
필드 이름을 포함 하는 문자열에 대 한 포인터입니다.

*varValue*<br/>
필드의 값을 저장 하는 `COleVariant` 개체에 대 한 참조입니다.

*nIndex*<br/>
인덱스를 기준으로 조회 하기 위해 레코드 집합의 Fields 컬렉션에 있는 필드의 인덱스 (0부터 시작)입니다.

### <a name="return-value"></a>Return Value

값을 반환 하는 두 가지 버전의 `GetFieldValue`는 필드 값을 포함 하는 [COleVariant](../../mfc/reference/colevariant-class.md) 개체를 반환 합니다.

### <a name="remarks"></a>설명

이름 또는 서 수 위치를 기준으로 필드를 조회할 수 있습니다.

> [!NOTE]
>  `COleVariant` 개체를 반환 하는 버전을 호출 하는 대신 `COleVariant` 개체 참조를 매개 변수로 사용 하는이 멤버 함수의 버전 중 하나를 호출 하는 것이 더 효율적입니다. 이 함수의 두 번째 버전은 이전 버전과의 호환성을 위해 유지 됩니다.

`GetFieldValue` 및 [SetFieldValue](#setfieldvalue) 를 사용 하 여 [DoFieldExchange](#dofieldexchange) 메커니즘을 사용 하 여 열을 정적으로 바인딩하지 않고 런타임에 필드를 동적으로 바인딩합니다.

`GetFieldValue` 및 `DoFieldExchange` 메커니즘을 결합 하 여 성능을 향상 시킬 수 있습니다. 예를 들어 `GetFieldValue`를 사용 하 여 요청 시에만 필요한 값을 검색 하 고 해당 호출을 인터페이스의 "추가 정보" 단추에 할당 합니다.

관련 내용은 DAO 도움말의 "Field Object" 및 "Value Property" 항목을 참조 하십시오.

##  <a name="getindexcount"></a>CDaoRecordset:: GetIndexCount

이 멤버 함수를 호출 하 여 테이블 형식 레코드 집합에서 사용할 수 있는 인덱스 수를 확인 합니다.

```
short GetIndexCount();
```

### <a name="return-value"></a>Return Value

테이블 형식 레코드 집합의 인덱스 수입니다.

### <a name="remarks"></a>설명

`GetIndexCount`은 레코드 집합의 모든 인덱스를 반복 하는 데 유용 합니다. 이러한 목적을 위해 [Getindexinfo](#getindexinfo)와 함께 `GetIndexCount`를 사용 합니다. 다이너셋 형식 또는 스냅숏 형식 레코드 집합에서이 멤버 함수를 호출 하는 경우 MFC는 예외를 throw 합니다.

관련 내용은 DAO 도움말의 "Attributes 속성" 항목을 참조 하십시오.

##  <a name="getindexinfo"></a>CDaoRecordset:: GetIndexInfo

이 멤버 함수를 호출 하 여 레코드 집합의 기본 테이블에 정의 된 인덱스에 대 한 다양 한 종류의 정보를 얻을 수 있습니다.

```
void GetIndexInfo(
    int nIndex,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetIndexInfo(
    LPCTSTR lpszName,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
숫자 위치로 조회 하기 위해 테이블의 인덱스 컬렉션에 있는 인덱스 (0부터 시작)입니다.

*indexinfo*<br/>
[CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조체에 대 한 참조입니다.

*dwInfoOptions*<br/>
검색할 인덱스에 대 한 정보를 지정 하는 옵션입니다. 사용할 수 있는 옵션은 함수에서 반환 하는 항목과 함께 여기에 나열 됩니다. 최상의 성능을 위해 필요한 정보 수준만 검색 합니다.

- `AFX_DAO_PRIMARY_INFO` (기본값) 이름, 필드 정보, 필드

- 주 정보를 포함 하는 기본 정보를 포함 하는 `AFX_DAO_SECONDARY_INFO` 기본, 고유, 클러스터형, IgnoreNulls, 필수, 외래

- 기본 및 보조 정보를 포함 하는 `AFX_DAO_ALL_INFO` 및: 고유 카운트

*lpszName*<br/>
이름으로 조회할 인덱스 개체의 이름에 대 한 포인터입니다.

### <a name="remarks"></a>설명

한 버전의 함수를 사용 하 여 컬렉션에서 인덱스를 찾을 수 있습니다. 다른 버전에서는 이름을 기준으로 인덱스를 조회할 수 있습니다.

반환 되는 정보에 대 한 설명은 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조를 참조 하세요. 이 구조에는 위의 정보 항목에 해당 하는 멤버가 포함 되어 *있습니다.* 한 수준에서 정보를 요청 하는 경우 모든 이전 수준에 대 한 정보도 얻을 수 있습니다.

관련 내용은 DAO 도움말의 "Attributes 속성" 항목을 참조 하십시오.

##  <a name="getlastmodifiedbookmark"></a>CDaoRecordset:: GetLastModifiedBookmark

가장 최근에 추가 되었거나 업데이트 된 레코드의 책갈피를 검색 하려면이 멤버 함수를 호출 합니다.

```
COleVariant GetLastModifiedBookmark();
```

### <a name="return-value"></a>Return Value

가장 최근에 추가 되거나 변경 된 레코드를 나타내는 책갈피를 포함 하는 `COleVariant`입니다.

### <a name="remarks"></a>설명

레코드 집합 개체를 만들거나 열 때 각 레코드는 해당 레코드를 지 원하는 경우 이미 고유한 책갈피를 가집니다. [Getbookmark](#getbookmark) 를 호출 하 여 레코드 집합에서 책갈피를 지원 하는지 확인 합니다. 레코드 집합에서 책갈피를 지원 하지 않는 경우 `CDaoException`이 throw 됩니다.

레코드를 추가 하면 레코드 집합의 끝에 표시 되며 현재 레코드가 아닙니다. 새 레코드를 최신 레코드로 만들려면 `GetLastModifiedBookmark`를 호출한 다음 `SetBookmark`를 호출 하 여 새로 추가 된 레코드로 돌아갑니다.

관련 내용은 DAO 도움말의 "LastModified 속성" 항목을 참조 하십시오.

##  <a name="getlockingmode"></a>CDaoRecordset:: GetLockingMode

이 멤버 함수를 호출 하 여 레코드 집합에 적용 되는 잠금 유형을 확인 합니다.

```
BOOL GetLockingMode();
```

### <a name="return-value"></a>Return Value

잠금 유형이 비관적 이면 0이 아닌 값이 고, 낙관적 레코드 잠금의 경우 0입니다.

### <a name="remarks"></a>설명

비관적 잠금이 적용 되는 경우 편집 하는 레코드를 포함 하는 데이터 페이지는 [편집](#edit) 멤버 함수를 호출 하는 즉시 잠깁니다. [Update](#update) 또는 [Close](#close) 멤버 함수를 호출 하거나 이동 또는 찾기 작업 중 하나를 호출 하면 페이지 잠금이 해제 됩니다.

낙관적 잠금이 적용 되는 경우 레코드를 포함 하는 데이터 페이지는 `Update` 멤버 함수를 사용 하 여 레코드를 업데이트 하는 동안에만 잠깁니다.

ODBC 데이터 원본으로 작업할 때 잠금 모드는 항상 낙관적입니다.

관련 내용은 DAO 도움말의 "LockEdits 속성" 및 "다중 사용자 응용 프로그램의 잠금 동작" 항목을 참조 하십시오.

##  <a name="getname"></a>CDaoRecordset:: GetName

이 멤버 함수를 호출 하 여 레코드 집합의 이름을 검색 합니다.

```
CString GetName();
```

### <a name="return-value"></a>Return Value

레코드 집합의 이름을 포함 하는 `CString`입니다.

### <a name="remarks"></a>설명

레코드 집합의 이름은 문자로 시작 해야 하며 최대 40 자를 포함할 수 있습니다. 숫자 및 밑줄 문자를 포함할 수 있지만 문장 부호 또는 공백을 포함할 수 없습니다.

관련 내용은 DAO 도움말의 "이름 속성" 항목을 참조 하십시오.

##  <a name="getparamvalue"></a>CDaoRecordset:: GetParamValue

이 멤버 함수를 호출 하 여 기본 DAOParameter 개체에 저장 된 지정 된 매개 변수의 현재 값을 검색 합니다.

```
virtual COleVariant GetParamValue(int nIndex);
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
기본 DAOParameter 개체에 있는 매개 변수의 숫자 위치입니다.

*lpszName*<br/>
원하는 값을 가진 매개 변수의 이름입니다.

### <a name="return-value"></a>Return Value

매개 변수의 값을 포함 하는 [COleVariant](../../mfc/reference/colevariant-class.md) 클래스의 개체입니다.

### <a name="remarks"></a>설명

이름 또는 컬렉션의 숫자 위치를 사용 하 여 매개 변수에 액세스할 수 있습니다.

관련 정보는 DAO 도움말의 "매개 변수 개체" 항목을 참조 하십시오.

##  <a name="getpercentposition"></a>CDaoRecordset:: GetPercentPosition

다이너셋 형식 또는 스냅숏 형식 레코드 집합으로 작업 하는 경우 레코드 집합을 완전히 채우기 전에 `GetPercentPosition`를 호출 하는 경우에는 [Getrecordcount](#getrecordcount)를 호출 하 여 표시 된 것 처럼 액세스 하는 레코드의 수를 기준으로 이동 합니다.

```
float GetPercentPosition();
```

### <a name="return-value"></a>Return Value

레코드 집합의 레코드에 대 한 백분율을 기준으로 레코드 집합 개체에서 현재 레코드의 대략적인 위치를 나타내는 0에서 100 사이의 숫자입니다.

### <a name="remarks"></a>설명

[MoveLast](#movelast) 를 호출 하 여 마지막 레코드로 이동 하 여 모든 레코드 집합의 채우기를 완료할 수 있지만이 경우에는 상당한 시간이 걸릴 수 있습니다.

인덱스가 없는 테이블을 포함 하 여 세 가지 유형의 레코드 집합 개체에 대해 `GetPercentPosition`를 호출할 수 있습니다. 그러나 전방 전용 스크롤 스냅숏이 나 외부 데이터베이스에 대 한 통과 쿼리에서 열린 레코드 집합에서 `GetPercentPosition`를 호출할 수 없습니다. 현재 레코드가 없거나 현재 레코드가 삭제 된 경우 `CDaoException` throw 됩니다.

관련 내용은 DAO 도움말의 "PercentPosition 속성" 항목을 참조 하십시오.

##  <a name="getrecordcount"></a>CDaoRecordset:: GetRecordCount

이 멤버 함수를 호출 하 여 액세스 한 레코드 집합의 레코드 수를 확인 합니다.

```
long GetRecordCount();
```

### <a name="return-value"></a>Return Value

레코드 집합 개체에서 액세스 한 레코드 수를 반환 합니다.

### <a name="remarks"></a>설명

모든 레코드에 액세스할 때까지 `GetRecordCount`는 다이너셋 형식 또는 스냅숏 형식 레코드 집합에 포함 된 레코드 수를 나타내지 않습니다. 이 멤버 함수 호출은 완료 하는 데 상당한 시간이 걸릴 수 있습니다.

마지막 레코드에 액세스 한 후에는 반환 값이 레코드 집합에서 삭제 취소 된 레코드의 총 수를 나타냅니다. 마지막 레코드를 강제로 액세스 하려면 레코드 집합에 대 한 `MoveLast` 또는 `FindLast` 멤버 함수를 호출 합니다. SQL 카운트를 사용 하 여 쿼리에서 반환할 대략적인 레코드 수를 결정할 수도 있습니다.

응용 프로그램이 다이너셋 형식의 레코드 집합에서 레코드를 삭제 하면 `GetRecordCount`의 반환 값이 감소 합니다. 그러나 다른 사용자가 삭제 한 레코드는 현재 레코드가 삭제 된 레코드에 배치 될 때까지 `GetRecordCount` 반영 되지 않습니다. 레코드 수에 영향을 주는 트랜잭션을 실행 하 고 트랜잭션을 롤백하는 경우 `GetRecordCount`는 남은 레코드의 실제 수를 반영 하지 않습니다.

스냅숏 형식의 레코드 집합에서 `GetRecordCount` 값은 기본 테이블의 변경 내용에 의해 영향을 받지 않습니다.

테이블 형식 레코드 집합에서 `GetRecordCount` 값은 테이블의 대략적인 레코드 수를 반영 하며 테이블 레코드가 추가 및 삭제 되는 즉시 영향을 받습니다.

레코드가 없는 레코드 집합은 값 0을 반환 합니다. 연결 된 테이블 또는 ODBC 데이터베이스로 작업할 때 `GetRecordCount` 항상-1을 반환 합니다. 레코드 집합에 대해 `Requery` 멤버 함수를 호출 하면 쿼리를 다시 실행 한 것 처럼 `GetRecordCount` 값이 다시 설정 됩니다.

관련 정보는 DAO 도움말의 "RecordCount 속성" 항목을 참조 하십시오.

##  <a name="getsql"></a>CDaoRecordset:: GetSQL

이 멤버 함수를 호출 하 여 레코드를 열 때 레코드 집합의 레코드를 선택 하는 데 사용 된 SQL 문을 가져옵니다.

```
CString GetSQL() const;
```

### <a name="return-value"></a>Return Value

SQL 문을 포함 하는 `CString`입니다.

### <a name="remarks"></a>설명

이는 일반적으로 SQL **SELECT** 문입니다.

`GetSQL`에서 반환 되는 문자열은 일반적으로 *lpszSQL* 매개 변수에서 레코드 집합에 전달 했을 때 [Open](#open) 멤버 함수에 전달 했을 수 있는 문자열과 다릅니다. 이는 레코드 집합이 `Open`에 전달 된 내용, 클래스 마법사를 사용 하 여 지정한 내용 및 [m_strFilter](#m_strfilter) 및 [m_strSort](#m_strsort) 데이터 멤버에 지정 된 내용에 따라 전체 SQL 문을 생성 하기 때문입니다.

> [!NOTE]
>  `Open`를 호출한 후에만이 멤버 함수를 호출 합니다.

관련 내용은 DAO 도움말의 "SQL 속성" 항목을 참조 하십시오.

##  <a name="gettype"></a>CDaoRecordset:: GetType

레코드 집합 개체의 형식을 확인 하기 위해 레코드 집합을 연 후이 멤버 함수를 호출 합니다.

```
short GetType();
```

### <a name="return-value"></a>Return Value

레코드 집합의 유형을 나타내는 다음 값 중 하나입니다.

- `dbOpenTable` 테이블 형식 레코드 집합

- `dbOpenDynaset` 다이너셋 형식 레코드 집합

- `dbOpenSnapshot` 스냅숏 형식 레코드 집합

### <a name="remarks"></a>설명

관련 내용은 DAO 도움말의 "형식 속성" 항목을 참조 하십시오.

##  <a name="getvalidationrule"></a>CDaoRecordset:: GetValidationRule

이 멤버 함수를 호출 하 여 데이터 유효성 검사에 사용 되는 규칙을 결정 합니다.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Return Value

레코드의 데이터를 변경 하거나 테이블에 추가 하는 데 해당 데이터의 유효성을 검사 하는 값을 포함 하는 `CString` 개체입니다.

### <a name="remarks"></a>설명

이 규칙은 텍스트 기반 이며 기본 테이블이 변경 될 때마다 적용 됩니다. 데이터가 유효 하지 않은 경우 MFC는 예외를 throw 합니다. 반환 된 오류 메시지는 기본 필드 개체의 ValidationText 속성 (지정 된 경우) 또는 기본 필드 개체의 ValidationRule 속성으로 지정 된 식의 텍스트입니다. [GetValidationText](#getvalidationtext) 를 호출 하 여 오류 메시지의 텍스트를 가져올 수 있습니다.

예를 들어 일이 필요한 레코드의 필드에는 "DAY BETWEEN 1에서 31"과 같은 유효성 검사 규칙이 있을 수 있습니다.

관련 내용은 DAO 도움말의 "ValidationRule 속성" 항목을 참조 하십시오.

##  <a name="getvalidationtext"></a>CDaoRecordset:: GetValidationText

기본 필드 개체의 ValidationText 속성 텍스트를 검색 하려면이 멤버 함수를 호출 합니다.

```
CString GetValidationText();
```

### <a name="return-value"></a>Return Value

필드 값이 내부 필드 개체의 유효성 검사 규칙을 충족 하지 않는 경우 표시 되는 메시지의 텍스트를 포함 하는 `CString` 개체입니다.

### <a name="remarks"></a>설명

관련 내용은 DAO 도움말의 "ValidationText 속성" 항목을 참조 하십시오.

##  <a name="isbof"></a>CDaoRecordset:: IsBOF

레코드에서 레코드로 이동 하기 전에이 멤버 함수를 호출 하 여 레코드 집합의 첫 번째 레코드 앞에 있는지 알아보세요.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Return Value

레코드 집합이 레코드를 포함 하지 않거나 첫 번째 레코드 앞으로 스크롤한 경우 0이 아닌 값입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`IsEOF`와 함께 `IsBOF`를 호출 하 여 레코드 집합에 레코드가 포함 되어 있는지 아니면 비어 있는지 확인할 수도 있습니다. `Open`호출 하는 즉시 레코드 집합에 레코드가 포함 되어 있지 않은 경우 `IsBOF`은 0이 아닌 값을 반환 합니다. 하나 이상의 레코드를 포함 하는 레코드 집합을 열 때 첫 번째 레코드는 현재 레코드이 고 `IsBOF`는 0을 반환 합니다.

첫 번째 레코드가 현재 레코드이 고 `MovePrev`를 호출 하는 경우 `IsBOF` 이후에 0이 아닌 값이 반환 됩니다. `IsBOF`에서 0이 아닌 값을 반환 하 고 `MovePrev`를 호출 하면 예외가 throw 됩니다. `IsBOF`에서 0이 아닌 값을 반환 하는 경우 현재 레코드는 정의 되지 않으며 현재 레코드를 필요로 하는 모든 작업에서 예외가 발생 합니다.

`IsBOF` 및 `IsEOF` 설정에 대 한 특정 메서드의 효과:

- `Open*`를 내부적으로 호출 하면 `MoveFirst`를 호출 하 여 레코드 집합의 첫 번째 레코드를 현재 레코드로 만듭니다. 따라서 빈 레코드 집합에 대 한 `Open`를 호출 하면 `IsBOF` 및 `IsEOF`에서 0이 아닌 값이 반환 됩니다. 실패 한 `MoveFirst` 또는 `MoveLast` 호출의 동작은 다음 표를 참조 하세요.)

- 레코드를 성공적으로 찾은 모든 이동 작업은 `IsBOF`와 `IsEOF` 모두 0을 반환 합니다.

- `AddNew` 호출 후에 새 레코드를 삽입 하는 `Update` 호출을 수행 하면 `IsBOF` 0이 반환 되 고 `IsEOF`이 이미 0이 아닌 경우에만 발생 합니다. `IsEOF` 상태는 항상 변경 되지 않은 상태로 유지 됩니다. Microsoft Jet 데이터베이스 엔진에서 정의한 대로 빈 레코드 집합의 현재 레코드 포인터는 파일의 끝에 있으므로 현재 레코드 뒤에 새 레코드가 삽입 됩니다.

- `Delete` 호출은 레코드 집합에서 남은 레코드만 제거 해도 `IsBOF` 또는 `IsEOF`값이 변경 되지 않습니다.

이 표에서는 `IsBOF`/ `IsEOF`의 여러 조합에서 허용 되는 이동 작업을 보여 줍니다.

||MoveFirst, MoveLast|MovePrev<br /><br /> Move < 0|0 이동|MoveNext<br /><br /> Move > 0|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`= 0이 아닌 값<br /><br /> `IsEOF`=0|허용됨|예외|예외|허용됨|
|`IsBOF`=0,<br /><br /> `IsEOF`= 0이 아닌 값|허용됨|허용됨|예외|예외|
|둘 다 0이 아닙니다.|예외|예외|예외|예외|
|0 모두|허용됨|허용됨|허용됨|허용됨|

이동 작업을 허용 하는 것은 작업에서 레코드를 성공적으로 찾으려고 한다는 의미는 아닙니다. 단지 지정 된 이동 작업을 수행 하려는 시도가 허용 되 고 예외를 생성 하지 않음을 나타냅니다. `IsBOF` 및 `IsEOF` 멤버 함수의 값은 시도한 이동의 결과로 변경 될 수 있습니다.

`IsBOF` 및 `IsEOF` 설정의 값에 대 한 레코드를 찾을 수 없는 이동 작업의 효과는 다음 표에 나와 있습니다.

||IsBOF|IsEOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|0이 아닌|0이 아닌|
|`Move` 0|변경 내용 없음|변경 내용 없음|
|`MovePrev`, `Move` < 0|0이 아닌|변경 내용 없음|
|`MoveNext`, `Move` > 0|변경 내용 없음|0이 아닌|

관련 내용은 DAO 도움말의 "BOF, EOF 속성" 항목을 참조 하십시오.

##  <a name="isdeleted"></a>CDaoRecordset:: IsDeleted

현재 레코드가 삭제 되었는지 여부를 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Return Value

레코드 집합을 삭제 된 레코드에 배치 하는 경우 0이 아닙니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

레코드로 스크롤하고 `IsDeleted` TRUE (0이 아님)를 반환 하는 경우 다른 레코드 집합 작업을 수행 하기 전에 다른 레코드로 스크롤해야 합니다.

> [!NOTE]
>  스냅숏 또는 테이블 형식 레코드 집합에서 레코드에 대 한 삭제 된 상태를 확인할 필요가 없습니다. 레코드는 스냅숏에서 삭제할 수 없기 때문에 `IsDeleted`를 호출할 필요가 없습니다. 테이블 형식 레코드 집합의 경우 삭제 된 레코드는 실제로 레코드 집합에서 제거 됩니다. 사용자, 다른 사용자 또는 다른 레코드 집합에서 레코드를 삭제 한 후에는 해당 레코드로 다시 스크롤할 수 없습니다. 따라서 `IsDeleted`를 호출할 필요가 없습니다.

다이너셋에서 레코드를 삭제 하면 해당 레코드는 레코드 집합에서 제거 되 고 해당 레코드로 다시 스크롤할 수 없습니다. 그러나 다이너셋의 레코드가 동일한 테이블을 기반으로 하는 다른 사용자 또는 다른 레코드 집합에서 삭제 되는 경우 나중에 해당 레코드로 스크롤하면 `IsDeleted`에서 TRUE를 반환 합니다.

관련 정보는 DAO 도움말의 "Delete 메서드", "LastModified 속성" 및 "EditMode 속성" 항목을 참조 하십시오.

##  <a name="iseof"></a>CDaoRecordset:: IsEOF

레코드에서 레코드로 스크롤할 때이 멤버 함수를 호출 하 여 레코드 집합의 마지막 레코드를 벗어났는지 여부를 알아보세요.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Return Value

레코드 집합이 레코드를 포함 하지 않거나 마지막 레코드를 넘어 스크롤 된 경우 0이 아닌 값입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`IsEOF`를 호출 하 여 레코드 집합이 레코드를 포함 하거나 비어 있는지 확인할 수도 있습니다. `Open`호출 하는 즉시 레코드 집합에 레코드가 포함 되어 있지 않은 경우 `IsEOF`은 0이 아닌 값을 반환 합니다. 하나 이상의 레코드를 포함 하는 레코드 집합을 열 때 첫 번째 레코드는 현재 레코드이 고 `IsEOF`는 0을 반환 합니다.

`MoveNext`를 호출할 때 마지막 레코드가 현재 레코드 이면 `IsEOF`는 0이 아닌 값을 반환 합니다. `IsEOF`에서 0이 아닌 값을 반환 하 고 `MoveNext`를 호출 하면 예외가 throw 됩니다. `IsEOF`에서 0이 아닌 값을 반환 하는 경우 현재 레코드는 정의 되지 않으며 현재 레코드를 필요로 하는 모든 작업에서 예외가 발생 합니다.

`IsBOF` 및 `IsEOF` 설정에 대 한 특정 메서드의 효과:

- `Open`를 내부적으로 호출 하면 `MoveFirst`를 호출 하 여 레코드 집합의 첫 번째 레코드를 현재 레코드로 만듭니다. 따라서 빈 레코드 집합에 대 한 `Open`를 호출 하면 `IsBOF` 및 `IsEOF`에서 0이 아닌 값이 반환 됩니다. 실패 한 `MoveFirst` 호출의 동작은 다음 표를 참조 하세요.

- 레코드를 성공적으로 찾은 모든 이동 작업은 `IsBOF`와 `IsEOF` 모두 0을 반환 합니다.

- `AddNew` 호출 후에 새 레코드를 삽입 하는 `Update` 호출을 수행 하면 `IsBOF` 0이 반환 되 고 `IsEOF`이 이미 0이 아닌 경우에만 발생 합니다. `IsEOF` 상태는 항상 변경 되지 않은 상태로 유지 됩니다. Microsoft Jet 데이터베이스 엔진에서 정의한 대로 빈 레코드 집합의 현재 레코드 포인터는 파일의 끝에 있으므로 현재 레코드 뒤에 새 레코드가 삽입 됩니다.

- `Delete` 호출은 레코드 집합에서 남은 레코드만 제거 해도 `IsBOF` 또는 `IsEOF`값이 변경 되지 않습니다.

이 표에서는 `IsBOF`/ `IsEOF`의 여러 조합에서 허용 되는 이동 작업을 보여 줍니다.

||MoveFirst, MoveLast|MovePrev<br /><br /> Move < 0|0 이동|MoveNext<br /><br /> Move > 0|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`= 0이 아닌 값<br /><br /> `IsEOF`=0|허용됨|예외|예외|허용됨|
|`IsBOF`=0,<br /><br /> `IsEOF`= 0이 아닌 값|허용됨|허용됨|예외|예외|
|둘 다 0이 아닙니다.|예외|예외|예외|예외|
|0 모두|허용됨|허용됨|허용됨|허용됨|

이동 작업을 허용 하는 것은 작업에서 레코드를 성공적으로 찾으려고 한다는 의미는 아닙니다. 단지 지정 된 이동 작업을 수행 하려는 시도가 허용 되 고 예외를 생성 하지 않음을 나타냅니다. `IsBOF` 및 `IsEOF` 멤버 함수의 값은 시도한 이동의 결과로 변경 될 수 있습니다.

`IsBOF` 및 `IsEOF` 설정의 값에 대 한 레코드를 찾을 수 없는 이동 작업의 효과는 다음 표에 나와 있습니다.

||IsBOF|IsEOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|0이 아닌|0이 아닌|
|`Move` 0|변경 내용 없음|변경 내용 없음|
|`MovePrev`, `Move` < 0|0이 아닌|변경 내용 없음|
|`MoveNext`, `Move` > 0|변경 내용 없음|0이 아닌|

관련 내용은 DAO 도움말의 "BOF, EOF 속성" 항목을 참조 하십시오.

##  <a name="isfielddirty"></a>CDaoRecordset:: IsFieldDirty

이 멤버 함수를 호출 하 여 다이너셋의 지정 된 필드 데이터 멤버가 "더티" (변경 됨)로 플래그가 지정 되었는지 여부를 확인 합니다.

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
상태를 확인할 필드 데이터 멤버에 대 한 포인터 이거나, 필드가 커밋되지 않았는지 여부를 확인 하는 NULL입니다.

### <a name="return-value"></a>Return Value

지정 된 필드 데이터 멤버가 커밋되지 않은 것으로 플래그가 지정 되 면 0이 아닌 값입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`Edit` 또는 `AddNew`를 호출 하 여 `CDaoRecordset`의 `Update` 멤버 함수를 호출 하 여 현재 레코드가 업데이트 되는 경우 모든 더티 필드 데이터 멤버의 데이터는 데이터 원본에 대 한 레코드에 전송 됩니다. 이 정보를 사용 하 여 필드 데이터 멤버에 플래그를 추가 하 여 데이터 원본에 기록 되지 않도록 열을 표시 하는 등의 추가 단계를 수행할 수 있습니다.

`IsFieldDirty`는 `DoFieldExchange`를 통해 구현 됩니다.

##  <a name="isfieldnull"></a>CDaoRecordset:: IsFieldNull

이 멤버 함수를 호출 하 여 레코드 집합의 지정 된 필드 데이터 멤버에 Null로 플래그가 지정 되었는지 여부를 확인 합니다.

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
상태를 확인할 필드 데이터 멤버에 대 한 포인터 이거나, 필드가 Null 인지 여부를 확인 하는 NULL입니다.

### <a name="return-value"></a>Return Value

지정 된 필드 데이터 멤버가 Null로 플래그가 지정 된 경우 0이 아닙니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

(데이터베이스 용어에서 Null은 "값을 갖지 않음"을 의미 하 고의 C++null과 같지 않습니다.) 필드 데이터 멤버가 Null로 플래그가 지정 된 경우 값이 없는 현재 레코드의 열로 해석 됩니다.

> [!NOTE]
>  특정 상황에서는 다음 코드 예제에 나와 있는 것 처럼 `IsFieldNull`를 사용 하는 것이 비효율적 일 수 있습니다.

[!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]

> [!NOTE]
>  `CDaoRecordset`에서 파생 하지 않고 동적 레코드 바인딩을 사용 하는 경우 예제와 같이 VT_NULL를 사용 해야 합니다.

##  <a name="isfieldnullable"></a>CDaoRecordset:: IsFieldNullable

지정 된 필드 데이터 멤버가 "nullable" (Null 값으로 설정할 수 있음) 인지 여부를 확인 하려면이 멤버 함수를 호출 합니다. C++ Null은 null과 같지 않습니다 .이는 데이터베이스 용어에서 "값을 갖지 않음"을 의미 합니다.

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
상태를 확인할 필드 데이터 멤버에 대 한 포인터 이거나, 필드가 Null 인지 여부를 확인 하는 NULL입니다.

### <a name="return-value"></a>Return Value

지정 된 필드 데이터 멤버를 Null로 설정할 수 있는 경우 0이 아닙니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

Null 일 수 없는 필드에는 값이 있어야 합니다. 레코드를 추가 하거나 업데이트할 때 이러한 필드를 Null로 설정 하려고 하면 데이터 원본에서 추가 또는 업데이트를 거부 하 고 `Update`에서 예외를 throw 합니다. `SetFieldNull`를 호출 하는 경우를 제외 하 고 `Update`를 호출할 때 예외가 발생 합니다.

##  <a name="isopen"></a>CDaoRecordset:: IsOpen

이 멤버 함수를 호출 하 여 레코드 집합이 열려 있는지 확인 합니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Return Value

레코드 집합 개체의 `Open` 또는 `Requery` 멤버 함수가 이전에 호출 되었고 레코드 집합이 닫히지 않은 경우 0이 아닙니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

##  <a name="m_bcheckcachefordirtyfields"></a>CDaoRecordset:: m_bCheckCacheForDirtyFields

캐시 된 필드가 더티 (변경 됨) 및 Null로 자동으로 표시 되는지 여부를 나타내는 플래그를 포함 합니다.

### <a name="remarks"></a>설명

플래그의 기본값은 TRUE입니다. 이 데이터 멤버의 설정은 전체 이중 버퍼링 메커니즘을 제어 합니다. 플래그를 TRUE로 설정 하면 DFX 메커니즘을 사용 하 여 필드 별로 캐싱을 해제할 수 있습니다. 플래그를 FALSE로 설정한 경우 `SetFieldDirty`를 호출 하 고 직접 `SetFieldNull` 해야 합니다.

`Open`를 호출 하기 전에이 데이터 멤버를 설정 하십시오. 이 메커니즘은 사용 편의성을 위해 주로 사용 됩니다. 변경이 수행 되 면 필드의 이중 버퍼링 때문에 성능이 느릴 수 있습니다.

##  <a name="m_nfields"></a>CDaoRecordset:: m_nFields

레코드 집합 클래스의 필드 데이터 멤버 수와 데이터 원본의 레코드 집합에서 선택한 열 수를 포함 합니다.

### <a name="remarks"></a>설명

레코드 집합 클래스의 생성자는 올바른 수의 정적 바인딩 필드를 사용 하 여 `m_nFields`을 초기화 해야 합니다. 클래스 마법사는이 초기화를 사용 하 여 레코드 집합 클래스를 선언할 때이 초기화를 작성 합니다. 수동으로 작성할 수도 있습니다.

프레임 워크는이 숫자를 사용 하 여 필드 데이터 멤버와 데이터 소스에 있는 현재 레코드의 해당 열 간의 상호 작용을 관리 합니다.

> [!NOTE]
>  이 숫자는 `CDaoFieldExchange::outputColumn`매개 변수를 사용 하 여 `SetFieldType`를 호출한 후 `DoFieldExchange`에 등록 된 출력 열 수와 일치 해야 합니다.

`CDaoRecordset::GetFieldValue` 및 `CDaoRecordset::SetFieldValue`를 통해 열을 동적으로 바인딩할 수 있습니다. 이렇게 하면 `DoFieldExchange` 멤버 함수의 DFX 함수 호출 수를 반영 하기 위해 `m_nFields` 수를 증가 시킬 필요가 없습니다.

##  <a name="m_nparams"></a>CDaoRecordset:: m_nParams

레코드 집합의 쿼리와 함께 전달 되는 매개 변수의 수와 같은 레코드 집합 클래스의 매개 변수 데이터 멤버 수를 포함 합니다.

### <a name="remarks"></a>설명

레코드 집합 클래스에 매개 변수 데이터 멤버가 있는 경우 클래스의 생성자는 올바른 수를 사용 하 여 *m_nParams* 을 초기화 해야 합니다. *M_nParams* 기본값은 0입니다. 수동으로 수행 해야 하는 매개 변수 데이터 멤버를 추가 하는 경우에는 매개 변수 수를 반영 하도록 클래스 생성자에서 초기화를 수동으로 추가 해야 합니다 .이 값은 적어도 *m_strFilter* 또는 *m_strSort* 문자열의 ' ' 자리 표시자 수 만큼 커야 합니다.

프레임 워크는이 숫자를 사용 하 여 레코드 집합의 쿼리를 매개 변수화 합니다.

> [!NOTE]
>  이 숫자는 `CFieldExchange::param`매개 변수를 사용 하 여 `SetFieldType`를 호출한 후 `DoFieldExchange`에 등록 된 "params"의 수와 일치 해야 합니다.

관련 정보는 DAO 도움말의 "매개 변수 개체" 항목을 참조 하십시오.

##  <a name="m_pdaorecordset"></a>CDaoRecordset:: m_pDAORecordset

`CDaoRecordset` 개체의 내부에 있는 DAO 레코드 집합 개체에 대 한 OLE 인터페이스에 대 한 포인터를 포함 합니다.

### <a name="remarks"></a>설명

DAO 인터페이스에 직접 액세스 해야 하는 경우이 포인터를 사용 합니다.

관련 내용은 DAO 도움말의 "레코드 집합 개체" 항목을 참조 하십시오.

##  <a name="m_pdatabase"></a>CDaoRecordset:: m_pDatabase

레코드 집합을 데이터 소스에 연결 하는 `CDaoDatabase` 개체에 대 한 포인터를 포함 합니다.

### <a name="remarks"></a>설명

이 변수는 두 가지 방법으로 설정 됩니다. 일반적으로 레코드 집합 개체를 생성할 때 이미 열려 있는 `CDaoDatabase` 개체에 대 한 포인터를 전달 합니다. 대신 NULL을 전달 하면 `CDaoRecordset` `CDaoDatabase` 개체를 만들어 엽니다. 두 경우 모두 `CDaoRecordset`는이 변수에 포인터를 저장 합니다.

일반적으로 `m_pDatabase`에 저장 된 포인터를 직접 사용 하지 않아도 됩니다. 그러나 `CDaoRecordset`에 대 한 고유한 확장을 작성 하는 경우 포인터를 사용 해야 할 수 있습니다. 예를 들어 고유한 `CDaoException`를 throw 하는 경우 포인터가 필요할 수 있습니다.

관련 내용은 DAO 도움말의 "데이터베이스 개체" 항목을 참조 하십시오.

##  <a name="m_strfilter"></a>CDaoRecordset:: m_strFilter

SQL 문의 **WHERE** 절을 생성 하는 데 사용 되는 문자열을 포함 합니다.

### <a name="remarks"></a>설명

여기에는 레코드 집합을 필터링 할 예약 **된 단어가 포함** 되지 않습니다. 테이블 형식 레코드 집합에는이 데이터 멤버를 사용할 수 없습니다. `m_strFilter` 사용은 `CDaoQueryDef` 포인터를 사용 하 여 레코드 집합을 열 때 영향을 주지 않습니다.

미국 버전의 Microsoft Jet 데이터베이스 엔진을 사용 하지 않는 경우에도 날짜를 포함 하는 필드를 필터링 할 때 미국 날짜 형식 (월-일-연도)을 사용 합니다. 그렇지 않으면 데이터가 원하는 대로 필터링 되지 않을 수 있습니다.

관련 내용은 DAO 도움말의 "필터 속성" 항목을 참조 하십시오.

##  <a name="m_strsort"></a>CDaoRecordset:: m_strSort

예약 된 단어 **orderby**를 사용 하지 않고 SQL 문의 **orderby** 절을 포함 하는 문자열을 포함 합니다.

### <a name="remarks"></a>설명

다이너셋 및 스냅숏 형식의 레코드 집합 개체를 기준으로 정렬할 수 있습니다.

테이블 형식 레코드 집합 개체는 정렬할 수 없습니다. 테이블 형식 레코드 집합의 정렬 순서를 확인 하려면 [SetCurrentIndex](#setcurrentindex)를 호출 합니다.

*M_strSort* 사용은 `CDaoQueryDef` 포인터를 사용 하 여 레코드 집합을 열 때 영향을 주지 않습니다.

관련 내용은 DAO 도움말의 "Sort Property" 항목을 참조 하십시오.

##  <a name="move"></a>CDaoRecordset:: Move

현재 레코드에서 레코드 집합 *Lrows* 레코드를 배치 하려면이 멤버 함수를 호출 합니다.

```
virtual void Move(long lRows);
```

### <a name="parameters"></a>매개 변수

*lRows*<br/>
앞으로 또는 뒤로 이동할 레코드 수입니다. 양수 값은 레코드 집합의 끝 부분으로 앞으로 이동 합니다. 음수 값은 시작 부분을 향해 뒤로 이동 합니다.

### <a name="remarks"></a>설명

앞으로 또는 뒤로 이동할 수 있습니다. `Move( 1 )`은 `MoveNext`와 동일 하며 `Move( -1 )` `MovePrev`와 동일 합니다.

> [!CAUTION]
>  레코드 집합에 레코드가 없는 경우 `Move` 함수를 호출 하면 예외가 throw 됩니다. 일반적으로 이동 작업 전에 `IsBOF`와 `IsEOF`를 모두 호출 하 여 레코드 집합에 레코드가 있는지 여부를 확인 합니다. `Open` 또는 `Requery`를 호출한 후 `IsBOF` 또는 `IsEOF`를 호출 합니다.

> [!NOTE]
>  `IsBOF` 또는 `IsEOF`에서 0이 아닌 값을 반환 하는 레코드 집합의 시작 또는 끝을 지나서 스크롤하면 `Move`를 호출 하면 `CDaoException`throw 됩니다.

> [!NOTE]
>  현재 레코드를 업데이트 하거나 추가 하는 동안 `Move` 함수를 호출 하면 경고가 발생 하지 않고 업데이트가 손실 됩니다.

앞 으로만 이동 가능한 스크롤 스냅숏에서 `Move`를 호출 하는 경우 *Lrows* 매개 변수는 양의 정수 여야 하며 책갈피는 허용 되지 않으므로 앞 으로만 이동할 수 있습니다.

레코드 집합의 first, last, next 또는 previous 레코드를 현재 레코드로 만들려면 `MoveFirst`, `MoveLast`, `MoveNext`또는 `MovePrev` 멤버 함수를 호출 합니다.

관련 정보는 DAO 도움말의 "Move Method" 및 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" 항목을 참조 하십시오.

##  <a name="movefirst"></a>CDaoRecordset:: MoveFirst

이 멤버 함수를 호출 하 여 레코드 집합의 첫 번째 레코드 (있는 경우)를 현재 레코드로 만듭니다.

```
void MoveFirst();
```

### <a name="remarks"></a>설명

레코드 집합을 연 후 즉시 `MoveFirst`를 호출할 필요가 없습니다. 이때 첫 번째 레코드 (있는 경우)가 자동으로 현재 레코드가 됩니다.

> [!CAUTION]
>  레코드 집합에 레코드가 없는 경우 `Move` 함수를 호출 하면 예외가 throw 됩니다. 일반적으로 이동 작업 전에 `IsBOF`와 `IsEOF`를 모두 호출 하 여 레코드 집합에 레코드가 있는지 여부를 확인 합니다. `Open` 또는 `Requery`를 호출한 후 `IsBOF` 또는 `IsEOF`를 호출 합니다.

> [!NOTE]
>  현재 레코드를 업데이트 하거나 추가 하는 동안 `Move` 함수를 호출 하면 경고가 발생 하지 않고 업데이트가 손실 됩니다.

조건을 적용 하지 않고 레코드에서 레코드로 이동 하려면 `Move` 함수를 사용 합니다. 찾기 작업을 사용 하 여 특정 조건에 맞는 다이너셋 형식 또는 스냅숏 형식 recordset 개체에서 레코드를 찾을 수 있습니다. 테이블 형식 recordset 개체에서 레코드를 찾으려면 `Seek`를 호출 합니다.

레코드 집합이 테이블 형식 레코드 집합을 참조 하는 경우 이동은 테이블의 현재 인덱스를 따릅니다. 기본 DAO 개체의 인덱스 속성을 사용 하 여 현재 인덱스를 설정할 수 있습니다. 현재 인덱스를 설정 하지 않은 경우 반환 되는 레코드의 순서는 정의 되지 않습니다.

SQL 쿼리 또는 쿼리 정의를 기반으로 하는 레코드 집합 개체에 대해 `MoveLast`를 호출 하면 쿼리가 강제로 완료 되 고 레코드 집합 개체가 완전히 채워집니다.

앞 으로만 이동 가능한 스크롤 스냅숏으로 `MoveFirst` 또는 `MovePrev` 멤버 함수를 호출할 수 없습니다.

레코드 집합 개체에서 현재 레코드의 위치를 특정 개수의 레코드를 앞 이나 뒤로 이동 하려면 `Move`를 호출 합니다.

관련 정보는 DAO 도움말의 "Move Method" 및 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" 항목을 참조 하십시오.

##  <a name="movelast"></a>CDaoRecordset:: MoveLast

이 멤버 함수를 호출 하 여 레코드 집합의 마지막 레코드 (있는 경우)를 현재 레코드로 만듭니다.

```
void MoveLast();
```

### <a name="remarks"></a>설명

> [!CAUTION]
>  레코드 집합에 레코드가 없는 경우 `Move` 함수를 호출 하면 예외가 throw 됩니다. 일반적으로 이동 작업 전에 `IsBOF`와 `IsEOF`를 모두 호출 하 여 레코드 집합에 레코드가 있는지 여부를 확인 합니다. `Open` 또는 `Requery`를 호출한 후 `IsBOF` 또는 `IsEOF`를 호출 합니다.

> [!NOTE]
>  현재 레코드를 업데이트 하거나 추가 하는 동안 `Move` 함수를 호출 하면 경고가 발생 하지 않고 업데이트가 손실 됩니다.

조건을 적용 하지 않고 레코드에서 레코드로 이동 하려면 `Move` 함수를 사용 합니다. 찾기 작업을 사용 하 여 특정 조건에 맞는 다이너셋 형식 또는 스냅숏 형식 recordset 개체에서 레코드를 찾을 수 있습니다. 테이블 형식 recordset 개체에서 레코드를 찾으려면 `Seek`를 호출 합니다.

레코드 집합이 테이블 형식 레코드 집합을 참조 하는 경우 이동은 테이블의 현재 인덱스를 따릅니다. 기본 DAO 개체의 인덱스 속성을 사용 하 여 현재 인덱스를 설정할 수 있습니다. 현재 인덱스를 설정 하지 않은 경우 반환 되는 레코드의 순서는 정의 되지 않습니다.

SQL 쿼리 또는 쿼리 정의를 기반으로 하는 레코드 집합 개체에 대해 `MoveLast`를 호출 하면 쿼리가 강제로 완료 되 고 레코드 집합 개체가 완전히 채워집니다.

레코드 집합 개체에서 현재 레코드의 위치를 특정 개수의 레코드를 앞 이나 뒤로 이동 하려면 `Move`를 호출 합니다.

관련 정보는 DAO 도움말의 "Move Method" 및 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" 항목을 참조 하십시오.

##  <a name="movenext"></a>CDaoRecordset:: MoveNext

이 멤버 함수를 호출 하 여 레코드 집합의 다음 레코드를 현재 레코드로 만듭니다.

```
void MoveNext();
```

### <a name="remarks"></a>설명

이전 레코드로 이동 하기 전에 `IsBOF`를 호출 하는 것이 좋습니다. `MovePrev` 호출은 `IsBOF` 반환 하는 경우 `CDaoException`를 throw 합니다 .이는 첫 번째 레코드 이전에 이미 스크롤 했거나 레코드 집합에서 레코드를 선택 하지 않았음을 나타냅니다.

> [!CAUTION]
>  레코드 집합에 레코드가 없는 경우 `Move` 함수를 호출 하면 예외가 throw 됩니다. 일반적으로 이동 작업 전에 `IsBOF`와 `IsEOF`를 모두 호출 하 여 레코드 집합에 레코드가 있는지 여부를 확인 합니다. `Open` 또는 `Requery`를 호출한 후 `IsBOF` 또는 `IsEOF`를 호출 합니다.

> [!NOTE]
>  현재 레코드를 업데이트 하거나 추가 하는 동안 `Move` 함수를 호출 하면 경고가 발생 하지 않고 업데이트가 손실 됩니다.

조건을 적용 하지 않고 레코드에서 레코드로 이동 하려면 `Move` 함수를 사용 합니다. 찾기 작업을 사용 하 여 특정 조건에 맞는 다이너셋 형식 또는 스냅숏 형식 recordset 개체에서 레코드를 찾을 수 있습니다. 테이블 형식 recordset 개체에서 레코드를 찾으려면 `Seek`를 호출 합니다.

레코드 집합이 테이블 형식 레코드 집합을 참조 하는 경우 이동은 테이블의 현재 인덱스를 따릅니다. 기본 DAO 개체의 인덱스 속성을 사용 하 여 현재 인덱스를 설정할 수 있습니다. 현재 인덱스를 설정 하지 않은 경우 반환 되는 레코드의 순서는 정의 되지 않습니다.

레코드 집합 개체에서 현재 레코드의 위치를 특정 개수의 레코드를 앞 이나 뒤로 이동 하려면 `Move`를 호출 합니다.

관련 정보는 DAO 도움말의 "Move Method" 및 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" 항목을 참조 하십시오.

##  <a name="moveprev"></a>CDaoRecordset:: MovePrev

이 멤버 함수를 호출 하 여 레코드 집합의 이전 레코드를 현재 레코드로 만듭니다.

```
void MovePrev();
```

### <a name="remarks"></a>설명

이전 레코드로 이동 하기 전에 `IsBOF`를 호출 하는 것이 좋습니다. `MovePrev` 호출은 `IsBOF` 반환 하는 경우 `CDaoException`를 throw 합니다 .이는 첫 번째 레코드 이전에 이미 스크롤 했거나 레코드 집합에서 레코드를 선택 하지 않았음을 나타냅니다.

> [!CAUTION]
>  레코드 집합에 레코드가 없는 경우 `Move` 함수를 호출 하면 예외가 throw 됩니다. 일반적으로 이동 작업 전에 `IsBOF`와 `IsEOF`를 모두 호출 하 여 레코드 집합에 레코드가 있는지 여부를 확인 합니다. `Open` 또는 `Requery`를 호출한 후 `IsBOF` 또는 `IsEOF`를 호출 합니다.

> [!NOTE]
>  현재 레코드를 업데이트 하거나 추가 하는 동안 `Move` 함수를 호출 하면 경고가 발생 하지 않고 업데이트가 손실 됩니다.

조건을 적용 하지 않고 레코드에서 레코드로 이동 하려면 `Move` 함수를 사용 합니다. 찾기 작업을 사용 하 여 특정 조건에 맞는 다이너셋 형식 또는 스냅숏 형식 recordset 개체에서 레코드를 찾을 수 있습니다. 테이블 형식 recordset 개체에서 레코드를 찾으려면 `Seek`를 호출 합니다.

레코드 집합이 테이블 형식 레코드 집합을 참조 하는 경우 이동은 테이블의 현재 인덱스를 따릅니다. 기본 DAO 개체의 인덱스 속성을 사용 하 여 현재 인덱스를 설정할 수 있습니다. 현재 인덱스를 설정 하지 않은 경우 반환 되는 레코드의 순서는 정의 되지 않습니다.

앞 으로만 이동 가능한 스크롤 스냅숏으로 `MoveFirst` 또는 `MovePrev` 멤버 함수를 호출할 수 없습니다.

레코드 집합 개체에서 현재 레코드의 위치를 특정 개수의 레코드를 앞 이나 뒤로 이동 하려면 `Move`를 호출 합니다.

관련 정보는 DAO 도움말의 "Move Method" 및 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" 항목을 참조 하십시오.

##  <a name="open"></a>CDaoRecordset:: Open

이 멤버 함수를 호출 하 여 레코드 집합에 대 한 레코드를 검색 해야 합니다.

```
virtual void Open(
    int nOpenType = AFX_DAO_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    int nOptions = 0);

virtual void Open(
    CDaoTableDef* pTableDef,
    int nOpenType = dbOpenTable,
    int nOptions = 0);

virtual void Open(
    CDaoQueryDef* pQueryDef,
    int nOpenType = dbOpenDynaset,
    int nOptions = 0);
```

### <a name="parameters"></a>매개 변수

*nOpenType*<br/>
해당 값은

- 양방향 스크롤이 포함 된 다이너셋 형식의 레코드 집합을 `dbOpenDynaset` 합니다. 이것이 기본값입니다.

- 양방향 스크롤이 있는 테이블 형식 레코드 집합을 `dbOpenTable` 합니다.

- 양방향 스크롤이 있는 스냅숏 형식 레코드 집합을 `dbOpenSnapshot` 합니다.

*lpszSQL*<br/>
다음 중 하나를 포함 하는 문자열 포인터입니다.

- NULL 포인터입니다.

- 하나 이상의 테이블 및/또는 쿼리 테이블 이름 (쉼표로 구분)입니다.

- SQL **SELECT** 문 (선택적으로 sql **WHERE** 또는 **ORDERBY** 절)

- 통과 쿼리입니다.

*nOptions*<br/>
아래에 나열 된 하나 이상의 옵션입니다. 기본값은 0입니다. 가능한 값은 다음과 같습니다.

- `dbAppendOnly` 새 레코드를 추가할 수만 있습니다 (다이너셋 형식 레코드 집합에만 해당). 이 옵션은 레코드를 추가 하는 것만을 의미 합니다. MFC ODBC 데이터베이스 클래스에는 레코드를 검색 하 고 추가할 수 있는 추가 전용 옵션이 있습니다.

- `dbForwardOnly` 레코드 집합은 앞 으로만 이동 가능한 스크롤 스냅숏입니다.

- 다른 사용자가 편집 중인 데이터를 변경 하는 경우 예외를 생성 `dbSeeChanges` 합니다.

- `dbDenyWrite` 다른 사용자는 레코드를 수정 하거나 추가할 수 없습니다.

- `dbDenyRead` 다른 사용자는 레코드를 볼 수 없습니다 (테이블 형식 레코드 집합에만 해당).

- `dbReadOnly` 레코드를 볼 수만 있습니다. 다른 사용자는이를 수정할 수 있습니다.

- 일치 하지 않는 업데이트 `dbInconsistent` 허용 됩니다 (다이너셋 형식 레코드 집합에만 해당).

- `dbConsistent` 일관성 있는 업데이트만 허용 됩니다 (다이너셋 형식 레코드 집합에만 해당).

> [!NOTE]
>  상수 `dbConsistent`와 `dbInconsistent`는 함께 사용할 수 없습니다. `Open`의 지정 된 인스턴스 중 하나를 사용할 수 있지만 둘 다 사용할 수는 없습니다.

*pTableDef*<br/>
[CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 개체에 대 한 포인터입니다. 이 버전은 테이블 형식 레코드 집합에 대해서만 유효 합니다. 이 옵션을 사용 하는 경우 `CDaoRecordset`를 구성 하는 데 사용 되는 `CDaoDatabase` 포인터는 사용 되지 않습니다. 대신, 테이블 정의가 있는 데이터베이스가 사용 됩니다.

*pQueryDef*<br/>
[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 개체에 대 한 포인터입니다. 이 버전은 다이너셋 형식 및 스냅숏 형식 레코드 집합에 대해서만 유효 합니다. 이 옵션을 사용 하는 경우 `CDaoRecordset`를 구성 하는 데 사용 되는 `CDaoDatabase` 포인터는 사용 되지 않습니다. 대신 querydef가 있는 데이터베이스가 사용 됩니다.

### <a name="remarks"></a>설명

`Open`를 호출 하기 전에 레코드 집합 개체를 생성 해야 합니다. 다음과 같은 여러 가지 방법으로 이 작업을 수행할 수 있습니다.

- 레코드 집합 개체를 생성할 때 이미 열려 있는 `CDaoDatabase` 개체에 대 한 포인터를 전달 합니다.

- 레코드 집합 개체를 생성 하는 경우 열려 있지 않은 `CDaoDatabase` 개체에 대 한 포인터를 전달 합니다. 레코드 집합은 `CDaoDatabase` 개체를 열 수 있지만 레코드 집합 개체가 닫힐 때이 개체를 닫지 않습니다.

- 레코드 집합 개체를 생성 하는 경우 NULL 포인터를 전달 합니다. 레코드 집합 개체는 `GetDefaultDBName`를 호출 하 여 Microsoft Access의 이름을 가져옵니다. 열려는 MDB 파일입니다. 그러면 레코드 집합은 `CDaoDatabase` 개체를 열고 레코드 집합이 열려 있는 동안에는 열어 둡니다. 레코드 집합에서 `Close`를 호출 하면 `CDaoDatabase` 개체도 닫힙니다.

    > [!NOTE]
    >  레코드 집합에서 `CDaoDatabase` 개체가 열리면 비독점적 access를 사용 하 여 데이터 원본을 엽니다.

*LpszSQL* 매개 변수를 사용 하는 `Open` 버전의 경우 레코드 집합이 열리면 여러 가지 방법 중 하나로 레코드를 검색할 수 있습니다. 첫 번째 옵션은 `DoFieldExchange`에 DFX 함수를 포함 하는 것입니다. 두 번째 옵션은 `GetFieldValue` 멤버 함수를 호출 하 여 동적 바인딩을 사용 하는 것입니다. 이러한 옵션은 개별적으로 또는 함께 구현할 수 있습니다. 결합 된 경우에는 `Open`에 대 한 호출에 대해 직접 SQL 문을 전달 해야 합니다.

`CDaoTableDef` 개체를 전달 하는 `Open`의 두 번째 버전을 사용 하면 결과 열을 `DoFieldExchange` 및 DFX 메커니즘을 통해 바인딩하고 `GetFieldValue`를 통해 동적으로 바인딩할 수 있습니다.

> [!NOTE]
>  테이블 형식 레코드 집합에 대 한 `CDaoTableDef` 개체를 사용 하 여 `Open`만 호출할 수 있습니다.

`CDaoQueryDef` 개체를 전달 하는 `Open`의 세 번째 버전을 사용 하면 해당 쿼리가 실행 되 고, 결과 열을 `DoFieldExchange` 및 DFX 메커니즘을 통해 바인딩할 수 있으며, `GetFieldValue`을 통해 동적으로 바인딩할 수 있습니다.

> [!NOTE]
>  다이너셋 형식 및 스냅숏 형식 레코드 집합에 대 한 `CDaoQueryDef` 개체를 사용 하 여 `Open`만 호출할 수 있습니다.

`lpszSQL` 매개 변수를 사용 하는 `Open`의 첫 번째 버전에서는 다음 표에 표시 된 조건에 따라 레코드가 선택 됩니다.

|`lpszSQL` 매개 변수의 값|선택한 레코드는 다음에 의해 결정 됩니다.|예제|
|--------------------------------------|----------------------------------------|-------------|
|NULL|`GetDefaultSQL`에서 반환 된 문자열입니다.||
|하나 이상의 테이블 및/또는 쿼리 정의 이름에 대 한 쉼표로 구분 된 목록입니다.|`DoFieldExchange`에 표시 된 모든 열입니다.|`"Customer"`|
|테이블 목록 **에서** 열 목록 **선택**|지정 된 테이블 정의 및/또는 쿼리 정의의 지정 된 열입니다.|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|

일반적인 절차는 `Open`에 NULL을 전달 하는 것입니다. 이 경우 `Open`는 `CDaoRecordset`파생 클래스를 만들 때 클래스 마법사가 생성 하는 재정의 가능한 멤버 함수인 `GetDefaultSQL`를 호출 합니다. 이 값은 클래스 마법사에서 지정한 테이블 및/또는 쿼리 정의 이름을 제공 합니다. 대신 *lpszSQL* 매개 변수에서 다른 정보를 지정할 수 있습니다.

전달 하는 것과 관계 없이 쿼리에 대 한 최종 SQL 문자열을 생성 하 `Open` 문자열에는 전달 된 *lpszSQL* 문자열에 추가 된 sql **WHERE** 및 **ORDERBY** 절이 포함 될 수 있습니다. 그런 다음 쿼리를 실행 합니다. `Open`를 호출한 후 `GetSQL`를 호출 하 여 생성 된 문자열을 검사할 수 있습니다.

레코드 집합 클래스의 필드 데이터 멤버는 선택한 데이터의 열에 바인딩됩니다. 레코드가 반환 되 면 첫 번째 레코드가 현재 레코드가 됩니다.

필터 또는 정렬과 같은 레코드 집합에 대 한 옵션을 설정 하려는 경우에는 레코드 집합 개체를 생성 한 후 `Open`를 호출 하기 전에 `m_strSort` 설정 하거나 `m_strFilter` 합니다. 레코드 집합이 이미 열려 있는 후 레코드 집합의 레코드를 새로 고치려면 `Requery`를 호출 합니다.

다이너셋 형식 또는 스냅숏 형식 레코드 집합에서 `Open`를 호출 하거나 데이터 원본이 SQL 문이나 연결 된 테이블을 나타내는 테이블 정의를 참조 하는 경우에는 형식 인수에 대해 `dbOpenTable`를 사용할 수 없습니다. 이렇게 하면 MFC에서 예외가 throw 됩니다. 테이블 정의 개체가 연결 된 테이블을 나타내는지 여부를 확인 하려면 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 개체를 만들고 해당 [getconnect](../../mfc/reference/cdaotabledef-class.md#getconnect) 멤버 함수를 호출 합니다.

같은 레코드를 편집 하거나 삭제 하는 경우 다른 사용자 또는 컴퓨터의 다른 프로그램에서 변경한 내용을 트래핑 하려면 `dbSeeChanges` 플래그를 사용 합니다. 예를 들어 두 사용자가 같은 레코드를 편집 하기 시작 하면 `Update` 멤버 함수를 호출 하는 첫 번째 사용자가 성공 합니다. 두 번째 사용자가 `Update`를 호출 하면 `CDaoException` throw 됩니다. 마찬가지로 두 번째 사용자가 `Delete`를 호출 하 여 레코드를 삭제 하려고 시도 하 고 첫 번째 사용자가 이미 변경 된 경우에는 `CDaoException` 발생 합니다.

일반적으로 업데이트 하는 동안 사용자가이 `CDaoException`를 가져오는 경우 코드에서 필드의 내용을 새로 고치고 새로 수정 된 값을 검색 해야 합니다. 삭제 하는 동안 예외가 발생 하는 경우 코드에서 사용자에 게 새 레코드 데이터를 표시 하 고 데이터가 최근에 변경 되었음을 나타내는 메시지를 표시할 수 있습니다. 이 시점에서 코드는 사용자가 여전히 레코드를 삭제 하려고 한다는 확인을 요청할 수 있습니다.

> [!TIP]
>  응용 프로그램이 ODBC 데이터 원본에서 연 레코드 집합을 통해 단일 패스를 만들 때 전달 전용 스크롤 옵션 (`dbForwardOnly`)을 사용 하 여 성능을 향상 시킬 수 있습니다.

관련 내용은 DAO 도움말의 "OpenRecordset 메서드" 항목을 참조 하십시오.

##  <a name="requery"></a>CDaoRecordset:: Requery

이 멤버 함수를 호출 하 여 레코드 집합을 다시 작성 (새로 고침) 합니다.

```
virtual void Requery();
```

### <a name="remarks"></a>설명

레코드가 반환 되 면 첫 번째 레코드가 현재 레코드가 됩니다.

사용자 또는 다른 사용자가 데이터 원본에 만드는 추가 및 삭제를 레코드 집합에 반영 하려면 `Requery`를 호출 하 여 레코드 집합을 다시 빌드해야 합니다. 레코드 집합이 다이너셋 인 경우 사용자 또는 다른 사용자가 기존 레코드에 대해 수행 하는 업데이트 (추가는 제외)가 자동으로 반영 됩니다. 레코드 집합이 스냅숏이 면 `Requery`를 호출 하 여 다른 사용자의 편집 내용과 추가 및 삭제를 반영 해야 합니다.

다이너셋 또는 스냅숏의 경우 매개 변수 값을 사용 하 여 레코드 집합을 다시 작성 하려는 경우 언제 든 지 `Requery`를 호출 합니다. `Requery`를 호출 하기 전에 [m_strFilter](#m_strfilter) 및 [m_strSort](#m_strsort) 설정 하 여 새 필터나 정렬을 설정 합니다. `Requery`를 호출 하기 전에 매개 변수 데이터 멤버에 새 값을 할당 하 여 새 매개 변수를 설정 합니다.

레코드 집합을 다시 작성 하려는 시도가 실패 하면 레코드 집합은 닫힙니다. `Requery`를 호출 하기 전에 [Canrestart](#canrestart) 멤버 함수를 호출 하 여 레코드 집합을 다시 검색할 수 있는지 여부를 확인할 수 있습니다. `CanRestart`는 `Requery` 성공 하는 것을 보장 하지 않습니다.

> [!CAUTION]
>  `Open`를 호출한 후에만 `Requery`를 호출 합니다.

> [!NOTE]
>  [Requery](#requery) 를 호출 하면 DAO 책갈피가 변경 됩니다.

`CanRestart`를 호출 하면 0이 반환 되거나 테이블 형식 레코드 집합에서 사용할 수 없는 경우에는 다이너셋 형식 또는 스냅숏 형식 레코드 집합에서 `Requery`를 호출할 수 없습니다.

`Requery`를 호출한 후 `IsBOF`와 `IsEOF` 모두 0이 아닌 값을 반환 하는 경우 쿼리는 레코드를 반환 하지 않고 레코드 집합에 데이터가 포함 되지 않습니다.

관련 내용은 DAO 도움말의 "Requery 메서드" 항목을 참조 하십시오.

##  <a name="seek"></a>CDaoRecordset:: Seek

이 멤버 함수를 호출 하 여 현재 인덱스에 대 한 지정 된 조건을 충족 하는 인덱싱된 테이블 형식 recordset 개체에서 레코드를 찾고이 레코드를 현재 레코드로 설정 합니다.

```
BOOL Seek(
    LPCTSTR lpszComparison,
    COleVariant* pKey1,
    COleVariant* pKey2 = NULL,
    COleVariant* pKey3 = NULL);

BOOL Seek(
    LPCTSTR lpszComparison,
    COleVariant* pKeyArray,
    WORD nKeys);
```

### <a name="parameters"></a>매개 변수

*lpszComparison*<br/>
"<", "\<=", "=", "> =" 또는 ">" 문자열 식 중 하나입니다.

*pKey1*<br/>
인덱스의 첫 번째 필드에 해당 하는 값을 갖는 [COleVariant](../../mfc/reference/colevariant-class.md) 에 대 한 포인터입니다. 필수 사항입니다.

*pKey2*<br/>
인덱스의 두 번째 필드 (있는 경우)에 해당 하는 값이 있는 `COleVariant`에 대 한 포인터입니다. 기본값은 NULL입니다.

*pKey3*<br/>
인덱스의 세 번째 필드 (있는 경우)에 해당 하는 값이 있는 `COleVariant`에 대 한 포인터입니다. 기본값은 NULL입니다.

*pKeyArray*<br/>
변형 배열에 대 한 포인터입니다. 배열 크기는 인덱스의 필드 수에 해당 합니다.

*nKeys*<br/>
배열의 크기에 해당 하는 정수입니다 .이 정수는 인덱스의 필드 수입니다.

> [!NOTE]
>  키에 와일드 카드를 지정 하지 마십시오. 와일드 카드를 `Seek` 하면 일치 하는 레코드를 반환 하지 않습니다.

### <a name="return-value"></a>Return Value

일치 하는 레코드가 있는 경우 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`Seek`의 두 번째 (배열) 버전을 사용 하 여 4 개 이상의 필드 인덱스를 처리 합니다.

`Seek`를 사용 하면 테이블 형식 레코드 집합에서 고성능 인덱스 검색을 사용할 수 있습니다. `Seek`를 호출 하기 전에 `SetCurrentIndex`을 호출 하 여 현재 인덱스를 설정 해야 합니다. 인덱스가 고유 하지 않은 키 필드를 식별 하는 경우 `Seek`는 조건을 충족 하는 첫 번째 레코드를 찾습니다. 인덱스를 설정 하지 않으면 예외가 throw 됩니다.

유니코드 레코드 집합을 만들지 않는 경우 `COleVariant` 개체를 명시적으로 ANSI로 선언 해야 합니다. 이 작업을 수행 하려면 *vtSrc* 가 `VT_BSTRT` (ANSI)로 설정 된 생성자의 [COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszSrc* **,** *vtSrc* **)** 또는 *lpszSrc* 가 `VT_BSTRT`로 설정 된 `COleVariant` 함수 [setstring](../../mfc/reference/colevariant-class.md#setstring) **(** *vtSrc* **,** *vtSrc* **)** 를 사용 하 여이 작업을 수행할 수 있습니다.

`Seek`를 호출 하는 경우 하나 이상의 키 값과 비교 연산자 ("<", "\<=", "=", "> =" 또는 ">")를 전달 합니다. `Seek` 지정 된 키 필드를 검색 하 고 *lpszComparison* 및 *pKey1*에 지정 된 조건을 충족 하는 첫 번째 레코드를 찾습니다. `Seek` 발견 되 면 0이 아닌 값을 반환 하 고 해당 레코드를 current로 만듭니다. `Seek`에서 일치 하는 항목을 찾지 못하면 `Seek`는 0을 반환 하 고 현재 레코드는 정의 되지 않습니다. DAO를 직접 사용 하는 경우 NoMatch 속성을 명시적으로 확인 해야 합니다.

`lpszComparison` "=", "> =" 또는 ">" 이면 인덱스의 시작 부분에서 `Seek` 시작 합니다. *LpszComparison* 이 "<" 또는 "< = `Seek`" 이면 인덱스의 끝에서 시작 하 고 끝에 중복 된 인덱스 항목이 없으면 뒤로 검색 합니다. 이 경우 `Seek`는 인덱스 끝의 중복 인덱스 항목 중 임의의 항목에서 시작 됩니다.

`Seek`를 사용 하는 경우 현재 레코드가 될 필요는 없습니다.

특정 조건을 충족 하는 다이너셋 형식 또는 스냅숏 형식 레코드 집합에서 레코드를 찾으려면 찾기 작업을 사용 합니다. 특정 조건을 만족 하는 레코드 뿐만 아니라 모든 레코드를 포함 하려면 이동 작업을 사용 하 여 레코드에서 레코드로 이동 합니다.

연결 된 테이블은 다이너셋 형식 또는 스냅숏 형식 레코드 집합으로 열어야 하므로 모든 형식의 연결 된 테이블에서 `Seek`를 호출할 수 없습니다. 그러나 `CDaoDatabase::Open`를 호출 하 여 설치 가능한 ISAM 데이터베이스를 직접 여는 경우 성능이 느려질 수 있지만 해당 데이터베이스의 테이블에서 `Seek`를 호출할 수 있습니다.

관련 내용은 DAO 도움말의 "Seek 메서드" 항목을 참조 하십시오.

##  <a name="setabsoluteposition"></a>CDaoRecordset:: SetAbsolutePosition

레코드 집합 개체의 현재 레코드에 대 한 상대 레코드 번호를 설정 합니다.

```
void SetAbsolutePosition(long lPosition);
```

### <a name="parameters"></a>매개 변수

*lPosition*<br/>
레코드 집합에서 현재 레코드의 서 수 위치에 해당 합니다.

### <a name="remarks"></a>설명

`SetAbsolutePosition`를 호출 하면 다이너셋 형식 또는 스냅숏 형식 레코드 집합의 서 수 위치에 따라 특정 레코드에 현재 레코드 포인터를 배치할 수 있습니다. [GetAbsolutePosition](#getabsoluteposition)를 호출 하 여 현재 레코드 번호를 확인할 수도 있습니다.

> [!NOTE]
>  이 멤버 함수는 다이너셋 형식 및 스냅숏 형식 레코드 집합에 대해서만 유효 합니다.

기본 DAO 개체의 AbsolutePosition 속성 값은 0부터 시작 합니다. 0의 설정은 레코드 집합의 첫 번째 레코드를 참조 합니다. 채워진 레코드 수보다 큰 값을 설정 하면 MFC에서 예외가 throw 됩니다. `GetRecordCount` 멤버 함수를 호출 하 여 레코드 집합에서 채워진 레코드 수를 확인할 수 있습니다.

현재 레코드를 삭제 하면 AbsolutePosition 속성 값이 정의 되지 않고 MFC가 참조 되는 경우 예외를 throw 합니다. 새 레코드는 시퀀스의 끝에 추가 됩니다.

> [!NOTE]
>  이 속성은 서로게이트 레코드 번호로 사용 하기 위한 것이 아닙니다. 책갈피는 지정 된 위치를 유지 하 고 반환 하는 데 권장 되는 방법 이지만 책갈피를 지 원하는 모든 형식의 레코드 집합 개체에 현재 레코드를 배치할 수 있는 유일한 방법입니다. 특히, 앞의 레코드가 삭제 될 때 지정 된 레코드의 위치가 변경 됩니다. 또한 레코드 집합에 있는 개별 레코드의 순서는 **ORDERBY** 절을 사용 하 여 SQL 문을 사용 하 여 생성 된 경우를 제외 하 고는 다시 생성 될 경우 지정 된 레코드는 동일한 절대 위치를 갖게 됩니다.

관련 내용은 DAO 도움말의 "AbsolutePosition 속성" 항목을 참조 하십시오.

##  <a name="setbookmark"></a>CDaoRecordset:: SetBookmark

이 멤버 함수를 호출 하 여 지정 된 책갈피를 포함 하는 레코드에 레코드 집합을 배치 합니다.

```
void SetBookmark(COleVariant varBookmark);
```

### <a name="parameters"></a>매개 변수

*varBookmark*<br/>
특정 레코드의 책갈피 값을 포함 하는 [COleVariant](../../mfc/reference/colevariant-class.md) 개체입니다.

### <a name="remarks"></a>설명

레코드 집합 개체를 만들거나 열 때 각 레코드에는 이미 고유한 책갈피가 있습니다. `GetBookmark`를 호출 하 고 값을 `COleVariant` 개체에 저장 하 여 현재 레코드에 대 한 책갈피를 검색할 수 있습니다. 나중에 저장 된 책갈피 값을 사용 하 여 `SetBookmark`를 호출 하 여 해당 레코드로 돌아갈 수 있습니다.

> [!NOTE]
>  [Requery](#requery) 를 호출 하면 DAO 책갈피가 변경 됩니다.

유니코드 레코드 집합을 만들지 않는 경우 `COleVariant` 개체를 명시적으로 ANSI로 선언 해야 합니다. 이 작업을 수행 하려면 *vtSrc* 가 `VT_BSTRT` (ANSI)로 설정 된 생성자의 [COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszSrc* **,** *vtSrc* **)** 또는 *lpszSrc* 가 `VT_BSTRT`로 설정 된 `COleVariant` 함수 [setstring](../../mfc/reference/colevariant-class.md#setstring) **(** *vtSrc* **,** *vtSrc* **)** 를 사용 하 여이 작업을 수행할 수 있습니다.

관련 내용은 DAO 도움말의 "책갈피 속성" 및 책갈피를 사용할 수 있는 속성 "항목을 참조 하십시오.

##  <a name="setcachesize"></a>CDaoRecordset:: SetCacheSize

캐시 될 레코드 수를 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetCacheSize(long lSize);
```

### <a name="parameters"></a>매개 변수

*lSize*<br/>
레코드 수를 지정 합니다. 일반적인 값은 100입니다. 0을 설정 하면 캐싱이 해제 됩니다. 설정은 5에서 1200 사이 여야 합니다. 캐시는 상당한 양의 메모리를 사용할 수 있습니다.

### <a name="remarks"></a>설명

캐시는 응용 프로그램이 실행 되는 동안 데이터를 다시 요청 하는 경우 서버에서 가장 최근에 검색 된 데이터를 보관 하는 로컬 메모리의 공간입니다. 데이터 캐싱은 다이너셋 형식의 레코드 집합 개체를 통해 원격 서버에서 데이터를 검색 하는 응용 프로그램의 성능을 향상 시킵니다. 데이터가 요청 될 때 Microsoft Jet 데이터베이스 엔진은 서버에서 검색 하는 대신 요청 된 데이터에 대 한 캐시를 먼저 확인 하 여 더 많은 시간을 사용 합니다. ODBC 데이터 원본에서 가져오지 않은 데이터는 캐시에 저장 되지 않습니다.

모든 ODBC 데이터 원본 (예: 연결 된 테이블)에는 로컬 캐시를 사용할 수 있습니다. 캐시를 만들려면 원격 데이터 원본에서 레코드 집합 개체를 열고 `SetCacheSize` 및 `SetCacheStart` 멤버 함수를 호출한 다음 `FillCache` 멤버 함수를 호출 하거나 이동 작업 중 하나를 사용 하 여 레코드를 단계별로 실행 합니다. `SetCacheSize` 멤버 함수의 *Lsize* 매개 변수는 응용 프로그램에서 한 번에 사용할 수 있는 레코드 수를 기반으로 할 수 있습니다. 예를 들어 화면에 표시할 데이터의 원본으로 레코드 집합을 사용 하는 경우 `SetCacheSize` *Lsize* 매개 변수를 20으로 전달 하 여 20 개의 레코드를 한 번에 표시할 수 있습니다.

관련 내용은 DAO 도움말의 "CacheSize, CacheStart 속성" 항목을 참조 하십시오.

##  <a name="setcachestart"></a>CDaoRecordset:: SetCacheStart

캐시 될 레코드 집합의 첫 번째 레코드에 대 한 책갈피를 지정 하려면이 멤버 함수를 호출 합니다.

```
void SetCacheStart(COleVariant varBookmark);
```

### <a name="parameters"></a>매개 변수

*varBookmark*<br/>
캐시 될 레코드 집합에서 첫 번째 레코드의 책갈피를 지정 하는 [COleVariant](../../mfc/reference/colevariant-class.md) 입니다.

### <a name="remarks"></a>설명

`SetCacheStart` 멤버 함수의 *varbookmark* 매개 변수에 대 한 모든 레코드의 책갈피 값을 사용할 수 있습니다. 현재 레코드를 사용 하 여 캐시를 시작 하려는 레코드를 만들고, [Setbookmark](#setbookmark)를 사용 하 여 해당 레코드에 대 한 책갈피를 설정 하 고, `SetCacheStart` 멤버 함수에 대 한 매개 변수로 책갈피 값을 전달 합니다.

Microsoft Jet 데이터베이스 엔진은 캐시 범위 내에서 레코드를 요청 하 고 서버에서 캐시 범위를 벗어난 레코드를 요청 합니다.

캐시에서 검색 된 레코드는 다른 사용자가 원본 데이터에 대해 동시에 변경한 내용을 반영 하지 않습니다.

모든 캐시 된 데이터를 강제로 업데이트 하려면 `SetCacheSize`의 *Lsize* 매개 변수를 0으로 전달 하 고, 원래 요청한 캐시 크기를 사용 하 여 `SetCacheSize`를 다시 호출한 다음 `FillCache` 멤버 함수를 호출 합니다.

유니코드 레코드 집합을 만들지 않는 경우 `COleVariant` 개체를 명시적으로 ANSI로 선언 해야 합니다. 이 작업을 수행 하려면 *vtSrc* 가 `VT_BSTRT` (ANSI)로 설정 된 생성자의 [COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszSrc* **,** *vtSrc* **)** 또는 *lpszSrc* 가 `VT_BSTRT`로 설정 된 `COleVariant` 함수 [setstring](../../mfc/reference/colevariant-class.md#setstring) **(** *vtSrc* **,** *vtSrc* **)** 를 사용 하 여이 작업을 수행할 수 있습니다.

관련 내용은 DAO 도움말의 CacheSize, CacheStart Properties 항목을 참조 하십시오.

##  <a name="setcurrentindex"></a>CDaoRecordset:: SetCurrentIndex

테이블 형식 레코드 집합에 인덱스를 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetCurrentIndex(LPCTSTR lpszIndex);
```

### <a name="parameters"></a>매개 변수

*lpszIndex*<br/>
설정할 인덱스의 이름을 포함 하는 포인터입니다.

### <a name="remarks"></a>설명

기본 테이블의 레코드는 특정 순서로 저장 되지 않습니다. 인덱스를 설정 하면 데이터베이스에서 반환 되는 레코드의 순서가 변경 되지만 레코드가 저장 되는 순서에는 영향을 주지 않습니다. 지정 된 인덱스가 이미 정의 되어 있어야 합니다. 존재 하지 않는 인덱스 개체를 사용 하려고 하거나 [Seek](#seek)를 호출할 때 인덱스를 설정 하지 않은 경우 MFC는 예외를 throw 합니다.

[CDaoTableDef:: CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) 를 호출 하 고 [CDaoTableDef:: Append](../../mfc/reference/cdaotabledef-class.md#append)를 호출한 다음 레코드 집합을 다시 열어 기본 테이블 정의의 Indexes 컬렉션에 새 인덱스를 추가 하 여 테이블에 대 한 새 인덱스를 만들 수 있습니다.

테이블 형식 레코드 집합에서 반환 된 레코드는 기본 테이블 정의에 대해 정의 된 인덱스만 정렬할 수 있습니다. 다른 순서로 레코드를 정렬 하기 위해 [CDaoRecordset:: m_strSort](#m_strsort)에 저장 된 SQL **ORDERBY** 절을 사용 하 여 다이너셋 형식 또는 스냅숏 형식 레코드 집합을 열 수 있습니다.

관련 정보는 DAO 도움말의 "인덱스 개체" 및 정의 "현재 인덱스" 항목을 참조 하십시오.

##  <a name="setfielddirty"></a>CDaoRecordset:: SetFieldDirty

이 멤버 함수를 호출 하 여 레코드 집합의 필드 데이터 멤버에 변경 되거나 변경 되지 않은 것으로 플래그를 지정 합니다.

```
void SetFieldDirty(
    void* pv,
    BOOL bDirty = TRUE);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
레코드 집합 또는 NULL에 있는 필드 데이터 멤버의 주소를 포함 합니다. NULL 인 경우 레코드 집합의 모든 필드 데이터 멤버에 플래그가 지정 됩니다. C++ Null은 데이터베이스 용어에서 null과 같지 않습니다 .이는 "값이 없습니다."를 의미 합니다.

*bDirty*<br/>
필드 데이터 멤버를 "더티" (변경 됨)로 플래그를 지정 하려면 TRUE입니다. 필드 데이터 멤버에 "clean" (변경 되지 않음)으로 플래그를 지정 하려면 FALSE로 설정 합니다.

### <a name="remarks"></a>설명

필드를 변경 되지 않은 것으로 표시 하면 필드가 업데이트 되지 않습니다.

이 프레임 워크는 변경 된 필드 데이터 멤버를 표시 하 여 DAO 레코드 필드 교환 (DFX) 메커니즘에 의해 데이터 원본의 레코드에 기록 되도록 합니다. 필드의 값을 변경 하는 것은 일반적으로 필드를 자동으로 설정 합니다. 따라서 사용자가 직접 `SetFieldDirty`를 호출할 필요가 없지만 필드 데이터 멤버의 값에 관계 없이 열이 명시적으로 업데이트 되거나 삽입 되도록 할 수도 있습니다. 또한 DFX 메커니즘은 PSEUDONULL 사용을 사용 합니다. 자세한 내용은 [CDaoFieldExchange:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)를 참조 하세요.

이중 버퍼링 메커니즘이 사용 되지 않는 경우 필드의 값을 변경 해도 필드가 더티로 자동 설정 되지 않습니다. 이 경우 필드를 더티로 명시적으로 설정 해야 합니다. [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 에 포함 된 플래그는이 자동 필드 검사를 제어 합니다.

> [!NOTE]
>  [Edit](#edit) 또는 [AddNew](#addnew)를 호출한 후에만이 멤버 함수를 호출 합니다.

함수의 첫 번째 인수에 NULL을 사용 하면 `CDaoFieldExchange`의 **param** 필드가 아니라 모든 `outputColumn` 필드에 함수가 적용 됩니다. 예를 들어

[!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]

`outputColumn` 필드만 NULL로 설정 됩니다. **param** 필드는 영향을 받지 않습니다.

**매개 변수**를 사용 하려면 작업할 개별 **매개** 변수의 실제 주소를 제공 해야 합니다. 예를 들어 다음과 같습니다.

[!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]

즉, `outputColumn` 필드를 사용할 때와 마찬가지로 모든 **매개 변수** 필드를 NULL로 설정할 수 없습니다.

`SetFieldDirty`는 `DoFieldExchange`를 통해 구현 됩니다.

##  <a name="setfieldnull"></a>CDaoRecordset:: SetFieldNull

이 멤버 함수를 호출 하 여 레코드 집합의 필드 데이터 멤버에 Null (값 없음) 또는 Null이 아닌 값으로 플래그를 지정 합니다.

```
void SetFieldNull(
    void* pv,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
레코드 집합 또는 NULL에 있는 필드 데이터 멤버의 주소를 포함 합니다. NULL 인 경우 레코드 집합의 모든 필드 데이터 멤버에 플래그가 지정 됩니다. C++ Null은 데이터베이스 용어에서 null과 같지 않습니다 .이는 "값이 없습니다."를 의미 합니다.

*bNull*<br/>
필드 데이터 멤버에 값이 없는 것으로 플래그가 지정 되는 경우 0이 아닌 값 (Null)입니다. 필드 데이터 멤버가 Null이 아닌 것으로 플래그가 지정 되 면 0이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`SetFieldNull`은 `DoFieldExchange` 메커니즘에서 바인딩된 필드에 사용 됩니다.

레코드 집합에 새 레코드를 추가 하면 처음에는 모든 필드 데이터 멤버가 Null 값으로 설정 되 고 "더티" (변경 됨)로 플래그가 지정 됩니다. 데이터 원본에서 레코드를 검색 하는 경우 해당 열의 열 값이 이미 있거나 Null입니다. 필드를 Null로 설정 하는 것이 적절 하지 않은 경우 [CDaoException](../../mfc/reference/cdaoexception-class.md) 이 throw 됩니다.

예를 들어, 이중 버퍼링 메커니즘을 사용 하는 경우, 예를 들어 현재 레코드의 필드를 값이 없는 것으로 지정 하려는 경우 *Bnull* 이 TRUE로 설정 된 `SetFieldNull`를 호출 하 여 Null로 플래그를 지정 합니다. 이전에 Null로 표시 된 필드에 값을 지정 하려면 새 값을 설정 하기만 하면 됩니다. `SetFieldNull`를 사용 하 여 Null 플래그를 제거할 필요는 없습니다. 필드가 Null 일 수 있는지 여부를 확인 하려면 [IsFieldNullable](#isfieldnullable)를 호출 합니다.

이중 버퍼링 메커니즘을 사용 하지 않는 경우 필드의 값을 변경 해도 필드가 더티로 자동 설정 되 고 Null이 아닌 값으로 설정 됩니다. 필드를 변경 하 고 Null이 아닌 필드를 구체적으로 설정 해야 합니다. [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 에 포함 된 플래그는이 자동 필드 검사를 제어 합니다.

DFX 메커니즘에서는 PSEUDONULL 사용을 사용 합니다. 자세한 내용은 [CDaoFieldExchange:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)를 참조 하세요.

> [!NOTE]
>  [Edit](#edit) 또는 [AddNew](#addnew)를 호출한 후에만이 멤버 함수를 호출 합니다.

함수의 첫 번째 인수에 NULL을 사용 하면 `CDaoFieldExchange`의 **param** 필드가 아닌 `outputColumn` 필드에만 함수가 적용 됩니다. 예를 들어

[!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]

`outputColumn` 필드만 NULL로 설정 됩니다. **param** 필드는 영향을 받지 않습니다.

##  <a name="setfieldvalue"></a>CDaoRecordset:: SetFieldValue

이 멤버 함수를 호출 하 여 필드 값을 서 수 위치로 설정 하거나 문자열의 값을 변경 하 여 설정 합니다.

```
virtual void SetFieldValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetFieldValue(
    int nIndex,
    const COleVariant& varValue);

void SetFieldValue(
    LPCTSTR lpszName,
    LPCTSTR lpszValue);

void SetFieldValue(
    int nIndex,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
필드 이름을 포함 하는 문자열에 대 한 포인터입니다.

*varValue*<br/>
필드 내용의 값을 포함 하는 [COleVariant](../../mfc/reference/colevariant-class.md) 개체에 대 한 참조입니다.

*nIndex*<br/>
레코드 집합의 Fields 컬렉션에 있는 필드의 서 수 위치 (0부터 시작)를 나타내는 정수입니다.

*lpszValue*<br/>
필드 내용의 값을 포함 하는 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`SetFieldValue` 및 [GetFieldValue](#getfieldvalue) 를 사용 하 여 [DoFieldExchange](#dofieldexchange) 메커니즘을 사용 하 여 열을 정적으로 바인딩하지 않고 런타임에 필드를 동적으로 바인딩합니다.

유니코드 레코드 집합을 만들지 않는 경우 `COleVariant` 매개 변수를 포함 하지 않는 `SetFieldValue` 형식을 사용 해야 합니다. 그렇지 않으면 `COleVariant` 개체를 명시적으로 ANSI로 선언 해야 합니다. 이 작업을 수행 하려면 *vtSrc* 가 `VT_BSTRT` (ANSI)로 설정 된 생성자의 [COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszSrc* **,** *vtSrc* **)** 또는 *lpszSrc* 가 `VT_BSTRT`로 설정 된 `COleVariant` 함수 [setstring](../../mfc/reference/colevariant-class.md#setstring) **(** *vtSrc* **,** *vtSrc* **)** 를 사용 하 여이 작업을 수행할 수 있습니다.

관련 내용은 DAO 도움말의 "Field Object" 및 "Value Property" 항목을 참조 하십시오.

##  <a name="setfieldvaluenull"></a>CDaoRecordset:: SetFieldValueNull

이 멤버 함수를 호출 하 여 필드를 Null 값으로 설정 합니다.

```
void SetFieldValueNull(int nIndex);
void SetFieldValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0부터 시작 하는 인덱스 조회를 위해 레코드 집합에 있는 필드의 인덱스입니다.

*lpszName*<br/>
이름으로 조회 하기 위한 레코드 집합의 필드 이름입니다.

### <a name="remarks"></a>설명

C++NULL은 데이터베이스 용어로는 "값이 없습니다."를 의미 하는 Null과 같지 않습니다.

관련 내용은 DAO 도움말의 "Field Object" 및 "Value Property" 항목을 참조 하십시오.

##  <a name="setlockingmode"></a>CDaoRecordset:: SetLockingMode

이 멤버 함수를 호출 하 여 레코드 집합의 잠금 유형을 설정 합니다.

```
void SetLockingMode(BOOL bPessimistic);
```

### <a name="parameters"></a>매개 변수

*bPessimistic*<br/>
잠금 유형을 나타내는 플래그입니다.

### <a name="remarks"></a>설명

비관적 잠금이 적용 되는 경우 `Edit` 멤버 함수를 호출 하는 즉시 편집 중인 레코드가 포함 된 2K 페이지가 잠깁니다. `Update` 또는 `Close` 멤버 함수를 호출 하거나 이동 또는 찾기 작업 중 하나를 호출 하면 페이지 잠금이 해제 됩니다.

낙관적 잠금이 적용 되는 경우 레코드를 포함 하는 2K 페이지는 `Update` 멤버 함수를 사용 하 여 레코드를 업데이트 하는 동안에만 잠깁니다.

페이지가 잠겨 있는 경우 다른 사용자가 동일한 페이지에서 레코드를 편집할 수 없습니다. `SetLockingMode`를 호출 하 고 0이 아닌 값을 전달 하 고 다른 사용자가 이미 잠긴 페이지를 사용 하는 경우 `Edit`를 호출 하면 예외가 throw 됩니다. 다른 사용자는 잠긴 페이지에서 데이터를 읽을 수 있습니다.

0 값을 사용 하 여 `SetLockingMode`를 호출 하 고 나중에 다른 사용자가 페이지를 잠그는 동안 `Update`를 호출 하면 예외가 발생 합니다. 다른 사용자가 변경한 레코드를 확인 하 고 변경 내용을 잃지 않는 경우 현재 레코드의 책갈피 값을 사용 하 여 `SetBookmark` 멤버 함수를 호출 합니다.

ODBC 데이터 원본으로 작업할 때 잠금 모드는 항상 낙관적입니다.

##  <a name="setparamvalue"></a>CDaoRecordset:: SetParamValue

런타임에 레코드 집합에서 매개 변수의 값을 설정 하려면이 멤버 함수를 호출 합니다.

```
virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);

virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
Querydef의 Parameters 컬렉션에 있는 매개 변수의 숫자 위치입니다.

*var*<br/>
설정할 값입니다. 설명을 참조 하세요.

*lpszName*<br/>
값을 설정 하려는 매개 변수의 이름입니다.

### <a name="remarks"></a>설명

매개 변수는 레코드 집합의 SQL 문자열의 일부로 이미 설정 되어 있어야 합니다. 이름 또는 컬렉션의 인덱스 위치를 사용 하 여 매개 변수에 액세스할 수 있습니다.

`COleVariant` 개체로 설정할 값을 지정 합니다. `COleVariant` 개체에서 원하는 값 및 형식을 설정 하는 방법에 대 한 자세한 내용은 클래스 [COleVariant](../../mfc/reference/colevariant-class.md)를 참조 하세요. 유니코드 레코드 집합을 만들지 않는 경우 `COleVariant` 개체를 명시적으로 ANSI로 선언 해야 합니다. 이 작업을 수행 하려면 *vtSrc* 가 `VT_BSTRT` (ANSI)로 설정 된 생성자의 [COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszSrc* **,** *vtSrc* **)** 또는 *lpszSrc* 가 `VT_BSTRT`로 설정 된 `COleVariant` 함수 [setstring](../../mfc/reference/colevariant-class.md#setstring) **(** *vtSrc* **,** *vtSrc* **)** 를 사용 하 여이 작업을 수행할 수 있습니다.

##  <a name="setparamvaluenull"></a>CDaoRecordset:: SetParamValueNull

이 멤버 함수를 호출 하 여 매개 변수를 Null 값으로 설정 합니다.

```
void SetParamValueNull(int nIndex);
void SetParamValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0부터 시작 하는 인덱스 조회를 위해 레코드 집합에 있는 필드의 인덱스입니다.

*lpszName*<br/>
이름으로 조회 하기 위한 레코드 집합의 필드 이름입니다.

### <a name="remarks"></a>설명

C++NULL은 데이터베이스 용어로는 "값이 없습니다."를 의미 하는 Null과 같지 않습니다.

##  <a name="setpercentposition"></a>CDaoRecordset:: SetPercentPosition

이 멤버 함수를 호출 하 여 레코드 집합의 레코드에 대 한 백분율을 기준으로 레코드 집합 개체에서 현재 레코드의 대략적인 위치를 변경 하는 값을 설정 합니다.

```
void SetPercentPosition(float fPosition);
```

### <a name="parameters"></a>매개 변수

*fPosition*<br/>
0부터 100까지의 숫자입니다.

### <a name="remarks"></a>설명

다이너셋 형식 또는 스냅숏 형식 레코드 집합으로 작업 하는 경우 `SetPercentPosition`를 호출 하기 전에 먼저 마지막 레코드로 이동 하 여 레코드 집합을 채웁니다. 레코드 집합을 완전 하 게 채우기 전에 `SetPercentPosition`를 호출 하는 경우 이동 양은 [Getrecordcount](#getrecordcount)값으로 표시 되는 액세스 한 레코드 수를 기준으로 합니다. `MoveLast`를 호출 하 여 마지막 레코드로 이동할 수 있습니다.

`SetPercentPosition`를 호출 하면 해당 값에 해당 하는 대략적인 위치의 레코드가 최신 상태가 됩니다.

> [!NOTE]
>  현재 레코드를 레코드 집합의 특정 레코드로 이동 하기 위해 `SetPercentPosition`를 호출 하는 것은 권장 되지 않습니다. 대신 [Setbookmark](#setbookmark) 멤버 함수를 호출 합니다.

관련 내용은 DAO 도움말의 "PercentPosition 속성" 항목을 참조 하십시오.

##  <a name="update"></a>CDaoRecordset:: Update

`AddNew` 또는 `Edit` 멤버 함수를 호출한 후이 멤버 함수를 호출 합니다.

```
virtual void Update();
```

### <a name="remarks"></a>설명

이 호출은 `AddNew` 또는 `Edit` 작업을 완료 하는 데 필요 합니다.

`AddNew` 및 `Edit`는 모두 데이터 원본에 저장 하기 위해 추가 되거나 편집 된 데이터를 저장 하는 편집 버퍼를 준비 합니다. `Update`는 데이터를 저장 합니다. 변경 된 것으로 표시 되거나 검색 된 필드만 업데이트 됩니다.

데이터 원본에서 트랜잭션을 지 원하는 경우 `Update` 호출 (및 해당 `AddNew` 또는 `Edit` 호출)을 트랜잭션의 일부로 만들 수 있습니다.

> [!CAUTION]
> `AddNew` 또는 `Edit`를 먼저 호출 하지 않고 `Update`를 호출 하는 경우 `Update` `CDaoException`를 throw 합니다. `AddNew` 또는 `Edit`를 호출 하는 경우 [MoveNext](#movenext) 를 호출 하기 전에 `Update`를 호출 하거나 레코드 집합 또는 데이터 원본 연결을 닫아야 합니다. 그렇지 않으면 알림 없이 변경 내용이 손실 됩니다.

Recordset 개체가 다중 사용자 환경에서 pessimistically 잠긴 경우에는 업데이트가 완료 될 때까지 `Edit` 사용 되는 시점에서 레코드가 잠깁니다. 레코드 집합이 낙관적으로 잠겨 있으면 레코드는 잠기고 데이터베이스에서 업데이트 되기 직전에 미리 편집 된 레코드와 비교 됩니다. `Edit`를 호출한 후에 레코드가 변경 되 면 `Update` 작업이 실패 하 고 MFC에서 예외가 throw 됩니다. `SetLockingMode`를 사용 하 여 잠금 모드를 변경할 수 있습니다.

> [!NOTE]
> 낙관적 잠금은 ODBC 및 설치 가능 ISAM과 같은 외부 데이터베이스 형식에서 항상 사용 됩니다.

관련 정보는 DAO 도움말의 "AddNew 메서드", "CancelUpdate 메서드", "Delete 메서드", "LastModified 속성", "업데이트 방법" 및 "EditMode 속성" 항목을 참조 하십시오.

## <a name="see-also"></a>참고 항목

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoWorkspace 클래스](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)<br/>
