---
title: CDockingManager 클래스
ms.date: 11/04/2016
f1_keywords:
- CDockingManager
- AFXDOCKINGMANAGER/CDockingManager
- AFXDOCKINGMANAGER/CDockingManager::AddDockSite
- AFXDOCKINGMANAGER/CDockingManager::AddHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::AddMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::AddPane
- AFXDOCKINGMANAGER/CDockingManager::AdjustDockingLayout
- AFXDOCKINGMANAGER/CDockingManager::AdjustPaneFrames
- AFXDOCKINGMANAGER/CDockingManager::AdjustRectToClientArea
- AFXDOCKINGMANAGER/CDockingManager::AlignAutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::AutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::BringBarsToTop
- AFXDOCKINGMANAGER/CDockingManager::BuildPanesMenu
- AFXDOCKINGMANAGER/CDockingManager::CalcExpectedDockedRect
- AFXDOCKINGMANAGER/CDockingManager::Create
- AFXDOCKINGMANAGER/CDockingManager::DeterminePaneAndStatus
- AFXDOCKINGMANAGER/CDockingManager::DisableRestoreDockState
- AFXDOCKINGMANAGER/CDockingManager::DockPane
- AFXDOCKINGMANAGER/CDockingManager::DockPaneLeftOf
- AFXDOCKINGMANAGER/CDockingManager::EnableAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::EnableDocking
- AFXDOCKINGMANAGER/CDockingManager::EnableDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::EnablePaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::FindDockSite
- AFXDOCKINGMANAGER/CDockingManager::FindDockSiteByPane
- AFXDOCKINGMANAGER/CDockingManager::FindPaneByID
- AFXDOCKINGMANAGER/CDockingManager::FixupVirtualRects
- AFXDOCKINGMANAGER/CDockingManager::FrameFromPoint
- AFXDOCKINGMANAGER/CDockingManager::GetClientAreaBounds
- AFXDOCKINGMANAGER/CDockingManager::GetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::GetDockSiteFrameWnd
- AFXDOCKINGMANAGER/CDockingManager::GetEnabledAutoHideAlignment
- AFXDOCKINGMANAGER/CDockingManager::GetMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::GetOuterEdgeBounds
- AFXDOCKINGMANAGER/CDockingManager::GetPaneList
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManager
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManagerPermanent
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingTheme
- AFXDOCKINGMANAGER/CDockingManager::HideAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::InsertDockSite
- AFXDOCKINGMANAGER/CDockingManager::InsertPane
- AFXDOCKINGMANAGER/CDockingManager::IsDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::IsInAdjustLayout
- AFXDOCKINGMANAGER/CDockingManager::IsOLEContainerMode
- AFXDOCKINGMANAGER/CDockingManager::IsPointNearDockSite
- AFXDOCKINGMANAGER/CDockingManager::IsPrintPreviewValid
- AFXDOCKINGMANAGER/CDockingManager::LoadState
- AFXDOCKINGMANAGER/CDockingManager::LockUpdate
- AFXDOCKINGMANAGER/CDockingManager::OnActivateFrame
- AFXDOCKINGMANAGER/CDockingManager::OnClosePopupMenu
- AFXDOCKINGMANAGER/CDockingManager::OnMoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::OnPaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::PaneFromPoint
- AFXDOCKINGMANAGER/CDockingManager::ProcessPaneContextMenuCommand
- AFXDOCKINGMANAGER/CDockingManager::RecalcLayout
- AFXDOCKINGMANAGER/CDockingManager::ReleaseEmptyPaneContainers
- AFXDOCKINGMANAGER/CDockingManager::RemoveHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::RemoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::RemovePaneFromDockManager
- AFXDOCKINGMANAGER/CDockingManager::ReplacePane
- AFXDOCKINGMANAGER/CDockingManager::ResortMiniFramesForZOrder
- AFXDOCKINGMANAGER/CDockingManager::SaveState
- AFXDOCKINGMANAGER/CDockingManager::SendMessageToMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::Serialize
- AFXDOCKINGMANAGER/CDockingManager::SetAutohideZOrder
- AFXDOCKINGMANAGER/CDockingManager::SetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::SetDockState
- AFXDOCKINGMANAGER/CDockingManager::SetPrintPreviewMode
- AFXDOCKINGMANAGER/CDockingManager::SetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::ShowDelayShowMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::ShowPanes
- AFXDOCKINGMANAGER/CDockingManager::StartSDocking
- AFXDOCKINGMANAGER/CDockingManager::StopSDocking
- AFXDOCKINGMANAGER/CDockingManager::m_bHideDockingBarsInContainerMode
- AFXDOCKINGMANAGER/CDockingManager::m_dockModeGlobal
- AFXDOCKINGMANAGER/CDockingManager::m_nDockSensitivity
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeDockingBarDock
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeToolBarDock
helpviewer_keywords:
- CDockingManager [MFC], AddDockSite
- CDockingManager [MFC], AddHiddenMDITabbedBar
- CDockingManager [MFC], AddMiniFrame
- CDockingManager [MFC], AddPane
- CDockingManager [MFC], AdjustDockingLayout
- CDockingManager [MFC], AdjustPaneFrames
- CDockingManager [MFC], AdjustRectToClientArea
- CDockingManager [MFC], AlignAutoHidePane
- CDockingManager [MFC], AutoHidePane
- CDockingManager [MFC], BringBarsToTop
- CDockingManager [MFC], BuildPanesMenu
- CDockingManager [MFC], CalcExpectedDockedRect
- CDockingManager [MFC], Create
- CDockingManager [MFC], DeterminePaneAndStatus
- CDockingManager [MFC], DisableRestoreDockState
- CDockingManager [MFC], DockPane
- CDockingManager [MFC], DockPaneLeftOf
- CDockingManager [MFC], EnableAutoHidePanes
- CDockingManager [MFC], EnableDocking
- CDockingManager [MFC], EnableDockSiteMenu
- CDockingManager [MFC], EnablePaneContextMenu
- CDockingManager [MFC], FindDockSite
- CDockingManager [MFC], FindDockSiteByPane
- CDockingManager [MFC], FindPaneByID
- CDockingManager [MFC], FixupVirtualRects
- CDockingManager [MFC], FrameFromPoint
- CDockingManager [MFC], GetClientAreaBounds
- CDockingManager [MFC], GetDockingMode
- CDockingManager [MFC], GetDockSiteFrameWnd
- CDockingManager [MFC], GetEnabledAutoHideAlignment
- CDockingManager [MFC], GetMiniFrames
- CDockingManager [MFC], GetOuterEdgeBounds
- CDockingManager [MFC], GetPaneList
- CDockingManager [MFC], GetSmartDockingManager
- CDockingManager [MFC], GetSmartDockingManagerPermanent
- CDockingManager [MFC], GetSmartDockingParams
- CDockingManager [MFC], GetSmartDockingTheme
- CDockingManager [MFC], HideAutoHidePanes
- CDockingManager [MFC], InsertDockSite
- CDockingManager [MFC], InsertPane
- CDockingManager [MFC], IsDockSiteMenu
- CDockingManager [MFC], IsInAdjustLayout
- CDockingManager [MFC], IsOLEContainerMode
- CDockingManager [MFC], IsPointNearDockSite
- CDockingManager [MFC], IsPrintPreviewValid
- CDockingManager [MFC], LoadState
- CDockingManager [MFC], LockUpdate
- CDockingManager [MFC], OnActivateFrame
- CDockingManager [MFC], OnClosePopupMenu
- CDockingManager [MFC], OnMoveMiniFrame
- CDockingManager [MFC], OnPaneContextMenu
- CDockingManager [MFC], PaneFromPoint
- CDockingManager [MFC], ProcessPaneContextMenuCommand
- CDockingManager [MFC], RecalcLayout
- CDockingManager [MFC], ReleaseEmptyPaneContainers
- CDockingManager [MFC], RemoveHiddenMDITabbedBar
- CDockingManager [MFC], RemoveMiniFrame
- CDockingManager [MFC], RemovePaneFromDockManager
- CDockingManager [MFC], ReplacePane
- CDockingManager [MFC], ResortMiniFramesForZOrder
- CDockingManager [MFC], SaveState
- CDockingManager [MFC], SendMessageToMiniFrames
- CDockingManager [MFC], Serialize
- CDockingManager [MFC], SetAutohideZOrder
- CDockingManager [MFC], SetDockingMode
- CDockingManager [MFC], SetDockState
- CDockingManager [MFC], SetPrintPreviewMode
- CDockingManager [MFC], SetSmartDockingParams
- CDockingManager [MFC], ShowDelayShowMiniFrames
- CDockingManager [MFC], ShowPanes
- CDockingManager [MFC], StartSDocking
- CDockingManager [MFC], StopSDocking
- CDockingManager [MFC], m_bHideDockingBarsInContainerMode
- CDockingManager [MFC], m_dockModeGlobal
- CDockingManager [MFC], m_nDockSensitivity
- CDockingManager [MFC], m_nTimeOutBeforeDockingBarDock
- CDockingManager [MFC], m_nTimeOutBeforeToolBarDock
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
ms.openlocfilehash: 76fd12b0817c99d0d08327f9d9156eadf3559dc5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753331"
---
# <a name="cdockingmanager-class"></a>CDockingManager 클래스

