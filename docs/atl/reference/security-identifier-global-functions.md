---
title: 보안 식별자 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::Sids::AccountOps
- atlsecurity/ATL::Sids::Admins
- atlsecurity/ATL::Sids::AnonymousLogon
- atlsecurity/ATL::Sids::AuthenticatedUser
- atlsecurity/ATL::Sids::BackupOps
- atlsecurity/ATL::Sids::Batch
- atlsecurity/ATL::Sids::CreatorGroup
- atlsecurity/ATL::Sids::CreatorGroupServer
- atlsecurity/ATL::Sids::CreatorOwner
- atlsecurity/ATL::Sids::CreatorOwnerServer
- atlsecurity/ATL::Sids::Dialup
- atlsecurity/ATL::Sids::Guests
- atlsecurity/ATL::Sids::Interactive
- atlsecurity/ATL::Sids::Local
- atlsecurity/ATL::Sids::Network
- atlsecurity/ATL::Sids::NetworkService
- atlsecurity/ATL::Sids::Null
- atlsecurity/ATL::Sids::PowerUsers
- atlsecurity/ATL::Sids::PrintOps
- atlsecurity/ATL::Sids::Proxy
- atlsecurity/ATL::Sids::RasServers
- atlsecurity/ATL::Sids::Replicator
- atlsecurity/ATL::Sids::RestrictedCode
- atlsecurity/ATL::Sids::Self
- atlsecurity/ATL::Sids::ServerLogon
- atlsecurity/ATL::Sids::Service
- atlsecurity/ATL::Sids::System
- atlsecurity/ATL::Sids::SystemOps
- atlsecurity/ATL::Sids::TerminalServer
- atlsecurity/ATL::Sids::Users
- atlsecurity/ATL::Sids::World
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
ms.openlocfilehash: 83326c13de7585806ab841f728f587f1131b5e8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325988"
---
# <a name="security-identifier-global-functions"></a>보안 식별자 전역 함수

이러한 함수는 잘 알려진 일반적인 SID 개체를 반환합니다.

