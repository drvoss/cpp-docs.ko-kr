---
title: CGopher파일찾기 클래스
ms.date: 11/04/2016
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
helpviewer_keywords:
- CGopherFileFind [MFC], CGopherFileFind
- CGopherFileFind [MFC], FindFile
- CGopherFileFind [MFC], FindNextFile
- CGopherFileFind [MFC], GetCreationTime
- CGopherFileFind [MFC], GetLastAccessTime
- CGopherFileFind [MFC], GetLastWriteTime
- CGopherFileFind [MFC], GetLength
- CGopherFileFind [MFC], GetLocator
- CGopherFileFind [MFC], GetScreenName
- CGopherFileFind [MFC], IsDots
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
ms.openlocfilehash: 7a42b99c919abd9098bff1897c4c5febf443314d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373689"
---
# <a name="cgopherfilefind-class"></a>CGopher파일찾기 클래스

Gopher 서버의 인터넷 파일 검색에 유용합니다.

> [!NOTE]
> 클래스 `CGopherConnection`및 `CGopherFile` `CGopherFileFind` `CGopherLocator` 해당 구성원은 Windows XP 플랫폼에서 작동하지 않지만 이전 플랫폼에서 계속 작동하므로 더 이상 사용되지 않습니다.

## <a name="syntax"></a>구문

```
class CGopherFileFind : public CFileFind
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CGopher파일찾기::CGopherFileFind](#cgopherfilefind)|`CGopherFileFind` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CGopherFileFind::찾기 파일](#findfile)|고퍼 서버에서 파일을 찾습니다.|
|[CGopherFileFind::FindNextFile](#findnextfile)|[FindFile](#findfile)에 대한 이전 호출에서 파일 검색을 계속합니다.|
|[CGopherFileFind::GetCreationTime](#getcreationtime)|지정된 파일이 생성된 시간을 가져옵니다.|
|[CGopher파일찾기::겟라스트액세스타임](#getlastaccesstime)|지정된 파일에 마지막으로 액세스한 시간을 가져옵니다.|
|[CGopher파일찾기::겟라스트쓰기타임](#getlastwritetime)|지정된 파일이 마지막으로 작성된 시간을 가져옵니다.|
|[CGopherFileFind::GetLength](#getlength)|발견된 파일의 길이를 바이트로 가져옵니다.|
|[CGopherFileFind::GetLocator](#getlocator)|개체를 `CGopherLocator` 가져옵니다.|
|[CGopherFileFind::GetScreenName](#getscreenname)|고퍼 화면의 이름을 가져옵니다.|
|[CGopher파일찾기::이도트](#isdots)|파일을 반복하는 동안 현재 디렉터리 및 상위 디렉터리 마커에 대한 테스트입니다.|

## <a name="remarks"></a>설명

`CGopherFileFind`에는 검색을 시작하고 파일을 찾고 파일의 URL을 반환하는 멤버 함수가 포함됩니다.

인터넷 및 로컬 파일 검색용으로 설계된 다른 MFC 클래스에는 [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) 및 [CFileFind](../../mfc/reference/cfilefind-class.md)가 있습니다. 이러한 `CGopherFileFind`클래스와 함께 사용자는 서버 프로토콜, 파일 형식 또는 위치(로컬 컴퓨터 또는 원격 서버)에 관계없이 특정 파일을 찾을 수 있는 원활한 메커니즘을 제공합니다. HTTP는 검색에 필요한 직접 파일 조작을 지원하지 않으므로 HTTP 서버에서 검색할 수 있는 MFC 클래스가 없습니다.

> [!NOTE]
> `CGopherFileFind`기본 클래스 [CFileFind의](../../mfc/reference/cfilefind-class.md)다음 멤버 함수를 지원하지 않습니다.

- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)

- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)

- [GetFile 경로](../../mfc/reference/cfilefind-class.md#getfilepath)

- [GetFile 타이틀](../../mfc/reference/cfilefind-class.md#getfiletitle)

- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)

또한 와 함께 `CGopherFileFind`사용할 `CFileFind` 때 는 멤버 함수 [IsDots는](../../mfc/reference/cfilefind-class.md#isdots) 항상 FALSE입니다.

사용 `CGopherFileFind` 방법 및 기타 WinInet 클래스에 대한 자세한 내용은 [WinInet와 함께](../../mfc/win32-internet-extensions-wininet.md)인터넷 프로그래밍 문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CGopherFileFind`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="cgopherfilefindcgopherfilefind"></a><a name="cgopherfilefind"></a>CGopher파일찾기::CGopherFileFind

이 멤버 함수는 개체를 생성하기 위해 호출됩니다. `CGopherFileFind`

