---
title: 크탭베드판 클래스
ms.date: 11/04/2016
f1_keywords:
- CTabbedPane
- AFXTABBEDPANE/CTabbedPane
- AFXTABBEDPANE/CTabbedPane::DetachPane
- AFXTABBEDPANE/CTabbedPane::EnableTabAutoColor
- AFXTABBEDPANE/CTabbedPane::FloatTab
- AFXTABBEDPANE/CTabbedPane::GetTabArea
- AFXTABBEDPANE/CTabbedPane::GetTabWnd
- AFXTABBEDPANE/CTabbedPane::HasAutoHideMode
- AFXTABBEDPANE/CTabbedPane::IsTabLocationBottom
- AFXTABBEDPANE/CTabbedPane::ResetTabs
- AFXTABBEDPANE/CTabbedPane::SetTabAutoColors
- AFXTABBEDPANE/CTabbedPane::m_bTabsAlwaysTop
- AFXTABBEDPANE/CTabbedPane::m_pTabWndRTC
helpviewer_keywords:
- CTabbedPane [MFC], DetachPane
- CTabbedPane [MFC], EnableTabAutoColor
- CTabbedPane [MFC], FloatTab
- CTabbedPane [MFC], GetTabArea
- CTabbedPane [MFC], GetTabWnd
- CTabbedPane [MFC], HasAutoHideMode
- CTabbedPane [MFC], IsTabLocationBottom
- CTabbedPane [MFC], ResetTabs
- CTabbedPane [MFC], SetTabAutoColors
- CTabbedPane [MFC], m_bTabsAlwaysTop
- CTabbedPane [MFC], m_pTabWndRTC
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
ms.openlocfilehash: 17351eaed585ec34117a2ef825964fd51bd0d86b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365948"
---
# <a name="ctabbedpane-class"></a>크탭베드판 클래스

분리 가능한 탭이 포함된 창의 기능을 구현합니다.

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CTabbedPane : public CBaseTabbedPane
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CTabbedPane::CTabbedPane`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CTabbedPane::DetachPane](#detachpane)|(재정의 [CBaseTabbedPane::DetachPane](../../mfc/reference/cbasetabbedpane-class.md#detachpane).)|
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|탭의 자동 색 지정을 사용하거나 사용하지 않도록 설정합니다.|
|[CTabbedPane::FloatTab](#floattab)|창은 부동 이지만 창현재 분리 가능한 탭에 있는 경우에만. [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)|
|[CTabbedPane::GetTabArea](#gettabarea)|탭 창 내 탭 영역의 크기와 위치를 반환합니다.|
|[CTabbedPane::GetTabWnd](#gettabwnd)||
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|탭 창을 자동 숨기기 모드로 전환할 수 있는지 여부를 결정합니다. (재정의 [CBaseTabbedPane::HasAutoHideMode.)](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode)|
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|탭이 창의 맨 아래에 있는지 여부를 결정합니다.|
|[CTabbedPane::ResetTabs](#resettabs)|모든 탭 창을 기본 상태로 다시 설정합니다.|
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|자동 색 기능이 사용되는 경우 사용할 수 있는 사용자 지정 색 목록을 설정합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|애플리케이션에서 탭의 기본 위치입니다.|
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|사용자 지정 `CMFCTabCtrl` 파생 개체에 대한 런타임 클래스 정보입니다.|

## <a name="remarks"></a>설명

사용자가 두 번째 창의 캡션을 가리켜서 한 창을 다른 창에 연결하는 경우 프레임워크에서 자동으로 이 클래스의 인스턴스를 만듭니다. 프레임워크에서 만든 모든 탭 창의 ID는 -1입니다.

Outlook 스타일 탭 대신 일반 탭을 지정하려면 AFX_CBRS_REGULAR_TABS 스타일을 [CDockablePane:CreateEx](../../mfc/reference/cdockablepane-class.md#createex) 메서드로 전달합니다.

분리 가능한 탭을 포함하는 탭 창을 만드는 경우 프레임워크에서 자동으로 창을 삭제할 수 있으므로 포인터를 저장하면 안 됩니다. 탭 창에 대한 포인터를 가져오려면 `CBasePane::GetParentTabbedPane` 메서드를 호출합니다.

## <a name="example"></a>예제

이 예제에서는 `CTabbedPane` 개체를 만듭니다. 다음으로, 우리는 [CBaseTabbedPane를 사용::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) 추가 탭을 연결 합니다.

```cpp
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);

