---
title: CArchive예외 클래스
ms.date: 11/04/2016
f1_keywords:
- CArchiveException
- AFX/CArchiveException
- AFX/CArchiveException::CArchiveException
- AFX/CArchiveException::m_cause
- AFX/CArchiveException::m_strFileName
helpviewer_keywords:
- CArchiveException [MFC], CArchiveException
- CArchiveException [MFC], m_cause
- CArchiveException [MFC], m_strFileName
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
ms.openlocfilehash: ad2a9d8c5b4466a04b5a88fcce7679911bf1b81a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377008"
---
# <a name="carchiveexception-class"></a>CArchive예외 클래스

직렬화 예외 조건을 나타냅니다.

## <a name="syntax"></a>구문

```
class CArchiveException : public CException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C보관예외::C보관예외](#carchiveexception)|`CArchiveException` 개체를 생성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C아카이브예외::m_cause](#m_cause)|예외 원인을 나타냅니다.|
|[C아카이브예외::m_strFileName](#m_strfilename)|이 예외 조건에 대 한 파일의 이름을 지정 합니다.|

## <a name="remarks"></a>설명

클래스에는 `CArchiveException` 예외의 원인을 나타내는 공용 데이터 멤버가 포함됩니다.

`CArchiveException`개체는 [CArchive](../../mfc/reference/carchive-class.md) 멤버 함수 내에서 생성되고 throw됩니다. **CATCH** 식의 범위 내에서 이러한 개체에 액세스할 수 있습니다. 원인 코드는 운영 체제와 독립적입니다. 예외 처리에 대한 자세한 내용은 [예외 처리(MFC)를](../../mfc/exception-handling-in-mfc.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CArchiveException`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="carchiveexceptioncarchiveexception"></a><a name="carchiveexception"></a>C보관예외::C보관예외

개체에 `CArchiveException` *원인* 값을 저장 하는 개체를 생성 합니다.

```
CArchiveException(
    int cause = CArchiveException::none,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>매개 변수

*원인*<br/>
예외의 원인을 나타내는 열거된 형식 변수입니다. 열거형 자 목록은 [m_cause](#m_cause) 데이터 멤버를 참조하십시오.

*lpszArchiveName*<br/>
예외를 일으키는 `CArchive` 개체의 이름을 포함하는 문자열을 가리킵니다.

### <a name="remarks"></a>설명

힙에 개체를 `CArchiveException` 만들고 직접 throw하거나 전역 함수 [AfxThrowArchiveException에서](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) 처리할 수 있습니다.

이 생성자는 직접 사용하지 마십시오. 대신 전역 함수를 `AfxThrowArchiveException`호출합니다.

## <a name="carchiveexceptionm_cause"></a><a name="m_cause"></a>C아카이브예외::m_cause

예외의 원인을 지정합니다.

```
int m_cause;
```

### <a name="remarks"></a>설명

이 데이터 멤버는 **int**형식의 공용 변수입니다. 해당 값은 확장된 형식에 `CArchiveException` 의해 정의됩니다. 아래에 열거자와 해당 의미가 나와 있습니다.

- `CArchiveException::none`오류가 발생하지 않았습니다.

- `CArchiveException::genericException`지정되지 않은 오류입니다.

- `CArchiveException::readOnly`로딩을 위해 열린 아카이브에 쓰려고 했습니다.

- `CArchiveException::endOfFile`개체를 읽는 동안 파일 끝에 도달했습니다.

- `CArchiveException::writeOnly`보관을 위해 열린 아카이브에서 읽으려고 했습니다.

- `CArchiveException::badIndex`잘못된 파일 형식입니다.

- `CArchiveException::badClass`개체를 잘못된 형식의 개체로 읽으려고 했습니다.

- `CArchiveException::badSchema`클래스의 다른 버전으로 개체를 읽으려고 했습니다.

    > [!NOTE]
    >  이러한 `CArchiveException` 원인 열거자는 `CFileException` 원인 열거자와는 다릅니다.

    > [!NOTE]
    > `CArchiveException::generic`는 사용되지 않습니다. 대신 `genericException`를 사용하세요. **제네릭이** 응용 프로그램에서 사용되고 /clr로 빌드된 경우 해독하기 쉽지 않은 구문 오류가 있습니다.

## <a name="carchiveexceptionm_strfilename"></a><a name="m_strfilename"></a>C아카이브예외::m_strFileName

이 예외 조건에 대 한 파일의 이름을 지정 합니다.

```
CString m_strFileName;
```

## <a name="see-also"></a>참고 항목

[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CArchive 클래스](../../mfc/reference/carchive-class.md)<br/>
[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)<br/>
[예외 처리](../../mfc/reference/exception-processing.md)
