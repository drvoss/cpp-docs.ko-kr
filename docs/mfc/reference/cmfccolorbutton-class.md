---
title: CMFC컬러버튼 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::EnableAutomaticButton
- AFXCOLORBUTTON/CMFCColorButton::EnableOtherButton
- AFXCOLORBUTTON/CMFCColorButton::GetAutomaticColor
- AFXCOLORBUTTON/CMFCColorButton::GetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColorName
- AFXCOLORBUTTON/CMFCColorButton::SetColumnsNumber
- AFXCOLORBUTTON/CMFCColorButton::SetDocumentColors
- AFXCOLORBUTTON/CMFCColorButton::SetPalette
- AFXCOLORBUTTON/CMFCColorButton::SizeToContent
- AFXCOLORBUTTON/CMFCColorButton::IsDrawXPTheme
- AFXCOLORBUTTON/CMFCColorButton::OnDraw
- AFXCOLORBUTTON/CMFCColorButton::OnDrawBorder
- AFXCOLORBUTTON/CMFCColorButton::OnDrawFocusRect
- AFXCOLORBUTTON/CMFCColorButton::OnShowColorPopup
- AFXCOLORBUTTON/CMFCColorButton::RebuildPalette
- AFXCOLORBUTTON/CMFCColorButton::UpdateColor
- AFXCOLORBUTTON/CMFCColorButton::m_bEnabledInCustomizeMode
helpviewer_keywords:
- CMFCColorButton [MFC], CMFCColorButton
- CMFCColorButton [MFC], EnableAutomaticButton
- CMFCColorButton [MFC], EnableOtherButton
- CMFCColorButton [MFC], GetAutomaticColor
- CMFCColorButton [MFC], GetColor
- CMFCColorButton [MFC], SetColor
- CMFCColorButton [MFC], SetColorName
- CMFCColorButton [MFC], SetColumnsNumber
- CMFCColorButton [MFC], SetDocumentColors
- CMFCColorButton [MFC], SetPalette
- CMFCColorButton [MFC], SizeToContent
- CMFCColorButton [MFC], IsDrawXPTheme
- CMFCColorButton [MFC], OnDraw
- CMFCColorButton [MFC], OnDrawBorder
- CMFCColorButton [MFC], OnDrawFocusRect
- CMFCColorButton [MFC], OnShowColorPopup
- CMFCColorButton [MFC], RebuildPalette
- CMFCColorButton [MFC], UpdateColor
- CMFCColorButton [MFC], m_bEnabledInCustomizeMode
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
ms.openlocfilehash: cf24c162d0eda272f73c69c434589ae6ef3332a4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752553"
---
# <a name="cmfccolorbutton-class"></a>CMFC컬러버튼 클래스

`CMFCColorButton` 및 [cmfccolorbar 클래스](../../mfc/reference/cmfccolorbar-class.md) 클래스는 색 선택 컨트롤을 구현하는데 함께 사용됩니다.

## <a name="syntax"></a>구문

