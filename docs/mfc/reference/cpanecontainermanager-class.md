---
title: CPaneContainer관리자 클래스
ms.date: 11/04/2016
f1_keywords:
- CPaneContainerManager
- AFXPANECONTAINERMANAGER/CPaneContainerManager
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneContainerManager
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneContainerManagerToDockablePane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPanesToList
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneToList
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneToRecentPaneContainer
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CalcRects
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CanBeAttached
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CheckAndRemoveNonValidPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CheckForMiniFrameAndCaption
- AFXPANECONTAINERMANAGER/CPaneContainerManager::Create
- AFXPANECONTAINERMANAGER/CPaneContainerManager::DoesAllowDynInsertBefore
- AFXPANECONTAINERMANAGER/CPaneContainerManager::DoesContainFloatingPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::EnableGrippers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::FindPaneContainer
- AFXPANECONTAINERMANAGER/CPaneContainerManager::FindTabbedPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetAvailableSpace
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetDefaultPaneDivider
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetDockSiteFrameWnd
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetFirstPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetFirstVisiblePane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetMinMaxOffset
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetMinSize
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetNodeCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetPaneContainerRTC
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetPaneCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetTotalRefCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetVisiblePaneCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetWindowRect
- AFXPANECONTAINERMANAGER/CPaneContainerManager::HideAll
- AFXPANECONTAINERMANAGER/CPaneContainerManager::InsertPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::IsAutoHideMode
- AFXPANECONTAINERMANAGER/CPaneContainerManager::IsEmpty
- AFXPANECONTAINERMANAGER/CPaneContainerManager::IsRootPaneContainerVisible
- AFXPANECONTAINERMANAGER/CPaneContainerManager::NotifyPaneDivider
- AFXPANECONTAINERMANAGER/CPaneContainerManager::OnPaneDividerMove
- AFXPANECONTAINERMANAGER/CPaneContainerManager::OnShowPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::PaneFromPoint
- AFXPANECONTAINERMANAGER/CPaneContainerManager::ReleaseEmptyPaneContainers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemoveAllPanesAndPaneDividers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemoveNonValidPanes
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemovePaneDivider
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemovePaneFromPaneContainer
- AFXPANECONTAINERMANAGER/CPaneContainerManager::ReplacePane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::ResizePaneContainers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::Serialize
- AFXPANECONTAINERMANAGER/CPaneContainerManager::SetDefaultPaneDividerForPanes
- AFXPANECONTAINERMANAGER/CPaneContainerManager::SetPaneContainerRTC
- AFXPANECONTAINERMANAGER/CPaneContainerManager::SetResizeMode
- AFXPANECONTAINERMANAGER/CPaneContainerManager::StoreRecentDockSiteInfo
helpviewer_keywords:
- CPaneContainerManager [MFC], AddPane
- CPaneContainerManager [MFC], AddPaneContainerManager
- CPaneContainerManager [MFC], AddPaneContainerManagerToDockablePane
- CPaneContainerManager [MFC], AddPanesToList
- CPaneContainerManager [MFC], AddPaneToList
- CPaneContainerManager [MFC], AddPaneToRecentPaneContainer
- CPaneContainerManager [MFC], CalcRects
- CPaneContainerManager [MFC], CanBeAttached
- CPaneContainerManager [MFC], CheckAndRemoveNonValidPane
- CPaneContainerManager [MFC], CheckForMiniFrameAndCaption
- CPaneContainerManager [MFC], Create
- CPaneContainerManager [MFC], DoesAllowDynInsertBefore
- CPaneContainerManager [MFC], DoesContainFloatingPane
- CPaneContainerManager [MFC], EnableGrippers
- CPaneContainerManager [MFC], FindPaneContainer
- CPaneContainerManager [MFC], FindTabbedPane
- CPaneContainerManager [MFC], GetAvailableSpace
- CPaneContainerManager [MFC], GetDefaultPaneDivider
- CPaneContainerManager [MFC], GetDockSiteFrameWnd
- CPaneContainerManager [MFC], GetFirstPane
- CPaneContainerManager [MFC], GetFirstVisiblePane
- CPaneContainerManager [MFC], GetMinMaxOffset
- CPaneContainerManager [MFC], GetMinSize
- CPaneContainerManager [MFC], GetNodeCount
- CPaneContainerManager [MFC], GetPaneContainerRTC
- CPaneContainerManager [MFC], GetPaneCount
- CPaneContainerManager [MFC], GetTotalRefCount
- CPaneContainerManager [MFC], GetVisiblePaneCount
- CPaneContainerManager [MFC], GetWindowRect
- CPaneContainerManager [MFC], HideAll
- CPaneContainerManager [MFC], InsertPane
- CPaneContainerManager [MFC], IsAutoHideMode
- CPaneContainerManager [MFC], IsEmpty
- CPaneContainerManager [MFC], IsRootPaneContainerVisible
- CPaneContainerManager [MFC], NotifyPaneDivider
- CPaneContainerManager [MFC], OnPaneDividerMove
- CPaneContainerManager [MFC], OnShowPane
- CPaneContainerManager [MFC], PaneFromPoint
- CPaneContainerManager [MFC], ReleaseEmptyPaneContainers
- CPaneContainerManager [MFC], RemoveAllPanesAndPaneDividers
- CPaneContainerManager [MFC], RemoveNonValidPanes
- CPaneContainerManager [MFC], RemovePaneDivider
- CPaneContainerManager [MFC], RemovePaneFromPaneContainer
- CPaneContainerManager [MFC], ReplacePane
- CPaneContainerManager [MFC], ResizePaneContainers
- CPaneContainerManager [MFC], Serialize
- CPaneContainerManager [MFC], SetDefaultPaneDividerForPanes
- CPaneContainerManager [MFC], SetPaneContainerRTC
- CPaneContainerManager [MFC], SetResizeMode
- CPaneContainerManager [MFC], StoreRecentDockSiteInfo
ms.assetid: 3d974c15-a62f-4648-bb5b-cc31ab7950af
ms.openlocfilehash: 6b4c406360158795b9c9554bfd70e7d41875be13
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753641"
---
# <a name="cpanecontainermanager-class"></a>CPaneContainer관리자 클래스

