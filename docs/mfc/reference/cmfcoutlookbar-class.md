---
title: CMFCOutlookBar 클래스
ms.date: 06/25/2018
f1_keywords:
- CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar::AllowDestroyEmptyTabbedPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanAcceptPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanSetCaptionTextToTabName
- AFXOUTLOOKBAR/CMFCOutlookBar::Create
- AFXOUTLOOKBAR/CMFCOutlookBar::CreateCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::DoesAllowDynInsertBefore
- AFXOUTLOOKBAR/CMFCOutlookBar::FloatTab
- AFXOUTLOOKBAR/CMFCOutlookBar::GetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::GetTabArea
- AFXOUTLOOKBAR/CMFCOutlookBar::IsMode2003
- AFXOUTLOOKBAR/CMFCOutlookBar::OnAfterAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnBeforeAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnScroll
- AFXOUTLOOKBAR/CMFCOutlookBar::RemoveCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::SetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::SetMode2003
helpviewer_keywords:
- CMFCOutlookBar [MFC], AllowDestroyEmptyTabbedPane
- CMFCOutlookBar [MFC], CanAcceptPane
- CMFCOutlookBar [MFC], CanSetCaptionTextToTabName
- CMFCOutlookBar [MFC], Create
- CMFCOutlookBar [MFC], CreateCustomPage
- CMFCOutlookBar [MFC], DoesAllowDynInsertBefore
- CMFCOutlookBar [MFC], FloatTab
- CMFCOutlookBar [MFC], GetButtonsFont
- CMFCOutlookBar [MFC], GetTabArea
- CMFCOutlookBar [MFC], IsMode2003
- CMFCOutlookBar [MFC], OnAfterAnimation
- CMFCOutlookBar [MFC], OnBeforeAnimation
- CMFCOutlookBar [MFC], OnScroll
- CMFCOutlookBar [MFC], RemoveCustomPage
- CMFCOutlookBar [MFC], SetButtonsFont
- CMFCOutlookBar [MFC], SetMode2003
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
ms.openlocfilehash: fe328cb0d857ff9154624d218b1b56362890ce81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369647"
---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar 클래스

Microsoft Outlook 2000 또는 Outlook 2003의 **탐색 창** 과 시각적으로 유사한 탭 창입니다. 개체에는 `CMFCOutlookBar` [CMFCOutlookBarTabCtrl 클래스](../../mfc/reference/cmfcoutlookbartabctrl-class.md) 개체와 일련의 탭이 포함되어 있습니다. 탭은 [CMFCOutlookBarPane 클래스](../../mfc/reference/cmfcoutlookbarpane-class.md) 개체 또는 `CWnd`-파생 개체일 수 있습니다. Outlook 표시줄은 사용자에게 일련의 단추와 표시 영역으로 나타납니다. 사용자가 단추를 클릭하면 해당 컨트롤 또는 단추 창이 표시됩니다.

## <a name="syntax"></a>구문

