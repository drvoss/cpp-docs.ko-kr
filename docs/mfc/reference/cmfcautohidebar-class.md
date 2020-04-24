---
title: CMFCAutoHideBar 클래스
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
helpviewer_keywords:
- CMFCAutoHideBar [MFC], CMFCAutoHideBar
- CMFCAutoHideBar [MFC], AddAutoHideWindow
- CMFCAutoHideBar [MFC], AllowShowOnPaneMenu
- CMFCAutoHideBar [MFC], CalcFixedLayout
- CMFCAutoHideBar [MFC], Create
- CMFCAutoHideBar [MFC], GetFirstAHWindow
- CMFCAutoHideBar [MFC], GetVisibleCount
- CMFCAutoHideBar [MFC], OnShowControlBarMenu
- CMFCAutoHideBar [MFC], RemoveAutoHideWindow
- CMFCAutoHideBar [MFC], SetActiveInGroup
- CMFCAutoHideBar [MFC], SetRecentVisibleState
- CMFCAutoHideBar [MFC], ShowAutoHideWindow
- CMFCAutoHideBar [MFC], StretchPane
- CMFCAutoHideBar [MFC], UnSetAutoHideMode
- CMFCAutoHideBar [MFC], UpdateVisibleState
- CMFCAutoHideBar [MFC], m_nShowAHWndDelay
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
ms.openlocfilehash: 05f77dfba442f1ce4a375c8f225908799ece1788
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751767"
---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar 클래스

