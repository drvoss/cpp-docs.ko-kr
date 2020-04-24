---
title: CDockSite Class
ms.date: 10/18/2018
f1_keywords:
- CDockSite
- AFXDOCKSITE/CDockSite
- AFXDOCKSITE/CDockSite::AddRow
- AFXDOCKSITE/CDockSite::AdjustDockingLayout
- AFXDOCKSITE/CDockSite::AdjustLayout
- AFXDOCKSITE/CDockSite::AlignDockSite
- AFXDOCKSITE/CDockSite::CalcFixedLayout
- AFXDOCKSITE/CDockSite::CanAcceptPane
- AFXDOCKSITE/CDockSite::CreateEx
- AFXDOCKSITE/CDockSite::CreateRow
- AFXDOCKSITE/CDockSite::DockPane
- AFXDOCKSITE/CDockSite::DoesAllowDynInsertBefore
- AFXDOCKSITE/CDockSite::FindRowIndex
- AFXDOCKSITE/CDockSite::FixupVirtualRects
- AFXDOCKSITE/CDockSite::GetDockSiteID
- AFXDOCKSITE/CDockSite::GetDockSiteRowsList
- AFXDOCKSITE/CDockSite::IsAccessibilityCompatible
- AFXDOCKSITE/CDockSite::IsDragMode
- AFXDOCKSITE/CDockSite::IsLastRow
- AFXDOCKSITE/CDockSite::IsRectWithinDockSite
- AFXDOCKSITE/CDockSite::IsResizable
- AFXDOCKSITE/CDockSite::MovePane
- AFXDOCKSITE/CDockSite::OnInsertRow
- AFXDOCKSITE/CDockSite::OnRemoveRow
- AFXDOCKSITE/CDockSite::OnResizeRow
- AFXDOCKSITE/CDockSite::OnSetWindowPos
- AFXDOCKSITE/CDockSite::OnShowRow
- AFXDOCKSITE/CDockSite::OnSizeParent
- AFXDOCKSITE/CDockSite::PaneFromPoint
- AFXDOCKSITE/CDockSite::DockPaneLeftOf
- AFXDOCKSITE/CDockSite::FindPaneByID
- AFXDOCKSITE/CDockSite::GetPaneList
- AFXDOCKSITE/CDockSite::RectSideFromPoint
- AFXDOCKSITE/CDockSite::RemovePane
- AFXDOCKSITE/CDockSite::RemoveRow
- AFXDOCKSITE/CDockSite::ReplacePane
- AFXDOCKSITE/CDockSite::RepositionPanes
- AFXDOCKSITE/CDockSite::ResizeDockSite
- AFXDOCKSITE/CDockSite::ResizeRow
- AFXDOCKSITE/CDockSite::ShowPane
- AFXDOCKSITE/CDockSite::ShowRow
- AFXDOCKSITE/CDockSite::SwapRows
helpviewer_keywords:
- CDockSite [MFC], AddRow
- CDockSite [MFC], AdjustDockingLayout
- CDockSite [MFC], AdjustLayout
- CDockSite [MFC], AlignDockSite
- CDockSite [MFC], CalcFixedLayout
- CDockSite [MFC], CanAcceptPane
- CDockSite [MFC], CreateEx
- CDockSite [MFC], CreateRow
- CDockSite [MFC], DockPane
- CDockSite [MFC], DoesAllowDynInsertBefore
- CDockSite [MFC], FindRowIndex
- CDockSite [MFC], FixupVirtualRects
- CDockSite [MFC], GetDockSiteID
- CDockSite [MFC], GetDockSiteRowsList
- CDockSite [MFC], IsAccessibilityCompatible
- CDockSite [MFC], IsDragMode
- CDockSite [MFC], IsLastRow
- CDockSite [MFC], IsRectWithinDockSite
- CDockSite [MFC], IsResizable
- CDockSite [MFC], MovePane
- CDockSite [MFC], OnInsertRow
- CDockSite [MFC], OnRemoveRow
- CDockSite [MFC], OnResizeRow
- CDockSite [MFC], OnSetWindowPos
- CDockSite [MFC], OnShowRow
- CDockSite [MFC], OnSizeParent
- CDockSite [MFC], PaneFromPoint
- CDockSite [MFC], DockPaneLeftOf
- CDockSite [MFC], FindPaneByID
- CDockSite [MFC], GetPaneList
- CDockSite [MFC], RectSideFromPoint
- CDockSite [MFC], RemovePane
- CDockSite [MFC], RemoveRow
- CDockSite [MFC], ReplacePane
- CDockSite [MFC], RepositionPanes
- CDockSite [MFC], ResizeDockSite
- CDockSite [MFC], ResizeRow
- CDockSite [MFC], ShowPane
- CDockSite [MFC], ShowRow
- CDockSite [MFC], SwapRows
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
ms.openlocfilehash: 471d68ead1bc5a11ace29f572647c4a7f2406b4e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753278"
---
# <a name="cdocksite-class"></a>CDockSite Class

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

