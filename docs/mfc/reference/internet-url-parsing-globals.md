---
title: 글로벌 및 도우미를 구문 분석하는 인터넷 URL
ms.date: 04/03/2017
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
ms.openlocfilehash: 742b381ecb55c433d0f384174b7612fcc21e9716
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356614"
---
# <a name="internet-url-parsing-globals-and-helpers"></a>글로벌 및 도우미를 구문 분석하는 인터넷 URL

클라이언트가 인터넷 서버에 쿼리를 보내는 경우 전역을 구문 분석하는 URL 중 하나를 사용하여 클라이언트에 대한 정보를 추출할 수 있습니다. 도우미 기능은 다른 인터넷 기능을 제공합니다.

## <a name="internet-url-parsing-globals"></a>인터넷 URL 전역 구문 분석

|||
|-|-|
|[AfxParseURL](#afxparseurl)|URL 문자열을 구문 분석 하 고 서비스 유형 및 해당 구성 요소를 반환 합니다.|
|[AfxParseURLEx](#afxparseurlex)|URL 문자열을 구문 분석하 고 서비스 유형 및 해당 구성 요소를 반환 하 고 사용자 이름 및 암호를 제공 합니다.|

## <a name="other-internet-helpers"></a>기타 인터넷 도우미

|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|인터넷 연결과 관련된 예외를 throw합니다.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|인터넷 핸들의 유형을 결정합니다.|

## <a name="afxparseurl"></a><a name="afxparseurl"></a>아프파르세URL

이 글로벌 [CInternetSession에서 사용 됩니다.:OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

```
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort);
```

### <a name="parameters"></a>매개 변수

*프스트URL*<br/>
구문 분석할 URL을 포함하는 문자열에 대한 포인터입니다.

*dwServiceType*<br/>
인터넷 서비스의 유형을 나타냅니다. 가능한 값은 다음과 같습니다.

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*스트서버*<br/>
서비스 유형 다음에 URL의 첫 번째 세그먼트입니다.

*스트오브젝트*<br/>
URL이 참조하는 개체입니다(비어 있을 수 있음).

*nPort*<br/>
있는 경우 URL의 서버 또는 개체 부분에서 결정됩니다.

### <a name="return-value"></a>Return Value

URL이 구문 분석된 경우 0이 아닙니다. 그렇지 않으면 비어 있거나 알려진 인터넷 서비스 형식을 포함하지 않는 경우 0입니다.

### <a name="remarks"></a>설명

URL 문자열을 구문 분석 하 고 서비스 유형 및 해당 구성 요소를 반환 합니다.

예를 들어 `AfxParseURL` 양식의 URL을 *service://server/dir/dir/object.ext:port* 구문 분석하고 다음과 같이 저장된 구성 요소를 반환합니다.

*strServer* == "서버"

*strObject* == "/디르/디르/디르/object/object.ext"

*nPort* == #port

*dwServiceType* == #service

> [!NOTE]
> 이 함수를 호출하려면 프로젝트에 AFXINET이 포함되어야 합니다. H.

### <a name="requirements"></a>요구 사항

  **헤더** afxinet.h

## <a name="afxparseurlex"></a><a name="afxparseurlex"></a>아프파르세URL렉스

이 글로벌 함수는 [AfxParseURL의](#afxparseurl) 확장 버전이며 [CInternetSession::OpenURL에서](../../mfc/reference/cinternetsession-class.md#openurl)사용됩니다.

```
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort,
    CString& strUsername,
    CString& strPassword,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>매개 변수

*프스트URL*<br/>
구문 분석할 URL을 포함하는 문자열에 대한 포인터입니다.

*dwServiceType*<br/>
인터넷 서비스의 유형을 나타냅니다. 가능한 값은 다음과 같습니다.

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*스트서버*<br/>
서비스 유형 다음에 URL의 첫 번째 세그먼트입니다.

*스트오브젝트*<br/>
URL이 참조하는 개체입니다(비어 있을 수 있음).

*nPort*<br/>
있는 경우 URL의 서버 또는 개체 부분에서 결정됩니다.

*str사용자 이름*<br/>
사용자 이름을 `CString` 포함하는 개체에 대한 참조입니다.

*스트패스암호*<br/>
사용자의 암호를 `CString` 포함하는 개체에 대한 참조입니다.

*dwFlags*<br/>
URL을 구문 분석하는 방법을 제어하는 플래그입니다. 다음 값의 조합일 수 있습니다.

|값|의미|
|-----------|-------------|
|ICU_DECODE|%XX 이스케이프 시퀀스를 문자로 변환합니다.|
|ICU_NO_ENCODE|안전하지 않은 문자를 이스케이프 시퀀스로 변환하지 마십시오.|
|ICU_NO_META|메타 시퀀스를 제거하지 마십시오(예: "\ " 및 "\ ..") URL에서 볼 수 있습니다.|
|ICU_ENCODE_SPACES_ONLY|공백만 인코딩합니다.|
|ICU_BROWSER_MODE|'#' 또는 '' 다음 의 문자를 인코딩하거나 디코딩하지 말고 '' 이후의 공백을 제거하지 마십시오. 이 값을 지정하지 않으면 전체 URL이 인코딩되고 후행 공백이 제거됩니다.|

플래그가 없는 MFC 기본값을 사용하는 경우 함수는 모든 안전하지 않은 문자와 메타 \\시퀀스(예: \\.,\\., 및 ...)를 변환하여 시퀀스를 이스케이프합니다.

### <a name="return-value"></a>Return Value

URL이 구문 분석된 경우 0이 아닙니다. 그렇지 않으면 비어 있거나 알려진 인터넷 서비스 형식을 포함하지 않는 경우 0입니다.

### <a name="remarks"></a>설명

URL 문자열을 구문 분석 하 고 서비스 유형 및 해당 구성 요소를 반환 하 고 사용자의 이름과 암호를 제공 합니다. 플래그는 안전하지 않은 문자를 처리하는 방법을 나타냅니다.

> [!NOTE]
> 이 함수를 호출하려면 프로젝트에 AFXINET이 포함되어야 합니다. H.

### <a name="requirements"></a>요구 사항

  **헤더** afxinet.h

## <a name="afxgetinternethandletype"></a><a name="afxgetinternethandletype"></a>AfxGet인터넷핸들타입

이 전역 함수를 사용하여 인터넷 핸들의 유형을 확인합니다.

### <a name="syntax"></a>구문

  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );
```

### <a name="parameters"></a>매개 변수

*h쿼리*<br/>
인터넷 쿼리에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

WININET에서 정의한 모든 인터넷 서비스 유형입니다. H. 이러한 인터넷 서비스 목록은 비고 섹션을 참조하십시오. 핸들이 NULL이거나 인식되지 않으면 함수가 AFX_INET_SERVICE_UNK 반환합니다.

### <a name="remarks"></a>설명

다음 목록에는 에서 반환할 `AfxGetInternetHandleType`수 있는 인터넷 유형이 포함됩니다.

- INTERNET_HANDLE_TYPE_INTERNET

- INTERNET_HANDLE_TYPE_CONNECT_FTP

- INTERNET_HANDLE_TYPE_CONNECT_GOPHER

- INTERNET_HANDLE_TYPE_CONNECT_HTTP

- INTERNET_HANDLE_TYPE_FTP_FIND

- INTERNET_HANDLE_TYPE_FTP_FIND_HTML

- INTERNET_HANDLE_TYPE_FTP_FILE

- INTERNET_HANDLE_TYPE_FTP_FILE_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FIND

- INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FILE

- INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML

- INTERNET_HANDLE_TYPE_HTTP_REQUEST

> [!NOTE]
> 이 함수를 호출하려면 프로젝트에 AFXINET이 포함되어야 합니다. H.

### <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="afxthrowinternetexception"></a><a name="afxthrowinternetexception"></a>AfxThrow인터넷예외

인터넷 예외를 throw합니다.

### <a name="syntax"></a>구문

```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );
```

### <a name="parameters"></a>매개 변수

*dwContext*<br/>
오류를 일으킨 작업에 대한 컨텍스트 식별자입니다. *dwContext의* 기본값은 [CInternetSession에서](cinternetsession-class.md) 원래 지정되며 [CInternetConnection](cinternetconnection-class.md)및 [CInternetFile](cinternetfile-class.md)-파생 클래스로 전달됩니다. 연결 또는 파일에서 수행되는 특정 작업의 경우 일반적으로 기본값을 *dwContext* 를 사용 하여 재정의합니다. 이 값은 [CInternetSession::OnStatusCallback으로](cinternetsession-class.md#onstatuscallback) 반환되어 특정 작업의 상태를 식별합니다.

*dwError*<br/>
예외를 일으킨 오류입니다.

### <a name="remarks"></a>설명

운영 체제 오류 코드를 기반으로 원인을 확인할 책임은 있습니다.

> [!NOTE]
> 이 함수를 호출하려면 프로젝트에 AFXINET이 포함되어야 합니다. H.

### <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[C인터넷예외 클래스](cinternetexception-class.md)<br/>
[AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
