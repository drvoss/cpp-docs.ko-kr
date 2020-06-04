---
title: CMFC메뉴바 클래스
ms.date: 10/18/2018
f1_keywords:
- CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar::AdjustLocations
- AFXMENUBAR/CMFCMenuBar::AllowChangeTextLabels
- AFXMENUBAR/CMFCMenuBar::AllowShowOnPaneMenu
- AFXMENUBAR/CMFCMenuBar::CalcFixedLayout
- AFXMENUBAR/CMFCMenuBar::CalcLayout
- AFXMENUBAR/CMFCMenuBar::CalcMaxButtonHeight
- AFXMENUBAR/CMFCMenuBar::CanBeClosed
- AFXMENUBAR/CMFCMenuBar::CanBeRestored
- AFXMENUBAR/CMFCMenuBar::Create
- AFXMENUBAR/CMFCMenuBar::CreateEx
- AFXMENUBAR/CMFCMenuBar::CreateFromMenu
- AFXMENUBAR/CMFCMenuBar::EnableHelpCombobox
- AFXMENUBAR/CMFCMenuBar::EnableMenuShadows
- AFXMENUBAR/CMFCMenuBar::GetAvailableExpandSize
- AFXMENUBAR/CMFCMenuBar::GetColumnWidth
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenu
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::GetFloatPopupDirection
- AFXMENUBAR/CMFCMenuBar::GetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::GetHelpCombobox
- AFXMENUBAR/CMFCMenuBar::GetHMenu
- AFXMENUBAR/CMFCMenuBar::GetMenuFont
- AFXMENUBAR/CMFCMenuBar::GetMenuItem
- AFXMENUBAR/CMFCMenuBar::GetRowHeight
- AFXMENUBAR/CMFCMenuBar::GetSystemButton
- AFXMENUBAR/CMFCMenuBar::GetSystemButtonsCount
- AFXMENUBAR/CMFCMenuBar::GetSystemMenu
- AFXMENUBAR/CMFCMenuBar::HighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsButtonExtraSizeAvailable
- AFXMENUBAR/CMFCMenuBar::IsHighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsMenuShadows
- AFXMENUBAR/CMFCMenuBar::IsRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommands
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommandsDelay
- AFXMENUBAR/CMFCMenuBar::LoadState
- AFXMENUBAR/CMFCMenuBar::OnChangeHot
- AFXMENUBAR/CMFCMenuBar::OnDefaultMenuLoaded
- AFXMENUBAR/CMFCMenuBar::OnSendCommand
- AFXMENUBAR/CMFCMenuBar::OnSetDefaultButtonText
- AFXMENUBAR/CMFCMenuBar::OnToolHitTest
- AFXMENUBAR/CMFCMenuBar::PreTranslateMessage
- AFXMENUBAR/CMFCMenuBar::RestoreOriginalstate
- AFXMENUBAR/CMFCMenuBar::SaveState
- AFXMENUBAR/CMFCMenuBar::SetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::SetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::SetMaximizeMode
- AFXMENUBAR/CMFCMenuBar::SetMenuButtonRTC
- AFXMENUBAR/CMFCMenuBar::SetMenuFont
- AFXMENUBAR/CMFCMenuBar::SetRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::SetShowAllCommands
helpviewer_keywords:
- CMFCMenuBar [MFC], AdjustLocations
- CMFCMenuBar [MFC], AllowChangeTextLabels
- CMFCMenuBar [MFC], AllowShowOnPaneMenu
- CMFCMenuBar [MFC], CalcFixedLayout
- CMFCMenuBar [MFC], CalcLayout
- CMFCMenuBar [MFC], CalcMaxButtonHeight
- CMFCMenuBar [MFC], CanBeClosed
- CMFCMenuBar [MFC], CanBeRestored
- CMFCMenuBar [MFC], Create
- CMFCMenuBar [MFC], CreateEx
- CMFCMenuBar [MFC], CreateFromMenu
- CMFCMenuBar [MFC], EnableHelpCombobox
- CMFCMenuBar [MFC], EnableMenuShadows
- CMFCMenuBar [MFC], GetAvailableExpandSize
- CMFCMenuBar [MFC], GetColumnWidth
- CMFCMenuBar [MFC], GetDefaultMenu
- CMFCMenuBar [MFC], GetDefaultMenuResId
- CMFCMenuBar [MFC], GetFloatPopupDirection
- CMFCMenuBar [MFC], GetForceDownArrows
- CMFCMenuBar [MFC], GetHelpCombobox
- CMFCMenuBar [MFC], GetHMenu
- CMFCMenuBar [MFC], GetMenuFont
- CMFCMenuBar [MFC], GetMenuItem
- CMFCMenuBar [MFC], GetRowHeight
- CMFCMenuBar [MFC], GetSystemButton
- CMFCMenuBar [MFC], GetSystemButtonsCount
- CMFCMenuBar [MFC], GetSystemMenu
- CMFCMenuBar [MFC], HighlightDisabledItems
- CMFCMenuBar [MFC], IsButtonExtraSizeAvailable
- CMFCMenuBar [MFC], IsHighlightDisabledItems
- CMFCMenuBar [MFC], IsMenuShadows
- CMFCMenuBar [MFC], IsRecentlyUsedMenus
- CMFCMenuBar [MFC], IsShowAllCommands
- CMFCMenuBar [MFC], IsShowAllCommandsDelay
- CMFCMenuBar [MFC], LoadState
- CMFCMenuBar [MFC], OnChangeHot
- CMFCMenuBar [MFC], OnDefaultMenuLoaded
- CMFCMenuBar [MFC], OnSendCommand
- CMFCMenuBar [MFC], OnSetDefaultButtonText
- CMFCMenuBar [MFC], OnToolHitTest
- CMFCMenuBar [MFC], PreTranslateMessage
- CMFCMenuBar [MFC], RestoreOriginalstate
- CMFCMenuBar [MFC], SaveState
- CMFCMenuBar [MFC], SetDefaultMenuResId
- CMFCMenuBar [MFC], SetForceDownArrows
- CMFCMenuBar [MFC], SetMaximizeMode
- CMFCMenuBar [MFC], SetMenuButtonRTC
- CMFCMenuBar [MFC], SetMenuFont
- CMFCMenuBar [MFC], SetRecentlyUsedMenus
- CMFCMenuBar [MFC], SetShowAllCommands
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
ms.openlocfilehash: f25bff9564eb7a4290f958f0b7810cac8ef7e238
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749626"
---
# <a name="cmfcmenubar-class"></a>CMFC메뉴바 클래스

