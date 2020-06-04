---
title: CPaneFrameWnd 클래스
ms.date: 11/04/2016
f1_keywords:
- CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd::AddPane
- AFXPANEFRAMEWND/CPaneFrameWnd::AddRemovePaneFromGlobalList
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustPaneFrames
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcBorderSize
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcExpectedDockedRect
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeAttached
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeDockedToPane
- AFXPANEFRAMEWND/CPaneFrameWnd::CheckGripperVisibility
- AFXPANEFRAMEWND/CPaneFrameWnd::ConvertToTabbedDocument
- AFXPANEFRAMEWND/CPaneFrameWnd::Create
- AFXPANEFRAMEWND/CPaneFrameWnd::CreateEx
- AFXPANEFRAMEWND/CPaneFrameWnd::DockPane
- AFXPANEFRAMEWND/CPaneFrameWnd::FindFloatingPaneByID
- AFXPANEFRAMEWND/CPaneFrameWnd::FrameFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionHeight
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionText
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingMode
- AFXPANEFRAMEWND/CPaneFrameWnd::GetFirstVisiblePane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::GetParent
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPinState
- AFXPANEFRAMEWND/CPaneFrameWnd::GetRecentFloatingRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetVisiblePaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::HitTest
- AFXPANEFRAMEWND/CPaneFrameWnd::IsCaptured
- AFXPANEFRAMEWND/CPaneFrameWnd::IsDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollDown
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollUp
- AFXPANEFRAMEWND/CPaneFrameWnd::KillDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::LoadState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnBeforeDock
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDockToRecentPos
- AFXPANEFRAMEWND/CPaneFrameWnd::OnKillRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnMovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::OnPaneRecalcLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::OnSetRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnShowPane
- AFXPANEFRAMEWND/CPaneFrameWnd::PaneFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::Pin
- AFXPANEFRAMEWND/CPaneFrameWnd::RedrawAll
- AFXPANEFRAMEWND/CPaneFrameWnd::RemoveNonValidPanes
- AFXPANEFRAMEWND/CPaneFrameWnd::RemovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::ReplacePane
- AFXPANEFRAMEWND/CPaneFrameWnd::SaveState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetCaptionButtons
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::SetPreDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SizeToContent
- AFXPANEFRAMEWND/CPaneFrameWnd::StartTearOff
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentDockSiteInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentTabRelatedInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::OnCheckRollState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDrawBorder
- AFXPANEFRAMEWND/CPaneFrameWnd::m_bUseSaveBits
helpviewer_keywords:
- CPaneFrameWnd [MFC], AddPane
- CPaneFrameWnd [MFC], AddRemovePaneFromGlobalList
- CPaneFrameWnd [MFC], AdjustLayout
- CPaneFrameWnd [MFC], AdjustPaneFrames
- CPaneFrameWnd [MFC], CalcBorderSize
- CPaneFrameWnd [MFC], CalcExpectedDockedRect
- CPaneFrameWnd [MFC], CanBeAttached
- CPaneFrameWnd [MFC], CanBeDockedToPane
- CPaneFrameWnd [MFC], CheckGripperVisibility
- CPaneFrameWnd [MFC], ConvertToTabbedDocument
- CPaneFrameWnd [MFC], Create
- CPaneFrameWnd [MFC], CreateEx
- CPaneFrameWnd [MFC], DockPane
- CPaneFrameWnd [MFC], FindFloatingPaneByID
- CPaneFrameWnd [MFC], FrameFromPoint
- CPaneFrameWnd [MFC], GetCaptionHeight
- CPaneFrameWnd [MFC], GetCaptionRect
- CPaneFrameWnd [MFC], GetCaptionText
- CPaneFrameWnd [MFC], GetDockingManager
- CPaneFrameWnd [MFC], GetDockingMode
- CPaneFrameWnd [MFC], GetFirstVisiblePane
- CPaneFrameWnd [MFC], GetHotPoint
- CPaneFrameWnd [MFC], GetPane
- CPaneFrameWnd [MFC], GetPaneCount
- CPaneFrameWnd [MFC], GetParent
- CPaneFrameWnd [MFC], GetPinState
- CPaneFrameWnd [MFC], GetRecentFloatingRect
- CPaneFrameWnd [MFC], GetVisiblePaneCount
- CPaneFrameWnd [MFC], HitTest
- CPaneFrameWnd [MFC], IsCaptured
- CPaneFrameWnd [MFC], IsDelayShow
- CPaneFrameWnd [MFC], IsRollDown
- CPaneFrameWnd [MFC], IsRollUp
- CPaneFrameWnd [MFC], KillDockingTimer
- CPaneFrameWnd [MFC], LoadState
- CPaneFrameWnd [MFC], OnBeforeDock
- CPaneFrameWnd [MFC], OnDockToRecentPos
- CPaneFrameWnd [MFC], OnKillRollUpTimer
- CPaneFrameWnd [MFC], OnMovePane
- CPaneFrameWnd [MFC], OnPaneRecalcLayout
- CPaneFrameWnd [MFC], OnSetRollUpTimer
- CPaneFrameWnd [MFC], OnShowPane
- CPaneFrameWnd [MFC], PaneFromPoint
- CPaneFrameWnd [MFC], Pin
- CPaneFrameWnd [MFC], RedrawAll
- CPaneFrameWnd [MFC], RemoveNonValidPanes
- CPaneFrameWnd [MFC], RemovePane
- CPaneFrameWnd [MFC], ReplacePane
- CPaneFrameWnd [MFC], SaveState
- CPaneFrameWnd [MFC], SetCaptionButtons
- CPaneFrameWnd [MFC], SetDelayShow
- CPaneFrameWnd [MFC], SetDockingManager
- CPaneFrameWnd [MFC], SetDockingTimer
- CPaneFrameWnd [MFC], SetDockState
- CPaneFrameWnd [MFC], SetHotPoint
- CPaneFrameWnd [MFC], SetPreDockState
- CPaneFrameWnd [MFC], SizeToContent
- CPaneFrameWnd [MFC], StartTearOff
- CPaneFrameWnd [MFC], StoreRecentDockSiteInfo
- CPaneFrameWnd [MFC], StoreRecentTabRelatedInfo
- CPaneFrameWnd [MFC], OnCheckRollState
- CPaneFrameWnd [MFC], OnDrawBorder
- CPaneFrameWnd [MFC], m_bUseSaveBits
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
ms.openlocfilehash: 76f7c5c2c21f0e823545db3669ce454c8172317c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753614"
---
# <a name="cpaneframewnd-class"></a>CPaneFrameWnd 클래스

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