[CPane Class](../../mfc/reference/cpane-class.md) 에서 파생되는 창을 행 집합으로 배열하기 위한 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CDockSite: public CBasePane
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDockSite::AddRow](#addrow)||
|[CDockSite::AdjustDockingLayout](#adjustdockinglayout)|[(재정의 CBasePane::adjustDocking레이아웃.)](../../mfc/reference/cbasepane-class.md#adjustdockinglayout)|
|[CDockSite::AdjustLayout](#adjustlayout)|[(재정비::adjustLayout.)](../../mfc/reference/cbasepane-class.md#adjustlayout)|
|[CDockSite::AlignDockSite](#aligndocksite)||
|[CDockSite::CalcFixedLayout](#calcfixedlayout)|[(재정의 CBasePane::석회화 레이아웃.)](../../mfc/reference/cbasepane-class.md#calcfixedlayout)|
|[CDockSite::CanAcceptPane](#canacceptpane)|[(재정의 CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane).)|
|[CDockSite::CreateEx](#createex)|[(CBasePane 재정의::만들기.)](../../mfc/reference/cbasepane-class.md#createex)|
|[CDockSite::CreateRow](#createrow)||
|[CDockSite::DockPane](#dockpane)|[(재정의 CBasePane::DockPane](../../mfc/reference/cbasepane-class.md#dockpane).)|
|[CDockSite::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|[(재정의 CBasePane::DoesAllowDyn인가 전에](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CDockSite::FindRowIndex](#findrowindex)||
|[CDockSite::FixupVirtualRects](#fixupvirtualrects)||
|[CDockSite::GetDockSiteID](#getdocksiteid)||
|[CDockSite::GetDockSiteRowsList](#getdocksiterowslist)||
|[CDockSite::IsAccessibilityCompatible](#isaccessibilitycompatible)|( `CBasePane::IsAccessibilityCompatible`을 재정의합니다.)|
|[CDockSite::IsDragMode](#isdragmode)||
|[CDockSite::IsLastRow](#islastrow)||
|[CDockSite::IsRectWithinDockSite](#isrectwithindocksite)||
|[CDockSite::IsResizable](#isresizable)|[(재정의 CBasePane::이재명](../../mfc/reference/cbasepane-class.md#isresizable).)|
|[CDockSite::MovePane](#movepane)||
|[CDockSite::OnInsertRow](#oninsertrow)||
|[CDockSite::OnRemoveRow](#onremoverow)||
|[CDockSite::OnResizeRow](#onresizerow)||
|[CDockSite::OnSetWindowPos](#onsetwindowpos)||
|[CDockSite::OnShowRow](#onshowrow)||
|[CDockSite::OnSizeParent](#onsizeparent)||
|[CDockSite::PaneFromPoint](#panefrompoint)|주어진 매개 변수로 지정된 지점에서 도킹 사이트에 도킹된 창을 반환합니다.|
|[CDockSite::DockPaneLeftOf](#dockpaneleftof)|창을 다른 창의 왼쪽에 도킹합니다.|
|[CDock사이트::찾기파네바이드](#findpanebyid)|지정된 ID로 식별되는 창을 반환합니다.|
|[CDockSite::GetPaneList](#getpanelist)|도킹 사이트에 도킹된 창 목록을 반환합니다.|
|[CDockSite::RectSideFromPoint](#rectsidefrompoint)||
|[CDockSite::RemovePane](#removepane)||
|[CDockSite::RemoveRow](#removerow)||
|[CDockSite::ReplacePane](#replacepane)||
|[CDockSite::RepositionPanes](#repositionpanes)||
|[CDockSite::ResizeDockSite](#resizedocksite)||
|[CDockSite::ResizeRow](#resizerow)||
|[CDockSite::ShowPane](#showpane)|창을 표시합니다.|
|[CDockSite::ShowRow](#showrow)||
|[CDockSite::SwapRows](#swaprows)||

## <a name="remarks"></a>설명

프레임워크는 `CDockSite` [CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking)을 호출할 때 자동으로 개체를 만듭니다. 도킹 사이트 창은 주 프레임 창에서 클라이언트 영역의 가장자리에 배치됩니다.

[CFrameWndEx 클래스는](../../mfc/reference/cframewndex-class.md) 이러한 서비스를 처리하기 때문에 일반적으로 도크 사이트에서 제공하는 서비스를 호출할 필요가 없습니다.

## <a name="example"></a>예제

다음 예제에서는 `CDockSite` 클래스의 개체를 만드는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[Cobject](../../mfc/reference/cobject-class.md)\
❏&nbsp;[CCmd Target](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[독사이트](../../mfc/reference/cdocksite-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDockSite.h

## <a name="cdocksiteaddrow"></a><a name="addrow"></a>CDock사이트::애드로우

```
CDockingPanesRow* AddRow(
    POSITION pos,
    int nHeight);
```

### <a name="parameters"></a>매개 변수

【인】 *포스 (것)스*<br/>

【인】 *n높이*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksiteadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CDock사이트::조정도킹레이아웃

```
virtual void AdjustDockingLayout();
```

### <a name="remarks"></a>설명

## <a name="cdocksiteadjustlayout"></a><a name="adjustlayout"></a>CDock사이트::조정레이아웃

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>설명

## <a name="cdocksitealigndocksite"></a><a name="aligndocksite"></a>CDock사이트::정렬 독사이트

```cpp
void AlignDockSite(
    const CRect& rectToAlignBy,
    CRect& rectResult,
    BOOL bMoveImmediately);
```

### <a name="parameters"></a>매개 변수

【인】 *정류정렬*<br/>

【인】 *정류 결과*<br/>

【인】 *bMove즉시*<br/>

### <a name="remarks"></a>설명

## <a name="cdocksitecalcfixedlayout"></a><a name="calcfixedlayout"></a>CDock사이트::석회화레이아웃

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

## <a name="cdocksitecanacceptpane"></a><a name="canacceptpane"></a>CDock사이트::캔 수락파인

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksitecreateex"></a><a name="createex"></a>CDock사이트::만들기

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    DWORD dwControlBarStyle,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>매개 변수

【인】 *dwStyleEx*<br/>

【인】 *dw스타일*<br/>

[in] *rect*<br/>

【인】 *pParentWnd*<br/>

【인】 *dw컨트롤바스타일*<br/>

【인】 *p컨텍스트*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksitecreaterow"></a><a name="createrow"></a>CDock사이트::만들기행

```
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nRowHeight);
```

### <a name="parameters"></a>매개 변수

【인】 *p부모독바*<br/>

【인】 *n오프셋*<br/>

【인】 *nRow높이*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksitedockpane"></a><a name="dockpane"></a>CDock사이트::D오크파인

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>매개 변수

【인】 *pWnd*<br/>

【인】 *독 방법*<br/>

【인】 *lpRect*<br/>

### <a name="remarks"></a>설명

## <a name="cdocksitedockpaneleftof"></a><a name="dockpaneleftof"></a>CDock사이트::DockPaneLeftOf

창을 다른 창의 왼쪽에 도킹합니다.

```
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>매개 변수

*pBarToDock*<br/>
【인, 아웃】 *pTargetBar의*왼쪽에 도킹할 창에 대한 포인터입니다.

*pTargetBar*<br/>
【인, 아웃】 대상 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 창이 성공적으로 도킹된 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cdocksitedoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CDockSite::DoesAllowDyn인더인

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksitefindpanebyid"></a><a name="findpanebyid"></a>CDock사이트::찾기파네바이드

지정된 ID를 가지고 창을 반환합니다.

```
CPane* FindPaneByID(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 찾을 창의 명령 ID입니다.

### <a name="return-value"></a>Return Value

지정된 명령 ID가 있는 창에 대한 포인터 또는 창을 찾을 수 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

## <a name="cdocksitefindrowindex"></a><a name="findrowindex"></a>CDock사이트::찾기로인덱스

```
int FindRowIndex(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>매개 변수

【인】 *구덩이*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksitefixupvirtualrects"></a><a name="fixupvirtualrects"></a>CDock사이트::픽스업가상 수정

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>설명

## <a name="cdocksitegetdocksiteid"></a><a name="getdocksiteid"></a>CDock사이트::GetDockSiteID

```
virtual UINT GetDockSiteID() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksitegetdocksiterowslist"></a><a name="getdocksiterowslist"></a>CDockSite::GetDockSiteRowsList

```
const CObList& GetDockSiteRowsList() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksitegetpanelist"></a><a name="getpanelist"></a>CDock사이트::겟파인리스트

도크 사이트에 도킹된 창 목록을 반환합니다.

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>Return Value

도킹 바에 현재 도킹된 창 목록에 대한 읽기 전용 참조입니다.

## <a name="cdocksiteisaccessibilitycompatible"></a><a name="isaccessibilitycompatible"></a>CDock사이트::접근성 호환

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksiteisdragmode"></a><a name="isdragmode"></a>CDock사이트::IsDragmode

```
virtual BOOL IsDragMode() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksiteislastrow"></a><a name="islastrow"></a>CDockSite::IsLastRow

```
bool IsLastRow(CDockingPanesRow* pRow) const;
```

### <a name="parameters"></a>매개 변수

【인】 *구덩이*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksiteisrectwithindocksite"></a><a name="isrectwithindocksite"></a>CDockSite::IsRectWithinDock사이트

```
BOOL IsRectWithinDockSite(
    CRect rect,
    CPoint& ptDelta);
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

【인】 *pt델타*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksiteisresizable"></a><a name="isresizable"></a>CDock사이트::이재화 가능

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksitemovepane"></a><a name="movepane"></a>CDock사이트::무브파인

```
virtual BOOL MovePane(
    CPane* pWnd,
    UINT nFlags,
    CPoint ptOffset);
```

### <a name="parameters"></a>매개 변수

【인】 *pWnd*<br/>

【인】 *nFlags*<br/>

【인】 *ptOffset*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksiteoninsertrow"></a><a name="oninsertrow"></a>CDockSite::온인서트로

```
virtual void OnInsertRow(POSITION pos);
```

### <a name="parameters"></a>매개 변수

【인】 *포스 (것)스*<br/>

### <a name="remarks"></a>설명

## <a name="cdocksiteonremoverow"></a><a name="onremoverow"></a>CDock사이트::에 제거행

```
virtual void OnRemoveRow(
    POSITION pos,
    BOOL bByShow = FALSE);
```

### <a name="parameters"></a>매개 변수

【인】 *포스 (것)스*<br/>

【인】 *bByShow*<br/>

### <a name="remarks"></a>설명

## <a name="cdocksiteonresizerow"></a><a name="onresizerow"></a>CDock사이트::온리사이즈로우

```
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,
    int nOffset);
```

### <a name="parameters"></a>매개 변수

【인】 *pRowToresize*<br/>

【인】 *n오프셋*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksiteonsizeparent"></a><a name="onsizeparent"></a>CDockSite::온사이즈부모

```
virtual void OnSizeParent(
    CRect& rectAvailable,
    UINT nSide,
    BOOL bExpand,
    int nOffset);
```

### <a name="parameters"></a>매개 변수

【인】 *정류 사용 가능*<br/>

【인】 *nSide*<br/>

【인】 *b확장*<br/>

【인】 *n오프셋*<br/>

### <a name="remarks"></a>설명

## <a name="cdocksiteonsetwindowpos"></a><a name="onsetwindowpos"></a>CDockSite::온셋윈도우포스

```
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,
    const CRect& rectWnd,
    UINT nFlags);
```

### <a name="parameters"></a>매개 변수

【인】 *pWnd인더*<br/>

【인】 *직류*<br/>

【인】 *nFlags*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksiteonshowrow"></a><a name="onshowrow"></a>CDock사이트::온쇼로우

```
virtual void OnShowRow(
    POSITION pos,
    BOOL bShow);
```

### <a name="parameters"></a>매개 변수

【인】 *포스 (것)스*<br/>

【인】 *bShow*<br/>

### <a name="remarks"></a>설명

## <a name="cdocksitepanefrompoint"></a><a name="panefrompoint"></a>CDock사이트::P인FromPoint

주어진 매개 변수로 지정된 지점에서 도킹 사이트에 도킹된 창을 반환합니다.

```
virtual CPane* PaneFromPoint(CPoint pt);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
【인】 창을 검색할 점(화면 좌표)입니다.

### <a name="return-value"></a>Return Value

지정된 지점에 창이 없는 경우 지정된 지점 또는 NULL에 있는 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cdocksiterectsidefrompoint"></a><a name="rectsidefrompoint"></a>CDock사이트::직사각형에서부터

```
static int __stdcall RectSideFromPoint(
    const CRect& rect,
    const CPoint& point);
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

【인】 *점*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksiteremovepane"></a><a name="removepane"></a>CDock사이트::제거창

```
virtual void RemovePane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>매개 변수

【인】 *pWnd*<br/>

【인】 *독 방법*<br/>

### <a name="remarks"></a>설명

## <a name="cdocksiteremoverow"></a><a name="removerow"></a>CDock사이트::제거행

```cpp
void RemoveRow(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>매개 변수

【인】 *구덩이*<br/>

### <a name="remarks"></a>설명

## <a name="cdocksitereplacepane"></a><a name="replacepane"></a>CDock사이트::대체판

```
BOOL ReplacePane(
    CPane* pOldBar,
    CPane* pNewBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pOldBar*<br/>

【인】 *p뉴바*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksiterepositionpanes"></a><a name="repositionpanes"></a>CDock사이트::재배치파네

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>매개 변수

【인】 *정류뉴클라이언트에어리어*<br/>

### <a name="remarks"></a>설명

## <a name="cdocksiteresizedocksite"></a><a name="resizedocksite"></a>CDock사이트::크기 조정독사이트

```cpp
void ResizeDockSite(
    int nNewWidth,
    int nNewHeight);
```

### <a name="parameters"></a>매개 변수

【인】 *nNewWidth*<br/>

【인】 *nNewHeight*<br/>

### <a name="remarks"></a>설명

## <a name="cdocksiteresizerow"></a><a name="resizerow"></a>CDock사이트::크기 조정

```
int ResizeRow(
    CDockingPanesRow* pRow,
    int nNewSize,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>매개 변수

【인】 *구덩이*<br/>

【인】 *nNewSize*<br/>

【인】 *bAdjust레이아웃*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdocksiteshowpane"></a><a name="showpane"></a>CDock사이트::쇼파인

창을 표시합니다.

```
virtual BOOL ShowPane(
    CBasePane* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인, 아웃】 표시하거나 숨길 창에 대한 포인터입니다.

*bShow*<br/>
【인】 TRUE창을 표시하도록 지정합니다. FALSE창을 숨길 수 있도록 지정합니다.

*bDelay*<br/>
【인】 TRUE는 창이 표시될 때까지 창의 레이아웃을 지연시켜야 한다고 지정합니다. 그렇지 않으면 false입니다.

*bActivate*<br/>
【인】 이 매개 변수는 사용되지 않습니다.

### <a name="return-value"></a>Return Value

창이 표시되었지만 성공적으로 숨김이 있는 경우 TRUE입니다. 지정된 창이 이 도크 사이트에 속하지 않는 경우 FALSE입니다.

### <a name="remarks"></a>설명

도킹된 창을 표시하거나 숨기려면 이 메서드를 호출합니다. 일반적으로 부모 프레임 창이나 `CDockSite::ShowPane` 기본 창에서 호출되므로 직접 호출할 필요가 없습니다.

## <a name="cdocksiteshowrow"></a><a name="showrow"></a>CDock사이트::쇼로우

```cpp
void ShowRow(
    CDockingPanesRow* pRow,
    BOOL bShow,
    BOOL bAdjustLayout);
```

### <a name="parameters"></a>매개 변수

【인】 *구덩이*<br/>

【인】 *bShow*<br/>

【인】 *bAdjust레이아웃*<br/>

### <a name="remarks"></a>설명

## <a name="cdocksiteswaprows"></a><a name="swaprows"></a>CDock사이트::스왑로우

```cpp
void SwapRows(
    CDockingPanesRow* pFirstRow,
    CDockingPanesRow* pSecondRow);
```

### <a name="parameters"></a>매개 변수

【인】 *pFirstRow*<br/>

【인】 *pSecondRow*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CBasePane 클래스](../../mfc/reference/cbasepane-class.md)
