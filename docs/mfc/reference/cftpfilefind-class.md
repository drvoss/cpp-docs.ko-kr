---
title: CFtp파일찾기 클래스
ms.date: 11/04/2016
f1_keywords:
- CFtpFileFind
- AFXINET/CFtpFileFind
- AFXINET/CFtpFileFind::CFtpFileFind
- AFXINET/CFtpFileFind::FindFile
- AFXINET/CFtpFileFind::FindNextFile
- AFXINET/CFtpFileFind::GetFileURL
helpviewer_keywords:
- CFtpFileFind [MFC], CFtpFileFind
- CFtpFileFind [MFC], FindFile
- CFtpFileFind [MFC], FindNextFile
- CFtpFileFind [MFC], GetFileURL
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
ms.openlocfilehash: cf4afb4a683c2d0cf5f2977107d02ee300a53cb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373749"
---
# <a name="cftpfilefind-class"></a>CFtp파일찾기 클래스

FTP 서버의 인터넷 파일 검색에 유용합니다.

## <a name="syntax"></a>구문

```
class CFtpFileFind : public CFileFind
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CFtp파일찾기::CFtp파일찾기](#cftpfilefind)|`CFtpFileFind` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CFtpFileFind::찾기 파일](#findfile)|FTP 서버에서 파일을 찾습니다.|
|[CFtpFileFind::찾기다음 파일](#findnextfile)|[FindFile](#findfile)에 대한 이전 호출에서 파일 검색을 계속합니다.|
|[CFtpFileFind::GetFileURL](#getfileurl)|찾은 파일의 경로를 포함한 URL을 가져옵니다.|

## <a name="remarks"></a>설명

`CFtpFileFind`에는 검색을 시작하고, 파일을 찾고, 파일에 대한 URL 또는 기타 설명 정보를 반환하는 멤버 함수가 포함됩니다.

인터넷 및 로컬 파일 검색용으로 설계된 다른 MFC 클래스에는 [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) 및 [CFileFind](../../mfc/reference/cfilefind-class.md)가 있습니다. 이러한 `CFtpFileFind`클래스와 함께 클라이언트는 서버 프로토콜 이나 파일 형식(로컬 컴퓨터 또는 원격 서버)에 관계없이 특정 파일을 찾을 수 있는 원활한 메커니즘을 제공합니다. HTTP가 검색에 필요한 직접 파일 조작을 지원하지 않으므로 HTTP 서버에서 검색할 수 있는 MFC 클래스가 없습니다.

사용 `CFtpFileFind` 방법 및 기타 WinInet 클래스에 대한 자세한 내용은 [WinInet와 함께](../../mfc/win32-internet-extensions-wininet.md)인터넷 프로그래밍 문서를 참조하십시오.

## <a name="example"></a>예제

다음 코드는 FTP 서버의 현재 디렉터리에서 모든 파일을 열거하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CFtpFileFind`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="cftpfilefindcftpfilefind"></a><a name="cftpfilefind"></a>CFtp파일찾기::CFtp파일찾기

이 멤버 함수는 개체를 생성하기 위해 호출됩니다. `CFtpFileFind`

