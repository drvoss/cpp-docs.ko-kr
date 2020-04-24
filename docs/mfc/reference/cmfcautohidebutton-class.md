---
title: CMFC자동숨기기버튼 클래스
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::BringToTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Create
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAlignment
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAutoHideWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetParentToolBar
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetRect
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetTextSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::HighlightButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsActive
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHighlighted
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHorizontal
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsVisible
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Move
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDraw
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDrawBorder
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnFillBackground
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ReplacePane
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowAttachedWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::UnSetAutoHideMode
helpviewer_keywords:
- CMFCAutoHideButton [MFC], BringToTop
- CMFCAutoHideButton [MFC], Create
- CMFCAutoHideButton [MFC], GetAlignment
- CMFCAutoHideButton [MFC], GetAutoHideWindow
- CMFCAutoHideButton [MFC], GetParentToolBar
- CMFCAutoHideButton [MFC], GetRect
- CMFCAutoHideButton [MFC], GetSize
- CMFCAutoHideButton [MFC], GetTextSize
- CMFCAutoHideButton [MFC], HighlightButton
- CMFCAutoHideButton [MFC], IsActive
- CMFCAutoHideButton [MFC], IsHighlighted
- CMFCAutoHideButton [MFC], IsHorizontal
- CMFCAutoHideButton [MFC], IsTop
- CMFCAutoHideButton [MFC], IsVisible
- CMFCAutoHideButton [MFC], Move
- CMFCAutoHideButton [MFC], OnDraw
- CMFCAutoHideButton [MFC], OnDrawBorder
- CMFCAutoHideButton [MFC], OnFillBackground
- CMFCAutoHideButton [MFC], ReplacePane
- CMFCAutoHideButton [MFC], ShowAttachedWindow
- CMFCAutoHideButton [MFC], ShowButton
- CMFCAutoHideButton [MFC], UnSetAutoHideMode
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
ms.openlocfilehash: 3ea6ce13b8cca7e0130fe14459a832b476391b0c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751679"
---
# <a name="cmfcautohidebutton-class"></a>CMFC자동숨기기버튼 클래스

