---
title: CHttpConnection 클래스
ms.date: 03/27/2019
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
helpviewer_keywords:
- CHttpConnection [MFC], CHttpConnection
- CHttpConnection [MFC], OpenRequest
ms.assetid: a402b662-c445-4988-800d-c8278551babe
ms.openlocfilehash: af402b532b3aba28bdfefea5afa67331765db4c5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351825"
---
# <a name="chttpconnection-class"></a>CHttpConnection 클래스

HTTP 서버와의 연결을 관리합니다.

## <a name="syntax"></a>구문

```
class CHttpConnection : public CInternetConnection
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CHttp연결::CHttpConnection](#chttpconnection)|`CHttpConnection` 개체를 만듭니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CHttpConnection::OpenRequest](#openrequest)|HTTP 요청을 엽니다.|

## <a name="remarks"></a>설명

HTTP는 MFC WinInet 클래스에서 구현한 세 가지 인터넷 서버 프로토콜 중 하나입니다.

클래스에는 `CHttpConnection` HTTP 프로토콜을 사용하여 서버에 대한 연결을 관리하는 생성자와 하나의 멤버 [함수인 OpenRequest가](#openrequest)포함되어 있습니다.

HTTP 서버와 통신하려면 먼저 [CInternetSession](../../mfc/reference/cinternetsession-class.md)의 인스턴스를 만든 다음 [CHttpConnection](#chttpconnection) 개체를 만들어야 합니다. 개체를 `CHttpConnection` 직접 만들지 않습니다. 대신 [CInternetSession::GetHttpConnection을](../../mfc/reference/cinternetsession-class.md#gethttpconnection)호출하여 `CHttpConnection` 개체를 만들고 포인터를 반환합니다.

다른 MFC `CHttpConnection` 인터넷 클래스와 함께 작동하는 방법에 대한 자세한 내용은 [WinInet와 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)문서를 참조하십시오. 지원되는 다른 두 인터넷 프로토콜인 gopher 및 FTP를 사용하여 서버에 연결하는 것에 대한 자세한 내용은 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) 및 [CFtpConnection](../../mfc/reference/cftpconnection-class.md)클래스를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CHttpConnection`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="chttpconnectionchttpconnection"></a><a name="chttpconnection"></a>CHttp연결::CHttpConnection

이 멤버 함수는 개체를 생성하기 위해 호출됩니다. `CHttpConnection`

```
CHttpConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CHttpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 1);

CHttpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    DWORD dwFlags,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*pSession*<br/>
[CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에 대한 포인터입니다.

*hConnected*<br/>
인터넷 연결에 대한 핸들입니다.

*pstrServer*<br/>
서버 이름을 포함하는 문자열에 대한 포인터입니다.

*dwContext*<br/>
개체에 대한 컨텍스트 `CInternetConnection` 식별자입니다. *dwContext에*대한 자세한 내용은 **비고** 섹션을 참조하십시오.

*nPort*<br/>
이 연결에 대한 인터넷 포트를 식별하는 숫자입니다.

*pstrUserName*<br/>
로그인할 사용자의 이름을 지정하는 null 종료된 문자열에 대한 포인터입니다. NULL인 경우 기본값은 익명입니다.

*pstrPassword*<br/>
로그인하는 데 사용할 암호를 지정하는 null 종료된 문자열에 대한 포인터입니다. *pstrPassword와* *pstrUserName* 모두 NULL인 경우 기본 익명 암호는 사용자의 전자 메일 이름입니다. *pstrPassword가* NULL 또는 빈 문자열이지만 *pstrUserName이* NULL이 아닌 경우 빈 암호가 사용됩니다. 다음 표는 *pstrUserName* 및 *pstrPassword의*네 가지 가능한 설정에 대한 동작에 대해 설명합니다.

|*pstrUserName*|*pstrPassword*|FTP 서버로 전송된 사용자 이름|FTP 서버로 전송된 암호|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL 또는 " "|NULL 또는 " "|"anonymous"|사용자의 이메일 이름|
|NULL이 아닌 문자열|NULL 또는 " "|*pstrUserName*|" "|
|NULL |NULL이 아닌 문자열|오류|오류|
|NULL이 아닌 문자열|NULL이 아닌 문자열|*pstrUserName*|*pstrPassword*|

*dwFlags*<br/>
`INTERNET_FLAG_*` 플래그의 모든 조합입니다. *dwFlags* 값에 대한 설명은 [CHttpConnection::OpenRequest의](#openrequest) **설명** 섹션에서 표를 참조하십시오.

### <a name="remarks"></a>설명

직접 만들지 `CHttpConnection` 않습니다. 대신 [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)을 호출하여 개체를 만듭니다.

## <a name="chttpconnectionopenrequest"></a><a name="openrequest"></a>CHttpConnection::오픈 요청

HTTP 연결을 열려면 이 멤버 함수를 호출합니다.

```
CHttpFile* OpenRequest(
    LPCTSTR pstrVerb,
    LPCTSTR pstrObjectName,
    LPCTSTR pstrReferer = NULL,
    DWORD_PTR dwContext = 1,
    LPCTSTR* ppstrAcceptTypes = NULL,
    LPCTSTR pstrVersion = NULL,
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);

