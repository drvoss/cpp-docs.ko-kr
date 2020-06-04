---
title: CSid 클래스
ms.date: 03/27/2019
f1_keywords:
- CSid
- ATLSECURITY/ATL::CSid
- ATLSECURITY/ATL::CSid::CSidArray
- ATLSECURITY/ATL::CSid::CSid
- ATLSECURITY/ATL::CSid::AccountName
- ATLSECURITY/ATL::CSid::Domain
- ATLSECURITY/ATL::CSid::EqualPrefix
- ATLSECURITY/ATL::CSid::GetLength
- ATLSECURITY/ATL::CSid::GetPSID
- ATLSECURITY/ATL::CSid::GetPSID_IDENTIFIER_AUTHORITY
- ATLSECURITY/ATL::CSid::GetSubAuthority
- ATLSECURITY/ATL::CSid::GetSubAuthorityCount
- ATLSECURITY/ATL::CSid::IsValid
- ATLSECURITY/ATL::CSid::LoadAccount
- ATLSECURITY/ATL::CSid::Sid
- ATLSECURITY/ATL::CSid::SidNameUse
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
ms.openlocfilehash: 414cf428cebe8105d90b3add93cc7f1e76927c2a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330920"
---
# <a name="csid-class"></a>CSid 클래스

이 클래스는 `SID` (보안 식별자) 구조에 대 한 래퍼입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CSid
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[C시드:::C시드어레이](#csidarray)|`CSid` 개체의 배열|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C시드:::C시드](#csid)|생성자입니다.|
|[C시드::~C시드](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C시드::계정 이름](#accountname)|개체와 연결된 계정의 이름을 `CSid` 반환합니다.|
|[C시드::D오마인](#domain)|개체와 연결된 도메인의 이름을 `CSid` 반환합니다.|
|[C시드::등가픽](#equalprefix)|같음 테스트(보안 `SID` 식별자) 접두사입니다.|
|[C시드::GetLength](#getlength)|개체의 길이를 `CSid` 반환합니다.|
|[C시드::GetPSID](#getpsid)|구조에 대한 `SID` 포인터를 반환합니다.|
|[C시드::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|구조에 대한 `SID_IDENTIFIER_AUTHORITY` 포인터를 반환합니다.|
|[CSid::GetSubAuthority](#getsubauthority)|구조체에서 지정된 하위 `SID` 권한을 반환합니다.|
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|하위 기관 수를 반환합니다.|
|[C시드::유효합니다.](#isvalid)|개체의 `CSid` 유효성을 테스트합니다.|
|[CSid::로드 계정](#loadaccount)|계정 `CSid` 이름 및 도메인 또는 기존 `SID` 구조에 지정된 개체를 업데이트합니다.|
|[C시드::시드](#sid)|ID 문자열을 반환합니다.|
|[C시드::시드네임유즈](#sidnameuse)|개체의 상태에 대한 설명을 `CSid` 반환합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 =](#operator_eq)|대입 연산자입니다.|
|[연산자 const SID *](#operator_const_sid__star)|개체를 `CSid` 구조체에 대한 `SID` 포인터에 캐스팅합니다.|

### <a name="global-operators"></a>글로벌 오퍼레이터

|||
|-|-|
|[연산자 ==](#operator_eq_eq)|두 개의 보안 설명자 개체를 같음으로 테스트합니다.|
|[연산자 !=](#operator_neq)|두 개의 보안 설명자 개체를 테스트하여 부등값|
|[연산자\<](#operator_lt)|두 보안 설명자 개체의 상대 값을 비교합니다.|
|[연산자 >](#operator_gt)|두 보안 설명자 개체의 상대 값을 비교합니다.|
|[연산자\<=](#operator_lt__eq)|두 보안 설명자 개체의 상대 값을 비교합니다.|
|[연산자 >=](#operator_gt__eq)|두 보안 설명자 개체의 상대 값을 비교합니다.|

## <a name="remarks"></a>설명

구조는 `SID` 사용자 또는 그룹을 고유하게 식별하는 데 사용되는 가변 길이 구조입니다.

응용 프로그램은 `SID` 구조를 직접 수정하지 말고 이 래퍼 클래스에 제공된 메서드를 사용해야 합니다. 또한 [AtlGetOwnerSid,](security-global-functions.md#atlgetownersid) [AtlSetGroupSid,](security-global-functions.md#atlsetgroupsid) [AtlGetGroupSid](security-global-functions.md#atlgetgroupsid)및 [AtlSetOwnerSid를](security-global-functions.md#atlsetownersid)참조하십시오.

Windows의 액세스 제어 모델에 대한 자세한 내용은 Windows SDK의 [액세스 제어를](/windows/win32/SecAuthZ/access-control) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="csidaccountname"></a><a name="accountname"></a>C시드::계정 이름

개체와 연결된 계정의 이름을 `CSid` 반환합니다.

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>Return Value

계정 이름을 가리키는 LPCTSTR을 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 지정된 `SID` (보안 식별자)에 대 한 이름을 찾으려고 시도 합니다. 자세한 내용은 [조회계정 시드를](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw)참조하십시오.

에 대한 계정 `SID` 이름을 찾을 `AccountName` 수 없는 경우 빈 문자열을 반환합니다. 네트워크 시간 지정으로 인해 이 메서드가 이름을 찾을 수 없게 되는 경우에 이 이 가 발생할 수 있습니다. 로그인 세션을 식별하는 것과 같이 `SID` 해당 계정 이름이 없는 보안 식별자에 대해서도 발생합니다.

## <a name="csidcsid"></a><a name="csid"></a>C시드:::C시드

생성자입니다.

```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존 `CSid` 개체 `SID` 또는 (보안 식별자) 구조입니다.

*식별자 기관*<br/>
권한입니다.

*n서브기관카운트*<br/>
하위 권한 개수입니다.

*pszAccountName*<br/>
계정 이름입니다.

*psz시스템*<br/>
시스템 이름입니다. 이 문자열은 원격 컴퓨터의 이름일 수 있습니다. 이 문자열이 NULL이면 로컬 시스템이 대신 사용됩니다.

*p시드 (것)와 함께*<br/>
구조에 대한 `SID` 포인터입니다.

### <a name="remarks"></a>설명

생성자는 개체를 `CSid` 초기화하여 내부 데이터 멤버를 *SidTypeInvalid로*설정하거나 기존 에서 `CSid` `SID`설정을 복사하거나 기존 계정 또는 기존 계정에서 설정을 복사합니다.

초기화가 실패하면 생성자는 [CAtlException 클래스를](../../atl/reference/catlexception-class.md)throw합니다.

## <a name="csidcsid"></a><a name="dtor"></a>C시드::~C시드

소멸자입니다.

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>설명

소멸자는 개체에서 획득한 모든 리소스를 해제합니다.

## <a name="csidcsidarray"></a><a name="csidarray"></a>C시드:::C시드어레이

CSid 개체의 [배열입니다.](../../atl/reference/csid-class.md)

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>설명

이 typedef는 ACL(액세스 제어 목록)에서 보안 식별자를 검색하는 데 사용할 수 있는 배열 형식을 지정합니다. [참조 CAcl::GetAclEntry](../../atl/reference/cacl-class.md#getaclentries).

## <a name="csiddomain"></a><a name="domain"></a>C시드::D오마인

개체와 연결된 도메인의 이름을 `CSid` 반환합니다.

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>Return Value

도메인을 `LPCTSTR` 가리키는 것을 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 지정된 `SID` (보안 식별자)에 대 한 이름을 찾으려고 시도 합니다. 자세한 내용은 [조회계정 시드를](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw)참조하십시오.

에 대한 계정 `SID` 이름을 찾을 `Domain` 수 없는 경우 도메인을 빈 문자열로 반환합니다. 네트워크 시간 지정으로 인해 이 메서드가 이름을 찾을 수 없게 되는 경우에 이 이 가 발생할 수 있습니다. 로그인 세션을 식별하는 것과 같이 `SID` 해당 계정 이름이 없는 보안 식별자에 대해서도 발생합니다.

## <a name="csidequalprefix"></a><a name="equalprefix"></a>C시드::등가픽

같음 테스트(보안 `SID` 식별자) 접두사입니다.

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
`SID` 비교할(보안 식별자) `CSid` 구조또는 객체.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [EqualPrefixSid를](/windows/win32/api/securitybaseapi/nf-securitybaseapi-equalprefixsid) 참조하십시오.

## <a name="csidgetlength"></a><a name="getlength"></a>C시드::GetLength

개체의 길이를 `CSid` 반환합니다.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Return Value

개체의 바이트로 길이를 `CSid` 반환합니다.

### <a name="remarks"></a>설명

구조가 `CSid` 유효하지 않으면 반환 값이 정의되지 않습니다. 호출하기 `GetLength`전에 [CSid::IsValid](#isvalid) 멤버 함수를 `CSid` 사용하여 유효한지 확인합니다.

> [!NOTE]
> 디버그 빌드에서 함수는 개체가 유효하지 않은 경우 ASSERT를 `CSid` 발생시게 됩니다.

## <a name="csidgetpsid"></a><a name="getpsid"></a>C시드::GetPSID

(보안 식별자) 구조에 대 한 포인터를 `SID` 반환 합니다.

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>Return Value

`CSid` 개체의 기본 `SID` 구조의 주소를 반환합니다.

## <a name="csidgetpsid_identifier_authority"></a><a name="getpsid_identifier_authority"></a>C시드::GetPSID_IDENTIFIER_AUTHORITY

구조에 대한 `SID_IDENTIFIER_AUTHORITY` 포인터를 반환합니다.

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 구조체의 주소를 `SID_IDENTIFIER_AUTHORITY` 반환합니다. 실패하면 반환 값이 정의되지 않습니다. 개체가 `CSid` 유효하지 않은 경우 오류가 발생할 수 있으며, 이 경우 [CSid::IsValid](#isvalid) 메서드는 FALSE를 반환합니다. 확장 `GetLastError` 오류 정보에 대해 함수를 호출할 수 있습니다.

> [!NOTE]
> 디버그 빌드에서 함수는 개체가 유효하지 않은 경우 ASSERT를 `CSid` 발생시게 됩니다.

## <a name="csidgetsubauthority"></a><a name="getsubauthority"></a>CSid::GetSubAuthority

`SID` (보안 식별자) 구조에서 지정된 하위 기관을 반환합니다.

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>매개 변수

*n서브기관*<br/>
하위 기관입니다.

### <a name="return-value"></a>Return Value

*nSubAuthority에서* 참조하는 하위 권한을 반환합니다. 하위 기관 값은 상대 식별자(RID)입니다.

### <a name="remarks"></a>설명

*nSubAuthority* 매개 변수는 메서드가 반환할 하위 기관 배열 요소를 식별하는 인덱스 값을 지정합니다. 메서드는 이 값에 대한 유효성 검사 테스트를 수행하지 않습니다. 응용 프로그램은 [CSid::GetSubAuthorityCount를](#getsubauthoritycount) 호출하여 허용 가능한 값의 범위를 검색할 수 있습니다.

> [!NOTE]
> 디버그 빌드에서 함수는 개체가 유효하지 않은 경우 ASSERT를 `CSid` 발생시게 됩니다.

## <a name="csidgetsubauthoritycount"></a><a name="getsubauthoritycount"></a>CSid::GetSubAuthorityCount

하위 기관 수를 반환합니다.

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 반환 값은 하위 기관 수입니다.

메서드가 실패하면 반환 값이 정의되지 않습니다. 개체가 잘못되면 `CSid` 메서드가 실패합니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.

> [!NOTE]
> 디버그 빌드에서 함수는 개체가 유효하지 않은 경우 ASSERT를 `CSid` 발생시게 됩니다.

## <a name="csidisvalid"></a><a name="isvalid"></a>C시드::유효합니다.

개체의 `CSid` 유효성을 테스트합니다.

```
bool IsValid() const throw();
```

### <a name="return-value"></a>Return Value

개체가 유효한 `CSid` 경우 TRUE를 반환하고 FALSE가 아닌 경우 반환합니다. 이 메서드에 대 한 확장 된 오류 정보가 없습니다. 호출하지 `GetLastError`마십시오.

### <a name="remarks"></a>설명

이 `IsValid` 메서드는 `CSid` 개정 번호가 알려진 범위 내에 있는지, 하위 기관의 수가 최대값보다 작은지 확인하여 개체의 유효성을 검사합니다.

## <a name="csidloadaccount"></a><a name="loadaccount"></a>CSid::로드 계정

계정 `CSid` 이름 및 도메인 또는 기존 SID(보안 식별자) 구조에 지정된 개체를 업데이트합니다.

```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>매개 변수

*pszAccountName*<br/>
계정 이름입니다.

*psz시스템*<br/>
시스템 이름입니다. 이 문자열은 원격 컴퓨터의 이름일 수 있습니다. 이 문자열이 NULL이면 로컬 시스템이 대신 사용됩니다.

*p시드 (것)와 함께*<br/>
[SID](/windows/win32/api/winnt/ns-winnt-sid) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.

### <a name="remarks"></a>설명

`LoadAccount`지정된 이름에 대한 보안 식별자를 찾으려고 시도합니다. 자세한 내용은 [조회계정시드를](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw) 참조하십시오.

## <a name="csidoperator-"></a><a name="operator_eq"></a>CSid::연산자 =

대입 연산자입니다.

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
`SID` (보안 식별자) `CSid` 또는 개체에 `CSid` 할당합니다.

### <a name="return-value"></a>Return Value

업데이트된 `CSid` 개체에 대한 참조를 반환합니다.

## <a name="csidoperator-"></a><a name="operator_eq_eq"></a>CSid::연산자 ==

두 개의 보안 설명자 개체가 같음으로 테스트합니다.

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
== 연산자의 왼쪽에 나타나는 `SID` (보안 식별자) 또는 `CSid`

*rhs*<br/>
== 연산자의 오른쪽에 나타나는 `SID` (보안 식별자) `CSid`

### <a name="return-value"></a>Return Value

TRUE 보안 설명자가 같으면 FALSE입니다.

## <a name="csidoperator-"></a><a name="operator_neq"></a>CSid::연산자 !=

두 개의 보안 설명자 개체가 부등값에 대해 테스트합니다.

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
`SID` (보안 식별자) `CSid` 또는 != 연산자의 왼쪽에 나타납니다.

*rhs*<br/>
`SID` (보안 식별자) `CSid` 또는 != 연산자의 오른쪽에 나타납니다.

### <a name="return-value"></a>Return Value

TRUE 보안 설명자가 같지 않은 경우 TRUE, 그렇지 않으면 FALSE입니다.

## <a name="csidoperator-lt"></a><a name="operator_lt"></a>C시드::연산자&lt;

두 보안 설명자 개체의 상대 값을 비교합니다.

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
`SID` (보안 식별자) `CSid` 또는 != 연산자의 왼쪽에 나타납니다.

*rhs*<br/>
`SID` (보안 식별자) `CSid` 또는 != 연산자의 오른쪽에 나타납니다.

### <a name="return-value"></a>Return Value

*LHs가* *rhs보다*적으면 TRUE, 그렇지 않으면 FALSE.

## <a name="csidoperator-lt"></a><a name="operator_lt__eq"></a>C시드::연산자&lt;=

두 보안 설명자 개체의 상대 값을 비교합니다.

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
`SID` (보안 식별자) `CSid` 또는 != 연산자의 왼쪽에 나타납니다.

*rhs*<br/>
`SID` (보안 식별자) `CSid` 또는 != 연산자의 오른쪽에 나타납니다.

### <a name="return-value"></a>Return Value

*LHs가* *rhs보다*적거나 같으면 TRUE, 그렇지 않으면 FALSE.

## <a name="csidoperator-gt"></a><a name="operator_gt"></a>C시드::연산자&gt;

두 보안 설명자 개체의 상대 값을 비교합니다.

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
`SID` (보안 식별자) `CSid` 또는 != 연산자의 왼쪽에 나타납니다.

*rhs*<br/>
`SID` (보안 식별자) `CSid` 또는 != 연산자의 오른쪽에 나타납니다.

### <a name="return-value"></a>Return Value

*LHs가* *rhs보다*큰 경우 TRUE, 그렇지 않으면 FALSE.

## <a name="csidoperator-gt"></a><a name="operator_gt__eq"></a>C시드::연산자&gt;=

두 보안 설명자 개체의 상대 값을 비교합니다.

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
`SID` (보안 식별자) `CSid` 또는 != 연산자의 왼쪽에 나타납니다.

*rhs*<br/>
`SID` (보안 식별자) `CSid` 또는 != 연산자의 오른쪽에 나타납니다.

### <a name="return-value"></a>Return Value

*LHs가* *rhs보다*크거나 같으면 TRUE, 그렇지 않으면 FALSE입니다.

## <a name="csidoperator-const-sid-"></a><a name="operator_const_sid__star"></a>CSid::연산자 const SID\*

개체를 `CSid` `SID` (보안 식별자) 구조에 대한 포인터에 캐스팅합니다.

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>설명

구조의 주소를 `SID` 반환합니다.

## <a name="csidsid"></a><a name="sid"></a>C시드::시드

`SID` (보안 식별자) 구조를 문자열로 반환합니다.

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>Return Value

`SID` 구조를 표시, 저장 또는 전송에 적합한 형식으로 문자열로 반환합니다. [변환시드토스트링시드](/windows/win32/api/sddl/nf-sddl-convertsidtostringsidw).

## <a name="csidsidnameuse"></a><a name="sidnameuse"></a>C시드::시드네임유즈

개체의 상태에 대한 설명을 `CSid` 반환합니다.

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>Return Value

`CSid` 개체의 상태를 설명하는 값을 저장하는 데이터 멤버의 값을 반환합니다.

|값|Description|
|-----------|-----------------|
|시드 타입 유저|사용자(보안 `SID` 식별자)를 나타냅니다.|
|시드 타입 그룹|그룹을 `SID`나타냅니다.|
|시드 타입 도메인|도메인을 `SID`나타냅니다.|
|시드타이프알리아스|별칭을 `SID`나타냅니다.|
|시드타입알려진그룹|잘 `SID` 알려진 그룹에 대한 을 나타냅니다.|
|시드타입삭제계정|삭제된 `SID` 계정에 대한 을 나타냅니다.|
|시드 Type유효하지 않음|잘못되었습니다. `SID`|
|시드 유형 알 수 없음|알 수 `SID` 없는 형식을 나타냅니다.|
|시드 타입컴퓨터|컴퓨터에 `SID` 대한 을 나타냅니다.|

### <a name="remarks"></a>설명

[CSid::LoadAccount를](#loadaccount) 호출하여 `CSid` 해당 `SidNameUse` 상태를 반환하기 전에 개체를 업데이트합니다. `SidNameUse``LookupAccountName` (또는 `LookupAccountSid`호출하여) 개체의 상태를 변경하지 않지만 현재 상태만 반환합니다.

## <a name="see-also"></a>참고 항목

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 글로벌 기능](../../atl/reference/security-global-functions.md)<br/>
[연산자](../../atl/reference/atl-operators.md)
