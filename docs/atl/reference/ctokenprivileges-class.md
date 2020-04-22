---
title: CTokenPrivileges 클래스
ms.date: 11/04/2016
f1_keywords:
- CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::Add
- ATLSECURITY/ATL::CTokenPrivileges::Delete
- ATLSECURITY/ATL::CTokenPrivileges::DeleteAll
- ATLSECURITY/ATL::CTokenPrivileges::GetCount
- ATLSECURITY/ATL::CTokenPrivileges::GetDisplayNames
- ATLSECURITY/ATL::CTokenPrivileges::GetLength
- ATLSECURITY/ATL::CTokenPrivileges::GetLuidsAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetNamesAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetPTOKEN_PRIVILEGES
- ATLSECURITY/ATL::CTokenPrivileges::LookupPrivilege
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
ms.openlocfilehash: 75c09f723860540aa54cf3744cde7e61d9202f79
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747353"
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges 클래스

이 클래스는 구조의 `TOKEN_PRIVILEGES` 래퍼입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CTokenPrivileges
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C토큰 프리빌리지::CToken권한](#ctokenprivileges)|생성자입니다.|
|[C토큰 프리빌리지::~CToken권한](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C토큰 프리빌리지::추가](#add)|개체에 `CTokenPrivileges` 하나 이상의 권한을 추가합니다.|
|[C토큰 프리빌리지::D](#delete)|개체에서 권한을 삭제합니다. `CTokenPrivileges`|
|[CToken권한::Deleteall](#deleteall)|`CTokenPrivileges` 개체에서 모든 권한을 삭제합니다.|
|[CToken권한::겟카운트](#getcount)|개체의 권한 항목 수를 `CTokenPrivileges` 반환합니다.|
|[CToken권한::GetDisplay이름](#getdisplaynames)|`CTokenPrivileges` 개체에 포함된 권한에 대한 표시 이름을 검색합니다.|
|[C토큰 프리빌리지::GetLength](#getlength)|개체로 표시되는 `TOKEN_PRIVILEGES` 구조를 유지하는 데 필요한 값으로 `CTokenPrivileges` 버퍼 크기를 반환합니다.|
|[CToken권한::GetLuidsAnd속성](#getluidsandattributes)|개체에서 로컬 고유 식별자(LUI)와 특성 플래그를 검색합니다. `CTokenPrivileges`|
|[CToken권한::GetNamesand속성](#getnamesandattributes)|개체에서 권한 이름 및 특성 `CTokenPrivileges` 플래그를 검색합니다.|
|[C토큰 프리빌리지::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|구조에 대한 `TOKEN_PRIVILEGES` 포인터를 반환합니다.|
|[CToken권한::조회 프리빌리지](#lookupprivilege)|지정된 권한 이름과 연결된 특성을 검색합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CToken권한::연산자 const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|값을 구조에 대한 포인터에 `TOKEN_PRIVILEGES` 캐스팅합니다.|
|[CToken권한::연산자 =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

[액세스 토큰은](/windows/win32/SecAuthZ/access-tokens) 프로세스 또는 스레드의 보안 컨텍스트를 설명하고 Windows 시스템에 로그온한 각 사용자에게 할당되는 개체입니다.

액세스 토큰은 각 사용자에게 부여된 다양한 보안 권한을 설명하는 데 사용됩니다. 권한은 로컬고유 [식별자(LUID)라고](/windows/win32/api/winnt/ns-winnt-luid)하는 64비트 번호와 설명자 문자열로 구성됩니다.

`CTokenPrivileges` 클래스는 [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) 구조의 래퍼이며 0개 이상의 권한을 포함합니다. 제공된 클래스 메서드를 사용하여 권한을 추가, 삭제 또는 쿼리할 수 있습니다.

Windows의 액세스 제어 모델에 대한 자세한 내용은 Windows SDK의 [액세스 제어를](/windows/win32/SecAuthZ/access-control) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="ctokenprivilegesadd"></a><a name="add"></a>C토큰 프리빌리지::추가

액세스 토큰 개체에 `CTokenPrivileges` 하나 이상의 권한을 추가합니다.

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>매개 변수

*psz특권*<br/>
WINNT에 정의된 대로 권한의 이름을 지정하는 null-종단 문자열에 대한 포인터입니다. H 헤더 파일입니다.

*bEnable*<br/>
true이면 권한이 활성화됩니다. false이면 권한은 비활성화됩니다.

*r프리빌리지*<br/>
[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) 구조에 대한 참조입니다. 권한 및 특성은 이 구조에서 복사되어 개체에 `CTokenPrivileges` 추가됩니다.

### <a name="return-value"></a>Return Value

이 메서드의 첫 번째 형식은 권한이 성공적으로 추가된 경우 true를 반환합니다.

## <a name="ctokenprivilegesctokenprivileges"></a><a name="ctokenprivileges"></a>C토큰 프리빌리지::CToken권한

생성자입니다.

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
새 `CTokenPrivileges` 개체에 할당할 개체입니다.

*r프리빌리지*<br/>
새 [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) `CTokenPrivileges` 개체에 할당할 TOKEN_PRIVILEGES 구조입니다.

### <a name="remarks"></a>설명

객체는 `CTokenPrivileges` 구조체 또는 이전에 `TOKEN_PRIVILEGES` 정의된 `CTokenPrivileges` 개체를 사용하여 선택적으로 만들 수 있습니다.

## <a name="ctokenprivilegesctokenprivileges"></a><a name="dtor"></a>C토큰 프리빌리지::~CToken권한

소멸자입니다.

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>설명

소멸자는 할당된 모든 리소스를 해제합니다.

## <a name="ctokenprivilegesdelete"></a><a name="delete"></a>C토큰 프리빌리지::D

액세스 토큰 개체에서 `CTokenPrivileges` 권한을 삭제합니다.

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>매개 변수

*psz특권*<br/>
WINNT에 정의된 대로 권한의 이름을 지정하는 null-종단 문자열에 대한 포인터입니다. H 헤더 파일입니다. 예를 들어 이 매개 변수는 상수 SE_SECURITY_NAME 또는 해당 문자열인 "SeSecurityPrivilege"를 지정할 수 있습니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 권한이 성공적으로 삭제된 경우 true를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 제한된 토큰을 만드는 도구로 유용합니다.

## <a name="ctokenprivilegesdeleteall"></a><a name="deleteall"></a>CToken권한::Deleteall

`CTokenPrivileges` 액세스 토큰 개체에서 모든 권한을 삭제합니다.

```cpp
void DeleteAll() throw();
```

### <a name="remarks"></a>설명

`CTokenPrivileges` 액세스 토큰 개체에 포함된 모든 권한을 삭제합니다.

## <a name="ctokenprivilegesgetdisplaynames"></a><a name="getdisplaynames"></a>CToken권한::GetDisplay이름

액세스 토큰 개체에 포함된 권한에 `CTokenPrivileges` 대한 표시 이름을 검색합니다.

```cpp
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p표시 이름*<br/>
`CString` 개체의 배열에 대한 포인터입니다. `CNames`는 형식 def로 `CTokenPrivileges::CAtlArray<CString>`정의됩니다.

### <a name="remarks"></a>설명

매개 `pDisplayNames` 변수는 `CString` 개체에 포함된 권한에 해당하는 표시 이름을 수신하는 개체 `CTokenPrivileges` 배열에 대한 포인터입니다. 이 메서드는 WINNT의 정의된 권한 섹션에 지정된 권한에 대해서만 표시 이름을 검색합니다. H.

이 메서드는 표시 가능한 이름을 검색합니다: 예를 들어 특성 이름이 SE_REMOTE_SHUTDOWN_NAME 경우 표시 가능한 이름은 "원격 시스템에서 강제 종료"입니다. 시스템 이름을 얻으려면 [CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)를 사용합니다.

## <a name="ctokenprivilegesgetcount"></a><a name="getcount"></a>CToken권한::겟카운트

개체의 권한 항목 수를 `CTokenPrivileges` 반환합니다.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Return Value

`CTokenPrivileges` 개체에 포함된 권한 수를 반환합니다.

## <a name="ctokenprivilegesgetlength"></a><a name="getlength"></a>C토큰 프리빌리지::GetLength

개체의 길이를 `CTokenPrivileges` 반환합니다.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Return Value

개체에 포함된 모든 권한 항목을 `TOKEN_PRIVILEGES` 포함하여 개체로 표시되는 구조를 유지하는 데 필요한 바이트 수를 반환합니다. `CTokenPrivileges`

## <a name="ctokenprivilegesgetluidsandattributes"></a><a name="getluidsandattributes"></a>CToken권한::GetLuidsAnd속성

개체에서 로컬 고유 식별자(LUI)와 특성 플래그를 검색합니다. `CTokenPrivileges`

```cpp
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p프리빌리지*<br/>
[LUID](/windows/win32/api/winnt/ns-winnt-luid) 개체의 배열에 대한 포인터입니다. `CLUIDArray`은 으로 정의된 `CAtlArray<LUID> CLUIDArray`형식def입니다.

*p특성*<br/>
DWORD 개체의 배열에 대한 포인터입니다. 이 매개 변수를 생략하거나 NULL이 면 특성이 검색되지 않습니다. `CAttributes`은 으로 정의된 `CAtlArray <DWORD> CAttributes`형식def입니다.

### <a name="remarks"></a>설명

이 메서드는 `CTokenPrivileges` 액세스 토큰 개체에 포함 된 모든 권한을 열거 하 고 개별 LUIDs 및 (선택적으로) 특성 플래그 배열 개체에 배치 합니다.

## <a name="ctokenprivilegesgetnamesandattributes"></a><a name="getnamesandattributes"></a>CToken권한::GetNamesand속성

개체에서 이름 및 특성 `CTokenPrivileges` 플래그를 검색합니다.

```cpp
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*p 이름*<br/>
개체 배열에 `CString` 대한 포인터입니다. `CNames`은 으로 정의된 `CAtlArray <CString> CNames`형식def입니다.

*p특성*<br/>
DWORD 개체의 배열에 대한 포인터입니다. 이 매개 변수를 생략하거나 NULL이 면 특성이 검색되지 않습니다. `CAttributes`은 으로 정의된 `CAtlArray <DWORD> CAttributes`형식def입니다.

### <a name="remarks"></a>설명

이 메서드는 `CTokenPrivileges` 개체에 포함 된 모든 권한을 열거 하 고 이름을 배치 하 고 (선택적으로) 특성 플래그 배열 개체에 플래그를 지정 합니다.

이 메서드는 표시 가능한 이름 대신 특성 SE_REMOTE_SHUTDOWN_NAME 이름을 검색합니다. 표시 가능한 이름을 얻으려면 [CTokenPrivileges::GetDisplayNames 메서드를](#getdisplaynames)사용합니다.

## <a name="ctokenprivilegesgetptoken_privileges"></a><a name="getptoken_privileges"></a>C토큰 프리빌리지::GetPTOKEN_PRIVILEGES

구조에 대한 `TOKEN_PRIVILEGES` 포인터를 반환합니다.

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>Return Value

[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) 구조에 대한 포인터를 반환합니다.

## <a name="ctokenprivilegeslookupprivilege"></a><a name="lookupprivilege"></a>CToken권한::조회 프리빌리지

지정된 권한 이름과 연결된 특성을 검색합니다.

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*psz특권*<br/>
WINNT에 정의된 대로 권한의 이름을 지정하는 null-종단 문자열에 대한 포인터입니다. H 헤더 파일입니다. 예를 들어 이 매개 변수는 상수 SE_SECURITY_NAME 또는 해당 문자열인 "SeSecurityPrivilege"를 지정할 수 있습니다.

*pdw속성*<br/>
특성을 받는 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

특성이 성공적으로 검색된 경우 true를 반환합니다.

## <a name="ctokenprivilegesoperator-"></a><a name="operator_eq"></a>CToken권한::연산자 =

대입 연산자입니다.

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*r프리빌리지*<br/>
개체에 할당할 [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) `CTokenPrivileges` 구조입니다.

*rhs*<br/>
`CTokenPrivileges` 개체에 할당할 개체입니다.

### <a name="return-value"></a>Return Value

업데이트된 `CTokenPrivileges` 개체를 반환합니다.

## <a name="ctokenprivilegesoperator-const-token_privileges-"></a><a name="operator_const_token_privileges__star"></a>CToken권한::연산자 콘스트 TOKEN_PRIVILEGES\*

값을 구조에 대한 포인터에 `TOKEN_PRIVILEGES` 캐스팅합니다.

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>설명

TOKEN_PRIVILEGES [구조에](/windows/win32/api/winnt/ns-winnt-token_privileges) 대한 포인터에 값을 캐스팅합니다.

## <a name="see-also"></a>참조

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)<br/>
[Luid](/windows/win32/api/winnt/ns-winnt-luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 글로벌 기능](../../atl/reference/security-global-functions.md)
