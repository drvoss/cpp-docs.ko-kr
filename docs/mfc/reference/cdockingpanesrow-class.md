---
title: 도킹파네스로우 클래스
ms.date: 10/18/2018
f1_keywords:
- CDockingPanesRow
- AFXDOCKINGPANESROW/CDockingPanesRow
- AFXDOCKINGPANESROW/CDockingPanesRow::AddPane
- AFXDOCKINGPANESROW/CDockingPanesRow::AddPaneFromRow
- AFXDOCKINGPANESROW/CDockingPanesRow::ArrangePanes
- AFXDOCKINGPANESROW/CDockingPanesRow::CalcFixedLayout
- AFXDOCKINGPANESROW/CDockingPanesRow::Create
- AFXDOCKINGPANESROW/CDockingPanesRow::ExpandStretchedPanes
- AFXDOCKINGPANESROW/CDockingPanesRow::ExpandStretchedPanesRect
- AFXDOCKINGPANESROW/CDockingPanesRow::FixupVirtualRects
- AFXDOCKINGPANESROW/CDockingPanesRow::GetAvailableLength
- AFXDOCKINGPANESROW/CDockingPanesRow::GetAvailableSpace
- AFXDOCKINGPANESROW/CDockingPanesRow::GetClientRect
- AFXDOCKINGPANESROW/CDockingPanesRow::GetDockSite
- AFXDOCKINGPANESROW/CDockingPanesRow::GetExtraSpace
- AFXDOCKINGPANESROW/CDockingPanesRow::GetGroupFromPane
- AFXDOCKINGPANESROW/CDockingPanesRow::GetID
- AFXDOCKINGPANESROW/CDockingPanesRow::GetMaxPaneSize
- AFXDOCKINGPANESROW/CDockingPanesRow::GetPaneCount
- AFXDOCKINGPANESROW/CDockingPanesRow::GetPaneList
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowAlignment
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowHeight
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowOffset
- AFXDOCKINGPANESROW/CDockingPanesRow::GetVisibleCount
- AFXDOCKINGPANESROW/CDockingPanesRow::GetWindowRect
- AFXDOCKINGPANESROW/CDockingPanesRow::HasPane
- AFXDOCKINGPANESROW/CDockingPanesRow::IsEmpty
- AFXDOCKINGPANESROW/CDockingPanesRow::IsExclusiveRow
- AFXDOCKINGPANESROW/CDockingPanesRow::IsHorizontal
- AFXDOCKINGPANESROW/CDockingPanesRow::IsVisible
- AFXDOCKINGPANESROW/CDockingPanesRow::Move
- AFXDOCKINGPANESROW/CDockingPanesRow::MovePane
- AFXDOCKINGPANESROW/CDockingPanesRow::OnResizePane
- AFXDOCKINGPANESROW/CDockingPanesRow::RedrawAll
- AFXDOCKINGPANESROW/CDockingPanesRow::RemovePane
- AFXDOCKINGPANESROW/CDockingPanesRow::ReplacePane
- AFXDOCKINGPANESROW/CDockingPanesRow::RepositionPanes
- AFXDOCKINGPANESROW/CDockingPanesRow::Resize
- AFXDOCKINGPANESROW/CDockingPanesRow::ResizeByPaneDivider
- AFXDOCKINGPANESROW/CDockingPanesRow::ScreenToClient
- AFXDOCKINGPANESROW/CDockingPanesRow::SetExtra
- AFXDOCKINGPANESROW/CDockingPanesRow::ShowDockSiteRow
- AFXDOCKINGPANESROW/CDockingPanesRow::ShowPane
- AFXDOCKINGPANESROW/CDockingPanesRow::UpdateVisibleState
helpviewer_keywords:
- CDockingPanesRow [MFC], AddPane
- CDockingPanesRow [MFC], AddPaneFromRow
- CDockingPanesRow [MFC], ArrangePanes
- CDockingPanesRow [MFC], CalcFixedLayout
- CDockingPanesRow [MFC], Create
- CDockingPanesRow [MFC], ExpandStretchedPanes
- CDockingPanesRow [MFC], ExpandStretchedPanesRect
- CDockingPanesRow [MFC], FixupVirtualRects
- CDockingPanesRow [MFC], GetAvailableLength
- CDockingPanesRow [MFC], GetAvailableSpace
- CDockingPanesRow [MFC], GetClientRect
- CDockingPanesRow [MFC], GetDockSite
- CDockingPanesRow [MFC], GetExtraSpace
- CDockingPanesRow [MFC], GetGroupFromPane
- CDockingPanesRow [MFC], GetID
- CDockingPanesRow [MFC], GetMaxPaneSize
- CDockingPanesRow [MFC], GetPaneCount
- CDockingPanesRow [MFC], GetPaneList
- CDockingPanesRow [MFC], GetRowAlignment
- CDockingPanesRow [MFC], GetRowHeight
- CDockingPanesRow [MFC], GetRowOffset
- CDockingPanesRow [MFC], GetVisibleCount
- CDockingPanesRow [MFC], GetWindowRect
- CDockingPanesRow [MFC], HasPane
- CDockingPanesRow [MFC], IsEmpty
- CDockingPanesRow [MFC], IsExclusiveRow
- CDockingPanesRow [MFC], IsHorizontal
- CDockingPanesRow [MFC], IsVisible
- CDockingPanesRow [MFC], Move
- CDockingPanesRow [MFC], MovePane
- CDockingPanesRow [MFC], OnResizePane
- CDockingPanesRow [MFC], RedrawAll
- CDockingPanesRow [MFC], RemovePane
- CDockingPanesRow [MFC], ReplacePane
- CDockingPanesRow [MFC], RepositionPanes
- CDockingPanesRow [MFC], Resize
- CDockingPanesRow [MFC], ResizeByPaneDivider
- CDockingPanesRow [MFC], ScreenToClient
- CDockingPanesRow [MFC], SetExtra
- CDockingPanesRow [MFC], ShowDockSiteRow
- CDockingPanesRow [MFC], ShowPane
- CDockingPanesRow [MFC], UpdateVisibleState
ms.assetid: e7a17832-0ebb-4bce-b799-cec9b60f76fe
ms.openlocfilehash: d7535ae6c5246a372fd1a48573716bb166991d4e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753318"
---
# <a name="cdockingpanesrow-class"></a>도킹파네스로우 클래스

