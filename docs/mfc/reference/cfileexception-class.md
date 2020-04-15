---
title: CFile예외 클래스
ms.date: 11/04/2016
f1_keywords:
- CFileException
- AFX/CFileException
- AFX/CFileException::CFileException
- AFX/CFileException::ErrnoToException
- AFX/CFileException::GetErrorMessage
- AFX/CFileException::OsErrorToException
- AFX/CFileException::ThrowErrno
- AFX/CFileException::ThrowOsError
- AFX/CFileException::m_cause
- AFX/CFileException::m_lOsError
- AFX/CFileException::m_strFileName
helpviewer_keywords:
- CFileException [MFC], CFileException
- CFileException [MFC], ErrnoToException
- CFileException [MFC], GetErrorMessage
- CFileException [MFC], OsErrorToException
- CFileException [MFC], ThrowErrno
- CFileException [MFC], ThrowOsError
- CFileException [MFC], m_cause
- CFileException [MFC], m_lOsError
- CFileException [MFC], m_strFileName
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
ms.openlocfilehash: 2d1025ca33d5641982ba52f1ac539db85df3bfd5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373886"
---
# <a name="cfileexception-class"></a>CFile예외 클래스

파일 관련 예외 상태를 나타냅니다.

## <a name="syntax"></a>구문

```
class CFileException : public CException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CFile예외::CFile예외](#cfileexception)|`CFileException` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CFile예외::ErrnoToException](#errnotoexception)|런타임 오류 번호에 해당하는 원인 코드를 반환합니다.|
|[CFile예외::GetErrorMessage](#geterrormessage)|예외를 설명하는 메시지를 검색합니다.|
|[CFile예외::OsErrorToException](#oserrortoexception)|운영 체제 오류 코드에 해당하는 원인 코드를 반환합니다.|
|[CFile예외::투척기](#throwerrno)|런타임 오류 번호를 기반으로 파일 예외를 throw합니다.|
|[CFile예외::throwOsError](#throwoserror)|운영 체제 오류 번호를 기반으로 파일 예외를 throw합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CFile예외:m_cause](#m_cause)|예외 원인에 해당하는 이식 가능한 코드를 포함합니다.|
|[CFile예외::m_lOsError](#m_loserror)|관련 운영 체제 오류 번호를 포함합니다.|
|[CFile예외:m_strFileName](#m_strfilename)|이 예외에 대 한 파일의 이름을 포함 합니다.|

## <a name="remarks"></a>설명

클래스에는 `CFileException` 이식 가능한 원인 코드와 운영 체제별 오류 번호를 포함하는 공용 데이터 멤버가 포함됩니다. 또한 클래스는 파일 예외를 throw하고 운영 체제 오류 및 C 런타임 오류모두에 대한 원인 코드를 반환하기 위한 정적 멤버 함수를 제공합니다.

`CFileException`개체는 `CFile` 멤버 함수및 파생 클래스의 멤버 함수에서 생성되고 throw됩니다. **CATCH** 식의 범위 내에서 이러한 개체에 액세스할 수 있습니다. 이식성의 경우 원인 코드만 사용하여 예외에 대한 이유를 가져옵니다. 예외에 대한 자세한 내용은 [MFC(예외 처리)](../../mfc/exception-handling-in-mfc.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CFileException`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cfileexceptioncfileexception"></a><a name="cfileexception"></a>CFile예외::CFile예외

`CFileException` 원인 코드와 운영 체제 코드를 개체에 저장하는 개체를 생성합니다.

```
CFileException(
    int cause = CFileException::none,
    LONG lOsError = -1,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>매개 변수

*원인*<br/>
예외의 원인을 나타내는 열거된 형식 변수입니다. 가능한 값 목록은 [CFileException:m_cause](#m_cause) 를 참조하십시오.

*로스에이슬*<br/>
사용 가능한 경우 예외에 대한 운영 체제별 이유입니다. *lOsError* 매개 변수는 *원인보다* 더 많은 정보를 제공합니다.

*lpszArchiveName*<br/>
예외를 일으키는 `CFile` 개체의 이름을 포함하는 문자열을 가리킵니다.

### <a name="remarks"></a>설명

이 생성자는 직접 사용하지 말고 전역 함수 [AfxThrowFileException을](exception-processing.md#afxthrowfileexception)호출합니다.

> [!NOTE]
> 변수 *lOsError는* 개체에만 `CFile` `CStdioFile` 적용됩니다. 클래스는 `CMemFile` 이 오류 코드를 처리하지 않습니다.

## <a name="cfileexceptionerrnotoexception"></a><a name="errnotoexception"></a>CFile예외::ErrnoToException

지정된 런타임 라이브러리 오류 값을 예인된 오류 값으로 `CFileException` 변환합니다.

```
static int PASCAL ErrnoToException(int nErrno);
```

### <a name="parameters"></a>매개 변수

*nErrno*<br/>
런타임에 정의된 정수 오류 코드에는 ERRNO 파일이 포함됩니다. H.

### <a name="return-value"></a>Return Value

지정된 런타임 라이브러리 오류 값에 해당하는 수임된 값입니다.

### <a name="remarks"></a>설명

가능한 나열된 값 목록은 [CFileException:m_cause](#m_cause) 를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]

## <a name="cfileexceptiongeterrormessage"></a><a name="geterrormessage"></a>CFile예외::GetErrorMessage

예외를 설명하는 텍스트를 검색합니다.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT nMaxError,
    PUINT pnHelpContext = NULL) const;
```

