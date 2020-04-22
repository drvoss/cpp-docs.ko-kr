---
title: CRegKey 클래스
ms.date: 11/04/2016
f1_keywords:
- CRegKey
- ATLBASE/ATL::CRegKey
- ATLBASE/ATL::CRegKey::CRegKey
- ATLBASE/ATL::CRegKey::Attach
- ATLBASE/ATL::CRegKey::Close
- ATLBASE/ATL::CRegKey::Create
- ATLBASE/ATL::CRegKey::DeleteSubKey
- ATLBASE/ATL::CRegKey::DeleteValue
- ATLBASE/ATL::CRegKey::Detach
- ATLBASE/ATL::CRegKey::EnumKey
- ATLBASE/ATL::CRegKey::Flush
- ATLBASE/ATL::CRegKey::GetKeySecurity
- ATLBASE/ATL::CRegKey::NotifyChangeKeyValue
- ATLBASE/ATL::CRegKey::Open
- ATLBASE/ATL::CRegKey::QueryBinaryValue
- ATLBASE/ATL::CRegKey::QueryDWORDValue
- ATLBASE/ATL::CRegKey::QueryGUIDValue
- ATLBASE/ATL::CRegKey::QueryMultiStringValue
- ATLBASE/ATL::CRegKey::QueryQWORDValue
- ATLBASE/ATL::CRegKey::QueryStringValue
- ATLBASE/ATL::CRegKey::QueryValue
- ATLBASE/ATL::CRegKey::RecurseDeleteKey
- ATLBASE/ATL::CRegKey::SetBinaryValue
- ATLBASE/ATL::CRegKey::SetDWORDValue
- ATLBASE/ATL::CRegKey::SetGUIDValue
- ATLBASE/ATL::CRegKey::SetKeySecurity
- ATLBASE/ATL::CRegKey::SetKeyValue
- ATLBASE/ATL::CRegKey::SetMultiStringValue
- ATLBASE/ATL::CRegKey::SetQWORDValue
- ATLBASE/ATL::CRegKey::SetStringValue
- ATLBASE/ATL::CRegKey::SetValue
- ATLBASE/ATL::CRegKey::m_hKey
- ATLBASE/ATL::CRegKey::m_pTM
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
ms.openlocfilehash: d3bdb2e7c3ab0ef56ef7f6fba5d43f1ba0bb7fc6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746514"
---
# <a name="cregkey-class"></a>CRegKey 클래스

