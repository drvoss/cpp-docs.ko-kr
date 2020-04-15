---
title: CDocItem 클래스
ms.date: 11/04/2016
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
ms.openlocfilehash: 438bc2a03239946dbfca53d5f2989c731b682ab0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375614"
---
# <a name="cdocitem-class"></a>CDocItem 클래스

문서 데이터의 구성 요소로, 문서 항목에 대한 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CDocItem : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDocItem::GetDocument](#getdocument)|항목이 포함된 문서를 반환합니다.|
|[CDoc항목::공백](#isblank)|항목에 정보가 포함되어 있는지 여부를 확인합니다.|

## <a name="remarks"></a>설명

`CDocItem`개체는 클라이언트 및 서버 문서 모두에서 OLE 항목을 나타내는 데 사용됩니다.

자세한 내용은 [컨테이너: 컨테이너 구현](../../mfc/containers-implementing-a-container.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocItem`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="cdocitemgetdocument"></a><a name="getdocument"></a>CDocItem::GetDocument

이 함수를 호출하여 항목이 포함된 문서를 가져옵니다.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>Return Value

항목이 포함된 문서에 대한 포인터입니다. NULL, 항목이 문서의 일부가 아닌 경우.

### <a name="remarks"></a>설명

이 함수는 파생 된 클래스 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 및 [COleServerItem에서](../../mfc/reference/coleserveritem-class.md)재정의 되어 [COleDocument,](../../mfc/reference/coledocument-class.md) [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)또는 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) 개체에 대한 포인터를 반환합니다.

## <a name="cdocitemisblank"></a><a name="isblank"></a>CDoc항목::공백

기본 직렬화가 발생할 때 프레임 워크에 의해 호출 됩니다.

```
virtual BOOL IsBlank() const;
```

### <a name="return-value"></a>Return Value

항목에 정보가 없는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

기본적으로 `CDocItem` 개체는 비어 있지 않습니다. [COleClientItem](../../mfc/reference/coleclientitem-class.md) 개체는 에서 `CDocItem`직접 파생되기 때문에 비어 있는 경우가 있습니다. 그러나 [COleServerItem](../../mfc/reference/coleserveritem-class.md) 개체는 항상 비어 있습니다. 기본적으로 x 또는 y `COleClientItem` 익스텐션이 없는 개체를 포함하는 OLE 응용 프로그램은 직렬화됩니다. 이 작업은 항목에 x 또는 y `IsBlank` 익스텐션이 없는 경우의 재정의를 통해 TRUE를 반환하여 수행됩니다.

직렬화 하는 동안 다른 작업을 구현 하려는 경우 이 함수를 재정의 합니다.

## <a name="see-also"></a>참고 항목

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[콜레문서 클래스](../../mfc/reference/coledocument-class.md)<br/>
[콜레서버아이템 클래스](../../mfc/reference/coleserveritem-class.md)<br/>
[COle클라이언트항목 클래스](../../mfc/reference/coleclientitem-class.md)
