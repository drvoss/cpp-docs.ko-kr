---
title: CMFC버튼 클래스
ms.date: 08/28/2018
f1_keywords:
- CMFCButton
- AFXBUTTON/CMFCButton
- AFXBUTTON/CMFCButton::CleanUp
- AFXBUTTON/CMFCButton::EnableFullTextTooltip
- AFXBUTTON/CMFCButton::EnableMenuFont
- AFXBUTTON/CMFCButton::EnableWindowsTheming
- AFXBUTTON/CMFCButton::GetToolTipCtrl
- AFXBUTTON/CMFCButton::IsAutoCheck
- AFXBUTTON/CMFCButton::IsAutorepeatCommandMode
- AFXBUTTON/CMFCButton::IsCheckBox
- AFXBUTTON/CMFCButton::IsChecked
- AFXBUTTON/CMFCButton::IsHighlighted
- AFXBUTTON/CMFCButton::IsPressed
- AFXBUTTON/CMFCButton::IsPushed
- AFXBUTTON/CMFCButton::IsRadioButton
- AFXBUTTON/CMFCButton::IsWindowsThemingEnabled
- AFXBUTTON/CMFCButton::SetAutorepeatMode
- AFXBUTTON/CMFCButton::SetCheckedImage
- AFXBUTTON/CMFCButton::SetFaceColor
- AFXBUTTON/CMFCButton::SetImage
- AFXBUTTON/CMFCButton::SetMouseCursor
- AFXBUTTON/CMFCButton::SetMouseCursorHand
- AFXBUTTON/CMFCButton::SetStdImage
- AFXBUTTON/CMFCButton::SetTextColor
- AFXBUTTON/CMFCButton::SetTextHotColor
- AFXBUTTON/CMFCButton::SetTooltip
- AFXBUTTON/CMFCButton::SizeToContent
- AFXBUTTON/CMFCButton::OnDraw
- AFXBUTTON/CMFCButton::OnDrawBorder
- AFXBUTTON/CMFCButton::OnDrawFocusRect
- AFXBUTTON/CMFCButton::OnDrawText
- AFXBUTTON/CMFCButton::OnFillBackground
- AFXBUTTON/CMFCButton::SelectFont
- AFXBUTTON/CMFCButton::m_bDrawFocus
- AFXBUTTON/CMFCButton::m_bHighlightChecked
- AFXBUTTON/CMFCButton::m_bRightImage
- AFXBUTTON/CMFCButton::m_bTransparent
- AFXBUTTON/CMFCButton::m_nAlignStyle
- AFXBUTTON/CMFCButton::m_nFlatStyle
helpviewer_keywords:
- CMFCButton [MFC], CleanUp
- CMFCButton [MFC], EnableFullTextTooltip
- CMFCButton [MFC], EnableMenuFont
- CMFCButton [MFC], EnableWindowsTheming
- CMFCButton [MFC], GetToolTipCtrl
- CMFCButton [MFC], IsAutoCheck
- CMFCButton [MFC], IsAutorepeatCommandMode
- CMFCButton [MFC], IsCheckBox
- CMFCButton [MFC], IsChecked
- CMFCButton [MFC], IsHighlighted
- CMFCButton [MFC], IsPressed
- CMFCButton [MFC], IsPushed
- CMFCButton [MFC], IsRadioButton
- CMFCButton [MFC], IsWindowsThemingEnabled
- CMFCButton [MFC], SetAutorepeatMode
- CMFCButton [MFC], SetCheckedImage
- CMFCButton [MFC], SetFaceColor
- CMFCButton [MFC], SetImage
- CMFCButton [MFC], SetMouseCursor
- CMFCButton [MFC], SetMouseCursorHand
- CMFCButton [MFC], SetStdImage
- CMFCButton [MFC], SetTextColor
- CMFCButton [MFC], SetTextHotColor
- CMFCButton [MFC], SetTooltip
- CMFCButton [MFC], SizeToContent
- CMFCButton [MFC], OnDraw
- CMFCButton [MFC], OnDrawBorder
- CMFCButton [MFC], OnDrawFocusRect
- CMFCButton [MFC], OnDrawText
- CMFCButton [MFC], OnFillBackground
- CMFCButton [MFC], SelectFont
- CMFCButton [MFC], m_bDrawFocus
- CMFCButton [MFC], m_bHighlightChecked
- CMFCButton [MFC], m_bRightImage
- CMFCButton [MFC], m_bTransparent
- CMFCButton [MFC], m_nAlignStyle
- CMFCButton [MFC], m_nFlatStyle
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
ms.openlocfilehash: e949feaaac3570e1518cfb488cc1c42a471a1c46
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754875"
---
# <a name="cmfcbutton-class"></a>CMFC버튼 클래스

클래스는 `CMFCButton` 단추 텍스트 정렬, 단추 텍스트와 이미지 결합, 커서 선택 및 도구 설명 지정과 같은 [기능을 CButton](../../mfc/reference/cbutton-class.md) 클래스에 추가합니다.

## <a name="syntax"></a>구문

