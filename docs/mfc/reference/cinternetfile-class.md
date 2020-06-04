---
title: C인터넷파일 클래스
ms.date: 11/04/2016
f1_keywords:
- CInternetFile
- AFXINET/CInternetFile
- AFXINET/CInternetFile::CInternetFile
- AFXINET/CInternetFile::Abort
- AFXINET/CInternetFile::Close
- AFXINET/CInternetFile::Flush
- AFXINET/CInternetFile::GetLength
- AFXINET/CInternetFile::Read
- AFXINET/CInternetFile::ReadString
- AFXINET/CInternetFile::Seek
- AFXINET/CInternetFile::SetReadBufferSize
- AFXINET/CInternetFile::SetWriteBufferSize
- AFXINET/CInternetFile::Write
- AFXINET/CInternetFile::WriteString
- AFXINET/CInternetFile::m_hFile
helpviewer_keywords:
- CInternetFile [MFC], CInternetFile
- CInternetFile [MFC], Abort
- CInternetFile [MFC], Close
- CInternetFile [MFC], Flush
- CInternetFile [MFC], GetLength
- CInternetFile [MFC], Read
- CInternetFile [MFC], ReadString
- CInternetFile [MFC], Seek
- CInternetFile [MFC], SetReadBufferSize
- CInternetFile [MFC], SetWriteBufferSize
- CInternetFile [MFC], Write
- CInternetFile [MFC], WriteString
- CInternetFile [MFC], m_hFile
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
ms.openlocfilehash: e3f1a7167f5464423754951764c4441513197841
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372395"
---
# <a name="cinternetfile-class"></a>C인터넷파일 클래스

인터넷 프로토콜을 사용하는 원격 시스템의 파일에 액세스할 수 있습니다.

## <a name="syntax"></a>구문

```
class CInternetFile : public CStdioFile
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[C인터넷 파일::C인터넷파일](#cinternetfile)|`CInternetFile` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CInternetFile::Abort](#abort)|모든 경고 및 오류를 무시하고 파일을 닫습니다.|
|[CInternetFile::Close](#close)|를 `CInternetFile` 닫고 리소스를 해제합니다.|
|[C인터넷 파일::플러시](#flush)|쓰기 버퍼의 내용을 플러시하고 메모리의 데이터가 대상 컴퓨터에 기록되도록 합니다.|
|[C인터넷 파일::GetLength](#getlength)|파일 크기를 반환합니다.|
|[CInternetFile::Read](#read)|지정된 바이트 수를 읽습니다.|
|[CInternetFile::ReadString](#readstring)|문자 스트림을 읽습니다.|
|[CInternetFile::Seek](#seek)|열린 파일에서 포인터의 위치를 바짝 바짝 바뜨습니다.|
|[C인터넷파일::세트읽기버퍼크기](#setreadbuffersize)|데이터를 읽을 버퍼의 크기를 설정합니다.|
|[C인터넷파일::셋쓰기버퍼크기](#setwritebuffersize)|데이터가 기록될 버퍼의 크기를 설정합니다.|
|[C인터넷파일::쓰기](#write)|지정된 바이트 수를 씁니다.|
|[C인터넷파일::쓰기스트링](#writestring)|null 종료된 문자열을 파일에 씁니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C인터넷파일:운영자 HINTERNET](#operator_hinternet)|인터넷 핸들의 캐스팅 연산자입니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CInternetFile::m_hFile](#m_hfile)|파일에 대한 핸들입니다.|

## <a name="remarks"></a>설명

[CHttpFile](../../mfc/reference/chttpfile-class.md) 및 [CGopherFile](../../mfc/reference/cgopherfile-class.md) 파일 클래스에 대 한 기본 클래스를 제공 합니다. 개체를 `CInternetFile` 직접 만들지 않습니다. 대신 [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) 또는 [CHttpConnection::OpenRequest를](../../mfc/reference/chttpconnection-class.md#openrequest)호출하여 파생 된 클래스 중 하나의 개체를 만듭니다. `CInternetFile` [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)을 호출하여 개체를 만들 수도 있습니다.

`CInternetFile` 멤버는 `Open`에 `LockRange`대해 `UnlockRange` `CInternetFile`및 `Duplicate` 구현되지 않습니다. `CInternetFile` 개체에서 이러한 함수를 호출하면 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

다른 MFC `CInternetFile` 인터넷 클래스와 함께 작동하는 방법에 대한 자세한 내용은 [WinInet와 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

`CInternetFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="cinternetfileabort"></a><a name="abort"></a>C인터넷 파일::중단

이 개체와 연결된 파일을 닫고 파일을 읽거나 쓸 수 없게 만듭니다.

