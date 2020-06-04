---
title: CBasePane 클래스
ms.date: 11/06/2018
f1_keywords:
- CBasePane
- AFXBASEPANE/CBasePane
- AFXBASEPANE/CBasePane::AccNotifyObjectFocusEvent
- AFXBASEPANE/CBasePane::AddPane
- AFXBASEPANE/CBasePane::AdjustDockingLayout
- AFXBASEPANE/CBasePane::AdjustLayout
- AFXBASEPANE/CBasePane::CalcFixedLayout
- AFXBASEPANE/CBasePane::CanAcceptPane
- AFXBASEPANE/CBasePane::CanAutoHide
- AFXBASEPANE/CBasePane::CanBeAttached
- AFXBASEPANE/CBasePane::CanBeClosed
- AFXBASEPANE/CBasePane::CanBeDocked
- AFXBASEPANE/CBasePane::CanBeResized
- AFXBASEPANE/CBasePane::CanBeTabbedDocument
- AFXBASEPANE/CBasePane::CanFloat
- AFXBASEPANE/CBasePane::CanFocus
- AFXBASEPANE/CBasePane::CopyState
- AFXBASEPANE/CBasePane::CreateDefaultMiniframe
- AFXBASEPANE/CBasePane::CreateEx
- AFXBASEPANE/CBasePane::DockPane
- AFXBASEPANE/CBasePane::DockPaneUsingRTTI
- AFXBASEPANE/CBasePane::DockToFrameWindow
- AFXBASEPANE/CBasePane::DoesAllowDynInsertBefore
- AFXBASEPANE/CBasePane::EnableDocking
- AFXBASEPANE/CBasePane::EnableGripper
- AFXBASEPANE/CBasePane::FloatPane
- AFXBASEPANE/CBasePane::get_accHelpTopic
- AFXBASEPANE/CBasePane::get_accSelection
- AFXBASEPANE/CBasePane::GetCaptionHeight
- AFXBASEPANE/CBasePane::GetControlBarStyle
- AFXBASEPANE/CBasePane::GetCurrentAlignment
- AFXBASEPANE/CBasePane::GetDockingMode
- AFXBASEPANE/CBasePane::GetDockSiteFrameWnd
- AFXBASEPANE/CBasePane::GetEnabledAlignment
- AFXBASEPANE/CBasePane::GetMFCStyle
- AFXBASEPANE/CBasePane::GetPaneIcon
- AFXBASEPANE/CBasePane::GetPaneRow
- AFXBASEPANE/CBasePane::GetPaneStyle
- AFXBASEPANE/CBasePane::GetParentDockSite
- AFXBASEPANE/CBasePane::GetParentMiniFrame
- AFXBASEPANE/CBasePane::GetParentTabbedPane
- AFXBASEPANE/CBasePane::GetParentTabWnd
- AFXBASEPANE/CBasePane::GetRecentVisibleState
- AFXBASEPANE/CBasePane::HideInPrintPreviewMode
- AFXBASEPANE/CBasePane::InsertPane
- AFXBASEPANE/CBasePane::IsAccessibilityCompatible
- AFXBASEPANE/CBasePane::IsAutoHideMode
- AFXBASEPANE/CBasePane::IsDialogControl
- AFXBASEPANE/CBasePane::IsDocked
- AFXBASEPANE/CBasePane::IsFloating
- AFXBASEPANE/CBasePane::IsHorizontal
- AFXBASEPANE/CBasePane::IsInFloatingMultiPaneFrameWnd
- AFXBASEPANE/CBasePane::IsMDITabbed
- AFXBASEPANE/CBasePane::IsPaneVisible
- AFXBASEPANE/CBasePane::IsPointNearDockSite
- AFXBASEPANE/CBasePane::IsResizable
- AFXBASEPANE/CBasePane::IsRestoredFromRegistry
- AFXBASEPANE/CBasePane::IsTabbed
- AFXBASEPANE/CBasePane::IsVisible
- AFXBASEPANE/CBasePane::LoadState
- AFXBASEPANE/CBasePane::MoveWindow
- AFXBASEPANE/CBasePane::OnAfterChangeParent
- AFXBASEPANE/CBasePane::OnBeforeChangeParent
- AFXBASEPANE/CBasePane::OnDrawCaption
- AFXBASEPANE/CBasePane::OnMovePaneDivider
- AFXBASEPANE/CBasePane::OnPaneContextMenu
- AFXBASEPANE/CBasePane::OnRemoveFromMiniFrame
- AFXBASEPANE/CBasePane::OnSetAccData
- AFXBASEPANE/CBasePane::PaneFromPoint
- AFXBASEPANE/CBasePane::RecalcLayout
- AFXBASEPANE/CBasePane::RemovePaneFromDockManager
- AFXBASEPANE/CBasePane::SaveState
- AFXBASEPANE/CBasePane::SelectDefaultFont
- AFXBASEPANE/CBasePane::SetControlBarStyle
- AFXBASEPANE/CBasePane::SetDockingMode
- AFXBASEPANE/CBasePane::SetPaneAlignment
- AFXBASEPANE/CBasePane::SetPaneStyle
- AFXBASEPANE/CBasePane::SetWindowPos
- AFXBASEPANE/CBasePane::ShowPane
- AFXBASEPANE/CBasePane::StretchPane
- AFXBASEPANE/CBasePane::UndockPane
- AFXBASEPANE/CBasePane::DoPaint
helpviewer_keywords:
- CBasePane [MFC], AccNotifyObjectFocusEvent
- CBasePane [MFC], AddPane
- CBasePane [MFC], AdjustDockingLayout
- CBasePane [MFC], AdjustLayout
- CBasePane [MFC], CalcFixedLayout
- CBasePane [MFC], CanAcceptPane
- CBasePane [MFC], CanAutoHide
- CBasePane [MFC], CanBeAttached
- CBasePane [MFC], CanBeClosed
- CBasePane [MFC], CanBeDocked
- CBasePane [MFC], CanBeResized
- CBasePane [MFC], CanBeTabbedDocument
- CBasePane [MFC], CanFloat
- CBasePane [MFC], CanFocus
- CBasePane [MFC], CopyState
- CBasePane [MFC], CreateDefaultMiniframe
- CBasePane [MFC], CreateEx
- CBasePane [MFC], DockPane
- CBasePane [MFC], DockPaneUsingRTTI
- CBasePane [MFC], DockToFrameWindow
- CBasePane [MFC], DoesAllowDynInsertBefore
- CBasePane [MFC], EnableDocking
- CBasePane [MFC], EnableGripper
- CBasePane [MFC], FloatPane
- CBasePane [MFC], get_accHelpTopic
- CBasePane [MFC], get_accSelection
- CBasePane [MFC], GetCaptionHeight
- CBasePane [MFC], GetControlBarStyle
- CBasePane [MFC], GetCurrentAlignment
- CBasePane [MFC], GetDockingMode
- CBasePane [MFC], GetDockSiteFrameWnd
- CBasePane [MFC], GetEnabledAlignment
- CBasePane [MFC], GetMFCStyle
- CBasePane [MFC], GetPaneIcon
- CBasePane [MFC], GetPaneRow
- CBasePane [MFC], GetPaneStyle
- CBasePane [MFC], GetParentDockSite
- CBasePane [MFC], GetParentMiniFrame
- CBasePane [MFC], GetParentTabbedPane
- CBasePane [MFC], GetParentTabWnd
- CBasePane [MFC], GetRecentVisibleState
- CBasePane [MFC], HideInPrintPreviewMode
- CBasePane [MFC], InsertPane
- CBasePane [MFC], IsAccessibilityCompatible
- CBasePane [MFC], IsAutoHideMode
- CBasePane [MFC], IsDialogControl
- CBasePane [MFC], IsDocked
- CBasePane [MFC], IsFloating
- CBasePane [MFC], IsHorizontal
- CBasePane [MFC], IsInFloatingMultiPaneFrameWnd
- CBasePane [MFC], IsMDITabbed
- CBasePane [MFC], IsPaneVisible
- CBasePane [MFC], IsPointNearDockSite
- CBasePane [MFC], IsResizable
- CBasePane [MFC], IsRestoredFromRegistry
- CBasePane [MFC], IsTabbed
- CBasePane [MFC], IsVisible
- CBasePane [MFC], LoadState
- CBasePane [MFC], MoveWindow
- CBasePane [MFC], OnAfterChangeParent
- CBasePane [MFC], OnBeforeChangeParent
- CBasePane [MFC], OnDrawCaption
- CBasePane [MFC], OnMovePaneDivider
- CBasePane [MFC], OnPaneContextMenu
- CBasePane [MFC], OnRemoveFromMiniFrame
- CBasePane [MFC], OnSetAccData
- CBasePane [MFC], PaneFromPoint
- CBasePane [MFC], RecalcLayout
- CBasePane [MFC], RemovePaneFromDockManager
- CBasePane [MFC], SaveState
- CBasePane [MFC], SelectDefaultFont
- CBasePane [MFC], SetControlBarStyle
- CBasePane [MFC], SetDockingMode
- CBasePane [MFC], SetPaneAlignment
- CBasePane [MFC], SetPaneStyle
- CBasePane [MFC], SetWindowPos
- CBasePane [MFC], ShowPane
- CBasePane [MFC], StretchPane
- CBasePane [MFC], UndockPane
- CBasePane [MFC], DoPaint
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
ms.openlocfilehash: 941f32dfadffd97210586edd7c2aa63c3c1708cd
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752983"
---
# <a name="cbasepane-class"></a>CBasePane 클래스

