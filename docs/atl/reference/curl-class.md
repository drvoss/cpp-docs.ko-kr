---
title: CUrl 클래스
ms.date: 05/06/2019
f1_keywords:
- CUrl
- ATLUTIL/ATL::CUrl
- ATLUTIL/ATL::CUrl::CUrl
- ATLUTIL/ATL::CUrl::Canonicalize
- ATLUTIL/ATL::CUrl::Clear
- ATLUTIL/ATL::CUrl::CrackUrl
- ATLUTIL/ATL::CUrl::CreateUrl
- ATLUTIL/ATL::CUrl::GetExtraInfo
- ATLUTIL/ATL::CUrl::GetExtraInfoLength
- ATLUTIL/ATL::CUrl::GetHostName
- ATLUTIL/ATL::CUrl::GetHostNameLength
- ATLUTIL/ATL::CUrl::GetPassword
- ATLUTIL/ATL::CUrl::GetPasswordLength
- ATLUTIL/ATL::CUrl::GetPortNumber
- ATLUTIL/ATL::CUrl::GetScheme
- ATLUTIL/ATL::CUrl::GetSchemeName
- ATLUTIL/ATL::CUrl::GetSchemeNameLength
- ATLUTIL/ATL::CUrl::GetUrlLength
- ATLUTIL/ATL::CUrl::GetUrlPath
- ATLUTIL/ATL::CUrl::GetUrlPathLength
- ATLUTIL/ATL::CUrl::GetUserName
- ATLUTIL/ATL::CUrl::GetUserNameLength
- ATLUTIL/ATL::CUrl::SetExtraInfo
- ATLUTIL/ATL::CUrl::SetHostName
- ATLUTIL/ATL::CUrl::SetPassword
- ATLUTIL/ATL::CUrl::SetPortNumber
- ATLUTIL/ATL::CUrl::SetScheme
- ATLUTIL/ATL::CUrl::SetSchemeName
- ATLUTIL/ATL::CUrl::SetUrlPath
- ATLUTIL/ATL::CUrl::SetUserName
helpviewer_keywords:
- CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
ms.openlocfilehash: 3468e17b031d0a72bc56d915c689fbe4c78859e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330479"
---
# <a name="curl-class"></a>CUrl 클래스

