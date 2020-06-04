---
title: CListView 클래스
ms.date: 11/04/2016
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
helpviewer_keywords:
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
ms.openlocfilehash: d7f3b7c43d98c4f2c42d0c27c8e224f33e4b3301
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749130"
---
# <a name="clistview-class"></a>CListView 클래스

MFC의 문서 보기 아키텍처를 사용하여 목록 제어 기능을 캡슐화하는 클래스인 [CListCtrl의](../../mfc/reference/clistctrl-class.md)목록 제어 및 사용을 간소화합니다.

## <a name="syntax"></a>구문

```
class CListView : public CCtrlView
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CListView::CListView](#clistview)|`CListView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CListView::겟리스트Ctrl](#getlistctrl)|뷰와 연결된 목록 컨트롤을 반환합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CListView::삭제이미지 목록](#removeimagelist)|목록 보기에서 지정된 이미지 목록을 제거합니다.|

## <a name="remarks"></a>설명

이 아키텍처에 대한 자세한 내용은 [CView](../../mfc/reference/cview-class.md) 클래스의 개요와 인용된 상호 참조를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CListView`

## <a name="requirements"></a>요구 사항

**헤더:** afxcview.h

## <a name="clistviewclistview"></a><a name="clistview"></a>CListView::CListView

`CListView` 개체를 생성합니다.

```
CListView();
```

## <a name="clistviewgetlistctrl"></a><a name="getlistctrl"></a>CListView::겟리스트Ctrl

이 멤버 함수를 호출하여 뷰와 연결된 목록 컨트롤에 대한 참조를 가져옵니다.

```
CListCtrl& GetListCtrl() const;
```

### <a name="return-value"></a>Return Value

뷰와 연결된 목록 컨트롤에 대한 참조입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]

## <a name="clistviewremoveimagelist"></a><a name="removeimagelist"></a>CListView::삭제이미지 목록

목록 보기에서 지정된 이미지 목록을 제거합니다.

```cpp
void RemoveImageList(int nImageList);
```

### <a name="parameters"></a>매개 변수

*nImageList*<br/>
제거할 이미지의 0기반 인덱스입니다.

## <a name="see-also"></a>참조

[MFC 샘플 행 목록](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)
