---
title: CMDIChildWndEx 클래스
ms.date: 10/18/2018
f1_keywords:
- CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx::ActivateTopLevelFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AdjustDockingLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnMDITabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnTaskBarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnWindowsList
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPaneLeftOf
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableAutoHidePanes
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableDocking
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDockingManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDocumentName
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameIcon
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameText
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabProxyWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarPreviewWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetToolbarButtonToolTipText
- AFXMDICHILDWNDEX/CMDIChildWndEx::InsertPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::InvalidateIconicBitmaps
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsPointNearDockSite
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsReadOnly
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsRegisteredWithTaskbarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarTabsSupportEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicLivePreviewBitmap
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicThumbnail
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnMoveMiniFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnSetPreviewMode
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailStretch
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnUpdateFrameTitle
- AFXMDICHILDWNDEX/CMDIChildWndEx::PaneFromPoint
- AFXMDICHILDWNDEX/CMDIChildWndEx::RecalcLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::RegisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::RemovePaneFromDockManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabActive
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabOrder
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabProperties
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::ShowPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::UnregisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::UpdateTaskbarTabIcon
helpviewer_keywords:
- CMDIChildWndEx [MFC], ActivateTopLevelFrame
- CMDIChildWndEx [MFC], AddPane
- CMDIChildWndEx [MFC], AddTabbedPane
- CMDIChildWndEx [MFC], AdjustDockingLayout
- CMDIChildWndEx [MFC], CanShowOnMDITabs
- CMDIChildWndEx [MFC], CanShowOnTaskBarTabs
- CMDIChildWndEx [MFC], CanShowOnWindowsList
- CMDIChildWndEx [MFC], DockPane
- CMDIChildWndEx [MFC], DockPaneLeftOf
- CMDIChildWndEx [MFC], EnableAutoHidePanes
- CMDIChildWndEx [MFC], EnableDocking
- CMDIChildWndEx [MFC], EnableTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], GetDockingManager
- CMDIChildWndEx [MFC], GetDocumentName
- CMDIChildWndEx [MFC], GetFrameIcon
- CMDIChildWndEx [MFC], GetFrameText
- CMDIChildWndEx [MFC], GetPane
- CMDIChildWndEx [MFC], GetRelatedTabGroup
- CMDIChildWndEx [MFC], GetTabbedPane
- CMDIChildWndEx [MFC], GetTabProxyWnd
- CMDIChildWndEx [MFC], GetTaskbarPreviewWnd
- CMDIChildWndEx [MFC], GetTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], GetToolbarButtonToolTipText
- CMDIChildWndEx [MFC], InsertPane
- CMDIChildWndEx [MFC], InvalidateIconicBitmaps
- CMDIChildWndEx [MFC], IsPointNearDockSite
- CMDIChildWndEx [MFC], IsReadOnly
- CMDIChildWndEx [MFC], IsRegisteredWithTaskbarTabs
- CMDIChildWndEx [MFC], IsTabbedPane
- CMDIChildWndEx [MFC], IsTaskbarTabsSupportEnabled
- CMDIChildWndEx [MFC], IsTaskbarThumbnailClipRectEnabled
- CMDIChildWndEx [MFC], m_dwDefaultTaskbarTabPropertyFlags
- CMDIChildWndEx [MFC], OnGetIconicLivePreviewBitmap
- CMDIChildWndEx [MFC], OnGetIconicThumbnail
- CMDIChildWndEx [MFC], OnMoveMiniFrame
- CMDIChildWndEx [MFC], OnPressTaskbarThmbnailCloseButton
- CMDIChildWndEx [MFC], OnSetPreviewMode
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailActivate
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailMouseActivate
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailStretch
- CMDIChildWndEx [MFC], OnUpdateFrameTitle
- CMDIChildWndEx [MFC], PaneFromPoint
- CMDIChildWndEx [MFC], RecalcLayout
- CMDIChildWndEx [MFC], RegisterTaskbarTab
- CMDIChildWndEx [MFC], RemovePaneFromDockManager
- CMDIChildWndEx [MFC], SetRelatedTabGroup
- CMDIChildWndEx [MFC], SetTaskbarTabActive
- CMDIChildWndEx [MFC], SetTaskbarTabOrder
- CMDIChildWndEx [MFC], SetTaskbarTabProperties
- CMDIChildWndEx [MFC], SetTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], ShowPane
- CMDIChildWndEx [MFC], UnregisterTaskbarTab
- CMDIChildWndEx [MFC], UpdateTaskbarTabIcon
ms.assetid: d39fec06-0bd6-4271-917d-35aae3b24d8e
ms.openlocfilehash: cdc82ef48bacfe4d5b8d90222e7055c5fbe8b4a1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754564"
---
# <a name="cmdichildwndex-class"></a>CMDIChildWndEx 클래스