`CMFCAutoHideBar` 클래스는 자동 숨기기 기능을 구현하는 특수 도구 모음 클래스입니다.

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCAutoHideBar : public CPane
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||
|[CMFCAutoHideBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|( `CPane::AllowShowOnPaneMenu`을 재정의합니다.)|
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|[(재정의 CBasePane::석회화 레이아웃.)](../../mfc/reference/cbasepane-class.md#calcfixedlayout)|
|[CMFCAutoHideBar::Create](#create)|컨트롤 막대를 만들고 [CPane](../../mfc/reference/cpane-class.md) 개체에 연결합니다. [(재정의 CPane::만들기.)](../../mfc/reference/cpane-class.md#create)|
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|특수 창 메뉴를 표시하려고 할 때 프레임워크에서 호출됩니다. [(재정의 CPane::OnShowControlBar메뉴.)](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu)|
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|[(재정의 Cpane::SetActiveInGroup.)](../../mfc/reference/cpane-class.md#setactiveingroup)|
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||
|[CMFCAutoHideBar::StretchPane](#stretchpane)|창을 가로 또는 세로로 확장합니다. [(재정의 CBasePane::스트레치 파인](../../mfc/reference/cbasepane-class.md#stretchpane).)|
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|사용자가 [CMFCAutoHideButton 클래스](../../mfc/reference/cmfcautohidebutton-class.md) 위에 마우스 커서를 배치하는 순간과 프레임워크에 연결된 창이 표시되는 순간 사이의 시간 지연입니다.|

## <a name="remarks"></a>설명

사용자가 도킹 창을 자동 숨기기 모드로 전환하면 프레임워크에서 자동으로 `CMFCAutoHideBar` 개체를 만듭니다. 또한 필요한 [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) 및 [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) 개체를 만듭니다. 각 `CAutoHideDockSite` 개체는 개별 `CMFCAutoHideButton`에 연결됩니다.

`CMFCAutoHideBar` 클래스는 사용자의 마우스로 `CMFCAutoHideButton`을 가리킬 때 `CAutoHideDockSite`의 표시를 구현합니다. 도구 모음에서 WM_MOUSEMOVE 메시지를 받으면 `CMFCAutoHideBar`에서 타이머를 시작합니다. 타이머가 완료되면 도구 모음에 WM_TIMER 이벤트 알림을 보냅니다. 도구 모음은 마우스 포인터가 타이머가 시작될 때 배치되었던 것과 동일한 자동 숨기기 단추에 배치되었는지 확인하여 이 이벤트를 처리합니다. 그럴 경우 연결된 `CAutoHideDockSite`가 표시됩니다.

`m_nShowAHWndDelay`를 설정하여 타이머의 지연 길이를 제어할 수 있습니다. 기본값은 400ms입니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCAutoHideBar` 개체를 생성하고 해당 `GetDockSiteRow` 메서드를 사용하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxautohidebar.h

## <a name="cmfcautohidebaraddautohidewindow"></a><a name="addautohidewindow"></a>CMFC자동숨기기바::애드오토하이드윈도우

자동으로 숨길 수 있도록 하는 기능을 `CDockablePane` 창에 추가합니다.

```
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>매개 변수

*p자동숨기드*<br/>
【인】 숨기려는 창입니다.

*dw정렬*<br/>
【인】 응용 프로그램 창과 자동 숨기기 단추의 정렬을 지정하는 값입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

*dwAlignment* 매개 변수는 자동 숨기기 버튼이 응용 프로그램에 있는 위치를 나타냅니다. 이 매개 변수는 다음 값 중 하나가 될 수 있습니다.

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFC자동하이드바::허용쇼온파인메뉴

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcautohidebarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFC자동숨기기바::석회화레이아웃

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>매개 변수

【인】 *b스트레치*<br/>

【인】 *b호르츠 (주)*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcautohidebarcmfcautohidebar"></a><a name="cmfcautohidebar"></a>CMFC자동숨기기바::CMFC자동숨기드바

CMFCAutoHideBar 개체를 생성합니다.

```
CMFCAutoHideBar();
```

### <a name="remarks"></a>설명

## <a name="cmfcautohidebarcreate"></a><a name="create"></a>CMFC자동숨기기표시::만들기

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>

*dwStyle*<br/>

*rect*<br/>

*pParentWnd*<br/>

*nID*<br/>

*dw컨트롤바스타일*<br/>

*pContext*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcautohidebargetfirstahwindow"></a><a name="getfirstahwindow"></a>CMFC자동하이드바:::겟퍼스트아윈도우

애플리케이션의 첫 번째 자동 숨기기 창에 대한 포인터를 반환합니다.

```
CDockablePane* GetFirstAHWindow();
```

### <a name="return-value"></a>Return Value

애플리케이션의 첫 번째 자동 숨기기 창이거나, 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

## <a name="cmfcautohidebargetvisiblecount"></a><a name="getvisiblecount"></a>CMFC자동숨기기바::눈에 보이는 카운트

표시되는 자동 숨기기 단추 수를 가져옵니다.

```
int GetVisibleCount();
```

### <a name="return-value"></a>Return Value

표시되는 자동 숨기기 단추 수를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcautohidebarm_nshowahwnddelay"></a><a name="m_nshowahwnddelay"></a>CMFC자동숨기기바::m_nShowAHWndDelay

사용자가 [CMFCAutoHideButton 클래스](../../mfc/reference/cmfcautohidebutton-class.md) 위에 마우스 커서를 배치하는 순간과 프레임워크에 연결된 창이 표시되는 순간 사이의 시간 지연입니다.

```
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;
```

### <a name="remarks"></a>설명

사용자가 마우스 커서를 `CMFCAutoHideButton`에 배치하면 프레임워크에 연결된 창이 표시되기 전에 약간의 지연이 있습니다. 이 매개 변수는 밀리초 단위로 해당 지연의 길이를 결정합니다.

## <a name="cmfcautohidebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a>CMFC자동숨기기바::온쇼컨트롤바메뉴

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>매개 변수

[in] *CPoint*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcautohidebarremoveautohidewindow"></a><a name="removeautohidewindow"></a>CMFC자동숨기기바::리모크오토하이드윈도우

자동 숨기기 창을 제거하고 삭제합니다.

```
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```

### <a name="parameters"></a>매개 변수

CDockablePane* *pAutoHideWnd* 자동 숨기기 창을 제거할 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcautohidebarsetactiveingroup"></a><a name="setactiveingroup"></a>CMFC자동하이드바::셋액티브인그룹

자동 숨기기 막대에 활성으로 플래그를 지정합니다.

```
virtual void SetActiveInGroup(BOOL bActive);
```

### <a name="parameters"></a>매개 변수

【인】 BOOL *bActive* TRUE가 활성으로 설정; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

[CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup)을 참조하세요.

## <a name="cmfcautohidebarsetrecentvisiblestate"></a><a name="setrecentvisiblestate"></a>CMFC자동숨기기바::최근가보이는 상태

```cpp
void SetRecentVisibleState(BOOL bState);
```

### <a name="parameters"></a>매개 변수

*bState*<br/>
【인】 설정할 상태입니다.

### <a name="remarks"></a>설명

## <a name="cmfcautohidebarshowautohidewindow"></a><a name="showautohidewindow"></a>CMFC자동숨기기바::쇼오토하이드로우윈도우

자동 숨기기 창을 표시합니다.

```
BOOL ShowAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>매개 변수

*p자동숨기드*<br/>
【인】 표시할 창입니다.

*bShow*<br/>
【인】 TRUE창을 표시합니다.

*bDelay*<br/>
【인】 이 매개 변수는 무시됩니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcautohidebarstretchpane"></a><a name="stretchpane"></a>CMFC자동숨기기바::스트레치파인

`CMFCAutoHideButton` 개체에 맞게 자동 숨기기 막대의 크기를 축소된 상태로 조정합니다.

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>매개 변수

*nLength*<br/>
【인】 값은 기본 구현에서 사용되지 않습니다. 파생된 구현에서는 이 값을 사용하여 크기 조정된 창의 길이를 나타냅니다.

*bVert*<br/>
【인】 값은 기본 구현에서 사용되지 않습니다. 파생 구현에서 TRUE를 사용하여 자동 숨기기 막대가 수직으로 축소되는 경우를 처리하고 자동 숨기기 막대가 수평으로 축소되는 경우 FALSE를 처리합니다.

### <a name="return-value"></a>Return Value

크기 조정된 창의 결과 크기입니다.

### <a name="remarks"></a>설명

파생된 클래스는 이 메서드를 재정의하여 동작을 사용자 지정할 수 있습니다.

## <a name="cmfcautohidebarunsetautohidemode"></a><a name="unsetautohidemode"></a>CMFC자동숨기기::언셋오토하이드모드

자동 숨기기 막대의 그룹에 대해 자동 숨기기 모드를 사용하지 않도록 설정합니다.

```cpp
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)
```

### <a name="parameters"></a>매개 변수

[에서] pFirstBarInGroup 그룹의 첫 번째 자동 숨기기 막대에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmfcautohidebarupdatevisiblestate"></a><a name="updatevisiblestate"></a>CMFC자동숨기기바::업데이트가보이는 상태

자동 숨기기 막대를 다시 그려야 할 때 프레임워크에서 호출됩니다.

```cpp
void UpdateVisibleState();
```

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CPane 클래스](../../mfc/reference/cpane-class.md)<br/>
[CAutoHideDock사이트 클래스](../../mfc/reference/cautohidedocksite-class.md)<br/>
[CMFC자동숨기기버튼 클래스](../../mfc/reference/cmfcautohidebutton-class.md)