주 프레임 창에서 도킹 레이아웃을 제어하는 핵심 기능을 구현합니다.

## <a name="syntax"></a>구문

```
class CDockingManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDock관리자::애드독사이트](#adddocksite)|도크 창을 만들고 컨트롤 막대 목록에 추가합니다.|
|[도킹 매니저::추가 숨겨진MDITabbedBar](#addhiddenmditabbedbar)|숨겨진 MDI 탭 바 창 목록에 막대 창에 핸들을 추가합니다.|
|[도킹 매니저::애드미니프레임](#addminiframe)|미니 프레임 목록에 프레임을 추가합니다.|
|[CDockingManager::애드파인](#addpane)|도킹 관리자에 창을 등록합니다.|
|[CDockingManager::adjustDocking레이아웃](#adjustdockinglayout)|프레임 창에서 모든 창의 레이아웃을 다시 계산하고 조정합니다.|
|[도킹 매니저::조정페네프레임](#adjustpaneframes)|WM_NCCALCSIZE 메시지가 모든 창과 `CPaneFrameWnd` 창으로 전송됩니다.|
|[CDockingManager::adjustRectToClientarea](#adjustrecttoclientarea)|사각형의 정렬을 조정합니다.|
|[CDockingManager::정렬자동하이드파인](#alignautohidepane)|도킹 영역으로 둘러싸인 프레임 클라이언트 영역의 전체 너비 또는 높이를 차지하므로 자동 숨기기 모드에서 도킹 창의 크기를 조정합니다.|
|[CDockingManager:::자동 숨기기 파인](#autohidepane)|자동 숨기기 도구 모음을 만듭니다.|
|[도킹 매니저::브링바토탑](#bringbarstotop)|지정된 정렬이 있는 도킹된 막대를 맨 위에 가져옵니다.|
|[CDockingManager::빌드파네스메뉴](#buildpanesmenu)|도킹 창 및 도구 모음의 이름을 메뉴에 추가합니다.|
|[CDockingManager:::CalcExpectedDockedRect](#calcexpecteddockedrect)|도킹된 창의 예상 사각형을 계산합니다.|
|[CDock관리자::만들기](#create)|도킹 관리자를 만듭니다.|
|[CDockingManager::D에테르미니네앤스테이터스](#determinepaneandstatus)|지정된 점과 도킹 상태를 포함하는 창을 결정합니다.|
|[CDockingManager::D실행 가능한복원독상태](#disablerestoredockstate)|레지스트리에서 도킹 레이아웃 로드를 활성화하거나 사용하지 않도록 설정합니다.|
|[도킹매니저::D오크파인](#dockpane)|창을 다른 창이나 프레임 창에 도킹합니다.|
|[도킹매니저::D오크파네레프트](#dockpaneleftof)|창을 다른 창의 왼쪽에 도킹합니다.|
|[CDockingManager::인에이블오토하이드파인](#enableautohidepanes)|창을 주 프레임에 도킹하고, 도크 창을 만들고, 컨트롤 막대 목록에 추가합니다.|
|[C도킹 관리자::사용 독킹](#enabledocking)|도크 창을 만들고 창을 주 프레임에 도킹할 수 있습니다.|
|[CDock관리자::인에이블독사이트메뉴](#enabledocksitemenu)|모든 도킹 창의 캡션에 팝업 메뉴를 여는 추가 단추를 표시합니다.|
|[CDockingManager::인에이블파인컨텍스트메뉴](#enablepanecontextmenu)|사용자가 오른쪽 마우스 단추를 클릭하고 라이브러리에서 WM_CONTEXTMENU 메시지를 처리할 때 응용 프로그램 도구 모음 및 도킹 창 목록이 있는 특수 컨텍스트 메뉴를 표시하도록 라이브러리에 지시합니다.|
|[CDock관리자::찾기 독사이트](#finddocksite)|지정된 위치에 있고 지정된 선형이 있는 막대 창을 검색합니다.|
|[CDockingManager:::찾기독사이트비파인](#finddocksitebypane)|대상 막대 창의 ID가 있는 막대 창을 반환합니다.|
|[도킹 매니저:::찾기파네바이드](#findpanebyid)|지정된 컨트롤 ID로 창을 찾습니다.|
|[CDockingManager::수정가상 렉트](#fixupvirtualrects)|모든 현재 도구 모음 위치를 가상 사각형에 커밋합니다.|
|[도킹 매니저::프레임From포인트](#framefrompoint)|지정된 점을 포함하는 프레임을 반환합니다.|
|[CDockingManager::겟클라이언트아리어바운드](#getclientareabounds)|클라이언트 영역의 경계가 포함된 사각형을 가져옵니다.|
|[CDockingManager::GetDocking모드](#getdockingmode)|현재 도킹 모드를 반환합니다.|
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|부모 창 프레임에 대한 포인터를 가져옵니다.|
|[CDockingManager::GetEnabled자동하이드정렬](#getenabledautohidealignment)|창의 활성화된 정렬을 반환합니다.|
|[도킹 매니저::겟미니프레임](#getminiframes)|미니프레임 목록을 가져옵니다.|
|[CDockingManager::GetOuterEdge바운드](#getouteredgebounds)|프레임의 외부 모서리를 포함하는 사각형을 가져옵니다.|
|[CDockingManager::GetPaneList](#getpanelist)|도킹 관리자에 속한 창 목록을 반환합니다. 여기에는 모든 부동 창이 포함됩니다.|
|[CDockingManager::GetSmartDock관리자](#getsmartdockingmanager)|스마트 도킹 관리자에 대한 포인터를 검색합니다.|
|[CDockingManager::GetSmartDock관리자 영구](#getsmartdockingmanagerpermanent)|스마트 도킹 관리자에 대한 포인터를 검색합니다.|
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|도킹 관리자에 대한 스마트 도킹 매개 변수를 반환합니다.|
|[CDockingManager::겟스마트도킹테마](#getsmartdockingtheme)|스마트 도킹 마커를 표시하는 데 사용되는 테마를 반환하는 정적 메서드입니다.|
|[CDockingManager:::숨어있는하이드로이드파인](#hideautohidepanes)|자동 숨기기 모드에 있는 창을 숨깁니다.|
|[CDock관리자::삽입 독 사이트](#insertdocksite)|도크 창을 만들고 컨트롤 막대 목록에 삽입합니다.|
|[CDockingManager::삽입창](#insertpane)|컨트롤 창을 컨트롤 막대 목록에 삽입합니다.|
|[도킹 매니저::IsDockSiteMenu](#isdocksitemenu)|팝업 메뉴가 모든 창의 캡션에 표시되는지 여부를 지정합니다.|
|[CDockingManager::IsInadjust레이아웃](#isinadjustlayout)|모든 창의 레이아웃이 조정되는지 여부를 결정합니다.|
|[도킹 매니저:::이솔컨테이너모드](#isolecontainermode)|도킹 관리자가 OLE 컨테이너 모드에 있는지 여부를 지정합니다.|
|[도킹 매니저::이스포인트니어독사이트](#ispointneardocksite)|지정된 점이 도크 사이트 근처에 있는지 여부를 결정합니다.|
|[CDockingManager::IsPrint미리보기 유효](#isprintpreviewvalid)|인쇄 미리 보기 모드가 설정되어 있는지 확인합니다.|
|[CDockingManager::로드 스테이트](#loadstate)|레지스트리에서 도킹 관리자의 상태를 로드합니다.|
|[CDockingManager::잠금 업데이트](#lockupdate)|지정된 창을 잠그습니다.|
|[도킹 매니저::온인즈프레임](#onactivateframe)|프레임 창이 활성화되거나 비활성화될 때 프레임워크에서 호출됩니다.|
|[CDockingManager::에 닫닫기 팝업 메뉴](#onclosepopupmenu)|활성 팝업 메뉴에서 WM_DESTROY 메시지를 처리할 때 프레임워크에서 호출됩니다.|
|[도킹 매니저::온무드미니프레임](#onmoveminiframe)|프레임 워크에서 호출하여 미니 프레임 창을 이동합니다.|
|[CDockingManager::온파네컨텍스트메뉴](#onpanecontextmenu)|창 목록이 있는 메뉴를 빌드할 때 프레임워크에서 호출합니다.|
|[도킹매니저::P인FromPoint](#panefrompoint)|지정된 점을 포함하는 창을 반환합니다.|
|[CDockingManager::P로케스파네컨텍스트메뉴명령](#processpanecontextmenucommand)|프레임워크에서 지정된 명령에 대한 확인란을 선택하거나 지우고 표시된 창의 레이아웃을 다시 계산하도록 합니다.|
|[CDockingManager::RecalcLayout](#recalclayout)|컨트롤 목록에 있는 컨트롤의 내부 레이아웃을 다시 계산합니다.|
|[CDockingManager::릴리스빈파네컨테이너](#releaseemptypanecontainers)|빈 창 컨테이너를 해제합니다.|
|[도킹 매니저::제거숨겨진MDITabbedBar](#removehiddenmditabbedbar)|지정된 숨겨진 막대 창을 제거합니다.|
|[도킹 매니저::제거미니프레임](#removeminiframe)|미니 프레임 목록에서 지정된 프레임을 제거합니다.|
|[CDockingManager::제거페네From독매니저](#removepanefromdockmanager)|창을 등록 취소하고 도킹 관리자의 목록에서 창이 제거됩니다.|
|[CDockingManager::대체창](#replacepane)|한 창을 다른 창으로 대체합니다.|
|[도킹매니저::리조트미니프레임포어더](#resortminiframesforzorder)|미니 프레임 목록에 프레임을 리조트.|
|[CDockingManager::저장 상태](#savestate)|도킹 관리자의 상태를 레지스트리에 저장합니다.|
|[도킹 매니저::센드 메시지토미니프레임](#sendmessagetominiframes)|지정된 메시지를 모든 미니 프레임에 보냅니다.|
|[CDock관리자::직렬화](#serialize)|도킹 관리자를 아카이브에 씁니다. ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)를 재정의합니다.)|
|[도킹 매니저::SetAutohideZOrder](#setautohidezorder)|컨트롤 막대와 지정된 창의 크기, 너비 및 높이를 설정합니다.|
|[CDockingManager::SetDocking모드](#setdockingmode)|도킹 모드를 설정합니다.|
|[CDockingManager::SetDockState](#setdockstate)|컨트롤 막대, 미니 프레임 및 자동 숨기기 막대의 도킹 상태를 설정합니다.|
|[CDockingManager:::세트프린트 프리뷰모드](#setprintpreviewmode)|인쇄 미리 보기에 표시되는 막대의 인쇄 미리 보기 모드를 설정합니다.|
|[CDockingManager:::SetSmartDockingParams](#setsmartdockingparams)|스마트 도킹의 동작을 정의하는 매개 변수를 설정합니다.|
|[CDockingManager::쇼지연쇼미니프레임](#showdelayshowminiframes)|미니 프레임의 창을 표시하거나 숨깁니다.|
|[도킹 매니저::쇼파네스](#showpanes)|컨트롤 및 자동 숨기기 막대의 창을 표시하거나 숨깁니다.|
|[CDockingManager::시작스도킹](#startsdocking)|스마트 도킹 관리자의 정렬에 따라 지정된 창의 스마트 도킹을 시작합니다.|
|[CDockingManager::중지스독킹](#stopsdocking)|스마트 도킹을 중지합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[도킹 관리자::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|도킹 관리자가 OLE 컨테이너 모드에서 창을 숨길지 여부를 지정합니다.|
|[도킹 매니저::m_dockModeGlobal](#m_dockmodeglobal)|전역 도킹 모드를 지정합니다.|
|[도킹 관리자::m_nDockSensitivity](#m_ndocksensitivity)|도킹 민감도를 지정합니다.|
|[도킹 매니저::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|도킹 창이 즉시 도킹 모드에서 도킹되기 전의 시간을 밀리초 단위로 지정합니다.|
|[도킹 매니저::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|도구 모음이 주 프레임 창에 도킹되기 전의 시간을 밀리초 단위로 지정합니다.|

## <a name="remarks"></a>설명

주 프레임 창은 이 클래스를 자동으로 만들고 초기화합니다.

도킹 관리자 개체에는 도킹 레이아웃에 있는 모든 창 목록과 주 프레임 창에 속하는 모든 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) 창 목록이 있습니다.

클래스는 `CDockingManager` 창 이나 창을 찾는 데 사용할 수 `CPaneFrameWnd` 있는 일부 서비스를 구현 합니다. 일반적으로 이러한 서비스는 주 프레임 창 개체에 래핑되므로 직접 호출하지 않습니다. 자세한 내용은 [CPaneFrameWnd 클래스를](../../mfc/reference/cpaneframewnd-class.md)참조하십시오.

## <a name="customization-tips"></a>사용자 지정 팁

다음 팁은 `CDockingManager` 개체에 적용됩니다.

- [CDockingManager 클래스는](../../mfc/reference/cdockingmanager-class.md) 다음 도킹 모드를 지원합니다.

  - `AFX_DOCK_TYPE::DT_IMMEDIATE`

  - `AFX_DOCK_TYPE::DT_STANDARD`

  - `AFX_DOCK_TYPE::DT_SMART`

  이러한 도킹 모드는 [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) 의해 정의되며 [CDockingManager::SetDockingMode](#setdockingmode)를 호출하여 설정됩니다.

- 부동 되지 않는, 비 조정 창을 만들려면 [CDockingManager::AddPane](#addpane) 메서드를 호출 합니다. 이 메서드는 창의 레이아웃을 담당하는 도킹 관리자에 창을 등록합니다.

## <a name="example"></a>예제

다음 예제에서는 클래스에서 개체를 구성 `CDockingManager` 하는 다양 `CDockingManager` 한 메서드를 사용 하는 방법을 보여 줍니다. 이 예제에서는 모든 도킹 창의 캡션에 팝업 메뉴를 여는 추가 단추를 표시하는 방법과 개체의 도킹 모드를 설정하는 방법을 보여 줍니다. 이 코드 조각은 Visual [Studio 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CDockingManager](../../mfc/reference/cdockingmanager-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDockingManager.h

## <a name="cdockingmanageradddocksite"></a><a name="adddocksite"></a>CDock관리자::애드독사이트

도크 창을 만들고 컨트롤 막대 목록에 추가합니다.

```
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>매개 변수