```
explicit CFtpFileFind(
    CFtpConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*pConnection*<br/>
`CFtpConnection` 개체에 대한 포인터입니다. [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)를 호출하여 FTP 연결을 얻을 수 있습니다.

*dwContext*<br/>
개체에 대한 컨텍스트 `CFtpFileFind` 식별자입니다. 이 매개 변수에 대한 자세한 내용은 **비고를** 참조하십시오.

### <a name="remarks"></a>설명

*dwContext에* 대한 기본값은 MFC에서 `CFtpFileFind` `CFtpFileFind` 개체를 만든 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에서 개체로 전송됩니다. 기본값을 재정의하여 컨텍스트 식별자를 선택한 값으로 설정할 수 있습니다. 컨텍스트 식별자가 [CInternetSession::OnStatusCallback으로](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 반환되어 식별되는 개체에 대한 상태를 제공합니다. 컨텍스트 식별자에 대한 자세한 내용은 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 문서를 참조하십시오.

### <a name="example"></a>예제

  이 항목의 이전 클래스 개요에서 예제를 참조하십시오.

## <a name="cftpfilefindfindfile"></a><a name="findfile"></a>CFtpFileFind::찾기 파일

FTP 파일을 찾으려면 이 멤버 함수를 호출합니다.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>매개 변수

*pstrName*<br/>
찾을 파일의 이름을 포함하는 문자열에 대한 포인터입니다. NULL이면 호출이 와일드카드 검색(*)을 수행합니다.

*dwFlags*<br/>
이 세션을 처리하는 방법을 설명하는 플래그입니다. 이러한 플래그는 비트별 OR 연산자(&#124;)와 결합할 수 있으며 다음과 같습니다.

- INTERNET_FLAG_RELOAD 로컬로 캐시된 경우에도 와이어에서 데이터를 가져옵니다. 기본 플래그입니다.

- INTERNET_FLAG_DONT_CACHE 로컬 또는 게이트웨이에서 데이터를 캐시하지 마십시오.

- INTERNET_FLAG_RAW_DATA 기본값을 재정의하여 원시 데이터(FTP의 [경우 WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조)를 반환합니다.

- INTERNET_FLAG_SECURE 보안 소켓 계층 또는 PCT로 와이어에서 트랜잭션을 보호합니다. 이 플래그는 HTTP 요청에만 적용됩니다.

- INTERNET_FLAG_EXISTING_CONNECT 가능하면 각 요청에 대해 새 세션을 `FindFile` 만드는 대신 서버에 대한 기존 연결을 새 요청에 다시 사용합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 확장 오류 정보를 얻으려면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)호출합니다.

### <a name="remarks"></a>설명

호출후 `FindFile` 첫 번째 FTP 파일을 검색, 후속 FTP 파일을 검색 하는 [FindNextFile를](#findnextfile) 호출할 수 있습니다.

### <a name="example"></a>예제

  이 항목의 이전 예제를 참조하십시오.

## <a name="cftpfilefindfindnextfile"></a><a name="findnextfile"></a>CFtpFileFind::찾기다음 파일

[FindFile](#findfile) 멤버 함수에 대한 호출로 시작된 파일 검색을 계속하려면 이 멤버 함수를 호출합니다.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Return Value

파일이 더 많은 경우 0이 아닙니다. 발견된 파일이 디렉터리에서 마지막 파일이거나 오류가 발생한 경우 0입니다. 확장 오류 정보를 얻으려면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)호출합니다. 발견된 파일이 디렉터리에서 마지막 파일이거나 일치하는 파일을 찾을 수 없는 `GetLastError` 경우 함수는 ERROR_NO_MORE_FILES 반환합니다.

### <a name="remarks"></a>설명

특성 함수를 호출하기 전에 이 함수를 한 번 이상 호출해야 [합니다(CFileFind:FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)참조).

`FindNextFile`Win32 함수 [FindNextFile을](/windows/win32/api/fileapi/nf-fileapi-findnextfilew)래핑합니다.

### <a name="example"></a>예제

  이 항목의 이전 예제를 참조하십시오.

## <a name="cftpfilefindgetfileurl"></a><a name="getfileurl"></a>CFtpFileFind::GetFileURL

지정된 파일의 URL을 얻으려면 이 멤버 함수를 호출합니다.

```
CString GetFileURL() const;
```

### <a name="return-value"></a>Return Value

범용 리소스 로케이터(URL)의 파일 및 경로입니다.

### <a name="remarks"></a>설명

`GetFileURL`형식의 URL을 반환한다는 점을 제외하면 멤버 함수 [CFileFind::GetFilePath와](../../mfc/reference/cfilefind-class.md#getfilepath) `ftp://moose/dir/file.txt`유사합니다.

## <a name="see-also"></a>참고 항목

[CFileFind 클래스](../../mfc/reference/cfilefind-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CGopher파일찾기 클래스](../../mfc/reference/cgopherfilefind-class.md)<br/>
[C인터넷파일 클래스](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile 클래스](../../mfc/reference/chttpfile-class.md)
