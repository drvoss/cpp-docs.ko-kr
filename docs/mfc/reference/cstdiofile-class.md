---
title: CStdioFile 클래스
ms.date: 08/29/2019
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
helpviewer_keywords:
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
ms.openlocfilehash: 80ee65aa339a38b3d8434bc4c7cb977e263f037b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366010"
---
# <a name="cstdiofile-class"></a>CStdioFile 클래스

런타임 함수 [fopen에서](../../c-runtime-library/reference/fopen-wfopen.md)열리는 C 런타임 스트림 파일을 나타냅니다.

## <a name="syntax"></a>구문

```
class CStdioFile : public CFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CStdioFile::CStdioFile](#cstdiofile)|경로 또는 `CStdioFile` 파일 포인터에서 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CStdioFile::열기](#open)|오버로드되었습니다. Open은 기본 `CStdioFile` 생성자(CFile::Open [CFile::Open](../../mfc/reference/cfile-class.md#open)재정의)와 함께 사용하도록 설계되었습니다.|
|[CStdioFile::읽기 문자열](#readstring)|한 줄의 텍스트를 읽습니다.|
|[CStdioFile::검색](#seek)|현재 파일 포인터의 위치를 정합니다.|
|[CStdioFile::쓰기 문자열](#writestring)|한 줄의 텍스트를 씁니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CStdioFile::m_pStream](#m_pstream)|열려 있는 파일에 대한 포인터를 포함합니다.|

## <a name="remarks"></a>설명

스트림 파일은 버퍼링되며 텍스트 모드(기본값) 또는 이진 모드에서 열 수 있습니다.

텍스트 모드는 캐리지 리턴 라인 피드 쌍에 대한 특수 처리를 제공합니다. 텍스트 모드 `CStdioFile` 개체에 줄 바수(줄 바임) 문자(0x0A)를 작성하면 바이트 쌍(0x0D, 0x0A)이 파일로 전송됩니다. 읽으면 바이트 쌍(0x0D, 0x0A)이 단일 0x0A 바이트로 변환됩니다.

[CFile](../../mfc/reference/cfile-class.md) 함수 [중복](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange)및 [UnlockRange에](../../mfc/reference/cfile-class.md#unlockrange) 대 한 `CStdioFile`지원 되지 않습니다.

에서 `CStdioFile`이러한 함수를 호출하면 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)을 받게 됩니다.

사용에 `CStdioFile`대한 자세한 내용은 *런타임 라이브러리 참조의* [MFC](../../mfc/files-in-mfc.md) 및 [파일 처리문서](../../c-runtime-library/file-handling.md) 파일을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CStdioFile`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cstdiofilecstdiofile"></a><a name="cstdiofile"></a>CStdioFile::CStdioFile

`CStdioFile` 개체를 생성하고 초기화합니다.

