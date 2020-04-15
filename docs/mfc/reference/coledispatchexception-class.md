---
title: 콜레디스패치예외 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
helpviewer_keywords:
- COleDispatchException [MFC], m_dwHelpContext
- COleDispatchException [MFC], m_strDescription
- COleDispatchException [MFC], m_strHelpFile
- COleDispatchException [MFC], m_strSource
- COleDispatchException [MFC], m_wCode
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
ms.openlocfilehash: 4572b639b757569d8e3cfa731f99c123762f3900
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375057"
---
# <a name="coledispatchexception-class"></a>콜레디스패치예외 클래스

OLE 자동화의 핵심인 OLE `IDispatch` 인터페이스에만 해당하는 예외를 처리합니다.

## <a name="syntax"></a>구문

```
class COleDispatchException : public CException
```

## <a name="members"></a>멤버

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[올레디스패치예외:m_dwHelpContext](#m_dwhelpcontext)|오류에 대한 컨텍스트를 도와줍니다.|
|[올레디스패치예외::m_strDescription](#m_strdescription)|구두 오류 설명입니다.|
|[올레디스패치예외:m_strHelpFile](#m_strhelpfile)|와 함께 사용할 `m_dwHelpContext`도움말 파일입니다.|
|[올레디스패치예외:m_strSource](#m_strsource)|예외를 생성한 응용 프로그램입니다.|
|[올레디스패치예외:m_wCode](#m_wcode)|`IDispatch`-특정 오류 코드.|

## <a name="remarks"></a>설명

`CException` 기본 클래스에서 파생된 다른 예외 `COleDispatchException` 클래스와 마찬가지로 THROW, THROW_LAST, TRY, CATCH, AND_CATCH 및 END_CATCH 매크로와 함께 사용할 수 있습니다.

일반적으로 [AfxThrowOleDispatchException을](exception-processing.md#afxthrowoledispatchexception) 호출하여 개체를 `COleDispatchException` 만들고 throw해야 합니다.

예외에 대한 자세한 내용은 [MFC(예외 처리)](../../mfc/exception-handling-in-mfc.md) 및 [예외: OLE 예외](../../mfc/exceptions-ole-exceptions.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleDispatchException`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="coledispatchexceptionm_dwhelpcontext"></a><a name="m_dwhelpcontext"></a>올레디스패치예외:m_dwHelpContext

응용 프로그램의 도움말에서 도움말 컨텍스트를 식별합니다( HLP) 파일.

```
DWORD m_dwHelpContext;
```

### <a name="remarks"></a>설명

이 멤버는 예외가 throw될 때 [AfxThrowOleDispatch](exception-processing.md#afxthrowoledispatchexception) 예외 함수에 의해 설정됩니다.

### <a name="example"></a>예제

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)에 대한 예제를 참조하세요.

## <a name="coledispatchexceptionm_strdescription"></a><a name="m_strdescription"></a>올레디스패치예외::m_strDescription

"디스크 가득 찼다"와 같은 구두 오류 설명이 포함되어 있습니다.

```
CString m_strDescription;
```

### <a name="remarks"></a>설명

이 멤버는 예외가 throw될 때 [AfxThrowOleDispatch](exception-processing.md#afxthrowoledispatchexception) 예외 함수에 의해 설정됩니다.

### <a name="example"></a>예제

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)에 대한 예제를 참조하세요.

## <a name="coledispatchexceptionm_strhelpfile"></a><a name="m_strhelpfile"></a>올레디스패치예외:m_strHelpFile

프레임워크는 이 문자열에 응용 프로그램의 도움말 파일 의 이름으로 채웁니다.

```
CString m_strHelpFile;
```

## <a name="coledispatchexceptionm_strsource"></a><a name="m_strsource"></a>올레디스패치예외:m_strSource

프레임워크는 예외를 생성한 응용 프로그램의 이름으로 이 문자열을 채웁니다.

```
CString m_strSource;
```

### <a name="example"></a>예제

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)에 대한 예제를 참조하세요.

## <a name="coledispatchexceptionm_wcode"></a><a name="m_wcode"></a>올레디스패치예외:m_wCode

응용 프로그램과 관련된 오류 코드가 포함되어 있습니다.

```
WORD m_wCode;
```

### <a name="remarks"></a>설명

이 멤버는 예외가 throw될 때 [AfxThrowOleDispatch](exception-processing.md#afxthrowoledispatchexception) 예외 함수에 의해 설정됩니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[올레디스패치드라이버 클래스](../../mfc/reference/coledispatchdriver-class.md)<br/>
[COleException 클래스](../../mfc/reference/coleexception-class.md)
