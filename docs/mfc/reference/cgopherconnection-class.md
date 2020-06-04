---
title: CGopher커넥션 클래스
ms.date: 11/04/2016
f1_keywords:
- CGopherConnection
- AFXINET/CGopherConnection
- AFXINET/CGopherConnection::CGopherConnection
- AFXINET/CGopherConnection::CreateLocator
- AFXINET/CGopherConnection::GetAttribute
- AFXINET/CGopherConnection::OpenFile
helpviewer_keywords:
- CGopherConnection [MFC], CGopherConnection
- CGopherConnection [MFC], CreateLocator
- CGopherConnection [MFC], GetAttribute
- CGopherConnection [MFC], OpenFile
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
ms.openlocfilehash: eade1a82b674d5ad2e91146559139445ef017180
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373709"
---
# <a name="cgopherconnection-class"></a>CGopher커넥션 클래스

Gopher 인터넷 서버 연결을 관리합니다.

> [!NOTE]
> 클래스 `CGopherConnection`및 `CGopherFile` `CGopherFileFind` `CGopherLocator` 해당 구성원은 Windows XP 플랫폼에서 작동하지 않지만 이전 플랫폼에서 계속 작동하므로 더 이상 사용되지 않습니다.

## <a name="syntax"></a>구문

```
class CGopherConnection : public CInternetConnection
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CGopher 연결::CGopher 연결](#cgopherconnection)|`CGopherConnection` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CGopher 연결::만들기로케이터](#createlocator)|[GopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체를 만들어 고퍼 서버에서 파일을 찾습니다.|
|[CGopher 연결::Get특성](#getattribute)|고퍼 개체에 대한 특성 정보를 검색합니다.|
|[CGopher 연결::열기 파일](#openfile)|고퍼 파일을 엽니다.|

## <a name="remarks"></a>설명

고퍼 서비스는 MFC WinInet 클래스에서 인식하는 세 가지 인터넷 서비스 중 하나입니다.

클래스에는 `CGopherConnection` 생성자와 gopher 서비스를 관리하는 세 개의 추가 멤버 [함수(OpenFile,](#openfile) [CreateLocator](#createlocator)및 [GetAttribute)가](#getattribute)포함되어 있습니다.

gopher 인터넷 서버와 통신하려면 먼저 [CInternetSession의](../../mfc/reference/cinternetsession-class.md)인스턴스를 만든 다음 [CInternetSession::GetGopherConnection를](../../mfc/reference/cinternetsession-class.md#getgopherconnection) `CGopherConnection` 호출하여 개체를 만들고 포인터를 반환해야 합니다. 개체를 `CGopherConnection` 직접 만들지 않습니다.

다른 MFC `CGopherConnection` 인터넷 클래스와 함께 작동하는 방법에 대한 자세한 내용은 [WinInet와 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)문서를 참조하십시오. 지원되는 다른 두 인터넷 서비스 사용에 대한 자세한 내용은 FTP 및 HTTP 클래스 [CHttpConnection](../../mfc/reference/chttpconnection-class.md) 및 [CFtpConnection](../../mfc/reference/cftpconnection-class.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CGopherConnection`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="cgopherconnectioncgopherconnection"></a><a name="cgopherconnection"></a>CGopher 연결::CGopher 연결

이 멤버 함수는 개체를 생성하기 위해 호출됩니다. `CGopherConnection`

```
CGopherConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CGopherConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 0,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>매개 변수

*pSession*<br/>
관련 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에 대한 포인터입니다.

*hConnected*<br/>
현재 인터넷 세션의 Windows 핸들입니다.

*pstrServer*<br/>
FTP 서버 이름을 포함하는 문자열에 대한 포인터입니다.

*dwContext*<br/>
작업에 대 한 컨텍스트 식별자입니다. *dwContext는* [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)에서 반환된 작업의 상태 정보를 식별합니다. 기본값은 1로 설정됩니다. 그러나 작업에 대 한 특정 컨텍스트 ID를 명시적으로 할당할 수 있습니다. 개체 및 개체가 수행하는 모든 작업은 해당 컨텍스트 ID와 연결됩니다.

*pstrUserName*<br/>
로그인할 사용자의 이름을 지정하는 null-종료된 문자열에 대한 포인터입니다. NULL인 경우 기본값은 익명입니다.

*pstrPassword*<br/>
로그인하는 데 사용할 암호를 지정하는 null 종료된 문자열에 대한 포인터입니다. *pstrPassword와* *pstrUserName* 모두 NULL인 경우 기본 익명 암호는 사용자의 전자 메일 이름입니다. *pstrPassword가* NULL(또는 빈 문자열)이지만 *pstrUserName이* NULL이 아닌 경우 빈 암호가 사용됩니다. 다음 표는 *pstrUserName* 및 *pstrPassword의*네 가지 가능한 설정에 대한 동작에 대해 설명합니다.

|*pstrUserName*|*pstrPassword*|FTP 서버로 전송된 사용자 이름|FTP 서버로 전송된 암호|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL 또는 " "|NULL 또는 " "|"anonymous"|사용자의 이메일 이름|
|NULL이 아닌 문자열|NULL 또는 " "|*pstrUserName*|" "|
|NULL 비-NULL 문자열|오류|오류||
|NULL이 아닌 문자열|NULL이 아닌 문자열|*pstrUserName*|*pstrPassword*|

*nPort*<br/>
서버에서 사용할 TCP/IP 포트를 식별하는 숫자입니다.

### <a name="remarks"></a>설명

직접 만들지 `CGopherConnection` 않습니다. 대신 [CInternetSession::GetGopherConnection를](../../mfc/reference/cinternetsession-class.md#getgopherconnection)호출하여 `CGopherConnection` 개체를 만들고 포인터를 반환합니다.

## <a name="cgopherconnectioncreatelocator"></a><a name="createlocator"></a>CGopher 연결::만들기로케이터

이 멤버 함수를 호출하여 gopher 로케이터를 만들어 고퍼 서버에서 파일을 찾거나 식별합니다.

```
CGopherLocator CreateLocator(
    LPCTSTR pstrDisplayString,
    LPCTSTR pstrSelectorString,
    DWORD dwGopherType);