> [!IMPORTANT]
> 다음 표에 나열된 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[Sids::AccountOps](#accountops)|DOMAIN_ALIAS_RID_ACCOUNT_OPS SID를 반환합니다.|
|[Sids::Admins](#admins)|DOMAIN_ALIAS_RID_ADMINS SID를 반환합니다.|
|[Sids::AnonymousLogon](#anonymouslogon)|SECURITY_ANONYMOUS_LOGON_RID SID를 반환합니다.|
|[Sids::AuthenticatedUser](#authenticateduser)|SECURITY_AUTHENTICATED_USER_RID SID를 반환합니다.|
|[Sids::BackupOps](#backupops)|DOMAIN_ALIAS_RID_BACKUP_OPS SID를 반환합니다.|
|[Sids::Batch](#batch)|SECURITY_BATCH_RID SID를 반환합니다.|
|[Sids::CreatorGroup](#creatorgroup)|SECURITY_CREATOR_GROUP_RID SID를 반환합니다.|
|[Sids::CreatorGroupServer](#creatorgroupserver)|SECURITY_CREATOR_GROUP_SERVER_RID SID를 반환합니다.|
|[Sids::CreatorOwner](#creatorowner)|SECURITY_CREATOR_OWNER_RID SID를 반환합니다.|
|[Sids::CreatorOwnerServer](#creatorownerserver)|SECURITY_CREATOR_OWNER_SERVER_RID SID를 반환합니다.|
|[Sids::Dialup](#dialup)|SECURITY_DIALUP_RID SID를 반환합니다.|
|[Sids::Guests](#guests)|DOMAIN_ALIAS_RID_GUESTS SID를 반환합니다.|
|[Sids::Interactive](#interactive)|SECURITY_INTERACTIVE_RID SID를 반환합니다.|
|[Sids::Local](#local)|SECURITY_LOCAL_RID SID를 반환합니다.|
|[Sids::Network](#network)|SECURITY_NETWORK_RID SID를 반환합니다.|
|[Sids::NetworkService](#networkservice)|SECURITY_NETWORK_SERVICE_RID SID를 반환합니다.|
|[Sids::Null](#null)|SECURITY_NULL_RID SID를 반환합니다.|
|[Sids::PreW2KAccess](#prew2kaccess)|DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID를 반환합니다.|
|[Sids::PowerUsers](#powerusers)|DOMAIN_ALIAS_RID_POWER_USERS SID를 반환합니다.|
|[Sids::PrintOps](#printops)|DOMAIN_ALIAS_RID_PRINT_OPS SID를 반환합니다.|
|[Sids::Proxy](#proxy)|SECURITY_PROXY_RID SID를 반환합니다.|
|[Sids::RasServers](#rasservers)|DOMAIN_ALIAS_RID_RAS_SERVERS SID를 반환합니다.|
|[Sids::Replicator](#replicator)|DOMAIN_ALIAS_RID_REPLICATOR SID를 반환합니다.|
|[Sids::RestrictedCode](#restrictedcode)|SECURITY_RESTRICTED_CODE_RID SID를 반환합니다.|
|[Sids::Self](#self)|SECURITY_PRINCIPAL_SELF_RID SID를 반환합니다.|
|[Sids::ServerLogon](#serverlogon)|SECURITY_SERVER_LOGON_RID SID를 반환합니다.|
|[Sids::Service](#service)|SECURITY_SERVICE_RID SID를 반환합니다.|
|[Sids::System](#system)|SECURITY_LOCAL_SYSTEM_RID SID를 반환합니다.|
|[Sids::SystemOps](#systemops)|DOMAIN_ALIAS_RID_SYSTEM_OPS SID를 반환합니다.|
|[Sids::TerminalServer](#terminalserver)|SECURITY_TERMINAL_SERVER_RID SID를 반환합니다.|
|[Sids::Users](#users)|DOMAIN_ALIAS_RID_USERS SID를 반환합니다.|
|[시드:::세계](#world)|SECURITY_WORLD_RID SID를 반환합니다.|

### <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="sidsaccountops"></a><a name="accountops"></a>시드::계정 옵스

DOMAIN_ALIAS_RID_ACCOUNT_OPS SID를 반환합니다.

```
CSid AccountOps() throw(...);
```

## <a name="sidsadmins"></a><a name="admins"></a>시드::관리자

DOMAIN_ALIAS_RID_ADMINS SID를 반환합니다.

```
CSid Admins() throw(...);
```

## <a name="sidsanonymouslogon"></a><a name="anonymouslogon"></a>시드::익명로그온

SECURITY_ANONYMOUS_LOGON_RID SID를 반환합니다.

```
CSid AnonymousLogon() throw(...);
```

## <a name="sidsauthenticateduser"></a><a name="authenticateduser"></a>시드::인증된 사용자

SECURITY_AUTHENTICATED_USER_RID SID를 반환합니다.

```
CSid AuthenticatedUser() throw(...);
```

## <a name="sidsbackupops"></a><a name="backupops"></a>시드::백업 옵스

DOMAIN_ALIAS_RID_BACKUP_OPS SID를 반환합니다.

```
CSid BackupOps() throw(...);
```

## <a name="sidsbatch"></a><a name="batch"></a>시드::배치

SECURITY_BATCH_RID SID를 반환합니다.

```
CSid Batch() throw(...);
```

## <a name="sidscreatorgroup"></a><a name="creatorgroup"></a>시드:::크리에이터 그룹

SECURITY_CREATOR_GROUP_RID SID를 반환합니다.

```
CSid CreatorGroup() throw(...);
```

## <a name="sidscreatorgroupserver"></a><a name="creatorgroupserver"></a>시드:::크리에이터그룹서버

SECURITY_CREATOR_GROUP_SERVER_RID SID를 반환합니다.

```
CSid CreatorGroupServer() throw(...);
```

## <a name="sidscreatorowner"></a><a name="creatorowner"></a>시드:::크리에이터 오너

SECURITY_CREATOR_OWNER_RID SID를 반환합니다.

```
CSid CreatorOwner() throw(...);
```

## <a name="sidscreatorownerserver"></a><a name="creatorownerserver"></a>시드:::크리에이터 오너서버

SECURITY_CREATOR_OWNER_SERVER_RID SID를 반환합니다.

```
CSid CreatorOwnerServer() throw(...);
```

## <a name="sidsdialup"></a><a name="dialup"></a>시드::D

SECURITY_DIALUP_RID SID를 반환합니다.

```
CSid Dialup() throw(...);
```

## <a name="sidsguests"></a><a name="guests"></a>시드:::게스트

DOMAIN_ALIAS_RID_GUESTS SID를 반환합니다.

```
CSid Guests() throw(...);
```

## <a name="sidsinteractive"></a><a name="interactive"></a>시드::대화형

SECURITY_INTERACTIVE_RID SID를 반환합니다.

```
CSid Interactive() throw(...);
```

## <a name="sidslocal"></a><a name="local"></a>시드::로컬

SECURITY_LOCAL_RID SID를 반환합니다.

```
CSid Local() throw(...);
```

## <a name="sidsnetwork"></a><a name="network"></a>시드::네트워크

SECURITY_NETWORK_RID SID를 반환합니다.

```
CSid Network() throw(...);
```

## <a name="sidsnetworkservice"></a><a name="networkservice"></a>시드::네트워크 서비스

SECURITY_NETWORK_SERVICE_RID SID를 반환합니다.

```
CSid NetworkService() throw(...);
```

### <a name="remarks"></a>설명

네트워크 서비스를 사용하여 NT AUTHORITY\NetworkService 사용자가 CPerfMon 보안 개체를 읽을 수 있도록 합니다. NetworkService는 DLL이 Windows XP 홈 에디션, Windows XP 프로페셔널, Windows Server 2003 및 더 큰 운영 체제의 NetworkService 계정으로 로그인할 수 있도록 하는 ATLServer 코드에 보안 특성을 추가합니다.

Perfmon MMC의 ATLServer CPerfMon 클래스로 사용자 지정 로그 카운터를 만들면 실시간 보기에서 올바르게 표시되지만 로그 파일을 볼 때 카운터가 나타나지 않을 수 있습니다. CPerfMon 사용자 지정 성능 카운터는 Windows XP 홈 에디션, Windows XP Professional, Windows Server 2003(또는 그 이상) 운영 체제에서 "성능 로그 및 경고" 서비스(smlogsvc.exe)에서 실행하는 데 필요한 권한이 없습니다. 이 서비스는 "NT AUTHORITY\NetworkService" 계정에서 실행됩니다.

## <a name="sidsnull"></a><a name="null"></a>시드::Null

SECURITY_NULL_RID SID를 반환합니다.

```
CSid Null() throw(...);
```

## <a name="sidsprew2kaccess"></a><a name="prew2kaccess"></a>시드::PreW2KAccess

DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID를 반환합니다.

```
CSid PreW2KAccess() throw(...);
```

## <a name="sidspowerusers"></a><a name="powerusers"></a>시드::PowerUsers

DOMAIN_ALIAS_RID_POWER_USERS SID를 반환합니다.

```
CSid PowerUsers() throw(...);
```

## <a name="sidsprintops"></a><a name="printops"></a>시드::P린트옵스

DOMAIN_ALIAS_RID_PRINT_OPS SID를 반환합니다.

```
CSid PrintOps() throw(...);
```

## <a name="sidsproxy"></a><a name="proxy"></a>시드::P

SECURITY_PROXY_RID SID를 반환합니다.

```
CSid Proxy() throw(...);
```

## <a name="sidsrasservers"></a><a name="rasservers"></a>시드:::RasServers

DOMAIN_ALIAS_RID_RAS_SERVERS SID를 반환합니다.

```
CSid RasServers() throw(...);
```

## <a name="sidsreplicator"></a><a name="replicator"></a>시드::복제기

DOMAIN_ALIAS_RID_REPLICATOR SID를 반환합니다.

```
CSid Replicator() throw(...);
```

## <a name="sidsrestrictedcode"></a><a name="restrictedcode"></a>시드::제한코드

SECURITY_RESTRICTED_CODE_RID SID를 반환합니다.

```
CSid RestrictedCode() throw(...);
```

## <a name="sidsself"></a><a name="self"></a>시드:::셀프

SECURITY_PRINCIPAL_SELF_RID SID를 반환합니다.

```
CSid Self() throw(...);
```

## <a name="sidsserverlogon"></a><a name="serverlogon"></a>시드:::서버 로그온

SECURITY_SERVER_LOGON_RID SID를 반환합니다.

```
CSid ServerLogon() throw(...);
```

## <a name="sidsservice"></a><a name="service"></a>시드:::서비스

SECURITY_SERVICE_RID SID를 반환합니다.

```
CSid Service() throw(...);
```

## <a name="sidssystem"></a><a name="system"></a>시드::시스템

SECURITY_LOCAL_SYSTEM_RID SID를 반환합니다.

```
CSid System() throw(...);
```

## <a name="sidssystemops"></a><a name="systemops"></a>시드:::시스템 옵스

DOMAIN_ALIAS_RID_SYSTEM_OPS SID를 반환합니다.

```
CSid SystemOps() throw(...);
```

## <a name="sidsterminalserver"></a><a name="terminalserver"></a>시드::터미널 서버

SECURITY_TERMINAL_SERVER_RID SID를 반환합니다.

```
CSid TerminalServer() throw(...);
```

## <a name="sidsusers"></a><a name="users"></a>시드::사용자

DOMAIN_ALIAS_RID_USERS SID를 반환합니다.

```
CSid Users() throw(...);
```

## <a name="sidsworld"></a><a name="world"></a>시드:::세계

SECURITY_WORLD_RID SID를 반환합니다.

```
CSid World() throw(...);
```

## <a name="see-also"></a>참고 항목

[Functions](../../atl/reference/atl-functions.md)
