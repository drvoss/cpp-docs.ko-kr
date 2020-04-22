---
title: CAccessToken 클래스
ms.date: 07/02/2019
f1_keywords:
- CAccessToken
- ATLSECURITY/ATL::CAccessToken
- ATLSECURITY/ATL::CAccessToken::Attach
- ATLSECURITY/ATL::CAccessToken::CheckTokenMembership
- ATLSECURITY/ATL::CAccessToken::CreateImpersonationToken
- ATLSECURITY/ATL::CAccessToken::CreatePrimaryToken
- ATLSECURITY/ATL::CAccessToken::CreateProcessAsUser
- ATLSECURITY/ATL::CAccessToken::CreateRestrictedToken
- ATLSECURITY/ATL::CAccessToken::Detach
- ATLSECURITY/ATL::CAccessToken::DisablePrivilege
- ATLSECURITY/ATL::CAccessToken::DisablePrivileges
- ATLSECURITY/ATL::CAccessToken::EnablePrivilege
- ATLSECURITY/ATL::CAccessToken::EnablePrivileges
- ATLSECURITY/ATL::CAccessToken::GetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::GetEffectiveToken
- ATLSECURITY/ATL::CAccessToken::GetGroups
- ATLSECURITY/ATL::CAccessToken::GetHandle
- ATLSECURITY/ATL::CAccessToken::GetImpersonationLevel
- ATLSECURITY/ATL::CAccessToken::GetLogonSessionId
- ATLSECURITY/ATL::CAccessToken::GetLogonSid
- ATLSECURITY/ATL::CAccessToken::GetOwner
- ATLSECURITY/ATL::CAccessToken::GetPrimaryGroup
- ATLSECURITY/ATL::CAccessToken::GetPrivileges
- ATLSECURITY/ATL::CAccessToken::GetProcessToken
- ATLSECURITY/ATL::CAccessToken::GetProfile
- ATLSECURITY/ATL::CAccessToken::GetSource
- ATLSECURITY/ATL::CAccessToken::GetStatistics
- ATLSECURITY/ATL::CAccessToken::GetTerminalServicesSessionId
- ATLSECURITY/ATL::CAccessToken::GetThreadToken
- ATLSECURITY/ATL::CAccessToken::GetTokenId
- ATLSECURITY/ATL::CAccessToken::GetType
- ATLSECURITY/ATL::CAccessToken::GetUser
- ATLSECURITY/ATL::CAccessToken::HKeyCurrentUser
- ATLSECURITY/ATL::CAccessToken::Impersonate
- ATLSECURITY/ATL::CAccessToken::ImpersonateLoggedOnUser
- ATLSECURITY/ATL::CAccessToken::IsTokenRestricted
- ATLSECURITY/ATL::CAccessToken::LoadUserProfile
- ATLSECURITY/ATL::CAccessToken::LogonUser
- ATLSECURITY/ATL::CAccessToken::OpenCOMClientToken
- ATLSECURITY/ATL::CAccessToken::OpenNamedPipeClientToken
- ATLSECURITY/ATL::CAccessToken::OpenRPCClientToken
- ATLSECURITY/ATL::CAccessToken::OpenThreadToken
- ATLSECURITY/ATL::CAccessToken::PrivilegeCheck
- ATLSECURITY/ATL::CAccessToken::Revert
- ATLSECURITY/ATL::CAccessToken::SetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::SetOwner
- ATLSECURITY/ATL::CAccessToken::SetPrimaryGroup
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
ms.openlocfilehash: f7a2ee2f9d633c1ed743621eec5b2f7cc04c0e0b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748834"
---
# <a name="caccesstoken-class"></a>CAccessToken 클래스

