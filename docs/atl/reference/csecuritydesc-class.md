---
title: CSecurityDesc 클래스
ms.date: 11/04/2016
f1_keywords:
- CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::FromString
- ATLSECURITY/ATL::CSecurityDesc::GetControl
- ATLSECURITY/ATL::CSecurityDesc::GetDacl
- ATLSECURITY/ATL::CSecurityDesc::GetGroup
- ATLSECURITY/ATL::CSecurityDesc::GetOwner
- ATLSECURITY/ATL::CSecurityDesc::GetPSECURITY_DESCRIPTOR
- ATLSECURITY/ATL::CSecurityDesc::GetSacl
- ATLSECURITY/ATL::CSecurityDesc::IsDaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsDaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsDaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsDaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsGroupDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsOwnerDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsSaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsSaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::MakeAbsolute
- ATLSECURITY/ATL::CSecurityDesc::MakeSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::SetControl
- ATLSECURITY/ATL::CSecurityDesc::SetDacl
- ATLSECURITY/ATL::CSecurityDesc::SetGroup
- ATLSECURITY/ATL::CSecurityDesc::SetOwner
- ATLSECURITY/ATL::CSecurityDesc::SetSacl
- ATLSECURITY/ATL::CSecurityDesc::ToString
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
ms.openlocfilehash: 926e4e0a795982479188d90ed866bf5e2584c187
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330972"
---
# <a name="csecuritydesc-class"></a>CSecurityDesc 클래스

