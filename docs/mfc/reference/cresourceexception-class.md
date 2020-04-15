---
title: CResource예외 클래스
ms.date: 11/04/2016
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
ms.openlocfilehash: 557bfe1cc41c3dda65bd95d7d687820c0b9862b7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368324"
---
# <a name="cresourceexception-class"></a>CResource예외 클래스

Windows에서 요청된 리소스를 찾거나 할당할 수 없을 경우 발생합니다.

## <a name="syntax"></a>구문

```
class CResourceException : public CSimpleException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C리소스 예외::C리소스 예외](#cresourceexception)|`CResourceException` 개체를 생성합니다.|

## <a name="remarks"></a>설명

더 이상의 자격이 필요하지 않거나 불가능합니다.

사용에 `CResourceException`대한 자세한 내용은 [MFC(예외 처리)](../../mfc/exception-handling-in-mfc.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CResourceException`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cresourceexceptioncresourceexception"></a><a name="cresourceexception"></a>C리소스 예외::C리소스 예외

`CResourceException` 개체를 생성합니다.

```
CResourceException();
```

### <a name="remarks"></a>설명

이 생성자는 직접 사용하지 말고 전역 함수 [AfxThrowResourceException을](exception-processing.md#afxthrowresourceexception)호출합니다. 예외에 대한 자세한 내용은 [MFC의 예외 처리](../exception-handling-in-mfc.md)문서를 참조하십시오.

## <a name="see-also"></a>참고 항목

[CException 클래스](cexception-class.md)<br/>
[계층 구조 차트](../hierarchy-chart.md)