```
explicit CGopherFileFind(
    CGopherConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*pConnection*<br/>
[CGopherConnection](../../mfc/reference/cgopherconnection-class.md) 개체에 대한 포인터입니다.

*dwContext*<br/>
작업에 대 한 컨텍스트 식별자입니다. *dwContext*에 대한 자세한 내용은 **비고를** 참조하십시오.

### <a name="remarks"></a>설명

*dwContext에* 대한 기본값은 MFC에서 `CGopherFileFind` `CGopherFileFind` 개체를 만든 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에서 개체로 전송됩니다. 개체를 `CGopherFileFind` 생성할 때 기본값을 재정의하여 컨텍스트 식별자를 선택한 값으로 설정할 수 있습니다. 컨텍스트 식별자가 [CInternetSession::OnStatusCallback으로](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 반환되어 식별되는 개체에 대한 상태를 제공합니다. 컨텍스트 식별자에 대한 자세한 내용은 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 문서를 참조하십시오.

## <a name="cgopherfilefindfindfile"></a><a name="findfile"></a>CGopherFileFind::찾기 파일

이 멤버 함수를 호출하여 gopher 파일을 찾습니다.

```
virtual BOOL FindFile(
    CGopherLocator& refLocator,
    LPCTSTR pstrString,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

virtual BOOL FindFile(
    LPCTSTR pstrString,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>매개 변수

*refLocator*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체에 대한 참조입니다.

*스트링 스트링*<br/>
파일 이름이 포함된 문자열에 대한 포인터입니다.

*dwFlags*<br/>
이 세션을 처리하는 방법을 설명하는 플래그입니다. 유효한 플래그는 다음과 같습니다.

- INTERNET_FLAG_RELOAD 로컬로 캐시된 경우에도 원격 서버에서 데이터를 가져옵니다.

- INTERNET_FLAG_DONT_CACHE 로컬 또는 게이트웨이에서 데이터를 캐시하지 마십시오.

- INTERNET_FLAG_SECURE 보안 소켓 계층 또는 PCT를 통해 와이어에서 안전한 거래를 요청합니다. 이 플래그는 HTTP 요청에만 적용됩니다.

- INTERNET_FLAG_USE_EXISTING 가능하면 각 요청에 대해 새 세션을 `FindFile` 만드는 대신 서버에 대한 기존 연결을 새 요청에 다시 사용합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 확장 오류 정보를 얻으려면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)호출합니다.

### <a name="remarks"></a>설명

`FindFile` 호출후 첫 번째 gopher 개체를 검색 할 수 있습니다 [FindNextFile](#findnextfile) 후속 고퍼 파일을 검색 할 수 있습니다.

## <a name="cgopherfilefindfindnextfile"></a><a name="findnextfile"></a>CGopherFileFind::FindNextFile

이 멤버 함수를 호출하여 [CGopherFileFind::FindFile](#findfile)을 호출하여 시작된 파일 검색을 계속합니다.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Return Value

파일이 더 많은 경우 0이 아닙니다. 발견된 파일이 디렉터리에서 마지막 파일이거나 오류가 발생한 경우 0입니다. 확장 오류 정보를 얻으려면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)호출합니다. 발견된 파일이 디렉터리에서 마지막 파일이거나 일치하는 파일을 찾을 수 없는 `GetLastError` 경우 함수는 ERROR_NO_MORE_FILES 반환합니다.

## <a name="cgopherfilefindgetcreationtime"></a><a name="getcreationtime"></a>CGopherFileFind::GetCreationTime

현재 파일의 생성 시간을 가져옵니다.

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>매개 변수

*p타임 스탬프*<br/>
파일이 생성된 시간을 포함하는 [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 구조에 대한 포인터입니다.

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하면 영하지 않은; 0이 실패하면 `GetCreationTime`[FindNextFile이](#findnextfile) 이 `CGopherFileFind` 개체에서 호출된 적이 없는 경우에만 0을 반환합니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `GetCreationTime`번 이상 호출해야 합니다.

> [!NOTE]
> 모든 파일 시스템이 동일한 의미 체계를 사용하여 이 함수에서 반환되는 타임스탬프를 구현하는 것은 아닙니다. 이 함수는 기본 파일 시스템 또는 서버가 시간 특성 유지를 지원하지 않는 경우 다른 타임스탬프 함수에서 반환하는 동일한 값을 반환할 수 있습니다. 시간 형식에 대한 자세한 내용은 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조를 참조하십시오. 일부 운영 체제에서 반환된 시간은 파일이 있는 컴퓨터의 로컬 표준 시간대에 있습니다. 자세한 내용은 Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API를 참조하십시오.

## <a name="cgopherfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a>CGopher파일찾기::겟라스트액세스타임

지정된 파일에 마지막으로 액세스한 시간을 가져옵니다.

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>매개 변수

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 참조입니다.

*p타임 스탬프*<br/>
파일이 마지막으로 액세스한 시간을 포함하는 [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 영하지 않은; 0이 실패하면 `GetLastAccessTime`[FindNextFile이](#findnextfile) 이 `CGopherFileFind` 개체에서 호출된 적이 없는 경우에만 0을 반환합니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `GetLastAccessTime`번 이상 호출해야 합니다.

> [!NOTE]
> 모든 파일 시스템이 동일한 의미 체계를 사용하여 이 함수에서 반환되는 타임스탬프를 구현하는 것은 아닙니다. 이 함수는 기본 파일 시스템 또는 서버가 시간 특성 유지를 지원하지 않는 경우 다른 타임스탬프 함수에서 반환하는 동일한 값을 반환할 수 있습니다. 시간 형식에 대한 자세한 내용은 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조를 참조하십시오. 일부 운영 체제에서 반환된 시간은 파일이 있는 컴퓨터의 로컬 표준 시간대에 있습니다. 자세한 내용은 Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API를 참조하십시오.

## <a name="cgopherfilefindgetlastwritetime"></a><a name="getlastwritetime"></a>CGopher파일찾기::겟라스트쓰기타임

파일이 마지막으로 변경된 시간을 가져옵니다.

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>매개 변수

*p타임 스탬프*<br/>
파일이 마지막으로 작성된 시간을 포함하는 [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 구조에 대한 포인터입니다.

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하면 영하지 않은; 0이 실패하면 `GetLastWriteTime`[FindNextFile이](#findnextfile) 이 `CGopherFileFind` 개체에서 호출된 적이 없는 경우에만 0을 반환합니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `GetLastWriteTime`번 이상 호출해야 합니다.

> [!NOTE]
> 모든 파일 시스템이 동일한 의미 체계를 사용하여 이 함수에서 반환되는 타임스탬프를 구현하는 것은 아닙니다. 이 함수는 기본 파일 시스템 또는 서버가 시간 특성 유지를 지원하지 않는 경우 다른 타임스탬프 함수에서 반환하는 동일한 값을 반환할 수 있습니다. 시간 형식에 대한 자세한 내용은 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조를 참조하십시오. 일부 운영 체제에서 반환된 시간은 파일이 있는 컴퓨터의 로컬 표준 시간대에 있습니다. 자세한 내용은 Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API를 참조하십시오.

## <a name="cgopherfilefindgetlength"></a><a name="getlength"></a>CGopherFileFind::GetLength

이 멤버 함수를 호출하여 찾은 파일의 길이(바이트)를 가져옵니다.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Return Value

발견된 파일의 길이(바이트)입니다.

### <a name="remarks"></a>설명

`GetLength`WIN32_FIND_DATA Win32 [구조를](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 사용하여 파일 크기 값을 바이트로 가져옵니다.

> [!NOTE]
> MFC 7.0에서 `GetLength` 64비트 정수 유형을 지원합니다. 이 최신 버전의 라이브러리로 빌드된 기존 코드는 잘림 경고가 발생할 수 있습니다.

### <a name="example"></a>예제

  [CFile::GetLength(기본](../../mfc/reference/cfile-class.md#getlength) 클래스 구현)에 대한 예제를 참조하십시오.

## <a name="cgopherfilefindgetlocator"></a><a name="getlocator"></a>CGopherFileFind::GetLocator

이 멤버 함수를 호출하여 [FindFile에서](#findfile) 고퍼 파일을 찾는 데 사용하는 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체를 가져옵니다.

```
CGopherLocator GetLocator() const;
```

### <a name="return-value"></a>Return Value

`CGopherLocator` 개체입니다.

## <a name="cgopherfilefindgetscreenname"></a><a name="getscreenname"></a>CGopherFileFind::GetScreenName

이 멤버 함수를 호출하여 gopher 화면의 이름을 가져옵니다.

```
CString GetScreenName() const;
```

### <a name="return-value"></a>Return Value

고퍼 화면의 이름입니다.

## <a name="cgopherfilefindisdots"></a><a name="isdots"></a>CGopher파일찾기::이도트

파일을 반복하는 동안 현재 디렉터리 및 상위 디렉터리 마커에 대한 테스트입니다.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Return Value

발견된 파일에 "." 또는 "."라는 이름이 있는 경우 Nonzero는 발견된 파일이 실제로 디렉터리임을 나타냅니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `IsDots`번 이상 호출해야 합니다.

## <a name="see-also"></a>참고 항목

[CFileFind 클래스](../../mfc/reference/cfilefind-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFtp파일찾기 클래스](../../mfc/reference/cftpfilefind-class.md)<br/>
[CFileFind 클래스](../../mfc/reference/cfilefind-class.md)<br/>
[C인터넷파일 클래스](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile 클래스](../../mfc/reference/chttpfile-class.md)
