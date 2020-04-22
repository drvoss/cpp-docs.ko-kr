---
title: CSacl 클래스
ms.date: 11/04/2016
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
ms.openlocfilehash: d5a060555901361ef6c70c6a4f801605eafd92cf
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746556"
---
# <a name="csacl-class"></a>CSacl 클래스

이 클래스는 SACL(시스템 액세스 제어 목록) 구조의 래퍼입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CSacl : public CAcl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CSacl:::CSacl](#csacl)|생성자입니다.|
|[CSacl::~CSacl](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSacl::추가 감사 에이스](#addauditace)|개체에 감사 액세스 제어 항목(ACE)을 추가합니다. `CSacl`|
|[CSacl::GetAceCount](#getacecount)|개체의 액세스 제어 항목(AEs) 수를 `CSacl` 반환합니다.|
|[CSacl::제거 에이스](#removeace)|개체에서 특정 ACE(액세스 제어 항목)를 제거합니다. `CSacl`|
|[CSacl::제거모든 에이스](#removeallaces)|개체에 포함된 모든 AC를 `CSacl` 제거합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CSacl::연산자 =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

SACL에는 도메인 컨트롤러의 보안 이벤트 로그에서 감사 레코드를 생성하는 액세스 시도 유형을 지정하는 액세스 제어 항목(ACE)이 포함되어 있습니다. SACL은 개체의 복제본이 포함된 모든 도메인 컨트롤러가 아니라 액세스 시도가 발생한 도메인 컨트롤러에서만 로그 항목을 생성합니다.

개체의 보안 설명자에서 SACL을 설정하거나 검색하려면 요청 스레드의 액세스 토큰에서 SE_SECURITY_NAME 권한을 활성화해야 합니다. 관리자 그룹에는 기본적으로 이 권한이 부여되며 다른 사용자 또는 그룹에 부여할 수 있습니다. 권한이 부여되는 것이 전부는 아닙니다: 권한에 의해 정의된 작업을 수행하기 전에 권한을 활성화하려면 보안 액세스 토큰에서 권한을 활성화해야 합니다. 이 모델을 사용하면 특정 시스템 작업에 대해서만 권한을 사용하도록 설정한 다음 더 이상 필요하지 않을 때 사용하지 않도록 설정할 수 있습니다. SE_SECURITY_NAME 활성화에 대한 예는 [AtlGetSacl](security-global-functions.md#atlgetsacl) 및 [AtlSetSacl을](security-global-functions.md#atlsetsacl) 참조하십시오.

제공된 클래스 메서드를 사용하여 개체에서 AC를 추가, `SACL` 제거, 생성 및 삭제합니다. 또한 [아틀겟사클과](security-global-functions.md#atlgetsacl) [아틀셋사클을](security-global-functions.md#atlsetsacl)참조하십시오.

Windows의 액세스 제어 모델에 대한 자세한 내용은 Windows SDK의 [액세스 제어를](/windows/win32/SecAuthZ/access-control) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CAcl](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="csacladdauditace"></a><a name="addauditace"></a>CSacl::추가 감사 에이스

개체에 감사 액세스 제어 항목(ACE)을 추가합니다. `CSacl`

```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
[CSid 개체입니다.](../../atl/reference/csid-class.md)

*액세스 마스크*<br/>
지정된 `CSid` 개체에 대해 감사할 액세스 권한 마스크가 지정됩니다.

*b성공*<br/>
허용된 액세스 시도를 감사할지 여부를 지정합니다. 감사를 사용하도록 이 플래그를 true로 설정합니다. 그렇지 않으면 false로 설정합니다.

*b실패*<br/>
거부된 액세스 시도를 감사할지 여부를 지정합니다. 감사를 사용하도록 이 플래그를 true로 설정합니다. 그렇지 않으면 false로 설정합니다.

*에이스 플래그*<br/>
ACE 상속을 제어하는 비트 플래그 집합입니다.

*pObjectType*<br/>
개체 유형입니다.

*p상속된 개체 유형*<br/>
상속된 개체 형식입니다.

### <a name="return-value"></a>Return Value

ACE가 `CSacl` 개체에 추가된 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

`CSacl` 개체에는 보안 이벤트 로그에서 감사 레코드를 생성하는 액세스 시도 유형을 지정하는 액세스 제어 항목(ACEs)이 포함되어 있습니다. 이 메서드는 개체에 `CSacl` 이러한 ACE를 추가 합니다.

*AceFlags* 매개 변수에서 설정할 수 있는 다양한 플래그에 대한 설명은 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 를 참조하십시오.

## <a name="csaclcsacl"></a><a name="csacl"></a>CSacl:::CSacl

생성자입니다.

```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존(액세스 `ACL` 제어 목록) 구조입니다.

### <a name="remarks"></a>설명

객체는 `CSacl` 기존 `ACL` 구조를 사용하여 선택적으로 만들 수 있습니다. 이 매개 변수가 시스템 액세스 제어 목록(SACL)이지 임의 액세스 제어 목록(DACL)이 아닌지 확인합니다. 디버그 빌드에서 DACL이 제공되면 어설션이 발생합니다. 릴리스에서 DACL의 모든 항목은 무시됩니다.

## <a name="csaclcsacl"></a><a name="dtor"></a>CSacl::~CSacl

소멸자입니다.

```
~CSacl() throw();
```

### <a name="remarks"></a>설명

소멸자는 모든 액세스 제어 항목(ACEs)을 포함하여 개체에서 획득한 모든 리소스를 해제합니다.

## <a name="csaclgetacecount"></a><a name="getacecount"></a>CSacl::GetAceCount

개체의 액세스 제어 항목(AEs) 수를 `CSacl` 반환합니다.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Return Value

개체에 포함된 AC의 수를 `CSacl` 반환합니다.

## <a name="csacloperator-"></a><a name="operator_eq"></a>CSacl::연산자 =

대입 연산자입니다.

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존 `ACL` 개체에 할당할 (액세스 제어 목록)입니다.

### <a name="return-value"></a>Return Value

업데이트된 `CSacl` 개체에 대한 참조를 반환합니다. 매개 변수가 `ACL` 실제로 시스템 액세스 제어 목록(SACL)이 아닌 임의 액세스 제어 목록(DACL)인지 확인합니다. 디버그 빌드에서 어설션이 발생하고 릴리스 빌드에서 매개 변수가 `ACL` 무시됩니다.

## <a name="csaclremoveace"></a><a name="removeace"></a>CSacl::제거 에이스

개체에서 특정 ACE(액세스 제어 항목)를 제거합니다. `CSacl`

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
제거할 ACE 항목에 대한 인덱스를 만듭니다.

### <a name="remarks"></a>설명

이 메서드는 [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)에서 파생됩니다.

## <a name="csaclremoveallaces"></a><a name="removeallaces"></a>CSacl::제거모든 에이스

개체에 포함된 모든 액세스 제어 항목(AC)을 `CSacl` 제거합니다.

```cpp
void RemoveAllAces() throw();
```

### <a name="remarks"></a>설명

개체의 `ACE` 모든 구조(있는 경우)를 제거합니다. `CSacl`

## <a name="see-also"></a>참조

[카클 클래스](../../atl/reference/cacl-class.md)<br/>
[ACL](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Ace](/windows/win32/SecAuthZ/access-control-entries)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 글로벌 기능](../../atl/reference/security-global-functions.md)
