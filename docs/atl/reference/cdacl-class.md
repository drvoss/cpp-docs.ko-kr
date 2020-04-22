---
title: CDacl 클래스
ms.date: 11/04/2016
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
ms.openlocfilehash: 713e78635fe261615a82ab518cdb2c68ac0eeed4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747732"
---
# <a name="cdacl-class"></a>CDacl 클래스

이 클래스는 DACL(임의 액세스 제어 목록) 구조의 래퍼입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CDacl : public CAcl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDacl::CDacl](#cdacl)|생성자입니다.|
|[CDacl::~CDacl](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDacl::허용된 에이스](#addallowedace)|허용되는 ACE(액세스 제어 항목)를 `CDacl` 개체에 추가합니다.|
|[CDacl::추가 거부 에이스](#adddeniedace)|개체에 거부된 `CDacl` ACE를 추가합니다.|
|[CDacl::GetAceCount](#getacecount)|개체의 AC(액세스 제어 항목) 수를 `CDacl` 반환합니다.|
|[CDacl::제거 에이스](#removeace)|개체에서 특정 ACE(액세스 제어 항목)를 제거합니다. `CDacl`|
|[CDacl::제거모든 에이스](#removeallaces)|개체에 포함된 모든 AC를 `CDacl` 제거합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CDacl::연산자 =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

개체의 보안 설명자는 DACL을 포함할 수 있습니다. DACL에는 개체에 액세스할 수 있는 사용자 및 그룹을 식별하는 0개 이상의 AC(액세스 제어 항목)가 포함되어 있습니다. DACL이 비어 있는 경우(즉, A.0이 없음) 액세스가 명시적으로 부여되지 않으므로 액세스가 암시적으로 거부됩니다. 그러나 개체의 보안 설명자가 DACL이 없는 경우 개체는 보호되지 않으며 모든 사용자가 완전한 액세스 권한을 갖습니다.

개체의 DACL을 검색하려면 개체의 소유자이거나 개체에 READ_CONTROL 액세스할 수 있어야 합니다. 개체의 DACL을 변경하려면 개체에 대한 WRITE_DAC 액세스 권한이 있어야 합니다.

제공된 클래스 메서드를 사용하여 개체에서 AC를 생성, `CDacl` 추가, 제거 및 삭제합니다. 또한 [아틀겟다클과](security-global-functions.md#atlgetdacl) [아틀셋다클을](security-global-functions.md#atlsetdacl)참조하십시오.

Windows의 액세스 제어 모델에 대한 자세한 내용은 Windows SDK의 [액세스 제어를](/windows/win32/SecAuthZ/access-control) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CAcl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="cdacladdallowedace"></a><a name="addallowedace"></a>CDacl::허용된 에이스

허용되는 ACE(액세스 제어 항목)를 `CDacl` 개체에 추가합니다.

```
bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
[CSid 개체입니다.](../../atl/reference/csid-class.md)

*액세스 마스크*<br/>
지정된 `CSid` 개체에 대해 허용할 액세스 권한 마스크가 지정됩니다.

*에이스 플래그*<br/>
ACE 상속을 제어하는 비트 플래그 집합입니다.

*pObjectType*<br/>
개체 유형입니다.

*p상속된 개체 유형*<br/>
상속된 개체 형식입니다.

### <a name="return-value"></a>Return Value

ACE가 `CDacl` 개체에 추가된 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

`CDacl` 개체에는 개체에 액세스할 수 있는 사용자 및 그룹을 식별하는 0개 이상의 AC(액세스 제어 항목)가 포함되어 있습니다. 이 메서드는 개체에 대 `CDacl` 한 액세스를 허용 하는 ACE를 추가 합니다.

매개 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 변수에서 설정할 수 있는 다양한 플래그에 `AceFlags` 대한 설명은 ACE_HEADER 를 참조하십시오.

## <a name="cdacladddeniedace"></a><a name="adddeniedace"></a>CDacl::추가 거부 에이스

개체에 거부된 ACE(액세스 제어 `CDacl` 항목)를 추가합니다.

```
bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
`CSid` 개체입니다.

*액세스 마스크*<br/>
지정된 `CSid` 개체에 대해 거부될 액세스 권한 마스크가 지정됩니다.

*에이스 플래그*<br/>
ACE 상속을 제어하는 비트 플래그 집합입니다. 메서드의 첫 번째 형식에서 기본값은 0입니다.

*pObjectType*<br/>
개체 유형입니다.

*p상속된 개체 유형*<br/>
상속된 개체 형식입니다.

### <a name="return-value"></a>Return Value

ACE가 `CDacl` 개체에 추가된 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

`CDacl` 개체에는 개체에 액세스할 수 있는 사용자 및 그룹을 식별하는 0개 이상의 AC(액세스 제어 항목)가 포함되어 있습니다. 이 메서드는 개체에 대 `CDacl` 한 액세스를 거부 하는 ACE를 추가 합니다.

매개 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 변수에서 설정할 수 있는 다양한 플래그에 `AceFlags` 대한 설명은 ACE_HEADER 를 참조하십시오.

## <a name="cdaclcdacl"></a><a name="cdacl"></a>CDacl::CDacl

생성자입니다.

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존(액세스 `ACL` 제어 목록) 구조입니다.

### <a name="remarks"></a>설명

객체는 `CDacl` 기존 `ACL` 구조를 사용하여 선택적으로 만들 수 있습니다. SACL(시스템 액세스 제어 목록)이 아닌 DACL(임의 액세스 제어 목록)만 이 매개 변수로 전달해야 합니다. 디버그 빌드에서 SACL을 전달하면 ASSERT가 발생합니다. 릴리스 빌드에서 SACL을 통과하면 ACL의 AEs(액세스 제어 항목)가 무시되고 오류가 발생하지 않습니다.

## <a name="cdaclcdacl"></a><a name="dtor"></a>CDacl::~CDacl

소멸자입니다.

```
~CDacl () throw();
```

### <a name="remarks"></a>설명

소멸자는 [CDacl::RemoveAllAces를](#removeallaces)사용하여 모든 ACE(액세스 제어 항목)를 포함하여 개체에서 획득한 모든 리소스를 해제합니다.

## <a name="cdaclgetacecount"></a><a name="getacecount"></a>CDacl::GetAceCount

개체의 AC(액세스 제어 항목) 수를 `CDacl` 반환합니다.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Return Value

개체에 포함된 AC의 수를 `CDacl` 반환합니다.

## <a name="cdacloperator-"></a><a name="operator_eq"></a>CDacl::연산자 =

대입 연산자입니다.

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존 개체에 할당할 ACL(액세스 제어 목록)입니다.

### <a name="return-value"></a>Return Value

업데이트된 `CDacl` 개체에 대한 참조를 반환합니다.

### <a name="remarks"></a>설명

DACL(임의 액세스 제어 목록)만 이 함수에 전달해야 합니다. 이 함수에 SACL(시스템 액세스 제어 목록)을 전달하면 디버그 빌드에서 ASSERT가 발생하지만 릴리스 빌드에는 오류가 발생하지 않습니다.

## <a name="cdaclremoveace"></a><a name="removeace"></a>CDacl::제거 에이스

개체에서 특정 ACE(액세스 제어 항목)를 제거합니다. `CDacl`

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
제거할 ACE 항목에 대한 인덱스를 만듭니다.

### <a name="remarks"></a>설명

이 메서드는 [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)에서 파생됩니다.

## <a name="cdaclremoveallaces"></a><a name="removeallaces"></a>CDacl::제거모든 에이스

개체에 포함된 모든 AC(액세스 제어 항목)를 `CDacl` 제거합니다.

```cpp
void RemoveAllAces() throw();
```

### <a name="remarks"></a>설명

개체의 `ACE` 모든(액세스 제어 항목) 구조(있는 `CDacl` 경우)를 제거합니다.

## <a name="see-also"></a>참조

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[카클 클래스](../../atl/reference/cacl-class.md)<br/>
[ACL](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Ace](/windows/win32/SecAuthZ/access-control-entries)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 글로벌 기능](../../atl/reference/security-global-functions.md)
