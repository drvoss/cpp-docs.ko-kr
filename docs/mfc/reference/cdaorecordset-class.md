---
title: CDao레코드 집합 클래스
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
ms.openlocfilehash: 6a1475d1b0bc083cfd180ea5a211e752c973e2f8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754675"
---
# <a name="cdaorecordset-class"></a>CDao레코드 집합 클래스

데이터 소스에서 선택한 레코드 집합을 나타냅니다.

## <a name="syntax"></a>구문

```
class CDaoRecordset : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDao레코드 집합::CDao레코드 집합](#cdaorecordset)|`CDaoRecordset` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDao레코드 집합::새 새](#addnew)|새 레코드를 추가할 준비를 합니다. [업데이트를](#update) 호출하여 추가를 완료합니다.|
|[CDao 레코드 집합::CanAppend](#canappend)|AddNew 멤버 함수를 통해 레코드 집합에 새 레코드를 추가할 수 있는 경우 0이 아닌 레코드를 [반환합니다.](#addnew)|
|[CDao레코드 집합::캔북마크](#canbookmark)|레코드 집합이 책갈피를 지원하는 경우 0이 아닌 것을 반환합니다.|
|[CDao레코드 집합::취소 업데이트](#cancelupdate)|[편집](#edit) 또는 [AddNew](#addnew) 작업으로 인해 보류 중인 업데이트를 취소합니다.|
|[CDao레코드 집합::캔다시 시작](#canrestart)|레코드 집합의 쿼리를 다시 실행하기 위해 [다시 쿼리를](#requery) 호출할 수 있는 경우 0이 아닌 것을 반환합니다.|
|[CDao레코드 집합::캔스크롤](#canscroll)|레코드를 스크롤할 수 있는 경우 0이 아닌 것을 반환합니다.|
|[CDao레코드 집합::캔트랜스액트](#cantransact)|데이터 원본이 트랜잭션을 지원하는 경우 0이 아닌 것을 반환합니다.|
|[CDao레코드 집합::캔업데이트](#canupdate)|레코드 집합을 업데이트할 수 있는 경우 0이 아닌 것을 반환합니다(레코드추가, 업데이트 또는 삭제할 수 있음).|
|[CDao레코드 집합::닫기](#close)|레코드 집합을 닫습니다.|
|[CDao레코드세트::D](#delete)|레코드 집합에서 현재 레코드를 삭제합니다. 삭제 후 다른 레코드로 명시적으로 스크롤해야 합니다.|
|[CDaoRecordset::DoFieldExchange](#dofieldexchange)|레코드 집합의 필드 데이터 멤버와 데이터 원본의 해당 레코드 간에 양방향으로 데이터를 교환하도록 호출됩니다. DAO 레코드 필드 교환(DFX)을 구현합니다.|
|[CDao레코드 집합::편집](#edit)|현재 레코드에 대한 변경 내용을 준비합니다. 호출하여 `Update` 편집을 완료합니다.|
|[CDao레코드 집합::채우기 캐시](#fillcache)|ODBC 데이터 원본의 데이터를 포함하는 레코드 집합 개체에 대해 로컬 캐시의 전체 또는 일부를 채웁니다.|
|[CDao레코드 집합::찾기](#find)|지정된 조건을 충족하고 해당 레코드를 기록하는 다이나스트 형식 레코드 집합에서 특정 문자열의 첫 번째, 다음, 이전 또는 마지막 위치를 찾습니다.|
|[CDao레코드 집합::찾기우선](#findfirst)|지정된 조건을 충족하고 해당 레코드를 현재 레코드로 만드는 다이너셋 유형 또는 스냅숏 형식 레코드 집합에서 첫 번째 레코드를 찾습니다.|
|[CDao레코드 집합::찾기 마지막](#findlast)|지정된 조건을 충족하고 해당 레코드를 현재 레코드로 만드는 다이너셋 유형 또는 스냅숏 형식 레코드 집합에서 마지막 레코드를 찾습니다.|
|[CDao레코드 집합::다음 찾기](#findnext)|지정된 조건을 충족하고 해당 레코드를 현재 레코드로 만드는 다이너셋 유형 또는 스냅숏 형식 레코드 집합에서 다음 레코드를 찾습니다.|
|[CDao레코드 집합::찾기사전](#findprev)|지정된 조건을 충족하고 해당 레코드를 현재 레코드로 만드는 다이너셋 유형 또는 스냅숏 형식 레코드 집합에서 이전 레코드를 찾습니다.|
|[CDao레코드 집합::GetAbsolutePosition](#getabsoluteposition)|레코드 집합 개체의 현재 레코드의 레코드 번호를 반환합니다.|
|[CDao레코드 집합::Getbookmark](#getbookmark)|레코드의 책갈피를 나타내는 값을 반환합니다.|
|[CDao레코드 집합::GetCacheSize](#getcachesize)|ODBC 데이터 원본에서 로컬로 캐시할 데이터를 포함하는 다이너셋 형식 레코드 집합의 레코드 수를 지정하는 값을 반환합니다.|
|[CDao레코드 집합::겟캐시스타트](#getcachestart)|캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정하는 값을 반환합니다.|
|[CDao레코드 집합::GetCurrentIndex](#getcurrentindex)|인덱싱된 테이블 형식에서 `CString` `CDaoRecordset`가장 최근에 사용한 인덱스 이름이 포함된 인덱스를 반환합니다.|
|[CDao레코드 집합::GetDateCreated](#getdatecreated)|개체의 기본 을 기본으로 `CDaoRecordset` 하는 기본 테이블이 만들어진 날짜 및 시간을 반환합니다.|
|[CDao레코드 집합::GetDateLast업데이트](#getdatelastupdated)|개체의 기본 을 기본으로 하는 기본 테이블의 디자인에 `CDaoRecordset` 대한 가장 최근 변경 된 날짜와 시간을 반환 합니다.|
|[CDao레코드 집합::GetDefaultDBName](#getdefaultdbname)|기본 데이터 원본의 이름을 반환합니다.|
|[CDao레코드 집합::GetDefaultSQL](#getdefaultsql)|실행할 기본 SQL 문자열을 얻으려면 호출됩니다.|
|[CDao레코드 집합::GetEditMode](#geteditmode)|현재 레코드에 대한 편집 상태를 나타내는 값을 반환합니다.|
|[CDao레코드 집합::겟필드카운트](#getfieldcount)|레코드 집합의 필드 수를 나타내는 값을 반환합니다.|
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|레코드 집합의 필드에 대한 특정 종류의 정보를 반환합니다.|
|[CDao레코드 집합::겟필드밸류](#getfieldvalue)|레코드 집합에서 필드 값을 반환합니다.|
|[CDao레코드 집합::GetIndexCount](#getindexcount)|레코드 집합의 기본 을 기본으로 하는 테이블의 인덱스 수를 검색합니다.|
|[CDao레코드 집합::GetIndexInfo](#getindexinfo)|인덱스에 대한 다양한 종류의 정보를 반환합니다.|
|[CDao 레코드 집합::GetLast수정된 책갈피](#getlastmodifiedbookmark)|가장 최근에 추가하거나 업데이트된 레코드를 결정하는 데 사용됩니다.|
|[CDao레코드 집합::겟잠금 모드](#getlockingmode)|편집 중에 적용되는 잠금 유형을 나타내는 값을 반환합니다.|
|[CDao레코드 집합::GetName](#getname)|레코드 `CString` 집합의 이름을 포함하는 를 반환합니다.|
|[CDao레코드 집합::겟파라임밸류](#getparamvalue)|기본 DAOParameter 개체에 저장된 지정된 매개 변수의 현재 값을 검색합니다.|
|[CDao레코드 집합::GetPercent포지션](#getpercentposition)|현재 레코드의 위치를 총 레코드 수의 백분율로 반환합니다.|
|[CDao레코드 집합::겟레코드 카운트](#getrecordcount)|레코드 집합 개체에서 액세스한 레코드 수를 반환합니다.|
|[CDao 레코드 집합::GetSQL](#getsql)|레코드 집합에 대한 레코드를 선택하는 데 사용되는 SQL 문자열을 가져옵니다.|
|[CDao레코드 집합::GetType](#gettype)|테이블 유형, 다이너셋 형식 또는 스냅숏 형식과 같은 레코드 집합의 형식을 결정하기 위해 호출됩니다.|
|[CDao레코드 집합::GetvalidationRule](#getvalidationrule)|필드에 `CString` 입력될 때 데이터의 유효성을 검사하는 값이 포함된 값을 반환합니다.|
|[CDao레코드 집합::유효성 검사 텍스트](#getvalidationtext)|유효성 검사 규칙이 충족되지 않을 때 표시되는 텍스트를 검색합니다.|
|[CDao 레코드 집합::IsBOF](#isbof)|레코드 집합이 첫 번째 레코드 앞에 위치한 경우 0이 아닌 것을 반환합니다. 현재 레코드가 없습니다.|
|[CDao레코드 집합::삭제됨](#isdeleted)|레코드 집합이 삭제된 레코드에 배치된 경우 0이 아닌 것을 반환합니다.|
|[CDao 레코드 집합::IsEOF](#iseof)|레코드 집합이 마지막 레코드 다음으로 배치된 경우 0이 아닌 것을 반환합니다. 현재 레코드가 없습니다.|
|[CDao 레코드 집합::IsFieldDirty](#isfielddirty)|현재 레코드의 지정된 필드가 변경된 경우 0이 아닌 필드를 반환합니다.|
|[CDao레코드 집합::이스필드널](#isfieldnull)|현재 레코드의 지정된 필드가 Null(값이 없음)인 경우 0이 아닌 필드를 반환합니다.|
|[CDao레코드 집합::IsFieldNullable](#isfieldnullable)|현재 레코드의 지정된 필드를 Null로 설정할 수 있는 경우 0이 아닌 필드를 반환합니다(값이 없음).|
|[CDao레코드 집합::이열기](#isopen)|[Open이](#open) 이전에 호출된 경우 0이 아닌 것을 반환합니다.|
|[CDao레코드 집합::이동](#move)|레코드 집합을 현재 레코드의 지정된 레코드 수에 어느 방향으로든 배치합니다.|
|[CDao레코드 집합::이동우선](#movefirst)|레코드 집합의 첫 번째 레코드에 현재 레코드를 배치합니다.|
|[CDao레코드 집합::무브라스트](#movelast)|레코드 집합의 마지막 레코드에 현재 레코드를 배치합니다.|
|[CDao레코드 집합::MoveNext](#movenext)|레코드 집합의 다음 레코드에 현재 레코드를 배치합니다.|
|[CDao레코드 집합::무브프레프](#moveprev)|레코드 집합의 이전 레코드에 현재 레코드를 배치합니다.|
|[CDao레코드 집합::열기](#open)|테이블, 다이너셋 또는 스냅숏에서 새 레코드 집합을 만듭니다.|
|[CDao레코드 집합::다시 쿼리](#requery)|레코드 집합의 쿼리를 다시 실행하여 선택한 레코드를 새로 고칩니다.|
|[CDao 레코드 집합::검색](#seek)|현재 인덱스에 대 한 지정 된 조건을 충족 하 고 해당 레코드를 현재 레코드를 만드는 인덱싱된 테이블 형식 레코드 집합 개체에서 레코드를 찾습니다.|
|[CDao레코드 집합::설정절대위치](#setabsoluteposition)|레코드 집합 개체의 현재 레코드의 레코드 번호를 설정합니다.|
|[CDao레코드 집합::세트북마크](#setbookmark)|지정된 책갈피를 포함하는 레코드에 레코드 집합을 배치합니다.|
|[CDao레코드 집합::세트캐시크기](#setcachesize)|ODBC 데이터 원본에서 로컬로 캐시할 데이터를 포함하는 다이너셋 형식 레코드 집합의 레코드 수를 지정하는 값을 설정합니다.|
|[CDao레코드 집합::세트캐시스타트](#setcachestart)|캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정하는 값을 설정합니다.|
|[CDao레코드 집합::세트전류 인덱스](#setcurrentindex)|테이블 형식 레코드 집합에 인덱스를 설정하기 위해 호출되었습니다.|
|[CDao레코드 집합::세트필드더티](#setfielddirty)|현재 레코드에서 지정된 필드를 변경된 것으로 표시합니다.|
|[CDao레코드 집합::세트필드널](#setfieldnull)|현재 레코드에서 지정된 필드의 값을 Null로 설정합니다(값이 없음).|
|[CDao레코드 집합::세트필드밸류](#setfieldvalue)|레코드 집합에서 필드 값을 설정합니다.|
|[CDao레코드 집합::세트필드밸류널](#setfieldvaluenull)|레코드 집합의 필드 값을 Null로 설정합니다. (값이 없음).|
|[CDao레코드 집합::세트 잠금 모드](#setlockingmode)|편집 하는 동안 적용 될 잠금의 종류를 나타내는 값을 설정 합니다.|
|[CDao레코드 집합::SetParam값](#setparamvalue)|기본 DAOParameter 개체에 저장된 지정된 매개 변수의 현재 값을 설정합니다.|
|[CDao레코드 집합::SetParamValueNull](#setparamvaluenull)|지정된 매개 변수의 현재 값을 Null로 설정합니다(값이 없음).|
|[CDao레코드 집합::설정백분율 위치](#setpercentposition)|현재 레코드의 위치를 레코드 집합의 총 레코드 수의 백분율에 해당하는 위치로 설정합니다.|
|[CDao레코드 집합::업데이트](#update)|데이터 `AddNew` 원본에 `Edit` 새 데이터 또는 편집된 데이터를 저장하여 또는 작업을 완료합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDao레코드 집합::m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|필드가 자동으로 변경된 것으로 표시되는지 여부를 나타내는 플래그가 포함되어 있습니다.|
|[CDao레코드 집합::m_nFields](#m_nfields)|레코드 집합 클래스의 필드 데이터 멤버 수와 데이터 원본에서 레코드 집합에서 선택한 열 수를 포함합니다.|
|[CDao레코드 집합::m_nParams](#m_nparams)|레코드 집합 클래스의 매개 변수 데이터 멤버 수(레코드 집합의 쿼리와 함께 전달된 매개 변수 수)를 포함합니다.|
|[CDao레코드 집합::m_pDAORecordset](#m_pdaorecordset)|레코드 집합 개체의 기본 DAO 인터페이스에 대한 포인터입니다.|
|[CDao레코드 집합::m_pDatabase](#m_pdatabase)|이 결과 집합에 대한 원본 데이터베이스입니다. [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체에 대한 포인터를 포함합니다.|
|[CDao레코드 집합::m_strFilter](#m_strfilter)|SQL **WHERE** 문을 생성하는 데 사용되는 문자열을 포함합니다.|
|[CDao레코드 집합::m_strSort](#m_strsort)|SQL **ORDER BY** 문을 생성하는 데 사용되는 문자열을 포함합니다.|

## <a name="remarks"></a>설명

"레코드 집합"이라고 `CDaoRecordset` 하는 개체는 다음 세 가지 형태로 사용할 수 있습니다.

- 테이블 유형 레코드 집합은 단일 데이터베이스 테이블에서 레코드를 검사, 추가, 변경 또는 삭제하는 데 사용할 수 있는 기본 테이블을 나타냅니다.

- Dynaset 형식 레코드 집합은 업데이트 가능한 레코드를 가질 수 있는 쿼리의 결과입니다. 이러한 레코드 집합은 기본 데이터베이스 테이블 또는 테이블에서 레코드를 검사, 추가, 변경 또는 삭제하는 데 사용할 수 있는 레코드 집합입니다. Dynaset 형식 레코드 집합에는 데이터베이스에 있는 하나 이상의 테이블의 필드가 포함될 수 있습니다.

- 스냅숏 유형 레코드 집합은 데이터를 찾거나 보고서를 생성하는 데 사용할 수 있는 레코드 집합의 정적 복사본입니다. 이러한 레코드 집합에는 데이터베이스에 있는 하나 이상의 테이블의 필드가 포함될 수 있지만 업데이트할 수는 없습니다.

각 레코드 집합은 레코드 집합이 열릴 때 고정된 레코드 집합을 나타냅니다. 테이블 형식 레코드 집합 또는 다이나식 레코드 집합의 레코드로 스크롤하면 다른 사용자 나 응용 프로그램의 다른 레코드 집합에서 레코드 집합을 연 후 레코드에 대한 변경 내용을 반영합니다. (스냅샷 형식 레코드 집합을 업데이트할 수 없습니다.) 에서 응용 `CDaoRecordset` 프로그램 별 레코드 집합 클래스를 직접 사용하거나 파생시킬 수 있습니다. `CDaoRecordset` 그런 다음 아래의 작업을 수행할 수 있습니다.

- 레코드를 스크롤합니다.

- 인덱스를 설정하고 [Seek(테이블](#seek) 유형 레코드 집합만)를 사용하여 레코드를 빠르게 찾습니다.

- 문자열 비교를 기반으로 레코드를 찾습니다:\<"<", "=", "=", ">=" 또는 ">"(다이너셋 유형 및 스냅숏 형식 레코드 집합).

- 레코드를 업데이트하고 잠금 모드를 지정합니다(스냅숏 형식 레코드 집합 제외).

- 레코드 집합을 필터링하여 데이터 원본에서 사용할 수 있는 레코드 중에서 선택한 레코드를 제한합니다.

- 레코드 집합을 정렬합니다.

- 레코드 집합을 매개 변수화하여 런타임까지 알려지지 않은 정보로 선택 영역을 사용자 지정합니다.

클래스는 `CDaoRecordset` 클래스와 `CRecordset`유사한 인터페이스를 제공합니다. 주요 차이점은 클래스가 `CDaoRecordset` OLE를 기반으로 하는 DAO(데이터 액세스 개체)를 통해 데이터에 액세스한다는 것입니다. 클래스는 `CRecordset` 개방형 데이터베이스 연결(ODBC)과 해당 DBMS에 대한 ODBC 드라이버를 통해 DBMS에 액세스합니다.

> [!NOTE]
> DAO 데이터베이스 클래스는 ODBC(개방형 데이터베이스 연결)를 기반으로 하는 MFC 데이터베이스 클래스와 구별됩니다. 모든 DAO 데이터베이스 클래스 이름에는 "CDao" 접두사가 있습니다. DAO 클래스를 사용하여 ODBC 데이터 원본에 계속 액세스할 수 있습니다. DAO 클래스는 일반적으로 Microsoft Jet 데이터베이스 엔진에 만기되어 있기 때문에 우수한 기능을 제공합니다.

에서 클래스를 `CDaoRecordset` 직접 사용하거나 `CDaoRecordset`파생할 수 있습니다. 두 경우 모두 레코드 집합 클래스를 사용하려면 데이터베이스를 열고 레코드 집합 개체를 생성자가 개체에 포인터를 전달하여 레코드 집합 개체를 생성합니다. `CDaoDatabase` 개체를 `CDaoRecordset` 생성하고 MFC가 임시 `CDaoDatabase` 개체를 만들도록 할 수도 있습니다. 그런 다음 레코드 집합의 [Open](#open) 멤버 함수를 호출하여 개체가 테이블 형식 레코드 집합인지, 다이너셋 형식 레코드 집합인지 또는 스냅숏 형식 레코드 집합인지 지정합니다. 호출은 `Open` 데이터베이스에서 데이터를 선택하고 첫 번째 레코드를 검색합니다.

개체의 멤버 함수 및 데이터 멤버를 사용하여 레코드를 스크롤하고 작동합니다. 사용 가능한 작업은 개체가 테이블 형식 레코드 집합인지, 다이너셋 형식 레코드 집합인지 또는 스냅숏 형식 레코드 집합인지 여부와 업데이트 가능한 지 읽기 전용인지 여부에 따라 달라집니다. `Open` 호출 이후 변경되거나 추가된 레코드를 새로 고치려면 개체의 [Requery](#requery) 멤버 함수를 호출합니다. 개체의 `Close` 멤버 함수를 호출하고 개체를 완료하면 개체를 삭제합니다.

`CDaoRecordset`DAO 레코드 필드 교환(DFX)을 사용하여 `CDaoRecordset` 형식 이안전한 C++ 멤버 또는 `CDaoRecordset`파생 클래스의 구성원을 통해 레코드 필드의 읽기 및 업데이트를 지원합니다. [GetFieldValue 및 SetFieldValue를](#getfieldvalue) 사용 하 여 DFX 메커니즘을 사용 하지 않고 데이터베이스에서 열의 동적 [바인딩을](#setfieldvalue)구현할 수도 있습니다.

관련 정보는 DAO 도움말의 "레코드 집합 개체" 항목을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDaoRecordset`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="cdaorecordsetaddnew"></a><a name="addnew"></a>CDao레코드 집합::새 새

이 멤버 함수를 호출하여 테이블 유형 또는 다이너셋 형식 레코드 집합에 새 레코드를 추가합니다.

```
virtual void AddNew();
```

### <a name="remarks"></a>설명