클래스는 `CMDIChildWndEx` Windows 다중 문서 인터페이스(MDI) 자식 창의 기능을 제공합니다. [CMDIChildWnd 클래스의](../../mfc/reference/cmdichildwnd-class.md)기능을 확장합니다. MDI 애플리케이션에서 특정 MFC 클래스를 사용하면 프레임워크에 이 클래스가 필요합니다.

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMDIChildWndEx : public CMDIChildWnd
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMDIChildWndEx::활성화탑레벨프레임](#activatetoplevelframe)|작업 표시줄 탭에서 응용 프로그램을 활성화해야 하는 경우 최상위 프레임을 활성화하기 위해 프레임워크에서 내부적으로 호출합니다.|
|`CMDIChildWndEx::AddDockSite`|이 메서드는 사용 하거나 구현 되지 않습니다.|
|[CMDIChildWndEx::애드파인](#addpane)|창을 추가합니다.|
|[CMDIChildWndEx::애드탭베드파인](#addtabbedpane)|탭된 창을 추가합니다.|
|[CMDIChildWndEx::조정도킹레이아웃](#adjustdockinglayout)|도킹 레이아웃을 조정합니다.|
|[CMDIChildWndEx::캔쇼온MDITabs](#canshowonmditabs)||
|[CMDIChildWndEx::캔쇼온태스크바탭](#canshowontaskbartabs)|이 MDI 자식이 Windows 7 작업 표시줄 탭에 표시될 수 있는지 여부를 프레임워크에 알려줍니다.|
|[CMDIChildWndEx::캔쇼온윈도우리스트](#canshowonwindowslist)|[CMFCWindowsManagerDialog 클래스](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 대화 상자에 MDI 자식 창 이름을 표시할 수 있는 경우 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.|
|`CMDIChildWndEx::CreateObject`|이 클래스 형식의 동적 인스턴스를 만들기 위해 프레임 워크에서 호출 합니다.|
|[CMDIChildWndEx::DockPane](#dockpane)|창을 도킹합니다.|
|[CMDIChildWndEx::DockPaneLeftOf](#dockpaneleftof)|창을 다른 창의 왼쪽에 도킹합니다.|
|[CMDIChildWndEx::인에이블오토하이드파인즈](#enableautohidepanes)|창이 창의 지정된 면에 도킹될 때 자동 숨기기 모드를 활성화합니다.|
|[CMDIChildWndEx::인에이블도킹](#enabledocking)|자식 창을 주 프레임에 도킹할 수 있습니다.|
|[CMDIChildWndEx::인에이블태스크바썸네일클립렉트](#enabletaskbarthumbnailcliprect)|창의 클라이언트 영역 일부를 자동으로 선택하거나 비활성화하여 작업 표시줄에 해당 창의 축소판으로 표시합니다.|
|[CMDIChildWndEx::GetDockingManager](#getdockingmanager)||
|[CMDIChildWndEx::GetDocumentName](#getdocumentname)|MDI 자식 창에 표시되는 문서의 이름을 반환합니다.|
|[CMDIChildWndEx::겟프레임아이콘](#getframeicon)|MDI 자식 창 아이콘을 검색 하는 프레임 워크에 의해 호출 됩니다.|
|[CMDIChildWndEx::GetFrameText](#getframetext)|MDI 자식 창에 대 한 텍스트를 검색 하는 프레임 워크에 의해 호출 됩니다.|
|[CMDIChildWndEx::겟파인](#getpane)|지정된 컨트롤 ID로 창을 찾습니다.|
|[CMDIChildWndEx::관련 탭 그룹](#getrelatedtabgroup)||
|[CMDIChildWndEx::GetTabbedPane](#gettabbedpane)|탭된 문서로 변환된 포함된 도킹 창에 대한 포인터를 반환합니다.|
|[CMDIChildWndEx::GetTab프록시Wnd](#gettabproxywnd)|실제로 Windows 7 작업 표시줄 탭에 등록 된 탭 프록시 창을 반환합니다.|
|[CMDIChildWndEx::GetTaskbar프리뷰](#gettaskbarpreviewwnd)|Windows 7 작업 표시줄 탭 축소판에 표시할 자식 창(일반적으로 보기 또는 분할창)을 가져와야 할 때 프레임워크에서 호출합니다.|
|[CMDIChildWndEx::겟태스크바썸네일클립렉트](#gettaskbarthumbnailcliprect)|작업 표시줄에서 해당 창의 축소판으로 표시할 창의 클라이언트 영역 의 일부를 선택해야 할 때 프레임워크에서 호출합니다.|
|`CMDIChildWndEx::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 호출합니다.|
|[CMDIChildWndEx::gettoolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|도구 모음 단추에 대한 도구 설명을 검색하려면 프레임워크에서 호출합니다.|
|[CMDIChildWndEx::삽입판](#insertpane)|지정된 창을 도킹 관리자에 등록합니다.|
|[CMDIChildWndEx::무효화아이코닉비트맵](#invalidateiconicbitmaps)|MDI 자식의 상징적인 비트맵 표현을 무효화합니다.|
|[CMDIChildWndEx::이스포인트니어독사이트](#ispointneardocksite)|지정된 점이 도크 사이트 근처에 있는지 여부를 결정합니다.|
|[CMDIChildWndEx::IsRead전용](#isreadonly)|하위 창에 표시되는 문서가 읽기 전용인 경우 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.|
|[CMDIChildWndEx::등록된작업 표시줄탭](#isregisteredwithtaskbartabs)|MDI 자식이 Windows 7 작업 표시줄 탭에 성공적으로 등록된 경우 TRUE를 반환합니다.|
|[CMDIChildWndEx::이스탭베드파인](#istabbedpane)|MDI 자식 창에 도킹 창이 포함되어 있는 경우 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.|
|[CMDIChildWndEx::IsTaskbarTabs지원 지원](#istaskbartabssupportenabled)|MDI 자식이 Windows 7 작업 표시줄 탭에 나타날 수 있는지 여부를 알려줍니다.|
|[CMDIChildWndEx::이태스크바썸네일클립렉트사용](#istaskbarthumbnailcliprectenabled)|작업 표시줄에서 해당 창의 축소판 그림으로 표시할 창의 클라이언트 영역 의 일부를 자동으로 선택할 수 있는지 여부를 알려줍니다.|
|[CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags](#m_dwdefaulttaskbartabpropertyflags)|탭 (MDI 자식)가 Windows 7 작업 표시 줄 탭에 등록 될 때 SetTaskbarTabProperties 메서드에 프레임 워크에 의해 전달 되는 플래그의 조합입니다. 기본 조합은 STPF_USEAPPTHUMBNAILWHENACTIVE &#124; STPF_USEAPPPEEKWHENACTIVE.|
|[CMDIChildWndEx::OnGetIconicLive프리뷰비트맵](#ongeticoniclivepreviewbitmap)|MDI 자식의 라이브 미리 보기를 위해 비트맵을 가져와야 할 때 프레임워크에서 호출합니다.|
|[CMDIChildWndEx::OnGetIconic엄지손가락](#ongeticonicthumbnail)|MDI 자식의 상징적 인 축소판 그림에 대한 비트 맵을 가져와야 할 때 프레임 워크에서 호출됩니다.|
|[CMDIChildWndEx::온무브미니프레임](#onmoveminiframe)|프레임 워크에서 호출하여 미니 프레임 창을 이동합니다.|
|[CMDIChildWndEx::OnpressTaskbarThmb네일클로즈버튼](#onpresstaskbarthmbnailclosebutton)|사용자가 작업 표시 줄 탭 축소판에 닫기 단추를 누를 때 프레임 워크에 의해 호출 됩니다.|
|[CMDIChildWndEx::온셋프리뷰모드](#onsetpreviewmode)|인쇄 미리 보기 모드를 입력하거나 종료하려면 프레임워크에서 호출됩니다.|
|[CMDIChildWndEx::OnTaskbarTab엄지네일활성화](#ontaskbartabthumbnailactivate)|작업 표시줄 탭 축소판이 WM_ACTIVATE 메시지를 처리해야 하는 경우 프레임워크에서 호출됩니다.|
|[CMDIChildWndEx::OnTaskbarTab엄지네일마우스활성화](#ontaskbartabthumbnailmouseactivate)|작업 표시줄 탭 축소판이 WM_MOUSEACTIVATE 메시지를 처리해야 하는 경우 프레임워크에서 호출됩니다.|
|[CMDIChildWndEx::온태스크바탭섬네일스트레치](#ontaskbartabthumbnailstretch)|그것은 윈도우 7 작업 표시 줄 탭 축소판 미리보기 MDI 자식에 대한 비트 맵을 스트레칭해야 할 때 프레임 워크에 의해 호출됩니다.|
|[CMDIChildWndEx::온업데이트프레임타이틀](#onupdateframetitle)|프레임 제목을 업데이트하기 위해 프레임워크에서 호출합니다. ( `CMDIChildWnd::OnUpdateFrameTitle`을 재정의합니다.)|
|[CMDIChildWndEx::P인FromPoint](#panefrompoint)|지정된 점을 포함하는 창을 반환합니다.|
|`CMDIChildWndEx::PreTranslateMessage`|창 메시지가 [TranslateMessage](../../mfc/reference/cwinapp-class.md) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) Windows 함수로 디스패치되기 전에 [CWinApp](/windows/win32/api/winuser/nf-winuser-dispatchmessage) 클래스가 이 메시지를 해석하는 데 사용됩니다. ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 재정의합니다.)|
|[CMDIChildWndEx::리콜크 레이아웃](#recalclayout)|창의 레이아웃을 다시 계산합니다.|
|[CMDIChildWndEx::레지스터작업 표시줄 탭](#registertaskbartab)|Windows 7 작업 표시줄 탭으로 MDI 자식을 등록합니다.|
|[CMDIChildWndEx::제거파네에서독매니저](#removepanefromdockmanager)|도킹 관리자에서 창을 제거합니다.|
|[CMDIChildWndEx::세트 관련 탭 그룹](#setrelatedtabgroup)||
|[CMDIChildWndEx::설정 작업 표시줄탭 활성](#settaskbartabactive)|해당 윈도우 7 작업 표시 줄 탭을 활성화합니다.|
|[CMDIChildWndEx::설정 작업 표시줄 탭 순서](#settaskbartaborder)|Windows 7 작업 표시줄 탭에서 지정된 창 앞에 MDI 자식을 삽입합니다.|
|[CMDIChildWndEx::SetTaskbarTabProperties](#settaskbartabproperties)|Windows 7 작업 표시줄 탭에 대한 속성을 설정합니다.|
|[CMDIChildWndEx::셋태스크바썸네일클립렉트](#settaskbarthumbnailcliprect)|프레임워크에서 내부적으로 호출하여 클리핑 사각형을 설정하여 작업 표시줄에서 해당 창의 축소판으로 표시할 창 의 클라이언트 영역 의 일부를 선택합니다.|
|[CMDIChildWndEx::쇼파인](#showpane)||
|[CMDIChildWndEx::레지스터 해제작업 표시줄 탭](#unregistertaskbartab)|Windows 7 작업 표시줄 탭에서 MDI 자식을 제거합니다.|
|[CMDIChildWndEx::업데이트 작업 표시줄TabIcon](#updatetaskbartabicon)|업데이트 윈도우 7 작업 표시줄 탭 아이콘.|

## <a name="remarks"></a>설명

MDI 응용 프로그램에서 확장 된 도킹 기능을 활용 하려면 `CMDIChildWndEx` [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)대신 응용 프로그램의 MDI 자식 창 클래스를 파생 합니다.

## <a name="example"></a>예제

다음 예제는 에서 `CMDIChildWndEx`클래스를 파생합니다. 이 코드 조각은 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램에서](../../overview/visual-cpp-samples.md)제공됩니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#3](../../mfc/codesnippet/cpp/cmdichildwndex-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)

[CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxMDIChildWndEx.h

## <a name="cmdichildwndexaddpane"></a><a name="addpane"></a>CMDIChildWndEx::애드파인

창을 추가합니다.

```
BOOL AddPane(
    CBasePane* pControlBar,
    BOOL bTail = TRUE);
```

### <a name="parameters"></a>매개 변수

*p컨트롤바*<br/>
【인】 창에 대한 포인터입니다.

*b테일 (것)들*<br/>
【인】 TRUE 도킹 관리자에 대 한 창 목록의 끝에 창을 추가 합니다. 그렇지 않으면 false입니다.

### <a name="return-value"></a>Return Value

창이 도킹 관리자에 성공적으로 등록된 경우 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="cmdichildwndexaddtabbedpane"></a><a name="addtabbedpane"></a>CMDIChildWndEx::애드탭베드파인

탭된 창을 추가합니다.

```cpp
void AddTabbedPane(CDockablePane* pControlBar);
```

### <a name="parameters"></a>매개 변수

*p컨트롤바*<br/>
【인】 창에 대한 포인터입니다.

## <a name="cmdichildwndexadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CMDIChildWndEx::조정도킹레이아웃

도킹 레이아웃을 조정합니다.

```
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```

### <a name="parameters"></a>매개 변수

*HDWP*<br/>
【인】 지연된 창 위치 구조로 처리합니다.

## <a name="cmdichildwndexcanshowonmditabs"></a><a name="canshowonmditabs"></a>CMDIChildWndEx::캔쇼온MDITabs

```
virtual BOOL CanShowOnMDITabs();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmdichildwndexcanshowonwindowslist"></a><a name="canshowonwindowslist"></a>CMDIChildWndEx::캔쇼온윈도우리스트

MDI 자식 창 이름을 [CMFCWindowsManagerDialog 클래스](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 대화 상자에 표시할 수 있는지 여부를 지정합니다.

```
virtual BOOL CanShowOnWindowsList();
```

### <a name="return-value"></a>Return Value

TRUE 창을 **Windows** 대화 상자에 표시할 수 있는 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

파생 된 클래스에서이 메서드를 재정의 하 고 **Windows** 대화 상자에 창을 표시 하지 않아야 하는 경우 FALSE를 반환 합니다. 이 함수는 `CMFCWindowsManagerDialog`에서 호출됩니다.

## <a name="cmdichildwndexdockpane"></a><a name="dockpane"></a>CMDIChildWndEx::DockPane

창을 도킹합니다.

```cpp
void DockPane(
    CBasePane* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 창에 대한 포인터입니다.

*nDockBarID*<br/>
【인】 창의 ID입니다.

*Lprect*<br/>
【인】 사각형에 대한 포인터입니다.

### <a name="remarks"></a>설명

*lpRect* 매개 변수는 사용 되지 않습니다.

## <a name="cmdichildwndexdockpaneleftof"></a><a name="dockpaneleftof"></a>CMDIChildWndEx::DockPaneLeftOf

창을 다른 창의 왼쪽에 도킹합니다.

```
BOOL DockPaneLeftOf(
    CPane* pBar,
    CPane* pLeftOf);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
도킹할 창에 대한 포인터입니다.

*p왼쪽*<br/>
참조 지점 역할을 하는 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 진실, 실패에 거짓.

### <a name="remarks"></a>설명

이 메서드는 *pBar에서* 지정 한 창을 사용 하 고 *pLeftOf에*의해 지정 된 창의 왼쪽에 도킹 합니다.

미리 정의된 순서로 여러 창을 도킹하려는 경우 이 메서드를 호출합니다.

## <a name="cmdichildwndexenableautohidepanes"></a><a name="enableautohidepanes"></a>CMDIChildWndEx::인에이블오토하이드파인즈

창이 창의 지정된 면에 도킹될 때 자동 숨기기 모드를 활성화합니다.

```
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```

### <a name="parameters"></a>매개 변수

*dwDockStyle*<br/>
【인】 활성화된 주 프레임 창의 측면을 지정합니다. 다음 플래그 중 하나 이상을 사용합니다.

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cmdichildwndexenabledocking"></a><a name="enabledocking"></a>CMDIChildWndEx::인에이블도킹

자식 창을 주 프레임에 도킹할 수 있습니다.

```
BOOL EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>매개 변수

*dwDockStyle*<br/>
【인】 활성화할 도킹 정렬을 지정합니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

주 프레임에 도킹 정렬을 활성화하려면 이 메서드를 호출합니다. CBRS_ALIGN_ 플래그 조합을 전달할 수 있습니다(자세한 내용은 [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)참조).

## <a name="cmdichildwndexgetdockingmanager"></a><a name="getdockingmanager"></a>CMDIChildWndEx::GetDockingManager

```
CDockingManager* GetDockingManager();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmdichildwndexgetdocumentname"></a><a name="getdocumentname"></a>CMDIChildWndEx::GetDocumentName

MDI 자식 창에 표시되는 문서의 이름을 반환합니다.

```
virtual LPCTSTR GetDocumentName(CObject** pObj);
```

### <a name="return-value"></a>Return Value

문서 의 이름을 포함 하는 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

문서는 MDI 자식 창에 표시되는 내용입니다. 일반적으로 창에는 파일에서 로드하거나 파일에 저장된 데이터가 표시됩니다. 따라서 문서의 이름은 파일의 이름입니다. 기본 구현은 `GetDocumentName` 에서 `CDocument::GetPathName`얻은 문자열을 반환합니다.

창에 파일에서 로드되지 않은 문서가 표시되는 경우 파생 클래스에서 이 메서드를 재정의하고 고유한 문서 식별자를 반환합니다.

`GetDocumentName`열려 있는 모든 문서의 상태를 저장할 때 프레임워크에서 호출됩니다. 반환된 문자열이 레지스트리에 기록됩니다.

프레임워크가 나중에 상태를 복원하는 경우 문서 이름이 레지스트리에서 [읽혀지고 CMDIFrameWndEx::CreateDocument창으로](../../mfc/reference/cmdiframewndex-class.md#createdocumentwindow)전달됩니다. [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)-derived 클래스에서 이 메서드를 재정의하고 이 이름을 가지고 있는 파일에서 이 이름을 가지고 있는 문서를 만들거나 엽니다. 문서가 파일을 기반으로 하지 않는 경우 문서 식별자 자체를 기반으로 문서를 만듭니다. 문서를 저장하고 복원하려는 경우에만 이전 작업을 수행해야 합니다.

### <a name="example"></a>예제

다음 예제에서는 `GetDocumentName` 메서드를 사용하는 방법을 보여 줍니다. 이 코드 조각은 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램에서](../../overview/visual-cpp-samples.md)제공됩니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#17](../../mfc/codesnippet/cpp/cmdichildwndex-class_2.cpp)]

## <a name="cmdichildwndexgetframeicon"></a><a name="getframeicon"></a>CMDIChildWndEx::겟프레임아이콘

MDI 자식 창의 아이콘을 검색 하려면 프레임 워크에 의해 호출 됩니다.

```
virtual HICON GetFrameIcon() const;
```

### <a name="return-value"></a>Return Value

창 아이콘의 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 MDI 자식 프레임 창을 포함 하는 MDI 탭에 표시 할 아이콘을 결정 하기 위해 프레임 워크에 의해 호출 됩니다.

기본적으로 이 메서드는 창 아이콘을 반환합니다. -derived 클래스에서 재정의하여 `GetFrameIcon` 이 동작을 사용자 지정합니다. `CMDIChildWndEx`

## <a name="cmdichildwndexgetframetext"></a><a name="getframetext"></a>CMDIChildWndEx::GetFrameText

MDI 자식 창에 대 한 텍스트를 검색 하는 프레임 워크에 의해 호출 됩니다.

```
virtual CString GetFrameText() const;
```

### <a name="return-value"></a>Return Value

프레임 창 텍스트가 포함된 문자열입니다.

### <a name="remarks"></a>설명

이 메서드는 MDI 자식 프레임 창을 포함 하는 MDI 탭에 표시 할 텍스트를 결정 하기 위해 프레임 워크에서 호출 됩니다.

기본적으로 이 메서드는 창 텍스트를 반환합니다. -derived 클래스에서 재정의하여 `GetFrameText` 이 동작을 사용자 지정합니다. `CMDIChildWndEx`

## <a name="cmdichildwndexgetpane"></a><a name="getpane"></a>CMDIChildWndEx::겟파인

지정된 컨트롤 ID로 창을 찾습니다.

```
CBasePane* GetPane(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 찾을 창의 제어 ID입니다.

### <a name="return-value"></a>Return Value

창에 대한 포인터가 발견되면 NULL이 있습니다.

## <a name="cmdichildwndexgetrelatedtabgroup"></a><a name="getrelatedtabgroup"></a>CMDIChildWndEx::관련 탭 그룹

```
CMFCTabCtrl* GetRelatedTabGroup();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmdichildwndexgettabbedpane"></a><a name="gettabbedpane"></a>CMDIChildWndEx::GetTabbedPane

MDI 탭된 문서 그룹의 일부인 도킹 창에 대한 포인터를 반환합니다.

```
CDockablePane* GetTabbedPane() const;
```

### <a name="return-value"></a>Return Value

MDI 탭된 문서 그룹의 일부인 도킹 창에 대한 포인터입니다.

## <a name="cmdichildwndexgettoolbarbuttontooltiptext"></a><a name="gettoolbarbuttontooltiptext"></a>CMDIChildWndEx::gettoolbarButtonToolTipText

도구 모음 단추에 대한 도구 설명을 검색하려면 프레임워크에서 호출합니다.

```
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton*,
    CString&);
```

### <a name="return-value"></a>Return Value

도구 설명이 표시된 경우 TRUE입니다. 기본 구현은 FALSE를 반환합니다.

### <a name="remarks"></a>설명

도구 모음 단추에 대한 사용자 지정 도구 팁을 표시하려면 이 방법을 재정의합니다.

## <a name="cmdichildwndexinsertpane"></a><a name="insertpane"></a>CMDIChildWndEx::삽입판

지정된 창을 도킹 관리자에 등록합니다.

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>매개 변수

*p컨트롤바*<br/>
【인】 삽입할 창에 대한 포인터입니다.

*p Target*<br/>
【인】 인접 창에 대한 포인터입니다.

*b애프터*<br/>
【인】 TRUE인 경우 *pControlBar가* *pTarget*에 삽입됩니다. FALSE인 경우 *pControlBar가* *pTarget*앞에 삽입됩니다.

### <a name="return-value"></a>Return Value

TRUE 메서드가 성공하면 FALSE가 그렇지 않으면 FALSE입니다.

## <a name="cmdichildwndexispointneardocksite"></a><a name="ispointneardocksite"></a>CMDIChildWndEx::이스포인트니어독사이트

지정된 점이 도크 사이트 근처에 있는지 여부를 결정합니다.

```
BOOL IsPointNearDockSite(
    CPoint point,
    DWORD& dwBarAlignment,
    BOOL& bOuterEdge) const;
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
【인】 지정된 점입니다.

*dwBar 정렬*<br/>
【인】 점이 근처에 있는 모서리를 지정합니다. 가능한 값은 CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT, CBRS_ALIGN_TOP 및 CBRS_ALIGN_BOTTOM

*bOuterEdge*<br/>
【인】 TRUE 점이 도크 사이트의 외부 테두리 근처에 있는 경우; 그렇지 않으면 거짓.

### <a name="return-value"></a>Return Value

포인트가 도크 사이트 근처에 있는 경우 TRUE; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

점은 도킹 관리자에서 설정된 민감도 내에 있을 때 도크 사이트 근처에 있습니다. 기본 민감도는 15픽셀입니다.

## <a name="cmdichildwndexisreadonly"></a><a name="isreadonly"></a>CMDIChildWndEx::IsRead전용

하위 창에 표시되는 문서가 읽기 전용인지 여부를 지정합니다.

```
virtual BOOL IsReadOnly();
```

### <a name="return-value"></a>Return Value

TRUE 문서가 읽기 전용인 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 함수는 읽기 전용 문서를 저장하지 못하도록 하는 데 사용됩니다.

### <a name="example"></a>예제

다음 예제에서는 메서드재정의방법을 `IsReadOnly` 보여 줍니다. 이 코드 조각은 [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램에서](../../overview/visual-cpp-samples.md)제공됩니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#2](../../mfc/codesnippet/cpp/cmdichildwndex-class_3.cpp)]

## <a name="cmdichildwndexistabbedpane"></a><a name="istabbedpane"></a>CMDIChildWndEx::이스탭베드파인

MDI 자식 창에 도킹 창이 있는지 여부를 지정합니다.

```
BOOL IsTabbedPane() const;
```

### <a name="return-value"></a>Return Value

True MDI 자식 창에 탭된 문서로 변환된 도킹 창이 포함되어 있는 경우 그렇지 않으면 거짓.

## <a name="cmdichildwndexonmoveminiframe"></a><a name="onmoveminiframe"></a>CMDIChildWndEx::온무브미니프레임

프레임 워크에서 호출하여 미니 프레임 창을 이동합니다.

```
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```

### <a name="parameters"></a>매개 변수

*pFrame*<br/>
【인】 미니 프레임 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 메서드가 성공하면 FALSE가 됩니다.

## <a name="cmdichildwndexonsetpreviewmode"></a><a name="onsetpreviewmode"></a>CMDIChildWndEx::온셋프리뷰모드

인쇄 미리 보기 모드를 입력하거나 종료하려면 프레임워크에서 호출됩니다.

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>매개 변수

*bPreview*<br/>
【인】 TRUE인 경우 인쇄 미리 보기 모드를 입력합니다. FALSE인 경우 인쇄 미리 보기 모드를 종료합니다.

*pState*<br/>
【인】 인쇄 미리 보기 상태 구조에 대한 포인터입니다.

## <a name="cmdichildwndexonupdateframetitle"></a><a name="onupdateframetitle"></a>CMDIChildWndEx::온업데이트프레임타이틀

프레임 제목을 업데이트하기 위해 프레임워크에서 호출합니다.

```
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```

### <a name="parameters"></a>매개 변수

*bAddToTitle*<br/>
【인】 TRUE인 경우 제목에 문서 이름을 추가합니다.

## <a name="cmdichildwndexpanefrompoint"></a><a name="panefrompoint"></a>CMDIChildWndEx::P인FromPoint

지정된 점을 포함하는 창을 반환합니다.

```
CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    bool bExactBar,
    CRuntimeClass* pRTCBarType) const;

CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    DWORD& dwAlignment,
    CRuntimeClass* pRTCBarType) const;
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
【인】 검사할 점을 화면 좌표로 지정합니다.

*n감도*<br/>
【인】 이 금액만큼 검색 영역을 늘립니다. 지정된 점이 증가된 영역에 속하는 경우 창은 검색 기준을 충족합니다.

*bExactBar*<br/>
【인】 *true는 nSensitivity* 매개 변수를 무시합니다. 그렇지 않으면 false입니다.

*pRTCBarType*<br/>
【인】 NULL이 아닌 경우 메서드는 지정된 형식의 창만 검색합니다.

*dw정렬*<br/>
【인】 지정된 지점에서 창이 발견되면 이 매개변수에는 지정된 점에 가장 가까운 창의 측면이 포함됩니다. 자세한 내용은 주의 섹션을 참조하세요.

### <a name="return-value"></a>Return Value

지정된 점을 `CBasePane`포함하는 -derived 개체에 대한 포인터 또는 창이 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 창에 런타임 클래스 및 가시성과 같은 지정된 조건에 따라 지정된 점이 포함되어 있는지 확인합니다.

함수가 반환되고 창이 발견되면 *dwAlignment에는* 지정된 점의 정렬이 포함됩니다. 예를 들어 점이 창의 맨 위에 가장 가깝으면 *dwAlignment이* CBRS_ALIGN_TOP 설정됩니다.

## <a name="cmdichildwndexrecalclayout"></a><a name="recalclayout"></a>CMDIChildWndEx::리콜크 레이아웃

창의 레이아웃을 다시 계산합니다.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>매개 변수

*bNotify*<br/>
【인】 TRUE이면 창의 활성 인플레이스 항목에서 레이아웃 변경에 대한 알림을 받습니다.

## <a name="cmdichildwndexremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>CMDIChildWndEx::제거파네에서독매니저

도킹 관리자에서 창을 제거합니다.

```cpp
void RemovePaneFromDockManager(
    CBasePane* pControlBar,
    BOOL bDestroy,
    BOOL bAdjustLayout,
    BOOL bAutoHide,
    CBasePane* pBarReplacement);
```

### <a name="parameters"></a>매개 변수

*p컨트롤바*<br/>
【인】 제거할 창에 대한 포인터입니다.

*bDestroy*<br/>
【인】 TRUE이면 제거된 창이 소멸됩니다.

*bAdjust레이아웃*<br/>
【인】 TRUE인 경우 도킹 레이아웃을 즉시 조정합니다.

*b자동 숨기기*<br/>
【인】 TRUE인 경우 도킹 레이아웃은 자동 숨기기 막대 목록과 관련이 있습니다. FALSE인 경우 도킹 레이아웃은 일반 창 목록과 관련이 있습니다.

*pBar교체*<br/>
【인】 제거된 창을 대체하는 창에 대한 포인터입니다.

## <a name="cmdichildwndexsetrelatedtabgroup"></a><a name="setrelatedtabgroup"></a>CMDIChildWndEx::세트 관련 탭 그룹

```cpp
void SetRelatedTabGroup(CMFCTabCtrl* p);
```

### <a name="parameters"></a>매개 변수

【인】 *p*<br/>

### <a name="remarks"></a>설명

## <a name="cmdichildwndexshowpane"></a><a name="showpane"></a>CMDIChildWndEx::쇼파인

```cpp
void ShowPane(
    CBasePane* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

【인】 *bShow*<br/>

【인】 *bDelay*<br/>

【인】 *b활성화*<br/>

### <a name="remarks"></a>설명

## <a name="cmdichildwndexupdatetaskbartabicon"></a><a name="updatetaskbartabicon"></a>CMDIChildWndEx::업데이트 작업 표시줄TabIcon

Windows 7 작업 표시줄 탭 아이콘을 업데이트합니다.

```
virtual void UpdateTaskbarTabIcon(HICON hIcon);
```

### <a name="parameters"></a>매개 변수

*hIcon*<br/>
Windows 7 작업 표시줄 탭에 표시할 아이콘의 핸들입니다.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexunregistertaskbartab"></a><a name="unregistertaskbartab"></a>CMDIChildWndEx::레지스터 해제작업 표시줄 탭

Windows 7 작업 표시줄 탭에서 MDI 자식을 제거합니다.

```cpp
void UnregisterTaskbarTab(BOOL bCheckRegisteredMDIChildCount = TRUE);
```

### <a name="parameters"></a>매개 변수

*bCheck등록MDIChildCount*<br/>
이 함수가 MDI 탭에 등록된 MDI 자식 수를 확인해야 하는지 여부를 지정합니다. 이 숫자가 0이면 이 함수는 응용 프로그램의 작업 표시줄 축소판에서 클리핑 사각형을 제거합니다.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexsettaskbarthumbnailcliprect"></a><a name="settaskbarthumbnailcliprect"></a>CMDIChildWndEx::셋태스크바썸네일클립렉트

프레임워크에서 클리핑 사각형을 설정하여 작업 표시줄에 해당 창의 축소판으로 표시할 창 클라이언트 영역의 일부를 선택합니다.

```
virtual BOOL SetTaskbarThumbnailClipRect(CRect rect);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
새 클리핑 사각형을 지정합니다. 사각형이 비어 있거나 null이면 클리핑이 제거됩니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexsettaskbartabproperties"></a><a name="settaskbartabproperties"></a>CMDIChildWndEx::설정 작업 표시줄탭속성

Windows 7 작업 표시줄 탭에 대한 속성을 설정합니다.

```cpp
void SetTaskbarTabProperties(DWORD dwFlags);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
STPFLAG 값의 조합입니다. 자세한 내용은 [ITaskbarList4:SetTabProperties](/windows/win32/api/shobjidl_core/nf-shobjidl_core-itaskbarlist4-settabproperties).

### <a name="remarks"></a>설명

## <a name="cmdichildwndexsettaskbartaborder"></a><a name="settaskbartaborder"></a>CMDIChildWndEx::설정 작업 표시줄 탭 순서

Windows 7 작업 표시줄 탭에서 지정된 창 앞에 MDI 자식을 삽입합니다.

```cpp
void SetTaskbarTabOrder(CMDIChildWndEx* pWndBefore = NULL);
```

### <a name="parameters"></a>매개 변수

*pWnd이전*<br/>
축소판 그림이 왼쪽에 삽입된 MDI 자식 창에 대한 포인터입니다. 이 창을 통해 `RegisterTaskbarTab`이미 등록되어 있어야 합니다. 이 값이 NULL이면 새 축소판 그림이 목록의 끝에 추가됩니다.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexsettaskbartabactive"></a><a name="settaskbartabactive"></a>CMDIChildWndEx::설정 작업 표시줄탭 활성

해당 Windows 7 작업 표시줄 탭을 활성화합니다.

```cpp
void SetTaskbarTabActive();
```

### <a name="remarks"></a>설명

## <a name="cmdichildwndexregistertaskbartab"></a><a name="registertaskbartab"></a>CMDIChildWndEx::레지스터작업 표시줄 탭

Windows 7 작업 표시줄 탭으로 MDI 자식을 등록합니다.

```
virtual void RegisterTaskbarTab(CMDIChildWndEx* pWndBefore = NULL);
```

### <a name="parameters"></a>매개 변수

*pWnd이전*<br/>
축소판 그림이 왼쪽에 삽입된 MDI 자식 창에 대한 포인터입니다. 이 창을 통해 `RegisterTaskbarTab`이미 등록되어 있어야 합니다. 이 값이 NULL이면 새 축소판 그림이 목록의 끝에 추가됩니다.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexontaskbartabthumbnailstretch"></a><a name="ontaskbartabthumbnailstretch"></a>CMDIChildWndEx::온태스크바탭섬네일스트레치

그것은 윈도우에 대한 비트 맵을 스트레칭해야 할 때 프레임 워크에 의해 호출 7 작업 표시 줄 탭 축소판 미리보기 MDI 자식.

```
virtual BOOL OnTaskbarTabThumbnailStretch(
    HBITMAP hBmpDst,
    const CRect& rectDst,
    HBITMAP hBmpSrc,
    const CRect& rectSrc);
```

### <a name="parameters"></a>매개 변수

*hBmpDst*<br/>
대상 비트맵에 대한 핸들입니다.

*정류자*<br/>
대상 사각형을 지정합니다.

*hBmpSrc*<br/>
소스 비트맵에 대한 핸들입니다.

*rectSrc*<br/>
소스 사각형을 지정합니다.

### <a name="remarks"></a>설명

요구 사항 : afxmdichildwndex.h

## <a name="cmdichildwndexontaskbartabthumbnailmouseactivate"></a><a name="ontaskbartabthumbnailmouseactivate"></a>CMDIChildWndEx::OnTaskbarTab엄지네일마우스활성화

작업 표시줄 탭 축소판이 WM_MOUSEACTIVATE 메시지를 처리해야 하는 경우 프레임워크에서 호출됩니다.

```
virtual int OnTaskbarTabThumbnailMouseActivate(
    CWnd* pDesktopWnd,
    UINT nHitTest,
    UINT message);
```

### <a name="parameters"></a>매개 변수

*pDesktopWnd*<br/>
활성화되는 창의 최상위 상위 창에 대한 포인터를 지정합니다. 포인터는 일시적일 수 있으며 저장해서는 안 됩니다.

*n히트 테스트*<br/>
적중 테스트 영역 코드를 지정합니다. 적중 테스트는 커서의 위치를 결정하는 테스트입니다.

*message*<br/>
마우스 메시지 번호를 지정합니다.

### <a name="remarks"></a>설명

기본 구현은 관련 MDI 자식 프레임을 활성화합니다.

## <a name="cmdichildwndexontaskbartabthumbnailactivate"></a><a name="ontaskbartabthumbnailactivate"></a>CMDIChildWndEx::OnTaskbarTab엄지네일활성화

작업 표시줄 탭 축소판이 WM_ACTIVATE 메시지를 처리해야 하는 경우 프레임워크에서 호출됩니다.

```
virtual void OnTaskbarTabThumbnailActivate(
    UINT nState,
    CWnd* pWndOther,
    BOOL bMinimized);
```

### <a name="parameters"></a>매개 변수

*nState*<br/>
활성화 또는 비활성화 `CWnd` 중인지 여부를 지정합니다.

*pWnd기타*<br/>
활성화 `CWnd` 또는 비활성화되는 포인터입니다. 포인터는 NULL일 수 있으며 일시적일 수 있습니다.

*b최소화*<br/>
활성화 또는 `CWnd` 비활성화되는 최소화된 상태를 지정합니다. TRUE 값은 창이 최소화했음을 나타냅니다.

### <a name="remarks"></a>설명

기본 구현은 관련 MDI 자식 프레임을 활성화합니다.

## <a name="cmdichildwndexonpresstaskbarthmbnailclosebutton"></a><a name="onpresstaskbarthmbnailclosebutton"></a>CMDIChildWndEx::OnpressTaskbarThmb네일클로즈버튼

사용자가 작업 표시줄 탭 축소판에서 닫기 단추를 누를 때 프레임워크에서 호출됩니다.

```
virtual void OnPressTaskbarThmbnailCloseButton();
```

### <a name="remarks"></a>설명

## <a name="cmdichildwndexongeticonicthumbnail"></a><a name="ongeticonicthumbnail"></a>CMDIChildWndEx::OnGetIconic엄지손가락

MDI 자식의 상징적인 축소판 그림에 대한 비트맵을 가져와야 할 때 프레임워크에서 호출합니다.

```
virtual HBITMAP OnGetIconicThumbnail(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
필요한 비트맵의 너비를 지정합니다.

*nHeight*<br/>
필요한 비트맵의 높이를 지정합니다.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexongeticoniclivepreviewbitmap"></a><a name="ongeticoniclivepreviewbitmap"></a>CMDIChildWndEx::OnGetIconicLive프리뷰비트맵

MDI 자식의 라이브 미리 보기를 위해 비트맵을 가져와야 할 때 프레임워크에서 호출합니다.

```
virtual HBITMAP OnGetIconicLivePreviewBitmap(
    BOOL bIsMDIChildActive,
    CPoint& ptLocation);
```

### <a name="parameters"></a>매개 변수

*비스엠디차일드액티브*<br/>
이 매개 변수는 현재 활성 상태이고 주 창이 최소화되지 않은 MDI 자식에 대해 비트맵이 요청된 경우 TRUE입니다. 이 경우 기본 처리는 주 창의 스냅숏을 생성합니다.

*pt위치*<br/>
기본(최상위) 창 클라이언트 좌표에서 비트맵의 위치를 지정합니다. 이 점은 받는 이별에서 제공해야 합니다.

### <a name="return-value"></a>Return Value

처리된 경우 핸들을 유효한 32bpp 비트맵(그렇지 않으면 NULL)으로 반환합니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하고 MDI 자식의 라이브 미리 보기에 유효한 32bpp 비트맵을 반환합니다. 이 메서드는 MDI 자식이 Windows 7 작업 표시줄 탭에 표시 될 때만 호출 됩니다. NULL을 반환하는 경우 MFC는 기본 처리기를 호출하고 `PrintWindow`를 사용하여 `PrintClient` 비트맵을 가져옵니다.

## <a name="cmdichildwndexm_dwdefaulttaskbartabpropertyflags"></a><a name="m_dwdefaulttaskbartabpropertyflags"></a>CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags

탭 (MDI 자식)가 Windows `SetTaskbarTabProperties` 7 작업 표시 줄 탭에 등록 될 때 메서드에 프레임 워크에 의해 전달 되는 플래그의 조합입니다.

```
AFX_IMPORT_DATA static DWORD m_dwDefaultTaskbarTabPropertyFlags;
```

### <a name="remarks"></a>설명

기본 조합은 STPF_USEAPPTHUMBNAILWHENACTIVE &#124; STPF_USEAPPPEEKWHENACTIVE.

## <a name="cmdichildwndexistaskbarthumbnailcliprectenabled"></a><a name="istaskbarthumbnailcliprectenabled"></a>CMDIChildWndEx::이태스크바썸네일클립렉트사용

작업 표시줄에서 해당 창의 축소판 그림으로 표시할 창의 클라이언트 영역 의 일부를 자동으로 선택할 수 있는지 여부를 알려줍니다.

```
BOOL IsTaskbarThumbnailClipRectEnabled() const;
```

### <a name="return-value"></a>Return Value

표시할 창의 클라이언트 영역 의 일부를 자동으로 선택하면 TRUE를 반환합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexistaskbartabssupportenabled"></a><a name="istaskbartabssupportenabled"></a>CMDIChildWndEx::IsTaskbarTabs지원 지원

MDI 자식이 Windows 7 작업 표시줄 탭에 나타날 수 있는지 여부를 알려줍니다.

```
BOOL IsTaskbarTabsSupportEnabled();
```

### <a name="return-value"></a>Return Value

True 경우 MDI 자식 Windows 7 작업 표시줄 탭에 나타날 수 있습니다. MDI 자식이 Windows 7 작업 표시줄 탭에 나타날 수 없는 경우 FALSE.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexisregisteredwithtaskbartabs"></a><a name="isregisteredwithtaskbartabs"></a>CMDIChildWndEx::등록된작업 표시줄탭

MDI 자식이 Windows 7 작업 표시줄 탭에 성공적으로 등록된 경우 TRUE를 반환합니다.

```
BOOL IsRegisteredWithTaskbarTabs();
```

### <a name="return-value"></a>Return Value

True MDI 자식이 Windows 7 작업 표시줄 탭에 등록된 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexinvalidateiconicbitmaps"></a><a name="invalidateiconicbitmaps"></a>CMDIChildWndEx::무효화아이코닉비트맵

MDI 자식의 상징적인 비트맵 표현을 무효화합니다.

```
BOOL InvalidateIconicBitmaps();
```

### <a name="return-value"></a>Return Value

Windows 7 작업 표시줄 지원이 비활성화되어 있거나 MDI 자식이 Windows 7 작업 표시줄 탭에 등록되지 않은 경우 FALSE를 반환합니다. 그렇지 않으면 TRUE를 반환합니다.

### <a name="remarks"></a>설명

MDI 자식의 라이브 콘텐츠 또는 크기가 변경된 경우 호출해야 합니다.

## <a name="cmdichildwndexgettaskbarthumbnailcliprect"></a><a name="gettaskbarthumbnailcliprect"></a>CMDIChildWndEx::겟태스크바썸네일클립렉트

작업 표시줄에서 해당 창의 축소판으로 표시할 창의 클라이언트 영역 의 일부를 선택해야 할 때 프레임워크에서 호출합니다.

```
virtual CRect GetTaskbarThumbnailClipRect() const;
```

### <a name="return-value"></a>Return Value

창 좌표의 사각형입니다. 이 사각형은 최상위 프레임의 클라이언트 영역에 매핑됩니다. 클리핑 사각형을 지우려면 사각형이 비어 있어야 합니다.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexgettaskbarpreviewwnd"></a><a name="gettaskbarpreviewwnd"></a>CMDIChildWndEx::GetTaskbar프리뷰

Windows 7 작업 표시줄 탭 축소판에 표시할 자식 창(일반적으로 보기 또는 분할자 창)을 가져와야 할 때 프레임워크에서 호출합니다.

```
virtual CWnd* GetTaskbarPreviewWnd();
```

### <a name="return-value"></a>Return Value

이 MDI 자식과 관련된 Windows 7 작업 표시줄 탭에 미리 보기가 표시되어야 하는 `CWnd` 개체에 유효한 포인터를 반환해야 합니다. 기본 구현은 AFX_IDW_PANE_FIRST 제어 ID(일반적으로 `CView`-derived 클래스)를 가진 이 MDI 자식의 자식 창을 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexgettabproxywnd"></a><a name="gettabproxywnd"></a>CMDIChildWndEx::GetTab프록시Wnd

Windows 7 작업 표시줄 탭에 등록된 탭 프록시 창을 반환합니다.

```
CMDITabProxyWnd* GetTabProxyWnd();
```

### <a name="return-value"></a>Return Value

Windows 7 `CMDITabProxyWnd` 작업 표시줄 탭에 등록된 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexenabletaskbarthumbnailcliprect"></a><a name="enabletaskbarthumbnailcliprect"></a>CMDIChildWndEx::인에이블태스크바썸네일클립렉트

창의 클라이언트 영역 일부를 자동으로 선택하거나 비활성화하여 작업 표시줄에 해당 창의 축소판으로 표시합니다.

```cpp
void EnableTaskbarThumbnailClipRect(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
표시할 창의 클라이언트 영역 부분의 활성화(TRUE) 또는 (FALSE) 자동 선택을 사용하도록 지정합니다.

### <a name="remarks"></a>설명

## <a name="cmdichildwndexcanshowontaskbartabs"></a><a name="canshowontaskbartabs"></a>CMDIChildWndEx::캔쇼온태스크바탭

이 MDI 자식이 Windows 7 작업 표시줄 탭에 표시될 수 있는지 여부를 프레임워크에 알려줍니다.

```
virtual BOOL CanShowOnTaskBarTabs();
```

### <a name="return-value"></a>Return Value

True MDI 자식의 내용을 Windows 7 작업 표시줄 축소판에 표시할 수 있는 경우.

### <a name="remarks"></a>설명

파생 된 클래스에서이 메서드를 재정의 하 고 Windows 7 작업 표시줄 탭에서이 MDI 자식의 모양을 사용 하지 않도록 설정 하려면 FALSE를 반환 합니다.

## <a name="cmdichildwndexactivatetoplevelframe"></a><a name="activatetoplevelframe"></a>CMDIChildWndEx::활성화탑레벨프레임

작업 표시줄 탭에서 응용 프로그램이 활성화될 때 최상위 프레임을 활성화하기 위해 프레임워크에서 호출합니다.

```
virtual void ActivateTopLevelFrame();
```

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMDI차일드 클래스](../../mfc/reference/cmdichildwnd-class.md)<br/>
[CMFC윈도우매니저디아로그 클래스](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)<br/>
[CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)
