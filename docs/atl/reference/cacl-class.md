---
title: 카클 클래스
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
ms.openlocfilehash: 458f7cd50462a145d005f3f81d87cc06fc7e01b1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748778"
---
# <a name="cacl-class"></a>카클 클래스

이 클래스는 (액세스 `ACL` 제어 목록) 구조에 대 한 래퍼입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAcl
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[CAcl::CAccessMask배열](#caccessmaskarray)|ACCESS_MASKs 배열입니다.|
|[CAcl:::카에이스 플래그어어레이](#caceflagarray)|BYT의 배열입니다.|
|[CAcl::CAceType배열](#cacetypearray)|BYT의 배열입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAcl:::CAcl](#cacl)|생성자입니다.|
|[CAcl::~CAcl](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAcl::GetAceCount](#getacecount)|ACE(액세스 제어 항목) 개체 수를 반환합니다.|
|[CAcl::GetAclEntry](#getaclentries)|개체에서 액세스 제어 목록(ACL) 항목을 `CAcl` 검색합니다.|
|[CAcl::GetAclEntry](#getaclentry)|개체의 항목에 대한 모든 정보를 `CAcl` 검색합니다.|
|[CAcl::GetLength](#getlength)|ACL의 길이를 반환합니다.|
|[CAcl::GetPACL](#getpacl)|PACL(ACL에 대한 포인터)을 반환합니다.|
|[CAcl::비어 있음](#isempty)|개체에서 `CAcl` 항목에 대해 테스트합니다.|
|[CAcl::IsNull](#isnull)|개체의 상태를 `CAcl` 반환합니다.|
|[CAcl::제거 에이스](#removeace)|개체에서 특정 ACE(액세스 제어 항목)를 제거합니다. `CAcl`|
|[CAcl::제거 에이스](#removeaces)|지정된 에 적용되는 모든 `CAcl` AC(액세스 제어 항목)를 `CSid`제거합니다.|
|[CAcl::설정비어](#setempty)|개체를 `CAcl` 비어 있는 것으로 표시합니다.|
|[CAcl::SetNull](#setnull)|개체를 `CAcl` NULL로 표시합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CAcl::연산자 Const ACL *](#operator_const_acl__star)|오브젝트를 `CAcl` 구조체에 `ACL` 투사합니다.|
|[CAcl::연산자 =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

구조는 `ACL` ACL(액세스 제어 목록)의 헤더입니다. ACL에는 0개 이상의 AEs(액세스 제어 항목)의 순차 목록이 [포함됩니다.](/windows/win32/SecAuthZ/access-control-entries) ACL의 개별 AC는 0에서 *n-1로*번호가 매겨지며, 여기서 *n은* ACL의 ACEs 수입니다. ACL을 편집할 때 응용 프로그램은 ACL 내의 액세스 제어 항목(ACE)을 인덱스로 참조합니다.

두 가지 ACL 유형이 있습니다.

- 임의

- 시스템

임의 ACL은 개체의 소유자 또는 개체에 대한 액세스 권한을 부여한 사람이 WRITE_DAC 제어합니다. 특정 사용자 및 그룹이 개체에 대해 가질 수 있는 액세스를 지정합니다. 예를 들어 파일 소유자는 임의 ACL을 사용하여 파일에 액세스할 수 있는 사용자와 그룹을 제어할 수 있습니다.

개체에는 시스템 관리자가 제어하는 시스템 ACL 의 형태로 연결된 시스템 수준 보안 정보가 있을 수도 있습니다. 시스템 ACL을 사용하면 시스템 관리자가 개체에 대한 액세스 권한을 얻으려는 모든 시도를 감사할 수 있습니다.

자세한 내용은 Windows SDK의 [ACL](/windows/win32/SecAuthZ/access-control-lists) 토론을 참조하십시오.

Windows의 액세스 제어 모델에 대한 자세한 내용은 Windows SDK의 [액세스 제어를](/windows/win32/SecAuthZ/access-control) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="caclcaccessmaskarray"></a><a name="caccessmaskarray"></a>CAcl::CAccessMask배열

ACCESS_MASK 개체의 배열입니다.

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>설명

이 typedef는 액세스 제어 항목(ACEs)에 사용되는 액세스 권한을 저장하는 데 사용할 수 있는 배열 형식을 지정합니다.

## <a name="caclcaceflagarray"></a><a name="caceflagarray"></a>CAcl:::카에이스 플래그어어레이

BYT의 배열입니다.

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>설명

이 typedef는 ACE(액세스 제어 항목) 형식별 컨트롤 플래그를 정의하는 데 사용되는 배열 형식을 지정합니다. 가능한 플래그의 전체 목록은 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 정의를 참조하십시오.

## <a name="caclcacetypearray"></a><a name="cacetypearray"></a>CAcl::CAceType배열

BYT의 배열입니다.

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>설명

이 typedef는 ACCESS_ALLOWED_ACE_TYPE 또는 ACCESS_DENIED_ACE_TYPE 같은 ACE(액세스 제어 항목) 개체의 특성을 정의하는 데 사용되는 배열 유형을 지정합니다. 가능한 형식의 전체 목록은 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 정의를 참조하십시오.

## <a name="caclcacl"></a><a name="cacl"></a>CAcl:::CAcl

생성자입니다.

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존 `CAcl` 개체입니다.

### <a name="remarks"></a>설명

기존 `CAcl` `CAcl` 개체를 사용하여 선택적으로 개체를 만들 수 있습니다.

## <a name="caclcacl"></a><a name="dtor"></a>CAcl::~CAcl

소멸자입니다.

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>설명

소멸자는 개체에서 획득한 모든 리소스를 해제합니다.

## <a name="caclgetacecount"></a><a name="getacecount"></a>CAcl::GetAceCount

ACE(액세스 제어 항목) 개체 수를 반환합니다.

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>Return Value

개체의 ACE 항목 수를 `CAcl` 반환합니다.

## <a name="caclgetaclentries"></a><a name="getaclentries"></a>CAcl::GetAclEntry

개체에서 액세스 제어 목록(ACL) 항목을 `CAcl` 검색합니다.

```cpp
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSids*<br/>
[CSid](../../atl/reference/csid-class.md) 개체의 배열에 대한 포인터입니다.

*p액세스 마스크*<br/>
액세스 마스크입니다.

*pAcetype*<br/>
액세스 제어 항목(ACE) 형식입니다.

*페에이스 플래그*<br/>
ACE 플래그입니다.

### <a name="remarks"></a>설명

이 메서드는 배열 매개 변수를 `CAcl` 개체에 포함된 모든 ACE 개체의 세부 정보로 채웁니다. 특정 배열에 대한 세부 정보가 필요하지 않은 경우 NULL을 사용합니다.

각 배열의 내용은 서로, 즉 `CAccessMaskArray` 배열의 첫 번째 요소는 `CSidArray` 배열의 첫 번째 요소에 해당합니다.

ACE 유형 및 플래그에 대한 자세한 내용은 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 참조하십시오.

## <a name="caclgetaclentry"></a><a name="getaclentry"></a>CAcl::GetAclEntry

ACL(액세스 제어 목록)의 항목에 대한 모든 정보를 검색합니다.

```cpp
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
검색할 ACL 항목에 대한 인덱스입니다.

*p시드 (것)와 함께*<br/>
ACL 항목이 적용되는 [CSid](../../atl/reference/csid-class.md) 개체입니다.

*p 마스크*<br/>
액세스 권한을 부여하거나 거부할 수 있는 권한을 지정하는 마스크입니다.

*p유형*<br/>
ACE 유형입니다.

*pFlags*<br/>
ACE 플래그입니다.

*pObjectType*<br/>
개체 유형입니다. ACE에 개체 형식이 지정되지 않았거나 ACE가 OBJECT ACE가 아닌 경우 GUID_NULL 설정됩니다.

*p상속된 개체 유형*<br/>
상속된 개체 형식입니다. 상속된 개체 형식이 ACE에 지정되지 않았거나 ACE가 OBJECT ACE가 아닌 경우 GUID_NULL 설정됩니다.

### <a name="remarks"></a>설명

이 메서드는 개별 ACE에 대 한 모든 정보를 검색 [합니다.: GetAclEntry](#getaclentries) 만 사용할 수 있는 보다 더 많은 정보를 제공 합니다.

ACE 유형 및 플래그에 대한 자세한 내용은 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 참조하십시오.

## <a name="caclgetlength"></a><a name="getlength"></a>CAcl::GetLength

액세스 제어 목록(ACL)의 길이를 반환합니다.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Return Value

구조를 유지하는 데 필요한 바이트로 `ACL` 필요한 길이를 반환합니다.

## <a name="caclgetpacl"></a><a name="getpacl"></a>CAcl::GetPACL

ACL(액세스 제어 목록)에 대한 포인터를 반환합니다.

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>Return Value

구조에 대한 `ACL` 포인터를 반환합니다.

## <a name="caclisempty"></a><a name="isempty"></a>CAcl::비어 있음

개체에서 `CAcl` 항목에 대해 테스트합니다.

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>설명

개체가 NULL이 아니고 항목이 없는 경우 TRUE를 `CAcl` 반환합니다. 개체가 NULL이거나 하나 이상의 항목을 포함하는 경우 FALSE를 `CAcl` 반환합니다.

## <a name="caclisnull"></a><a name="isnull"></a>CAcl::IsNull

개체의 상태를 `CAcl` 반환합니다.

```
bool IsNull() const throw();
```

### <a name="return-value"></a>Return Value

그렇지 않으면 `CAcl` 개체가 NULL인 경우 TRUE를 반환합니다.

## <a name="cacloperator-const-acl-"></a><a name="operator_const_acl__star"></a>CAcl::연산자 Const ACL *

개체를 `CAcl` (액세스 `ACL` 제어 목록) 구조로 캐스팅합니다.

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>설명

구조의 주소를 `ACL` 반환합니다.

## <a name="cacloperator-"></a><a name="operator_eq"></a>CAcl::연산자 =

대입 연산자입니다.

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
`CAcl` 기존 개체에 할당할 수 있습니다.

### <a name="return-value"></a>Return Value

업데이트된 `CAcl` 개체에 대한 참조를 반환합니다.

## <a name="caclremoveace"></a><a name="removeace"></a>CAcl::제거 에이스

개체에서 특정 ACE(액세스 제어 항목)를 제거합니다. `CAcl`

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
제거할 ACE 항목에 대한 인덱스를 만듭니다.

### <a name="remarks"></a>설명

이 메서드는 [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)에서 파생됩니다.

## <a name="caclremoveaces"></a><a name="removeaces"></a>CAcl::제거 에이스

지정된 에 적용되는 모든 `CAcl` AC(액세스 제어 항목)를 제거합니다. `CSid`

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
`CSid` 개체에 대한 참조입니다.

## <a name="caclsetempty"></a><a name="setempty"></a>CAcl::설정비어

개체를 `CAcl` 비어 있는 것으로 표시합니다.

```cpp
void SetEmpty() throw();
```

### <a name="remarks"></a>설명

빈 `CAcl` 또는 NULL로 설정할 수 있습니다: 두 상태는 구별됩니다.

## <a name="caclsetnull"></a><a name="setnull"></a>CAcl::SetNull

개체를 `CAcl` NULL로 표시합니다.

```cpp
void SetNull() throw();
```

### <a name="remarks"></a>설명

빈 `CAcl` 또는 NULL로 설정할 수 있습니다: 두 상태는 구별됩니다.

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 글로벌 기능](../../atl/reference/security-global-functions.md)