하나의 창이 포함된 미니 프레임 창을 구현합니다. 창은 창의 클라이언트 영역을 채웁니다.

## <a name="syntax"></a>구문

```
class CPaneFrameWnd : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CPaneFrameWnd::AddPane](#addpane)|창을 추가합니다.|
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](#addremovepanefromgloballist)|전역 목록에서 창을 추가하거나 제거합니다.|
|[CPaneFrameWnd::AdjustLayout](#adjustlayout)|미니 프레임 창의 레이아웃을 조정합니다.|
|[CPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)||
|[CPaneFrameWnd::CalcBorderSize](#calcbordersize)|미니 프레임 창의 테두리 크기를 계산합니다.|
|[CPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|도킹된 창의 예상 사각형을 계산합니다.|
|[CPaneFrameWnd::CanBeAttached](#canbeattached)|현재 창을 다른 창이나 프레임 창에 도킹할 수 있는지 여부를 결정합니다.|
|[CPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|미니 프레임 창을 창에 도킹할 수 있는지 여부를 결정합니다.|
|[CPaneFrameWnd::CheckGripperVisibility](#checkgrippervisibility)||
|[CPaneFrameWnd::ConvertToTabbedDocument](#converttotabbeddocument)|창을 탭된 문서로 변환합니다.|
|[CPaneFrameWnd::Create](#create)|미니 프레임 창을 만들고 `CPaneFrameWnd` 개체에 연결합니다.|
|[CPaneFrameWnd::CreateEx](#createex)|미니 프레임 창을 만들고 `CPaneFrameWnd` 개체에 연결합니다.|
|[CPaneFrameWnd::DockPane](#dockpane)|창을 도킹합니다.|
|[CPaneFrameWnd::FindFloatingPaneByID](#findfloatingpanebyid)|부동 창의 전역 목록에서 지정된 컨트롤 ID를 가진 창을 찾습니다.|
|[CPaneFrameWnd::FrameFromPoint](#framefrompoint)|사용자가 제공한 지점을 포함하는 미니 프레임 창을 찾습니다.|
|[CPaneFrameWnd::GetCaptionHeight](#getcaptionheight)|미니 프레임 창 캡션의 높이를 반환합니다.|
|[CPaneFrameWnd::GetCaptionRect](#getcaptionrect)|미니 프레임 창 캡션의 경계 사각형을 계산합니다.|
|[CPaneFrameWnd::GetCaptionText](#getcaptiontext)|캡션 텍스트를 반환합니다.|
|[CPaneFrameWnd::GetDockingManager](#getdockingmanager)||
|[CPaneFrameWnd::GetDockingMode](#getdockingmode)|도킹 모드를 반환합니다.|
|[CPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|미니 프레임 창에 포함된 첫 번째 표시 창을 반환합니다.|
|[CPaneFrameWnd::GetHotPoint](#gethotpoint)||
|[CPaneFrameWnd::GetPane](#getpane)|미니 프레임 창에 포함된 창을 반환합니다.|
|[CPaneFrameWnd::GetPaneCount](#getpanecount)|미니 프레임 창에 포함된 창 수를 반환합니다.|
|[CPaneFrameWnd::GetParent](#getparent)||
|[CPaneFrameWnd::GetPinState](#getpinstate)||
|[CPaneFrameWnd::GetRecentFloatingRect](#getrecentfloatingrect)||
|[CPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|미니 프레임 창에 포함된 표시 창 수를 반환합니다.|
|[CPaneFrameWnd::HitTest](#hittest)|미니 프레임 창의 어떤 부분이 지정된 지점에 있는지 결정합니다.|
|[CPaneFrameWnd::IsCaptured](#iscaptured)||
|[CPaneFrameWnd::IsDelayShow](#isdelayshow)||
|[CPaneFrameWnd::IsRollDown](#isrolldown)|미니 프레임 창이 롤다운되어야 하는지 여부를 결정합니다.|
|[CPaneFrameWnd::IsRollUp](#isrollup)|미니 프레임 창이 롤업되어야 하는지 여부를 결정합니다.|
|[CPaneFrameWnd::KillDockingTimer](#killdockingtimer)|도킹 타이머를 중지합니다.|
|[CPaneFrameWnd::LoadState](#loadstate)|레지스트리에서 창의 상태를 로드합니다.|
|[CPaneFrameWnd::OnBeforeDock](#onbeforedock)|도킹 가능한지 여부를 결정합니다.|
|[CPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|가장 최근 위치에 미니 프레임 창을 도킹합니다.|
|[CPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|롤업 타이머를 중지합니다.|
|[CPaneFrameWnd::OnMovePane](#onmovepane)|지정된 오프셋만큼 미니 프레임 창을 이동합니다.|
|[CPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|포함된 창의 레이아웃을 조정합니다.|
|[CPaneFrameWnd::OnSetRollUpTimer](#onsetrolluptimer)|롤업 타이머를 설정합니다.|
|[CPaneFrameWnd::OnShowPane](#onshowpane)|미니 프레임 창의 창이 숨겨지거나 표시될 때 프레임워크에서 호출됩니다.|
|[CPaneFrameWnd::PaneFromPoint](#panefrompoint)|미니 프레임 창 안에 사용자가 제공한 지점을 포함하는 경우 창을 반환합니다.|
|[CPaneFrameWnd::Pin](#pin)||
|`CPaneFrameWnd::PreTranslateMessage`|창 메시지가 [TranslateMessage](../../mfc/reference/cwinapp-class.md) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) Windows 함수로 디스패치되기 전에 [CWinApp](/windows/win32/api/winuser/nf-winuser-dispatchmessage) 클래스가 이 메시지를 해석하는 데 사용됩니다.|
|[CPaneFrameWnd::RedrawAll](#redrawall)|모든 미니 프레임 창을 다시 그립니다.|
|[CPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|잘못된 창을 제거하기 위해 프레임워크에서 호출됩니다.|
|[CPaneFrameWnd::RemovePane](#removepane)|미니 프레임 창에서 창을 제거합니다.|
|[CPaneFrameWnd::ReplacePane](#replacepane)|한 창을 다른 창으로 대체합니다.|
|[CPaneFrameWnd::SaveState](#savestate)|레지스트리에 창의 상태를 저장합니다.|
|`CPaneFrameWnd::Serialize`|이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다.|
|[CPaneFrameWnd::SetCaptionButtons](#setcaptionbuttons)|캡션 단추를 설정합니다.|
|[CPaneFrameWnd::SetDelayShow](#setdelayshow)||
|[CPaneFrameWnd::SetDockingManager](#setdockingmanager)||
|[CPaneFrameWnd::SetDockingTimer](#setdockingtimer)|도킹 타이머를 설정합니다.|
|[CPaneFrameWnd::SetDockState](#setdockstate)|도킹 상태를 설정합니다.|
|[CPaneFrameWnd::SetHotPoint](#sethotpoint)||
|[CPaneFrameWnd::SetPreDockState](#setpredockstate)|사전 도킹 상태를 설정하기 위해 프레임워크에서 호출됩니다.|
|[CPaneFrameWnd::SizeToContent](#sizetocontent)|포함된 창과 크기가 같도록 미니 프레임 창의 크기를 조정합니다.|
|[CPaneFrameWnd::StartTearOff](#starttearoff)|메뉴를 분리합니다.|
|[CPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CPaneFrameWnd::OnCheckRollState](#oncheckrollstate)|미니 프레임 창이 롤업 또는 롤다운되어야 하는지를 결정합니다.|
|[CPaneFrameWnd::OnDrawBorder](#ondrawborder)|미니 프레임 창의 테두리를 그립니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|CS_SAVEBITS 클래스 스타일로 창 클래스를 등록할지 여부를 지정합니다.|

## <a name="remarks"></a>설명

창이 도킹된 상태에서 부동 상태로 전환되면 프레임워크에서 자동으로 `CPaneFrameWnd` 개체를 만듭니다.

내용을 표시(즉시 도킹)하거나 끌기 사각형을 사용하여(표준 도킹) 미니 프레임 창을 끌 수 있습니다. 미니 프레임 컨테이너 창의 도킹 모드에 따라 미니 프레임의 끌기 동작이 결정됩니다. 자세한 내용은 [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode)을 참조하십시오.

미니 프레임 창에 포함된 창 스타일에 따라 캡션에 단추가 표시됩니다. 창을 닫을 수 있는 경우 [(CBasePane::CanBeClosed)](../../mfc/reference/cbasepane-class.md#canbeclosed)닫기 단추를 표시 합니다. 창에 AFX_CBRS_AUTO_ROLLUP 스타일이 있으면 핀이 표시됩니다.

`CPaneFrameWnd`에서 클래스를 파생하는 경우 프레임워크에 만드는 방법을 알려야 합니다. [CPane::CreateDefaultMiniframe을](../../mfc/reference/cpane-class.md#createdefaultminiframe)재정의하여 클래스를 만들거나 `CPane::m_pMiniFrameRTC` 클래스의 런타임 클래스 정보를 가리키도록 멤버를 설정합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPaneFrameWnd`

