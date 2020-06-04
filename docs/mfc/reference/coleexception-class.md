---
title: COleException 클래스
ms.date: 11/04/2016
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
ms.openlocfilehash: 737c9e669990f4de6ae18cdc7662c131ad61516f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375004"
---
# <a name="coleexception-class"></a>COleException 클래스

OLE 작업과 관련된 예외 조건을 나타냅니다.

## <a name="syntax"></a>구문

```
class COleException : public CException
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[코레예외::P로키스](#process)|적발된 예외를 OLE 반환 코드로 변환합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[콜레예외::m_sc](#m_sc)|예외의 원인을 나타내는 상태 코드를 포함합니다.|

## <a name="remarks"></a>설명

클래스에는 `COleException` 예외 이유를 나타내는 상태 코드를 포함하는 공용 데이터 멤버가 포함됩니다.

일반적으로 개체를 `COleException` 직접 만들지 않아야 합니다. 대신 [AfxThrowOleException을](exception-processing.md#afxthrowoleexception)호출해야 합니다.

예외에 대한 자세한 내용은 [MFC(예외 처리)](../../mfc/exception-handling-in-mfc.md) 및 [예외: OLE 예외](../../mfc/exceptions-ole-exceptions.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleException`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="coleexceptionm_sc"></a><a name="m_sc"></a>콜레예외::m_sc

이 데이터 멤버에는 예외의 원인을 나타내는 OLE 상태 코드가 있습니다.

```
SCODE m_sc;
```

### <a name="remarks"></a>설명

이 변수의 값은 [AfxThrowOleException에](exception-processing.md#afxthrowoleexception)의해 설정됩니다.

SCODE에 대한 자세한 내용은 Windows SDK의 [COM 오류 코드 구조를](/windows/win32/com/structure-of-com-error-codes) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]

## <a name="coleexceptionprocess"></a><a name="process"></a>코레예외::P로키스

**프로세스** 멤버 함수를 호출하여 CATCH된 예외를 OLE 상태 코드로 변환합니다.

```
static SCODE PASCAL Process(const CException* pAnyException);
```

### <a name="parameters"></a>매개 변수

*pAnyException*<br/>
적발된 예외에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

OLE 상태 코드입니다.

### <a name="remarks"></a>설명

> [!NOTE]
> 이 함수는 **정적입니다.**

SCODE에 대한 자세한 내용은 Windows SDK의 [COM 오류 코드 구조를](/windows/win32/com/structure-of-com-error-codes) 참조하십시오.

### <a name="example"></a>예제

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)에 대한 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[MFC 샘플 CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