CHttpFile* OpenRequest(
    int nVerb,
    LPCTSTR pstrObjectName,
    LPCTSTR pstrReferer = NULL,
    DWORD_PTR dwContext = 1,
    LPCTSTR* ppstrAcceptTypes = NULL,
    LPCTSTR pstrVersion = NULL,
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);
```

### <a name="parameters"></a>매개 변수

*pstrVerb*<br/>
요청에 사용할 동사를 포함하는 문자열에 대한 포인터입니다. NULL이면 "GET"이 사용됩니다.

*pstrObjectName*<br/>
지정된 동사의 대상 개체를 포함하는 문자열에 대한 포인터입니다. 이 문자열은 일반적으로 파일 이름, 실행 모듈 또는 검색 지정자입니다.

*pstrReferer*<br/>
요청의*URL(pstrObjectName)을*가져온 문서의 주소(URL)를 지정하는 문자열에 대한 포인터입니다. NULL이면 HTTP 헤더가 지정되지 않습니다.

*dwContext*<br/>
`OpenRequest` 작업에 대한 컨텍스트 식별자입니다. *dwContext에*대한 자세한 내용은 비고 섹션을 참조하십시오.

*ppstrAccept유형*<br/>
클라이언트에서 허용하는 콘텐츠 형식을 나타내는 문자열에 대한 null 종료된 LPCTSTR 배열에 대한 포인터입니다. *ppstrAcceptType이* NULL인 경우 서버는 클라이언트가 "text/*" 형식의 문서만 허용한다고 해석합니다(즉, 텍스트 문서만, 그림이나 다른 이진 파일이 아님). 콘텐츠 형식 첨부 HTTP POST 및 PUT 등 첨부된 정보가 있는 쿼리에 대한 데이터의 형식을 식별하는 CGI 변수 CONTENT_TYPE과 같습니다.

*pstrVersion*<br/>
HTTP 버전을 정의하는 문자열에 대한 포인터입니다. NULL이 면 "HTTP/1.0"이 사용됩니다.

*dwFlags*<br/>
INTERNET_ * FLAG_ 플래그의 조합입니다. 가능한 *dwFlags* 값에 대한 설명은 비고 섹션을 참조하십시오.

*nVerb*<br/>
HTTP 요청 형식과 관련된 숫자입니다. 다음 중 하나일 수 있습니다.

|HTTP 요청 형식|*nVerb* 값|
|-----------------------|-------------------|
|HTTP_VERB_POST|0|
|HTTP_VERB_GET|1|
|HTTP_VERB_HEAD|2|
|HTTP_VERB_PUT|3|
|HTTP_VERB_LINK|4|
|HTTP_VERB_DELETE|5|
|HTTP_VERB_UNLINK|6|

### <a name="return-value"></a>Return Value

[CHttpFile](../../mfc/reference/chttpfile-class.md) 개체에 대한 포인터가 요청되었습니다.

### <a name="remarks"></a>설명

*dwFlags는* 다음 중 하나가 될 수 있습니다.

|인터넷 플래그|Description|
|-------------------|-----------------|
|INTERNET_FLAG_RELOAD|캐시가 아니라 원본 서버에서 요청한 파일, 개체 또는 디렉터리 목록을 다운로드합니다.|
|INTERNET_FLAG_DONT_CACHE|반환된 엔터티를 캐시에 추가하지 않습니다.|
|INTERNET_FLAG_MAKE_PERSISTENT|반환된 엔터티를 영구 엔터티로 캐시에 추가합니다. 즉, 표준 캐시 정리, 일관성 검사 또는 가비지 수집캐시에서 이 항목을 제거할 수 없습니다.|
|INTERNET_FLAG_SECURE|보안 트랜잭션 의미 체계를 사용합니다. 그것은 SSL / PCT를 사용하는 것으로 변환하고 HTTP 요청에만 의미가 있습니다|
|INTERNET_FLAG_NO_AUTO_REDIRECT|HTTP에서만 사용되며 [CHttpFile:SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest)에서 리디렉션을 자동으로 처리해서는 안 되도록 지정합니다.|

`dwContext` 기본값을 재정의하여 컨텍스트 식별자를 설정한 값으로 설정합니다. 컨텍스트 식별자는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에서 `CHttpConnection` 만든 개체의 이 특정 작업과 연결됩니다. 값이 [CInternetSession::OnStatusCallback으로](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 반환되어 식별된 작업에 대한 상태를 제공합니다. 컨텍스트 식별자에 대한 자세한 내용은 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 문서를 참조하십시오.

이 함수를 사용할 경우 예외가 throw될 수 있습니다.

## <a name="see-also"></a>참고 항목

[C인터넷커넥션 클래스](../../mfc/reference/cinternetconnection-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C인터넷커넥션 클래스](../../mfc/reference/cinternetconnection-class.md)<br/>
[CHttpFile 클래스](../../mfc/reference/chttpfile-class.md)
