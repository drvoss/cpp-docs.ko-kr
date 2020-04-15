---
title: CHttpFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CHttpFile
- AFXINET/CHttpFile
- AFXINET/CHttpFile::CHttpFile
- AFXINET/CHttpFile::AddRequestHeaders
- AFXINET/CHttpFile::EndRequest
- AFXINET/CHttpFile::GetFileURL
- AFXINET/CHttpFile::GetObject
- AFXINET/CHttpFile::GetVerb
- AFXINET/CHttpFile::QueryInfo
- AFXINET/CHttpFile::QueryInfoStatusCode
- AFXINET/CHttpFile::SendRequest
- AFXINET/CHttpFile::SendRequestEx
helpviewer_keywords:
- CHttpFile [MFC], CHttpFile
- CHttpFile [MFC], AddRequestHeaders
- CHttpFile [MFC], EndRequest
- CHttpFile [MFC], GetFileURL
- CHttpFile [MFC], GetObject
- CHttpFile [MFC], GetVerb
- CHttpFile [MFC], QueryInfo
- CHttpFile [MFC], QueryInfoStatusCode
- CHttpFile [MFC], SendRequest
- CHttpFile [MFC], SendRequestEx
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
ms.openlocfilehash: cba3ba7d86577703de2bf5709d66bbd5e0298863
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368386"
---
# <a name="chttpfile-class"></a>CHttpFile 클래스

