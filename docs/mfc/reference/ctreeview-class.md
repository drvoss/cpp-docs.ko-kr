---
title: CTreeView 클래스
ms.date: 11/04/2016
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
ms.openlocfilehash: 2ef93152c83d3bbec2b89ada0596ee612b24701b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373289"
---
# <a name="ctreeview-class"></a>CTreeView 클래스

MFC의 문서 보기 아키텍처를 사용하여 트리 제어 기능을 캡슐화하는 클래스인 트리 컨트롤 및 [CTreeCtrl의](../../mfc/reference/ctreectrl-class.md)사용을 간소화합니다.

## <a name="syntax"></a>구문

```
class CTreeView : public CCtrlView
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CTreeView::CTreeView](#ctreeview)|`CTreeView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CTreeView::겟트리Ctrl](#gettreectrl)|뷰와 연결된 트리 컨트롤을 반환합니다.|

## <a name="remarks"></a>설명

이 아키텍처에 대한 자세한 내용은 [CView](../../mfc/reference/cview-class.md) 클래스의 개요와 인용된 상호 참조를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CTreeView`

## <a name="requirements"></a>요구 사항

**헤더:** afxcview.h

## <a name="ctreeviewctreeview"></a><a name="ctreeview"></a>CTreeView::CTreeView

`CTreeView` 개체를 생성합니다.

```
CTreeView();
```

## <a name="ctreeviewgettreectrl"></a><a name="gettreectrl"></a>CTreeView::겟트리Ctrl

뷰와 연결된 트리 컨트롤에 대한 참조를 반환합니다.

```
CTreeCtrl& GetTreeCtrl() const;
```

## <a name="see-also"></a>참고 항목

[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)<br/>
[CTreeCtrl 클래스](../../mfc/reference/ctreectrl-class.md)
