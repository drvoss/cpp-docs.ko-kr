---
title: C인터넷세션 클래스
ms.date: 06/20/2018
f1_keywords:
- CInternetSession
- AFXINET/CInternetSession
- AFXINET/CInternetSession::CInternetSession
- AFXINET/CInternetSession::Close
- AFXINET/CInternetSession::EnableStatusCallback
- AFXINET/CInternetSession::GetContext
- AFXINET/CInternetSession::GetCookie
- AFXINET/CInternetSession::GetCookieLength
- AFXINET/CInternetSession::GetFtpConnection
- AFXINET/CInternetSession::GetGopherConnection
- AFXINET/CInternetSession::GetHttpConnection
- AFXINET/CInternetSession::OnStatusCallback
- AFXINET/CInternetSession::OpenURL
- AFXINET/CInternetSession::SetCookie
- AFXINET/CInternetSession::SetOption
helpviewer_keywords:
- CInternetSession [MFC], CInternetSession
- CInternetSession [MFC], Close
- CInternetSession [MFC], EnableStatusCallback
- CInternetSession [MFC], GetContext
- CInternetSession [MFC], GetCookie
- CInternetSession [MFC], GetCookieLength
- CInternetSession [MFC], GetFtpConnection
- CInternetSession [MFC], GetGopherConnection
- CInternetSession [MFC], GetHttpConnection
- CInternetSession [MFC], OnStatusCallback
- CInternetSession [MFC], OpenURL
- CInternetSession [MFC], SetCookie
- CInternetSession [MFC], SetOption
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
ms.openlocfilehash: ddd7ca6676805e6de1b7afb5ebc77733701dfef9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372387"
---
# <a name="cinternetsession-class"></a>C인터넷세션 클래스

한 개 또는 여러 개의 동시 인터넷 세션을 만들어 초기화하며, 필요한 경우 프록시 서버에 대한 연결을 설명합니다.

## <a name="syntax"></a>구문

