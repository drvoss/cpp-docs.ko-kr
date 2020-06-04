---
title: CMFC컬러메뉴버튼 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
ms.openlocfilehash: 9c895573c626a890facfef689fce4b516aff5115
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752523"
---
# <a name="cmfccolormenubutton-class"></a>CMFC컬러메뉴버튼 클래스

클래스는 `CMFCColorMenuButton` 메뉴 명령 또는 색상 선택기 대화 상자를 시작하는 도구 모음 단추를 지원합니다.

## <a name="syntax"></a>구문

```
class CMFCColorMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC컬러메뉴버튼::CMFC컬러메뉴버튼](#cmfccolormenubutton)|`CMFCColorMenuButton` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC컬러메뉴버튼::인에이블오토온버튼](#enableautomaticbutton)|일반 색상 버튼 위에 배치된 "자동" 버튼을 활성화하고 비활성화합니다. (표준 시스템 자동 버튼은 **자동으로**레이블이 지정됩니다.)|
|[CMFC컬러메뉴버튼::문서색상 사용](#enabledocumentcolors)|시스템 색상 대신 문서별 색상을 표시할 수 있습니다.|
|[CMFC컬러 메뉴 버튼::인에이블기타버튼](#enableotherbutton)|일반 색상 버튼 아래에 배치된 "기타" 버튼을 활성화하고 비활성화합니다. (표준 시스템 "기타" 버튼에는 **더 많은 색상으로**레이블이 지정됩니다.)|
|[CMFC컬러메뉴버튼::인에이블티어티오프](#enabletearoff)|색상 창을 분리하는 기능을 활성화합니다.|
|[CMFC컬러 메뉴버튼::겟오토틱컬러](#getautomaticcolor)|현재 자동 색상을 검색합니다.|
|[CMFC컬러 메뉴 버튼 : : GetColor](#getcolor)|현재 단추의 색상을 검색합니다.|
|[CMFC컬러 메뉴 버튼::겟컬러바이CmdID](#getcolorbycmdid)|지정된 명령 ID에 해당하는 색상을 검색합니다.|
|[CMFC컬러 메뉴 버튼::온체인지부모](#onchangeparentwnd)|부모 창이 변경될 때 프레임워크에서 호출됩니다.|
|[CMFC컬러메뉴버튼:오픈컬러디아로그](#opencolordialog)|색상 선택 대화 상자를 엽니다.|
|[CMFC컬러메뉴버튼:세트컬러](#setcolor)|현재 색상 단추의 색상을 설정합니다.|
|[CMFC컬러 메뉴 버튼::세트컬러바이CmdID](#setcolorbycmdid)|지정된 색상 메뉴 단추의 색상을 설정합니다.|
|[CMFC컬러메뉴버튼:세트컬러네임](#setcolorname)|지정된 색상에 대한 새 이름을 설정합니다.|
|[CMFC컬러 메뉴 버튼::세트열번호](#setcolumnsnumber)|`CMFCColorBar` 개체에 의해 표시되는 열 수를 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC컬러메뉴버튼::복사](#copyfrom)|다른 도구 모음 단추를 현재 단추에 복사합니다.|
|[CMFC컬러 메뉴 버튼::만들기팝업 메뉴](#createpopupmenu)|색상 선택 대화 상자를 만듭니다.|
|[CMFC컬러 메뉴 버튼::비어 있는 메뉴허용](#isemptymenuallowed)|빈 메뉴가 지원되는지 여부를 나타냅니다.|
|[CMFC컬러 메뉴 버튼::온드로우](#ondraw)|단추에 이미지를 표시 하는 프레임 워크에 의해 호출 됩니다.|
|[CMFC컬러 메뉴 버튼::온드로우온커스터](#ondrawoncustomizelist)|도구 모음 사용자 `CMFCColorMenuButton` 지정 대화 상자 목록에 개체가 표시되기 전에 프레임워크에서 호출됩니다.|

## <a name="remarks"></a>설명

원래 메뉴 명령 또는 도구 모음 `CMFCColorMenuButton` 단추를 개체로 바꾸려면 `CMFCColorMenuButton` 개체를 만들고 적절한 [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md) 스타일을 설정한 다음 `ReplaceButton` [CMFCToolBar 클래스의](../../mfc/reference/cmfctoolbar-class.md) 메서드를 호출합니다. 도구 모음을 사용자 지정하는 경우 [CMFCToolBars사용자 지정Dialog::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) 메서드를 호출합니다.

[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu) 이벤트 처리기를 처리하는 동안 색상 선택기 대화 상자가 만들어집니다. 이벤트 처리기는 WM_COMMAND 메시지로 부모 프레임에 대해 사용자에게 보입니다. 개체는 `CMFCColorMenuButton` 원래 메뉴 명령 또는 도구 모음 단추에 할당된 컨트롤 ID를 보냅니다.

## <a name="example"></a>예제

다음 예제에서는 클래스의 다양한 메서드를 사용하여 색상 메뉴 단추를 `CMFCColorMenuButton` 만들고 구성하는 방법을 보여 줍니다. 이 예제에서는 `CPalette` 개체가 먼저 생성된 다음 `CMFCColorMenuButton` 클래스의 개체를 생성하는 데 사용됩니다. 그런 `CMFCColorMenuButton` 다음 개체는 자동 및 기타 단추를 사용하도록 설정하고 색상과 열 수를 설정하여 구성됩니다. 이 코드는 [Word Pad 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)

[CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxcolormenubutton.h

## <a name="cmfccolormenubuttoncmfccolormenubutton"></a><a name="cmfccolormenubutton"></a>CMFC컬러메뉴버튼::CMFC컬러메뉴버튼

`CMFCColorMenuButton` 개체를 생성합니다.

```
CMFCColorMenuButton();