```
class CMFCColorButton : public CMFCButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC컬러 버튼::CMFC컬러버튼](#cmfccolorbutton)|새 `CMFCColorButton` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|일반 색상 버튼 위에 배치된 "자동" 버튼을 활성화하고 비활성화합니다. (표준 시스템 자동 버튼은 **자동으로**레이블이 지정됩니다.)|
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|일반 색상 버튼 아래에 배치된 "기타" 버튼을 활성화하고 비활성화합니다. (표준 시스템 "기타" 버튼에는 **더 많은 색상으로**레이블이 지정됩니다.)|
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|현재 자동 색상을 검색합니다.|
|[CMFC컬러 버튼 : : GetColor](#getcolor)|단추의 색상을 검색합니다.|
|[CMFC컬러 버튼: 세트컬러](#setcolor)|단추의 색상을 설정합니다.|
|[CMFCColorButton::SetColorName](#setcolorname)|색상 이름을 설정합니다.|
|[CMFC컬러 버튼::세트열번호](#setcolumnsnumber)|색상 선택 대화 상자의 열 수를 설정합니다.|
|[CMFC컬러 버튼::세트문서색상](#setdocumentcolors)|색상 선택 대화 상자에 표시되는 문서별 색상 목록을 지정합니다.|
|[CMFC컬러 버튼::세팔레트](#setpalette)|표준 디스플레이 색상 팔레트를 지정합니다.|
|[CMFC컬러 버튼:크기토콘텐츠](#sizetocontent)|텍스트 및 이미지 크기에 따라 단추 컨트롤의 크기를 변경합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC컬러 버튼::이스드로드XP테마](#isdrawxptheme)|현재 색상 버튼이 Windows XP의 시각적 스타일에 표시되는지 여부를 나타냅니다.|
|[CMFCColorButton::OnDraw](#ondraw)|단추의 이미지를 표시 하는 프레임 워크에 의해 호출 됩니다.|
|[CMFC컬러 버튼::온드로우보더](#ondrawborder)|단추의 테두리를 표시 하는 프레임 워크에 의해 호출 됩니다.|
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|단추에 포커스가 있을 때 포커스 사각형을 표시 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|색상 선택기 대화 상자가 표시될 때 프레임워크에서 호출됩니다.|
|[CMFC컬러 버튼::리빌드팔레트](#rebuildpalette)|보호된 데이터 `m_pPalette` 멤버를 지정된 팔레트 또는 기본 시스템 팔레트로 초기화합니다.|
|[CMFCColorButton::UpdateColor](#updatecolor)|사용자가 색상 선택 대화 상자의 팔레트에서 색상을 선택할 때 프레임워크에서 호출됩니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|`m_bAltColorDlg`|부울. TRUE인 경우 *프레임워크는 다른* 단추를 클릭할 때 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 색상 대화 상자를 표시하거나 FALSE인 경우 시스템 색상 대화 상자가 표시됩니다. 기본값은 TRUE입니다. 자세한 내용은 [CMFCColorButton::인에타 버튼](#enableotherbutton)을 참조하십시오.|
|`m_bAutoSetFocus`|부울. TRUE인 경우 프레임워크는 메뉴가 표시될 때 색상 메뉴에 포커스를 설정하거나 FALSE인 경우 포커스를 변경하지 않습니다. 기본값은 TRUE입니다.|
|[CMFC컬러 버튼:m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|색상 단추에 대해 사용자 지정 모드가 활성화되어 있는지 여부를 나타냅니다.|
|`m_Color`|[COLORREF](/windows/win32/gdi/colorref) 값입니다. 현재 선택한 색상을 포함합니다.|
|`m_ColorAutomatic`|[COLORREF](/windows/win32/gdi/colorref) 값입니다. 현재 선택된 기본 색상을 포함합니다.|
|`m_Colors`|[COLORREF](/windows/win32/gdi/colorref) 값의 [배열입니다.](../../mfc/reference/carray-class.md) 현재 사용 가능한 색상이 포함되어 있습니다.|
|`m_lstDocColors`|[COLORREF](/windows/win32/gdi/colorref) 값의 [C리스트입니다.](../../mfc/reference/clist-class.md) 현재 문서 색상을 포함합니다.|
|`m_nColumns`|정수입니다. 색상 선택 메뉴의 색상 표에 표시할 열 수를 포함합니다.|
|`m_pPalette`|[CPalette에](../../mfc/reference/cpalette-class.md)대한 포인터입니다. 현재 색상 선택 메뉴에서 사용할 수 있는 색상을 포함합니다.|
|`m_pPopup`|[CMFCColorPopupMenu 클래스](../../mfc/reference/cmfccolorpopupmenu-class.md) 개체에 대한 포인터입니다. 색상 단추를 클릭하면 표시되는 색상 선택 메뉴입니다.|
|`m_strAutoColorText`|문자열입니다. 색상 선택 메뉴의 "자동" 단추 레이블입니다.|
|`m_strDocColorsText`|문자열입니다. 문서 색상을 표시하는 색상 선택 메뉴의 단추 레이블입니다.|
|`m_strOtherText`|문자열입니다. 색상 선택 메뉴의 "기타" 단추 레이블입니다.|

## <a name="remarks"></a>설명

기본적으로 클래스는 `CMFCColorButton` 색상 선택기 대화 상자를 여는 푸시 단추로 사용됩니다. 색상 선택기 대화 상자에는 작은 색상 단추 배열과 사용자 지정 색상 선택기를 표시하는 "기타" 버튼이 포함되어 있습니다. (표준 시스템 "기타" 버튼에는 **더 많은 색상으로**레이블이 지정됩니다.) 사용자가 새 색상을 선택하면 개체가 `CMFCColorButton` 변경 을 반영하고 선택한 색상을 표시합니다.

코드에서 직접 또는 **ClassWizard** 도구 및 대화 상자 템플릿을 사용하여 색상 단추 컨트롤을 만듭니다. 색상 단추 컨트롤을 직접 만드는 `CMFCColorButton` 경우 응용 프로그램에 변수를 추가한 `Create` 다음 개체의 생성자 및 메서드를 호출합니다. `CMFCColorButton` **ClassWizard를**사용하는 경우 응용 `CButton` 프로그램에 변수를 추가한 다음 변수의 `CButton` 형식을 `CMFCColorButton`에서 로 변경합니다.

프레임 워크 `OnLButtonDown` 이벤트 처리기를 호출 할 때 색상 선택기 대화 상자 [(CMFCColorBar 클래스)는](../../mfc/reference/cmfccolorbar-class.md) [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) 방법으로 표시됩니다. [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) 방법을 재정의하여 사용자 지정 색상 선택을 지원할 수 있습니다.

개체는 `CMFCColorButton` WM_COMMAND 전송하여 색상이 변경되고 있음을 부모에게 WM_COMMAND BN_CLICKED 알림입니다. 부모는 [CMFCColorButton::GetColor](#getcolor) 메서드를 사용하여 현재 색상을 검색합니다.

## <a name="example"></a>예제

다음 예제에서는 클래스에서 다양 한 메서드를 사용 `CMFCColorButton` 하 여 색상 단추를 구성 하는 방법을 보여 줍니다. 메서드는 색상 단추의 색상과 열 수를 설정하고 자동 및 기타 단추를 사용하도록 설정합니다. 이 예제는 [상태 표시줄 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxcolorbutton.h

## <a name="cmfccolorbuttoncmfccolorbutton"></a><a name="cmfccolorbutton"></a>CMFC컬러 버튼::CMFC컬러버튼

새 `CMFCColorButton` 개체를 생성합니다.

```
CMFCColorButton();
```

## <a name="cmfccolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFC컬러 버튼::인에이블오토온버튼

색상 선택기 컨트롤의 "자동" 버튼을 활성화 또는 비활성화하고 자동(기본) 색상을 설정합니다.

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 자동 단추의 텍스트를 지정합니다.

*colorAutomatic*<br/>
【인】 자동 단추의 기본 색상을 지정하는 RGB 값입니다.

*bEnable*<br/>
【인】 자동 단추를 사용하도록 설정하거나 사용하지 않도록 설정할 지 여부를 지정합니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a>CMFC컬러 버튼::인에이블기타버튼

일반 색상 버튼 아래에 나타나는 "기타" 버튼을 사용하거나 사용하지 않도록 설정합니다.

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 단추의 텍스트를 지정합니다.

*bAltColorDlg*<br/>
【인】 사용자가 단추를 클릭할 때 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 대화 상자 또는 시스템 색상 대화 상자가 열리는지 여부를 지정합니다.

*bEnable*<br/>
【인】 "기타" 버튼이 활성화되어 있는지 또는 사용하지 않도록 설정되었는지 여부를 지정합니다.

### <a name="remarks"></a>설명

"기타" 버튼을 클릭하여 색상 대화 상자를 표시합니다. *bAltColorDlg* 매개 변수가 TRUE이면 [CMFCColorDialog 클래스가](../../mfc/reference/cmfccolordialog-class.md) 표시됩니다. 그렇지 않으면 시스템 색상 대화 상자가 표시됩니다.

## <a name="cmfccolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>CMFC컬러 버튼 : : GetAutomatic색상

현재 자동(기본) 색상을 검색합니다.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Return Value

현재 자동 색상을 나타내는 RGB 값입니다.

### <a name="remarks"></a>설명

현재 자동 색상은 [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton) 메서드에 의해 설정됩니다.

## <a name="cmfccolorbuttongetcolor"></a><a name="getcolor"></a>CMFC컬러 버튼 : : GetColor

현재 선택한 색상을 검색합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Return Value

RGB 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorbuttonisdrawxptheme"></a><a name="isdrawxptheme"></a>CMFC컬러 버튼::이스드로드XP테마

현재 색상 버튼이 Windows XP의 시각적 스타일에 표시되는지 여부를 나타냅니다.

```
BOOL IsDrawXPTheme() const;
```

### <a name="return-value"></a>Return Value

시각적 스타일이 지원되고 현재 색상 버튼이 Windows XP의 시각적 스타일에 표시되는 경우 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="cmfccolorbuttonm_benabledincustomizemode"></a><a name="m_benabledincustomizemode"></a>CMFC컬러 버튼:m_bEnabledInCustomizeMode

색상 단추를 사용자 지정 모드로 설정합니다.

```
BOOL m_bEnabledInCustomizeMode;
```

### <a name="remarks"></a>설명

사용자 지정 대화 상자의 페이지에 색상 단추를 추가해야 하거나 사용자 지정 중에 다른 색상을 선택할 수 있도록 `m_bEnabledInCustomizeMode` 허용하는 경우 멤버를 TRUE로 설정하여 단추를 사용하도록 설정합니다. 기본적으로 이 멤버는 FALSE로 설정됩니다.

## <a name="cmfccolorbuttonondraw"></a><a name="ondraw"></a>CMFC컬러 버튼::온드로우

단추의 이미지를 렌더링 하는 프레임 워크에 의해 호출 됩니다.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 단추의 이미지를 렌더링하는 데 사용되는 장치 컨텍스트를 가리킵니다.

*rect*<br/>
【인】 단추를 바인딩하는 사각형입니다.

*uiState*<br/>
【인】 단추의 시각적 상태를 지정합니다.

### <a name="remarks"></a>설명

렌더링 프로세스를 사용자 지정하려면 이 메서드를 재정의합니다.

## <a name="cmfccolorbuttonondrawborder"></a><a name="ondrawborder"></a>CMFC컬러 버튼::온드로우보더

단추의 테두리를 표시 하는 프레임 워크에 의해 호출 됩니다.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 테두리를 그리는 데 사용되는 장치 컨텍스트를 가리킵니다.

*rectClient*<br/>
【인】 그릴 단추의 경계를 정의하는 *pDC* 매개 변수에 의해 지정된 장치 컨텍스트의 사각형입니다.

*uiState*<br/>
【인】 단추의 시각적 상태를 지정합니다.

### <a name="remarks"></a>설명

이 함수를 재정의하여 색상 단추의 테두리 모양을 사용자 지정합니다.

## <a name="cmfccolorbuttonondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFC컬러 버튼::온드로우포커스렉트

단추에 포커스가 있을 때 포커스 사각형을 표시 하려면 프레임 워크에서 호출 합니다.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 포커스 사각형을 그리는 데 사용되는 장치 컨텍스트를 가리킵니다.

*rectClient*<br/>
【인】 단추의 경계를 정의하는 *pDC* 매개 변수에 의해 지정된 장치 컨텍스트의 사각형입니다.

### <a name="remarks"></a>설명

포커스 사각형의 모양을 사용자 지정하려면 이 메서드를 재정의합니다.

## <a name="cmfccolorbuttononshowcolorpopup"></a><a name="onshowcolorpopup"></a>CMFC컬러 버튼::온쇼컬러팝업

팝업 색상 막대가 표시되기 전에 호출됩니다.

```
virtual void OnShowColorPopup();
```

### <a name="remarks"></a>설명

## <a name="cmfccolorbuttonrebuildpalette"></a><a name="rebuildpalette"></a>CMFC컬러 버튼::리빌드팔레트

보호된 데이터 `m_pPalette` 멤버를 지정된 팔레트 또는 기본 시스템 팔레트로 초기화합니다.

```cpp
void RebuildPalette(CPalette* pPal);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pPal*|【인】 논리 팔레트 또는 NULL에 대한 포인터입니다. NULL이면 기본 시스템 팔레트가 사용됩니다.|

