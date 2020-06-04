---
title: CMultiPaneFramewnd 클래스
ms.date: 11/04/2016
f1_keywords:
- CMultiPaneFrameWnd
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::AddPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::AddRecentPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::AdjustLayout
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::AdjustPaneFrames
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::CalcExpectedDockedRect
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::CanBeAttached
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::CanBeDockedToPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::CheckGripperVisibility
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::CloseMiniFrame
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::ConvertToTabbedDocument
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::DockFrame
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::DockPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::DockRecentPaneToMainFrame
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::GetCaptionText
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::GetPaneContainerManager
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::GetFirstVisiblePane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::GetPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::GetPaneCount
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::GetVisiblePaneCount
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::InsertPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::LoadState
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::OnDockToRecentPos
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::OnKillRollUpTimer
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::OnPaneRecalcLayout
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::OnSetRollUpTimer
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::OnShowPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::PaneFromPoint
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::RemoveNonValidPanes
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::RemovePane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::ReplacePane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::SaveState
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::Serialize
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::SetDockState
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::SetLastFocusedPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::SetPreDockState
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::StoreRecentDockSiteInfo
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::StoreRecentTabRelatedInfo
helpviewer_keywords:
- CMultiPaneFrameWnd [MFC], AddPane
- CMultiPaneFrameWnd [MFC], AddRecentPane
- CMultiPaneFrameWnd [MFC], AdjustLayout
- CMultiPaneFrameWnd [MFC], AdjustPaneFrames
- CMultiPaneFrameWnd [MFC], CalcExpectedDockedRect
- CMultiPaneFrameWnd [MFC], CanBeAttached
- CMultiPaneFrameWnd [MFC], CanBeDockedToPane
- CMultiPaneFrameWnd [MFC], CheckGripperVisibility
- CMultiPaneFrameWnd [MFC], CloseMiniFrame
- CMultiPaneFrameWnd [MFC], ConvertToTabbedDocument
- CMultiPaneFrameWnd [MFC], DockFrame
- CMultiPaneFrameWnd [MFC], DockPane
- CMultiPaneFrameWnd [MFC], DockRecentPaneToMainFrame
- CMultiPaneFrameWnd [MFC], GetCaptionText
- CMultiPaneFrameWnd [MFC], GetPaneContainerManager
- CMultiPaneFrameWnd [MFC], GetFirstVisiblePane
- CMultiPaneFrameWnd [MFC], GetPane
- CMultiPaneFrameWnd [MFC], GetPaneCount
- CMultiPaneFrameWnd [MFC], GetVisiblePaneCount
- CMultiPaneFrameWnd [MFC], InsertPane
- CMultiPaneFrameWnd [MFC], LoadState
- CMultiPaneFrameWnd [MFC], OnDockToRecentPos
- CMultiPaneFrameWnd [MFC], OnKillRollUpTimer
- CMultiPaneFrameWnd [MFC], OnPaneRecalcLayout
- CMultiPaneFrameWnd [MFC], OnSetRollUpTimer
- CMultiPaneFrameWnd [MFC], OnShowPane
- CMultiPaneFrameWnd [MFC], PaneFromPoint
- CMultiPaneFrameWnd [MFC], RemoveNonValidPanes
- CMultiPaneFrameWnd [MFC], RemovePane
- CMultiPaneFrameWnd [MFC], ReplacePane
- CMultiPaneFrameWnd [MFC], SaveState
- CMultiPaneFrameWnd [MFC], Serialize
- CMultiPaneFrameWnd [MFC], SetDockState
- CMultiPaneFrameWnd [MFC], SetLastFocusedPane
- CMultiPaneFrameWnd [MFC], SetPreDockState
- CMultiPaneFrameWnd [MFC], StoreRecentDockSiteInfo
- CMultiPaneFrameWnd [MFC], StoreRecentTabRelatedInfo
ms.assetid: 989a548e-0d70-46b7-a513-8cf740e1be3e
ms.openlocfilehash: 047dd5ca2ca6705549e8f92de1550248e348ff52
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752795"
---
# <a name="cmultipaneframewnd-class"></a>CMultiPaneFramewnd 클래스