### <a name="parameters"></a>매개 변수

*lpsz오류*<br/>
【인, 아웃】 오류 메시지를 받는 버퍼에 대한 포인터입니다.

*nMaxError*<br/>
【인】 지정된 버퍼가 보유할 수 있는 최대 문자 수입니다. 여기에는 null 문자 종료가 포함됩니다.

*pn도움말컨텍스트*<br/>
【인, 아웃】 도움말 컨텍스트 ID를 받는 서명되지 않은 정수에 대한 포인터입니다. 이 `NULL`경우 ID가 반환되지 않습니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

지정된 버퍼가 너무 작으면 오류 메시지가 잘립니다.

### <a name="example"></a>예제

다음 예에서는 `CFileException::GetErrorMessage`를 사용합니다.

[!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]

## <a name="cfileexceptionm_cause"></a><a name="m_cause"></a>CFile예외:m_cause

`CFileException` 열거형 형식으로 정의되는 값을 포함합니다.

```
int m_cause;
```

### <a name="remarks"></a>설명

이 데이터 멤버는 **int**형식의 공용 변수입니다. 열거자와 그 의미는 다음과 같습니다.

- `CFileException::none`0: 오류가 발생하지 않았습니다.

- `CFileException::genericException`1: 지정되지 않은 오류가 발생했습니다.

- `CFileException::fileNotFound`2: 파일을 찾을 수 없습니다.

- `CFileException::badPath`3: 경로의 전체 또는 일부가 유효하지 않습니다.

- `CFileException::tooManyOpenFiles`4: 열린 파일의 허용 수를 초과했습니다.

- `CFileException::accessDenied`5: 파일에 액세스할 수 없습니다.

- `CFileException::invalidFile`6: 잘못된 파일 핸들을 사용하려고 했습니다.

- `CFileException::removeCurrentDir`7: 현재 작업 디렉토리를 제거할 수 없습니다.

- `CFileException::directoryFull`8: 더 이상 디렉터리 항목이 없습니다.

- `CFileException::badSeek`9 : 파일 포인터를 설정하려고 하는 중 오류가 발생했습니다.

- `CFileException::hardIO`10: 하드웨어 오류가 발생했습니다.

- `CFileException::sharingViolation`11: 공유. EXE가 로드되지 않았거나 공유 영역이 잠겼습니다.

- `CFileException::lockViolation`12: 이미 잠긴 영역을 잠그려는 시도가 있었습니다.

- `CFileException::diskFull`14: 디스크가 가득 찼습니다.

- `CFileException::endOfFile`15: 파일의 끝에 도달했습니다.

    > [!NOTE]
    >  이러한 `CFileException` 원인 열거자는 `CArchiveException` 원인 열거자와는 다릅니다.

    > [!NOTE]
    > `CArchiveException::generic`는 사용되지 않습니다. 대신 `genericException`를 사용하세요. **제네릭이** 응용 프로그램에서 사용되고 /clr로 빌드된 경우 결과 구문 오류를 해독하기가 쉽지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]

## <a name="cfileexceptionm_loserror"></a><a name="m_loserror"></a>CFile예외::m_lOsError

이 예외에 대한 운영 체제 오류 코드를 포함합니다.

```
LONG m_lOsError;
```

### <a name="remarks"></a>설명

오류 코드 목록은 운영 체제 기술 설명서를 참조하십시오. 이 데이터 멤버는 LONG 형식의 공용 변수입니다.

## <a name="cfileexceptionm_strfilename"></a><a name="m_strfilename"></a>CFile예외:m_strFileName

이 예외 조건에 대한 파일의 이름을 포함합니다.

```
CString m_strFileName;
```

## <a name="cfileexceptionoserrortoexception"></a><a name="oserrortoexception"></a>CFile예외::OsErrorToException

지정된 *lOsError* 값에 해당하는 열거형기를 반환합니다. 오류 코드를 알 수 없는 경우 `CFileException::generic`함수가 반환됩니다.

```
static int PASCAL OsErrorToException(LONG lOsError);
```

### <a name="parameters"></a>매개 변수

*로스에이슬*<br/>
운영 체제별 오류 코드입니다.

### <a name="return-value"></a>Return Value

지정된 운영 체제 오류 값에 해당하는 수임된 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]

## <a name="cfileexceptionthrowerrno"></a><a name="throwerrno"></a>CFile예외::투척기

지정된 `CFileException` *nErrno* 값에 해당하는 개체를 생성한 다음 예외를 throw합니다.

```
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>매개 변수

*nErrno*<br/>
런타임에 정의된 정수 오류 코드에는 ERRNO 파일이 포함됩니다. H.

*lpsz파일이름*<br/>
가능한 경우 예외를 일으킨 파일의 이름이 포함된 문자열에 대한 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]

## <a name="cfileexceptionthrowoserror"></a><a name="throwoserror"></a>CFile예외::throwOsError

지정된 `CFileException` *lOsError* 값에 해당하는 값을 throw합니다. 오류 코드를 알 수 없는 경우 함수는 `CFileException::generic`로 코딩된 예외를 throw합니다.

```
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>매개 변수

*로스에이슬*<br/>
운영 체제별 오류 코드입니다.

*lpsz파일이름*<br/>
가능한 경우 예외를 일으킨 파일의 이름이 포함된 문자열에 대한 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]

## <a name="see-also"></a>참고 항목

[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[예외 처리](../../mfc/reference/exception-processing.md)