```cpp
class CMFCOutlookBar : public CBaseTabbedPane
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCOutlookBar::CMFCOutlookBar`|기본 생성자입니다.|
|`CMFCOutlookBar::~CMFCOutlookBar`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|빈 탭창을 파기할 수 있는지 여부를 지정합니다. (재정의 [CBaseTabbedPane:허용Destroy빈탭빈](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|
|[CMFC아웃바::캔수락파네](#canacceptpane)|Outlook 막대 창에 다른 창을 도킹할 수 있는지 여부를 결정합니다. (CDockablePane 재정의::CanAcceptPane.)|
|[CMFC아웃바::캔세트캡션텍스트To탭네임](#cansetcaptiontexttotabname)|탭된 창의 캡션이 활성 탭과 동일한 텍스트를 표시하는지 여부를 [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname)결정합니다.|
|[CMFC아웃바::만들기](#create)|Outlook 막대 컨트롤을 만듭니다.|
|[CMFC아웃바::사용자 지정 페이지 만들기](#createcustompage)|사용자 지정 Outlook 막대 탭을 만듭니다.|
|`CMFCOutlookBar::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFC아웃아웃바::DoesAllowDyn인더인](#doesallowdyninsertbefore)|사용자가 Outlook 막대의 외부 가장자리에 컨트롤 막대를 도킹할 수 있는지 여부를 결정합니다.|
|[CMFC아웃바::플로트탭](#floattab)|창은 부동 이지만 창현재 분리 가능한 탭에 있는 경우에만. [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)|
|[CMFC아웃바::GetButtons글꼴](#getbuttonsfont)|Outlook 막대의 단추에 텍스트 글꼴을 반환합니다.|
|[CMFC아웃바::겟탭에어리어](#gettabarea)|Outlook 막대에서 탭 영역의 크기와 위치를 반환합니다. (재정의 [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|
|`CMFCOutlookBar::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFC아웃아웃바::IsMode2003](#ismode2003)|Outlook 막대의 동작이 Microsoft Office Outlook 2003의 동작과 모방되는지 여부를 결정합니다(비고 참조).|
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|활성 탭이 애니메이션을 사용하여 설정된 후 [CMFCOutlookBarTabCtrl::SetActiveTab에](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) 의해 호출됩니다.|
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|[CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) 탭 페이지가 애니메이션을 사용하여 활성 탭으로 설정되기 전에 호출됩니다.|
|[CMFCOutlookBar::OnScroll](#onscroll)|Outlook 막대가 위 또는 아래로 스크롤되는 경우 프레임 워크에서 호출됩니다.|
|[CMFC아웃바::사용자 지정 페이지 제거](#removecustompage)|사용자 지정 Outlook 막대 탭을 제거합니다.|
|[CMFC아웃아웃바:::버튼글꼴](#setbuttonsfont)|Outlook 막대의 단추에 텍스트의 글꼴을 설정합니다.|
|[CMFC아웃바::SetMode2003](#setmode2003)|Outlook 막대의 동작이 Outlook 2003의 동작과 모방하는지 여부를 지정합니다(설명 참조).|

## <a name="remarks"></a>설명

Outlook 막대의 예는 [OutlookDemo 샘플: MFC OutlookDemo 응용 프로그램을](../../overview/visual-cpp-samples.md)참조하십시오.

## <a name="implementing-the-outlook-bar"></a>Outlook 표시줄 구현

애플리케이션에서 `CMFCOutlookBar` 컨트롤을 사용하려면 다음 단계를 수행합니다.

1. `CMFCOutlookBar` 개체를 주 프레임 창 클래스에 포함합니다.

    ```cpp
    class CMainFrame : public CMDIFrameWnd
    {
        // ...
        CMFCOutlookBar m_wndOutlookBar;
        CMFCOutlookBarPane m_wndOutlookPane;
        // ...
    };
    ```

1. 메인 프레임에서 WM_CREATE 메시지를 처리할 때 [CMFCOutlookBar::Create](#create) 메서드를 호출하여 Outlook 막대 탭 컨트롤을 만듭니다.

    ```cpp
    m_wndOutlookBar.Create (_T("Shortcuts"),
        this,
        CRect (0, 0, 100, 100),
        ID_VIEW_OUTLOOKBAR,
        WS_CHILD | WS_VISIBLE | CBRS_LEFT);
    ```

1. `CMFCOutlookBarTabCtrl` [CBaseTabbedPane::GetBaseWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow)를 사용하여 기본에 대한 포인터를 가져옵니다.

    ```cpp
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();
    ```

1. 버튼이 포함된 각 탭에 대해 [CMFCOutlookBarPane 클래스](../../mfc/reference/cmfcoutlookbarpane-class.md) 개체를 만듭니다.

    ```cpp
    m_wndOutlookPane.Create(&m_wndOutlookBar,
        AFX_DEFAULT_TOOLBAR_STYLE,
        ID_OUTLOOK_PANE_GENERAL,
        AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);

    // make the Outlook pane detachable (enable docking)
    m_wndOutlookPane.EnableDocking(CBRS_ALIGN_ANY);

    // add buttons
    m_wndOutlookPane.AddButton(theApp.LoadIcon (IDR_MAINFRAME),
        "About",
        ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON),
        "Open",
        ID_FILE_OPEN);
    ```

1. [CMFCOutlookBarTabCtrl::AddTab을](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) 호출하여 각 새 *bDetachable* 탭을 추가합니다. 또는 [CMFCOutlookBarTabCtrl::AddControl을](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) 사용하여 분리 가능한 페이지를 추가합니다.

    ```cpp
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);
    ```

1. `CWnd`-파생 된 컨트롤 (예 : [CMFCShellTreeCtrl 클래스)을](../../mfc/reference/cmfcshelltreectrl-class.md)탭으로 추가하려면 컨트롤을 만들고 [CMFCOutlookBarTabCtrl ::AddTab을](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) 호출하여 Outlook 막대에 추가합니다.

> [!NOTE]
> 각 [CMFCOutlookBarPane 클래스](../../mfc/reference/cmfcoutlookbarpane-class.md) 개체 및 각 `CWnd`파생 개체에 대해 고유한 컨트롤 아이디를 사용해야 합니다.

런타임시 새 페이지를 동적으로 추가하거나 삭제하려면 [CMFCOutlookBar::Create 사용자 지정 페이지](#createcustompage) 및 [CMFCOutlookBar::RemoveCustomPage](#removecustompage)를 사용합니다.

## <a name="outlook-2003-mode"></a>전망 2003 모드

Outlook 2003 모드에서 탭 단추는 Outlook 막대 창의 맨 아래에 배치됩니다. 단추를 표시할 공간이 충분하지 않으면 창 아래쪽을 따라 도구 모음 모양 영역에 아이콘으로 표시됩니다.

[CMFCOutlookBar::SetMode2003을](#setmode2003) 사용하여 Outlook 2003 모드를 활성화합니다. [CMFCOutlookBarTabCtrl::SetToolbarImageList를](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) 사용하여 Outlook 표시줄 하단에 표시되는 아이콘이 포함된 비트맵을 설정합니다. 비트맵의 아이콘은 탭 인덱스로 정렬해야 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxoutlookbar.h

## <a name="cmfcoutlookbarallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a>CMFC아웃바::허용파괴빈탭빈판

빈 탭창을 파기할 수 있는지 여부를 지정합니다.

```cpp
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Return Value

빈 탭 창을 파괴 할 수있는 경우 TRUE; 그렇지 않으면 false입니다. 기본 구현은 항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

빈 탭된 창을 삭제할 수 없는 경우 프레임워크는 대신 창을 숨깁니다.

## <a name="cmfcoutlookbarcanacceptpane"></a><a name="canacceptpane"></a>CMFC아웃바::캔수락파네

Outlook 막대 창에 다른 창을 도킹할 수 있는지 여부를 결정합니다.

```cpp
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 이 창에 도킹되는 다른 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

다른 창을 Outlook 막대 창에 도킹할 수 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

Outlook 막대가 Outlook 2003 모드에 있는 경우 도킹이 지원되지 않으므로 반환 값은 FALSE입니다.

*pBar* 매개 변수가 NULL이면 이 메서드는 FALSE를 반환합니다.

그렇지 않으면 이 메서드는 기본 메서드 [CBasePane:CanAcceptPane로](../../mfc/reference/cbasepane-class.md#canacceptpane)작동합니다.

## <a name="cmfcoutlookbarcansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a>CMFC아웃바::캔세트캡션텍스트To탭네임

탭된 창의 캡션이 활성 탭과 동일한 텍스트를 표시하는지 여부를 결정합니다.

```cpp
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Return Value

TRUE Outlook 막대 창 캡션이 활성 탭의 텍스트로 자동으로 설정된 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

[CBaseTabbedPane::인에이블셋캡션TextToTabName을](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) 사용하여 이 기능을 사용하거나 비활성화합니다.

Outlook 2003 모드에서는 이 설정이 항상 활성화됩니다.

## <a name="cmfcoutlookbarcreate"></a><a name="create"></a>CMFC아웃바::만들기

Outlook 막대 컨트롤을 만듭니다.

```cpp
virtual BOOL Create(
    LPCTSTR lpszCaption,
    CWnd* pParentWnd,
    const RECT& rect,
    UINT nID,
    DWORD dwStyle,
    DWORD dwControlBarStyle=AFX_CBRS_RESIZE,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>매개 변수

*lpszCaption*<br/>
【인】 창 캡션을 지정합니다.

*pParentWnd*<br/>
【인】 상위 창에 대한 포인터를 지정합니다. NULL이 아니어야 합니다.

*rect*<br/>
【인】 Outlook 막대 크기와 위치를 픽셀 단위로 지정합니다.

*nID*<br/>
【인】 컨트롤 ID를 지정합니다. 응용 프로그램에 사용되는 다른 컨트롤 아이디와 구별되어야 합니다.

*dwStyle*<br/>
【인】 원하는 컨트롤 막대 스타일을 지정합니다. 가능한 값은 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)을 참조하십시오.

*dw컨트롤바스타일*<br/>
【인】 특수 라이브러리 정의 스타일을 지정합니다.

*pContext*<br/>
【인】 컨텍스트를 만듭니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

두 단계로 `CMFCOutlookBar` 객체를 생성합니다. 먼저 생성자 호출 한 `Create`다음 outlook 막대 컨트롤을 만들고 `CMFCOutlookBar` 개체에 연결 하는 호출 합니다.

*dwControlBarStyle에서*지정할 사용 가능한 라이브러리 정의 스타일 목록은 [CBasePane::CreateEx를](../../mfc/reference/cbasepane-class.md#createex) 참조하십시오.

### <a name="example"></a>예제

다음 예제에서는 `Create` `CMFCOutlookBar` 클래스의 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 Outlook [다중 보기 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]

## <a name="cmfcoutlookbarcreatecustompage"></a><a name="createcustompage"></a>CMFC아웃바::사용자 지정 페이지 만들기

사용자 지정 Outlook 막대 탭을 만듭니다.

```cpp
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,
    BOOL bActivatePage=TRUE,
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,
    BOOL bEnableTextLabels=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszPageName*<br/>
【인】 페이지 레이블입니다.

*b활성화 페이지*<br/>
【인】 TRUE이면 페이지가 만들 때 활성화됩니다.

*dw사용 도킹*<br/>
【인】 페이지가 분리될 때 활성화된 도킹 면을 지정하는 CBRS_ALIGN_ 플래그의 조합입니다.

*bEnable텍스트 레이블*<br/>
【인】 TRUE이면 페이지에 있는 단추에 대해 텍스트 레이블이 활성화됩니다.

### <a name="return-value"></a>Return Value

새로 만든 페이지에 대한 포인터 또는 생성에 실패한 경우 NULL입니다.

### <a name="remarks"></a>설명

사용자가 사용자 지정 Outlook 막대 페이지를 만들 수 있도록 하려면 이 메서드를 사용 합니다. 응용 프로그램당 최대 100페이지를 만들 수 있습니다. 페이지 컨트롤 아이디는 0xF000부터 시작합니다. 사용자 지정 Outlook 막대 페이지의 총 수가 100페이지를 초과하면 생성이 실패합니다.

[CMFCOutlookBar::제거 사용자 지정 페이지를](#removecustompage) 삭제 합니다.

## <a name="cmfcoutlookbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CMFC아웃아웃바::DoesAllowDyn인더인

사용자가 Outlook 막대의 바깥쪽 가장자리에 창을 도킹할 수 있는지 여부를 지정합니다.

```
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Return Value

기본 구현은 FALSE를 반환합니다.

### <a name="remarks"></a>설명

프레임워크는 동적 `DoesAllowDynInsertBefore` 창을 도킹할 위치를 찾는 경우 메서드를 호출합니다. 함수가 FALSE를 반환하는 경우 프레임워크는 창의 외부 가장자리에 있는 동적 창의 도킹을 허용하지 않습니다.

일반적으로 Outlook 막대를 정적 부동 컨트롤로 만듭니다. 파생 클래스에서 이 함수를 재정의하고 TRUE를 반환하여 이 동작을 변경할 수 있습니다.

> [!NOTE]
> 동적 창은 도킹 할 때 도킹 된 정적 창의 상태를 확인하므로 가능하면 정적 창 후에 동적 창을 도킹해야합니다.

## <a name="cmfcoutlookbarfloattab"></a><a name="floattab"></a>CMFC아웃바::플로트탭

창을 부동합니다.

```cpp
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 부동 창에 대한 포인터입니다.

*nTabID*<br/>
【인】 부동 할 탭의 0 기반 인덱스입니다.

*dockMethod*<br/>
【인】 창을 플로트로 만드는 데 사용할 방법을 지정합니다.  자세한 내용은 [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)을 참조하십시오.

*bHide*<br/>
【인】 부동 하기 전에 창을 숨기기 위해 TRUE; 그렇지 않으면 false입니다. 이 메서드의 기본 클래스 버전과 달리 이 매개 변수에는 기본값이 없습니다.

### <a name="return-value"></a>Return Value

창이 떠 있는 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) Outlook 막대 컨트롤의 마지막 남은 탭을 플로팅할 수 없다는 점을 제외하면 다음과 같습니다.

## <a name="cmfcoutlookbargetbuttonsfont"></a><a name="getbuttonsfont"></a>CMFC아웃바::GetButtons글꼴

Outlook 막대의 페이지 단추 탭에서 텍스트 글꼴을 반환합니다.

```cpp
CFont* GetButtonsFont() const;
```

### <a name="return-value"></a>Return Value

Outlook 막대 단추 탭에 텍스트를 표시하는 데 사용되는 글꼴 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 Outlook 페이지 단추 탭에 텍스트를 표시하는 데 사용되는 글꼴을 검색합니다. [CMFCOutlookBar::SetButtonsFont에서](#setbuttonsfont)호출하여 글꼴을 설정할 수 있습니다.

## <a name="cmfcoutlookbargettabarea"></a><a name="gettabarea"></a>CMFC아웃바::겟탭에어리어

Outlook 막대에서 탭 영역의 크기와 위치를 결정합니다.

```cpp
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>매개 변수

*rectTabAreaTop*<br/>
【아웃】 함수가 반환될 때 상단 탭 영역의 크기와 위치(클라이언트 좌표)를 포함합니다.

*rectTabAreaBottom*<br/>
【아웃】 함수가 반환될 때 아래쪽 탭 영역의 크기와 위치(클라이언트 좌표)를 포함합니다.

### <a name="remarks"></a>설명

프레임워크는 이 메서드를 호출하여 대상 창에 대한 도킹 유형을 결정합니다. 프레임워크에서 사용자가 대상 창의 탭 영역에 도킹할 창을 드래그한다고 결정하면 첫 번째 창을 대상 창의 새 탭으로 추가하려고 시도합니다. 그렇지 않으면 대상 창의 적절한 쪽에 첫 번째 창을 도킹하려고 시도합니다. 프레임워크는 추가 도킹 창을 수용할 수 있도록 슬라이더가 있는 새 컨테이너를 만듭니다.

Outlook 막대가 `GetTabArea` 정적인 경우 Outlook 막대의 전체 클라이언트 영역을 반환하는 기본 구현입니다. 즉, Outlook 막대를 띄워줄 수 없는 경우입니다. 그렇지 않으면 페이지 버튼이 Outlook 막대 컨트롤의 위쪽과 아래쪽에 있는 영역을 반환합니다.

이 동작을 변경 하려면 `CMFCOutlookBar` 파생 된 클래스에서이 메서드를 재정의 합니다.

## <a name="cmfcoutlookbarismode2003"></a><a name="ismode2003"></a>CMFC아웃아웃바::IsMode2003

Outlook 막대의 동작이 Microsoft Office Outlook 2003의 동작을 모방하는지 여부를 지정합니다.

```cpp
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Return Value

Outlook 막대가 마이크로 소프트 오피스 2003 모드에서 실행되는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

[CMFCOutlookBar::SetMode2003을](#setmode2003)사용하여 이 모드를 활성화할 수 있습니다.

## <a name="cmfcoutlookbaronafteranimation"></a><a name="onafteranimation"></a>CMFC아웃아웃바::온애프터애니메이션

활성 탭이 애니메이션을 사용하여 설정된 후 [CMFCOutlookBarTabCtrl::SetActiveTab에](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) 의해 호출됩니다.

```cpp
virtual void OnAfterAnimation(int nPage);
```

### <a name="parameters"></a>매개 변수

*n페이지*<br/>
【인】 활성화된 탭 페이지의 0기준 인덱스입니다.

### <a name="remarks"></a>설명

활성 탭을 설정하는 시각적 효과는 애니메이션을 활성화했는지 여부에 따라 달라집니다. 자세한 내용은 [CMFCOutlookBarTabCtrl::인에이블애니메이션](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation)을 참조하십시오.

## <a name="cmfcoutlookbaronbeforeanimation"></a><a name="onbeforeanimation"></a>CMFC아웃아웃바::온프애니메이션

[CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) 탭 페이지가 애니메이션을 사용하여 활성 탭으로 설정되기 전에 호출됩니다.

```cpp
virtual BOOL OnBeforeAnimation(int nPage);
```

### <a name="parameters"></a>매개 변수

*n페이지*<br/>
【인】 활성화되도록 설정될 탭 페이지의 0기준 인덱스입니다.

### <a name="return-value"></a>Return Value

새 활성 탭을 설정할 때 애니메이션을 사용해야 하는 경우 TRUE를 반환하거나 애니메이션을 사용하지 않도록 설정해야 하는 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcoutlookbaronscroll"></a><a name="onscroll"></a>CMFC아웃아웃바::온스크롤

Outlook 막대가 위 또는 아래로 스크롤되는 경우 프레임 워크에서 호출됩니다.

```cpp
virtual void OnScroll(BOOL bDown);
```

### <a name="parameters"></a>매개 변수

*bDown*<br/>
【인】 Outlook 막대가 아래로 스크롤되는 경우 TRUE또는 위로 스크롤하는 경우 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcoutlookbarremovecustompage"></a><a name="removecustompage"></a>CMFC아웃바::사용자 지정 페이지 제거

사용자 지정 Outlook 막대 탭 페이지를 제거합니다.

```cpp
BOOL RemoveCustomPage(
    UINT uiPage,
    CMFCOutlookBarTabCtrl* pTargetWnd);
```

### <a name="parameters"></a>매개 변수

*uiPage*<br/>
【인】 상위 Outlook 창에서 페이지의 0기반 인덱스입니다.

*pTargetWnd*<br/>
【인】 부모 Outlook 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

사용자 지정 페이지가 성공적으로 제거된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

사용자 지정 페이지를 삭제하려면 이 함수를 호출합니다. 페이지가 제거되면 컨트롤 ID가 사용 가능한 ID 풀로 반환됩니다.

제거할 페이지가 현재 있는 [CMFCOutlookBarTabCtrl 클래스](../../mfc/reference/cmfcoutlookbartabctrl-class.md) 개체에 대한 포인터를 제공해야 합니다. 사용자는 다른 Outlook 막대 간에 분리 가능한 페이지를 이동할 수 있지만 사용자 지정 페이지에 대한 정보는 [CMFCOutlookBar::CreateCustomPage라고](#createcustompage)하는 Outlook 막대 개체에 있습니다.

[CBaseTabbedPane::GetBaseWindow를](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) 사용하여 Outlook 창에 대한 포인터를 가져옵니다.

## <a name="cmfcoutlookbarsetbuttonsfont"></a><a name="setbuttonsfont"></a>CMFC아웃아웃바:::버튼글꼴

Outlook 막대의 단추에 텍스트의 글꼴을 설정합니다.

```cpp
void SetButtonsFont(
    CFont* pFont,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
【인】 새 글꼴을 지정합니다.

*bRedraw*<br/>
【인】 TRUE이면 Outlook 막대가 다시 그려집니다.

### <a name="remarks"></a>설명

이 방법을 사용하여 Outlook 탭 페이지 단추에 표시되는 텍스트에 대한 글꼴을 설정합니다.

## <a name="cmfcoutlookbarsetmode2003"></a><a name="setmode2003"></a>CMFC아웃바::SetMode2003

Outlook 막대의 동작이 Outlook 2003의 동작과 모방하는지 여부를 지정합니다.

```cpp
void SetMode2003(BOOL bMode2003=TRUE);
```

### <a name="parameters"></a>매개 변수

*bMode2003*<br/>
【인】 TRUE인 경우 Office 2003 모드가 활성화되어 있습니다.

### <a name="remarks"></a>설명

이 기능을 사용하여 Office 2003 모드를 사용 하거나 사용하지 않도록 설정합니다. 이 모드에서 Outlook 막대에는 사용자 지정 버튼이있는 추가 도구 모음이 있습니다. Outlook 막대의 동작은 Microsoft Office 2003의 Outlook 막대 동작을 준수합니다.

기본적으로 이 모드는 비활성화됩니다.

> [!NOTE]
> 이 함수는 [CMFCOutlookBar::Create](#create)전에 호출되어야 합니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CBaseTabbedPane 클래스](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)<br/>
[CMFC아웃아웃바파네 클래스](../../mfc/reference/cmfcoutlookbarpane-class.md)