if (!pTabbededBar->Create (_T(""),
    this,
    CRect (0,
    0,
    200,
    200),
    TRUE,
    (UINT) -1,
    WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |
    WS_CLIPCHILDREN | CBRS_LEFT |
    CBRS_FLOAT_MULTI))
{
    TRACE0("Failed to create Solution Explorer bar\n");

    return FALSE;      // fail to create
}

pTabbededBar->AddTab (&m_wndClassView);
pTabbededBar->AddTab (&m_wndResourceView);

pTabbededBar->AddTab (&m_wndFileView);
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);

DockPane(pTabbededBar);
```

## <a name="example"></a>예제

탭 된 컨트롤 바 개체를 만드는 또 다른 방법은 [CDockablePane를 사용 하는 것입니다:AttachToTabWnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd). 메서드는 `AttachToTabWnd` [CDockablePane::SetTabbedPaneRTC에](../../mfc/reference/cdockablepane-class.md#settabbedpanertc)의해 설정 된 런타임 클래스 정보를 사용 하 여 탭 된 창 개체를 동적으로 만듭니다.

이 예제에서는 탭 창을 동적으로 만들고 두 탭을 연결한 다음 두 번째 탭을 분리 불가능하게 만듭니다.

```cpp
DockPane(&m_wndClassView);

CTabbedPane* pTabbedBar = NULL;
m_wndResourceView.AttachToTabWnd (&m_wndClassView,
    DM_SHOW,
    TRUE,
    (CDockablePane**) &pTabbedBar);

m_wndFileView.AttachToTabWnd (pTabbedBar,
    DM_SHOW,
    TRUE,
    (CDockablePane**) &pTabbedBar);

pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1,
    FALSE);
```

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CTabbedPane](../../mfc/reference/ctabbedpane-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxTabbedPane.h

## <a name="ctabbedpanedetachpane"></a><a name="detachpane"></a>CTabbedPane::D에타흐파네

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

【인】 *bHide*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="ctabbedpaneenabletabautocolor"></a><a name="enabletabautocolor"></a>CTabbedPane::인에이블탭오토컬러

탭의 자동 색 지정을 사용하거나 사용하지 않도록 설정합니다.

```
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE 탭의 자동 착색을 활성화합니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 정적 방법을 사용하여 응용 프로그램의 모든 탭 창에서 탭의 자동 착색을 사용하거나 사용하지 않도록 설정합니다. 이 기능을 사용하도록 설정하면 각 탭은 고유한 색상으로 채워져 있습니다. [CMFCBaseTabCtrl::GetAutoColors](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors) 메서드를 호출하여 탭의 색상을 만드는 데 사용되는 색상 목록을 찾을 수 있습니다.

