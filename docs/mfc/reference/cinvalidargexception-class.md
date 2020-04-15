---
title: CInvalidArgException 클래스
ms.date: 11/04/2016
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
ms.openlocfilehash: b28b6e84043b85a8117694a67ff5fff13e7c786b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372370"
---
# <a name="cinvalidargexception-class"></a>CInvalidArgException 클래스

이 클래스는 잘못된 인수 예외 상태를 나타냅니다.

## <a name="syntax"></a>구문

```
class CInvalidArgException : public CSimpleException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CInvalidArg예외::CInvalidArgException](#cinvalidargexception)|생성자입니다.|

## <a name="remarks"></a>설명

개체는 `CInvalidArgException` 잘못된 인수 예외 조건을 나타냅니다.

예외 처리에 대한 자세한 내용은 [CException 클래스](../../mfc/reference/cexception-class.md) 항목 및 [예외 처리(MFC)를](../../mfc/exception-handling-in-mfc.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CInvalidArgException`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cinvalidargexceptioncinvalidargexception"></a><a name="cinvalidargexception"></a>CInvalidArg예외::CInvalidArgException

생성자입니다.

```
CInvalidArgException();
```

### <a name="remarks"></a>설명

이 생성자는 직접 사용하지 마십시오. 글로벌 함수 **AfxthrowInvalidArgException을**호출합니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CSimpleException 클래스](../../mfc/reference/csimpleexception-class.md)