```
CStdioFile();
CStdioFile(CAtlTransactionManager* pTM);
CStdioFile(FILE* pOpenStream);

CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags);

CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>매개 변수

*pOpenStream*<br/>
C 런타임 함수 [fopen에](../../c-runtime-library/reference/fopen-wfopen.md)대한 호출로 반환된 파일 포인터를 지정합니다.

*lpsz파일이름*<br/>
원하는 파일의 경로인 문자열을 지정합니다. 경로는 상대적이거나 절대적일 수 있습니다.

*n오픈 플래그*<br/>
파일 생성, 파일 공유 및 파일 액세스 모드에 대한 옵션을 지정합니다. 비트별 OR () **|** 연산자를 사용하여 여러 옵션을 지정할 수 있습니다.

하나의 파일 액세스 모드 옵션이 필요합니다. 다른 모드는 선택 사항입니다. 모드 옵션 및 기타 플래그 목록은 [CFile::CFile을](../../mfc/reference/cfile-class.md#cfile) 참조하십시오. MFC 버전 3.0 이상에서는 공유 플래그가 허용됩니다.

*Ptm*<br/>
CAtlTransactionManager 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

기본 생성자는 `CStdioFile` 개체에 파일을 첨부하지 않습니다. 이 생성기를 사용하는 경우 메서드를 `CStdioFile::Open` 사용하여 파일을 열고 개체에 `CStdioFile` 연결해야 합니다.

단일 매개 변수 생성자는 열린 파일 스트림을 개체에 `CStdioFile` 연결합니다. 허용된 포인터 값에는 미리 정의된 입력/출력 파일 포인터 *stdin,* *stdout*또는 *stderr*가 포함됩니다.

2매개 변수 생성자는 `CStdioFile` 개체를 만들고 지정된 경로로 해당 파일을 엽니다.

*pOpenStream* 또는 *lpszFileName에*대해 NULL을 전달하는 경우 `CInvalidArgException*`생성자는 을 throw합니다.

파일을 열거나 만들 수 없는 경우 생성자는 `CFileException*`을 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]

## <a name="cstdiofilem_pstream"></a><a name="m_pstream"></a>CStdioFile::m_pStream

데이터 `m_pStream` 멤버는 C 런타임 함수에서 `fopen`반환되는 열린 파일에 대한 포인터입니다.

```
FILE* m_pStream;
```

### <a name="remarks"></a>설명

파일이 열리거나 닫혀 본 적이 없는 경우 NULL입니다.

## <a name="cstdiofileopen"></a><a name="open"></a>CStdioFile::열기

오버로드되었습니다. Open은 기본 `CStdioFile` 생성자에서 사용하도록 설계되었습니다.

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
원하는 파일의 경로인 문자열입니다. 경로는 상대적이거나 절대적일 수 있습니다.

*n오픈 플래그*<br/>
공유 및 액세스 모드. 파일을 열 때 수행할 작업을 지정합니다. 비트와이즈 OR(&#124;) 연산자를 사용하여 옵션을 결합할 수 있습니다. 액세스 권한 1개와 공유 옵션 1개가 필요합니다. 모드만들기 및 모드NoInherit 모드는 선택 사항입니다.

*pError*<br/>
실패한 작업의 상태를 수신하는 기존 파일 예외 개체에 대한 포인터입니다.

*Ptm*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cstdiofilereadstring"></a><a name="readstring"></a>CStdioFile::읽기 문자열

`CStdioFile` 개체와 연결된 파일에서 *nMax-1*문자의 한계까지 텍스트 데이터를 버퍼로 읽습니다.

```
virtual LPTSTR ReadString(
    LPTSTR lpsz,
    UINT nMax);

virtual BOOL ReadString(CString& rString);
```

### <a name="parameters"></a>매개 변수

*lpsz*<br/>
null 종료된 텍스트 문자열을 수신할 사용자 제공 버퍼에 대한 포인터를 지정합니다.

*nMax*<br/>
null 문자 종료를 계산하지 않고 읽을 최대 문자 수를 지정합니다.

*rString*<br/>
함수가 `CString` 반환될 때 문자열을 포함하는 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

텍스트 데이터가 포함된 버퍼에 대한 포인터입니다. 데이터를 읽지 않고 파일 끝에 도달한 경우 NULL; 또는 부울경우 데이터를 읽지 않고 파일 끝에 도달한 경우 FALSE가 표시됩니다.

### <a name="remarks"></a>설명

읽기는 첫 번째 줄 바인 문자에 의해 중지됩니다. 이 경우 *nMax*-1 문자보다 적은 문자를 읽은 경우 줄 바운더링 문자가 버퍼에 저장됩니다. null 문자('\0')는 두 경우 모두 추가됩니다.

[CFile::Read는](../../mfc/reference/cfile-class.md#read) 텍스트 모드 입력에도 사용할 수 있지만 캐리지 리턴 라인 피드 쌍에서는 종료되지 않습니다.

> [!NOTE]
> 이 `CString` 함수의 버전은 있는 `'\n'` 경우를 제거합니다. LPTSTR 버전은 그렇지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]

## <a name="cstdiofileseek"></a><a name="seek"></a>CStdioFile::검색

이전에 열린 파일에서 포인터의 위치를 바하십시오.

```
virtual ULONGLONG Seek(
    LONGLONG lOff,
    UINT nFrom);
