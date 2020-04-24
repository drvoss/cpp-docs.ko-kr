---
title: CFileFind 클래스
ms.date: 11/04/2016
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
ms.openlocfilehash: 5bb53a6abf7040bd6ee9f5f2cf56b0feb4d62e66
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755024"
---
# <a name="cfilefind-class"></a>CFileFind 클래스

로컬 파일 검색을 수행하고 인터넷 파일 검색을 수행하는 [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) 및 [CFtpFileFind의](../../mfc/reference/cftpfilefind-class.md)기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CFileFind : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C파일찾기::CFileFind](#cfilefind)|`CFileFind` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C파일찾기:닫기](#close)|검색 요청을 닫습니다.|
|[CFileFind::찾기 파일](#findfile)|디렉터리에서 지정된 파일 이름을 검색합니다.|
|[C파일찾기::다음 파일 찾기](#findnextfile)|[FindFile](#findfile)에 대한 이전 호출에서 파일 검색을 계속합니다.|
|[CFileFind::GetCreationTime](#getcreationtime)|파일을 만든 시간을 가져옵니다.|
|[CFileFind::GetFile 이름](#getfilename)|찾은 파일의 확장명을 포함하여 이름을 가져옵니다.|
|[CFileFind::GetFilePath](#getfilepath)|찾은 파일의 전체 경로를 가져옵니다.|
|[CFileFind::GetFile 제목](#getfiletitle)|찾은 파일의 제목을 가져옵니다. 제목에는 확장이 포함되지 않습니다.|
|[CFileFind::GetFileURL](#getfileurl)|찾은 파일의 파일 경로를 포함한 URL을 가져옵니다.|
|[C파일 찾기::겟라스트액세스타임](#getlastaccesstime)|파일이 마지막으로 액세스된 시간을 가져옵니다.|
|[C파일 찾기::겟라스트쓰기타임](#getlastwritetime)|파일이 마지막으로 변경되고 저장된 시간을 가져옵니다.|
|[CFileFind::GetLength](#getlength)|발견된 파일의 길이를 바이트로 가져옵니다.|
|[CFileFind::GetRoot](#getroot)|찾은 파일의 루트 디렉토리를 가져옵니다.|
|[CFileFind::보관](#isarchived)|발견된 파일이 보관되었는지 여부를 결정합니다.|
|[CFileFind::압축](#iscompressed)|발견된 파일이 압축되는지 여부를 결정합니다.|
|[CFileFind::IsDirectory](#isdirectory)|발견된 파일이 디렉터리인지 확인합니다.|
|[C파일 찾기::IsDots](#isdots)|발견된 파일의 이름에 이름이 "." 또는 "."로 되어 있는지 확인하여 실제로 디렉터리임을 나타냅니다.|
|[CFileFind::숨김](#ishidden)|찾은 파일이 숨겨져 있는지 확인합니다.|
|[CFileFind::일반](#isnormal)|발견된 파일이 정상인지 여부를 결정합니다(즉, 다른 특성이 없음).|
|[C파일 찾기::읽기 전용](#isreadonly)|발견된 파일이 읽기 전용인지 여부를 결정합니다.|
|[C파일찾기::IsSystem](#issystem)|찾은 파일이 시스템 파일인지 확인합니다.|
|[C파일 찾기::임시](#istemporary)|찾은 파일이 일시적인지 확인합니다.|
|[C파일찾기::매치마스크](#matchesmask)|찾을 파일의 원하는 파일 특성을 나타냅니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C파일찾기::닫기 컨텍스트](#closecontext)|현재 검색 핸들에서 지정한 파일을 닫습니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CFileFind::m_pTM](#m_ptm)|`CAtlTransactionManager` 개체에 대한 포인터입니다.|

## <a name="remarks"></a>설명

`CFileFind`에는 검색을 시작하고, 파일을 찾고, 파일의 제목, 이름 또는 경로를 반환하는 멤버 함수가 포함됩니다. 인터넷 검색의 경우 멤버 함수 [GetFileURL이](#getfileurl) 파일의 URL을 반환합니다.

`CFileFind`는 특정 서버 형식을 검색하도록 설계된 두 개의 `CGopherFileFind` 다른 MFC 클래스의 기본 `CFtpFileFind` 클래스입니다. 이 세 클래스는 클라이언트가 로컬 컴퓨터 나 원격 서버에서 서버 프로토콜, 파일 형식 또는 위치에 관계없이 파일을 찾을 수 있는 원활한 메커니즘을 제공합니다.

다음 코드는 현재 디렉터리에 있는 모든 파일을 열거하여 각 파일의 이름을 인쇄합니다.

[!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]

예제를 단순하게 유지하기 위해 이 코드는 `cout` C++ 표준 라이브러리 클래스를 사용합니다. 예를 `cout` 들어 그래픽 사용자 인터페이스가 있는 프로그램에서 는 에 대한 `CListBox::AddString`호출로 줄이 바뀌를 수 있습니다.

사용 `CFileFind` 방법 및 기타 WinInet 클래스에 대한 자세한 내용은 [WinInet와 함께](../../mfc/win32-internet-extensions-wininet.md)인터넷 프로그래밍 문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CFileFind`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cfilefindcfilefind"></a><a name="cfilefind"></a>C파일찾기::CFileFind

이 멤버 함수는 `CFileFind` 개체가 생성될 때 호출됩니다.

```
CFileFind();
CFileFind(CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>매개 변수

*Ptm*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="example"></a>예제

  [CFileFind::GetFileName](#getfilename)에 대한 예제를 참조하십시오.

## <a name="cfilefindclose"></a><a name="close"></a>C파일찾기:닫기

이 멤버 함수를 호출하여 검색을 종료하고 컨텍스트를 재설정하고 모든 리소스를 해제합니다.

```cpp
void Close();
```

### <a name="remarks"></a>설명

호출 `Close`한 후 새 검색을 시작 `CFileFind` 하려면 [FindFile를](#findfile) 호출 하기 전에 새 인스턴스를 만들 필요가 없습니다.

### <a name="example"></a>예제

  [CFileFind::GetFileName](#getfilename)에 대한 예제를 참조하십시오.

## <a name="cfilefindclosecontext"></a><a name="closecontext"></a>C파일찾기::닫기 컨텍스트

현재 검색 핸들에서 지정한 파일을 닫습니다.

```
virtual void CloseContext();
```

### <a name="remarks"></a>설명

검색 핸들의 현재 값으로 지정된 파일을 닫습니다. 이 함수를 재정의하여 기본 동작을 변경합니다.

유효한 검색 핸들을 검색하려면 [FindFile](#findfile) 또는 [FindNextFile](#findnextfile) 함수를 한 번 이상 호출해야 합니다. 및 `FindFile` `FindNextFile` 함수는 검색 핸들을 사용하여 지정된 이름과 일치하는 이름의 파일을 찾습니다.

## <a name="cfilefindfindfile"></a><a name="findfile"></a>CFileFind::찾기 파일

이 멤버 함수를 호출하여 파일 검색을 엽니다.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwUnused = 0);
```

### <a name="parameters"></a>매개 변수

*pstrName*<br/>
찾을 파일의 이름을 포함하는 문자열에 대한 포인터입니다. *pstrName에*대해 NULL을 `FindFile` 전달하면 와일드카드(*.)\*검색을 수행합니다.

*dwUnused*<br/>
파생 클래스를 사용하여 다형성을 만들기 `FindFile` 위해 예약되었습니다. 0이어야 합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 확장 오류 정보를 얻으려면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)호출합니다.

### <a name="remarks"></a>설명

호출후 `FindFile` 파일 검색을 시작 하려면 [FindNextFile](#findnextfile) 호출 후속 파일을 검색 합니다. 다음 특성 `FindNextFile` 멤버 함수 중 하나만 호출하기 전에 한 번 이상 호출해야 합니다.

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFile 타이틀](#getfiletitle)

- [GetFile 경로](#getfilepath)

- [GetFileURL](#getfileurl)

- [겟라스트액세스타임](#getlastaccesstime)

- [겟라스트쓰기타임](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [보관](#isarchived)

- [IsCompressed](#iscompressed)

- [이스디렉토리](#isdirectory)

- [이도트 (주)](#isdots)

- [숨김](#ishidden)

- [이스노멀](#isnormal)

- [Isreadonly](#isreadonly)

- [IsSystem](#issystem)

- [Is임시](#istemporary)

- [매치마스크](#matchesmask)

### <a name="example"></a>예제

  [CFileFind::IsDirectory에](#isdirectory)대 한 예제를 참조 하십시오.

## <a name="cfilefindfindnextfile"></a><a name="findnextfile"></a>C파일찾기::다음 파일 찾기

이 멤버 함수를 호출하여 [이전 호출에서 FindFile](#findfile)에 대한 파일 검색을 계속합니다.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Return Value

파일이 더 많은 경우 0이 아닙니다. 발견된 파일이 디렉터리에서 마지막 파일이거나 오류가 발생한 경우 0입니다. 확장 오류 정보를 얻으려면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)호출합니다. 발견된 파일이 디렉터리에서 마지막 파일이거나 일치하는 파일을 찾을 수 없는 `GetLastError` 경우 함수는 ERROR_NO_MORE_FILES 반환합니다.

### <a name="remarks"></a>설명

다음 특성 `FindNextFile` 멤버 함수 중 하나만 호출하기 전에 한 번 이상 호출해야 합니다.

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFile 타이틀](#getfiletitle)

- [GetFile 경로](#getfilepath)

- [GetFileURL](#getfileurl)

- [겟라스트액세스타임](#getlastaccesstime)

- [겟라스트쓰기타임](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [보관](#isarchived)

- [IsCompressed](#iscompressed)

- [이스디렉토리](#isdirectory)

- [이도트 (주)](#isdots)

- [숨김](#ishidden)

- [이스노멀](#isnormal)

- [Isreadonly](#isreadonly)

- [IsSystem](#issystem)

- [Is임시](#istemporary)

- [매치마스크](#matchesmask)

`FindNextFile`Win32 함수 [FindNextFile을](/windows/win32/api/fileapi/nf-fileapi-findnextfilew)래핑합니다.

### <a name="example"></a>예제

  [CFileFind::IsDirectory에](#isdirectory)대 한 예제를 참조 하십시오.

## <a name="cfilefindgetcreationtime"></a><a name="getcreationtime"></a>CFileFind::GetCreationTime

지정된 파일이 생성된 시간을 얻으려면 이 멤버 함수를 호출합니다.

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

성공하면 영하지 않은; 0이 실패하면 `GetCreationTime`[FindNextFile이](#findnextfile) 이 `CFileFind` 개체에서 호출된 적이 없는 경우에만 0을 반환합니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `GetCreationTime`번 이상 호출해야 합니다.

> [!NOTE]
> 모든 파일 시스템이 동일한 의미 체계를 사용하여 이 함수에서 반환되는 타임스탬프를 구현하는 것은 아닙니다. 이 함수는 기본 파일 시스템 또는 서버가 시간 특성 유지를 지원하지 않는 경우 다른 타임스탬프 함수에서 반환하는 동일한 값을 반환할 수 있습니다. 시간 형식에 대한 자세한 내용은 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조를 참조하십시오. 일부 운영 시스템에서 반환된 시간은 파일이 위치한 컴퓨터에 로컬 표준 시간대에 있습니다. 자세한 내용은 Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API를 참조하십시오.

### <a name="example"></a>예제

  [CFileFind::GetLength](#getlength)에 대한 예제를 참조하십시오.

## <a name="cfilefindgetfilename"></a><a name="getfilename"></a>CFileFind::GetFile 이름

이 멤버 함수를 호출하여 찾은 파일의 이름을 가져옵니다.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Return Value

가장 최근에 찾은 파일의 이름입니다.

### <a name="remarks"></a>설명

GetFileName을 호출하기 전에 [FindNextFile을](#findnextfile) 한 번 이상 호출해야 합니다.

`GetFileName`는 파일 `CFileFind` 이름의 일부 형식을 반환 하는 세 멤버 함수 중 하나입니다. 다음 목록에서는 세 가지와 그 다양성에 대해 설명합니다.

- `GetFileName`확장프로그램을 포함한 파일 이름을 반환합니다. 예를 들어 `GetFileName` 파일 *c:\myhtml\myfile.txt에* 대한 사용자 메시지를 생성하기 위해 호출하면 파일 이름 *myfile.txt*가 반환됩니다.

- [GetFilePath는](#getfilepath) 파일의 전체 경로를 반환합니다. 예를 들어 `GetFilePath` 파일 *c:\myhtml\myfile.txt에* 대한 사용자 메시지를 생성하기 위해 호출하면 파일 경로 *c:\myhtml\myfile.txt*가 반환됩니다.

- [GetFileTitle](#getfiletitle) 파일 확장명을 제외 하 고 파일 이름을 반환 합니다. 예를 들어 `GetFileTitle` 파일 *c:\myhtml\myfile.txt에* 대한 사용자 메시지를 생성하기 위해 호출하면 파일 제목 *myfile이*반환됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]

## <a name="cfilefindgetfilepath"></a><a name="getfilepath"></a>CFileFind::GetFilePath

지정된 파일의 전체 경로를 얻으려면 이 멤버 함수를 호출합니다.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Return Value

지정된 파일의 경로입니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `GetFilePath`번 이상 호출해야 합니다.

`GetFilePath`는 파일 `CFileFind` 이름의 일부 형식을 반환 하는 세 멤버 함수 중 하나입니다. 다음 목록에서는 세 가지와 그 다양성에 대해 설명합니다.

- [GetFileName](#getfilename) 확장명을 포함 하 여 파일 이름을 반환 합니다. 예를 들어 `GetFileName` 파일 *c:\myhtml\myfile.txt에* 대한 사용자 메시지를 생성하기 위해 호출하면 파일 이름 *myfile.txt*가 반환됩니다.

- `GetFilePath`파일의 전체 경로를 반환합니다. 예를 들어 `GetFilePath` 파일에 `c:\myhtml\myfile.txt` 대한 사용자 메시지를 생성하기 위해 `c:\myhtml\myfile.txt`호출하면 파일 경로가 반환됩니다.

- [GetFileTitle](#getfiletitle) 파일 확장명을 제외 하 고 파일 이름을 반환 합니다. 예를 들어 `GetFileTitle` 파일 *c:\myhtml\myfile.txt에* 대한 사용자 메시지를 생성하기 위해 호출하면 파일 제목 *myfile이*반환됩니다.

### <a name="example"></a>예제

  [CFileFind::GetFileName](#getfilename)에 대한 예제를 참조하십시오.

## <a name="cfilefindgetfiletitle"></a><a name="getfiletitle"></a>CFileFind::GetFile 제목

이 멤버 함수를 호출하여 찾은 파일의 제목을 가져옵니다.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Return Value

파일의 제목입니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `GetFileTitle`번 이상 호출해야 합니다.

`GetFileTitle`는 파일 `CFileFind` 이름의 일부 형식을 반환 하는 세 멤버 함수 중 하나입니다. 다음 목록에서는 세 가지와 그 다양성에 대해 설명합니다.

- [GetFileName](#getfilename) 확장명을 포함 하 여 파일 이름을 반환 합니다. 예를 들어 `GetFileName` 파일 *c:\myhtml\myfile.txt에* 대한 사용자 메시지를 생성하기 위해 호출하면 파일 이름 *myfile.txt*가 반환됩니다.

- [GetFilePath는](#getfilepath) 파일의 전체 경로를 반환합니다. 예를 들어 `GetFilePath` 파일 *c:\myhtml\myfile.txt에* 대한 사용자 메시지를 생성하기 위해 호출하면 파일 경로 *c:\myhtml\myfile.txt*가 반환됩니다.

- `GetFileTitle`파일 확장명을 제외한 파일 이름을 반환합니다. 예를 들어 `GetFileTitle` 파일 *c:\myhtml\myfile.txt에* 대한 사용자 메시지를 생성하기 위해 호출하면 파일 제목 *myfile이*반환됩니다.

### <a name="example"></a>예제

  [CFileFind::GetFileName](#getfilename)에 대한 예제를 참조하십시오.

## <a name="cfilefindgetfileurl"></a><a name="getfileurl"></a>CFileFind::GetFileURL

지정된 URL을 검색하려면 이 멤버 함수를 호출합니다.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Return Value

전체 URL입니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `GetFileURL`번 이상 호출해야 합니다.

`GetFileURL`형식의 `file://path`URL을 반환한다는 점을 제외하면 멤버 함수 [GetFilePath와](#getfilepath)유사합니다. 예를 들어 `GetFileURL` *myfile.txt의* 전체 URL을 얻으려면 `file://c:\myhtml\myfile.txt`호출하면 URL이 반환됩니다.

### <a name="example"></a>예제

  [CFileFind::GetFileName](#getfilename)에 대한 예제를 참조하십시오.

## <a name="cfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a>C파일 찾기::겟라스트액세스타임

지정된 파일에 마지막으로 액세스한 시간을 얻으려면 이 멤버 함수를 호출합니다.

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

성공하면 영하지 않은; 0이 실패하면 `GetLastAccessTime`[FindNextFile이](#findnextfile) 이 `CFileFind` 개체에서 호출된 적이 없는 경우에만 0을 반환합니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `GetLastAccessTime`번 이상 호출해야 합니다.

> [!NOTE]
> 모든 파일 시스템이 동일한 의미 체계를 사용하여 이 함수에서 반환되는 타임스탬프를 구현하는 것은 아닙니다. 이 함수는 기본 파일 시스템 또는 서버가 시간 특성 유지를 지원하지 않는 경우 다른 타임스탬프 함수에서 반환하는 동일한 값을 반환할 수 있습니다. 시간 형식에 대한 자세한 내용은 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조를 참조하십시오. 일부 운영 시스템에서 반환된 시간은 파일이 위치한 컴퓨터에 로컬 표준 시간대에 있습니다. 자세한 내용은 Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API를 참조하십시오.

### <a name="example"></a>예제

  [CFileFind::GetLength](#getlength)에 대한 예제를 참조하십시오.

## <a name="cfilefindgetlastwritetime"></a><a name="getlastwritetime"></a>C파일 찾기::겟라스트쓰기타임

이 멤버 함수를 호출하여 파일이 마지막으로 변경된 시간을 가져옵니다.

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

성공하면 영하지 않은; 0이 실패하면 `GetLastWriteTime`[FindNextFile이](#findnextfile) 이 `CFileFind` 개체에서 호출된 적이 없는 경우에만 0을 반환합니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `GetLastWriteTime`번 이상 호출해야 합니다.

> [!NOTE]
> 모든 파일 시스템이 동일한 의미 체계를 사용하여 이 함수에서 반환되는 타임스탬프를 구현하는 것은 아닙니다. 이 함수는 기본 파일 시스템 또는 서버가 시간 특성 유지를 지원하지 않는 경우 다른 타임스탬프 함수에서 반환하는 동일한 값을 반환할 수 있습니다. 시간 형식에 대한 자세한 내용은 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조를 참조하십시오. 일부 운영 시스템에서 반환된 시간은 파일이 위치한 컴퓨터에 로컬 표준 시간대에 있습니다. 자세한 내용은 Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API를 참조하십시오.

### <a name="example"></a>예제

  [CFileFind::GetLength](#getlength)에 대한 예제를 참조하십시오.

## <a name="cfilefindgetlength"></a><a name="getlength"></a>CFileFind::GetLength

이 멤버 함수를 호출하여 찾은 파일의 길이를 바이트로 가져옵니다.

```
ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Return Value

발견된 파일의 길이(바이트)입니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `GetLength`번 이상 호출해야 합니다.

`GetLength`WIN32_FIND_DATA Win32 [구조를](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 사용하여 파일 크기 값을 바이트별로 가져옵니다.

> [!NOTE]
> MFC 7.0에서 `GetLength` 64비트 정수 유형을 지원합니다. 이 최신 버전의 라이브러리로 빌드된 기존 코드에는 잘림 경고가 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]

## <a name="cfilefindgetroot"></a><a name="getroot"></a>CFileFind::GetRoot

이 멤버 함수를 호출하여 찾은 파일의 루트를 가져옵니다.

```
virtual CString GetRoot() const;
```

### <a name="return-value"></a>Return Value

활성 검색의 루트입니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `GetRoot`번 이상 호출해야 합니다.

이 멤버 함수는 검색을 시작하는 데 사용되는 드라이브 지정기 및 경로 이름을 반환합니다. 예를 들어 빈 문자열을 `GetRoot` 반환하는 결과와 함께 `*.dat` [FindFile을](#findfile) 호출합니다. `c:\windows\system\*.dll`을 반환하는 `FindFile` `GetRoot` `c:\windows\system\`결과에 패스합니다.

### <a name="example"></a>예제

  [CFileFind::GetFileName](#getfilename)에 대한 예제를 참조하십시오.

## <a name="cfilefindisarchived"></a><a name="isarchived"></a>CFileFind::보관

이 멤버 함수를 호출하여 발견된 파일이 보관되었는지 확인합니다.

```
BOOL IsArchived() const;
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램은 WIN32_FIND_DATA [구조에서](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 식별된 파일 특성인 FILE_ATTRIBUTE_ARCHIVE 백업하거나 제거할 아카이브 파일을 표시합니다.

호출하기 전에 [FindNextFile을](#findnextfile) 한 `IsArchived`번 이상 호출해야 합니다.

파일 특성의 전체 목록은 멤버 함수 [MatchesMask를](#matchesmask) 참조하십시오.

### <a name="example"></a>예제

  [CFileFind::GetLength](#getlength)에 대한 예제를 참조하십시오.

## <a name="cfilefindiscompressed"></a><a name="iscompressed"></a>CFileFind::압축

이 멤버 함수를 호출하여 발견된 파일이 압축되었는지 확인합니다.

```
BOOL IsCompressed() const;
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

압축된 파일은 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조에서 식별된 파일 특성인 FILE_ATTRIBUTE_COMPRESSED 표시됩니다. 파일의 경우 이 특성은 파일의 모든 데이터가 압축되어 있음을 나타냅니다. 디렉터리에서 이 특성은 새로 만든 파일 및 하위 디렉터리에 대한 압축이 기본값임을 나타냅니다.

호출하기 전에 [FindNextFile을](#findnextfile) 한 `IsCompressed`번 이상 호출해야 합니다.

파일 특성의 전체 목록은 멤버 함수 [MatchesMask를](#matchesmask) 참조하십시오.

### <a name="example"></a>예제

  [CFileFind::GetLength](#getlength)에 대한 예제를 참조하십시오.

## <a name="cfilefindisdirectory"></a><a name="isdirectory"></a>CFileFind::IsDirectory

이 멤버 함수를 호출하여 발견된 파일이 디렉터리인지 확인합니다.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

디렉터리인 파일은 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조에서 식별된 파일 특성을 FILE_ATTRIBUTE_DIRECTORY 표시합니다.

호출하기 전에 [FindNextFile을](#findnextfile) 한 `IsDirectory`번 이상 호출해야 합니다.

파일 특성의 전체 목록은 멤버 함수 [MatchesMask를](#matchesmask) 참조하십시오.

### <a name="example"></a>예제

이 작은 프로그램은 C:\ 의 모든 디렉토리를 다시 저주합니다. 을 받고 디렉터리 이름을 인쇄합니다.

[!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]

## <a name="cfilefindisdots"></a><a name="isdots"></a>C파일 찾기::IsDots

파일을 반복하는 동안 이 멤버 함수를 호출하여 현재 디렉터리 및 상위 디렉터리 마커를 테스트합니다.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Return Value

발견된 파일에 "." 또는 "."라는 이름이 있는 경우 Nonzero는 발견된 파일이 실제로 디렉터리임을 나타냅니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `IsDots`번 이상 호출해야 합니다.

### <a name="example"></a>예제

  [CFileFind::IsDirectory에](#isdirectory)대 한 예제를 참조 하십시오.

## <a name="cfilefindishidden"></a><a name="ishidden"></a>CFileFind::숨김

이 멤버 함수를 호출하여 발견된 파일이 숨겨져 있는지 확인합니다.

```
BOOL IsHidden() const;
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

[WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조에서 식별된 파일 특성인 FILE_ATTRIBUTE_HIDDEN 표시된 숨겨진 파일입니다. 숨겨진 파일은 일반 디렉터리 목록에 포함되지 않습니다.

호출하기 전에 [FindNextFile을](#findnextfile) 한 `IsHidden`번 이상 호출해야 합니다.

파일 특성의 전체 목록은 멤버 함수 [MatchesMask를](#matchesmask) 참조하십시오.

### <a name="example"></a>예제

  [CFileFind::GetLength](#getlength)에 대한 예제를 참조하십시오.

## <a name="cfilefindisnormal"></a><a name="isnormal"></a>CFileFind::일반

이 멤버 함수를 호출하여 발견된 파일이 일반 파일인지 확인합니다.

```
BOOL IsNormal() const;
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

[WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조에서 식별된 파일 특성인 FILE_ATTRIBUTE_NORMAL 표시된 파일입니다. 일반 파일에는 다른 특성집합이 없습니다. 다른 모든 파일 특성은 이 특성을 재정의합니다.

호출하기 전에 [FindNextFile을](#findnextfile) 한 `IsNormal`번 이상 호출해야 합니다.

파일 특성의 전체 목록은 멤버 함수 [MatchesMask를](#matchesmask) 참조하십시오.

### <a name="example"></a>예제

  [CFileFind::GetLength](#getlength)에 대한 예제를 참조하십시오.

## <a name="cfilefindisreadonly"></a><a name="isreadonly"></a>C파일 찾기::읽기 전용

이 멤버 함수를 호출하여 발견된 파일이 읽기 전용인지 확인합니다.

```
BOOL IsReadOnly() const;
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

읽기 전용 파일은 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조에서 식별된 파일 특성인 FILE_ATTRIBUTE_READONLY 표시됩니다. 응용 프로그램은 이러한 파일을 읽을 수 있지만 파일을 쓰거나 삭제할 수는 없습니다.

호출하기 전에 [FindNextFile을](#findnextfile) 한 `IsReadOnly`번 이상 호출해야 합니다.

파일 특성의 전체 목록은 멤버 함수 [MatchesMask를](#matchesmask) 참조하십시오.

### <a name="example"></a>예제

  [CFileFind::GetLength](#getlength)에 대한 예제를 참조하십시오.

## <a name="cfilefindissystem"></a><a name="issystem"></a>C파일찾기::IsSystem

이 멤버 함수를 호출하여 발견된 파일이 시스템 파일인지 확인합니다.

```
BOOL IsSystem() const;
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

시스템 파일은 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조에서 식별된 파일 특성인 FILE_ATTRIBUTE_SYSTEM()로 표시됩니다. 시스템 파일은 운영 체제의 일부이거나 운영 체제에서만 사용됩니다.

호출하기 전에 [FindNextFile을](#findnextfile) 한 `IsSystem`번 이상 호출해야 합니다.

파일 특성의 전체 목록은 멤버 함수 [MatchesMask를](#matchesmask) 참조하십시오.

### <a name="example"></a>예제

  [CFileFind::GetLength](#getlength)에 대한 예제를 참조하십시오.

## <a name="cfilefindistemporary"></a><a name="istemporary"></a>C파일 찾기::임시

이 멤버 함수를 호출하여 발견된 파일이 임시 파일인지 확인합니다.

```
BOOL IsTemporary() const;
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

임시 파일은 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조에서 식별된 파일 특성인 FILE_ATTRIBUTE_TEMPORARY 표시됩니다. 임시 파일은 임시 저장소에 사용됩니다. 응용 프로그램은 절대적으로 필요한 경우에만 파일에 작성해야합니다. 파일의 대부분은 파일이 곧 삭제되기 때문에 미디어로 플러시되지 않고 메모리에 남아 있습니다.

호출하기 전에 [FindNextFile을](#findnextfile) 한 `IsTemporary`번 이상 호출해야 합니다.

파일 특성의 전체 목록은 멤버 함수 [MatchesMask를](#matchesmask) 참조하십시오.

### <a name="example"></a>예제

  [CFileFind::GetLength](#getlength)에 대한 예제를 참조하십시오.

## <a name="cfilefindm_ptm"></a><a name="m_ptm"></a>CFileFind::m_pTM

`CAtlTransactionManager` 개체에 대한 포인터입니다.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>설명

## <a name="cfilefindmatchesmask"></a><a name="matchesmask"></a>C파일찾기::매치마스크

이 멤버 함수를 호출하여 발견된 파일의 파일 특성을 테스트합니다.

```
virtual BOOL MatchesMask(DWORD dwMask) const;
```

### <a name="parameters"></a>매개 변수

*dwMask*<br/>
찾은 파일에 대해 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) 구조에서 식별된 하나 이상의 파일 특성을 지정합니다. 여러 특성을 검색하려면 비트별 OR(&#124;) 연산자를 사용합니다. 다음 특성의 모든 조합은 허용됩니다.

- FILE_ATTRIBUTE_ARCHIVE 파일이 아카이브 파일입니다. 응용 프로그램은 이 특성을 사용하여 백업 또는 제거를 위해 파일을 표시합니다.

- FILE_ATTRIBUTE_COMPRESSED 파일 또는 디렉터리압축. 파일의 경우 이는 파일의 모든 데이터가 압축된다는 것을 의미합니다. 디렉터리에서 이는 새로 만든 파일 및 하위 디렉터리에 대한 압축이 기본값임을 의미합니다.

- FILE_ATTRIBUTE_DIRECTORY 파일이 디렉터리입니다.

- FILE_ATTRIBUTE_NORMAL 파일에 다른 특성집합이 없습니다. 이 특성은 단독으로 사용하는 경우에만 유효합니다. 다른 모든 파일 특성은 이 특성을 재정의합니다.

- FILE_ATTRIBUTE_HIDDEN 파일이 숨김입니다. 일반 디렉터리 목록에 포함되지 않습니다.

- FILE_ATTRIBUTE_READONLY 파일만 읽습니다. 응용 프로그램은 파일을 읽을 수 있지만 파일을 쓰거나 삭제할 수는 없습니다.

- FILE_ATTRIBUTE_SYSTEM 파일의 일부이거나 운영 체제에서만 사용됩니다.

- FILE_ATTRIBUTE_TEMPORARY 파일이 임시 저장소에 사용되고 있습니다. 응용 프로그램은 절대적으로 필요한 경우에만 파일에 작성해야합니다. 파일의 대부분은 파일이 곧 삭제되기 때문에 미디어로 플러시되지 않고 메모리에 남아 있습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 확장 오류 정보를 얻으려면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)호출합니다.

### <a name="remarks"></a>설명

호출하기 전에 [FindNextFile을](#findnextfile) 한 `MatchesMask`번 이상 호출해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFtp파일찾기 클래스](../../mfc/reference/cftpfilefind-class.md)<br/>
[CGopher파일찾기 클래스](../../mfc/reference/cgopherfilefind-class.md)<br/>
[C인터넷파일 클래스](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile 클래스](../../mfc/reference/chttpfile-class.md)
