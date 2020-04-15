---
title: CAtlTemporaryFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::Close
- ATLFILE/ATL::CAtlTemporaryFile::Create
- ATLFILE/ATL::CAtlTemporaryFile::Flush
- ATLFILE/ATL::CAtlTemporaryFile::GetPosition
- ATLFILE/ATL::CAtlTemporaryFile::GetSize
- ATLFILE/ATL::CAtlTemporaryFile::HandsOff
- ATLFILE/ATL::CAtlTemporaryFile::HandsOn
- ATLFILE/ATL::CAtlTemporaryFile::LockRange
- ATLFILE/ATL::CAtlTemporaryFile::Read
- ATLFILE/ATL::CAtlTemporaryFile::Seek
- ATLFILE/ATL::CAtlTemporaryFile::SetSize
- ATLFILE/ATL::CAtlTemporaryFile::TempFileName
- ATLFILE/ATL::CAtlTemporaryFile::UnlockRange
- ATLFILE/ATL::CAtlTemporaryFile::Write
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
ms.openlocfilehash: 605e4bcbe7208b18d8d1a50507e8e142a93bde5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321317"
---
# <a name="catltemporaryfile-class"></a>CAtlTemporaryFile 클래스

이 클래스는 임시 파일을 만들고 사용하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAtlTemporaryFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAtl 임시 파일::CAtl 임시 파일](#catltemporaryfile)|생성자입니다.|
|[CAtl 임시 파일::~CAtl임시파일](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAtl임시 파일::닫기](#close)|임시 파일을 닫고 해당 내용을 삭제하거나 지정된 파일 이름 아래에 저장하려면 이 메서드를 호출합니다.|
|[CAtl임시 파일::만들기](#create)|임시 파일을 만들려면 이 메서드를 호출합니다.|
|[CAtl임시 파일::플러시](#flush)|파일 버퍼에 남아 있는 모든 데이터를 임시 파일에 기록하도록 하려면 이 메서드를 호출합니다.|
|[CAtl임시 파일::GetPosition](#getposition)|이 메서드를 호출하여 현재 파일 포인터 위치를 가져옵니다.|
|[CAtl 임시 파일::GetSize](#getsize)|임시 파일의 바이트 단위 크기를 얻으려면이 메서드를 호출 합니다.|
|[CAtl임시 파일::핸즈오프](#handsoff)|이 메서드를 호출하여 개체에서 `CAtlTemporaryFile` 파일의 연결을 해제합니다.|
|[CAtl 임시 파일::핸즈온](#handson)|이 메서드를 호출하여 기존 임시 파일을 열고 포인터를 파일 끝에 배치합니다.|
|[CAtl임시 파일::잠금 범위](#lockrange)|이 메서드를 호출하여 파일의 영역을 잠그면 다른 프로세스가 액세스하지 못하도록 합니다.|
|[CAtl임시 파일::읽기](#read)|파일 포인터가 표시된 위치에서 시작하는 임시 파일의 데이터를 읽으려면 이 메서드를 호출합니다.|
|[CAtl임시 파일::검색](#seek)|임시 파일의 파일 포인터를 이동하려면 이 메서드를 호출합니다.|
|[CAtl 임시 파일::SetSize](#setsize)|임시 파일의 크기를 설정하려면 이 메서드를 호출합니다.|
|[CAtl 임시 파일::임시 파일 이름](#tempfilename)|임시 파일의 이름을 반환하려면 이 메서드를 호출합니다.|
|[CAtl임시 파일::잠금 해제 범위](#unlockrange)|임시 파일의 영역잠금을 해제하려면 이 메서드를 호출합니다.|
|[CAtl임시 파일::쓰기](#write)|파일 포인터가 표시된 위치에서 시작하는 임시 파일에 데이터를 작성하려면 이 메서드를 호출합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CAtl임시 파일::연산자 핸들](#operator_handle)|임시 파일에 핸들을 반환합니다.|

## <a name="remarks"></a>설명

`CAtlTemporaryFile`임시 파일을 쉽게 만들고 사용할 수 있습니다. 파일의 이름이 자동으로 지정되고, 열리고, 닫히고, 삭제됩니다. 파일을 닫은 후 파일 내용이 필요한 경우 지정된 이름을 가진 새 파일에 저장할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlfile.h

## <a name="example"></a>예제

[CAtl임시 파일::CAtl 임시 파일](#catltemporaryfile)에 대한 예제를 참조하십시오.

## <a name="catltemporaryfilecatltemporaryfile"></a><a name="catltemporaryfile"></a>CAtl 임시 파일::CAtl 임시 파일

생성자입니다.

```
CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>설명

[CAtlTemporaryFile ::Create에](#create)대한 호출이 수행될 때까지 파일이 실제로 열리지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]

## <a name="catltemporaryfilecatltemporaryfile"></a><a name="dtor"></a>CAtl 임시 파일::~CAtl임시파일

소멸자입니다.

```
~CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>설명

소멸자는 [CAtlTemporaryFile::Close를](#close)호출합니다.

## <a name="catltemporaryfileclose"></a><a name="close"></a>CAtl임시 파일::닫기

임시 파일을 닫고 해당 내용을 삭제하거나 지정된 파일 이름 아래에 저장하려면 이 메서드를 호출합니다.

```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*szNewName*<br/>
임시 파일의 내용을 저장할 새 파일의 이름입니다. 이 인수가 NULL이면 임시 파일의 내용이 삭제됩니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="example"></a>예제

[CAtl임시 파일::CAtl 임시 파일](#catltemporaryfile)에 대한 예제를 참조하십시오.

## <a name="catltemporaryfilecreate"></a><a name="create"></a>CAtl임시 파일::만들기

임시 파일을 만들려면 이 메서드를 호출합니다.

```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```

### <a name="parameters"></a>매개 변수

*pszDir*<br/>
임시 파일의 경로입니다. NULL이면 [GetTempPath가](/windows/win32/api/fileapi/nf-fileapi-gettemppathw) 호출되어 경로를 할당합니다.

*dwDesiredAccess*<br/>
원하는 액세스. Windows SDK의 [CreateFile에서](/windows/win32/api/fileapi/nf-fileapi-createfilew) *dwDesiredAccess를* 참조하십시오.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="example"></a>예제

[CAtl임시 파일::CAtl 임시 파일](#catltemporaryfile)에 대한 예제를 참조하십시오.

## <a name="catltemporaryfileflush"></a><a name="flush"></a>CAtl임시 파일::플러시

파일 버퍼에 남아 있는 모든 데이터를 임시 파일에 기록하도록 하려면 이 메서드를 호출합니다.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

파일이 닫히지 않는다는 점을 제외하면 [CAtlTemporaryFile::HandsOff와](#handsoff)유사합니다.

### <a name="example"></a>예제

[CAtl임시 파일::CAtl 임시 파일](#catltemporaryfile)에 대한 예제를 참조하십시오.

## <a name="catltemporaryfilegetposition"></a><a name="getposition"></a>CAtl임시 파일::GetPosition

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

파일 포인터 위치를 변경하려면 [CAtlTemporaryFile::Seek](#seek)를 사용합니다.

## <a name="catltemporaryfilegetsize"></a><a name="getsize"></a>CAtl 임시 파일::GetSize

임시 파일의 바이트 단위 크기를 얻으려면이 메서드를 호출 합니다.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>매개 변수

*nLen*<br/>
파일의 바이트 수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="catltemporaryfilehandsoff"></a><a name="handsoff"></a>CAtl임시 파일::핸즈오프

이 메서드를 호출하여 개체에서 `CAtlTemporaryFile` 파일의 연결을 해제합니다.

```
HRESULT HandsOff() throw();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

`HandsOff`및 [CAtlTemporaryFile::HandsOn은](#handson) 개체에서 파일의 연결을 해제하고 필요한 경우 다시 연결하는 데 사용됩니다. `HandsOff`을 사용하여 파일 버퍼에 남아 있는 모든 데이터를 임시 파일에 기록한 다음 파일을 닫습니다. 파일을 영구적으로 닫고 삭제하거나 지정된 이름으로 파일의 내용을 닫고 유지하려면 [CAtlTemporaryFile:Close](#close)를 사용합니다.

## <a name="catltemporaryfilehandson"></a><a name="handson"></a>CAtl 임시 파일::핸즈온

이 메서드를 호출하여 기존 임시 파일을 열고 포인터를 파일 끝에 배치합니다.

```
HRESULT HandsOn() throw();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[CAtl임시 파일::HandsOff](#handsoff) `HandsOn` 개체에서 파일 의 연결을 해제 하 고 필요한 경우 다시 연결 하는 데 사용 됩니다.

## <a name="catltemporaryfilelockrange"></a><a name="lockrange"></a>CAtl임시 파일::잠금 범위

이 메서드를 호출하여 임시 파일의 영역을 잠그면 다른 프로세스가 액세스하지 못하도록 합니다.

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

파일의 바이트를 잠그면 다른 프로세스에서 해당 바이트에 액세스할 수 없습니다. 파일의 둘 이상의 영역을 잠글 수 있지만 겹치는 영역은 허용되지 않습니다. 리전잠금을 성공적으로 해제하려면 [CAtlTemporaryFile::UnlockRange를](#unlockrange)사용하여 바이트 범위가 이전에 잠긴 지역과 정확히 일치하도록 합니다. `LockRange`인접 영역을 병합하지 않습니다. 잠긴 두 영역이 인접한 경우 각각을 별도로 잠금 해제해야 합니다.

## <a name="catltemporaryfileoperator-handle"></a><a name="operator_handle"></a>CAtl임시 파일::연산자 핸들

임시 파일에 핸들을 반환합니다.

```
operator HANDLE() throw();
```

## <a name="catltemporaryfileread"></a><a name="read"></a>CAtl임시 파일::읽기

파일 포인터가 표시된 위치에서 시작하는 임시 파일의 데이터를 읽으려면 이 메서드를 호출합니다.

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```

### <a name="parameters"></a>매개 변수

*pBuffer*<br/>
파일에서 읽은 데이터를 수신할 버퍼에 대한 포인터입니다.

*nBufSize*<br/>
버퍼 크기(바이트)입니다.

*nBytes읽기*<br/>
읽은 바이트 수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[CAtlFile::Read를](../../atl/reference/catlfile-class.md#read)호출합니다. 파일 포인터의 위치를 변경하려면 [CAtlTemporaryFile::Seek](#seek)를 호출합니다.

### <a name="example"></a>예제

[CAtl임시 파일::CAtl 임시 파일](#catltemporaryfile)에 대한 예제를 참조하십시오.

## <a name="catltemporaryfileseek"></a><a name="seek"></a>CAtl임시 파일::검색

임시 파일의 파일 포인터를 이동하려면 이 메서드를 호출합니다.

```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>매개 변수

*n오프셋*<br/>
*dwFrom에* 의해 주어진 시작 점에서 바이트로 오프셋.

*dwFrom*<br/>
시작점(FILE_BEGIN, FILE_CURRENT 또는 FILE_END).

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[CAtlFile::Seek를](../../atl/reference/catlfile-class.md#seek)호출합니다. 현재 파일 포인터 위치를 얻으려면 [CAtlTemporaryFile ::GetPosition](#getposition)를 호출합니다.

### <a name="example"></a>예제

[CAtl임시 파일::CAtl 임시 파일](#catltemporaryfile)에 대한 예제를 참조하십시오.

## <a name="catltemporaryfilesetsize"></a><a name="setsize"></a>CAtl 임시 파일::SetSize

임시 파일의 크기를 설정하려면 이 메서드를 호출합니다.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>매개 변수

*n뉴렌*<br/>
바이트로 파일의 새 길이입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[CAtlFile::SetSize를](../../atl/reference/catlfile-class.md#setsize)호출합니다. 반환시 파일 포인터는 파일의 끝에 배치됩니다.

## <a name="catltemporaryfiletempfilename"></a><a name="tempfilename"></a>CAtl 임시 파일::임시 파일 이름

임시 파일의 이름을 반환하려면 이 메서드를 호출합니다.

```
LPCTSTR TempFileName() throw();
```

### <a name="return-value"></a>Return Value

파일 이름을 가리키는 LPCTSTR를 반환합니다.

### <a name="remarks"></a>설명

파일 이름은 [GetTempFile](/windows/win32/api/fileapi/nf-fileapi-gettempfilenamew)Windows SDK 함수를 호출하여 [CAtlTemporaryFile::CAtl임시](#catltemporaryfile) 파일에서 생성됩니다. 파일 확장은 항상 임시 파일에 대한 "TFR"이 됩니다.

## <a name="catltemporaryfileunlockrange"></a><a name="unlockrange"></a>CAtl임시 파일::잠금 해제 범위

임시 파일의 영역잠금을 해제하려면 이 메서드를 호출합니다.

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

[호출 CAtlFile ::잠금 해제 범위](../../atl/reference/catlfile-class.md#unlockrange).

## <a name="catltemporaryfilewrite"></a><a name="write"></a>CAtl임시 파일::쓰기

파일 포인터가 표시된 위치에서 시작하는 임시 파일에 데이터를 작성하려면 이 메서드를 호출합니다.

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*pBuffer*<br/>
파일에 기록할 데이터를 포함하는 버퍼입니다.

*nBufSize*<br/>
버퍼에서 전송할 바이트 수입니다.

*pnBytes작성*<br/>
쓴 바이트 수.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[CAtlFile::쓰기를](../../atl/reference/catlfile-class.md#write)호출합니다.

### <a name="example"></a>예제

[CAtl임시 파일::CAtl 임시 파일](#catltemporaryfile)에 대한 예제를 참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CAtlFile 클래스](../../atl/reference/catlfile-class.md)