## <a name="requirements"></a>요구 사항

**헤더:** afxPaneFramewnd.h

## <a name="cpaneframewndaddpane"></a><a name="addpane"></a>CPaneFrameWnd::애드파인

창을 추가합니다.

```
virtual void AddPane(CBasePane* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 추가할 창입니다.

## <a name="cpaneframewndaddremovepanefromgloballist"></a><a name="addremovepanefromgloballist"></a>CPaneFrameWnd::AddRemovePaneFrom글로벌리스트

전역 목록에서 창을 추가하거나 제거합니다.

```
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,
    BOOL bAdd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 추가하거나 제거할 창입니다.

*bAdd*<br/>
【인】 0이 아닌 경우 창을 추가합니다. 0이면 창을 제거합니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="cpaneframewndadjustlayout"></a><a name="adjustlayout"></a>CPaneFrameWnd::조정레이아웃

미니 프레임 창의 레이아웃을 조정합니다.

```
virtual void AdjustLayout();
```

## <a name="cpaneframewndadjustpaneframes"></a><a name="adjustpaneframes"></a>CPaneFrameWnd::adjustPaneFrames

```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>설명

## <a name="cpaneframewndcalcbordersize"></a><a name="calcbordersize"></a>CPaneFrameWnd::CalcBorderSize

미니프레임 창의 테두리 크기를 계산합니다.

```
virtual void CalcBorderSize(CRect& rectBorderSize) const;
```

### <a name="parameters"></a>매개 변수

*직사각형 테두리크기*<br/>
【아웃】 미니프레임 창의 테두리의 크기(픽셀 단위)를 포함합니다.

### <a name="remarks"></a>설명

이 메서드는 프레임 워크에서 호출되어 미니프레임 창의 테두리 크기를 계산합니다. 반환된 크기는 미니프레임 창에 도구 모음또는 [CDockablePane이](../../mfc/reference/cdockablepane-class.md)포함되어 있는지 여부에 따라 달라집니다.

## <a name="cpaneframewndcalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CPaneFrameWnd::칼크예상도크렉트

도킹된 창의 예상 사각형을 계산합니다.

```
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>매개 변수

