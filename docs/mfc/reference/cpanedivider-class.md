---
title: 크파네 디바이더 클래스
ms.date: 11/04/2016
f1_keywords:
- CPaneDivider
- AFXPANEDIVIDER/CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::AddPaneContainer
- AFXPANEDIVIDER/CPaneDivider::AddPane
- AFXPANEDIVIDER/CPaneDivider::AddRecentPane
- AFXPANEDIVIDER/CPaneDivider::CalcExpectedDockedRect
- AFXPANEDIVIDER/CPaneDivider::CalcFixedLayout
- AFXPANEDIVIDER/CPaneDivider::CheckVisibility
- AFXPANEDIVIDER/CPaneDivider::CreateEx
- AFXPANEDIVIDER/CPaneDivider::DoesAllowDynInsertBefore
- AFXPANEDIVIDER/CPaneDivider::DoesContainFloatingPane
- AFXPANEDIVIDER/CPaneDivider::FindPaneContainer
- AFXPANEDIVIDER/CPaneDivider::FindTabbedPane
- AFXPANEDIVIDER/CPaneDivider::GetDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::GetFirstPane
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividerStyle
- AFXPANEDIVIDER/CPaneDivider::GetRootContainerRect
- AFXPANEDIVIDER/CPaneDivider::GetWidth
- AFXPANEDIVIDER/CPaneDivider::Init
- AFXPANEDIVIDER/CPaneDivider::InsertPane
- AFXPANEDIVIDER/CPaneDivider::IsAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::IsDefault
- AFXPANEDIVIDER/CPaneDivider::IsHorizontal
- AFXPANEDIVIDER/CPaneDivider::Move
- AFXPANEDIVIDER/CPaneDivider::NotifyAboutRelease
- AFXPANEDIVIDER/CPaneDivider::OnShowPane
- AFXPANEDIVIDER/CPaneDivider::ReleaseEmptyPaneContainers
- AFXPANEDIVIDER/CPaneDivider::RemovePane
- AFXPANEDIVIDER/CPaneDivider::ReplacePane
- AFXPANEDIVIDER/CPaneDivider::RepositionPanes
- AFXPANEDIVIDER/CPaneDivider::Serialize
- AFXPANEDIVIDER/CPaneDivider::SetAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::SetPaneContainerManager
- AFXPANEDIVIDER/CPaneDivider::ShowWindow
- AFXPANEDIVIDER/CPaneDivider::StoreRecentDockSiteInfo
- AFXPANEDIVIDER/CPaneDivider::StoreRecentTabRelatedInfo
- AFXPANEDIVIDER/CPaneDivider::GetPanes
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividers
- AFXPANEDIVIDER/CPaneDivider::m_nDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::m_pSliderRTC
helpviewer_keywords:
- CPaneDivider [MFC], CPaneDivider
- CPaneDivider [MFC], AddPaneContainer
- CPaneDivider [MFC], AddPane
- CPaneDivider [MFC], AddRecentPane
- CPaneDivider [MFC], CalcExpectedDockedRect
- CPaneDivider [MFC], CalcFixedLayout
- CPaneDivider [MFC], CheckVisibility
- CPaneDivider [MFC], CreateEx
- CPaneDivider [MFC], DoesAllowDynInsertBefore
- CPaneDivider [MFC], DoesContainFloatingPane
- CPaneDivider [MFC], FindPaneContainer
- CPaneDivider [MFC], FindTabbedPane
- CPaneDivider [MFC], GetDefaultWidth
- CPaneDivider [MFC], GetFirstPane
- CPaneDivider [MFC], GetPaneDividerStyle
- CPaneDivider [MFC], GetRootContainerRect
- CPaneDivider [MFC], GetWidth
- CPaneDivider [MFC], Init
- CPaneDivider [MFC], InsertPane
- CPaneDivider [MFC], IsAutoHideMode
- CPaneDivider [MFC], IsDefault
- CPaneDivider [MFC], IsHorizontal
- CPaneDivider [MFC], Move
- CPaneDivider [MFC], NotifyAboutRelease
- CPaneDivider [MFC], OnShowPane
- CPaneDivider [MFC], ReleaseEmptyPaneContainers
- CPaneDivider [MFC], RemovePane
- CPaneDivider [MFC], ReplacePane
- CPaneDivider [MFC], RepositionPanes
- CPaneDivider [MFC], Serialize
- CPaneDivider [MFC], SetAutoHideMode
- CPaneDivider [MFC], SetPaneContainerManager
- CPaneDivider [MFC], ShowWindow
- CPaneDivider [MFC], StoreRecentDockSiteInfo
- CPaneDivider [MFC], StoreRecentTabRelatedInfo
- CPaneDivider [MFC], GetPanes
- CPaneDivider [MFC], GetPaneDividers
- CPaneDivider [MFC], m_nDefaultWidth
- CPaneDivider [MFC], m_pSliderRTC
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
ms.openlocfilehash: 0ebac4e18f65d789d5196266d57184744ad5ad28
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753620"
---
# <a name="cpanedivider-class"></a>크파네 디바이더 클래스

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