레코드의 필드는 처음에 Null입니다. (데이터베이스 용어에서 Null은 "값이 없음"을 의미하며 C++에서 NULL과 동일하지 않습니다. 작업을 완료하려면 [멤버 업데이트](#update) 함수를 호출해야 합니다. `Update`변경 내용을 데이터 원본에 저장합니다.

> [!CAUTION]
> 레코드를 편집한 다음 호출하지 `Update`않고 다른 레코드로 스크롤하면 변경 내용이 경고 없이 손실됩니다.

[AddNew를](#addnew)호출하여 다이너셋 형식 레코드 집합에 레코드를 추가하면 레코드가 레코드 집합에 표시되고 새 `CDaoRecordset` 개체에 표시되는 기본 테이블에 포함됩니다.

새 레코드의 위치는 레코드 집합 유형에 따라 다릅니다.

- 새 레코드가 삽입되는 다이너셋 형식 레코드 집합에서는 보장되지 않습니다. 이 동작은 성능 및 동시성 이유로 Microsoft Jet 3.0에서 변경되었습니다. 새로 추가된 레코드를 현재 레코드로 만드는 것이 목표인 경우 마지막으로 수정된 레코드의 책갈피를 얻고 해당 책갈피로 이동합니다.

[!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]

- 인덱스가 지정된 테이블 형식 레코드 집합에서 레코드는 정렬 순서대로 적절한 위치에 반환됩니다. 인덱스를 지정하지 않은 경우 레코드 집합이 끝날 때 새 레코드가 반환됩니다.

사용 `AddNew` 하기 전에 현재 레코드는 현재 상태로 유지됩니다. 새 레코드를 현재 상태로 만들고 레코드 집합이 책갈피를 지원하려면 [SetBookmark를](#setbookmark) 호출하여 기본 DAO 레코드 집합 개체의 LastModified 속성 설정으로 식별된 책갈피를 호출합니다. 이렇게 하면 추가된 레코드에서 카운터(자동 증분) 필드의 값을 결정하는 데 유용합니다. 자세한 내용은 [GetLast수정책명표를](#getlastmodifiedbookmark)참조하십시오.

데이터베이스가 트랜잭션을 지원하는 경우 `AddNew` 트랜잭션의 일부로 호출할 수 있습니다. 트랜잭션에 대한 자세한 내용은 클래스 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)를 참조하십시오. 호출하기 전에 [CDaoWorkspace::BeginTrans를](../../mfc/reference/cdaoworkspace-class.md#begintrans) `AddNew`호출해야 합니다.

`AddNew` [Open](#open) 멤버 함수가 호출되지 않은 레코드 집합을 호출하는 것은 불법입니다. 추가할 수 없는 `AddNew` 레코드 집합을 호출하면 A가 `CDaoException` throw됩니다. 레코드 집합을 호출하여 업데이트할 수 있는지 여부를 확인할 수 [있습니다.](#canappend)

프레임워크는 변경된 필드 데이터 멤버를 표시하여 DAO 레코드 필드 교환(DFX) 메커니즘에 의해 데이터 원본의 레코드에 기록되도록 합니다. 필드 값을 변경하면 일반적으로 필드가 자동으로 더러워지므로 [SetFieldDirty](#setfielddirty) 를 직접 호출할 필요가 거의 없지만 필드 데이터 멤버에 있는 값에 관계없이 열이 명시적으로 업데이트되거나 삽입되도록 할 수 있습니다. DFX 메커니즘은 **또한 PSEUDO NULL의**사용을 사용합니다. 자세한 내용은 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)를 참조하십시오.

이중 버퍼링 메커니즘이 사용되지 않는 경우 필드 값을 변경해도 필드가 자동으로 더티로 설정되지 않습니다. 이 경우 필드를 더티로 명시적으로 설정해야 합니다. [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 포함된 플래그는 이 자동 필드 검사를 제어합니다.

> [!NOTE]
> 레코드가 이중 버퍼링(즉, 자동 필드 검사가 활성화됨)인 경우 호출은 `CancelUpdate` 멤버 변수를 이전에 `AddNew` 또는 `Edit` 호출된 값으로 복원합니다.

관련 정보는 DAO 도움말의 "새 새 메서드 추가", "취소 업데이트 메서드", "마지막으로 수정된 속성" 및 "편집 모드 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetcanappend"></a><a name="canappend"></a>CDao 레코드 집합::CanAppend

이 멤버 함수를 호출하여 이전에 연 레코드 집합이 [AddNew](#addnew) 멤버 함수를 호출하여 새 레코드를 추가할 수 있는지 여부를 확인합니다.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Return Value

레코드 집합에서 새 레코드를 추가할 수 있는 경우 0이 아닙니다. 그렇지 않으면 0. `CanAppend`레코드 집합을 읽기 전용으로 열면 0이 반환됩니다.

### <a name="remarks"></a>설명

관련 정보는 DAO 도움말의 "방법 부화" 항목을 참조하십시오.

## <a name="cdaorecordsetcanbookmark"></a><a name="canbookmark"></a>CDao레코드 집합::캔북마크

이 멤버 함수를 호출하여 이전에 연 레코드 집합이 책갈피를 사용하여 레코드를 개별적으로 표시할 수 있는지 확인합니다.

```
BOOL CanBookmark();
```

### <a name="return-value"></a>Return Value

레코드 집합이 책갈피를 지원하는 경우 0이 아닌 0입니다.

### <a name="remarks"></a>설명

Microsoft Jet 데이터베이스 엔진 테이블을 기반으로 레코드 집합을 사용하는 경우 정방향 전용 스크롤 레코드 집합으로 플래그가 지정된 스냅숏 유형 레코드 집합을 제외하고 책갈피를 사용할 수 있습니다. 다른 데이터베이스 제품(외부 ODBC 데이터 원본)은 책갈피를 지원하지 않을 수 있습니다.

관련 정보는 DAO 도움말의 "즐겨찾기 표시 가능 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetcancelupdate"></a><a name="cancelupdate"></a>CDao레코드 집합::취소 업데이트

멤버 `CancelUpdate` 함수는 [편집](#edit) 또는 [AddNew](#addnew) 작업으로 인해 보류 중인 업데이트를 취소합니다.

```
virtual void CancelUpdate();
```

### <a name="remarks"></a>설명

예를 들어 응용 프로그램이 `Edit` 또는 `AddNew` 멤버 함수를 호출하고 `CancelUpdate` [Update를](#update)호출하지 않은 경우 이후에 변경한 내용을 취소하거나 `Edit` `AddNew` 호출한 경우

> [!NOTE]
> 레코드가 이중 버퍼링(즉, 자동 필드 검사가 활성화됨)인 경우 호출은 `CancelUpdate` 멤버 변수를 이전에 `AddNew` 또는 `Edit` 호출된 값으로 복원합니다.

보류 중인 `Edit` `AddNew` 작업이 없거나 `CancelUpdate` 없는 경우 MFC가 예외를 throw합니다. [GetEditMode](#geteditmode) 멤버 함수를 호출하여 취소할 수 있는 보류 중인 작업이 있는지 확인합니다.

관련 정보는 DAO 도움말의 "취소 업데이트 방법" 항목을 참조하십시오.

## <a name="cdaorecordsetcanrestart"></a><a name="canrestart"></a>CDao레코드 집합::캔다시 시작

이 멤버 함수를 호출하여 레코드 집합이 `Requery` 멤버 함수를 호출하여 쿼리를 다시 시작할 수 있는지 확인합니다(레코드 레코드 새로 고침).

```
BOOL CanRestart();
```

### <a name="return-value"></a>Return Value

Nonzero `Requery` 레코드 집합의 쿼리를 다시 실행 하기 위해 호출할 수 있습니다 경우, 그렇지 않으면 0.

### <a name="remarks"></a>설명

테이블 형식 레코드 집합은 `Requery`을 지원하지 않습니다.

지원되지 않는 경우 `Requery` [닫기](#close) 다음 [열기를](#open) 호출하여 데이터를 새로 고칩니다. 매개 변수 `Requery` 값이 변경된 후 레코드 집합 개체의 기본 매개 변수 쿼리를 업데이트하도록 호출할 수 있습니다.

관련 정보는 DAO 도움말의 "다시 시작 가능한 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetcanscroll"></a><a name="canscroll"></a>CDao레코드 집합::캔스크롤

이 멤버 함수를 호출하여 레코드 집합이 스크롤을 허용하는지 여부를 확인합니다.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Return Value

레코드를 스크롤할 수 있는 경우 0이 아닙니다.

### <a name="remarks"></a>설명

을 통해 `dbForwardOnly` [열기를](#open) 호출하면 레코드 집합은 앞으로만 스크롤할 수 있습니다.

관련 정보는 DAO 도움말의 "현재 레코드 포인터 위치 지정" 항목을 참조하십시오.

## <a name="cdaorecordsetcantransact"></a><a name="cantransact"></a>CDao레코드 집합::캔트랜스액트

이 멤버 함수를 호출하여 레코드 집합이 트랜잭션을 허용하는지 여부를 확인합니다.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Return Value

기본 데이터 원본이 트랜잭션을 지원하는 경우 비영(nonzero)(그렇지 않으면 0).

### <a name="remarks"></a>설명

관련 정보는 DAO 도움말의 "트랜잭션 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetcanupdate"></a><a name="canupdate"></a>CDao레코드 집합::캔업데이트

이 멤버 함수를 호출하여 레코드 집합을 업데이트할 수 있는지 여부를 확인합니다.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Return Value

레코드 집합을 업데이트할 수 있는 경우(레코드 추가, 업데이트 및 삭제), 그렇지 않으면 0이 아닙니다.

### <a name="remarks"></a>설명

레코드 집합은 기본 데이터 원본이 읽기 전용이거나 레코드 집합에 `dbReadOnly` 대해 [열기를](#open) 호출할 때 *nOptions에* 대해 지정한 경우 읽기 전용일 수 있습니다.

관련 정보는 DAO 도움말의 "새 새 메서드 추가", "메서드 편집", "방법 삭제", "업데이트 방법" 및 "업데이트 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetcdaorecordset"></a><a name="cdaorecordset"></a>CDao레코드 집합::CDao레코드 집합

`CDaoRecordset` 개체를 생성합니다.

```
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>매개 변수

*p데이터베이스*<br/>
[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체 또는 NULL 값에 대한 포인터를 포함합니다. NULL이 아니고 `CDaoDatabase` 개체의 `Open` 멤버 함수가 데이터 원본에 연결하기 위해 호출되지 않은 경우 레코드 집합은 자체 [Open](#open) 호출 중에 해당 함수를 열려고 시도합니다. NULL을 통과하면 `CDaoDatabase` `CDaoRecordset`에서 레코드 집합 클래스를 파생한 경우 지정한 데이터 원본 정보를 사용하여 개체가 생성되고 연결됩니다.

### <a name="remarks"></a>설명

에서 응용 `CDaoRecordset` 프로그램 별 클래스를 직접 사용하거나 파생시킬 수 있습니다. `CDaoRecordset` ClassWizard를 사용하여 레코드 집합 클래스를 파생할 수 있습니다.

> [!NOTE]
> 클래스를 파생하는 `CDaoRecordset` 경우 파생 클래스는 자체 생성자(생성자)를 제공해야 합니다. 파생 클래스의 생성자에서 생성자 `CDaoRecordset::CDaoRecordset`호출 하여 해당 매개 변수를 전달합니다.

NULL을 레코드 집합 생성자로 `CDaoDatabase` 전달하여 개체를 자동으로 생성하고 연결합니다. 레코드 집합을 생성하기 전에 `CDaoDatabase` 개체를 생성하고 연결할 필요가 없는 유용한 바로 가기입니다. 개체가 `CDaoDatabase` 열려 있지 않으면 기본 작업 공간을 사용하는 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체도 만들어집니다. 자세한 내용은 [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase)를 참조하십시오.

## <a name="cdaorecordsetclose"></a><a name="close"></a>CDao레코드 집합::닫기

개체를 `CDaoRecordset` 닫으면 연결된 데이터베이스의 열린 레코드 집합 컬렉션에서 개체가 제거됩니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

개체가 `Close` `CDaoRecordset` 파괴되지 않으므로 동일한 데이터 원본 또는 `Open` 다른 데이터 원본을 호출하여 개체를 다시 사용할 수 있습니다.

보류 중인 [AddNew](#addnew) 또는 [편집](#edit) 문이 모두 취소되고 보류 중인 모든 트랜잭션이 롤백됩니다. 보류 중인 추가 또는 편집을 유지하려면 각 레코드 `Close` 집합을 호출하기 전에 [Update를](#update) 호출합니다.

호출한 `Close` `Open` 후 다시 호출할 수 있습니다. 이렇게 하면 레코드 집합 개체를 다시 사용할 수 있습니다. 더 나은 대안은 가능한 경우 [Requery를](#requery)호출하는 것입니다.

관련 정보는 DAO 도움말의 "방법 닫기" 항목을 참조하십시오.

## <a name="cdaorecordsetdelete"></a><a name="delete"></a>CDao레코드세트::D

이 멤버 함수를 호출하여 열린 다이나셋 유형 또는 테이블 형식 레코드 집합 개체에서 현재 레코드를 삭제합니다.

```
virtual void Delete();
```

### <a name="remarks"></a>설명

성공적으로 삭제되면 레코드 집합의 필드 데이터 멤버가 Null 값으로 설정되고 삭제된 레코드를 이동하려면 [이동,](#move) [검색,](#seek) [SetBookmark](#setbookmark)등 레코드 집합 탐색 멤버 함수 중 하나를 명시적으로 호출해야 합니다. 레코드 집합에서 레코드를 삭제하는 경우 호출하기 `Delete`전에 레코드 집합에 현재 레코드가 있어야 합니다. 그렇지 않으면 MFC에서 예외를 throw합니다.

`Delete`현재 레코드를 제거하고 액세스할 수 없게 만듭니다. 삭제된 레코드를 편집하거나 사용할 수는 없지만 최신 상태로 유지됩니다. 그러나 다른 레코드로 이동하면 삭제된 레코드를 다시 현재 상태로 만들 수 없습니다.

> [!CAUTION]
> 레코드 집합은 업데이터 처리용이어야 하며 호출할 `Delete`때 레코드 집합에 유효한 레코드 전류가 있어야 합니다. 예를 들어 레코드를 삭제하지만 다시 호출하기 `Delete` 전에 새 레코드로 `Delete` 스크롤하지 않으면 [CDaoException](../../mfc/reference/cdaoexception-class.md)을 throw합니다.

트랜잭션을 사용하고 [CDaoWorkspace::롤백](../../mfc/reference/cdaoworkspace-class.md#rollback) 멤버 함수를 호출하는 경우 레코드를 삭제 취소할 수 있습니다. 기준 테이블이 계단식 삭제 관계의 기본 테이블인 경우 현재 레코드를 삭제하면 외래 테이블에서 하나 이상의 레코드도 삭제될 수 있습니다. 자세한 내용은 DAO 도움말에서 "계단식 삭제" 정의를 참조하십시오.

와 `AddNew` `Edit` `Delete` 는 달리, 에 대한 호출은 `Update`에 대한 호출이 뒤따르지 않습니다.

관련 정보는 DAO 도움말의 "새 새 메서드 추가", "메서드 편집", "방법 삭제", "업데이트 방법" 및 "업데이트 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetdofieldexchange"></a><a name="dofieldexchange"></a>CDao레코드세트::DoFieldExchange

프레임워크는 이 멤버 함수를 호출하여 레코드 집합 개체의 필드 데이터 멤버와 데이터 원본의 현재 레코드의 해당 열 간에 데이터를 자동으로 교환합니다.

```
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
개체에 대한 `CDaoFieldExchange` 포인터를 포함합니다. 프레임워크는 필드 교환 작업에 대한 컨텍스트를 지정하도록 이 개체를 이미 설정했습니다.

### <a name="remarks"></a>설명

또한 레코드 집합의 선택을 위해 SQL 문 문자열의 매개 변수 자리 표시자에 매개 변수 데이터 멤버(있는 경우)를 바인딩합니다. DFx(필드 레코드 필드 교환)라고 하는 필드 데이터 교환은 레코드 집합 개체의 필드 데이터 멤버에서 데이터 원본의 레코드 필드, 데이터 원본의 레코드에서 레코드 집합 개체에 이르기까지 양방향으로 작동합니다. 열을 동적으로 바인딩하는 경우 을 구현할 `DoFieldExchange`필요가 없습니다.

파생 된 레코드 집합 클래스에 대해 구현하기 `DoFieldExchange` 위해 일반적으로 수행해야 하는 유일한 작업은 ClassWizard를 사용하여 클래스를 만들고 필드 데이터 멤버의 이름과 데이터 형식을 지정하는 것입니다. ClassWizard가 작성하는 내용에 코드를 추가하여 매개 변수 데이터 멤버를 지정할 수도 있습니다. 모든 필드를 동적으로 바인딩하려면 매개 변수 데이터 멤버를 지정하지 않으면 이 함수가 비활성 상태가 됩니다.

ClassWizard를 사용 하 여 파생 된 레코드 집합 클래스를 `DoFieldExchange` 선언 하는 경우 마법사는 다음 예제와 유사한 재정의를 씁니다.

[!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]

## <a name="cdaorecordsetedit"></a><a name="edit"></a>CDao레코드 집합::편집

이 멤버 함수를 호출하여 현재 레코드를 변경할 수 있습니다.

```
virtual void Edit();
```

### <a name="remarks"></a>설명

멤버 함수를 `Edit` 호출하면 현재 레코드필드의 변경 내용이 복사 버퍼에 복사됩니다. 원하는 레코드를 변경한 후 호출하여 `Update` 변경 내용을 저장합니다. `Edit`레코드 집합의 데이터 멤버 의 값을 저장합니다. 호출하는 `Edit`경우 변경한 다음 `Edit` 다시 호출하면 레코드 값이 첫 번째 `Edit` 호출 이전의 값으로 복원됩니다.

> [!CAUTION]
> 레코드를 편집한 다음 첫 번째 호출 `Update`없이 다른 레코드로 이동하는 작업을 수행하면 변경 내용이 경고 없이 손실됩니다. 또한 레코드 집합 또는 상위 데이터베이스를 닫으면 편집된 레코드가 경고 없이 삭제됩니다.

경우에 따라 Null(데이터가 포함되지 않은)으로 열을 업데이트할 수 있습니다. 이렇게 하려면 TRUE `SetFieldNull` 매개 변수를 사용하여 Null 필드를 표시합니다. 이렇게 하면 열이 업데이트됩니다. 값이 변경되지 않은 경우에도 데이터 원본에 필드를 작성하려면 TRUE 매개 `SetFieldDirty` 변수를 사용하여 호출합니다. 필드에 Null 값이 있는 경우에도 작동합니다.

프레임워크는 변경된 필드 데이터 멤버를 표시하여 DAO 레코드 필드 교환(DFX) 메커니즘에 의해 데이터 원본의 레코드에 기록되도록 합니다. 필드 값을 변경하면 일반적으로 필드가 자동으로 더러워지므로 [SetFieldDirty](#setfielddirty) 를 직접 호출할 필요가 거의 없지만 필드 데이터 멤버에 있는 값에 관계없이 열이 명시적으로 업데이트되거나 삽입되도록 할 수 있습니다. DFX 메커니즘은 **또한 PSEUDO NULL의**사용을 사용합니다. 자세한 내용은 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)를 참조하십시오.

이중 버퍼링 메커니즘이 사용되지 않는 경우 필드 값을 변경해도 필드가 자동으로 더티로 설정되지 않습니다. 이 경우 필드를 더티로 명시적으로 설정해야 합니다. [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 포함된 플래그는 이 자동 필드 검사를 제어합니다.

레코드 집합 개체가 다중 사용자 환경에서 비관적으로 잠겨 있으면 업데이트가 `Edit` 완료될 때까지 레코드가 잠긴 상태로 유지됩니다. 레코드 집합이 낙관적으로 잠긴 경우 레코드가 잠겨 있고 데이터베이스에서 업데이트되기 직전에 미리 편집된 레코드와 비교됩니다. 호출한 `Edit`후 레코드가 변경된 `Update` 경우 작업이 실패하고 MFC가 예외를 throw합니다. `SetLockingMode`을 통해 잠금 모드를 변경할 수 있습니다.

> [!NOTE]
> 낙관적 잠금은 항상 ODBC 및 설치 가능한 ISAM과 같은 외부 데이터베이스 형식에 사용됩니다.

을 호출한 `Edit`후에도 현재 레코드는 최신 상태로 유지됩니다. 호출하려면 `Edit`현재 레코드가 있어야 합니다. 현재 레코드가 없거나 레코드 집합이 열린 테이블 형식 또는 다이나식 레코드 집합 개체를 참조하지 않는 경우 예외가 발생합니다. 호출하면 `Edit` `CDaoException` 다음 조건에서 throw됩니다.

- 현재 레코드가 없습니다.

- 데이터베이스 또는 레코드 집합은 읽기 전용입니다.

- 레코드의 필드가 업데이터 할 수 없습니다.

- 데이터베이스 또는 레코드 집합이 다른 사용자가 단독으로 사용할 수 있습니다.

- 다른 사용자가 레코드가 포함된 페이지를 잠갔습니다.

데이터 원본이 트랜잭션을 지원하는 경우 `Edit` 트랜잭션의 일부로 호출할 수 있습니다. 호출하기 `Edit` 전에 `CDaoWorkspace::BeginTrans` 레코드 집합이 열린 후에 전화해야 합니다. 또한 호출은 `CDaoWorkspace::CommitTrans` 작업을 완료하기 `Update` 위해 호출하는 대신사용할 수 `Edit` 없습니다. 트랜잭션에 대한 자세한 내용은 `CDaoWorkspace`클래스 를 참조하십시오.

관련 정보는 DAO 도움말의 "새 새 메서드 추가", "메서드 편집", "방법 삭제", "업데이트 방법" 및 "업데이트 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetfillcache"></a><a name="fillcache"></a>CDao레코드 집합::채우기 캐시

이 멤버 함수를 호출하여 레코드 집합에서 지정된 수의 레코드를 캐시합니다.

```cpp
void FillCache(
    long* pSize = NULL,
    COleVariant* pBookmark = NULL);
```

### <a name="parameters"></a>매개 변수

*pSize*<br/>
캐시를 채울 행 수를 지정합니다. 이 매개 변수를 생략하면 기본 DAO 개체의 CacheSize 속성 설정에 의해 값이 결정됩니다.

*p북마크*<br/>
책갈피를 지정하는 [COleVariant입니다.](../../mfc/reference/colevariant-class.md) 이 책갈피로 표시된 레코드부터 캐시가 채워져 있습니다. 이 매개 변수를 생략하면 기본 DAO 개체의 CacheStart 속성으로 표시된 레코드부터 캐시가 채워지습니다.

### <a name="remarks"></a>설명

캐싱은 원격 서버에서 데이터를 검색하거나 가져오는 응용 프로그램의 성능을 향상시킵니다. 캐시는 응용 프로그램이 실행되는 동안 데이터가 다시 요청될 수 있다는 가정 하에 서버에서 가장 최근에 가져온 데이터를 보유하는 로컬 메모리의 공간입니다. 데이터가 요청되면 Microsoft Jet 데이터베이스 엔진은 서버에서 데이터를 가져오는 대신 먼저 캐시에 대한 캐시를 검사하므로 시간이 더 걸립니다. 데이터가 캐시에 저장되지 않기 때문에 비 ODBC 데이터 원본에 데이터 캐싱을 사용하면 영향을 주지 않습니다.

캐시가 가져올 때 레코드로 채워질 때까지 기다리는 대신 member 함수를 호출하여 언제든지 `FillCache` 캐시를 명시적으로 채울 수 있습니다. 한 번에 여러 레코드가 아니라 `FillCache` 한 번에 여러 레코드를 가져오기 때문에 캐시를 채우는 것이 더 빠릅니다. 예를 들어 각 레코드 화면이 표시되는 동안 응용 프로그램 `FillCache` 호출을 통해 다음 레코드 화면을 가져올 수 있습니다.

레코드 집합 개체로 액세스하는 모든 ODBC 데이터베이스에는 로컬 캐시가 있을 수 있습니다. 캐시를 만들려면 원격 데이터 원본에서 레코드 집합 개체를 `SetCacheSize` 연 `SetCacheStart` 다음 레코드 집합의 및 멤버 함수를 호출합니다. *lSize* 및 *lBookmark가* 지정한 `SetCacheSize` 범위를 부분적으로 또는 전체적으로 벗어난 `SetCacheStart`범위를 만드는 경우 이 범위를 벗어난 레코드 집합 부분은 무시되고 캐시에 로드되지 않습니다. 요청이 원격 데이터 원본에 남아 있는 것보다 많은 레코드를 요청하는 경우 `FillCache` 나머지 레코드만 가져오고 예외는 throw되지 않습니다.

캐시에서 가져온 레코드는 다른 사용자가 원본 데이터에 동시에 변경한 내용을 반영하지 않습니다.

`FillCache`레코드만 캐시되지 않은 레코드만 가져옵니다. 캐시된 모든 데이터의 업데이트를 강제로 수행하려면 `SetCacheSize` 0과 동일한 *lSize* 매개 변수를 사용하여 멤버 함수를 호출하고 원래 요청한 캐시 크기와 `FillCache`동일한 *lSize* 매개 변수를 사용하여 다시 호출한 `SetCacheSize` 다음 을 호출합니다.

관련 정보는 DAO 도움말의 "FillCache 메서드" 항목을 참조하십시오.

## <a name="cdaorecordsetfind"></a><a name="find"></a>CDao레코드 집합::찾기

비교 연산자를 사용하여 다이나셋 또는 스냅숏 형식 레코드 집합에서 특정 문자열을 찾으려면 이 멤버 함수를 호출합니다.

```
virtual BOOL Find(
    long lFindType,
    LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lFindType*<br/>
원하는 찾기 작업의 유형을 나타내는 값입니다. 사용 가능한 값은

- AFX_DAO_NEXT 일치하는 문자열의 다음 위치를 찾습니다.

- AFX_DAO_PREV 일치하는 문자열의 이전 위치를 찾습니다.

- AFX_DAO_FIRST 일치하는 문자열의 첫 번째 위치를 찾습니다.

- AFX_DAO_LAST 일치하는 문자열의 마지막 위치를 찾습니다.

*lpsz필터*<br/>
문자열 식(예: **WHERE라는**단어가 없는 SQL 문의 WHERE **절)은** 레코드를 찾는 데 사용됩니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]

### <a name="return-value"></a>Return Value

일치 하는 레코드를 찾을 경우 비영, 그렇지 않으면 0.

### <a name="remarks"></a>설명

문자열의 첫 번째, 다음, 이전 또는 마지막 인스턴스를 찾을 수 있습니다. `Find`가상 함수이므로 재정의하고 고유한 구현을 추가할 수 있습니다. 의 `FindFirst` `FindLast`및 `FindNext` `FindPrev` 멤버 함수는 `Find` 멤버 함수를 호출하므로 `Find` 모든 Find 작업의 동작을 제어하는 데 사용할 수 있습니다.

테이블 형식 레코드 집합에서 레코드를 찾으려면 [멤버](#seek) 함수를 호출합니다.

> [!TIP]
> 레코드 집합이 작을수록 더 효과적입니다. `Find` 일반적으로 특히 ODBC 데이터의 경우 원하는 레코드만 검색하는 새 쿼리를 만드는 것이 좋습니다.

관련 정보는 DAO 도움말의 "FindFirst, FindLast, FindNext, FindNext, Find이전 방법 찾기" 항목을 참조하십시오.

## <a name="cdaorecordsetfindfirst"></a><a name="findfirst"></a>CDao레코드 집합::찾기우선

지정된 조건과 일치하는 첫 번째 레코드를 찾으려면 이 멤버 함수를 호출합니다.

```
BOOL FindFirst(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lpsz필터*<br/>
문자열 식(예: **WHERE라는**단어가 없는 SQL 문의 WHERE **절)은** 레코드를 찾는 데 사용됩니다.

### <a name="return-value"></a>Return Value

일치 하는 레코드를 찾을 경우 비영, 그렇지 않으면 0.

### <a name="remarks"></a>설명

멤버 `FindFirst` 함수는 레코드 집합의 시작 부분에서 검색을 시작하고 레코드 집합의 끝까지 검색합니다.

검색에 모든 레코드를 포함하려면(특정 조건을 충족하는 레코드뿐만 아니라) Move 작업 중 하나를 사용하여 레코드에서 레코드로 이동합니다. 테이블 형식 레코드 집합에서 레코드를 찾으려면 `Seek` 멤버 함수를 호출합니다.

조건과 일치하는 레코드가 위치하지 않으면 현재 레코드 포인터가 `FindFirst` 결정되지 않고 0을 반환합니다. 레코드 집합에 조건을 충족시키는 레코드가 두 개 이상 `FindFirst` 포함된 경우 첫 `FindNext` 번째 발생을 찾고 다음 발생을 찾습니다.

> [!CAUTION]
> 현재 레코드를 편집하는 경우 다른 레코드로 이동하기 `Update` 전에 멤버 함수를 호출하여 변경 내용을 저장해야 합니다. 업데이트 하지 않고 다른 레코드로 이동 하면 변경 내용 경고 없이 손실 됩니다.

멤버 `Find` 함수는 다음 표에 지정된 위치에서 검색합니다.

|작업 찾기|Begin|검색 방향|
|---------------------|-----------|----------------------|
|`FindFirst`|레코드 집합의 시작|레코드 집합의 끝|
|`FindLast`|레코드 집합의 끝|레코드 집합의 시작|
|`FindNext`|현재 레코드|레코드 집합의 끝|
|`FindPrevious`|현재 레코드|레코드 집합의 시작|

> [!NOTE]
> 호출할 `FindLast`때 Microsoft Jet 데이터베이스 엔진은 검색을 시작하기 전에 레코드 집합을 완전히 채웁니다( 아직 완료되지 않은 경우). 첫 번째 검색은 후속 검색보다 오래 걸릴 수 있습니다.

Find 작업 중 하나를 사용하는 것은 `MoveFirst` 호출 `MoveNext`또는 조건을 지정하지 않고 첫 번째 또는 다음 레코드를 최신 상태로 만드는 호출 또는 과 동일하지 않습니다. 이동 작업을 통해 찾기 작업을 따를 수 있습니다.

찾기 작업을 사용할 때 다음 을 염두에 두십시오.

- 0이 아닌 것을 반환하면 `Find` 현재 레코드가 정의되지 않습니다. 이 경우 현재 레코드 포인터를 유효한 레코드에 다시 배치해야 합니다.

- 정방향 전용 스크롤 스냅숏 유형 레코드 집합에서는 찾기 작업을 사용할 수 없습니다.

- Microsoft Jet 데이터베이스 엔진의 미국 버전을 사용하지 않는 경우에도 날짜가 포함된 필드를 검색할 때 미국 날짜 형식(월-날짜)을 사용해야 합니다. 그렇지 않으면 일치하는 레코드를 찾을 수 없습니다.

- ODBC 데이터베이스 및 대형 다이너셋으로 작업할 때 찾기 작업을 사용하는 것이 느리다는 것을 발견할 수 있습니다. 사용자 지정된 **ORDERBY** 또는 **WHERE** 절, 매개 변수 쿼리 또는 `CDaoQuerydef` 특정 인덱싱된 레코드를 검색하는 개체를 사용하여 SQL 쿼리를 사용하여 성능을 향상시킬 수 있습니다.

관련 정보는 DAO 도움말의 "FindFirst, FindLast, FindNext, FindNext, Find이전 방법 찾기" 항목을 참조하십시오.

## <a name="cdaorecordsetfindlast"></a><a name="findlast"></a>CDao레코드 집합::찾기 마지막

지정된 조건과 일치하는 마지막 레코드를 찾으려면 이 멤버 함수를 호출합니다.

```
BOOL FindLast(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lpsz필터*<br/>
문자열 식(예: **WHERE라는**단어가 없는 SQL 문의 WHERE **절)은** 레코드를 찾는 데 사용됩니다.

### <a name="return-value"></a>Return Value

일치 하는 레코드를 찾을 경우 비영, 그렇지 않으면 0.

### <a name="remarks"></a>설명

멤버 `FindLast` 함수는 레코드 집합의 끝에서 검색을 시작하고 레코드 집합의 시작 부분으로 뒤로 검색합니다.

검색에 모든 레코드를 포함하려면(특정 조건을 충족하는 레코드뿐만 아니라) Move 작업 중 하나를 사용하여 레코드에서 레코드로 이동합니다. 테이블 형식 레코드 집합에서 레코드를 찾으려면 `Seek` 멤버 함수를 호출합니다.

조건과 일치하는 레코드가 위치하지 않으면 현재 레코드 포인터가 `FindLast` 결정되지 않고 0을 반환합니다. 레코드 집합에 조건을 충족시키는 레코드가 두 개 이상 `FindFirst` 포함된 경우 첫 `FindNext` 번째 발생을 찾고 첫 번째 발생 후 다음 발생을 찾습니다.

> [!CAUTION]
> 현재 레코드를 편집하는 경우 다른 레코드로 이동하기 `Update` 전에 멤버 함수를 호출하여 변경 내용을 저장해야 합니다. 업데이트 하지 않고 다른 레코드로 이동 하면 변경 내용 경고 없이 손실 됩니다.

Find 작업 중 하나를 사용하는 것은 `MoveFirst` 호출 `MoveNext`또는 조건을 지정하지 않고 첫 번째 또는 다음 레코드를 최신 상태로 만드는 호출 또는 과 동일하지 않습니다. 이동 작업을 통해 찾기 작업을 따를 수 있습니다.

찾기 작업을 사용할 때 다음 을 염두에 두십시오.

- 0이 아닌 것을 반환하면 `Find` 현재 레코드가 정의되지 않습니다. 이 경우 현재 레코드 포인터를 유효한 레코드에 다시 배치해야 합니다.

- 정방향 전용 스크롤 스냅숏 유형 레코드 집합에서는 찾기 작업을 사용할 수 없습니다.

- Microsoft Jet 데이터베이스 엔진의 미국 버전을 사용하지 않는 경우에도 날짜가 포함된 필드를 검색할 때 미국 날짜 형식(월-날짜)을 사용해야 합니다. 그렇지 않으면 일치하는 레코드를 찾을 수 없습니다.

- ODBC 데이터베이스 및 대형 다이너셋으로 작업할 때 찾기 작업을 사용하는 것이 느리다는 것을 발견할 수 있습니다. 사용자 지정된 **ORDERBY** 또는 **WHERE** 절, 매개 변수 쿼리 또는 `CDaoQuerydef` 특정 인덱싱된 레코드를 검색하는 개체를 사용하여 SQL 쿼리를 사용하여 성능을 향상시킬 수 있습니다.

관련 정보는 DAO 도움말의 "FindFirst, FindLast, FindNext, FindNext, Find이전 방법 찾기" 항목을 참조하십시오.

## <a name="cdaorecordsetfindnext"></a><a name="findnext"></a>CDao레코드 집합::다음 찾기

지정된 조건과 일치하는 다음 레코드를 찾으려면 이 멤버 함수를 호출합니다.

```
BOOL FindNext(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lpsz필터*<br/>
문자열 식(예: **WHERE라는**단어가 없는 SQL 문의 WHERE **절)은** 레코드를 찾는 데 사용됩니다.

### <a name="return-value"></a>Return Value

일치 하는 레코드를 찾을 경우 비영, 그렇지 않으면 0.

### <a name="remarks"></a>설명

멤버 `FindNext` 함수는 현재 레코드에서 검색을 시작하고 레코드 집합의 끝까지 검색합니다.

검색에 모든 레코드를 포함하려면(특정 조건을 충족하는 레코드뿐만 아니라) Move 작업 중 하나를 사용하여 레코드에서 레코드로 이동합니다. 테이블 형식 레코드 집합에서 레코드를 찾으려면 `Seek` 멤버 함수를 호출합니다.

조건과 일치하는 레코드가 위치하지 않으면 현재 레코드 포인터가 `FindNext` 결정되지 않고 0을 반환합니다. 레코드 집합에 조건을 충족시키는 레코드가 두 개 이상 `FindFirst` 포함된 경우 첫 `FindNext` 번째 발생을 찾고 다음 발생을 찾습니다.

> [!CAUTION]
> 현재 레코드를 편집하는 경우 다른 레코드로 이동하기 `Update` 전에 멤버 함수를 호출하여 변경 내용을 저장해야 합니다. 업데이트 하지 않고 다른 레코드로 이동 하면 변경 내용 경고 없이 손실 됩니다.

Find 작업 중 하나를 사용하는 것은 `MoveFirst` 호출 `MoveNext`또는 조건을 지정하지 않고 첫 번째 또는 다음 레코드를 최신 상태로 만드는 호출 또는 과 동일하지 않습니다. 이동 작업을 통해 찾기 작업을 따를 수 있습니다.

찾기 작업을 사용할 때 다음 을 염두에 두십시오.

- 0이 아닌 것을 반환하면 `Find` 현재 레코드가 정의되지 않습니다. 이 경우 현재 레코드 포인터를 유효한 레코드에 다시 배치해야 합니다.

- 정방향 전용 스크롤 스냅숏 유형 레코드 집합에서는 찾기 작업을 사용할 수 없습니다.

- Microsoft Jet 데이터베이스 엔진의 미국 버전을 사용하지 않는 경우에도 날짜가 포함된 필드를 검색할 때 미국 날짜 형식(월-날짜)을 사용해야 합니다. 그렇지 않으면 일치하는 레코드를 찾을 수 없습니다.

- ODBC 데이터베이스 및 대형 다이너셋으로 작업할 때 찾기 작업을 사용하는 것이 느리다는 것을 발견할 수 있습니다. 사용자 지정된 **ORDERBY** 또는 **WHERE** 절, 매개 변수 쿼리 또는 `CDaoQuerydef` 특정 인덱싱된 레코드를 검색하는 개체를 사용하여 SQL 쿼리를 사용하여 성능을 향상시킬 수 있습니다.

관련 정보는 DAO 도움말의 "FindFirst, FindLast, FindNext, FindNext, Find이전 방법 찾기" 항목을 참조하십시오.

## <a name="cdaorecordsetfindprev"></a><a name="findprev"></a>CDao레코드 집합::찾기사전

지정된 조건과 일치하는 이전 레코드를 찾으려면 이 멤버 함수를 호출합니다.

```
BOOL FindPrev(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lpsz필터*<br/>
문자열 식(예: **WHERE라는**단어가 없는 SQL 문의 WHERE **절)은** 레코드를 찾는 데 사용됩니다.

### <a name="return-value"></a>Return Value

일치 하는 레코드를 찾을 경우 비영, 그렇지 않으면 0.

### <a name="remarks"></a>설명

멤버 `FindPrev` 함수는 현재 레코드에서 검색을 시작하고 레코드 집합의 시작 부분으로 뒤로 검색합니다.

검색에 모든 레코드를 포함하려면(특정 조건을 충족하는 레코드뿐만 아니라) Move 작업 중 하나를 사용하여 레코드에서 레코드로 이동합니다. 테이블 형식 레코드 집합에서 레코드를 찾으려면 `Seek` 멤버 함수를 호출합니다.

조건과 일치하는 레코드가 위치하지 않으면 현재 레코드 포인터가 `FindPrev` 결정되지 않고 0을 반환합니다. 레코드 집합에 조건을 충족시키는 레코드가 두 개 이상 `FindFirst` 포함된 경우 첫 `FindNext` 번째 발생을 찾고 다음 발생을 찾습니다.

> [!CAUTION]
> 현재 레코드를 편집하는 경우 다른 레코드로 이동하기 `Update` 전에 멤버 함수를 호출하여 변경 내용을 저장해야 합니다. 업데이트 하지 않고 다른 레코드로 이동 하면 변경 내용 경고 없이 손실 됩니다.

Find 작업 중 하나를 사용하는 것은 `MoveFirst` 호출 `MoveNext`또는 조건을 지정하지 않고 첫 번째 또는 다음 레코드를 최신 상태로 만드는 호출 또는 과 동일하지 않습니다. 이동 작업을 통해 찾기 작업을 따를 수 있습니다.

찾기 작업을 사용할 때 다음 을 염두에 두십시오.

- 0이 아닌 것을 반환하면 `Find` 현재 레코드가 정의되지 않습니다. 이 경우 현재 레코드 포인터를 유효한 레코드에 다시 배치해야 합니다.

- 정방향 전용 스크롤 스냅숏 유형 레코드 집합에서는 찾기 작업을 사용할 수 없습니다.

- Microsoft Jet 데이터베이스 엔진의 미국 버전을 사용하지 않는 경우에도 날짜가 포함된 필드를 검색할 때 미국 날짜 형식(월-날짜)을 사용해야 합니다. 그렇지 않으면 일치하는 레코드를 찾을 수 없습니다.

- ODBC 데이터베이스 및 대형 다이너셋으로 작업할 때 찾기 작업을 사용하는 것이 느리다는 것을 발견할 수 있습니다. 사용자 지정된 **ORDERBY** 또는 **WHERE** 절, 매개 변수 쿼리 또는 `CDaoQuerydef` 특정 인덱싱된 레코드를 검색하는 개체를 사용하여 SQL 쿼리를 사용하여 성능을 향상시킬 수 있습니다.

관련 정보는 DAO 도움말의 "FindFirst, FindLast, FindNext, FindNext, Find이전 방법 찾기" 항목을 참조하십시오.

## <a name="cdaorecordsetgetabsoluteposition"></a><a name="getabsoluteposition"></a>CDao레코드 집합::GetAbsolutePosition

레코드 집합 개체의 현재 레코드의 레코드 번호를 반환합니다.

```
long GetAbsolutePosition();
```

### <a name="return-value"></a>Return Value

0에서 레코드 집합의 레코드 수까지의 정수입니다. 레코드 집합에서 현재 레코드의 서수 위치에 해당합니다.

### <a name="remarks"></a>설명

기본 DAO 개체의 절대 위치 속성 값은 0 기반입니다. 0으로 설정하면 레코드 집합의 첫 번째 레코드를 나타냅니다. [GetRecordCount](#getrecordcount)를 호출하여 레코드 집합에서 채워진 레코드 수를 확인할 수 있습니다. 호출은 `GetRecordCount` 모든 레코드에 액세스하여 개수를 결정해야 하기 때문에 시간이 걸릴 수 있습니다.

레코드 집합에 레코드가 없는 경우와 같이 현재 레코드가 없는 경우 - 1이 반환됩니다. 현재 레코드가 삭제되면 AbsolutePosition 속성 값이 정의되지 않고 MFC가 참조되는 경우 예외를 throw합니다. 다이나셋 형식 레코드 집합의 경우 시퀀스의 끝에 새 레코드가 추가됩니다.

> [!NOTE]
> 이 속성은 서로게이트 레코드 번호로 사용할 수 없습니다. 책갈피는 여전히 지정된 위치로 유지 및 반환하는 권장 되는 방법 이며 모든 유형의 레코드 집합 개체에 현재 레코드를 배치 하는 유일한 방법입니다. 특히 이전 레코드가 삭제될 때 지정된 레코드의 위치가 변경됩니다. 또한 **ORDERBY** 절을 사용하여 SQL 문으로 만들지 않는 한 레코드 집합 내의 개별 레코드 순서가 보장되지 않으므로 레코드 집합이 다시 만들어지면 지정된 레코드의 절대 위치가 동일하다는 보장은 없습니다.

> [!NOTE]
> 이 멤버 함수는 다이너셋 유형 및 스냅숏 형식 레코드 집합에만 유효합니다.

관련 정보는 DAO 도움말의 "절대 위치 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetbookmark"></a><a name="getbookmark"></a>CDao레코드 집합::Getbookmark

이 멤버 함수를 호출하여 특정 레코드에서 책갈피 값을 가져옵니다.

```
COleVariant GetBookmark();
```

### <a name="return-value"></a>Return Value

현재 레코드에서 책갈피를 나타내는 값을 반환합니다.

### <a name="remarks"></a>설명

레코드 집합 개체를 만들거나 열면 각 레코드에 해당 개체를 지원하는 경우 이미 고유한 책갈피가 있습니다. 레코드 `CanBookmark` 집합이 책갈피를 지원하는지 여부를 확인하려면 호출합니다.

개체에 책갈피 값을 할당하여 현재 레코드의 책갈피를 `COleVariant` 저장할 수 있습니다. 다른 레코드로 이동한 후 언제든지 해당 레코드로 `SetBookmark` 빠르게 돌아가려면 해당 `COleVariant` 개체의 값에 해당하는 매개 변수를 사용하여 호출합니다.

> [!NOTE]
> [다시 쿼리를](#requery) 호출하여 DAO 책갈피를 변경합니다.

관련 정보는 DAO 도움말의 "책갈피 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetcachesize"></a><a name="getcachesize"></a>CDao레코드 집합::GetCacheSize

캐시된 레코드 수를 얻으려면 이 멤버 함수를 호출합니다.

```
long GetCacheSize();
```

### <a name="return-value"></a>Return Value

ODBC 데이터 원본에서 로컬로 캐시할 데이터를 포함하는 다이너셋 형식 레코드 집합의 레코드 수를 지정하는 값입니다.

### <a name="remarks"></a>설명

데이터 캐싱은 다이너셋 유형 레코드 집합 개체를 통해 원격 서버에서 데이터를 검색하는 응용 프로그램의 성능을 향상시킵니다. 캐시는 응용 프로그램이 실행되는 동안 데이터가 다시 요청될 경우 서버에서 가장 최근에 검색된 데이터를 보유하는 로컬 메모리의 공간입니다. 데이터가 요청되면 Microsoft Jet 데이터베이스 엔진은 요청된 데이터에 대한 캐시를 먼저 서버에서 검색하는 대신 검사하므로 시간이 더 걸립니다. ODBC 데이터 원본에서 제공되지 않는 데이터는 캐시에 저장되지 않습니다.

연결된 테이블과 같은 모든 ODBC 데이터 원본에는 로컬 캐시가 있을 수 있습니다.

관련 정보는 DAO 도움말의 "CacheSize, CacheStart 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetcachestart"></a><a name="getcachestart"></a>CDao레코드 집합::겟캐시스타트

이 멤버 함수를 호출하여 캐시할 레코드 집합의 첫 번째 레코드의 책갈피 값을 가져옵니다.

```
COleVariant GetCacheStart();
```

### <a name="return-value"></a>Return Value

캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정하는 A입니다. `COleVariant`

### <a name="remarks"></a>설명

Microsoft Jet 데이터베이스 엔진은 캐시 범위 내의 레코드를 캐시 범위 내에 요청하고 서버에서 캐시 범위를 벗어난 레코드를 요청합니다.

> [!NOTE]
> 캐시에서 검색된 레코드는 다른 사용자가 원본 데이터에 동시에 변경한 내용을 반영하지 않습니다.

관련 정보는 DAO 도움말의 "CacheSize, CacheStart 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetcurrentindex"></a><a name="getcurrentindex"></a>CDao레코드 집합::GetCurrentIndex

이 멤버 함수를 호출하여 인덱싱된 테이블 유형 `CDaoRecordset` 개체에서 현재 사용 중인 인덱스를 확인합니다.

```
CString GetCurrentIndex();
```

### <a name="return-value"></a>Return Value

테이블 `CString` 유형 레코드 집합과 함께 현재 사용 중인 인덱스의 이름을 포함하는 A입니다. 인덱스가 설정되지 않은 경우 빈 문자열을 반환합니다.

### <a name="remarks"></a>설명

이 인덱스는 테이블 형식 레코드 집합에서 레코드를 정렬하기 위한 기초이며 [Seek](#seek) 멤버 함수에서 레코드를 찾는 데 사용됩니다.

개체에는 `CDaoRecordset` 두 개 이상의 인덱스가 있을 수 있지만 한 번에 하나의 인덱스만 사용할 수 [있습니다(CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 개체에는 여러 인덱스가 정의되어 있을 수 있음).

관련 정보는 DAO 도움말의 "색인 개체" 항목 및 정의 "현재 인덱스"를 참조하십시오.

## <a name="cdaorecordsetgetdatecreated"></a><a name="getdatecreated"></a>CDao레코드 집합::GetDateCreated

이 멤버 함수를 호출하여 기본 테이블이 만들어진 날짜와 시간을 검색합니다.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Return Value

기본 테이블을 만든 날짜와 시간을 포함하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체입니다.

### <a name="remarks"></a>설명

날짜 및 시간 설정은 기본 테이블이 만들어진 컴퓨터에서 파생됩니다.

관련 정보는 DAO 도움말의 "DateCreated, 마지막으로 업데이트된 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetdatelastupdated"></a><a name="getdatelastupdated"></a>CDao레코드 집합::GetDateLast업데이트

이 멤버 함수를 호출하여 스키마가 마지막으로 업데이트된 날짜와 시간을 검색합니다.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Return Value

기본 테이블 구조(스키마)의 날짜와 시간을 포함하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체가 마지막으로 업데이트되었습니다.

### <a name="remarks"></a>설명

날짜 및 시간 설정은 기본 테이블 구조(스키마)가 마지막으로 업데이트된 컴퓨터에서 파생됩니다.

관련 정보는 DAO 도움말의 "DateCreated, 마지막으로 업데이트된 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetdefaultdbname"></a><a name="getdefaultdbname"></a>CDao레코드 집합::GetDefaultDBName

이 멤버 함수를 호출하여 이 레코드 집합에 대한 데이터베이스 이름을 확인합니다.

```
virtual CString GetDefaultDBName();
```

### <a name="return-value"></a>Return Value

이 `CString` 레코드 집합이 파생되는 데이터베이스의 경로와 이름을 포함하는 A입니다.

### <a name="remarks"></a>설명

[CDaoDatabase에](../../mfc/reference/cdaodatabase-class.md)대한 포인터 없이 레코드 집합을 만든 경우 이 경로는 레코드 집합에서 기본 데이터베이스를 여는 데 사용됩니다. 기본적으로 이 함수는 빈 문자열을 반환합니다. ClassWizard에서 `CDaoRecordset`새 레코드 집합을 파생하면 이 함수가 생성됩니다.

다음 예제에서는 문자열을 올바르게 해석하는\\\\데 필요한 대로 문자열에서 double 백슬래시()를 사용하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]

## <a name="cdaorecordsetgetdefaultsql"></a><a name="getdefaultsql"></a>CDao레코드 집합::GetDefaultSQL

프레임워크는 이 멤버 함수를 호출하여 레코드 집합의 기반이 되는 기본 SQL 문을 가져옵니다.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Return Value

기본 `CString` SQL 문을 포함하는 A입니다.

### <a name="remarks"></a>설명

테이블 이름 또는 SQL **SELECT** 문일 수 있습니다.

ClassWizard를 사용 하 여 레코드 집합 클래스를 선언 하 여 기본 SQL 문을 간접적으로 정의 하 고 ClassWizard는이 작업을 수행 합니다.

null SQL 문자열을 [Open에](#open)전달하는 경우 이 함수가 호출되어 레코드 집합에 대한 테이블 이름 또는 SQL을 결정합니다.

## <a name="cdaorecordsetgeteditmode"></a><a name="geteditmode"></a>CDao레코드 집합::GetEditMode

이 멤버 함수를 호출하여 다음 값 중 하나인 편집 상태를 확인합니다.

```
short GetEditMode();
```

### <a name="return-value"></a>Return Value

현재 레코드에 대한 편집 상태를 나타내는 값을 반환합니다.

### <a name="remarks"></a>설명

|값|Description|
|-----------|-----------------|
|`dbEditNone`|편집 작업이 진행 중입니다.|
|`dbEditInProgress`|`Edit`가 호출된 경우|
|`dbEditAdd`|`AddNew`가 호출된 경우|

관련 정보는 DAO 도움말의 "편집모드 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetfieldcount"></a><a name="getfieldcount"></a>CDao레코드 집합::겟필드카운트

이 멤버 함수를 호출하여 레코드 집합에 정의된 필드(열) 수를 검색합니다.

```
short GetFieldCount();
```

### <a name="return-value"></a>Return Value

레코드 집합의 필드 수입니다.

### <a name="remarks"></a>설명

관련 정보는 DAO 도움말의 "재산 수" 항목을 참조하십시오.

## <a name="cdaorecordsetgetfieldinfo"></a><a name="getfieldinfo"></a>CDao레코드 집합::GetFieldInfo

레코드 집합의 필드에 대한 정보를 가져오려면 이 멤버 함수를 호출합니다.

```cpp
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
인덱스별 조회를 위해 레코드 집합의 필드 컬렉션에서 미리 정의된 필드의 0기반 인덱스입니다.

*Fieldinfo*<br/>
[CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조에 대한 참조입니다.

*dwInfoOptions*<br/>
검색할 레코드 집합에 대한 정보를 지정하는 옵션입니다. 사용 가능한 옵션은 함수가 반환되는 원인과 함께 여기에 나열됩니다. 최상의 성능을 얻으려면 필요한 정보 수준만 검색합니다.

- `AFX_DAO_PRIMARY_INFO`(기본값) 이름, 유형, 크기, 속성

- `AFX_DAO_SECONDARY_INFO`기본 정보, 플러스: 서수 위치, 필수, 제로 길이 허용, 정렬 순서, 외국 이름, 소스 필드, 소스 테이블

- `AFX_DAO_ALL_INFO`기본 및 보조 정보, 플러스: 기본값, 유효성 검사 규칙, 유효성 검사 텍스트

*lpszName*<br/>
필드 이름입니다.

### <a name="remarks"></a>설명

함수의 한 버전을 사용하면 인덱스별로 필드를 조회할 수 있습니다. 다른 버전에서는 이름으로 필드를 조회할 수 있습니다.

반환된 정보에 대한 설명은 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조를 참조하십시오. 이 구조에는 *dwInfoOptions*에 대한 설명에 위에 나열된 정보 항목에 해당하는 멤버가 있습니다. 한 수준에서 정보를 요청하면 이전 수준에 대한 정보도 얻을 수 있습니다.

관련 정보는 DAO 도움말의 "속성 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetfieldvalue"></a><a name="getfieldvalue"></a>CDao레코드 집합::겟필드밸류

이 멤버 함수를 호출하여 레코드 집합에서 데이터를 검색합니다.

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
필드 의 이름을 포함 하는 문자열에 대 한 포인터입니다.

*varValue*<br/>
필드 값을 `COleVariant` 저장할 개체에 대한 참조입니다.

*nIndex*<br/>
인덱스별 조회를 위해 레코드 집합의 필드 컬렉션에 있는 필드의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

값을 반환 하는 `GetFieldValue` 두 버전의 [COleVariant](../../mfc/reference/colevariant-class.md) 필드 값을 포함 하는 COleVariant 개체를 반환 합니다.

### <a name="remarks"></a>설명

이름 또는 서수 위치로 필드를 조회할 수 있습니다.

> [!NOTE]
> 개체를 반환하는 버전을 호출하는 대신 개체 참조를 `COleVariant` 매개 변수로 하는 이 멤버 함수의 `COleVariant` 버전 중 하나를 호출하는 것이 더 효율적입니다. 이 함수의 후자 버전은 이전 버전과의 호환성을 위해 유지됩니다.

DoFieldExchange 메커니즘을 사용하여 정적 바인딩 열이 아닌 런타임에 필드를 동적으로 바인딩하려면 및 `GetFieldValue` [SetFieldValue를](#setfieldvalue) 사용합니다. [DoFieldExchange](#dofieldexchange)

`GetFieldValue`메커니즘을 `DoFieldExchange` 결합하여 성능을 향상시킬 수 있습니다. 예를 들어 `GetFieldValue` 요청 시만 필요한 값을 검색하고 해당 호출을 인터페이스의 "추가 정보" 단추에 할당하는 데 사용합니다.

관련 정보는 DAO 도움말의 "필드 개체" 및 "값 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetindexcount"></a><a name="getindexcount"></a>CDao레코드 집합::GetIndexCount

이 멤버 함수를 호출하여 테이블 유형 레코드 집합에서 사용할 수 있는 인덱스 수를 확인합니다.

```
short GetIndexCount();
```

### <a name="return-value"></a>Return Value

테이블 유형 레코드 집합의 인덱스 수입니다.

### <a name="remarks"></a>설명

`GetIndexCount`는 레코드 집합의 모든 인덱스를 반복하는 데 유용합니다. 이를 `GetIndexCount` 위해 [GetIndexInfo](#getindexinfo). 다이나셋 형식 또는 스냅숏 형식 레코드 집합에서 이 멤버 함수를 호출하면 MFC가 예외를 throw합니다.

관련 정보는 DAO 도움말의 "속성 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetindexinfo"></a><a name="getindexinfo"></a>CDao레코드 집합::GetIndexInfo

이 멤버 함수를 호출하여 레코드 집합의 기본 기본 기본 테이블에 정의된 인덱스에 대한 다양한 종류의 정보를 가져옵니다.

```cpp
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
숫자 위치별 조회에 대한 테이블의 인덱스 컬렉션의 0기반 인덱스입니다.

*인덱스 정보*<br/>
[CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조에 대한 참조입니다.

*dwInfoOptions*<br/>
검색할 인덱스에 대한 정보를 지정하는 옵션입니다. 사용 가능한 옵션은 함수가 반환되는 원인과 함께 여기에 나열됩니다. 최상의 성능을 얻으려면 필요한 정보 수준만 검색합니다.

- `AFX_DAO_PRIMARY_INFO`(기본값) 이름, 필드 정보, 필드

- `AFX_DAO_SECONDARY_INFO`기본 정보 및 추가: 기본, 고유, 클러스터된, IgnoreNulls, 필수, 외국

- `AFX_DAO_ALL_INFO`기본 및 보조 정보, 플러스: 고유 개수

*lpszName*<br/>
이름으로 조회하기 위해 인덱스 개체의 이름에 대한 포인터입니다.

### <a name="remarks"></a>설명

한 버전의 함수를 사용하면 컬렉션의 위치에 따라 인덱스를 조회할 수 있습니다. 다른 버전에서는 이름으로 인덱스를 조회할 수 있습니다.

반환된 정보에 대한 설명은 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조를 참조하십시오. 이 구조에는 *dwInfoOptions*에 대한 설명에 위에 나열된 정보 항목에 해당하는 멤버가 있습니다. 한 수준에서 정보를 요청하면 이전 수준에 대한 정보도 얻을 수 있습니다.

관련 정보는 DAO 도움말의 "속성 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetlastmodifiedbookmark"></a><a name="getlastmodifiedbookmark"></a>CDao 레코드 집합::GetLast수정된 책갈피

이 멤버 함수를 호출하여 가장 최근에 추가되거나 업데이트된 레코드의 책갈피를 검색합니다.

```
COleVariant GetLastModifiedBookmark();
```

### <a name="return-value"></a>Return Value

가장 `COleVariant` 최근에 추가하거나 변경한 레코드를 나타내는 책갈피를 포함하는 책갈피입니다.

### <a name="remarks"></a>설명

레코드 집합 개체를 만들거나 열면 각 레코드에 해당 개체를 지원하는 경우 이미 고유한 책갈피가 있습니다. [GetBookmark에](#getbookmark) 전화하여 레코드 집합이 책갈피를 지원하는지 확인합니다. 레코드 집합이 책갈피를 지원하지 `CDaoException` 않으면 a가 throw됩니다.

레코드를 추가하면 레코드 집합의 끝에 나타나며 현재 레코드가 아닙니다. 새 레코드를 현재 상태로 `GetLastModifiedBookmark` 만들려면 `SetBookmark` 호출한 다음 호출하여 새로 추가된 레코드로 돌아갑니다.

관련 정보는 DAO 도움말의 "LastModified 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetlockingmode"></a><a name="getlockingmode"></a>CDao레코드 집합::겟잠금 모드

이 멤버 함수를 호출하여 레코드 집합에 적용되는 잠금 유형을 확인합니다.

```
BOOL GetLockingMode();
```

### <a name="return-value"></a>Return Value

비영의 유형이 비관적인 경우, 그렇지 않으면 낙관적 레코드 잠금을 위한 0입니다.

### <a name="remarks"></a>설명

비관적 잠금이 적용되면 편집 [멤버](#edit) 함수를 호출하는 즉시 편집 중인 레코드를 포함하는 데이터 페이지가 잠깁니다. [업데이트](#update) 또는 [멤버 닫기](#close) 함수 또는 이동 또는 찾기 작업을 호출할 때 페이지가 잠금 해제됩니다.

낙관적 잠금이 적용되면 레코드가 포함된 데이터 페이지가 멤버 함수로 레코드를 `Update` 업데이트하는 동안에만 잠깁니다.

ODBC 데이터 원본으로 작업할 때 잠금 모드는 항상 낙관적입니다.

관련 정보는 DAO 도움말의 "LockEdits 속성" 및 "다중 사용자 응용 프로그램의 잠금 동작" 항목을 참조하십시오.

## <a name="cdaorecordsetgetname"></a><a name="getname"></a>CDao레코드 집합::GetName

이 멤버 함수를 호출하여 레코드 집합의 이름을 검색합니다.

```
CString GetName();
```

### <a name="return-value"></a>Return Value

레코드 `CString` 집합의 이름을 포함하는 A입니다.

### <a name="remarks"></a>설명

레코드 집합의 이름은 문자로 시작해야 하며 최대 40자를 포함할 수 있습니다. 숫자와 밑줄 문자를 포함할 수 있지만 문장 부호 나 공백을 포함 할 수는 없습니다.

관련 정보는 DAO 도움말의 "이름 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetparamvalue"></a><a name="getparamvalue"></a>CDao레코드 집합::겟파라임밸류

기본 DAOParameter 개체에 저장된 지정된 매개 변수의 현재 값을 검색하려면 이 멤버 함수를 호출합니다.

```
virtual COleVariant GetParamValue(int nIndex);
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
기본 DAOParameter 개체에서 매개 변수의 숫자 위치입니다.

*lpszName*<br/>
원하는 값을 가진 매개 변수의 이름입니다.

### <a name="return-value"></a>Return Value

매개 변수의 값을 포함 하는 클래스 [COleVariant의](../../mfc/reference/colevariant-class.md) 개체입니다.

### <a name="remarks"></a>설명

이름 또는 컬렉션의 숫자 위치로 매개 변수에 액세스할 수 있습니다.

관련 정보는 DAO 도움말의 "매개 변수 개체" 항목을 참조하십시오.

## <a name="cdaorecordsetgetpercentposition"></a><a name="getpercentposition"></a>CDao레코드 집합::GetPercent포지션

다이너셋 유형 또는 스냅숏 형식 레코드 집합으로 `GetPercentPosition` 작업할 때 레코드 집합을 완전히 채우기 전에 호출하는 경우 이동 량은 [GetRecordCount](#getrecordcount)를 호출하여 표시된 대로 액세스한 레코드 수와 동일합니다.

```
float GetPercentPosition();
```

### <a name="return-value"></a>Return Value

레코드 집합의 레코드 백분율을 기반으로 레코드 집합 개체에서 현재 레코드의 대략적인 위치를 나타내는 0에서 100 사이의 숫자입니다.

### <a name="remarks"></a>설명

[MoveLast를](#movelast) 호출하여 모든 레코드 집합의 채우기를 완료하여 마지막 레코드로 이동할 수 있지만 상당한 시간이 걸릴 수 있습니다.

인덱스가 `GetPercentPosition` 없는 테이블을 포함하여 세 가지 유형의 레코드 집합 개체를 모두 호출할 수 있습니다. 그러나 외부 데이터베이스에 `GetPercentPosition` 대한 통과 쿼리에서 열린 레코드 집합이나 정방향 전용 스크롤 스냅숏을 호출할 수는 없습니다. 현재 레코드가 없거나 현재 레코드가 삭제된 경우 `CDaoException` a가 throw됩니다.

관련 정보는 DAO 도움말의 "백분율 위치 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetrecordcount"></a><a name="getrecordcount"></a>CDao레코드 집합::겟레코드 카운트

이 멤버 함수를 호출하여 레코드 집합에 액세스한 레코드 수를 확인합니다.

```
long GetRecordCount();
```

### <a name="return-value"></a>Return Value

레코드 집합 개체에서 액세스한 레코드 수를 반환합니다.

### <a name="remarks"></a>설명

`GetRecordCount`모든 레코드에 액세스할 때까지 다이너셋 형식 또는 스냅숏 형식 레코드 집합에 포함된 레코드 수를 나타내지 않습니다. 이 멤버 함수 호출을 완료하는 데 상당한 시간이 걸릴 수 있습니다.

마지막 레코드에 액세스하면 반환 값은 레코드 집합에서 삭제되지 않은 레코드의 총 수를 나타냅니다. 마지막 레코드에 액세스하도록 강제하려면 레코드 `MoveLast` `FindLast` 집합에 대한 또는 멤버 함수를 호출합니다. SQL Count를 사용하여 쿼리가 반환할 대략적인 레코드 수를 결정할 수도 있습니다.

응용 프로그램이 다이너셋 형식 레코드 집합의 레코드를 삭제하면 반환 값이 `GetRecordCount` 줄어듭니다. 그러나 다른 사용자가 삭제한 레코드는 `GetRecordCount` 현재 레코드가 삭제된 레코드에 배치될 때까지 반영되지 않습니다. 레코드 수에 영향을 주는 트랜잭션을 실행 한 후 `GetRecordCount` 트랜잭션을 롤백 하는 경우 나머지 레코드의 실제 수를 반영 하지 않습니다.

스냅숏 `GetRecordCount` 형식 레코드 집합의 값은 기본 테이블의 변경사항의 영향을 받지 않습니다.

테이블 형식 `GetRecordCount` 레코드 집합의 값은 테이블의 대략적인 레코드 수를 반영하며 테이블 레코드가 추가되고 삭제될 때 즉시 영향을 받습니다.

레코드가 없는 레코드 집합은 0 값을 반환합니다. 연결된 테이블 또는 ODBC 데이터베이스로 `GetRecordCount` 작업할 때항상 반환 - 1. 레코드 `Requery` 집합에서 멤버 함수를 호출하면 `GetRecordCount` 쿼리가 다시 실행된 것처럼 값이 재설정됩니다.

관련 정보는 DAO 도움말의 "RecordCount 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetsql"></a><a name="getsql"></a>CDao 레코드 집합::GetSQL

이 멤버 함수를 호출하여 레코드 집합이 열릴 때 레코드 집합의 레코드를 선택하는 데 사용된 SQL 문을 가져옵니다.

```
CString GetSQL() const;
```

### <a name="return-value"></a>Return Value

SQL `CString` 문을 포함하는 A입니다.

### <a name="remarks"></a>설명

일반적으로 SQL **SELECT** 문이 됩니다.

반환되는 `GetSQL` 문자열은 일반적으로 [open](#open) 멤버 함수에 *lpszSQL* 매개 변수의 레코드 집합에 전달한 문자열과 다릅니다. 이는 레코드 집합이 ClassWizard로 지정한 내용과 `Open` [m_strFilter](#m_strfilter) 및 [m_strSort](#m_strsort) 데이터 멤버에 지정한 내용을 기반으로 전체 SQL 문을 생성하기 때문입니다.

> [!NOTE]
> 을 호출한 후에만 `Open`이 멤버 함수를 호출합니다.

관련 정보는 DAO 도움말의 "SQL 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgettype"></a><a name="gettype"></a>CDao레코드 집합::GetType

레코드 집합을 연 후 이 멤버 함수를 호출하여 레코드 집합 개체의 형식을 확인합니다.

```
short GetType();
```

### <a name="return-value"></a>Return Value

레코드 집합의 형식을 나타내는 다음 값 중 하나입니다.

- `dbOpenTable`테이블 유형 레코드 집합

- `dbOpenDynaset`다이나셋 형 레코드 집합

- `dbOpenSnapshot`스냅샷 유형 레코드 집합

### <a name="remarks"></a>설명

관련 정보는 DAO 도움말의 "속성 유형" 항목을 참조하십시오.

## <a name="cdaorecordsetgetvalidationrule"></a><a name="getvalidationrule"></a>CDao레코드 집합::GetvalidationRule

이 멤버 함수를 호출하여 데이터의 유효성을 검사하는 데 사용되는 규칙을 확인합니다.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Return Value

레코드가 `CString` 변경되었거나 테이블에 추가될 때 레코드의 데이터의 유효성을 검사하는 값을 포함하는 개체입니다.

### <a name="remarks"></a>설명

이 규칙은 텍스트 기반이며 기본 테이블이 변경될 때마다 적용됩니다. 데이터가 합법적이지 않은 경우 MFC는 예외를 throw합니다. 반환 된 오류 메시지는 기본 필드 개체의 ValidationText 속성의 텍스트(지정된 경우) 또는 기본 필드 개체의 ValidationRule 속성에 의해 지정된 식의 텍스트입니다. [GetValidationText를](#getvalidationtext) 호출하여 오류 메시지의 텍스트를 가져올 수 있습니다.

예를 들어 해당 월의 요일이 필요한 레코드의 필드에는 "DAY BETWEEN 1 과 31"과 같은 유효성 검사 규칙이 있을 수 있습니다.

관련 정보는 DAO 도움말의 "유효성 검사규칙 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetgetvalidationtext"></a><a name="getvalidationtext"></a>CDao레코드 집합::유효성 검사 텍스트

기본 필드 개체의 ValidationText 속성의 텍스트를 검색 하려면이 멤버 함수를 호출 합니다.

```
CString GetValidationText();
```

### <a name="return-value"></a>Return Value

`CString` 필드의 값이 기본 필드 개체의 유효성 검사 규칙을 충족하지 않는 경우 표시되는 메시지의 텍스트를 포함하는 개체입니다.

### <a name="remarks"></a>설명

관련 정보는 DAO 도움말의 "유효성 검사텍스트 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetisbof"></a><a name="isbof"></a>CDao 레코드 집합::IsBOF

레코드에서 레코드로 스크롤하기 전에 이 멤버 함수를 호출하여 레코드 집합의 첫 번째 레코드 보다 먼저 갔는지 여부를 알아봅니다.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Return Value

레코드 집합에 레코드가 없거나 첫 번째 레코드 앞에 뒤로 스크롤한 경우 Nonzero입니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

함께 `IsEOF` 호출하여 `IsBOF` 레코드 집합에 레코드가 포함되어 있는지 또는 비어 있는지 확인할 수도 있습니다. 호출 `Open`직후 에 레코드 집합에 레코드가 `IsBOF` 없는 경우 0이 아닌 반환합니다. 레코드가 하나 이상 있는 레코드 집합을 열면 첫 번째 `IsBOF` 레코드가 현재 레코드이고 0을 반환합니다.

첫 번째 레코드가 현재 레코드이고 `MovePrev` `IsBOF` 호출하면 이후에 0이 아닌 레코드가 반환됩니다. 0이 아닌 것을 `MovePrev`반환하고 호출하면 `IsBOF` 예외가 throw됩니다. 0이 아닌 것을 반환하면 `IsBOF` 현재 레코드가 정의되지 않으며 현재 레코드가 필요한 모든 작업은 예외가 발생합니다.

특정 방법 및 `IsBOF` `IsEOF` 설정의 효과:

- 내부적으로 `Open*` 호출하면 레코드 집합의 첫 번째 레코드가 `MoveFirst`호출하여 현재 레코드를 만듭니다. 따라서 빈 `Open` 레코드 집합을 `IsBOF` `IsEOF` 호출하면 영하지 않은 레코드가 반환됩니다. (실패 `MoveFirst` 또는 `MoveLast` 호출의 동작은 다음 표를 참조하십시오.)

- 레코드를 성공적으로 찾은 모든 `IsBOF` 이동 `IsEOF` 작업은 모두 0을 발생시고 반환합니다.

- 호출 다음에 새 `Update` 레코드를 성공적으로 삽입하는 호출은 `IsBOF` 0을 반환하지만 `IsEOF` 이미 0이 아닌 경우에만 반환됩니다. `AddNew` `IsEOF` 의 상태는 항상 변경되지 않습니다. Microsoft Jet 데이터베이스 엔진에서 정의한 대로 빈 레코드 집합의 현재 레코드 포인터는 파일 끝에 있으므로 현재 레코드 후에 새 레코드가 삽입됩니다.

- 레코드 `Delete` 집합에서 남은 레코드만 제거하더라도 모든 호출은 `IsBOF` 또는 `IsEOF`의 값을 변경하지 않습니다.

이 표에서는 `IsBOF` /  `IsEOF`다른 조합으로 허용되는 Move 작업을 보여 주며 의 다른 조합을 보여 주며 있습니다.

||이동우선, 이동마지막|무브프레프,<br /><br /> < 0 이동|이동 0|Movenext<br /><br /> > 0 이동|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`=영하지 않은,<br /><br /> `IsEOF`=0|허용됨|예외|예외|허용됨|
|`IsBOF`=0,<br /><br /> `IsEOF`=비영점|허용됨|허용됨|예외|예외|
|모두 제로가 아닌|예외|예외|예외|예외|
|둘 다 0|허용됨|허용됨|허용됨|허용됨|

Move 작업을 허용한다고 해서 작업이 레코드를 성공적으로 찾다는 의미는 아닙니다. 단순히 지정된 Move 작업을 수행하려는 시도가 허용되고 예외를 생성하지 않음을 나타냅니다. `IsBOF` 및 `IsEOF` 멤버 함수의 값은 이동 시도의 결과로 변경될 수 있습니다.

값 `IsBOF` 및 `IsEOF` 설정에 대한 레코드를 찾지 않는 Move 작업의 효과는 다음 표에 나와 있습니다.

||Isbof|Iseof|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|비영점|비영점|
|`Move` 0|변경 내용 없음|변경 내용 없음|
|`MovePrev`, `Move` < 0|비영점|변경 내용 없음|
|`MoveNext`, `Move` > 0|변경 내용 없음|비영점|

관련 정보는 DAO 도움말의 "BOF, EOF 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetisdeleted"></a><a name="isdeleted"></a>CDao레코드 집합::삭제됨

이 멤버 함수를 호출하여 현재 레코드가 삭제되었는지 확인합니다.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Return Value

레코드 집합이 삭제된 레코드에 배치된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

레코드로 스크롤하여 `IsDeleted` TRUE(영하지 않은)를 반환하는 경우 다른 레코드 집합 작업을 수행하려면 먼저 다른 레코드로 스크롤해야 합니다.

> [!NOTE]
> 스냅샷 또는 테이블 유형 레코드 집합의 레코드에 대해 삭제된 상태를 확인할 필요가 없습니다. 스냅샷에서 레코드를 삭제할 수 없으므로 을 `IsDeleted`호출할 필요가 없습니다. 테이블 형식 레코드 집합의 경우 삭제된 레코드가 레코드 집합에서 실제로 제거됩니다. 사용자, 다른 사용자 또는 다른 레코드 집합에서 레코드가 삭제되면 해당 레코드로 다시 스크롤할 수 없습니다. 따라서 을 호출할 `IsDeleted`필요가 없습니다.

다이너셋에서 레코드를 삭제하면 레코드 집합에서 제거되며 해당 레코드로 다시 스크롤할 수 없습니다. 그러나 다이너셋의 레코드가 다른 사용자나 동일한 테이블을 기반으로 다른 레코드 집합에서 삭제된 경우 나중에 해당 레코드로 스크롤할 때 TRUE가 `IsDeleted` 반환됩니다.

관련 정보는 DAO 도움말의 "방법 삭제", "마지막으로 수정된 속성" 및 "편집모드 속성"을 참조하십시오.

## <a name="cdaorecordsetiseof"></a><a name="iseof"></a>CDao 레코드 집합::IsEOF

레코드에서 레코드로 스크롤할 때 이 멤버 함수를 호출하여 레코드 집합의 마지막 레코드를 초과했는지 여부를 알아봅니다.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Return Value

레코드 집합에 레코드가 없거나 마지막 레코드 를 넘어 스크롤한 경우 Nonzero입니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

호출하여 `IsEOF` 레코드 집합에 레코드가 포함되어 있는지 또는 비어 있는지 확인할 수도 있습니다. 호출 `Open`직후 에 레코드 집합에 레코드가 `IsEOF` 없는 경우 0이 아닌 반환합니다. 레코드가 하나 이상 있는 레코드 집합을 열면 첫 번째 `IsEOF` 레코드가 현재 레코드이고 0을 반환합니다.

마지막 레코드가 호출할 `MoveNext`때 현재 `IsEOF` 레코드인 경우 이후에 0이 아닌 레코드가 반환됩니다. 0이 아닌 것을 `MoveNext`반환하고 호출하면 `IsEOF` 예외가 throw됩니다. 0이 아닌 것을 반환하면 `IsEOF` 현재 레코드가 정의되지 않으며 현재 레코드가 필요한 모든 작업은 예외가 발생합니다.

특정 방법 및 `IsBOF` `IsEOF` 설정의 효과:

- 내부적으로 `Open` 호출하면 레코드 집합의 첫 번째 레코드가 `MoveFirst`호출하여 현재 레코드를 만듭니다. 따라서 빈 `Open` 레코드 집합을 `IsBOF` `IsEOF` 호출하면 영하지 않은 레코드가 반환됩니다. (실패한 `MoveFirst` 호출의 동작은 다음 표를 참조하십시오.)

- 레코드를 성공적으로 찾은 모든 `IsBOF` 이동 `IsEOF` 작업은 모두 0을 발생시고 반환합니다.

- 호출 다음에 새 `Update` 레코드를 성공적으로 삽입하는 호출은 `IsBOF` 0을 반환하지만 `IsEOF` 이미 0이 아닌 경우에만 반환됩니다. `AddNew` `IsEOF` 의 상태는 항상 변경되지 않습니다. Microsoft Jet 데이터베이스 엔진에서 정의한 대로 빈 레코드 집합의 현재 레코드 포인터는 파일 끝에 있으므로 현재 레코드 후에 새 레코드가 삽입됩니다.

- 레코드 `Delete` 집합에서 남은 레코드만 제거하더라도 모든 호출은 `IsBOF` 또는 `IsEOF`의 값을 변경하지 않습니다.

이 표에서는 `IsBOF` /  `IsEOF`다른 조합으로 허용되는 Move 작업을 보여 주며 의 다른 조합을 보여 주며 있습니다.

||이동우선, 이동마지막|무브프레프,<br /><br /> < 0 이동|이동 0|Movenext<br /><br /> > 0 이동|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`=영하지 않은,<br /><br /> `IsEOF`=0|허용됨|예외|예외|허용됨|
|`IsBOF`=0,<br /><br /> `IsEOF`=비영점|허용됨|허용됨|예외|예외|
|모두 제로가 아닌|예외|예외|예외|예외|
|둘 다 0|허용됨|허용됨|허용됨|허용됨|

Move 작업을 허용한다고 해서 작업이 레코드를 성공적으로 찾다는 의미는 아닙니다. 단순히 지정된 Move 작업을 수행하려는 시도가 허용되고 예외를 생성하지 않음을 나타냅니다. `IsBOF` 및 `IsEOF` 멤버 함수의 값은 Move를 시도한 결과로 변경될 수 있습니다.

값 `IsBOF` 및 `IsEOF` 설정에 대한 레코드를 찾지 않는 Move 작업의 효과는 다음 표에 나와 있습니다.

||Isbof|Iseof|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|비영점|비영점|
|`Move` 0|변경 내용 없음|변경 내용 없음|
|`MovePrev`, `Move` < 0|비영점|변경 내용 없음|
|`MoveNext`, `Move` > 0|변경 내용 없음|비영점|

관련 정보는 DAO 도움말의 "BOF, EOF 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetisfielddirty"></a><a name="isfielddirty"></a>CDao 레코드 집합::IsFieldDirty

이 멤버 함수를 호출하여 다이너셋의 지정된 필드 데이터 멤버가 "더티"(변경됨)로 플래그가 지정되었는지 확인합니다.

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
확인하려는 상태 또는 NULL을 사용하여 필드가 더러워진지 여부를 확인하는 필드 데이터 멤버에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

지정된 필드 데이터 멤버에 더티로 플래그가 지정된 경우 Nonzero입니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

모든 더러운 필드 데이터 멤버의 데이터는 현재 레코드가 `Update` (호출 또는 `CDaoRecordset` `Edit` `AddNew`다음)의 멤버 함수에 대한 호출에 의해 업데이트될 때 데이터 원본의 레코드로 전송됩니다. 이 지식을 사용하면 필드 데이터 멤버의 플래그를 해제하여 열에 표시하지 않도록 데이터 원본에 기록되지 않도록 하는 등의 추가 단계를 수행할 수 있습니다.

`IsFieldDirty`을 통해 `DoFieldExchange`구현됩니다.

## <a name="cdaorecordsetisfieldnull"></a><a name="isfieldnull"></a>CDao레코드 집합::이스필드널

이 멤버 함수를 호출하여 레코드 집합의 지정된 필드 데이터 멤버가 Null로 플래그가 지정되었는지 확인합니다.

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
확인하려는 상태 또는 NULL을 사용하여 필드가 Null인지 여부를 확인하는 필드 데이터 멤버에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

지정된 필드 데이터 멤버에 Null로 플래그가 지정된 경우 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

(데이터베이스 용어에서 Null은 "값이 없음"을 의미하며 C++에서 NULL과 동일하지 않습니다. 필드 데이터 멤버에 Null플래그가 지정되면 값이 없는 현재 레코드의 열로 해석됩니다.

> [!NOTE]
> 다음 코드 예제에서 `IsFieldNull` 설명하는 것처럼 특정 상황에서는 사용하는 것이 비효율적일 수 있습니다.

[!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]

> [!NOTE]
> `CDaoRecordset`에서 파생되지 않고 동적 레코드 바인딩을 사용하는 경우 예제와 같이 VT_NULL 사용해야 합니다.

## <a name="cdaorecordsetisfieldnullable"></a><a name="isfieldnullable"></a>CDao레코드 집합::IsFieldNullable

이 멤버 함수를 호출하여 지정된 필드 데이터 멤버가 "null"인지 여부를 결정합니다(Null 값으로 설정할 수 있습니다. C++ NULL은 Null과 같지 않으며 데이터베이스 용어에서 "값이 없음"을 의미합니다.

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
확인하려는 상태 또는 NULL을 사용하여 필드가 Null인지 여부를 확인하는 필드 데이터 멤버에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

지정된 필드 데이터 멤버를 Null로 만들 수 있는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

Null이 될 수 없는 필드에는 값이 있어야 합니다. 레코드를 추가하거나 업데이트할 때 이러한 필드를 Null로 설정하려고 하면 데이터 원본이 추가 `Update` 또는 업데이트를 거부하고 예외를 throw합니다. 호출할 때가 아니라 `Update`호출할 때 `SetFieldNull`예외가 발생합니다.

## <a name="cdaorecordsetisopen"></a><a name="isopen"></a>CDao레코드 집합::이열기

이 멤버 함수를 호출하여 레코드 집합이 열려 있는지 확인합니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Return Value

레코드 집합 개체 `Open` 또는 `Requery` 멤버 함수가 이전에 호출되고 레코드 집합이 닫히지 않은 경우 Nonzero입니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

## <a name="cdaorecordsetm_bcheckcachefordirtyfields"></a><a name="m_bcheckcachefordirtyfields"></a>CDao레코드 집합::m_bCheckCacheForDirtyFields

캐시된 필드가 자동으로 더티(변경) 및 Null로 표시되는지 여부를 나타내는 플래그가 포함되어 있습니다.

### <a name="remarks"></a>설명

플래그는 TRUE로 기본설정됩니다. 이 데이터 멤버의 설정은 전체 이중 버퍼링 메커니즘을 제어합니다. 플래그를 TRUE로 설정하면 DFX 메커니즘을 사용하여 필드별로 캐싱을 끌 수 있습니다. 플래그를 FALSE로 설정하면 `SetFieldDirty` `SetFieldNull` 직접 호출해야 합니다.

을 호출하기 전에 `Open`이 데이터 멤버를 설정합니다. 이 메커니즘은 주로 사용 편의성을 위한 것입니다. 변경이 수행될 때 필드의 이중 버퍼링으로 인해 성능이 느려질 수 있습니다.

## <a name="cdaorecordsetm_nfields"></a><a name="m_nfields"></a>CDao레코드 집합::m_nFields

레코드 집합 클래스의 필드 데이터 멤버 수와 데이터 원본에서 레코드 집합에서 선택한 열 수를 포함합니다.

### <a name="remarks"></a>설명

레코드 집합 클래스의 생성자는 정적으로 바인딩된 필드의 올바른 수로 초기화해야 `m_nFields` 합니다. ClassWizard는 레코드 집합 클래스를 선언하는 데 사용할 때 이 초기화를 작성합니다. 수동으로 작성할 수도 있습니다.

프레임워크는 이 번호를 사용하여 필드 데이터 멤버와 데이터 원본의 현재 레코드의 해당 열 간의 상호 작용을 관리합니다.

> [!NOTE]
> 이 번호는 매개 변수를 `DoFieldExchange` `SetFieldType` `CDaoFieldExchange::outputColumn`호출한 후 등록된 출력 열 수와 일치해야 합니다.

을 통해 `CDaoRecordset::GetFieldValue` 열을 동적으로 바인딩할 `CDaoRecordset::SetFieldValue`수 있습니다. 이렇게 하면 멤버 함수에서 DFX 함수 호출 `m_nFields` 수를 반영하기 위해 개수를 증분할 필요가 없습니다. `DoFieldExchange`

## <a name="cdaorecordsetm_nparams"></a><a name="m_nparams"></a>CDao레코드 집합::m_nParams

레코드 집합 클래스의 매개 변수 데이터 멤버 수(레코드 집합의 쿼리와 함께 전달된 매개 변수 수)를 포함합니다.

### <a name="remarks"></a>설명

레코드 집합 클래스에 매개 변수 데이터 멤버가 있는 경우 클래스의 생성자는 올바른 번호로 *m_nParams* 초기화해야 합니다. *m_nParams* 값은 기본값의 0으로 설정됩니다. 수동으로 수행해야 하는 매개 변수 데이터 멤버를 추가하는 경우 매개 변수 수를 반영하기 위해 클래스 생성자에 초기화를 수동으로 추가해야 *합니다(m_strFilter* 또는 *m_strSort* 문자열의 '자리 표시자 수만큼 이상 이어야 합니다).

프레임워크는 레코드 집합의 쿼리를 매개변수화할 때 이 번호를 사용합니다.

> [!NOTE]
> 이 번호는 매개 변수를 `DoFieldExchange` `SetFieldType` `CFieldExchange::param`호출한 후 등록된 "params" 수와 일치해야 합니다.

관련 정보는 DAO 도움말의 "매개 변수 개체" 항목을 참조하십시오.

## <a name="cdaorecordsetm_pdaorecordset"></a><a name="m_pdaorecordset"></a>CDao레코드 집합::m_pDAORecordset

개체의 기본을 기본으로 하는 DAO 레코드 `CDaoRecordset` 집합 개체에 대 한 OLE 인터페이스에 대 한 포인터를 포함 합니다.

### <a name="remarks"></a>설명

DAO 인터페이스에 직접 액세스해야 하는 경우 이 포인터를 사용합니다.

관련 정보는 DAO 도움말의 "레코드 집합 개체" 항목을 참조하십시오.

## <a name="cdaorecordsetm_pdatabase"></a><a name="m_pdatabase"></a>CDao레코드 집합::m_pDatabase

레코드 집합이 `CDaoDatabase` 데이터 원본에 연결된 개체에 대한 포인터를 포함합니다.

### <a name="remarks"></a>설명

이 변수는 두 가지 방법으로 설정됩니다. 일반적으로 레코드 집합 개체를 생성할 때 이미 열려 `CDaoDatabase` 있는 개체에 대한 포인터를 전달합니다. 대신 NULL을 통과하면 `CDaoRecordset` `CDaoDatabase` 개체를 만들고 엽니다. 두 경우 `CDaoRecordset` 모두 이 변수에 포인터를 저장합니다.

일반적으로 `m_pDatabase`에 저장된 포인터를 직접 사용할 필요가 없습니다. 그러나 `CDaoRecordset`에 대한 사용자 고유의 확장을 작성하는 경우 포인터를 사용해야 할 수 있습니다. 예를 들어, 직접 `CDaoException`던지는 경우 포인터가 필요할 수 있습니다.

관련 정보는 DAO 도움말의 "데이터베이스 개체" 항목을 참조하십시오.

## <a name="cdaorecordsetm_strfilter"></a><a name="m_strfilter"></a>CDao레코드 집합::m_strFilter

SQL 문의 **WHERE** 절을 생성하는 데 사용되는 문자열을 포함합니다.

### <a name="remarks"></a>설명

레코드 집합을 필터링하기 위해 **예약된 WHERE** 라는 단어는 포함되지 않습니다. 이 데이터 멤버의 사용은 테이블 형식 레코드 집합에 적용되지 않습니다. `m_strFilter` 포인터를 사용하여 레코드 집합을 열 때 에는 아무런 영향을 주지 `CDaoQueryDef` 않습니다.

Microsoft Jet 데이터베이스 엔진의 미국 버전을 사용하지 않는 경우에도 날짜가 포함된 필드를 필터링할 때 미국 날짜 형식(월-일)을 사용합니다. 그렇지 않으면 예상대로 데이터가 필터링되지 않을 수 있습니다.

관련 정보는 DAO 도움말의 "속성 필터링" 항목을 참조하십시오.

## <a name="cdaorecordsetm_strsort"></a><a name="m_strsort"></a>CDao레코드 집합::m_strSort

예약 된 단어 **ORDERBY** 없이 SQL 문의 ORDERBY 절을 포함 하는 **문자열을**포함 합니다.

### <a name="remarks"></a>설명

다이나셋 및 스냅숏 형식 레코드 집합 개체를 정렬할 수 있습니다.

테이블 형식 레코드 집합 개체를 정렬할 수 없습니다. 테이블 형식 레코드 집합의 정렬 순서를 확인하려면 [SetCurrentIndex](#setcurrentindex)를 호출합니다.

*m_strSort* 사용하면 포인터를 `CDaoQueryDef` 사용하여 레코드 집합을 열 때 아무런 영향을 주지 않습니다.

관련 정보는 DAO 도움말의 "속성 정렬" 항목을 참조하십시오.

## <a name="cdaorecordsetmove"></a><a name="move"></a>CDao레코드 집합::이동

이 멤버 함수를 호출하여 레코드 집합 *lRows* 레코드를 현재 레코드에서 배치합니다.

```
virtual void Move(long lRows);
```

### <a name="parameters"></a>매개 변수

*로우스 (rows)*<br/>
앞으로 또는 뒤로 이동할 레코드 수입니다. 양수 값은 레코드 집합의 끝을 향해 앞으로 이동합니다. 음수 값은 시작 부분으로 뒤로 이동합니다.

### <a name="remarks"></a>설명

앞으로 또는 뒤로 이동할 수 있습니다. `Move( 1 )``MoveNext`과 같으며 `Move( -1 )` 에 `MovePrev`해당합니다.

> [!CAUTION]
> 레코드 집합에 `Move` 레코드가 없는 경우 함수를 호출하면 예외가 발생합니다. 일반적으로 Move 작업 `IsBOF` `IsEOF` 전에 둘 다 호출하여 레코드 집합에 레코드가 있는지 여부를 확인합니다. 전화 또는 `Open` `Requery`에 `IsBOF` 전화한 `IsEOF`후 .

> [!NOTE]
> 레코드 집합의 시작 또는 끝을 지나 스크롤한 `IsBOF` `IsEOF` 경우(또는 0이 `Move` 아닌 것을 `CDaoException`반환) 를 throw하는 호출이 됩니다.

> [!NOTE]
> 현재 레코드가 `Move` 업데이트되거나 추가되는 동안 함수를 호출하면 경고 없이 업데이트가 손실됩니다.

정방향 `Move` 전용 스크롤 스냅숏을 호출할 때 *lRows* 매개 변수는 양수 정수여야 하며 책갈피는 허용되지 않으므로 앞으로만 이동할 수 있습니다.

레코드 집합의 첫 번째 레코드, 마지막 레코드, 다음 레코드 또는 `MoveFirst` `MoveLast`이전 `MoveNext`레코드를 현재 레코드를 호출하려면 을 `MovePrev` 호출합니다.

관련 정보는 DAO 도움말의 "이동 방법" 및 "MoveFirst, MoveLast, MoveNext, MoveNext, MovePrevious 메서드" 항목을 참조하십시오.

## <a name="cdaorecordsetmovefirst"></a><a name="movefirst"></a>CDao레코드 집합::이동우선

이 멤버 함수를 호출하여 레코드 집합(있는 경우)의 첫 번째 레코드를 현재 레코드로 만듭니다.

```cpp
void MoveFirst();
```

### <a name="remarks"></a>설명

레코드 집합을 연 `MoveFirst` 직후에 호출할 필요가 없습니다. 이 때 첫 번째 레코드(있는 경우)는 자동으로 현재 레코드입니다.

> [!CAUTION]
> 레코드 집합에 `Move` 레코드가 없는 경우 함수를 호출하면 예외가 발생합니다. 일반적으로 Move 작업 `IsBOF` `IsEOF` 전에 둘 다 호출하여 레코드 집합에 레코드가 있는지 여부를 확인합니다. 전화 또는 `Open` `Requery`에 `IsBOF` 전화한 `IsEOF`후 .

> [!NOTE]
> 현재 레코드가 `Move` 업데이트되거나 추가되는 동안 함수를 호출하면 경고 없이 업데이트가 손실됩니다.

`Move` 조건을 적용하지 않고 함수를 사용하여 레코드에서 레코드로 이동합니다. 찾기 작업을 사용하여 특정 조건을 충족하는 다이너셋 유형 또는 스냅숏 형식 레코드 집합 개체에서 레코드를 찾습니다. 테이블 형식 레코드 집합 개체에서 레코드를 `Seek`찾으려면 을 호출합니다.

레코드 집합이 테이블 유형 레코드 집합을 참조하는 경우 이동은 테이블의 현재 인덱스를 따릅니다. 기본 DAO 개체의 인덱스 속성을 사용하여 현재 인덱스를 설정할 수 있습니다. 현재 인덱스를 설정하지 않으면 반환된 레코드의 순서가 정의되지 않습니다.

SQL 쿼리 `MoveLast` 또는 쿼리 def를 기반으로 레코드 집합 개체를 호출하는 경우 쿼리가 강제로 완료되고 레코드 집합 개체가 완전히 채워집니다.

정방향 전용 `MoveFirst` `MovePrev` 스크롤 스냅숏을 사용하면 또는 멤버 함수를 호출할 수 없습니다.

레코드 집합 개체에서 현재 레코드의 위치를 특정 레코드 수를 앞으로 또는 `Move`뒤로 이동하려면 을 호출합니다.

관련 정보는 DAO 도움말의 "이동 방법" 및 "MoveFirst, MoveLast, MoveNext, MoveNext, MovePrevious 메서드" 항목을 참조하십시오.

## <a name="cdaorecordsetmovelast"></a><a name="movelast"></a>CDao레코드 집합::무브라스트

이 멤버 함수를 호출하여 레코드의 마지막 레코드(있는 경우)를 현재 레코드로 만듭니다.

```cpp
void MoveLast();
```

### <a name="remarks"></a>설명

> [!CAUTION]
> 레코드 집합에 `Move` 레코드가 없는 경우 함수를 호출하면 예외가 발생합니다. 일반적으로 Move 작업 `IsBOF` `IsEOF` 전에 둘 다 호출하여 레코드 집합에 레코드가 있는지 여부를 확인합니다. 전화 또는 `Open` `Requery`에 `IsBOF` 전화한 `IsEOF`후 .

> [!NOTE]
> 현재 레코드가 `Move` 업데이트되거나 추가되는 동안 함수를 호출하면 경고 없이 업데이트가 손실됩니다.

`Move` 조건을 적용하지 않고 함수를 사용하여 레코드에서 레코드로 이동합니다. 찾기 작업을 사용하여 특정 조건을 충족하는 다이너셋 유형 또는 스냅숏 형식 레코드 집합 개체에서 레코드를 찾습니다. 테이블 형식 레코드 집합 개체에서 레코드를 `Seek`찾으려면 을 호출합니다.

레코드 집합이 테이블 유형 레코드 집합을 참조하는 경우 이동은 테이블의 현재 인덱스를 따릅니다. 기본 DAO 개체의 인덱스 속성을 사용하여 현재 인덱스를 설정할 수 있습니다. 현재 인덱스를 설정하지 않으면 반환된 레코드의 순서가 정의되지 않습니다.

SQL 쿼리 `MoveLast` 또는 쿼리 def를 기반으로 레코드 집합 개체를 호출하는 경우 쿼리가 강제로 완료되고 레코드 집합 개체가 완전히 채워집니다.

레코드 집합 개체에서 현재 레코드의 위치를 특정 레코드 수를 앞으로 또는 `Move`뒤로 이동하려면 을 호출합니다.

관련 정보는 DAO 도움말의 "이동 방법" 및 "MoveFirst, MoveLast, MoveNext, MoveNext, MovePrevious 메서드" 항목을 참조하십시오.

## <a name="cdaorecordsetmovenext"></a><a name="movenext"></a>CDao레코드 집합::MoveNext

이 멤버 함수를 호출하여 레코드 집합의 다음 레코드를 현재 레코드로 만듭니다.

```cpp
void MoveNext();
```

### <a name="remarks"></a>설명

이전 레코드로 이동하기 전에 호출하는 `IsBOF` 것이 좋습니다. `CDaoException` if를 `IsBOF` `MovePrev` throw하는 호출은 0이 아닌 것을 반환하며, 이는 첫 번째 레코드 앞에 이미 스크롤했거나 레코드 집합에서 선택한 레코드가 없음을 나타냅니다.

> [!CAUTION]
> 레코드 집합에 `Move` 레코드가 없는 경우 함수를 호출하면 예외가 발생합니다. 일반적으로 Move 작업 `IsBOF` `IsEOF` 전에 둘 다 호출하여 레코드 집합에 레코드가 있는지 여부를 확인합니다. 전화 또는 `Open` `Requery`에 `IsBOF` 전화한 `IsEOF`후 .

> [!NOTE]
> 현재 레코드가 `Move` 업데이트되거나 추가되는 동안 함수를 호출하면 경고 없이 업데이트가 손실됩니다.

`Move` 조건을 적용하지 않고 함수를 사용하여 레코드에서 레코드로 이동합니다. 찾기 작업을 사용하여 특정 조건을 충족하는 다이너셋 유형 또는 스냅숏 형식 레코드 집합 개체에서 레코드를 찾습니다. 테이블 형식 레코드 집합 개체에서 레코드를 `Seek`찾으려면 을 호출합니다.

레코드 집합이 테이블 유형 레코드 집합을 참조하는 경우 이동은 테이블의 현재 인덱스를 따릅니다. 기본 DAO 개체의 인덱스 속성을 사용하여 현재 인덱스를 설정할 수 있습니다. 현재 인덱스를 설정하지 않으면 반환된 레코드의 순서가 정의되지 않습니다.

레코드 집합 개체에서 현재 레코드의 위치를 특정 레코드 수를 앞으로 또는 `Move`뒤로 이동하려면 을 호출합니다.

관련 정보는 DAO 도움말의 "이동 방법" 및 "MoveFirst, MoveLast, MoveNext, MoveNext, MovePrevious 메서드" 항목을 참조하십시오.

## <a name="cdaorecordsetmoveprev"></a><a name="moveprev"></a>CDao레코드 집합::무브프레프

이 멤버 함수를 호출하여 레코드 집합의 이전 레코드를 현재 레코드로 만듭니다.

```cpp
void MovePrev();
```

### <a name="remarks"></a>설명

이전 레코드로 이동하기 전에 호출하는 `IsBOF` 것이 좋습니다. `CDaoException` if를 `IsBOF` `MovePrev` throw하는 호출은 0이 아닌 것을 반환하며, 이는 첫 번째 레코드 앞에 이미 스크롤했거나 레코드 집합에서 선택한 레코드가 없음을 나타냅니다.

> [!CAUTION]
> 레코드 집합에 `Move` 레코드가 없는 경우 함수를 호출하면 예외가 발생합니다. 일반적으로 Move 작업 `IsBOF` `IsEOF` 전에 둘 다 호출하여 레코드 집합에 레코드가 있는지 여부를 확인합니다. 전화 또는 `Open` `Requery`에 `IsBOF` 전화한 `IsEOF`후 .

> [!NOTE]
> 현재 레코드가 `Move` 업데이트되거나 추가되는 동안 함수를 호출하면 경고 없이 업데이트가 손실됩니다.

`Move` 조건을 적용하지 않고 함수를 사용하여 레코드에서 레코드로 이동합니다. 찾기 작업을 사용하여 특정 조건을 충족하는 다이너셋 유형 또는 스냅숏 형식 레코드 집합 개체에서 레코드를 찾습니다. 테이블 형식 레코드 집합 개체에서 레코드를 `Seek`찾으려면 을 호출합니다.

레코드 집합이 테이블 유형 레코드 집합을 참조하는 경우 이동은 테이블의 현재 인덱스를 따릅니다. 기본 DAO 개체의 인덱스 속성을 사용하여 현재 인덱스를 설정할 수 있습니다. 현재 인덱스를 설정하지 않으면 반환된 레코드의 순서가 정의되지 않습니다.

정방향 전용 `MoveFirst` `MovePrev` 스크롤 스냅숏을 사용하면 또는 멤버 함수를 호출할 수 없습니다.

레코드 집합 개체에서 현재 레코드의 위치를 특정 레코드 수를 앞으로 또는 `Move`뒤로 이동하려면 을 호출합니다.

관련 정보는 DAO 도움말의 "이동 방법" 및 "MoveFirst, MoveLast, MoveNext, MoveNext, MovePrevious 메서드" 항목을 참조하십시오.

## <a name="cdaorecordsetopen"></a><a name="open"></a>CDao레코드 집합::열기

레코드 집합에 대한 레코드를 검색하려면 이 멤버 함수를 호출해야 합니다.

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

*n오픈타입*<br/>
해당 값은

- `dbOpenDynaset`양방향 스크롤이 있는 다이너셋 형식 레코드 집합입니다. 이것이 기본값입니다.

- `dbOpenTable`양방향 스크롤이 있는 테이블 유형 레코드 집합입니다.

- `dbOpenSnapshot`양방향 스크롤이 있는 스냅숏 유형 레코드 집합입니다.

*lpszSQL*<br/>
다음 중 하나를 포함하는 문자열 포인터:

- NULL 포인터입니다.

- 하나 이상의 테이블defs 및/또는 쿼리 defs(쉼표 로 구분된)의 이름입니다.

- SQL **SELECT** 문(선택적으로 SQL **WHERE** 또는 **ORDERBY** 절포함).

- 통과 쿼리입니다.

*nOptions*<br/>
아래에 나열된 옵션 중 하나 이상. 기본값은 0입니다. 가능한 값은 다음과 같습니다.

- `dbAppendOnly`새 레코드만 추가할 수 있습니다(다이너셋 형식 레코드 집합만). 이 옵션은 말 그대로 레코드만 추가될 수 있음을 의미합니다. MFC ODBC 데이터베이스 클래스에는 레코드를 검색하고 추가할 수 있는 추가 전용 옵션이 있습니다.

- `dbForwardOnly`레코드 집합은 정방향 전용 스크롤 스냅숏입니다.

- `dbSeeChanges`다른 사용자가 편집중인 데이터를 변경하는 경우 예외를 생성합니다.

- `dbDenyWrite`다른 사용자는 레코드를 수정하거나 추가할 수 없습니다.

- `dbDenyRead`다른 사용자는 레코드를 볼 수 없습니다(테이블 유형 레코드 집합만).

- `dbReadOnly`레코드만 볼 수 있습니다. 다른 사용자는 수정할 수 있습니다.

- `dbInconsistent`일관되지 않은 업데이트가 허용됩니다(다이너셋 유형 레코드 집합만).

- `dbConsistent`일관된 업데이트만 허용됩니다(다이너셋 유형 레코드 집합만).

> [!NOTE]
> 상수는 `dbConsistent` `dbInconsistent` 상호 배타적입니다. 둘 중 하나만 사용할 수 있지만 지정된 인스턴스에서 `Open`둘 다 사용할 수는 없습니다.

*p테이블데프*<br/>
[CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 개체에 대한 포인터입니다. 이 버전은 테이블 형식 레코드 집합에만 유효합니다. 이 옵션을 사용하는 `CDaoDatabase` 경우 를 생성하는 `CDaoRecordset` 데 사용되는 포인터가 사용되지 않습니다. 오히려 tabledef가 있는 데이터베이스가 사용됩니다.

*pQueryDef*<br/>
[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 개체에 대한 포인터입니다. 이 버전은 다이너셋 유형 및 스냅숏 형식 레코드 집합에만 유효합니다. 이 옵션을 사용하는 `CDaoDatabase` 경우 를 생성하는 `CDaoRecordset` 데 사용되는 포인터가 사용되지 않습니다. 오히려 쿼리def가 있는 데이터베이스가 사용됩니다.

### <a name="remarks"></a>설명

호출하기 `Open`전에 레코드 집합 개체를 생성해야 합니다. 다음과 같은 여러 가지 방법으로 이 작업을 수행할 수 있습니다.

- 레코드 집합 개체를 생성할 때 이미 `CDaoDatabase` 열려 있는 개체에 포인터를 전달합니다.

- 레코드 집합 개체를 생성할 때 열려 `CDaoDatabase` 있지 않은 개체에 포인터를 전달합니다. 레코드 집합은 `CDaoDatabase` 개체를 열지만 레코드 집합 개체가 닫히면 개체가 닫히지 않습니다.

- 레코드 집합 개체를 생성할 때 NULL 포인터를 전달합니다. 레코드 집합 개체는 Microsoft Access의 이름을 얻기 위해 호출합니다. `GetDefaultDBName` 열려면 MDB 파일입니다. 그런 다음 레코드 `CDaoDatabase` 집합은 개체를 열고 레코드 집합이 열려 있는 한 열어 유지합니다. 레코드 집합을 호출하면 `Close` `CDaoDatabase` 개체도 닫힙됩니다.

    > [!NOTE]
    >  레코드 집합이 개체를 `CDaoDatabase` 열면 비독점 액세스 권한이 있는 데이터 원본이 열립니다.

`Open` *lpszSQL* 매개 변수를 사용하는 버전의 경우 레코드 집합이 열리면 여러 가지 방법 중 하나로 레코드를 검색할 수 있습니다. 첫 번째 옵션은 에 DFX 함수를 두는 것입니다. `DoFieldExchange` 두 번째 옵션은 멤버 함수를 `GetFieldValue` 호출하여 동적 바인딩을 사용하는 것입니다. 이러한 옵션은 별도로 또는 조합하여 구현할 수 있습니다. 결합된 경우 을 호출할 때 SQL 문을 직접 전달해야 합니다. `Open`

개체에서 전달하는 위치의 `Open` 두 번째 버전을 사용하면 결과 열을 사용하여 DFX 메커니즘을 통해 `DoFieldExchange` 바인딩하고/또는 을 통해 `GetFieldValue`동적으로 바인딩할 수 있습니다. `CDaoTableDef`

> [!NOTE]
> 테이블 형식 `Open` 레코드 `CDaoTableDef` 집합에 대한 개체만 호출할 수 있습니다.

개체에서 전달하는 위치의 `Open` 세 번째 버전을 사용하면 해당 쿼리가 실행되고 결과 열을 통해 `DoFieldExchange` 바인딩하고 DFX 메커니즘을 바인딩하거나 을 통해 `GetFieldValue`동적으로 바인딩할 수 있습니다. `CDaoQueryDef`

> [!NOTE]
> 다이나셋 `Open` 유형 `CDaoQueryDef` 및 스냅숏 형식 레코드 집합에 대한 개체만 호출할 수 있습니다.

매개 변수를 `Open` 사용하는 첫 번째 버전의 경우 다음 표에 표시된 조건에 따라 레코드가 선택됩니다. `lpszSQL`

|`lpszSQL` 매개 변수의 값|선택한 레코드는|예제|
|--------------------------------------|----------------------------------------|-------------|
|NULL|에서 반환된 `GetDefaultSQL`문자열입니다.||
|하나 이상의 테이블def및/또는 쿼리def 이름의 쉼표로 구분된 목록입니다.|에 표시된 모든 `DoFieldExchange`열은|`"Customer"`|
|**테이블** 목록에서 열 목록 **선택**|지정된 tabledef(들) 및/또는 쿼리 def(들)에서 지정된 열입니다.|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|

일반적인 절차는 NULL을 에 `Open`전달하는 것입니다. 이 경우 `Open` 호출 `GetDefaultSQL`- 파생 클래스를 만들 때 ClassWizard가 `CDaoRecordset`생성하는 재정의 가능한 멤버 함수입니다. 이 값은 ClassWizard에서 지정한 tabledef 및/또는 querydef 이름을 제공합니다. 대신 *lpszSQL* 매개 변수에서 다른 정보를 지정할 수 있습니다.

전달하는 것이 `Open` 무엇이든 간에 쿼리에 대한 최종 SQL 문자열을 생성합니다(문자열에 전달한 *lpszSQL* 문자열에 SQL **WHERE** 및 **ORDERBY** 절이 추가될 수 있음) 쿼리를 실행합니다. 호출 `Open`한 후 호출하여 `GetSQL` 구성된 문자열을 검사할 수 있습니다.

레코드 집합 클래스의 필드 데이터 멤버는 선택한 데이터의 열에 바인딩됩니다. 레코드가 반환되면 첫 번째 레코드가 현재 레코드가 됩니다.

필터 또는 정렬과 같은 레코드 집합에 대한 옵션을 설정하려는 경우 레코드 집합 개체를 생성한 `m_strSort` `m_strFilter` 후 를 호출하기 `Open`전에 . 레코드 집합이 이미 열려 있는 후 레코드 집합의 레코드를 `Requery`새로 고치려면 을 호출합니다.

다이나셋 `Open` 형식 또는 스냅숏 형식 레코드 집합을 호출하거나 데이터 원본이 연결된 테이블을 나타내는 SQL 문 또는 tabledef를 참조하는 경우 형식 인수에 사용할 `dbOpenTable` 수 없습니다. 이렇게 하면 MFC에서 예외를 throw합니다. tabledef 개체가 연결된 테이블을 나타내는지 여부를 확인하려면 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 개체를 만들고 [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) 멤버 함수를 호출합니다.

동일한 `dbSeeChanges` 레코드를 편집하거나 삭제할 때 다른 사용자 또는 컴퓨터에서 변경한 내용을 트랩하려면 플래그를 사용합니다. 예를 들어 두 사용자가 동일한 레코드를 편집하기 시작하면 `Update` 멤버 함수를 호출하는 첫 번째 사용자가 성공합니다. 두 `Update` 번째 사용자가 호출하면 `CDaoException` a가 throw됩니다. 마찬가지로 두 번째 사용자가 `Delete` 호출하여 레코드를 삭제하려고 시도하고 첫 번째 사용자가 이미 `CDaoException` 변경한 경우 a가 발생합니다.

일반적으로 사용자가 업데이트하는 `CDaoException` 동안 이 값을 얻는 경우 코드는 필드의 내용을 새로 고치고 새로 수정된 값을 검색해야 합니다. 삭제 하는 과정에서 예외가 발생 하는 경우 코드에 새 레코드 데이터와 데이터가 최근에 변경 되었음을 나타내는 메시지를 표시할 수 있습니다. 이 시점에서 코드는 사용자가 여전히 레코드를 삭제하려는 확인을 요청할 수 있습니다.

> [!TIP]
> 정방향 전용 스크롤 옵션()`dbForwardOnly`을 사용하여 응용 프로그램이 ODBC 데이터 원본에서 열린 레코드 집합을 통해 단일 패스를 할 때 성능을 향상시킵니다.

관련 정보는 DAO 도움말의 "OpenRecordset 방법" 항목을 참조하십시오.

## <a name="cdaorecordsetrequery"></a><a name="requery"></a>CDao레코드 집합::다시 쿼리

이 멤버 함수를 호출하여 레코드 집합을 다시 빌드(새로 고침)합니다.

```
virtual void Requery();
```

### <a name="remarks"></a>설명

레코드가 반환되면 첫 번째 레코드가 현재 레코드가 됩니다.

레코드 집합이 사용자 또는 다른 사용자가 데이터 원본에 만드는 추가 및 삭제를 반영하려면 를 호출하여 `Requery`레코드 집합을 다시 빌드해야 합니다. 레코드 집합이 다이너셋인 경우 사용자 또는 다른 사용자가 기존 레코드에 대해 하는 업데이트는 자동으로 반영되지만 추가는 포함되지 않습니다. 레코드 집합이 스냅샷인 경우 `Requery` 다른 사용자의 편집 및 추가 및 삭제를 반영하기 위해 호출해야 합니다.

다이나셋 또는 스냅숏의 경우 `Requery` 매개 변수 값을 사용하여 레코드 집합을 다시 빌드할 때마다 호출합니다. m_strFilter [및](#m_strfilter) [m_strSort](#m_strsort) 설정하여 새 필터 `Requery`또는 정렬을 설정합니다. 을 호출하기 `Requery`전에 매개 변수 데이터 멤버에 새 값을 할당하여 새 매개 변수를 설정합니다.

레코드 집합을 다시 빌드하려는 시도가 실패하면 레코드 집합이 닫힙됩니다. 호출하기 `Requery`전에 [CanRestart](#canrestart) 멤버 함수를 호출하여 레코드 집합을 다시 쿼리할 수 있는지 여부를 확인할 수 있습니다. `CanRestart`성공할 것이라는 `Requery` 보장은 없습니다.

> [!CAUTION]
> 을 `Requery` 호출한 `Open`후에만 호출합니다.

> [!NOTE]
> [다시 쿼리를](#requery) 호출하여 DAO 책갈피를 변경합니다.

호출이 `CanRestart` 0을 `Requery` 반환하는 경우 다이너셋 형식 또는 스냅숏 형식 레코드 집합을 호출할 수 없으며 테이블 형식 레코드 집합에서 사용할 수도 없습니다.

호출 `Requery` `IsBOF` 한 `IsEOF` 후 둘 다 및 비0을 반환하는 경우 쿼리는 레코드를 반환하지 않으며 레코드 집합에는 데이터가 포함되지 않습니다.

관련 정보는 DAO 도움말의 "메서드 다시 쿼리" 항목을 참조하십시오.

## <a name="cdaorecordsetseek"></a><a name="seek"></a>CDao 레코드 집합::검색

이 멤버 함수를 호출하여 현재 인덱스에 대한 지정된 조건을 충족하고 해당 레코드를 현재 레코드로 만드는 인덱싱된 테이블 유형 레코드 집합 개체에서 레코드를 찾습니다.

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

*lpsz비교*<br/>
다음 문자열 표현식 중 하나는 "<", "=",\<"=", "=", ">=" 또는 ">"입니다.

*pKey1*<br/>
값이 인덱스의 첫 번째 필드에 해당하는 [COleVariant에](../../mfc/reference/colevariant-class.md) 대한 포인터입니다. 필수 사항입니다.

*pKey2*<br/>
값이 있는 `COleVariant` 경우 인덱스의 두 번째 필드에 해당하는 a에 대한 포인터입니다. 기본값은 NULL로 설정됩니다.

*pKey3*<br/>
값이 있는 `COleVariant` 경우 인덱스의 세 번째 필드에 해당하는 a에 대한 포인터입니다. 기본값은 NULL로 설정됩니다.

*pKeyArray*<br/>
변형 배열에 대한 포인터입니다. 배열 크기는 인덱스의 필드 수에 해당합니다.

*키*<br/>
인덱스의 필드 수인 배열크기에 해당하는 정수입니다.

> [!NOTE]
> 키에 와일드카드를 지정하지 마십시오. 와일드카드로 인해 `Seek` 일치하는 레코드가 반환되지 않습니다.

### <a name="return-value"></a>Return Value

일치 하는 레코드를 찾을 경우 비영, 그렇지 않으면 0.

### <a name="remarks"></a>설명

두 번째(배열) 버전을 `Seek` 사용하여 4개 이상의 필드의 인덱스를 처리합니다.

`Seek`이를 통해 테이블 유형 레코드 집합에서 고성능 인덱스를 검색할 수 있습니다. 호출하기 `SetCurrentIndex` `Seek`전에 호출하여 현재 인덱스를 설정해야 합니다. 인덱스가 고유하지 않은 키 필드 또는 `Seek` 필드를 식별하는 경우 조건을 충족시키는 첫 번째 레코드를 찾습니다. 인덱스를 설정하지 않으면 예외가 throw됩니다.

UNICODE 레코드 집합을 만들지 않는 경우 `COleVariant` 개체를 ANSI로 명시적으로 선언해야 합니다. 이 작업은 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant) `VT_BSTRT` `COleVariant` *(lpszSrc,* **,** *vtSrc)* **)** vtSrc가 `VT_BSTRT` 설정된 생성자 형식(ANSI)을 **(** 사용하거나 *vtSrc가* 설정된 [SetString(lpszSrc,](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc)을* **)** 사용하여 수행할 수 있습니다. *vtSrc*

호출할 `Seek`때 하나 이상의 키 값과 비교 연산자("<", "=",\<"=", "=", ">=" 또는 ">")를 전달합니다. `Seek`지정된 키 필드를 검색하고 *lpsz@d.kr] lpsz@fa.kr* *pKey1* 발견되면 `Seek` 0이 아닌 것을 반환하고 해당 레코드를 현재 상태로 만듭니다. 일치 `Seek` 를 찾지 못하면 `Seek` 0을 반환하고 현재 레코드가 정의되지 않습니다. DAO를 직접 사용하는 경우 NoMatch 속성을 명시적으로 확인해야 합니다.

"=", ">=" 또는 ">"인 경우 `lpszComparison` 인덱스의 시작 부분에서 `Seek` 시작합니다. *lpsz@<* <=="인 경우 인덱스 `Seek` 의 끝에서 시작하여 끝에 중복 된 인덱스 항목이 없는 한 뒤로 검색합니다. 이 경우 `Seek` 인덱스 끝에 있는 중복 인덱스 항목 중 임의의 항목에서 시작합니다.

을 사용할 `Seek`때 현재 레코드가 있을 필요는 없습니다.

특정 조건을 조정하는 다이너셋 유형 또는 스냅숏 형식 레코드 집합에서 레코드를 찾으려면 찾기 작업을 사용합니다. 특정 조건을 충족하는 레코드뿐만 아니라 모든 레코드를 포함하려면 Move 작업을 사용하여 레코드에서 레코드로 이동합니다.

연결된 테이블은 다이너셋 형식 또는 스냅숏 형식 레코드 집합으로 열어야 하므로 연결된 형식의 연결된 테이블을 호출할 `Seek` 수 없습니다. 그러나 설치 가능한 `CDaoDatabase::Open` ISAM 데이터베이스를 직접 열어야 하는 `Seek` 경우 성능이 느려질 수 있지만 해당 데이터베이스의 테이블을 호출할 수 있습니다.

관련 정보는 DAO 도움말의 "방법 찾기" 항목을 참조하십시오.

## <a name="cdaorecordsetsetabsoluteposition"></a><a name="setabsoluteposition"></a>CDao레코드 집합::설정절대위치

레코드 집합 개체의 현재 레코드의 상대 레코드 번호를 설정합니다.

```cpp
void SetAbsolutePosition(long lPosition);
```

### <a name="parameters"></a>매개 변수

*lPosition*<br/>
레코드 집합에서 현재 레코드의 서수 위치에 해당합니다.

### <a name="remarks"></a>설명

호출을 `SetAbsolutePosition` 사용하면 다이너셋 유형 또는 스냅숏 형식 레코드 집합의 서수 위치를 기반으로 현재 레코드 포인터를 특정 레코드에 배치할 수 있습니다. [GetAbsolutePosition](#getabsoluteposition)를 호출하여 현재 레코드 번호를 확인할 수도 있습니다.

> [!NOTE]
> 이 멤버 함수는 다이너셋 유형 및 스냅숏 형식 레코드 집합에만 유효합니다.

기본 DAO 개체의 절대 위치 속성 값은 0 기반입니다. 0으로 설정하면 레코드 집합의 첫 번째 레코드를 나타냅니다. 채워진 레코드 수보다 큰 값을 설정하면 MFC가 예외를 throw합니다. `GetRecordCount` 멤버 함수를 호출하여 레코드 집합에서 채워진 레코드 수를 확인할 수 있습니다.

현재 레코드가 삭제되면 AbsolutePosition 속성 값이 정의되지 않고 MFC가 참조되는 경우 예외를 throw합니다. 시퀀스의 끝에 새 레코드가 추가됩니다.

> [!NOTE]
> 이 속성은 서로게이트 레코드 번호로 사용할 수 없습니다. 책갈피는 여전히 지정된 위치로 유지 및 반환하는 권장 되는 방법 이며 책갈피를 지 조는 레코드 집합 개체의 모든 유형에 현재 레코드를 배치 하는 유일한 방법입니다. 특히 이전 레코드가 삭제될 때 지정된 레코드의 위치가 변경됩니다. 또한 **ORDERBY** 절을 사용하여 SQL 문으로 만들지 않는 한 레코드 집합 내의 개별 레코드 순서가 보장되지 않으므로 레코드 집합이 다시 만들어지면 지정된 레코드의 절대 위치가 동일하다는 보장은 없습니다.

관련 정보는 DAO 도움말의 "절대 위치 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetsetbookmark"></a><a name="setbookmark"></a>CDao레코드 집합::세트북마크

이 멤버 함수를 호출하여 지정된 책갈피를 포함하는 레코드에 레코드 집합을 배치합니다.

```cpp
void SetBookmark(COleVariant varBookmark);
```

### <a name="parameters"></a>매개 변수

*바북마크*<br/>
특정 레코드에 대한 책갈피 값을 포함하는 [COleVariant](../../mfc/reference/colevariant-class.md) 개체입니다.

### <a name="remarks"></a>설명

레코드 집합 개체를 만들거나 열면 각 레코드에 이미 고유한 책갈피가 있습니다. 개체에 값을 호출하고 `GetBookmark` 저장하여 현재 레코드의 책갈피를 검색할 수 `COleVariant` 있습니다. 나중에 저장된 책갈피 값을 `SetBookmark` 사용하여 호출하여 해당 레코드로 돌아갈 수 있습니다.

> [!NOTE]
> [다시 쿼리를](#requery) 호출하여 DAO 책갈피를 변경합니다.

UNICODE 레코드 집합을 만들지 않는 경우 `COleVariant` 개체를 ANSI로 명시적으로 선언해야 합니다. 이 작업은 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant) `VT_BSTRT` `COleVariant` *(lpszSrc,* **,** *vtSrc)* **)** vtSrc가 `VT_BSTRT` 설정된 생성자 형식(ANSI)을 **(** 사용하거나 *vtSrc가* 설정된 [SetString(lpszSrc,](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc)을* **)** 사용하여 수행할 수 있습니다. *vtSrc*

관련 정보는 DAO 도움말의 "책갈피 속성" 항목 및 북마크 가능한 속성"을 참조하십시오.

## <a name="cdaorecordsetsetcachesize"></a><a name="setcachesize"></a>CDao레코드 집합::세트캐시크기

이 멤버 함수를 호출하여 캐시할 레코드 수를 설정합니다.

```cpp
void SetCacheSize(long lSize);
```

### <a name="parameters"></a>매개 변수

*l사이즈*<br/>
레코드 수를 지정합니다. 일반적인 값은 100입니다. 0으로 설정하면 캐싱이 꺼집니다. 설정은 5레코드에서 1200개 레코드 사이여야 합니다. 캐시는 상당한 양의 메모리를 사용할 수 있습니다.

### <a name="remarks"></a>설명

캐시는 응용 프로그램이 실행되는 동안 데이터가 다시 요청될 경우 서버에서 가장 최근에 검색된 데이터를 보유하는 로컬 메모리의 공간입니다. 데이터 캐싱은 다이너셋 유형 레코드 집합 개체를 통해 원격 서버에서 데이터를 검색하는 응용 프로그램의 성능을 향상시킵니다. 데이터가 요청되면 Microsoft Jet 데이터베이스 엔진은 요청된 데이터에 대한 캐시를 먼저 서버에서 검색하는 대신 검사하므로 시간이 더 걸립니다. ODBC 데이터 원본에서 제공되지 않는 데이터는 캐시에 저장되지 않습니다.

연결된 테이블과 같은 모든 ODBC 데이터 원본에는 로컬 캐시가 있을 수 있습니다. 캐시를 만들려면 원격 데이터 원본에서 레코드 집합 개체를 `SetCacheStart` 열고 및 멤버 함수를 `FillCache` `SetCacheSize` 호출한 다음 Move 작업 중 하나를 사용하여 멤버 함수 또는 단계를 호출합니다. `SetCacheSize` 멤버 함수의 *lSize* 매개 변수는 응용 프로그램에서 한 번에 작업할 수 있는 레코드 수를 기반으로 할 수 있습니다. 예를 들어 레코드 집합을 화면에 표시할 데이터의 원본으로 사용하는 경우 `SetCacheSize` *lSize* 매개 변수를 20으로 전달하여 한 번에 20개의 레코드를 표시할 수 있습니다.

관련 정보는 DAO 도움말의 "CacheSize, CacheStart 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetsetcachestart"></a><a name="setcachestart"></a>CDao레코드 집합::세트캐시스타트

이 멤버 함수를 호출하여 캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정합니다.

```cpp
void SetCacheStart(COleVariant varBookmark);
```

### <a name="parameters"></a>매개 변수

*바북마크*<br/>
캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정하는 [COleVariant입니다.](../../mfc/reference/colevariant-class.md)

### <a name="remarks"></a>설명

`SetCacheStart` 멤버 함수의 varBookmark 매개 변수에 대 한 레코드의 *책갈피* 값을 사용할 수 있습니다. 현재 레코드로 캐시를 시작하고 [SetBookmark를](#setbookmark)사용하여 해당 레코드에 대한 책갈피를 설정하고 책갈피 값을 멤버 `SetCacheStart` 함수의 매개 변수로 전달하려는 레코드를 만듭니다.

Microsoft Jet 데이터베이스 엔진은 캐시 범위 내의 레코드를 캐시 범위 내에 요청하고 서버에서 캐시 범위를 벗어난 레코드를 요청합니다.

캐시에서 검색된 레코드는 다른 사용자가 원본 데이터에 동시에 변경한 내용을 반영하지 않습니다.

캐시된 모든 데이터의 업데이트를 강제로 수행하려면 *lSize* `SetCacheSize` 매개 변수를 `SetCacheSize` 0으로 전달하고 원래 요청한 캐시 크기로 `FillCache` 다시 호출한 다음 멤버 함수를 호출합니다.

UNICODE 레코드 집합을 만들지 않는 경우 `COleVariant` 개체를 ANSI로 명시적으로 선언해야 합니다. 이 작업은 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant) `VT_BSTRT` `COleVariant` *(lpszSrc,* **,** *vtSrc)* **)** vtSrc가 `VT_BSTRT` 설정된 생성자 형식(ANSI)을 **(** 사용하거나 *vtSrc가* 설정된 [SetString(lpszSrc,](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc)을* **)** 사용하여 수행할 수 있습니다. *vtSrc*

관련 정보는 DAO 도움말에서 CacheSize, CacheStart 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetsetcurrentindex"></a><a name="setcurrentindex"></a>CDao레코드 집합::세트전류 인덱스

테이블 형식 레코드 집합에 인덱스를 설정 하려면이 멤버 함수를 호출 합니다.

```cpp
void SetCurrentIndex(LPCTSTR lpszIndex);
```

### <a name="parameters"></a>매개 변수

*lpszIndex*<br/>
설정할 인덱스 의 이름을 포함하는 포인터입니다.

### <a name="remarks"></a>설명

기본 테이블의 레코드는 특정 순서로 저장되지 않습니다. 인덱스를 설정하면 데이터베이스에서 반환되는 레코드 순서가 변경되지만 레코드가 저장되는 순서에는 영향을 주지 않습니다. 지정된 인덱스가 이미 정의되어 있어야 합니다. 존재하지 않는 인덱스 개체를 사용하려고 하거나 [Seek를](#seek)호출할 때 인덱스가 설정되지 않은 경우 MFC는 예외를 throw합니다.

[CDaoTableDef::CreateIndex를](../../mfc/reference/cdaotabledef-class.md#createindex) 호출하고 [CDaoTableDef::Append를](../../mfc/reference/cdaotabledef-class.md#append)호출한 다음 레코드 집합을 다시 열어 기본 테이블 def의 인덱스 컬렉션에 새 인덱스를 적용하여 테이블에 대한 새 인덱스를 만들 수 있습니다.

테이블 형식 레코드 집합에서 반환된 레코드는 기본 tabledef에 대해 정의된 인덱스에서만 정렬할 수 있습니다. 레코드를 다른 순서로 정렬하려면 [CDaoRecordset:m_strSort에](#m_strsort)저장된 SQL **ORDERBY** 절을 사용하여 다이너셋 유형 또는 스냅숏 형식 레코드 집합을 열 수 있습니다.

관련 정보는 DAO 도움말의 "색인 개체" 항목 및 정의 "현재 인덱스"를 참조하십시오.

## <a name="cdaorecordsetsetfielddirty"></a><a name="setfielddirty"></a>CDao레코드 집합::세트필드더티

이 멤버 함수를 호출하여 레코드 집합의 필드 데이터 멤버를 변경된 것으로 또는 변경되지 않은 상태로 플래그를 표시합니다.

```cpp
void SetFieldDirty(
    void* pv,
    BOOL bDirty = TRUE);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
레코드 집합 또는 NULL에 필드 데이터 멤버의 주소를 포함합니다. NULL이면 레코드 집합의 모든 필드 데이터 멤버에 플래그가 지정됩니다. (C++ NULL은 데이터베이스 용어에서 Null과 같지 않습니다. 즉 "값이 없음")

*bDirty*<br/>
TRUE 필드 데이터 멤버를 "더티"(변경됨)로 플래그를 지정하는 경우 그렇지 않으면 필드 데이터 멤버를 "정리"(변경되지 않음)로 플래그를 지정하는 경우 FALSE입니다.

### <a name="remarks"></a>설명

필드를 변경되지 않은 것으로 표시하면 필드가 업데이트되지 않습니다.

프레임워크는 변경된 필드 데이터 멤버를 표시하여 DAO 레코드 필드 교환(DFX) 메커니즘에 의해 데이터 원본의 레코드에 기록되도록 합니다. 필드 값을 변경하면 일반적으로 필드가 자동으로 더러워지므로 직접 `SetFieldDirty` 호출할 필요가 거의 없지만 필드 데이터 멤버에 있는 값에 관계없이 열이 명시적으로 업데이트되거나 삽입되도록 할 수도 있습니다. DFX 메커니즘은 또한 PSEUDONULL의 사용을 사용합니다. 자세한 내용은 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)를 참조하십시오.

이중 버퍼링 메커니즘이 사용되지 않는 경우 필드 값을 변경해도 필드가 자동으로 더티로 설정되지 않습니다. 이 경우 필드를 더티로 명시적으로 설정해야 합니다. [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 포함된 플래그는 이 자동 필드 검사를 제어합니다.

> [!NOTE]
> [편집](#edit) 또는 AddNew 를 호출한 후에만 이 멤버 [함수를](#addnew)호출합니다.

함수의 첫 번째 인수에 NULL을 사용하면 `outputColumn` 에서 **매개 변수** 필드가 아닌 모든 필드에 함수가 `CDaoFieldExchange`적용됩니다. 예를 들어,

[!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]

필드만 `outputColumn` NULL로 설정합니다. **매개 변수** 필드는 영향을 받지 않습니다.

**매개 변수에서**작업하려면 다음과 같이 작업하려는 개별 **매개 람의** 실제 주소를 제공해야 합니다.

[!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]

즉, 모든 **매개 변수** 필드를 NULL로 `outputColumn` 설정할 수 없습니다.

`SetFieldDirty`을 통해 `DoFieldExchange`구현됩니다.

## <a name="cdaorecordsetsetfieldnull"></a><a name="setfieldnull"></a>CDao레코드 집합::세트필드널

이 멤버 함수를 호출하여 레코드 집합의 필드 데이터 멤버를 Null(특히 값이 없음)으로 플래그를 정하거나 Null이 아닌 것으로 플래그를 표시합니다.

```cpp
void SetFieldNull(
    void* pv,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
레코드 집합 또는 NULL에 필드 데이터 멤버의 주소를 포함합니다. NULL이면 레코드 집합의 모든 필드 데이터 멤버에 플래그가 지정됩니다. (C++ NULL은 데이터베이스 용어에서 Null과 같지 않습니다. 즉 "값이 없음")

*bNull*<br/>
필드 데이터 멤버가 값(Null)이 없는 것으로 플래그가 지정되는 경우 Nonzero입니다. 그렇지 않으면 필드 데이터 멤버가 Null이 아닌 것으로 플래그가 지정되는 경우 0입니다.

### <a name="remarks"></a>설명

`SetFieldNull``DoFieldExchange` 는 메커니즘에 바인딩된 필드에 사용됩니다.

레코드 집합에 새 레코드를 추가하면 모든 필드 데이터 멤버가 처음에 Null 값으로 설정되고 "더티"(변경됨)로 플래그가 지정됩니다. 데이터 원본에서 레코드를 검색하면 해당 열에 이미 값이 있거나 Null입니다. 필드 Null을 만드는 것이 적절하지 않으면 [CDaoException이](../../mfc/reference/cdaoexception-class.md) throw됩니다.

이중 버퍼링 메커니즘을 사용하는 경우(예: 현재 레코드의 필드를 값을 갖지 않는 것으로 지정하려는 `SetFieldNull` *경우) bNull을* 사용하여 TRUE로 설정하여 Null로 플래그를 지정합니다. 필드가 이전에 Null로 표시되어 있고 이제 값을 지정하려는 경우 새 값을 설정하기만 하면 됩니다. `SetFieldNull`을 사용하여 Null 플래그를 제거할 필요가 없습니다. 필드가 Null이 될 수 있는지 여부를 확인하려면 [IsFieldNullable을](#isfieldnullable)호출합니다.

이중 버퍼링 메커니즘을 사용하지 않는 경우 필드 값을 변경해도 필드가 자동으로 더럽고 Null이 아닌 것으로 설정되지 않습니다. 필드를 더럽고 Null이 아닌 필드를 구체적으로 설정해야 합니다. [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 포함된 플래그는 이 자동 필드 검사를 제어합니다.

DFX 메커니즘은 PSEUDONULL의 사용을 사용합니다. 자세한 내용은 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)를 참조하십시오.

> [!NOTE]
> [편집](#edit) 또는 AddNew 를 호출한 후에만 이 멤버 [함수를](#addnew)호출합니다.

함수의 첫 번째 인수에 NULL을 사용하면 `outputColumn` `CDaoFieldExchange`에서 **매개 변수** 필드가 아닌 필드에만 함수가 적용됩니다. 예를 들어,

[!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]

필드만 `outputColumn` NULL로 설정합니다. **매개 변수** 필드는 영향을 받지 않습니다.

## <a name="cdaorecordsetsetfieldvalue"></a><a name="setfieldvalue"></a>CDao레코드 집합::세트필드밸류

이 멤버 함수를 호출하여 서수 위치 또는 문자열 값을 변경하여 필드 값을 설정합니다.

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
필드 이름을 포함하는 문자열에 대한 포인터입니다.

*varValue*<br/>
필드 내용의 값을 포함하는 [COleVariant](../../mfc/reference/colevariant-class.md) 개체에 대한 참조입니다.

*nIndex*<br/>
레코드 집합의 필드 컬렉션(0 기반)에서 필드의 서수 위치를 나타내는 정수입니다.

*lpsz값*<br/>
필드 내용의 값을 포함하는 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

DoFieldExchange 메커니즘을 사용하여 정적 바인딩 열이 아닌 런타임에 필드를 동적으로 바인딩하려면 및 `SetFieldValue` [GetFieldValue를](#getfieldvalue) 사용합니다. [DoFieldExchange](#dofieldexchange)

UNICODE 레코드 집합을 만들지 않는 경우 `SetFieldValue` `COleVariant` 매개 변수를 포함하지 않는 형식을 사용하거나 개체를 `COleVariant` ANSI로 명시적으로 선언해야 합니다. 이 작업은 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant) `VT_BSTRT` `COleVariant` *(lpszSrc,* **,** *vtSrc)* **)** vtSrc가 `VT_BSTRT` 설정된 생성자 형식(ANSI)을 **(** 사용하거나 *vtSrc가* 설정된 [SetString(lpszSrc,](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc)을* **)** 사용하여 수행할 수 있습니다. *vtSrc*

관련 정보는 DAO 도움말의 "필드 개체" 및 "값 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetsetfieldvaluenull"></a><a name="setfieldvaluenull"></a>CDao레코드 집합::세트필드밸류널

이 멤버 함수를 호출하여 필드를 Null 값으로 설정합니다.

```cpp
void SetFieldValueNull(int nIndex);
void SetFieldValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0기반 인덱스로 조회하기 위한 레코드 집합의 필드 인덱스입니다.

*lpszName*<br/>
이름으로 조회할 레코드 집합의 필드 이름입니다.

### <a name="remarks"></a>설명

C++ NULL은 Null과 같지 않으며 데이터베이스 용어에서 "값이 없음"을 의미합니다.

관련 정보는 DAO 도움말의 "필드 개체" 및 "값 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetsetlockingmode"></a><a name="setlockingmode"></a>CDao레코드 집합::세트 잠금 모드

이 멤버 함수를 호출하여 레코드 집합에 대한 잠금 유형을 설정합니다.

```cpp
void SetLockingMode(BOOL bPessimistic);
```

### <a name="parameters"></a>매개 변수

*bPessimistic*<br/>
잠금 유형을 나타내는 플래그입니다.

### <a name="remarks"></a>설명

비관적 잠금이 적용되면 편집중인 레코드가 포함된 2K 페이지가 멤버 함수를 `Edit` 호출하는 즉시 잠깁니다. `Update` 또는 `Close` 멤버 함수 또는 이동 또는 찾기 작업을 호출할 때 페이지의 잠금이 해제됩니다.

낙관적 잠금이 적용되면 레코드가 포함된 2K 페이지는 레코드가 멤버 함수로 업데이트되는 동안에만 잠깁니다. `Update`

페이지가 잠긴 경우 다른 사용자는 동일한 페이지에서 레코드를 편집할 수 없습니다. 영하지 `SetLockingMode` 않은 값을 호출하고 전달하는 다른 사용자가 이미 페이지가 잠겨 있는 경우 `Edit`을 호출할 때 예외가 throw됩니다. 다른 사용자는 잠긴 페이지에서 데이터를 읽을 수 있습니다.

다른 사용자가 `SetLockingMode` 페이지를 잠그는 동안 `Update` 0값으로 호출하고 나중에 호출하는 경우 예외가 발생합니다. 다른 사용자가 레코드에 변경한 내용을 확인하고 변경 내용을 손실하려면 현재 레코드의 `SetBookmark` 책갈피 값을 사용하여 멤버 함수를 호출합니다.

ODBC 데이터 원본으로 작업할 때 잠금 모드는 항상 낙관적입니다.

## <a name="cdaorecordsetsetparamvalue"></a><a name="setparamvalue"></a>CDao레코드 집합::SetParam값

런타임에 레코드 집합에서 매개 변수값을 설정하려면 이 멤버 함수를 호출합니다.

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
querydef의 매개 변수 컬렉션에서 매개 변수의 숫자 위치입니다.

*var*<br/>
설정할 값; 비고를 참조하십시오.

*lpszName*<br/>
설정할 값을 지정하려는 매개 변수의 이름입니다.

### <a name="remarks"></a>설명

매개 변수는 레코드 집합의 SQL 문자열의 일부로 이미 설정되어 있어야 합니다. 이름 또는 컬렉션의 인덱스 위치로 매개 변수에 액세스할 수 있습니다.

개체로 설정할 값을 `COleVariant` 지정합니다. 개체에서 원하는 값 및 형식을 설정하는 자세한 내용은 [클래스 COleVariant](../../mfc/reference/colevariant-class.md)을 참조하십시오. `COleVariant` UNICODE 레코드 집합을 만들지 않는 경우 `COleVariant` 개체를 ANSI로 명시적으로 선언해야 합니다. 이 작업은 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant) `VT_BSTRT` `COleVariant` *(lpszSrc,* **,** *vtSrc)* **)** vtSrc가 `VT_BSTRT` 설정된 생성자 형식(ANSI)을 **(** 사용하거나 *vtSrc가* 설정된 [SetString(lpszSrc,](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc)을* **)** 사용하여 수행할 수 있습니다. *vtSrc*

## <a name="cdaorecordsetsetparamvaluenull"></a><a name="setparamvaluenull"></a>CDao레코드 집합::SetParamValueNull

이 멤버 함수를 호출하여 매개 변수를 Null 값으로 설정합니다.

```cpp
void SetParamValueNull(int nIndex);
void SetParamValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0기반 인덱스로 조회하기 위한 레코드 집합의 필드 인덱스입니다.

*lpszName*<br/>
이름으로 조회할 레코드 집합의 필드 이름입니다.

### <a name="remarks"></a>설명

C++ NULL은 Null과 같지 않으며 데이터베이스 용어에서 "값이 없음"을 의미합니다.

## <a name="cdaorecordsetsetpercentposition"></a><a name="setpercentposition"></a>CDao레코드 집합::설정백분율 위치

이 멤버 함수를 호출하여 레코드 집합의 레코드 백분율을 기준으로 레코드 집합 개체에서 현재 레코드의 대략적인 위치를 변경하는 값을 설정합니다.

```cpp
void SetPercentPosition(float fPosition);
```

### <a name="parameters"></a>매개 변수

*fPosition*<br/>
0부터 100까지의 숫자입니다.

### <a name="remarks"></a>설명

다이나셋 형식 또는 스냅숏 형식 레코드 집합으로 작업할 때 먼저 호출하기 `SetPercentPosition`전에 마지막 레코드로 이동하여 레코드 집합을 채웁니다. 레코드 집합을 완전히 채우기 전에 호출하는 `SetPercentPosition` 경우 이동 량은 [GetRecordCount](#getrecordcount)값으로 표시된 대로 액세스한 레코드 수를 기준으로 합니다. 을 호출하여 `MoveLast`마지막 레코드로 이동할 수 있습니다.

호출하면 `SetPercentPosition`해당 값에 해당하는 대략적인 위치의 레코드가 최신 상태가 됩니다.

> [!NOTE]
> 현재 `SetPercentPosition` 레코드를 레코드 집합의 특정 레코드로 이동하도록 호출하는 것은 권장되지 않습니다. 대신 [SetBookmark](#setbookmark) 멤버 함수를 호출합니다.

관련 정보는 DAO 도움말의 "백분율 위치 속성" 항목을 참조하십시오.

## <a name="cdaorecordsetupdate"></a><a name="update"></a>CDao레코드 집합::업데이트

`AddNew` 또는 `Edit` 멤버 함수를 호출한 후 이 멤버 함수를 호출합니다.

```
virtual void Update();
```

### <a name="remarks"></a>설명

또는 `Edit` 작업을 완료하려면 `AddNew` 이 호출이 필요합니다.

둘 `AddNew` `Edit` 다 데이터 원본에 저장하기 위해 추가되거나 편집된 데이터가 배치되는 편집 버퍼를 준비합니다. `Update`데이터를 저장합니다. 변경된 것으로 표시되거나 검색된 필드만 업데이트됩니다.

데이터 원본이 트랜잭션을 지원하는 경우 `Update` 트랜잭션의 호출(및 해당 `AddNew` 또는 `Edit` 통화) 부분을 만들 수 있습니다.

> [!CAUTION]
> 먼저 호출하지 `Update` 않고 `AddNew` 호출하거나 `Edit` `Update` `CDaoException`을 throw합니다. 호출하거나 `AddNew` `Edit`을 호출하는 `Update` 경우 [MoveNext를](#movenext) 호출하거나 레코드 집합 또는 데이터 원본 연결을 닫기 전에 호출해야 합니다. 그렇지 않으면 변경 내용이 알림 없이 손실됩니다.

레코드 집합 개체가 다중 사용자 환경에서 비관적으로 잠겨 있으면 업데이트가 `Edit` 완료될 때까지 레코드가 잠긴 상태로 유지됩니다. 레코드 집합이 낙관적으로 잠긴 경우 레코드가 잠겨 있고 데이터베이스에서 업데이트되기 직전에 미리 편집된 레코드와 비교됩니다. 호출한 `Edit`후 레코드가 변경된 `Update` 경우 작업이 실패하고 MFC가 예외를 throw합니다. `SetLockingMode`을 통해 잠금 모드를 변경할 수 있습니다.

> [!NOTE]
> 낙관적 잠금은 항상 ODBC 및 설치 가능한 ISAM과 같은 외부 데이터베이스 형식에 사용됩니다.

관련 정보는 DAO 도움말의 "새 새 메서드 추가", "취소 업데이트 메서드", "메서드 삭제", "마지막으로 수정된 속성", "업데이트 방법" 및 "편집 모드 속성"을 참조하십시오.

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDao워크스페이스 클래스](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDao데이터베이스 클래스](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)<br/>
