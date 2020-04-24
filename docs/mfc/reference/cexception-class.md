---
title: CException 클래스
ms.date: 11/04/2016
f1_keywords:
- CException
- AFX/CException
- AFX/CException::CException
- AFX/CException::Delete
- AFX/CException::ReportError
helpviewer_keywords:
- CException [MFC], CException
- CException [MFC], Delete
- CException [MFC], ReportError
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
ms.openlocfilehash: 93901f6f92ee79bd893b2ec0d1e341e77749d951
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753185"
---
# <a name="cexception-class"></a>CException 클래스

MFC 라이브러리의 모든 예외에 대한 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE CException : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C예외::C예외](#cexception)|`CException` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C예외::D](#delete)|개체를 `CException` 삭제합니다.|
|[C예외::보고서오류](#reporterror)|메시지 상자에 오류 메시지를 사용자에게 보고합니다.|

## <a name="remarks"></a>설명

추상 기본 클래스이기 `CException` 때문에 `CException` 개체를 직접 만들 수 없습니다. 파생 된 클래스의 개체를 만들어야 합니다. 고유한 `CException`스타일 클래스를 만들어야 하는 경우 위에 나열된 파생 클래스 중 하나를 모델로 사용합니다. 파생 클래스도 을 사용하는지 `IMPLEMENT_DYNAMIC`확인합니다.

파생 클래스와 해당 설명은 다음과 같습니다.

|||
|-|-|
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|리소스에 중요한 MFC 예외에 대한 기본 클래스|
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|잘못된 인수 예외 조건|
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|메모리 부족 예외|
|[CNot지원 예외](../../mfc/reference/cnotsupportedexception-class.md)|지원되지 않는 작업 요청|
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|아카이브별 예외|
|[CFileException](../../mfc/reference/cfileexception-class.md)|파일별 예외|
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows 리소스를 찾을 수 없거나 삐걱거리지 않음|
|[COleException](../../mfc/reference/coleexception-class.md)|OLE 예외|
|[CDBException](../../mfc/reference/cdbexception-class.md)|데이터베이스 예외(즉, 개방형 데이터베이스 연결을 기반으로 하는 MFC 데이터베이스 클래스에 대해 발생하는 예외 조건)|
|[올레디스패치예외](../../mfc/reference/coledispatchexception-class.md)|OLE 디스패치(자동화) 예외|
|[CUserException](../../mfc/reference/cuserexception-class.md)|리소스를 찾을 수 없다는 것을 나타내는 예외|
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|데이터 액세스 개체 예외(즉, DAO 클래스에 대해 발생하는 예외 조건)|
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|인터넷 예외(즉, 인터넷 클래스에 대해 발생하는 예외 조건).|

이러한 예외는 [throw](exception-processing.md#throw), [THROW_LAST,](exception-processing.md#throw_last) [시도](exception-processing.md#try), [catch](exception-processing.md#catch), [and_catch](exception-processing.md#and_catch)및 [end_catch](exception-processing.md#end_catch) 매크로와 함께 사용됩니다. 예외에 대한 자세한 내용은 [예외 처리를](exception-processing.md)참조하거나 [MFC(예외 처리)](../exception-handling-in-mfc.md)문서를 참조하십시오.

특정 예외를 catch하려면 적절한 파생 클래스를 사용합니다. 모든 유형의 예외를 catch하려면 을 사용한 `CException`다음 [CObject::IsKindOf를](cobject-class.md#iskindof) 사용하여 -derive된 클래스를 `CException`구분합니다. 동적 `CObject::IsKindOf` 형식 검사를 이용하기 위해 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) 매크로로 선언된 클래스에만 작동합니다. 만드는 `CException`모든 파생 클래스도 매크로를 `IMPLEMENT_DYNAMIC` 사용해야 합니다.

[GetErrorMessage](cfileexception-class.md#geterrormessage) 또는 [ReportError,](#reporterror)파생 된 클래스 중 `CException`에서 작동 하는 두 멤버 함수를 호출 하 여 사용자에 게 예외에 대 한 세부 정보를 보고할 수 있습니다.

매크로 중 하나에 의해 예외가 발견되면 `CException` 개체가 자동으로 삭제됩니다. 직접 삭제하지 마십시오. **catch** 키워드를 사용하여 예외가 발견되면 자동으로 삭제되지 않습니다. 소멸 개체를 삭제하는 시기에 대한 자세한 내용은 [MFC(예외 처리)](../exception-handling-in-mfc.md) 문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](cobject-class.md)

`CException`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cexceptioncexception"></a><a name="cexception"></a>C예외::C예외

이 멤버 함수는 `CException` 개체를 생성합니다.

```
explicit CException(BOOL bAutoDelete);
```

### <a name="parameters"></a>매개 변수

*b_AutoDelete*<br/>
`CException` 개체에 대한 메모리가 힙에 할당된 경우 TRUE를 지정합니다. 이렇게 하면 `CException` `Delete` 멤버 함수가 호출되어 예외를 삭제할 때 개체가 삭제됩니다. 개체가 `CException` 스택에 있거나 전역 개체인 경우 FALSE를 지정합니다. 이 경우 멤버 `CException` 함수가 호출될 `Delete` 때 개체가 삭제되지 않습니다.

### <a name="remarks"></a>설명

일반적으로 이 생성자(생성자)를 직접 호출할 필요가 없습니다. 예외를 throw 하는 함수는 -derived `CException`클래스의 인스턴스를 만들고 해당 생성기를 호출하거나 [AfxThrowFileException과](exception-processing.md#afxthrowfileexception)같은 MFC throw 함수 중 하나를 사용하여 미리 정의된 형식을 throw해야 합니다. 이 설명서는 완전성을 위해서만 제공됩니다.

## <a name="cexceptiondelete"></a><a name="delete"></a>C예외::D

이 함수는 개체가 `CException` 힙에 만들어졌는지 확인하고, 이 경우 개체의 **delete** 연산자호출합니다.

```cpp
void Delete();
```

### <a name="remarks"></a>설명

개체를 삭제할 `CException` 때 멤버 `Delete` 함수를 사용하여 예외를 삭제합니다. 개체가 전역 개체이거나 스택에 만들어졌기 때문에 delete 연산자는 직접 사용하지 마십시오. **delete** `CException`

객체를 생성할 때 개체를 삭제할지 여부를 지정할 수 있습니다. 자세한 내용은 [CException:CException](#cexception)을 참조하십시오.

C ++ `Delete` **try**- **catch** 메커니즘을 사용하는 경우에만 호출하면됩니다. MFC 매크로 **TRY** 및 **CATCH를**사용하는 경우 이러한 매크로가 자동으로 이 함수를 호출합니다.

### <a name="example"></a>예제

```cpp
CFile* pFile = NULL;
// Constructing a CFile object with this override may throw
// a CFile exception, and won't throw any other exceptions.
// Calling CString::Format() may throw a CMemoryException,
// so we have a catch block for such exceptions, too. Any
// other exception types this function throws will be
// routed to the calling function.
// Note that this example performs the same actions as the
// example for CATCH, but uses C++ try/catch syntax instead
// of using the MFC TRY/CATCH macros. This sample must use
// CException::Delete() to delete the exception objects
// before closing the catch block, while the CATCH example
// implicitly performs the deletion via the macros.
try
{
   pFile = new CFile(_T("C:\\WINDOWS\\SYSTEM.INI"),
      CFile::modeRead | CFile::shareDenyNone);
   ULONGLONG ullLength = pFile->GetLength();
   CString str;
   str.Format(_T("Your SYSTEM.INI file is %u bytes long."), ullLength);
   AfxMessageBox(str);
}
catch(CFileException* pEx)
{
   // Simply show an error message to the user.
   pEx->ReportError();
   pEx->Delete();
}
catch(CMemoryException* pEx)
{
   // We can't recover from this memory exception, so we'll
   // just terminate the app without any cleanup. Normally, an
   // an application should do everything it possibly can to
   // clean up properly and _not_ call AfxAbort().
   pEx->Delete();
   AfxAbort();
}
// If an exception occurrs in the CFile constructor,
// the language will free the memory allocated by new
// and will not complete the assignment to pFile.
// Thus, our clean-up code needs to test for NULL.
if (pFile != NULL)
{
   pFile->Close();
   delete pFile;
}
```

## <a name="cexceptionreporterror"></a><a name="reporterror"></a>C예외::보고서오류

이 멤버 함수를 호출하여 메시지 상자의 오류 텍스트를 사용자에게 보고합니다.

```
virtual int ReportError(
    UINT nType = MB_OK,
    UINT nMessageID = 0);
```

### <a name="parameters"></a>매개 변수

*nType*<br/>
메시지 상자의 스타일을 지정합니다. [메시지 상자 스타일의](styles-used-by-mfc.md#message-box-styles) 조합을 상자에 적용합니다. 이 매개 변수를 지정하지 않으면 기본값이 MB_OK.

*nMessageID*<br/>
예외 개체에 오류 메시지가 없는 경우 표시할 메시지의 리소스 ID(문자열 테이블 항목)를 지정합니다. 0이면 "오류 메시지를 사용할 수 없음"이라는 메시지가 표시됩니다.

### <a name="return-value"></a>Return Value

값; `AfxMessageBox` 그렇지 않으면 0메시지 상자를 표시할 메모리가 충분하지 않은 경우. 가능한 반환 값은 [AfxMessageBox를](cstring-formatting-and-message-box-display.md#afxmessagebox) 참조하십시오.

### <a name="example"></a>예제

다음은 `CException::ReportError`의 사용 예입니다. 또 다른 예는 [CATCH](exception-processing.md#catch)에 대한 예제를 참조하십시오.

```cpp
CFile fileInput;
CFileException ex;

// try to open a file for reading.
// The file will certainly not
// exist because there are too many explicit
// directories in the name.

// if the call to Open() fails, ex will be
// initialized with exception
// information.  the call to ex.ReportError() will
// display an appropriate
// error message to the user, such as
// "\Too\Many\Bad\Dirs.DAT contains an
// invalid path."  The error message text will be
// appropriate for the
// file name and error condition.

if (!fileInput.Open(_T("\\Too\\Many\\Bad\\Dirs.DAT"), CFile::modeRead, &ex))
{
  ex.ReportError();
}
else
{
  // the file was opened, so do whatever work
  // with fileInput we were planning...

  fileInput.Close();
}
```

## <a name="see-also"></a>참조

[CObject 클래스](cobject-class.md)<br/>
[계층 구조 차트](../hierarchy-chart.md)<br/>
[예외 처리](exception-processing.md)<br/>
[어떻게 합니까: 사용자 지정 예외 클래스 를 직접 만듭니다.](https://go.microsoft.com/fwlink/p/?linkid=128045)