도킹을 구현하는 메뉴 모음입니다.
자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCMenuBar : public CMFCToolbar
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCMenuBar::AdjustLocations](#adjustlocations)|( `CMFCToolBar::AdjustLocations`을 재정의합니다.)|
|[CMFCMenuBar::AllowChangeTextLabels](#allowchangetextlabels)|도구 모음 단추의 이미지 아래에 텍스트 레이블을 표시할 수 있는지 여부를 지정합니다. [(CMFCToolBar 재정의::허용변경 텍스트 레이블.)](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels)|
|[CMFC메뉴바::허용쇼온파인메뉴](#allowshowonpanemenu)|( `CPane::AllowShowOnPaneMenu`을 재정의합니다.)|
|[CMFC메뉴바::석회화레이아웃](#calcfixedlayout)|도구 모음의 수평 크기를 계산합니다. [(CMFCToolBar 재정의::석회화 레이아웃.)](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout)|
|[CMFC메뉴바::석회화레이아웃](#calclayout)|( `CMFCToolBar::CalcLayout`을 재정의합니다.)|
|[CMFC메뉴바::칼맥스버튼높이](#calcmaxbuttonheight)|도구 모음에서 단추의 최대 높이를 계산합니다. [(CMFCToolBar 재정의::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight).)|
|[CMFC메뉴바::수있습니다.](#canbeclosed)|사용자가 도구 모음을 닫을 수 있는지 여부를 지정합니다. [(CMFCToolBar 재정의::수 있음.)](../../mfc/reference/cmfctoolbar-class.md#canbeclosed)|
|[CMFC메뉴바::캔복원](#canberestored)|사용자 지정 후 시스템에서 도구 모음을 원래 상태로 복원할 수 있는지 여부를 결정합니다. [(CMFCToolBar 재정의::캔복원.)](../../mfc/reference/cmfctoolbar-class.md#canberestored)|
|[CMFC메뉴바::만들기](#create)|메뉴 컨트롤을 만들고 개체에 `CMFCMenuBar` 연결합니다.|
|[CMFC메뉴바::만들기](#createex)|추가 `CMFCMenuBar` 스타일 옵션이 있는 객체를 만듭니다.|
|[CMFC메뉴바::만들기메뉴](#createfrommenu)|`CMFCMenuBar` 개체를 초기화합니다. 채워진 에 대한 템플릿 역할을 하는 HMENU `CMFCMenuBar`매개 변수를 허용합니다.|
|[CMFC메뉴바::인에이블헬프콤보박스](#enablehelpcombobox)|메뉴 모음의 오른쪽에 있는 **도움말** 콤보 상자를 활성화합니다.|
|[CMFC메뉴바::인에이블메뉴섀도우](#enablemenushadows)|팝업 메뉴에 대한 그림자를 표시할지 여부를 지정합니다.|
|[CMFC메뉴바::다운로드 사용 가능한확장크기](#getavailableexpandsize)|[(재정의 CPane::GetAvailableExpandSize.)](../../mfc/reference/cpane-class.md#getavailableexpandsize)|
|[CMFC메뉴바::GetColumn너비](#getcolumnwidth)|도구 모음 단추의 너비를 반환합니다. [(CMFCToolBar 재정의::GetColumn너비.)](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth)|
|[CMFC메뉴바::GetDefaultMenu](#getdefaultmenu)|리소스 파일의 원래 메뉴에 핸들을 반환합니다.|
|[CMFC메뉴바::GetDefaultMenuResid](#getdefaultmenuresid)|리소스 파일의 원래 메뉴에 대한 리소스 식별자를 반환합니다.|
|[CMFC메뉴바::겟플로트팝디렉션](#getfloatpopupdirection)||
|[CMFC메뉴바::겟포스다운로우](#getforcedownarrows)||
|[CMFC메뉴바::겟헬프콤보박스](#gethelpcombobox)|**도움말** 콤보 상자에 대한 포인터를 반환합니다.|
|[CMFC메뉴바::겟메뉴](#gethmenu)|핸들을 개체에 연결된 메뉴로 `CMFCMenuBar` 반환합니다.|
|[CMFC메뉴바::겟메뉴폰트](#getmenufont)|메뉴 개체에 대한 현재 전역 글꼴을 반환합니다.|
|[CMFC메뉴바::겟메뉴아이템](#getmenuitem)|제공된 항목 인덱스와 연결된 도구 모음 단추를 반환합니다.|
|[CMFC메뉴바::겟로우높이](#getrowheight)|도구 모음 단추의 높이를 반환합니다. [(CMFCToolBar 재정의::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFC메뉴바::겟시스템 버튼](#getsystembutton)||
|[CMFC메뉴바::겟시스템 버튼카운트](#getsystembuttonscount)||
|[CMFC메뉴바::겟시스템메뉴](#getsystemmenu)||
|[CMFC메뉴바::강조 표시 안 함항목](#highlightdisableditems)|비활성화된 메뉴 항목이 강조 표시되어 있는지 여부를 나타냅니다.|
|[CMFC메뉴바::이버튼엑스트라사이즈사용 가능](#isbuttonextrasizeavailable)|도구 모음에 테두리가 확장된 단추를 표시할 수 있는지 여부를 결정합니다. [(재정의 CMFCToolBar::IsButton추가 크기 초과 사용 가능.)](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable)|
|[CMFC메뉴바::하이라이트 비활성화항목](#ishighlightdisableditems)|비활성화된 항목이 강조 표시되어 있는지 여부를 나타냅니다.|
|[CMFC메뉴바::이스메뉴섀도우](#ismenushadows)|팝업 메뉴에 그림자가 그려지는지 여부를 나타냅니다.|
|[CMFC메뉴바::최근 사용 메뉴](#isrecentlyusedmenus)|최근에 사용한 메뉴 명령이 메뉴 모음에 표시되는지 여부를 나타냅니다.|
|[CMFC메뉴바::이쇼올커맨드](#isshowallcommands)|팝업 메뉴에 모든 명령이 표시되는지 여부를 나타냅니다.|
|[CMFC메뉴바::이쇼올커맨드딜지연](#isshowallcommandsdelay)|메뉴가 짧은 지연 후 모든 명령을 표시하는지 여부를 나타냅니다.|
|[CMFC메뉴바::로드스테이트](#loadstate)|레지스트리에서 `CMFCMenuBar` 개체의 상태를 로드합니다.|
|[CMFC메뉴바::온체인지핫](#onchangehot)|사용자가 도구 모음에서 단추를 선택할 때 프레임워크에서 호출됩니다. [(CMFCToolBar 재정의::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot).)|
|[CMFC메뉴바::기본메뉴 로드](#ondefaultmenuloaded)|프레임 창리소스 파일에서 기본 메뉴를 로드할 때 프레임워크에서 호출됩니다.|
|[CMFC메뉴바::온센드커맨드](#onsendcommand)|( `CMFCToolBar::OnSendCommand`을 재정의합니다.)|
|[CMFC메뉴바::기본 설정 단추 텍스트](#onsetdefaultbuttontext)|메뉴가 사용자 지정 모드에 있고 사용자가 메뉴 항목의 텍스트를 변경할 때 프레임워크에서 호출됩니다.|
|[CMFC메뉴바::온툴히트테스트](#ontoolhittest)|( `CMFCToolBar::OnToolHitTest`을 재정의합니다.)|
|[CMFC메뉴바::P다시번역메시지](#pretranslatemessage)|( `CMFCToolBar::PreTranslateMessage`을 재정의합니다.)|
|[CMFC메뉴바::복원오리지널스테이트](#restoreoriginalstate)|메뉴가 사용자 지정 모드에 있고 사용자가 메뉴 모음에 대해 **재설정을** 선택할 때 프레임워크에서 호출됩니다.|
|[CMFC메뉴바::저장상태](#savestate)|`CMFCMenuBar` 개체의 상태를 레지스트리에 저장합니다.|
|[CMFC메뉴바:::설정기본메뉴리시드](#setdefaultmenuresid)|리소스 파일의 원래 메뉴를 설정합니다.|
|[CMFC메뉴바::셋포스다운로우](#setforcedownarrows)||
|[CMFC메뉴바::설정 최대화 모드](#setmaximizemode)|MDI 자식 창이 표시 모드를 변경할 때 프레임워크에서 호출됩니다. MDI 자식 창이 새로 최대화되어 있거나 더 이상 최대화되지 않은 경우 이 메서드는 메뉴 막대를 업데이트합니다.|
|[CMFC메뉴바::세트메뉴버튼RTC](#setmenubuttonrtc)|사용자가 메뉴 단추를 동적으로 만들 때 생성되는 런타임 클래스 정보를 설정합니다.|
|[CMFC메뉴바::세트메뉴폰트](#setmenufont)|응용 프로그램의 모든 메뉴에 대한 글꼴을 설정합니다.|
|[CMFC메뉴바::최근 사용 메뉴](#setrecentlyusedmenus)|메뉴 막대에 최근에 사용한 메뉴 명령이 표시되는지 여부를 지정합니다.|
|[CMFC메뉴바::세트쇼올커맨드](#setshowallcommands)|메뉴 막대에 모든 명령이 표시되는지 여부를 지정합니다.|

## <a name="remarks"></a>설명

클래스는 `CMFCMenuBar` 도킹 기능을 구현하는 메뉴 모음입니다. 닫을 수는 없지만 도구 모음과 유사합니다.

`CMFCMenuBar`는 최근에 사용한 메뉴 항목 개체를 표시하는 옵션을 지원합니다. 이 옵션을 사용하도록 설정하면 처음 볼 때 사용 가능한 명령의 하위 집합만 `CMFCMenuBar` 표시됩니다. 그 후 최근에 사용한 명령이 명령의 원래 하위 집합과 함께 표시됩니다. 또한 사용자는 항상 메뉴를 확장하여 사용 가능한 모든 명령을 볼 수 있습니다. 따라서 사용 가능한 각 명령은 지속적으로 표시하거나 최근에 선택된 경우에만 표시하도록 구성됩니다.

개체를 `CMFCMenuBar` 사용하려면 기본 창 프레임 개체에 포함합니다. `WM_CREATE` 메시지를 처리할 때 `CMFCMenuBar::Create` 전화 `CMFCMenuBar::CreateEx`또는 . 사용하는 함수를 만드는 위치에 관계없이 포인터를 주 프레임 창으로 전달합니다. 그런 다음 [CFrameWndEx::EnableDocking을](../../mfc/reference/cframewndex-class.md#enabledocking)호출하여 도킹을 활성화합니다. [CFrameWndEx::DockPane를](../../mfc/reference/cframewndex-class.md#dockpane)호출하여 이 메뉴를 도킹합니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCMenuBar` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 창 의 스타일을 설정하고, 사용자 지정 단추를 활성화하고, 도움말 상자를 활성화하고, 팝업 메뉴에 대한 그림자를 활성화하고, 메뉴 모음을 업데이트하는 방법을 보여 줍니다. 이 코드 조각은 IE [데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]
[!code-cpp[NVC_MFC_IEDemo#3](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFC베이스툴바](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

`CMFCMenuBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxmenubar.h

## <a name="cmfcmenubaradjustlocations"></a><a name="adjustlocations"></a>CMFC메뉴바::조정위치

메뉴 모음의 메뉴 항목의 위치를 조정합니다.

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>설명

## <a name="cmfcmenubarallowchangetextlabels"></a><a name="allowchangetextlabels"></a>CMFC메뉴바::허용변경텍스트라벨

메뉴 모음의 이미지 아래에 텍스트 레이블이 허용되는지 여부를 결정합니다.

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>Return Value

사용자가 이미지 아래에 텍스트 레이블을 표시하도록 선택할 수 있는 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcmenubarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFC메뉴바::허용쇼온파인메뉴

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFC메뉴바::석회화레이아웃

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

## <a name="cmfcmenubarcalclayout"></a><a name="calclayout"></a>CMFC메뉴바::석회화레이아웃

```
virtual CSize CalcLayout(
    DWORD dwMode,
    int nLength = -1);
```

### <a name="parameters"></a>매개 변수

【인】 *dw모드*<br/>

【인】 *n길이*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubarcalcmaxbuttonheight"></a><a name="calcmaxbuttonheight"></a>CMFC메뉴바::칼맥스버튼높이

```
virtual int CalcMaxButtonHeight();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubarcanbeclosed"></a><a name="canbeclosed"></a>CMFC메뉴바::수있습니다.

```
virtual BOOL CanBeClosed() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubarcanberestored"></a><a name="canberestored"></a>CMFC메뉴바::캔복원

```
virtual BOOL CanBeRestored() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubarcreate"></a><a name="create"></a>CMFC메뉴바::만들기

메뉴 컨트롤을 만들고 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 개체에 연결합니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,
    UINT nID = AFX_IDW_MENUBAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
【인】 새 `CMFCMenuBar` 개체의 부모 창에 대한 포인터입니다.

*dwStyle*<br/>
【인】 새 메뉴 모음의 스타일입니다.

*nID*<br/>
【인】 메뉴 모음의 자식 창에 대한 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

개체를 생성한 `CMFCMenuBar` 후 를 `Create`호출해야 합니다. 이 메서드는 `CMFCMenuBar` 컨트롤을 만들고 개체에 `CMFCMenuBar` 연결 합니다.

도구 모음 스타일에 대한 자세한 내용은 [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle)을 참조하십시오.

## <a name="cmfcmenubarcreateex"></a><a name="createex"></a>CMFC메뉴바::만들기

지정된 확장 스타일을 가진 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 개체를 만듭니다.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = TBSTYLE_FLAT,
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,
    CRect rcBorders = CRect(1,
    1,
    1,
    1),
    UINT nID =AFX_IDW_MENUBAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
【인】 새 `CMFCMenuBar` 개체의 상위 창에 대한 포인터입니다.

*dwCtrl스타일*<br/>
【인】 새 메뉴 모음에 대한 추가 스타일입니다.

*dwStyle*<br/>
【인】 새 메뉴 모음의 기본 스타일입니다.

*rcBorders*<br/>
【인】 개체의 테두리에 대한 크기를 지정하는 `CRect` 매개 `CMFCMenuBar` 변수입니다.

*nID*<br/>
【인】 메뉴 모음의 자식 창에 대한 ID입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

도구 모음 스타일 외에 스타일을 지정하려는 경우 [CMFCMenuBar::만들기](#create) 대신 이 함수를 사용해야 합니다. 자주 사용하는 추가 스타일은 TBSTYLE_TRANSPARENT CBRS_TOP.

추가 스타일 목록은 [도구 모음 컨트롤 및 단추 스타일,](/windows/win32/Controls/toolbar-control-and-button-styles)공통 제어 [스타일](/windows/win32/Controls/common-control-styles)및 공통 [창 스타일을](/windows/win32/winmsg/window-styles)참조하십시오.

### <a name="example"></a>예제

다음 예제에서는 `CreateEx` `CMFCMenuBar` 클래스의 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 IE [데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]
[!code-cpp[NVC_MFC_IEDemo#2](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]

## <a name="cmfcmenubarcreatefrommenu"></a><a name="createfrommenu"></a>CMFC메뉴바::만들기메뉴

[CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 개체를 초기화합니다. 이 메서드는 `CMFCMenuBar` HMENU 매개 변수 다음에 개체를 모델합니다.

```
virtual void CreateFromMenu(
    HMENU hMenu,
    BOOL bDefaultMenu = FALSE,
    BOOL bForceUpdate = FALSE);
```

### <a name="parameters"></a>매개 변수

*Hmenu*<br/>
【인】 메뉴 리소스에 대한 핸들입니다. `CreateFromMenu`이 리소스를 `CMFCMenuBar`에 대한 템플릿으로 사용합니다.

*b기본 메뉴*<br/>
【인】 새 메뉴가 기본 메뉴인지 여부를 나타내는 부울입니다.

*bForceUpdate*<br/>
【인】 이 메서드가 메뉴 업데이트를 강제하는지 여부를 나타내는 부울입니다.

### <a name="remarks"></a>설명

메뉴 컨트롤에 메뉴 리소스와 동일한 메뉴 항목을 사용하려는 경우 이 메서드를 사용합니다. [CMFCMenuBar::만들기](#create) 또는 [CMFCMenuBar::CreateEx](#createex)를 호출한 후 이 메서드를 호출합니다.

## <a name="cmfcmenubarenablehelpcombobox"></a><a name="enablehelpcombobox"></a>CMFC메뉴바::인에이블헬프콤보박스

메뉴 모음의 오른쪽에 있는 **도움말** 콤보 상자를 활성화합니다.

```cpp
void EnableHelpCombobox(
    UINT uiID,
    LPCTSTR lpszPrompt = NULL,
    int nComboBoxWidth = 150);
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
【인】 **도움말** 콤보 상자의 단추에 대한 명령 ID입니다.

*lpsz프롬프트*<br/>
【인】 비어 있고 활성화되어 있지 않은 경우 프레임워크가 콤보 상자에 표시되는 텍스트를 포함하는 문자열입니다. 예를 들어 "여기에 텍스트를 입력"을 입력합니다.

*n콤보박스폭*<br/>
【인】 콤보 상자의 너비(픽셀)입니다.

### <a name="remarks"></a>설명

**도움말** 콤보 상자는 Microsoft Word의 메뉴 모음에 있는 **도움말** 콤보 상자와 유사합니다.

*uiID가* 0으로 설정된 이 메서드를 호출하면 이 메서드가 콤보 상자를 숨깁니다. 그렇지 않으면 이 메서드는 메뉴 모음의 오른쪽에 콤보 상자를 자동으로 표시합니다. 이 메서드를 호출한 후 [CMFCMenuBar::GetHelpCombobox를](#gethelpcombobox) 호출하여 삽입된 [CMFCToolBarComboBox](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) 개체에 대한 포인터를 가져옵니다.

## <a name="cmfcmenubarenablemenushadows"></a><a name="enablemenushadows"></a>CMFC메뉴바::인에이블메뉴섀도우

팝업 메뉴에 그림자를 활성화합니다.

```
static void EnableMenuShadows(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 팝업 메뉴에 그림자를 사용하도록 설정해야 하는지 여부를 나타내는 부울 매개변수입니다.

### <a name="remarks"></a>설명

이 메서드가 사용하는 알고리즘은 복잡하며 느린 시스템에서 응용 프로그램의 성능을 저하시킬 수 있습니다.

## <a name="cmfcmenubargetavailableexpandsize"></a><a name="getavailableexpandsize"></a>CMFC메뉴바::다운로드 사용 가능한확장크기

```
virtual int GetAvailableExpandSize() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubargetcolumnwidth"></a><a name="getcolumnwidth"></a>CMFC메뉴바::GetColumn너비

```
virtual int GetColumnWidth() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubargetdefaultmenu"></a><a name="getdefaultmenu"></a>CMFC메뉴바::GetDefaultMenu

원래 메뉴에 대한 핸들을 검색합니다. 프레임워크는 리소스 파일에서 원래 메뉴를 로드합니다.

```
HMENU GetDefaultMenu() const;
```

### <a name="return-value"></a>Return Value

메뉴 리소스에 대한 핸들입니다.

### <a name="remarks"></a>설명

응용 프로그램에서 메뉴를 사용자 지정하는 경우 이 메서드를 사용하여 원래 메뉴에 대한 핸들을 검색할 수 있습니다.

## <a name="cmfcmenubargetdefaultmenuresid"></a><a name="getdefaultmenuresid"></a>CMFC메뉴바::GetDefaultMenuResid

기본 메뉴에 대한 리소스 식별자를 검색합니다.

```
UINT GetDefaultMenuResId() const;
```

### <a name="return-value"></a>Return Value

메뉴 리소스 식별자입니다.

### <a name="remarks"></a>설명

프레임워크는 리소스 파일에서 `CMFCMenuBar` 개체의 기본 메뉴를 로드합니다.

## <a name="cmfcmenubargetfloatpopupdirection"></a><a name="getfloatpopupdirection"></a>CMFC메뉴바::겟플로트팝디렉션

```
int GetFloatPopupDirection(CMFCToolBarMenuButton* pButton);
```

### <a name="parameters"></a>매개 변수

【인】 *p 버튼*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubargetforcedownarrows"></a><a name="getforcedownarrows"></a>CMFC메뉴바::겟포스다운로우

```
BOOL GetForceDownArrows();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubargethelpcombobox"></a><a name="gethelpcombobox"></a>CMFC메뉴바::겟헬프콤보박스

**도움말** 콤보 상자에 대한 포인터를 반환합니다.

```
CMFCToolBarComboBoxButton* GetHelpCombobox();
```

### <a name="return-value"></a>Return Value

**도움말** 콤보 상자에 대한 포인터입니다. **도움말** 콤보 상자가 숨겨져 있거나 활성화되어 있지 않은 경우 NULL입니다.

### <a name="remarks"></a>설명

**도움말** 콤보 상자는 메뉴 모음의 오른쪽에 있습니다. 이 콤보 상자를 사용하려면 [CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox) 메서드를 호출합니다.

## <a name="cmfcmenubargethmenu"></a><a name="gethmenu"></a>CMFC메뉴바::겟메뉴

[CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 개체에 연결된 메뉴에 대한 핸들을 검색합니다.

```
HMENU GetHMenu() const;
```

## <a name="cmfcmenubargetmenufont"></a><a name="getmenufont"></a>CMFC메뉴바::겟메뉴폰트

현재 메뉴 글꼴을 검색합니다.

```
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>매개 변수

*b호르츠 (주)*<br/>
【인】 가로 또는 세로 글꼴을 반환할지 여부를 지정하는 부울 매개 변수입니다. TRUE는 가로 글꼴을 나타냅니다.

### <a name="return-value"></a>Return Value

현재 메뉴 막대 글꼴을 포함하는 [CFont](../../mfc/reference/cfont-class.md) 매개 변수에 대한 포인터입니다.

### <a name="remarks"></a>설명

반환된 글꼴은 응용 프로그램의 전역 매개 변수입니다. 모든 `CMFCMenuBar` 개체에 대해 두 개의 전역 글꼴이 유지됩니다. 이러한 별도의 글꼴은 가로 및 세로 메뉴 모음에 사용됩니다.

## <a name="cmfcmenubargetmenuitem"></a><a name="getmenuitem"></a>CMFC메뉴바::겟메뉴아이템

항목 인덱스를 기반으로 메뉴 모음에서 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) 개체를 검색합니다.

```
CMFCToolBarButton* GetMenuItem(int iItem) const;
```

### <a name="parameters"></a>매개 변수

*iItem*<br/>
【인】 반환할 메뉴 항목의 인덱스입니다.

### <a name="return-value"></a>Return Value

*iItem*에서 `CMFCToolBarButton` 지정한 인덱스와 일치하는 개체에 대한 포인터입니다. 인덱스가 유효하지 않은 경우 NULL입니다.

## <a name="cmfcmenubargetrowheight"></a><a name="getrowheight"></a>CMFC메뉴바::겟로우높이

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubargetsystembutton"></a><a name="getsystembutton"></a>CMFC메뉴바::겟시스템 버튼

```
CMFCToolBarMenuButtonsButton* GetSystemButton(
    UINT uiBtn,
    BOOL bByCommand = TRUE) const;
```

### <a name="parameters"></a>매개 변수

【인】 *uiBtn*<br/>

【인】 *bByCommand*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubargetsystembuttonscount"></a><a name="getsystembuttonscount"></a>CMFC메뉴바::겟시스템 버튼카운트

```
int GetSystemButtonsCount() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubargetsystemmenu"></a><a name="getsystemmenu"></a>CMFC메뉴바::겟시스템메뉴

```
CMFCToolBarSystemMenuButton* GetSystemMenu() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubarhighlightdisableditems"></a><a name="highlightdisableditems"></a>CMFC메뉴바::강조 표시 안 함항목

프레임워크에서 비활성화된 메뉴 항목을 강조 하는지 여부를 제어합니다.

```
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```

### <a name="parameters"></a>매개 변수

*bHighlight*<br/>
【인】 프레임워크에서 사용할 수 없는 메뉴 항목을 강조 표시할지 여부를 나타내는 부울 매개 변수입니다.

### <a name="remarks"></a>설명

기본적으로 프레임워크는 사용자가 마우스 포인터를 위에 배치할 때 사용할 수 없는 메뉴 항목을 강조 표시하지 않습니다.

## <a name="cmfcmenubarisbuttonextrasizeavailable"></a><a name="isbuttonextrasizeavailable"></a>CMFC메뉴바::이버튼엑스트라사이즈사용 가능

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubarishighlightdisableditems"></a><a name="ishighlightdisableditems"></a>CMFC메뉴바::하이라이트 비활성화항목

프레임워크에서 사용할 수 없는 메뉴 항목을 강조 표시할지 여부를 나타냅니다.

```
static BOOL IsHighlightDisabledItems();
```

### <a name="return-value"></a>Return Value

TRUE 를 사용할 수 없는 메뉴 항목이 강조 표시되어 있는 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

기본적으로 프레임워크는 사용자가 마우스 포인터를 위에 배치할 때 사용할 수 없는 메뉴 항목을 강조 표시하지 않습니다. [CMFCMenuBar::강조 표시장애인항목](#highlightdisableditems) 메서드를 사용하여 이 기능을 활성화합니다.

## <a name="cmfcmenubarismenushadows"></a><a name="ismenushadows"></a>CMFC메뉴바::이스메뉴섀도우

프레임워크가 팝업 메뉴에 대한 그림자를 그리는지 여부를 나타냅니다.

```
static BOOL IsMenuShadows();
```

### <a name="return-value"></a>Return Value

TRUE 프레임워크가 메뉴 그림자를 그리는 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

[CMFCMenuBar::EnableMenuShadows 메서드를](#enablemenushadows) 사용하여 이 기능을 사용하거나 사용하지 않도록 설정합니다.

## <a name="cmfcmenubarisrecentlyusedmenus"></a><a name="isrecentlyusedmenus"></a>CMFC메뉴바::최근 사용 메뉴

최근에 사용한 메뉴 명령이 메뉴 모음에 표시되는지 여부를 나타냅니다.

```
static BOOL IsRecentlyUsedMenus();
```

### <a name="return-value"></a>Return Value

개체에 최근에 `CMFCMenuBar` 사용된 메뉴 명령이 표시되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

[CMFCMenuBar::Set최근사용메뉴메뉴를](#setrecentlyusedmenus) 사용하여 메뉴 모음에 최근에 사용한 메뉴 명령어가 표시되는지 여부를 제어합니다.

## <a name="cmfcmenubarisshowallcommands"></a><a name="isshowallcommands"></a>CMFC메뉴바::이쇼올커맨드

메뉴에 모든 명령이 표시되는지 여부를 나타냅니다.

```
static BOOL IsShowAllCommands();
```

### <a name="return-value"></a>Return Value

모든 명령을 `CMFCMenuBar` 표시하는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

개체는 `CMFCMenuBar` 모든 명령을 표시하거나 명령의 하위 집합만 표시하도록 구성할 수 있습니다. 이 기능에 대한 자세한 내용은 [CMFCMenuBar 클래스를](../../mfc/reference/cmfcmenubar-class.md)참조하십시오.

`IsShowAllCommands`이 기능이 `CMFCMenuBar` 개체에 대해 어떻게 구성되는지 알려줍니다. 표시되는 메뉴 명령을 제어하려면 [CMFCMenuBar::SetShowAllCommands](#setshowallcommands) 및 [CMFCMenuBar::Set최근사용 메뉴](#setrecentlyusedmenus)메서드 를 사용합니다.

## <a name="cmfcmenubarisshowallcommandsdelay"></a><a name="isshowallcommandsdelay"></a>CMFC메뉴바::이쇼올커맨드딜지연

[CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 개체가 짧은 지연 후 모든 명령을 표시하는지 여부를 나타냅니다.

```
static BOOL IsShowAllCommandsDelay();
```

### <a name="return-value"></a>Return Value

메뉴 모음이 짧은 지연 후 전체 메뉴를 표시하는 경우 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

최근에 사용한 항목을 표시하도록 메뉴 모음을 구성하면 메뉴 모음에 다음 두 가지 방법 중 하나로 전체 메뉴가 표시됩니다.

- 사용자가 메뉴 아래쪽의 화살표 위로 커서를 마우스로 가리키면 프로그래밍된 지연 후 전체 메뉴를 표시합니다.

- 사용자가 메뉴 하단의 화살표를 클릭한 후 전체 메뉴를 표시합니다.

기본적으로 모든 `CMFCMenuBar` 객체는 이 옵션을 사용하여 짧은 지연 후 전체 메뉴를 표시합니다. 이 옵션은 `CMFCMenuBar` 클래스에서 프로그래밍 방식으로 변경할 수 없습니다. 그러나 사용자는 **사용자 지정** 대화 상자를 사용하여 도구 모음 사용자 지정 중에 동작을 변경할 수 있습니다.

## <a name="cmfcmenubarloadstate"></a><a name="loadstate"></a>CMFC메뉴바::로드스테이트

Windows 레지스트리에서 메뉴 모음의 상태를 로드합니다.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT)-1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 Windows 레지스트리 키의 경로를 포함하는 문자열입니다.

*nIndex*<br/>
【인】 메뉴 모음의 컨트롤 ID입니다.

*uiID*<br/>
【인】 예약된 값입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

[CMFCMenuBar::SaveState](#savestate) 메서드를 사용하여 메뉴 모음의 상태를 레지스트리에 저장합니다. 저장된 정보에는 메뉴 항목, 도크 상태 및 메뉴 모음의 위치가 포함됩니다.

대부분의 경우 응용 프로그램은 `LoadState`을 호출하지 않습니다. 프레임워크는 작업 영역을 초기화할 때 이 메서드를 호출합니다.

## <a name="cmfcmenubaronchangehot"></a><a name="onchangehot"></a>CMFC메뉴바::온체인지핫

```
virtual void OnChangeHot(int iHot);
```

### <a name="parameters"></a>매개 변수

【인】 *아이 핫*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcmenubarondefaultmenuloaded"></a><a name="ondefaultmenuloaded"></a>CMFC메뉴바::기본메뉴 로드

프레임워크는 리소스 파일에서 메뉴 리소스를 로드할 때 이 메서드를 호출합니다.

```
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```

### <a name="parameters"></a>매개 변수

*Hmenu*<br/>
【인】 개체에 연결된 메뉴의 `CMFCMenuBar` 핸들입니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 프레임워크가 리소스 파일에서 메뉴 리소스를 로드한 후 사용자 지정 코드를 실행하도록 이 함수를 재정의합니다.

## <a name="cmfcmenubaronsendcommand"></a><a name="onsendcommand"></a>CMFC메뉴바::온센드커맨드

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>매개 변수

【인】 *p 버튼*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubaronsetdefaultbuttontext"></a><a name="onsetdefaultbuttontext"></a>CMFC메뉴바::기본 설정 단추 텍스트

사용자가 메뉴 모음에서 항목의 텍스트를 변경할 때 프레임워크는 이 메서드를 호출합니다.

```
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>매개 변수

*p 버튼*<br/>
【인】 사용자가 사용자 지정하려는 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 프레임워크가 사용자 변경 사항을 메뉴 모음에 적용하는 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드의 기본 구현은 단추의 텍스트를 사용자가 제공하는 텍스트로 변경합니다.

## <a name="cmfcmenubarontoolhittest"></a><a name="ontoolhittest"></a>CMFC메뉴바::온툴히트테스트

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

## <a name="cmfcmenubarpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFC메뉴바::P다시번역메시지

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

[in] *pMsg*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcmenubarrestoreoriginalstate"></a><a name="restoreoriginalstate"></a>CMFC메뉴바::복원오리지널스테이트

사용자가 **사용자 지정** 대화 상자에서 **재설정을** 선택할 때 프레임워크에서 호출됩니다.

```
virtual BOOL RestoreOriginalstate();
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 사용자가 사용자 지정 메뉴에서 **재설정을** 선택할 때 호출 됩니다. 이 메서드를 수동으로 호출하여 메뉴 모음의 상태를 프로그래밍 방식으로 재설정할 수도 있습니다. 이 메서드는 리소스 파일에서 원래 상태를 로드합니다.

사용자가 **재설정** 옵션을 선택할 때 처리를 수행하려는 경우 이 메서드를 재정의합니다.

## <a name="cmfcmenubarsavestate"></a><a name="savestate"></a>CMFC메뉴바::저장상태

[CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 개체의 상태를 Windows 레지스트리에 저장합니다.

```
virtual BOOL SaveState (
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT)-1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 Windows 레지스트리 키의 경로를 포함하는 문자열입니다.

*nIndex*<br/>
【인】 메뉴 모음의 컨트롤 ID입니다.

*uiID*<br/>
【인】 예약된 값입니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE; 그렇지 않으면 거짓;

### <a name="remarks"></a>설명

일반적으로 응용 프로그램은 을 `SaveState`호출하지 않습니다. 프레임워크는 작업 영역이 직렬화될 때 이 메서드를 호출합니다. 자세한 내용은 [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate)를 참조하십시오.

저장된 정보에는 메뉴 항목, 도크 상태 및 메뉴 모음의 위치가 포함됩니다.

## <a name="cmfcmenubarsetdefaultmenuresid"></a><a name="setdefaultmenuresid"></a>CMFC메뉴바:::설정기본메뉴리시드

리소스 ID를 기반으로 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) 개체의 기본 메뉴를 설정합니다.

```cpp
void SetDefaultMenuResId(UINT uiResId);
```

### <a name="parameters"></a>매개 변수

*위레시드*<br/>
【인】 새 기본 메뉴의 리소스 ID입니다.

### <a name="remarks"></a>설명

[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate) 메서드는 리소스 파일에서 기본 메뉴를 복원합니다.

[CMFCMenuBar::GetDefaultMenuResId 메서드를](#getdefaultmenuresid) 사용하여 기본 메뉴를 복원하지 않고 검색합니다.

## <a name="cmfcmenubarsetforcedownarrows"></a><a name="setforcedownarrows"></a>CMFC메뉴바::셋포스다운로우

```cpp
void SetForceDownArrows(BOOL bValue);
```

### <a name="parameters"></a>매개 변수

【인】 *b값*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcmenubarsetmaximizemode"></a><a name="setmaximizemode"></a>CMFC메뉴바::설정 최대화 모드

MDI가 표시 모드를 변경하고 메뉴 막대를 업데이트해야 할 때 프레임워크는 이 메서드를 호출합니다.

```cpp
void SetMaximizeMode(
    BOOL bMax,
    CWnd* pWnd = NULL,
    BOOL bRecalcLayout = TRUE);
```

### <a name="parameters"></a>매개 변수

*bMax*<br/>
【인】 모드를 지정하는 부울입니다. 자세한 내용은 주의 섹션을 참조하십시오.

*pWnd*<br/>
【인】 변경되는 MDI 자식 창에 대한 포인터입니다.

*bRecalcLayout*<br/>
【인】 메뉴 모음의 레이아웃을 즉시 다시 계산할지 여부를 지정하는 부울입니다.

### <a name="remarks"></a>설명

MDI 자식 창이 최대화되면 MDI 기본 프레임 창에 연결된 메뉴 모음에 시스템 메뉴와 **최소화,** **최대화** 및 **닫기** 버튼이 표시됩니다. *bMax가* TRUE이고 *pWnd가* NULL이 아닌 경우 MDI 자식 창이 최대화되고 메뉴 모음에 추가 컨트롤이 통합되어야 합니다. 그렇지 않으면 메뉴 모음이 일반 상태로 돌아갑니다.

## <a name="cmfcmenubarsetmenubuttonrtc"></a><a name="setmenubuttonrtc"></a>CMFC메뉴바::세트메뉴버튼RTC

사용자가 메뉴 단추를 만들 때 프레임워크에서 사용하는 런타임 클래스 정보를 설정합니다.

```cpp
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```

### <a name="parameters"></a>매개 변수

*p메뉴버튼RTC*<br/>
【인】 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)클래스에서 파생된 클래스에 대한 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 정보 입니다.

### <a name="remarks"></a>설명

사용자가 메뉴 모음에 새 단추를 추가하면 프레임워크에서 단추를 동적으로 만듭니다. 기본적으로 개체를 `CMFCMenuButton` 만듭니다. 이 메서드를 재정의하여 프레임워크가 만드는 단추 개체의 유형을 변경합니다.

## <a name="cmfcmenubarsetmenufont"></a><a name="setmenufont"></a>CMFC메뉴바::세트메뉴폰트

응용 프로그램의 모든 메뉴 막대에 대한 글꼴을 설정합니다.

```
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpLogFont*<br/>
【인】 설정할 글꼴을 정의하는 [LOGFONT](/windows/win32/api/dimm/ns-dimm-logfonta) 구조에 대한 포인터입니다.

*b호르츠 (주)*<br/>
【인】 TRUE *lpLogFont* 매개 변수를 세로 글꼴에 사용하려면 FALSE를 가로 글꼴에 사용하려는 경우 FALSE입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

모든 `CMFCMenuBar` 개체에 두 개의 글꼴이 사용됩니다. 이러한 별도의 글꼴은 가로 및 세로 메뉴 모음에 사용됩니다.

글꼴 설정은 전역 변수이며 `CMFCMenuBar` 모든 개체에 영향을 줍니다.

## <a name="cmfcmenubarsetrecentlyusedmenus"></a><a name="setrecentlyusedmenus"></a>CMFC메뉴바::최근 사용 메뉴

메뉴 막대에 최근에 사용한 메뉴 명령이 표시되는지 여부를 제어합니다.

```
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```

### <a name="parameters"></a>매개 변수

*본*<br/>
【인】 최근에 사용한 메뉴 명령이 표시되는지 여부를 제어하는 부울입니다.

## <a name="cmfcmenubarsetshowallcommands"></a><a name="setshowallcommands"></a>CMFC메뉴바::세트쇼올커맨드

메뉴에 사용 가능한 모든 명령이 표시되는지 여부를 제어합니다.

```
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```

### <a name="parameters"></a>매개 변수

*bShowAllCommands*<br/>
【인】 팝업 메뉴에 모든 메뉴 명령이 표시되는지 여부를 지정하는 부울 매개 변수입니다.

### <a name="remarks"></a>설명

메뉴에 모든 메뉴 명령이 표시되지 않으면 거의 사용되지 않는 명령을 숨깁니다. 메뉴 명령 표시에 대한 자세한 내용은 [CMFCMenuBar 클래스를](../../mfc/reference/cmfcmenubar-class.md)참조하십시오.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC툴바 클래스](../../mfc/reference/cmfctoolbar-class.md)
