---
title: CMFCPopupMenuBar 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::AdjustSizeImmediate
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::BuildOrigItems
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::CloseDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ExportToMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::FindDestintationToolBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetCurrentMenuImageSize
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetDefaultMenuId
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetLastCommandIndex
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ImportFromMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsDropDownListMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsPaletteMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanel
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanelInRegularMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::LoadFromHash
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::RestoreDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetButtonStyle
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::StartPopupMenuTimer
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::m_bDisableSideBarInXPMode
helpviewer_keywords:
- CMFCPopupMenuBar [MFC], AdjustSizeImmediate
- CMFCPopupMenuBar [MFC], BuildOrigItems
- CMFCPopupMenuBar [MFC], CloseDelayedSubMenu
- CMFCPopupMenuBar [MFC], ExportToMenu
- CMFCPopupMenuBar [MFC], FindDestintationToolBar
- CMFCPopupMenuBar [MFC], GetCurrentMenuImageSize
- CMFCPopupMenuBar [MFC], GetDefaultMenuId
- CMFCPopupMenuBar [MFC], GetLastCommandIndex
- CMFCPopupMenuBar [MFC], GetOffset
- CMFCPopupMenuBar [MFC], ImportFromMenu
- CMFCPopupMenuBar [MFC], IsDropDownListMode
- CMFCPopupMenuBar [MFC], IsPaletteMode
- CMFCPopupMenuBar [MFC], IsRibbonPanel
- CMFCPopupMenuBar [MFC], IsRibbonPanelInRegularMode
- CMFCPopupMenuBar [MFC], LoadFromHash
- CMFCPopupMenuBar [MFC], RestoreDelayedSubMenu
- CMFCPopupMenuBar [MFC], SetButtonStyle
- CMFCPopupMenuBar [MFC], SetOffset
- CMFCPopupMenuBar [MFC], StartPopupMenuTimer
- CMFCPopupMenuBar [MFC], m_bDisableSideBarInXPMode
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
ms.openlocfilehash: c0ba90246d19e8dd07c856eec6a518a8513ee665
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751928"
---
# <a name="cmfcpopupmenubar-class"></a>CMFCPopupMenuBar 클래스

팝업 메뉴에 포함된 메뉴 모음입니다.

## <a name="syntax"></a>구문