클래스는 `CPaneContainerManager` 현재 도킹 레이아웃의 저장소 및 표시를 관리합니다.
자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CPaneContainerManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CPane 컨테이너 관리자::애드파인](#addpane)||
|[CPane 컨테이너 관리자::애드파네 컨테이너 관리자](#addpanecontainermanager)||
|[CPane 컨테이너 관리자::애드파네 컨테이너관리자토도킹파네](#addpanecontainermanagertodockablepane)||
|[CPane 컨테이너 관리자::애드파네스토리스트](#addpanestolist)||
|[CPane 컨테이너 관리자::애드파네토리스트](#addpanetolist)||
|[CPane컨테이너 관리자::애드파네토최근패네컨테이너](#addpanetorecentpanecontainer)||
|[CPane 컨테이너 관리자::칼크렉트](#calcrects)||
|[CPane 컨테이너 관리자::수 연결](#canbeattached)||
|[CPane 컨테이너 관리자::체크앤리Remove비유효파인](#checkandremovenonvalidpane)||
|[CPane 컨테이너 관리자::체크포미니프레임앤캡션](#checkforminiframeandcaption)||
|[CPane컨테이너 관리자::만들기](#create)||
|[CPaneContainer관리자::DoesAllowDyn인더인](#doesallowdyninsertbefore)||
|[CPaneContainer관리자::Does포함플로팅파네](#doescontainfloatingpane)||
|[CPaneContainer 관리자::인에이블그리퍼](#enablegrippers)||
|[CPane컨테이너 관리자::찾기창](#findpanecontainer)||
|[CPane컨테이너 관리자::찾기탭판](#findtabbedpane)||
|[CPane 컨테이너 관리자::사용 가능 공간](#getavailablespace)||
|[CPane 컨테이너 관리자::GetDefaultPane 분배기](#getdefaultpanedivider)||
|[CPane컨테이너 관리자::GetDockSiteFrameWnd](#getdocksiteframewnd)||
|[CPane컨테이너 관리자::GetFirstPane](#getfirstpane)||
|[CPane컨테이너 관리자::GetFirstVisiblePane](#getfirstvisiblepane)||
|[CPane 컨테이너 관리자::GetMinMax오프셋](#getminmaxoffset)||
|[CPane컨테이너 관리자::GetMinSize](#getminsize)||
|[CPane컨테이너 관리자::GetNodeCount](#getnodecount)||
|[CPane컨테이너 관리자::겟파인 컨테이너RTC](#getpanecontainerrtc)||
|[CPane컨테이너 관리자::겟파인카운트](#getpanecount)||
|[CPane컨테이너 관리자::GetTotalRefCount](#gettotalrefcount)||
|[CPane컨테이너 관리자::보이지 않는 파인카운트](#getvisiblepanecount)||
|[CPane 컨테이너 관리자::GetWindowRect](#getwindowrect)||
|[CPane컨테이너 관리자::숨기기모두](#hideall)||
|[CPane 컨테이너 관리자::삽입 창](#insertpane)||
|[CPane컨테이너 관리자::IsAutoHideMode](#isautohidemode)||
|[CPane컨테이너 관리자::비어 있음](#isempty)||
|[CPane컨테이너 관리자::IsRootPane컨테이너가 보입니다.](#isrootpanecontainervisible)||
|[CPane 컨테이너 관리자::알림파인 분배기](#notifypanedivider)||
|[CPane컨테이너 관리자::온파네 디바이더무브](#onpanedividermove)||
|[CPane 컨테이너 관리자::온쇼파인](#onshowpane)||
|[CPane컨테이너 관리자::P인FromPoint](#panefrompoint)||
|[CPane 컨테이너 관리자::릴리스빈파인 컨테이너](#releaseemptypanecontainers)||
|[CPane컨테이너 관리자::제거AllPanesAndPane 분배기](#removeallpanesandpanedividers)||
|[CPane 컨테이너 관리자::제거비유효 파인](#removenonvalidpanes)||
|[CPane컨테이너 관리자::제거파네 분배기](#removepanedivider)||
|[CPane컨테이너 관리자::제거페네에서파네컨테이너](#removepanefrompanecontainer)||
|[CPane컨테이너 관리자::대체창](#replacepane)||
|[CPane 컨테이너 관리자::크기 조정 컨테이너](#resizepanecontainers)||
|[CPaneContainer 관리자::직렬화](#serialize)|이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다. ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)를 재정의합니다.)|
|[CPane 컨테이너 관리자::설정기본파인 분배기포파네](#setdefaultpanedividerforpanes)||
|[CPane컨테이너 관리자::세파네 컨테이너RTC](#setpanecontainerrtc)||
|[CPane컨테이너 관리자::세트크기 모드](#setresizemode)||
|[CPane 컨테이너 관리자:::저장소최근독사이트정보](#storerecentdocksiteinfo)||

### <a name="remarks"></a>설명

프레임워크는 자동으로 개체의 `CPaneContainerManager` 인스턴스를 만들고 [CPaneDivider 클래스](../../mfc/reference/cpanedivider-class.md) 개체 또는 [CMultiPaneFrameWnd 클래스](../../mfc/reference/cmultipaneframewnd-class.md) 개체에 포함합니다.

클래스는 `CPaneContainerManager` [CPaneContainer](../../mfc/reference/cpanecontainer-class.md) 개체에서 빌드된 이진 트리의 루트에 대 한 포인터를 저장 합니다.

## <a name="example"></a>예제

다음 예제에서는 `CPaneContainerManager` 개체에 대한 참조를 얻는 방법을 보여 줍니다. 이 코드 조각은 창 [크기 설정 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_SetPaneSize#5](../../mfc/reference/codesnippet/cpp/cpanecontainermanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CPaneContainerManager](../../mfc/reference/cpanecontainermanager-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpanecontainermanager.h

## <a name="cpanecontainermanageraddpane"></a><a name="addpane"></a>CPane 컨테이너 관리자::애드파인

```
virtual void AddPane(CDockablePane* pControlBarToAdd);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨트롤바토추가*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanageraddpanecontainermanager"></a><a name="addpanecontainermanager"></a>CPane 컨테이너 관리자::애드파네 컨테이너 관리자

```
virtual BOOL AddPaneContainerManager(
    CPaneContainerManager& srcManager,
    BOOL bOuterEdge);

virtual BOOL AddPaneContainerManager(
    CDockablePane* pTargetControlBar,
    DWORD dwAlignment,
    CPaneContainerManager& srcManager,
    BOOL bCopy);
```

### <a name="parameters"></a>매개 변수

【인】 *srcManager*<br/>
【인】 *bOuterEdge*<br/>
【인】 *pTarget컨트롤바*<br/>
【인】 *dw정렬*<br/>
【인】 *bCopy*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanageraddpanecontainermanagertodockablepane"></a><a name="addpanecontainermanagertodockablepane"></a>CPane 컨테이너 관리자::애드파네 컨테이너관리자토도킹파네

```
virtual BOOL AddPaneContainerManagerToDockablePane(
    CDockablePane* pTargetControlBar,
    CPaneContainerManager& srcManager);
```

### <a name="parameters"></a>매개 변수

【인】 *pTarget컨트롤바*<br/>
【인】 *srcManager*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanageraddpanestolist"></a><a name="addpanestolist"></a>CPane 컨테이너 관리자::애드파네스토리스트

```cpp
void AddPanesToList(
    CObList* plstControlBars,
    CObList* plstSliders);
```

### <a name="parameters"></a>매개 변수

【인】 *plst컨트롤바*<br/>
【인】 *plst슬라이더*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanageraddpanetolist"></a><a name="addpanetolist"></a>CPane 컨테이너 관리자::애드파네토리스트

```cpp
void AddPaneToList(CDockablePane* pControlBarToAdd);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨트롤바토추가*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanageraddpanetorecentpanecontainer"></a><a name="addpanetorecentpanecontainer"></a>CPane컨테이너 관리자::애드파네토최근패네컨테이너

```
virtual CDockablePane* AddPaneToRecentPaneContainer(
    CDockablePane* pBarToAdd,
    CPaneContainer* pRecentContainer);
```

### <a name="parameters"></a>매개 변수

【인】 *pBarToAdd*<br/>
【인】 *p최근 컨테이너*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagercalcrects"></a><a name="calcrects"></a>CPane 컨테이너 관리자::칼크렉트

```cpp
void CalcRects(
    CRect& rectOriginal,
    CRect& rectInserted,
    CRect& rectSlider,
    DWORD& dwSliderStyle,
    DWORD dwAlignment,
    CSize sizeMinOriginal,
    CSize sizeMinInserted);
```

### <a name="parameters"></a>매개 변수

【인】 *정류 오리지널*<br/>
【인】 *정류 삽입*<br/>
【인】 *직사각형 슬라이더*<br/>
【인】 *dw슬라이더 스타일*<br/>
【인】 *dw정렬*<br/>
【인】 *크기원래*<br/>
【인】 *크기삽입*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagercanbeattached"></a><a name="canbeattached"></a>CPane 컨테이너 관리자::수 연결

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagercheckandremovenonvalidpane"></a><a name="checkandremovenonvalidpane"></a>CPane 컨테이너 관리자::체크앤리Remove비유효파인

```
BOOL CheckAndRemoveNonValidPane(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

【인】 *pWnd*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagercheckforminiframeandcaption"></a><a name="checkforminiframeandcaption"></a>CPane 컨테이너 관리자::체크포미니프레임앤캡션

```
virtual BOOL CheckForMiniFrameAndCaption(
    CPoint point,
    CDockablePane** ppTargetControlBar);
```

### <a name="parameters"></a>매개 변수

【인】 *점*<br/>
【인】 *ppTargetControlBar*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagercreate"></a><a name="create"></a>CPane컨테이너 관리자::만들기

```
virtual BOOL Create(
    CWnd* pParentWnd,
    CPaneDivider* pDefaultSlider,
    CRuntimeClass* pContainerRTC = NULL);
```

### <a name="parameters"></a>매개 변수

【인】 *pParentWnd*<br/>
【인】 *p디폴디폴 슬라이더*<br/>
【인】 *p컨테이너RTC*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerdoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CPaneContainer관리자::DoesAllowDyn인더인

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerdoescontainfloatingpane"></a><a name="doescontainfloatingpane"></a>CPaneContainer관리자::Does포함플로팅파네

```
virtual BOOL DoesContainFloatingPane();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerenablegrippers"></a><a name="enablegrippers"></a>CPaneContainer 관리자::인에이블그리퍼

```
virtual void EnableGrippers(BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

【인】 *bEnable*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerfindpanecontainer"></a><a name="findpanecontainer"></a>CPane컨테이너 관리자::찾기창

```
virtual CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,
    BOOL& bLeftBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>
【인】 *bLeftBar*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerfindtabbedpane"></a><a name="findtabbedpane"></a>CPane컨테이너 관리자::찾기탭판

```
CDockablePane* FindTabbedPane(UINT nID);
```

### <a name="parameters"></a>매개 변수

【인】 *니드 (미국)의*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergetavailablespace"></a><a name="getavailablespace"></a>CPane 컨테이너 관리자::사용 가능 공간

```
virtual void GetAvailableSpace(CRect& rect) const;
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergetdefaultpanedivider"></a><a name="getdefaultpanedivider"></a>CPane 컨테이너 관리자::GetDefaultPane 분배기

```
CPaneDivider* GetDefaultPaneDivider() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergetdocksiteframewnd"></a><a name="getdocksiteframewnd"></a>CPane컨테이너 관리자::GetDockSiteFrameWnd

```
virtual CWnd* GetDockSiteFrameWnd();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergetfirstpane"></a><a name="getfirstpane"></a>CPane컨테이너 관리자::GetFirstPane

```
virtual CBasePane* GetFirstPane() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergetfirstvisiblepane"></a><a name="getfirstvisiblepane"></a>CPane컨테이너 관리자::GetFirstVisiblePane

```
virtual CWnd* GetFirstVisiblePane() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergetminmaxoffset"></a><a name="getminmaxoffset"></a>CPane 컨테이너 관리자::GetMinMax오프셋

```
virtual void GetMinMaxOffset(
    CPaneDivider* pSlider,
    int& nMinOffset,
    int& nMaxOffset,
    int& nStep);
```

### <a name="parameters"></a>매개 변수

【인】 *p슬라이더*<br/>
【인】 *nMinOffset*<br/>
【인】 *nMax오프오프*<br/>
【인】 *n스텝*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergetminsize"></a><a name="getminsize"></a>CPane컨테이너 관리자::GetMinSize

```
virtual void GetMinSize(CSize& size);
```

### <a name="parameters"></a>매개 변수

【인】 *크기*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergetnodecount"></a><a name="getnodecount"></a>CPane컨테이너 관리자::GetNodeCount

```
int GetNodeCount() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergetpanecontainerrtc"></a><a name="getpanecontainerrtc"></a>CPane컨테이너 관리자::겟파인 컨테이너RTC

```
CRuntimeClass* GetPaneContainerRTC() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergetpanecount"></a><a name="getpanecount"></a>CPane컨테이너 관리자::겟파인카운트

```
int GetPaneCount() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergettotalrefcount"></a><a name="gettotalrefcount"></a>CPane컨테이너 관리자::GetTotalRefCount

```
int GetTotalRefCount() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergetvisiblepanecount"></a><a name="getvisiblepanecount"></a>CPane컨테이너 관리자::보이지 않는 파인카운트

```
virtual int GetVisiblePaneCount() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagergetwindowrect"></a><a name="getwindowrect"></a>CPane 컨테이너 관리자::GetWindowRect

```
virtual void GetWindowRect(CRect& rect) const;
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerhideall"></a><a name="hideall"></a>CPane컨테이너 관리자::숨기기모두

```
virtual void HideAll();
```

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerinsertpane"></a><a name="insertpane"></a>CPane 컨테이너 관리자::삽입 창

```
virtual BOOL InsertPane(
    CDockablePane* pControlBarToInsert,
    CDockablePane* pTargetControlBar,
    DWORD dwAlignment,
    LPCRECT lpRect = NULL,
    AFX_DOCK_METHOD dockMethod = DM_UNKNOWN);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨트롤바토인서인더*<br/>
【인】 *pTarget컨트롤바*<br/>
【인】 *dw정렬*<br/>
【인】 *lpRect*<br/>
【인】 *독 방법*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerisautohidemode"></a><a name="isautohidemode"></a>CPane컨테이너 관리자::IsAutoHideMode

```
BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerisempty"></a><a name="isempty"></a>CPane컨테이너 관리자::비어 있음

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerisrootpanecontainervisible"></a><a name="isrootpanecontainervisible"></a>CPane컨테이너 관리자::IsRootPane컨테이너가 보입니다.

```
virtual BOOL IsRootPaneContainerVisible() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagernotifypanedivider"></a><a name="notifypanedivider"></a>CPane 컨테이너 관리자::알림파인 분배기

```cpp
void NotifyPaneDivider();
```

### <a name="remarks"></a>설명

## <a name="cpanecontainermanageronpanedividermove"></a><a name="onpanedividermove"></a>CPane컨테이너 관리자::온파네 디바이더무브

```
virtual int OnPaneDividerMove(
    CPaneDivider* pSlider,
    UINT uFlags,
    int nOffset,
    HDWP& hdwp);
```

### <a name="parameters"></a>매개 변수

【인】 *p슬라이더*<br/>
【인】 *uFlags*<br/>
【인】 *n오프셋*<br/>
【인】 *HDWP*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanageronshowpane"></a><a name="onshowpane"></a>CPane 컨테이너 관리자::온쇼파인

```
virtual BOOL OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>
【인】 *bShow*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerpanefrompoint"></a><a name="panefrompoint"></a>CPane컨테이너 관리자::P인FromPoint

```
virtual CDockablePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    BOOL bExactBar,
    BOOL& bIsTabArea,
    BOOL& bCaption);
```

### <a name="parameters"></a>매개 변수

【인】 *점*<br/>
【인】 *n감도*<br/>
【인】 *bExactBar*<br/>
【인】 *비스탭 에어리어*<br/>
【인】 *b캡션*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerreleaseemptypanecontainers"></a><a name="releaseemptypanecontainers"></a>CPane 컨테이너 관리자::릴리스빈파인 컨테이너

```cpp
void ReleaseEmptyPaneContainers();
```

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerremoveallpanesandpanedividers"></a><a name="removeallpanesandpanedividers"></a>CPane컨테이너 관리자::제거AllPanesAndPane 분배기

```cpp
void RemoveAllPanesAndPaneDividers();
```

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerremovenonvalidpanes"></a><a name="removenonvalidpanes"></a>CPane 컨테이너 관리자::제거비유효 파인

```cpp
void RemoveNonValidPanes();
```

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerremovepanedivider"></a><a name="removepanedivider"></a>CPane컨테이너 관리자::제거파네 분배기

```
virtual void RemovePaneDivider(CPaneDivider* pSlider);
```

### <a name="parameters"></a>매개 변수

【인】 *p슬라이더*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerremovepanefrompanecontainer"></a><a name="removepanefrompanecontainer"></a>CPane컨테이너 관리자::제거페네에서파네컨테이너

```
virtual BOOL RemovePaneFromPaneContainer(CDockablePane* pControlBar);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨트롤바*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerreplacepane"></a><a name="replacepane"></a>CPane컨테이너 관리자::대체창

```
virtual BOOL ReplacePane(
    CDockablePane* pBarOld,
    CDockablePane* pBarNew);
```

### <a name="parameters"></a>매개 변수

【인】 *pBarOld*<br/>
【인】 *pBarNew*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerresizepanecontainers"></a><a name="resizepanecontainers"></a>CPane 컨테이너 관리자::크기 조정 컨테이너

```
virtual void ResizePaneContainers(
    UINT nSide,
    BOOL bExpand,
    int nOffset,
    HDWP& hdwp);

virtual void ResizePaneContainers(
    CRect rect,
    HDWP& hdwp);
```

### <a name="parameters"></a>매개 변수

【인】 *nSide*<br/>
【인】 *b확장*<br/>
【인】 *n오프셋*<br/>
【인】 *HDWP*<br/>
[in] *rect*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerserialize"></a><a name="serialize"></a>CPaneContainer 관리자::직렬화

```cpp
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

[in] *ar*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagersetdefaultpanedividerforpanes"></a><a name="setdefaultpanedividerforpanes"></a>CPane 컨테이너 관리자::설정기본파인 분배기포파네

```cpp
void SetDefaultPaneDividerForPanes(CPaneDivider* pSlider);
```

### <a name="parameters"></a>매개 변수

【인】 *p슬라이더*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagersetpanecontainerrtc"></a><a name="setpanecontainerrtc"></a>CPane컨테이너 관리자::세파네 컨테이너RTC

```cpp
void SetPaneContainerRTC(CRuntimeClass* pContainerRTC);
```

### <a name="parameters"></a>매개 변수

【인】 *p컨테이너RTC*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagersetresizemode"></a><a name="setresizemode"></a>CPane컨테이너 관리자::세트크기 모드

```
virtual void SetResizeMode(BOOL bResize);
```

### <a name="parameters"></a>매개 변수

【인】 *b 크기 조정*<br/>

### <a name="remarks"></a>설명

## <a name="cpanecontainermanagerstorerecentdocksiteinfo"></a><a name="storerecentdocksiteinfo"></a>CPane 컨테이너 관리자:::저장소최근독사이트정보

```
virtual void StoreRecentDockSiteInfo(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[CPaneContainer 클래스](../../mfc/reference/cpanecontainer-class.md)<br/>
[크파네 디바이더 클래스](../../mfc/reference/cpanedivider-class.md)