이 클래스는 시스템 레지스트리의 항목을 조작하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CRegKey
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CRegKey::CRegKey](#cregkey)|생성자입니다.|
|[CRegKey::~CRegKey](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CRegKey::연결](#attach)|[m_hKey](#m_hkey) 멤버 핸들을 에 설정하여 `hKey` `CRegKey` 개체에 HKEY를 연결하려면 이 메서드를 호출합니다.|
|[CRegKey::닫기](#close)|[m_hKey](#m_hkey) 멤버 핸들을 해제 하 고 NULL로 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::만들기](#create)|이 메서드를 호출하여 지정된 키를 만듭니다. `hKeyParent`|
|[CRegKey::DeleteSubKey](#deletesubkey)|레지스트리에서 지정된 키를 제거 하려면이 메서드를 호출 합니다.|
|[CRegKey::DeleteValue](#deletevalue)|[m_hKey](#m_hkey)에서 값 필드를 제거 하려면이 메서드를 호출 합니다.|
|[CRegKey::D에타치](#detach)|이 메서드를 호출하여 [m_hKey](#m_hkey) 멤버 핸들을 `CRegKey` 개체에서 분리하고 NULL로 설정합니다. `m_hKey`|
|[CRegKey::에눔키](#enumkey)|열려 있는 레지스트리 키의 하위 키를 열거하려면 이 메서드를 호출합니다.|
|[CRegKey::플러시](#flush)|이 메서드를 호출하여 열린 레지스트리 키의 모든 특성을 레지스트리에 작성합니다.|
|[CRegKey::GetKey보안](#getkeysecurity)|열려 있는 레지스트리 키를 보호하는 보안 설명자의 복사본을 검색하려면 이 메서드를 호출합니다.|
|[CRegKey::알림변경키값](#notifychangekeyvalue)|이 메서드는 열려 있는 레지스트리 키의 특성 또는 내용에 대 한 변경 내용을 호출자에게 보겠습니다.|
|[CRegKey::열기](#open)|이 메서드를 호출하여 지정된 키를 열고 이 키의 핸들로 [m_hKey](#m_hkey) 설정합니다.|
|[CRegKey::쿼리 바이너리값](#querybinaryvalue)|지정된 값 이름에 대 한 이진 데이터를 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::쿼리워드 값](#querydwordvalue)|지정된 값 이름에 대 한 DWORD 데이터를 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::쿼리 GUID값](#queryguidvalue)|지정된 값 이름에 대 한 GUID 데이터를 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::쿼리다중 문자열 값](#querymultistringvalue)|지정된 값 이름에 대 한 다중 문자열 데이터를 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::쿼리QWORD값](#queryqwordvalue)|지정된 값 이름에 대 한 QWORD 데이터를 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::쿼리 문자열 값](#querystringvalue)|지정된 값 이름에 대 한 문자열 데이터를 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::쿼리 값](#queryvalue)|[m_hKey](#m_hkey)지정된 값 필드에 대 한 데이터를 검색 하려면이 메서드를 호출 합니다. 이 메서드의 이전 버전은 더 이상 지원되지 않으며 ATL_DEPRECATED 으로 표시됩니다.|
|[CRegKey::재저주삭제키](#recursedeletekey)|레지스트리에서 지정된 키를 제거하고 하위 키를 명시적으로 제거하려면 이 메서드를 호출합니다.|
|[CRegKey::설정 바이너리 값](#setbinaryvalue)|레지스트리 키의 이진 값을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetDword값](#setdwordvalue)|레지스트리 키의 DWORD 값을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::설정GUID값](#setguidvalue)|레지스트리 키의 GUID 값을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetKey보안](#setkeysecurity)|레지스트리 키의 보안을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetKey값](#setkeyvalue)|지정된 키의 지정된 값 필드에 데이터를 저장 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetMultiString값](#setmultistringvalue)|레지스트리 키의 다중 문자열 값을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetQword값](#setqwordvalue)|레지스트리 키의 QWORD 값을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetString값](#setstringvalue)|레지스트리 키의 문자열 값을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetValue](#setvalue)|m_hKey 지정된 값 필드에 데이터를 저장하려면 [m_hKey](#m_hkey)이 메서드를 호출합니다. 이 메서드의 이전 버전은 더 이상 지원되지 않으며 ATL_DEPRECATED 으로 표시됩니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CRegKey::연산자 HKEY](#operator_hkey)|개체를 `CRegKey` HKEY로 변환합니다.|
|[CRegKey::연산자 =](#operator_eq)|대입 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CRegKey::m_hKey](#m_hkey)|개체와 연결된 레지스트리 키의 핸들을 포함합니다. `CRegKey`|
|[CRegKey::m_pTM](#m_ptm)|개체에 `CAtlTransactionManager` 대한 포인터|

## <a name="remarks"></a>설명

`CRegKey`은 시스템 레지스트리에서 키와 값을 만들고 삭제하는 방법을 제공합니다. 레지스트리에는 소프트웨어 버전 번호, 설치된 하드웨어의 논리적-물리적 매핑 및 COM 개체와 같은 시스템 구성 요소에 대한 설치별 정의 집합이 포함되어 있습니다.

`CRegKey`은 지정된 컴퓨터의 시스템 레지스트리에 프로그래밍 인터페이스를 제공합니다. 예를 들어 특정 레지스트리 키를 열려면 을 호출합니다. `CRegKey::Open` 데이터 값을 검색하거나 수정하려면 `CRegKey::QueryValue` `CRegKey::SetValue`각각 호출하거나 키를 닫려면 `CRegKey::Close`를 호출합니다.

키를 닫으면 해당 레지스트리 데이터가 하드 디스크에 기록됩니다(플러시). 이 프로세스는 몇 초 정도 걸릴 수 있습니다. 응용 프로그램이 하드 디스크에 레지스트리 데이터를 명시적으로 작성해야 하는 경우 [RegFlushKey](/windows/win32/api/winreg/nf-winreg-regflushkey) Win32 함수를 호출할 수 있습니다. 그러나 `RegFlushKey` 많은 시스템 리소스를 사용 하 고 절대적으로 필요한 경우에 호출 해야 합니다.

> [!IMPORTANT]
> 호출자가 레지스트리 위치를 지정할 수 있도록 허용하는 모든 메서드는 신뢰할 수 없는 데이터를 읽을 수 있습니다. [RegQueryValueEx를](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) 사용하는 메서드는 이 함수가 NULL이 종료된 문자열을 명시적으로 처리하지 않는다는 점을 고려해야 합니다. 두 조건 모두 호출 코드에서 확인해야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="cregkeyattach"></a><a name="attach"></a>CRegKey::연결

m_hKey 멤버 핸들을 hKey에 `CRegKey` 설정하여 [m_hKey](#m_hkey) 개체에 HKEY를 연결하려면 이 메서드를 *호출합니다.*

```cpp
void Attach(HKEY hKey) throw();
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
레지스트리 키의 핸들입니다.

### <a name="remarks"></a>설명

`Attach`NULL이 `m_hKey` 아닌 경우 어설션합니다.

## <a name="cregkeyclose"></a><a name="close"></a>CRegKey::닫기

[m_hKey](#m_hkey) 멤버 핸들을 해제 하 고 NULL로 설정 하려면이 메서드를 호출 합니다.

```
LONG Close() throw();
```

### <a name="return-value"></a>Return Value

성공하면 ERROR_SUCCESS 반환합니다. 그렇지 않으면 오류 값을 반환합니다.

## <a name="cregkeycreate"></a><a name="create"></a>CRegKey::만들기

*hKeyParent*의 하위 키로 존재하지 않는 경우 이 메서드를 호출하여 지정된 키를 만듭니다.

```
LONG Create(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPTSTR lpszClass = REG_NONE,
    DWORD dwOptions = REG_OPTION_NON_VOLATILE,
    REGSAM samDesired = KEY_READ | KEY_WRITE,
    LPSECURITY_ATTRIBUTES lpSecAttr = NULL,
    LPDWORD lpdwDisposition = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*hKeyParent*<br/>
열린 키의 핸들입니다.

*lpszKeyName*<br/>
만들거나 열 수 있는 키의 이름을 지정합니다. 이 이름은 *hKeyParent*의 하위 키여야 합니다.

*lpszClass*<br/>
만들거나 열 수 있는 키의 클래스를 지정합니다. 기본값은 REG_NONE.

*dwOptions*<br/>
키에 대한 옵션입니다. 기본값은 REG_OPTION_NON_VOLATILE. 가능한 값 및 설명 목록은 Windows SDK의 [RegCreateKeyEx를](/windows/win32/api/winreg/nf-winreg-regcreatekeyexw) 참조하십시오.

*삼원하는*<br/>
키에 대한 보안 액세스입니다. 기본값은 KEY_READ &#124; KEY_WRITE. 가능한 값 및 설명 목록은 을 `RegCreateKeyEx`참조하십시오.

*lpSecAttr*<br/>
자식 프로세스에서 키 핸들을 상속할 수 있는지 여부를 나타내는 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 구조에 대한 포인터입니다. 기본적으로 이 매개 변수는 NULL입니다(핸들을 상속할 수 없음).

*lpdwDisposition*<br/>
【아웃】 NULL이 아닌 경우 REG_CREATED_NEW_KEY(키가 존재하지 않고 생성된 경우) 또는 REG_OPENED_EXISTING_KEY(키가 존재하고 열린 경우)를 검색합니다.

### <a name="return-value"></a>Return Value

성공하면 ERROR_SUCCESS 반환하고 키를 엽니다. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

`Create`[m_hKey](#m_hkey) 멤버를 이 키의 핸들로 설정합니다.

## <a name="cregkeycregkey"></a><a name="cregkey"></a>CRegKey::CRegKey

생성자입니다.

```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
`CRegKey` 개체에 대한 참조입니다.

*hKey*<br/>
레지스트리 키에 대한 핸들입니다.

*Ptm*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="remarks"></a>설명

새 `CRegKey` 개체를 만듭니다. 개체는 기존 `CRegKey` 개체또는 핸들에서 레지스트리 키로 만들 수 있습니다.

## <a name="cregkeycregkey"></a><a name="dtor"></a>CRegKey::~CRegKey

소멸자입니다.

```
~CRegKey() throw();
```

### <a name="remarks"></a>설명

소멸자가 해제됩니다. `m_hKey`

## <a name="cregkeydeletesubkey"></a><a name="deletesubkey"></a>CRegKey::DeleteSubKey

레지스트리에서 지정된 키를 제거 하려면이 메서드를 호출 합니다.

```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```

### <a name="parameters"></a>매개 변수

*lpszSubKey*<br/>
삭제할 키 이름을 지정합니다. 이 이름은 [m_hKey](#m_hkey).

### <a name="return-value"></a>Return Value

성공하면 ERROR_SUCCESS 반환합니다. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

`DeleteSubKey`하위 키가 없는 키만 삭제할 수 있습니다. 키에 하위 키가 있는 경우 대신 [RecurseDeleteKey를](#recursedeletekey) 호출합니다.

## <a name="cregkeydeletevalue"></a><a name="deletevalue"></a>CRegKey::DeleteValue

[m_hKey](#m_hkey)에서 값 필드를 제거 하려면이 메서드를 호출 합니다.

```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```

### <a name="parameters"></a>매개 변수

*lpsz값*<br/>
제거할 값 필드를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 ERROR_SUCCESS 반환합니다. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

## <a name="cregkeydetach"></a><a name="detach"></a>CRegKey::D에타치

이 메서드를 호출하여 [m_hKey](#m_hkey) 멤버 핸들을 `CRegKey` 개체에서 분리하고 NULL로 설정합니다. `m_hKey`

```
HKEY Detach() throw();
```

### <a name="return-value"></a>Return Value

개체와 연결된 HKEY입니다. `CRegKey`

## <a name="cregkeyenumkey"></a><a name="enumkey"></a>CRegKey::에눔키

열려 있는 레지스트리 키의 하위 키를 열거하려면 이 메서드를 호출합니다.

```
LONG EnumKey(
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
하위 키 인덱스입니다. 이 매개 변수는 첫 번째 호출에 대해 0이어야 하며 후속 호출에 대해 증가해야 합니다.

*pszName*<br/>
null 문자 종료를 포함하여 하위 키의 이름을 받는 버퍼에 대한 포인터입니다. 하위 키의 이름만 전체 키 계층 구조가 아닌 버퍼에 복사됩니다.

*pnName길이*<br/>
*pszName* 매개 변수에 의해 지정된 버퍼의 크기를 TCHARs에서 지정하는 변수에 대한 포인터입니다. 이 크기에는 null 문자 종료가 포함되어야 합니다. 메서드가 반환될 때 *pnNameLength로* 가리키는 변수에는 버퍼에 저장된 문자 수가 포함됩니다. 반환된 개수에는 null 문자 종료가 포함되지 않습니다.

*pftLastWriteTime*<br/>
열거된 하위 키가 마지막으로 작성된 시간을 받는 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 반환 값은 ERROR_SUCCESS. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

하위 키를 등록하려면 인덱스가 `CRegKey::EnumKey` 0으로 호출합니다. 인덱스 값을 증분하고 메서드가 ERROR_NO_MORE_ITEMS 반환할 때까지 반복합니다. 자세한 내용은 Windows SDK의 [RegEnumKeyEx를](/windows/win32/api/winreg/nf-winreg-regenumkeyexw) 참조하십시오.

## <a name="cregkeyflush"></a><a name="flush"></a>CRegKey::플러시

이 메서드를 호출하여 열린 레지스트리 키의 모든 특성을 레지스트리에 작성합니다.

```
LONG Flush() throw();
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 반환 값은 ERROR_SUCCESS. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [RegEnumFlush를](/windows/win32/api/winreg/nf-winreg-regflushkey) 참조하십시오.

## <a name="cregkeygetkeysecurity"></a><a name="getkeysecurity"></a>CRegKey::GetKey보안

열려 있는 레지스트리 키를 보호하는 보안 설명자의 복사본을 검색하려면 이 메서드를 호출합니다.

```
LONG GetKeySecurity(
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```

### <a name="parameters"></a>매개 변수

*Si*<br/>
요청된 보안 정보를 나타내는 [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) 값입니다.

*Psd*<br/>
요청된 보안 설명자의 복사본을 받는 버퍼에 대한 포인터입니다.

*pn바이트*<br/>
*psd로*가리키는 버퍼의 크기(바이트)입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 반환 값은 ERROR_SUCCESS. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

자세한 내용은 [RegGetKeySecurity](/windows/win32/api/winreg/nf-winreg-reggetkeysecurity)을 참조하십시오.

## <a name="cregkeym_hkey"></a><a name="m_hkey"></a>CRegKey::m_hKey

개체와 연결된 레지스트리 키의 핸들을 포함합니다. `CRegKey`

```
HKEY m_hKey;
```

## <a name="cregkeym_ptm"></a><a name="m_ptm"></a>CRegKey::m_pTM

`CAtlTransactionManager` 개체에 대한 포인터입니다.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>설명

## <a name="cregkeynotifychangekeyvalue"></a><a name="notifychangekeyvalue"></a>CRegKey::알림변경키값

이 메서드는 열려 있는 레지스트리 키의 특성 또는 내용에 대 한 변경 내용을 호출자에게 보겠습니다.

```
LONG NotifyChangeKeyValue(
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```

### <a name="parameters"></a>매개 변수

*b워치서브트리*<br/>
지정된 키와 모든 하위 키의 변경 내용을 보고할지 또는 지정된 키에서만 보고할지 여부를 나타내는 플래그를 지정합니다. 이 매개 변수가 TRUE이면 메서드는 키와 하위 키의 변경 내용을 보고합니다. 매개 변수가 FALSE이면 메서드 는 키에서만 변경됩니다.

*dwNotify필터*<br/>
보고해야 하는 변경 내용을 제어하는 플래그 집합을 지정합니다. 이 매개 변수는 다음 값의 조합일 수 있습니다.

|값|의미|
|-----------|-------------|
|REG_NOTIFY_CHANGE_NAME|하위 키가 추가또는 삭제되면 호출자에게 알립니다.|
|REG_NOTIFY_CHANGE_ATTRIBUTES|호출자에게 보안 설명자 정보와 같은 키 특성에 대한 변경 사항을 알립니다.|
|REG_NOTIFY_CHANGE_LAST_SET|호출자에게 키 값에 대한 변경 사항을 알립니다. 여기에는 값 추가 또는 삭제 또는 기존 값 변경이 포함될 수 있습니다.|
|REG_NOTIFY_CHANGE_SECURITY|호출자에게 키의 보안 설명자에게 변경 사항을 알립니다.|

*h이벤트*<br/>
이벤트에 대한 핸들. *bAsync* 매개 변수가 TRUE이면 메서드가 즉시 반환되고 이 이벤트를 신호로 변경 내용이 보고됩니다. *bAsync가* FALSE이면 *hEvent는* 무시됩니다.

*bAsync*<br/>
메서드 보고서의 변경 방법을 나타내는 플래그를 지정합니다. 이 매개 변수가 TRUE이면 메서드가 즉시 반환되고 지정된 이벤트를 신호로 변경 내용을 보고합니다. 이 매개 변수가 FALSE이면 변경이 발생할 때까지 메서드가 반환되지 않습니다. *hEvent가* 유효한 이벤트를 지정하지 않으면 *bAsync* 매개 변수가 TRUE일 수 없습니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 반환 값은 ERROR_SUCCESS. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

> [!NOTE]
> 이 메서드는 지정된 키가 삭제된 경우 호출자에게 알리지 않습니다.

자세한 내용 및 샘플 프로그램에 대한 자세한 내용은 [RegNotifyChangeKeyValue](/windows/win32/api/winreg/nf-winreg-regnotifychangekeyvalue)을 참조하십시오.

## <a name="cregkeyopen"></a><a name="open"></a>CRegKey::열기

이 메서드를 호출하여 지정된 키를 열고 이 키의 핸들로 [m_hKey](#m_hkey) 설정합니다.

```
LONG Open(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```

### <a name="parameters"></a>매개 변수

*hKeyParent*<br/>
열린 키의 핸들입니다.

*lpszKeyName*<br/>
만들거나 열 수 있는 키의 이름을 지정합니다. 이 이름은 *hKeyParent*의 하위 키여야 합니다.

*삼원하는*<br/>
키에 대한 보안 액세스입니다. 기본값은 KEY_ALL_ACCESS. 가능한 값 및 설명 목록은 Windows SDK의 [RegCreateKeyEx를](/windows/win32/api/winreg/nf-winreg-regcreatekeyexw) 참조하십시오.

### <a name="return-value"></a>Return Value

성공하면 ERROR_SUCCESS 반환합니다. 그렇지 않으면 WINERROR에 정의된 0이 아닌 오류 값입니다. H.

### <a name="remarks"></a>설명

*lpszKeyName* 매개 변수가 NULL이거나 빈 문자열을 가리키는 경우 `Open` *hKeyParent로*식별된 키의 새 핸들을 열지만 이전에 열린 핸들은 닫지 않습니다.

[CRegKey::Create와](#create) `Open` 달리 지정된 키가 없는 경우 지정키를 만들지 않습니다.

## <a name="cregkeyoperator-hkey"></a><a name="operator_hkey"></a>CRegKey::연산자 HKEY

개체를 `CRegKey` HKEY로 변환합니다.

```
operator HKEY() const throw();
```

## <a name="cregkeyoperator-"></a><a name="operator_eq"></a>CRegKey::연산자 =

대입 연산자입니다.

```
CRegKey& operator= (CRegKey& key) throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
복사할 키입니다.

### <a name="return-value"></a>Return Value

새 키에 대한 참조를 반환합니다.

### <a name="remarks"></a>설명

이 연산자는 현재 개체에서 *키를* 분리하고 `CRegKey` 대신 개체에 할당합니다.

## <a name="cregkeyquerybinaryvalue"></a><a name="querybinaryvalue"></a>CRegKey::쿼리 바이너리값

지정된 값 이름에 대 한 이진 데이터를 검색 하려면이 메서드를 호출 합니다.

```
LONG QueryBinaryValue(
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
쿼리할 값의 이름을 포함하는 null-종단 문자열에 대한 포인터입니다.

*pValue*<br/>
값의 데이터를 받는 버퍼에 대한 포인터입니다.

*pn바이트*<br/>
*pValue* 매개 변수가 가리키는 버퍼의 크기를 바이트로 지정하는 변수에 대한 포인터입니다. 메서드가 반환되면 이 변수에는 버퍼에 복사된 데이터의 크기가 포함됩니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 ERROR_SUCCESS 반환됩니다. 메서드가 값을 읽지 못하면 WINERROR에 정의된 제로가 아닌 오류 코드를 반환합니다. H. 참조된 데이터가 REG_BINARY 형식이 아닌 경우 ERROR_INVALID_DATA 반환됩니다.

### <a name="remarks"></a>설명

이 메서드는 `RegQueryValueEx` 올바른 데이터 형식이 반환되는 지 확인하고 사용합니다. 자세한 내용은 [RegQueryValueEx를](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) 참조하십시오.

> [!IMPORTANT]
> 이 방법을 사용하면 호출자가 신뢰할 수 없는 데이터를 읽을 수 있는 레지스트리 위치를 지정할 수 있습니다. 또한 이 메서드에서 사용하는 [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) 함수는 NULL이 종료된 문자열을 명시적으로 처리하지 않습니다. 두 조건 모두 호출 코드에서 확인해야 합니다.

## <a name="cregkeyquerydwordvalue"></a><a name="querydwordvalue"></a>CRegKey::쿼리워드 값

지정된 값 이름에 대 한 DWORD 데이터를 검색 하려면이 메서드를 호출 합니다.

```
LONG QueryDWORDValue(
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
쿼리할 값의 이름을 포함하는 null-종단 문자열에 대한 포인터입니다.

*dw값*<br/>
DWORD를 받는 버퍼에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 ERROR_SUCCESS 반환됩니다. 메서드가 값을 읽지 못하면 WINERROR에 정의된 제로가 아닌 오류 코드를 반환합니다. H. 참조된 데이터가 REG_DWORD 형식이 아닌 경우 ERROR_INVALID_DATA 반환됩니다.

### <a name="remarks"></a>설명

이 메서드는 `RegQueryValueEx` 올바른 데이터 형식이 반환되는 지 확인하고 사용합니다. 자세한 내용은 [RegQueryValueEx를](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) 참조하십시오.

> [!IMPORTANT]
> 이 방법을 사용하면 호출자가 신뢰할 수 없는 데이터를 읽을 수 있는 레지스트리 위치를 지정할 수 있습니다. 또한 이 메서드에서 사용하는 [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) 함수는 NULL이 종료된 문자열을 명시적으로 처리하지 않습니다. 두 조건 모두 호출 코드에서 확인해야 합니다.

## <a name="cregkeyqueryguidvalue"></a><a name="queryguidvalue"></a>CRegKey::쿼리 GUID값

지정된 값 이름에 대 한 GUID 데이터를 검색 하려면이 메서드를 호출 합니다.

```
LONG QueryGUIDValue(
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
쿼리할 값의 이름을 포함하는 null-종단 문자열에 대한 포인터입니다.

*guidValue*<br/>
GUID를 받는 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 ERROR_SUCCESS 반환됩니다. 메서드가 값을 읽지 못하면 WINERROR에 정의된 제로가 아닌 오류 코드를 반환합니다. H. 참조된 데이터가 유효한 GUID가 아닌 경우 ERROR_INVALID_DATA 반환됩니다.

### <a name="remarks"></a>설명

이 메서드는 `CRegKey::QueryStringValue` [CLSIDFromString을](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring)사용 하 여 문자열을 사용 하 고 GUID로 변환 합니다.

> [!IMPORTANT]
> 이 방법을 사용하면 호출자가 신뢰할 수 없는 데이터를 읽을 수 있는 레지스트리 위치를 지정할 수 있습니다.

## <a name="cregkeyquerymultistringvalue"></a><a name="querymultistringvalue"></a>CRegKey::쿼리다중 문자열 값

지정된 값 이름에 대 한 다중 문자열 데이터를 검색 하려면이 메서드를 호출 합니다.

```
LONG QueryMultiStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
쿼리할 값의 이름을 포함하는 null-종단 문자열에 대한 포인터입니다.

*psz값*<br/>
다중 문자열 데이터를 받는 버퍼에 대한 포인터입니다. 다중 문자열은 두 개의 null 문자로 종료되는 null 종료된 문자열의 배열입니다.

*pnChars*<br/>
*szValue로*가리키는 버퍼의 TCHARs의 크기입니다. 메서드가 반환되면 *pnChars는* 종료 null 문자를 포함하여 검색된 다중 문자열의 TCHARs의 크기를 포함합니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 ERROR_SUCCESS 반환됩니다. 메서드가 값을 읽지 못하면 WINERROR에 정의된 제로가 아닌 오류 코드를 반환합니다. H. 참조된 데이터가 REG_MULTI_SZ 형식이 아닌 경우 ERROR_INVALID_DATA 반환됩니다.

### <a name="remarks"></a>설명

이 메서드는 `RegQueryValueEx` 올바른 데이터 형식이 반환되는 지 확인하고 사용합니다. 자세한 내용은 [RegQueryValueEx를](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) 참조하십시오.

> [!IMPORTANT]
> 이 방법을 사용하면 호출자가 신뢰할 수 없는 데이터를 읽을 수 있는 레지스트리 위치를 지정할 수 있습니다. 또한 이 메서드에서 사용하는 [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) 함수는 NULL이 종료된 문자열을 명시적으로 처리하지 않습니다. 두 조건 모두 호출 코드에서 확인해야 합니다.

## <a name="cregkeyqueryqwordvalue"></a><a name="queryqwordvalue"></a>CRegKey::쿼리QWORD값

지정된 값 이름에 대 한 QWORD 데이터를 검색 하려면이 메서드를 호출 합니다.

```
LONG QueryQWORDValue(
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
쿼리할 값의 이름을 포함하는 null-종단 문자열에 대한 포인터입니다.

*qw값*<br/>
QWORD를 받는 버퍼에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 ERROR_SUCCESS 반환됩니다. 메서드가 값을 읽지 못하면 WINERROR에 정의된 제로가 아닌 오류 코드를 반환합니다. H. 참조된 데이터가 REG_QWORD 형식이 아닌 경우 ERROR_INVALID_DATA 반환됩니다.

### <a name="remarks"></a>설명

이 메서드는 `RegQueryValueEx` 올바른 데이터 형식이 반환되는 지 확인하고 사용합니다. 자세한 내용은 [RegQueryValueEx를](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) 참조하십시오.

> [!IMPORTANT]
> 이 방법을 사용하면 호출자가 신뢰할 수 없는 데이터를 읽을 수 있는 레지스트리 위치를 지정할 수 있습니다. 또한 이 메서드에서 사용하는 [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) 함수는 NULL이 종료된 문자열을 명시적으로 처리하지 않습니다. 두 조건 모두 호출 코드에서 확인해야 합니다.

## <a name="cregkeyquerystringvalue"></a><a name="querystringvalue"></a>CRegKey::쿼리 문자열 값

지정된 값 이름에 대 한 문자열 데이터를 검색 하려면이 메서드를 호출 합니다.

```
LONG QueryStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
쿼리할 값의 이름을 포함하는 null-종단 문자열에 대한 포인터입니다.

*psz값*<br/>
문자열 데이터를 받는 버퍼에 대한 포인터입니다.

*pnChars*<br/>
*szValue로*가리키는 버퍼의 TCHARs의 크기입니다. 메서드가 반환되면 *pnChars에는* null 문자 종료를 포함하여 검색된 문자열의 TCHARs의 크기가 포함됩니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 ERROR_SUCCESS 반환됩니다. 메서드가 값을 읽지 못하면 WINERROR에 정의된 제로가 아닌 오류 코드를 반환합니다. H. 참조된 데이터가 REG_SZ 형식이 아닌 경우 ERROR_INVALID_DATA 반환됩니다. 메서드가 ERROR_MORE_DATA 반환하는 경우 *pnChars는* 바이트에서 필요한 버퍼 크기가 아니라 0과 같습니다.

### <a name="remarks"></a>설명

이 메서드는 `RegQueryValueEx` 올바른 데이터 형식이 반환되는 지 확인하고 사용합니다. 자세한 내용은 [RegQueryValueEx를](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) 참조하십시오.

> [!IMPORTANT]
> 이 방법을 사용하면 호출자가 신뢰할 수 없는 데이터를 읽을 수 있는 레지스트리 위치를 지정할 수 있습니다. 또한 이 메서드에서 사용하는 [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) 함수는 NULL이 종료된 문자열을 명시적으로 처리하지 않습니다. 두 조건 모두 호출 코드에서 확인해야 합니다.

## <a name="cregkeyqueryvalue"></a><a name="queryvalue"></a>CRegKey::쿼리 값

[m_hKey](#m_hkey)지정된 값 필드에 대 한 데이터를 검색 하려면이 메서드를 호출 합니다. 이 메서드의 이전 버전은 더 이상 지원되지 않으며 ATL_DEPRECATED 으로 표시됩니다.

```
LONG QueryValue(
    LPCTSTR pszValueName,
    DWORD* pdwType,
    void* pData,
    ULONG* pnBytes) throw();

ATL_DEPRECATED LONG QueryValue(
    DWORD& dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG QueryValue(
    LPTSTR szValue,
    LPCTSTR lpszValueName,
    DWORD* pdwCount);
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
쿼리할 값의 이름을 포함하는 null-종단 문자열에 대한 포인터입니다. *pszValueName이* NULL이거나 빈 문자열인 경우 """이면 메서드는 키의 이름이 지정되지 않은 값또는 기본값(있는 경우)에 대한 형식과 데이터를 검색합니다.

*pdwType*<br/>
지정된 값에 저장된 데이터 형식을 나타내는 코드를 받는 변수에 대한 포인터입니다. 형식 코드가 필요하지 않은 경우 *pdwType* 매개 변수가 NULL일 수 있습니다.

*Pdata*<br/>
값의 데이터를 받는 버퍼에 대한 포인터입니다. 데이터가 필요하지 않은 경우 이 매개 변수는 NULL일 수 있습니다.

*pn바이트*<br/>
*pData* 매개 변수가 가리키는 버퍼의 크기를 바이트로 지정하는 변수에 대한 포인터입니다. 메서드가 반환되면 이 변수에는 *pData에* 복사된 데이터의 크기가 포함됩니다.

*dw값*<br/>
값 필드의 숫자 데이터입니다.

*lpszValueName*<br/>
쿼리할 값 필드를 지정합니다.

*sz값*<br/>
값 필드의 문자열 데이터입니다.

*pdwCount*<br/>
문자열 데이터의 크기입니다. 해당 값은 처음에 *szValue* 버퍼의 크기로 설정됩니다.

### <a name="return-value"></a>Return Value

성공하면 ERROR_SUCCESS 반환합니다. 그렇지 않으면 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

두 원래 버전의 `QueryValue` 더 이상 지원 되지 않습니다 및 ATL_DEPRECATED 표시 됩니다. 컴파일러는 이러한 양식을 사용하는 경우 경고를 발행합니다.

나머지 메서드는 RegQueryValueEx를 호출합니다.

> [!IMPORTANT]
> 이 방법을 사용하면 호출자가 신뢰할 수 없는 데이터를 읽을 수 있는 레지스트리 위치를 지정할 수 있습니다. 또한 이 메서드에서 사용하는 RegQueryValueEx 함수는 NULL이 종료된 문자열을 명시적으로 처리하지 않습니다. 두 조건 모두 호출 코드에서 확인해야 합니다.

## <a name="cregkeyrecursedeletekey"></a><a name="recursedeletekey"></a>CRegKey::재저주삭제키

레지스트리에서 지정된 키를 제거하고 하위 키를 명시적으로 제거하려면 이 메서드를 호출합니다.

```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```

### <a name="parameters"></a>매개 변수

*lpszKey*<br/>
삭제할 키 이름을 지정합니다. 이 이름은 [m_hKey](#m_hkey).

### <a name="return-value"></a>Return Value

성공하면 ERROR_SUCCESS 반환합니다. 그렇지 않으면 WINERROR에 정의된 0이 아닌 오류 값입니다. H.

### <a name="remarks"></a>설명

키에 하위 키가 있는 경우 이 메서드를 호출하여 키를 삭제해야 합니다.

## <a name="cregkeysetbinaryvalue"></a><a name="setbinaryvalue"></a>CRegKey::설정 바이너리 값

레지스트리 키의 이진 값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetBinaryValue(
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
설정할 값의 이름이 포함된 문자열에 대한 포인터입니다. 이 이름의 값이 아직 없는 경우 메서드는 키에 추가합니다.

*pValue*<br/>
지정된 값 이름으로 저장할 데이터를 포함하는 버퍼에 대한 포인터입니다.

*n바이트*<br/>
*pValue* 매개 변수가 가리키는 정보의 크기를 바이트별로 지정합니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 반환 값은 ERROR_SUCCESS. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

이 메서드는 [RegSetValueEx를](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) 사용 하 여 레지스트리에 값을 작성 합니다.

## <a name="cregkeysetdwordvalue"></a><a name="setdwordvalue"></a>CRegKey::SetDword값

레지스트리 키의 DWORD 값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
설정할 값의 이름이 포함된 문자열에 대한 포인터입니다. 이 이름의 값이 아직 없는 경우 메서드는 키에 추가합니다.

*dw값*<br/>
지정된 값 이름으로 저장할 DWORD 데이터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 반환 값은 ERROR_SUCCESS. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

이 메서드는 [RegSetValueEx를](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) 사용 하 여 레지스트리에 값을 작성 합니다.

## <a name="cregkeysetguidvalue"></a><a name="setguidvalue"></a>CRegKey::설정GUID값

레지스트리 키의 GUID 값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
설정할 값의 이름이 포함된 문자열에 대한 포인터입니다. 이 이름의 값이 아직 없는 경우 메서드는 키에 추가합니다.

*guidValue*<br/>
지정된 값 이름으로 저장할 GUID를 참조합니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 반환 값은 ERROR_SUCCESS. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

이 메서드는 `CRegKey::SetStringValue` GUID를 사용하고 [StringFromGUID2를](/windows/win32/api/combaseapi/nf-combaseapi-stringfromguid2)사용하여 문자열로 변환합니다.

## <a name="cregkeysetkeyvalue"></a><a name="setkeyvalue"></a>CRegKey::SetKey값

지정된 키의 지정된 값 필드에 데이터를 저장 하려면이 메서드를 호출 합니다.

```
LONG SetKeyValue(
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*lpszKeyName*<br/>
만들거나 열 수 있는 키의 이름을 지정합니다. 이 이름은 [m_hKey](#m_hkey).

*lpsz값*<br/>
저장할 데이터를 지정합니다. 이 매개 변수는 NULL이 아닌 매개 변수여야 합니다.

*lpszValueName*<br/>
설정할 값 필드를 지정합니다. 이 이름의 값 필드가 키에 아직 없는 경우 추가됩니다.

### <a name="return-value"></a>Return Value

성공하면 ERROR_SUCCESS 반환합니다. 그렇지 않으면 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

*lpszKeyName 키를* 만들거나 열고 *lpszValue* 값 값 필드에 *lpszValue* 데이터를 저장 하려면이 메서드를 호출 합니다.

## <a name="cregkeysetkeysecurity"></a><a name="setkeysecurity"></a>CRegKey::SetKey보안

레지스트리 키의 보안을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```

### <a name="parameters"></a>매개 변수

*Si*<br/>
설정할 보안 설명자의 구성 요소를 지정합니다. 값은 다음 값의 조합일 수 있습니다.

|값|의미|
|-----------|-------------|
|DACL_SECURITY_INFORMATION|키의 임의 액세스 제어 목록(DACL)을 설정합니다. 키에 WRITE_DAC 액세스 권한이 있어야 하거나 호출 프로세스가 개체의 소유자여야 합니다.|
|GROUP_SECURITY_INFORMATION|키의 기본 그룹 보안 식별자(SID)를 설정합니다. 키에 WRITE_OWNER 액세스 권한이 있어야 하거나 호출 프로세스가 개체의 소유자여야 합니다.|
|OWNER_SECURITY_INFORMATION|키 소유자 SID를 설정합니다. 키에 WRITE_OWNER 액세스 권한이 있어야 하거나 호출 프로세스가 개체의 소유자이거나 SE_TAKE_OWNERSHIP_NAME 권한이 활성화되어 있어야 합니다.|
|SACL_SECURITY_INFORMATION|키의 시스템 액세스 제어 목록(SACL)을 설정합니다. 키에 ACCESS_SYSTEM_SECURITY 액세스 권한이 있어야 합니다. 이 액세스를 얻는 적절한 방법은 호출자의 현재 액세스 토큰에서 SE_SECURITY_NAME [권한을](/windows/win32/secauthz/privileges) 활성화하고 ACCESS_SYSTEM_SECURITY 액세스에 대한 핸들을 연 다음 권한을 사용하지 않도록 설정하는 것입니다.|

*Psd*<br/>
지정된 키에 대해 설정할 보안 특성을 지정하는 [SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 반환 값은 ERROR_SUCCESS. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

키의 보안 특성을 설정합니다. 자세한 내용은 [RegSetKeySecurity를](/windows/win32/api/winreg/nf-winreg-regsetkeysecurity) 참조하십시오.

## <a name="cregkeysetmultistringvalue"></a><a name="setmultistringvalue"></a>CRegKey::SetMultiString값

레지스트리 키의 다중 문자열 값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
설정할 값의 이름이 포함된 문자열에 대한 포인터입니다. 이 이름의 값이 아직 없는 경우 메서드는 키에 추가합니다.

*psz값*<br/>
지정된 값 이름으로 저장할 다중 문자열 데이터에 대한 포인터입니다. 다중 문자열은 두 개의 null 문자로 종료되는 null 종료된 문자열의 배열입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 반환 값은 ERROR_SUCCESS. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

이 메서드는 [RegSetValueEx를](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) 사용 하 여 레지스트리에 값을 작성 합니다.

## <a name="cregkeysetqwordvalue"></a><a name="setqwordvalue"></a>CRegKey::SetQword값

레지스트리 키의 QWORD 값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
설정할 값의 이름이 포함된 문자열에 대한 포인터입니다. 이 이름의 값이 아직 없는 경우 메서드는 키에 추가합니다.

*qw값*<br/>
지정된 값 이름으로 저장할 QWORD 데이터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 반환 값은 ERROR_SUCCESS. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

이 메서드는 [RegSetValueEx를](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) 사용 하 여 레지스트리에 값을 작성 합니다.

## <a name="cregkeysetstringvalue"></a><a name="setstringvalue"></a>CRegKey::SetString값

레지스트리 키의 문자열 값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetStringValue(
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
설정할 값의 이름이 포함된 문자열에 대한 포인터입니다. 이 이름의 값이 아직 없는 경우 메서드는 키에 추가합니다.

*psz값*<br/>
지정된 값 이름으로 저장할 문자열 데이터에 대한 포인터입니다.

*dwType*<br/>
레지스트리에 쓸 문자열의 유형(REG_SZ(기본값) 또는 REG_EXPAND_SZ(다중 문자열의 경우)입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 반환 값은 ERROR_SUCCESS. 메서드가 실패하면 반환 값은 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

이 메서드는 [RegSetValueEx를](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) 사용 하 여 레지스트리에 값을 작성 합니다.

## <a name="cregkeysetvalue"></a><a name="setvalue"></a>CRegKey::SetValue

m_hKey 지정된 값 필드에 데이터를 저장하려면 [m_hKey](#m_hkey)이 메서드를 호출합니다. 이 메서드의 이전 버전은 더 이상 지원되지 않으며 ATL_DEPRECATED 으로 표시됩니다.

```
LONG SetValue(
    LPCTSTR pszValueName,
    DWORD dwType,
    const void* pValue,
    ULONG nBytes) throw();

static LONG WINAPI SetValue(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL);

ATL_DEPRECATED LONG SetValue(
    DWORD dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG SetValue(
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL,
    bool bMulti = false,
    int nValueLen = -1);
```

### <a name="parameters"></a>매개 변수

*psz값 이름*<br/>
설정할 값의 이름이 포함된 문자열에 대한 포인터입니다. 이 이름의 값이 키에 아직 없는 경우 메서드는 키에 추가합니다. *pszValueName이* NULL이거나 빈 문자열인 ""인 경우 메서드는 키의 이름이 지정되지 않았거나 기본값에 대한 형식과 데이터를 설정합니다.

*dwType*<br/>
*pValue* 매개 변수가 가리키는 데이터 형식을 나타내는 코드를 지정합니다.

*pValue*<br/>
지정된 값 이름으로 저장할 데이터를 포함하는 버퍼에 대한 포인터입니다.

*n바이트*<br/>
*pValue* 매개 변수가 가리키는 정보의 크기를 바이트별로 지정합니다. 데이터가 REG_SZ, REG_EXPAND_SZ 또는 REG_MULTI_SZ 경우 *nBytes에는* null 문자 종료의 크기가 포함되어야 합니다.

*hKeyParent*<br/>
열린 키의 핸들입니다.

*lpszKeyName*<br/>
만들거나 열 수 있는 키의 이름을 지정합니다. 이 이름은 *hKeyParent*의 하위 키여야 합니다.

*lpsz값*<br/>
저장할 데이터를 지정합니다. 이 매개 변수는 NULL이 아닌 매개 변수여야 합니다.

*lpszValueName*<br/>
설정할 값 필드를 지정합니다. 이 이름의 값 필드가 키에 아직 없는 경우 추가됩니다.

*dw값*<br/>
저장할 데이터를 지정합니다.

*bMulti*<br/>
false이면 문자열이 형식 REG_SZ 나타냅니다. true이면 문자열이 REG_MULTI_SZ 형식의 다중 문자열임을 나타냅니다.

*n밸류렌*<br/>
*bMultitrue인* 경우 *nValueLen은* 문자의 *lpszValue* 문자열의 길이입니다. *bMulti가* false이면 -1 값은 메서드가 자동으로 길이를 계산한다는 것을 나타냅니다.

### <a name="return-value"></a>Return Value

성공하면 ERROR_SUCCESS 반환합니다. 그렇지 않으면 WINERROR에 정의된 제로가 아닌 오류 코드입니다. H.

### <a name="remarks"></a>설명

두 원래 버전의 `SetValue` ATL_DEPRECATED 표시 되어 더 이상 사용 하지 않아야 합니다. 컴파일러는 이러한 양식을 사용하는 경우 경고를 발행합니다.

세 번째 메서드는 [RegSetValueEx를](/windows/win32/api/winreg/nf-winreg-regsetvalueexw)호출합니다.

## <a name="see-also"></a>참조

[DCOM 샘플](../../overview/visual-cpp-samples.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