이 클래스는 액세스 토큰의 래퍼입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAccessToken
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C액세스 토큰::~CAccessToken](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C액세스 토큰::첨부](#attach)|지정된 액세스 토큰 핸들의 소유권을 가져가려면 이 메서드를 호출합니다.|
|[C액세스 토큰::체크토큰 멤버 자격](#checktokenmembership)|이 메서드를 호출하여 개체에서 지정된 `CAccessToken` SID가 활성화되어 있는지 확인합니다.|
|[CAccessToken::만들기 사칭 토큰](#createimpersonationtoken)|새 가장 액세스 토큰을 만들려면 이 메서드를 호출합니다.|
|[CAccess토큰::기본 토큰 만들기](#createprimarytoken)|새 기본 토큰을 만들려면 이 메서드를 호출합니다.|
|[CAccessToken::만들기프로세스AsUser](#createprocessasuser)|이 메서드를 호출하여 개체로 표시되는 사용자의 보안 컨텍스트에서 `CAccessToken` 실행되는 새 프로세스를 만듭니다.|
|[CAccess토큰:만들기제한토큰](#createrestrictedtoken)|이 메서드를 호출하여 제한된 `CAccessToken` 새 개체를 만듭니다.|
|[C액세스 토큰::D에타치](#detach)|액세스 토큰의 소유권을 취소하려면 이 메서드를 호출합니다.|
|[C액세스토큰::D가능프리빌리지](#disableprivilege)|이 메서드를 호출하여 개체에서 권한을 비활성화합니다. `CAccessToken`|
|[CAccessToken::D사용 가능한 특권](#disableprivileges)|`CAccessToken` 이 메서드를 호출하여 개체에서 하나 이상의 권한을 비활성화합니다.|
|[CAccess토큰::인에이블프리빌리지](#enableprivilege)|이 메서드를 호출하여 개체에서 권한을 활성화합니다. `CAccessToken`|
|[CAccessToken::사용 권한 권한](#enableprivileges)|`CAccessToken` 이 메서드를 호출하여 개체에서 하나 이상의 권한을 사용하도록 설정합니다.|
|[C액세스 토큰::GetDefaultDacl](#getdefaultdacl)|이 메서드를 호출하여 개체의 기본 DACL을 `CAccessToken` 반환합니다.|
|[CAccessToken::GetEffective토큰](#geteffectivetoken)|이 메서드를 호출하여 현재 스레드에 `CAccessToken` 대해 유효한 액세스 토큰과 동일한 개체를 가져옵니다.|
|[C액세스 토큰::Getgroups](#getgroups)|`CAccessToken` 이 메서드를 호출하여 개체의 토큰 그룹을 반환합니다.|
|[C액세스 토큰::GetHandle](#gethandle)|액세스 토큰에 대한 핸들을 검색하려면 이 메서드를 호출합니다.|
|[C액세스 토큰::Get사칭 레벨](#getimpersonationlevel)|액세스 토큰에서 가장 수준을 얻으려면 이 메서드를 호출합니다.|
|[C액세스 토큰::겟로그온세션ID](#getlogonsessionid)|이 메서드를 호출하여 개체와 연결된 `CAccessToken` 로그온 세션 ID를 가져옵니다.|
|[C액세스 토큰::겟로그온 시드](#getlogonsid)|이 메서드를 호출하여 개체와 연결된 `CAccessToken` Logon SID를 가져옵니다.|
|[C액세스 토큰::GetOwner](#getowner)|이 메서드를 호출하여 소유자가 `CAccessToken` 개체와 연결하도록 합니다.|
|[C액세스 토큰::겟프라이티 그룹](#getprimarygroup)|`CAccessToken` 이 메서드를 호출하여 개체와 연결된 기본 그룹을 가져옵니다.|
|[C액세스 토큰::Get권한](#getprivileges)|`CAccessToken` 이 메서드를 호출하여 개체와 연결된 권한을 가져옵니다.|
|[CAccessToken::GetProcess토큰](#getprocesstoken)|지정된 프로세스의 액세스 토큰을 사용해서 `CAccessToken`을 초기화하려면 이 메서드를 호출합니다.|
|[C액세스 토큰::GetProfile](#getprofile)|이 메서드를 호출하여 개체와 연결된 사용자 `CAccessToken` 프로필을 가리키는 핸들을 가져옵니다.|
|[C액세스 토큰::GetSource](#getsource)|`CAccessToken` 이 메서드를 호출하여 개체의 소스를 가져옵니다.|
|[C액세스 토큰::통계학](#getstatistics)|개체와 연결된 정보를 얻으려면 `CAccessToken` 이 메서드를 호출합니다.|
|[CAccessToken::GetTerminal서비스세션ID](#getterminalservicessessionid)|이 메서드를 호출하여 개체와 연결된 `CAccessToken` 터미널 서비스 세션 세션 ID를 가져옵니다.|
|[CAccessToken::GetThread토큰](#getthreadtoken)|지정된 스레드에서 `CAccessToken` 토큰을 초기화하려면 이 메서드를 호출합니다.|
|[C액세스 토큰::GetTokenId](#gettokenid)|이 메서드를 호출하여 개체와 `CAccessToken` 연결된 토큰 ID를 가져옵니다.|
|[C액세스 토큰::GetType](#gettype)|`CAccessToken` 이 메서드를 호출하여 개체의 토큰 형식을 가져옵니다.|
|[C액세스 토큰::Getuser](#getuser)|이 메서드를 호출하여 개체와 `CAccessToken` 연결된 사용자를 식별합니다.|
|[C액세스 토큰::HKeyCurrentUser](#hkeycurrentuser)|이 메서드를 호출하여 개체와 연결된 사용자 `CAccessToken` 프로필을 가리키는 핸들을 가져옵니다.|
|[CAccessToken::가장](#impersonate)|이 메서드를 호출하여 스레드에 `CAccessToken` 가장을 할당합니다.|
|[CAccessToken::가장로그온유저](#impersonateloggedonuser)|호출 스레드가 로그온한 사용자의 보안 컨텍스트를 가장할 수 있도록 이 메서드를 호출합니다.|
|[C액세스 토큰::Is토큰제한](#istokenrestricted)|이 메서드를 호출하여 `CAccessToken` 개체에 제한된 SID 목록이 포함되어 있는지 테스트합니다.|
|[C액세스 토큰::로드유저 프로필](#loaduserprofile)|이 메서드를 호출하여 개체와 `CAccessToken` 연결된 사용자 프로필을 로드합니다.|
|[C액세스 토큰::로그온유저](#logonuser)|지정된 자격 증명과 연결된 사용자에 대한 로그온 세션을 만들려면 이 메서드를 호출합니다.|
|[C액세스 토큰::오픈콤클라이언트토큰](#opencomclienttoken)|COM 클라이언트에서 액세스 토큰을 초기화하려면 `CAccessToken` 클라이언트에서 호출을 처리하는 COM 서버 내에서 이 메서드를 호출합니다.|
|[CAccessToken::오픈 명 파이프 클라이언트 토큰](#opennamedpipeclienttoken)|클라이언트에서 액세스 토큰으로 초기화하려면 명명된 파이프를 `CAccessToken` 통해 요청을 받는 서버 내에서 이 메서드를 호출합니다.|
|[C액세스 토큰::오픈RPC클라이언트토큰](#openrpcclienttoken)|RPC 클라이언트에서 호출을 처리하는 서버 내에서 이 메서드를 `CAccessToken` 호출하여 클라이언트의 액세스 토큰을 초기화합니다.|
|[CAccess토큰::오픈스레드토큰](#openthreadtoken)|이 메서드를 호출하여 가장 수준을 설정한 다음 `CAccessToken` 지정된 스레드의 토큰으로 초기화합니다.|
|[C액세스토큰::P리빌레게체크](#privilegecheck)|`CAccessToken` 이 메서드를 호출하여 개체에서 지정된 권한 집합이 활성화되어 있는지 확인합니다.|
|[C액세스 토큰::되돌리기](#revert)|이 메서드를 호출하여 가장 토큰을 사용하는 스레드를 중지합니다.|
|[C액세스 토큰::세트디폴디폴드](#setdefaultdacl)|이 메서드를 호출하여 개체의 기본 `CAccessToken` DACL을 설정합니다.|
|[C액세스 토큰::세트 소유자](#setowner)|이 메서드를 호출하여 개체의 소유자를 설정합니다. `CAccessToken`|
|[C액세스 토큰::셋프라이터 그룹](#setprimarygroup)|이 메서드를 호출하여 개체의 `CAccessToken` 기본 그룹을 설정합니다.|

## <a name="remarks"></a>설명

[액세스 토큰은](/windows/win32/SecAuthZ/access-tokens) 프로세스 또는 스레드의 보안 컨텍스트를 설명하고 Windows 시스템에 로그온한 각 사용자에게 할당되는 개체입니다.

Windows의 액세스 제어 모델에 대한 자세한 내용은 Windows SDK의 [액세스 제어를](/windows/win32/SecAuthZ/access-control) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="caccesstokenattach"></a><a name="attach"></a>C액세스 토큰::첨부

지정된 액세스 토큰 핸들의 소유권을 가져가려면 이 메서드를 호출합니다.

```cpp
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>매개 변수

*h토큰*<br/>
액세스 토큰에 대한 핸들입니다.

### <a name="remarks"></a>설명

디버그 빌드에서 개체에 액세스 토큰의 `CAccessToken` 소유권이 이미 있는 경우 어설션 오류가 발생합니다.

## <a name="caccesstokencaccesstoken"></a><a name="dtor"></a>C액세스 토큰::~CAccessToken

소멸자입니다.

```
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제합니다.

## <a name="caccesstokenchecktokenmembership"></a><a name="checktokenmembership"></a>C액세스 토큰::체크토큰 멤버 자격

이 메서드를 호출하여 개체에서 지정된 `CAccessToken` SID가 활성화되어 있는지 확인합니다.

```
bool CheckTokenMembership(
    const CSid& rSid,
    bool* pbIsMember) const throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
[CSid 클래스](../../atl/reference/csid-class.md) 개체에 대한 참조입니다.

*pbIsMember*<br/>
검사 결과를 받는 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

메서드는 `CheckTokenMembership` 액세스 토큰의 사용자 및 그룹 SID에 SID가 있는지 확인합니다. SID가 있고 SE_GROUP_ENABLED 특성이 있는 경우 *pbIsMember는* TRUE로 설정됩니다. 그렇지 않으면 FALSE로 설정됩니다.

디버그 빌드에서 *pbIsMember가* 유효한 포인터가 아닌 경우 어설션 오류가 발생합니다.

> [!NOTE]
> 개체는 `CAccessToken` 기본 토큰이 아닌 가장 토큰이어야 합니다.

## <a name="caccesstokencreateimpersonationtoken"></a><a name="createimpersonationtoken"></a>CAccessToken::만들기 사칭 토큰

이 메서드를 호출하여 가장 액세스 토큰을 만듭니다.

```
bool CreateImpersonationToken(
    CAccessToken* pImp,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>매개 변수

*포 주가*<br/>
새 `CAccessToken` 개체에 대한 포인터입니다.

*Sil*<br/>
새 토큰의 가장 수준을 제공하는 [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) 지정된 형식을 지정합니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

`CreateImpersonationToken`을 호출 [duplicateToken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetoken) 새 가장 토큰을 만듭니다.

## <a name="caccesstokencreateprimarytoken"></a><a name="createprimarytoken"></a>CAccess토큰::기본 토큰 만들기

새 기본 토큰을 만들려면 이 메서드를 호출합니다.

```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pPri*<br/>
새 `CAccessToken` 개체에 대한 포인터입니다.

*dwDesiredAccess*<br/>
새 토큰에 대해 요청된 액세스 권한을 지정합니다. 기본값인 MAXIMUM_ALLOWED 호출자에게 유효한 모든 액세스 권한을 요청합니다. [액세스 권한에](/windows/win32/SecAuthZ/access-rights-and-access-masks) 대한 자세한 내용은 액세스 권한 및 액세스 마스크를 참조하십시오.

*pToken특성*<br/>
새 토큰에 대한 보안 설명기를 지정하고 자식 프로세스가 토큰을 상속할 수 있는지 여부를 결정하는 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 구조에 대한 포인터입니다. *pTokenAttributes가* NULL이면 토큰은 기본 보안 설명자가 되고 핸들을 상속할 수 없습니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

`CreatePrimaryToken`을 호출 [중복TokenEx](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetokenex) 새 기본 토큰을 만듭니다.

## <a name="caccesstokencreateprocessasuser"></a><a name="createprocessasuser"></a>CAccessToken::만들기프로세스AsUser

이 메서드를 호출하여 개체로 표시되는 사용자의 보안 컨텍스트에서 `CAccessToken` 실행되는 새 프로세스를 만듭니다.

```
bool CreateProcessAsUser(
    LPCTSTR pApplicationName,
    LPTSTR pCommandLine,
    LPPROCESS_INFORMATION pProcessInformation,
    LPSTARTUPINFO pStartupInfo,
    DWORD dwCreationFlags = NORMAL_PRIORITY_CLASS,
    bool bLoadProfile = false,
    const CSecurityAttributes* pProcessAttributes = NULL,
    const CSecurityAttributes* pThreadAttributes = NULL,
    bool bInherit = false,
    LPCTSTR pCurrentDirectory = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*p응용 프로그램 이름*<br/>
실행할 모듈을 지정하는 null 종료 된 문자열에 대한 포인터입니다. 이 매개 변수는 NULL이 아닐 수 있습니다.

*pCommandLine*<br/>
실행할 명령줄을 지정하는 null-종단 문자열에 대한 포인터입니다.

*pProcess 정보*<br/>
새 프로세스에 대한 식별 정보를 수신하는 [PROCESS_INFORMATION 구조에](/windows/win32/api/processthreadsapi/ns-processthreadsapi-process_information) 대한 포인터입니다.

*pStartup정보*<br/>
새 프로세스의 기본 창이 표시되는 방법을 지정하는 [STARTUPINFO](/windows/win32/api/processthreadsapi/ns-processthreadsapi-startupinfow) 구조에 대한 포인터입니다.

*dw크리에이션 플래그*<br/>
우선 순위 클래스 및 프로세스 만들기를 제어하는 추가 플래그를 지정합니다. 플래그 목록은 Win32 함수 [CreateProcessAUser를](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw) 참조하십시오.

*b로드 프로파일*<br/>
TRUE이면 사용자의 프로필에 [LoadUserProfile](/windows/win32/api/userenv/nf-userenv-loaduserprofilew)이 로드됩니다.

*pProcess속성*<br/>
새 프로세스에 대한 보안 설명기를 지정하고 자식 프로세스가 반환된 핸들을 상속할 수 있는지 여부를 결정하는 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 구조에 대한 포인터입니다. *pProcessAttributes가* NULL이면 프로세스에 기본 보안 설명자가 있으며 핸들을 상속할 수 없습니다.

*p스레드 특성*<br/>
새 스레드에 대한 보안 설명기를 지정하고 자식 프로세스가 반환된 핸들을 상속할 수 있는지 여부를 결정하는 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 구조에 대한 포인터입니다. *pThreadAttributes가* NULL이면 스레드는 기본 보안 설명자가 되고 핸들을 상속할 수 없습니다.

*b상속*<br/>
새 프로세스가 호출 프로세스에서 핸들을 상속하는지 여부를 나타냅니다. TRUE인 경우 호출 프로세스의 상속 가능한 각 열린 핸들은 새 프로세스에 의해 상속됩니다. 상속된 핸들은 원래 핸들과 동일한 값 및 액세스 권한을 갖습니다.

*pCurrent디렉터리*<br/>
새 프로세스에 대한 현재 드라이브 및 디렉터리를 지정하는 null 종료된 문자열에 대한 포인터입니다. 문자열은 드라이브 문자를 포함하는 전체 경로여야 합니다. 이 매개 변수가 NULL이면 새 프로세스는 호출 프로세스와 동일한 현재 드라이브 및 디렉터리를 갖습니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

`CreateProcessAsUser`는 `CreateProcessAsUser` Win32 함수를 사용하여 개체로 표시되는 사용자의 보안 컨텍스트에서 `CAccessToken` 실행되는 새 프로세스를 만듭니다. 필요한 매개 변수에 대한 전체 설명은 [CreateProcessAsUser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw) 함수에 대한 설명을 참조하십시오.

이 메서드가 성공하려면 `CAccessToken` 개체는 제한된 토큰이 아니면 할당PrimaryToken 및 IncreaseQuota 권한을 보유해야 합니다.

## <a name="caccesstokencreaterestrictedtoken"></a><a name="createrestrictedtoken"></a>CAccess토큰:만들기제한토큰

이 메서드를 호출하여 제한된 `CAccessToken` 새 개체를 만듭니다.

```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p제한토큰*<br/>
제한된 새 `CAccessToken` 개체입니다.

*시드토비활성화*<br/>
거부 `CTokenGroups` 전용 SID를 지정하는 개체입니다.

*시드토제한*<br/>
제한 `CTokenGroups` 하는 SID를 지정 하는 개체입니다.

*권한 삭제*<br/>
제한된 `CTokenPrivileges` 토큰에서 삭제할 권한을 지정하는 개체입니다. 기본값은 빈 개체를 만듭니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

`CreateRestrictedToken`[Create제한토큰](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createrestrictedtoken) Win32 함수를 사용하여 `CAccessToken` 제한사항이 있는 새 개체를 만듭니다.

> [!IMPORTANT]
> 을 `CreateRestrictedToken`사용하는 경우 다음을 확인합니다: 기존 토큰이 유효하고 사용자가 입력하지 않음) *SidsToDisable* 및 *PrivilegesToDelete는* 모두 유효하며 사용자가 입력하지 않습니다. 메서드가 FALSE를 반환하는 경우 기능을 거부합니다.

## <a name="caccesstokendetach"></a><a name="detach"></a>C액세스 토큰::D에타치

액세스 토큰의 소유권을 취소하려면 이 메서드를 호출합니다.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Return Value

핸들을 분리된 `CAccessToken` 핸들로 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 액세스 `CAccessToken`토큰의 소유권을 취소합니다.

## <a name="caccesstokendisableprivilege"></a><a name="disableprivilege"></a>C액세스토큰::D가능프리빌리지

이 메서드를 호출하여 개체에서 권한을 비활성화합니다. `CAccessToken`

```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>매개 변수

*psz특권*<br/>
개체에서 비활성화할 권한이 포함된 문자열에 `CAccessToken` 대한 포인터입니다.

*p이전 상태*<br/>
권한의 `CTokenPrivileges` 이전 상태를 포함 할 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokendisableprivileges"></a><a name="disableprivileges"></a>CAccessToken::D사용 가능한 특권

`CAccessToken` 이 메서드를 호출하여 개체에서 하나 이상의 권한을 비활성화합니다.

```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>매개 변수

*r프리빌리지*<br/>
개체에서 비활성화할 권한이 포함된 문자열 배열에 `CAccessToken` 대한 포인터입니다.

*p이전 상태*<br/>
권한의 `CTokenPrivileges` 이전 상태를 포함 할 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokenenableprivilege"></a><a name="enableprivilege"></a>CAccess토큰::인에이블프리빌리지

이 메서드를 호출하여 개체에서 권한을 활성화합니다. `CAccessToken`

```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>매개 변수

*psz특권*<br/>
개체에서 사용할 수 있는 권한이 포함된 `CAccessToken` 문자열에 대한 포인터입니다.

*p이전 상태*<br/>
권한의 `CTokenPrivileges` 이전 상태를 포함 할 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokenenableprivileges"></a><a name="enableprivileges"></a>CAccessToken::사용 권한 권한

`CAccessToken` 이 메서드를 호출하여 개체에서 하나 이상의 권한을 사용하도록 설정합니다.

```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>매개 변수

*r프리빌리지*<br/>
개체에서 사용할 수 있는 권한을 포함하는 문자열 배열에 `CAccessToken` 대한 포인터입니다.

*p이전 상태*<br/>
권한의 `CTokenPrivileges` 이전 상태를 포함 할 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokengetdefaultdacl"></a><a name="getdefaultdacl"></a>C액세스 토큰::GetDefaultDacl

이 메서드를 호출하여 개체의 기본 DACL을 `CAccessToken` 반환합니다.

```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pDacl*<br/>
개체의 기본 DACL을 수신하는 `CAccessToken` [CDacl 클래스 개체에](../../atl/reference/cdacl-class.md) 대한 포인터입니다.

### <a name="return-value"></a>Return Value

기본 DACL이 복구된 경우 TRUE를 반환합니다.

## <a name="caccesstokengeteffectivetoken"></a><a name="geteffectivetoken"></a>CAccessToken::GetEffective토큰

이 메서드를 호출하여 현재 스레드에 `CAccessToken` 대해 유효한 액세스 토큰과 동일한 개체를 가져옵니다.

```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>매개 변수

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokengetgroups"></a><a name="getgroups"></a>C액세스 토큰::Getgroups

`CAccessToken` 이 메서드를 호출하여 개체의 토큰 그룹을 반환합니다.

```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p 그룹*<br/>
그룹 정보를 수신할 [CTokenGroups 클래스](../../atl/reference/ctokengroups-class.md) 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokengethandle"></a><a name="gethandle"></a>C액세스 토큰::GetHandle

액세스 토큰에 대한 핸들을 검색하려면 이 메서드를 호출합니다.

```
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>Return Value

개체의 액세스 `CAccessToken` 토큰에 대한 핸들을 반환합니다.

## <a name="caccesstokengetimpersonationlevel"></a><a name="getimpersonationlevel"></a>C액세스 토큰::Get사칭 레벨

액세스 토큰에서 가장 수준을 얻으려면 이 메서드를 호출합니다.

```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p사칭 레벨*<br/>
가장 수준 정보를 수신하는 [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) 열거형 에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokengetlogonsessionid"></a><a name="getlogonsessionid"></a>C액세스 토큰::겟로그온세션ID

이 메서드를 호출하여 개체와 연결된 `CAccessToken` 로그온 세션 ID를 가져옵니다.

```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>매개 변수

*플루이드 (것)들*<br/>
로그온 세션 ID를 받게 되는 [LUID에](/windows/win32/api/winnt/ns-winnt-luid) 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

디버그 빌드에서 *pluid가* 잘못된 값인 경우 어설션 오류가 발생합니다.

## <a name="caccesstokengetlogonsid"></a><a name="getlogonsid"></a>C액세스 토큰::겟로그온 시드

이 메서드를 호출하여 개체와 연결된 `CAccessToken` Logon SID를 가져옵니다.

```
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p시드 (것)와 함께*<br/>
[CSid 클래스](../../atl/reference/csid-class.md) 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

디버그 빌드에서 *pSid가* 잘못된 값인 경우 어설션 오류가 발생합니다.

## <a name="caccesstokengetowner"></a><a name="getowner"></a>C액세스 토큰::GetOwner

이 메서드를 호출하여 소유자가 `CAccessToken` 개체와 연결하도록 합니다.

```
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p시드 (것)와 함께*<br/>
[CSid 클래스](../../atl/reference/csid-class.md) 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

이 액세스 토큰이 적용되는 동안 생성된 모든 개체에 대해 소유자는 기본적으로 설정됩니다.

## <a name="caccesstokengetprimarygroup"></a><a name="getprimarygroup"></a>C액세스 토큰::겟프라이티 그룹

`CAccessToken` 이 메서드를 호출하여 개체와 연결된 기본 그룹을 가져옵니다.

```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p시드 (것)와 함께*<br/>
[CSid 클래스](../../atl/reference/csid-class.md) 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

이 액세스 토큰이 적용되는 동안 생성된 모든 개체에 대해 그룹은 기본적으로 설정됩니다.

## <a name="caccesstokengetprivileges"></a><a name="getprivileges"></a>C액세스 토큰::Get권한

`CAccessToken` 이 메서드를 호출하여 개체와 연결된 권한을 가져옵니다.

```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p프리빌리지*<br/>
권한을 받을 [CTokenPrivileges 클래스](../../atl/reference/ctokenprivileges-class.md) 개체에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokengetprocesstoken"></a><a name="getprocesstoken"></a>CAccessToken::GetProcess토큰

지정된 프로세스의 액세스 토큰을 사용해서 `CAccessToken`을 초기화하려면 이 메서드를 호출합니다.

```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

*hProcess*<br/>
액세스 토큰이 열린 프로세스에 대한 핸들입니다. NULL의 기본값을 사용하는 경우 현재 프로세스가 사용됩니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

OpenProcessToken Win32 함수를 [호출합니다.](/windows/win32/api/processthreadsapi/nf-processthreadsapi-openprocesstoken)

## <a name="caccesstokengetprofile"></a><a name="getprofile"></a>C액세스 토큰::GetProfile

이 메서드를 호출하여 개체와 연결된 사용자 `CAccessToken` 프로필을 가리키는 핸들을 가져옵니다.

```
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>Return Value

사용자 프로필을 가리키는 핸들 또는 프로필이 없는 경우 NULL을 반환합니다.

## <a name="caccesstokengetsource"></a><a name="getsource"></a>C액세스 토큰::GetSource

`CAccessToken` 이 메서드를 호출하여 개체의 소스를 가져옵니다.

```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p소스*<br/>
[TOKEN_SOURCE](/windows/win32/api/winnt/ns-winnt-token_source) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokengetstatistics"></a><a name="getstatistics"></a>C액세스 토큰::통계학

개체와 연결된 정보를 얻으려면 `CAccessToken` 이 메서드를 호출합니다.

```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p통계*<br/>
[TOKEN_STATISTICS](/windows/win32/api/winnt/ns-winnt-token_statistics) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokengetterminalservicessessionid"></a><a name="getterminalservicessessionid"></a>CAccessToken::GetTerminal서비스세션ID

이 메서드를 호출하여 개체와 연결된 `CAccessToken` 터미널 서비스 세션 세션 ID를 가져옵니다.

```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pdwSessionId*<br/>
터미널 서비스 세션 ID입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokengetthreadtoken"></a><a name="getthreadtoken"></a>CAccessToken::GetThread토큰

지정된 스레드에서 `CAccessToken` 토큰을 초기화하려면 이 메서드를 호출합니다.

```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```

### <a name="parameters"></a>매개 변수

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

*hThread*<br/>
액세스 토큰이 열려 있는 스레드를 처리합니다.

*bOpenAsSelf*<br/>
`GetThreadToken` 메서드를 호출 하는 스레드의 보안 컨텍스트 또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 액세스 검사를 만들 지 여부를 나타냅니다.

이 매개 변수가 FALSE이면 호출 스레드에 대한 보안 컨텍스트를 사용하여 액세스 검사가 수행됩니다. 스레드가 클라이언트를 가장하는 경우 이 보안 컨텍스트는 클라이언트 프로세스의 컨텍스트일 수 있습니다. 이 매개 변수가 TRUE이면 호출 스레드에 대한 프로세스의 보안 컨텍스트를 사용하여 액세스 검사가 이루어집니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokengettokenid"></a><a name="gettokenid"></a>C액세스 토큰::GetTokenId

이 메서드를 호출하여 개체와 `CAccessToken` 연결된 토큰 ID를 가져옵니다.

```
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>매개 변수

*플루이드 (것)들*<br/>
토큰 ID를 받게 되는 [LUID에](/windows/win32/api/winnt/ns-winnt-luid) 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokengettype"></a><a name="gettype"></a>C액세스 토큰::GetType

`CAccessToken` 이 메서드를 호출하여 개체의 토큰 형식을 가져옵니다.

```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p유형*<br/>
성공 시 토큰 유형을 받는 [TOKEN_TYPE](/windows/win32/api/winnt/ne-winnt-token_type) 변수의 주소입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

TOKEN_TYPE 열거형 유형에는 기본 토큰과 가장 토큰을 구분하는 값이 포함되어 있습니다.

## <a name="caccesstokengetuser"></a><a name="getuser"></a>C액세스 토큰::Getuser

이 메서드를 호출하여 개체와 `CAccessToken` 연결된 사용자를 식별합니다.

```
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p시드 (것)와 함께*<br/>
[CSid 클래스](../../atl/reference/csid-class.md) 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="caccesstokenhkeycurrentuser"></a><a name="hkeycurrentuser"></a>C액세스 토큰::HKeyCurrentUser

이 메서드를 호출하여 개체와 연결된 사용자 `CAccessToken` 프로필을 가리키는 핸들을 가져옵니다.

```
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>Return Value

사용자 프로필을 가리키는 핸들 또는 프로필이 없는 경우 NULL을 반환합니다.

## <a name="caccesstokenimpersonate"></a><a name="impersonate"></a>CAccessToken::가장

이 메서드를 호출하여 스레드에 `CAccessToken` 가장을 할당합니다.

```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*hThread*<br/>
스레드를 처리하여 가장 토큰을 할당합니다. 이 핸들은 TOKEN_IMPERSONATE 액세스 권한으로 열려 있어야 합니다. *hThread가* NULL이면 메서드는 스레드가 가장 토큰 사용을 중지하도록 합니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

디버그 빌드에서 토큰에 대한 유효한 `CAccessToken` 포인터가 없는 경우 어설션 오류가 발생합니다.

[CAutoRevert사칭 클래스를](../../atl/reference/cautorevertimpersonation-class.md) 사용하여 가장된 액세스 토큰을 자동으로 되돌릴 수 있습니다.

## <a name="caccesstokenimpersonateloggedonuser"></a><a name="impersonateloggedonuser"></a>CAccessToken::가장로그온유저

호출 스레드가 로그온한 사용자의 보안 컨텍스트를 가장할 수 있도록 이 메서드를 호출합니다.

```
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

> [!IMPORTANT]
> 어떤 이유로든 가장 함수에 대한 호출이 실패하면 클라이언트가 가장되지 않으며 호출이 이루어진 프로세스의 보안 컨텍스트에서 클라이언트 요청이 이루어집니다. 프로세스가 권한이 높은 계정으로 실행중이거나 관리 그룹의 구성원으로 실행중인 경우 사용자는 허용되지 않는 작업을 수행할 수 있습니다. 따라서 이 함수에 대한 반환 값은 항상 확인해야 합니다.

## <a name="caccesstokenistokenrestricted"></a><a name="istokenrestricted"></a>C액세스 토큰::Is토큰제한

이 메서드를 호출하여 `CAccessToken` 개체에 제한된 SID 목록이 포함되어 있는지 테스트합니다.

```
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>Return Value

개체에 제한 된 SID 목록이 포함 된 경우 TRUE를 반환 합니다., 제한 된 SID가 없는 경우 FALSE 또는 메서드가 실패 하는 경우.

## <a name="caccesstokenloaduserprofile"></a><a name="loaduserprofile"></a>C액세스 토큰::로드유저 프로필

이 메서드를 호출하여 개체와 `CAccessToken` 연결된 사용자 프로필을 로드합니다.

```
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

디버그 빌드에서 유효한 토큰이 `CAccessToken` 없거나 사용자 프로필이 이미 있는 경우 어설션 오류가 발생합니다.

## <a name="caccesstokenlogonuser"></a><a name="logonuser"></a>C액세스 토큰::로그온유저

지정된 자격 증명과 연결된 사용자에 대한 로그온 세션을 만들려면 이 메서드를 호출합니다.

```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```

### <a name="parameters"></a>매개 변수

*pszUserName*<br/>
사용자 이름을 지정하는 null 종료 된 문자열에 대 한 포인터입니다. 로그온할 사용자 계정의 이름입니다.

*pszDomain*<br/>
계정 데이터베이스에 *pszUserName* 계정이 포함된 도메인 또는 서버의 이름을 지정하는 null 종료된 문자열에 대한 포인터입니다.

*psz암호*<br/>
*pszUserName에*의해 지정된 사용자 계정에 대한 일반 텍스트 암호를 지정하는 null 종료 된 문자열에 대한 포인터 .

*dwLogonType*<br/>
수행할 로그온 작업 유형을 지정합니다. 자세한 내용은 [LogonUser를](/windows/win32/api/winbase/nf-winbase-logonuserw) 참조하십시오.

*dwLogon공급자*<br/>
로그온 공급자를 지정합니다. 자세한 내용은 [LogonUser를](/windows/win32/api/winbase/nf-winbase-logonuserw) 참조하십시오.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

로그온으로 인한 액세스 토큰은 `CAccessToken`에 연결됩니다. 이 메서드가 성공하려면 `CAccessToken` 개체가 SE_TCB_NAME 권한을 보유하여 신뢰할 수 있는 컴퓨터 기반의 일부로 홀더를 식별해야 합니다. 필요한 권한에 대한 자세한 내용은 [LogonUser를](/windows/win32/api/winbase/nf-winbase-logonuserw) 참조하십시오.

## <a name="caccesstokenopencomclienttoken"></a><a name="opencomclienttoken"></a>C액세스 토큰::오픈콤클라이언트토큰

COM 클라이언트에서 액세스 토큰을 초기화하려면 `CAccessToken` 클라이언트에서 호출을 처리하는 COM 서버 내에서 이 메서드를 호출합니다.

```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>매개 변수

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

*b사칭*<br/>
TRUE이면 이 호출이 성공적으로 완료되면 현재 스레드가 호출 COM 클라이언트를 가장합니다. FALSE이면 액세스 토큰이 열리지만 이 호출이 완료되면 스레드에 가장 토큰이 없습니다.

*bOpenAsSelf*<br/>
[GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) 메서드를 호출 하는 스레드의 보안 컨텍스트또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 액세스 검사를 만들 지 여부를 나타냅니다.

이 매개 변수가 FALSE이면 호출 스레드에 대한 보안 컨텍스트를 사용하여 액세스 검사가 수행됩니다. 스레드가 클라이언트를 가장하는 경우 이 보안 컨텍스트는 클라이언트 프로세스의 컨텍스트일 수 있습니다. 이 매개 변수가 TRUE이면 호출 스레드에 대한 프로세스의 보안 컨텍스트를 사용하여 액세스 검사가 이루어집니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

[CAutoRevert사칭 클래스는](../../atl/reference/cautorevertimpersonation-class.md) *b사칭* 플래그를 TRUE로 설정하여 만든 가장된 액세스 토큰을 자동으로 되돌리는 데 사용할 수 있습니다.

## <a name="caccesstokenopennamedpipeclienttoken"></a><a name="opennamedpipeclienttoken"></a>CAccessToken::오픈 명 파이프 클라이언트 토큰

클라이언트에서 액세스 토큰으로 초기화하려면 명명된 파이프를 `CAccessToken` 통해 요청을 받는 서버 내에서 이 메서드를 호출합니다.

```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>매개 변수

*h파이프*<br/>
명명된 파이프를 처리합니다.

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

*b사칭*<br/>
TRUE이면 이 호출이 성공적으로 완료되면 현재 스레드가 호출 파이프 클라이언트를 가장합니다. FALSE이면 액세스 토큰이 열리지만 이 호출이 완료되면 스레드에 가장 토큰이 없습니다.

*bOpenAsSelf*<br/>
[GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) 메서드를 호출 하는 스레드의 보안 컨텍스트또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 액세스 검사를 만들 지 여부를 나타냅니다.

이 매개 변수가 FALSE이면 호출 스레드에 대한 보안 컨텍스트를 사용하여 액세스 검사가 수행됩니다. 스레드가 클라이언트를 가장하는 경우 이 보안 컨텍스트는 클라이언트 프로세스의 컨텍스트일 수 있습니다. 이 매개 변수가 TRUE이면 호출 스레드에 대한 프로세스의 보안 컨텍스트를 사용하여 액세스 검사가 이루어집니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

[CAutoRevert사칭 클래스는](../../atl/reference/cautorevertimpersonation-class.md) *b사칭* 플래그를 TRUE로 설정하여 만든 가장된 액세스 토큰을 자동으로 되돌리는 데 사용할 수 있습니다.

## <a name="caccesstokenopenrpcclienttoken"></a><a name="openrpcclienttoken"></a>C액세스 토큰::오픈RPC클라이언트토큰

RPC 클라이언트에서 호출을 처리하는 서버 내에서 이 메서드를 `CAccessToken` 호출하여 클라이언트의 액세스 토큰을 초기화합니다.

```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>매개 변수

*바인딩 핸들*<br/>
클라이언트에 대한 바인딩을 나타내는 서버의 바인딩 핸들입니다.

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

*b사칭*<br/>
TRUE이면 이 호출이 성공적으로 완료되면 현재 스레드가 호출 RPC 클라이언트를 가장합니다. FALSE이면 액세스 토큰이 열리지만 이 호출이 완료되면 스레드에 가장 토큰이 없습니다.

*bOpenAsSelf*<br/>
[GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) 메서드를 호출 하는 스레드의 보안 컨텍스트또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 액세스 검사를 만들 지 여부를 나타냅니다.

이 매개 변수가 FALSE이면 호출 스레드에 대한 보안 컨텍스트를 사용하여 액세스 검사가 수행됩니다. 스레드가 클라이언트를 가장하는 경우 이 보안 컨텍스트는 클라이언트 프로세스의 컨텍스트일 수 있습니다. 이 매개 변수가 TRUE이면 호출 스레드에 대한 프로세스의 보안 컨텍스트를 사용하여 액세스 검사가 이루어집니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

[CAutoRevert사칭 클래스는](../../atl/reference/cautorevertimpersonation-class.md) *b사칭* 플래그를 TRUE로 설정하여 만든 가장된 액세스 토큰을 자동으로 되돌리는 데 사용할 수 있습니다.

## <a name="caccesstokenopenthreadtoken"></a><a name="openthreadtoken"></a>CAccess토큰::오픈스레드토큰

이 메서드를 호출하여 가장 수준을 설정한 다음 `CAccessToken` 지정된 스레드의 토큰으로 초기화합니다.

```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```

### <a name="parameters"></a>매개 변수

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

*b사칭*<br/>
TRUE이면 이 메서드가 완료된 후 스레드가 요청된 가장 수준에 남아 있습니다. FALSE인 경우 스레드는 원래 가장 수준으로 되돌아갑니다.

*bOpenAsSelf*<br/>
[GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) 메서드를 호출 하는 스레드의 보안 컨텍스트또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 액세스 검사를 만들 지 여부를 나타냅니다.

이 매개 변수가 FALSE이면 호출 스레드에 대한 보안 컨텍스트를 사용하여 액세스 검사가 수행됩니다. 스레드가 클라이언트를 가장하는 경우 이 보안 컨텍스트는 클라이언트 프로세스의 컨텍스트일 수 있습니다. 이 매개 변수가 TRUE이면 호출 스레드에 대한 프로세스의 보안 컨텍스트를 사용하여 액세스 검사가 이루어집니다.

*Sil*<br/>
토큰의 가장 수준을 제공하는 [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) 지정된 형식을 지정합니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

`OpenThreadToken`[CAccessToken::GetThreadToken과](#getthreadtoken)유사하지만 스레드의 액세스 `CAccessToken` 토큰에서 초기화하기 전에 가장 수준을 설정합니다.

[CAutoRevert사칭 클래스는](../../atl/reference/cautorevertimpersonation-class.md) *b사칭* 플래그를 TRUE로 설정하여 만든 가장된 액세스 토큰을 자동으로 되돌리는 데 사용할 수 있습니다.

## <a name="caccesstokenprivilegecheck"></a><a name="privilegecheck"></a>C액세스토큰::P리빌레게체크

`CAccessToken` 이 메서드를 호출하여 개체에서 지정된 권한 집합이 활성화되어 있는지 확인합니다.

```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
    bool* pbResult) const throw();
```

### <a name="parameters"></a>매개 변수

*필수 특전*<br/>
[PRIVILEGE_SET](/windows/win32/api/winnt/ns-winnt-privilege_set) 구조에 대한 포인터입니다.

*pb결과*<br/>
메서드가 설정한 값을 포인터로 지정한 권한 중 일부 또는 `CAccessToken` 전부가 개체에서 활성화되어 있는지 여부를 나타냅니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

반환할 `PrivilegeCheck` 때 `Attributes` 각 [LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes) 구조의 멤버는 해당 권한이 활성화된 경우 SE_PRIVILEGE_USED_FOR_ACCESS 설정됩니다. 이 메서드는 [PrivilegeCheck](/windows/win32/api/securitybaseapi/nf-securitybaseapi-privilegecheck) Win32 함수를 호출합니다.

## <a name="caccesstokenrevert"></a><a name="revert"></a>C액세스 토큰::되돌리기

스레드가 가장 토큰을 사용하지 못하도록 하려면 이 메서드를 호출합니다.

```
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>매개 변수

*hThread*<br/>
스레드를 처리하여 가장에서 되돌리라고 합니다. *hThread가* NULL이면 현재 스레드가 가정됩니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

가장 토큰의 회귀는 [CAutoVert사칭 클래스를](../../atl/reference/cautorevertimpersonation-class.md)사용하여 자동으로 수행할 수 있습니다.

## <a name="caccesstokensetdefaultdacl"></a><a name="setdefaultdacl"></a>C액세스 토큰::세트디폴디폴드

이 메서드를 호출하여 개체의 기본 `CAccessToken` DACL을 설정합니다.

```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>매개 변수

*rDacl*<br/>
새 기본 [CDacl 클래스](../../atl/reference/cdacl-class.md) 정보입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

기본 DACL은 이 액세스 토큰을 사용하여 새 개체를 만들 때 기본적으로 사용되는 DACL입니다.

## <a name="caccesstokensetowner"></a><a name="setowner"></a>C액세스 토큰::세트 소유자

이 메서드를 호출하여 개체의 소유자를 설정합니다. `CAccessToken`

```
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
소유자 정보를 포함하는 [CSid 클래스](../../atl/reference/csid-class.md) 개체입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

소유자는 이 액세스 토큰이 적용되는 동안 생성된 새 개체에 사용되는 기본 소유자입니다.

## <a name="caccesstokensetprimarygroup"></a><a name="setprimarygroup"></a>C액세스 토큰::셋프라이터 그룹

이 메서드를 호출하여 개체의 `CAccessToken` 기본 그룹을 설정합니다.

```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
기본 그룹 정보를 포함하는 [CSid 클래스](../../atl/reference/csid-class.md) 개체입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

기본 그룹은 이 액세스 토큰이 적용되는 동안 생성된 새 개체의 기본 그룹입니다.

## <a name="see-also"></a>참조

[ATL보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[토큰 액세스](/windows/win32/SecAuthZ/access-tokens)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
