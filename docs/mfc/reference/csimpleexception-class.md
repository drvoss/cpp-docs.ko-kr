---
title: CSimpleException 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
ms.openlocfilehash: eb94ba9e3d26b3cd910f23c3d4abb29d3b8b1cd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318354"
---
# <a name="csimpleexception-class"></a>CSimpleException 클래스

이 클래스는 리소스에 중요한 MFC 예외의 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE CSimpleException : public CException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CSimple예외::C단순예외](#csimpleexception)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C단순 예외::GetErrorMessage](#geterrormessage)|발생한 오류에 대한 텍스트를 제공합니다.|

## <a name="remarks"></a>설명

`CSimpleException`는 리소스에 중요한 MFC 예외의 기본 클래스이며 오류 메시지의 소유권 및 초기화를 처리합니다. 다음 클래스는 `CSimpleException` 기본 클래스로 사용합니다.

|||
|-|-|
|[C메모리예외 클래스](../../mfc/reference/cmemoryexception-class.md)|메모리 부족 예외|
|[CNot지원 예외 클래스](../../mfc/reference/cnotsupportedexception-class.md)|지원되지 않는 작업에 대한 요청|
|[CResource예외 클래스](../../mfc/reference/cresourceexception-class.md)|Windows 리소스를 찾을 수 없거나 삐걱거리지 않음|
|[CUserException 클래스](../../mfc/reference/cuserexception-class.md)|리소스를 찾을 수 없다는 것을 나타내는 예외|
|[CInvalidArgException 클래스](../../mfc/reference/cinvalidargexception-class.md)|잘못된 인수를 나타내는 예외|

추상 기본 클래스이기 때문에 `CSimpleException` 개체를 `CSimpleException` 직접 선언할 수 없습니다. 대신 이전 테이블의 것과 같은 파생 개체를 선언해야 합니다. 고유한 파생 클래스를 선언하는 경우 이전 클래스를 모델로 사용합니다.

자세한 내용은 [CException 클래스](../../mfc/reference/cexception-class.md) 항목 및 [예외 처리(MFC)를](../../mfc/exception-handling-in-mfc.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CSimpleException`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="csimpleexceptioncsimpleexception"></a><a name="csimpleexception"></a>CSimple예외::C단순예외

생성자입니다.

```
CSimpleException();
explicit CSimpleException(BOOL bAutoDelete);
```

### <a name="parameters"></a>매개 변수

*bAutoDelete*<br/>
`CSimpleException` 개체에 대한 메모리가 힙에 할당된 경우 TRUE를 지정합니다. 이렇게 하면 `CSimpleException` `Delete` 멤버 함수가 호출되어 예외를 삭제할 때 개체가 삭제됩니다. 개체가 `CSimpleException` 스택에 있거나 전역 개체인 경우 FALSE를 지정합니다. 이 경우 멤버 `CSimpleException` 함수가 호출될 `Delete` 때 개체가 삭제되지 않습니다.

### <a name="remarks"></a>설명

일반적으로 이 생성자(생성자)를 직접 호출할 필요가 없습니다. 예외를 throw 하는 함수는 -derived `CException`클래스의 인스턴스를 만들고 해당 생성기를 호출하거나 [AfxThrowFileException과](exception-processing.md#afxthrowfileexception)같은 MFC throw 함수 중 하나를 사용하여 미리 정의된 형식을 throw해야 합니다.

## <a name="csimpleexceptiongeterrormessage"></a><a name="geterrormessage"></a>C단순 예외::GetErrorMessage

이 멤버 함수를 호출하여 발생한 오류에 대한 텍스트를 제공합니다.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```

### <a name="parameters"></a>매개 변수

*lpsz오류*<br/>
오류 메시지를 받게 되는 버퍼에 대한 포인터입니다.

*nMaxError*<br/>
NULL 종사자를 포함하여 버퍼가 보유할 수 있는 최대 문자 수입니다.

*pn도움말컨텍스트*<br/>
도움말 컨텍스트 ID를 받을 UINT의 주소입니다. NULL이면 ID가 반환되지 않습니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0을 사용할 수 있는 오류 메시지 텍스트가 없는 경우.

### <a name="remarks"></a>설명

자세한 내용은 [CException:GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[예외 처리](../../mfc/exception-handling-in-mfc.md)
