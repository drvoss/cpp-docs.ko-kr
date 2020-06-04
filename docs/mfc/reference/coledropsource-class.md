---
title: 콜레드롭소스 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
helpviewer_keywords:
- COleDropSource [MFC], COleDropSource
- COleDropSource [MFC], GiveFeedback
- COleDropSource [MFC], OnBeginDrag
- COleDropSource [MFC], QueryContinueDrag
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
ms.openlocfilehash: 324c4b7273f021b43c319fb0a494ac843856c78a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375020"
---
# <a name="coledropsource-class"></a>콜레드롭소스 클래스

데이터를 놓기 대상으로 드래그할 수 있습니다.

## <a name="syntax"></a>구문

```
class COleDropSource : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레드롭소스::콜레드롭소스](#coledropsource)|`COleDropSource` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[콜레드롭소스::피드백 제공](#givefeedback)|끌어서 놓기 작업 중에 커서를 변경합니다.|
|[콜레드롭소스::온비드래그](#onbegindrag)|끌어서 놓기 작업 중에 마우스 캡처를 처리합니다.|
|[COleDropSource::쿼리다시드래그](#querycontinuedrag)|드래그를 계속할지 여부를 확인합니다.|

## <a name="remarks"></a>설명

[COleDropTarget](../../mfc/reference/coledroptarget-class.md) 클래스는 끌어서 놓기 작업의 수신 부분을 처리합니다. 오브젝트는 `COleDropSource` 끌기 작업이 시작되는 시기를 결정하고, 끌기 작업 중에 피드백을 제공하고, 끌기 작업이 끝나는 시기를 결정합니다.

개체를 `COleDropSource` 사용하려면 생성자만 호출합니다. 이렇게 하면 마우스 클릭과 같은 이벤트가 [COleDataSource::DoDragDrop,](../../mfc/reference/coledatasource-class.md#dodragdrop) [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop)또는 [COleServerItem::DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) 함수를 사용하여 드래그 작업을 시작하는 작업을 시작하는 프로세스를 단순화합니다. 이러한 함수는 당신을 `COleDropSource` 위한 개체를 만듭니다. 재정의 가능한 함수의 기본 `COleDropSource` 동작을 수정할 수 있습니다. 이러한 멤버 함수는 프레임워크에서 적절한 시간에 호출됩니다.

OLE를 사용한 끌어서 놓기 작업에 대한 자세한 내용은 [OLE 끌어서 놓기](../../mfc/drag-and-drop-ole.md)문서를 참조하십시오.

자세한 내용은 Windows SDK의 [IDropSource를](/windows/win32/api/oleidl/nn-oleidl-idropsource) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropSource`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="coledropsourcecoledropsource"></a><a name="coledropsource"></a>콜레드롭소스::콜레드롭소스

`COleDropSource` 개체를 생성합니다.

```
COleDropSource();
```

## <a name="coledropsourcegivefeedback"></a><a name="givefeedback"></a>콜레드롭소스::피드백 제공

[COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) 또는 [COleDropTarget::DragEnter를](../../mfc/reference/coledroptarget-class.md#ondragenter)호출한 후 프레임워크에서 호출됩니다.

```
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```

### <a name="parameters"></a>매개 변수

*드롭 이펙트*<br/>
일반적으로 선택한 데이터로 이 시점에서 드롭이 발생하면 어떤 일이 발생하는지 나타내는 사용자에게 표시할 효과입니다. 일반적으로 이 값은 [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) 또는 [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover)에 대한 가장 최근 호출에서 반환되는 값입니다. 다음 중 하나 이상이 될 수 있습니다.

- DROPEFFECT_NONE 한 방울은 허용되지 않습니다.

- DROPEFFECT_COPY 복사 작업이 수행됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행됩니다.

- DROPEFFECT_LINK 삭제된 데이터에서 원본 데이터에 대한 링크가 설정됩니다.

- DROPEFFECT_SCROLL 드래그 스크롤 작업이 발생하려고 하거나 대상에서 발생 합니다.

### <a name="return-value"></a>Return Value

드래그가 진행 중인 경우 DRAGDROP_S_USEDEFAULTCURSORS 반환하고, 그렇지 않은 경우 NOERROR를 반환합니다.

### <a name="remarks"></a>설명

이 함수를 재정의하여 이 시점에서 드롭이 발생한 경우 발생하는 일에 대한 피드백을 사용자에게 제공합니다. 기본 구현에서는 OLE 기본 커서를 사용합니다. OLE를 사용한 끌어서 놓기 작업에 대한 자세한 내용은 [OLE 끌어서 놓기](../../mfc/drag-and-drop-ole.md)문서를 참조하십시오.

자세한 내용은 [IDropSource::GiveFeedback](/windows/win32/api/oleidl/nf-oleidl-idropsource-givefeedback), [IDropTarget::DragOver](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover)및 [IDropTarget::DwindowsSDK에서 수행자](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter) 참조.

## <a name="coledropsourceonbegindrag"></a><a name="onbegindrag"></a>콜레드롭소스::온비드래그

왼쪽 마우스 단추를 누르는 등 끌기 작업을 시작할 수 있는 이벤트가 발생할 때 프레임워크에서 호출합니다.

```
virtual BOOL OnBeginDrag(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
선택한 데이터가 포함된 창을 가리킵니다.

### <a name="return-value"></a>Return Value

드래그가 허용되는 경우 0이 아닌 0입니다.

### <a name="remarks"></a>설명

끌기 프로세스가 시작되는 방식을 수정하려면 이 함수를 재정의합니다. 기본 구현은 마우스를 캡처하고 사용자가 왼쪽 또는 오른쪽 마우스 단추를 클릭하거나 ESC에 닿을 때까지 드래그 모드로 유지됩니다.

## <a name="coledropsourcequerycontinuedrag"></a><a name="querycontinuedrag"></a>COleDropSource::쿼리다시드래그

끌기가 시작된 후 드래그 작업이 취소되거나 완료될 때까지 프레임워크에서 이 함수를 반복적으로 호출합니다.

```
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed,
    DWORD dwKeyState);
```

### <a name="parameters"></a>매개 변수

*b이스케이프프레스드*<br/>
에 대한 마지막 호출 이후 ESC 키를 눌렀는지 여부를 `COleDropSource::QueryContinueDrag`명시합니다.

*dwKeyState*<br/>
키보드의 수정자 키 의 상태를 포함합니다. 이는 MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON 및 MK_RBUTTON 여러 가지 조합입니다.

### <a name="return-value"></a>Return Value

ESC 키 또는 오른쪽 버튼을 누르거나 드래그를 시작하기 전에 왼쪽 버튼을 누른 경우 DRAGDROP_S_CANCEL. 드롭 작업이 발생해야 하는지 DRAGDROP_S_DROP. 그렇지 않으면 S_OK.

### <a name="remarks"></a>설명

드래깅이 취소되거나 드롭이 발생하는 지점을 변경하려면 이 함수를 재정의합니다.

기본 구현은 다음과 같이 끌어를 놓기 시작하거나 드래그를 취소합니다. ESC 키 또는 오른쪽 마우스 버튼을 누르면 드래그 작업이 취소됩니다. 드래그가 시작된 후 왼쪽 마우스 버튼을 누르면 놓기 작업이 시작됩니다. 그렇지 않으면 S_OK 반환하고 더 이상 작업을 수행하지 않습니다.

이 함수는 자주 호출되므로 가능한 한 많이 최적화해야 합니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 클라이언트](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
