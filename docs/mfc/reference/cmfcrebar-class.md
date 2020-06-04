---
title: CMFCReBar 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCReBar
- AFXREBAR/CMFCReBar
- AFXREBAR/CMFCReBar::AddBar
- AFXREBAR/CMFCReBar::CalcFixedLayout
- AFXREBAR/CMFCReBar::CanFloat
- AFXREBAR/CMFCReBar::Create
- AFXREBAR/CMFCReBar::EnableDocking
- AFXREBAR/CMFCReBar::GetReBarBandInfoSize
- AFXREBAR/CMFCReBar::GetReBarCtrl
- AFXREBAR/CMFCReBar::OnShowControlBarMenu
- AFXREBAR/CMFCReBar::OnToolHitTest
- AFXREBAR/CMFCReBar::OnUpdateCmdUI
- AFXREBAR/CMFCReBar::SetPaneAlignment
helpviewer_keywords:
- CMFCReBar [MFC], AddBar
- CMFCReBar [MFC], CalcFixedLayout
- CMFCReBar [MFC], CanFloat
- CMFCReBar [MFC], Create
- CMFCReBar [MFC], EnableDocking
- CMFCReBar [MFC], GetReBarBandInfoSize
- CMFCReBar [MFC], GetReBarCtrl
- CMFCReBar [MFC], OnShowControlBarMenu
- CMFCReBar [MFC], OnToolHitTest
- CMFCReBar [MFC], OnUpdateCmdUI
- CMFCReBar [MFC], SetPaneAlignment
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
ms.openlocfilehash: 409c97aba64c97ecf0443d14a70848cc298a44ba
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749995"
---
# <a name="cmfcrebar-class"></a>CMFCReBar 클래스