이 클래스는 구조의 `SECURITY_DESCRIPTOR` 래퍼입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CSecurityDesc
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C보안데스크::C보안데스](#csecuritydesc)|생성자입니다.|
|[CSecurity데스크::~CSecurity데스크](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C보안데스크::FromString](#fromstring)|문자열 형식 보안 설명자는 유효한 기능 보안 설명자로 변환합니다.|
|[C보안데스크::GetControl](#getcontrol)|보안 설명자에서 제어 정보를 검색합니다.|
|[CSecurityDesc::GetDacl](#getdacl)|보안 설명자에서 임의 액세스 제어 목록(DACL) 정보를 검색합니다.|
|[C보안데스크::겟그룹](#getgroup)|보안 설명자에서 기본 그룹 정보를 검색합니다.|
|[CSecurityDesc::GetOwner](#getowner)|보안 설명자에서 소유자 정보 형식을 검색합니다.|
|[C보안데스크::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|구조에 대한 `SECURITY_DESCRIPTOR` 포인터를 반환합니다.|
|[CSecurityDesc:::겟사클](#getsacl)|보안 설명자에서 시스템 액세스 제어 목록(SACL) 정보를 검색합니다.|
|[CSecurityDesc::IsDaclAuto상속](#isdaclautoinherited)|DACL이 자동 전파를 지원하도록 구성되었는지 확인합니다.|
|[C보안데스크::이스다클디폴드](#isdacldefaulted)|보안 설명자가 기본 DACL로 구성되었는지 확인합니다.|
|[CSecurityDesc::이스다클 현재](#isdaclpresent)|보안 설명자가 DACL을 포함하고 있는지 확인합니다.|
|[CSecurityDesc:::IsDaclprotected](#isdaclprotected)|수정을 방지하기 위해 DACL이 구성되었는지 확인합니다.|
|[C보안데스크::IsGroup기본](#isgroupdefaulted)|보안 설명자의 그룹 보안 식별자(SID)가 기본적으로 설정되었는지 확인합니다.|
|[C보안데스크::IsOwner기본](#isownerdefaulted)|보안 설명자의 소유자 SID가 기본적으로 설정되었는지 확인합니다.|
|[CSecurityDesc::IsSaclAuto상속](#issaclautoinherited)|자동 전파를 지원하도록 SACL이 구성되었는지 확인합니다.|
|[C보안데스크::IsSaclDefaulted](#issacldefaulted)|보안 설명자가 기본 SACL로 구성되었는지 확인합니다.|
|[CSecurityDesc::IsSacl현재](#issaclpresent)|보안 설명자가 SACL을 포함하고 있는지 확인합니다.|
|[CSecurityDesc:::IsSaclprotected](#issaclprotected)|수정을 방지하기 위해 SACL이 구성되었는지 확인합니다.|
|[CSecurityDesc::IsSelf상대](#isselfrelative)|보안 설명자가 자체 상대 형식인지 확인합니다.|
|[C보안데스크::메이크Absolute](#makeabsolute)|이 메서드를 호출하여 보안 설명기를 절대 형식으로 변환합니다.|
|[CSecurityDesc:::자기 친척 만들기](#makeselfrelative)|이 메서드를 호출하여 보안 설명기를 자체 상대 형식으로 변환합니다.|
|[C보안데스크::세트컨트롤](#setcontrol)|보안 설명자의 제어 비트를 설정합니다.|
|[CSecurityDesc:::세다클](#setdacl)|DACL에서 정보를 설정합니다. DACL이 보안 설명자에 이미 있으면 대체됩니다.|
|[C보안데스크::세트그룹](#setgroup)|절대 형식 보안 설명자의 기본 그룹 정보를 설정하여 이미 있는 기본 그룹 정보를 대체합니다.|
|[C보안데스크::세트 오너](#setowner)|절대 형식 보안 설명자의 소유자 정보를 설정하여 이미 있는 소유자 정보를 대체합니다.|
|[CSecurityDesc:::세사클](#setsacl)|SACL에서 정보를 설정합니다. SACL이 보안 설명자에 이미 있으면 대체됩니다.|
|[CSecurityDesc:::토스트링](#tostring)|보안 설명기를 문자열 형식으로 변환합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CSecurityDesc::연산자 const SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|구조에 대한 `SECURITY_DESCRIPTOR` 포인터를 반환합니다.|
|[C보안데스크::연산자 =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

구조에는 `SECURITY_DESCRIPTOR` 개체와 연결된 보안 정보가 포함되어 있습니다. 응용 프로그램은 이 구조를 사용하여 개체의 보안 상태를 설정하고 쿼리합니다. 또한 [AtlGet보안설명서를](security-global-functions.md#atlgetsecuritydescriptor)참조하십시오.

응용 프로그램은 `SECURITY_DESCRIPTOR` 구조를 직접 수정해서는 안 되며 대신 제공된 클래스 메서드를 사용해야 합니다.

Windows의 액세스 제어 모델에 대한 자세한 내용은 Windows SDK의 [액세스 제어를](/windows/win32/SecAuthZ/access-control) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="csecuritydesccsecuritydesc"></a><a name="csecuritydesc"></a>C보안데스크::C보안데스

생성자입니다.

```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
새 `CSecurityDesc` `CSecurityDesc` 개체에 할당할 개체 또는 `SECURITY_DESCRIPTOR` 구조입니다.

### <a name="remarks"></a>설명

객체는 `CSecurityDesc` 구조체 또는 이전에 `SECURITY_DESCRIPTOR` 정의된 `CSecurityDesc` 개체를 사용하여 선택적으로 만들 수 있습니다.

## <a name="csecuritydesccsecuritydesc"></a><a name="dtor"></a>CSecurity데스크::~CSecurity데스크

소멸자입니다.

```
virtual ~CSecurityDesc() throw();
```

### <a name="remarks"></a>설명

소멸자는 할당된 모든 리소스를 해제합니다.

## <a name="csecuritydescfromstring"></a><a name="fromstring"></a>C보안데스크::FromString

문자열 형식 보안 설명자는 유효한 기능 보안 설명자로 변환합니다.

```
bool FromString(LPCTSTR pstr) throw(...);
```

### <a name="parameters"></a>매개 변수

*pstr*<br/>
변환할 [문자열 형식 보안 설명자가](/windows/win32/SecAuthZ/security-descriptor-string-format) 포함된 null-terminateed 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 대한 진실을 반환합니다. 실패시 예외를 throw합니다.

### <a name="remarks"></a>설명

문자열은 [CSecurityDesc::ToString](#tostring)을 사용하여 만들 수 있습니다. 보안 설명기를 문자열로 변환하면 저장 및 전송이 더 쉬워집니다.

이 메서드는 [변환스트링보안스크립트를 호출합니다.](/windows/win32/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptorw)

## <a name="csecuritydescgetcontrol"></a><a name="getcontrol"></a>C보안데스크::GetControl

보안 설명자에서 제어 정보를 검색합니다.

```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```

### <a name="parameters"></a>매개 변수

*psdc*<br/>
보안 설명자의 제어 정보를 받는 `SECURITY_DESCRIPTOR_CONTROL` 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 false를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 [GetSecurity 설명자 제어를](/windows/win32/api/securitybaseapi/nf-securitybaseapi-getsecuritydescriptorcontrol)호출합니다.

## <a name="csecuritydescgetdacl"></a><a name="getdacl"></a>CSecurityDesc::GetDacl

보안 설명자에서 임의 액세스 제어 목록(DACL) 정보를 검색합니다.

```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pDacl*<br/>
보안 설명자의 DACL 복사본을 저장할 `CDacl` 구조에 대한 포인터입니다. 임의 ACL이 있는 경우 메서드는 보안 설명자의 임의 ACL 주소로 *pDacl을* 설정합니다. 임의 ACL이 없으면 값이 저장되지 않습니다.

*pb현재*<br/>
지정된 보안 설명자에서 임의 ACL이 있음을 나타내는 값을 나타냅니다. 보안 설명자가 임의 ACL을 포함하는 경우 이 매개 변수는 true로 설정됩니다. 보안 설명자가 임의 ACL을 포함하지 않는 경우 이 매개 변수는 false로 설정됩니다.

*pbDefaulted*<br/>
보안 설명자에 대한 임의 ACL이 `SECURITY_DESCRIPTOR_CONTROL` 있는 경우 구조체에서 SE_DACL_DEFAULTED 플래그 값으로 설정된 플래그에 대한 포인터입니다. 이 플래그가 true이면 임의 ACL이 기본 메커니즘에 의해 검색되었습니다. false이면 임의 ACL이 사용자가 명시적으로 지정했습니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 false를 반환합니다.

## <a name="csecuritydescgetgroup"></a><a name="getgroup"></a>C보안데스크::겟그룹

보안 설명자에서 기본 그룹 정보를 검색합니다.

```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p시드 (것)와 함께*<br/>
CDacl에 저장된 그룹의 복사본을 받는 [CSid(보안](../../atl/reference/csid-class.md) 식별자)에 대한 포인터입니다.

*pbDefaulted*<br/>
메서드가 반환될 때 `SECURITY_DESCRIPTOR_CONTROL` 구조에서 SE_GROUP_DEFAULTED 플래그 값으로 설정된 플래그에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 false를 반환합니다.

## <a name="csecuritydescgetowner"></a><a name="getowner"></a>CSecurityDesc::GetOwner

보안 설명자에서 소유자 정보 형식을 검색합니다.

```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p시드 (것)와 함께*<br/>
CDacl에 저장된 그룹의 복사본을 받는 [CSid(보안](../../atl/reference/csid-class.md) 식별자)에 대한 포인터입니다.

*pbDefaulted*<br/>
메서드가 반환될 때 `SECURITY_DESCRIPTOR_CONTROL` 구조에서 SE_OWNER_DEFAULTED 플래그 값으로 설정된 플래그에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 false를 반환합니다.

## <a name="csecuritydescgetpsecurity_descriptor"></a><a name="getpsecurity_descriptor"></a>C보안데스크::GetPSECURITY_DESCRIPTOR

구조에 대한 `SECURITY_DESCRIPTOR` 포인터를 반환합니다.

```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```

### <a name="return-value"></a>Return Value

[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor) 구조에 대한 포인터를 반환합니다.

## <a name="csecuritydescgetsacl"></a><a name="getsacl"></a>CSecurityDesc:::겟사클

보안 설명자에서 시스템 액세스 제어 목록(SACL) 정보를 검색합니다.

```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSacl*<br/>
보안 설명자의 SACL 복사본을 저장할 `CSacl` 구조에 대한 포인터입니다. 시스템 ACL이 있는 경우 메서드는 보안 설명자의 시스템 ACL 주소로 *pSacl을* 설정합니다. 시스템 ACL이 없으면 값이 저장되지 않습니다.

*pb현재*<br/>
플래그에 대한 포인터 메서드는 지정된 보안 설명자에서 시스템 ACL의 존재를 나타냅니다. 보안 설명자가 시스템 ACL을 포함하는 경우 이 매개 변수는 true로 설정됩니다. 보안 설명자가 시스템 ACL을 포함하지 않는 경우 이 매개 변수는 false로 설정됩니다.

*pbDefaulted*<br/>
보안 설명자에 대한 시스템 ACL이 `SECURITY_DESCRIPTOR_CONTROL` 있는 경우 구조의 SE_SACL_DEFAULTED 플래그 값으로 설정된 플래그에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 false를 반환합니다.

## <a name="csecuritydescisdaclautoinherited"></a><a name="isdaclautoinherited"></a>CSecurityDesc::IsDaclAuto상속

임의 액세스 제어 목록(DACL)이 자동 전파를 지원하도록 구성되었는지 확인합니다.

```
bool IsDaclAutoInherited() const throw();
```

### <a name="return-value"></a>Return Value

보안 설명자가 기존 자식 개체에 상속 가능한 액세스 제어 항목(AEs)의 자동 전파를 지원하도록 설정된 DACL을 포함하는 경우 true를 반환합니다. 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

시스템은 개체 및 기존 자식 개체에 대한 자동 상속 알고리즘을 수행할 때 이 비트를 설정합니다.

## <a name="csecuritydescisdacldefaulted"></a><a name="isdacldefaulted"></a>C보안데스크::이스다클디폴드

보안 설명자가 기본 임의 액세스 제어 목록(DACL)으로 구성되는지 여부를 결정합니다.

```
bool IsDaclDefaulted() const throw();
```

### <a name="return-value"></a>Return Value

보안 설명자가 기본 DACL을 포함하는 경우 true를 반환합니다.

### <a name="remarks"></a>설명

이 플래그는 ACE(액세스 제어 항목) 상속과 관련하여 시스템이 DACL을 처리하는 방법에 영향을 줄 수 있습니다. 예를 들어 개체 작성자가 DACL을 지정하지 않으면 개체는 작성자의 액세스 토큰에서 기본 DACL을 받습니다. SE_DACL_PRESENT 플래그가 설정되지 않은 경우 시스템에서 이 플래그를 무시합니다.

이 플래그는 개체의 최종 DACL을 계산하는 방법을 결정하는 데 사용되며 보안 개체의 보안 설명자 컨트롤에 물리적으로 저장되지 않습니다.

이 플래그를 설정하려면 [CSecurityDesc::SetDacl](#setdacl) 메서드를 사용합니다.

## <a name="csecuritydescisdaclpresent"></a><a name="isdaclpresent"></a>CSecurityDesc::이스다클 현재

보안 설명자가 임의 액세스 제어 목록(DACL)을 포함하는지 여부를 결정합니다.

```
bool IsDaclPresent() const throw();
```

### <a name="return-value"></a>Return Value

보안 설명자가 DACL을 포함하는 경우 true를 반환합니다.

### <a name="remarks"></a>설명

이 플래그가 설정되지 않았거나 이 플래그가 설정되고 DACL이 NULL인 경우 보안 설명자는 모든 사람에게 전체 액세스를 허용합니다.

이 플래그는 보안 설명자가 보안 개체와 연결될 때까지 호출자가 지정한 보안 정보를 보유하는 데 사용됩니다. 보안 설명자가 보안 개체와 연결되면 SE_DACL_PRESENT 플래그는 항상 보안 설명자 컨트롤에 설정됩니다.

이 플래그를 설정하려면 [CSecurityDesc::SetDacl](#setdacl) 메서드를 사용합니다.

## <a name="csecuritydescisdaclprotected"></a><a name="isdaclprotected"></a>CSecurityDesc:::IsDaclprotected

임의 액세스 제어 목록(DACL)이 수정을 방지하도록 구성되었는지 확인합니다.

```
bool IsDaclProtected() const throw();
```

### <a name="return-value"></a>Return Value

상속 가능한 액세스 제어 항목(AEs)에 의해 보안 설명자가 수정되지 않도록 DACL이 구성된 경우 true를 반환합니다. 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

이 플래그를 설정하려면 [CSecurityDesc::SetDacl](#setdacl) 메서드를 사용합니다.

이 메서드는 상속 가능한 AEs의 자동 전파를 지원합니다.

## <a name="csecuritydescisgroupdefaulted"></a><a name="isgroupdefaulted"></a>C보안데스크::IsGroup기본

보안 설명자의 그룹 보안 식별자(SID)가 기본적으로 설정되었는지 확인합니다.

```
bool IsGroupDefaulted() const throw();
```

### <a name="return-value"></a>Return Value

보안 설명자의 그룹 SID를 제공한 보안 설명자의 원래 공급자가 아닌 기본 메커니즘이 true를 반환합니다. 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

이 플래그를 설정하려면 [CSecurityDesc::SetGroup](#setgroup) 메서드를 사용합니다.

## <a name="csecuritydescisownerdefaulted"></a><a name="isownerdefaulted"></a>C보안데스크::IsOwner기본

보안 설명자의 소유자 보안 식별자(SID)가 기본적으로 설정되었는지 확인합니다.

```
bool IsOwnerDefaulted() const throw();
```

### <a name="return-value"></a>Return Value

보안 설명자의 소유자 SID를 제공한 보안 설명자의 원래 공급자가 아닌 기본 메커니즘이 true를 반환합니다. 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

이 플래그를 설정하려면 [CSecurityDesc::SetOwner](#setowner) 메서드를 사용합니다.

## <a name="csecuritydescissaclautoinherited"></a><a name="issaclautoinherited"></a>CSecurityDesc::IsSaclAuto상속

자동 전파를 지원하도록 시스템 액세스 제어 목록(SACL)이 구성되었는지 확인합니다.

```
bool IsSaclAutoInherited() const throw();
```

### <a name="return-value"></a>Return Value

보안 설명자가 기존 자식 개체에 상속 가능한 액세스 제어 항목(AEs)의 자동 전파를 지원하도록 설정된 SACL을 포함하는 경우 true를 반환합니다. 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

시스템은 개체 및 기존 자식 개체에 대한 자동 상속 알고리즘을 수행할 때 이 비트를 설정합니다.

## <a name="csecuritydescissacldefaulted"></a><a name="issacldefaulted"></a>C보안데스크::IsSaclDefaulted

보안 설명자가 기본 시스템 액세스 제어 목록(SACL)으로 구성되었는지 확인합니다.

```
bool IsSaclDefaulted() const throw();
```

### <a name="return-value"></a>Return Value

보안 설명자가 기본 SACL을 포함하는 경우 true를 반환합니다.

### <a name="remarks"></a>설명

이 플래그는 ACE(액세스 제어 항목) 상속과 관련하여 시스템이 SACL을 처리하는 방법에 영향을 줄 수 있습니다. SE_SACL_PRESENT 플래그가 설정되지 않은 경우 시스템에서 이 플래그를 무시합니다.

이 플래그를 설정하려면 [CSecurityDesc::SetSacl](#setsacl) 메서드를 사용합니다.

## <a name="csecuritydescissaclpresent"></a><a name="issaclpresent"></a>CSecurityDesc::IsSacl현재

보안 설명자가 시스템 액세스 제어 목록(SACL)을 포함하고 있는지 확인합니다.

```
bool IsSaclPresent() const throw();
```

### <a name="return-value"></a>Return Value

보안 설명자가 SACL을 포함하는 경우 true를 반환합니다.

### <a name="remarks"></a>설명

이 플래그를 설정하려면 [CSecurityDesc::SetSacl](#setsacl) 메서드를 사용합니다.

## <a name="csecuritydescissaclprotected"></a><a name="issaclprotected"></a>CSecurityDesc:::IsSaclprotected

시스템 액세스 제어 목록(SACL)이 수정을 방지하도록 구성되었는지 확인합니다.

```
bool IsSaclProtected() const throw();
```

### <a name="return-value"></a>Return Value

SACL이 상속 가능한 액세스 제어 항목(AEs)에 의해 수정되지 않도록 보안 설명자가 구성된 경우 true를 반환합니다. 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

이 플래그를 설정하려면 [CSecurityDesc::SetSacl](#setsacl) 메서드를 사용합니다.

이 메서드는 상속 가능한 AEs의 자동 전파를 지원합니다.

## <a name="csecuritydescisselfrelative"></a><a name="isselfrelative"></a>CSecurityDesc::IsSelf상대

보안 설명자가 자체 상대 형식인지 확인합니다.

```
bool IsSelfRelative() const throw();
```

### <a name="return-value"></a>Return Value

연속된 메모리 블록에 있는 모든 보안 정보가 있는 자체 상대 형식인 경우 true를 반환합니다. 보안 설명자가 절대 형식인 경우 false를 반환합니다. 자세한 내용은 [절대 및 자기 상대 보안 설명자](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors)를 참조하십시오.

## <a name="csecuritydescmakeabsolute"></a><a name="makeabsolute"></a>C보안데스크::메이크Absolute

이 메서드를 호출하여 보안 설명기를 절대 형식으로 변환합니다.

```
bool MakeAbsolute() throw(...);
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 true를 반환합니다.

### <a name="remarks"></a>설명

절대 형식의 보안 설명자는 정보 자체가 아니라 포함된 정보에 대한 포인터를 포함합니다. 자기 상대 형식의 보안 설명자는 연속된 메모리 블록에 있는 정보를 포함합니다. 자기 상대적 보안 설명자에서 `SECURITY_DESCRIPTOR` 구조는 항상 정보를 시작하지만 보안 설명자의 다른 구성 요소는 순서에 따라 구조를 따를 수 있습니다. 메모리 주소를 사용하는 대신 자체 상대 보안 설명자의 구성 요소는 보안 설명자의 시작 부분에서 오프셋으로 식별됩니다. 이 형식은 보안 설명자를 디스크에 저장하거나 통신 프로토콜을 통해 전송해야 하는 경우에 유용합니다. 자세한 내용은 [절대 및 자기 상대 보안 설명자](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors)를 참조하십시오.

## <a name="csecuritydescmakeselfrelative"></a><a name="makeselfrelative"></a>CSecurityDesc:::자기 친척 만들기

이 메서드를 호출하여 보안 설명기를 자체 상대 형식으로 변환합니다.

```
bool MakeSelfRelative() throw(...);
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 true를 반환합니다.

### <a name="remarks"></a>설명

절대 형식의 보안 설명자는 정보 자체를 포함하는 대신 포함된 정보에 대한 포인터를 포함합니다. 자기 상대 형식의 보안 설명자는 연속된 메모리 블록에 있는 정보를 포함합니다. 자기 상대적 보안 설명자에서 `SECURITY_DESCRIPTOR` 구조는 항상 정보를 시작하지만 보안 설명자의 다른 구성 요소는 순서에 따라 구조를 따를 수 있습니다. 메모리 주소를 사용하는 대신 보안 설명자의 구성 요소는 보안 설명자의 시작 부분에서 오프셋으로 식별됩니다. 이 형식은 보안 설명자를 디스크에 저장하거나 통신 프로토콜을 통해 전송해야 하는 경우에 유용합니다. 자세한 내용은 [절대 및 자기 상대 보안 설명자](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors)를 참조하십시오.

## <a name="csecuritydescoperator-"></a><a name="operator_eq"></a>C보안데스크::연산자 =

대입 연산자입니다.

```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
개체에 `SECURITY_DESCRIPTOR` `CSecurityDesc` 할당할 구조 또는 `CSecurityDesc` 개체입니다.

### <a name="return-value"></a>Return Value

업데이트된 `CSecurityDesc` 개체를 반환합니다.

## <a name="csecuritydescoperator-const-security_descriptor-"></a><a name="operator_const_security_descriptor__star"></a>CSecurityDesc::연산자 const SECURITY_DESCRIPTOR *

값을 구조에 대한 포인터에 `SECURITY_DESCRIPTOR` 캐스팅합니다.

```
operator const SECURITY_DESCRIPTOR *() const throw();
```

## <a name="csecuritydescsetcontrol"></a><a name="setcontrol"></a>C보안데스크::세트컨트롤

보안 설명자의 제어 비트를 설정합니다.

```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest,
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```

### <a name="parameters"></a>매개 변수

*컨트롤비트오브이자*<br/>
설정하려는 제어 비트를 나타내는 SECURITY_DESCRIPTOR_CONTROL 마스크입니다. 설정할 수 있는 플래그 목록은 [SetSecurity설명사 제어를](/windows/win32/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol)참조하십시오.

*컨트롤비트토셋*<br/>
*ControlBitsOfInterest* 마스크에 의해 지정된 컨트롤 비트에 대한 새 값을 나타내는 SECURITY_DESCRIPTOR_CONTROL 마스크입니다. 이 매개 변수는 *ControlBitsOfInterest* 매개 변수에 대해 나열된 플래그의 조합일 수 있습니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 [SetSecurity설명자 제어를](/windows/win32/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol)호출합니다.

## <a name="csecuritydescsetdacl"></a><a name="setdacl"></a>CSecurityDesc:::세다클

임의 액세스 제어 목록(DACL)에 정보를 설정합니다. DACL이 보안 설명자에 이미 있으면 대체됩니다.

```
inline void SetDacl(
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>매개 변수

*Dacl*<br/>
보안 설명자에 대한 DACL을 지정하는 `CDacl` 개체를 참조합니다. 이 매개 변수는 NULL이 아니어야 합니다. 보안 설명자에서 NULL DACL을 설정하려면 메서드의 첫 번째 형식을 *bPresent* 집합을 false로 사용하여야 합니다.

*b 현재 현황*<br/>
보안 설명자에 DACL이 있음을 나타내는 플래그를 지정합니다. 이 매개 변수가 true이면 메서드는 `SECURITY_DESCRIPTOR_CONTROL` 구조에서 SE_DACL_PRESENT 플래그를 설정하고 *Dacl* 및 *bDefaulted* 매개 변수의 값을 사용합니다. false이면 메서드가 SE_DACL_PRESENT 플래그를 지우고 *bDefaulted는* 무시됩니다.

*b기본*<br/>
DACL의 소스를 나타내는 플래그를 지정합니다. 이 플래그가 true이면 DACL이 일부 기본 메커니즘에 의해 검색되었습니다. false이면 사용자가 DACL을 명시적으로 지정했습니다. 메서드는 이 값을 구조체의 `SECURITY_DESCRIPTOR_CONTROL` SE_DACL_DEFAULTED 플래그에 저장합니다. 이 매개 변수를 지정하지 않으면 SE_DACL_DEFAULTED 플래그가 지워집니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="remarks"></a>설명

빈 DACL과 존재하지 않는 DACL 사이에는 중요한 차이점이 있습니다. DACL이 비어 있으면 액세스 제어 항목이 없으며 액세스 권한이 명시적으로 부여되지 않습니다. 따라서 개체에 대한 액세스가 암시적으로 거부됩니다. 반면 개체에 DACL이 없는 경우 개체에 보호가 할당되지 않으며 액세스 요청이 부여됩니다.

## <a name="csecuritydescsetgroup"></a><a name="setgroup"></a>C보안데스크::세트그룹

절대 형식 보안 설명자의 기본 그룹 정보를 설정하여 이미 있는 기본 그룹 정보를 대체합니다.

```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>매개 변수

*Sid*<br/>
보안 설명자의 새 기본 그룹에 대한 [CSid](../../atl/reference/csid-class.md) 개체를 참조합니다. 이 매개 변수는 NULL이 아니어야 합니다. 보안 설명자는 DACL 또는 SACL이 없는 것으로 표시할 수 있지만 그룹과 소유자가 있어야 하며, 심지어 NULL SID(특별한 의미가 있는 기본 제공 SID)도 있어야 합니다.

*b기본*<br/>
기본 그룹 정보가 기본 메커니즘에서 파생되었는지 여부를 나타냅니다. 이 값이 true이면 기본 정보이며 메서드는 이 값을 `SECURITY_DESCRIPTOR_CONTROL` 구조의 SE_GROUP_DEFAULTED 플래그로 저장합니다. 이 매개변수가 0이면 SE_GROUP_DEFAULTED 플래그가 지워집니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

## <a name="csecuritydescsetowner"></a><a name="setowner"></a>C보안데스크::세트 오너

절대 형식 보안 설명자의 소유자 정보를 설정합니다. 이미 있는 소유자 정보를 대체합니다.

```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>매개 변수

*Sid*<br/>
보안 설명자의 새 주 소유자에 대 한 [CSid](../../atl/reference/csid-class.md) 개체입니다. 이 매개 변수는 NULL이 아니어야 합니다.

*b기본*<br/>
소유자 정보가 기본 메커니즘에서 파생되는지 여부를 나타냅니다. 이 값이 true이면 기본 정보입니다. 메서드는 이 값을 구조체의 `SECURITY_DESCRIPTOR_CONTROL` SE_OWNER_DEFAULTED 플래그로 저장합니다. 이 매개변수가 0이면 SE_OWNER_DEFAULTED 플래그가 지워집니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

## <a name="csecuritydescsetsacl"></a><a name="setsacl"></a>CSecurityDesc:::세사클

시스템 액세스 제어 목록(SACL)에 정보를 설정합니다. SACL이 보안 설명자에 이미 있으면 대체됩니다.

```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>매개 변수

*Sacl*<br/>
보안 설명자에 대한 SACL을 지정하는 `CSacl` 개체에 대한 포인터입니다. 이 매개 변수는 NULL이 아니어야 하며 CSacl 개체여야 합니다. DACL과 달리 SACL 개체는 액세스 권한을 지정하지 않고 정보만 감사하므로 NULL과 빈 SACL 간에는 차이가 없습니다.

*b기본*<br/>
SACL의 소스를 나타내는 플래그를 지정합니다. 이 플래그가 true이면 SACL이 일부 기본 메커니즘에 의해 검색되었습니다. false이면 사용자가 SACL을 명시적으로 지정했습니다. 메서드는 이 값을 구조체의 `SECURITY_DESCRIPTOR_CONTROL` SE_SACL_DEFAULTED 플래그에 저장합니다. 이 매개 변수를 지정하지 않으면 SE_SACL_DEFAULTED 플래그가 지워집니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

## <a name="csecuritydesctostring"></a><a name="tostring"></a>CSecurityDesc:::토스트링

보안 설명기를 문자열 형식으로 변환합니다.

```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pstr*<br/>
[문자열 형식 보안 설명기를](/windows/win32/SecAuthZ/security-descriptor-string-format)받을 null-종료 된 문자열에 대 한 포인터입니다.

*Si*<br/>
SECURITY_INFORMATION 비트 플래그조합을 지정하여 출력 문자열에 포함할 보안 설명자의 구성 요소를 나타냅니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="remarks"></a>설명

보안 설명자가 문자열 형식으로 지정되면 더 쉽게 저장하거나 전송할 수 있습니다. 메서드를 `CSecurityDesc::FromString` 사용하여 문자열을 다시 보안 설명자로 변환합니다.

*si* 매개 변수에는 다음과 같은 SECURITY_INFORMATION 플래그가 포함될 수 있습니다.

|값|의미|
|-----------|-------------|
|OWNER_SECURITY_INFORMATION|소유자를 포함합니다.|
|GROUP_SECURITY_INFORMATION|기본 그룹을 포함합니다.|
|DACL_SECURITY_INFORMATION|DACL을 포함합니다.|
|SACL_SECURITY_INFORMATION|SACL을 포함합니다.|

DACL이 NULL이고 SE_DACL_PRESENT 컨트롤 비트가 입력 보안 설명자에서 설정된 경우 메서드가 실패합니다.

DACL이 NULL이고 SE_DACL_PRESENT 컨트롤 비트가 입력 보안 설명자에서 설정되지 않은 경우 결과 보안 설명자 문자열에는 D: 구성 요소가 없습니다. 자세한 내용은 [보안 설명자 문자열 형식을](/windows/win32/SecAuthZ/security-descriptor-string-format) 참조하십시오.

이 메서드는 [변환스트링보안스크립트를 호출합니다.](/windows/win32/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptorw)

## <a name="see-also"></a>참고 항목

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 글로벌 기능](../../atl/reference/security-global-functions.md)