## <a name="cmfccolorbuttonsetcolor"></a><a name="setcolor"></a>CMFC컬러 버튼: 세트컬러

단추의 색상을 지정합니다.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
【인】 RGB 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorbuttonsetcolorname"></a><a name="setcolorname"></a>CMFC컬러 버튼::세트컬러네임

색상의 이름을 지정합니다.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
【인】 색상의 RGB 값입니다.

*strName*<br/>
【인】 색상의 이름입니다.

### <a name="remarks"></a>설명

색상 이름 목록은 응용 프로그램별 전역입니다. 따라서이 메서드는 매개 변수를 [CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname)로 전송합니다.

## <a name="cmfccolorbuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFC컬러 버튼::세트열번호

사용자의 색상 선택 프로세스 중에 사용자에게 표시되는 색상 테이블에 표시되는 열 수를 정의합니다.

```cpp
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>매개 변수

*nColumns*<br/>
【인】 열 수를 지정합니다.

### <a name="remarks"></a>설명

사용자는 미리 정의된 색상 표를 표시하는 팝업 색상 막대에서 색상을 선택할 수 있습니다. 이 메서드를 사용 하 여 테이블의 열 수를 정의 합니다.

## <a name="cmfccolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a>CMFC컬러 버튼::세트문서색상

색상 집합과 집합 이름을 지정합니다. [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md) 개체를 사용하여 색상 집합이 표시됩니다.

```cpp
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 문서 색상 세트와 함께 표시할 레이블을 지정합니다.