static CGopherLocator CreateLocator(LPCTSTR pstrLocator);

static CGopherLocator CreateLocator(
    LPCTSTR pstrServerName,
    LPCTSTR pstrDisplayString,
    LPCTSTR pstrSelectorString,
    DWORD dwGopherType,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>매개 변수

*pstr디스플레이스트링*<br/>
검색할 고퍼 문서 또는 디렉터리 이름을 포함하는 문자열에 대한 포인터입니다. *pstrDisplayString* 매개 변수가 NULL이면 gopher 서버의 기본 디렉토리가 반환됩니다.

*pstr선택자 스트링*<br/>
항목을 검색하기 위해 gopher 서버로 보낼 선택기 문자열에 대한 포인터입니다. *pstrSelectorString은* NULL일 수 있습니다.

*dwGopherType*<br/>
이렇게 하면 *pstrSelectorString이* 디렉터리 또는 문서를 참조하는지 여부와 요청이 gopher 또는 gopher+인지 여부를 지정합니다. Windows SDK에서 [GOPHER_FIND_DATA](/windows/win32/api/wininet/ns-wininet-gopher_find_dataw) 구조에 대한 특성을 참조하십시오.

*스트로케이터*<br/>
열 파일을 식별하는 문자열에 대한 포인터입니다. 일반적으로 이 문자열은 [CGopherFileFind:GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator)에 대한 호출에서 반환됩니다.

*pstrServer이름*<br/>
고퍼 서버 이름이 포함된 문자열에 대한 포인터입니다.

*nPort*<br/>
이 연결에 대한 인터넷 포트를 식별하는 번호입니다.

### <a name="return-value"></a>Return Value

[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체입니다.

### <a name="remarks"></a>설명

멤버 함수의 정적 버전은 서버를 지정해야 하며 비정적 버전은 연결 개체의 서버 이름을 사용합니다.

고퍼 서버에서 정보를 검색하려면 응용 프로그램이 먼저 gopher 로케이터를 가져와야 합니다. 그런 다음 응용 프로그램은 로케이터를 불투명 토큰으로 처리해야 합니다(즉, 응용 프로그램은 로케이터를 사용할 수 있지만 직접 조작하거나 비교하지는 않음). 일반적으로 응용 프로그램은 [CGopherFileFind:FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) 멤버 함수를 호출하기 위해 로케이터를 사용하여 특정 정보를 검색합니다.

## <a name="cgopherconnectiongetattribute"></a><a name="getattribute"></a>CGopher 연결::Get특성

이 멤버 함수를 호출하여 gopher 서버에서 항목에 대한 특정 특성 정보를 검색합니다.

```
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,
    CString& strResult,);
```

### <a name="parameters"></a>매개 변수

*refLocator*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체에 대한 참조입니다.

*strRequested특성*<br/>
요청된 특성의 이름을 지정하는 공간 구분 문자열입니다.

*strResult*<br/>
로케이터 형식을 받는 [CString에](../../atl-mfc-shared/reference/cstringt-class.md) 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

## <a name="cgopherconnectionopenfile"></a><a name="openfile"></a>CGopher 연결::열기 파일

이 멤버 함수를 호출하여 gopher 서버에서 파일을 엽니다.

```
CGopherFile* OpenFile(
    CGopherLocator& refLocator,
    DWORD dwFlags = 0,
    LPCTSTR pstrView = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*refLocator*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체에 대한 참조입니다.

*dwFlags*<br/>
INTERNET_FLAG_* 플래그의 모든 조합. INTERNET_FLAG_\* 플래그에 대한 자세한 내용은 [CInternetSession::OpenUrl을](../../mfc/reference/cinternetsession-class.md#openurl) 참조하십시오.

*pstrView*<br/>
파일 보기 문자열에 대한 포인터입니다. 서버에 파일의 여러 뷰가 있는 경우 이 매개 변수는 열 파일 뷰를 지정합니다. *pstrView가* NULL이면 기본 파일 뷰가 사용됩니다.

*dwContext*<br/>
열려 있는 파일의 컨텍스트 ID입니다. *dwContext*에 대한 자세한 내용은 **비고를** 참조하십시오.

### <a name="return-value"></a>Return Value

열 수 [있는 CGopherFile](../../mfc/reference/cgopherfile-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

*dwContext* 기본값을 재정의하여 컨텍스트 식별자를 선택한 값으로 설정합니다. 컨텍스트 식별자는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에서 `CGopherConnection` 만든 개체의 이 특정 작업과 연결됩니다. 값이 [CInternetSession::OnStatusCallback으로](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 반환되어 식별되는 작업에 대한 상태를 제공합니다. 컨텍스트 식별자에 대한 자세한 내용은 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 문서를 참조하십시오.

## <a name="see-also"></a>참고 항목

[C인터넷커넥션 클래스](../../mfc/reference/cinternetconnection-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFtp커넥션 클래스](../../mfc/reference/cftpconnection-class.md)<br/>
[CHttpConnection 클래스](../../mfc/reference/chttpconnection-class.md)<br/>
[C인터넷커넥션 클래스](../../mfc/reference/cinternetconnection-class.md)<br/>
[CGopherLocator 클래스](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)<br/>
[C인터넷세션 클래스](../../mfc/reference/cinternetsession-class.md)
