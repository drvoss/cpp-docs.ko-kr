---
title: CFtp커넥션 클래스
ms.date: 08/29/2019
f1_keywords:
- CFtpConnection
- AFXINET/CFtpConnection
- AFXINET/CFtpConnection::CFtpConnection
- AFXINET/CFtpConnection::Command
- AFXINET/CFtpConnection::CreateDirectory
- AFXINET/CFtpConnection::GetCurrentDirectory
- AFXINET/CFtpConnection::GetCurrentDirectoryAsURL
- AFXINET/CFtpConnection::GetFile
- AFXINET/CFtpConnection::OpenFile
- AFXINET/CFtpConnection::PutFile
- AFXINET/CFtpConnection::Remove
- AFXINET/CFtpConnection::RemoveDirectory
- AFXINET/CFtpConnection::Rename
- AFXINET/CFtpConnection::SetCurrentDirectory
helpviewer_keywords:
- CFtpConnection [MFC], CFtpConnection
- CFtpConnection [MFC], Command
- CFtpConnection [MFC], CreateDirectory
- CFtpConnection [MFC], GetCurrentDirectory
- CFtpConnection [MFC], GetCurrentDirectoryAsURL
- CFtpConnection [MFC], GetFile
- CFtpConnection [MFC], OpenFile
- CFtpConnection [MFC], PutFile
- CFtpConnection [MFC], Remove
- CFtpConnection [MFC], RemoveDirectory
- CFtpConnection [MFC], Rename
- CFtpConnection [MFC], SetCurrentDirectory
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
ms.openlocfilehash: a1fe516869aa98cc291597211eee175ef591e45d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373770"
---
# <a name="cftpconnection-class"></a>CFtp커넥션 클래스

인터넷 서버에 대한 FTP 연결을 관리하고 해당 서버의 디렉터리 및 파일을 직접 조작할 수 있습니다.

## <a name="syntax"></a>구문

```
class CFtpConnection : public CInternetConnection
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CFtp연결::CFtp연결](#cftpconnection)|`CFtpConnection` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CFtp연결::명령](#command)|FTP 서버에 직접 명령을 보냅니다.|
|[CFtp연결::디렉터리 만들기](#createdirectory)|서버에서 디렉터리를 만듭니다.|
|[CFtp연결::GetCurrent디렉터리](#getcurrentdirectory)|이 연결에 대한 현재 디렉터리를 가져옵니다.|
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|이 연결에 대한 현재 디렉터리를 URL로 가져옵니다.|
|[CFtp연결::GetFile](#getfile)|연결된 서버에서 파일 가져옵니다.|
|[CFtp연결::오픈파일](#openfile)|연결된 서버에서 파일을 엽니다.|
|[CFtp연결::PutFile](#putfile)|서버에 파일을 배치합니다.|
|[CFtp연결::제거](#remove)|서버에서 파일을 제거합니다.|
|[CFtpConnection::RemoveDirectory](#removedirectory)|서버에서 지정된 디렉터리를 제거합니다.|
|[CFtpConnection::Rename](#rename)|서버의 파일 이름을 바꿉니다.|
|[CFtp연결::설정전류 디렉터리](#setcurrentdirectory)|현재 FTP 디렉터리를 설정합니다.|

## <a name="remarks"></a>설명

FTP는 MFC WinInet 클래스에서 인정하는 세 가지 인터넷 서비스 중 하나입니다.

FTP 인터넷 서버와 통신하려면 먼저 [CInternetSession](../../mfc/reference/cinternetsession-class.md)의 인스턴스를 만든 `CFtpConnection` 다음 개체를 만들어야 합니다. 개체를 `CFtpConnection` 직접 만들지 않습니다. 대신 [CInternetSession::GetFtpConnection을](../../mfc/reference/cinternetsession-class.md#getftpconnection)호출하여 `CFtpConnection` 개체를 만들고 포인터를 반환합니다.

다른 MFC `CFtpConnection` 인터넷 클래스와 함께 작동하는 방법에 대한 자세한 내용은 [WinInet와 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)문서를 참조하십시오. 다른 두 지원 되는 서비스, HTTP 및 고퍼와 통신에 대 한 자세한 내용은 [클래스 CHttpConnection](../../mfc/reference/chttpconnection-class.md) 및 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)를 참조 하십시오.

## <a name="example"></a>예제

  [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) 클래스 개요의 예제를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CFtpConnection`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="cftpconnectioncftpconnection"></a><a name="cftpconnection"></a>CFtp연결::CFtp연결

