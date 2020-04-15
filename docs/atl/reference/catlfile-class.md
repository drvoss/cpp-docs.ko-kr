---
title: CAtlFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlFile
- ATLFILE/ATL::CAtlFile
- ATLFILE/ATL::CAtlFile::CAtlFile
- ATLFILE/ATL::CAtlFile::Create
- ATLFILE/ATL::CAtlFile::Flush
- ATLFILE/ATL::CAtlFile::GetOverlappedResult
- ATLFILE/ATL::CAtlFile::GetPosition
- ATLFILE/ATL::CAtlFile::GetSize
- ATLFILE/ATL::CAtlFile::LockRange
- ATLFILE/ATL::CAtlFile::Read
- ATLFILE/ATL::CAtlFile::Seek
- ATLFILE/ATL::CAtlFile::SetSize
- ATLFILE/ATL::CAtlFile::UnlockRange
- ATLFILE/ATL::CAtlFile::Write
- ATLFILE/ATL::CAtlFile::m_pTM
helpviewer_keywords:
- CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
ms.openlocfilehash: 39f323874ccde5178722235b9beb34c2572407a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318972"
---
# <a name="catlfile-class"></a>CAtlFile 클래스

이 클래스는 Windows 파일 처리 API 주위에 씬 래퍼를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAtlFile : public CHandle
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[카틀 파일::CAtlFile](#catlfile)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAtlFile::만들기](#create)|파일을 만들거나 열려면 이 메서드를 호출합니다.|
|[카틀 파일 :: 플러시](#flush)|이 메서드를 호출하여 파일의 버퍼를 지우고 버퍼링된 모든 데이터가 파일에 기록됩니다.|
|[CAtlFile::GetOverlapped결과](#getoverlappedresult)|이 메서드를 호출하여 파일에서 겹친 작업의 결과를 가져옵니다.|
|[CAtlFile::Getposition](#getposition)|파일에서 현재 파일 포인터 위치를 얻으려면이 메서드를 호출합니다.|
|[카틀 파일::겟사이즈](#getsize)|파일의 바이트로 크기를 얻으려면이 메서드를 호출합니다.|
|[카틀 파일 :: 잠금 범위](#lockrange)|이 메서드를 호출하여 파일의 영역을 잠그면 다른 프로세스가 액세스하지 못하도록 합니다.|
|[CAtlFile::읽기](#read)|이 메서드를 호출하여 파일 포인터가 표시된 위치에서 시작하는 파일의 데이터를 읽습니다.|
|[CAtlFile::검색](#seek)|파일의 파일 포인터를 이동 하려면이 메서드를 호출 합니다.|
|[카틀파일::세트크기](#setsize)|파일 크기를 설정하려면 이 메서드를 호출합니다.|
|[카틀파일::언락레인지](#unlockrange)|이 메서드를 호출하여 파일 영역의 잠금을 해제합니다.|
|[CAtlFile::쓰기](#write)|이 메서드를 호출하여 파일 포인터가 표시된 위치에서 시작하는 파일에 데이터를 작성합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[카틀 파일:m_pTM](#m_ptm)|개체에 `CAtlTransactionManager` 대한 포인터|

## <a name="remarks"></a>설명

파일 처리 요구 사항이 비교적 간단하지만 MFC 종속성을 포함하지 않고 Windows API가 제공하는 것보다 더 추상화가 필요한 경우 이 클래스를 사용합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CHandle](../../atl/reference/chandle-class.md)

`CAtlFile`

## <a name="requirements"></a>요구 사항

**헤더:** atlfile.h

## <a name="catlfilecatlfile"></a><a name="catlfile"></a>카틀 파일::CAtlFile

생성자입니다.

```
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```

### <a name="parameters"></a>매개 변수

*파일*<br/>
파일 개체입니다.

*hFile*<br/>
파일 핸들입니다.

*Ptm*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="remarks"></a>설명

복사 생성자는 파일 핸들의 소유권을 `CAtlFile` 원래 개체에서 새로 구성된 개체로 전송합니다.

## <a name="catlfilecreate"></a><a name="create"></a>CAtlFile::만들기

파일을 만들거나 열려면 이 메서드를 호출합니다.

```
HRESULT Create(
    LPCTSTR szFilename,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes = FILE_ATTRIBUTE_NORMAL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    HANDLE hTemplateFile = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*szFilename*<br/>
파일 이름입니다.

*dwDesiredAccess*<br/>
원하는 액세스. Windows SDK의 [CreateFile에서](/windows/win32/api/fileapi/nf-fileapi-createfilew) *dwDesiredAccess를* 참조하십시오.

*dwShare모드*<br/>
공유 모드입니다. *에서 dwShareMode를* `CreateFile`참조하십시오.

*dw크리에이션 디포지션*<br/>
창조 성향. *dwCreationDisposition를* `CreateFile`참조하십시오.

*dwFlagsand속성*<br/>
플래그 및 특성입니다. *dwFlags및속성* . `CreateFile`

*lpsa*<br/>
보안 특성입니다. *lpSecurity속성* 은 `CreateFile`을 참조하십시오.

*h템플릿파일*<br/>
템플릿 파일입니다. *에서 hTemplateFile을* `CreateFile`참조하십시오.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[CreateFile을](/windows/win32/api/fileapi/nf-fileapi-createfilew) 호출하여 파일을 만들거나 엽니다.

## <a name="catlfileflush"></a><a name="flush"></a>카틀 파일 :: 플러시

이 메서드를 호출하여 파일의 버퍼를 지우고 버퍼링된 모든 데이터가 파일에 기록됩니다.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[플러시파일버퍼를](/windows/win32/api/fileapi/nf-fileapi-flushfilebuffers) 호출하여 버퍼링된 데이터를 파일로 플러시합니다.

## <a name="catlfilegetoverlappedresult"></a><a name="getoverlappedresult"></a>CAtlFile::GetOverlapped결과

이 메서드를 호출하여 파일에서 겹친 작업의 결과를 가져옵니다.

```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```

### <a name="parameters"></a>매개 변수

*겹쳐있는*<br/>
중첩된 구조입니다. Windows SDK에서 [오버랩된 결과에서](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult) *lpOverlapped를* 참조하십시오.

*dwBytes전송됨*<br/>
바이트가 전송되었습니다. 를 `GetOverlappedResult` *참조하십시오.에서 전송된 번호의*

*b대기*<br/>
대기 옵션입니다. *에서 bWait를* `GetOverlappedResult`참조하십시오.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[GetOverlappedResult](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult) 호출하여 파일에서 겹친 작업의 결과를 가져옵니다.

## <a name="catlfilegetposition"></a><a name="getposition"></a>CAtlFile::Getposition

이 메서드를 호출하여 현재 파일 포인터 위치를 가져옵니다.

```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
바이트의 위치입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

현재 파일 포인터 위치를 얻기 위해 [SetFilePointer를](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) 호출합니다.

## <a name="catlfilegetsize"></a><a name="getsize"></a>카틀 파일::겟사이즈

파일의 바이트로 크기를 얻으려면이 메서드를 호출합니다.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>매개 변수

*nLen*<br/>
파일의 바이트 수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[GetFileSize를](/windows/win32/api/fileapi/nf-fileapi-getfilesize) 호출하여 파일의 바이트 로 크기를 가져옵니다.

## <a name="catlfilelockrange"></a><a name="lockrange"></a>카틀 파일 :: 잠금 범위

이 메서드를 호출하여 파일의 영역을 잠그면 다른 프로세스가 액세스하지 못하도록 합니다.

```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
잠금을 시작해야 하는 파일의 위치입니다.

*nCount*<br/>
잠글 바이트 범위의 길이입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[LockFile을](/windows/win32/api/fileapi/nf-fileapi-lockfile) 호출하여 파일의 영역을 잠급전도합니다. 파일의 바이트를 잠그면 다른 프로세스에서 해당 바이트에 액세스할 수 없습니다. 파일의 둘 이상의 영역을 잠글 수 있지만 겹치는 영역은 허용되지 않습니다. 영역의 잠금을 해제할 때 [CAtlFile::UnlockRange를](#unlockrange)사용하여 바이트 범위는 이전에 잠긴 지역과 정확히 일치해야 합니다. `LockRange`인접 영역을 병합하지 않습니다. 잠긴 두 영역이 인접한 경우 각각을 별도로 잠금 해제해야 합니다.

## <a name="catlfilem_ptm"></a><a name="m_ptm"></a>카틀 파일:m_pTM

`CAtlTransactionManager` 개체에 대한 포인터입니다.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>설명

## <a name="catlfileread"></a><a name="read"></a>CAtlFile::읽기

이 메서드를 호출하여 파일 포인터가 표시된 위치에서 시작하는 파일의 데이터를 읽습니다.

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();
```

### <a name="parameters"></a>매개 변수

*pBuffer*<br/>
파일에서 읽은 데이터를 수신할 버퍼에 대한 포인터입니다.

*nBufSize*<br/>
버퍼 크기(바이트)입니다.

*nBytes읽기*<br/>
읽은 바이트 수입니다.

*겹쳐있는*<br/>
중첩된 구조입니다. Windows SDK의 [ReadFile에서](/windows/win32/api/fileapi/nf-fileapi-readfile) *중복 된 lpOverlapped를* 참조하십시오.

*pfn완성루틴*<br/>
완료 루틴입니다. 윈도우 SDK에서 [ReadFileEx에서](/windows/win32/api/fileapi/nf-fileapi-readfileex) *lpCompletionRoutine를* 참조하십시오.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

처음 세 가지 양식은 [파일에서](/windows/win32/api/fileapi/nf-fileapi-readfile)데이터를 읽을 수 있는 마지막 [ReadFileEx인 ReadFile을](/windows/win32/api/fileapi/nf-fileapi-readfileex) 호출합니다. [CAtlFile::Seek를](#seek) 사용하여 파일 포인터를 이동합니다.

## <a name="catlfileseek"></a><a name="seek"></a>CAtlFile::검색

파일의 파일 포인터를 이동 하려면이 메서드를 호출 합니다.

```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>매개 변수

*n오프셋*<br/>
*dwFrom*.

*dwFrom*<br/>
시작점(FILE_BEGIN, FILE_CURRENT 또는 FILE_END).

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[SetFilePointer를](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) 호출하여 파일 포인터를 이동합니다.

## <a name="catlfilesetsize"></a><a name="setsize"></a>카틀파일::세트크기

파일 크기를 설정하려면 이 메서드를 호출합니다.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>매개 변수

*n뉴렌*<br/>
바이트로 파일의 새 길이입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

파일 크기를 설정하려면 [SetFile포인터](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) 및 [SetEndOfFile을](/windows/win32/api/fileapi/nf-fileapi-setendoffile) 호출합니다. 반환시 파일 포인터는 파일의 끝에 배치됩니다.

## <a name="catlfileunlockrange"></a><a name="unlockrange"></a>카틀파일::언락레인지

이 메서드를 호출하여 파일 영역의 잠금을 해제합니다.

```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
잠금 해제가 시작되는 파일의 위치입니다.

*nCount*<br/>
잠금을 해제할 바이트 범위의 길이입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[UnlockFile을](/windows/win32/api/fileapi/nf-fileapi-unlockfile) 호출하여 파일 영역의 잠금을 해제합니다.

## <a name="catlfilewrite"></a><a name="write"></a>CAtlFile::쓰기

이 메서드를 호출하여 파일 포인터가 표시된 위치에서 시작하는 파일에 데이터를 작성합니다.

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();
```

### <a name="parameters"></a>매개 변수

*pBuffer*<br/>
파일에 기록할 데이터를 포함하는 버퍼입니다.

*nBufSize*<br/>
버퍼에서 전송할 바이트 수입니다.

*겹쳐있는*<br/>
중첩된 구조입니다. Windows SDK의 [WriteFile에서](/windows/win32/api/fileapi/nf-fileapi-writefile) *중복 된 lpOverlapped를* 참조하십시오.

*pfn완성루틴*<br/>
완료 루틴입니다. 윈도우 SDK에서 [WriteFileEx에서](/windows/win32/api/fileapi/nf-fileapi-writefileex) *lpCompletionRoutine를* 참조하십시오.

*pnBytes작성*<br/>
작성된 바이트입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

처음 세 가지 양식은 [WriteFile을](/windows/win32/api/fileapi/nf-fileapi-writefile)호출합니다. [WriteFileEx](/windows/win32/api/fileapi/nf-fileapi-writefileex) [CAtlFile::Seek를](#seek) 사용하여 파일 포인터를 이동합니다.

## <a name="see-also"></a>참고 항목

[선택 윤곽 샘플](../../overview/visual-cpp-samples.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CHandle 클래스](../../atl/reference/chandle-class.md)