MFC의 모든 창에 대한 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CBasePane : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CBasePane::CBasePane`|기본 생성자입니다.|
|`CBasePane::~CBasePane`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CBasePane::accHitTest`|화면의 지정된 지점에서 자식 요소나 자식 개체를 검색하기 위해 프레임워크에서 호출됩니다. [(CWnd 재정의::accHitTest](../../mfc/reference/cwnd-class.md#acchittest).)|
|`CBasePane::accLocation`|지정된 개체의 현재 화면 위치를 검색하기 위해 프레임워크에서 호출합니다. [(CWnd::acclocation](../../mfc/reference/cwnd-class.md#acclocation)를 재정의합니다.)|
|[CBasePane::AccNotify개체포커스이벤트](#accnotifyobjectfocusevent)|`CBasePane`이 메서드를 사용 하지 않습니다.|
|`CBasePane::accSelect`|선택 영역을 수정하거나 지정된 개체의 키보드 포커스를 이동하기 위해 프레임워크에서 호출됩니다. [(CWnd 재정의::accSelect.)](../../mfc/reference/cwnd-class.md#accselect)|
|[CBasePane::애드파인](#addpane)|도킹 관리자에 창을 추가합니다.|
|[CBasePane::조정도킹레이아웃](#adjustdockinglayout)|도킹 관리자로 전화를 리디렉션하여 도킹 레이아웃을 조정합니다.|
|[CBasePane::조정레이아웃](#adjustlayout)|창이 내부 레이아웃을 조정해야 할 때 프레임워크에서 호출됩니다.|
|[CBasePane::석회화레이아웃](#calcfixedlayout)|컨트롤 막대의 수평 크기를 계산합니다.|
|[CBasePane::캔 수락파인](#canacceptpane)|다른 창을 창에 도킹할 수 있는지 여부를 결정합니다.|
|[CBasePane::CanAutoHide](#canautohide)|창이 자동 숨기기 모드를 지원하는지 여부를 결정합니다.|
|[CBasePane:::첨부할 수 있습니다.](#canbeattached)|창을 다른 창에 도킹할 수 있는지 여부를 결정합니다.|
|[CBasePane::수 닫힘](#canbeclosed)|창을 닫을 수 있는지 여부를 결정합니다.|
|[CBasePane::캔독](#canbedocked)|창을 다른 창에 도킹할 수 있는지 여부를 결정합니다.|
|[CBasePane::수있습니다](#canberesized)|창의 크기를 조정할 수 있는지 여부를 결정합니다.|
|[CBasePane::수탭문서](#canbetabbeddocument)|창을 MDI 탭 문서로 변환할 수 있는지 여부를 지정합니다.|
|[CBasePane::캔플로트](#canfloat)|창이 부동할 수 있는지 여부를 결정합니다.|
|[CBasePane::캔포커스](#canfocus)|창이 포커스를 수신할 수 있는지 여부를 지정합니다.|
|[CBasePane::복사 상태](#copystate)|지정된 창의 상태를 복사합니다.|
|[CBasePane::만들기기본미니프레임](#createdefaultminiframe)|창이 부동할 수 있는 경우 미니 프레임 창을 만듭니다.|
|[CBasePane::만들기](#createex)|창 컨트롤을 만듭니다.|
|[CBasePane::D오크파인](#dockpane)|창을 다른 창이나 프레임 창에 도킹합니다.|
|[CBasePane::DockPaneUsingRTTI](#dockpaneusingrtti)|런타임 형식 정보를 사용하여 창을 도킹합니다.|
|[CBasePane::DockToFrame창](#docktoframewindow)|도킹 가능한 창을 프레임에 도킹합니다.|
|[CBasePane::DoesAllowDyn인더인](#doesallowdyninsertbefore)|이 창과 상위 프레임 사이에 다른 창을 동적으로 삽입할 수 있는지 여부를 결정합니다.|
|[CBasePane::사용 도킹](#enabledocking)|창을 주 프레임에 도킹할 수 있습니다.|
|[CBasePane::인에이블그리퍼](#enablegripper)|그리퍼를 활성화하거나 비활성화합니다. 그리퍼가 활성화된 경우 사용자는 그리퍼를 드래그하여 창의 위치를 변경할 수 있습니다.|
|`CBasePane::FillWindowRect`|내부적으로 사용됩니다.|
|[CBasePane::플로트파인](#floatpane)|창을 부동합니다.|
|`CBasePane::get_accChild`|지정된 자식의 `IDispatch` 인터페이스 주소를 검색하기 위해 프레임워크에서 호출됩니다. [(재정의 CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild).)|
|`CBasePane::get_accChildCount`|이 개체에 속하는 자식 수를 검색하기 위해 프레임워크에서 호출합니다. [(cwnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount)재정의 .)|
|`CBasePane::get_accDefaultAction`|개체에 대 한 기본 작업을 설명 하는 문자열을 검색 하려면 프레임 워크에서 호출 합니다. [(CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction)재정의 .)|
|`CBasePane::get_accDescription`|지정한 개체의 모양을 설명하는 문자열을 검색하기 위해 프레임워크에서 호출됩니다. [(CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription)재정의 .)|
|`CBasePane::get_accFocus`|키보드 포커스가 있는 개체를 검색하기 위해 프레임워크에서 호출됩니다. [(재정의 CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus).)|
|`CBasePane::get_accHelp`|개체에 대 한 도움말 속성 문자열을 검색 하는 프레임 워크에 의해 호출 됩니다. [(CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp)재정의 .)|
|[CBasePane::get_accHelpTopic](#get_acchelptopic)|지정된 개체와 연결된 WinHelp 파일의 전체 경로 및 해당 파일에 있는 해당 토픽의 식별자를 검색하기 위해 프레임워크에서 호출합니다. [(CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic)재정의 .)|
|`CBasePane::get_accKeyboardShortcut`|개체에 대 한 지정 된 바로 가기 키를 검색 하는 프레임 워크에 의해 호출 됩니다. [(재정의 CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut).)|
|`CBasePane::get_accName`|지정된 개체의 이름을 검색하기 위해 프레임워크에서 호출됩니다. [(cwnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname)재정의 .)|
|`CBasePane::get_accParent`|개체의 부모에 대 `IDispatch` 한 인터페이스를 검색 하는 프레임 워크에 의해 호출 됩니다. [(cwnd::get_accParent.)](../../mfc/reference/cwnd-class.md#get_accparent)|
|`CBasePane::get_accRole`|지정된 개체의 역할을 설명하는 정보를 검색하기 위해 프레임워크에서 호출됩니다. [(CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole)재정의 .)|
|[CBasePane::get_accSelection](#get_accselection)|이 개체의 선택된 자식 개체를 검색하기 위해 프레임워크에서 호출됩니다. [(CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection)재정의 .)|
|`CBasePane::get_accState`|지정된 개체의 현재 상태를 검색하기 위해 프레임워크에서 호출됩니다. [(CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate)재정의 .)|
|`CBasePane::get_accValue`|지정된 개체의 값을 검색하기 위해 프레임워크에서 호출됩니다. [(cwnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue)재정의 .)|
|[CBasePane::GetCaptionHeight](#getcaptionheight)|캡션 높이를 반환합니다.|
|[CBasePane::GetControlBar스타일](#getcontrolbarstyle)|컨트롤 막대 스타일을 반환합니다.|
|[CBasePane::GetCurrent정렬](#getcurrentalignment)|현재 창 선형을 반환합니다.|
|[CBasePane::겟도킹 모드](#getdockingmode)|창에 대한 현재 도킹 모드를 반환합니다.|
|[CBasePane::GetDockSiteFrameD](#getdocksiteframewnd)|창에 대한 도크 사이트인 창에 대한 포인터를 반환합니다.|
|[CBasePane::GetEnabled정렬](#getenabledalignment)|창에 적용되는 CBRS_ALIGN_ 스타일을 반환합니다.|
|[CBasePane::GetMFC스타일](#getmfcstyle)|MFC에 특정한 창 스타일을 반환합니다.|
|[CBasePane::GetPaneIcon](#getpaneicon)|창 아이콘에 핸들을 반환합니다.|
|`CBasePane::GetPaneRect`|내부적으로 사용됩니다.|
|[CBasePane:::겟파네로우](#getpanerow)|창이 도킹된 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)개체에 대한 포인터를 반환합니다.|
|[CBasePane::겟파인 스타일](#getpanestyle)|창 스타일을 반환합니다.|
|[CBasePane::GetParentDockSite](#getparentdocksite)|상위 도크 사이트에 대한 포인터를 반환합니다.|
|[CBasePane::GetParentMiniFrame](#getparentminiframe)|상위 미니 프레임 창에 대한 포인터를 반환합니다.|
|[CBasePane:::GetParentTabbedPane](#getparenttabbedpane)|상위 탭창에 대한 포인터를 반환합니다.|
|[CBasePane::GetParentTabwnd](#getparenttabwnd)|탭 안에 있는 부모 창에 대한 포인터를 반환합니다.|
|[CBasePane::Get최근가볼 수 있는 상태](#getrecentvisiblestate)|프레임워크는 보관에서 창이 복원될 때 이 메서드를 호출합니다.|
|[CBasePane::숨바꼭한인쇄 미리보기 모드](#hideinprintpreviewmode)|창이 인쇄 미리 보기에 숨겨져 있는지 여부를 지정합니다.|
|[CBasePane::삽입창](#insertpane)|지정된 창을 도킹 관리자에 등록합니다.|
|[CBasePane::접근성 호환](#isaccessibilitycompatible)|창이 활성 접근성을 지원하는지 여부를 지정합니다.|
|[CBasePane::IsAutoHideMode](#isautohidemode)|창이 자동 숨기기 모드에 있는지 여부를 결정합니다.|
|[CBasePane::IsDialog제어](#isdialogcontrol)|창이 대화 상자 컨트롤인지 여부를 지정합니다.|
|[CBasePane::IsDocked](#isdocked)|창이 도킹되었는지 여부를 결정합니다.|
|[CBasePane::떠 있는](#isfloating)|창이 부동 인지 여부를 확인 합니다.|
|[CBasePane::수평](#ishorizontal)|창이 수평으로 도킹되는지 여부를 결정합니다.|
|[CBasePane::이인 플로팅멀티파인프레임](#isinfloatingmultipaneframewnd)|창이 다중 창 프레임 창에 있는지 여부를 지정합니다.|
|[CBasePane::IsMDITabbed](#ismditabbed)|창이 탭된 문서로 MDI 자식 창에 추가되었는지 여부를 결정합니다.|
|[CBasePane::IsPaneVisible](#ispanevisible)|창에 대해 WS_VISIBLE 플래그가 설정되어 있는지 여부를 지정합니다.|
|[CBasePane::이포인트니어독사이트](#ispointneardocksite)|지정된 점이 도크 사이트 근처에 있는지 여부를 결정합니다.|
|[CBasePane::이재성](#isresizable)|창의 크기를 조정할 수 있는지 여부를 결정합니다.|
|[CBasePane::복원에서레지스트리](#isrestoredfromregistry)|창이 레지스트리에서 복원되는지 여부를 결정합니다.|
|[CBasePane::IsTabbed](#istabbed)|탭된 창의 탭 컨트롤에 창이 삽입되었는지 여부를 결정합니다.|
|`CBasePane::IsTooltipTopmost`|내부적으로 사용됩니다.|
|[CBasePane::가 보입니다.](#isvisible)|창이 표시되는지 여부를 결정합니다.|
|[CBasePane::로드스테이트](#loadstate)|레지스트리에서 창 상태를 로드합니다.|
|[CBasePane::이동 창](#movewindow)|창을 이동합니다.|
|[CBasePane::온애프터체인지부모](#onafterchangeparent)|창의 부모가 변경되었을 때 프레임워크에서 호출됩니다.|
|[CBasePane::에 전에변경부모](#onbeforechangeparent)|창이 부모 창을 변경하기 직전에 프레임워크에서 호출됩니다.|
|[CBasePane::온드로우 캡션](#ondrawcaption)|프레임워크는 캡션이 그려질 때 이 메서드를 호출합니다.|
|[CBasePane::온무파네 분배기](#onmovepanedivider)|이 메서드는 현재 사용 되지 않습니다.|
|[CBasePane::온파네컨텍스트 메뉴](#onpanecontextmenu)|창 목록이 있는 메뉴를 빌드할 때 프레임워크에서 호출합니다.|
|[CBasePane::에제거해제미니프레임](#onremovefromminiframe)|상위 미니 프레임 창에서 창이 제거될 때 프레임워크에서 호출됩니다.|
|[CBasePane::온셋데이터](#onsetaccdata)|`CBasePane`이 메서드를 사용 하지 않습니다.|
|`CBasePane::OnUpdateCmdUI`|내부적으로 사용됩니다.|
|[CBasePane::P인FromPoint](#panefrompoint)|지정된 점을 포함하는 창을 반환합니다.|
|`CBasePane::PreTranslateMessage`|창 메시지가 [TranslateMessage](../../mfc/reference/cwinapp-class.md) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) Windows 함수로 디스패치되기 전에 [CWinApp](/windows/win32/api/winuser/nf-winuser-dispatchmessage) 클래스가 이 메시지를 해석하는 데 사용됩니다. ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 재정의합니다.)|
|[CBasePane::리콜레이아웃](#recalclayout)|`CBasePane`이 메서드를 사용 하지 않습니다.|
|[CBasePane::제거파인에서독매니저](#removepanefromdockmanager)|창을 등록 취소하고 도킹 관리자의 목록에서 창이 제거됩니다.|
|[CBasePane::저장 상태](#savestate)|레지스트리에 창의 상태를 저장합니다.|
|[CBasePane::선택기본글꼴](#selectdefaultfont)|지정된 장치 컨텍스트에 대한 기본 글꼴을 선택합니다.|
|`CBasePane::Serialize`|이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다. ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)를 재정의합니다.)|
|[CBasePane::세트컨트롤바스타일](#setcontrolbarstyle)|컨트롤 막대 스타일을 설정합니다.|
|[CBasePane::SetDocking 모드](#setdockingmode)|창에 대한 도킹 모드를 설정합니다.|
|`CBasePane::SetMDITabbed`|내부적으로 사용됩니다.|
|[CBasePane::세파네정렬](#setpanealignment)|창의 맞춤을 설정합니다.|
|`CBasePane::SetPaneRect`|내부적으로 사용됩니다.|
|[CBasePane::SetPaneStyle](#setpanestyle)|창의 스타일을 설정합니다.|
|`CBasePane::SetRestoredFromRegistry`|내부적으로 사용됩니다.|
|[CBasePane::SetWindowPos](#setwindowpos)|창의 크기, 위치 및 Z 순서를 변경합니다.|
|[CBasePane::쇼파인](#showpane)|창을 표시하거나 숨깁니다.|
|[CBasePane::스트레치파인](#stretchpane)|창을 가로 또는 세로로 확장합니다.|
|[CBasePane::도킹 팬 해제](#undockpane)|도크 사이트, 기본 슬라이더 또는 현재 도킹된 미니 프레임 창에서 창을 제거합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CBasePane::D페인트](#dopaint)|창의 배경을 채웁니다.|

## <a name="remarks"></a>설명

MFC에서 사용할 수 있는 확장 된 도킹 기능을 지원하는 창 클래스를 `CBasePane` 만들려면 [CPane 클래스에서 파생하거나 CPane Class에서](../../mfc/reference/cpane-class.md)파생시켜야 합니다.

## <a name="customization-tips"></a>사용자 지정 팁

다음 사용자 지정 팁은 `CBasePane Class` 해당 클래스와 상속되는 모든 클래스와 관련이 있습니다.

- 창을 작성할 때 다음과 같은 몇 가지 새 스타일을 적용할 수 있습니다.

  - AFX_CBRS_FLOAT 창을 플로트합니다.

  - AFX_CBRS_AUTOHIDE 자동 숨기기 모드를 활성화합니다.

  - AFX_CBRS_CLOSE 창을 닫을 수 있습니다(숨김).

  이러한 플래그는 비트-OR 작업과 결합할 수 있습니다.

`CBasePane`[CBasePane::CanBeClosed](#canbeclosed), [CBasePane::CanAutoHide,](#canautohide) [CBasePane::CanFloat](#canfloat). 파생 클래스에서 재정의하여 동작을 사용자 지정할 수 있습니다.

- [CBasePane::CanAcceptPane](#canacceptpane)을 재정의하여 도킹 동작을 사용자 지정할 수 있습니다. 창이 이 메서드에서 FALSE를 반환하여 다른 창이 도킹되지 않도록 합니다.

- 부동 할 수 없고 다른 창이 도킹되지 못하게하는 정적 창을 만들려면 (OutlookDemo 예제의 Outlook 막대와 유사), 비 부동으로 만들고 [CBasePane ::DoesAllowDynInsertBefore](#doesallowdyninsertbefore) FALSE를 반환합니다. 창이 AFX_CBRS_FLOAT 스타일 없이 만들어지면 기본 구현은 FALSE를 반환합니다.

- -1이외의 아이디를 사용하여 모든 창을 만듭니다.

- 창 가시성을 확인하려면 [CBasePane::IsVisible](#isvisible)를 사용합니다. 탭 및 자동 숨기기 모드에서 가시성 상태를 올바르게 처리합니다.

- 부동 되지 않는 조정 가능한 창을 만들려면 AFX_CBRS_FLOAT 스타일 없이 만들고 [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)를 호출합니다.

- 도킹 레이아웃에서 창을 제외하거나 도킹 바에서 도구 모음을 제거하려면 [CBasePane::UndockPane을](#undockpane)호출합니다. 자동 숨기기 모드에서 또는 탭된 창 탭에 있는 창에 대해 이 메서드를 호출하지 마십시오.

- 자동 숨기기 모드에 있는 창을 부동 또는 도킹 해제하려면 [CBasePane::FloatPane::UndockPane를](#floatpane) 호출하기 전에 FALSE를 사용하여 [CDockablePane::SetAutoHideMode를](../../mfc/reference/cdockablepane-class.md#setautohidemode) 호출해야 합니다. [CBasePane::UndockPane](#undockpane)

## <a name="example"></a>예제

다음 예제에서는 `CBasePane` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 `CFrameWndEx` 클래스에서 창을 검색하는 방법과 도킹 모드, 창 정렬 및 창 스타일을 설정하는 방법을 보여 줍니다. 코드는 워드 [패드 샘플에서](../../overview/visual-cpp-samples.md)입니다.

[!code-cpp[NVC_MFC_WordPad#2](../../mfc/reference/codesnippet/cpp/cbasepane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxbasepane.h

## <a name="cbasepaneaccnotifyobjectfocusevent"></a><a name="accnotifyobjectfocusevent"></a>CBasePane::AccNotify개체포커스이벤트

`CBasePane`이 메서드를 사용 하지 않습니다.

```
virtual void AccNotifyObjectFocusEvent(int);
```

### <a name="parameters"></a>매개 변수

*int*<br/>
【인】 사용되지 않습니다.

## <a name="cbasepaneaddpane"></a><a name="addpane"></a>CBasePane::애드파인

도킹 관리자에 창을 추가합니다.

```cpp
void AddPane(CBasePane* pBar);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 추가할 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 방법은 도킹 관리자에 창을 추가하는 편리한 방법입니다. 이 메서드를 사용 하 여 상위 프레임의 형식을 분석 하는 코드를 작성할 필요가 없습니다.

자세한 내용은 [CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md) 및 [CMDIFrameWndEx::AddPane](../../mfc/reference/cmdiframewndex-class.md#addpane)을 참조하십시오.

## <a name="cbasepaneadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CBasePane::조정도킹레이아웃

도킹 관리자로 전화를 리디렉션하여 도킹 레이아웃을 조정합니다.

```
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```

### <a name="parameters"></a>매개 변수

*HDWP*<br/>
【아웃】 여러 창 위치를 포함하는 구조체에 대한 핸들입니다.

### <a name="remarks"></a>설명

이 방법은 도킹 레이아웃을 조정하는 편리한 방법입니다. 이 메서드를 사용 하 여 상위 프레임의 형식을 분석 하는 코드를 작성할 필요가 없습니다.

자세한 내용은 [CDockingManager::adjustDocking레이아웃을](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout) 참조하십시오.

## <a name="cbasepaneadjustlayout"></a><a name="adjustlayout"></a>CBasePane::조정레이아웃

창의 내부 레이아웃을 조정 하기 위해 프레임 워크에 의해 호출 됩니다.

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>설명

창이 내부 레이아웃을 조정해야 할 때 프레임워크는 이 메서드를 호출합니다. 기본 구현은 아무 것도 수행하지 않습니다.

## <a name="cbasepanecalcfixedlayout"></a><a name="calcfixedlayout"></a>CBasePane::석회화레이아웃

컨트롤 막대의 수평 크기를 계산합니다.

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>매개 변수

*b스트레치*<br/>
【인】 막대를 프레임 크기로 늘려야 하는지 여부를 나타냅니다. *bStretch* 매개변수는 막대가 도킹 막대가 아닌 경우 0이 아니며 도킹 또는 부동(도킹에 사용 가능)이 0입니다.

*b호르츠 (주)*<br/>
【인】 막대가 수평 또는 수직 방향임을 나타냅니다. 막대가 가로 방향이고 세로 방향인 경우 0인 경우 *bHorz* 매개변수는 0이 아닙니다.

### <a name="return-value"></a>Return Value

개체의 컨트롤 막대 크기(픽셀 `CSize` 단위)입니다.

### <a name="remarks"></a>설명

[CControlBar:::CalcFixed레이아웃의](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout) 비고 섹션을 참조하십시오.

## <a name="cbasepanecanacceptpane"></a><a name="canacceptpane"></a>CBasePane::캔 수락파인

다른 창을 창에 도킹할 수 있는지 여부를 결정합니다.

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 도킹할 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

다른 창을 수락할 수 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

프레임워크는 *pBar에서* 지정한 창을 현재 창에 도킹하기 전에 이 메서드를 호출합니다.

이 메서드와 [CBasePane:CanBeDocked](#canbedocked) 메서드를 사용하여 창이 응용 프로그램의 다른 창에 도킹되는 방법을 제어합니다.

기본 구현은 FALSE를 반환합니다.

## <a name="cbasepanecanautohide"></a><a name="canautohide"></a>CBasePane::CanAutoHide

창이 자동 숨기기 모드를 지원하는지 여부를 결정합니다.

```
virtual BOOL CanAutoHide() const;
```

### <a name="return-value"></a>Return Value

이 창이 자동 숨기기 모드를 지원하는 경우 TRUE; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

프레임워크는 이 함수를 호출하여 창이 자동 숨기기 모드를 지원하는지 여부를 확인합니다.

시공 하는 동안 AFX_CBRS_AUTOHIDE 플래그를 [CBasePane::CreateEx에](#createex)전달 하 여이 기능을 설정할 수 있습니다.

기본 구현은 AFX_CBRS_AUTOHIDE 플래그를 확인합니다. 파생 클래스에서 이 메서드를 재정의하여 이 동작을 사용자 지정합니다.

## <a name="cbasepanecanbeattached"></a><a name="canbeattached"></a>CBasePane:::첨부할 수 있습니다.

창을 다른 창 또는 프레임 창에 도킹할 수 있는지 여부를 결정합니다.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Return Value

TRUE 창을 다른 창 또는 프레임 창에 도킹할 수 있는 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

기본 구현은 FALSE를 반환합니다. 파생 클래스에서 이 메서드를 재정의하여 [CBasePane::EnableDocking](#enabledocking)을 호출하지 않고 도킹하는 기능을 활성화하거나 사용하지 않도록 설정합니다.

## <a name="cbasepanecanbeclosed"></a><a name="canbeclosed"></a>CBasePane::수 닫힘

창을 닫을 수 있는지 여부를 결정합니다.

```
virtual BOOL CanBeClosed() const;
```

### <a name="return-value"></a>Return Value

TRUE 창을 닫을 수 있는 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

프레임워크는 창을 닫을 수 있는지 여부를 결정하기 위해 이 메서드를 호출합니다. 메서드가 TRUE를 반환하면 **닫기** 단추가 창의 제목 표시줄에 추가되고 창이 부동인 경우 창의 미니프레임 창의 제목 표시줄에 추가됩니다.

시공 하는 동안 AFX_CBRS_CLOSE 플래그를 [CBasePane::CreateEx에](#createex)전달 하 여이 기능을 설정할 수 있습니다.

기본 구현은 AFX_CBRS_CLOSE 플래그를 확인합니다.

## <a name="cbasepanecanbedocked"></a><a name="canbedocked"></a>CBasePane::캔독

창을 다른 창에 도킹할 수 있는지 여부를 결정합니다.

```
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;
```

### <a name="parameters"></a>매개 변수

*pDockBar*<br/>
【인】 다른 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

이 창을 다른 창에 도킹할 수 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

프레임워크는 *pDockBar에서* 지정한 창을 현재 창에 도킹하기 전에 이 메서드를 호출합니다.

이 메서드와 [CBasePane:CanAcceptPane](#canacceptpane) 메서드를 사용하여 창이 응용 프로그램의 다른 창에 도킹되는 방법을 제어합니다.

기본 구현은 FALSE를 반환합니다.

## <a name="cbasepanecanberesized"></a><a name="canberesized"></a>CBasePane::수있습니다

창의 크기를 조정할 수 있는지 여부를 결정합니다.

```
virtual BOOL CanBeResized() const;
```

### <a name="return-value"></a>Return Value

TRUE 창크기를 크기를 조정할 수 있는 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 AFX_CBRS_RESIZE 플래그를 확인 `CBasePane::OnCreate`합니다. 이 플래그를 지정하지 않으면 도킹 관리자는 창을 도킹하는 대신 고정가능한 것으로 내부적으로 플래그를 지정합니다.

## <a name="cbasepanecanbetabbeddocument"></a><a name="canbetabbeddocument"></a>CBasePane::수탭문서

창을 MDI 탭 문서로 변환할 수 있는지 여부를 지정합니다.

```
virtual BOOL CanBeTabbedDocument() const;
```

### <a name="return-value"></a>Return Value

TRUE 창을 탭된 문서로 변환할 수 있는 경우; 그렇지 않으면 false입니다. `CBasePane::CanBeTabbedDocument`항상 FALSE를 반환합니다.

### <a name="remarks"></a>설명

`CBasePane` [CDockablePane 클래스와](../../mfc/reference/cdockablepane-class.md)같은 특정 파생 형식의 개체만 탭된 문서로 변환할 수 있습니다.

## <a name="cbasepanecanfloat"></a><a name="canfloat"></a>CBasePane::캔플로트

창이 부동할 수 있는지 여부를 결정합니다.

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Return Value

TRUE 창이 부동 할 수 있는 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

프레임워크는 이 메서드를 호출하여 창이 부동 할 수 있는지 여부를 결정합니다.

시공 하는 동안 AFX_CBRS_FLOAT 플래그를 [CBasePane::CreateEx에](#createex)전달 하 여이 기능을 설정할 수 있습니다.

> [!NOTE]
> 프레임워크는 부동되지 않는 창이 정적이며 도킹 상태가 변경될 수 없다고 가정합니다. 따라서 프레임워크는 부동 되지 않는 창의 도킹 상태를 저장 하지 않습니다.

기본 구현은 AFX_CBRS_FLOAT 스타일을 검사합니다.

## <a name="cbasepanecanfocus"></a><a name="canfocus"></a>CBasePane::캔포커스

창이 포커스를 수신할 수 있는지 여부를 지정합니다.

```
virtual BOOL CanFocus() const;
```

### <a name="return-value"></a>Return Value

창이 포커스를 받을 수 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드를 파생 클래스에서 재정의하여 포커스를 제어합니다. 예를 들어 도구 모음이 포커스를 받을 수 없기 때문에 이 메서드는 도구 모음 개체에서 호출될 때 FALSE를 반환합니다.

프레임워크는 창이 도킹되거나 부동될 때 입력 포커스를 설정하려고 시도합니다.

## <a name="cbasepanecopystate"></a><a name="copystate"></a>CBasePane::복사 상태

지정된 창의 상태를 복사합니다.

```
virtual void CopyState(CBasePane* pOrgBar);
```

### <a name="parameters"></a>매개 변수

*포그바*<br/>
【인】 다른 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 *pOrgBar에서* 이 창에 상태를 복사합니다.

## <a name="cbasepanecreatedefaultminiframe"></a><a name="createdefaultminiframe"></a>CBasePane::만들기기본미니프레임

창이 부동 할 수있는 경우이 메서드는 창을 위한 미니 프레임 창을 만듭니다.

```
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```

### <a name="parameters"></a>매개 변수

*정류 초기*<br/>
【인】 미니 프레임 창의 초기 좌표를 지정합니다.

### <a name="return-value"></a>Return Value

생성에 실패한 경우 새 미니 프레임 창 또는 NULL에 대한 포인터입니다.

### <a name="remarks"></a>설명

프레임워크는 창이 부동 상태로 전환될 때 이 메서드를 호출합니다. 메서드는 미니 프레임 창을 만들고 창을 이 창에 연결 합니다.

기본 구현은 NULL을 반환합니다.

## <a name="cbasepanecreateex"></a><a name="createex"></a>CBasePane::만들기

창 컨트롤을 만듭니다.

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    DWORD dwControlBarStyle=0,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>매개 변수

*dwStyleEx*<br/>
【인】 확장 된 스타일 (참조 [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) 자세한 내용은).

*lpszClassName*<br/>
【인】 창 클래스 이름입니다.

*lpszWindowName*<br/>
【인】 창 이름입니다.

*dwStyle*<br/>
【인】 창 [스타일(CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)참조).

*rect*<br/>
【인】 초기 사각형입니다.

*pParentWnd*<br/>
【인】 상위 창에 대한 포인터입니다.

*nID*<br/>
【인】 창 ID를 지정합니다. 설명은 고유해야 합니다.

*dw컨트롤바스타일*<br/>
【인】 창에 플래그를 스타일합니다.

*pContext*<br/>
【인】 에 대한 포인터`CcreateContext`

### <a name="return-value"></a>Return Value

TRUE 창이 성공적으로 만들어지면 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

클래스의 `lpszClassName`창을 만듭니다. WS_CAPTION 지정하면 라이브러리에서 캡션이 있는 창을 `CBasePane::m_bHasCaption` 지원하지 않으므로 이 메서드는 WS_CAPTION 스타일 비트를 지우고 TRUE로 설정합니다.

자식 창 스타일과 MFC 컨트롤 바(CBRS_) 스타일의 조합을 사용할 수 있습니다.

라이브러리는 창에 대한 몇 가지 새로운 스타일을 추가합니다. 다음 표는 새 스타일에 대해 설명합니다.

|스타일|Description|
|-----------|-----------------|
|AFX_CBRS_FLOAT|창이 부동할 수 있습니다.|
|AFX_CBRS_AUTOHIDE|창은 자동 숨기기 모드를 지원합니다.|
|AFX_CBRS_RESIZE|창의 크기를 조정할 수 있습니다. **중요 사항:**  이 스타일은 구현되지 않습니다.|
|AFX_CBRS_CLOSE|창을 닫을 수 있습니다.|
|AFX_CBRS_AUTO_ROLLUP|창이 부동 할 때 롤업 할 수 있습니다.|
|AFX_CBRS_REGULAR_TABS|한 창이 이 스타일을 가진 다른 창에 도킹되면 일반 탭창이 만들어집니다. (자세한 내용은 [CTabbedPane 클래스를](../../mfc/reference/ctabbedpane-class.md)참조하십시오.)|
|AFX_CBRS_OUTLOOK_TABS|한 창이 이 스타일을 가진 다른 창에 도킹되면 Outlook 스타일 탭 창이 만들어집니다. (자세한 내용은 [CMFCOutlookBar 클래스를](../../mfc/reference/cmfcoutlookbar-class.md)참조하십시오.)|

새 스타일을 사용하려면 *dwControlBarStyle*에 지정합니다.

## <a name="cbasepanedockpane"></a><a name="dockpane"></a>CBasePane::D오크파인

창을 다른 창이나 프레임 창에 도킹합니다.

```
virtual BOOL DockPane(
    CBasePane* pDockBar,
    LPCRECT lpRect,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>매개 변수

*pDockBar*<br/>
【인】 다른 창에 대한 포인터입니다.

*Lprect*<br/>
【인】 대상 사각형을 지정합니다.

*dockMethod*<br/>
【인】 도킹 방법을 지정합니다.

### <a name="return-value"></a>Return Value

컨트롤 막대가 성공적으로 도킹된 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

*pDockBar에*의해 지정된 다른 창이나 도크 [바(CDockSite Class)에](../../mfc/reference/cdocksite-class.md)창을 도킹하거나 *pDockBar가* NULL인 경우 주 프레임에 이 함수를 호출합니다.

*dockMethod는* 창이 도킹되는 방법을 지정합니다. 가능한 값 목록은 [CPane::DockPane을](../../mfc/reference/cpane-class.md#dockpane) 참조하십시오.

## <a name="cbasepanedockpaneusingrtti"></a><a name="dockpaneusingrtti"></a>CBasePane::DockPaneUsingRTTI

런타임 형식 정보를 사용하여 창을 도킹합니다.

```cpp
void DockPaneUsingRTTI(BOOL bUseDockSite);
```

### <a name="parameters"></a>매개 변수

*bUseDock사이트*<br/>
【인】 TRUE인 경우 도킹 사이트에 도킹합니다. FALSE인 경우 상위 프레임에 도킹합니다.

## <a name="cbasepanedocktoframewindow"></a><a name="docktoframewindow"></a>CBasePane::DockToFrame창

도킹 가능한 창을 프레임에 도킹합니다.

```
virtual BOOL DockToFrameWindow(
    DWORD dwAlignment,
    LPCRECT lpRect = NULL,
    DWORD dwDockFlags = DT_DOCK_LAST,
    CBasePane* pRelativeBar = NULL,
    int nRelativeIndex = -1,
    BOOL bOuterEdge = FALSE);
```

### <a name="parameters"></a>매개 변수

*dw정렬*<br/>
【인】 창을 도킹할 상위 프레임의 측면입니다.

*Lprect*<br/>
【인】 원하는 크기입니다.

*dwDockFlags*<br/>
【인】 무시.

*pRelativeBar*<br/>
【인】 무시.

*n친척색인*<br/>
【인】 무시.

*bOuterEdge*<br/>
【인】 TRUE이고 *dwAlignment에*의해 지정된 측면에 다른 도킹 가능한 창이 있는 경우 창은 부모 프레임의 가장자리에 더 가까운 다른 창 외부에 도킹됩니다. FALSE인 경우 창이 클라이언트 영역의 중심에 더 가깝게 도킹됩니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

창 분할 [(CPane Divider 클래스)를](../../mfc/reference/cpanedivider-class.md)만들 수 없는 경우이 메서드가 실패 합니다. 그렇지 않으면 항상 TRUE를 반환합니다.

## <a name="cbasepanedoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CBasePane::DoesAllowDyn인더인

이 창과 상위 프레임 사이에 다른 창을 동적으로 삽입할 수 있는지 여부를 결정합니다.

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Return Value

TRUE 사용자가 다른 창을 삽입할 수 있는 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

프레임워크는 이 메서드를 호출하여 사용자가 이 창 앞에 창을 동적으로 삽입할 수 있는지 여부를 결정합니다.

예를 들어 응용 프로그램에서 프레임의 왼쪽에 도킹된 창(예: Outlook 막대)을 만든다고 가정합니다. 사용자가 첫 번째 창의 왼쪽에 다른 창을 도킹하지 못하도록 하려면 이 메서드를 재정의하고 FALSE를 반환합니다.

[CDockablePane 클래스에서](../../mfc/reference/cdockablepane-class.md)파생된 부동 되지 않는 창에 대해 이 메서드를 재정의하고 FALSE를 반환하는 것이 좋습니다.

기본 구현은 TRUE를 반환합니다.

## <a name="cbasepanedopaint"></a><a name="dopaint"></a>CBasePane::D페인트

창의 배경을 채웁니다.

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

### <a name="remarks"></a>설명

기본 구현은 현재 시각적 관리자를 호출하여 배경을 [채웁니다(CMFCVisualManager::OnFillBarBackground).](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground)

## <a name="cbasepaneenabledocking"></a><a name="enabledocking"></a>CBasePane::사용 도킹

창을 주 프레임에 도킹할 수 있습니다.

```
virtual void EnableDocking(DWORD dwAlignment);
```

### <a name="parameters"></a>매개 변수

*dw정렬*<br/>
【인】 활성화할 도킹 정렬을 지정합니다.

### <a name="remarks"></a>설명

주 프레임에 도킹 정렬을 활성화하려면 이 메서드를 호출합니다. CBRS_ALIGN_ 플래그 조합을 전달할 수 있습니다(자세한 내용은 [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)참조).

`EnableDocking`내부 플래그를 `CBasePane::m_dwEnabledAlignment` 설정하고 창이 도킹될 때 프레임워크에서 이 플래그를 확인합니다.

[CBasePane::GetEnabledAlignment을](#getenabledalignment) 호출하여 창에 대한 도킹 정렬을 결정합니다.

## <a name="cbasepaneenablegripper"></a><a name="enablegripper"></a>CBasePane::인에이블그리퍼

그리퍼를 활성화하거나 비활성화합니다. 그리퍼가 활성화된 경우 사용자는 그리퍼를 드래그하여 창의 위치를 변경할 수 있습니다.

```
virtual void EnableGripper(BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 트루는 그리퍼를 활성화하기 위해; FALSE를 비활성화합니다.

### <a name="remarks"></a>설명

프레임워크는 이 메서드를 사용하여 WS_CAPTION 스타일을 사용하는 대신 그리퍼를 사용하도록 설정합니다.

## <a name="cbasepanefloatpane"></a><a name="floatpane"></a>CBasePane::플로트파인

창을 부동합니다.

```
virtual BOOL FloatPane(
    CRect rectFloat,
    AFX_DOCK_METHOD dockMethod=DM_UNKNOWN,
    bool bShow=true);
```

### <a name="parameters"></a>매개 변수

*직류 플로트*<br/>
【인】 부동 창이 나타나는 화면 좌표를 지정합니다.

*dockMethod*<br/>
【인】 창을 부동에 사용할 dock 메서드를 지정합니다.

*bShow*<br/>
【인】 부동 창이 표시되는지(TRUE) 또는 숨김(FALSE)을 지정합니다.

### <a name="return-value"></a>Return Value

창이 성공적으로 부동된 경우 TRUE; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드를 호출하여 *rectFloat에서*지정한 화면 위치에 창을 플로팅합니다.

## <a name="cbasepaneget_acchelptopic"></a><a name="get_acchelptopic"></a>CBasePane::get_accHelpTopic

프레임워크는 지정된 개체와 연결된 **WinHelp** 파일의 전체 경로및 해당 파일에 있는 적절한 토픽의 식별자를 검색하기 위해 이 메서드를 호출합니다.

```
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,
    VARIANT varChild,
    long* pidTopic);
```

### <a name="parameters"></a>매개 변수

*psz도움말파일*<br/>
【인】 지정된 개체와 연결된 **WinHelp** 파일의 전체 경로를 수신하는 BSTR의 주소(있는 경우)입니다.

*바차일드*<br/>
【인】 검색할 도움말 항목이 개체의 항목인지 아니면 개체의 자식 요소 중 하나인지 지정합니다. 이 매개 변수는 CHILDID_SELF(개체에 대한 도움말 항목을 가져오려면) 또는 자식 ID(개체의 자식 요소 중 하나에 대한 도움말 항목을 가져오려면)일 수 있습니다.

*pidTopic*<br/>
【인】 지정된 개체와 연결된 **도움말** 파일 항목을 식별합니다.

### <a name="return-value"></a>Return Value

`CBasePane`이 메서드를 구현 하지 않습니다. 따라서 `CBasePane::get_accHelpTopic` 항상 S_FALSE 반환합니다.

### <a name="remarks"></a>설명

이 기능은 MFC의 활성 접근성 지원의 일부입니다. 파생 클래스에서 이 함수를 재정의하여 개체에 대한 도움말 정보를 제공합니다.

## <a name="cbasepaneget_accselection"></a><a name="get_accselection"></a>CBasePane::get_accSelection

프레임워크는 이 메서드를 호출하여 이 개체의 선택된 자식을 검색합니다.

```
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```

### <a name="parameters"></a>매개 변수

*pvar어린이*<br/>
【인】 선택한 자식을 식별하는 정보를 받습니다.

### <a name="return-value"></a>Return Value

`CBasePane`이 메서드를 구현 하지 않습니다. *pvarChildren이* NULL인 경우 이 메서드는 E_INVALIDARG 반환합니다. 그렇지 않으면 이 메서드는 DISP_E_MEMBERNOTFOUND 반환합니다.

### <a name="remarks"></a>설명

이 기능은 MFC의 활성 접근성 지원의 일부입니다. 창없는 ActiveX 컨트롤 이외의 창이 없는 사용자 인터페이스 요소가 있는 경우 파생 클래스에서 이 함수를 재정의합니다.

## <a name="cbasepanegetcaptionheight"></a><a name="getcaptionheight"></a>CBasePane::GetCaptionHeight

캡션 높이를 반환합니다.

```
virtual int GetCaptionHeight() const;
```

### <a name="return-value"></a>Return Value

캡션 높이입니다.

## <a name="cbasepanegetcontrolbarstyle"></a><a name="getcontrolbarstyle"></a>CBasePane::GetControlBar스타일

컨트롤 막대 스타일을 반환합니다.

```
virtual DWORD GetControlBarStyle() const
```

### <a name="return-value"></a>Return Value

AFX_CBRS_ 플래그의 비트 또는 조합입니다.

### <a name="remarks"></a>설명

반환 값은 다음과 같은 가능한 값의 조합입니다.

|스타일|Description|
|-----------|-----------------|
|AFX_CBRS_FLOAT|컨트롤 막대를 부동 으로 만듭니다.|
|AFX_CBRS_AUTOHIDE|자동 숨기기 모드를 활성화합니다.|
|AFX_CBRS_RESIZE|컨트롤 막대의 크기 조정을 활성화합니다. 이 플래그를 설정하면 도킹 가능한 창에 컨트롤 막대를 배치할 수 있습니다.|
|AFX_CBRS_CLOSE|컨트롤 막대를 숨길 수 있습니다.|

## <a name="cbasepanegetcurrentalignment"></a><a name="getcurrentalignment"></a>CBasePane::GetCurrent정렬

현재 창 선형을 반환합니다.

```
virtual DWORD GetCurrentAlignment() const;
```

### <a name="return-value"></a>Return Value

컨트롤 막대의 현재 정렬입니다. 다음 표에서는 가능한 값을 보여 주며 다음과 같은 값을 보여 주며 다음과 같은 값을 보여 주며 있습니다.

|값|맞춤|
|-----------|---------------|
|CBRS_ALIGN_LEFT|왼쪽 맞춤.|
|CBRS_ALIGN_RIGHT|오른쪽 정렬.|
|CBRS_ALIGN_TOP|상단 정렬.|
|CBRS_ALIGN_BOTTOM|하단 정렬.|

## <a name="cbasepanegetdockingmode"></a><a name="getdockingmode"></a>CBasePane::겟도킹 모드

창에 대한 현재 도킹 모드를 반환합니다.

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>Return Value

창을 드래그하는 경우 DT_STANDARD 드래그 사각형으로 화면에 표시됩니다. 창의 내용을 드래그하는 경우 DT_IMMEDIATE.

### <a name="remarks"></a>설명

프레임워크는 이 메서드를 호출하여 창의 현재 도킹 모드를 결정합니다.

`CBasePane::m_dockMode` 정의되지 않은 경우(DT_UNDEFINED) 도킹 모드는 전역 도킹`AFX_GLOBAL_DATA::m_dockModeGlobal`모드()에서 가져온 것입니다.

*m_dockMode* 설정하거나 재정의하면 `GetDockingMode` 각 창에 대한 도킹 모드를 제어할 수 있습니다.

## <a name="cbasepanegetdocksiteframewnd"></a><a name="getdocksiteframewnd"></a>CBasePane::GetDockSiteFrameD

창이 도킹된 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)개체에 대한 포인터를 반환합니다.

```
virtual CWnd* GetDockSiteFrameWnd() const;
```

### <a name="return-value"></a>Return Value

창의 도크 사이트에 대한 포인터입니다.

### <a name="remarks"></a>설명

창의 도크 사이트에 대한 포인터를 검색하려면 이 메서드를 호출합니다. 창이 주 프레임에 도킹된 경우 도크 사이트는 주 프레임 창이거나 창이 부동하는 경우 미니 프레임 창이 될 수 있습니다.

## <a name="cbasepanegetenabledalignment"></a><a name="getenabledalignment"></a>CBasePane::GetEnabled정렬

창에 적용되는 CBRS_ALIGN_ 스타일을 반환합니다.

```
virtual DWORD GetEnabledAlignment() const;
```

### <a name="return-value"></a>Return Value

CBRS_ALIGN_ 스타일의 조합입니다. 다음 표에서는 가능한 스타일을 보여 주었습니다.

|플래그|사용 가능한 정렬|
|----------|-----------------------|
|CBRS_ALIGN_LEFT|왼쪽.|
|CBRS_ALIGN_RIGHT|오른쪽.|
|CBRS_ALIGN_TOP|위쪽.|
|CBRS_ALIGN_BOTTOM|하단.|
|CBRS_ALIGN_ANY|모든 플래그의 조합입니다.|

### <a name="remarks"></a>설명

이 메서드를 호출하여 창에 대해 활성화된 선형을 확인합니다. 활성화된 정렬은 창을 도킹할 수 있는 주 프레임 창의 측면을 의미합니다.

[CBasePane::EnableDocking을](#enabledocking)사용하여 도킹 정렬을 활성화합니다.

## <a name="cbasepanegetmfcstyle"></a><a name="getmfcstyle"></a>CBasePane::GetMFC스타일

MFC에 특정한 창 스타일을 반환합니다.

```
virtual DWORD GetMFCStyle() const;
```

### <a name="return-value"></a>Return Value

라이브러리별(AFX_CBRS_) 창 스타일의 조합입니다.

## <a name="cbasepanegetpaneicon"></a><a name="getpaneicon"></a>CBasePane::GetPaneIcon

창 아이콘에 핸들을 반환합니다.

```
virtual HICON GetPaneIcon(BOOL bBigIcon);
```

### <a name="parameters"></a>매개 변수

*bBigIcon*<br/>
【인】 TRUE인 경우 32픽셀 x 32픽셀 아이콘을 지정합니다. FALSE인 경우 16픽셀 x 16픽셀 아이콘을 지정합니다.

### <a name="return-value"></a>Return Value

창 아이콘의 핸들입니다. 실패하면 NULL을 반환합니다.

### <a name="remarks"></a>설명

기본 구현은 [CWnd::GetIcon을](../../mfc/reference/cwnd-class.md#geticon)호출합니다.

## <a name="cbasepanegetpanerow"></a><a name="getpanerow"></a>CBasePane:::겟파네로우

창이 도킹된 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)개체에 대한 포인터를 반환합니다.

```
CDockingPanesRow* GetPaneRow();
```

### <a name="return-value"></a>Return Value

창이 `CDockingPanesRow` 도킹되었는지 에 대한 포인터 또는 부동 창인 경우 NULL입니다.

### <a name="remarks"></a>설명

창이 도킹된 행에 액세스하려면 이 메서드를 호출합니다. 예를 들어 특정 행의 창을 정렬하려면 `GetPaneRow` 전화를 걸고 [CDockingPanesRow::ArrangePanes](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes)를 호출합니다.

## <a name="cbasepanegetpanestyle"></a><a name="getpanestyle"></a>CBasePane::겟파인 스타일

창 스타일을 반환합니다.

```
virtual DWORD GetPaneStyle() const;
```

### <a name="return-value"></a>Return Value

생성 시 [CBasePane::SetPaneStyle](#setpanestyle) 메서드에 의해 설정된 컨트롤 막대 스타일(CBRS_ 스타일 포함)의 조합입니다.

## <a name="cbasepanegetparentdocksite"></a><a name="getparentdocksite"></a>CBasePane::GetParentDockSite

상위 도크 사이트에 대한 포인터를 반환합니다.

```
virtual CDockSite* GetParentDockSite() const;
```

### <a name="return-value"></a>Return Value

상위 도크 사이트입니다.

## <a name="cbasepanegetparentminiframe"></a><a name="getparentminiframe"></a>CBasePane::GetParentMiniFrame

상위 미니 프레임 창에 대한 포인터를 반환합니다.

```
virtual CPaneFrameWnd* GetParentMiniFrame(BOOL bNoAssert=FALSE) const;
```

### <a name="parameters"></a>매개 변수

*bNoAssert*<br/>
【인】 TRUE인 경우 이 메서드는 유효하지 않은 포인터를 확인하지 않습니다. 응용 프로그램이 종료될 때 이 메서드를 호출하는 경우 이 매개 변수를 TRUE로 설정합니다.

### <a name="return-value"></a>Return Value

창이 부동 하는 경우 부모 미니 프레임 창에 대 한 유효한 포인터; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 함수를 호출하여 부모 미니 프레임 창에 대한 포인터를 검색합니다. 이 메서드는 모든 부모를 거치고 [CPaneFrameWnd 클래스에서](../../mfc/reference/cpaneframewnd-class.md)파생된 개체를 확인합니다.

창이 부동 인지 여부를 확인 하는 데 사용 합니다. `GetParentMiniFrame`

## <a name="cbasepanegetparenttabbedpane"></a><a name="getparenttabbedpane"></a>CBasePane:::GetParentTabbedPane

상위 탭창에 대한 포인터를 반환합니다.

```
CBaseTabbedPane* GetParentTabbedPane() const;
```

### <a name="return-value"></a>Return Value

상위 탭 창에 대한 포인터가 있는 경우 그렇지 않으면 NULL.

## <a name="cbasepanegetparenttabwnd"></a><a name="getparenttabwnd"></a>CBasePane::GetParentTabwnd

탭 안에 있는 부모 창에 대한 포인터를 반환합니다.

```
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;
```

### <a name="parameters"></a>매개 변수

*hWndTab*<br/>
【아웃】 반환 값이 NULL이 아닌 경우 이 매개 변수에는 상위 탭된 창에 대한 핸들이 포함됩니다.

### <a name="return-value"></a>Return Value

상위 탭 창 또는 NULL에 대한 유효한 포인터입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 부모 탭 창에 대한 포인터를 검색합니다. 창이 도킹 래퍼 `GetParent` [(CDockablePaneAdapter 클래스)](../../mfc/reference/cdockablepaneadapter-class.md)내부 또는 창 어댑터 [(CDockablePaneAdapter 클래스)](../../mfc/reference/cdockablepaneadapter-class.md)내부에있을 수 있기 때문에 호출하기에 충분하지 않을 수 있습니다. 이러한 `GetParentTabWnd` 경우 유효한 포인터를 검색할 수 있습니다(부모가 탭된 창이라고 가정).

## <a name="cbasepanegetrecentvisiblestate"></a><a name="getrecentvisiblestate"></a>CBasePane::Get최근가볼 수 있는 상태

프레임워크는 보관에서 창이 복원될 때 이 메서드를 호출합니다.

```
virtual BOOL GetRecentVisibleState() const;
```

### <a name="return-value"></a>Return Value

최근 표시되는 상태를 지정하는 BOOL입니다. TRUE이면 창이 직렬화될 때 표시되고 복원될 때 표시되어야 합니다. FALSE인 경우 창은 직렬화될 때 숨겨져 있으며 복원할 때 숨어야합니다.

## <a name="cbasepanehideinprintpreviewmode"></a><a name="hideinprintpreviewmode"></a>CBasePane::숨바꼭한인쇄 미리보기 모드

창이 인쇄 미리 보기에 숨겨져 있는지 여부를 지정합니다.

```
virtual BOOL HideInPrintPreviewMode() const;
```

### <a name="return-value"></a>Return Value

창이 인쇄 미리 보기에 표시되지 않는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

기본 창은 인쇄 미리 보기에 표시되지 않습니다. 따라서이 메서드는 항상 TRUE를 반환 합니다.

## <a name="cbasepaneinsertpane"></a><a name="insertpane"></a>CBasePane::삽입창

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

## <a name="cbasepaneisaccessibilitycompatible"></a><a name="isaccessibilitycompatible"></a>CBasePane::접근성 호환

창이 활성 접근성을 지원하는지 여부를 지정합니다.

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>Return Value

TRUE 창이 활성 내게 필요한 옵션 지원을 지원하는 경우; 그렇지 않으면 false입니다.

## <a name="cbasepaneisautohidemode"></a><a name="isautohidemode"></a>CBasePane::IsAutoHideMode

창이 자동 숨기기 모드에 있는지 여부를 결정합니다.

```
virtual BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>Return Value

창이 자동 숨기기 모드인 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

기본 창은 자동으로 숨길 수 없습니다. 이 메서드는 항상 FALSE를 반환합니다.

## <a name="cbasepaneisdialogcontrol"></a><a name="isdialogcontrol"></a>CBasePane::IsDialog제어

창이 대화 상자 컨트롤인지 여부를 지정합니다.

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>Return Value

창이 대화 상자 컨트롤인 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

프레임워크는 이 메서드를 사용하여 모든 창에 대한 레이아웃 일관성을 보장합니다.

## <a name="cbasepaneisdocked"></a><a name="isdocked"></a>CBasePane::IsDocked

창이 도킹되었는지 여부를 결정합니다.

```
virtual BOOL IsDocked() const;
```

### <a name="return-value"></a>Return Value

TRUE 창의 부모가 미니 프레임이 아니거나 창이 다른 창이 있는 미니 프레임에 떠 있는 경우 그렇지 않으면 false입니다.

## <a name="cbasepaneisfloating"></a><a name="isfloating"></a>CBasePane::떠 있는

창이 부동 인지 여부를 확인 합니다.

```
virtual BOOL IsFloating() const;
```

### <a name="return-value"></a>Return Value

창이 부동 하는 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 [CBasePane::IsDocked의](#isdocked)반대 값을 반환합니다.

## <a name="cbasepaneishorizontal"></a><a name="ishorizontal"></a>CBasePane::수평

창이 수평으로 도킹되는지 여부를 결정합니다.

```
virtual BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Return Value

창이 수평으로 도킹된 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

기본 구현은 CBRS_ORIENT_HORZ 대해 현재 도킹 정렬을 검사합니다.

## <a name="cbasepaneisinfloatingmultipaneframewnd"></a><a name="isinfloatingmultipaneframewnd"></a>CBasePane::이인 플로팅멀티파인프레임

창이 다중 창 프레임 창에 있는지 여부를 [지정합니다(CMultiPaneFrameWnd 클래스).](../../mfc/reference/cmultipaneframewnd-class.md)

```
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;
```

### <a name="return-value"></a>Return Value

창이 다중 창 프레임 창에 있는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

도킹 가능한 창만 다중 창 프레임 창에 떠있을 수 있습니다. 따라서 `CBasePane::IsInFloatingMultiPaneFrameWnd` 항상 FALSE를 반환합니다.

## <a name="cbasepaneismditabbed"></a><a name="ismditabbed"></a>CBasePane::IsMDITabbed

창이 탭된 문서로 MDI 자식 창에 추가되었는지 여부를 결정합니다.

```
virtual BOOL IsMDITabbed() const;
```

### <a name="return-value"></a>Return Value

TRUE 창이 탭된 문서로 MDI 자식 창에 추가된 경우 그렇지 않으면 false입니다.

## <a name="cbasepaneispanevisible"></a><a name="ispanevisible"></a>CBasePane::IsPaneVisible

창에 대해 WS_VISIBLE 플래그가 설정되어 있는지 여부를 지정합니다.

```
BOOL IsPaneVisible() const;
```

### <a name="return-value"></a>Return Value

WS_VISIBLE 설정된 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

[CBasePane::가시광선을](#isvisible) 사용하여 창 가시성을 확인합니다.

## <a name="cbasepaneispointneardocksite"></a><a name="ispointneardocksite"></a>CBasePane::이포인트니어독사이트

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
【아웃】 점이 근처에 있는 모서리를 지정합니다. 가능한 값은 CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT, CBRS_ALIGN_TOP 및 CBRS_ALIGN_BOTTOM

*bOuterEdge*<br/>
【아웃】 TRUE 점이 도크 사이트의 외부 테두리 근처에 있는 경우; 그렇지 않으면 거짓.

### <a name="return-value"></a>Return Value

포인트가 도크 사이트 근처에 있는 경우 TRUE; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

점은 도킹 관리자에서 설정된 민감도 내에 있을 때 도크 사이트 근처에 있습니다. 기본 민감도는 15픽셀입니다.

## <a name="cbasepaneisresizable"></a><a name="isresizable"></a>CBasePane::이재성

창의 크기를 조정할 수 있는지 여부를 결정합니다.

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>Return Value

TRUE 사용자가 창을 크기를 조정할 수 있는 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

[CDockablePane 클래스의](../../mfc/reference/cdockablepane-class.md) 창 크기를 조정할 수 있습니다.

상태 [표시줄(CMFCStatusBar 클래스)과](../../mfc/reference/cmfcstatusbar-class.md)도크 모음(CDockSite [클래스)의](../../mfc/reference/cdocksite-class.md)크기를 조정할 수 없습니다.

## <a name="cbasepaneisrestoredfromregistry"></a><a name="isrestoredfromregistry"></a>CBasePane::복원에서레지스트리

창이 레지스트리에서 복원되는지 여부를 결정합니다.

```
virtual BOOL IsRestoredFromRegistry() const;
```

### <a name="return-value"></a>Return Value

TRUE 창이 레지스트리에서 복원되는 경우 그렇지 않으면 false입니다.

## <a name="cbasepaneistabbed"></a><a name="istabbed"></a>CBasePane::IsTabbed

탭된 창의 탭 컨트롤에 창이 삽입되었는지 여부를 결정합니다.

```
virtual BOOL IsTabbed() const;
```

### <a name="return-value"></a>Return Value

TRUE 컨트롤 막대가 탭된 창의 탭에 삽입된 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 즉시 부모에 대 한 포인터를 검색 하 고 부모의 런타임 [클래스는 CMFCBaseTabCtrl 클래스](../../mfc/reference/cmfcbasetabctrl-class.md)인지 확인 합니다.

## <a name="cbasepaneisvisible"></a><a name="isvisible"></a>CBasePane::가 보입니다.

창이 표시되는지 여부를 결정합니다.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Return Value

TRUE 창이 표시되는 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드를 사용하여 창의 가시성을 확인합니다. `::IsWindowVisible`는 사용하지 마세요.

창이 탭되지 않은 [경우(CBasePane::IsTabbed](#istabbed)참조) 이 메서드는 WS_VISIBLE 스타일을 확인합니다. 창이 탭된 경우 이 메서드는 상위 탭 창의 가시성을 확인합니다. 상위 창이 표시되는 경우 함수는 [CMFCBaseTabCtrl::IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible)를 사용하여 창 탭의 가시성을 확인합니다.

## <a name="cbasepaneloadstate"></a><a name="loadstate"></a>CBasePane::로드스테이트

레지스트리에서 창의 상태를 로드합니다.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName=NULL,
    int nIndex=-1,
    UINT uiID=(UINT)-1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 프로필 이름입니다.

*nIndex*<br/>
【인】 프로필 인덱스입니다.

*uiID*<br/>
【인】 창 ID.

### <a name="return-value"></a>Return Value

TRUE 창 상태가 성공적으로 로드된 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

프레임워크는 이 메서드를 호출하여 레지스트리에서 창 상태를 로드합니다. 파생 클래스에서 재정의하여 [CBasePane::SaveState](#savestate)에 의해 저장된 추가 정보를 로드합니다.

## <a name="cbasepanemovewindow"></a><a name="movewindow"></a>CBasePane::이동 창

창을 이동합니다.

```
virtual HDWP MoveWindow(
    CRect& rect,
    BOOL bRepaint = TRUE,
    HDWP hdwp = NULL);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 창의 새 위치와 크기를 지정하는 사각형입니다.

*bRepaint*<br/>
【인】 TRUE이면 창이 다시 그려집니다. FALSE이면 창이 다시 그려지지 않습니다.

*HDWP*<br/>
【인】 지연된 창 위치 구조로 처리합니다.

### <a name="return-value"></a>Return Value

지연된 창 위치 구조 또는 NULL에 대한 핸들입니다.

### <a name="remarks"></a>설명

*NULL을 hdwp* 매개 변수로 전달하는 경우 이 메서드는 창을 정상적으로 이동합니다. 핸들을 전달하는 경우 이 메서드는 지연된 창 이동을 수행합니다. [BeginDeferWindowPos를](/windows/win32/api/winuser/nf-winuser-begindeferwindowpos) 호출하거나 이 메서드에 이전 호출의 반환 값을 저장하여 핸들을 가져올 수 있습니다.

## <a name="cbasepaneonafterchangeparent"></a><a name="onafterchangeparent"></a>CBasePane::온애프터체인지부모

창의 부모가 변경된 후 프레임워크에서 호출됩니다.

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>매개 변수

*pWndOld부모*<br/>
【인】 이전 부모에 대한 포인터입니다.

### <a name="remarks"></a>설명

프레임워크는 일반적으로 도킹 또는 부동 작업으로 인해 창의 부모가 변경된 후 이 메서드를 호출합니다.

기본 구현은 아무 작업도 수행하지 않습니다.

## <a name="cbasepaneonbeforechangeparent"></a><a name="onbeforechangeparent"></a>CBasePane::에 전에변경부모

창이 부모 창을 변경하기 직전에 프레임워크에서 호출됩니다.

```
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,
    BOOL bDelay=FALSE);
```

### <a name="parameters"></a>매개 변수

*pWndNewParent*<br/>
【인】 새 부모 창에 대한 포인터입니다.

*bDelay*<br/>
【인】 레이아웃 조정을 지연해야 하는지 여부를 지정합니다.

### <a name="remarks"></a>설명

프레임워크는 일반적으로 도킹, 부동 또는 자동 숨기기 작업으로 인해 창의 부모가 변경되기 직전에 이 메서드를 호출합니다.

기본 구현은 아무 작업도 수행하지 않습니다.

## <a name="cbasepaneondrawcaption"></a><a name="ondrawcaption"></a>CBasePane::온드로우 캡션

프레임워크는 캡션이 그려질 때 이 메서드를 호출합니다.

```
virtual void OnDrawCaption();
```

### <a name="remarks"></a>설명

이 메서드에는 `CBasePane` 클래스에 대 한 기능이 없습니다.

## <a name="cbasepaneonmovepanedivider"></a><a name="onmovepanedivider"></a>CBasePane::온무파네 분배기

이 메서드는 현재 사용 되지 않습니다.

```
virtual void OnMovePaneDivider(CPaneDivider* /* unused */);
```

### <a name="parameters"></a>매개 변수

*하지 않는*<br/>
【인】 사용되지 않습니다.

## <a name="cbasepaneonpanecontextmenu"></a><a name="onpanecontextmenu"></a>CBasePane::온파네컨텍스트 메뉴

창 목록이 있는 메뉴를 빌드할 때 프레임워크에서 호출합니다.

```
virtual void OnPaneContextMenu(
    CWnd* pParentFrame,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*p부모 프레임*<br/>
【인】 상위 프레임에 대한 포인터입니다.

*지점*<br/>
【인】 바로 가기 메뉴의 위치를 지정합니다.

### <a name="remarks"></a>설명

`OnPaneContextMenu`현재 프레임 창에 속하는 창 목록을 유지 관리하는 도킹 관리자를 호출합니다. 이 메서드는 바로 가기 메뉴에 창의 이름을 추가 하 고 표시 합니다. 메뉴의 명령은 개별 창을 표시하거나 숨깁니다.

이 메서드를 재정의하여 이 동작을 사용자 지정합니다.

## <a name="cbasepaneonremovefromminiframe"></a><a name="onremovefromminiframe"></a>CBasePane::에제거해제미니프레임

상위 미니 프레임 창에서 창이 제거될 때 프레임워크에서 호출됩니다.

```
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```

### <a name="parameters"></a>매개 변수

*pMiniFrame*<br/>
【인】 창이 제거되는 미니 프레임 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

프레임워크는 도킹의 결과로 부모 미니 프레임 창에서 창이 제거될 때 이 메서드를 호출합니다.

기본 구현은 아무 작업도 수행하지 않습니다.

## <a name="cbasepaneonsetaccdata"></a><a name="onsetaccdata"></a>CBasePane::온셋데이터

`CBasePane`이 메서드를 사용 하지 않습니다.

```
virtual BOOL OnSetAccData(long lVal);
```

### <a name="parameters"></a>매개 변수

*lVal*<br/>
【인】 사용되지 않습니다.

### <a name="return-value"></a>Return Value

이 메서드는 항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cbasepanepanefrompoint"></a><a name="panefrompoint"></a>CBasePane::P인FromPoint

지정된 점을 포함하는 창을 반환합니다.

```
CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    bool bExactBar = false,
    CRuntimeClass* pRTCBarType = NULL) const;
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
【인】 검사할 점을 화면 좌표로 지정합니다.

*n감도*<br/>
【인】 이 금액만큼 검색 영역을 늘립니다. 지정된 지점이 증가된 영역에 속하는 경우 창이 검색 기준을 충족합니다.

*bExactBar*<br/>
【인】 *true는 nSensitivity* 매개 변수를 무시합니다. 그렇지 않으면 false입니다.

*pRTCBarType*<br/>
【인】 NULL이 아닌 경우 메서드는 지정된 형식의 창만 검색합니다.

### <a name="return-value"></a>Return Value

지정된 `CBasePane`점을 포함하는 -derive된 개체 또는 창이 없는 경우 NULL입니다.

## <a name="cbasepanerecalclayout"></a><a name="recalclayout"></a>CBasePane::리콜레이아웃

`CBasePane`이 메서드를 사용 하지 않습니다.

```
virtual void RecalcLayout();
```

## <a name="cbasepaneremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>CBasePane::제거파인에서독매니저

창을 등록 취소하고 도킹 관리자의 목록에서 창이 제거됩니다.

```cpp
void RemovePaneFromDockManager(
    CBasePane* pBar,
    BOOL bDestroy = TRUE,
    BOOL bAdjustLayout = FALSE,
    BOOL bAutoHide = FALSE,
    CBasePane* pBarReplacement = NULL);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 제거할 창에 대한 포인터입니다.

*bDestroy*<br/>
【인】 TRUE이면 제거된 창이 소멸됩니다.

*bAdjust레이아웃*<br/>
【인】 TRUE인 경우 도킹 레이아웃을 즉시 조정합니다.

*b자동 숨기기*<br/>
【인】 TRUE인 경우 도킹 레이아웃은 자동 숨기기 막대 목록과 관련이 있습니다. FALSE인 경우 도킹 레이아웃은 일반 창 목록과 관련이 있습니다.

*pBar교체*<br/>
【인】 제거된 창을 대체하는 창에 대한 포인터입니다.

## <a name="cbasepanesavestate"></a><a name="savestate"></a>CBasePane::저장 상태

레지스트리에 창의 상태를 저장합니다.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName=NULL,
    int nIndex=-1,
    UINT uiID=(UINT)-1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 프로필 이름입니다.

*nIndex*<br/>
【인】 프로필 인덱스입니다.

*uiID*<br/>
【인】 창 ID.

### <a name="return-value"></a>Return Value

TRUE 상태가 성공적으로 저장된 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

프레임워크는 창의 상태를 레지스트리에 저장할 때 이 메서드를 호출합니다. 파생 `SaveState` 클래스에서 재정의하여 추가 정보를 저장합니다.

## <a name="cbasepaneselectdefaultfont"></a><a name="selectdefaultfont"></a>CBasePane::선택기본글꼴

지정된 장치 컨텍스트에 대한 기본 글꼴을 선택합니다.

```
CFont* SelectDefaultFont(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트입니다.

### <a name="return-value"></a>Return Value

기본 [CFont 클래스](../../mfc/reference/cfont-class.md) 개체에 대한 포인터입니다.

## <a name="cbasepanesetcontrolbarstyle"></a><a name="setcontrolbarstyle"></a>CBasePane::세트컨트롤바스타일

컨트롤 막대 스타일을 설정합니다.

```
virtual void SetControlBarStyle(DWORD dwNewStyle);
```

### <a name="parameters"></a>매개 변수

*dwNewStyle*<br/>
【인】 다음과 같은 가능한 값의 비트-OR 조합입니다.

|스타일|Description|
|-----------|-----------------|
|AFX_CBRS_FLOAT|컨트롤 막대를 부동 으로 만듭니다.|
|AFX_CBRS_AUTOHIDE|자동 숨기기 모드를 활성화합니다.|
|AFX_CBRS_RESIZE|컨트롤 막대의 크기 조정을 활성화합니다. 이 플래그를 설정하면 도킹 가능한 창에 컨트롤 막대를 배치할 수 있습니다.|
|AFX_CBRS_CLOSE|컨트롤 막대를 숨길 수 있습니다.|

## <a name="cbasepanesetdockingmode"></a><a name="setdockingmode"></a>CBasePane::SetDocking 모드

창에 대한 도킹 모드를 설정합니다.

```cpp
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```

### <a name="parameters"></a>매개 변수

*독모드신규*<br/>
【인】 창에 대한 새 도킹 모드를 지정합니다.

### <a name="remarks"></a>설명

프레임워크는 표준 및 즉시 도킹 모드의 두 가지 도킹 모드를 지원합니다.

표준 도킹 모드에서는 드래그 사각형을 사용하여 창과 미니 프레임 창이 이동됩니다. 즉각적인 도킹 모드에서는 컨트롤 바와 미니 프레임 창이 컨텍스트에 따라 즉시 이동됩니다.

처음에 도킹 모드는 [CDockingManager:m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal)에 의해 전역적으로 정의됩니다. `SetDockingMode` 메서드를 사용하여 각 창에 대해 개별적으로 도킹 모드를 설정할 수 있습니다.

## <a name="cbasepanesetpanealignment"></a><a name="setpanealignment"></a>CBasePane::세파네정렬

창의 맞춤을 설정합니다.

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>매개 변수

*dw정렬*<br/>
【인】 새 정렬을 지정합니다.

### <a name="remarks"></a>설명

일반적으로 프레임워크는 창이 주 프레임의 한 쪽에서 다른 쪽으로 도킹될 때 이 메서드를 호출합니다.

다음 표에서는 *dwAlignment에*대해 가능한 값을 보여 주며 다음과 같은 값을 보여 주며 다음과 같은 값을 보여 주며 다음과 같은 값을 보여 주며 다음과 같은 값을 보여 주며 다음과

|값|맞춤|
|-----------|---------------|
|CBRS_ALIGN_LEFT|왼쪽 맞춤.|
|CBRS_ALIGN_RIGHT|오른쪽 정렬.|
|CBRS_ALIGN_TOP|상단 정렬.|
|CBRS_ALIGN_BOTTOM|하단 정렬.|

## <a name="cbasepanesetpanestyle"></a><a name="setpanestyle"></a>CBasePane::SetPaneStyle

창의 스타일을 설정합니다.

```
virtual void SetPaneStyle(DWORD dwNewStyle);
```

### <a name="parameters"></a>매개 변수

*dwNewStyle*<br/>
【인】 설정할 새 스타일을 지정합니다.

### <a name="remarks"></a>설명

이 메서드는 afxres.h에 정의된 CBRS_ 스타일을 설정하는 데 사용할 수 있습니다. 창 스타일과 창 맞춤이 함께 저장되므로 다음과 같이 현재 선형과 결합하여 새 스타일을 설정합니다.

`pPane->SetPaneStyle (pPane->GetCurrentAlignment() | CBRS_TOOLTIPS);`

## <a name="cbasepanesetwindowpos"></a><a name="setwindowpos"></a>CBasePane::SetWindowPos

창의 크기, 위치 및 Z 순서를 변경합니다.

```
virtual HDWP SetWindowPos(
    const CWnd* pWndInsertAfter,
    int x,
    int y,
    int cx,
    int cy,
    UINT nFlags,
    HDWP hdwp = NULL);
```

### <a name="parameters"></a>매개 변수

*pWnd인더*<br/>
【인】 Z 순서로 `CWnd` 이 `CWnd` 개체 앞에 오는 개체를 식별합니다. 자세한 내용은 [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)를 참조하십시오.

*x*<br/>
【인】 창의 왼쪽 위치를 지정합니다.

*Y*<br/>
【인】 창 위쪽의 위치를 지정합니다.

*Cx*<br/>
【인】 창의 너비를 지정합니다.

*Cy*<br/>
【인】 창의 높이를 지정합니다.

*nFlags*<br/>
【인】 크기 및 위치 옵션을 지정합니다. 자세한 내용은 [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)를 참조하십시오.

*HDWP*<br/>
【인】 하나 이상의 창에 대한 크기 및 위치 정보가 포함된 구조를 처리합니다.

### <a name="return-value"></a>Return Value

업데이트된 지연된 창 위치 구조 또는 NULL에 대한 핸들입니다.

### <a name="remarks"></a>설명

*pWndInsertAfter가* NULL인 경우 이 메서드는 [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)를 호출합니다. *pWndInsertAfter가* NULL이 아닌 경우 `DeferWindowPos`이 메서드는 을 호출합니다.

## <a name="cbasepaneshowpane"></a><a name="showpane"></a>CBasePane::쇼파인

창을 표시하거나 숨깁니다.

```
virtual void ShowPane(
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
【인】 창을 표시할지(TRUE) 또는 숨기기(FALSE)할지 지정합니다.

*bDelay*<br/>
【인】 TRUE인 경우 도킹 레이아웃의 재계산이 지연됩니다.

*bActivate*<br/>
【인】 TRUE이면 표시될 때 창이 활성화됩니다.

### <a name="remarks"></a>설명

이 메서드는 창을 표시하거나 숨깁니다. 이 메서드는 `ShowWindow` 관련 도킹 관리자에게 창의 가시성 변경 사항을 통보하기 때문에 이 메서드를 대신 사용합니다.

[CBasePane::IsVisible를](#isvisible) 사용하여 창의 현재 가시성을 확인합니다.

## <a name="cbasepanestretchpane"></a><a name="stretchpane"></a>CBasePane::스트레치파인

창을 가로 또는 세로로 확장합니다.

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>매개 변수

*nLength*<br/>
【인】 창을 늘릴 길이입니다.

*bVert*<br/>
【인】 TRUE인 경우 창을 세로로 늘입니다. FALSE인 경우 창을 가로로 늘입니다.

### <a name="return-value"></a>Return Value

늘어난 창의 크기입니다.

## <a name="cbasepaneundockpane"></a><a name="undockpane"></a>CBasePane::도킹 팬 해제

도크 사이트, 기본 슬라이더 또는 현재 도킹된 미니 프레임 창에서 창을 제거합니다.

```
virtual void UndockPane(BOOL bDelay=FALSE);
```

### <a name="parameters"></a>매개 변수

*bDelay*<br/>
TRUE이면 도킹 레이아웃이 즉시 다시 계산되지 않습니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 창 상태를 조작하거나 도킹 레이아웃에서 창을 제외합니다.

이 창을 계속 사용하려면 이 메서드를 호출하기 전에 [CBasePane::DockPane](#dockpane) 또는 [CBasePane::FloatPane를](#floatpane) 호출합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CPane](../../mfc/reference/cbasepane-class.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)