이 멤버 함수는 개체를 생성하기 위해 호출됩니다. `CFtpConnection`

```
CFtpConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CFtpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 0,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
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

*bPassive*<br/>
이 FTP 세션에 대한 수동 또는 활성 모드를 지정합니다. TRUE로 설정하면 Win32 API *dwFlag를* INTERNET_FLAG_PASSIVE 설정합니다.

### <a name="remarks"></a>설명

개체를 `CFtpConnection` 직접 만들지 않습니다. 대신 [CInternetSession::GetFtpConnection을](../../mfc/reference/cinternetsession-class.md#getftpconnection)호출하여 `CFptConnection` 개체를 만듭니다.

## <a name="cftpconnectioncommand"></a><a name="command"></a>CFtp연결::명령

FTP 서버에 직접 명령을 보냅니다.

```
CInternetFile* Command(
    LPCTSTR pszCommand,
    CmdResponseType eResponse = CmdRespNone,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*pszCommand*<br/>
보낼 명령을 포함하는 문자열에 대한 포인터입니다.

*eResponse*<br/>
FTP 서버에서 응답이 예상되는지 여부를 지정합니다. 다음 값 중 하나를 사용할 수 있습니다.

- `CmdRespNone`응답이 예상되지 않습니다.
- `CmdRespRead`응답이 예상됩니다.
- `CmdRespWrite`사용되지 않습니다.

CmdResponseType은 *afxinet.h에*정의된 CFtpConnection의 멤버입니다.

*dwFlags*<br/>
이 함수를 제어하는 플래그를 포함하는 값입니다. 전체 목록은 [FTPCommand](/windows/win32/api/wininet/nf-wininet-ftpcommandw)을 참조하십시오.

*dwContext*<br/>
콜백에서 애플리케이션 컨텍스트를 식별하는 데 사용되는 애플리케이션 정의 값을 포함하는 값에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [FTPCommand](/windows/win32/api/wininet/nf-wininet-ftpcommandw) 함수의 기능을 에뮬레이트합니다.

오류가 발생하면 MFC는 [CInternetException](../../mfc/reference/cinternetexception-class.md)형식의 예외를 throw합니다.

## <a name="cftpconnectioncreatedirectory"></a><a name="createdirectory"></a>CFtp연결::디렉터리 만들기

연결된 서버에서 디렉터리를 만들려면 이 멤버 함수를 호출합니다.

```
BOOL CreateDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>매개 변수

*pstrDirName*<br/>
만들 디렉터리 이름을 포함하는 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Windows 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

서버에 `GetCurrentDirectory` 대한 이 연결에 대한 현재 작업 디렉터리를 결정하는 데 사용합니다. 원격 시스템이 루트 디렉터리에 연결되었다고 가정하지 마십시오.

매개 `pstrDirName` 변수는 현재 디렉터리와 관련된 부분또는 정규화된 파일 이름일 수 있습니다. 백슬래시 ()\\또는 앞으로 슬래시 (/)는 두 이름의 디렉토리 구분 기호로 사용할 수 있습니다. `CreateDirectory`는 디렉터리 이름 구분 기호를 사용 하기 전에 적절 한 문자로 변환 합니다.

## <a name="cftpconnectiongetcurrentdirectory"></a><a name="getcurrentdirectory"></a>CFtp연결::GetCurrent디렉터리

이 멤버 함수를 호출하여 현재 디렉터리 이름을 가져옵니다.

```
BOOL GetCurrentDirectory(CString& strDirName) const;

BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>매개 변수

*strDirName*<br/>
디렉터리 이름을 수신하는 문자열에 대한 참조입니다.

*pstrDirName*<br/>
디렉터리 이름을 수신하는 문자열에 대한 포인터입니다.

*lpdwLen*<br/>
다음 정보가 포함된 DWORD에 대한 포인터:

|||
|-|-|
|항목시|*pstrDirName에서*참조하는 버퍼의 크기입니다.|
|반품 시|*pstrDirName에*저장된 문자 수입니다. 멤버 함수가 실패하고 ERROR_INSUFFICIENT_BUFFER 반환되는 경우 *lpdwLen은* 문자열을 수신하기 위해 응용 프로그램이 할당해야 하는 바이트 수를 포함합니다.|

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

대신 디렉터리 이름을 URL로 받으려면 [GetCurrentDirectoryAsURL 을 호출합니다.](#getcurrentdirectoryasurl)

매개 변수 *pstrDirName* 또는 *strDirName* 현재 디렉터리 또는 정규화 된 에 대해 부분적으로 정규화된 파일 이름일 수 있습니다. 백슬래시 ()\\또는 앞으로 슬래시 (/)는 두 이름의 디렉토리 구분 기호로 사용할 수 있습니다. `GetCurrentDirectory`는 디렉터리 이름 구분 기호를 사용 하기 전에 적절 한 문자로 변환 합니다.

## <a name="cftpconnectiongetcurrentdirectoryasurl"></a><a name="getcurrentdirectoryasurl"></a>CFtp연결::겟전류 디렉터리아URL

이 멤버 함수를 호출하여 현재 디렉터리의 이름을 URL로 가져옵니다.

```
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;

BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>매개 변수

*strDirName*<br/>
디렉터리 이름을 수신하는 문자열에 대한 참조입니다.

*pstrDirName*<br/>
디렉터리 이름을 수신하는 문자열에 대한 포인터입니다.

*lpdwLen*<br/>
다음 정보가 포함된 DWORD에 대한 포인터:

|||
|-|-|
|항목시|*pstrDirName에서*참조하는 버퍼의 크기입니다.|
|반품 시|*pstrDirName에*저장된 문자 수입니다. 멤버 함수가 실패하고 ERROR_INSUFFICIENT_BUFFER 반환되는 경우 *lpdwLen은* 문자열을 수신하기 위해 응용 프로그램이 할당해야 하는 바이트 수를 포함합니다.|

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

`GetCurrentDirectoryAsURL`[GetCurrentDirectory와 동일하게 행동합니다.](#getcurrentdirectory)

매개 변수 *strDirName* 현재 디렉터리또는 정규화된 파일 이름을 부분적으로 정규화할 수 있습니다. 백슬래시 ()\\또는 앞으로 슬래시 (/)는 두 이름의 디렉토리 구분 기호로 사용할 수 있습니다. `GetCurrentDirectoryAsURL`는 디렉터리 이름 구분 기호를 사용 하기 전에 적절 한 문자로 변환 합니다.

## <a name="cftpconnectiongetfile"></a><a name="getfile"></a>CFtp연결::GetFile

이 멤버 함수를 호출하여 FTP 서버에서 파일을 받고 로컬 컴퓨터에 저장합니다.

```
BOOL GetFile(
    LPCTSTR pstrRemoteFile,
    LPCTSTR pstrLocalFile,
    BOOL bFailIfExists = TRUE,
    DWORD dwAttributes = FILE_ATTRIBUTE_NORMAL,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*pstrRemoteFile*<br/>
FTP 서버에서 검색할 파일의 이름을 포함하는 null 종료 된 문자열에 대한 포인터입니다.

*pstrLocalFile*<br/>
로컬 시스템에서 만들 파일의 이름을 포함하는 null 종료 된 문자열에 대한 포인터입니다.

*bFailIfExists*<br/>
파일 이름이 기존 파일에서 이미 사용중일 수 있는지 여부를 나타냅니다. 로컬 파일 이름이 이미 있고 이 매개 `GetFile` 변수가 TRUE인 경우 실패합니다. `GetFile` 그렇지 않으면 파일의 기존 복사본을 지웁히 됩니다.

*dwAttributes*<br/>
파일의 특성을 나타냅니다. 다음 FILE_ATTRIBUTE_* 플래그의 조합일 수 있습니다.

- FILE_ATTRIBUTE_ARCHIVE 파일이 아카이브 파일입니다. 응용 프로그램은 이 특성을 사용하여 백업 또는 제거를 위해 파일을 표시합니다.

- FILE_ATTRIBUTE_COMPRESSED 파일 또는 디렉터리압축. 파일의 경우 압축은 파일의 모든 데이터가 압축된다는 것을 의미합니다. 디렉터리에서 압축은 새로 만든 파일 및 하위 디렉토리의 기본값입니다.

- FILE_ATTRIBUTE_DIRECTORY 파일이 디렉터리입니다.

- FILE_ATTRIBUTE_NORMAL 파일에 다른 특성집합이 없습니다. 이 특성은 단독으로 사용하는 경우에만 유효합니다. 다른 모든 파일 속성은 FILE_ATTRIBUTE_NORMAL 재정의합니다.

- FILE_ATTRIBUTE_HIDDEN 파일이 숨김입니다. 일반 디렉터리 목록에 포함되지 않습니다.

- FILE_ATTRIBUTE_READONLY 파일만 읽습니다. 응용 프로그램은 파일을 읽을 수 있지만 파일을 쓰거나 삭제할 수는 없습니다.

- FILE_ATTRIBUTE_SYSTEM 파일의 일부이거나 운영 체제에서만 사용됩니다.

- FILE_ATTRIBUTE_TEMPORARY 파일이 임시 저장소에 사용되고 있습니다. 응용 프로그램은 절대적으로 필요한 경우에만 파일에 작성해야합니다. 파일의 대부분은 파일이 곧 삭제되기 때문에 미디어로 플러시되지 않고 메모리에 남아 있습니다.

*dwFlags*<br/>
전송이 발생하는 조건을 지정합니다. 이 매개 변수는 Windows SDK의 [FtpGetFile에](/windows/win32/api/wininet/nf-wininet-ftpgetfilew) 설명된 *dwFlags* 값 중 어느 한 값일 수 있습니다.

*dwContext*<br/>
파일 검색에 대한 컨텍스트 식별자입니다. *dwContext*에 대한 자세한 내용은 **비고를** 참조하십시오.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

`GetFile`는 FTP 서버에서 파일을 읽고 로컬로 저장하는 것과 관련된 모든 오버헤드를 처리하는 상위 수준 루틴입니다. 파일 데이터만 검색하거나 파일 전송에 대한 면밀한 제어가 필요한 응용 프로그램은 대신 사용하고 `OpenFile` [CInternetFile::Read를](../../mfc/reference/cinternetfile-class.md#read) 사용해야 합니다.

*dwFlags가* FILE_TRANSFER_TYPE_ASCII 경우 파일 데이터의 변환도 제어 및 서식 지정 문자를 Windows 등가물로 변환합니다. 기본 전송은 이진 모드로, 파일이 서버에 저장된 것과 동일한 형식으로 다운로드됩니다.

*pstrRemoteFile* 및 *pstrLocalFile* 모두 현재 디렉터리와 비교하여 부분적으로 정규화된 파일 이름이거나 정규화된 파일 이름일 수 있습니다. 백슬래시 ()\\또는 앞으로 슬래시 (/)는 두 이름의 디렉토리 구분 기호로 사용할 수 있습니다. `GetFile`는 디렉터리 이름 구분 기호를 사용 하기 전에 적절 한 문자로 변환 합니다.

*dwContext* 기본값을 재정의하여 컨텍스트 식별자를 선택한 값으로 설정합니다. 컨텍스트 식별자는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에서 `CFtpConnection` 만든 개체의 이 특정 작업과 연결됩니다. 값이 [CInternetSession::OnStatusCallback으로](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 반환되어 식별되는 작업에 대한 상태를 제공합니다. 컨텍스트 식별자에 대한 자세한 내용은 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 문서를 참조하십시오.

## <a name="cftpconnectionopenfile"></a><a name="openfile"></a>CFtp연결::오픈파일

이 멤버 함수를 호출하여 FTP 서버에 있는 파일을 열어 읽거나 작성합니다.

```
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,
    DWORD dwAccess = GENERIC_READ,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*pstrFileName*<br/>
열 파일의 이름을 포함하는 문자열에 대한 포인터입니다.

*dwAccess*<br/>
파일에 액세스하는 방법을 결정합니다. GENERIC_READ 또는 GENERIC_WRITE 수 있지만 둘 다 아닐 수는 없습니다.

*dwFlags*<br/>
후속 전송이 발생하는 조건을 지정합니다. 다음 FTP_TRANSFER_* 상수 중 어느 한 개일 수 있습니다.

- FTP_TRANSFER_TYPE_ASCII FTP ASCII(유형 A) 전송 방법을 사용하여 파일전송을 합니다. 제어 및 서식 정보를 로컬 등가물로 변환합니다.

- FTP_TRANSFER_TYPE_BINARY 파일은 FTP의 이미지(유형 I) 전송 방법을 사용하여 데이터를 전송합니다. 파일은 변경되지 않고 데이터를 그대로 전송합니다. 이것이 기본 전송 방법입니다.

*dwContext*<br/>
파일을 여는 컨텍스트 식별자입니다. *dwContext*에 대한 자세한 내용은 **비고를** 참조하십시오.

### <a name="return-value"></a>Return Value

[CInternetFile](../../mfc/reference/cinternetfile-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

`OpenFile`다음 상황에서 사용해야 합니다.

- 응용 프로그램에는 FTP 서버의 파일로 보내고 만들어야 하는 데이터가 있지만 해당 데이터는 로컬 파일에 없습니다. `OpenFile`에서 파일을 열면 응용프로그램은 [cinternetfile::Write](../../mfc/reference/cinternetfile-class.md#write)를 사용하여 FTP 파일데이터를 서버로 보냅니다.

- 응용 프로그램은 서버에서 파일을 검색하여 디스크에 쓰는 대신 응용 프로그램 제어 메모리에 배치해야 합니다. 응용 프로그램은 [CInternetFile::Read를](../../mfc/reference/cinternetfile-class.md#read) 사용하여 `OpenFile` 파일을 엽니다.

- 응용 프로그램은 파일 전송에 대한 세부 적인 제어 수준이 필요합니다. 예를 들어, 애플리케이션은 파일을 다운로드하는 동안 파일 전송 상태의 진행 상황을 나타내는 진행률 제어를 표시할 수 있다.

`OpenFile`를 호출하고 `CInternetConnection::Close`를 호출할 때까지 응용 프로그램은 [cinternetfile:: Read](../../mfc/reference/cinternetfile-class.md#read), [cinternetfile:: Write](../../mfc/reference/cinternetfile-class.md#write), `CInternetConnection::Close` 또는 [ccefilefind:: findfile](../../mfc/reference/cftpfilefind-class.md#findfile)만 호출할 수 있습니다. 동일한 FTP 세션에 대한 다른 FTP 함수에 대한 호출이 실패하고 오류 코드를 FTP_ETRANSFER_IN_PROGRESS 설정합니다.

*pstrFileName* 매개 변수는 현재 디렉터리와 비교하여 부분적으로 정규화된 파일 이름이거나 정규화된 파일 이름일 수 있습니다. 백슬래시 ()\\또는 앞으로 슬래시 (/)는 두 이름의 디렉토리 구분 기호로 사용할 수 있습니다. `OpenFile`는 디렉터리 이름 구분 기호를 사용하기 전에 적절한 문자로 변환합니다.

*dwContext* 기본값을 재정의하여 컨텍스트 식별자를 선택한 값으로 설정합니다. 컨텍스트 식별자는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에서 `CFtpConnection` 만든 개체의 이 특정 작업과 연결됩니다. 값이 [CInternetSession::OnStatusCallback으로](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 반환되어 식별되는 작업에 대한 상태를 제공합니다. 컨텍스트 식별자에 대한 자세한 내용은 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 문서를 참조하십시오.

## <a name="cftpconnectionputfile"></a><a name="putfile"></a>CFtp연결::PutFile

FTP 서버에 파일을 저장하려면 이 멤버 함수를 호출합니다.

```
BOOL PutFile(
    LPCTSTR pstrLocalFile,
    LPCTSTR pstrRemoteFile,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*pstrLocalFile*<br/>
로컬 시스템에서 보낼 파일 의 이름을 포함하는 문자열에 대한 포인터입니다.

*pstrRemoteFile*<br/>
FTP 서버에서 만들 파일 의 이름을 포함하는 문자열에 대한 포인터입니다.

*dwFlags*<br/>
파일 전송이 발생하는 조건을 지정합니다. [OpenFile](#openfile)에 설명된 FTP_TRANSFER_* 상수 중 어느 한 개일 수 있습니다.

*dwContext*<br/>
파일을 배치하기 위한 컨텍스트 식별자입니다. *dwContext*에 대한 자세한 내용은 **비고를** 참조하십시오.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

`PutFile`는 FTP 서버에 파일을 저장하는 것과 관련된 모든 작업을 처리하는 고급 루틴입니다. 데이터만 보내거나 파일 전송을 면밀히 제어해야 하는 응용 프로그램은 [OpenFile](#openfile) 및 [CInternetFile:Write](../../mfc/reference/cinternetfile-class.md#write)를 사용해야 합니다.

`dwContext` 기본값을 재정의하여 컨텍스트 식별자를 설정한 값으로 설정합니다. 컨텍스트 식별자는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체에서 `CFtpConnection` 만든 개체의 이 특정 작업과 연결됩니다. 값이 [CInternetSession::OnStatusCallback으로](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 반환되어 식별되는 작업에 대한 상태를 제공합니다. 컨텍스트 식별자에 대한 자세한 내용은 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 문서를 참조하십시오.

## <a name="cftpconnectionremove"></a><a name="remove"></a>CFtp연결::제거

연결된 서버에서 지정된 파일을 삭제하려면 이 멤버 함수를 호출합니다.

```
BOOL Remove(LPCTSTR pstrFileName);
```

### <a name="parameters"></a>매개 변수

*pstrFileName*<br/>
제거할 파일 이름이 포함된 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

*pstrFileName* 매개 변수는 현재 디렉터리와 비교하여 부분적으로 정규화된 파일 이름이거나 정규화된 파일 이름일 수 있습니다. 백슬래시 ()\\또는 앞으로 슬래시 (/)는 두 이름의 디렉토리 구분 기호로 사용할 수 있습니다. 이 `Remove` 함수는 디렉터리 이름 구분 기호를 사용 하기 전에 적절 한 문자로 변환 합니다.

## <a name="cftpconnectionremovedirectory"></a><a name="removedirectory"></a>CFtp연결::제거디렉터리

연결된 서버에서 지정된 디렉터리를 제거하려면 이 멤버 함수를 호출합니다.

```
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>매개 변수

*pstrDirName*<br/>
제거할 디렉터리가 포함된 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

[GetCurrentDirectory를](#getcurrentdirectory) 사용하여 서버의 현재 작업 디렉터리를 확인합니다. 원격 시스템이 루트 디렉터리에 연결되었다고 가정하지 마십시오.

*pstrDirName* 매개 변수는 현재 디렉터리와 관련된 부분적 또는 정규화된 파일 이름일 수 있습니다. 백슬래시 ()\\또는 앞으로 슬래시 (/)는 두 이름의 디렉토리 구분 기호로 사용할 수 있습니다. `RemoveDirectory`는 디렉터리 이름 구분 기호를 사용 하기 전에 적절 한 문자로 변환 합니다.

## <a name="cftpconnectionrename"></a><a name="rename"></a>CFtp 연결::이름 바꾸기

연결된 서버에서 지정된 파일의 이름을 바꾸려면 이 멤버 함수를 호출합니다.

```
BOOL Rename(
    LPCTSTR pstrExisting,
    LPCTSTR pstrNew);
```

### <a name="parameters"></a>매개 변수

*pstrExisting*<br/>
이름을 바꿀 파일의 현재 이름을 포함하는 문자열에 대한 포인터입니다.

*pstrNew*<br/>
파일의 새 이름이 포함된 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

*pstrExisting* 및 *pstrNew* 매개 변수는 현재 디렉터리에 대해 부분적으로 정규화된 파일 이름이거나 정규화된 파일 이름일 수 있습니다. 백슬래시 ()\\또는 앞으로 슬래시 (/)는 두 이름의 디렉토리 구분 기호로 사용할 수 있습니다. `Rename`는 디렉터리 이름 구분 기호를 사용 하기 전에 적절 한 문자로 변환 합니다.

## <a name="cftpconnectionsetcurrentdirectory"></a><a name="setcurrentdirectory"></a>CFtp연결::설정전류 디렉터리

이 멤버 함수를 호출하여 FTP 서버의 다른 디렉터리로 변경합니다.

```
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>매개 변수

*pstrDirName*<br/>
디렉터리 이름을 포함하는 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

*pstrDirName* 매개 변수는 현재 디렉터리와 관련된 부분적 또는 정규화된 파일 이름일 수 있습니다. 백슬래시 ()\\또는 앞으로 슬래시 (/)는 두 이름의 디렉토리 구분 기호로 사용할 수 있습니다. `SetCurrentDirectory`는 디렉터리 이름 구분 기호를 사용 하기 전에 적절 한 문자로 변환 합니다.

[GetCurrentDirectory를](#getcurrentdirectory) 사용하여 FTP 서버의 현재 작업 디렉토리를 확인합니다. 원격 시스템이 루트 디렉터리에 연결되었다고 가정하지 마십시오.

## <a name="see-also"></a>참고 항목

[C인터넷커넥션 클래스](../../mfc/reference/cinternetconnection-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C인터넷커넥션 클래스](../../mfc/reference/cinternetconnection-class.md)<br/>
[C인터넷세션 클래스](../../mfc/reference/cinternetsession-class.md)