*pWndToDock*<br/>
【인】 도킹할 창에 대한 포인터입니다.

*pt마우스*<br/>
【인】 마우스 위치입니다.

*정류 결과*<br/>
【아웃】 계산된 사각형입니다.

*b그리기 탭*<br/>
【아웃】 TRUE인 경우 탭을 그립니다. FALSE인 경우 탭을 그리지 마십시오.

*ppTargetBar*<br/>
【아웃】 대상 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 사용자가 *ptMouse에* 의해 지정 된 지점으로 창을 드래그 하 고 거기 도킹 하는 경우 창이 차지 하는 사각형을 계산 합니다.

## <a name="cpaneframewndcanbeattached"></a><a name="canbeattached"></a>CPaneFrameWnd::수 있습니다연결

현재 창을 다른 창이나 프레임 창에 도킹할 수 있는지 여부를 결정합니다.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Return Value

TRUE 창을 다른 창 또는 프레임 창에 도킹할 수 있는 경우 그렇지 않으면 거짓.

## <a name="cpaneframewndcanbedockedtopane"></a><a name="canbedockedtopane"></a>CPaneFrameWnd::캔베독토파네

미니 프레임 창을 창에 도킹할 수 있는지 여부를 결정합니다.

```
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;
```

### <a name="parameters"></a>매개 변수

*pDockingBar*<br/>
【인】 창입니다.

### <a name="return-value"></a>Return Value

미니 프레임을 *pDockingBar에*도킹할 수 있는 경우 비영체; 그렇지 않으면 0.

## <a name="cpaneframewndcheckgrippervisibility"></a><a name="checkgrippervisibility"></a>CPaneFrameWnd::체크그리퍼 가시성

```
virtual void CheckGripperVisibility();
```

### <a name="remarks"></a>설명

## <a name="cpaneframewndconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>CPaneFrameWnd::변환토탭문서

창을 탭된 문서로 변환합니다.

```
virtual void ConvertToTabbedDocument();
```

## <a name="cpaneframewndcreate"></a><a name="create"></a>CPaneFrameWnd::만들기

미니프레임 창을 만들고 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) 개체에 연결합니다.

