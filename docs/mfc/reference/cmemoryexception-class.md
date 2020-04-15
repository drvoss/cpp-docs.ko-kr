---
title: C메모리예외 클래스
ms.date: 11/04/2016
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
ms.openlocfilehash: 375b4227a25ae4c18cfd263eff4c3ec13f1304e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370003"
---
# <a name="cmemoryexception-class"></a>C메모리예외 클래스

메모리 부족 예외 상태를 나타냅니다.

## <a name="syntax"></a>구문

```
class CMemoryException : public CSimpleException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C메모리예외::C메모리예외](#cmemoryexception)|`CMemoryException` 개체를 생성합니다.|

## <a name="remarks"></a>설명

더 이상의 자격이 필요하지 않거나 불가능합니다. 메모리 예외는 **새**에 의해 자동으로 throw됩니다. 예를 들어 을 사용하여 `malloc`사용자 고유의 메모리 함수를 작성하는 경우 메모리 예외를 throw해야 합니다.

자세한 `CMemoryException`내용은 [MFC(예외 처리)](../../mfc/exception-handling-in-mfc.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CMemoryException`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cmemoryexceptioncmemoryexception"></a><a name="cmemoryexception"></a>C메모리예외::C메모리예외

`CMemoryException` 개체를 생성합니다.

```
CMemoryException();
```

### <a name="remarks"></a>설명

이 생성자는 직접 사용하지 말고 전역 함수 [AfxThrowMemoryException을](exception-processing.md#afxthrowmemoryexception)호출합니다. 이 전역 함수는 이전에 할당된 메모리에서 예외 개체를 생성하기 때문에 메모리 부족 상황에서 성공할 수 있습니다. 예외 처리에 대한 자세한 내용은 문서 [예외를](../exception-handling-in-mfc.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[CException 클래스](cexception-class.md)<br/>
[계층 구조 차트](../hierarchy-chart.md)