*정보*<br/>
【인】 도크 창 정렬이 포함된 정보 구조에 대한 참조입니다.

*ppDockBar*<br/>
【아웃】 새 도크 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

도크 창이 성공적으로 생성된 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cdockingmanageraddhiddenmditabbedbar"></a><a name="addhiddenmditabbedbar"></a>도킹 매니저::추가 숨겨진MDITabbedBar

숨겨진 MDI 탭 바 창 목록에 막대 창에 핸들을 추가합니다.

```cpp
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 막대 창에 대한 포인터

## <a name="cdockingmanageraddpane"></a><a name="addpane"></a>CDockingManager::애드파인

도킹 관리자에 창을 등록합니다.

```
BOOL AddPane(
    CBasePane* pWnd,
    BOOL bTail = TRUE,
    BOOL bAutoHide = FALSE,
    BOOL bInsertForOuterEdge = FALSE);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인, 아웃】 도킹 관리자에 추가할 창을 지정합니다.

*b테일 (것)들*<br/>
【인】 TRUE 도킹 관리자에 대 한 창 목록의 끝에 창을 추가 합니다. 그렇지 않으면 false입니다.

*b자동 숨기기*<br/>
【인】 내부 용으로만 사용하십시오. 항상 기본값 FALSE를 사용합니다.

*b인서인더OuterEdge*<br/>
【인】 내부 용으로만 사용하십시오. 항상 기본값 FALSE를 사용합니다.

### <a name="return-value"></a>Return Value

창이 도킹 관리자에 성공적으로 등록된 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 부동, 재지정이 불가능한 창을 도킹 관리자에 등록합니다. 창을 등록하지 않으면 도킹 관리자가 배치될 때 창이 올바르게 나타나지 않습니다.

## <a name="cdockingmanageradjustdockinglayout"></a><a name="adjustdockinglayout"></a>CDockingManager::adjustDocking레이아웃

프레임 창에서 모든 창의 레이아웃을 다시 계산하고 조정합니다.

```
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```

### <a name="parameters"></a>매개 변수

*HDWP*<br/>
【인】 지연된 창 위치 구조를 지정합니다. 자세한 내용은 [Windows 데이터 형식](/windows/win32/WinProg/windows-data-types)을 참조하세요.

### <a name="remarks"></a>설명

## <a name="cdockingmanageraddminiframe"></a><a name="addminiframe"></a>도킹 매니저::애드미니프레임

미니 프레임 목록에 프레임을 추가합니다.