```
class CMFCButton : public CButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCButton::CMFCButton`|기본 생성자입니다.|
|`CMFCButton::~CMFCButton`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC 버튼 :: 정리](#cleanup)|내부 변수를 재설정하고 이미지, 비트맵 및 아이콘과 같은 할당된 리소스를 해제합니다.|
|`CMFCButton::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCButton::DrawItem`|소유자가 그린 단추의 시각적 측면이 변경된 경우 프레임워크에서 호출합니다. [(재정의: :DrawItem.)](../../mfc/reference/cbutton-class.md#drawitem)|
|[CMFC 버튼::인에이블풀텍스트툴팁](#enablefulltexttooltip)|도구 설명의 전체 텍스트를 큰 도구 설명 창에 표시할지 또는 작은 도구 설명 창에 텍스트의 잘린 버전을 표시할지 지정합니다.|
|[CMFC 버튼::인에이블메뉴폰트](#enablemenufont)|단추 텍스트 글꼴이 응용 프로그램 메뉴 글꼴과 동일한지 여부를 지정합니다.|
|[CMFC 버튼::인에이블윈도우테마잉](#enablewindowstheming)|단추 테두리의 스타일이 현재 Windows 테마에 해당하는지 여부를 지정합니다.|
|`CMFCButton::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFC 버튼 :: GetTool팁Ctrl](#gettooltipctrl)|기본 도구 설명 컨트롤에 대한 참조를 반환합니다.|
|[CMFC 버튼 :: IsAutoCheck](#isautocheck)|확인란 또는 라디오 버튼이 자동 단추인지 여부를 나타냅니다.|
|[CMFC버튼::IsAutorepeat명령모드](#isautorepeatcommandmode)|단추를 자동 반복 모드로 설정되어 있는지 여부를 나타냅니다.|
|[CMFC 버튼 ::이체크박스](#ischeckbox)|단추를 확인란 단추인지 여부를 나타냅니다.|
|[CMFC 버튼::체크됨](#ischecked)|현재 단추를 선택했는지 여부를 나타냅니다.|
|[CMFC단추::강조 표시](#ishighlighted)|단추를 강조 표시할지 여부를 나타냅니다.|
|[CMFC 버튼 : :](#ispressed)|단추를 누르고 강조 표시할지 여부를 나타냅니다.|
|[CMFC버튼::푸시](#ispushed)|단추를 눌렸는지 여부를 나타냅니다.|
|[CMFC 버튼 ::Is라디오 버튼](#isradiobutton)|단추를 라디오 단추인지 여부를 나타냅니다.|
|[CMFC버튼::IsWindowsTheming사용](#iswindowsthemingenabled)|단추 테두리의 스타일이 현재 Windows 테마에 해당하는지 여부를 나타냅니다.|
|`CMFCButton::OnDrawParentBackground`|지정된 영역에서 단추의 부모의 배경을 그립니다. [(재정의 AFX_GLOBAL_DATA::Draw부모배경](../../mfc/reference/afx-global-data-structure.md)|
|`CMFCButton::PreTranslateMessage`|창 메시지가 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 함수로 전달되기 전에 변환합니다. ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 재정의합니다.)|
|[CMFC버튼::세트자동반복모드](#setautorepeatmode)|단추를 자동 반복 모드로 설정합니다.|
|[CMFC버튼::세트이미지](#setcheckedimage)|선택된 단추의 이미지를 설정합니다.|
|[CMFC버튼::셋페이스컬러](#setfacecolor)|단추 텍스트의 배경색을 설정합니다.|
|[CMFC버튼::세트이미지](#setimage)|단추의 이미지를 설정합니다.|
|[CMFC 버튼 :: 세트 마우스 커서](#setmousecursor)|커서 이미지를 설정합니다.|
|[CMFC 버튼 :: 세트 마우스 커서핸드](#setmousecursorhand)|커서를 손 의 이미지로 설정합니다.|
|[CMFC버튼::셋스트이미지](#setstdimage)|개체를 `CMenuImages` 사용하여 단추 이미지를 설정합니다.|
|[CMFC버튼::세트텍스트컬러](#settextcolor)|선택되지 않은 단추에 대해 단추 텍스트의 색상을 설정합니다.|
|[CMFC 버튼 :: 세트텍스트핫컬러](#settexthotcolor)|선택한 단추에 대해 단추 텍스트의 색상을 설정합니다.|
|[CMFC 버튼 :: 설정 도구 팁](#settooltip)|도구 팁을 단추와 연결합니다.|
|[CMFC 버튼 ::크기토콘텐츠](#sizetocontent)|단추 텍스트와 이미지를 포함하도록 단추 크기를 조정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC 버튼 :: 온드로우](#ondraw)|단추를 그리는 프레임워크에서 호출합니다.|
|[CMFC버튼::온드로우보더](#ondrawborder)|단추의 테두리를 그리는 프레임워크에서 호출합니다.|
|[CMFC버튼::온드로우포커스렉트](#ondrawfocusrect)|단추에 대 한 포커스 사각형을 그리는 프레임 워크에 의해 호출 됩니다.|
|[CMFC 버튼 ::에 그리기 텍스트](#ondrawtext)|단추 텍스트를 그리는 프레임워크에서 호출합니다.|
|[CMFC 버튼 :: 온필백](#onfillbackground)|단추 텍스트의 배경을 그리는 프레임워크에서 호출합니다.|
|[CMFC 버튼 :: 선택 글꼴](#selectfont)|지정된 장치 컨텍스트와 연결된 글꼴을 검색합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CMFC버튼:m_nAlignStyle](#m_nalignstyle)|단추 텍스트의 정렬을 지정합니다.|
|[CMFC버튼:m_bDontUseWinXPTheme](#m_bDontUseWinXPTheme)|Windows XP 테마를 사용할지 여부를 지정합니다.|
|[CMFC버튼:m_bDrawFocus](#m_bdrawfocus)|단추 주위에 포커스 사각형을 그릴지 여부를 나타냅니다.|
|[CMFC버튼:m_nFlatStyle](#m_nflatstyle)|테두리 가없는, 평면, 세미 플랫 또는 3D와 같은 단추의 스타일을 지정합니다.|
|[CMFC버튼:m_bGrayDisabled](#m_bGrayDisabled)|TRUE이면 비활성화된 단추를 회색으로 그려야 합니다.|
|[CMFC버튼:m_bHighlightChecked](#m_bhighlightchecked)|커서가 위로 마우스를 가져간 BS_CHECKBOX 스타일 단추를 강조 표시할지 여부를 나타냅니다.|
|[CMFC버튼:m_bResponseOnButtonDown](#m_bResponseOnButtonDown)|단추 아래로 이벤트에 응답할지 여부를 나타냅니다.|
|[CMFC버튼:m_bRightImage](#m_brightimage)|단추의 오른쪽에 이미지를 표시할지 여부를 나타냅니다.|
|[CMFC버튼:m_bTopImage](#m_bTopImage)| 이미지가 단추 위에 있는지 여부를 나타냅니다.|
|[CMFC버튼:m_bTransparent](#m_btransparent)|단추의 투명 여부를 나타냅니다.|
|[CMFC버튼:m_bWasDblClk](#m_bWasDblClk)| 마지막 클릭 이벤트가 두 번 클릭되었는지 여부를 나타냅니다.|

## <a name="remarks"></a>설명

하이퍼링크를 지원하는 [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) 클래스와 색상 선택 대화 상자를 지원하는 `CMFCColorButton` 클래스와 같은 다른 유형의 단추는 클래스에서 `CMFCButton` 파생됩니다.

`CMFCButton` 개체의 스타일은 *3D,* *평면,* *반 평면* 또는 *테두리가 될*수 있습니다. 단추 텍스트는 단추의 왼쪽, 위쪽 또는 가운데에 정렬할 수 있습니다. 런타임에 버튼이 텍스트, 이미지 또는 텍스트와 이미지를 표시하는지 여부를 제어할 수 있습니다. 커서가 단추 위로 마우스를 가져간 경우 특정 커서 이미지를 표시되도록 지정할 수도 있습니다.

코드에서 직접 또는 **MFC 클래스 마법사** 도구와 대화 상자 템플릿을 사용하여 단추 컨트롤을 만듭니다. 단추 컨트롤을 직접 만드는 경우 `CMFCButton` 응용 프로그램에 변수를 추가 한 `Create` 다음 개체의 생성자 및 메서드를 `CMFCButton` 호출합니다. **MFC 클래스 마법사를**사용하는 경우 `CButton` 응용 프로그램에 변수를 추가한 다음 변수의 형식을 에서 `CButton` 로 `CMFCButton`변경합니다.

대화 상자 응용 프로그램에서 알림 메시지를 처리하려면 각 알림에 대한 메시지 맵 항목 및 이벤트 처리기를 추가합니다. 개체에서 `CMFCButton` 보낸 알림은 개체에서 보낸 알림과 동일합니다. `CButton`

## <a name="example"></a>예제

다음 예제에서는 클래스에서 다양 한 메서드를 사용 하 `CMFCButton` 여 단추의 속성을 구성 하는 방법을 보여 줍니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxbutton.h

## <a name="cmfcbuttoncleanup"></a><a name="cleanup"></a>CMFC 버튼 :: 정리

내부 변수를 재설정하고 이미지, 비트맵 및 아이콘과 같은 할당된 리소스를 해제합니다.

```
virtual void CleanUp();
```

## <a name="cmfcbuttonenablefulltexttooltip"></a><a name="enablefulltexttooltip"></a>CMFC 버튼::인에이블풀텍스트툴팁

도구 설명의 전체 텍스트를 큰 도구 설명 창에 표시할지 또는 작은 도구 설명 창에 텍스트의 잘린 버전을 표시할지 지정합니다.

```cpp
void EnableFullTextTooltip(BOOL bOn=TRUE);
```

### <a name="parameters"></a>매개 변수

*본*<br/>
【인】 TRUE는 모든 텍스트를 표시합니다. 잘린 텍스트를 표시하려면 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttonenablemenufont"></a><a name="enablemenufont"></a>CMFC 버튼::인에이블메뉴폰트

단추 텍스트 글꼴이 응용 프로그램 메뉴 글꼴과 동일한지 여부를 지정합니다.

```cpp
void EnableMenuFont(
    BOOL bOn=TRUE,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>매개 변수

*본*<br/>
【인】 TRUE 응용 프로그램 메뉴 글꼴을 단추 텍스트 글꼴로 사용 하 여; 시스템 글꼴을 사용하는 FALSE입니다. 기본값은 TRUE입니다.

*bRedraw*<br/>
【인】 TRUE는 즉시 화면을 다시 그릴; 그렇지 않으면 false입니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 단추 텍스트 글꼴을 지정하지 않으면 [CWnd::SetFont](../../mfc/reference/cwnd-class.md#setfont) 메서드를 사용하여 글꼴을 지정할 수 있습니다. 글꼴을 전혀 지정하지 않으면 프레임워크에서 기본 글꼴을 설정합니다.

## <a name="cmfcbuttonenablewindowstheming"></a><a name="enablewindowstheming"></a>CMFC 버튼::인에이블윈도우테마잉

단추 테두리의 스타일이 현재 Windows 테마에 해당하는지 여부를 지정합니다.

```
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE 는 현재 Windows 테마를 사용하여 단추 테두리를 그립니다. False는 윈도우 테마를 사용하지 않습니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드는 클래스에서 파생 된 응용 프로그램의 `CMFCButton` 모든 단추에 영향을 줍니다.

## <a name="cmfcbuttongettooltipctrl"></a><a name="gettooltipctrl"></a>CMFC 버튼 :: GetTool팁Ctrl

기본 도구 설명 컨트롤에 대한 참조를 반환합니다.

```
CToolTipCtrl& GetToolTipCtrl();
```

### <a name="return-value"></a>Return Value

기본 도구 설명 컨트롤에 대한 참조입니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttonisautocheck"></a><a name="isautocheck"></a>CMFC 버튼 :: IsAutoCheck

확인란 또는 라디오 버튼이 자동 단추인지 여부를 나타냅니다.

```
BOOL IsAutoCheck() const;
```

### <a name="return-value"></a>Return Value

단추에 스타일 BS_AUTOCHECKBOX 또는 BS_AUTORADIOBUTTON 있는 경우 true입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttonisautorepeatcommandmode"></a><a name="isautorepeatcommandmode"></a>CMFC버튼::IsAutorepeat명령모드

단추를 자동 반복 모드로 설정되어 있는지 여부를 나타냅니다.

```
BOOL IsAutorepeatCommandMode() const;
```

### <a name="return-value"></a>Return Value

TRUE 버튼이 자동 반복 모드로 설정된 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

[CMFCButton::Set자동 반복 모드](#setautorepeatmode) 메서드를 사용하여 단추를 자동 반복 모드로 설정합니다.

## <a name="cmfcbuttonischeckbox"></a><a name="ischeckbox"></a>CMFC 버튼 ::이체크박스

단추를 확인란 단추인지 여부를 나타냅니다.

```
BOOL IsCheckBox() const;
```

### <a name="return-value"></a>Return Value

단추에 BS_CHECKBOX 또는 BS_AUTOCHECKBOX 스타일이 있는 경우 true입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttonischecked"></a><a name="ischecked"></a>CMFC 버튼::체크됨

현재 단추를 선택했는지 여부를 나타냅니다.

```
BOOL IsChecked() const;
```

### <a name="return-value"></a>Return Value

현재 단추가 선택된 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

프레임워크는 다양한 종류의 단추를 검사했음을 나타내는 다양한 방법을 사용합니다. 예를 들어, 라디오 버튼에는 점이 포함되어 있을 때 선택됩니다. **X가**포함되어 있으면 확인란이 선택됩니다.

## <a name="cmfcbuttonishighlighted"></a><a name="ishighlighted"></a>CMFC단추::강조 표시

단추를 강조 표시할지 여부를 나타냅니다.

```
BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Return Value

TRUE 단추를 강조 표시 하는 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

마우스가 단추 위로 마우스를 가져가면 버튼이 강조 표시됩니다.

## <a name="cmfcbuttonispressed"></a><a name="ispressed"></a>CMFC 버튼 : :

단추를 누르고 강조 표시할지 여부를 나타냅니다.

```
BOOL IsPressed() const;
```

### <a name="return-value"></a>Return Value

버튼을 누르면 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttonispushed"></a><a name="ispushed"></a>CMFC버튼::푸시

단추를 눌렸는지 여부를 나타냅니다.

```
BOOL IsPushed() const;
```

### <a name="return-value"></a>Return Value

TRUE 단추를 누르면 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttonisradiobutton"></a><a name="isradiobutton"></a>CMFC 버튼 ::Is라디오 버튼

단추를 라디오 단추인지 여부를 나타냅니다.

```
BOOL IsRadioButton() const;
```

### <a name="return-value"></a>Return Value

단추 스타일이 BS_RADIOBUTTON BS_AUTORADIOBUTTON 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttoniswindowsthemingenabled"></a><a name="iswindowsthemingenabled"></a>CMFC버튼::IsWindowsTheming사용

단추 테두리의 스타일이 현재 Windows 테마에 해당하는지 여부를 나타냅니다.

```
static BOOL IsWindowsThemingEnabled();
```

### <a name="return-value"></a>Return Value

TRUE 단추 테두리의 스타일이 현재 Windows 테마에 해당하는 경우 그렇지 않으면 false입니다.

## <a name="cmfcbuttonm_bdontusewinxptheme"></a><a name="m_bDontUseWinXPTheme"/>CMFC버튼:m_bDontUseWinXPTheme

단추를 그릴 때 Windows XP 테마를 사용할지 여부를 지정합니다.

```
BOOL m_bDontUseWinXPTheme;
```

## <a name="cmfcbuttonm_bdrawfocus"></a><a name="m_bdrawfocus"></a>CMFC버튼:m_bDrawFocus

단추 주위에 포커스 사각형을 그릴지 여부를 나타냅니다.

```
BOOL m_bDrawFocus;
```

### <a name="remarks"></a>설명

멤버를 `m_bDrawFocus` TRUE로 설정하여 단추에 포커스가 수신되는 경우 프레임워크가 단추의 텍스트 및 이미지 주위에 포커스 사각형을 그릴 수 있도록 지정합니다.

`CMFCButton` 생성자는 이 멤버를 TRUE로 초기화합니다.

## <a name="cmfcbuttonm_bgraydisabled"></a><a name="m_bGrayDisabled"></a>CMFC버튼:m_bGrayDisabled

TRUE이면 비활성화된 단추를 회색으로 그려야 합니다.

```
BOOL m_bGrayDisabled;
```

## <a name="cmfcbuttonm_bhighlightchecked"></a><a name="m_bhighlightchecked"></a>CMFC버튼:m_bHighlightChecked

커서가 위로 마우스를 가져간 BS_CHECKBOX 스타일 단추를 강조 표시할지 여부를 나타냅니다.

```
BOOL m_bHighlightChecked;
```

### <a name="remarks"></a>설명

멤버를 `m_bHighlightChecked` TRUE로 설정하여 마우스가 마우스 위로 마우스를 가져갈 때 프레임워크가 BS_CHECKBOX 스타일 단추를 강조 표시하도록 지정합니다.

## <a name="cmfcbuttonm_bresponseonbuttondown"></a><a name="m_bResponseOnButtonDown"></a>CMFC버튼:m_bResponseOnButtonDown

단추 아래로 이벤트에 응답할지 여부를 나타냅니다.

```
BOOL m_bResponseOnButtonDown;
```

## <a name="cmfcbuttonm_brightimage"></a><a name="m_brightimage"></a>CMFC버튼:m_bRightImage

단추의 오른쪽에 이미지를 표시할지 여부를 나타냅니다.

```
BOOL m_bRightImage;
```

## <a name="cmfcbuttonm_btopimagem_btopimage"></a><a name="m_bTopImage"></a>CMFCButton::m_bTopImage](#m_bTopImage)

이미지가 단추 위에 있는지 여부를 나타냅니다.

```
BOOL m_bTopImage;
```

### <a name="remarks"></a>설명

멤버를 `m_bRightImage` TRUE로 설정하여 프레임워크가 단추의 텍스트 레이블 오른쪽에 단추의 이미지를 표시하도록 지정합니다.

## <a name="cmfcbuttonm_btransparent"></a><a name="m_btransparent"></a>CMFC버튼:m_bTransparent

단추의 투명 여부를 나타냅니다.

```
BOOL m_bTransparent;
```

### <a name="remarks"></a>설명

멤버를 `m_bTransparent` TRUE로 설정하여 프레임워크가 단추를 투명하게 만들도록 지정합니다. `CMFCButton` 생성자는 이 멤버를 FALSE로 초기화합니다.

## <a name="cmfcbuttonm_nalignstyle"></a><a name="m_nalignstyle"></a>CMFC버튼:m_nAlignStyle

단추 텍스트의 정렬을 지정합니다.

```
AlignStyle m_nAlignStyle;
```

### <a name="remarks"></a>설명

다음 `CMFCButton::AlignStyle` 열거형 값 중 하나를 사용하여 단추 텍스트의 맞춤을 지정합니다.

|값|Description|
|-----------|-----------------|
|ALIGN_CENTER|(기본값) 단추 텍스트를 단추의 가운데에 정렬합니다.|
|ALIGN_LEFT|단추 텍스트를 단추의 왼쪽에 정렬합니다.|
|ALIGN_RIGHT|단추 텍스트를 단추의 오른쪽에 정렬합니다.|

`CMFCButton` 생성자는 ALIGN_CENTER 위해 이 멤버를 초기화합니다.

## <a name="cmfcbuttonm_bwasdblclkm_bwasdblclk"></a><a name="m_bWasDblClk"></a>CMFCButton::m_bWasDblClk](#m_bWasDblClk)|

마지막 클릭 이벤트가 두 번 클릭되었는지 여부를 나타냅니다.|

```
BOOL m_bWasDblClk;
```

## <a name="cmfcbuttonm_nflatstyle"></a><a name="m_nflatstyle"></a>CMFC버튼:m_nFlatStyle

테두리 가없는, 평면, 세미 플랫 또는 3D와 같은 단추의 스타일을 지정합니다.

```
FlatStyle  m_nFlatStyle;
```

### <a name="remarks"></a>설명

다음 표에는 `CMFCButton::m_nFlatStyle` 단추의 모양을 지정하는 열거형 값이 나열되어 있습니다.

|값|Description|
|-----------|-----------------|
|BUTTONSTYLE_3D|(기본값) 버튼의 측면이 높고 입체적인 것처럼 보입니다. 단추를 클릭하면 버튼이 깊은 들여쓰기로 눌려있는 것처럼 보입니다.|
|BUTTONSTYLE_FLAT|마우스가 단추 위로 일시 중지되지 않으면 버튼이 2차원으로 나타나고 측면이 올라가지 않습니다. 마우스가 단추 위로 일시 중지되면 버튼의 3차원 측면이 낮게 나타납니다. 단추를 클릭하면 버튼이 얕은 들여쓰기로 눌려있는 것처럼 보입니다.|
|BUTTONSTYLE_SEMIFLAT|버튼의 측면이 낮고 3차원으로 나타납니다. 단추를 클릭하면 버튼이 깊은 들여쓰기로 눌려있는 것처럼 보입니다.|
|BUTTONSTYLE_NOBORDERS|단추는 측면을 들어 올리지 않고 항상 2차원으로 나타납니다. 단추를 클릭할 때 들여쓰기로 누른 것으로 나타나지 않습니다.|

`CMFCButton` 생성자는 BUTTONSTYLE_3D 위해 이 멤버를 초기화합니다.

### <a name="example"></a>예제

다음 예제에서는 `m_nFlatStyle` `CMFCButton` 클래스에서 멤버 변수의 값을 설정 하는 방법을 보여 줍니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]

## <a name="cmfcbuttonondraw"></a><a name="ondraw"></a>CMFC 버튼 :: 온드로우

단추를 그리는 프레임워크에서 호출합니다.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 단추를 바인딩하는 사각형에 대한 참조입니다.

*uiState*<br/>
【인】 현재 단추 상태입니다. 자세한 내용은 `itemState` [DRAWITEMSTRUCT 구조](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 항목의 멤버를 참조하십시오.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 고유한 코드를 사용하여 단추를 그립니다.

## <a name="cmfcbuttonondrawborder"></a><a name="ondrawborder"></a>CMFC버튼::온드로우보더

단추의 테두리를 그리는 프레임워크에서 호출합니다.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rectClient*<br/>
【인】 단추를 바인딩하는 사각형에 대한 참조입니다.

*uiState*<br/>
【인】 현재 단추 상태입니다. 자세한 내용은 `itemState` [DRAWITEMSTRUCT 구조](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 항목의 멤버를 참조하십시오.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 고유한 코드를 사용하여 테두리를 그립니다.

## <a name="cmfcbuttonondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFC버튼::온드로우포커스렉트

단추에 대 한 포커스 사각형을 그리는 프레임 워크에 의해 호출 됩니다.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rectClient*<br/>
【인】 단추를 바인딩하는 사각형에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 고유한 코드를 사용하여 포커스 사각형을 그립니다.

## <a name="cmfcbuttonondrawtext"></a><a name="ondrawtext"></a>CMFC 버튼 ::에 그리기 텍스트

단추 텍스트를 그리는 프레임워크에서 호출합니다.

```
virtual void OnDrawText(
    CDC* pDC,
    const CRect& rect,
    const CString& strText,
    UINT uiDTFlags,
    UINT uiState);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 단추를 바인딩하는 사각형에 대한 참조입니다.

*strText*<br/>
【인】 그릴 텍스트입니다.

*uiDTFlags*<br/>
【인】 텍스트의 서식을 지정하는 플래그입니다. 자세한 내용은 [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) 메서드의 *nFormat* 매개 변수를 참조하십시오.

*uiState*<br/>
[in] 예약되어 있습니다.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 고유한 코드를 사용하여 단추 텍스트를 그립니다.

## <a name="cmfcbuttononfillbackground"></a><a name="onfillbackground"></a>CMFC 버튼 :: 온필백

단추 텍스트의 배경을 그리는 프레임워크에서 호출합니다.

```
virtual void OnFillBackground(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rectClient*<br/>
【인】 단추를 바인딩하는 사각형에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 고유한 코드를 사용하여 단추의 배경을 그립니다.

## <a name="cmfcbuttonselectfont"></a><a name="selectfont"></a>CMFC 버튼 :: 선택 글꼴

지정된 장치 컨텍스트와 연결된 글꼴을 검색합니다.

```
virtual CFont* SelectFont(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

사용자 고유의 코드를 사용하여 글꼴을 검색하려면 이 메서드를 재정의합니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttonsetautorepeatmode"></a><a name="setautorepeatmode"></a>CMFC버튼::세트자동반복모드

단추를 자동 반복 모드로 설정합니다.

```cpp
void SetAutorepeatMode(int nTimeDelay=500);
```

### <a name="parameters"></a>매개 변수

*n시간 지연*<br/>
【인】 상위 창으로 전송되는 메시지 사이의 간격을 지정하는 음수가 아닌 숫자입니다. 간격은 밀리초단위로 측정되고 기본값은 500밀리초입니다. 자동 반복 메시지 모드를 사용하지 않도록 설정하려면 0을 지정합니다.

### <a name="remarks"></a>설명

이 메서드는 단추를 해제 하거나 *nTimeDelay* 매개 변수가 0으로 설정 될 때까지 부모 창에 WM_COMMAND 메시지를 계속 보냅니다.

## <a name="cmfcbuttonsetcheckedimage"></a><a name="setcheckedimage"></a>CMFC버튼::세트이미지

선택된 단추의 이미지를 설정합니다.

```cpp
void SetCheckedImage(
    HICON hIcon,
    BOOL bAutoDestroy=TRUE,
    HICON hIconHot=NULL,
    HICON hIconDisabled=NULL,
    BOOL bAlphaBlend=FALSE);

void SetCheckedImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy=TRUE,
    HBITMAP hBitmapHot=NULL,
    BOOL bMap3dColors=TRUE,
    HBITMAP hBitmapDisabled=NULL);

void SetCheckedImage(
    UINT uiBmpResId,
    UINT uiBmpHotResId=0,
    UINT uiBmpDsblResID=0);
```

### <a name="parameters"></a>매개 변수

*hIcon*<br/>
【인】 새 이미지의 비트맵과 마스크를 포함하는 아이콘을 처리합니다.

*b오토파괴*<br/>
【인】 TRUE는 비트맵 리소스가 자동으로 소멸되도록 지정합니다. 그렇지 않으면 false입니다. 기본값은 TRUE입니다.

*hIconHot*<br/>
【인】 선택한 상태에 대한 이미지가 포함된 아이콘을 처리합니다.

*hBitmap*<br/>
【인】 선택되지 않은 상태에 대한 이미지가 포함된 비트맵을 처리합니다.

*h비트맵핫*<br/>
【인】 선택한 상태에 대한 이미지가 포함된 비트맵을 처리합니다.

*bMap3d색상*<br/>
【인】 단추 배경에 대해 투명 한 색상을 지정 합니다. 즉, 단추의 얼굴입니다. 색상 값 RGB(192, 192, 192)를 사용하는 TRUE; FALSE에 의해 `AFX_GLOBAL_DATA::clrBtnFace`정의된 색상 값을 사용합니다.

*uiBmpResId*<br/>
【인】 선택되지 않은 이미지에 대한 리소스 ID입니다.

*uiBmpHotResId*<br/>
【인】 선택한 이미지의 리소스 ID입니다.

*hIcon 사용 안 함*<br/>
【인】 비활성화된 이미지의 아이콘을 처리합니다.

*h비트맵비활성화*<br/>
【인】 비활성화된 이미지가 포함된 비트맵을 처리합니다.

*uiBmpDsblResID*<br/>
【인】 비활성화된 비트맵의 리소스 ID입니다.

*b알파블렌드*<br/>
【인】 TRUE는 알파 채널을 사용하는 32비트 이미지만 사용합니다. FALSE, 알파 채널 이미지만 사용하지 않습니다. 기본값은 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttonsetfacecolor"></a><a name="setfacecolor"></a>CMFC버튼::셋페이스컬러

단추 텍스트의 배경색을 설정합니다.

```cpp
void SetFaceColor(
    COLORREF crFace,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>매개 변수

*crFace*<br/>
【인】 RGB 색상 값입니다.

*bRedraw*<br/>
【인】 TRUE는 즉시 화면을 다시 그릴; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 단추 배경 (얼굴)에 대 한 새 채우기 색상을 정의 합니다. [CMFCButton::m_bTransparent](#m_btransparent) 멤버 변수가 TRUE인 경우 배경이 채워지지 않습니다.

## <a name="cmfcbuttonsetimage"></a><a name="setimage"></a>CMFC버튼::세트이미지

단추의 이미지를 설정합니다.

```cpp
void SetImage(
    HICON hIcon,
    BOOL bAutoDestroy=TRUE,
    HICON hIconHot=NULL,
    HICON hIconDisabled=NULL,
    BOOL bAlphaBlend=FALSE);

void SetImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy=TRUE,
    HBITMAP hBitmapHot=NULL,
    BOOL bMap3dColors=TRUE,
    HBITMAP hBitmapDisabled=NULL);

void SetImage(
    UINT uiBmpResId,
    UINT uiBmpHotResId=0,
    UINT uiBmpDsblResID=0);
```

### <a name="parameters"></a>매개 변수

*hIcon*<br/>
【인】 새 이미지의 비트맵과 마스크를 포함하는 아이콘을 처리합니다.

*b오토파괴*<br/>
【인】 TRUE는 비트맵 리소스가 자동으로 소멸되도록 지정합니다. 그렇지 않으면 false입니다. 기본값은 TRUE입니다.

*hIconHot*<br/>
【인】 선택한 상태에 대한 이미지가 포함된 아이콘을 처리합니다.

*hBitmap*<br/>
【인】 선택되지 않은 상태에 대한 이미지가 포함된 비트맵을 처리합니다.

*h비트맵핫*<br/>
【인】 선택한 상태에 대한 이미지가 포함된 비트맵을 처리합니다.

*uiBmpResId*<br/>
【인】 선택되지 않은 이미지에 대한 리소스 ID입니다.

*uiBmpHotResId*<br/>
【인】 선택한 이미지의 리소스 ID입니다.

*bMap3d색상*<br/>
【인】 단추 배경에 대해 투명 한 색상을 지정 합니다. 즉, 단추의 얼굴입니다. 색상 값 RGB(192, 192, 192)를 사용하는 TRUE; FALSE에 의해 `AFX_GLOBAL_DATA::clrBtnFace`정의된 색상 값을 사용합니다.

*hIcon 사용 안 함*<br/>
【인】 비활성화된 이미지의 아이콘을 처리합니다.

*h비트맵비활성화*<br/>
【인】 비활성화된 이미지가 포함된 비트맵을 처리합니다.

*uiBmpDsblResID*<br/>
【인】 비활성화된 비트맵의 리소스 ID입니다.

*b알파블렌드*<br/>
【인】 TRUE는 알파 채널을 사용하는 32비트 이미지만 사용합니다. FALSE, 알파 채널 이미지만 사용하지 않습니다. 기본값은 FALSE입니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

다음 예제에서는 `SetImage` `CMFCButton` 클래스에서 메서드의 다양 한 버전을 사용 하는 방법을 보여 줍니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]

## <a name="cmfcbuttonsetmousecursor"></a><a name="setmousecursor"></a>CMFC 버튼 :: 세트 마우스 커서

커서 이미지를 설정합니다.

```cpp
void SetMouseCursor(HCURSOR hcursor);
```

### <a name="parameters"></a>매개 변수

*휘서 ()구커서*<br/>
【인】 커서의 핸들입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 손 커서와 같은 커서 이미지를 단추와 연결합니다. 커서는 응용 프로그램 리소스에서 로드됩니다.

### <a name="example"></a>예제

다음 예제에서는 `SetMouseCursor` `CMFCButton` 클래스에서 메서드를 사용 하는 방법을 보여 줍니다. 이 예제는 새 컨트롤 [샘플의](../../overview/visual-cpp-samples.md)코드 의 일부입니다.

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]

## <a name="cmfcbuttonsetmousecursorhand"></a><a name="setmousecursorhand"></a>CMFC 버튼 :: 세트 마우스 커서핸드

커서를 손 의 이미지로 설정합니다.

```cpp
void SetMouseCursorHand();
```

### <a name="remarks"></a>설명

이 메서드를 사용하여 손의 커서 이미지를 단추와 연결합니다. 커서는 응용 프로그램 리소스에서 로드됩니다.

## <a name="cmfcbuttonsetstdimage"></a><a name="setstdimage"></a>CMFC버튼::셋스트이미지

개체를 `CMenuImages` 사용하여 단추 이미지를 설정합니다.

```cpp
void SetStdImage(
    CMenuImages::IMAGES_IDS id,
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 `CMenuImage::IMAGES_IDS` 열거형에 정의된 단추 이미지 식별자 중 하나입니다. 이미지 값은 화살표, 핀 및 라디오 단추와 같은 이미지를 지정합니다.

*상태*<br/>
【인】 `CMenuImages::IMAGE_STATE` 열거형에 정의된 단추 이미지 상태 식별자 중 하나입니다. 이미지 상태는 검정, 회색, 밝은 회색, 흰색 및 진한 회색과 같은 단추 색상을 지정합니다. 기본값은 `CMenuImages::ImageBlack`입니다.

*id사용 안 함*<br/>
【인】 `CMenuImage::IMAGES_IDS` 열거형에 정의된 단추 이미지 식별자 중 하나입니다. 이미지는 버튼이 비활성화되어 있음을 나타냅니다. 기본값은 첫 번째 단추 `CMenuImages::IdArrowDown`이미지()입니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttonsettextcolor"></a><a name="settextcolor"></a>CMFC버튼::세트텍스트컬러

선택되지 않은 단추에 대해 단추 텍스트의 색상을 설정합니다.

```cpp
void SetTextColor(COLORREF clrText);
```

### <a name="parameters"></a>매개 변수

*clrText*<br/>
【인】 RGB 색상 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttonsettexthotcolor"></a><a name="settexthotcolor"></a>CMFC 버튼 :: 세트텍스트핫컬러

선택한 단추에 대해 단추 텍스트의 색상을 설정합니다.

```cpp
void SetTextHotColor(COLORREF clrTextHot);
```

### <a name="parameters"></a>매개 변수

*clrTextHot*<br/>
【인】 RGB 색상 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttonsettooltip"></a><a name="settooltip"></a>CMFC 버튼 :: 설정 도구 팁

도구 팁을 단추와 연결합니다.

```cpp
void SetTooltip(LPCTSTR lpszToolTipText);
```

### <a name="parameters"></a>매개 변수

*lpszTool팁텍스트*<br/>
【인】 도구 설명의 텍스트에 대한 포인터입니다. 도구 설명이 비활성화하려면 NULL을 지정합니다.

### <a name="remarks"></a>설명

## <a name="cmfcbuttonsizetocontent"></a><a name="sizetocontent"></a>CMFC 버튼 ::크기토콘텐츠

단추 텍스트와 이미지를 포함하도록 단추 크기를 조정합니다.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>매개 변수

*bCalcOnly*<br/>
【인】 TRUE는 버튼의 새 크기를 계산하지만 변경되지는 않습니다. FALSE를 클릭하여 단추의 크기를 변경합니다. 기본값은 FALSE입니다.

### <a name="return-value"></a>Return Value

단추의 새 크기를 포함하는 `CSize` 개체입니다.

### <a name="remarks"></a>설명

기본적으로 이 메서드는 10픽셀의 수평 여백과 5픽셀의 세로 여백을 포함하는 새 크기를 계산합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCLinkCtrl 클래스](../../mfc/reference/cmfclinkctrl-class.md)<br/>
[CMFC컬러버튼 클래스](../../mfc/reference/cmfccolorbutton-class.md)<br/>
[CMFCMenuButton 클래스](../../mfc/reference/cmfcmenubutton-class.md)
