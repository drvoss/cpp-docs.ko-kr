---
title: CAcl 클래스
ms.date: 11/04/2016
f1_keywords:
- CAcl
- ATLSECURITY/ATL::CAcl
- ATLSECURITY/ATL::CAcl::CAccessMaskArray
- ATLSECURITY/ATL::CAcl::CAceFlagArray
- ATLSECURITY/ATL::CAcl::CAceTypeArray
- ATLSECURITY/ATL::CAcl::CAcl
- ATLSECURITY/ATL::CAcl::GetAceCount
- ATLSECURITY/ATL::CAcl::GetAclEntries
- ATLSECURITY/ATL::CAcl::GetAclEntry
- ATLSECURITY/ATL::CAcl::GetLength
- ATLSECURITY/ATL::CAcl::GetPACL
- ATLSECURITY/ATL::CAcl::IsEmpty
- ATLSECURITY/ATL::CAcl::IsNull
- ATLSECURITY/ATL::CAcl::RemoveAce
- ATLSECURITY/ATL::CAcl::RemoveAces
- ATLSECURITY/ATL::CAcl::SetEmpty
- ATLSECURITY/ATL::CAcl::SetNull
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
ms.openlocfilehash: 5d03154597f800042846e82d0a0cf5e7c46b613f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864907"
---
# <a name="cacl-class"></a>CAcl 클래스

이 클래스는 `ACL` (액세스 제어 목록) 구조체에 대 한 래퍼입니다.