CMFCColorMenuButton(
    UINT uiCmdID,
    LPCTSTR lpszText,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>매개 변수

*uiCmdID*<br/>
【인】 단추 명령 ID입니다.

*lpszText*<br/>
【인】 단추 텍스트입니다.

*pPalette*<br/>
【인】 단추의 색상 팔레트에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

첫 번째 생성자는 기본 생성자입니다. 오브젝트의 현재 색상과 자동 색상은 검은색으로 초기화됩니다(RGB(0, 0, 0)).).

두 번째 생성자는 지정된 명령 ID에 해당하는 색상으로 단추를 초기화합니다.

## <a name="cmfccolormenubuttoncopyfrom"></a><a name="copyfrom"></a>CMFC컬러메뉴버튼::복사

하나의 [CMFCToolBarMenuButton 클래스](../../mfc/reference/cmfctoolbarmenubutton-class.md)-파생 개체를 다른 개체에 복사합니다.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
【인】 복사할 소스 단추입니다.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 개체에서 파생된 개체를 복사합니다. `CMFCColorMenuButton`

## <a name="cmfccolormenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a>CMFC컬러 메뉴 버튼::만들기팝업 메뉴

색상 선택 대화 상자를 만듭니다.

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Return Value

색상 선택 대화 상자를 나타내는 개체입니다.

### <a name="remarks"></a>설명

사용자가 색상 메뉴 단추를 누를 때 이 메서드는 프레임워크에서 호출됩니다.

## <a name="cmfccolormenubuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFC컬러메뉴버튼::인에이블오토온버튼

일반 색상 버튼 위에 배치된 "자동" 버튼을 활성화하고 비활성화합니다. (표준 시스템 자동 버튼은 **자동으로**레이블이 지정됩니다.)

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 단추가 자동으로 수행될 때 표시되는 단추 텍스트를 지정합니다.

*colorAutomatic*<br/>
【인】 새 자동 색상을 지정합니다.

*bEnable*<br/>
【인】 단추는 자동인지 여부를 지정합니다.

### <a name="remarks"></a>설명

자동 버튼은 현재 기본 색상을 적용합니다.

## <a name="cmfccolormenubuttonenabledocumentcolors"></a><a name="enabledocumentcolors"></a>CMFC컬러메뉴버튼::문서색상 사용

시스템 색상 대신 문서별 색상을 표시할 수 있습니다.

```cpp
void EnableDocumentColors(
    LPCTSTR lpszLabel,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 단추 텍스트를 지정합니다.

*bEnable*<br/>
【인】 TRUE는 문서별 색상을 표시하거나 FALSE를 표시하여 시스템 색상을 표시합니다.

### <a name="remarks"></a>설명

사용자가 색상 메뉴 단추를 클릭할 때 이 방법을 사용하여 현재 문서 색상 또는 시스템 팔레트 색상을 표시합니다.

## <a name="cmfccolormenubuttonenableotherbutton"></a><a name="enableotherbutton"></a>CMFC컬러 메뉴 버튼::인에이블기타버튼

일반 색상 버튼 아래에 배치된 "기타" 버튼을 활성화하고 비활성화합니다. (표준 시스템 "기타" 버튼에는 **더 많은 색상으로**레이블이 지정됩니다.)

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 단추 텍스트를 지정합니다.

*bAltColorDlg*<br/>
【인】 `CMFCColorDialog` TRUE를 지정하여 대화 상자를 표시하거나 FALSE를 사용하여 표준 시스템 색상 대화 상자를 표시합니다.

*bEnable*<br/>
【인】 TRUE를 지정하여 "기타" 단추를 표시합니다. 그렇지 않으면 false입니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolormenubuttonenabletearoff"></a><a name="enabletearoff"></a>CMFC컬러메뉴버튼::인에이블티어티오프

색상 창을 분리하는 기능을 활성화합니다.

```cpp
void EnableTearOff(
    UINT uiID,
    int nVertDockColumns=-1,
    int nHorzDockRows=-1);
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
【인】 분리 창에 대한 ID를 지정합니다.

