---
title: CMFC스테이바 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
helpviewer_keywords:
- CMFCStatusBar [MFC], CalcFixedLayout
- CMFCStatusBar [MFC], CommandToIndex
- CMFCStatusBar [MFC], Create
- CMFCStatusBar [MFC], CreateEx
- CMFCStatusBar [MFC], DoesAllowDynInsertBefore
- CMFCStatusBar [MFC], EnablePaneDoubleClick
- CMFCStatusBar [MFC], EnablePaneProgressBar
- CMFCStatusBar [MFC], GetCount
- CMFCStatusBar [MFC], GetDrawExtendedArea
- CMFCStatusBar [MFC], GetExtendedArea
- CMFCStatusBar [MFC], GetItemID
- CMFCStatusBar [MFC], GetItemRect
- CMFCStatusBar [MFC], GetPaneInfo
- CMFCStatusBar [MFC], GetPaneProgress
- CMFCStatusBar [MFC], GetPaneStyle
- CMFCStatusBar [MFC], GetPaneText
- CMFCStatusBar [MFC], GetPaneWidth
- CMFCStatusBar [MFC], GetTipText
- CMFCStatusBar [MFC], InvalidatePaneContent
- CMFCStatusBar [MFC], PreCreateWindow
- CMFCStatusBar [MFC], SetDrawExtendedArea
- CMFCStatusBar [MFC], SetIndicators
- CMFCStatusBar [MFC], SetPaneAnimation
- CMFCStatusBar [MFC], SetPaneBackgroundColor
- CMFCStatusBar [MFC], SetPaneIcon
- CMFCStatusBar [MFC], SetPaneInfo
- CMFCStatusBar [MFC], SetPaneProgress
- CMFCStatusBar [MFC], SetPaneStyle
- CMFCStatusBar [MFC], SetPaneText
- CMFCStatusBar [MFC], SetPaneTextColor
- CMFCStatusBar [MFC], SetPaneWidth
- CMFCStatusBar [MFC], SetTipText
- CMFCStatusBar [MFC], OnDrawPane
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
ms.openlocfilehash: 024fbad44af2fb11e967141fc8e7ccc0aad0ccbe
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753472"
---
# <a name="cmfcstatusbar-class"></a>CMFC스테이바 클래스

