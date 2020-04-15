---
title: CAtlTransactionManager 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::Close
- ATLTRANSACTIONMANAGER/ATL::Commit
- ATLTRANSACTIONMANAGER/ATL::Create
- ATLTRANSACTIONMANAGER/ATL::CreateFile
- ATLTRANSACTIONMANAGER/ATL::DeleteFile
- ATLTRANSACTIONMANAGER/ATL::FindFirstFile
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributesEx
- ATLTRANSACTIONMANAGER/ATL::GetHandle
- ATLTRANSACTIONMANAGER/ATL::IsFallback
- ATLTRANSACTIONMANAGER/ATL::MoveFile
- ATLTRANSACTIONMANAGER/ATL::RegCreateKeyEx
- ATLTRANSACTIONMANAGER/ATL::RegDeleteKey
- ATLTRANSACTIONMANAGER/ATL::RegOpenKeyEx
- ATLTRANSACTIONMANAGER/ATL::Rollback
- ATLTRANSACTIONMANAGER/ATL::SetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::m_bFallback
- ATLTRANSACTIONMANAGER/ATL::m_hTransaction
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
ms.openlocfilehash: 5c2814f963ea4814e0d7585e0e4d6dda26c1f04d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321320"
---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager 클래스

CAtlTransactionManager 클래스는 커널 트랜잭션 관리자(KTM) 함수에 래퍼를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAtlTransactionManager;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[~ 카틀트랜잭션매니저](#dtor)|CAtl트랜잭션관리자 소멸자.|
|[CAtlTransactionManager](#catltransactionmanager)|CAtlTransactionManager 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[닫기](#close)|트랜잭션 핸들 하나를 닫습니다.|
|[커밋](#commit)|트랜잭션을 커밋할 것을 요청합니다.|
|[만들기](#create)|트랜잭션 핸들을 만듭니다.|
|[CreateFile](#createfile)|파일, 파일 스트림 또는 디렉터리를 트랜잭션 작업으로 만들거나 엽니다.|
|[DeleteFile](#deletefile)|기존 파일을 트랜잭션 작업으로 삭제합니다.|
|[찾기퍼스트파일](#findfirstfile)|디렉터리에서 파일 또는 하위 디렉터리를 트랜잭션 작업으로 검색합니다.|
|[GetFile 속성](#getfileattributes)|지정된 파일 또는 디렉터리에 대한 파일 시스템 특성을 트랜잭션 작업으로 검색합니다.|
|[GetFile특성Ex](#getfileattributesex)|지정된 파일 또는 디렉터리에 대한 파일 시스템 특성을 트랜잭션 작업으로 검색합니다.|
|[GetHandle](#gethandle)|트랜잭션 핸들을 반환합니다.|
|[이스폴백](#isfallback)|대체 호출이 활성화되어 있는지 여부를 결정합니다.|
|[MoveFile](#movefile)|기존 파일또는 자식을 포함한 디렉터리를 트랜잭션 작업으로 이동합니다.|
|[레지만들키엑스](#regcreatekeyex)|지정된 레지스트리 키를 만들고 트랜잭션과 연결합니다. 키가 이미 있으면 함수가 열립니다.|
|[레지삭제키](#regdeletekey)|레지스트리의 지정된 플랫폼별 보기에서 하위 키와 해당 값을 트랜잭션 작업으로 삭제합니다.|
|[레지오픈키엑스](#regopenkeyex)|지정된 레지스트리 키를 열고 트랜잭션과 연결합니다.|
|[롤백](#rollback)|트랜잭션을 롤백할 것을 요청합니다.|
|[세트파일속성](#setfileattributes)|파일 또는 디렉터리에 대한 특성을 트랜잭션 작업으로 설정합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[m_bFallback](#m_bfallback)|대체가 지원되는 경우 TRUE입니다. 그렇지 않으면 거짓.|
|[m_hTransaction](#m_htransaction)|트랜잭션 핸들입니다.|

## <a name="remarks"></a>설명

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[ATL:::CAtl트랜잭션매니저](../../atl/reference/catltransactionmanager-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** atltransactionmanager.h

## <a name="catltransactionmanager"></a><a name="dtor"></a>~ 카틀트랜잭션매니저

CAtl트랜잭션관리자 소멸자.

```
virtual ~CAtlTransactionManager();
```

### <a name="remarks"></a>설명

정상적인 처리에서는 트랜잭션이 자동으로 커밋되고 닫힙됩니다. 예외 해제 중에 소멸자가 호출되면 트랜잭션이 롤백되고 닫힙됩니다.

## <a name="catltransactionmanager"></a><a name="catltransactionmanager"></a>카틀트랜잭션매니저

CAtlTransactionManager 생성자입니다.

```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```

### <a name="parameters"></a>매개 변수

*b폴백*<br/>
TRUE는 지원 대체를 나타냅니다. 트랜잭션 함수가 실패하면 클래스는 자동으로 "비트랜잭션" 함수를 호출합니다. FALSE는 "대체" 호출이 없음을 나타냅니다.

*b 자동 만들기 트랜잭션*<br/>
TRUE는 트랜잭션 처리기가 생성자에서 자동으로 생성됨을 나타냅니다. FALSE는 그렇지 않음을 나타냅니다.

### <a name="remarks"></a>설명

## <a name="close"></a><a name="close"></a>가까이

트랜잭션 핸들을 닫습니다.

```
inline BOOL Close();
```

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

이 래퍼는 `CloseHandle` 함수를 호출합니다. 메서드는 소멸자에서 자동으로 호출됩니다.

## <a name="commit"></a><a name="commit"></a>커밋

트랜잭션을 커밋할 것을 요청합니다.

```
inline BOOL Commit();
```

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

이 래퍼는 `CommitTransaction` 함수를 호출합니다. 메서드는 소멸자에서 자동으로 호출됩니다.

## <a name="create"></a><a name="create"></a>만들

트랜잭션 핸들을 만듭니다.

```
inline BOOL Create();
```

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

이 래퍼는 `CreateTransaction` 함수를 호출합니다. 확인

## <a name="createfile"></a><a name="createfile"></a>Createfile

파일, 파일 스트림 또는 디렉터리를 트랜잭션 작업으로 만들거나 엽니다.

```
inline HANDLE CreateFile(
    LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```

### <a name="parameters"></a>매개 변수

*lpFileName*<br/>
만들거나 열 개체의 이름입니다.

*dwDesiredAccess*<br/>
읽기, 쓰기, 둘 다 또는 둘 다(0)로 요약할 수 있는 개체에 대한 액세스입니다. 가장 일반적으로 사용되는 값은 GENERIC_READ, GENERIC_WRITE 또는 둘 다인 GENERIC_READ &#124; GENERIC_WRITE.

*dwShare모드*<br/>
0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE 읽기, 쓰기, 삭제, 모두 삭제 또는 없음을 읽을 수 있는 개체의 공유 모드입니다.

*lp보안속성*<br/>
선택적 보안 설명자가 포함된 SECURITY_ATTRIBUTES 구조에 대한 포인터이며 반환된 핸들을 자식 프로세스에 의해 상속할 수 있는지 여부도 결정합니다. 매개 변수는 NULL일 수 있습니다.

*dw크리에이션 디포지션*<br/>
존재하고 존재하지 않는 파일에 대해 수행할 작업입니다. 이 매개 변수는 CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING 또는 TRUNCATE_EXISTING 결합할 수 없는 다음 값 중 하나여야 합니다.

*dwFlagsand속성*<br/>
파일 특성 및 플래그입니다. 이 매개 변수에는 사용 가능한 파일 특성(FILE_ATTRIBUTE_*)의 조합이 포함될 수 있습니다. 다른 모든 파일 특성은 FILE_ATTRIBUTE_NORMAL 재정의합니다. 이 매개 변수에는 버퍼링 동작, 액세스 모드 및 기타 특수 목적 플래그를 제어하기 위한 플래그(FILE_FLAG_)\*조합도 포함될 수 있습니다. 이러한 값은\* 모든 FILE_ATTRIBUTE_ 값과 결합됩니다.

*h템플릿파일*<br/>
액세스 권한이 GENERIC_READ 있는 템플릿 파일에 대한 유효한 핸들입니다. 템플릿 파일은 생성되는 파일에 대한 파일 특성 및 확장 특성을 제공합니다. 이 매개 변수는 NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

개체에 액세스하는 데 사용할 수 있는 핸들을 반환합니다.

### <a name="remarks"></a>설명

이 래퍼는 `CreateFileTransacted` 함수를 호출합니다.

## <a name="deletefile"></a><a name="deletefile"></a>파일 삭제

기존 파일을 트랜잭션 작업으로 삭제합니다.

```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```

### <a name="parameters"></a>매개 변수

*lpFileName*<br/>
삭제할 파일의 이름입니다.

### <a name="remarks"></a>설명

이 래퍼는 `DeleteFileTransacted` 함수를 호출합니다.

## <a name="findfirstfile"></a><a name="findfirstfile"></a>찾기퍼스트파일

디렉터리에서 파일 또는 하위 디렉터리를 트랜잭션 작업으로 검색합니다.

```
inline HANDLE FindFirstFile(
    LPCTSTR lpFileName,
    WIN32_FIND_DATA* pNextInfo);
```

### <a name="parameters"></a>매개 변수

*lpFileName*<br/>
검색할 디렉터리 또는 경로 및 파일 이름입니다. 이 매개 변수에는 별표(*) 또는 물음표()와 같은 와일드카드 문자가 포함될 수 있습니다.

*pNext정보*<br/>
찾은 파일 또는 하위 디렉터리에 대한 정보를 수신하는 WIN32_FIND_DATA 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값은 후속 `FindNextFile` `FindClose`호출 또는 에 대한 호출에 사용되는 검색 핸들입니다. 함수가 실패하거나 *lpFileName* 매개 변수의 검색 문자열에서 파일을 찾지 못하면 반환 값이 INVALID_HANDLE_VALUE.

### <a name="remarks"></a>설명

이 래퍼는 `FindFirstFileTransacted` 함수를 호출합니다.

## <a name="getfileattributes"></a><a name="getfileattributes"></a>GetFile 속성

지정된 파일 또는 디렉터리에 대한 파일 시스템 특성을 트랜잭션 작업으로 검색합니다.

```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```

### <a name="parameters"></a>매개 변수

*lpFileName*<br/>
파일 또는 디렉터리 이름입니다.

### <a name="remarks"></a>설명

이 래퍼는 `GetFileAttributesTransacted` 함수를 호출합니다.

## <a name="getfileattributesex"></a><a name="getfileattributesex"></a>GetFile특성Ex

지정된 파일 또는 디렉터리에 대한 파일 시스템 특성을 트랜잭션 작업으로 검색합니다.

```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```

### <a name="parameters"></a>매개 변수

*lpFileName*<br/>
파일 또는 디렉터리 이름입니다.

*fInfoLevelId*<br/>
검색할 특성 정보의 수준입니다.

*lpFile정보*<br/>
특성 정보를 받는 버퍼에 대한 포인터입니다. 이 버퍼에 저장되는 특성 정보의 유형은 *fInfoLevelId*의 값에 의해 결정됩니다. *fInfoLevelId* 매개 변수가 GetFileExInfoStandard인 경우 이 매개 변수는 WIN32_FILE_ATTRIBUTE_DATA 구조를 가리킵니다.

### <a name="remarks"></a>설명

이 래퍼는 `GetFileAttributesTransacted` 함수를 호출합니다.

## <a name="gethandle"></a><a name="gethandle"></a>GetHandle

트랜잭션 핸들을 반환합니다.

```
HANDLE GetHandle() const;
```

### <a name="return-value"></a>Return Value

클래스에 대한 트랜잭션 핸들을 반환합니다. 핸들에 `CAtlTransactionManager` 연결되지 않은 경우 NULL을 반환합니다.

### <a name="remarks"></a>설명

## <a name="isfallback"></a><a name="isfallback"></a>이스폴백

대체 호출이 활성화되어 있는지 여부를 결정합니다.

```
BOOL IsFallback() const;
```

### <a name="return-value"></a>Return Value

반환 TRUE는 클래스가 대체 호출을 지원합니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="m_bfallback"></a><a name="m_bfallback"></a>m_bFallback

대체가 지원되는 경우 TRUE입니다. 그렇지 않으면 거짓.

```
BOOL m_bFallback;
```

### <a name="remarks"></a>설명

## <a name="m_htransaction"></a><a name="m_htransaction"></a>m_hTransaction

트랜잭션 핸들입니다.

```
HANDLE m_hTransaction;
```

### <a name="remarks"></a>설명

## <a name="movefile"></a><a name="movefile"></a>이동 파일

기존 파일또는 자식을 포함한 디렉터리를 트랜잭션 작업으로 이동합니다.

```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```

### <a name="parameters"></a>매개 변수

*lpOldFileName*<br/>
로컬 컴퓨터에서 기존 파일 또는 디렉터리의 현재 이름입니다.

*lpNewFile네임*<br/>
파일 또는 디렉터리이름의 새 이름입니다. 이 이름은 아직 존재하지 않아야 합니다. 새 파일이 다른 파일 시스템 이나 드라이브에 있을 수 있습니다. 새 디렉터리가 동일한 드라이브에 있어야 합니다.

### <a name="remarks"></a>설명

이 래퍼는 `MoveFileTransacted` 함수를 호출합니다.

## <a name="regcreatekeyex"></a><a name="regcreatekeyex"></a>레지만들키엑스

지정된 레지스트리 키를 만들고 트랜잭션과 연결합니다. 키가 이미 있으면 함수가 열립니다.

```
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
열린 레지스트리 키에 대한 핸들입니다.

*lpSubKey*<br/>
이 함수가 열리거나 만드는 하위 키의 이름입니다.

*dwReserved*<br/>
이 매개 변수는 예약되어 있으며 0이어야 합니다.

*lpClass*<br/>
이 키의 사용자 정의 클래스입니다. 이 매개 변수는 무시될 수 있습니다. 이 매개 변수는 NULL일 수 있습니다.

*dwOptions*<br/>
이 매개 변수는 REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE 또는 REG_OPTION_VOLATILE 값 중 하나일 수 있습니다.

*삼원하는*<br/>
키에 대한 액세스 권한을 지정하는 마스크입니다.

*lp보안속성*<br/>
반환된 핸들이 자식 프로세스에 의해 상속되는지 여부를 결정하는 SECURITY_ATTRIBUTES 구조에 대한 포인터입니다. *lpSecurityAttributes가* NULL이면 핸들을 상속할 수 없습니다.

*phk결과*<br/>
열린 키또는 생성된 키에 대한 핸들을 받는 변수에 대한 포인터입니다. 키가 미리 정의된 레지스트리 키 중 하나가 아닌 `RegCloseKey` 경우 핸들 사용을 완료한 후 함수를 호출합니다.

*lpdwDisposition*<br/>
REG_CREATED_NEW_KEY 또는 REG_OPENED_EXISTING_KEY 다음 처리 값 중 하나를 수신하는 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값이 ERROR_SUCCESS. 함수가 실패하면 반환 값은 Winerror.h에 정의된 제로가 아닌 오류 코드입니다.

### <a name="remarks"></a>설명

이 래퍼는 `RegCreateKeyTransacted` 함수를 호출합니다.

## <a name="regdeletekey"></a><a name="regdeletekey"></a>레지삭제키

레지스트리의 지정된 플랫폼별 보기에서 하위 키와 해당 값을 트랜잭션 작업으로 삭제합니다.

```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*hKey*|열린 레지스트리 키에 대한 핸들입니다.|
|*lpSubKey*|삭제할 키의 이름입니다.|

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값이 ERROR_SUCCESS. 함수가 실패하면 반환 값은 Winerror.h에 정의된 제로가 아닌 오류 코드입니다.

### <a name="remarks"></a>설명

이 래퍼는 `RegDeleteKeyTransacted` 함수를 호출합니다.

## <a name="regopenkeyex"></a><a name="regopenkeyex"></a>레지오픈키엑스

지정된 레지스트리 키를 열고 트랜잭션과 연결합니다.

```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
열린 레지스트리 키에 대한 핸들입니다.

*lpSubKey*<br/>
열 레지스트리 하위 키의 이름입니다.

*ul옵션*<br/>
이 매개 변수는 예약되어 있으며 0이어야 합니다.

*삼원하는*<br/>
키에 대한 액세스 권한을 지정하는 마스크입니다.

*phk결과*<br/>
열린 키또는 생성된 키에 대한 핸들을 받는 변수에 대한 포인터입니다. 키가 미리 정의된 레지스트리 키 중 하나가 아닌 `RegCloseKey` 경우 핸들 사용을 완료한 후 함수를 호출합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값이 ERROR_SUCCESS. 함수가 실패하면 반환 값은 Winerror.h에 정의된 제로가 아닌 오류 코드입니다.

### <a name="remarks"></a>설명

이 래퍼는 `RegOpenKeyTransacted` 함수를 호출합니다.

## <a name="rollback"></a><a name="rollback"></a>롤백

트랜잭션을 롤백할 것을 요청합니다.

```
inline BOOL Rollback();
```

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

이 래퍼는 `RollbackTransaction` 함수를 호출합니다.

## <a name="setfileattributes"></a><a name="setfileattributes"></a>세트파일속성

파일 또는 디렉터리에 대한 특성을 트랜잭션 작업으로 설정합니다.

```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```

### <a name="parameters"></a>매개 변수

*lpFileName*<br/>
파일 또는 디렉터리 이름입니다.

*dwAttributes*<br/>
파일에 대해 설정할 파일 특성입니다. 자세한 내용은 [SetFileAttributesTransacted](/windows/win32/api/winbase/nf-winbase-setfileattributestransactedw)를 참조하십시오.

### <a name="remarks"></a>설명

이 래퍼는 `SetFileAttributesTransacted` 함수를 호출합니다.

## <a name="see-also"></a>참고 항목

[ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)