HTTP 서버에서 파일을 요청하고 읽는 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CHttpFile : public CInternetFile
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CHttpFile::CHttpFile](#chttpfile)|`CHttpFile` 개체를 만듭니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CHttpFile::추가 요청 헤더](#addrequestheaders)|HTTP 서버로 전송된 요청에 헤더를 추가합니다.|
|[CHttpFile::끝 요청](#endrequest)|SendRequestEx 멤버 함수를 사용하여 HTTP 서버로 전송된 요청을 [종료합니다.](#sendrequestex)|
|[CHttpFile::GetFileURL](#getfileurl)|지정된 파일의 URL을 가져옵니다.|
|[CHttpFile::GetObject](#getobject)|HTTP 서버에 요청에 있는 동사의 대상 개체를 가져옵니다.|
|[CHttpFile::GetVerb](#getverb)|HTTP 서버에 대한 요청에 사용된 동사를 가져옵니다.|
|[CHttpFile::쿼리정보](#queryinfo)|HTTP 서버에서 응답 또는 요청 헤더를 반환합니다.|
|[CHttpFile::쿼리정보 상태 코드](#queryinfostatuscode)|HTTP 요청과 연결된 상태 코드를 검색하고 제공된 `dwStatusCode` 매개 변수에 배치합니다.|
|[CHttpFile::보내기 요청](#sendrequest)|HTTP 서버에 요청을 보냅니다.|
|[CHttpFile::SendRequestEx](#sendrequestex)|의 [쓰기](../../mfc/reference/cinternetfile-class.md#write) 또는 [쓰기 문자열](../../mfc/reference/cinternetfile-class.md#writestring) 메서드를 사용하여 `CInternetFile`HTTP 서버에 요청을 보냅니다.|

## <a name="remarks"></a>설명

인터넷 세션이 HTTP 서버에서 데이터를 읽는 경우 의 `CHttpFile`인스턴스를 만들어야 합니다.

다른 MFC `CHttpFile` 인터넷 클래스와 함께 작동하는 방법에 대한 자세한 내용은 [WinInet와 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CHttpFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="chttpfileaddrequestheaders"></a><a name="addrequestheaders"></a>CHttpFile::추가 요청 헤더

이 멤버 함수를 호출하여 하나 이상의 HTTP 요청 헤더를 HTTP 요청 핸들에 추가합니다.

```
BOOL AddRequestHeaders(
    LPCTSTR pstrHeaders,
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW,
    int dwHeadersLen = -1);

BOOL AddRequestHeaders(
    CString& str,
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW);
```

### <a name="parameters"></a>매개 변수

*pstr헤더*<br/>
요청에 부가할 헤더 또는 헤더가 포함된 문자열에 대한 포인터입니다. 각 헤더는 CR/LF 쌍으로 종료되어야 합니다.

*dwFlags*<br/>
새 헤더의 의미 체계를 수정합니다. 다음 중 하나일 수 있습니다.

- HTTP_ADDREQ_FLAG_COALESCE 플래그를 사용하여 동일한 이름의 헤더를 병합하여 다음 헤더에 발견된 첫 번째 헤더를 추가합니다. 예를 들어 " 수락:\*텍스트/ "다음에 "수락: 오디오/\*" 단일 헤더의 형성결과 "동의: 텍스트/\*오디오/\*". 병합된 또는 별도의 헤더로 전송된 요청으로 수신된 데이터와 관련하여 일관된 체계를 보장하는 것은 호출 응용 프로그램에 달려 있습니다.

- HTTP_ADDREQ_FLAG_REPLACE 제거 및 추가를 수행하여 현재 헤더를 대체합니다. 헤더 이름은 현재 헤더를 제거하는 데 사용되며 전체 값은 새 헤더를 추가하는 데 사용됩니다. 헤더 값이 비어 있고 헤더가 발견되면 제거됩니다. 비어 있지 않으면 헤더 값이 대체됩니다.

- HTTP_ADDREQ_FLAG_ADD_IF_NEW 아직 존재하지 않는 경우에만 헤더를 추가합니다. 있는 오류가 있으면 오류가 반환됩니다.

- HTTP_ADDREQ_FLAG_ADD 교체와 함께 사용됩니다. 헤더가 없는 경우 헤더를 추가합니다.

*dw헤더슬렌*<br/>
*pstrHeaders의*길이(문자)입니다. 이것이 -1L이면 *pstrHeaders는* 0-종료된 것으로 가정하고 길이가 계산됩니다.

*Str*<br/>
추가할 요청 헤더 또는 헤더를 포함하는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

`AddRequestHeaders`HTTP 요청 핸들에 추가 된 자유 형식 헤더를 추가합니다. HTTP 서버로 전송된 정확한 요청에 대한 자세한 제어가 필요한 정교한 클라이언트가 사용하기 위한 것입니다.

> [!NOTE]
> 응용 프로그램은 HTTP_ADDREQ_FLAG_ADD 또는 HTTP_ADDREQ_FLAG_ADD_IF_NEW 사용하여 호출을 위해 `AddRequestHeaders` *pstrHeaders* 또는 *str에서* 여러 헤더를 전달할 수 있습니다. 응용 프로그램이 HTTP_ADDREQ_FLAG_REMOVE 또는 HTTP_ADDREQ_FLAG_REPLACE 사용하여 헤더를 제거하거나 바꾸려고 하면 *lpszHeader에서*하나의 헤더만 제공될 수 있습니다.

## <a name="chttpfilechttpfile"></a><a name="chttpfile"></a>CHttpFile::CHttpFile

이 멤버 함수는 개체를 생성하기 위해 호출됩니다. `CHttpFile`

```
CHttpFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrObject,
    LPCTSTR pstrServer,
    LPCTSTR pstrVerb,
    DWORD_PTR dwContext);

CHttpFile(
    HINTERNET hFile,
    LPCTSTR pstrVerb,
    LPCTSTR pstrObject,
    CHttpConnection* pConnection);
```

### <a name="parameters"></a>매개 변수

*hFile*<br/>
인터넷 파일에 대한 핸들입니다.

*hSession*<br/>
인터넷 세션에 대한 핸들입니다.

*pstrObject*<br/>
개체를 포함하는 문자열에 `CHttpFile` 대한 포인터입니다.

*pstrServer*<br/>
서버 이름을 포함하는 문자열에 대한 포인터입니다.

*pstrVerb*<br/>
요청을 보낼 때 사용할 메서드를 포함하는 문자열에 대한 포인터입니다. 포스트, 헤드 또는 GET이 될 수 있습니다.

*dwContext*<br/>
개체에 대한 컨텍스트 `CHttpFile` 식별자입니다. 이 매개 변수에 대한 자세한 내용은 **비고를** 참조하십시오.

*pConnection*<br/>
[CHttpConnection](../../mfc/reference/chttpconnection-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

개체를 `CHttpFile` 직접 생성하지 않습니다. 대신 [CInternetSession:::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) 또는 [CHttpConnection::OpenRequest 대신 호출합니다.](../../mfc/reference/chttpconnection-class.md#openrequest)

에 대 `dwContext` 한 기본값은 개체를 만든 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에서 `CHttpFile` `CHttpFile` 개체에 MFC에 의해 전송 됩니다. 개체를 `CInternetSession::OpenURL` 호출하거나 `CHttpConnection` 생성할 때 기본값을 재정의하여 컨텍스트 식별자를 선택한 값으로 설정할 수 있습니다. `CHttpFile` 컨텍스트 식별자가 [CInternetSession::OnStatusCallback으로](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 반환되어 식별되는 개체에 대한 상태를 제공합니다. 컨텍스트 식별자에 대한 자세한 내용은 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 문서를 참조하십시오.

## <a name="chttpfileendrequest"></a><a name="endrequest"></a>CHttpFile::끝 요청

[SendRequestEx](#sendrequestex) 멤버 함수를 사용하여 HTTP 서버로 전송된 요청을 종료하려면 이 멤버 함수를 호출합니다.

```
BOOL EndRequest(
    DWORD dwFlags = 0,
    LPINTERNET_BUFFERS lpBuffIn = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
작업을 설명하는 플래그입니다. 적절한 플래그 목록은 Windows SDK의 [HttpEndRequest를](/windows/win32/api/wininet/nf-wininet-httpendrequestw) 참조하십시오.

*lpBuffIn*<br/>
작업에 사용되는 입력 버퍼를 설명하는 초기화 된 [INTERNET_BUFFERS](/windows/win32/api/wininet/ns-wininet-internet_buffersw) 대한 포인터입니다.

*dwContext*<br/>
`CHttpFile` 작업에 대한 컨텍스트 식별자입니다. 이 매개 변수에 대한 자세한 내용은 비고를 참조하십시오.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출이 실패하면 throw된 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체를 검사하여 오류의 원인을 확인합니다.

### <a name="remarks"></a>설명

*dwContext에* 대한 기본값은 MFC에서 `CHttpFile` `CHttpFile` 개체를 만든 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에서 개체로 전송됩니다. [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) 또는 [CHttpConnection를](../../mfc/reference/chttpconnection-class.md) 호출하여 `CHttpFile` 개체를 생성할 때 기본값을 재정의하여 컨텍스트 식별자를 선택한 값으로 설정할 수 있습니다. 컨텍스트 식별자가 [CInternetSession::OnStatusCallback으로](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 반환되어 식별되는 개체에 대한 상태를 제공합니다. 컨텍스트 식별자에 대한 자세한 내용은 [인터넷 첫 번째 단계 문서를](../../mfc/wininet-basics.md) 참조하십시오.

## <a name="chttpfilegetfileurl"></a><a name="getfileurl"></a>CHttpFile::GetFileURL

이 멤버 함수를 호출하여 HTTP 파일의 이름을 URL로 가져옵니다.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Return Value

이 파일과 연결된 리소스를 참조하는 URL을 포함하는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.

### <a name="remarks"></a>설명

[SendRequest에](#sendrequest) 대한 성공적인 호출 후 또는 `CHttpFile` [OpenURL에](../../mfc/reference/cinternetsession-class.md#openurl)의해 성공적으로 만들어진 개체에서만 이 멤버 함수를 사용합니다.

## <a name="chttpfilegetobject"></a><a name="getobject"></a>CHttpFile::GetObject

이 멤버 함수를 호출하여 이와 `CHttpFile`연결된 개체의 이름을 가져옵니다.

```
CString GetObject() const;
```

### <a name="return-value"></a>Return Value

개체의 이름을 포함하는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.

### <a name="remarks"></a>설명

[SendRequest에](#sendrequest) 대한 성공적인 호출 후 또는 `CHttpFile` [OpenURL에](../../mfc/reference/cinternetsession-class.md#openurl)의해 성공적으로 만들어진 개체에서만 이 멤버 함수를 사용합니다.

## <a name="chttpfilegetverb"></a><a name="getverb"></a>CHttpFile::GetVerb

이 멤버 함수를 호출하여 HTTP 동사(또는 `CHttpFile`메서드)를 이 와 연결합니다.

```
CString GetVerb() const;
```

### <a name="return-value"></a>Return Value

HTTP 동사 (또는 메서드)의 이름을 포함하는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.

### <a name="remarks"></a>설명

[SendRequest에](#sendrequest) 대한 성공적인 호출 후 또는 `CHttpFile` [OpenURL에](../../mfc/reference/cinternetsession-class.md#openurl)의해 성공적으로 만들어진 개체에서만 이 멤버 함수를 사용합니다.

## <a name="chttpfilequeryinfo"></a><a name="queryinfo"></a>CHttpFile::쿼리정보

이 멤버 함수를 호출하여 응답을 반환하거나 HTTP 요청에서 헤더를 요청합니다.

```
BOOL QueryInfo(
    DWORD dwInfoLevel,
    LPVOID lpvBuffer,
    LPDWORD lpdwBufferLength,
    LPDWORD lpdwIndex = NULL) const;

BOOL QueryInfo(
    DWORD dwInfoLevel,
    CString& str,
    LPDWORD dwIndex = NULL) const;

BOOL QueryInfo(
    DWORD dwInfoLevel,
    SYSTEMTIME* pSysTime,
    LPDWORD dwIndex = NULL) const;
```

### <a name="parameters"></a>매개 변수

*dwInfo레벨*<br/>
쿼리에 대한 특성과 요청된 정보 유형을 지정하는 다음 플래그의 조합입니다.

- HTTP_QUERY_CUSTOM 헤더 이름을 찾아 출력시 *lpvBuffer에서* 이 값을 반환합니다. HTTP_QUERY_CUSTOM 헤더를 찾을 수 없는 경우 어설션을 throw합니다.

- HTTP_QUERY_FLAG_REQUEST_HEADERS 일반적으로 응용 프로그램은 응답 헤더를 쿼리하지만 응용 프로그램은 이 플래그를 사용하여 요청 헤더를 쿼리할 수도 있습니다.

- HTTP_QUERY_FLAG_SYSTEMTIME 값이 "마지막 수정 시간"과 같은 날짜/시간 문자열인 헤더의 경우 이 플래그는 데이터를 구문 분석하기 위해 응용 프로그램이 필요하지 않은 표준 Win32 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조로 헤더 값을 반환합니다. 이 플래그를 사용하는 경우 함수의 `SYSTEMTIME` 재정의를 사용할 수 있습니다.

- HTTP_QUERY_FLAG_NUMBER 값이 숫자인 헤더(예: 상태 코드)의 경우 이 플래그는 데이터를 32비트 번호로 반환합니다.

가능한 값 목록은 **비고** 섹션을 참조하십시오.

*lpvBuffer*<br/>
정보를 받는 버퍼에 대한 포인터입니다.

*lpdw버퍼길이*<br/>
항목에서 이 값은 데이터 버퍼의 길이(문자 수 또는 바이트)를 포함하는 값을 가리킵니다. 이 매개 변수에 대한 자세한 내용은 **설명** 섹션을 참조하십시오.

*lpdw인덱스*<br/>
0기반 헤더 인덱스에 대한 포인터입니다. NULL일 수 있습니다. 이 플래그를 사용하여 동일한 이름의 여러 헤더를 등록합니다. 입력시 *lpdwIndex는* 반환할 지정된 헤더의 인덱스를 나타냅니다. 출력시 *lpdwIndex는* 다음 헤더의 인덱스를 나타냅니다. 다음 인덱스를 찾을 수 없는 경우 ERROR_HTTP_HEADER_NOT_FOUND 반환 됩니다.

*Str*<br/>
반환된 정보를 수신하는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 대한 참조입니다.

*dw인덱스*<br/>
인덱스 값입니다. *lpdwIndex*를 참조하십시오.

*pSysTime*<br/>
Win32 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

[SendRequest에](#sendrequest) 대한 성공적인 호출 후 또는 `CHttpFile` [OpenURL에](../../mfc/reference/cinternetsession-class.md#openurl)의해 성공적으로 만들어진 개체에서만 이 멤버 함수를 사용합니다.

`QueryInfo`다음 에서 다음과 같은 유형의 데이터를 검색할 수 있습니다.

- 문자열(기본값)

- `SYSTEMTIME`("데이터:" "만료:" 등, 헤더의 경우)

- DWORD(STATUS_CODE, CONTENT_LENGTH 등)

문자열이 버퍼에 기록되고 멤버 함수가 성공하면 `lpdwBufferLength` NULL 문자 종료에 대해 문자열에서 1을 뺀 문자열길이가 포함됩니다.

가능한 *dwInfoLevel* 값은 다음과 같습니다.

- HTTP_QUERY_MIME_VERSION

- HTTP_QUERY_CONTENT_TYPE

- HTTP_QUERY_CONTENT_TRANSFER_ENCODING

- HTTP_QUERY_CONTENT_ID

- HTTP_QUERY_CONTENT_DESCRIPTION

- HTTP_QUERY_CONTENT_LENGTH

- HTTP_QUERY_ALLOWED_METHODS

- HTTP_QUERY_PUBLIC_METHODS

- HTTP_QUERY_DATE

- HTTP_QUERY_EXPIRES

- HTTP_QUERY_LAST_MODIFIED

- HTTP_QUERY_MESSAGE_ID

- HTTP_QUERY_URI

- HTTP_QUERY_DERIVED_FROM

- HTTP_QUERY_LANGUAGE

- HTTP_QUERY_COST

- HTTP_QUERY_WWW_LINK

- HTTP_QUERY_PRAGMA

- HTTP_QUERY_VERSION

- HTTP_QUERY_STATUS_CODE

- HTTP_QUERY_STATUS_TEXT

- HTTP_QUERY_RAW_HEADERS

- HTTP_QUERY_RAW_HEADERS_CRLF

## <a name="chttpfilequeryinfostatuscode"></a><a name="queryinfostatuscode"></a>CHttpFile::쿼리정보 상태 코드

이 멤버 함수를 호출하여 HTTP 요청과 연결된 상태 코드를 받고 제공된 *dwStatusCode* 매개 변수에 배치합니다.

```
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;
```

### <a name="parameters"></a>매개 변수

*dw 상태 코드*<br/>
상태 코드에 대한 참조입니다. 상태 코드는 요청된 이벤트의 성공 또는 실패를 나타냅니다. 상태 코드 설명 의 선택에 대 한 **설명을** 참조 하십시오.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

[SendRequest에](#sendrequest) 대한 성공적인 호출 후 또는 `CHttpFile` [OpenURL에](../../mfc/reference/cinternetsession-class.md#openurl)의해 성공적으로 만들어진 개체에서만 이 멤버 함수를 사용합니다.

HTTP 상태 코드는 요청의 성공 또는 실패를 나타내는 그룹으로 나뉩니다. 다음 표에서는 상태 코드 그룹과 가장 일반적인 HTTP 상태 코드를 간략하게 설명합니다.

|그룹|의미|
|-----------|-------------|
|200-299|Success|
|300-399|정보|
|400-499|오류 요청|
|500-599|서버 오류|

일반적인 HTTP 상태 코드:

|상태 코드|의미|
|-----------------|-------------|
|200|위치 URL, 전송은 다음과 같습니다.|
|400|이해할 수 없는 요청|
|404|요청된 URL을 찾을 수 없습니다.|
|405|서버가 요청된 메서드를 지원하지 않습니다.|
|500|알 수 없는 서버 오류|
|503|서버 용량에 도달했습니다.|

## <a name="chttpfilesendrequest"></a><a name="sendrequest"></a>CHttpFile::보내기 요청

HTTP 서버에 요청을 보내려면 이 멤버 함수를 호출합니다.

```
BOOL SendRequest(
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLen = 0,
    LPVOID lpOptional = NULL,
    DWORD dwOptionalLen = 0);

BOOL SendRequest(
    CString& strHeaders,
    LPVOID lpOptional = NULL,
    DWORD dwOptionalLen = 0);
```

### <a name="parameters"></a>매개 변수

*pstr헤더*<br/>
보낼 헤더의 이름이 포함된 문자열에 대한 포인터입니다.

*dw헤더슬렌*<br/>
*pstrHeaders로*식별된 헤더의 길이입니다.

*lp선택 사항*<br/>
요청 헤더 직후에 보낼 선택적 데이터입니다. 이것은 일반적으로 POST 및 PUT 작업에 사용됩니다. 보낼 선택적 데이터가 없는 경우 NULL이 될 수 있습니다.

*dw옵션렌*<br/>
*lp의 길이선택적*.

*스트헤더*<br/>
전송되는 요청에 대한 헤더 의 이름이 포함된 문자열입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출이 실패하면 throw된 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체를 검사하여 오류의 원인을 확인합니다.

## <a name="chttpfilesendrequestex"></a><a name="sendrequestex"></a>CHttpFile::SendRequestEx

HTTP 서버에 요청을 보내려면 이 멤버 함수를 호출합니다.

```
BOOL SendRequestEx(
    DWORD dwTotalLen,
    DWORD dwFlags = HSR_INITIATE,
    DWORD_PTR dwContext = 1);

BOOL SendRequestEx(
    LPINTERNET_BUFFERS lpBuffIn,
    LPINTERNET_BUFFERS lpBuffOut,
    DWORD dwFlags = HSR_INITIATE,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*dwTotalLen*<br/>
요청에서 보낼 바이트 수입니다.

*dwFlags*<br/>
작업을 설명하는 플래그입니다. 적절한 플래그 목록은 Windows SDK의 [HttpSendRequestEx를](/windows/win32/api/wininet/nf-wininet-httpsendrequestexw) 참조하십시오.

*dwContext*<br/>
`CHttpFile` 작업에 대한 컨텍스트 식별자입니다. 이 매개 변수에 대한 자세한 내용은 비고를 참조하십시오.

*lpBuffIn*<br/>
작업에 사용되는 입력 버퍼를 설명하는 초기화 된 [INTERNET_BUFFERS](/windows/win32/api/wininet/ns-wininet-internet_buffersw) 대한 포인터입니다.

*lpBuffOut*<br/>
작업에 사용되는 출력 버퍼를 설명하는 초기화된 INTERNET_BUFFERS 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 영하지 않습니다. 호출이 실패하면 throw된 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체를 검사하여 오류의 원인을 확인합니다.

### <a name="remarks"></a>설명

이 함수를 사용하면 응용 프로그램에서 [의 쓰기](../../mfc/reference/cinternetfile-class.md#write) 및 [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) 메서드를 사용하여 데이터를 보낼 수 `CInternetFile`있습니다. 이 함수의 재정의를 호출하기 전에 보낼 데이터의 길이를 알아야 합니다. 첫 번째 재정의를 사용하면 보낼 데이터의 길이를 지정할 수 있습니다. 두 번째 재정의는 INTERNET_BUFFERS 구조에 대한 포인터를 허용하며, 이 포인터는 버퍼를 자세히 설명하는 데 사용할 수 있습니다.

콘텐츠가 파일에 기록되면 [EndRequest를](#endrequest) 호출하여 작업을 종료합니다.

*dwContext에* 대한 기본값은 MFC에서 `CHttpFile` `CHttpFile` 개체를 만든 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에서 개체로 전송됩니다. [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) 또는 [CHttpConnection를](../../mfc/reference/chttpconnection-class.md) 호출하여 `CHttpFile` 개체를 생성할 때 기본값을 재정의하여 컨텍스트 식별자를 선택한 값으로 설정할 수 있습니다. 컨텍스트 식별자가 [CInternetSession::OnStatusCallback으로](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 반환되어 식별되는 개체에 대한 상태를 제공합니다. 컨텍스트 식별자에 대한 자세한 내용은 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 문서를 참조하십시오.

### <a name="example"></a>예제

이 코드 조각은 문자열의 내용을 MFCISAPI라는 DLL로 보냅니다. 로컬 호스트 서버의 DLL입니다. 이 예제에서는 블록에서 `WriteString`데이터를 전송하기 위해 여러 호출을 사용하는 호출을 하나만 사용하는 것이 허용됩니다.

[!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]

## <a name="see-also"></a>참고 항목

[C인터넷파일 클래스](../../mfc/reference/cinternetfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C인터넷파일 클래스](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpConnection 클래스](../../mfc/reference/chttpconnection-class.md)
