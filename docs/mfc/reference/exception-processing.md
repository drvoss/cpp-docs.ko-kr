---
title: 예외 처리
ms.date: 11/04/2016
helpviewer_keywords:
- macros [MFC], exception handling
- DAO (Data Access Objects), exceptions [MFC]
- OLE exceptions [MFC], MFC functions
- exceptions [MFC], processing
- exception macros [MFC]
- termination functions, MFC
- MFC, exceptions
- exceptions [MFC], MFC throwing functions
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
ms.openlocfilehash: bdf9dee88c29621bdc77c83d2633d93b4b9d10a7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751607"
---
# <a name="exception-processing"></a>예외 처리

프로그램이 실행되면 "예외"라는 여러 가지 비정상적인 조건과 오류가 발생할 수 있습니다. 여기에는 메모리 부족, 리소스 할당 오류 및 파일 찾기 실패가 포함될 수 있습니다.

Microsoft 재단 클래스 라이브러리는 C++에 대한 ANSI 표준 위원회에서 제안한 것을 따라 밀접하게 모델링된 예외 처리 체계를 사용합니다. 비정상적인 상황이 발생할 수 있는 함수를 호출하기 전에 예외 처리기를 설정해야 합니다. 함수에 비정상적인 조건이 발생 하면 예외를 throw 하 고 컨트롤은 예외 처리기에 전달 됩니다.

Microsoft Foundation 클래스 라이브러리에 포함된 여러 매크로에서 예외 처리기가 설정됩니다. 다른 여러 전역 함수는 특수한 예외를 throw하고 필요한 경우 프로그램을 종료하는 데 도움이 됩니다. 이러한 매크로 및 전역 함수는 다음과 같은 범주로 나뉩니다.

- 예외 처리기를 구조화하는 예외 매크로입니다.

- 특정 형식에 대한 예외를 생성하는 예외 throw 함수입니다.

- 프로그램 종료를 유발하는 종료 기능입니다.

예제 및 자세한 내용은 [예외](../../mfc/exception-handling-in-mfc.md)문서를 참조하십시오.

### <a name="exception-macros"></a>예외 매크로