```
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 프레임에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 프레임이 미니 프레임 목록에 없고 성공적으로 추가된 경우 그렇지 않으면 거짓.

## <a name="cdockingmanageradjustpaneframes"></a><a name="adjustpaneframes"></a>도킹 매니저::조정페네프레임

WM_NCCALCSIZE 메시지가 모든 창과 `CPaneFrameWnd` 창으로 전송됩니다.

```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>설명

## <a name="cdockingmanageradjustrecttoclientarea"></a><a name="adjustrecttoclientarea"></a>CDockingManager::adjustRectToClientarea

사각형의 정렬을 조정합니다.

```
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,
    DWORD dwAlignment);
```

### <a name="parameters"></a>매개 변수

*정류 결과*<br/>
【인】 `CRect` 개체에 대한 참조

*dw정렬*<br/>
【인】 `CRect` 개체의 정렬

### <a name="return-value"></a>Return Value

TRUE 개체의 정렬이 `CRect` 조정된 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

*dwAlignment* 매개 변수는 다음 값 중 하나를 가질 수 있습니다.

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

## <a name="cdockingmanageralignautohidepane"></a><a name="alignautohidepane"></a>CDockingManager::정렬자동하이드파인

도킹 영역으로 둘러싸인 프레임 클라이언트 영역의 전체 너비 또는 높이를 차지하므로 자동 숨기기 모드에서 도킹 창의 크기를 조정합니다.

```cpp
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,
    BOOL bIsVisible = TRUE);
```

### <a name="parameters"></a>매개 변수

*p디폴디폴 슬라이더*<br/>
【인】 도킹 슬라이더 창입니다.

*bIsVisible*<br/>
【인】 도킹 창이 표시되는 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cdockingmanagerautohidepane"></a><a name="autohidepane"></a>CDockingManager:::자동 숨기기 파인

자동 숨기기 도구 모음을 만듭니다.

```
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 막대 창에 대한 포인터입니다.

*pCurr자동하이드툴바*<br/>
【인】 자동 숨기기 도구 모음에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

자동 숨기기 도구 모음이 만들어지지 않은 경우 NULL; 그렇지 않으면 새 도구 모음에 대한 포인터입니다.

## <a name="cdockingmanagerbringbarstotop"></a><a name="bringbarstotop"></a>도킹 매니저::브링바토탑

지정된 정렬이 있는 도킹된 막대를 맨 위에 가져옵니다.

```cpp
void BringBarsToTop(
    DWORD dwAlignment = 0,
    BOOL bExcludeDockedBars = TRUE);
```

### <a name="parameters"></a>매개 변수

*dw정렬*<br/>
【인】 다른 창의 맨 위로 가져온 도크 막대의 정렬입니다.

*bExcludeDocked바*<br/>
【인】 도킹된 막대가 맨 위에 있는 것을 제외하려면 TRUE; 그렇지 않으면 거짓.

## <a name="cdockingmanagerbuildpanesmenu"></a><a name="buildpanesmenu"></a>CDockingManager::빌드파네스메뉴

도킹 창 및 도구 모음의 이름을 메뉴에 추가합니다.

```cpp
void BuildPanesMenu(
    CMenu& menu,
    BOOL bToolbarsOnly);