[CTabbedPane::SetTabAutoColors](#settabautocolors)를 호출하여 탭에 사용할 색상 목록을 지정할 수 있습니다.

이 옵션은 기본적으로 사용되지 않습니다.

## <a name="ctabbedpanefloattab"></a><a name="floattab"></a>CTabbedPane::플로트탭

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>
【인】 *nTabID*<br/>
【인】 *독 방법*<br/>
【인】 *bHide*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="ctabbedpanegettabarea"></a><a name="gettabarea"></a>CTabbedPane::GetTabarea

탭된 창에서 탭 영역의 크기와 위치를 반환합니다.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>매개 변수

*rectTabAreaTop*<br/>
【아웃】 상단 탭 영역의 화면 좌표에 크기와 위치가 포함됩니다.

*rectTabAreaBottom*<br/>
【아웃】 하단 탭 영역의 화면 좌표에 크기와 위치가 포함됩니다.

### <a name="remarks"></a>설명

프레임워크는 이 메서드를 호출하여 사용자가 드래그하는 창을 도킹하는 방법을 결정합니다. 사용자가 대상 창의 탭 영역 위로 창을 끌면 프레임워크는 대상 창의 새 탭으로 창을 추가하려고 시도합니다. 그렇지 않으면 두 창을 구분하는 창 분할기를 사용하여 새 창 컨테이너를 만드는 것을 포함하는 대상 창의 측면에 창을 도킹하려고 시도합니다.

-derived 클래스에서 `CTabbedPane`이 메서드를 재정의하여 이 동작을 변경합니다.

## <a name="ctabbedpanegettabwnd"></a><a name="gettabwnd"></a>CTabbedPane:::GetTabWnd

```
CMFCTabCtrl* GetTabWnd() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="ctabbedpanehasautohidemode"></a><a name="hasautohidemode"></a>CTabbedPane::하스오토하이드모드

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="ctabbedpaneistablocationbottom"></a><a name="istablocationbottom"></a>CTabbedPane::IsTablocationbottom

탭이 창의 맨 아래에 있는지 여부를 결정합니다.

```
virtual BOOL IsTabLocationBottom() const;
```

### <a name="return-value"></a>Return Value

탭 영역이 탭창 하단에 있는 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="ctabbedpanem_btabsalwaystop"></a><a name="m_btabsalwaystop"></a>CTabbedPane::m_bTabsAlwaysTop

애플리케이션에서 탭의 기본 위치입니다.

```
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;
```

### <a name="remarks"></a>설명

이 정적 멤버를 TRUE로 설정하여 응용 프로그램의 모든 탭이 탭된 창의 맨 위에 표시하도록 합니다.

탭된 창을 만들려면 먼저 이 값을 설정해야 합니다.

기본값은 FALSE입니다.

## <a name="ctabbedpanem_ptabwndrtc"></a><a name="m_ptabwndrtc"></a>CTabbedPane::m_pTabWndRTC

사용자 지정 `CMFCTabCtrl` 파생 개체에 대한 런타임 클래스 정보입니다.

```
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;
```

### <a name="remarks"></a>설명

탭된 창 내에서 사용자 지정 탭창을 사용하는 `CMFCTabCtrl`경우 이 정적 멤버 변수를 -derived 개체의 런타임 클래스 정보에 대한 포인터로 설정합니다.

## <a name="ctabbedpaneresettabs"></a><a name="resettabs"></a>CTabbedPane::재설정탭

모든 탭 창을 기본 상태로 다시 설정합니다.

```
static void ResetTabs();
```

### <a name="remarks"></a>설명

이 메서드를 호출하여 탭된 모든 창을 기본 상태로 되돌리시고 호출할 때 이 메서드는 모든 탭된 창의 테두리 크기와 자동 색상 상태를 재설정합니다.

## <a name="ctabbedpanesettabautocolors"></a><a name="settabautocolors"></a>CTabbedPane::SetTabAutoColors

자동 색상 기능을 사용할 때 사용되는 사용자 지정 색상 목록을 설정합니다.

```
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>매개 변수

*arColors*<br/>
【인】 설정할 색상 배열이 포함되어 있습니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 자동 색상 기능을 사용 하는 경우 사용 되는 색상 목록을 사용자 지정 합니다. 이 함수는 정적 함수이며 응용 프로그램의 모든 탭된 창에 영향을 줍니다.

[CTabbedPane사용::인에이블탭오토컬러를](#enabletabautocolor) 사용하여 자동 색상 기능을 사용 하거나 비활성화할 수 있습니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)<br/>
[CBaseTabbedPane 클래스](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFC아웃아웃바 클래스](../../mfc/reference/cmfcoutlookbar-class.md)