`CMFCReBar` 개체는 철근 컨트롤에 대한 레이아웃, 지속성 및 상태 정보를 제공하는 컨트롤 막대입니다.
자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCReBar : public CPane
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCReBar::애드바](#addbar)|철근에 밴드를 추가합니다.|
|[CMFCReBar:::석회화레이아웃](#calcfixedlayout)|[(재정의 CBasePane::석회화 레이아웃.)](../../mfc/reference/cbasepane-class.md#calcfixedlayout)|
|[CMFCReBar:::캔플로트](#canfloat)|[(CBasePane 재정의::캔플로팅.)](../../mfc/reference/cbasepane-class.md#canfloat)|
|[CMFCReBar::만들기](#create)|철근 컨트롤을 만들고 오브젝트에 `CMFCReBar` 연결합니다.|
|[CMFCReBar::사용 도킹](#enabledocking)|[(CBasePane 재정의::사용 도킹.)](../../mfc/reference/cbasepane-class.md#enabledocking)|
|[CMFCReBar::겟레바밴드인포사이즈](#getrebarbandinfosize)||
|[CMFCReBar:::겟레바크터](#getrebarctrl)|기본 [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) 공통 컨트롤에 직접 액세스할 수 있습니다.|
|[CMFCReBar::온쇼컨트롤바메뉴](#onshowcontrolbarmenu)|[(재정의 CPane::OnShowControlBar메뉴.)](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu)|
|[CMFCReBar:::온툴히트테스트](#ontoolhittest)|[(재정의 cwnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|
|[CMFCReBar::에 업데이트CmdUI](#onupdatecmdui)|[(재정의 CBasePane::OnUpdateCmdUI](cbasepane-class.md).)|
|[CMFCReBar::세파네정렬](#setpanealignment)|[(재정비: :SetPane정렬.)](../../mfc/reference/cbasepane-class.md#setpanealignment)|

## <a name="remarks"></a>설명

개체에는 `CMFCReBar` 다양한 자식 창이 포함될 수 있습니다. 여기에는 편집 상자, 도구 모음 및 목록 상자가 포함됩니다. 철근의 크기를 프로그래밍 방식으로 조정할 수 있거나 그리퍼 막대를 드래그하여 철근의 크기를 수동으로 조정할 수 있습니다. 철근 오브젝트의 배경을 원하는 비트맵으로 설정할 수도 있습니다.

철근 객체는 도구 모음 오브젝트와 유사하게 행동합니다. 철근 컨트롤에는 하나 이상의 밴드가 포함될 수 있으며 각 밴드에는 그리퍼 막대, 비트맵, 텍스트 레이블 및 자식 창이 포함될 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCReBar` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 철근 컨트롤을 만들고 밴드를 추가하는 방법을 보여 주며, 이 컨트롤에 밴드를 추가하는 방법을 보여 주어 있습니다. 밴드는 내부 도구 모음으로 작동합니다. 이 코드 조각은 [철근 테스트 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[Cobject](../../mfc/reference/cobject-class.md)\
❏&nbsp;[CCmd Target](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[크파네](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CMFCReBar](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxRebar.h

## <a name="cmfcrebaraddbar"></a><a name="addbar"></a>CMFCReBar::애드바

철근에 밴드를 추가합니다.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인, 아웃】 철근에 삽입할 자식 창에 대한 포인터입니다. 참조된 개체에는 **WS_CHILD** 창 스타일이 있어야 합니다.

*pszText*<br/>
【인】 검사수에 표시할 텍스트를 지정합니다. 텍스트는 자식 창의 일부가 아닙니다. 대신 철근 자체에 표시됩니다.

*pbmp*<br/>
【인, 아웃】 철근 배경에 표시할 비트맵을 지정합니다.

*dwStyle*<br/>
【인】 밴드에 적용할 스타일을 포함합니다. 밴드 스타일의 전체 목록은 Windows SDK 설명서의 `fStyle` [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) 구조에 대한 설명을 참조하십시오.

*clrFore*<br/>
【인】 철근의 전경 색상을 나타냅니다.

*clrBack*<br/>
【인】 철근의 배경색을 나타냅니다.

### <a name="return-value"></a>Return Value

밴드가 철근에 성공적으로 추가된 경우 TRUE; 그렇지 않으면 false입니다.

## <a name="cmfcrebarcreate"></a><a name="create"></a>CMFCReBar::만들기

철근 컨트롤을 만들고 [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) 오브젝트에 연결합니다.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
【인, 아웃】 이 철근 컨트롤의 상위 창에 대한 포인터입니다.

*dwCtrl스타일*<br/>
【인】 철근 컨트롤의 스타일을 지정합니다. 기본 스타일 값은 **RBS_BANDBORDERS,** 좁은 선을 표시 하여 철근 컨트롤에서 인접 밴드를 분리합니다. 유효한 스타일 목록은 Windows SDK 설명서의 [철근 제어 스타일을](/windows/win32/Controls/rebar-control-styles) 참조하십시오.

*dwStyle*<br/>
【인】 철근 컨트롤의 창 스타일입니다. 유효한 스타일 목록은 창 [스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)을 참조하십시오.

*nID*<br/>
【인】 단조고명의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

철근이 성공적으로 생성된 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cmfcrebargetrebarctrl"></a><a name="getrebarctrl"></a>CMFCReBar:::겟레바크터

개체에 `CReBarCtrl` 대한 기본 공통 `CMFCReBar` 컨트롤에 직접 액세스할 수 있습니다.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Return Value

기본 `CReBarCtrl` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 철근을 사용자 지정할 때 Windows 철근 공통 제어 기능을 활용합니다.

## <a name="cmfcrebarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFCReBar:::석회화레이아웃

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

## <a name="cmfcrebarcanfloat"></a><a name="canfloat"></a>CMFCReBar:::캔플로트

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcrebarenabledocking"></a><a name="enabledocking"></a>CMFCReBar::사용 도킹

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>매개 변수

【인】 *dwDock스타일*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcrebargetrebarbandinfosize"></a><a name="getrebarbandinfosize"></a>CMFCReBar::겟레바밴드인포사이즈

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcrebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a>CMFCReBar::온쇼컨트롤바메뉴

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>매개 변수

[in] *CPoint*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcrebarontoolhittest"></a><a name="ontoolhittest"></a>CMFCReBar:::온툴히트테스트

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>매개 변수

【인】 *점*<br/>
【인】 *pTI*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcrebaronupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCReBar::에 업데이트CmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>매개 변수

【인】 *p Target*<br/>
【인】 *bDisableIfNohndler*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcrebarsetpanealignment"></a><a name="setpanealignment"></a>CMFCReBar::세파네정렬

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>매개 변수

【인】 *dw정렬*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CReBarCtrl 클래스](../../mfc/reference/crebarctrl-class.md)<br/>
[CPane 클래스](../../mfc/reference/cpane-class.md)