클래스는 `CPaneDivider` 두 개의 창을 분할하거나, 두 개의 창 그룹을 나누거나, 창 그룹을 주 프레임 창의 클라이언트 영역에서 분리합니다.

## <a name="syntax"></a>구문

```
class CPaneDivider : public CBasePane
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CPane 분배기:::CPane 분배기](#cpanedivider)||

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CPane 분배기 ::애드파인 컨테이너](#addpanecontainer)||
|[CPane 분배기::애드파인](#addpane)||
|[CPane 분배기:::AddRecentPane](#addrecentpane)||
|[CPane Divider:::석회화도킹렉트](#calcexpecteddockedrect)||
|[CPane 분배기::석회화 레이아웃](#calcfixedlayout)|[(재정의 CBasePane::석회화 레이아웃.)](../../mfc/reference/cbasepane-class.md#calcfixedlayout)|
|[CPane 분배기::검사 가시성](#checkvisibility)||
|[CPane 분배기::만들기](#createex)|[(CBasePane 재정의::만들기.)](../../mfc/reference/cbasepane-class.md#createex)|
|[CPane Divider::DoesAllowDyn인더인](#doesallowdyninsertbefore)|[(재정의 CBasePane::DoesAllowDyn인가 전에](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CPane Divider::Does포함플로팅파네](#doescontainfloatingpane)||
|[CPane 분배기 ::찾기파인 컨테이너](#findpanecontainer)||
|[CPane 분배기 :::찾기탭판](#findtabbedpane)||
|[CPane 분배기::GetDefault폭](#getdefaultwidth)||
|[CPane 분배기::GetFirstPane](#getfirstpane)||
|[CPane 분배기 ::: 겟파인 디바이더 스타일](#getpanedividerstyle)||
|[CPane 분배기::GetRootContainerRect](#getrootcontainerrect)||
|[CPane 분배기 ::GetWidth](#getwidth)||
|[크파네 디바이더::이니트](#init)||
|[CPane 분배기 ::삽입 창](#insertpane)||
|[크파네 디바이더::IsAutoHideMode](#isautohidemode)|[(재정의 CBasePane::IsAutoHideMode.)](../../mfc/reference/cbasepane-class.md#isautohidemode)|
|[크파네 디바이더::Isdefault](#isdefault)||
|[크파네 디바이더::수평](#ishorizontal)|[(CBasePane 재정의::IsHorizontal.)](../../mfc/reference/cbasepane-class.md#ishorizontal)|
|[CPane 분배기 ::이동](#move)||
|[CPane Divider::알림 릴리스](#notifyaboutrelease)||
|[크파네 디바이더::온쇼파인](#onshowpane)||
|[CPane 분배기::릴리스빈파인 컨테이너](#releaseemptypanecontainers)||
|[CPane 분배기 ::제거창](#removepane)||
|[CPane 분배기 :: 대체판](#replacepane)||
|[CPane Divider::재배치파네](#repositionpanes)||
|[CPane Divider::직렬화](#serialize)|( `CBasePane::Serialize`을 재정의합니다.)|
|[크파네 디바이더::SetAutoHideMode](#setautohidemode)||
|[CPane 분배기::SetPane컨테이너 관리자](#setpanecontainermanager)||
|[크파네 디바이더::쇼윈도우](#showwindow)||
|[CPane Divider:::스토어최근독사이트정보](#storerecentdocksiteinfo)||
|[CPane 분배기:::저장소최근탭관련정보](#storerecenttabrelatedinfo)||

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[크파네 디바이더::겟파인](#getpanes)|[CPaneContainer 클래스에](../../mfc/reference/cpanecontainer-class.md)있는 창 목록을 반환합니다. 이 메서드는 기본 창 구분에 대해서만 호출해야 합니다.|
|[CPane 분배기:::겟파인 분배기](#getpanedividers)|[CPaneContainer 클래스에](../../mfc/reference/cpanecontainer-class.md)있는 창 분할자 목록을 반환합니다. 이 메서드는 기본 창 구분에 대해서만 호출해야 합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CPane Divider::m_nDefaultWidth](#m_ndefaultwidth)|응용 프로그램의 모든 창 구분값의 픽셀로 기본 너비를 지정합니다.|
|[CPane Divider::m_pSliderRTC](#m_psliderrtc)|-derived 개체에 대한 런타임 `CPaneDivider`클래스 정보에 대한 포인터를 보유합니다.|

## <a name="remarks"></a>설명

프레임워크는 `CPaneDivider` 창이 도킹될 때 자동으로 개체를 만듭니다.

창 분할에는 두 가지 유형이 있습니다.

- 기본 창 분할은 창 그룹이 주 프레임 창의 측면에 도킹될 때 만들어집니다. 기본 창 구분은 [CPaneContainerManager 클래스에](../../mfc/reference/cpanecontainermanager-class.md) 대한 포인터를 보유하고 창 그룹(예: 창 크기 조정 또는 다른 창 또는 컨테이너 도킹)에서 대부분의 작업을 컨테이너 관리자로 리디렉션합니다. 각 도킹 창은 기본 창 구분선에 대한 포인터를 유지 관리합니다.

- 일반 창 분할기는 컨테이너에 두 개의 창을 분할합니다. 자세한 내용은 [CPaneContainer 클래스](../../mfc/reference/cpanecontainer-class.md)를 참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `CWorkspaceBar` 개체에서 `CPaneDivider` 개체를 가져오는 방법을 보여 줍니다. 이 코드 조각은 [MDI 탭 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/cpp/cpanedivider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[Cobject](../../mfc/reference/cobject-class.md)\
❏&nbsp;[CCmd Target](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[크파네 디바이더](../../mfc/reference/cpanedivider-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxPane Divider.h

## <a name="cpanedividersetautohidemode"></a><a name="setautohidemode"></a>크파네 디바이더::SetAutoHideMode

```cpp
void SetAutoHideMode(BOOL bMode);
```

### <a name="parameters"></a>매개 변수

【인】 *b 모드*<br/>

### <a name="remarks"></a>설명

## <a name="cpanedividersetpanecontainermanager"></a><a name="setpanecontainermanager"></a>CPane 분배기::SetPane컨테이너 관리자

```cpp
void SetPaneContainerManager(CPaneContainerManager* p);
```

### <a name="parameters"></a>매개 변수

【인】 *p*<br/>

### <a name="remarks"></a>설명

## <a name="cpanedivideraddpane"></a><a name="addpane"></a>CPane 분배기::애드파인

```
virtual void AddPane(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

### <a name="remarks"></a>설명

## <a name="cpanedivideraddpanecontainer"></a><a name="addpanecontainer"></a>CPane 분배기 ::애드파인 컨테이너

```
virtual BOOL AddPaneContainer(
    CPaneContainerManager& barContainerManager,
    BOOL bOuterEdge);

virtual BOOL AddPaneContainer(
    CDockablePane* pTargetBar,
    CPaneContainerManager& barContainerManager,
    DWORD dwAlignment);
```

### <a name="parameters"></a>매개 변수

【인】 *바 컨테이너 관리자*<br/>
【인】 *bOuterEdge*<br/>
【인】 *pTargetBar*<br/>
【인】 *dw정렬*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedivideraddrecentpane"></a><a name="addrecentpane"></a>CPane 분배기:::AddRecentPane

```
virtual CDockablePane* AddRecentPane(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividercalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CPane Divider:::석회화도킹렉트

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

## <a name="cpanedividercalcfixedlayout"></a><a name="calcfixedlayout"></a>CPane 분배기::석회화 레이아웃

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

## <a name="cpanedividercheckvisibility"></a><a name="checkvisibility"></a>CPane 분배기::검사 가시성

```
virtual BOOL CheckVisibility();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividercpanedivider"></a><a name="cpanedivider"></a>CPane 분배기:::CPane 분배기

```
CPaneDivider();

CPaneDivider(
    BOOL bDefaultSlider,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>매개 변수

【인】 *b기본 슬라이더*<br/>
【인】 *pParent*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividercreateex"></a><a name="createex"></a>CPane 분배기::만들기

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext);
```

### <a name="parameters"></a>매개 변수

【인】 *dwStyleEx*<br/>
【인】 *dw스타일*<br/>
[in] *rect*<br/>
【인】 *pParentWnd*<br/>
【인】 *니드 (미국)의*<br/>
【인】 *p컨텍스트*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividerdoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CPane Divider::DoesAllowDyn인더인

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividerdoescontainfloatingpane"></a><a name="doescontainfloatingpane"></a>CPane Divider::Does포함플로팅파네

```
virtual BOOL DoesContainFloatingPane();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividerfindpanecontainer"></a><a name="findpanecontainer"></a>CPane 분배기 ::찾기파인 컨테이너

```
CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,
    BOOL& bLeftBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>
【인】 *bLeftBar*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividerfindtabbedpane"></a><a name="findtabbedpane"></a>CPane 분배기 :::찾기탭판

```
CDockablePane* FindTabbedPane(UINT nID);
```

### <a name="parameters"></a>매개 변수

【인】 *니드 (미국)의*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividergetdefaultwidth"></a><a name="getdefaultwidth"></a>CPane 분배기::GetDefault폭

```
static int __stdcall GetDefaultWidth();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividergetfirstpane"></a><a name="getfirstpane"></a>CPane 분배기::GetFirstPane

```
const CBasePane* GetFirstPane() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividergetpanedividers"></a><a name="getpanedividers"></a>CPane 분배기:::겟파인 분배기

[CPaneContainer 클래스에](../../mfc/reference/cpanecontainer-class.md)있는 창 분할자 목록을 반환합니다. 이 메서드는 기본 창 구분에 대해서만 호출해야 합니다.

```cpp
void GetPaneDividers(CObList& lstSliders);
```

### <a name="parameters"></a>매개 변수

*lst슬라이더*<br/>
【아웃】 창 컨테이너에 있는 창 분할자 목록을 포함합니다.

### <a name="remarks"></a>설명

이 메서드는 기본 창 구분에 대해서만 호출해야 합니다. 기본 창 분할기는 전체 창 컨테이너의 크기를 조정하는 분할기입니다.

## <a name="cpanedividergetpanedividerstyle"></a><a name="getpanedividerstyle"></a>CPane 분배기 ::: 겟파인 디바이더 스타일

```
DWORD GetPaneDividerStyle() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividergetpanes"></a><a name="getpanes"></a>크파네 디바이더::겟파인

[CPaneContainer 클래스에](../../mfc/reference/cpanecontainer-class.md)있는 창 목록을 반환합니다. 이 메서드는 기본 창 구분값을 검색하기 위해서만 호출해야 합니다.

```cpp
void GetPanes(CObList& lstBars);
```

### <a name="parameters"></a>매개 변수

*lstBar*<br/>
【아웃】 창 컨테이너에 있는 창 목록을 포함합니다.

### <a name="remarks"></a>설명

이 메서드는 기본 창 구분에 대해서만 호출해야 합니다. 기본 창 분할기는 전체 창 컨테이너의 크기를 조정하는 분할기입니다.

## <a name="cpanedividergetrootcontainerrect"></a><a name="getrootcontainerrect"></a>CPane 분배기::GetRootContainerRect

```
CRect GetRootContainerRect();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividergetwidth"></a><a name="getwidth"></a>CPane 분배기 ::GetWidth

```
int GetWidth() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividerinit"></a><a name="init"></a>크파네 디바이더::이니트

```cpp
void Init(
    BOOL bDefaultSlider = FALSE,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>매개 변수

【인】 *b기본 슬라이더*<br/>
【인】 *pParent*<br/>

### <a name="remarks"></a>설명

## <a name="cpanedividerinsertpane"></a><a name="insertpane"></a>CPane 분배기 ::삽입 창

```
virtual BOOL InsertPane(
    CDockablePane* pBarToInsert,
    CDockablePane* pTargetBar,
    DWORD dwAlignment,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>매개 변수

【인】 *pBarTo인서*<br/>
【인】 *pTargetBar*<br/>
【인】 *dw정렬*<br/>
【인】 *lpRect*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividerisautohidemode"></a><a name="isautohidemode"></a>크파네 디바이더::IsAutoHideMode

```
BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividerisdefault"></a><a name="isdefault"></a>크파네 디바이더::Isdefault

```
BOOL IsDefault() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividerishorizontal"></a><a name="ishorizontal"></a>크파네 디바이더::수평

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividerm_ndefaultwidth"></a><a name="m_ndefaultwidth"></a>CPane Divider::m_nDefaultWidth

응용 프로그램의 모든 창 구분사이의 기본 너비(픽셀)를 지정합니다.

```
AFX_IMPORT_DATA static int m_nDefaultWidth;
```

## <a name="cpanedividermove"></a><a name="move"></a>CPane 분배기 ::이동

```
virtual void Move(
    CPoint& ptOffset,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>매개 변수

【인】 *ptOffset*<br/>
【인】 *bAdjust레이아웃*<br/>

### <a name="remarks"></a>설명

## <a name="cpanedividerm_psliderrtc"></a><a name="m_psliderrtc"></a>CPane Divider::m_pSliderRTC

-derived 개체에 대한 런타임 클래스 정보에 대한 포인터를 `CPaneDivider`보유합니다.

```
AFX_IMPORT_DATA static CRuntimeClass* m_pSliderRTC;
```

### <a name="remarks"></a>설명

사용자 지정 창 분할자를 만드는 경우 이 멤버 변수를 설정합니다. 이렇게 하면 창이 그려질 때 프레임워크에서 창 분할기를 만들 수 있습니다.

### <a name="example"></a>예제

다음 예제에서는 멤버 변수를 설정하는 방법을 보여 주며 `m_pSliderRTC` 있습니다.

```
class CMySplitter : public CPaneDivider
{
...
};

CPaneDivider::m_pSliderRTC = RUNTIME_CLASS(CMySpliter);
```

## <a name="cpanedividernotifyaboutrelease"></a><a name="notifyaboutrelease"></a>CPane Divider::알림 릴리스

```
virtual void NotifyAboutRelease();
```

### <a name="remarks"></a>설명

## <a name="cpanedivideronshowpane"></a><a name="onshowpane"></a>크파네 디바이더::온쇼파인

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>
【인】 *bShow*<br/>

### <a name="remarks"></a>설명

## <a name="cpanedividerreleaseemptypanecontainers"></a><a name="releaseemptypanecontainers"></a>CPane 분배기::릴리스빈파인 컨테이너

```cpp
void ReleaseEmptyPaneContainers();
```

### <a name="remarks"></a>설명

## <a name="cpanedividerremovepane"></a><a name="removepane"></a>CPane 분배기 ::제거창

```
virtual void RemovePane(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

### <a name="remarks"></a>설명

## <a name="cpanedividerreplacepane"></a><a name="replacepane"></a>CPane 분배기 :: 대체판

```
virtual BOOL ReplacePane(
    CDockablePane* pBarToReplace,
    CDockablePane* pBarToReplaceWith);
```

### <a name="parameters"></a>매개 변수

【인】 *pBarToReplace*<br/>
【인】 *pBarToReplaceWith*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cpanedividerrepositionpanes"></a><a name="repositionpanes"></a>CPane Divider::재배치파네

```
virtual void RepositionPanes(
    CRect& rectNew,
    HDWP& hdwp);
```

### <a name="parameters"></a>매개 변수

【인】 *렉트뉴*<br/>
【인】 *HDWP*<br/>

### <a name="remarks"></a>설명

## <a name="cpanedividerserialize"></a><a name="serialize"></a>CPane Divider::직렬화

```cpp
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

[in] *ar*<br/>

### <a name="remarks"></a>설명

## <a name="cpanedividershowwindow"></a><a name="showwindow"></a>크파네 디바이더::쇼윈도우

```cpp
void ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>매개 변수

【인】 *nCmdShow*<br/>

### <a name="remarks"></a>설명

## <a name="cpanedividerstorerecentdocksiteinfo"></a><a name="storerecentdocksiteinfo"></a>CPane Divider:::스토어최근독사이트정보

```cpp
void StoreRecentDockSiteInfo(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

### <a name="remarks"></a>설명

## <a name="cpanedividerstorerecenttabrelatedinfo"></a><a name="storerecenttabrelatedinfo"></a>CPane 분배기:::저장소최근탭관련정보

```cpp
void StoreRecentTabRelatedInfo(
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
[CPaneContainer관리자 클래스](../../mfc/reference/cpanecontainermanager-class.md)<br/>
[CPaneContainer 클래스](../../mfc/reference/cpanecontainer-class.md)<br/>
[CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md)<br/>
[CBasePane 클래스](../../mfc/reference/cbasepane-class.md)