도크 사이트의 동일한 수평 또는 수직 행(열)에 위치한 창 목록을 관리합니다.

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CDockingPanesRow : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CDockingPanesRow::CDockingPanesRow`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDockingPanesRow::AddPane](#addpane)||
|[CDockingPanesRow::AddPaneFromRow](#addpanefromrow)||
|[CDockingPanesRow::배열파네스](#arrangepanes)|지정된 여백 및 간격 매개 변수에 따라 창을 일렬로 정렬합니다.|
|[CDockingPanesRow::CalcFixedLayout](#calcfixedlayout)||
|[CDockingPanesRow::Create](#create)||
|[CDockingPanesRow::ExpandStretchedPanes](#expandstretchedpanes)||
|[CDockingPanesRow::ExpandStretchedPanesRect](#expandstretchedpanesrect)||
|[CDockingPanesRow::FixupVirtualRects](#fixupvirtualrects)||
|[CDockingPanesRow::GetAvailableLength](#getavailablelength)||
|[CDockingPanesRow::GetAvailableSpace](#getavailablespace)||
|[CDockingPanesRow::GetClientRect](#getclientrect)||
|[CDockingPanesRow::GetDockSite](#getdocksite)||
|[CDockingPanesRow::GetExtraSpace](#getextraspace)||
|[CDockingPanesRow::GetGroupFromPane](#getgroupfrompane)||
|[CDockingPanesRow::GetID](#getid)||
|[CDockingPanesRow::GetMaxPaneSize](#getmaxpanesize)||
|[CDockingPanesRow::GetPaneCount](#getpanecount)||
|[CDockingPanesRow::GetPaneList](#getpanelist)||
|[CDockingPanesRow::GetRowAlignment](#getrowalignment)||
|[CDockingPanesRow::GetRowHeight](#getrowheight)||
|[CDockingPanesRow::GetRowOffset](#getrowoffset)||
|[CDockingPanesRow::GetVisibleCount](#getvisiblecount)||
|[CDockingPanesRow::GetWindowRect](#getwindowrect)||
|[CDockingPanesRow::HasPane](#haspane)||
|[CDockingPanesRow::IsEmpty](#isempty)||
|[CDockingPanesRow::IsExclusiveRow](#isexclusiverow)||
|[CDockingPanesRow::IsHorizontal](#ishorizontal)||
|[CDockingPanesRow::IsVisible](#isvisible)||
|[CDockingPanesRow::Move](#move)||
|[CDockingPanesRow::MovePane](#movepane)||
|[CDockingPanesRow::OnResizePane](#onresizepane)||
|[CDockingPanesRow::RedrawAll](#redrawall)||
|[CDockingPanesRow::RemovePane](#removepane)||
|[CDockingPanesRow::ReplacePane](#replacepane)||
|[CDockingPanesRow::RepositionPanes](#repositionpanes)||
|[CDockingPanesRow::Resize](#resize)||
|[CDockingPanesRow::ResizeByPaneDivider](#resizebypanedivider)||
|[CDockingPanesRow::ScreenToClient](#screentoclient)||
|[CDockingPanesRow::SetExtra](#setextra)||
|[CDockingPanesRow::ShowDockSiteRow](#showdocksiterow)||
|[CDockingPanesRow::ShowPane](#showpane)||
|[CDockingPanesRow::UpdateVisibleState](#updatevisiblestate)||

## <a name="remarks"></a>설명

`CDockingPanesRow` 개체는 도킹 사이트 개체에 의해 내부적으로 만들어집니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCAutoHideBar` 개체에서 `CDockingPanesRow` 개체를 가져오는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cdockingpanesrow-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDockingPanesRow.h

