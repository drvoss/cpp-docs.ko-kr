---
title: CTokenGroups 클래스
ms.date: 11/04/2016
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
ms.openlocfilehash: ccfa628f4a099f7e13eb09d272c72c2bdd846f37
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746385"
---
# <a name="ctokengroups-class"></a>CTokenGroups 클래스

이 클래스는 구조의 `TOKEN_GROUPS` 래퍼입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CTokenGroups
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C토큰 그룹::C토큰 그룹](#ctokengroups)|생성자입니다.|
|[C토큰 그룹::~C토큰 그룹](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C토큰 그룹::추가](#add)|개체에 `CSid` a `TOKEN_GROUPS` 또는 `CTokenGroups` 기존 구조를 추가합니다.|
|[C토큰 그룹::D](#delete)|개체에서 `CSid` a 및 관련 특성을 `CTokenGroups` 삭제합니다.|
|[CToken그룹::D모두](#deleteall)|개체에서 `CSid` 모든 개체 및 관련 `CTokenGroups` 특성을 삭제합니다.|
|[CToken그룹::겟카운트](#getcount)|`CSid` 개체에 포함된 `CTokenGroups` 개체 및 관련 특성 수를 반환합니다.|
|[C토큰 그룹::GetLength](#getlength)|개체의 크기를 `CTokenGroups` 반환합니다.|
|[C토큰 그룹::GetPTOKEN_GROUPS](#getptoken_groups)|구조에 대한 포인터를 검색합니다. `TOKEN_GROUPS`|
|[CToken그룹::겟시드앤트속성](#getsidsandattributes)|개체에 `CSid` 속하는 개체 및 특성을 검색합니다. `CTokenGroups`|
|[C토큰 그룹::조회 시드](#lookupsid)|개체와 연결된 특성을 `CSid` 검색합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CToken그룹::연산자 const TOKEN_GROUPS *](#operator_const_token_groups__star)|개체를 `CTokenGroups` 구조체에 대한 `TOKEN_GROUPS` 포인터로 캐스팅합니다.|
|[C토큰 그룹::연산자 =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

[액세스 토큰은](/windows/win32/SecAuthZ/access-tokens) 프로세스 또는 스레드의 보안 컨텍스트를 설명하고 Windows 시스템에 로그온한 각 사용자에게 할당되는 개체입니다.

클래스는 `CTokenGroups` 액세스 토큰에 그룹 보안 식별자(SID)에 대한 정보를 포함하는 [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) 구조의 래퍼입니다.

Windows의 액세스 제어 모델에 대한 자세한 내용은 Windows SDK의 [액세스 제어를](/windows/win32/SecAuthZ/access-control) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="ctokengroupsadd"></a><a name="add"></a>C토큰 그룹::추가

개체에 `CSid` a `TOKEN_GROUPS` 또는 `CTokenGroups` 기존 구조를 추가합니다.

```cpp
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
[CSid 개체입니다.](../../atl/reference/csid-class.md)

*dwAttributes*<br/>
개체와 연결할 특성입니다. `CSid`

*r토큰 그룹*<br/>
[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) 구조입니다.

### <a name="remarks"></a>설명

이러한 메서드는 하나 `CSid` 이상의 개체와 해당 `CTokenGroups` 관련 특성을 개체에 추가합니다.

## <a name="ctokengroupsctokengroups"></a><a name="ctokengroups"></a>C토큰 그룹::C토큰 그룹

생성자입니다.

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
개체를 구성할 개체 또는 [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) 구조입니다. `CTokenGroups` `CTokenGroups`

### <a name="remarks"></a>설명

객체는 `CTokenGroups` 구조체 또는 이전에 `TOKEN_GROUPS` 정의된 `CTokenGroups` 개체를 사용하여 선택적으로 만들 수 있습니다.

## <a name="ctokengroupsctokengroups"></a><a name="dtor"></a>C토큰 그룹::~C토큰 그룹

소멸자입니다.

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>설명

소멸자는 할당된 모든 리소스를 해제합니다.

## <a name="ctokengroupsdelete"></a><a name="delete"></a>C토큰 그룹::D

개체에서 `CSid` a 및 관련 특성을 `CTokenGroups` 삭제합니다.

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
SID(보안 식별자) 및 특성을 제거해야 하는 [CSid](../../atl/reference/csid-class.md) 개체입니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 `CSid` false가 제거된 경우 true를 반환합니다.

## <a name="ctokengroupsdeleteall"></a><a name="deleteall"></a>CToken그룹::D모두

개체에서 `CSid` 모든 개체 및 관련 `CTokenGroups` 특성을 삭제합니다.

```cpp
void DeleteAll() throw();
```

## <a name="ctokengroupsgetcount"></a><a name="getcount"></a>CToken그룹::겟카운트

에 포함된 `CSid` 개체 수를 `CTokenGroups`반환합니다.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Return Value

개체에 포함된 [CSid](../../atl/reference/csid-class.md) 개체 수와 관련 `CTokenGroups` 특성을 반환합니다.

## <a name="ctokengroupsgetlength"></a><a name="getlength"></a>C토큰 그룹::GetLength

개체의 크기를 `CTokenGroup` 반환합니다.

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>설명

`CTokenGroup` 개체의 총 크기를 바이트로 반환합니다.

## <a name="ctokengroupsgetptoken_groups"></a><a name="getptoken_groups"></a>C토큰 그룹::GetPTOKEN_GROUPS

구조에 대한 포인터를 검색합니다. `TOKEN_GROUPS`

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>Return Value

액세스 토큰 개체에 속하는 [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) `CTokenGroups` 구조에 대한 포인터를 검색합니다.

## <a name="ctokengroupsgetsidsandattributes"></a><a name="getsidsandattributes"></a>CToken그룹::겟시드앤트속성

개체를 `CSid` 검색하고(선택적으로) `CTokenGroups` 개체에 속하는 특성을 검색합니다.

```cpp
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSids*<br/>
[CSid](../../atl/reference/csid-class.md) 개체의 배열에 대한 포인터입니다.

*p특성*<br/>
DWORD 배열에 대한 포인터입니다. 이 매개 변수를 생략하거나 NULL이 면 특성이 검색되지 않습니다.

### <a name="remarks"></a>설명

이 메서드는 개체에 포함된 `CSid` 모든 개체를 `CTokenGroups` 열거하고 개체에 배치하고 (선택적으로) 특성 플래그를 배열 개체에 표시합니다.

## <a name="ctokengroupslookupsid"></a><a name="lookupsid"></a>C토큰 그룹::조회 시드

개체와 연결된 특성을 `CSid` 검색합니다.

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
[CSid 개체입니다.](../../atl/reference/csid-class.md)

*pdw속성*<br/>
개체의 특성을 수락하는 `CSid` DWORD에 대한 포인터입니다. 생략하거나 NULL이 면 특성이 검색되지 않습니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 `CSid` false가 발견되면 true를 반환합니다.

### <a name="remarks"></a>설명

*pdwAttributes를* NULL로 설정하면 특성에 액세스하지 `CSid` 않고 의 존재를 확인할 수 있습니다. 이 메서드는 액세스 권한을 확인하는 데 사용해서는 안 됩니다. 응용 프로그램은 대신 [CAccessToken::CheckToken멤버 자격 메서드를](../../atl/reference/caccesstoken-class.md#checktokenmembership) 사용 해야 합니다.

## <a name="ctokengroupsoperator-"></a><a name="operator_eq"></a>C토큰 그룹::연산자 =

대입 연산자입니다.

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
개체에 할당할 개체 또는 [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) 구조입니다. `CTokenGroups` `CTokenGroups`

### <a name="return-value"></a>Return Value

업데이트된 `CTokenGroups` 개체를 반환합니다.

## <a name="ctokengroupsoperator-const-token_groups-"></a><a name="operator_const_token_groups__star"></a>CToken그룹::연산자 const TOKEN_GROUPS *

값을 구조에 대한 포인터에 `TOKEN_GROUPS` 캐스팅합니다.

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>설명

[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) 구조에 대한 포인터에 값을 캐스팅합니다.

## <a name="see-also"></a>참조

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[CSid 클래스](../../atl/reference/csid-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 글로벌 기능](../../atl/reference/security-global-functions.md)