클래스는 `CMultiPaneFrameWnd` [CPaneFrameWnd 클래스를](../../mfc/reference/cpaneframewnd-class.md)확장합니다. 여러 창을 지원합니다. 컨트롤 막대에 포함된 단일 핸들 `CMultiPaneFrameWnd` 대신 사용자가 서로 `CMultiPaneFrameWnd` 도킹하고 여러 부동 탭창을 동적으로 만들 수 있는 [CPaneContainerManager 클래스](../../mfc/reference/cpanecontainermanager-class.md) 개체가 포함되어 있습니다.

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMultiPaneFrameWnd : public CPaneFrameWnd
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMultiPaneFrameWnd::애드파인](#addpane)|창을 추가합니다. (재정의 [CPaneFrameWnd::AddPane](../../mfc/reference/cpaneframewnd-class.md#addpane).)|
|[CMultiPaneFrameWnd::추가최근 파인](#addrecentpane)||
|[CMultiPaneFrameWnd::조정 레이아웃](#adjustlayout)|미니 프레임 창의 레이아웃을 조정합니다. (재정의 [CPaneFrameWnd::adjustLayout.)](../../mfc/reference/cpaneframewnd-class.md#adjustlayout)|
|[CMultiPaneFrameWnd::adjustPaneFrames](#adjustpaneframes)|[(재정의 CPaneFrameWnd::adjustPaneFrames.)](../../mfc/reference/cpaneframewnd-class.md#adjustpaneframes)|
|[CMultiPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|도킹된 창의 예상 사각형을 계산합니다. (재정의 [CPaneFrameWnd::CalcExpectedDockedRect](../../mfc/reference/cpaneframewnd-class.md#calcexpecteddockedrect).)|
|[CMultiPaneFrameWnd::수 있습니다연결](#canbeattached)|현재 창이 다른 창또는 프레임 창에 도킹할 수 있는지 여부를 결정합니다. (재정의 [CPaneFrameWnd::CanBeAttached.)](../../mfc/reference/cpaneframewnd-class.md#canbeattached)|
|[CMultiPaneFrameWnd::CanBeDockedTopane](#canbedockedtopane)|미니 프레임 창이 창에 도킹할 수 있는지 여부를 결정합니다. (재정의 [CPaneFrameWnd::CanBeDockedToPane](../../mfc/reference/cpaneframewnd-class.md#canbedockedtopane).)|
|[CMultiPaneFrameWnd::체크그리퍼 가시성](#checkgrippervisibility)|(재정의 [CPaneFrameWnd::체크그리퍼 가시성.)](../../mfc/reference/cpaneframewnd-class.md#checkgrippervisibility)|
|[CMultiPaneFrameWnd::닫기미니프레임](#closeminiframe)|( `CPaneFrameWnd::CloseMiniFrame`을 재정의합니다.)|
|[CMultiPaneFrameWnd::변환토탭문서](#converttotabbeddocument)|창을 탭된 문서로 변환합니다. (재정의 [CPaneFramewnd::변환토탭 문서.)](../../mfc/reference/cpaneframewnd-class.md#converttotabbeddocument)|
|[CMultiPaneFrameWnd::DockFrame](#dockframe)||
|[CMultiPaneFrameWnd::DockPane](#dockpane)|창을 도킹합니다. (재정의 [CPaneFramewnd::DockPane](../../mfc/reference/cpaneframewnd-class.md#dockpane).)|
|[CMultiPaneFramewnd::Dock최근파네토메인프레임](#dockrecentpanetomainframe)||
|[CMultiPaneFrameWnd::GetCaptionText](#getcaptiontext)|캡션 텍스트를 반환합니다. (재정의 [CPaneFrameWnd::GetCaptionText](../../mfc/reference/cpaneframewnd-class.md#getcaptiontext).)|
|[CMultiPaneFrameWnd::GetPaneContainer관리자](#getpanecontainermanager)|내부 컨테이너 관리자 개체에 대한 참조를 반환합니다.|
|[CMultiPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|미니 프레임 창에 포함된 첫 번째 표시 창을 반환합니다. (재정의 [CPaneFrameWnd::GetFirstVisiblePane](../../mfc/reference/cpaneframewnd-class.md#getfirstvisiblepane).)|
|[CMultiPaneFrameWnd::GetPane](#getpane)|미니 프레임 창에 포함된 창을 반환합니다. (재정의 [CPaneFrameWnd::GetPane](../../mfc/reference/cpaneframewnd-class.md#getpane).)|
|[CMultiPaneFrameWnd::GetPaneCount](#getpanecount)|미니 프레임 창에 포함된 창 수를 반환합니다. (재정의 [CPaneFrameWnd::GetPaneCount](../../mfc/reference/cpaneframewnd-class.md#getpanecount).)|
|[CMultiPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|미니 프레임 창에 포함된 표시 창 수를 반환합니다. (재정의 [CPaneFrameWnd::GetVisiblePaneCount](../../mfc/reference/cpaneframewnd-class.md#getvisiblepanecount).)|
|[CMultiPaneFrameWnd::삽입창](#insertpane)||
|[CMultiPaneFrameWnd::로드 스테이트](#loadstate)|레지스트리에서 창의 상태를 로드합니다. [(재정의 CPaneFrameWnd::로드 상태.)](../../mfc/reference/cpaneframewnd-class.md#loadstate)|
|[CMultiPaneFrameWnd::OnDockToRecentpos](#ondocktorecentpos)|가장 최근 위치에 미니 프레임 창을 도킹합니다. (재정의 [CPaneFrameWnd::OnDockToRecentpos](../../mfc/reference/cpaneframewnd-class.md#ondocktorecentpos).)|
|[CMultiPaneFrameWnd::OnKillRollUp타이머](#onkillrolluptimer)|롤업 타이머를 중지합니다. (재정의 [CPaneFrameWnd::OnKillRollUp타이머](../../mfc/reference/cpaneframewnd-class.md#onkillrolluptimer).)|
|[CMultiPaneFrameWnd::온파네리칼레이아웃](#onpanerecalclayout)|미니 프레임 창 내부의 창 레이아웃을 조정합니다. (재정의 [CPaneFramewnd::OnPaneRecalcLayout](../../mfc/reference/cpaneframewnd-class.md#onpanerecalclayout).)|
|[CMultiPaneFrameWnd::온셋롤업타이머](#onsetrolluptimer)|롤업 타이머를 설정합니다. (재정의 [CPaneFrameWnd::OnSetRollUp타이머](../../mfc/reference/cpaneframewnd-class.md#onsetrolluptimer).)|
|[CMultiPaneFrameWnd::OnShowPane](#onshowpane)|미니 프레임 창의 창이 숨겨지거나 표시될 때 프레임워크에서 호출됩니다. (재정의 [CPaneFramewnd::OnShowPane](../../mfc/reference/cpaneframewnd-class.md#onshowpane).)|
|[CMultiPaneFramewnd::PaneFromPoint](#panefrompoint)|미니 프레임 창 안에 사용자가 제공한 지점을 포함하는 경우 창을 반환합니다. (재정의 [CPaneFramewnd::PaneFromPoint](../../mfc/reference/cpaneframewnd-class.md#panefrompoint).)|
|[CMultiPaneFrameWnd::제거비유효파인](#removenonvalidpanes)|잘못된 창을 제거하기 위해 프레임워크에서 호출됩니다. (재정의 [CPaneFrameWnd::RemoveNon유효 파인](../../mfc/reference/cpaneframewnd-class.md#removenonvalidpanes).)|
|[CMultiPaneFrameWnd::제거창](#removepane)|미니 프레임 창에서 창을 제거합니다. (재정의 [CPaneFrameWnd::RemovePane](../../mfc/reference/cpaneframewnd-class.md#removepane).)|
|[CMultiPaneFrameWnd::대체판](#replacepane)|한 창을 다른 창으로 대체합니다. (재정의 [CPaneFrameWnd::대체 창](../../mfc/reference/cpaneframewnd-class.md#replacepane).)|
|[CMultiPaneFrameWnd::저장 상태](#savestate)|레지스트리에 창의 상태를 저장합니다. [(재정의 CPaneFrameWnd::SaveState](../../mfc/reference/cpaneframewnd-class.md#savestate).)|
|[CMultiPaneFrameWnd::직렬화](#serialize)|( `CPaneFrameWnd::Serialize`을 재정의합니다.)|
|[CMultiPaneFrameWnd::SetDockState](#setdockstate)|도킹 상태를 설정합니다. [(재정의 CPaneFrameWnd::SetDockState](../../mfc/reference/cpaneframewnd-class.md#setdockstate).)|
|[CMultiPaneFrameWnd::SetLastFocusedPane](#setlastfocusedpane)||
|[CMultiPaneFrameWnd::SetPreDockState](#setpredockstate)|사전 도킹 상태를 설정합니다. (재정의 [CPaneFrameWnd::SetPreDockState](../../mfc/reference/cpaneframewnd-class.md#setpredockstate).)|
|[CMultiPaneFrameWnd::최근독사이트정보](#storerecentdocksiteinfo)|(재정의 [CPaneFrameWnd::StoreRecentDockSiteInfo](../../mfc/reference/cpaneframewnd-class.md#storerecentdocksiteinfo).)|
|[CMultiPaneFrameWnd::저장소최근탭관련정보](#storerecenttabrelatedinfo)|(재정의 [CPaneFrameWnd::StoreRecentTab관련 정보](../../mfc/reference/cpaneframewnd-class.md#storerecenttabrelatedinfo).)|

## <a name="remarks"></a>설명

이 클래스의 대부분의 메서드는 [CPaneFrameWnd 클래스의 메서드를 재정의합니다.](../../mfc/reference/cpaneframewnd-class.md)

창이 AFX_CBRS_AUTO_ROLLUP 스타일을 사용하고 사용자가 여러 창 프레임 창으로 창을 도킹하는 경우 사용자는 다른 도킹된 창의 스타일 설정에 관계없이 창을 롤업할 수 있습니다.

프레임워크는 사용자가 CBRS_FLOAT_MULTI `CMultiPaneFrameWnd` 스타일을 사용하는 창을 띄우면 개체를 자동으로 만듭니다.

`CPaneFrameWnd` 클래스에서 클래스를 파생하고 동적으로 만드는 것에 대한 자세한 내용은 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)를 참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `CMultiPaneFrameWnd` 개체에 대한 포인터를 검색하는 방법을 보여 줍니다. 이 코드 조각은 창 [크기 설정 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_SetPaneSize#4](../../mfc/reference/codesnippet/cpp/cmultipaneframewnd-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)

[CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxMultiPaneFramewnd.h

## <a name="cmultipaneframewndaddpane"></a><a name="addpane"></a>CMultiPaneFrameWnd::애드파인

```
virtual void AddPane(CBasePane* pWnd);
```

### <a name="parameters"></a>매개 변수

【인】 *pWnd*<br/>

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndaddrecentpane"></a><a name="addrecentpane"></a>CMultiPaneFrameWnd::추가최근 파인

```
virtual BOOL AddRecentPane(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndadjustlayout"></a><a name="adjustlayout"></a>CMultiPaneFrameWnd::조정 레이아웃

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndadjustpaneframes"></a><a name="adjustpaneframes"></a>CMultiPaneFrameWnd::adjustPaneFrames

```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndcalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CMultiPaneFrameWnd::CalcExpectedDockedRect

```
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pWndToDock*<br/>
【인】 *pt마우스*<br/>
【인】 *정류 결과*<br/>
【인】 *b그리기 탭*<br/>
【인】 *ppTargetBar*<br/>

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndcanbeattached"></a><a name="canbeattached"></a>CMultiPaneFrameWnd::수 있습니다연결

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndcanbedockedtopane"></a><a name="canbedockedtopane"></a>CMultiPaneFrameWnd::CanBeDockedTopane

```
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;
```

### <a name="parameters"></a>매개 변수

【인】 *pDockingBar*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndcheckgrippervisibility"></a><a name="checkgrippervisibility"></a>CMultiPaneFrameWnd::체크그리퍼 가시성

```
virtual void CheckGripperVisibility();
```

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndcloseminiframe"></a><a name="closeminiframe"></a>CMultiPaneFrameWnd::닫기미니프레임

```
virtual void CloseMiniFrame();
```

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>CMultiPaneFrameWnd::변환토탭문서

```
virtual void ConvertToTabbedDocument();
```

### <a name="remarks"></a>설명

## <a name="cmultipaneframewnddockframe"></a><a name="dockframe"></a>CMultiPaneFrameWnd::DockFrame

```
virtual BOOL DockFrame(
    CPaneFrameWnd* pDockedFrame,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>매개 변수

【인】 *pDocked프레임*<br/>
【인】 *독 방법*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewnddockpane"></a><a name="dockpane"></a>CMultiPaneFrameWnd::DockPane

```
virtual BOOL DockPane(CDockablePane* pDockedBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pDockedBar*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewnddockrecentpanetomainframe"></a><a name="dockrecentpanetomainframe"></a>CMultiPaneFramewnd::Dock최근파네토메인프레임

```
virtual void DockRecentPaneToMainFrame(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndgetcaptiontext"></a><a name="getcaptiontext"></a>CMultiPaneFrameWnd::GetCaptionText

```
virtual CString GetCaptionText();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndgetfirstvisiblepane"></a><a name="getfirstvisiblepane"></a>CMultiPaneFrameWnd::GetFirstVisiblePane

```
virtual CWnd* GetFirstVisiblePane() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndgetpane"></a><a name="getpane"></a>CMultiPaneFrameWnd::GetPane

```
virtual CWnd* GetPane() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndgetpanecontainermanager"></a><a name="getpanecontainermanager"></a>CMultiPaneFrameWnd::GetPaneContainer관리자

내부 컨테이너 관리자 개체에 대한 참조를 반환합니다.

```
CPaneContainerManager& GetPaneContainerManager();
```

### <a name="return-value"></a>Return Value

내부 컨테이너 관리자 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드는 내부 [CPaneContainerManager 클래스](../../mfc/reference/cpanecontainermanager-class.md) 개체에 액세스 하는 데 사용할 수 있습니다.

## <a name="cmultipaneframewndgetpanecount"></a><a name="getpanecount"></a>CMultiPaneFrameWnd::GetPaneCount

```
virtual int GetPaneCount() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndgetvisiblepanecount"></a><a name="getvisiblepanecount"></a>CMultiPaneFrameWnd::GetVisiblePaneCount

```
virtual int GetVisiblePaneCount() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndinsertpane"></a><a name="insertpane"></a>CMultiPaneFrameWnd::삽입창

```
virtual BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨트롤바*<br/>
【인】 *p Target*<br/>
【인】 *b애프터*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndloadstate"></a><a name="loadstate"></a>CMultiPaneFrameWnd::로드 스테이트

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

【인】 *lpsz프로필이름*<br/>
【인】 *UIID*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndondocktorecentpos"></a><a name="ondocktorecentpos"></a>CMultiPaneFrameWnd::OnDockToRecentpos

```
virtual void OnDockToRecentPos();
```

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndonkillrolluptimer"></a><a name="onkillrolluptimer"></a>CMultiPaneFrameWnd::OnKillRollUp타이머

```
virtual void OnKillRollUpTimer();
```

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndonpanerecalclayout"></a><a name="onpanerecalclayout"></a>CMultiPaneFrameWnd::온파네리칼레이아웃

```
virtual void OnPaneRecalcLayout();
```

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndonsetrolluptimer"></a><a name="onsetrolluptimer"></a>CMultiPaneFrameWnd::온셋롤업타이머

```
virtual void OnSetRollUpTimer();
```

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndonshowpane"></a><a name="onshowpane"></a>CMultiPaneFrameWnd::OnShowPane

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>
【인】 *bShow*<br/>

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndpanefrompoint"></a><a name="panefrompoint"></a>CMultiPaneFramewnd::PaneFromPoint

```
virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    BOOL bCheckVisibility);
```

### <a name="parameters"></a>매개 변수

【인】 *점*<br/>
【인】 *n감도*<br/>
【인】 *b체크가시성*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndremovenonvalidpanes"></a><a name="removenonvalidpanes"></a>CMultiPaneFrameWnd::제거비유효파인

```
virtual void RemoveNonValidPanes();
```

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndremovepane"></a><a name="removepane"></a>CMultiPaneFrameWnd::제거창

```
virtual void RemovePane(
    CBasePane* pBar,
    BOOL bDestroy = FALSE,
    BOOL bNoDelayedDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>
【인】 *bDestroy*<br/>
【인】 *b지연파괴*<br/>

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndreplacepane"></a><a name="replacepane"></a>CMultiPaneFrameWnd::대체판

```
virtual void ReplacePane(
    CBasePane* pBarOrg,
    CBasePane* pBarReplaceWith);
```

### <a name="parameters"></a>매개 변수

【인】 *pBarOrg*<br/>
【인】 *pBarReplaceWith*<br/>

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndsavestate"></a><a name="savestate"></a>CMultiPaneFrameWnd::저장 상태

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

【인】 *lpsz프로필이름*<br/>
【인】 *UIID*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndserialize"></a><a name="serialize"></a>CMultiPaneFrameWnd::직렬화

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

[in] *ar*<br/>

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndsetdockstate"></a><a name="setdockstate"></a>CMultiPaneFrameWnd::SetDockState

```
virtual void SetDockState(CDockingManager* pDockManager);
```

### <a name="parameters"></a>매개 변수

【인】 *pDockManager*<br/>

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndsetlastfocusedpane"></a><a name="setlastfocusedpane"></a>CMultiPaneFrameWnd::SetLastFocusedPane

```cpp
void SetLastFocusedPane(HWND hwnd);
```

### <a name="parameters"></a>매개 변수

【인】 *hwnd*<br/>

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndsetpredockstate"></a><a name="setpredockstate"></a>CMultiPaneFrameWnd::SetPreDockState

```
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,
    CBasePane* pBarToDock = NULL,
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```

### <a name="parameters"></a>매개 변수

【인】 *프리독스테이트*<br/>
【인】 *pBarToDock*<br/>
【인】 *독 방법*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndstorerecentdocksiteinfo"></a><a name="storerecentdocksiteinfo"></a>CMultiPaneFrameWnd::최근독사이트정보

```
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

### <a name="remarks"></a>설명

## <a name="cmultipaneframewndstorerecenttabrelatedinfo"></a><a name="storerecenttabrelatedinfo"></a>CMultiPaneFrameWnd::저장소최근탭관련정보

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
[CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md)