숨기도록 구성된 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) 를 표시하거나 숨기는 단추입니다.

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCAutoHideButton : public CObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCAutoHideButton::BringToTop](#bringtotop)||
|[CMFCAutoHideButton::Create](#create)|자동 숨기기 단추를 만들고 초기화합니다.|
|[CMFCAutoHideButton::GetAlignment](#getalignment)|자동 숨기기 단추의 맞춤을 검색합니다.|
|[CMFCAutoHideButton::GetAutoHideWindow](#getautohidewindow)|자동 숨기기 단추와 연결된 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 개체를 반환합니다.|
|[CMFCAutoHideButton::GetParentToolBar](#getparenttoolbar)||
|[CMFCAutoHideButton::GetRect](#getrect)||
|[CMFCAutoHideButton::GetSize](#getsize)|자동 숨기기 단추의 크기를 결정합니다.|
|[CMFCAutoHideButton::GetTextSize](#gettextsize)|자동 숨기기 단추에 대한 텍스트 레이블의 크기를 반환합니다.|
|[CMFCAutoHideButton::HighlightButton](#highlightbutton)|자동 숨기기 단추를 강조 표시합니다.|
|[CMFCAutoHideButton::IsActive](#isactive)|자동 숨기기 단추가 활성 상태인지를 나타냅니다.|
|[CMFCAutoHideButton::IsHighlighted](#ishighlighted)|자동 숨기기 단추의 강조 표시 상태를 반환합니다.|
|[CMFCAutoHideButton::IsHorizontal](#ishorizontal)|자동 숨기기 단추가 가로 또는 세로로 표시되는지를 결정합니다.|
|[CMFCAutoHideButton::IsTop](#istop)||
|[CMFCAutoHideButton::IsVisible](#isvisible)|단추의 표시 여부를 나타냅니다.|
|[CMFCAutoHideButton::Move](#move)||
|[CMFCAutoHideButton::OnDraw](#ondraw)|자동 숨기기 단추를 그릴 때 프레임워크에서 이 메서드를 호출합니다.|
|[CMFCAutoHideButton::OnDrawBorder](#ondrawborder)|자동 숨기기 단추의 테두리를 그릴 때 프레임워크에서 이 메서드를 호출합니다.|
|[CMFCAutoHideButton::OnFillBackground](#onfillbackground)|자동 숨기기 단추의 배경을 채울 때 프레임워크에서 이 메서드를 호출합니다.|
|[CMFCAutoHideButton::ReplacePane](#replacepane)||
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|연결된 [CDockablePane 클래스를](../../mfc/reference/cdockablepane-class.md)표시하거나 숨깁니다.|
|[CMFCAutoHideButton::ShowButton](#showbutton)|자동 숨기기 단추를 표시하거나 숨깁니다.|
|[CMFCAutoHideButton::UnSetAutoHideMode](#unsetautohidemode)||

## <a name="remarks"></a>설명

생성 시 `CMFCAutoHideButton` 개체는 [CDockablePane 클래스에](../../mfc/reference/cdockablepane-class.md)연결됩니다. 사용자가 `CMFCAutoHideButton` 개체를 조작할 때 `CDockablePane` 개체가 숨겨지거나 표시됩니다.

기본적으로 프레임워크에서는 사용자가 자동 숨기기를 설정할 때 자동으로 `CMFCAutoHideButton`을 만듭니다. 프레임워크에서는 `CMFCAutoHideButton` 클래스 대신 사용자 지정 UI 클래스의 요소를 만들 수 있습니다. 프레임워크에서 사용해야 하는 사용자 지정 UI 클래스를 지정하려면 사용자 지정 UI 클래스와 같은 정적 멤버 변수 `CMFCAutoHideBar::m_pAutoHideButtonRTS`를 설정합니다. 기본적으로 이 변수는 `CMFCAutoHideButton`으로 설정됩니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCAutoHideButton` 개체를 생성하고 `CMFCAutoHideButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 예제에서는 `Create` 메서드를 사용하여 `CMFCAutoHideButton` 개체를 초기화하고, 연결된 `CDockablePane` 클래스를 표시하고, 자동 숨기기 단추를 표시하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAutoHideButton`

## <a name="requirements"></a>요구 사항

**헤더:** afxautohidebutton.h

## <a name="cmfcautohidebuttonbringtotop"></a><a name="bringtotop"></a>CMFC자동숨기기버튼:BringToTop

```cpp
void BringToTop();
```

### <a name="remarks"></a>설명

## <a name="cmfcautohidebuttoncreate"></a><a name="create"></a>CMFC자동숨기기버튼:만들기

자동 숨기기 단추를 만들고 초기화합니다.

```
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>매개 변수

*p부모 바*<br/>
【인】 상위 도구 모음에 대한 포인터입니다.

*p자동숨기드*<br/>
【인】 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 개체에 대한 포인터입니다. 이 자동 숨기기 단추는 `CDockablePane`을 숨기고 을 표시합니다.

*dw정렬*<br/>
【인】 단추와 주 프레임 창의 정렬을 지정하는 값입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

개체를 `CMFCAutoHideButton` 만들 때 자동 숨기기 단추를 특정 `CDockablePane`. 사용자는 자동 숨기기 버튼을 사용하여 관련 `CDockablePane`을 숨기고 표시할 수 있습니다.

*dwAlignment* 매개 변수는 자동 숨기기 버튼이 응용 프로그램에 있는 위치를 나타냅니다. 이 매개 변수는 다음 값 중 하나가 될 수 있습니다.

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetalignment"></a><a name="getalignment"></a>CMFC자동숨기기버튼:정렬 정렬

자동 숨기기 단추의 맞춤을 검색합니다.

```
DWORD GetAlignment() const;
```

### <a name="return-value"></a>Return Value

자동 숨기기 단추의 현재 정렬이 포함된 DWORD 값입니다.

### <a name="remarks"></a>설명

자동 숨기기 단추의 정렬은 버튼이 응용 프로그램에 있는 위치를 나타냅니다. 다음 값 중 하나일 수 있습니다.

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CRBS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetautohidewindow"></a><a name="getautohidewindow"></a>CMFC자동숨기기버튼::겟오토하이드윈도우

자동 숨기기 단추와 연결된 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 개체를 반환합니다.

```
CDockablePane* GetAutoHideWindow() const;
```

### <a name="return-value"></a>Return Value

연결된 개체에 `CDockablePane` 대한 포인터입니다.

### <a name="remarks"></a>설명

자동 숨기기 단추를 `CDockablePane`에 연결하려면 `CDockablePane` 을 매개 변수로 [CMFCAutoHideButton:만들기](#create) 메서드에 전달합니다.

## <a name="cmfcautohidebuttongetparenttoolbar"></a><a name="getparenttoolbar"></a>CMFC자동 숨기기 버튼::GetParent도구바

```
CMFCAutoHideBar* GetParentToolBar();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcautohidebuttongetrect"></a><a name="getrect"></a>CMFC자동숨기기버튼::겟렉트

```
CRect GetRect() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcautohidebuttongetsize"></a><a name="getsize"></a>CMFC자동 숨기기 버튼::겟사이즈

자동 숨기기 단추의 크기를 결정합니다.

```
CSize GetSize() const;
```

### <a name="return-value"></a>Return Value

단추 `CSize` 크기를 포함하는 개체입니다.

### <a name="remarks"></a>설명

계산된 크기에는 자동 숨기기 단추의 테두리 크기가 포함됩니다.

## <a name="cmfcautohidebuttongettextsize"></a><a name="gettextsize"></a>CMFC자동 숨기기 버튼::GetText크기

자동 숨기기 단추에 대한 텍스트 레이블의 크기를 반환합니다.

```
virtual CSize GetTextSize() const;
```

### <a name="return-value"></a>Return Value

자동 숨기기 단추의 텍스트 크기를 포함하는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.

## <a name="cmfcautohidebuttonisactive"></a><a name="isactive"></a>CMFC자동숨기기버튼::액티브

자동 숨기기 단추가 활성 상태인지를 나타냅니다.

```
BOOL IsActive() const;
```

### <a name="return-value"></a>Return Value

자동 숨기기 버튼이 활성화되어 있는 경우 TRUE; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

연결된 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md) 창이 표시될 때 자동 숨기기 버튼이 활성화됩니다.

## <a name="cmfcautohidebuttonishorizontal"></a><a name="ishorizontal"></a>CMFC자동숨기기버튼:수평

자동 숨기기 단추가 가로 또는 세로로 표시되는지를 결정합니다.

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Return Value

버튼이 수평인 경우 0이 아닙니다. 0 그렇지 않으면.

### <a name="remarks"></a>설명

프레임워크는 [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) 개체를 만들 때 의 방향을 설정합니다.  [CMFC자동 숨기기 버튼::만들기](#create) 메서드에서 *dwAlignment* 매개 변수를 사용하여 방향을 제어할 수 있습니다.

## <a name="cmfcautohidebuttonistop"></a><a name="istop"></a>CMFC자동숨기기버튼:이스탑

```
BOOL IsTop() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcautohidebuttonisvisible"></a><a name="isvisible"></a>CMFC자동 숨기기 버튼::볼 수 있습니다.

자동 숨기기 버튼이 표시되는지 여부를 나타냅니다.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Return Value

TRUE 단추를 볼 수 있는 경우; 그렇지 않으면 거짓.

## <a name="cmfcautohidebuttonondraw"></a><a name="ondraw"></a>CMFC자동 숨기기 버튼::온드로우

자동 숨기기 단추를 그릴 때 프레임워크에서 이 메서드를 호출합니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

### <a name="remarks"></a>설명

응용 프로그램에서 자동 숨기기 단추의 모양을 사용자 지정하려면 `CMFCAutoHideButton`에서 파생된 새 클래스를 만듭니다. 파생 클래스에서 이 메서드를 재정의합니다.

## <a name="cmfcautohidebuttonondrawborder"></a><a name="ondrawborder"></a>CMFC자동숨기기버튼::온드로우보더

자동 숨기기 단추의 테두리를 그릴 때 프레임워크에서 이 메서드를 호출합니다.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*정류 바운드*<br/>
【인】 자동 숨기기 단추의 경계 사각형입니다.

*직사각형 테두리크기*<br/>
【인】 자동 숨기기 단추의 각 면에 대한 테두리 두께입니다.

### <a name="remarks"></a>설명

응용 프로그램에서 각 자동 숨기기 단추의 테두리를 사용자 지정하려면 `CMFCAutoHideButton`에서 파생된 새 클래스를 만듭니다. 파생 클래스에서 이 메서드를 재정의합니다.

## <a name="cmfcautohidebuttononfillbackground"></a><a name="onfillbackground"></a>CMFC자동숨기기버튼::온필백

자동 숨기기 단추의 배경을 채울 때 프레임워크에서 이 메서드를 호출합니다.

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 자동 숨기기 단추의 경계 사각형입니다.

### <a name="remarks"></a>설명

응용 프로그램에서 자동 숨기기 단추에 대한 배경을 사용자 지정하려면 `CMFCAutoHideButton`에서 파생된 새 클래스를 만듭니다. 파생 클래스에서 이 메서드를 재정의합니다.

## <a name="cmfcautohidebuttonshowattachedwindow"></a><a name="showattachedwindow"></a>CMFC자동숨기기버튼::쇼첨부윈도우

연결된 [CDockablePane 클래스를](../../mfc/reference/cdockablepane-class.md)표시하거나 숨깁니다.

```cpp
void ShowAttachedWindow(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
【인】 이 메서드에 연결된 `CDockablePane`을 표시하는지 여부를 지정하는 부울입니다.

## <a name="cmfcautohidebuttonshowbutton"></a><a name="showbutton"></a>CMFC자동 숨기기 버튼::쇼버튼

자동 숨기기 단추를 표시하거나 숨깁니다.

```
virtual void ShowButton(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
【인】 자동 숨기기 단추를 표시할지 여부를 지정하는 부울입니다.

## <a name="cmfcautohidebuttonmove"></a><a name="move"></a>CMFC자동숨기기버튼::이동

```cpp
void Move(int nOffset);
```

### <a name="parameters"></a>매개 변수

【인】 *n오프셋*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcautohidebuttonreplacepane"></a><a name="replacepane"></a>CMFC자동 숨기기 버튼::교체판

```cpp
void ReplacePane(CDockablePane* pNewBar);
```

### <a name="parameters"></a>매개 변수

【인】 *p뉴바*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcautohidebuttonunsetautohidemode"></a><a name="unsetautohidemode"></a>CMFC자동숨기기버튼::언셋자동하이드모드

자동 숨기기 모드를 사용하지 않도록 설정합니다.

```
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```

### <a name="parameters"></a>매개 변수

*p퍼스트바인그룹*<br/>
【인】 그룹의 첫 번째 막대에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmfcautohidebuttonhighlightbutton"></a><a name="highlightbutton"></a>CMFC자동숨기기버튼::강조 표시버튼

자동 숨기기 버튼을 강조 합니다.

```
virtual void HighlightButton(BOOL bHighlight);
```

### <a name="parameters"></a>매개 변수

*bHighlight*<br/>
새 자동 숨기기 단추 상태를 지정합니다. TRUE는 단추가 강조 표시되고 FALSE는 단추가 강조 표시되지 않음을 나타냅니다.

### <a name="remarks"></a>설명

## <a name="cmfcautohidebuttonishighlighted"></a><a name="ishighlighted"></a>CMFC자동숨기기버튼::강조 표시

자동 숨기기 단추의 강조 표시 상태를 반환합니다.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Return Value

자동 숨기기 단추가 강조 표시되면 TRUE를 반환합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAutoHideBar 클래스](../../mfc/reference/cmfcautohidebar-class.md)<br/>
[CAutoHideDock사이트 클래스](../../mfc/reference/cautohidedocksite-class.md)