```
virtual BOOL Create(
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszWindowName*<br/>
【인】 미니프레임 창에 표시할 텍스트를 지정합니다.

*dwStyle*<br/>
【인】 창 스타일을 지정합니다. 자세한 내용은 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)을 참조하십시오.

*rect*<br/>
【인】 미니프레임 창의 초기 크기와 위치를 지정합니다.

*pParentWnd*<br/>
【인, 아웃】 미니프레임 창의 상위 프레임을 지정합니다. 이 값은 NULL이 아니어야 합니다.

*pContext*<br/>
【인, 아웃】 사용자 정의 컨텍스트를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 창이 성공적으로 생성된 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

미니프레임 창은 두 단계로 작성됩니다. 먼저 프레임워크는 개체를 `CPaneFrameWnd` 만듭니다. 둘째, Windows `Create` 미니프레임 창을 만들어 `CPaneFrameWnd` 개체에 연결합니다.

## <a name="cpaneframewndcreateex"></a><a name="createex"></a>CPaneFrameWnd::만들기

미니프레임 창을 만들고 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) 개체에 연결합니다.

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>매개 변수

*dwStyleEx*<br/>
【인】 확장 창 스타일을 지정합니다. 자세한 내용은 [확장 창 스타일을](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) 참조하십시오.

*lpszWindowName*<br/>
【인】 미니프레임 창에 표시할 텍스트를 지정합니다.

*dwStyle*<br/>
【인】 창 스타일을 지정합니다. 자세한 내용은 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)을 참조하십시오.

*rect*<br/>
【인】 미니프레임 창의 초기 크기와 위치를 지정합니다.

*pParentWnd*<br/>
【인, 아웃】 미니프레임 창의 상위 프레임을 지정합니다. 이 값은 NULL이 아니어야 합니다.

*pContext*<br/>
【인, 아웃】 사용자 정의 컨텍스트를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 창이 성공적으로 생성된 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

미니프레임 창은 두 단계로 작성됩니다. 먼저 프레임워크는 개체를 `CPaneFrameWnd` 만듭니다. 둘째, Windows `Create` 미니프레임 창을 만들어 `CPaneFrameWnd` 개체에 연결합니다.

## <a name="cpaneframewnddockpane"></a><a name="dockpane"></a>CPaneFrameWnd::D오크파인

창을 도킹합니다.

```
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```

### <a name="parameters"></a>매개 변수

*b와도킹*<br/>
【아웃】 창이 이미 도킹된 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="return-value"></a>Return Value

작업이 성공하면 `CDockablePane` 창이 도킹된 것입니다. 그렇지 않으면 NULL.

## <a name="cpaneframewndfindfloatingpanebyid"></a><a name="findfloatingpanebyid"></a>CPaneFrameWnd::찾기 플로팅파네비ID

부동 창의 전역 목록에서 지정된 컨트롤 ID를 가진 창을 찾습니다.

```
static CBasePane* FindFloatingPaneByID(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 찾을 창의 제어 ID를 나타냅니다.

### <a name="return-value"></a>Return Value

지정된 컨트롤 ID가 있는 창입니다. 그렇지 않으면 NULL(지정된 컨트롤 ID가 없는 창이 없는 경우).

## <a name="cpaneframewndframefrompoint"></a><a name="framefrompoint"></a>CPaneFrameWnd::프레임From포인트

지정된 점을 포함하는 미니 프레임 창을 찾습니다.

```
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,
    int nSensitivity,
    CPaneFrameWnd* pFrameToExclude = NULL,
    BOOL bFloatMultiOnly = FALSE);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
【인】 화면 좌표의 점입니다.

*n감도*<br/>
【인】 이 크기로 미니 프레임 창의 검색 영역을 늘립니다. 지정된 지점이 증가된 영역에 속하는 경우 미니 프레임 창은 검색 기준을 충족합니다.

*pFrame제외*<br/>
【인】 검색에서 제외할 미니 프레임 창을 지정합니다.

*bFloatMulti전용*<br/>
【인】 TRUE인 경우 CBRS_FLOAT_MULTI 스타일이 있는 미니 프레임 창만 검색합니다. FALSE인 경우 모든 미니 프레임 창을 검색합니다.

### <a name="return-value"></a>Return Value

*PT를*포함하는 미니 프레임 창에 대한 포인터입니다. 그렇지 않으면 NULL.

## <a name="cpaneframewndgetcaptionheight"></a><a name="getcaptionheight"></a>CPaneFrameWnd::GetCaptionHeight

미니 프레임 창 캡션의 높이를 반환합니다.

```
virtual int GetCaptionHeight() const;
```

### <a name="return-value"></a>Return Value

미니 프레임 창의 높이(픽셀 단위)입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 미니 프레임 창의 높이를 확인합니다. 기본적으로 높이는 SM_CYSMCAPTION 설정됩니다. 자세한 내용은 [GetSystemMetrics 함수를](/windows/win32/api/winuser/nf-winuser-getsystemmetrics)참조하십시오.

## <a name="cpaneframewndgetcaptionrect"></a><a name="getcaptionrect"></a>CPaneFrameWnd::GetCaptionRect

미니 프레임 창 캡션의 경계 사각형을 계산합니다.

```
virtual void GetCaptionRect(CRect& rectCaption) const;
```

### <a name="parameters"></a>매개 변수

*정류 캡션*<br/>
【아웃】 화면 좌표에 미니 프레임 창 캡션의 크기와 위치가 포함됩니다.

### <a name="remarks"></a>설명

이 메서드는 미니 프레임 창 캡션의 경계 사각형을 계산 하기 위해 프레임 워크에서 호출 됩니다.

## <a name="cpaneframewndgetcaptiontext"></a><a name="getcaptiontext"></a>CPaneFrameWnd::GetCaptionText

캡션 텍스트를 반환합니다.

```
virtual CString GetCaptionText();
```

### <a name="return-value"></a>Return Value

미니 프레임 창의 캡션 텍스트입니다.

### <a name="remarks"></a>설명

이 메서드는 캡션 텍스트를 표시할 때 프레임워크에서 호출됩니다.

## <a name="cpaneframewndgetdockingmanager"></a><a name="getdockingmanager"></a>CPaneFrameWnd::GetDockingManager

```
CDockingManager* GetDockingManager() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpaneframewndgetdockingmode"></a><a name="getdockingmode"></a>CPaneFrameWnd::GetDocking모드

도킹 모드를 반환합니다.

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>Return Value

도킹 모드입니다. 해당 값은

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

## <a name="cpaneframewndgetfirstvisiblepane"></a><a name="getfirstvisiblepane"></a>CPaneFrameWnd::GetFirstVisiblePane

미니 프레임 창에 포함된 첫 번째 표시 창을 반환합니다.

```
virtual CWnd* GetFirstVisiblePane() const;
```

### <a name="return-value"></a>Return Value

미니 프레임 창의 첫 번째 창 또는 미니 프레임 창에 창이 없는 경우 NULL입니다.

## <a name="cpaneframewndgethotpoint"></a><a name="gethotpoint"></a>CPaneFrameWnd::GetHotPoint

```
CPoint GetHotPoint() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpaneframewndgetpane"></a><a name="getpane"></a>CPaneFrameWnd::GetPane

미니 프레임 창에 포함된 창을 반환합니다.

```
virtual CWnd* GetPane() const;
```

### <a name="return-value"></a>Return Value

미니 프레임 창에 창이 없는 경우 미니 프레임 또는 NULL에 포함된 창입니다.

### <a name="remarks"></a>설명

## <a name="cpaneframewndgetpanecount"></a><a name="getpanecount"></a>CPaneFrameWnd:::겟파인카운트

미니 프레임 창에 포함된 창 수를 반환합니다.

```
virtual int GetPaneCount() const;
```

### <a name="return-value"></a>Return Value

미니 프레임 창의 창 수입니다. 이 값은 0일 수 있습니다.

### <a name="remarks"></a>설명

## <a name="cpaneframewndgetparent"></a><a name="getparent"></a>CPaneFrameWnd::GetParent

```
CWnd* GetParent();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpaneframewndgetpinstate"></a><a name="getpinstate"></a>CPaneFrameWnd::겟핀스테이트

```
BOOL GetPinState() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpaneframewndgetrecentfloatingrect"></a><a name="getrecentfloatingrect"></a>CPaneFrameWnd::Get최근 떠다니는 렉트

```
CRect GetRecentFloatingRect() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpaneframewndgetvisiblepanecount"></a><a name="getvisiblepanecount"></a>CPaneFrameWnd::GetVisiblePaneCount

미니 프레임 창에 포함된 표시 창 수를 반환합니다.

```
virtual int GetVisiblePaneCount() const;
```

### <a name="return-value"></a>Return Value

표시되는 창의 수입니다.

### <a name="remarks"></a>설명

## <a name="cpaneframewndhittest"></a><a name="hittest"></a>CPaneFrameWnd::히트 테스트

미니 프레임 창의 어떤 부분이 지정된 지점에 있는지 결정합니다.

```
virtual LRESULT HitTest(
    CPoint point,
    BOOL bDetectCaption);
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
[in] 테스트할 지점입니다.

*bDetect캡션*<br/>
【인】 TRUE인 경우 캡션과 대개 점을 확인합니다. FALSE인 경우 캡션을 무시합니다.

### <a name="return-value"></a>Return Value

해당 값은

|값|의미|
|-----------|-------------|
|HTNOWHERE|포인트는 미니 프레임 창 밖에 있습니다.|
|HT클라이언트|요점은 클라이언트 영역에 있습니다.|
|HT캡션|요점은 캡션에 있습니다.|
|HTTOP|포인트는 맨 위에 있습니다.|
|HTTOPLEFT|점은 왼쪽 상단에 있습니다.|
|HTTOPRIGHT|점은 오른쪽 상단에 있습니다.|
|HTLEFT|점은 왼쪽에 있습니다.|
|HTRIGHT|요점은 오른쪽에 있습니다.|
|HT 바텀|점은 하단에 있습니다.|
|HTBOTTOMLEFT|점은 왼쪽 하단에 있습니다.|
|HTBOTTOMRIGHT|점은 오른쪽 하단에 있습니다.|

## <a name="cpaneframewndiscaptured"></a><a name="iscaptured"></a>CPaneFrameWnd::캡처

```
BOOL IsCaptured() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpaneframewndisdelayshow"></a><a name="isdelayshow"></a>CPaneFrameWnd::IsDelayShow

```
BOOL IsDelayShow() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpaneframewndisrolldown"></a><a name="isrolldown"></a>CPaneFrameWnd::이스롤다운

미니 프레임 창이 롤다운되어야 하는지 여부를 결정합니다.

```
virtual BOOL IsRollDown() const;
```

### <a name="return-value"></a>Return Value

미니 프레임 창을 롤다운해야 하는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 프레임 워크에서 호출 되어 미니 프레임 창을 롤다운 해야 하는지 여부를 결정 합니다. AFX_CBRS_AUTO_ROLLUP 플래그가 있는 창이 하나 이상 있는 경우 미니 프레임 창에 롤업/롤다운 기능이 활성화됩니다. 이 플래그는 창을 만들 때 설정됩니다. 자세한 내용은 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)를 참조하십시오.

기본적으로 프레임워크는 마우스 포인터가 미니 프레임 창 경계 사각형 내에 있는지 여부를 확인하여 창을 롤다운해야 하는지 여부를 확인합니다. 파생 클래스에서 이 동작을 재정의할 수 있습니다.

## <a name="cpaneframewndisrollup"></a><a name="isrollup"></a>CPaneFrameWnd::이스롤업

미니 프레임 창이 롤업되어야 하는지 여부를 결정합니다.

```
virtual BOOL IsRollUp() const;
```

### <a name="return-value"></a>Return Value

미니 프레임 창을 롤업해야 하는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 프레임 워크에서 호출 되어 미니 프레임 창을 롤업 해야 하는지 여부를 결정 합니다. AFX_CBRS_AUTO_ROLLUP 플래그가 있는 창이 하나 이상 있는 경우 미니 프레임 창에 롤업/롤다운 기능이 활성화됩니다. 이 플래그는 창을 만들 때 설정됩니다. 자세한 내용은 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)를 참조하십시오.

기본적으로 프레임워크는 마우스 포인터가 미니 프레임 창 경계 사각형 내에 있는지 여부를 확인하여 창을 롤업해야 하는지 여부를 확인합니다. 파생 클래스에서 이 동작을 재정의할 수 있습니다.

## <a name="cpaneframewndkilldockingtimer"></a><a name="killdockingtimer"></a>CPaneFrameWnd::킬독 타이머

도킹 타이머를 중지합니다.

```cpp
void KillDockingTimer();
```

## <a name="cpaneframewndloadstate"></a><a name="loadstate"></a>CPaneFrameWnd::로드스테이트

레지스트리에서 창의 상태를 로드합니다.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 프로필 이름입니다.

*uiID*<br/>
【인】 창 ID입니다.

### <a name="return-value"></a>Return Value

TRUE 창 상태가 성공적으로 로드된 경우 그렇지 않으면 거짓.

## <a name="cpaneframewndm_busesavebits"></a><a name="m_busesavebits"></a>CPaneFrameWnd::m_bUseSaveBits

CS_SAVEBITS 클래스 스타일이 있는 창 클래스를 등록할지 여부를 지정합니다.

```
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;
```

### <a name="remarks"></a>설명

이 정적 멤버를 TRUE로 설정하여 CS_SAVEBITS 스타일이 있는 미니 프레임 창 클래스를 등록합니다. 이렇게 하면 사용자가 미니 프레임 창을 끌 때 깜박임을 줄일 수 있습니다.

## <a name="cpaneframewndonbeforedock"></a><a name="onbeforedock"></a>CPaneFrameWnd::OnBeforeDock

도킹 가능한지 여부를 결정합니다.

```
virtual BOOL OnBeforeDock();
```

### <a name="return-value"></a>Return Value

도킹이 가능한 경우 TRUE; 그렇지 않으면 false입니다.

## <a name="cpaneframewndoncheckrollstate"></a><a name="oncheckrollstate"></a>CPaneFrameWnd::OnCheckRollState

미니 프레임 창이 롤업 또는 롤다운되어야 하는지를 결정합니다.

```
virtual void OnCheckRollState();
```

### <a name="remarks"></a>설명

이 메서드는 프레임 워크에서 호출되어 미니 프레임 창을 롤업또는 아래로 롤업할지 여부를 결정합니다.

기본적으로 프레임워크는 [CPaneFrameWnd::IsRollUp](#isrollup) 및 [CPaneFrameWnd::IsRollDown을](#isrolldown) 호출하고 미니 프레임 창을 늘리거나 복원합니다. 파생 클래스에서 이 메서드를 재정의하여 다른 시각적 효과를 사용할 수 있습니다.

## <a name="cpaneframewndondocktorecentpos"></a><a name="ondocktorecentpos"></a>CPaneFrameWnd::OnDockToRecentpos

가장 최근 위치에 미니 프레임 창을 도킹합니다.

```
virtual void OnDockToRecentPos();
```

## <a name="cpaneframewndondrawborder"></a><a name="ondrawborder"></a>CPaneFrameWnd::온드로우 보더

미니 프레임 창의 테두리를 그립니다.

```
virtual void OnDrawBorder(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 테두리를 그리는 데 사용되는 장치 컨텍스트입니다.

### <a name="remarks"></a>설명

이 메서드는 프레임 워크에서 미니 프레임 창의 테두리를 그리는 호출 됩니다.

## <a name="cpaneframewndonkillrolluptimer"></a><a name="onkillrolluptimer"></a>CPaneFrameWnd::온킬롤업타이머

롤업 타이머를 중지합니다.

```
virtual void OnKillRollUpTimer();
```

## <a name="cpaneframewndonmovepane"></a><a name="onmovepane"></a>CPaneFrameWnd::온무브파인

지정된 오프셋만큼 미니 프레임 창을 이동합니다.

```
virtual void OnMovePane(
    CPane* pBar,
    CPoint ptOffset);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 창에 대한 포인터(무시됨).

*ptOffset*<br/>
【인】 창을 이동할 오프셋입니다.

## <a name="cpaneframewndonpanerecalclayout"></a><a name="onpanerecalclayout"></a>CPaneFrameWnd::온파네리칼레이아웃

미니 프레임 창 내부의 창 레이아웃을 조정합니다.

```
virtual void OnPaneRecalcLayout();
```

### <a name="remarks"></a>설명

프레임워크는 미니 프레임 창 내부의 창 레이아웃을 조정해야 하는 경우 이 메서드를 호출합니다.

기본적으로 창은 미니 프레임 창의 전체 클라이언트 영역을 덮도록 배치됩니다.

## <a name="cpaneframewndonsetrolluptimer"></a><a name="onsetrolluptimer"></a>CPaneFrameWnd::온셋롤업타이머

롤업 타이머를 설정합니다.

```
virtual void OnSetRollUpTimer();
```

## <a name="cpaneframewndonshowpane"></a><a name="onshowpane"></a>CPaneFrameWnd::OnShowPane

미니 프레임 창의 창이 숨겨지거나 표시될 때 프레임워크에서 호출됩니다.

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 표시되거나 숨겨지는 창입니다.

*bShow*<br/>
【인】 창이 표시되는 경우 TRUE입니다. 창이 숨겨져 있는 경우 FALSE입니다.

### <a name="remarks"></a>설명

미니 프레임 창의 창이 표시되거나 숨겨지면 프레임워크에서 호출됩니다. 기본 구현은 아무 작업도 수행하지 않습니다.

## <a name="cpaneframewndpin"></a><a name="pin"></a>CPaneFrameWnd::P

```cpp
void Pin(BOOL bPin = TRUE);
```

### <a name="parameters"></a>매개 변수

【인】 *b핀 (것)들*<br/>

### <a name="remarks"></a>설명

## <a name="cpaneframewndpanefrompoint"></a><a name="panefrompoint"></a>CPaneFrameWnd::P인FromPoint

미니 프레임 창 안에 사용자가 제공한 지점을 포함하는 경우 창을 반환합니다.

```
virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    BOOL bCheckVisibility);
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
【인】 사용자가 화면 좌표에서 클릭한 점입니다.

*n감도*<br/>
【인】 이 매개 변수는 사용되지 않습니다.

*b체크가시성*<br/>
【인】 TRUE는 보이는 창만 반환하도록 지정합니다. 그렇지 않으면 false입니다.

### <a name="return-value"></a>Return Value

사용자가 클릭한 창 또는 해당 위치에 창이 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

지정된 점을 포함하는 창을 얻으려면 이 메서드를 호출합니다.

## <a name="cpaneframewndredrawall"></a><a name="redrawall"></a>CPaneFrameWnd::다시 그리기 모두

모든 미니 프레임 창을 다시 그립니다.

```
static void RedrawAll();
```

### <a name="remarks"></a>설명

이 메서드는 각 창에 대해 [CWnd::RedrawWindow를](../../mfc/reference/cwnd-class.md#redrawwindow) 호출하여 모든 미니 프레임 창을 업데이트합니다.

## <a name="cpaneframewndremovenonvalidpanes"></a><a name="removenonvalidpanes"></a>CPaneFrameWnd::제거비유효파인

잘못된 창을 제거하기 위해 프레임워크에서 호출됩니다.

```
virtual void RemoveNonValidPanes();
```

## <a name="cpaneframewndremovepane"></a><a name="removepane"></a>CPaneFrameWnd::제거창

미니 프레임 창에서 창을 제거합니다.

```
virtual void RemovePane(
    CBasePane* pWnd,
    BOOL bDestroy = FALSE,
    BOOL bNoDelayedDestroy = FALSE);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 제거할 창에 대한 포인터입니다.

*bDestroy*<br/>
【인】 미니 프레임 창에 어떤 일이 발생하는지 지정합니다. *bDestroyTRUE이면* 이 메서드는 미니 프레임 창을 즉시 파괴합니다. FALSE인 경우 이 메서드는 특정 지연 후 미니 프레임 창을 삭제합니다.

*b지연파괴*<br/>
【인】 TRUE인 경우 지연된 소멸이 비활성화됩니다. FALSE인 경우 지연된 소멸이 활성화됩니다.

### <a name="remarks"></a>설명

프레임워크는 즉시 또는 특정 지연 후 미니 프레임 창을 파괴할 수 있습니다. 미니 프레임 창의 소멸을 지연하려면 *bNoDelayedDestroy* 매개 변수에서 FALSE를 전달합니다. 프레임워크가 AFX_WM_CHECKEMPTYMINIFRAME 메시지를 처리할 때 지연된 소멸이 발생합니다.

## <a name="cpaneframewndreplacepane"></a><a name="replacepane"></a>CPaneFrameWnd::대체판

한 창을 다른 창으로 대체합니다.

```
virtual void ReplacePane(
    CBasePane* pBarOrg,
    CBasePane* pBarReplaceWith);
```

### <a name="parameters"></a>매개 변수

*pBarOrg*<br/>
【인】 원래 창에 대한 포인터입니다.

*pBarReplaceWith*<br/>
【인】 원래 창을 대체하는 창에 대한 포인터입니다.

## <a name="cpaneframewndsavestate"></a><a name="savestate"></a>CPaneFrameWnd::저장 상태

레지스트리에 창의 상태를 저장합니다.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 프로필 이름입니다.

*uiID*<br/>
【인】 창 ID입니다.

### <a name="return-value"></a>Return Value

창 상태가 성공적으로 저장된 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cpaneframewndsetcaptionbuttons"></a><a name="setcaptionbuttons"></a>CPaneFrameWnd::캡션 단추

캡션 단추를 설정합니다.

```
virtual void SetCaptionButtons(DWORD dwButtons);
```

### <a name="parameters"></a>매개 변수

*dwButtons*<br/>
【인】 비트-OR 다음 값의 조합:

- AFX_CAPTION_BTN_CLOSE

- AFX_CAPTION_BTN_PIN

- AFX_CAPTION_BTN_MENU

- AFX_CAPTION_BTN_CUSTOMIZE

## <a name="cpaneframewndsetdelayshow"></a><a name="setdelayshow"></a>CPaneFrameWnd::세트딜레이지쇼

```cpp
void SetDelayShow(BOOL bDelayShow);
```

### <a name="parameters"></a>매개 변수

【인】 *b지연쇼*<br/>

### <a name="remarks"></a>설명

## <a name="cpaneframewndsetdockingmanager"></a><a name="setdockingmanager"></a>CPaneFrameWnd::SetdockingManager

```cpp
void SetDockingManager(CDockingManager* pManager);
```

### <a name="parameters"></a>매개 변수

【인】 *pManager*<br/>

### <a name="remarks"></a>설명

## <a name="cpaneframewndsetdockingtimer"></a><a name="setdockingtimer"></a>CPaneFrameWnd::Setdocking타이머

도킹 타이머를 설정합니다.

```cpp
void SetDockingTimer(UINT nTimeOut);
```

### <a name="parameters"></a>매개 변수

*n시간 시간*<br/>
【인】 시간 시간(시간)(밀리초)입니다.

## <a name="cpaneframewndsetdockstate"></a><a name="setdockstate"></a>CPaneFrameWnd::SetDockState

도킹 상태를 설정합니다.

```
virtual void SetDockState(CDockingManager* pDockManager);
```

### <a name="parameters"></a>매개 변수

*pDockManager*<br/>
【인】 도킹 관리자에 대한 포인터입니다.

## <a name="cpaneframewndsethotpoint"></a><a name="sethotpoint"></a>CPaneFrameWnd::SetHotPoint

```cpp
void SetHotPoint(CPoint& ptNew);
```

### <a name="parameters"></a>매개 변수

【인】 *ptNew*<br/>

### <a name="remarks"></a>설명

## <a name="cpaneframewndsetpredockstate"></a><a name="setpredockstate"></a>CPaneFrameWnd::SetPreDockState

사전 도킹 상태를 설정하기 위해 프레임워크에서 호출됩니다.

```
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,
    CBasePane* pBarToDock = NULL,
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```

### <a name="parameters"></a>매개 변수

*프리독스테이트*<br/>
【인】 가능한 값:

- PDS_NOTHING,

- PDS_DOCK_REGULAR,

- PDS_DOCK_TO_TAB

*pBarToDock*<br/>
【인】 도킹할 창에 대한 포인터입니다.

*dockMethod*<br/>
【인】 도킹 방법입니다. (이 매개 변수는 무시됩니다.)

### <a name="return-value"></a>Return Value

미니 프레임 창이 도킹 해제된 경우 TRUE; 도킹된 경우 FALSE입니다.

## <a name="cpaneframewndsizetocontent"></a><a name="sizetocontent"></a>CPaneFrameWnd::크기토콘텐츠

포함된 창과 동일하도록 미니 프레임 창의 크기를 조정합니다.

```
virtual void SizeToContent();
```

### <a name="remarks"></a>설명

이 메서드를 호출하여 미니 프레임 창의 크기를 포함된 창의 크기로 조정합니다.

## <a name="cpaneframewndstarttearoff"></a><a name="starttearoff"></a>CPaneFrameWnd::시작티어오프

메뉴를 분리합니다.

```
BOOL StartTearOff(CMFCPopu* pMenu);
```

### <a name="parameters"></a>매개 변수

*p메뉴*<br/>
【인】 메뉴에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="cpaneframewndstorerecentdocksiteinfo"></a><a name="storerecentdocksiteinfo"></a>CPaneFrameWnd::최근독사이트정보

```
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

### <a name="remarks"></a>설명

## <a name="cpaneframewndstorerecenttabrelatedinfo"></a><a name="storerecenttabrelatedinfo"></a>CPaneFrameWnd::저장소최근탭관련정보

```
virtual void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,
    CDockablePane* pTabbedBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pDockingBar*<br/>
【인】 *pTabbedBar*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)
