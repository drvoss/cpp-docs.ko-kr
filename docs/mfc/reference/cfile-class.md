---
title: CFile 클래스
ms.date: 06/12/2018
f1_keywords:
- CFile
- AFX/CFile
- AFX/CFile::CFile
- AFX/CFile::Abort
- AFX/CFile::Close
- AFX/CFile::Duplicate
- AFX/CFile::Flush
- AFX/CFile::GetFileName
- AFX/CFile::GetFilePath
- AFX/CFile::GetFileTitle
- AFX/CFile::GetLength
- AFX/CFile::GetPosition
- AFX/CFile::GetStatus
- AFX/CFile::LockRange
- AFX/CFile::Open
- AFX/CFile::Read
- AFX/CFile::Remove
- AFX/CFile::Rename
- AFX/CFile::Seek
- AFX/CFile::SeekToBegin
- AFX/CFile::SeekToEnd
- AFX/CFile::SetFilePath
- AFX/CFile::SetLength
- AFX/CFile::SetStatus
- AFX/CFile::UnlockRange
- AFX/CFile::Write
- AFX/CFile::hFileNull
- AFX/CFile::m_hFile
- AFX/CFile::m_pTM
helpviewer_keywords:
- CFile [MFC], CFile
- CFile [MFC], Abort
- CFile [MFC], Close
- CFile [MFC], Duplicate
- CFile [MFC], Flush
- CFile [MFC], GetFileName
- CFile [MFC], GetFilePath
- CFile [MFC], GetFileTitle
- CFile [MFC], GetLength
- CFile [MFC], GetPosition
- CFile [MFC], GetStatus
- CFile [MFC], LockRange
- CFile [MFC], Open
- CFile [MFC], Read
- CFile [MFC], Remove
- CFile [MFC], Rename
- CFile [MFC], Seek
- CFile [MFC], SeekToBegin
- CFile [MFC], SeekToEnd
- CFile [MFC], SetFilePath
- CFile [MFC], SetLength
- CFile [MFC], SetStatus
- CFile [MFC], UnlockRange
- CFile [MFC], Write
- CFile [MFC], hFileNull
- CFile [MFC], m_hFile
- CFile [MFC], m_pTM
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
ms.openlocfilehash: 53afaf7732811e25729944eb71130a88e4f17a87
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755007"
---
# <a name="cfile-class"></a>CFile 클래스