*nVertDock열*<br/>
【인】 분리 해제 상태에 있는 동안 수직으로 도킹된 색상 창의 열 수를 지정합니다.

*n호르즈독로우스*<br/>
【인】 분리 해제 상태에 있는 동안 수평으로 도킹된 색상 창의 행 수를 지정합니다.

### <a name="remarks"></a>설명

단추를 누를 때 팝업되는 색상 창에 대해 "분리" 기능을 `CMFCColorMenuButton` 사용하려면 이 메서드를 호출합니다.

## <a name="cmfccolormenubuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>CMFC컬러 메뉴버튼::겟오토틱컬러

현재 자동 색상을 검색합니다.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Return Value

현재 자동 색상을 나타내는 RGB 색상 값입니다.

### <a name="remarks"></a>설명

[CMFCColorMenuButton::enableAutomaticButton에](#enableautomaticbutton)의해 설정 된 자동 색상을 얻으려면이 메서드를 호출 합니다.

## <a name="cmfccolormenubuttongetcolor"></a><a name="getcolor"></a>CMFC컬러 메뉴 버튼 : : GetColor

현재 단추의 색상을 검색합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Return Value

단추의 색상입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolormenubuttongetcolorbycmdid"></a><a name="getcolorbycmdid"></a>CMFC컬러 메뉴 버튼::겟컬러바이CmdID

지정된 명령 ID에 해당하는 색상을 검색합니다.

```
static COLORREF GetColorByCmdID(UINT uiCmdID);
```

### <a name="parameters"></a>매개 변수

*uiCmdID*<br/>
【인】 명령 ID입니다.

### <a name="return-value"></a>Return Value

지정된 명령 ID에 해당하는 색상입니다.

### <a name="remarks"></a>설명

응용 프로그램에 여러 가지 색상 단추가 있는 경우 이 방법을 사용합니다. 사용자가 색상 단추를 클릭하면 단추는 WM_COMMAND 메시지에서 명령 ID를 부모에게 보냅니다. 메서드는 `GetColorByCmdID` 명령 ID를 사용하여 해당 색상을 검색합니다.

## <a name="cmfccolormenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a>CMFC컬러 메뉴 버튼::비어 있는 메뉴허용

빈 메뉴가 지원되는지 여부를 나타냅니다.

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>Return Value

빈 메뉴가 허용되는 경우 0이 아닙니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

빈 메뉴는 기본적으로 지원됩니다. 파생 클래스에서 이 동작을 변경하려면 이 메서드를 재정의합니다.

## <a name="cmfccolormenubuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFC컬러 메뉴 버튼::온체인지부모

부모 창이 변경될 때 프레임워크에서 호출됩니다.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 새 부모 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolormenubuttonondraw"></a><a name="ondraw"></a>CMFC컬러 메뉴 버튼::온드로우

단추에 이미지를 표시 하는 프레임 워크에 의해 호출 됩니다.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz=TRUE,
    BOOL bCustomizeMode=FALSE,
    BOOL bHighlight=FALSE,
    BOOL bDrawBorder=TRUE,
    BOOL bGrayDisabledButtons=TRUE);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 다시 그릴 영역을 경계하는 사각형입니다.

*p 이미지*<br/>
【인】 도구 모음 이미지 목록을 가리킵니다.

*b호르츠 (주)*<br/>
【인】 TRUE 도구 모음이 수평 도킹 상태에 있음을 지정합니다. 그렇지 않으면 false입니다. 기본값은 TRUE입니다.

*b 사용자 정의 모드*<br/>
【인】 TRUE 응용 프로그램이 사용자 지정 모드에 있음을 지정합니다. 그렇지 않으면 false입니다. 기본값은 FALSE입니다.