```cpp
class CInternetSession : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C인터넷세션::C인터넷세션](#cinternetsession)|`CInternetSession` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C인터넷세션::닫기](#close)|인터넷 세션이 종료되면 인터넷 연결을 닫습니다.|
|[C인터넷세션::인에이블스테이블스테이터스콜백](#enablestatuscallback)|상태 콜백 루틴을 설정합니다.|
|[C인터넷세션::GetContext](#getcontext)|인터넷 세션이 종료되면 인터넷 연결을 닫습니다.|
|[C인터넷세션::겟쿠키](#getcookie)|지정된 URL 및 모든 상위 URL에 대한 쿠키를 반환합니다.|
|[C인터넷세션::겟쿠키길이](#getcookielength)|버퍼에 저장된 쿠키의 길이를 지정하는 변수를 검색합니다.|
|[C인터넷세션::겟프트연결](#getftpconnection)|서버가 있는 FTP 세션을 엽니다. 사용자에 로그합니다.|
|[C인터넷세션::겟고퍼커넥션](#getgopherconnection)|연결을 열려는 응용 프로그램에 대한 gopher 서버를 엽니다.|
|[C인터넷세션::GetHttpConnection](#gethttpconnection)|연결을 열려는 응용 프로그램에 대한 HTTP 서버를 엽니다.|
|[C인터넷세션::온스테이콜백](#onstatuscallback)|상태 콜백이 활성화되어 있을 때 작업 상태를 업데이트합니다.|
|[C인터넷세션::오픈URL](#openurl)|URL을 구문 분석하고 엽니다.|
|[C인터넷세션::세트쿠키](#setcookie)|지정된 URL에 대한 쿠키를 설정합니다.|
|[C인터넷세션::세트옵션](#setoption)|인터넷 세션에 대한 옵션을 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C인터넷세션::운영자 HINTERNET](#operator_hinternet)|현재 인터넷 세션에 대한 핸들입니다.|

## <a name="remarks"></a>설명

응용 프로그램 기간 동안 인터넷 연결을 유지해야 하는 경우 `CInternetSession` [CWinApp](../../mfc/reference/cwinapp-class.md)클래스의 멤버를 만들 수 있습니다.

인터넷 세션을 설정하면 [OpenURL](#openurl)을 호출할 수 있습니다. `CInternetSession`그런 다음 전역 함수 [AfxParseURL을](internet-url-parsing-globals.md#afxparseurl)호출하여 URL을 구문 분석합니다. 프로토콜 유형에 관계없이 `CInternetSession` URL을 해석하고 관리합니다. URL 리소스 "file://"로 식별된 로컬 파일에 대한 요청을 처리할 수 있습니다. `OpenURL`전달하는 이름이 로컬 파일인 경우 [CStdioFile](../../mfc/reference/cstdiofile-class.md) 개체에 대한 포인터를 반환합니다.

을 사용하여 `OpenURL`인터넷 서버에서 URL을 열면 사이트에서 정보를 읽을 수 있습니다. 서버에 있는 파일에 대해 서비스별(예: HTTP, FTP 또는 고퍼) 작업을 수행하려면 해당 서버와 적절한 연결을 설정해야 합니다. 특정 서비스에 직접 연결의 특정 종류를 열려면 다음 멤버 기능 중 하나를 사용하십시오.

- [GetGopher연결은](#getgopherconnection) 고퍼 서비스에 대한 연결을 엽니다.

- HTTP 서비스에 대한 연결을 열려면 [GetHttpConnection입니다.](#gethttpconnection)

- [GETFtpConnectionFTP](#getftpconnection) 서비스에 대한 연결을 엽니다.

[SetOption을](#setoption) 사용하면 시간 시간 시간 값, 재시도 횟수 등과 같은 세션의 쿼리 옵션을 설정할 수 있습니다.

`CInternetSession`멤버 함수 [SetCookie,](#setcookie) [GetCookie](#getcookie)및 [GetCookieLength는](#getcookielength) 서버와 스크립트가 클라이언트 워크스테이션에 대한 상태 정보를 유지 관리하는 Win32 쿠키 데이터베이스를 관리하는 수단을 제공합니다.

기본 인터넷 프로그래밍 작업에 대한 자세한 내용은 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md)을 참조하십시오. MFC WinInet 클래스 사용에 대한 일반적인 내용은 [위니넷과 함께](../../mfc/win32-internet-extensions-wininet.md)하는 인터넷 프로그래밍 문서를 참조하십시오.

> [!NOTE]
> `CInternetSession`지원되지 않는 서비스 유형에 대해 [AfxThrowNot지원예외를](exception-processing.md#afxthrownotsupportedexception) throw합니다. FTP, HTTP, 고퍼 및 파일: 현재 는 다음과 같은 서비스 형식만 지원됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;`CInternetSession`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="cinternetsessioncinternetsession"></a><a name="cinternetsession"></a>C인터넷세션::C인터넷세션

이 멤버 함수는 `CInternetSession` 개체를 만들 때 호출됩니다.

```cpp
CInternetSession(
    LPCTSTR pstrAgent = NULL,
    DWORD_PTR dwContext = 1,
    DWORD dwAccessType = PRE_CONFIG_INTERNET_ACCESS,
    LPCTSTR pstrProxyName = NULL,
    LPCTSTR pstrProxyBypass = NULL,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>매개 변수

*pstrAgent*<br/>
인터넷 함수를 호출하는 응용 프로그램 또는 엔터티의 이름을 식별하는 문자열에 대한 포인터입니다(예: "Microsoft 인터넷 브라우저"). *pstrAgent가* NULL(기본값)인 경우 프레임워크는 응용 프로그램의 이름을 포함하는 null 종료 문자열을 반환하는 전역 함수 [AfxGetAppName을](application-information-and-management.md#afxgetappname)호출합니다. 일부 프로토콜은 이 문자열을 사용하여 서버에 대한 응용 프로그램을 식별합니다.

*dwContext*<br/>
작업에 대 한 컨텍스트 식별자입니다. *dwContext는* [CInternetSession::OnStatusCallback](#onstatuscallback)에서 반환된 작업의 상태 정보를 식별합니다. 기본값은 1로 설정됩니다. 그러나 작업에 대 한 특정 컨텍스트 ID를 명시적으로 할당할 수 있습니다. 개체 및 개체가 수행하는 모든 작업은 해당 컨텍스트 ID와 연결됩니다.

*dwAccessType*<br/>
필요한 액세스 유형입니다. 다음은 유효한 값이며, 그 중 하나가 제공될 수 있습니다.

- INTERNET_OPEN_TYPE_PRECONFIG 레지스트리에서 미리 구성된 설정을 사용하여 연결합니다. 이 액세스 유형은 기본값으로 설정됩니다. TIS 프록시를 통해 연결하려면 *dwAccessType을* 이 값으로 설정합니다. 레지스트리를 적절하게 설정합니다.

- INTERNET_OPEN_TYPE_DIRECT 인터넷에 직접 연결합니다.

- INTERNET_OPEN_TYPE_PROXY CERN 프록시를 통해 연결합니다.

다양한 유형의 프록시와 연결하는 방법에 대한 자세한 내용은 [일반적인 FTP 클라이언트 응용 프로그램의 단계를](../../mfc/steps-in-a-typical-ftp-client-application.md)참조하십시오.

*pstrProxyName*<br/>
*dwAccessType이* INTERNET_OPEN_TYPE_PROXY 설정된 경우 기본 CERN 프록시의 이름입니다. 기본값은 NULL입니다.

*pstrProxy우회*<br/>
선택적 서버 주소 목록이 포함된 문자열에 대한 포인터입니다. 이러한 주소는 프록시 액세스를 사용할 때 우회될 수 있습니다. NULL 값이 제공되면 레지스트리에서 바이패스 목록을 읽습니다. 이 매개 변수는 *dwAccessType이* INTERNET_OPEN_TYPE_PROXY 설정된 경우에만 의미가 있습니다.

*dwFlags*<br/>
다양한 캐싱 옵션을 나타냅니다. 기본값은 0으로 설정됩니다. 가능한 값은 다음과 같습니다.

- INTERNET_FLAG_DONT_CACHE 로컬 또는 게이트웨이 서버에서 데이터를 캐시하지 마십시오.

- INTERNET_FLAG_OFFLINE 다운로드 작업은 영구 캐시를 통해서만 충족됩니다. 항목이 캐시에 없으면 적절한 오류 코드가 반환됩니다. 이 플래그는 비트별 **OR(&#124;) **연산자와 결합될 수 있다. **OR**

### <a name="remarks"></a>설명

`CInternetSession`는 응용 프로그램에서 호출하는 첫 번째 인터넷 함수입니다. 내부 데이터 구조를 초기화하고 응용 프로그램에서 향후 호출을 준비합니다.

인터넷 연결을 열 수 `CInternetSession` 없는 경우 [AfxThrowInternetException을](internet-url-parsing-globals.md#afxthrowinternetexception)throw합니다.

### <a name="example"></a>예제

[CFtpFileFind에](../../mfc/reference/cftpfilefind-class.md)대한 예제를 참조하십시오.

## <a name="cinternetsessionclose"></a><a name="close"></a>C인터넷세션::닫기

응용 프로그램이 개체 사용을 완료하면 `CInternetSession` 이 멤버 함수를 호출합니다.

```cpp
virtual void Close();
```

### <a name="example"></a>예제

[CFtpFileFind에](../../mfc/reference/cftpfilefind-class.md)대한 예제를 참조하십시오.

## <a name="cinternetsessionenablestatuscallback"></a><a name="enablestatuscallback"></a>C인터넷세션::인에이블스테이블스테이터스콜백

상태 콜백을 활성화하려면 이 멤버 함수를 호출합니다.

```cpp
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
콜백이 활성화되어 있는지 또는 사용하지 않도록 설정했는지 여부를 지정합니다. 기본값은 TRUE입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출이 실패하면 throw된 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체를 검사하여 오류의 원인을 확인합니다.

### <a name="remarks"></a>설명

상태 콜백을 처리할 때 응용 프로그램의 상태 표시줄에서 작업 진행 률(예: 이름 확인, 서버 연결 등)에 대한 상태를 제공할 수 있습니다. 장기 작업 중에 작업 상태를 표시하는 것이 특히 바람직합니다.

콜백은 요청 처리 중에 발생하므로 응용 프로그램은 네트워크에 대한 데이터 처리량의 저하를 방지하기 위해 콜백에서 가능한 한 적은 시간을 소비해야 합니다. 예를 들어 콜백에 대화 상자를 배치하는 것은 서버가 요청을 종료하는 작업이 길어질 수 있습니다.

콜백이 보류 중인 경우 상태 콜백을 제거할 수 없습니다.

모든 작업을 비동기적으로 처리하려면 고유한 스레드를 만들거나 MFC 없이 WinInet 함수를 사용해야 합니다.

## <a name="cinternetsessiongetcontext"></a><a name="getcontext"></a>C인터넷세션::GetContext

이 멤버 함수를 호출하여 특정 응용 프로그램 세션에 대한 컨텍스트 값을 가져옵니다.

```cpp
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Return Value

응용 프로그램 정의 컨텍스트 식별자입니다.

### <a name="remarks"></a>설명

[OnStatusCallback](#onstatuscallback) 특정 응용 프로그램의 `GetContext` 상태를 보고 하기 위해 반환 된 컨텍스트 ID를 사용 합니다. 예를 들어 사용자가 상태 정보를 반환하는 인터넷 요청을 활성화하면 상태 콜백은 컨텍스트 ID를 사용하여 특정 요청에 대한 상태를 보고합니다. 사용자가 상태 정보를 반환하는 두 개의 별도 인터넷 `OnStatusCallback` 요청을 활성화하는 경우 컨텍스트 식별자를 사용하여 해당 요청에 대한 상태를 반환합니다. 따라서 컨텍스트 식별자는 모든 상태 콜백 작업에 사용되며 세션이 종료될 때까지 세션과 연결됩니다.

비동기 작업에 대한 자세한 내용은 인터넷 [첫 번째 단계: WinInet](../../mfc/wininet-basics.md)을 참조하십시오.

## <a name="cinternetsessiongetcookie"></a><a name="getcookie"></a>C인터넷세션::겟쿠키

이 멤버 함수는 Windows SDK에 설명된 대로 Win32 함수 [InternetGetCookie의](/windows/win32/api/wininet/nf-wininet-internetgetcookiew)동작을 구현합니다.

```cpp
static BOOL GetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPTSTR pstrCookieData,
    DWORD dwBufLen);

static BOOL GetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    CString& strCookieData);
```

### <a name="parameters"></a>매개 변수

*pstrUrl*<br/>
URL을 포함하는 문자열에 대한 포인터입니다.

*pstrCookieName*<br/>
지정된 URL에 대해 얻을 쿠키의 이름을 포함하는 문자열에 대한 포인터입니다.

*pstrCookieData*<br/>
첫 번째 오버로드에서 쿠키 데이터를 수신하는 버퍼의 주소를 포함하는 문자열에 대한 포인터입니다. 이 값은 NULL일 수 있습니다. 두 번째 오버로드에서 쿠키 데이터를 수신하는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 대한 참조입니다.

*dwBufLen*<br/>
*pstrCookieData* 버퍼의 크기를 지정하는 변수입니다. 함수가 성공하면 버퍼는 *pstrCookieData* 버퍼에 복사된 데이터의 양을 받습니다. *pstrCookieData가* NULL이면 이 매개 변수는 모든 쿠키 데이터를 복사하는 데 필요한 버퍼의 크기를 지정하는 값을 받습니다.

### <a name="return-value"></a>Return Value

성공하지 않은 경우 TRUE를 반환하거나 FALSE를 반환합니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인합니다. 다음 오류 값이 적용됩니다.

- ERROR_NO_MORE_ITEMS 지정된 URL과 모든 부모에 대한 쿠키가 없습니다.

- ERROR_INSUFFICIENT_BUFFER *dwBufLen에* 전달된 값은 모든 쿠키 데이터를 복사하기에 충분하지 않습니다. *dwBufLen에서* 반환되는 값은 모든 데이터를 얻는 데 필요한 버퍼의 크기입니다.

### <a name="remarks"></a>설명

두 번째 오버로드에서 MFC는 쿠키 데이터를 `CString` 제공된 개체로 검색합니다.

## <a name="cinternetsessiongetcookielength"></a><a name="getcookielength"></a>C인터넷세션::겟쿠키길이

이 멤버 함수를 호출하여 버퍼에 저장된 쿠키의 길이를 가져옵니다.

```cpp
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName);
```

### <a name="parameters"></a>매개 변수

*pstrUrl*<br/>
URL이 포함된 문자열에 대한 포인터

*pstrCookieName*<br/>
쿠키의 이름을 포함하는 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

버퍼에 저장된 쿠키의 길이를 나타내는 DWORD 값입니다. *pstrCookieName으로* 표시된 이름의 쿠키가 없으면 0입니다.

### <a name="remarks"></a>설명

이 값은 [GetCookie](#getcookie)에서 사용됩니다.

## <a name="cinternetsessiongetftpconnection"></a><a name="getftpconnection"></a>C인터넷세션::겟프트연결

FTP 연결을 설정하고 개체에 대한 포인터를 얻으려면 `CFtpConnection` 이 멤버 함수를 호출합니다.

```cpp
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
```

### <a name="parameters"></a>매개 변수

*pstrServer*<br/>
FTP 서버 이름을 포함하는 문자열에 대한 포인터입니다.

*pstrUserName*<br/>
로그인할 사용자의 이름을 지정하는 null-종료된 문자열에 대한 포인터입니다. NULL인 경우 기본값은 익명입니다.

*pstrPassword*<br/>
로그인하는 데 사용할 암호를 지정하는 null 종료된 문자열에 대한 포인터입니다. *pstrPassword와* *pstrUserName* 모두 NULL인 경우 기본 익명 암호는 사용자의 전자 메일 이름입니다. *pstrPassword가* NULL(또는 빈 문자열)이지만 *pstrUserName이* NULL이 아닌 경우 빈 암호가 사용됩니다. 다음 표는 *pstrUserName* 및 *pstrPassword의*네 가지 가능한 설정에 대한 동작에 대해 설명합니다.

| *pstrUserName*  | *pstrPassword*  | FTP 서버로 전송된 사용자 이름 | FTP 서버로 전송된 암호 |
|-----------------|-----------------|-----------------------------|-----------------------------|
|   NULL 또는 " "   |   NULL 또는 " "   |         "anonymous"         |      사용자의 이메일 이름      |
| NULL이 아닌 문자열 |   NULL 또는 " "   |       *pstrUserName*        |             " "             |
|      NULL       | NULL이 아닌 문자열 |            오류            |            오류            |
| NULL이 아닌 문자열 | NULL이 아닌 문자열 |       *pstrUserName*        |       *pstrPassword*        |

*nPort*<br/>
서버에서 사용할 TCP/IP 포트를 식별하는 숫자입니다.

*bPassive*<br/>
이 FTP 세션에 대한 수동 또는 활성 모드를 지정합니다. TRUE로 설정하면 Win32 API를 `dwFlag` INTERNET_FLAG_PASSIVE 설정합니다.

### <a name="return-value"></a>Return Value

[CFtpConnection](../../mfc/reference/cftpconnection-class.md) 개체에 대한 포인터입니다. 호출이 실패하면 throw된 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체를 검사하여 오류의 원인을 확인합니다.

### <a name="remarks"></a>설명

`GetFtpConnection`대/달러 서버에 연결하고 개체에 대한 포인터를 `CFTPConnection` 만들고 반환합니다. 서버에서 특정 작업을 수행하지 않습니다. 예를 들어 파일을 읽거나 쓰려면 이러한 작업을 별도의 단계로 수행해야 합니다. 파일 검색, 파일 열기 및 파일에 대한 읽기 또는 쓰기에 대한 자세한 내용은 [클래스 CFtpConnection](../../mfc/reference/cftpconnection-class.md) 및 [CFtpFileFind를](../../mfc/reference/cftpfilefind-class.md) 참조하십시오. 일반적인 FTP 연결 작업을 수행하는 단계는 [WinInet의 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md) 문서를 참조하십시오.

### <a name="example"></a>예제

[CFtpFileFind에](../../mfc/reference/cftpfilefind-class.md)대한 예제를 참조하십시오.

## <a name="cinternetsessiongetgopherconnection"></a><a name="getgopherconnection"></a>C인터넷세션::겟고퍼커넥션

이 멤버 함수를 호출하여 새 고퍼 연결을 `CGopherConnection` 설정하고 개체에 대한 포인터를 가져옵니다.

```cpp
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>매개 변수

*pstrServer*<br/>
고퍼 서버 이름이 포함된 문자열에 대한 포인터입니다.

*pstrUserName*<br/>
사용자 이름을 포함하는 문자열에 대한 포인터입니다.

*pstrPassword*<br/>
액세스 암호를 포함하는 문자열에 대한 포인터입니다.

*nPort*<br/>
서버에서 사용할 TCP/IP 포트를 식별하는 숫자입니다.

### <a name="return-value"></a>Return Value

[CGopherConnection](../../mfc/reference/cgopherconnection-class.md) 개체에 대한 포인터입니다. 호출이 실패하면 throw된 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체를 검사하여 오류의 원인을 확인합니다.

### <a name="remarks"></a>설명

`GetGopherConnection`을 클릭하면 고퍼 서버에 연결하고 개체에 대한 `CGopherConnection` 포인터를 만들고 반환합니다. 서버에서 특정 작업을 수행하지 않습니다. 예를 들어 데이터를 읽거나 쓰려면 이러한 작업을 별도의 단계로 수행해야 합니다. 파일 검색, 파일 열기, 파일에 대한 읽기 또는 쓰기에 대한 자세한 내용은 [CGopherConnection,](../../mfc/reference/cgopherconnection-class.md) [CGopherFile](../../mfc/reference/cgopherfile-class.md)및 [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) 클래스를 참조하십시오. FTP 사이트 탐색에 대한 자세한 내용은 구성원 기능 [OpenURL](#openurl)을 참조하십시오. 일반적인 고퍼 연결 작업을 수행하는 단계는 [WinInet의 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md) 문서를 참조하십시오.

## <a name="cinternetsessiongethttpconnection"></a><a name="gethttpconnection"></a>C인터넷세션::GetHttpConnection

HTTP 연결을 설정하고 개체에 대한 포인터를 얻으려면 `CHttpConnection` 이 멤버 함수를 호출합니다.

```cpp
CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL);

CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,
    DWORD dwFlags,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL);
```

### <a name="parameters"></a>매개 변수

*pstrServer*<br/>
HTTP 서버 이름을 포함하는 문자열에 대한 포인터입니다.

*nPort*<br/>
서버에서 사용할 TCP/IP 포트를 식별하는 숫자입니다.

*pstrUserName*<br/>
사용자 이름을 포함하는 문자열에 대한 포인터입니다.

*pstrPassword*<br/>
액세스 암호를 포함하는 문자열에 대한 포인터입니다.

*dwflags*<br/>
`INTERNET_FLAG_*` 플래그의 모든 조합입니다. *dwFlags* 값에 대한 설명은 [CHttpConnection::OpenRequest의](../../mfc/reference/chttpconnection-class.md#openrequest) **설명** 섹션에서 표를 참조하십시오.

### <a name="return-value"></a>Return Value

[CHttpConnection](../../mfc/reference/chttpconnection-class.md) 개체에 대한 포인터입니다. 호출이 실패하면 throw된 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체를 검사하여 오류의 원인을 확인합니다.

### <a name="remarks"></a>설명

`GetHttpConnection`을 클릭하면 HTTP 서버에 연결하고 개체에 대한 `CHttpConnection` 포인터를 만들고 반환합니다. 서버에서 특정 작업을 수행하지 않습니다. 예를 들어 HTTP 헤더를 쿼리하려는 경우 이 작업을 별도의 단계로 수행해야 합니다. HTTP 서버에 대한 연결을 사용하여 수행할 수 있는 작업에 대한 자세한 내용은 [CHttpConnection](../../mfc/reference/chttpconnection-class.md) 및 [CHttpFile](../../mfc/reference/chttpfile-class.md) 클래스를 참조하십시오. HTTP 사이트 탐색에 대한 자세한 내용은 구성원 기능 [OpenURL](#openurl)을 참조하십시오. 일반적인 HTTP 연결 작업을 수행하는 단계는 [WinInet의 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md) 문서를 참조하십시오.

## <a name="cinternetsessiononstatuscallback"></a><a name="onstatuscallback"></a>C인터넷세션::온스테이콜백

이 멤버 함수는 상태 콜백이 활성화되고 작업이 보류 중일 때 상태를 업데이트하기 위해 프레임워크에서 호출됩니다.

```cpp
virtual void OnStatusCallback(
    DWORD_PTR dwContext,
    DWORD dwInternetStatus,
    LPVOID lpvStatusInformation,
    DWORD dwStatusInformationLength);
```

### <a name="parameters"></a>매개 변수

*dwContext*<br/>
응용 프로그램에서 제공하는 컨텍스트 값입니다.

*dw인터넷 상태*<br/>
콜백이 이루어지는 이유를 나타내는 상태 코드입니다. 가능한 값표는 **비고를** 참조하십시오.

*lpvStatus정보*<br/>
이 콜백과 관련된 정보를 포함하는 버퍼에 대한 포인터입니다.

*dw상태정보길이*<br/>
*lpvStatus정보의*크기 .

### <a name="remarks"></a>설명

상태 콜백을 활용하려면 먼저 [EnableStatusCallback을](#enablestatuscallback) 호출해야 합니다.

*dwInternetStatus* 매개 변수는 수행 중인 작업을 나타내고 *lpvStatusInformation정보의* 내용을 결정합니다. *dw상태정보길이는* *lpvStatusInformation*에 포함된 데이터의 길이를 나타낸다. *dwInternetStatus에* 대한 다음 상태 값은 다음과 같이 정의됩니다.

|값|의미|
|-----------|-------------|
|INTERNET_STATUS_RESOLVING_NAME|*lpvStatusInformation에*포함된 이름의 IP 주소를 찾습니다.|
|INTERNET_STATUS_NAME_RESOLVED|*lpvStatusInformation*에 포함된 이름의 IP 주소를 성공적으로 찾았습니다.|
|INTERNET_STATUS_CONNECTING_TO_SERVER|소켓 주소[(SOCKADDR)에](/windows/win32/winsock/sockaddr-2)연결 하여 가리키는 *lpvStatusInformation*.|
|INTERNET_STATUS_CONNECTED_TO_SERVER|성공적으로 소켓 주소에 연결 (SOCKADDR) *lpvStatusInformation에*의해 가리키는 .|
|INTERNET_STATUS_SENDING_REQUEST|정보 요청을 서버로 보냅니다. *lpvStatusInformation 매개* 변수는 NULL입니다.|
|INTERNET_STATUS_ REQUEST_SENT|정보 요청을 서버에 성공적으로 전송했습니다. *lpvStatusInformation 매개* 변수는 NULL입니다.|
|INTERNET_STATUS_RECEIVING_RESPONSE|서버가 요청에 응답할 때까지 대기 중입니다. *lpvStatusInformation 매개* 변수는 NULL입니다.|
|INTERNET_STATUS_RESPONSE_RECEIVED|서버에서 응답을 성공적으로 받았습니다. *lpvStatusInformation 매개* 변수는 NULL입니다.|
|INTERNET_STATUS_CLOSING_CONNECTION|서버에 대한 연결을 닫습니다. *lpvStatusInformation 매개* 변수는 NULL입니다.|
|INTERNET_STATUS_CONNECTION_CLOSED|서버에 대한 연결을 성공적으로 닫았습니다. *lpvStatusInformation 매개* 변수는 NULL입니다.|
|INTERNET_STATUS_HANDLE_CREATED|Win32 API 함수 [InternetConnect에서](/windows/win32/api/wininet/nf-wininet-internetconnectw) 새 핸들을 만들었으며 있음을 나타냅니다. 이렇게 하면 응용 프로그램에서 Win32 함수 [InternetClose를](/windows/win32/api/wininet/nf-wininet-internetclosehandle) 다른 스레드에서 호출할 수 있습니다. 이러한 기능에 대한 자세한 내용은 Windows SDKfor를 참조하십시오.|
|INTERNET_STATUS_HANDLE_CLOSING|이 핸들 값을 성공적으로 종료했습니다.|

상태 콜백 루틴이 수행되기 전에 일부 작업이 필요하도록 이 멤버 함수를 재정의합니다.

> [!NOTE]
> 상태 콜백은 스레드 상태 보호가 필요합니다. 공유 라이브러리에서 MFC를 사용하는 경우 재정의 시작 부분에 다음 줄을 추가합니다.

[!code-cpp[NVC_MFCHtmlHttp#8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]

비동기 작업에 대한 자세한 내용은 인터넷 [첫 번째 단계: WinInet](../../mfc/wininet-basics.md)을 참조하십시오.

## <a name="cinternetsessionopenurl"></a><a name="openurl"></a>C인터넷세션::오픈URL

이 멤버 함수를 호출하여 지정된 요청을 HTTP 서버에 보내고 클라이언트가 요청과 함께 보낼 추가 RFC822, MIME 또는 HTTP 헤더를 지정할 수 있도록 합니다.

```cpp
CStdioFile* OpenURL(
    LPCTSTR pstrURL,
    DWORD_PTR dwContext = 1,
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLength = 0);
```

### <a name="parameters"></a>매개 변수

*프스트URL*<br/>
읽기를 시작할 URL 이름에 대한 포인터입니다. 파일:, ftp:, gopher:또는 http로 시작하는 URL만 지원됩니다. *pstrURL이* NULL인 경우 어설션합니다.

*dwContext*<br/>
콜백에서 반환된 핸들과 함께 전달된 응용 프로그램 정의 값입니다.

*dwFlags*<br/>
이 연결을 처리하는 방법을 설명하는 플래그입니다. 유효한 플래그에 대한 자세한 내용은 **비고를** 참조하십시오. 유효한 플래그는 다음과 같습니다.

- INTERNET_FLAG_TRANSFER_ASCII 기본값입니다. 파일을 ASCII 텍스트로 전송합니다.

- INTERNET_FLAG_TRANSFER_BINARY 파일을 이진 파일로 전송합니다.

- INTERNET_FLAG_RELOAD 로컬로 캐시된 경우에도 와이어에서 데이터를 가져옵니다.

- INTERNET_FLAG_DONT_CACHE 로컬 또는 게이트웨이에서 데이터를 캐시하지 마십시오.

- INTERNET_FLAG_SECURE 이 플래그는 HTTP 요청에만 적용됩니다. 보안 소켓 계층 또는 PCT를 사용하여 와이어에서 보안 트랜잭션을 요청합니다.

- INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT 가능하면 각 연결 요청에 대해 새 세션을 `OpenUrl` 만드는 대신 생성된 새 요청에 대해 서버에 대한 기존 연결을 다시 사용합니다.

- INTERNET_FLAG_PASSIVE FTP 사이트에 사용됩니다. 수동 FTP 의미 체계를 사용합니다. 의 [CInternet연결과](../../mfc/reference/cinternetconnection-class.md) 함께 `OpenURL`사용됩니다.

*pstr헤더*<br/>
HTTP 서버로 보낼 헤더가 포함된 문자열에 대한 포인터입니다.

*dw헤더길이*<br/>
추가 헤더의 길이(문자)입니다. 이것이 -1L이고 *pstrHeaders가 NULL이* 아닌 경우 *pstrHeaders는* 0으로 종료되고 길이가 계산됩니다.

### <a name="return-value"></a>Return Value

FTP, GOPHER, HTTP 및 파일 형식 인터넷 서비스에 대해서만 파일 핸들을 반환합니다. 구문 분석이 실패한 경우 NULL을 반환합니다.

반환 하는 `OpenURL` 포인터는 *pstrURL의*서비스 유형에 따라 달라 집니다. 아래 표는 반환할 수 `OpenURL` 있는 가능한 포인터를 보여 줍니다.

|URL 유형|반환|
|--------------|-------------|
|`file://`|`CStdioFile*`|
|`http://`|`CHttpFile*`|
|`gopher://`|`CGopherFile*`|
|`ftp://`|`CInternetFile*`|

### <a name="remarks"></a>설명

매개 변수 *dwFlags는* INTERNET_FLAG_TRANSFER_ASCII 또는 INTERNET_FLAG_TRANSFER_BINARY 포함해야 하지만 둘 다 포함되지는 않습니다. 나머지 플래그는 비트별 **OR** 연산자(&#124;)와 결합할 수 **있습니다. **

`OpenURL`Win32 함수를 `InternetOpenURL`래핑하는 은 인터넷 서버에서 데이터를 다운로드, 검색 및 읽을 수만 허용합니다. `OpenURL`원격 위치에서 파일 조작을 허용하지 않으므로 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) 개체가 필요하지 않습니다.

파일에 쓰기와 같은 연결 관련(즉, 프로토콜별) 함수를 사용하려면 세션을 연 다음 특정 종류의 연결을 연 다음 해당 연결을 사용하여 원하는 모드에서 파일을 여는 것입니다. 연결 `CInternetConnection` 관련 기능에 대한 자세한 내용은 을 참조하십시오.

## <a name="cinternetsessionoperator-hinternet"></a><a name="operator_hinternet"></a>C인터넷세션::운영자 HINTERNET

이 연산자를 사용하여 현재 인터넷 세션의 Windows 핸들을 가져옵니다.

```cpp
operator HINTERNET() const;
```

## <a name="cinternetsessionsetcookie"></a><a name="setcookie"></a>C인터넷세션::세트쿠키

지정된 URL에 대한 쿠키를 설정합니다.

```cpp
static BOOL SetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPCTSTR pstrCookieData);
```

### <a name="parameters"></a>매개 변수

*pstrUrl*<br/>
쿠키를 설정해야 하는 URL을 지정하는 null 종료된 문자열에 대한 포인터입니다.

*pstrCookieName*<br/>
쿠키의 이름을 포함하는 문자열에 대한 포인터입니다.

*pstrCookieData*<br/>
URL과 연결할 실제 문자열 데이터가 포함된 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하지 않은 경우 TRUE를 반환하거나 FALSE를 반환합니다. 특정 오류 코드를 얻으려면`GetLastError.`

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 Win32 메시지 [InternetSetCookie의](/windows/win32/api/wininet/nf-wininet-internetsetcookiew)동작을 구현합니다.

## <a name="cinternetsessionsetoption"></a><a name="setoption"></a>C인터넷세션::세트옵션

이 멤버 함수를 호출하여 인터넷 세션에 대한 옵션을 설정합니다.

```cpp
BOOL SetOption(
    DWORD dwOption,
    LPVOID lpBuffer,
    DWORD dwBufferLength,
    DWORD dwFlags = 0);

BOOL SetOption(
    DWORD dwOption,
    DWORD dwValue,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>매개 변수

*dw옵션*<br/>
설정할 인터넷 옵션입니다. 가능한 옵션 목록은 Windows SDKfor의 [옵션 플래그를](/windows/win32/WinInet/option-flags) 참조하십시오.

*lp버퍼*<br/>
옵션 설정이 포함된 버퍼입니다.

*dw버퍼길이*<br/>
*lpBuffer의* 길이 또는 *dwValue의*크기 .

*dw값*<br/>
옵션 설정이 포함된 DWORD입니다.

*dwFlags*<br/>
다양한 캐싱 옵션을 나타냅니다. 기본값은 0으로 설정됩니다. 가능한 값은 다음과 같습니다.

- INTERNET_FLAG_DONT_CACHE 로컬 또는 게이트웨이 서버에서 데이터를 캐시하지 마십시오.

- INTERNET_FLAG_OFFLINE 다운로드 작업은 영구 캐시를 통해서만 충족됩니다. 항목이 캐시에 없으면 적절한 오류 코드가 반환됩니다. 이 플래그는 비트별 **OR(&#124;) **연산자와 결합될 수 있다. **OR**

### <a name="return-value"></a>Return Value

작업이 성공하면 TRUE 값이 반환됩니다. 오류가 발생하면 FALSE 값이 반환됩니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

## <a name="see-also"></a>참고 항목

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C인터넷커넥션 클래스](../../mfc/reference/cinternetconnection-class.md)<br/>
[CHttpConnection 클래스](../../mfc/reference/chttpconnection-class.md)<br/>
[CFtp커넥션 클래스](../../mfc/reference/cftpconnection-class.md)<br/>
[CGopher커넥션 클래스](../../mfc/reference/cgopherconnection-class.md)
