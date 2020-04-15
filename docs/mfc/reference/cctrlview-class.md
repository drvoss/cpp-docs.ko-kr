---
title: CCtrlView 클래스
ms.date: 11/04/2016
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
helpviewer_keywords:
- CCtrlView [MFC], CCtrlView
- CCtrlView [MFC], OnDraw
- CCtrlView [MFC], PreCreateWindow
- CCtrlView [MFC], m_dwDefaultStyle
- CCtrlView [MFC], m_strClass
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
ms.openlocfilehash: f77f1c265920bd160da790647ef754c55e6dbda3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369351"
---
# <a name="cctrlview-class"></a>CCtrlView 클래스

문서 뷰 아키텍처를 Windows 98 및 Windows NT 버전 3.51 이상에서 지원하는 공통의 컨트롤에 맞게 변경합니다.

## <a name="syntax"></a>구문

```
class CCtrlView : public CView
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CCtrlView::CCtrlView](#cctrlview)|`CCtrlView` 개체를 생성합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CCtrlView::에 그리기](#ondraw)|지정된 장치 컨텍스트를 사용하여 그리려면 프레임워크에서 호출합니다.|
|[CCtrlView::P재현창](#precreatewindow)|이 `CCtrlView` 개체에 연결된 Windows 창을 만들기 전에 호출됩니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|뷰 클래스의 기본 스타일을 포함합니다.|
|[CCtrlView::m_strClass](#m_strclass)|뷰 클래스에 대 한 Windows 클래스 이름을 포함 합니다.|

## <a name="remarks"></a>설명

클래스 `CCtrlView` 및 해당 파생 항목인 [CEditView](../../mfc/reference/ceditview-class.md), [CListView,](../../mfc/reference/clistview-class.md) [CTreeView](../../mfc/reference/ctreeview-class.md)및 [CRichEditView는](../../mfc/reference/cricheditview-class.md)문서 보기 아키텍처를 Windows 95/98 및 Windows NT 버전 3.51 이상에서 지원하는 새로운 공통 컨트롤에 맞게 조정합니다. 문서 보기 아키텍처에 대한 자세한 내용은 [문서/아키텍처 보기](../../mfc/document-view-architecture.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CCtrlView`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cctrlviewcctrlview"></a><a name="cctrlview"></a>CCtrlView::CCtrlView

`CCtrlView` 개체를 생성합니다.

```
CCtrlView(
    LPCTSTR lpszClass,
    DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*lpszClass*<br/>
뷰 클래스의 Windows 클래스 이름입니다.

*dwStyle*<br/>
뷰 클래스의 스타일입니다.

### <a name="remarks"></a>설명

프레임워크는 새 프레임 창이 만들어지거나 창이 분할될 때 생성자입니다. [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) 재정의하여 문서가 첨부된 후 뷰를 초기화합니다. [CWnd::만들기](../../mfc/reference/cwnd-class.md#create) 또는 [CWnd::CreateEx를](../../mfc/reference/cwnd-class.md#createex) 호출하여 Windows 개체를 만듭니다.

## <a name="cctrlviewm_strclass"></a><a name="m_strclass"></a>CCtrlView::m_strClass

뷰 클래스에 대 한 Windows 클래스 이름을 포함 합니다.

```
CString m_strClass;
```

## <a name="cctrlviewm_dwdefaultstyle"></a><a name="m_dwdefaultstyle"></a>CCtrlView::m_dwDefaultStyle

뷰 클래스의 기본 스타일을 포함합니다.

```
DWORD m_dwDefaultStyle;
```

### <a name="remarks"></a>설명

이 스타일은 창을 만들 때 적용됩니다.

## <a name="cctrlviewondraw"></a><a name="ondraw"></a>CCtrlView::에 그리기

지정된 장치 컨텍스트를 사용하여 `CCtrlView` 개체의 내용을 그리는 프레임워크에서 호출합니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
도면이 발생하는 장치 컨텍스트에 대한 포인터입니다.

### <a name="remarks"></a>설명

`OnDraw`일반적으로 *pDC에서*지정한 화면 장치 컨텍스트를 전달하는 화면 표시에 대해 호출됩니다.

## <a name="cctrlviewprecreatewindow"></a><a name="precreatewindow"></a>CCtrlView::P재현창

이 `CWnd` 개체에 연결된 Windows 창을 만들기 전에 호출됩니다.

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>매개 변수

*cs*<br/>
[생성TRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) 구조입니다.

### <a name="return-value"></a>Return Value

창 만들기를 계속해야 하는 경우 0이 아닙니다. 0을 사용하여 생성 실패를 나타냅니다.

### <a name="remarks"></a>설명

이 함수를 직접 호출하지 마십시오.

이 함수의 기본 구현은 NULL window 클래스 이름을 확인하고 적절한 기본값을 대체합니다. 이 멤버 함수를 재정의하여 창을 작성하기 전에 `CREATESTRUCT` 구조를 수정합니다.

파생된 각 `CCtrlView` 클래스는 `PreCreateWindow`의 재정의에 자체 기능을 추가합니다. 의도적으로 이러한 `PreCreateWindow` 파생은 문서화되지 않습니다. 각 클래스에 적합한 스타일과 스타일 간의 상호 종속성을 확인하려면 응용 프로그램의 기본 클래스에 대한 MFC 소스 코드를 검사할 수 있습니다. 을 선택하는 `PreCreateWindow`경우 응용 프로그램의 기본 클래스에 사용된 스타일이 MFC 소스 코드에서 수집한 정보를 사용하여 필요한 기능을 제공하는지 여부를 확인할 수 있습니다.

창 스타일 변경에 대한 자세한 내용은 [MFC에서 만든 창의 스타일 변경을](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CTreeView 클래스](../../mfc/reference/ctreeview-class.md)<br/>
[CListView 클래스](../../mfc/reference/clistview-class.md)<br/>
[리치에이트뷰 클래스](../../mfc/reference/cricheditview-class.md)