|||
|-|-|
|[TRY](#try)|예외 처리를 위해 코드 블록을 지정합니다.|
|[잡을](#catch)|앞의 **TRY** 블록에서 예외를 catch하기 위한 코드 블록을 지정합니다.|
|[CATCH_ALL](#catch_all)|이전 **TRY** 블록의 모든 예외를 catch하기 위한 코드 블록을 지정합니다.|
|[AND_CATCH](#and_catch)|이전 **TRY** 블록에서 추가 예외 형식을 catch하기 위한 코드 블록을 지정합니다.|
|[AND_CATCH_ALL](#and_catch_all)|이전 **TRY** 블록에서 throw된 다른 모든 추가 예외 형식을 catch하기 위한 코드 블록을 지정합니다.|
|[END_CATCH](#end_catch)|마지막 **CATCH** 또는 **AND_CATCH** 코드 블록을 종료합니다.|
|[END_CATCH_ALL](#end_catch_all)|마지막 **CATCH_ALL** 코드 블록을 종료합니다.|
|[던져](#throw)|지정된 예외를 throw합니다.|
|[THROW_LAST](#throw_last)|현재 처리된 예외를 다음 외부 처리기에 throw합니다.|

### <a name="exception-throwing-functions"></a>예외 투척 함수

|||
|-|-|
|[AfxThrowArchiveException](#afxthrowarchiveexception)|아카이브 예외를 throw합니다.|
|[AfxThrowFileException](#afxthrowfileexception)|파일 예외를 throw합니다.|
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|잘못된 인수 예외를 throw합니다.|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|메모리 예외를 throw합니다.|
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|지원되지 않는 예외를 throw합니다.|
|[AfxThrowResourceException](#afxthrowresourceexception)|Windows 리소스가 찾을 수 없는 예외를 throw합니다.|
|[AfxThrowUserException](#afxthrowuserexception)|사용자가 시작한 프로그램 작업에서 예외를 throw합니다.|

MFC는 OLE 예외에 대해 특별히 두 가지 예외 throw 함수를 제공합니다.

### <a name="ole-exception-functions"></a>OLE 예외 함수

|||
|-|-|
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|OLE 자동화 함수 내에서 예외를 throw합니다.|
|[AfxThrowOleException](#afxthrowoleexception)|OLE 예외를 throw합니다.|

데이터베이스 예외를 지원하기 위해 데이터베이스 클래스는 `CDBException` 두 `CDaoException`가지 예외 클래스 및 예외 형식을 지원하는 전역 함수를 제공합니다.

### <a name="dao-exception-functions"></a>DAO 예외 함수

|||
|-|-|
|[AfxthrowDAO예외](#afxthrowdaoexception)|사용자 고유의 코드에서 [CDaoException을](../../mfc/reference/cdaoexception-class.md) throw합니다.|
|[AfxThrowDBException](#afxthrowdbexception)|사용자 고유의 코드에서 [CDBException을](../../mfc/reference/cdbexception-class.md) throw합니다.|

MFC는 다음과 같은 종료 함수를 제공합니다.

### <a name="termination-functions"></a>종료 함수

|||
|-|-|
|[AfxAbort](#afxabort)|치명적인 오류가 발생할 때 응용 프로그램을 종료하도록 호출됩니다.|

## <a name="try"></a><a name="try"></a>시도

**TRY** 블록을 설정합니다.

```
TRY
```

### <a name="remarks"></a>설명

**TRY** 블록은 예외를 throw할 수 있는 코드 블록을 식별합니다. 이러한 예외는 다음 **catch** 및 **AND_CATCH** 블록에서 처리됩니다. 재귀 허용: 예외를 무시하거나 THROW_LAST 매크로를 사용하여 외부 **TRY** 블록으로 전달될 수 있습니다. END_CATCH 또는 END_CATCH_ALL 매크로로 **TRY** 블록을 종료합니다.

자세한 내용은 [예외](../../mfc/exception-handling-in-mfc.md)문서를 참조하십시오.

### <a name="example"></a>예제

[CATCH](#catch)에 대한 예제를 참조하십시오.

### <a name="requirements"></a>요구 사항

헤더: afx.h

## <a name="catch"></a><a name="catch"></a>잡을

이전 **TRY** 블록에서 throw된 첫 번째 예외 형식을 catch하는 코드 블록을 정의합니다.

```
CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>매개 변수

*exception_class*<br/>
테스트할 예외 유형을 지정합니다. 표준 예외 클래스 목록은 클래스 [CException](../../mfc/reference/cexception-class.md)을 참조하십시오.

*exception_object_pointer_name*<br/>
매크로에 의해 생성되는 예외-개체 포인터에 대한 이름을 지정합니다. 포인터 이름을 사용하여 **CATCH** 블록 내의 예외 개체에 액세스할 수 있습니다. 이 변수는 자동으로 선언됩니다.

### <a name="remarks"></a>설명

예외 처리 코드는 필요한 경우 예외 개체를 확인하여 예외의 특정 원인에 대한 추가 정보를 가져올 수 있습니다. THROW_LAST 매크로를 호출하여 처리를 다음 외부 예외 프레임으로 이동합니다. END_CATCH 매크로로 **TRY** 블록을 종료합니다.

*exception_class* 클래스인 `CException`경우 모든 예외 형식이 catch됩니다. [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) 멤버 함수를 사용하여 throw된 특정 예외를 확인할 수 있습니다. 여러 종류의 예외를 catch하는 더 좋은 방법은 각각 다른 예외 형식을 가진 순차 **AND_CATCH** 문을 사용하는 것입니다.

예외 개체 포인터는 매크로에 의해 만들어집니다. 직접 선언할 필요는 없습니다.

> [!NOTE]
> **CATCH** 블록은 중괄호로 설명된 C++ 범위로 정의됩니다. 이 범위에서 변수를 선언하면 해당 범위 내에서만 액세스할 수 있습니다. 이는 *exception_object_pointer_name*에도 적용됩니다.

예외 및 CATCH 매크로에 대한 자세한 내용은 [예외](../../mfc/exception-handling-in-mfc.md)문서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]

## <a name="catch_all"></a><a name="catch_all"></a>CATCH_ALL

이전 **TRY** 블록에서 throw된 모든 예외 형식을 catch하는 코드 블록을 정의합니다.

```
CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>매개 변수

*exception_object_pointer_name*<br/>
매크로에 의해 생성되는 예외-개체 포인터에 대한 이름을 지정합니다. 포인터 이름을 사용해서 `CATCH_ALL` 블록 내에서 예외 개체에 액세스할 수 있습니다. 이 변수는 자동으로 선언됩니다.

### <a name="remarks"></a>설명

예외 처리 코드는 필요한 경우 예외 개체를 확인하여 예외의 특정 원인에 대한 추가 정보를 가져올 수 있습니다. `THROW_LAST` 매크로를 호출하여 다음 외부 예외 프레임으로 처리를 이동합니다. **CATCH_ALL**사용하는 경우 END_CATCH_ALL 매크로로 **TRY** 블록을 종료합니다.

> [!NOTE]
> **CATCH_ALL** 블록은 중괄호로 설명된 C++ 범위로 정의됩니다. 이 범위에서 변수를 선언하면 해당 범위 내에서만 액세스할 수 있습니다.

예외에 대한 자세한 내용은 [예외](../../mfc/exception-handling-in-mfc.md)문서를 참조하십시오.

### <a name="example"></a>예제

[CFile ::중단에](../../mfc/reference/cfile-class.md#abort)대한 예제를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="and_catch"></a><a name="and_catch"></a>AND_CATCH

이전 **TRY** 블록에서 throw된 추가 예외 형식을 catch하기 위한 코드 블록을 정의합니다.

```
AND_CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>매개 변수

*exception_class*<br/>
테스트할 예외 유형을 지정합니다. 표준 예외 클래스 목록은 클래스 [CException](../../mfc/reference/cexception-class.md)을 참조하십시오.

*exception_object_pointer_name*<br/>
매크로에 의해 생성될 예외 개체 포인터의 이름입니다. 포인터 이름을 사용하여 **AND_CATCH** 블록 내의 예외 개체에 액세스할 수 있습니다. 이 변수는 자동으로 선언됩니다.

### <a name="remarks"></a>설명

CATCH 매크로를 사용하여 하나의 예외 유형을 잡은 다음 AND_CATCH 매크로를 사용하여 각 후속 형식을 catch합니다. END_CATCH 매크로로 **TRY** 블록을 종료합니다.

예외 처리 코드는 필요한 경우 예외 개체를 확인하여 예외의 특정 원인에 대한 추가 정보를 가져올 수 있습니다. **AND_CATCH** 블록 내의 THROW_LAST 매크로를 호출하여 처리를 다음 외부 예외 프레임으로 이동합니다. **AND_CATCH** 앞의 **CATCH** 또는 **AND_CATCH** 블록의 끝을 표시합니다.

> [!NOTE]
> **AND_CATCH** 블록은 C++ 범위(중괄호로 설명)로 정의됩니다. 이 범위에서 변수를 선언하는 경우 해당 범위 내에서만 변수에 액세스할 수 있습니다. 이는 *exception_object_pointer_name* 변수에도 적용됩니다.

### <a name="example"></a>예제

[CATCH](#catch)에 대한 예제를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="and_catch_all"></a><a name="and_catch_all"></a>AND_CATCH_ALL

이전 **TRY** 블록에서 throw된 추가 예외 형식을 catch하기 위한 코드 블록을 정의합니다.

```
AND_CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>매개 변수

*exception_object_pointer_name*<br/>
매크로에 의해 생성될 예외 개체 포인터의 이름입니다. 포인터 이름을 사용하여 **AND_CATCH_ALL** 블록 내의 예외 개체에 액세스할 수 있습니다. 이 변수는 자동으로 선언됩니다.

### <a name="remarks"></a>설명

**CATCH** 매크로를 사용하여 하나의 예외 유형을 잡은 다음 AND_CATCH_ALL 매크로를 사용하여 다른 모든 후속 형식을 catch합니다. AND_CATCH_ALL 사용하는 경우 END_CATCH_ALL 매크로로 **TRY** 블록을 종료합니다.

예외 처리 코드는 필요한 경우 예외 개체를 확인하여 예외의 특정 원인에 대한 추가 정보를 가져올 수 있습니다. **AND_CATCH_ALL** 블록 내의 THROW_LAST 매크로를 호출하여 처리를 다음 외부 예외 프레임으로 이동합니다. **AND_CATCH_ALL** 앞의 **CATCH** 또는 **AND_CATCH_ALL** 블록의 끝을 표시합니다.

> [!NOTE]
> **AND_CATCH_ALL** 블록은 C++ 범위(중괄호로 설명)로 정의됩니다. 이 범위에서 변수를 선언하는 경우 해당 범위 내에서만 변수에 액세스할 수 있습니다.

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="end_catch"></a><a name="end_catch"></a>END_CATCH

마지막 **CATCH** 또는 **AND_CATCH** 블록의 끝을 표시합니다.

```
END_CATCH
```

### <a name="remarks"></a>설명

END_CATCH 매크로에 대한 자세한 내용은 [예외](../../mfc/exception-handling-in-mfc.md)문서를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="end_catch_all"></a><a name="end_catch_all"></a>END_CATCH_ALL

마지막 **CATCH_ALL88** 또는 **AND_CATCH_ALL** 블록의 끝을 표시합니다.

```
END_CATCH_ALL
```

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="throw-mfc"></a><a name="throw"></a>던지기 (MFC)

지정된 예외를 throw합니다.

```
THROW(exception_object_pointer)
```

### <a name="parameters"></a>매개 변수

*exception_object_pointer*<br/>
에서 파생된 예외 개체를 `CException`가리킵니다.

### <a name="remarks"></a>설명

**THROW는** 프로그램의 연결된 **CATCH** 블록에 제어를 전달하여 프로그램 실행을 중단합니다. **CATCH** 블록을 제공하지 않은 경우 컨트롤이 오류 메시지를 인쇄하고 종료하는 Microsoft Foundation 클래스 라이브러리 모듈로 전달됩니다.

자세한 내용은 [예외](../../mfc/exception-handling-in-mfc.md)문서를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="throw_last"></a><a name="throw_last"></a>THROW_LAST

예외를 다음 외부 **CATCH** 블록으로 다시 throw합니다.

```
THROW_LAST()
```

### <a name="remarks"></a>설명

이 매크로를 사용하면 로컬로 만든 예외를 throw할 수 있습니다. 방금 잡은 예외를 throw하려고 하면 일반적으로 범위를 벗어나 삭제됩니다. **THROW_LAST**경우 예외가 다음 **CATCH** 처리기에 올바르게 전달됩니다.

자세한 내용은 [예외](../../mfc/exception-handling-in-mfc.md)문서를 참조하십시오.

### <a name="example"></a>예제

[CFile ::중단에](../../mfc/reference/cfile-class.md#abort)대한 예제를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="afxthrowarchiveexception"></a><a name="afxthrowarchiveexception"></a>AfxthrowArchive예외

아카이브 예외를 throw합니다.

```cpp
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName);
```

### <a name="parameters"></a>매개 변수

*원인*<br/>
예외의 이유를 나타내는 정수지정합니다. 가능한 값 목록은 [CArchiveException:m_cause](../../mfc/reference/carchiveexception-class.md#m_cause)를 참조하십시오.

*lpszArchiveName*<br/>
예외를 일으킨 `CArchive` 개체의 이름이 포함된 문자열을 가리킵니다(사용 가능한 경우).

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="afxthrowfileexception"></a><a name="afxthrowfileexception"></a>AfxthrowFile예외

파일 예외를 throw합니다.

```cpp
void AfxThrowFileException(
    int cause,
    LONG lOsError = -1,
    LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>매개 변수

*원인*<br/>
예외의 이유를 나타내는 정수지정합니다. 가능한 값 목록은 [CFileException:m_cause](../../mfc/reference/cfileexception-class.md#m_cause)를 참조하십시오.

*로스에이슬*<br/>
예외의 원인을 명시하는 운영 체제 오류 번호(사용 가능한 경우)가 포함되어 있습니다. 오류 코드 목록은 운영 체제 설명서를 참조하십시오.

*lpsz파일이름*<br/>
예외를 일으킨 파일의 이름이 포함된 문자열을 가리킵니다(사용 가능한 경우).

### <a name="remarks"></a>설명

운영 체제 오류 코드를 기반으로 원인을 확인할 책임은 있습니다.

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="afxthrowinvalidargexception"></a><a name="afxthrowinvalidargexception"></a>AfxthrowInvalidArg예외

잘못된 인수 예외를 throw합니다.

### <a name="syntax"></a>구문

```cpp
void AfxThrowInvalidArgException( );
```

### <a name="remarks"></a>설명

이 함수는 잘못된 인수를 사용할 때 호출됩니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxthrowmemoryexception"></a><a name="afxthrowmemoryexception"></a>AfxthrowMemory예외

메모리 예외를 throw합니다.

```cpp
void AfxThrowMemoryException();
```

### <a name="remarks"></a>설명

기본 시스템 메모리 할당자(malloc 및 [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) Windows 함수)에 대한 호출이 실패하면 이 함수를 호출합니다. **malloc** 메모리 할당에 실패하면 **새** 메모리 예외가 자동으로 throw되므로 **새** 것으로 호출할 필요가 없습니다.

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="afxthrownotsupportedexception"></a><a name="afxthrownotsupportedexception"></a>AfxthrowNot지원예외

지원되지 않는 기능에 대한 요청의 결과인 예외를 throw합니다.

```cpp
void AfxThrowNotSupportedException();
```

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="afxthrowresourceexception"></a><a name="afxthrowresourceexception"></a>Afxthrow자원예외

리소스 예외를 throw합니다.

```cpp
void  AfxThrowResourceException();
```

### <a name="remarks"></a>설명

이 함수는 일반적으로 Windows 리소스를 로드할 수 없는 경우에 호출됩니다.

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="afxthrowuserexception"></a><a name="afxthrowuserexception"></a>AfxthrowUser예외

최종 사용자 작업을 중지하는 예외를 throw합니다.

```cpp
void AfxThrowUserException();
```

### <a name="remarks"></a>설명

이 함수는 일반적으로 `AfxMessageBox` 사용자에게 오류를 보고한 직후에 호출됩니다.

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="afxthrowoledispatchexception"></a><a name="afxthrowoledispatchexception"></a>AfxThrowOle디스패치예외

이 함수를 사용하여 OLE 자동화 함수 내에서 예외를 throw합니다.

```cpp
void AFXAPI AfxThrowOleDispatchException(
    WORD wCode ,
    LPCSTR lpszDescription,
    UINT nHelpID = 0);

void AFXAPI AfxThrowOleDispatchException(
    WORD wCode,
    UINT nDescriptionID,
    UINT nHelpID = -1);
```

### <a name="parameters"></a>매개 변수

*wCode*<br/>
응용 프로그램에 특정한 오류 코드입니다.

*lpszDescription*<br/>
오류에 대한 구두 설명입니다.

*nDescriptionID*<br/>
구두 오류 설명에 대한 리소스 ID입니다.

*nHelpID*<br/>
응용 프로그램의 도움말에 대한 도움말 컨텍스트() HLP) 파일.

### <a name="remarks"></a>설명

이 함수에 제공된 정보는 구동 응용 프로그램(Microsoft Visual Basic 또는 다른 OLE 자동화 클라이언트 응용 프로그램)을 통해 표시할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="afxthrowoleexception"></a><a name="afxthrowoleexception"></a>아프스로올예외

형식의 `COleException` 개체를 만들고 예외를 throw합니다.

```cpp
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr);
```

### <a name="parameters"></a>매개 변수

*사우스 캐롤라이나*<br/>
예외의 이유를 나타내는 OLE 상태 코드입니다.

*Hr*<br/>
예외의 원인을 나타내는 결과 코드를 처리합니다.

### <a name="remarks"></a>설명

HRESULT를 인수로 하는 버전은 결과 코드를 해당 SCODE로 변환합니다. HRESULT 및 SCODE에 대한 자세한 내용은 Windows SDK의 [COM 오류 코드 구조를](/windows/win32/com/structure-of-com-error-codes) 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="afxthrowdaoexception"></a><a name="afxthrowdaoexception"></a>AfxthrowDao예외

이 함수를 호출하여 사용자 고유의 코드에서 [CDaoException](../../mfc/reference/cdaoexception-class.md) 형식의 예외를 throw합니다.

```cpp
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,
    SCODE scode = S_OK);
```

### <a name="parameters"></a>매개 변수

*nAfxDao오류*<br/>
[CDaoException:m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror)아래에 나열된 값 중 하나일 수 있는 DAO 확장 오류 코드를 나타내는 정수 값입니다.

*Scode*<br/>
DAO의 올레 오류 코드입니다. 자세한 내용은 [CDaoException:m_scode](../../mfc/reference/cdaoexception-class.md#m_scode)을 참조하십시오.

### <a name="remarks"></a>설명

프레임워크는 또한 `AfxThrowDaoException`를 호출합니다. 호출에서 매개 변수 중 하나 또는 둘 다 전달할 수 있습니다. 예를 들어 **CDaoException::nAfxDaoError에** 정의된 오류 중 하나를 발생시키고 싶지만 *코드* 매개 변수에 신경 쓰지 않는 경우 *nAfxDaoError* 매개 변수에 유효한 코드를 전달하고 코드에 대한 기본값을 *수락합니다.*

MFC DAO 클래스와 관련된 예외에 대한 `CDaoException` 자세한 내용은 이 설명서의 클래스 및 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdb.h

## <a name="afxthrowdbexception"></a><a name="afxthrowdbexception"></a>AfxThrowDB예외

이 함수를 호출하여 사용자 `CDBException` 고유의 코드에서 형식 예외를 throw합니다.

```cpp
void AfxThrowDBException(
    RETCODE nRetCode,
    CDatabase* pdb,
    HSTMT hstmt);
```

### <a name="parameters"></a>매개 변수

*nRetCode*<br/>
예외가 throw되는 오류 유형을 정의하는 RETCODE 형식의 값입니다.

*Pdb*<br/>
예외가 `CDatabase` 연결된 데이터 원본 연결을 나타내는 개체에 대한 포인터입니다.

*hstmt*<br/>
예외가 연결된 명령문 핸들을 지정하는 ODBC HSTMT 핸들입니다.

### <a name="remarks"></a>설명

프레임워크는 `AfxThrowDBException` ODBC API 함수에 대한 호출에서 ODBC RETCODE를 수신하고 RETCODE를 예상 오류가 아닌 예외적인 조건으로 해석할 때 호출합니다. 예를 들어 디스크 읽기 오류로 인해 데이터 액세스 작업이 실패할 수 있습니다.

ODBC에서 정의한 RETCODE 값에 대한 자세한 내용은 Windows SDK의 "상태 및 오류 정보 검색"의 8장을 참조하십시오. 이러한 코드에 대한 MFC 확장에 대한 자세한 내용은 [클래스 CDBException](../../mfc/reference/cdbexception-class.md)을 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="afxabort"></a><a name="afxabort"></a>아프사보트

MFC에서 제공하는 기본 종료 함수입니다.

```cpp
void  AfxAbort();
```

### <a name="remarks"></a>설명

`AfxAbort`처리할 수 없는 catch되지 않은 예외와 같은 치명적인 오류가 있을 때 MFC 멤버 함수에서 내부적으로 호출됩니다. 복구할 `AfxAbort` 수 없는 치명적인 오류가 발생하면 드문 경우에 호출할 수 있습니다.

### <a name="example"></a>예제

[CATCH](#catch)에 대한 예제를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afx.h

## <a name="see-also"></a>참조

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[CException 클래스](cexception-class.md)<br/>
[CInvalidArgException 클래스](cinvalidargexception-class.md)