```

### <a name="parameters"></a>매개 변수

*메뉴*<br/>
【인】 도킹 창 및 도구 모음의 이름을 추가하는 메뉴입니다.

*b도구 바만*<br/>
【인】 TRUE 메뉴에 도구 모음 이름만 추가합니다. 그렇지 않으면 거짓.

## <a name="cdockingmanagercalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CDockingManager:::CalcExpectedDockedRect

도킹된 창의 예상 사각형을 계산합니다.

```cpp
void CalcExpectedDockedRect(
    CWnd* pWnd,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 도킹할 창에 대한 포인터입니다.

*pt마우스*<br/>
【인】 마우스 위치입니다.

*정류 결과*<br/>
【아웃】 계산된 사각형입니다.

*b그리기 탭*<br/>
【인】 탭을 그리는 TRUE; 그렇지 않으면 거짓.

*ppTargetBar*<br/>
【아웃】 대상 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 사용자가 *ptMouse에* 의해 지정 된 지점으로 창을 드래그 하 고 거기 도킹 하는 경우 창이 차지 하는 사각형을 계산 합니다.

## <a name="cdockingmanagercreate"></a><a name="create"></a>CDock관리자::만들기

도킹 관리자를 만듭니다.

```
BOOL Create(CFrameWnd* pParentWnd);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
【인】 도킹 관리자의 상위 프레임에 대한 포인터입니다. 이 값은 NULL이 아니어야 합니다.

### <a name="return-value"></a>Return Value

항상 사실.

## <a name="cdockingmanagerdeterminepaneandstatus"></a><a name="determinepaneandstatus"></a>CDockingManager::D에테르미니네앤스테이터스

지정된 점과 도킹 상태를 포함하는 창을 결정합니다.

```
virtual AFX_CS_STATUS DeterminePaneAndStatus(
    CPoint pt,
    int nSensitivity,
    DWORD dwEnabledAlignment,
    CBasePane** ppTargetBar,
    const CBasePane* pBarToIgnore,
    const CBasePane* pBarToDock);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
【인】 확인할 창의 위치입니다.

*n감도*<br/>
【인】 확인된 각 창의 창 사각형을 늘리는 값입니다. 지정된 지점이 이 증가된 영역에 있는 경우 창은 검색 조건을 충족합니다.

*dw활성화정렬*<br/>
【인】 도킹 창의 정렬입니다.

*ppTargetBar*<br/>
【아웃】 대상 창에 대한 포인터입니다.

*pBarToIgnore*<br/>
【인】 메서드가 무시하는 창입니다.

*pBarToDock*<br/>
【인】 도킹된 창입니다.

### <a name="return-value"></a>Return Value

도킹 상태입니다.

### <a name="remarks"></a>설명

도킹 상태는 다음 값 중 하나일 수 있습니다.

|AFX_CS_STATUS 값|의미|
|---------------------------|-------------|
|CS_NOTHING|포인터가 도크 사이트 위에 있지 않습니다. 따라서 창을 부동 상태로 유지합니다.|
|CS_DOCK_IMMEDIATELY|포인터가 즉시 모드(DT_IMMEDIATE 스타일이 활성화됨)의 도크 사이트 위에 있으므로 창을 즉시 도킹해야 합니다.|
|CS_DELAY_DOCK|포인터가 다른 도킹 창이거나 주 프레임의 가장자리인 도크 사이트 위에 있습니다.|
|CS_DELAY_DOCK_TO_TAB|포인터가 탭된 창에 도킹되도록 하는 도크 사이트 위에 있습니다. 이 문제는 마우스가 다른 도킹 창의 캡션 위에 있거나 탭된 창의 탭 영역 위에 있을 때 발생합니다.|

## <a name="cdockingmanagerdisablerestoredockstate"></a><a name="disablerestoredockstate"></a>CDockingManager::D실행 가능한복원독상태

레지스트리에서 도킹 레이아웃 로드를 활성화하거나 사용하지 않도록 설정합니다.

```cpp
void DisableRestoreDockState(BOOL bDisable = TRUE);
```

### <a name="parameters"></a>매개 변수

*b사용 안 함*<br/>
【인】 TRUE 레지스트리에서 도킹 레이아웃로드를 사용하지 않도록 설정합니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

응용 프로그램 상태가 로드될 때 도킹 창 및 도구 모음의 현재 레이아웃을 유지해야 하는 경우 이 메서드를 호출합니다.

## <a name="cdockingmanagerdockpane"></a><a name="dockpane"></a>도킹매니저::D오크파인

창을 다른 창이나 프레임 창에 도킹합니다.

```cpp
void DockPane(
    CBasePane* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 도킹할 막대 창에 대한 포인터입니다.

*nDockBarID*<br/>
【인】 도킹할 막대의 ID입니다.

*Lprect*<br/>
【인】 대상 사각형입니다.

## <a name="cdockingmanagerdockpaneleftof"></a><a name="dockpaneleftof"></a>도킹매니저::D오크파네레프트

창을 다른 창의 왼쪽에 도킹합니다.

```
BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>매개 변수

*pBarToDock*<br/>
【인】 *pTargetBar의*왼쪽에 도킹할 창에 대한 포인터입니다.

*pTargetBar*<br/>
【인】 대상 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 창이 성공적으로 도킹된 경우; 그렇지 않으면 false입니다.

## <a name="cdockingmanagerenableautohidepanes"></a><a name="enableautohidepanes"></a>CDockingManager::인에이블오토하이드파인

창을 주 프레임에 도킹하고, 도크 창을 만들고, 컨트롤 막대 목록에 추가합니다.

```
BOOL EnableAutoHidePanes(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
【인】 도킹 정렬입니다.

### <a name="return-value"></a>Return Value

도크 창이 성공적으로 생성된 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cdockingmanagerenabledocking"></a><a name="enabledocking"></a>C도킹 관리자::사용 독킹

도크 창을 만들고 창을 주 프레임에 도킹할 수 있습니다.

```
BOOL EnableDocking(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
【인】 도킹 정렬입니다.

### <a name="return-value"></a>Return Value

도크 창이 성공적으로 생성된 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cdockingmanagerenabledocksitemenu"></a><a name="enabledocksitemenu"></a>CDock관리자::인에이블독사이트메뉴

모든 도킹 창의 캡션에 팝업 메뉴를 여는 추가 단추를 표시합니다.

```
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE도크 사이트 메뉴를 활성화합니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

도크 사이트 메뉴에는 창의 도킹 상태를 변경하기 위한 다음 옵션이 표시됩니다.

- `Floating`- 창을 띄우기

- `Docking`- 창이 마지막으로 도킹된 위치에서 메인 프레임에 창을 도킹합니다.

- `AutoHide`- 자동 숨기기 모드로 창을 전환

- `Hide`- 창을 숨깁니다.

기본적으로 이 메뉴는 표시되지 않습니다.

## <a name="cdockingmanagerenablepanecontextmenu"></a><a name="enablepanecontextmenu"></a>CDockingManager::인에이블파인컨텍스트메뉴

사용자가 오른쪽 마우스 단추를 클릭하고 라이브러리에서 WM_CONTEXTMENU 메시지를 처리할 때 응용 프로그램 도구 모음 및 도킹 창 목록이 있는 특수 컨텍스트 메뉴를 표시하도록 라이브러리에 지시합니다.

```cpp
void EnablePaneContextMenu(
    BOOL bEnable,
    UINT uiCustomizeCmd,
    const CString& strCustomizeText,
    BOOL bToolbarsOnly = FALSE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE이면 라이브러리는 자동 컨텍스트 메뉴에 대한 지원을 켭니다. FALSE인 경우 라이브러리는 자동 컨텍스트 메뉴에 대한 지원을 끕니다.

*ui사용자 정의Cmd*<br/>
【인】 메뉴에서 사용자 **지정** 항목에 대한 명령 ID입니다.

*str사용자 정의 텍스트*<br/>
【인】 사용자 지정 항목의 **텍스트입니다.**

*b도구 바만*<br/>
【인】 TRUE이면 메뉴에 응용 프로그램 도구 모음 목록만 표시됩니다. FALSE인 경우 라이브러리는 이 목록에 응용 프로그램 도킹 창을 추가합니다.

## <a name="cdockingmanagerfinddocksite"></a><a name="finddocksite"></a>CDock관리자::찾기 독사이트

지정된 위치에 있고 지정된 선형이 있는 막대 창을 검색합니다.

```
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,
    BOOL bOuter);
```

### <a name="parameters"></a>매개 변수

*dw정렬*<br/>
【인】 막대 창의 정렬입니다.

*b아우터*<br/>
【인】 TRUE인 경우 컨트롤 막대 목록에서 헤드 위치에 있는 막대를 검색합니다. 그렇지 않으면 컨트롤 막대 목록의 꼬리 위치에 있는 막대를 검색합니다.

### <a name="return-value"></a>Return Value

지정된 맞춤이 있는 도킹 창입니다. 그렇지 않으면 NULL.

## <a name="cdockingmanagerfindpanebyid"></a><a name="findpanebyid"></a>도킹 매니저:::찾기파네바이드

지정된 컨트롤 ID로 창을 찾습니다.

```
virtual CBasePane* FindPaneByID(
    UINT uBarID,
    BOOL bSearchMiniFrames = FALSE);
```

### <a name="parameters"></a>매개 변수

*uBarID*<br/>
【인】 찾을 창의 컨트롤 ID를 지정합니다.

*b서치미니프레임*<br/>
【인】 TRUE는 검색에 모든 부동 창을 포함합니다. FALSE는 도킹된 창만 포함합니다.

### <a name="return-value"></a>Return Value

지정된 컨트롤 ID가 있는 [CBasePane](../../mfc/reference/cbasepane-class.md) 개체 또는 지정된 창을 찾을 수 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

## <a name="cdockingmanagerfinddocksitebypane"></a><a name="finddocksitebypane"></a>CDockingManager:::찾기독사이트비파인

대상 막대 창의 ID가 있는 막대 창을 반환합니다.

```
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```

### <a name="parameters"></a>매개 변수

*pTargetBar*<br/>
【인】 대상 막대 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

대상 막대 창의 ID를 가지는 막대 창; 이러한 막대 창이 없는 경우 NULL입니다.

## <a name="cdockingmanagerfixupvirtualrects"></a><a name="fixupvirtualrects"></a>CDockingManager::수정가상 렉트

모든 현재 도구 모음 위치를 가상 사각형에 커밋합니다.

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>설명

사용자가 도구 모음을 드래그하기 시작하면 응용 프로그램은 *가상 사각형의*원래 위치를 기억합니다. 사용자가 도구 모음을 도크 사이트 전체에서 이동하면 도구 모음이 다른 도구 모음을 이동할 수 있습니다. 다른 도구 모음의 원래 위치는 해당 가상 사각형에 저장됩니다.

## <a name="cdockingmanagerframefrompoint"></a><a name="framefrompoint"></a>도킹 매니저::프레임From포인트

지정된 점을 포함하는 프레임을 반환합니다.

```
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,
    CPaneFrameWnd* pFrameToExclude,
    BOOL bFloatMultiOnly) const;
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
【인】 검사할 점을 화면 좌표로 지정합니다.

*pFrame제외*<br/>
【인】 제외할 프레임에 대한 포인터입니다.

*bFloatMulti전용*<br/>
【인】 TRUE의 인스턴스가 아닌 프레임을 `CMultiPaneFrameWnd`제외합니다. 그렇지 않으면 거짓.

### <a name="return-value"></a>Return Value

지정된 점을 포함하는 프레임; 그렇지 않으면 NULL.

## <a name="cdockingmanagergetclientareabounds"></a><a name="getclientareabounds"></a>CDockingManager::겟클라이언트아리어바운드

클라이언트 영역의 경계가 포함된 사각형을 가져옵니다.

```
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```

### <a name="parameters"></a>매개 변수

*rcClient*<br/>
【아웃】 클라이언트 영역의 경계가 포함된 사각형에 대한 참조입니다.

### <a name="return-value"></a>Return Value

클라이언트 영역의 경계를 포함하는 사각형입니다.

## <a name="cdockingmanagergetdockingmode"></a><a name="getdockingmode"></a>CDockingManager::GetDocking모드

현재 도킹 모드를 반환합니다.

```
static AFX_DOCK_TYPE GetDockingMode();
```

### <a name="return-value"></a>Return Value

현재 도킹 모드를 나타내는 열거형 값입니다. 다음 값 중 하나일 수 있습니다.

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

### <a name="remarks"></a>설명

도킹 모드를 설정하려면 [CDockingManager::SetDockingMode](#setdockingmode)를 호출합니다.

## <a name="cdockingmanagergetdocksiteframewnd"></a><a name="getdocksiteframewnd"></a>CDockingManager::GetDockSiteFrameWnd

부모 창 프레임에 대한 포인터를 가져옵니다.

```
CFrameWnd* GetDockSiteFrameWnd() const;
```

### <a name="return-value"></a>Return Value

상위 창 프레임에 대한 포인터입니다.

## <a name="cdockingmanagergetenabledautohidealignment"></a><a name="getenabledautohidealignment"></a>CDockingManager::GetEnabled자동하이드정렬

창의 활성화된 정렬을 반환합니다.

```
DWORD GetEnabledAutoHideAlignment() const;
```

### <a name="return-value"></a>Return Value

CBRS_ALIGN_ 플래그의 비트 조합 또는 0 자동 숨기기 창을 사용할 수 없는 경우. 자세한 내용은 [CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking)을 참조하십시오.

### <a name="remarks"></a>설명

메서드는 자동 숨기기 컨트롤 막대에 대해 활성화된 정렬을 반환합니다. 자동 숨기기 막대를 사용하려면 [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes)를 호출합니다.

## <a name="cdockingmanagergetminiframes"></a><a name="getminiframes"></a>도킹 매니저::겟미니프레임

미니프레임 목록을 가져옵니다.

```
const CObList& GetMiniFrames() const;
```

### <a name="return-value"></a>Return Value

도킹 관리자에 속하는 컨트롤 막대가 포함된 미니프레임 목록입니다.

## <a name="cdockingmanagergetouteredgebounds"></a><a name="getouteredgebounds"></a>CDockingManager::GetOuterEdge바운드

프레임의 외부 모서리를 포함하는 사각형을 가져옵니다.

```
CRect GetOuterEdgeBounds() const;
```

### <a name="return-value"></a>Return Value

프레임의 외부 모서리를 포함하는 사각형입니다.

## <a name="cdockingmanagergetpanelist"></a><a name="getpanelist"></a>CDockingManager::GetPaneList

도킹 관리자에 속한 창 목록을 반환합니다. 여기에는 모든 부동 창이 포함됩니다.

```cpp
void GetPaneList(
    CObList& lstBars,
    BOOL bIncludeAutohide = FALSE,
    CRuntimeClass* pRTCFilter = NULL,
    BOOL bIncludeTabs = FALSE);
```

### <a name="parameters"></a>매개 변수

*lstBar*<br/>
【인, 아웃】 현재 도킹 관리자의 모든 창을 포함합니다.

*b포함자동하이드*<br/>
【인】 TRUE는 자동 숨기기 모드에 있는 창을 포함합니다. 그렇지 않으면 false입니다.

*pRTC필터*<br/>
【인】 NULL이 아닌 경우 반환된 목록에는 지정된 런타임 클래스의 창만 포함됩니다.

*b탭 포함*<br/>
【인】 TRUE 탭을 포함; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

도킹 관리자에 탭된 창이 있는 경우 메서드는 [CBaseTabbedPane 클래스](../../mfc/reference/cbasetabbedpane-class.md) 개체에 대한 포인터를 반환하며 탭을 명시적으로 지정해야 합니다.

*pRTCFilter를* 사용하여 특정 창 클래스를 가져옵니다. 예를 들어 이 값을 적절하게 설정하여 도구 모음만 가져올 수 있습니다.

## <a name="cdockingmanagergetsmartdockingmanager"></a><a name="getsmartdockingmanager"></a>CDockingManager::GetSmartDock관리자

스마트 도킹 관리자에 대한 포인터를 검색합니다.

```
CSmartDockingManager* GetSmartDockingManager();
```

### <a name="return-value"></a>Return Value

스마트 도킹 관리자에 대한 포인터입니다.

## <a name="cdockingmanagergetsmartdockingmanagerpermanent"></a><a name="getsmartdockingmanagerpermanent"></a>CDockingManager::GetSmartDock관리자 영구

스마트 도킹 관리자에 대한 포인터를 검색합니다.

```
CSmartDockingManager* GetSmartDockingManagerPermanent() const;
```

### <a name="return-value"></a>Return Value

스마트 도킹 관리자에 대한 포인터입니다.

## <a name="cdockingmanagergetsmartdockingparams"></a><a name="getsmartdockingparams"></a>CDockingManager::GetSmartDockingParams

도킹 관리자에 대한 스마트 도킹 매개 변수를 반환합니다.

```
static CSmartDockingInfo& GetSmartDockingParams();
```

### <a name="return-value"></a>Return Value

현재 도킹 관리자에 대한 스마트 도킹 매개 변수를 포함하는 클래스입니다. 자세한 내용은 [CSmartDockingInfo 클래스를](../../mfc/reference/csmartdockinginfo-class.md)참조하십시오.

### <a name="remarks"></a>설명

## <a name="cdockingmanagerhideautohidepanes"></a><a name="hideautohidepanes"></a>CDockingManager:::숨어있는하이드로이드파인

자동 숨기기 모드에 있는 창을 숨깁니다.

```cpp
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,
    BOOL bImmediately = FALSE);
```

### <a name="parameters"></a>매개 변수

*pBarTo제외*<br/>
【인】 숨기기에서 제외할 막대에 대한 포인터입니다.

*b즉시*<br/>
【인】 TRUE는 창을 즉시 숨길 수 있습니다. FALSE를 사용하여 자동 숨기기 효과로 창을 숨깁니다.

## <a name="cdockingmanagerinsertdocksite"></a><a name="insertdocksite"></a>CDock관리자::삽입 독 사이트

도크 창을 만들고 컨트롤 막대 목록에 삽입합니다.

```
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,
    DWORD dwAlignToInsertAfter,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>매개 변수

*정보*<br/>
【인】 도크 창에 대한 정렬 정보가 포함된 구조입니다.

*dwAlignTo인더*<br/>
【인】 도크 창의 정렬입니다.

*ppDockBar*<br/>
【아웃】 도크 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

도크 창이 성공적으로 생성된 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cdockingmanagerinsertpane"></a><a name="insertpane"></a>CDockingManager::삽입창

컨트롤 창을 컨트롤 막대 목록에 삽입합니다.

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>매개 변수

*p컨트롤바*<br/>
【인】 컨트롤 창에 대한 포인터입니다.

*p Target*<br/>
【인】 대상 창에 대한 포인터입니다.

*b애프터*<br/>
【인】 대상 창의 위치 후에 창을 삽입하는 TRUE; 그렇지 않으면 거짓.

### <a name="return-value"></a>Return Value

컨트롤 창이 컨트롤 막대 목록에 성공적으로 추가된 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 컨트롤 창이 이미 컨트롤 막대 목록에 있거나 대상 창이 컨트롤 막대 목록에 없는 경우 false를 반환합니다.

## <a name="cdockingmanagerisdocksitemenu"></a><a name="isdocksitemenu"></a>도킹 매니저::IsDockSiteMenu

팝업 메뉴가 모든 창의 캡션에 표시되는지 여부를 지정합니다.

```
static BOOL IsDockSiteMenu();
```

### <a name="return-value"></a>Return Value

TRUE 도킹 사이트 메뉴가 모든 도킹 창의 캡션에 표시되는 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

[CDock관리자::EnableDockSiteMenu를](#enabledocksitemenu)호출하여 도크 사이트 메뉴를 활성화할 수 있습니다.

## <a name="cdockingmanagerisinadjustlayout"></a><a name="isinadjustlayout"></a>CDockingManager::IsInadjust레이아웃

모든 창의 레이아웃이 조정되는지 여부를 결정합니다.

```
BOOL IsInAdjustLayout() const;
```

### <a name="return-value"></a>Return Value

모든 창의 레이아웃이 조정되는 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cdockingmanagerisolecontainermode"></a><a name="isolecontainermode"></a>도킹 매니저:::이솔컨테이너모드

도킹 관리자가 OLE 컨테이너 모드에 있는지 여부를 지정합니다.

```
BOOL IsOLEContainerMode() const;
```

### <a name="return-value"></a>Return Value

도킹 관리자가 OLE 컨테이너 모드에 있는 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

OLE 컨테이너 모드에서는 모든 도킹 창과 응용 프로그램 도구 모음이 숨김됩니다. [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) TRUE로 설정한 경우 창도 이 모드에서 숨김이 있습니다.

## <a name="cdockingmanagerispointneardocksite"></a><a name="ispointneardocksite"></a>도킹 매니저::이스포인트니어독사이트

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
【아웃】 점이 근처에 있는 모서리를 지정합니다. 가능한 값은 CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT, CBRS_ALIGN_TOP 및 CBRS_ALIGN_BOTTOM.

*bOuterEdge*<br/>
【아웃】 TRUE 점이 도크 사이트의 외부 테두리 근처에 있는 경우; 그렇지 않으면 거짓.

### <a name="return-value"></a>Return Value

포인트가 도크 사이트 근처에 있는 경우 TRUE; 그렇지 않으면 거짓.

## <a name="cdockingmanagerisprintpreviewvalid"></a><a name="isprintpreviewvalid"></a>CDockingManager::IsPrint미리보기 유효

인쇄 미리 보기 모드가 설정되어 있는지 확인합니다.

```
BOOL IsPrintPreviewValid() const;
```

### <a name="return-value"></a>Return Value

인쇄 미리 보기 모드가 설정된 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cdockingmanagerloadstate"></a><a name="loadstate"></a>CDockingManager::로드 스테이트

레지스트리에서 도킹 관리자의 상태를 로드합니다.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 프로필 이름입니다.

*uiID*<br/>
【인】 도킹 관리자의 ID입니다.

### <a name="return-value"></a>Return Value

도킹 관리자 상태가 성공적으로 로드된 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cdockingmanagerlockupdate"></a><a name="lockupdate"></a>CDockingManager::잠금 업데이트

지정된 창을 잠그습니다.

```cpp
void LockUpdate(BOOL bLock);
```

### <a name="parameters"></a>매개 변수

*블록*<br/>
【인】 창이 잠겨 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

창이 잠겨 있으면 이동할 수 없으며 다시 그릴 수 없습니다.

## <a name="cdockingmanagerm_bhidedockingbarsincontainermode"></a><a name="m_bhidedockingbarsincontainermode"></a>도킹 관리자::m_bHideDockingBarsInContainerMode

도킹 관리자가 OLE 컨테이너 모드에서 창을 숨길지 여부를 지정합니다.

```
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;
```

### <a name="remarks"></a>설명

응용 프로그램이 OLE 컨테이너 모드에 있을 때 모든 창을 주 프레임에 도킹된 상태로 유지하려면 이 값을 FALSE로 설정합니다. 기본적으로 이 값은 TRUE입니다.

## <a name="cdockingmanagerm_dockmodeglobal"></a><a name="m_dockmodeglobal"></a>도킹 매니저::m_dockModeGlobal

전역 도킹 모드를 지정합니다.

```
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;
```

### <a name="remarks"></a>설명

기본적으로 각 도킹 창은 이 도킹 모드를 사용합니다. 이 필드를 설정할 수 있는 값에 대한 자세한 내용은 [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode)을 참조하십시오.

## <a name="cdockingmanagerm_ndocksensitivity"></a><a name="m_ndocksensitivity"></a>도킹 관리자::m_nDockSensitivity

도킹 민감도를 지정합니다.

```
AFX_IMPORT_DATA static int m_nDockSensitivity;
```

### <a name="remarks"></a>설명

도킹 민감도는 프레임워크가 도킹된 상태로 변경하기 전에 부동 창이 도킹 창, 도킹 사이트 또는 다른 창에 접근할 수 있는 정도를 정의합니다.

## <a name="cdockingmanagerm_ntimeoutbeforedockingbardock"></a><a name="m_ntimeoutbeforedockingbardock"></a>도킹 매니저::m_nTimeOutBeforeDockingBarDock

도킹 창이 즉시 도킹 모드에서 도킹되기 전의 시간을 밀리초 단위로 지정합니다.

```
static UINT m_nTimeOutBeforeDockingBarDock;
```

### <a name="remarks"></a>설명

창이 도킹되기 전에 프레임워크는 지정된 시간 동안 대기합니다. 이렇게 하면 사용자가 창을 계속 드래그하는 동안 창이 실수로 위치에 도킹되는 것을 방지할 수 있습니다.

## <a name="cdockingmanagerm_ntimeoutbeforetoolbardock"></a><a name="m_ntimeoutbeforetoolbardock"></a>도킹 매니저::m_nTimeOutBeforeToolBarDock

도구 모음이 주 프레임 창에 도킹되기 전의 시간을 밀리초 단위로 지정합니다.

```
static UINT m_nTimeOutBeforeToolBarDock;
```

### <a name="remarks"></a>설명

도구 모음을 도킹하기 전에 프레임워크는 지정된 시간 동안 대기합니다. 이렇게 하면 사용자가 여전히 끌어당기는 동안 도구 모음이 실수로 위치에 도킹되는 것을 방지할 수 있습니다.

## <a name="cdockingmanageronactivateframe"></a><a name="onactivateframe"></a>도킹 매니저::온인즈프레임

프레임 창이 활성화되거나 비활성화될 때 프레임워크에서 호출됩니다.

```
virtual void OnActivateFrame(BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*bActivate*<br/>
【인】 TRUE이면 프레임 창이 활성화됩니다. FALSE이면 프레임 창이 비활성화됩니다.

## <a name="cdockingmanageronclosepopupmenu"></a><a name="onclosepopupmenu"></a>CDockingManager::에 닫닫기 팝업 메뉴

활성 팝업 메뉴에서 WM_DESTROY 메시지를 처리할 때 프레임워크에서 호출됩니다.

```cpp
void OnClosePopupMenu();
```

### <a name="remarks"></a>설명

프레임워크는 현재 기본 창을 닫을 때 WM_DESTROY 메시지를 보냅니다. 개체가 WM_DESTROY 메시지를 처리할 `CMFCPopupMenu` 때 `CMFCPopupMenu` 프레임 창에 속한 개체의 알림을 처리하려면 이 메서드를 재정의합니다.

## <a name="cdockingmanageronmoveminiframe"></a><a name="onmoveminiframe"></a>도킹 매니저::온무드미니프레임

프레임 워크에서 호출하여 미니 프레임 창을 이동합니다.

```
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```

### <a name="parameters"></a>매개 변수

*pFrame*<br/>
【인】 미니 프레임 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cdockingmanageronpanecontextmenu"></a><a name="onpanecontextmenu"></a>CDockingManager::온파네컨텍스트메뉴

창 목록이 있는 메뉴를 빌드할 때 프레임워크에서 호출합니다.

```cpp
void OnPaneContextMenu(CPoint point);
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
【인】 메뉴의 위치를 지정합니다.

## <a name="cdockingmanagerpanefrompoint"></a><a name="panefrompoint"></a>도킹매니저::P인FromPoint

지정된 점을 포함하는 창을 반환합니다.

```
virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    bool bExactBar = false,
    CRuntimeClass* pRTCBarType = NULL,
    BOOL bCheckVisibility = FALSE,
    const CBasePane* pBarToIgnore = NULL) const;

virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    DWORD& dwAlignment,
    CRuntimeClass* pRTCBarType = NULL,
    const CBasePane* pBarToIgnore = NULL) const;
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
【인】 검사할 점을 화면 좌표로 지정합니다.

*n감도*<br/>
【인】 확인된 각 창의 창 사각형을 팽창시키는 값입니다. 지정된 점이 이 팽창된 영역에 있는 경우 창은 검색 조건을 충족합니다.

*bExactBar*<br/>
【인】 *true는 nSensitivity* 매개 변수를 무시합니다. 그렇지 않으면 false입니다.

*pRTCBarType*<br/>
【인】 NULL이 아닌 경우 메서드는 지정된 형식의 창만 검색합니다.

*b체크가시성*<br/>
【인】 TRUE는 보이는 창만 확인합니다. 그렇지 않으면 false입니다.

*dw정렬*<br/>
【아웃】 지정된 지점에서 창이 발견되면 이 매개변수에는 지정된 점에 가장 가까운 창의 측면이 포함됩니다. 자세한 내용은 주의 섹션을 참조하세요.

*pBarToIgnore*<br/>
【인】 NULL이 아닌 경우 메서드는 이 매개 변수에 의해 지정된 창을 무시합니다.

### <a name="return-value"></a>Return Value

지정된 점을 포함하는 [CBasePane-파생](../../mfc/reference/cbasepane-class.md)개체 또는 창이 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

함수가 반환되고 창이 발견되면 *dwAlignment에는* 지정된 점의 정렬이 포함됩니다. 예를 들어 점이 창의 맨 위에 가장 가깝으면 *dwAlignment이* CBRS_ALIGN_TOP 설정됩니다.

## <a name="cdockingmanagerprocesspanecontextmenucommand"></a><a name="processpanecontextmenucommand"></a>CDockingManager::P로케스파네컨텍스트메뉴명령

프레임워크에서 지정된 명령에 대한 확인란을 선택하거나 지우고 표시된 창의 레이아웃을 다시 계산하도록 합니다.

```
BOOL ProcessPaneContextMenuCommand(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 메뉴에서 컨트롤 막대의 ID입니다.

*nCode*<br/>
【인】 명령 알림 코드입니다.

*pExtra*<br/>
【인】 `CCmdUI` *nCode가* CN_UPDATE_COMMAND_UI 경우 포인터에 캐스팅되는 void에 대한 포인터입니다.

*pHandlerInfo*<br/>
【인】 정보 구조에 대한 포인터입니다. 이 매개 변수는 사용되지 않습니다.

### <a name="return-value"></a>Return Value

true *pEXtra가* NULL이 아니고 *nCode가* CN_UPDATE_COMMAND_UI 같거나 지정된 *nID가*있는 컨트롤 막대가 있는 경우 TRUE .

## <a name="cdockingmanagerrecalclayout"></a><a name="recalclayout"></a>CDockingManager::RecalcLayout

컨트롤 목록에 있는 컨트롤의 내부 레이아웃을 다시 계산합니다.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>매개 변수

*bNotify*<br/>
【인】 이 매개 변수는 사용되지 않습니다.

## <a name="cdockingmanagerreleaseemptypanecontainers"></a><a name="releaseemptypanecontainers"></a>CDockingManager::릴리스빈파네컨테이너

빈 창 컨테이너를 해제합니다.

```cpp
void ReleaseEmptyPaneContainers();
```

## <a name="cdockingmanagerremovehiddenmditabbedbar"></a><a name="removehiddenmditabbedbar"></a>도킹 매니저::제거숨겨진MDITabbedBar

지정된 숨겨진 막대 창을 제거합니다.

```cpp
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 제거할 막대 창에 대한 포인터입니다.

## <a name="cdockingmanagerremoveminiframe"></a><a name="removeminiframe"></a>도킹 매니저::제거미니프레임

미니 프레임 목록에서 지정된 프레임을 제거합니다.

```
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 제거할 프레임에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 지정된 프레임이 제거된 경우; 그렇지 않으면 거짓.

## <a name="cdockingmanagerremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>CDockingManager::제거페네From독매니저

창을 등록 취소하고 도킹 관리자의 목록에서 창이 제거됩니다.

```cpp
void RemovePaneFromDockManager(
    CBasePane* pWnd,
    BOOL bDestroy,
    BOOL bAdjustLayout,
    BOOL bAutoHide = FALSE,
    CBasePane* pBarReplacement = NULL);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 제거할 창에 대한 포인터입니다.

*bDestroy*<br/>
【인】 TRUE이면 제거된 창이 소멸됩니다.

*bAdjust레이아웃*<br/>
【인】 TRUE인 경우 도킹 레이아웃을 즉시 조정합니다.

*b자동 숨기기*<br/>
【인】 TRUE이면 창이 자동 숨기기 막대 목록에서 제거됩니다. FALSE이면 일반 창 목록에서 창이 제거됩니다.

*pBar교체*<br/>
【인】 제거된 창을 대체하는 창에 대한 포인터입니다.

## <a name="cdockingmanagerreplacepane"></a><a name="replacepane"></a>CDockingManager::대체창

한 창을 다른 창으로 대체합니다.

```
BOOL ReplacePane(
    CDockablePane* pOriginalBar,
    CDockablePane* pNewBar);
```

### <a name="parameters"></a>매개 변수

*p오리지널 바*<br/>
【인】 원래 창에 대한 포인터입니다.

*p뉴바*<br/>
【인】 원래 창을 대체하는 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

창이 성공적으로 대체된 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cdockingmanagerresortminiframesforzorder"></a><a name="resortminiframesforzorder"></a>도킹매니저::리조트미니프레임포어더

미니 프레임 목록에 프레임을 리조트.

```cpp
void ResortMiniFramesForZOrder();
```

## <a name="cdockingmanagersavestate"></a><a name="savestate"></a>CDockingManager::저장 상태

도킹 관리자의 상태를 레지스트리에 저장합니다.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 레지스트리 키에 대한 경로입니다.

*uiID*<br/>
【인】 도킹 관리자 ID입니다.

### <a name="return-value"></a>Return Value

TRUE 상태가 성공적으로 저장된 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

도킹 관리자의 상태를 레지스트리에 저장하려면 제어 막대의 상태, 자동 숨기기 막대의 상태 및 도킹 관리자에 있는 미니 프레임의 상태를 저장해야 합니다.

## <a name="cdockingmanagersendmessagetominiframes"></a><a name="sendmessagetominiframes"></a>도킹 매니저::센드 메시지토미니프레임

지정된 메시지를 모든 미니 프레임에 보냅니다.

```
BOOL SendMessageToMiniFrames(
    UINT uMessage,
    WPARAM wParam = 0,
    LPARAM lParam = 0);
```

### <a name="parameters"></a>매개 변수

*u 메시지*<br/>
【인】 보낼 메시지입니다.

*wParam*<br/>
【인】 추가 메시지 종속 정보입니다.

*lParam*<br/>
【인】 추가 메시지 종속 정보입니다.

### <a name="return-value"></a>Return Value

항상 사실.

## <a name="cdockingmanagerserialize"></a><a name="serialize"></a>CDock관리자::직렬화

도킹 관리자를 아카이브에 씁니다.

```cpp
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
【인】 아카이브 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

도킹 관리자를 아카이브에 작성하려면 도킹 컨트롤 막대와 슬라이더의 수를 결정하고 컨트롤 막대, 미니 프레임, 자동 숨기기 막대 및 MDI 탭 막대를 아카이브에 작성해야 합니다.

## <a name="cdockingmanagersetautohidezorder"></a><a name="setautohidezorder"></a>도킹 매니저::SetAutohideZOrder

컨트롤 막대와 지정된 창의 크기, 너비 및 높이를 설정합니다.

```cpp
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```

### <a name="parameters"></a>매개 변수

*파도킹바*<br/>
【인】 도킹 가능한 창에 대한 포인터입니다.

## <a name="cdockingmanagersetdockingmode"></a><a name="setdockingmode"></a>CDockingManager::SetDocking모드

도킹 모드를 설정합니다.

```
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```

### <a name="parameters"></a>매개 변수

*독 모드*<br/>
새 도킹 모드를 지정합니다. 자세한 내용은 주의 섹션을 참조하세요.

*테마*<br/>
스마트 도킹 마커에 사용할 테마를 지정합니다. AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008 다음 열거된 값 중 하나가 될 수 있습니다.

### <a name="remarks"></a>설명

이 정적 메서드를 호출하여 도킹 모드를 설정합니다.

*dockMode는* 다음 값 중 하나가 될 수 있습니다.

- DT_STANDARD Visual Studio .NET 2003에서 구현된 표준 도킹 모드입니다. 창은 드래그 컨텍스트 없이 드래그됩니다.

- DT_IMMEDIATE - Microsoft Visio에서 구현된 즉시 도킹 모드입니다. 창은 드래그 컨텍스트로 드래그되지만 마커는 표시되지 않습니다.

- DT_SMART - Visual Studio 2005에서 구현된 스마트 도킹 모드입니다. 창을 드래그 컨텍스트로 드래그하고 창을 도킹할 수 있는 위치를 표시하는 스마트 마커가 표시됩니다.

## <a name="cdockingmanagersetdockstate"></a><a name="setdockstate"></a>CDockingManager::SetDockState

컨트롤 막대, 미니 프레임 및 자동 숨기기 막대의 도킹 상태를 설정합니다.

```
virtual void SetDockState();
```

## <a name="cdockingmanagersetprintpreviewmode"></a><a name="setprintpreviewmode"></a>CDockingManager:::세트프린트 프리뷰모드

인쇄 미리 보기에 표시되는 막대의 인쇄 미리 보기 모드를 설정합니다.

```cpp
void SetPrintPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>매개 변수

*bPreview*<br/>
【인】 인쇄 미리 보기 모드가 설정된 경우 TRUE; 그렇지 않으면 거짓.

*pState*<br/>
【인】 미리 보기 상태에 대한 포인터입니다. 이 매개 변수는 사용되지 않습니다.

## <a name="cdockingmanagersetsmartdockingparams"></a><a name="setsmartdockingparams"></a>CDockingManager:::SetSmartDockingParams

스마트 도킹의 동작을 정의하는 매개 변수를 설정합니다.

```
static void SetSmartDockingParams(CSmartDockingInfo& params);
```

### <a name="parameters"></a>매개 변수

*params*<br/>
【인, 아웃】 스마트 도킹에 대한 매개 변수를 정의합니다.

### <a name="remarks"></a>설명

스마트 도킹 마커의 모양, 색상 또는 모양을 사용자 지정하려면 이 메서드를 호출합니다.

스마트 도킹 마커에 대한 기본 모양을 사용하려면 [CSmartDockingInfo 클래스의](../../mfc/reference/csmartdockinginfo-class.md) 초기화되지 않은 인스턴스를 *매개 변수로*전달합니다.

## <a name="cdockingmanagershowdelayshowminiframes"></a><a name="showdelayshowminiframes"></a>CDockingManager::쇼지연쇼미니프레임

미니 프레임의 창을 표시하거나 숨깁니다.

```cpp
void ShowDelayShowMiniFrames(BOOL bshow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
【인】 도시된 프레임의 창을 활성화시키기 위해 TRUE; FALSE를 사용하여 프레임의 창을 숨깁니다.

## <a name="cdockingmanagershowpanes"></a><a name="showpanes"></a>도킹 매니저::쇼파네스

컨트롤 및 자동 숨기기 막대의 창을 표시하거나 숨깁니다.

```
virtual BOOL ShowPanes(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
【인】 창을 표시하는 TRUE; 창을 숨기기 위해 FALSE입니다.

### <a name="return-value"></a>Return Value

항상 FALSE입니다.

## <a name="cdockingmanagerstartsdocking"></a><a name="startsdocking"></a>CDockingManager::시작스도킹

스마트 도킹 관리자의 정렬에 따라 지정된 창의 스마트 도킹을 시작합니다.

```cpp
void StartSDocking(CWnd* pDockingWnd);
```

### <a name="parameters"></a>매개 변수

*pDockingWnd*<br/>
【인】 도킹할 창에 대한 포인터입니다.

## <a name="cdockingmanagerstopsdocking"></a><a name="stopsdocking"></a>CDockingManager::중지스독킹

스마트 도킹을 중지합니다.

```cpp
void StopSDocking();
```

## <a name="cdockingmanagergetsmartdockingtheme"></a><a name="getsmartdockingtheme"></a>CDockingManager::겟스마트도킹테마

스마트 도킹 마커를 표시하는 데 사용되는 테마를 반환하는 정적 메서드입니다.

```
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```

### <a name="return-value"></a>Return Value

AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008 다음 내큐어된 값 중 하나를 반환합니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[CFrameWndEx 클래스](../../mfc/reference/cframewndex-class.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)<br/>
[CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md)