이 클래스는 URL을 나타냅니다. 기존 URL 문자열을 구문 분석하거나 처음부터 문자열을 빌드하든 다른 요소와 독립적으로 URL의 각 요소를 조작할 수 있습니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CUrl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[Url::Url](#curl)|생성자입니다.|
|[CUrl::~Url](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CUrl:::표준화](#canonicalize)|URL 문자열을 표준 형식으로 변환하려면 이 메서드를 호출합니다.|
|[Url::지우기](#clear)|이 메서드를 호출하여 모든 URL 필드를 지웁히 합니다.|
|[Url::균열](#crackurl)|URL을 디코딩하고 구문 분석하려면 이 메서드를 호출합니다.|
|[CUrl::만들기Url](#createurl)|URL을 만들려면 이 메서드를 호출합니다.|
|[Url::GetExtraInfo](#getextrainfo)|URL에서 추가 정보(예: *텍스트* 또는 *#텍스트)를*얻으려면 이 메서드를 호출합니다.|
|[Url::GetExtraInfoLength](#getextrainfolength)|URL에서 검색할 추가 정보(예: *텍스트* 또는 *#텍스트)의*길이를 얻으려면 이 메서드를 호출합니다.|
|[CUrl::GetHostName](#gethostname)|URL에서 호스트 이름을 얻으려면이 메서드를 호출 합니다.|
|[CUrl::GetHostNameLength](#gethostnamelength)|호스트 이름의 길이를 얻으려면이 메서드를 호출 합니다.|
|[Url::GetPassword](#getpassword)|URL에서 암호를 얻으려면이 메서드를 호출합니다.|
|[Url::Get암호길이](#getpasswordlength)|암호의 길이를 얻으려면이 메서드를 호출합니다.|
|[Url::겟포트 넘버](#getportnumber)|ATL_URL_PORT 관점에서 포트 번호를 얻으려면이 메서드를 호출합니다.|
|[Url::GetScheme](#getscheme)|URL 스키마를 얻으려면이 메서드를 호출합니다.|
|[CUrl::GetSchemeName](#getschemename)|URL 구성표 이름을 얻으려면이 메서드를 호출 합니다.|
|[CUrl::GetScheme네임길이](#getschemenamelength)|URL 구성표 이름의 길이를 얻으려면 이 메서드를 호출합니다.|
|[Url:::GetUrl길이](#geturllength)|URL 길이를 얻으려면이 메서드를 호출합니다.|
|[Url:::GetUrlPath](#geturlpath)|URL 경로를 얻으려면이 메서드를 호출합니다.|
|[Url::GetUrl패스길이](#geturlpathlength)|URL 경로 길이를 얻으려면이 메서드를 호출 합니다.|
|[CUrl::GetUserName](#getusername)|URL에서 사용자 이름을 얻으려면이 메서드를 호출 합니다.|
|[Url::GetUserNameLength](#getusernamelength)|사용자 이름의 길이를 얻으려면이 메서드를 호출 합니다.|
|[Url::SetExtraInfo](#setextrainfo)|이 메서드를 호출하여 URL의 추가 정보(예: *텍스트* 또는 *#텍스트)를*설정합니다.|
|[CUrl::세트호스트 이름](#sethostname)|호스트 이름을 설정 하려면이 메서드를 호출 합니다.|
|[Url::설정 암호](#setpassword)|암호를 설정하려면 이 메서드를 호출합니다.|
|[Url::세트포트 번호](#setportnumber)|이 메서드를 호출하여 포트 번호를 ATL_URL_PORT 식으로 설정합니다.|
|[Url::세트스킴](#setscheme)|URL 스키마를 설정하려면 이 메서드를 호출합니다.|
|[CUrl::세트계획이름](#setschemename)|이 메서드를 호출하여 URL 구성표 이름을 설정합니다.|
|[Url::SetUrlPath](#seturlpath)|URL 경로를 설정하려면 이 메서드를 호출합니다.|
|[CUrl::SetUserName](#setusername)|사용자 이름을 설정 하려면이 메서드를 호출 합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CUrl::연산자 =](#operator_eq)|지정된 `CUrl` 개체를 현재 `CUrl` 개체에 할당합니다.|

## <a name="remarks"></a>설명

`CUrl`을 사용하면 경로 또는 포트 번호와 같은 URL 필드를 조작할 수 있습니다. `CUrl`다음 양식의 URL을 이해합니다.

\<스키마\<>/ 사용자\<이름 \@ \<>:\<암호>\<호스트 이름 \<>: 포트 번호>/ UrlPath>ExtraInfo>

일부 필드는 선택 사항입니다. 예를 들어 다음 URL을 고려하십시오.

`http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents`

[CUrl::CrackUrl은](#crackurl) 다음과 같이 구문 분석합니다.

- 구성표: "http" 또는 [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)

- 사용자 이름: '사람'

- 암호: "비밀"

- 호스트 이름:`www.microsoft.com`"

- 포트번호: 80

- URL경로: "visualc/stuff.htm"

- 엑스트라 정보: "#contents"

UrlPath 필드(예:)를 조작하려면 [GetUrlPath,](#geturlpath) [GetUrlPathLength](#geturlpathlength)및 [SetUrlPath](#seturlpath)를 사용합니다. [CreateUrl을](#createurl) 사용하여 전체 URL 문자열을 만듭니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlutil.h

## <a name="curlcanonicalize"></a><a name="canonicalize"></a>CUrl:::표준화

URL 문자열을 표준 형식으로 변환하려면 이 메서드를 호출합니다.

```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
정식화를 제어하는 플래그입니다. 플래그가 지정되지 않은 경우(dwFlags = 0) 메서드는 모든 안전하지 않은 \\문자와 메타 시퀀스(예: .,\\., 및 \\...)를 변환하여 시퀀스를 이스케이프합니다.*dwFlags* *dwFlags는* 다음 값 중 하나가 될 수 있습니다.

- ATL_URL_BROWSER_MODE: "#" 또는 "" 다음으로 문자를 인코딩하거나 디코딩하지 않으며 ""다음의 후행 공백을 제거하지 않습니다. 이 값을 지정하지 않으면 전체 URL이 인코딩되고 후행 공백이 제거됩니다.

- ATL_URL _DECODE: URL을 구문 분석하기 전에 모든 %XX 시퀀스를 이스케이프 시퀀스를 포함한 문자로 변환합니다.

- _ENCODE_PERCENT ATL_URL: 발생한 백분율 표시를 인코딩합니다. 기본적으로 백분율 기호는 인코딩되지 않습니다.

- ATL_URL _ENCODE_SPACES_ONLY: 공백만 인코딩합니다.

- ATL_URL _NO_ENCODE: 안전하지 않은 문자를 이스케이프 시퀀스로 변환하지 않습니다.

- ATL_URL _NO_META: URL에서 메타 시퀀스(예: "." 및 "..")를 제거하지 않습니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

표준 형식으로 변환하려면 안전하지 않은 문자와 공백을 시퀀스이 이스케이프시퀀스로 변환해야 합니다.

## <a name="curlclear"></a><a name="clear"></a>Url::지우기

이 메서드를 호출하여 모든 URL 필드를 지웁히 합니다.

```
inline void Clear() throw();
```

## <a name="curlcrackurl"></a><a name="crackurl"></a>Url::균열

URL을 디코딩하고 구문 분석하려면 이 메서드를 호출합니다.

```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>매개 변수

*lpszUrl*<br/>
URL입니다.

*dwFlags*<br/>
ATL_URL_DECODE 또는 ATL_URL_ESCAPE 지정하여 구문 분석 후 *lpszUrl의* 모든 이스케이프 문자를 실제 값으로 변환합니다. (Visual C++ 2005 이전에는 ATL_URL_DECODE 구문 분석하기 전에 모든 이스케이프 문자를 변환했습니다.)

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="curlcreateurl"></a><a name="createurl"></a>CUrl::만들기Url

이 메서드는 CUrl 개체의 구성 요소 필드에서 URL 문자열을 생성합니다.

```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```

### <a name="parameters"></a>매개 변수

*lpszUrl*<br/>
전체 URL 문자열을 보유하는 문자열 버퍼입니다.

*pdwMaxLength*<br/>
*lpszUrl* 문자열 버퍼의 최대 길이입니다.

*dwFlags*<br/>
*lpszUrl의* 모든 이스케이프 문자를 실제 값으로 변환할 ATL_URL_ESCAPE 지정합니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

이 메서드는 다음 형식을 사용 하 여 전체 URL 문자열을 구성 하기 위해 개별 필드를 적용 합니다.

**\<스키마\<> /\<사용자 \@ \<>\<: \<>\<도메인> 통과 : 포트>경로>추가>**

이 메서드를 호출할 때 *pdwMaxLength* 매개 변수는 처음에 *lpszUrl* 매개 변수에서 참조하는 문자열 버퍼의 최대 길이를 포함해야 합니다. *pdwMaxLength* 매개 변수의 값은 URL 문자열의 실제 길이로 업데이트됩니다.

### <a name="example"></a>예제

이 샘플에서는 CUrl 개체를 만들고 URL 문자열을 검색하는 것을 보여 줍니다.

[!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]

## <a name="curlcurl"></a><a name="curl"></a>Url::Url

생성자입니다.

```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```

### <a name="parameters"></a>매개 변수

*URL*<br/>
`CUrl` 복사하여 URL을 만들 개체입니다.

## <a name="curlcurl"></a><a name="dtor"></a>CUrl::~Url

소멸자입니다.

```
~CUrl() throw();
```

## <a name="curlgetextrainfo"></a><a name="getextrainfo"></a>Url::GetExtraInfo

URL에서 추가 정보(예: *텍스트* 또는 *#텍스트)를*얻으려면 이 메서드를 호출합니다.

```
inline LPCTSTR GetExtraInfo() const throw();
```

### <a name="return-value"></a>Return Value

추가 정보가 포함된 문자열을 반환합니다.

## <a name="curlgetextrainfolength"></a><a name="getextrainfolength"></a>Url::GetExtraInfoLength

URL에서 검색할 추가 정보(예: *텍스트* 또는 *#텍스트)의*길이를 얻으려면 이 메서드를 호출합니다.

```
inline DWORD GetExtraInfoLength() const throw();
```

### <a name="return-value"></a>Return Value

추가 정보가 포함된 문자열의 길이를 반환합니다.

## <a name="curlgethostname"></a><a name="gethostname"></a>CUrl::GetHostName

URL에서 호스트 이름을 얻으려면이 메서드를 호출 합니다.

```
inline LPCTSTR GetHostName() const throw();
```

### <a name="return-value"></a>Return Value

호스트 이름을 반환합니다.

## <a name="curlgethostnamelength"></a><a name="gethostnamelength"></a>CUrl::GetHostNameLength

호스트 이름의 길이를 얻으려면이 메서드를 호출 합니다.

```
inline DWORD GetHostNameLength() const throw();
```

### <a name="return-value"></a>Return Value

호스트 이름 길이를 반환합니다.

## <a name="curlgetpassword"></a><a name="getpassword"></a>Url::GetPassword

URL에서 암호를 얻으려면이 메서드를 호출합니다.

```
inline LPCTSTR GetPassword() const throw();
```

### <a name="return-value"></a>Return Value

암호를 반환합니다.

## <a name="curlgetpasswordlength"></a><a name="getpasswordlength"></a>Url::Get암호길이

암호의 길이를 얻으려면이 메서드를 호출합니다.

```
inline DWORD GetPasswordLength() const throw();
```

### <a name="return-value"></a>Return Value

암호 길이를 반환합니다.

## <a name="curlgetportnumber"></a><a name="getportnumber"></a>Url::겟포트 넘버

포트 번호를 얻으려면이 메서드를 호출합니다.

```
inline ATL_URL_PORT GetPortNumber() const throw();
```

### <a name="return-value"></a>Return Value

포트 번호를 반환합니다.

## <a name="curlgetscheme"></a><a name="getscheme"></a>Url::GetScheme

URL 스키마를 얻으려면이 메서드를 호출합니다.

```
inline ATL_URL_SCHEME GetScheme() const throw();
```

### <a name="return-value"></a>Return Value

URL의 구성표를 설명하는 [ATL_URL_SCHEME](atl-url-scheme-enum.md) 값을 반환합니다.

## <a name="curlgetschemename"></a><a name="getschemename"></a>CUrl::GetSchemeName

URL 구성표 이름을 얻으려면이 메서드를 호출 합니다.

```
inline LPCTSTR GetSchemeName() const throw();
```

### <a name="return-value"></a>Return Value

URL 구성표 이름(예: "http" 또는 "ftp")을 반환합니다.

## <a name="curlgetschemenamelength"></a><a name="getschemenamelength"></a>CUrl::GetScheme네임길이

URL 구성표 이름의 길이를 얻으려면 이 메서드를 호출합니다.

```
inline DWORD GetSchemeNameLength() const throw();
```

### <a name="return-value"></a>Return Value

URL 구성표 이름 길이를 반환합니다.

## <a name="curlgeturllength"></a><a name="geturllength"></a>Url:::GetUrl길이

URL 길이를 얻으려면이 메서드를 호출합니다.

```
inline DWORD GetUrlLength() const throw();
```

### <a name="return-value"></a>Return Value

URL 길이를 반환합니다.

## <a name="curlgeturlpath"></a><a name="geturlpath"></a>Url:::GetUrlPath

URL 경로를 얻으려면이 메서드를 호출합니다.

```
inline LPCTSTR GetUrlPath() const throw();
```

### <a name="return-value"></a>Return Value

URL 경로를 반환합니다.

## <a name="curlgeturlpathlength"></a><a name="geturlpathlength"></a>Url::GetUrl패스길이

URL 경로 길이를 얻으려면이 메서드를 호출 합니다.

```
inline DWORD GetUrlPathLength() const throw();
```

### <a name="return-value"></a>Return Value

URL 경로 길이를 반환합니다.

## <a name="curlgetusername"></a><a name="getusername"></a>CUrl::GetUserName

URL에서 사용자 이름을 얻으려면이 메서드를 호출 합니다.

```
inline LPCTSTR GetUserName() const throw();
```

### <a name="return-value"></a>Return Value

사용자 이름을 반환합니다.

## <a name="curlgetusernamelength"></a><a name="getusernamelength"></a>Url::GetUserNameLength

사용자 이름의 길이를 얻으려면이 메서드를 호출 합니다.

```
inline DWORD GetUserNameLength() const throw();
```

### <a name="return-value"></a>Return Value

사용자 이름 길이를 반환합니다.

## <a name="curloperator-"></a><a name="operator_eq"></a>CUrl::연산자 =

지정된 `CUrl` 개체를 현재 `CUrl` 개체에 할당합니다.

```
CUrl& operator= (const CUrl& urlThat) throw();
```

### <a name="parameters"></a>매개 변수

*URL*<br/>
현재 `CUrl` 개체에 복사할 개체입니다.

### <a name="return-value"></a>Return Value

현재 개체에 대한 참조를 반환합니다.

## <a name="curlsetextrainfo"></a><a name="setextrainfo"></a>Url::SetExtraInfo

이 메서드를 호출하여 URL의 추가 정보(예: *텍스트* 또는 *#텍스트)를*설정합니다.

```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```

### <a name="parameters"></a>매개 변수

*lpsz정보*<br/>
URL에 포함할 추가 정보가 포함된 문자열입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="curlsethostname"></a><a name="sethostname"></a>CUrl::세트호스트 이름

호스트 이름을 설정 하려면이 메서드를 호출 합니다.

```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```

### <a name="parameters"></a>매개 변수

*lpszHost*<br/>
호스트 이름입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="curlsetpassword"></a><a name="setpassword"></a>Url::설정 암호

암호를 설정하려면 이 메서드를 호출합니다.

```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```

### <a name="parameters"></a>매개 변수

*lpszPass*<br/>
암호입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="curlsetportnumber"></a><a name="setportnumber"></a>Url::세트포트 번호

이 메서드를 호출하여 포트 번호를 설정합니다.

```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```

### <a name="parameters"></a>매개 변수

*nPrt*<br/>
포트 번호.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="curlsetscheme"></a><a name="setscheme"></a>Url::세트스킴

URL 스키마를 설정하려면 이 메서드를 호출합니다.

```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```

### <a name="parameters"></a>매개 변수

*n계획*<br/>
스키마에 대한 [ATL_URL_SCHEME](atl-url-scheme-enum.md) 값 중 하나입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

또한 이름으로 구성표를 설정할 수도 [있습니다(CUrl:SetSchemeName](#setschemename)참조).

## <a name="curlsetschemename"></a><a name="setschemename"></a>CUrl::세트계획이름

이 메서드를 호출하여 URL 구성표 이름을 설정합니다.

```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```

### <a name="parameters"></a>매개 변수

*lpszSchm*<br/>
URL 구성표 이름입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

[ATL_URL_SCHEME](atl-url-scheme-enum.md) 상수를 사용하여 구성표를 설정할 수도 [있습니다(CUrl:SetScheme](#setscheme)참조).

## <a name="curlseturlpath"></a><a name="seturlpath"></a>Url::SetUrlPath

URL 경로를 설정하려면 이 메서드를 호출합니다.

```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```

### <a name="parameters"></a>매개 변수

*lpszPath*<br/>
URL 경로입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="curlsetusername"></a><a name="setusername"></a>CUrl::SetUserName

사용자 이름을 설정 하려면이 메서드를 호출 합니다.

```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```

### <a name="parameters"></a>매개 변수

*lpszUser*<br/>
사용자 이름입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="see-also"></a>참고 항목

[클래스](../../atl/reference/atl-classes.md)