*bHighlight*<br/>
【인】 TRUE 단추를 강조 표시 되도록 지정 합니다. 그렇지 않으면 false입니다. 기본값은 FALSE입니다.

*b드드로우보더*<br/>
【인】 TRUE 단추의 테두리가 표시되도록 지정합니다. 그렇지 않으면 false입니다. 기본값은 TRUE입니다.

*b회색비활성화단추*<br/>
【인】 TRUE 는 비활성화된 단추가 회색(흐리게) 바꿈되도록 지정합니다. 그렇지 않으면 false입니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolormenubuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFC컬러 메뉴 버튼::온드로우온커스터

도구 모음 사용자 `CMFCColorMenuButton` 지정 대화 상자 목록에 개체가 표시되기 전에 프레임워크에서 호출됩니다.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 그릴 단추를 경계로 하는 사각형입니다.

*b 선택됨*<br/>
【인】 TRUE는 단추가 선택된 상태임을 지정합니다. 그렇지 않으면 false입니다.

### <a name="return-value"></a>Return Value

단추의 너비입니다.

### <a name="remarks"></a>설명

이 메서드는 도구 모음 `CMFCColorMenuButton` 사용자 지정 프로세스 중에 개체가 목록 상자에 표시될 때 프레임워크에서 호출됩니다.

## <a name="cmfccolormenubuttonopencolordialog"></a><a name="opencolordialog"></a>CMFC컬러메뉴버튼:오픈컬러디아로그

색상 선택 대화 상자를 엽니다.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>매개 변수

*색상기본값*<br/>
【인】 색상 대화 상자에서 선택된 기본 색상입니다.

*컬러 레스*<br/>
【아웃】 사용자가 색상 대화 상자에서 선택한 색상을 반환합니다.

### <a name="return-value"></a>Return Value

사용자가 새 색상을 선택하면 0이 아닙니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메뉴 단추를 클릭하면 이 메서드를 호출하여 색상 대화 상자를 엽니다. 반환 값이 0이 아닌 경우 사용자가 선택하는 색상이 *colorRes* 매개 변수에 저장됩니다. [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) 메서드를 사용하여 표준 색상 대화 상자와 [CMFCColorDialog 클래스](../../mfc/reference/cmfccolordialog-class.md) 대화 상자 사이를 전환할 수 있습니다.

## <a name="cmfccolormenubuttonsetcolor"></a><a name="setcolor"></a>CMFC컬러메뉴버튼:세트컬러

현재 색상 단추의 색상을 설정합니다.

```
virtual void SetColor(
    COLORREF clr,
    BOOL bNotify=TRUE);
```

### <a name="parameters"></a>매개 변수

*Clr*<br/>
【인】 RGB 색상 값입니다.

*bNotify*<br/>
【인】 TRUE는 연결된 메뉴 버튼 또는 도구 모음 버튼에 *clr* 매개 변수 색상을 적용하는 데; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 현재 색상 단추의 색상을 변경합니다. *bNotify* 매개 변수가 0이 아닌 경우 연결된 팝업 메뉴 또는 도구 모음에서 해당 단추의 색상이 *clr* 매개 변수에 의해 지정된 색상으로 변경됩니다.

## <a name="cmfccolormenubuttonsetcolorbycmdid"></a><a name="setcolorbycmdid"></a>CMFC컬러 메뉴 버튼::세트컬러바이CmdID

지정된 색상 메뉴 단추의 색상을 설정합니다.

```
static void SetColorByCmdID(
    UINT uiCmdID,
    COLORREF color);
```

### <a name="parameters"></a>매개 변수

*uiCmdID*<br/>
【인】 색상 메뉴 단추의 리소스 ID입니다.

*색*<br/>
【인】 RGB 색상 값입니다.

## <a name="cmfccolormenubuttonsetcolorname"></a><a name="setcolorname"></a>CMFC컬러메뉴버튼:세트컬러네임

지정된 색상에 대한 새 이름을 설정합니다.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
【인】 이름이 변경되는 색상의 RGB 값입니다.

*strName*<br/>
【인】 색상의 새 이름입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolormenubuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFC컬러 메뉴 버튼::세트열번호

색상 선택 [컨트롤(CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) 개체)에 표시할 열 수를 설정합니다.

```cpp
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>매개 변수

*nColumns*<br/>
【인】 표시할 열 수입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC컬러바 클래스](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFC툴바 클래스](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBars커렌드디아로그 클래스](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)<br/>
[CMFC컬러버튼 클래스](../../mfc/reference/cmfccolorbutton-class.md)