```

### <a name="parameters"></a>매개 변수

*로프 (것)로프 (것)*<br/>
포인터를 이동할 바이트 수입니다.

*nFrom*<br/>
포인터 이동 모드. 다음 값 중 하나여야 합니다.

- `CFile::begin`: 파일 포인터 *lOff* 바이트를 파일의 시작 부분에서 앞으로 이동합니다.

- `CFile::current`: 파일 포인터 *lOff* 바이트를 파일의 현재 위치에서 이동합니다.

- `CFile::end`: 파일 포인터 *lOff* 바이트를 파일 끝에서 이동합니다. *lOff는* 기존 파일을 검색하려면 음수여야 합니다. 양수 값은 파일의 끝을 지나추구합니다.

### <a name="return-value"></a>Return Value

요청된 위치가 합법적인 `Seek` 경우 파일의 시작 부분에서 새 바이트 오프셋을 반환합니다. 그렇지 않으면 반환 값이 정의되지 `CFileException` 않고 개체가 throw됩니다.

### <a name="remarks"></a>설명

이 `Seek` 함수는 포인터를 지정된 양또는 상대적으로 이동하여 파일 내용에 임의로 액세스할 수 있도록 합니다. 검색 하는 동안 실제로 데이터를 읽을 수 없습니다. 요청된 위치가 파일 크기보다 크면 파일 길이가 해당 위치로 확장되고 예외가 throw되지 않습니다.

파일이 열리면 파일 포인터는 파일의 시작 부분인 오프셋 0에 배치됩니다.

이 `Seek` 구현은 CRT(런타임 라이브러리) 함수를 `fseek`기반으로 합니다. 텍스트 모드에서 열리는 스트림의 `Seek` 사용에는 몇 가지 제한이 있습니다. 자세한 내용은 [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)를 참조하십시오.

### <a name="example"></a>예제

다음 예제에서는 파일의 `Seek` 시작 부분에서 포인터 1000 바이트를 `cfile` 이동 하는 데 사용 하는 방법을 보여 주어 있습니다. 데이터를 `Seek` 읽지 않으므로 나중에 [CStdioFile:ReadString을](#readstring) 호출하여 데이터를 읽습니다.

[!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]

## <a name="cstdiofilewritestring"></a><a name="writestring"></a>CStdioFile::쓰기 문자열

버퍼의 데이터를 `CStdioFile` 개체와 연결된 파일에 씁니다.

```
virtual void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>매개 변수

*lpsz*<br/>
null 종료 된 문자열을 포함 하는 버퍼에 대 한 포인터를 지정 합니다.

### <a name="remarks"></a>설명

null 문자 () `\0`종료는 파일에 기록되지 않습니다. 이 메서드는 파일캐리지 반환 줄 피드 쌍으로 *파일에 lpsz의* 줄 바선을 씁니다.

null-종료되지 않은 데이터를 파일에 쓰려면 또는 `CStdioFile::Write` [CFile::Write](../../mfc/reference/cfile-class.md#write)를 사용합니다.

이 메서드는 `CInvalidArgException*` *lpsz* 매개 변수에 대 한 NULL을 지정 하는 경우를 throw 합니다.

이 메서드는 `CFileException*` 파일 시스템 오류에 대 한 응답을 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]

## <a name="see-also"></a>참고 항목

[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[C파일::D](../../mfc/reference/cfile-class.md#duplicate)<br/>
[C파일 :: 잠금 범위](../../mfc/reference/cfile-class.md#lockrange)<br/>
[C파일 ::잠금 해제 범위](../../mfc/reference/cfile-class.md#unlockrange)<br/>
[CNot지원 예외 클래스](../../mfc/reference/cnotsupportedexception-class.md)