MFC 파일 클래스의 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CFile : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C파일::CFile](#cfile)|경로 또는 `CFile` 파일 핸들에서 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C파일::중단](#abort)|모든 경고 및 오류를 무시하고 파일을 닫습니다.|
|[CFile::닫기](#close)|파일을 닫고 개체를 삭제합니다.|
|[C파일::D](#duplicate)|이 파일을 기반으로 중복 개체를 생성합니다.|
|[C파일 :: 플러시](#flush)|아직 작성할 데이터를 플러시합니다.|
|[CFile::GetFile 이름](#getfilename)|선택한 파일의 파일 이름을 검색합니다.|
|[C파일::GetFile경로](#getfilepath)|선택한 파일의 전체 파일 경로를 검색합니다.|
|[C파일::GetFile타이틀](#getfiletitle)|선택한 파일의 제목을 검색합니다.|
|[C파일::GetLength](#getlength)|파일의 길이를 검색합니다.|
|[C파일::GetPosition](#getposition)|현재 파일 포인터를 검색합니다.|
|[C파일::GetStatus](#getstatus)|열려 있는 파일의 상태를 검색하거나 정적 버전에서 지정된 파일(정적, 가상 함수)의 상태를 검색합니다.|
|[C파일 :: 잠금 범위](#lockrange)|파일에서 바이트 범위를 잠급전지.|
|[CFile::열기](#open)|오류 테스트 옵션이 있는 파일을 안전하게 엽니다.|
|[C파일::읽기](#read)|현재 파일 위치에 있는 파일에서 버퍼링되지 않은 데이터를 읽습니다.|
|[CFile::제거](#remove)|지정된 파일(정적 함수)을 삭제합니다.|
|[CFile::이름 바꾸기](#rename)|지정된 파일(정적 함수)의 이름을 바꿉니다.|
|[C파일::검색](#seek)|현재 파일 포인터의 위치를 정합니다.|
|[C파일::검색토비](#seektobegin)|현재 파일 포인터를 파일의 시작 부분에 배치합니다.|
|[C파일::검색토엔드](#seektoend)|현재 파일 포인터를 파일 끝에 배치합니다.|
|[C파일::SetFilePath](#setfilepath)|선택한 파일의 전체 파일 경로를 설정합니다.|
|[C파일::설정길이](#setlength)|파일의 길이를 변경합니다.|
|[CFile::설정 상태](#setstatus)|지정된 파일(정적, 가상 함수)의 상태를 설정합니다.|
|[C파일 ::잠금 해제 범위](#unlockrange)|파일에서 다양한 바이트를 잠금 해제합니다.|
|[CFile::쓰기](#write)|현재 파일 위치에 파일의 버퍼링되지 않은 데이터를 씁니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CFile::연산자 핸들](#operator_handle)|개체에 대한 `CFile` 핸들입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C파일::hFileNull](#hfilenull)|개체에 유효한 `CFile` 핸들이 있는지 확인합니다.|
|[C파일:m_hFile](#m_hfile)|일반적으로 운영 체제 파일 핸들이 포함되어 있습니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CFile:m_pTM](#m_ptm)|`CAtlTransactionManager` 개체에 대한 포인터입니다.|

## <a name="remarks"></a>설명

버퍼링되지 않은 이진 디스크 입력/출력 서비스를 직접 제공하며 파생 클래스를 통해 텍스트 파일 및 메모리 파일을 간접적으로 지원합니다. `CFile`Microsoft Foundation 클래스 `CArchive` 개체의 직렬화를 지원하기 위해 클래스와 함께 작동합니다.

이 클래스와 파생 된 클래스 간의 계층 관계를 사용하면 다형성 `CFile` 인터페이스를 통해 모든 파일 개체에서 프로그램을 작동 할 수 있습니다. 예를 들어 메모리 파일은 디스크 파일처럼 행동합니다.

범용 디스크 I/O에 및 파생 클래스를 사용합니다. `CFile` 디스크 `ofstream` 파일로 `iostream` 전송되는 형식의 텍스트에 대해 또는 다른 Microsoft 클래스를 사용합니다.

일반적으로 디스크 파일은 구성 시 `CFile` 자동으로 열리고 파기 시 닫힙습니다. 정적 멤버 함수를 사용하면 파일을 열지 않고도 파일의 상태를 심문할 수 있습니다.

사용에 `CFile`대한 자세한 내용은 *런타임 라이브러리 참조의* [MFC](../../mfc/files-in-mfc.md) 및 [파일 처리문서](../../c-runtime-library/file-handling.md) 파일을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CFile`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cfileabort"></a><a name="abort"></a>C파일::중단

이 개체와 연결된 파일을 닫고 파일을 읽거나 쓸 수 없게 만듭니다.

```
virtual void Abort();
```

### <a name="remarks"></a>설명

개체를 파괴하기 전에 파일을 닫지 않은 경우 소멸자가 파일을 닫습니다.

예외를 처리할 `CFile::Abort` 때는 `CFile::Close` 두 가지 중요한 방법이 다릅니다. 첫째, `Abort` 함수는 실패에 의해 `Abort`무시되기 때문에 실패에 대한 예외를 throw하지 않습니다. 둘째, `Abort` 파일이 열리지 않았거나 이전에 닫혔으면 **ASSERT를** 하지 않습니다.

**힙에** 개체를 `CFile` 할당하는 데 새 개체를 사용한 경우 파일을 닫은 후 삭제해야 합니다. `Abort` 설정 `m_hFile` 에 `CFile::hFileNull`입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]

## <a name="cfilecfile"></a><a name="cfile"></a>C파일::CFile

`CFile` 개체를 생성하고 초기화합니다.

```
CFile();
CFile(CAtlTransactionManager* pTM);
CFile(HANDLE hFile);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags,
CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>매개 변수

*hFile*<br/>
`CFile` 개체에 연결할 파일의 핸들입니다.

*lpsz파일이름*<br/>
`CFile` 개체에 연결할 파일의 상대 또는 전체 경로입니다.

*n오픈 플래그*<br/>
지정한 파일에 대한 파일 액세스 옵션의 비트 조합(OR)입니다. 사용 가능한 옵션은 설명 섹션을 참조하세요.

*Ptm*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="remarks"></a>설명

다음 5개의 테이블에는 *nOpenFlags* 매개 변수에 대한 가능한 옵션이 나열됩니다.

다음 파일 액세스 모드 옵션 중 하나만 선택해야 합니다. 기본 파일 액세스 모드는 `CFile::modeRead`(읽기 전용)입니다.

|값|Description|
|-----------|-----------------|
|`CFile::modeRead`|읽기 권한만 요청합니다.|
|`CFile::modeWrite`|쓰기 권한만 요청합니다.|
|`CFile::modeReadWrite`|읽기 및 쓰기 권한을 요청합니다.|

다음 문자 모드 옵션 중 하나를 선택합니다.

|값|Description|
|-----------|-----------------|
|`CFile::typeBinary`|이진 모드를 설정합니다(파생 클래스에만 사용됨).|
|`CFile::typeText`|캐리지 리턴 라인 피드 쌍에 대한 특수 처리가 있는 텍스트 모드를 설정합니다(파생 클래스에서만 사용).|
|`CFile::typeUnicode`|유니코드 모드를 설정합니다(파생 클래스에만 사용됨). 애플리케이션을 유니코드 구성에서 빌드할 때는 텍스트가 유니코드 형식으로 파일에 기록됩니다. BOM이 파일에 기록되지 않습니다.|

다음 파일 공유 모드 옵션 중 하나만 선택해야 합니다. 기본 파일 공유 모드는 `CFile::shareExclusive`(단독)입니다.

|값|Description|
|-----------|-----------------|
|`CFile::shareDenyNone`|공유 제한이 없습니다.|
|`CFile::shareDenyRead`|다른 모든 사용자에 대해 읽기 권한을 거부합니다.|
|`CFile::shareDenyWrite`|다른 모든 사용자에 대해 쓰기 권한을 거부합니다.|
|`CFile::shareExclusive`|다른 모든 사용자에 대해 읽기 및 쓰기 권한을 거부합니다.|

다음 파일 만들기 모드 옵션 중 첫 번째 옵션 또는 두 옵션을 모두 선택합니다. 기본 만들기 모드는 `CFile::modeNoTruncate`(기존 파일 열기)입니다.

|값|Description|
|-----------|-----------------|
|`CFile::modeCreate`|파일이 없는 경우 새 파일을 만듭니다. 파일이 이미 있는 경우 덮어쓰고 처음에는 길이가 0으로 설정됩니다.|
|`CFile::modeNoTruncate`|파일이 없는 경우 새 파일을 만듭니다. 그렇지 않으면 파일이 이미 있는 경우 개체에 `CFile` 첨부됩니다.|

설명에 따라 다음 파일 캐싱 옵션을 선택합니다. 기본적으로 시스템은 옵션으로 사용할 수 없는 범용 캐싱 스키마를 사용합니다.

|값|Description|
|-----------|-----------------|
|`CFile::osNoBuffer`|시스템에서 파일에 대한 중간 캐시를 사용하지 않습니다. 이 옵션은 다음 2개 옵션을 취소합니다.|
|`CFile::osRandomAccess`|임의 액세스를 위해 파일 캐시가 최적화됩니다. 이 옵션과 순차 검색 옵션을 모두 사용하지 마십시오.|
|`CFile::osSequentialScan`|순차 액세스를 위해 파일 캐시가 최적화됩니다. 이 옵션과 임의 액세스 옵션을 모두 사용하지 마십시오.|
|`CFile::osWriteThrough`|쓰기 작업은 지체 없이 수행됩니다.|

파일 핸들이 상속되지 않도록 하려면 다음 보안 옵션을 선택합니다. 기본적으로 새 자식 프로세스는 파일 핸들을 사용할 수 있습니다.

|값|Description|
|-----------|-----------------|
|`CFile::modeNoInherit`|자식 프로세스가 파일 핸들을 사용하지 못하도록 차단합니다.|

기본 생성자는 멤버를 초기화하지만 `CFile` 개체에 파일을 첨부하지 않습니다. 이 생성기를 사용한 후 [CFile::Open](#open) 메서드를 사용하여 파일을 열고 `CFile` 개체에 연결합니다.

매개 변수가 하나 포함된 생성자는 멤버를 초기화하고 기존 파일을 `CFile` 개체에 연결합니다.

매개 변수가 두 개 포함된 생성자는 멤버를 초기화하고 지정한 파일 열기를 시도합니다. 이 생성자가 지정한 파일을 정상적으로 열면 파일은 `CFile` 개체에 연결되고, 그렇지 않으면 이 생성자가 `CInvalidArgException` 개체에 대한 포인터를 throw합니다. 예외를 처리하는 방법에 대한 자세한 내용은 [예외](../../mfc/exception-handling-in-mfc.md)를 참조하십시오.

개체가 `CFile` 지정된 파일을 성공적으로 열면 `CFile` 개체가 소멸될 때 이 파일이 자동으로 닫힙집니다. 그렇지 않으면 파일이 더 이상 개체에 연결되지 `CFile` 않은 후에 명시적으로 닫아야 합니다.

### <a name="example"></a>예제

다음 코드에서는 `CFile` 사용 방법을 보여줍니다.

[!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]

## <a name="cfileclose"></a><a name="close"></a>CFile::닫기

이 개체와 연결된 파일을 닫고 파일을 읽거나 쓸 수 없게 만듭니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

개체를 파괴하기 전에 파일을 닫지 않은 경우 소멸자가 파일을 닫습니다.

**힙에** 개체를 `CFile` 할당하는 데 새 개체를 사용한 경우 파일을 닫은 후 삭제해야 합니다. `Close` 설정 `m_hFile` 에 `CFile::hFileNull`입니다.

### <a name="example"></a>예제

[CFile::CFile](#cfile)에 대한 예제를 참조하십시오.

## <a name="cfileduplicate"></a><a name="duplicate"></a>C파일::D

지정된 파일에 `CFile` 대한 중복 개체를 생성합니다.

```
virtual CFile* Duplicate() const;
```

### <a name="return-value"></a>Return Value

중복 `CFile` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 함수는 C 런타임 함수와 `_dup`동일합니다.

## <a name="cfileflush"></a><a name="flush"></a>C파일 :: 플러시

파일 버퍼에 남아 있는 모든 데이터를 파일에 기록하도록 강제합니다.

```
virtual void Flush();
```

### <a name="remarks"></a>설명

사용해도 `Flush` 버퍼 플러시가 `CArchive` 보장되지 는 않습니다. 아카이브를 사용하는 경우 [CArchive::Flush를](../../mfc/reference/carchive-class.md#flush) 먼저 호출합니다.

### <a name="example"></a>예제

[CFile::SetFilePath](#setfilepath)에 대한 예제를 참조하십시오.

## <a name="cfilegetfilename"></a><a name="getfilename"></a>CFile::GetFile 이름

지정된 파일의 이름을 검색하려면 이 멤버 함수를 호출합니다.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Return Value

파일 이름입니다.

### <a name="remarks"></a>설명

예를 들어, 파일 `GetFileName` `c:\windows\write\myfile.wri`, 파일 이름, `myfile.wri`에 대한 메시지를 사용자에게 생성하기 위해 호출할 때 반환됩니다.

이름을 포함하여 파일의 전체 경로를 반환하려면 [GetFilePath](#getfilepath)를 호출합니다. 파일 ()의 `myfile`제목을 반환하려면 [GetFileTitle을](#getfiletitle)호출합니다.

### <a name="example"></a>예제

이 코드 조각은 SYSTEM을 엽니다. WINDOWS 디렉토리에 있는 INI 파일입니다. 이 예제에서 출력 아래에 표시된 이름과 경로 및 제목을 인쇄합니다.

[!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]

## <a name="cfilegetfilepath"></a><a name="getfilepath"></a>C파일::GetFile경로

지정된 파일의 전체 경로를 검색하려면 이 멤버 함수를 호출합니다.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Return Value

지정된 파일의 전체 경로입니다.

### <a name="remarks"></a>설명

예를 들어, 파일, 파일 `GetFilePath` `c:\windows\write\myfile.wri`경로에 `c:\windows\write\myfile.wri`대한 메시지를 사용자에게 생성하기 위해 호출할 때 반환됩니다.

파일`myfile.wri`()의 이름만 반환하려면 [GetFileName](#getfilename)을 호출합니다. 파일 ()의`myfile`제목을 반환하려면 [GetFileTitle을](#getfiletitle)호출합니다.

### <a name="example"></a>예제

[GetFileName](#getfilename)에 대한 예제를 참조하십시오.

## <a name="cfilegetfiletitle"></a><a name="getfiletitle"></a>C파일::GetFile타이틀

이 멤버 함수를 호출하여 파일의 파일 제목(표시 이름)을 검색합니다.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Return Value

기본 파일의 제목입니다.

### <a name="remarks"></a>설명

이 메서드는 [GetFileTitle](/windows/win32/api/commdlg/nf-commdlg-getfiletitlew) 파일의 제목을 검색 하도록 호출 합니다. 성공하면 메서드는 시스템에서 파일 이름을 사용자에게 표시하는 데 사용할 문자열을 반환합니다. 그렇지 않으면 메서드호출 [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) 기본 파일의 파일 이름(파일 확장명 포함)을 검색합니다. 즉, 파일 확장명이 반환된 파일 제목 문자열에 항상 포함되지는 않습니다. 자세한 내용은 Windows SDK의 [GetFileTitle](/windows/win32/api/commdlg/nf-commdlg-getfiletitlew) 및 [PathFindFileName을](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) 참조하십시오.

이름을 포함하여 파일의 전체 경로를 반환하려면 [GetFilePath](#getfilepath)를 호출합니다. 파일 이름만 반환하려면 [GetFileName](#getfilename)을 호출합니다.

### <a name="example"></a>예제

[GetFileName](#getfilename)에 대한 예제를 참조하십시오.

## <a name="cfilegetlength"></a><a name="getlength"></a>C파일::GetLength

파일의 현재 논리 길이를 바이트로 가져옵니다.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Return Value

파일의 길이입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]

## <a name="cfilegetposition"></a><a name="getposition"></a>C파일::GetPosition

나중에 `Seek`에 대한 호출에서 사용할 수 있는 파일 포인터의 현재 값을 가져옵니다.

```
virtual ULONGLONG GetPosition() const;
```

### <a name="return-value"></a>Return Value

파일 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]

## <a name="cfilegetstatus"></a><a name="getstatus"></a>C파일::GetStatus

이 메서드는 지정된 `CFile` 개체 인스턴스 또는 지정된 파일 경로와 관련된 상태 정보를 검색합니다.

```
BOOL GetStatus(CFileStatus& rStatus) const;

static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*r 상태 지정*<br/>
상태 정보를 수신하는 `CFileStatus` 사용자 제공 구조에 대한 참조입니다. 구조에 `CFileStatus` 다음 필드가 있습니다.

- `CTime m_ctime`파일을 만든 날짜 및 시간입니다.

- `CTime m_mtime`파일이 마지막으로 수정된 날짜 및 시간입니다.

- `CTime m_atime`파일을 마지막으로 읽기 위해 액세스한 날짜 및 시간입니다.

- `ULONGLONG m_size`DIR 명령에 의해 보고된 바이트별 파일의 논리적 크기입니다.

- `BYTE m_attribute`파일의 특성 바이트입니다.

- `char m_szFullName[_MAX_PATH]`Windows 문자 집합의 절대 파일 이름입니다.

*lpsz파일이름*<br/>
원하는 파일의 경로인 Windows 문자 집합의 문자열입니다. 경로는 상대적 또는 절대적이거나 네트워크 경로 이름을 포함할 수 있습니다.

*Ptm*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="return-value"></a>Return Value

TRUE 지정된 파일에 대한 상태 정보가 성공적으로 얻은 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

비정적 버전의 `GetStatus` 개체는 지정된 `CFile` 개체와 연결된 열린 파일의 상태 정보를 검색합니다.  정적 버전의 `GetStatus` 파일은 실제로 파일을 열지 않고 지정된 파일 경로에서 파일 상태를 가져옵니다. 이 버전은 파일의 존재 및 액세스 권한을 테스트하는 데 유용합니다.

구조체의 `m_attribute` `CFileStatus` 멤버는 파일 특성 집합을 참조합니다. 이 `CFile` 클래스는 파일 특성을 상징적으로 지정할 수 있도록 **특성** 열거 형을 제공합니다.

```
enum Attribute {
    normal =    0x00,
    readOnly =  0x01,
    hidden =    0x02,
    system =    0x04,
    volume =    0x08,
    directory = 0x10,
    archive =   0x20
    };
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#10](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_6.cpp)]

## <a name="cfilehfilenull"></a><a name="hfilenull"></a>C파일::hFileNull

개체에 대해 유효한 파일 핸들의 `CFile` 존재를 확인합니다.

```
static AFX_DATA const HANDLE hFileNull;
```

### <a name="remarks"></a>설명

이 상수는 개체에 `CFile` 유효한 파일 핸들이 있는지 확인하는 데 사용됩니다.

다음 예제에서는 이 작업을 보여 줍니다.

[!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]

## <a name="cfilelockrange"></a><a name="lockrange"></a>C파일 :: 잠금 범위

파일이 이미 잠겨 있는 경우 예외를 throw하면서 열려 있는 파일에서 바이트 범위를 잠급전지 않습니다.

```
virtual void LockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>매개 변수

*dwPos*<br/>
잠글 바이트 범위의 시작에 대한 바이트 오프셋입니다.

*dwCount*<br/>
잠글 범위의 바이트 수입니다.

### <a name="remarks"></a>설명

파일의 바이트를 잠그면 다른 프로세스에서 해당 바이트에 액세스할 수 없습니다. 파일의 둘 이상의 영역을 잠글 수 있지만 겹치는 영역은 허용되지 않습니다.

멤버 함수를 사용하여 `UnlockRange` 영역을 잠금 해제하는 경우 바이트 범위는 이전에 잠긴 영역과 정확히 일치해야 합니다. 함수는 `LockRange` 인접 영역을 병합하지 않습니다. 잠긴 두 영역이 인접한 경우 각 영역의 잠금을 별도로 해제해야 합니다.

> [!NOTE]
> -derived 클래스에는 이 `CMemFile`함수를 사용할 수 없습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

## <a name="cfilem_hfile"></a><a name="m_hfile"></a>C파일:m_hFile

열려 있는 파일에 대한 운영 체제 파일 핸들을 포함합니다.

```
HANDLE m_hFile;
```

### <a name="remarks"></a>설명

`m_hFile`는 UINT 형식의 공용 변수입니다. 여기에는 `CFile::hFileNull`핸들이 할당되지 않은 경우 운영 체제독립적인 빈 파일 표시기가 포함됩니다.

멤버의 `m_hFile` 의미는 파생 클래스에 따라 달라지므로 사용하지 않는 것이 좋습니다. `m_hFile`클래스의 비다형성 사용을 지원하기 위해 편의를 위해 공용 멤버가 됩니다.

## <a name="cfilem_ptm"></a><a name="m_ptm"></a>CFile:m_pTM

`CAtlTransactionManager` 개체에 대한 포인터입니다.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>설명

## <a name="cfileopen"></a><a name="open"></a>CFile::열기

오버로드되었습니다. `Open`기본 `CFile` 생성자와 함께 사용하도록 설계되었습니다.

```
virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*lpsz파일이름*<br/>
원하는 파일에 대한 경로를 포함하는 문자열입니다. 경로는 상대, 절대 또는 UNC(네트워크 이름)일 수 있습니다.

*n오픈 플래그*<br/>
파일의 공유 및 액세스 모드를 정의하는 UINT입니다. 파일을 열 때 수행할 작업을 지정합니다. bitwise-OR **(&#124;)** 연산자를 사용하여 옵션을 결합할 수 있습니다. 액세스 권한 1개와 공유 옵션 1개가 필요합니다. `modeCreate` 및 `modeNoInherit` 모드는 선택 사항입니다. 모드 옵션 목록은 [CFile 생성자(CFile](#cfile) 생성자)를 참조하십시오.

*pError*<br/>
실패한 작업의 상태를 수신하는 기존 파일 예외 개체에 대한 포인터입니다.

*Ptm*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="return-value"></a>Return Value

열기가 성공한 경우 비영; 그렇지 않으면 0. *pError* 매개 변수는 0이 반환되는 경우에만 의미가 있습니다.

### <a name="remarks"></a>설명

두 `Open` 함수는 오류가 정상적이고 예상되는 상태인 파일을 여는 "안전한" 메서드입니다.

`CFile` 생성자는 오류 조건에서 예외를 throw하지만 `Open` 오류 조건에 대해 FALSE를 반환합니다. `Open`그러나 오류를 설명하기 위해 [CFileException](../../mfc/reference/cfileexception-class.md) 개체를 초기화할 수 있습니다. *pError* 매개 변수를 제공하지 않거나 *pError에*대해 NULL을 `Open` 전달하는 경우 FALSE를 `CFileException`반환하고 을 throw하지 않습니다. 기존 `CFileException`에 대한 포인터를 전달하고 `Open` 오류가 발생하면 함수가 해당 오류를 설명하는 정보로 채워지습니다. `Open`두 경우 모두 예외를 throw하지 않습니다.

다음 표는 의 `Open`가능한 결과를 설명합니다.

|`pError`|오류가 발생했습니다.|반환 값|CFile예외 콘텐츠|
|--------------|------------------------|------------------|----------------------------|
|NULL|예|TRUE|해당 없음|
|ptr 을`CFileException`|예|TRUE|변경 안 됨|
|NULL|예|FALSE|해당 없음|
|ptr 을`CFileException`|예|FALSE|오류를 설명하기 위해 초기화|

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]

[!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]

## <a name="cfileoperator-handle"></a><a name="operator_handle"></a>CFile::연산자 핸들

이 연산자는 에 대한 `CFile` 예상 [ReadFileEx](/windows/win32/api/fileapi/nf-fileapi-readfileex) 및 [GetFileTime과](/windows/win32/api/fileapi/nf-fileapi-getfiletime) 같은 `HANDLE`함수에 개체에 핸들을 전달하려면 이 연산자가 사용됩니다.

```
operator HANDLE() const;
```

## <a name="cfileread"></a><a name="read"></a>C파일::읽기

`CFile` 개체와 연결된 파일에서 버퍼로 데이터를 읽습니다.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
파일에서 읽은 데이터를 수신하는 사용자 제공 버퍼에 대한 포인터입니다.

*nCount*<br/>
파일에서 읽을 최대 바이트 수입니다. 텍스트 모드 파일의 경우 캐리지 리턴 라인 피드 쌍은 단일 문자로 계산됩니다.

### <a name="return-value"></a>Return Value

버퍼로 전송된 바이트 수입니다. 모든 `CFile` 클래스의 경우 파일 끝에 도달한 경우 반환 값이 *nCount보다* 작을 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]

또 다른 예는 [CFile::Open](#open)을 참조하십시오.

## <a name="cfileremove"></a><a name="remove"></a>CFile::제거

이 정적 함수는 경로에 의해 지정된 파일을 삭제합니다.

```
static void PASCAL Remove(
    LPCTSTR lpszFileName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*lpsz파일이름*<br/>
원하는 파일의 경로인 문자열입니다. 경로는 상대적이거나 절대적일 수 있으며 네트워크 이름을 포함할 수 있습니다.

*Ptm*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="remarks"></a>설명

`Remove`디렉터리도 제거되지 않습니다.

멤버 `Remove` 함수는 연결된 파일이 열려 있거나 파일을 제거할 수 없는 경우 예외를 throw합니다. 이 함수는 DEL 명령과 동일합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]

## <a name="cfilerename"></a><a name="rename"></a>CFile::이름 바꾸기

이 정적 함수는 지정된 파일의 이름을 바꿉니다.

```
static void PASCAL Rename(
    LPCTSTR lpszOldName,
    LPCTSTR lpszNewName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszOldName*<br/>
이전 경로입니다.

*lpszNewName*<br/>
새 경로입니다.

*Ptm*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="remarks"></a>설명

디렉터리의 이름을 바꿀 수 없습니다. 이 함수는 REN 명령과 동일합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]

## <a name="cfileseek"></a><a name="seek"></a>C파일::검색

파일 포인터를 열린 파일의 위치를 바짝 바뜨습니다.

```
virtual ULONGLONG Seek(
LONGLONG lOff,
UINT nFrom);
```

### <a name="parameters"></a>매개 변수

*로프 (것)로프 (것)*<br/>
파일 포인터를 이동할 바이트 수입니다. 양수 값은 파일 포인터를 파일 끝쪽으로 이동합니다. 음수 값은 파일 포인터를 파일의 시작 부분쪽으로 이동합니다.

*nFrom*<br/>
구할 위치. 가능한 값은 비고 섹션을 참조하십시오.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 파일 포인터의 위치입니다. 그렇지 않으면 반환 값이 정의되지 않고 `CFileException` 예외에 대한 포인터가 throw됩니다.

### <a name="remarks"></a>설명

다음 표에는 *nFrom* 매개 변수에 대한 가능한 값이 나열됩니다.

|값|Description|
|-----------|-----------------|
|`CFile::begin`|파일의 시작 부터 검색합니다.|
|`CFile::current`|파일 포인터의 현재 위치에서 검색합니다.|
|`CFile::end`|파일 의 끝에서 찾습니다.|

파일이 열리면 파일 포인터가 파일의 시작 부분인 0에 배치됩니다.

파일 포인터를 파일 끝을 벗어난 위치로 설정할 수 있습니다. 이렇게 하면 파일에 쓸 때까지 파일 크기가 증가하지 않습니다.

이 메서드에 대 한 예외 처리기 는 예외가 처리 된 후 예외 개체를 삭제 해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]

## <a name="cfileseektobegin"></a><a name="seektobegin"></a>C파일::검색토비

파일 포인터의 값을 파일의 시작 부분으로 설정합니다.

```cpp
void SeekToBegin();
```

### <a name="remarks"></a>설명

`SeekToBegin()`은 `Seek( 0L, CFile::begin )`와 동등합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

## <a name="cfileseektoend"></a><a name="seektoend"></a>C파일::검색토엔드

파일 포인터의 값을 파일의 논리적 끝으로 설정합니다.

```
ULONGLONG SeekToEnd();
```

### <a name="return-value"></a>Return Value

파일의 길이(바이트)입니다.

### <a name="remarks"></a>설명

`SeekToEnd()`은 `CFile::Seek( 0L, CFile::end )`와 동등합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

## <a name="cfilesetfilepath"></a><a name="setfilepath"></a>C파일::SetFilePath

이 함수를 호출하여 파일의 경로를 지정합니다. 예를 들어 [CFile](../../mfc/reference/cfile-class.md) 개체가 생성될 때 파일 의 경로를 사용할 `SetFilePath` 수 없는 경우 파일을 제공하기 위해 호출합니다.

```
virtual void SetFilePath(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>매개 변수

*lpszNewName*<br/>
새 경로를 지정하는 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

> [!NOTE]
> `SetFilePath`파일을 열거나 파일을 만들지 않습니다. 단순히 개체를 `CFile` 경로 이름과 연결하여 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]

## <a name="cfilesetlength"></a><a name="setlength"></a>C파일::설정길이

이 함수를 호출하여 파일 길이를 변경합니다.

```
virtual void SetLength(ULONGLONG dwNewLen);
```

### <a name="parameters"></a>매개 변수

*dw뉴렌*<br/>
바이트로 파일의 원하는 길이입니다. 이 값은 파일의 현재 길이보다 크거나 작을 수 있습니다. 파일이 확장되거나 적절하게 잘립니다.

### <a name="remarks"></a>설명

> [!NOTE]
> 을 `CMemFile`사용하면 이 함수가 개체를 throw할 수 있습니다. `CMemoryException`

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]

## <a name="cfilesetstatus"></a><a name="setstatus"></a>CFile::설정 상태

이 파일 위치와 연결된 파일의 상태를 설정합니다.

```
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,
    const CFileStatus& status,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*lpsz파일이름*<br/>
원하는 파일의 경로인 문자열입니다. 경로는 상대적이거나 절대적일 수 있으며 네트워크 이름을 포함할 수 있습니다.

*상태*<br/>
새 상태 정보를 포함하는 버퍼입니다. 멤버 `GetStatus` 함수를 호출하여 `CFileStatus` 구조를 현재 값으로 미리 채운 다음 필요에 따라 변경합니다. 값이 0이면 해당 상태 항목이 업데이트되지 않습니다. 구조에 대한 설명은 [GetStatus](#getstatus) `CFileStatus` 멤버 함수를 참조하십시오.

*Ptm*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="remarks"></a>설명

시간을 설정하려면 *상태* `m_mtime` 필드를 수정합니다.

파일의 특성만 `SetStatus` 변경하려고 호출하고 파일 상태 구조의 `m_mtime` 멤버가 0이 아닌 경우 특성도 영향을 받을 수 있습니다(타임스탬프 변경은 특성에 부작용이 있을 수 있음). 파일의 특성만 변경하려면 먼저 파일 상태 구조의 `m_mtime` 멤버를 0으로 설정한 다음 을 `SetStatus`호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]

## <a name="cfileunlockrange"></a><a name="unlockrange"></a>C파일 ::잠금 해제 범위

열려 있는 파일에서 다양한 바이트를 잠금 해제합니다.

```
virtual void UnlockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>매개 변수

*dwPos*<br/>
잠금을 해제할 바이트 범위의 시작의 바이트 오프셋입니다.

*dwCount*<br/>
잠금을 해제할 범위의 바이트 수입니다.

### <a name="remarks"></a>설명

자세한 내용은 [LockRange](#lockrange) 멤버 함수설명을 참조하십시오.

> [!NOTE]
> -derived 클래스에는 `CMemFile`이 함수를 사용할 수 없습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

## <a name="cfilewrite"></a><a name="write"></a>CFile::쓰기

버퍼의 데이터를 `CFile` 개체와 연결된 파일에 씁니다.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
파일에 기록할 데이터를 포함하는 사용자 제공 버퍼에 대한 포인터입니다.

*nCount*<br/>
버퍼에서 전송할 바이트 수입니다. 텍스트 모드 파일의 경우 캐리지 리턴 라인 피드 쌍은 단일 문자로 계산됩니다.

### <a name="remarks"></a>설명

`Write`디스크 전체 조건을 포함한 여러 조건에 대한 응답으로 예외를 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]

또한 [CFile::CFile](#cfile) 및 [CFile::open](#open)에 대한 예제를 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 드로클리](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CStdioFile 클래스](../../mfc/reference/cstdiofile-class.md)<br/>
[CMemFile 클래스](../../mfc/reference/cmemfile-class.md)