> [!IMPORTANT]
>  이 클래스와 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAcl
```

## <a name="members"></a>구성원

### <a name="public-typedefs"></a>공용 형식 정의

|속성|Description|
|----------|-----------------|
|[CAcl:: CAccessMaskArray](#caccessmaskarray)|ACCESS_MASKs의 배열입니다.|
|[CAcl:: CAceFlagArray](#caceflagarray)|바이트 배열입니다.|
|[CAcl:: Cac? 배열](#cacetypearray)|바이트 배열입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAcl:: CAcl](#cacl)|생성자입니다.|
|[CAcl:: ~ CAcl](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAcl:: GetAceCount](#getacecount)|ACE (액세스 제어 항목) 개체의 수를 반환 합니다.|
|[CAcl:: GetAclEntries](#getaclentries)|`CAcl` 개체에서 ACL (액세스 제어 목록) 항목을 검색 합니다.|
|[CAcl:: GetAclEntry](#getaclentry)|`CAcl` 개체의 항목에 대 한 모든 정보를 검색 합니다.|
|[CAcl:: GetLength](#getlength)|ACL의 길이를 반환 합니다.|
|[CAcl:: GetPACL](#getpacl)|패키지 (ACL에 대 한 포인터)를 반환 합니다.|
|[CAcl:: IsEmpty](#isempty)|항목에 대 한 `CAcl` 개체를 테스트 합니다.|
|[CAcl:: IsNull](#isnull)|`CAcl` 개체의 상태를 반환 합니다.|
|[CAcl:: RemoveAce](#removeace)|`CAcl` 개체에서 특정 ACE (액세스 제어 항목)를 제거 합니다.|
|[CAcl:: RemoveAces](#removeaces)|지정 된 `CSid`에 적용 되는 `CAcl`에서 모든 Ace (액세스 제어 항목)를 제거 합니다.|
|[CAcl:: SetEmpty](#setempty)|`CAcl` 개체를 비어 있는 것으로 표시 합니다.|
|[CAcl:: SetNull](#setnull)|`CAcl` 개체를 NULL로 표시 합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CAcl:: operator const ACL *](#operator_const_acl__star)|`ACL` 구조체로 `CAcl` 개체를 캐스팅 합니다.|
|[CAcl:: operator =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

`ACL` 구조체는 ACL (액세스 제어 목록)의 헤더입니다. ACL에는 0 개 이상의 [ace](/windows/win32/SecAuthZ/access-control-entries) (액세스 제어 항목)의 순차적 목록이 포함 됩니다. ACL의 개별 Ace 번호는 0에서 *n-1*사이입니다. 여기서 *n* 은 acl의 ace 수입니다. ACL을 편집 하는 경우 응용 프로그램은 해당 인덱스에 의해 ACL 내에서 ACE (액세스 제어 항목)를 참조 합니다.

ACL에는 두 가지 유형이 있습니다.

- 임의

- 시스템

임의 ACL은 개체의 소유자 또는 개체에 대 한 액세스 WRITE_DAC 부여 된 모든 사용자가 제어 합니다. 특정 사용자와 그룹이 개체에 대해 가질 수 있는 액세스를 지정 합니다. 예를 들어 파일 소유자는 임의의 ACL을 사용 하 여 파일에 액세스할 수 있는 사용자 및 그룹을 제어할 수 있습니다.

또한 개체에는 시스템 관리자가 제어 하는 시스템 ACL의 형태로 시스템 수준 보안 정보를 연결할 수 있습니다. 시스템 ACL을 통해 시스템 관리자는 개체에 대 한 액세스 시도를 감사할 수 있습니다.

자세한 내용은 Windows SDK [ACL](/windows/win32/SecAuthZ/access-control-lists) 토론을 참조 하십시오.

Windows의 액세스 제어 모델에 대 한 소개는 Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) 를 참조 하세요.

## <a name="requirements"></a>요구 사항

**헤더:.**

##  <a name="caccessmaskarray"></a>CAcl:: CAccessMaskArray

ACCESS_MASK 개체의 배열입니다.

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>설명

이 typedef는 Ace (액세스 제어 항목)에 사용 되는 액세스 권한을 저장 하는 데 사용할 수 있는 배열 형식을 지정 합니다.

##  <a name="caceflagarray"></a>CAcl:: CAceFlagArray

바이트 배열입니다.

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>설명

이 typedef는 ACE (액세스 제어 항목) 유형별 컨트롤 플래그를 정의 하는 데 사용 되는 배열 형식을 지정 합니다. 가능한 플래그의 전체 목록은 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 정의를 참조 하세요.

##  <a name="cacetypearray"></a>CAcl:: Cac? 배열

바이트 배열입니다.

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>설명

이 typedef는 ACCESS_ALLOWED_ACE_TYPE 또는 ACCESS_DENIED_ACE_TYPE와 같은 ACE (액세스 제어 항목) 개체의 특성을 정의 하는 데 사용 되는 배열 형식을 지정 합니다. 가능한 형식의 전체 목록은 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 정의를 참조 하세요.

##  <a name="cacl"></a>CAcl:: CAcl

생성자입니다.

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존 `CAcl` 개체입니다.

### <a name="remarks"></a>설명

`CAcl` 개체는 기존 `CAcl` 개체를 사용 하 여 선택적으로 만들 수 있습니다.

##  <a name="dtor"></a>CAcl:: ~ CAcl

소멸자입니다.

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>설명

소멸자는 개체에서 획득 한 모든 리소스를 해제 합니다.

##  <a name="getacecount"></a>CAcl:: GetAceCount

ACE (액세스 제어 항목) 개체의 수를 반환 합니다.

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>Return Value

`CAcl` 개체의 ACE 항목 수를 반환 합니다.

##  <a name="getaclentries"></a>CAcl:: GetAclEntries

`CAcl` 개체에서 ACL (액세스 제어 목록) 항목을 검색 합니다.

```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSids*<br/>
[CSid](../../atl/reference/csid-class.md) 개체의 배열에 대 한 포인터입니다.

*pAccessMasks*<br/>
액세스 마스크입니다.

*pAceTypes*<br/>
ACE (액세스 제어 항목) 형식입니다.

*pAceFlags*<br/>
ACE 플래그입니다.

### <a name="remarks"></a>설명

이 메서드는 `CAcl` 개체에 포함 된 모든 ACE 개체의 세부 정보를 사용 하 여 배열 매개 변수를 채웁니다. 특정 배열에 대 한 세부 정보가 필요 하지 않으면 NULL을 사용 합니다.

각 배열의 내용은 서로 일치 합니다. 즉, `CAccessMaskArray` 배열의 첫 번째 요소는 `CSidArray` 배열의 첫 번째 요소에 해당 합니다.

ACE 형식 및 플래그에 대 한 자세한 내용은 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 를 참조 하세요.

##  <a name="getaclentry"></a>CAcl:: GetAclEntry

ACL (액세스 제어 목록)에서 항목에 대 한 모든 정보를 검색 합니다.