## <a name="cdockingpanesrowaddpane"></a><a name="addpane"></a>CDockingPanesRow::애드파네

```
virtual void AddPane(
    CPane* pControlBar,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL,
    BOOL bAddLast = FALSE);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨트롤바*<br/>

【인】 *독 방법*<br/>

【인】 *lpRect*<br/>

【인】 *bAddLast*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowaddpanefromrow"></a><a name="addpanefromrow"></a>CDockingPanesRow::애드파네From로우

```
virtual void AddPaneFromRow(
    CPane* pControlBar,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨트롤바*<br/>

【인】 *독 방법*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowarrangepanes"></a><a name="arrangepanes"></a>CDockingPanesRow::배열파네스

지정된 여백 및 간격 매개변수에 따라 도킹 창을 행으로 정렬합니다.

```
virtual void ArrangePanes(
    int nMargin,
    int nSpacing);
```

### <a name="parameters"></a>매개 변수

*nMargin*<br/>
【인】 행의 왼쪽 위 모서리에서 첫 번째 창의 오프셋(픽셀)을 지정합니다.

*n 간격*<br/>
【인】 창 사이의 간격을 픽셀 단위로 지정합니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 도킹할 행을 정렬합니다. 이 메서드를 호출한 `CDockingPanesRow::FixupVirtualRects(FALSE, NULL)`후 을 호출해야 합니다.

## <a name="cdockingpanesrowcalcfixedlayout"></a><a name="calcfixedlayout"></a>CDockingPanesRow::석회화 레이아웃

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

## <a name="cdockingpanesrowcdockingpanesrow"></a><a name="cdockingpanesrow"></a>CDockingPanesRow::CDockingPanesRow

```
CDockingPanesRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nHeight);
```

### <a name="parameters"></a>매개 변수

【인】 *p부모독바*<br/>

【인】 *n오프셋*<br/>

【인】 *n높이*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowcreate"></a><a name="create"></a>CDockingPanesRow::만들기

```
virtual BOOL Create();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowexpandstretchedpanes"></a><a name="expandstretchedpanes"></a>CDockingPanesRow::확장늘보글

```cpp
void ExpandStretchedPanes();
```

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowexpandstretchedpanesrect"></a><a name="expandstretchedpanesrect"></a>CDockingPanesRow::확장늘보글파네스렉트

```cpp
void ExpandStretchedPanesRect();
```

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowfixupvirtualrects"></a><a name="fixupvirtualrects"></a>CDockingPanesRow::픽스업가상 수정

```cpp
void FixupVirtualRects(
    bool bMoveBackToVirtualRect,
    CPane* pBarToExclude = NULL);
```

### <a name="parameters"></a>매개 변수

【인】 *bMoveBackTo가상렉트*<br/>

【인】 *pBarTo제외*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetavailablelength"></a><a name="getavailablelength"></a>CDockingPanesRow::사용 가능 길이

```
virtual int GetAvailableLength(BOOL bUseVirtualRect = FALSE) const;
```

### <a name="parameters"></a>매개 변수

【인】 *bUse가상렉트*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetavailablespace"></a><a name="getavailablespace"></a>CDockingPanesRow::사용 가능 공간

```
virtual void GetAvailableSpace(CRect& rect);
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetclientrect"></a><a name="getclientrect"></a>CDockingPanesRow::GetClientRect

```cpp
void GetClientRect(CRect& rect) const;
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetdocksite"></a><a name="getdocksite"></a>CDockingPanesRow::GetDockSite

```
CDockSite* GetDockSite() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetextraspace"></a><a name="getextraspace"></a>CDockingPanesRow::GetExtraSpace

```
int GetExtraSpace() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetgroupfrompane"></a><a name="getgroupfrompane"></a>CDockingPanesRow::겟그룹From파인

```cpp
void GetGroupFromPane(
    CPane* pBar,
    CObList& lst);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

【인】 *lst*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetid"></a><a name="getid"></a>CDockingPanesRow::GetID

```
int GetID() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetmaxpanesize"></a><a name="getmaxpanesize"></a>CDockingPanesRow::겟맥스파네사이즈

```
int GetMaxPaneSize(BOOL bSkipHiddenBars = TRUE) const;
```

### <a name="parameters"></a>매개 변수

【인】 *b스킵히든바*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetpanecount"></a><a name="getpanecount"></a>CDockingPanesRow::겟파인카운트

```
int GetPaneCount() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetpanelist"></a><a name="getpanelist"></a>CDockingPanesRow::GetPaneList

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetrowalignment"></a><a name="getrowalignment"></a>CDockingPanesRow::GetRow정렬

```
DWORD GetRowAlignment() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetrowheight"></a><a name="getrowheight"></a>CDockingPanesRow::GetRowHeight높이

```
int GetRowHeight() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetrowoffset"></a><a name="getrowoffset"></a>CDockingPanesRow::GetRowoffset

```
int GetRowOffset() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetvisiblecount"></a><a name="getvisiblecount"></a>CDockingPanesRow::GetVisibleCount

```
virtual int GetVisibleCount();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowgetwindowrect"></a><a name="getwindowrect"></a>CDockingPanesRow::GetWindowRect

```cpp
void GetWindowRect(CRect& rect) const;
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowhaspane"></a><a name="haspane"></a>코킹파네스로우::하스파네

```
BOOL HasPane(CBasePane* pControlBar);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨트롤바*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowisempty"></a><a name="isempty"></a>CDockingPanesRow::비어 있음

```
virtual BOOL IsEmpty() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowisexclusiverow"></a><a name="isexclusiverow"></a>CDockingPanesRow::Is독점행

```
virtual BOOL IsExclusiveRow() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowishorizontal"></a><a name="ishorizontal"></a>CDockingPanesRow::Is수평

```
bool IsHorizontal() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowisvisible"></a><a name="isvisible"></a>CDockingPanesRow::가보입니다.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowmove"></a><a name="move"></a>CDockingPanesRow::이동

```
virtual void Move(int nOffset);
```

### <a name="parameters"></a>매개 변수

【인】 *n오프셋*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowmovepane"></a><a name="movepane"></a>CDockingPanesRow::무브파네

```cpp
void MovePane(
    CPane* pControlBar,
    CPoint ptOffset,
    BOOL bSwapControlBars,
    HDWP& hdwp);

void MovePane(
    CPane* pControlBar,
    CRect rectTarget,
    HDWP& hdwp);

void MovePane(
    CPane* pControlBar,
    int nOffset,
    bool bForward,
    HDWP& hdwp);

void MovePane(
    CPane* pControlBar,
    int nAbsolutOffset,
    HDWP& hdwp);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨트롤바*<br/>

【인】 *ptOffset*<br/>

【인】 *b스왑컨트롤바*<br/>

【인】 *HDWP*<br/>

【인】 *정류 대상*<br/>

【인】 *n오프셋*<br/>

【인】 *b앞으로*<br/>

【인】 *nAbsolut오프셋*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowonresizepane"></a><a name="onresizepane"></a>CDockingPanesRow::온리사이즈파네

```
virtual void OnResizePane(CBasePane* pControlBar);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨트롤바*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowredrawall"></a><a name="redrawall"></a>CDockingPanesRow::다시 그리기 모두

```cpp
void RedrawAll();
```

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowremovepane"></a><a name="removepane"></a>CDockingPanesRow::제거파네

```
virtual void RemovePane(CPane* pControlBar);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨트롤바*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowreplacepane"></a><a name="replacepane"></a>CDockingPanesRow::대체파네

```
virtual BOOL ReplacePane(
    CPane* pBarOld,
    CPane* pBarNew);
```

### <a name="parameters"></a>매개 변수

【인】 *pBarOld*<br/>

【인】 *pBarNew*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowrepositionpanes"></a><a name="repositionpanes"></a>CDockingPanesRow::재배치파네

```
virtual void RepositionPanes(
    CRect& rectNewParentBarArea,
    UINT nSide = (UINT)-1,
    BOOL bExpand = FALSE,
    int nOffset = 0);
```

### <a name="parameters"></a>매개 변수

【인】 *정류뉴부모바에어리어*<br/>

【인】 *nSide*<br/>

【인】 *b확장*<br/>

【인】 *n오프셋*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowresize"></a><a name="resize"></a>CDockingPanesRow::크기 조정

```
virtual int Resize(int nOffset);
```

### <a name="parameters"></a>매개 변수

【인】 *n오프셋*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowresizebypanedivider"></a><a name="resizebypanedivider"></a>CDockingPanesRow::크기 조정파네 디바이더

```
virtual int ResizeByPaneDivider(int /*ignored*/);
```

### <a name="parameters"></a>매개 변수

【인】 *무시됨*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowscreentoclient"></a><a name="screentoclient"></a>CDockingPanesRow::스크린토클라이언트

```cpp
void ScreenToClient(CRect& rect) const;
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowsetextra"></a><a name="setextra"></a>CDockingPanesRow::세트엑스트라

```cpp
void SetExtra(
    int nExtraSpace,
    AFX_ROW_ALIGNMENT rowExtraAlign);
```

### <a name="parameters"></a>매개 변수

【인】 *n엑스트라스페이스*<br/>

【인】 *행엑스트라정렬*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowshowdocksiterow"></a><a name="showdocksiterow"></a>CDockingPanesRow::쇼독사이트로우

```
virtual void ShowDockSiteRow(
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>매개 변수

【인】 *bShow*<br/>

【인】 *bDelay*<br/>

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowshowpane"></a><a name="showpane"></a>도킹파네스로우::쇼파네

```
virtual BOOL ShowPane(
    CPane* pControlBar,
    BOOL bShow,
    BOOL bDelay = FALSE);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨트롤바*<br/>

【인】 *bShow*<br/>

【인】 *bDelay*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockingpanesrowupdatevisiblestate"></a><a name="updatevisiblestate"></a>CDockingPanesRow::업데이트가 보이는 상태

```
virtual void UpdateVisibleState(BOOL bDelay);
```

### <a name="parameters"></a>매개 변수

【인】 *bDelay*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[CDockSite Class](../../mfc/reference/cdocksite-class.md)<br/>
[CPane 클래스](../../mfc/reference/cpane-class.md)