클래스는 `CMFCStatusBar` 클래스와 유사한 상태 `CStatusBar` 표시줄을 구현합니다. 그러나 `CMFCStatusBar` 클래스에는 `CStatusBar` 클래스에 의해 제공되지 않는 기능(예: 이미지, 애니메이션 및 진행률 표시줄을 표시하는 기능 및 마우스 두 번 클릭에 응답하는 기능)이 포함되어 있습니다.

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCStatusBar : public CPane
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC 상태 표시줄::석회화 레이아웃](#calcfixedlayout)|[(재정의 CBasePane::석회화 레이아웃.)](../../mfc/reference/cbasepane-class.md#calcfixedlayout)|
|[CMFC 상태 표시줄::명령토 인덱스](#commandtoindex)||
|[CMFC 상태 표시줄::만들기](#create)|컨트롤 막대를 만들고 [CPane](../../mfc/reference/cpane-class.md) 개체에 연결합니다. [(재정의 CPane::만들기.)](../../mfc/reference/cpane-class.md#create)|
|[CMFC 상태 표시줄::만들기 Ex](#createex)|컨트롤 막대를 만들고 [CPane](../../mfc/reference/cpane-class.md) 개체에 연결합니다. [(재정의 CPane::CreateEx.)](../../mfc/reference/cpane-class.md#createex)|
|[CMFC 상태 표시줄::DoesAllowDyn인더인](#doesallowdyninsertbefore)|이 창과 상위 프레임 사이에 다른 창을 동적으로 삽입할 수 있는지 여부를 결정합니다. [(재정의 CBasePane::DoesAllowDyn인가 전에](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFC 상태 표시줄::사용Pane더블클릭](#enablepanedoubleclick)|상태 표시줄에서 마우스를 두 번 클릭하면 사용할 수 없거나 비활성화합니다.|
|[CMFC 상태 표시줄::인에이블파인프로그레시브바](#enablepaneprogressbar)|지정된 창에 진행률 표시줄을 표시합니다.|
|[CMFC 상태 표시줄::GetCount](#getcount)|상태 표시줄에서 창 수를 반환합니다.|
|[CMFC 상태 표시줄::GetDraw확장 지역](#getdrawextendedarea)||
|[CMFC 상태 표시줄::GetExtendedArea](#getextendedarea)||
|[CMFC 상태 표시줄::GetItemID](#getitemid)||
|[CMFC 상태 표시줄::GetItemRect](#getitemrect)||
|[CMFC 상태 표시줄:::GetPaneInfo](#getpaneinfo)||
|[CMFC 상태 표시줄::GetPane 진행](#getpaneprogress)||
|[CMFC 상태 표시줄::겟파인 스타일](#getpanestyle)|창 스타일을 반환합니다. [(재정의 CBasePane::GetPaneStyle.)](../../mfc/reference/cbasepane-class.md#getpanestyle)|
|[CMFC 상태 표시줄::GetPaneText](#getpanetext)||
|[CMFC 상태 표시줄::GetPane폭](#getpanewidth)|상태 표시줄의 지정된 창의 너비를 픽셀 단위로 반환합니다.|
|[CMFC 상태 표시줄::GetTipText](#gettiptext)|상태 표시줄의 지정된 창에 대한 도구 설명 텍스트가 반환됩니다.|
|[CMFC 상태 표시줄::무효화파네콘텐츠](#invalidatepanecontent)|지정된 창을 무효화하고 해당 내용을 다시 그립니다.|
|[CMFC 상태 표시줄::P다시 창조창](#precreatewindow)|이 `CWnd` 개체에 연결된 Windows 창을 만들기 전에 프레임워크에서 호출합니다. [(cwnd::PreCreateWindow.)](../../mfc/reference/cwnd-class.md#precreatewindow)|
|[CMFC 상태 표시줄::세트드로우확장지역](#setdrawextendedarea)||
|[CMFC 상태 표시줄::설정 표시기](#setindicators)||
|[CMFC 상태 표시줄::세파네 애니메이션](#setpaneanimation)|지정된 창에 애니메이션을 할당합니다.|
|[CMFC 상태 표시줄::설정판배경색](#setpanebackgroundcolor)|상태 표시줄의 지정된 창에 대한 배경색을 설정합니다.|
|[CMFC 상태 표시줄::설정파네아이콘](#setpaneicon)|상태 표시줄의 지정된 창에 대한 표시기 아이콘을 설정합니다.|
|[CMFC 상태 표시줄:::세트파네정보](#setpaneinfo)||
|[CMFC 상태 표시줄::설정 진행률](#setpaneprogress)|상태 표시줄의 지정된 창에 대한 진행률 표시줄의 현재 진행률을 설정합니다.|
|[CMFC 상태 표시줄::세트파인 스타일](#setpanestyle)|창의 스타일을 설정합니다. [(재정의 CBasePane::SetPaneStyle.)](../../mfc/reference/cbasepane-class.md#setpanestyle)|
|[CMFC 상태 표시줄::설정창](#setpanetext)||
|[CMFC 상태 표시줄::세파네텍스트컬러](#setpanetextcolor)|상태 표시줄의 지정된 창에 대한 텍스트 색상을 설정합니다.|
|[CMFC 상태 표시줄::설정 너비](#setpanewidth)|상태 표시줄의 지정된 창의 픽셀로 너비를 설정합니다.|
|[CMFC 상태 표시줄::설정 팁 텍스트](#settiptext)|상태 표시줄의 지정된 창에 대한 도구 설명 텍스트를 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC 상태 표시줄::온드로우파인](#ondrawpane)|상태 표시줄의 창을 다시 그릴 때 프레임워크에서 호출됩니다.|

## <a name="remarks"></a>설명

다음 다이어그램은 [상태 표시줄 데모 샘플](../../overview/visual-cpp-samples.md) 응용 프로그램의 상태 표시줄 그림을 보여 주며 있습니다.

![CMFCStatusBar의 예제](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar의 예제")

## <a name="example"></a>예제

다음 예제에서는 응용 프로그램에서 클래스에서 다양 한 메서드를 `CMFCStatusBar` 호출 하는 데 사용 하는 로컬 변수를 보여 줍니다. 이러한 변수는 StatusBarDemoView.h에서 선언됩니다. 메인 프레임은 MainFrm.h에서 선언되고 문서는 StatusBarDemoDoc.h에 선언되고 뷰는 StatusBarDemoView.h에서 선언됩니다. 이 코드 조각은 상태 [표시줄 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]

## <a name="example"></a>예제

다음 예제에서는 MainFrm.h에서 `CMFCStatusBar` `GetStatusBar` 메서드를 도입 한 다음 StatusBarDemoView.h의 메서드에서이 메서드를 호출 하여 개체에 대 한 참조를 `GetStatusBar` 얻는 방법을 보여 줍니다. 이 코드 조각은 상태 [표시줄 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]

## <a name="example"></a>예제

다음 예제에서는 StatusBarDemoView.cpp에서 클래스에서 다양 한 메서드를 `CMFCStatusBar` 호출 하는 방법을 보여 줍니다. 상수는 MainFrm.h에서 선언됩니다. 이 예제에서는 아이콘을 설정하고, 상태 표시줄 창의 도구 설명 텍스트를 설정하고, 지정된 창에 진행률 표시줄을 표시하고, 지정된 창에 애니메이션을 할당하고, 상태 표시줄 창의 텍스트와 너비를 설정하고, 상태 표시줄 창의 진행률 표시줄의 현재 진행률 표시기를 설정하는 방법을 보여 주었습니다. 이 코드 조각은 상태 [표시줄 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxstatusbar.h

## <a name="cmfcstatusbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFC 상태 표시줄::석회화 레이아웃

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

## <a name="cmfcstatusbarcommandtoindex"></a><a name="commandtoindex"></a>CMFC 상태 표시줄::명령토 인덱스

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>매개 변수

【인】 *니드찾기*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbarcreate"></a><a name="create"></a>CMFC 상태 표시줄::만들기

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>매개 변수

【인】 *pParentWnd*<br/>
【인】 *dw스타일*<br/>
【인】 *니드 (미국)의*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbarcreateex"></a><a name="createex"></a>CMFC 상태 표시줄::만들기 Ex

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>매개 변수

【인】 *pParentWnd*<br/>
【인】 *dwCtrl스타일*<br/>
【인】 *dw스타일*<br/>
【인】 *니드 (미국)의*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CMFC 상태 표시줄::DoesAllowDyn인더인

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbarenablepanedoubleclick"></a><a name="enablepanedoubleclick"></a>CMFC 상태 표시줄::사용Pane더블클릭

상태 표시줄에서 마우스를 두 번 클릭하면 사용할 수 없거나 비활성화합니다.

```cpp
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE인 경우 마우스를 두 번 클릭하여 처리하도록 설정합니다. 그렇지 않으면 마우스를 두 번 클릭의 처리를 비활성화합니다.

### <a name="remarks"></a>설명

상태 표시줄이 두 번 클릭을 처리하도록 설정된 경우 Windows는 사용자가 상태 표시줄 창을 두 번 클릭할 때마다 리소스 ID와 함께 WM_COMMAND 알림을 상태 표시줄 소유자에게 보냅니다.

## <a name="cmfcstatusbarenablepaneprogressbar"></a><a name="enablepaneprogressbar"></a>CMFC 상태 표시줄::인에이블파인프로그레시브바

지정된 창에 진행률 표시줄을 표시합니다.

```cpp
void EnablePaneProgressBar(
    int nIndex,
    long nTotal=100,
    BOOL bDisplayText=FALSE,
    COLORREF clrBar=-1,
    COLORREF clrBarDest=-1,
    COLORREF clrProgressText=-1);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 진행률 표시줄을 사용하도록 설정할 창의 인덱스를 지정합니다.

*n토탈*<br/>
【인】 진행률 표시줄의 최대값을 지정합니다.

*b디스플레이텍스트*<br/>
【인】 진행률 표시줄에 현재 진행률 값을 표시할지 여부를 지정합니다.

*클러바*<br/>
【인】 진행률 표시줄의 배경색을 지정합니다.

*클라바드*<br/>
【인】 진행률 표시줄 배경의 보조 색상을 지정합니다. *clrBar와* 다른 값을 사용하여 그라데이션에 혼합된 색상으로 채웁니다.

*clrProgressText*<br/>
【인】 진행률 표시줄의 텍스트 색상을 지정합니다.

### <a name="remarks"></a>설명

*nTotal이* -1로 설정된 `EnablePaneProgressBar` 진행률 표시줄 호출을 사용하지 않도록 설정하려면 기본적으로 *nTotal은* 100으로 설정됩니다. 따라서 진행률을 백분율로 표시하기 위해 추가 계산이 필요하지 않습니다.

진행률 표시줄의 배경색이 그라데이션에 혼합된 색상을 표시되도록 *clrBar* 및 *clrBarDest에* 대해 다른 값을 전달해야 합니다. .

현재 진행률을 설정하려면 [CMFCStatusBar::SetPaneProgress](#setpaneprogress) 메서드를 호출합니다.

## <a name="cmfcstatusbargetcount"></a><a name="getcount"></a>CMFC 상태 표시줄::GetCount

상태 표시줄에서 창 수를 검색합니다.

```
int GetCount() const;
```

### <a name="return-value"></a>Return Value

상태 표시줄의 창 수입니다.

## <a name="cmfcstatusbargetdrawextendedarea"></a><a name="getdrawextendedarea"></a>CMFC 상태 표시줄::GetDraw확장 지역

```
BOOL GetDrawExtendedArea() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbargetextendedarea"></a><a name="getextendedarea"></a>CMFC 상태 표시줄::GetExtendedArea

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbargetitemid"></a><a name="getitemid"></a>CMFC 상태 표시줄::GetItemID

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

【인】 *n인덱스*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbargetitemrect"></a><a name="getitemrect"></a>CMFC 상태 표시줄::GetItemRect

```cpp
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

【인】 *n인덱스*<br/>
【인】 *lpRect*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcstatusbargetpaneinfo"></a><a name="getpaneinfo"></a>CMFC 상태 표시줄:::GetPaneInfo

```cpp
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>매개 변수

【인】 *n인덱스*<br/>
【인】 *니드 (미국)의*<br/>
【인】 *n스타일*<br/>
【인】 *cx너비*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcstatusbargetpaneprogress"></a><a name="getpaneprogress"></a>CMFC 상태 표시줄::GetPane 진행

```
long GetPaneProgress(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

【인】 *n인덱스*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbargetpanestyle"></a><a name="getpanestyle"></a>CMFC 상태 표시줄::겟파인 스타일

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

【인】 *n인덱스*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbargetpanetext"></a><a name="getpanetext"></a>CMFC 상태 표시줄::GetPaneText

```cpp
void GetPaneText(
    int nIndex,
    CString& s) const;

CString GetPaneText(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

【인】 *n인덱스*<br/>
【인】 *s*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbargetpanewidth"></a><a name="getpanewidth"></a>CMFC 상태 표시줄::GetPane폭

상태 표시줄의 창 너비를 검색합니다.

```
int GetPaneWidth(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 상태 표시줄 창의 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

*nIndex가* 지정하는 상태 표시줄 창의 너비입니다. 그렇지 않으면 상태 표시줄 창이 없는 경우 0입니다.

## <a name="cmfcstatusbargettiptext"></a><a name="gettiptext"></a>CMFC 상태 표시줄::GetTipText

상태 표시줄 창의 도구 설명 텍스트를 검색합니다.

```
CString GetTipText(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 도구 팁 텍스트를 검색할 창의 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

*nIndex가* 지정하는 상태 표시줄 창의 도구 설명 텍스트입니다. 그렇지 않으면 지정된 *nIndex에* 대해 상태 표시줄 창이 없거나 tooltip 텍스트가 비어 있는 경우 빈 문자열이 있습니다.

## <a name="cmfcstatusbarinvalidatepanecontent"></a><a name="invalidatepanecontent"></a>CMFC 상태 표시줄::무효화파네콘텐츠

상태 표시줄 창을 무효화하고 내용을 다시 그립니다.

```cpp
void InvalidatePaneContent(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 콘텐츠가 무효화되고 다시 그려질 창의 인덱스를 지정합니다.

### <a name="remarks"></a>설명

상태 표시줄이 무효화되면 다시 그리기로 표시됩니다. 메서드가 메서드에 `UpdateWindow` WM_PAINT 메시지를 `OnPaint` 보낼 때 Windows에서 다시 그립니다.

## <a name="cmfcstatusbarondrawpane"></a><a name="ondrawpane"></a>CMFC 상태 표시줄::온드로우파인

상태 표시줄의 창을 다시 그립니다.

```
virtual void OnDrawPane(
    CDC* pDC,
    CMFCStatusBarPaneInfo* pPane);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 그리기를 위한 장치 컨텍스트에 대한 포인터입니다.

*pPane*<br/>
【인】 다시 그릴 `CMFCStatusBarPaneInfo` 창에 대한 정보가 포함된 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

기본적으로 창의 스타일 및 내용에 따라 장치 컨텍스트 `OnDrawPane` *pDC를* 사용하여 창을 다시 그립니다.

-derived 클래스에서 `CMFCStatusBar`이 메서드를 재정의하여 창모양을 사용자 지정합니다.

## <a name="cmfcstatusbarprecreatewindow"></a><a name="precreatewindow"></a>CMFC 상태 표시줄::P다시 창조창

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>매개 변수

【인】 *cs*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbarsetdrawextendedarea"></a><a name="setdrawextendedarea"></a>CMFC 상태 표시줄::세트드로우확장지역

```cpp
void SetDrawExtendedArea(BOOL bSet = TRUE);
```

### <a name="parameters"></a>매개 변수

【인】 *bSet*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcstatusbarsetindicators"></a><a name="setindicators"></a>CMFC 상태 표시줄::설정 표시기

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>매개 변수

【인】 *lpID어레이*<br/>
【인】 *니드 카운트*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbarsetpaneanimation"></a><a name="setpaneanimation"></a>CMFC 상태 표시줄::세파네 애니메이션

지정된 창에 애니메이션을 할당합니다.

```cpp
void SetPaneAnimation(
    int nIndex,
    HIMAGELIST hImageList,
    UINT nFrameRate=500,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 애니메이션에 할당할 창의 인덱스를 지정합니다.

*hImageList*<br/>
【인】 애니메이션 프레임을 포함하는 이미지 목록에 대한 핸들을 지정합니다.

*n프레임레이트*<br/>
【인】 애니메이션의 프레임 속도를 밀리초 단위로 지정합니다.

*bUpdate*<br/>
【인】 TRUE이면 창 콘텐츠를 즉시 업데이트합니다. 그렇지 않으면 창 내용이 무효화되면 업데이트됩니다.

### <a name="remarks"></a>설명

현재 애니메이션을 사용하지 않도록 설정하려면 `hImageList` NULL로 설정하여 호출합니다. `SetPaneAnimation`

## <a name="cmfcstatusbarsetpanebackgroundcolor"></a><a name="setpanebackgroundcolor"></a>CMFC 상태 표시줄::설정판배경색

상태 표시줄 창의 배경색을 설정합니다.

```cpp
void SetPaneBackgroundColor(
    int nIndex,
    COLORREF clrBackground=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 새 배경색을 설정할 창의 인덱스를 지정합니다.

*clrBackground*<br/>
[in] 새 배경색을 지정합니다.

*bUpdate*<br/>
【인】 TRUE이면 창 콘텐츠를 즉시 업데이트합니다. 그렇지 않으면 다른 메서드에 의해 창이 무효화될 때까지 창 내용을 업데이트하지 마십시오.

## <a name="cmfcstatusbarsetpaneicon"></a><a name="setpaneicon"></a>CMFC 상태 표시줄::설정파네아이콘

상태 표시줄 창의 아이콘을 설정합니다.

```cpp
void SetPaneIcon(
    int nIndex,
    HICON hIcon,
    BOOL bUpdate=TRUE);

void SetPaneIcon(
    int nIndex,
    HBITMAP hBmp,
    COLORREF clrTransparent=RGB(255, 0, 255),
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 이미지를 설정할 창의 인덱스를 지정합니다.

*hIcon*<br/>
【인】 창 이미지로 설정할 아이콘에 대한 핸들을 지정합니다.

*bUpdate*<br/>
【인】 창 콘텐츠를 즉시 업데이트할지 여부를 지정합니다.

*hBmp*<br/>
【인】 창 이미지로 설정될 비트맵에 대한 핸들을 지정합니다.

*clr투명*<br/>
【인】 *hBmp가* 나타내는 비트맵의 투명한 색상을 지정합니다.

### <a name="remarks"></a>설명

HICON 또는 HBITMAP을 투명 한 색상과 함께 전달하여 창의 이미지를 설정할 수 있습니다. 더 이상 이미지를 표시하지 않으려면 NULL 값을 이미지 핸들로 전달합니다.

[CMFCStatusBar::SetPaneAnimation이](#setpaneanimation) 설정한 실행 중인 애니메이션이 있으면 애니메이션이 중지됩니다.

## <a name="cmfcstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a>CMFC 상태 표시줄:::세트파네정보

```cpp
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>매개 변수

【인】 *n인덱스*<br/>
【인】 *니드 (미국)의*<br/>
【인】 *n스타일*<br/>
【인】 *cx너비*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcstatusbarsetpaneprogress"></a><a name="setpaneprogress"></a>CMFC 상태 표시줄::설정 진행률

지정된 창에 대한 진행률 표시줄의 현재 진행률 표시기를 설정합니다.

```cpp
void SetPaneProgress(
    int nIndex,
    long nCurr,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 진행률 표시기를 업데이트할 창의 인덱스를 지정합니다.

*nCurr*<br/>
【인】 진행률 표시기의 현재 값을 지정합니다.

*bUpdate*<br/>
【인】 창을 즉시 업데이트할지 여부를 지정합니다.

### <a name="remarks"></a>설명

지정된 창에서 진행률 표시줄의 진행률 표시줄을 업데이트하려는 경우 이 메서드를 호출합니다.

지정된 창에 이 함수를 사용하려면 [CMFCStatusBar::EnablePaneProgressBar를](#enablepaneprogressbar) 먼저 호출해야 합니다.

## <a name="cmfcstatusbarsetpanestyle"></a><a name="setpanestyle"></a>CMFC 상태 표시줄::세트파인 스타일

```cpp
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>매개 변수

【인】 *n인덱스*<br/>
【인】 *n스타일*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcstatusbarsetpanetext"></a><a name="setpanetext"></a>CMFC 상태 표시줄::설정창

```
virtual BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>매개 변수

【인】 *n인덱스*<br/>
【인】 *lpszNewText*<br/>
【인】 *bUpdate*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcstatusbarsetpanetextcolor"></a><a name="setpanetextcolor"></a>CMFC 상태 표시줄::세파네텍스트컬러

지정된 창의 텍스트 색상을 설정합니다.

```cpp
void SetPaneTextColor(
    int nIndex,
    COLORREF clrText=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 새 텍스트 색상을 할당할 창의 인덱스를 지정합니다.

*clrText*<br/>
【인】 텍스트 색상을 지정합니다.

*bUpdate*<br/>
【인】 TRUE이면 창 콘텐츠를 즉시 업데이트합니다. 그렇지 않으면 다른 메서드에 의해 창이 무효화될 때까지 창 내용을 업데이트하지 마십시오.

## <a name="cmfcstatusbarsetpanewidth"></a><a name="setpanewidth"></a>CMFC 상태 표시줄::설정 너비

상태 표시줄 창의 너비를 설정합니다.

```cpp
void SetPaneWidth(
    int nIndex,
    int cx);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 새 너비를 설정할 상태 표시줄 창의 인덱스입니다.

*Cx*<br/>
【인】 상태 표시줄 창의 새 너비(픽셀)입니다.

## <a name="cmfcstatusbarsettiptext"></a><a name="settiptext"></a>CMFC 상태 표시줄::설정 팁 텍스트

상태 표시줄 창의 도구 설명 텍스트를 설정합니다.

```cpp
void SetTipText(
    int nIndex,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 도구 설명 텍스트를 할당할 창의 인덱스입니다.

*pszTip텍스트*<br/>
【인】 새 도구 설명 텍스트입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CPane 클래스](../../mfc/reference/cpane-class.md)<br/>
[CStatusBar 클래스](../../mfc/reference/cstatusbar-class.md)