```
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
검색할 ACL 항목의 인덱스입니다.

*pSid*<br/>
ACL 항목이 적용 되는 [CSid](../../atl/reference/csid-class.md) 개체입니다.

*pMask*<br/>
액세스를 허용 하거나 거부할 수 있는 사용 권한을 지정 하는 마스크입니다.

*pType*<br/>
ACE 형식입니다.

*pFlags*<br/>
ACE 플래그입니다.

*pObjectType*<br/>
개체 유형입니다. ACE에 개체 형식이 지정 되지 않은 경우 또는 ACE가 개체 ACE가 아닌 경우이 GUID_NULL로 설정 됩니다.

*pInheritedObjectType*<br/>
상속 된 개체 유형입니다. 상속 된 개체 형식이 ACE에 지정 되지 않은 경우 또는 ACE가 개체 ACE가 아닌 경우에는 GUID_NULL로 설정 됩니다.

### <a name="remarks"></a>설명

이 메서드는 개별 ACE에 대 한 모든 정보를 검색 하 고 [Cacl:: GetAclEntries](#getaclentries) 를 사용 가능 하 게 설정 하는 것 보다 많은 정보를 제공 합니다.

ACE 형식 및 플래그에 대 한 자세한 내용은 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 를 참조 하세요.

##  <a name="getlength"></a>CAcl:: GetLength

ACL (액세스 제어 목록)의 길이를 반환 합니다.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Return Value

`ACL` 구조체를 보유 하는 데 필요한 길이 (바이트)를 반환 합니다.

##  <a name="getpacl"></a>CAcl:: GetPACL

ACL (액세스 제어 목록)에 대 한 포인터를 반환 합니다.

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>Return Value

`ACL` 구조체에 대 한 포인터를 반환 합니다.

##  <a name="isempty"></a>CAcl:: IsEmpty

항목에 대 한 `CAcl` 개체를 테스트 합니다.

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>설명

`CAcl` 개체가 NULL이 아니고 항목을 포함 하지 않는 경우 TRUE를 반환 합니다. `CAcl` 개체가 NULL 이거나 하나 이상의 항목을 포함 하는 경우 FALSE를 반환 합니다.

##  <a name="isnull"></a>CAcl:: IsNull

`CAcl` 개체의 상태를 반환 합니다.

```
bool IsNull() const throw();
```

### <a name="return-value"></a>Return Value

`CAcl` 개체가 NULL 이면 TRUE, 그렇지 않으면 FALSE를 반환 합니다.

##  <a name="operator_const_acl__star"></a>CAcl:: operator const ACL *

`CAcl` 개체를 `ACL` (access control 목록) 구조체로 캐스팅 합니다.

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>설명

`ACL` 구조체의 주소를 반환 합니다.

##  <a name="operator_eq"></a>CAcl:: operator =

대입 연산자입니다.

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존 개체에 할당할 `CAcl`입니다.

### <a name="return-value"></a>Return Value

업데이트 된 `CAcl` 개체에 대 한 참조를 반환 합니다.

##  <a name="removeace"></a>CAcl:: RemoveAce

`CAcl` 개체에서 특정 ACE (액세스 제어 항목)를 제거 합니다.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
제거할 ACE 항목의 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 [CAtlArray:: RemoveAt](../../atl/reference/catlarray-class.md#removeat)에서 파생 됩니다.

##  <a name="removeaces"></a>CAcl:: RemoveAces

지정 된 `CSid`에 적용 되는 `CAcl`에서 alls Ace (액세스 제어 항목)를 제거 합니다.

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
`CSid` 개체에 대한 참조입니다.

##  <a name="setempty"></a>CAcl:: SetEmpty

`CAcl` 개체를 비어 있는 것으로 표시 합니다.

```
void SetEmpty() throw();
```

### <a name="remarks"></a>설명

`CAcl`은 비어 있거나 NULL로 설정할 수 있습니다. 두 상태는 서로 다릅니다.

##  <a name="setnull"></a>CAcl:: SetNull

`CAcl` 개체를 NULL로 표시 합니다.

```
void SetNull() throw();
```

### <a name="remarks"></a>설명

`CAcl`은 비어 있거나 NULL로 설정할 수 있습니다. 두 상태는 서로 다릅니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 전역 함수](../../atl/reference/security-global-functions.md)