```
virtual void Abort();
```

### <a name="remarks"></a>설명

개체를 파괴하기 전에 파일을 닫지 않은 경우 소멸자가 파일을 닫습니다.

예외를 처리할 `Abort` 때 두 가지 중요한 방법으로 [Close와](#close) 다릅니다. 첫째, `Abort` 함수는 오류를 무시하기 때문에 실패에 대한 예외를 throw하지 않습니다. 둘째, `Abort` 파일이 열리지 않았거나 이전에 닫혔는지 **ASSERT하지** 않습니다.

## <a name="cinternetfilecinternetfile"></a><a name="cinternetfile"></a>C인터넷 파일::C인터넷파일

이 멤버 함수는 `CInternetFile` 개체를 만들 때 호출됩니다.

```
CInternetFile(
    HINTERNET hFile,
    LPCTSTR pstrFileName,
    CInternetConnection* pConnection,
    BOOL bReadMode);

CInternetFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrFileName,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext,
    BOOL bReadMode);
```

### <a name="parameters"></a>매개 변수

*hFile*<br/>
인터넷 파일에 대한 핸들입니다.

*pstrFileName*<br/>
파일 이름이 포함된 문자열에 대한 포인터입니다.

*pConnection*<br/>
[CInternetConnection](../../mfc/reference/cinternetconnection-class.md) 개체에 대한 포인터입니다.

*bReadMode*<br/>
파일이 읽기 전용인지 여부를 나타냅니다.

*hSession*<br/>
인터넷 세션에 대한 핸들입니다.

*pstrServer*<br/>
서버 이름을 포함하는 문자열에 대한 포인터입니다.

*dwContext*<br/>
개체에 대한 컨텍스트 `CInternetFile` 식별자입니다. 컨텍스트 식별자에 대한 자세한 내용은 [WinInet 기본 정보를](../../mfc/wininet-basics.md) 참조하십시오.

### <a name="remarks"></a>설명

개체를 `CInternetFile` 직접 만들지 않습니다. 대신 [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) 또는 [CHttpConnection::OpenRequest를](../../mfc/reference/chttpconnection-class.md#openrequest)호출하여 파생 된 클래스 중 하나의 개체를 만듭니다. `CInternetFile` [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)을 호출하여 개체를 만들 수도 있습니다.

## <a name="cinternetfileclose"></a><a name="close"></a>C인터넷파일::닫기

를 `CInternetFile` 닫고 해당 리소스를 해제합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

파일을 작성하기 위해 열린 경우 모든 버퍼링된 데이터가 호스트에 기록되도록 [플러시에](#flush) 대한 암시적 호출이 있습니다. 파일 사용이 완료되면 호출해야 `Close` 합니다.

## <a name="cinternetfileflush"></a><a name="flush"></a>C인터넷 파일::플러시

쓰기 버퍼의 내용을 플러시하려면 이 멤버 함수를 호출합니다.

```
virtual void Flush();
```

### <a name="remarks"></a>설명

메모리의 모든 데이터가 실제로 대상 컴퓨터에 기록되었는지 확인하고 호스트 컴퓨터와의 트랜잭션이 완료되었는지 확인하는 데 사용합니다. `Flush` `Flush`쓰기 위해 `CInternetFile` 열린 개체에만 효과적입니다.

## <a name="cinternetfilegetlength"></a><a name="getlength"></a>C인터넷 파일::GetLength

파일 크기를 반환합니다.

```
virtual ULONGLONG GetLength() const;
```

## <a name="cinternetfilem_hfile"></a><a name="m_hfile"></a>C인터넷파일:m_hFile

이 개체와 연결된 파일에 대한 핸들입니다.

```
HINTERNET m_hFile;
```

## <a name="cinternetfileoperator-hinternet"></a><a name="operator_hinternet"></a>C인터넷파일:운영자 HINTERNET

이 연산자를 사용하여 현재 인터넷 세션의 Windows 핸들을 가져옵니다.

```
operator HINTERNET() const;
```

## <a name="cinternetfileread"></a><a name="read"></a>C인터넷파일::읽기

*lpvBuf,* 지정된 바이트 수, *nCount에서*시작하여 지정된 메모리로 읽으려면 이 멤버 함수를 호출합니다.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
파일 데이터를 읽을 메모리 주소에 대한 포인터입니다.

*nCount*<br/>
쓸 바이트 수 입니다.

### <a name="return-value"></a>Return Value

버퍼로 전송된 바이트 수입니다. 파일 끝에 도달한 경우 반환 값은 *nCount보다* 작을 수 있습니다.

### <a name="remarks"></a>설명

함수는 파일이 끝나는 경우 *nCount* 보다 작을 수 있는 바이트 수를 반환합니다. 파일을 읽는 동안 오류가 발생하면 함수는 오류를 설명하는 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체를 throw합니다. 파일의 끝을 지나서 읽는 것은 오류로 간주되지 않으며 예외가 throw되지 않습니다.

모든 데이터를 검색하려면 메서드가 0을 반환할 `CInternetFile::Read` 때까지 응용 프로그램이 메서드를 계속 호출해야 합니다.

## <a name="cinternetfilereadstring"></a><a name="readstring"></a>C인터넷파일::읽기 문자열

이 멤버 함수를 호출하여 줄 바운더문자를 찾을 때까지 문자 스트림을 읽습니다.

```
virtual BOOL ReadString(CString& rString);

virtual LPTSTR ReadString(
    LPTSTR pstr,
    UINT nMax);
```

### <a name="parameters"></a>매개 변수

*pstr*<br/>
읽는 줄을 수신하는 문자열에 대한 포인터입니다.

*nMax*<br/>
읽을 최대 문자 수입니다.

*rString*<br/>
읽기 줄을 받는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

[CInternetFile](../../mfc/reference/cinternetfile-class.md) 개체에서 검색된 일반 데이터를 포함하는 버퍼에 대한 포인터입니다. 이 메서드에 전달된 버퍼의 데이터 형식에 관계없이 데이터에 대한 조작(예: 유니코드로 변환)을 수행하지 않으므로 **반환된** <strong>\*</strong> 데이터를 void 형식이 반환된 것처럼 원하는 구조에 매핑해야 합니다.

데이터를 읽지 않고 파일 끝에 도달한 경우 NULL; 또는, 부울 경우, 거짓 파일의 끝에 도달 한 경우 어떤 데이터를 읽지 않고.

### <a name="remarks"></a>설명

이 함수는 *pstr* 매개 변수에서 참조하는 메모리에 결과 선을 배치합니다. *nMax에서*지정한 최대 문자 수에 도달하면 문자 읽기가 중지됩니다. 버퍼는 항상 종료 null 문자를 받습니다.

`ReadString` [SetReadBufferSize를](#setreadbuffersize)먼저 호출하지 않고 호출하면 4096 바이트의 버퍼를 얻을 수 있습니다.

## <a name="cinternetfileseek"></a><a name="seek"></a>C인터넷 파일::검색

이 멤버 함수를 호출하여 이전에 열린 파일에서 포인터의 위치를 바릅니다.

```
virtual ULONGLONG Seek(
    LONGLONG lOffset,
    UINT nFrom);
```

### <a name="parameters"></a>매개 변수

*lOffset*<br/>
바이트로 오프셋하여 파일의 읽기/쓰기 포인터를 이동합니다.

*nFrom*<br/>
오프셋에 대한 상대 참조입니다. 다음 값 중 하나여야 합니다.

- `CFile::begin`파일 포인터 *lOff* 바이트를 파일의 시작 부분에서 앞으로 이동합니다.

- `CFile::current`파일 포인터 *lOff* 바이트를 파일의 현재 위치에서 이동합니다.

- `CFile::end`파일 포인터 *lOff* 바이트를 파일 끝에서 이동합니다. *lOff는* 기존 파일을 검색하려면 음수여야 합니다. 양수 값은 파일의 끝을 지나추구합니다.

### <a name="return-value"></a>Return Value

요청된 위치가 합법적인 경우 파일의 처음부터 새 바이트 오프셋; 그렇지 않으면 값이 정의되지 않고 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체가 throw됩니다.

### <a name="remarks"></a>설명

이 `Seek` 함수는 포인터를 지정된 양또는 상대적으로 이동하여 파일 내용에 임의로 액세스할 수 있도록 합니다. 검색 하는 동안 실제로 데이터를 읽을 수 없습니다.

현재 이 멤버 함수에 대한 호출은 개체와 `CHttpFile` 연결된 데이터에 대해서만 지원됩니다. FTP 또는 고퍼 요청에는 지원되지 않습니다. 이러한 지원되지 않는 서비스 중 하나를 호출하면 `Seek` ERROR_INTERNET_INVALID_OPERATION Win32 오류 코드로 다시 전달됩니다.

파일이 열리면 파일 포인터는 파일의 시작 부분인 오프셋 0에 있습니다.

> [!NOTE]
> 을 `Seek` 사용하면 [Flush](#flush)에 대한 암시적 호출이 발생할 수 있습니다.

### <a name="example"></a>예제

  기본 클래스 [구현(CFile::Seek)에](../../mfc/reference/cfile-class.md#seek)대한 예제를 참조하십시오.

## <a name="cinternetfilesetreadbuffersize"></a><a name="setreadbuffersize"></a>C인터넷파일::세트읽기버퍼크기

`CInternetFile`이 멤버 함수를 호출하여 -derived 개체에서 사용하는 임시 읽기 버퍼의 크기를 설정합니다.

```
BOOL SetReadBufferSize(UINT nReadSize);
```

### <a name="parameters"></a>매개 변수

*nReadSize*<br/>
원하는 버퍼 크기(바이트)입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

기본 WinInet API는 버퍼링을 수행하지 않으므로 읽을 데이터의 양에 관계없이 응용 프로그램에서 데이터를 효율적으로 읽을 수 있는 버퍼 크기를 선택합니다. [Read에](#read) 대한 각 호출에 일반적으로 큰 데이터(예: 4KB 이상)가 포함된 경우 버퍼가 필요하지 않습니다. 그러나 작은 데이터 `Read` 청크를 얻기 위해 호출하거나 [ReadString을](#readstring) 사용하여 한 번에 개별 줄을 읽는 경우 읽기 버퍼는 응용 프로그램 성능을 향상시킵니다.

기본적으로 개체는 `CInternetFile` 읽기에 대한 버퍼링을 제공하지 않습니다. 이 멤버 함수를 호출하는 경우 읽기 액세스를 위해 파일이 열렸는지 확인해야 합니다.

언제든지 버퍼 크기를 늘릴 수 있지만 버퍼를 줄이면 아무런 효과가 없습니다. 먼저 `SetReadBufferSize`를 호출하지 않고 [ReadString](#readstring)를 호출하는 경우 4096 바이트의 버퍼를 가져옵니다.

## <a name="cinternetfilesetwritebuffersize"></a><a name="setwritebuffersize"></a>C인터넷파일::셋쓰기버퍼크기

`CInternetFile`이 멤버 함수를 호출하여 -derived 개체에서 사용하는 임시 쓰기 버퍼의 크기를 설정합니다.

```
BOOL SetWriteBufferSize(UINT nWriteSize);
```

### <a name="parameters"></a>매개 변수

*nWriteSize*<br/>
버퍼 크기(바이트)입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출에 실패하면 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 오류의 원인을 확인할 수 있습니다.

### <a name="remarks"></a>설명

기본 WinInet API는 버퍼링을 수행하지 않으므로 작성할 데이터의 양에 관계없이 응용 프로그램이 데이터를 효율적으로 쓸 수 있는 버퍼 크기를 선택합니다. [Write에](#write) 대한 각 호출에 일반적으로 많은 양의 데이터(예: 한 번에 4KB 이상)가 포함된 경우 버퍼가 필요하지 않습니다. 그러나 [쓰기를](#write) 호출하여 작은 데이터 청크를 작성하는 경우 쓰기 버퍼는 응용 프로그램의 성능을 향상시킵니다.

기본적으로 개체는 `CInternetFile` 쓰기에 대한 버퍼링을 제공하지 않습니다. 이 멤버 함수를 호출하는 경우 쓰기 액세스를 위해 파일이 열렸는지 확인해야 합니다. 언제든지 쓰기 버퍼의 크기를 변경할 수 있지만 이렇게 하면 [Flush에](#flush)대한 암시적 호출이 발생합니다.

## <a name="cinternetfilewrite"></a><a name="write"></a>C인터넷파일::쓰기

주어진 메모리, *lpvBuf,* 바이트의 지정된 수, *nCount에*쓰기 위해이 멤버 함수를 호출합니다 .

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
작성할 첫 번째 바이트에 대한 포인터입니다.

*nCount*<br/>
기록할 바이트 수를 지정합니다.

### <a name="remarks"></a>설명

데이터를 작성하는 동안 오류가 발생하면 함수는 오류를 설명하는 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체를 throw합니다.

## <a name="cinternetfilewritestring"></a><a name="writestring"></a>C인터넷파일::쓰기스트링

이 함수는 null-종료된 문자열을 연결된 파일에 씁니다.

```
virtual void WriteString(LPCTSTR pstr);
```

### <a name="parameters"></a>매개 변수

*pstr*<br/>
작성할 내용을 포함하는 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

데이터를 작성하는 동안 오류가 발생하면 함수는 오류를 설명하는 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체를 throw합니다.

## <a name="see-also"></a>참고 항목

[CStdioFile 클래스](../../mfc/reference/cstdiofile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C인터넷커넥션 클래스](../../mfc/reference/cinternetconnection-class.md)
