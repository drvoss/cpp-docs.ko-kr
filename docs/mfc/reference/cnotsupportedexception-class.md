---
title: CNot지원 예외 클래스
ms.date: 11/04/2016
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
ms.openlocfilehash: b859b939baef018e69b245e597eea90e608253ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363187"
---
# <a name="cnotsupportedexception-class"></a>CNot지원 예외 클래스

지원되지 않는 기능을 요청한 결과인 예외를 나타냅니다.

## <a name="syntax"></a>구문

```
class CNotSupportedException : public CSimpleException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CNot지원 예외::CNot지원 예외](#cnotsupportedexception)|`CNotSupportedException` 개체를 생성합니다.|

## <a name="remarks"></a>설명

더 이상의 자격이 필요하지 않거나 불가능합니다.

사용에 `CNotSupportedException`대한 자세한 내용은 [MFC(예외 처리)](../../mfc/exception-handling-in-mfc.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CNotSupportedException`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cnotsupportedexceptioncnotsupportedexception"></a><a name="cnotsupportedexception"></a>CNot지원 예외::CNot지원 예외

`CNotSupportedException` 개체를 생성합니다.

```
CNotSupportedException();
```

### <a name="remarks"></a>설명

이 생성자는 직접 사용하지 말고 전역 함수 [AfxThrowNotSupportedException을](exception-processing.md#afxthrownotsupportedexception)호출합니다. 예외 처리에 대한 자세한 내용은 [MFC의 예외 처리](../exception-handling-in-mfc.md)문서를 참조하십시오.

## <a name="see-also"></a>참고 항목

[CException 클래스](cexception-class.md)<br/>
[계층 구조 차트](../hierarchy-chart.md)