*lstColors*<br/>
【인】 RGB 값 목록에 대한 참조입니다.

### <a name="remarks"></a>설명

개체는 `CMFCColorButton` [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md) 개체로 전송되는 RGB 값 목록을 유지 관리합니다. 색상 막대가 표시되면 이러한 색상은 *lpszLabel* 매개 변수에 의해 레이블이 지정된 특수 섹션에 표시됩니다.

## <a name="cmfccolorbuttonsetpalette"></a><a name="setpalette"></a>CMFC컬러 버튼::세팔레트

팝업 색상 막대에 표시할 표준 색상을 지정합니다.

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>매개 변수

*pPalette*<br/>
【인】 색상 팔레트에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorbuttonsizetocontent"></a><a name="sizetocontent"></a>CMFC컬러 버튼:크기토콘텐츠

텍스트와 이미지에 맞게 단추 컨트롤의 크기를 조정합니다.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>매개 변수

*bCalcOnly*<br/>
【인】 0이 아닌 경우 단추 컨트롤의 새 크기가 계산되지만 실제 크기는 변경되지 않습니다.

### <a name="return-value"></a>Return Value

새 `CSize` 단추 컨트롤 크기를 지정하는 개체입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorbuttonupdatecolor"></a><a name="updatecolor"></a>CMFC컬러 버튼::업데이트컬러

사용자가 색상 단추를 클릭할 때 표시되는 색상 표시줄에서 색상을 선택할 때 프레임워크에서 호출됩니다.

```
virtual void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
【인】 사용자가 선택한 색상입니다.

### <a name="remarks"></a>설명

이 `UpdateColor` 함수는 현재 선택한 단추의 색상을 변경하고 표준 알림이 BN_CLICKED WM_COMMAND 메시지를 보내 부모에게 알리고 있습니다. [CMFCColorButton::GetColor](#getcolor) 메서드를 사용하여 선택한 색상을 검색합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC버튼 클래스](../../mfc/reference/cmfcbutton-class.md)<br/>
[CMFC컬러바 클래스](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)<br/>
[COLORREF](/windows/win32/gdi/colorref)<br/>
[C팔레트 클래스](../../mfc/reference/cpalette-class.md)<br/>
[CArray 클래스](../../mfc/reference/carray-class.md)<br/>
[CList 클래스](../../mfc/reference/clist-class.md)<br/>
[Cstring](../../atl-mfc-shared/reference/cstringt-class.md)