```
class CMFCPopupMenuBar : public CMFCToolBar
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|창의 레이아웃을 즉시 다시 계산합니다. [(재정의 Cpane::adjustSize즉시.)](../../mfc/reference/cpane-class.md#adjustsizeimmediate)|
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|지정된 메뉴 리소스에서 팝업 메뉴 항목을 로드합니다.|
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|지연된 팝업 메뉴 버튼을 닫습니다.|
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|팝업 메뉴 단추에서 메뉴를 빌드합니다.|
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|지정된 점이 있는 도구 모음을 찾습니다.|
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|메뉴 단추 이미지의 크기를 나타냅니다.|
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|기본 메뉴 항목의 식별자를 반환합니다.|
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|가장 최근에 호출된 메뉴 명령의 인덱스를 가져옵니다.|
|[CMFCPopupMenuBar::GetOffset](#getoffset)|팝업 메뉴 모음의 행 오프셋을 가져옵니다.|
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|지정된 메뉴에서 팝업 메뉴 단추를 가져오습니다.|
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|팝업 메뉴 모음이 드롭다운 목록 모드에 있는지 여부를 나타냅니다.|
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|팝업 메뉴 모음이 팔레트 모드에 있는지 여부를 나타냅니다.|
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|리본 패널인지 여부를 나타냅니다(기본적으로 FALSE).|
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|일반 모드에서 리본 패널인지 여부를 나타냅니다(기본적으로 FALSE).|
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|보관된 메뉴를 로드합니다.|
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|팝업 메뉴 모음을 닫기 위해 지연된 메뉴 단추를 복원합니다.|
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|지정된 인덱스에서 도구 모음 단추의 스타일을 설정합니다. [(CMFCToolBar 재정의::설정 단추 스타일.)](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle)|
|[CMFCPopupMenuBar::SetOffset](#setoffset)|팝업 메뉴 모음의 행 오프셋을 설정합니다.|
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|지정된 지연된 팝업 메뉴 단추에 대한 타이머를 시작합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CMFCPopup메뉴바::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|응용 프로그램에 Windows XP 모양이 있을 때 회색 사이드바가 표시될지 여부를 지정합니다.|

## <a name="remarks"></a>설명

는 `CMFCPopupMenuBar` [CMFCPopupMenu 클래스와](../../mfc/reference/cmfcpopupmenu-class.md) 동시에 생성되고 그 안에 내장되어 있습니다. 개체의 `CMFCPopupMenuBar` 전체 클라이언트 영역을 다룹니다. `CMFCPopupMenu` 키보드 및 마우스 입력을 지원합니다. 또한 해당 입력을 최상위 `CMFCPopupMenu` 프레임 창에 전달합니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCPopupMenuBar` `CMFCPopupMenu` 개체에서 개체를 초기화 하는 방법을 보여 줍니다. 이 코드 조각은 [클라이언트 그리기 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFC베이스툴바](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpopupmenubar.h

## <a name="cmfcpopupmenubaradjustsizeimmediate"></a><a name="adjustsizeimmediate"></a>CMFCPopup메뉴바::조정크기즉시

팝업 메뉴 모음 창의 레이아웃을 즉시 다시 계산합니다. [(재정의 CPane::adjustSize즉시](../../mfc/reference/cpane-class.md#adjustsizeimmediate).

```
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```

### <a name="parameters"></a>매개 변수

*bRecalcLayout*<br/>
【인】 TRUE는 팝업 메뉴 바 창의 레이아웃을 자동으로 다시 계산합니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubarbuildorigitems"></a><a name="buildorigitems"></a>CMFCPopup메뉴바::빌드오리그아이템

지정된 메뉴 리소스에서 팝업 메뉴 항목을 로드합니다.

```
BOOL BuildOrigItems(UINT uiMenuResID);
```

### <a name="parameters"></a>매개 변수

*uiMenuResID*<br/>
【인】 로드할 메뉴 리소스의 메뉴 ID를 지정합니다.

### <a name="return-value"></a>Return Value

성공하지 않은 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubarclosedelayedsubmenu"></a><a name="closedelayedsubmenu"></a>CMFCPopup메뉴바::클로즈딜지연서브메뉴

지연된 팝업 메뉴 단추를 닫습니다.

```
virtual void CloseDelayedSubMenu();
```

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubarexporttomenu"></a><a name="exporttomenu"></a>CMFCPopup메뉴바::내보내기메뉴

팝업 메뉴 단추에서 메뉴를 빌드합니다.

```
virtual HMENU ExportToMenu() const;
```

### <a name="return-value"></a>Return Value

새 메뉴에 핸들을 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubarfinddestintationtoolbar"></a><a name="finddestintationtoolbar"></a>CMFCPopup메뉴바::찾기디션툴바

지정된 점이 있는 도구 모음을 찾습니다.

```
CMFCToolBar* FindDestintationToolBar(CPoint point);
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
【인】 화면의 한 지점입니다.

### <a name="return-value"></a>Return Value

점이 있는 경우 또는 NULL이 있는 경우 지점이 있는 도구 모음에 핸들을 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubargetcurrentmenuimagesize"></a><a name="getcurrentmenuimagesize"></a>CMFCPopup메뉴바::겟전류메뉴이미지크기

메뉴 단추 이미지의 크기를 나타냅니다.

```
virtual CSize GetCurrentMenuImageSize() const;
```

### <a name="return-value"></a>Return Value

도구 모음에서 메뉴 단추 이미지의 크기를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubargetdefaultmenuid"></a><a name="getdefaultmenuid"></a>CMFCPopup메뉴바::GetDefaultMenuId

기본 메뉴 항목의 식별자를 반환합니다.

```
UINT GetDefaultMenuId() const;
```

### <a name="return-value"></a>Return Value

팝업 메뉴 모음에서 기본 메뉴 항목의 식별자를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubargetlastcommandindex"></a><a name="getlastcommandindex"></a>CMFCPopup메뉴바::겟라스트커맨드인덱스

가장 최근에 호출된 메뉴 명령의 인덱스를 가져옵니다.

```
static int __stdcall GetLastCommandIndex();
```

### <a name="return-value"></a>Return Value

호출된 마지막 메뉴 명령의 인덱스를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubargetoffset"></a><a name="getoffset"></a>CMFCPopup메뉴바::Getoffset

팝업 메뉴 모음의 행 오프셋을 가져옵니다.

```
int GetOffset() const;
```

### <a name="return-value"></a>Return Value

팝업 메뉴 모음의 행 오프셋을 반환합니다.

### <a name="remarks"></a>설명

이 값은 [CMFCPopupMenuBar::Setoffset을](#setoffset)사용하여 설정됩니다.

## <a name="cmfcpopupmenubarimportfrommenu"></a><a name="importfrommenu"></a>CMFCPopup메뉴바::가져오기 메뉴

지정된 메뉴에서 팝업 메뉴 단추를 가져오습니다.

```
virtual BOOL ImportFromMenu(
    HMENU hMenu,
    BOOL bShowAllCommands = FALSE);
```

### <a name="parameters"></a>매개 변수

*Hmenu*<br/>
【인】 팝업 메뉴 단추를 가져올 메뉴입니다.

*bShowAllCommands*<br/>
【인】 TRUE 메뉴의 모든 명령을 가져올 경우, 또는 거의 사용되지 않는 경우 FALSE가 숨김될 수 있습니다.

### <a name="return-value"></a>Return Value

메뉴 단추를 메뉴에서 성공적으로 가져온 경우 TRUE를 반환하거나 그렇지 않은 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubarisdropdownlistmode"></a><a name="isdropdownlistmode"></a>CMFCPopup메뉴바::이드롭다운리스트모드

팝업 메뉴 모음이 드롭다운 목록 모드에 있는지 여부를 나타냅니다.

```
BOOL IsDropDownListMode() const;
```

### <a name="return-value"></a>Return Value

팝업 메뉴 모음이 드롭다운 목록 모드인 경우 TRUE를 반환하거나 그렇지 않은 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubarispalettemode"></a><a name="ispalettemode"></a>CMFCPopup메뉴바::이스팔레트모드

팝업 메뉴 모음이 팔레트 모드에 있는지 여부를 나타냅니다.

```
BOOL IsPaletteMode() const;
```

### <a name="return-value"></a>Return Value

팔레트 모드가 활성화된 경우 TRUE를 반환하거나 그렇지 않은 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

메뉴 모음이 팔레트 모드로 설정되면 메뉴 항목이 여러 열과 제한된 수의 행에 나타납니다.

## <a name="cmfcpopupmenubarisribbonpanel"></a><a name="isribbonpanel"></a>CMFCPopup메뉴바::이리본패널

리본 패널인지 여부를 나타냅니다(기본적으로 FALSE).

```
virtual BOOL IsRibbonPanel() const;
```

### <a name="return-value"></a>Return Value

기본적으로 FALSE를 반환하여 리본 패널이 아님을 나타냅니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubarisribbonpanelinregularmode"></a><a name="isribbonpanelinregularmode"></a>CMFCPopup메뉴바::이리본패널인레귤모드

일반 모드에서 리본 패널인지 여부를 나타냅니다(기본적으로 FALSE).

```
virtual BOOL IsRibbonPanelInRegularMode() const;
```

### <a name="return-value"></a>Return Value

기본값은 기본적으로 FALSE를 반환하여 일반 모드에서 리본 패널이 아님을 나타냅니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubarloadfromhash"></a><a name="loadfromhash"></a>CMFCPopup메뉴바::로드프로부터 해시

보관된 메뉴를 로드합니다.

```
BOOL LoadFromHash(HMENU hMenu);
```

### <a name="parameters"></a>매개 변수

*Hmenu*<br/>
【인】 로드할 보관된 메뉴의 핸들입니다.

### <a name="return-value"></a>Return Value

메뉴가 성공적으로 로드된 경우 TRUE를 반환하거나 그렇지 않은 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubarm_bdisablesidebarinxpmode"></a><a name="m_bdisablesidebarinxpmode"></a>CMFCPopup메뉴바::m_bDisableSideBarInXPMode

Windows XP 모양이 있을 때 응용 프로그램에 회색 사이드바가 있는지 여부를 나타내는 부울 매개 변수입니다.

```
BOOL m_bDisableSideBarInXPMode;
```

### <a name="remarks"></a>설명

이 멤버 변수가 FALSE로 설정되어 있고 응용 프로그램에 Windows XP 모양이 있는 경우 프레임워크는 응용 프로그램에서 회색 사이드바를 그립니다.

기본값은 FALSE입니다.

## <a name="cmfcpopupmenubarrestoredelayedsubmenu"></a><a name="restoredelayedsubmenu"></a>CMFCPopup메뉴바::복원지연서브메뉴

팝업 메뉴 모음을 닫기 위해 지연된 메뉴 단추를 복원합니다.

```
virtual void RestoreDelayedSubMenu();
```

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubarsetbuttonstyle"></a><a name="setbuttonstyle"></a>CMFCPopup메뉴바::버튼 스타일

지정된 인덱스에서 도구 모음 단추의 스타일을 설정합니다. [(CMFCToolBar 재정의::설정 단추 스타일.)](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle)

```
virtual void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 스타일을 설정할 도구 모음 단추의 0기반 인덱스입니다.

*nStyle*<br/>
【인】 단추의 스타일입니다. 사용 가능한 도구 모음 단추 스타일 목록은 [도구 모음 컨트롤 스타일을](../../mfc/reference/toolbar-control-styles.md) 참조하십시오.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubarsetoffset"></a><a name="setoffset"></a>CMFCPopup메뉴바::세트오프셋

팝업 메뉴 모음의 행 오프셋을 설정합니다.

```cpp
void SetOffset(int iOffset);
```

### <a name="parameters"></a>매개 변수

*iOffset*<br/>
【인】 팝업 메뉴 막대를 오프셋해야 하는 행 수입니다.

### <a name="remarks"></a>설명

## <a name="cmfcpopupmenubarstartpopupmenutimer"></a><a name="startpopupmenutimer"></a>CMFCPopup메뉴바::스타트업메뉴타이머

지정된 지연된 팝업 메뉴 단추에 대한 타이머를 시작합니다.

```cpp
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,
    int nDelayFactor = 1);
```

### <a name="parameters"></a>매개 변수

*p메뉴 버튼*<br/>
【인】 지연 타이머를 설정할 메뉴 단추에 대한 포인터입니다.

*n지연 팩터*<br/>
【인】 표준 메뉴 지연 시간(일반적으로 반초에서 5초 사이)을 곱하는 지연 계수(최소 1개)와 동일합니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC컬러바 클래스](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFC팝메뉴 클래스](../../mfc/reference/cmfcpopupmenu-class.md)
