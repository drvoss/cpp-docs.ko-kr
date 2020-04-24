---
title: CMFC컬러바 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCColorBar
- AFXCOLORBAR/CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::ContextToSize
- AFXCOLORBAR/CMFCColorBar::CreateControl
- AFXCOLORBAR/CMFCColorBar::Create
- AFXCOLORBAR/CMFCColorBar::EnableAutomaticButton
- AFXCOLORBAR/CMFCColorBar::EnableOtherButton
- AFXCOLORBAR/CMFCColorBar::GetColor
- AFXCOLORBAR/CMFCColorBar::GetCommandID
- AFXCOLORBAR/CMFCColorBar::GetHighlightedColor
- AFXCOLORBAR/CMFCColorBar::GetHorzMargin
- AFXCOLORBAR/CMFCColorBar::GetVertMargin
- AFXCOLORBAR/CMFCColorBar::IsTearOff
- AFXCOLORBAR/CMFCColorBar::SetColor
- AFXCOLORBAR/CMFCColorBar::SetColorName
- AFXCOLORBAR/CMFCColorBar::SetCommandID
- AFXCOLORBAR/CMFCColorBar::SetDocumentColors
- AFXCOLORBAR/CMFCColorBar::SetHorzMargin
- AFXCOLORBAR/CMFCColorBar::SetVertMargin
- AFXCOLORBAR/CMFCColorBar::AdjustLocations
- AFXCOLORBAR/CMFCColorBar::AllowChangeTextLabels
- AFXCOLORBAR/CMFCColorBar::AllowShowOnList
- AFXCOLORBAR/CMFCColorBar::CalcSize
- AFXCOLORBAR/CMFCColorBar::CreatePalette
- AFXCOLORBAR/CMFCColorBar::GetColorGridSize
- AFXCOLORBAR/CMFCColorBar::GetExtraHeight
- AFXCOLORBAR/CMFCColorBar::InitColors
- AFXCOLORBAR/CMFCColorBar::OnKey
- AFXCOLORBAR/CMFCColorBar::OnSendCommand
- AFXCOLORBAR/CMFCColorBar::OnUpdateCmdUI
- AFXCOLORBAR/CMFCColorBar::OpenColorDialog
- AFXCOLORBAR/CMFCColorBar::Rebuild
- AFXCOLORBAR/CMFCColorBar::SelectPalette
- AFXCOLORBAR/CMFCColorBar::SetPropList
- AFXCOLORBAR/CMFCColorBar::ShowCommandMessageString
helpviewer_keywords:
- CMFCColorBar [MFC], CMFCColorBar
- CMFCColorBar [MFC], ContextToSize
- CMFCColorBar [MFC], CreateControl
- CMFCColorBar [MFC], Create
- CMFCColorBar [MFC], EnableAutomaticButton
- CMFCColorBar [MFC], EnableOtherButton
- CMFCColorBar [MFC], GetColor
- CMFCColorBar [MFC], GetCommandID
- CMFCColorBar [MFC], GetHighlightedColor
- CMFCColorBar [MFC], GetHorzMargin
- CMFCColorBar [MFC], GetVertMargin
- CMFCColorBar [MFC], IsTearOff
- CMFCColorBar [MFC], SetColor
- CMFCColorBar [MFC], SetColorName
- CMFCColorBar [MFC], SetCommandID
- CMFCColorBar [MFC], SetDocumentColors
- CMFCColorBar [MFC], SetHorzMargin
- CMFCColorBar [MFC], SetVertMargin
- CMFCColorBar [MFC], AdjustLocations
- CMFCColorBar [MFC], AllowChangeTextLabels
- CMFCColorBar [MFC], AllowShowOnList
- CMFCColorBar [MFC], CalcSize
- CMFCColorBar [MFC], CreatePalette
- CMFCColorBar [MFC], GetColorGridSize
- CMFCColorBar [MFC], GetExtraHeight
- CMFCColorBar [MFC], InitColors
- CMFCColorBar [MFC], OnKey
- CMFCColorBar [MFC], OnSendCommand
- CMFCColorBar [MFC], OnUpdateCmdUI
- CMFCColorBar [MFC], OpenColorDialog
- CMFCColorBar [MFC], Rebuild
- CMFCColorBar [MFC], SelectPalette
- CMFCColorBar [MFC], SetPropList
- CMFCColorBar [MFC], ShowCommandMessageString
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
ms.openlocfilehash: 58fddeef9cb0afe930af84b05e6a87871f729da4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752576"
---
# <a name="cmfccolorbar-class"></a>CMFC컬러바 클래스

클래스는 `CMFCColorBar` 문서 또는 응용 프로그램에서 색상을 선택할 수 있는 도킹 컨트롤 막대를 나타냅니다.

## <a name="syntax"></a>구문

```
class CMFCColorBar : public CMFCPopupMenuBar
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CMFC컬러바::CMFC컬러바](#cmfccolorbar)|`CMFCColorBar` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC컬러바::컨텍스트토크기](#contexttosize)|색상 막대 컨트롤의 단추를 포함하는 데 필요한 수직 및 수평 여백을 계산한 다음 해당 단추의 위치를 조정합니다.|
|[CMFC컬러바::만들기제어](#createcontrol)|색상 막대 컨트롤 창을 만들고 `CMFCColorBar` 개체에 연결하고 지정된 색상 팔레트를 포함하도록 컨트롤의 크기를 조정합니다.|
|[CMFC컬러바::만들기](#create)|색상 막대 컨트롤 창을 만들고 개체에 `CMFCColorBar` 연결합니다.|
|[CMFC컬러바::인에이블오토버튼](#enableautomaticbutton)|자동 단추를 표시하거나 숨깁니다.|
|[CMFC컬러바::인에이블기타버튼](#enableotherbutton)|사용자가 더 많은 색상을 선택할 수 있는 대화 상자의 표시를 활성화하거나 사용하지 않도록 설정합니다.|
|[CMFC컬러바: 겟컬러](#getcolor)|현재 선택한 색상을 검색합니다.|
|[CMFC컬러바::겟커맨드ID](#getcommandid)|현재 색상 막대 컨트롤의 명령 ID를 검색합니다.|
|[CMFC컬러바::겟하이라이트컬러](#gethighlightedcolor)|색상 단추에 포커스가 있음을 나타내는 색상을 검색합니다. 즉, 버튼이 *뜨겁습니다.*|
|[CMFC컬러바::게호즈마진](#gethorzmargin)|왼쪽 또는 오른쪽 색상 셀과 클라이언트 영역 경계 사이의 공간인 수평 여백을 검색합니다.|
|[CMFC컬러바::게버트마진](#getvertmargin)|위쪽 또는 아래쪽 색상 셀과 클라이언트 영역 경계 사이의 공간인 수직 여백을 검색합니다.|
|[CMFC컬러바::이티어오프](#istearoff)|현재 색상 막대가 도킹 가능한지 여부를 나타냅니다.|
|[CMFC컬러바::세트컬러](#setcolor)|현재 선택된 색상을 설정합니다.|
|[CMFC컬러바::세트컬러네임](#setcolorname)|지정된 색상에 대한 새 이름을 설정합니다.|
|[CMFC컬러바::세트커맨드ID](#setcommandid)|색상 막대 컨트롤에 대한 새 명령 ID를 설정합니다.|
|[CMFC컬러바::세트문서색상](#setdocumentcolors)|현재 문서에 사용되는 색상 목록을 설정합니다.|
|[CMFC컬러바::세트호즈마진](#sethorzmargin)|왼쪽 또는 오른쪽 색상 셀과 클라이언트 영역 경계 사이의 공백인 수평 여백을 설정합니다.|
|[CMFC컬러바::세트버트마진](#setvertmargin)|상하 색상 셀과 클라이언트 영역 경계 사이의 공간인 수직 여백을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC컬러바::조정위치](#adjustlocations)|색상 막대 컨트롤의 색상 단추 위치를 조정합니다.|
|[CMFC컬러바::허용변경텍스트라벨](#allowchangetextlabels)|색상 단추의 텍스트 레이블이 변경될 수 있는지 여부를 나타냅니다.|
|[CMFC컬러바::허용쇼온리스트](#allowshowonlist)|사용자 지정 프로세스 중에 색상 막대 컨트롤 개체가 도구 모음 목록에 나타날 수 있는지 여부를 나타냅니다.|
|[CMFC컬러바::석회화](#calcsize)|레이아웃 계산 프로세스의 일부로 프레임워크에서 호출됩니다.|
|[CMFC컬러바::팔레트 만들기](#createpalette)|지정된 색상 배열의 색상으로 팔레트를 초기화합니다.|
|[CMFC컬러바::겟컬러그리드사이즈](#getcolorgridsize)|색상 막대 컨트롤의 그리드에서 행과 열 수를 계산합니다.|
|[CMFC컬러바: 겟엑스트라하이트](#getextraheight)|현재 색상 막대에서 **기타** 단추, 문서 색상 등과 같은 기타 사용자 인터페이스 요소를 표시하는 데 필요한 추가 높이를 계산합니다.|
|[CMFC컬러바::이니트 컬러](#initcolors)|지정된 팔레트 또는 시스템 기본 팔레트의 색상으로 색상 배열을 초기화합니다.|
|[CMFC컬러바::온키](#onkey)|사용자가 키보드 단추를 누를 때 프레임워크에서 호출됩니다.|
|[CMFC컬러바::온센드커맨드](#onsendcommand)|팝업 컨트롤의 계층 구조를 닫기 위해 프레임 워크에서 호출 합니다.|
|[CMFC컬러바::온업데이트CmdUI](#onupdatecmdui)|항목이 표시되기 전에 색상 막대 컨트롤의 사용자 인터페이스 항목을 사용하거나 사용하지 않도록 설정하려면 프레임워크에서 호출합니다.|
|[CMFC컬러바::오픈컬러디아로그](#opencolordialog)|색상 대화 상자를 엽니다.|
|[CMFC컬러바::리빌드](#rebuild)|색상 막대 컨트롤을 완전히 다시 그립니다.|
|[CMFC컬러바:셀렉트 팔레트](#selectpalette)|지정된 장치 컨텍스트의 논리적 팔레트를 현재 색상 막대 컨트롤의 상위 단추 팔레트로 설정합니다.|
|[CMFC컬러바::세트프로프리스트](#setproplist)|보호된 `m_pWndPropList` 데이터 멤버를 지정된 포인터로 속성 그리드 컨트롤로 설정합니다.|
|[CMFC컬러바::쇼커맨드메시지스트링](#showcommandmessagestring)|상태 표시줄에서 메시지 줄을 업데이트하려면 색상 표시줄 컨트롤을 소유하는 프레임 창을 요청합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|`m_bInternal`|마우스 이벤트가 처리되는지 여부를 결정하는 부울 필드입니다. 일반적으로 마우스 이벤트는 이 필드가 TRUE이고 사용자 지정 모드가 FALSE일 때 처리됩니다.|
|`m_bIsEnabled`|컨트롤이 활성화되어 있는지 여부를 나타내는 부울입니다.|
|`m_bIsTearOff`|색상 막대 컨트롤이 도킹을 지원하는지 여부를 나타내는 부울입니다.|
|`m_BoxSize`|색상 막대 표에서 셀 크기를 지정하는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.|
|`m_bShowDocColorsWhenDocked`|색상 막대가 도킹될 때 문서 색상을 표시할지 여부를 나타내는 부울입니다. 자세한 내용은 [CMFCColorBar::SetDocumentColors](#setdocumentcolors)를 참조하십시오.|
|`m_bStdColorDlg`|표준 시스템 색상 대화 상자 또는 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 대화 상자를 표시할지 여부를 나타내는 부울입니다. 자세한 내용은 [CMFCColorBar::인에타 버튼](#enableotherbutton)을 참조하십시오.|
|`m_ColorAutomatic`|현재 자동 색상을 저장하는 [COLORREF입니다.](/windows/win32/gdi/colorref) 자세한 내용은 [CMFCColorBar::인에타 버튼](#enableotherbutton)을 참조하십시오.|
|`m_ColorNames`|RGB 색상 집합을 이름과 연결하는 [CMap](../../mfc/reference/cmap-class.md) 개체입니다.|
|`m_colors`|색상 막대 컨트롤에 표시되는 색상을 포함하는 [COLORREF](/windows/win32/gdi/colorref) [CArray](../../mfc/reference/carray-class.md) 값입니다.|
|`m_ColorSelected`|사용자가 현재 색상 막대 컨트롤에서 선택한 색상인 [COLORREF](/windows/win32/gdi/colorref) 값입니다.|
|`m_lstDocColors`|현재 문서에서 사용되는 색상을 포함하는 [COLORREF](/windows/win32/gdi/colorref) 값의 [CList입니다.](../../mfc/reference/clist-class.md)|
|`m_nCommandID`|색상 단추의 명령 ID인 서명되지 않은 정수입니다.|
|`m_nHorzMargin`|색상 그리드의 색상 단추 사이의 가로 여백인 정수입니다.|
|`m_nHorzOffset`|색상 단추의 가운데에 대한 수평 오프셋인 정수입니다. 이 값은 단추에 색상 외에 텍스트 또는 이미지가 표시되는 경우 중요합니다.|
|`m_nNumColumns`|색상의 막대 컨트롤 그리드에 있는 열 수인 정수입니다.|
|`m_nNumColumnsVert`|세로 방향 색상 격자의 열 수인 정수입니다.|
|`m_nNumRowsHorz`|색상의 수평 방향 격자에 있는 열 수인 정수입니다.|
|`m_nRowHeight`|색상 격자에 있는 색상 단추 행의 높이인 정수입니다.|
|`m_nVertMargin`|색상 그리드의 색상 단추 사이의 세로 여백인 정수입니다.|
|`m_nVertOffset`|색상 단추의 가운데에 수직 간격띄우기인 정수입니다. 이 값은 단추에 색상 외에 텍스트 또는 이미지가 표시되는 경우 중요합니다.|
|`m_Palette`|색상 막대 컨트롤에 사용되는 색상의 [C팔레트입니다.](../../mfc/reference/cpalette-class.md)|
|`m_pParentBtn`|현재 단추의 부모인 [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) 개체에 대한 포인터입니다. 이 값은 색상 단추도구 모음 컨트롤의 계층 구조에 있거나 색상 속성 그리드 컨트롤에 있는 경우 중요합니다.|
|`m_pParentRibbonBtn`|리본에 있고 현재 단추의 상위 단추인 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) 개체에 대한 포인터입니다. 이 값은 색상 단추도구 모음 컨트롤의 계층 구조에 있거나 색상 속성 그리드 컨트롤에 있는 경우 중요합니다.|
|`m_pWndPropList`|[CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) 개체에 대한 포인터입니다.|
|`m_strAutoColor`|**자동** 단추에 표시되는 텍스트인 [CString입니다.](../../atl-mfc-shared/reference/cstringt-class.md) 자세한 내용은 [CMFCColorBar:::인에이블오토메이션 을](#enableautomaticbutton)참조하십시오.|
|`m_strDocColors`|문서 색상 단추에 표시되는 텍스트인 [CString입니다.](../../atl-mfc-shared/reference/cstringt-class.md) 자세한 내용은 [CMFCColorBar::SetDocumentColors](#setdocumentcolors)를 참조하십시오.|
|`m_strOtherColor`|*다른* 단추에 표시되는 텍스트인 [CString입니다.](../../atl-mfc-shared/reference/cstringt-class.md) 자세한 내용은 [CMFCColorBar::인에타 버튼](#enableotherbutton)을 참조하십시오.|

## <a name="remarks"></a>설명

일반적으로 개체를 `CMFCColorBar` 직접 만들지 않습니다. 대신 [CMFCColorMenuButton 클래스(메뉴](../../mfc/reference/cmfccolormenubutton-class.md) 및 도구 모음에 사용) 또는 [CMFCColorButton 클래스가](../../mfc/reference/cmfccolorbutton-class.md) 개체를 `CMFCColorBar` 만듭니다.

클래스는 `CMFCColorBar` 다음과 같은 기능을 제공합니다.

- 문서 색상 목록을 자동으로 조정합니다.

- 문서 상태와 함께 상태를 저장하고 복원합니다.

- "자동" 버튼을 관리합니다.

- [CMFCColorPickerCtrl 클래스](../../mfc/reference/cmfccolorpickerctrl-class.md) 컨트롤을 사용하여 사용자 지정 색상을 선택합니다.

- "찢어짐" 상태를 [지원합니다(CMFCColorMenuButton 클래스를](../../mfc/reference/cmfccolormenubutton-class.md)사용하여 만든 경우).

응용 프로그램에 `CMFCColorBar` 기능을 통합하려면 다음을 수행하십시오.

1. 일반 메뉴 단추를 만들고 ID(예: ID_CHAR_COLOR)를 할당합니다.

1. 프레임 창 클래스에서 [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) 메서드를 재정의하고 [CMFCColorMenuButton 클래스](../../mfc/reference/cmfccolormenubutton-class.md) 개체로 일반 메뉴 단추를 바꿉니다(CMFCToolBar::ReplaceButton)를 호출합니다. [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)

1. [CMFCColorMenuButton 클래스](../../mfc/reference/cmfccolormenubutton-class.md) 생성 중에 `CMFCColorBar` 모든 스타일을 설정하고 개체의 기능을 사용하거나 사용하지 않도록 설정합니다. 개체는 `CMFCColorMenuButton` 프레임워크가 `CMFCColorBar` 메서드를 호출한 `CreatePopupMenu` 후 개체를 동적으로 만듭니다.

사용자가 색상 막대 컨트롤 단추를 클릭하면 프레임워크는 매크로를 `ON_COMMAND` 사용하여 색상 막대 컨트롤의 부모에게 알립니다. 매크로에서 명령 ID 매개 변수는 1단계의 색상 막대 제어 단추에 할당한 값입니다(이 예에서는 ID_CHAR_COLOR). 자세한 내용은 [CMFCColorMenuButton 클래스,](../../mfc/reference/cmfccolormenubutton-class.md) [CMFCColorButton 클래스,](../../mfc/reference/cmfccolorbutton-class.md) [CMFCColorPickerCtrl 클래스,](../../mfc/reference/cmfccolorpickerctrl-class.md) [CFrameWndEx 클래스](../../mfc/reference/cframewndex-class.md)및 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md) 클래스를 참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 클래스에서 다양 한 메서드를 사용 `CMFCColorBar` 하 여 색상 막대를 구성 하는 방법을 보여 줍니다. 메서드는 가로 및 세로 여백을 설정하고, 다른 단추를 활성화하고, 색상 막대 컨트롤 창을 만들고, 현재 선택한 색상을 설정합니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#1](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#2](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFC베이스툴바](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

[CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxcolorbar.h

## <a name="cmfccolorbaradjustlocations"></a><a name="adjustlocations"></a>CMFC컬러바::조정위치

색상 막대 컨트롤의 색상 단추 위치를 조정합니다.

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>설명

이 메서드는 WM_SIZE 메시지 처리 하는 동안 프레임 워크에 의해 호출 됩니다.

## <a name="cmfccolorbarallowchangetextlabels"></a><a name="allowchangetextlabels"></a>CMFC컬러바::허용변경텍스트라벨

색상 단추의 텍스트 레이블이 변경될 수 있는지 여부를 나타냅니다.

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>Return Value

항상 FALSE입니다.

### <a name="remarks"></a>설명

기본적으로 이 메서드는 항상 FALSE를 반환하므로 텍스트 레이블을 수정할 수 없습니다. 텍스트 레이블을 수정할 수 있도록 하려면 이 메서드를 재정의합니다.

## <a name="cmfccolorbarallowshowonlist"></a><a name="allowshowonlist"></a>CMFC컬러바::허용쇼온리스트

사용자 지정 프로세스 중에 색상 막대 컨트롤 개체가 도구 모음 목록에 나타날 수 있는지 여부를 나타냅니다.

```
virtual BOOL AllowShowOnList() const;
```

### <a name="return-value"></a>Return Value

항상 TRUE입니다.

### <a name="remarks"></a>설명

기본적으로 이 메서드는 항상 TRUE를 반환하므로 프레임워크가 사용자 지정 프로세스 중에 색상 막대 컨트롤을 표시할 수 있습니다. 이 메서드를 재정의하여 다른 동작을 구현합니다.

## <a name="cmfccolorbarcalcsize"></a><a name="calcsize"></a>CMFC컬러바::석회화

레이아웃 계산 프로세스의 일부로 프레임워크에서 호출됩니다.

```
virtual CSize CalcSize(BOOL bVertDock);
```

### <a name="parameters"></a>매개 변수

*b버독*<br/>
【인】 TRUE는 색상 막대 컨트롤이 수직으로 도킹되도록 지정합니다. FALSE는 색상 막대 컨트롤이 수평으로 도킹되도록 지정합니다.

### <a name="return-value"></a>Return Value

색상 막대 컨트롤의 색상 단추 배열의 크기입니다.

## <a name="cmfccolorbarcmfccolorbar"></a><a name="cmfccolorbar"></a>CMFC컬러바::CMFC컬러바

`CMFCColorBar` 개체를 생성합니다.

```
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors,
    CList<COLORREF,COLORREF>& lstDocColors,
    int nColumns,
    int nRowsDockHorz,
    int nColDockVert,
    COLORREF colorAutomatic,
    UINT nCommandID,
    CMFCColorButton* pParentBtn);

CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors,
    CList<COLORREF,COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic,
    UINT nCommandID,
    CMFCRibbonColorButton* pParentRibbonBtn);

CMFCColorBar(
    CMFCColorBar& src,
    UINT uiCommandID);
```

### <a name="parameters"></a>매개 변수

*색상*<br/>
【인】 프레임워크가 색상 막대 컨트롤에 표시되는 색상 배열입니다.

*색*<br/>
【인】 처음에 선택한 색상입니다.

*lpszAutoColor*<br/>
【인】 자동(기본) *automatic* 색상 단추 또는 NULL의 텍스트 레이블입니다.

자동 단추의 표준 레이블은 **자동**입니다.

*lpszOtherColor*<br/>
【인】 더 많은 색상 선택 또는 NULL을 표시하는 *다른* 단추의 텍스트 레이블입니다.

다른 버튼의 표준 레이블은 **더 많은 색상입니다...**.

*lpszDocColors*<br/>
【인】 문서 색상 단추의 텍스트 레이블입니다. 문서 색상팔레트에는 문서가 현재 사용하는 모든 색상이 나열됩니다.

*lstDocColors*<br/>
【인】 문서에서 현재 사용하는 색상 목록입니다.

*nColumns*<br/>
【인】 색상 배열에 있는 열 수입니다.

*n로우스독호즈*<br/>
【인】 색상 막대가 가로로 도킹될 때 있는 행 수입니다.

*n콜독버트*<br/>
【인】 색상 막대가 세로로 도킹될 때 있는 열 수입니다.

*colorAutomatic*<br/>
【인】 자동 단추를 클릭할 때 프레임워크가 적용되는 기본 색상입니다.

*nCommandID*<br/>
【인】 색상 막대 컨트롤 명령 ID입니다.

*p부모Btn*<br/>
【인】 상위 단추에 대한 포인터입니다.

*src*<br/>
【인】 새 `CMFCColorBar` `CMFCColorBar` 개체에 복사할 기존 개체입니다.

*uiCommandID*<br/>
【인】 명령 ID입니다.

## <a name="cmfccolorbarcontexttosize"></a><a name="contexttosize"></a>CMFC컬러바::컨텍스트토크기

색상 막대 컨트롤의 단추를 포함하는 데 필요한 수직 및 수평 여백을 계산하고 해당 단추의 위치를 조정합니다.

```cpp
void ContextToSize(
    BOOL bSquareButtons = TRUE,
    BOOL bCenterButtons = TRUE);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*b스퀘어 버튼*|【인】 TRUE는 색상 막대 컨트롤의 단추 모양이 정사각형임을 지정합니다. 그렇지 않으면 false입니다. 기본값은 TRUE입니다.|
|*b가운데 버튼*|【인】 TRUE는 색상 막대 컨트롤 버튼의 면에 있는 내용이 가운데에 있도록 지정하는 데; 그렇지 않으면 false입니다. 기본값은 TRUE입니다.|

### <a name="remarks"></a>설명

## <a name="cmfccolorbarcreate"></a><a name="create"></a>CMFC컬러바::만들기

색상 막대 컨트롤 창을 만들고 개체에 `CMFCColorBar` 연결합니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle,
    UINT nID,
    CPalette* pPalette=NULL,
    int nColumns=0,
    int nRowsDockHorz=0,
    int nColDockVert=0);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
【인】 부모 창에 대한 포인터입니다.

*dwStyle*<br/>
【인】 [창 스타일의](../../mfc/reference/styles-used-by-mfc.md#window-styles)비트 조합(OR)입니다.

*nID*<br/>
【인】 명령 ID입니다.

*pPalette*<br/>
【인】 색상 팔레트에 대한 포인터입니다. 기본값은 NULL입니다.

*nColumns*<br/>
【인】 색상 막대 컨트롤의 열 수입니다. 기본값은 0입니다.

*n로우스독호즈*<br/>
【인】 가로로 도킹될 때 색상 막대 컨트롤의 행 수입니다. 기본값은 0입니다.

*n콜독버트*<br/>
【인】 색상으로 도킹될 때 색상 막대 컨트롤의 열 수입니다. 기본값은 0입니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

개체를 `CMFCColorBar` 생성하려면 클래스 생성자 다음에 이 메서드를 호출합니다. 이 `Create` 메서드는 Windows 컨트롤을 만들고 색상 목록을 초기화합니다.

## <a name="cmfccolorbarcreatecontrol"></a><a name="createcontrol"></a>CMFC컬러바::만들기제어

색상 막대 컨트롤 창을 만들고 `CMFCColorBar` 개체에 연결하고 지정된 색상 팔레트를 포함하도록 컨트롤 창의 크기를 조정합니다.

```
virtual BOOL CreateControl(
    CWnd* pParentWnd,
    const CRect& rect,
    UINT nID,
    int nColumns=-1,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
【인】 부모 창에 대한 포인터입니다. NULL이 될 수 없습니다.

*rect*<br/>
【인】 색상 막대 컨트롤을 그릴 위치를 지정하는 경계 사각형입니다.

*nID*<br/>
【인】 컨트롤 ID입니다.

*nColumns*<br/>
【인】 색상 막대 컨트롤의 이상적인 열 수입니다. 이 메서드는 지정된 색상 팔레트에 맞게 해당 숫자를 수정합니다. 기본값은 -1이며 이 매개 변수가 지정되지 않음을 의미합니다.

*pPalette*<br/>
【인】 색상 팔레트 또는 NULL에 대한 포인터입니다. 이 매개변수가 NULL인 경우 이 메서드는 20개의 색상이 지정된 것처럼 색상 막대 컨트롤의 크기를 계산합니다. 기본값은 NULL입니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 *정류,* *nColumns*및 *pPalette* 매개 변수를 사용하여 색상 막대 컨트롤에서 적절한 숫자 또는 행과 열을 계산한 다음 [CMFCColorBar::Create](#create) 메서드를 호출합니다.

## <a name="cmfccolorbarcreatepalette"></a><a name="createpalette"></a>CMFC컬러바::팔레트 만들기

지정된 색상 배열의 색상으로 팔레트를 초기화합니다.

```
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,
    CPalette& palette);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*arColors*|【인】 색상의 배열입니다.|
|*색상표(palette)*|【인】 색상 팔레트입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="cmfccolorbarenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFC컬러바::인에이블오토버튼

자동 단추를 표시하거나 숨깁니다.

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 자동(기본) *automatic* 색상 단추 또는 NULL의 텍스트 레이블입니다.

자동 단추의 표준 레이블은 **자동**입니다.

*colorAutomatic*<br/>
【인】 자동 단추를 클릭할 때 프레임워크가 적용되는 기본 색상입니다.

*bEnable*<br/>
【인】 TRUE는 자동 버튼을 활성화; FALSE를 클릭하여 자동 버튼을 비활성화합니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

*lpszLabel* 매개 변수가 NULL이거나 *bEnable* 매개 변수가 FALSE인 경우 자동 단추의 텍스트 레이블이 삭제됩니다.

## <a name="cmfccolorbarenableotherbutton"></a><a name="enableotherbutton"></a>CMFC컬러바::인에이블기타버튼

사용자가 더 많은 색상을 선택할 수 있는 대화 상자의 표시를 활성화하거나 사용하지 않도록 설정합니다.

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 더 많은 색상 선택 또는 NULL을 표시하는 *다른* 단추의 텍스트 레이블입니다.

이 버튼의 표준 레이블은 **더 많은 색상입니다...**.

*bAltColorDlg*<br/>
【인】 [TRUECMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 대화 상자를 표시합니다. FALSE를 사용하여 표준 [CColorDialog](../../mfc/reference/ccolordialog-class.md) 대화 상자를 표시합니다. 기본값은 TRUE입니다.

*bEnable*<br/>
【인】 TRUE 버튼을 활성화합니다. FALSE를 클릭하여 단추를 비활성화합니다. 기본값은 TRUE입니다.

## <a name="cmfccolorbargetcolor"></a><a name="getcolor"></a>CMFC컬러바: 겟컬러

현재 선택한 색상을 검색합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Return Value

현재 선택한 색상입니다.

## <a name="cmfccolorbargetcolorgridsize"></a><a name="getcolorgridsize"></a>CMFC컬러바::겟컬러그리드사이즈

색상 막대 컨트롤의 그리드에서 행과 열 수를 계산합니다.

```
CSize GetColorGridSize(BOOL bVertDock) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*b버독*|【인】 수직으로 도킹된 컬러 바 컨트롤에 대한 계산을 수행하는 TRUE; 그렇지 않으면 수평 도킹 된 컨트롤에 대 한 계산을 수행 합니다.|

### <a name="return-value"></a>Return Value

구성 요소에 열 수가 포함되고 `cy` 구성 요소에 행 수가 포함된 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다. `cx`

## <a name="cmfccolorbargetcommandid"></a><a name="getcommandid"></a>CMFC컬러바::겟커맨드ID

현재 색상 막대 컨트롤의 명령 ID를 검색합니다.

```
UINT GetCommandID() const;
```

### <a name="return-value"></a>Return Value

명령 ID입니다.

### <a name="remarks"></a>설명

사용자가 새 색상을 선택하면 프레임워크는 명령 ID를 WM_COMMAND 메시지로 전송하여 `CMFCColorBar` 개체의 부모에게 알립니다.

## <a name="cmfccolorbargetextraheight"></a><a name="getextraheight"></a>CMFC컬러바: 겟엑스트라하이트

현재 색상 막대에서 **기타** 단추 또는 문서 색상과 같은 기타 사용자 인터페이스 요소를 표시하는 데 필요한 추가 높이를 계산합니다.

```
int GetExtraHeight(int nNumColumns) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*nNumColumns*|【인】 색상 막대 컨트롤에 문서 색상이 포함된 경우 문서 색상 표에 표시할 열 수가 포함됩니다. 그렇지 않으면 이 값이 사용되지 않습니다.|

### <a name="return-value"></a>Return Value

필요한 계산된 추가 높이입니다.

## <a name="cmfccolorbargethighlightedcolor"></a><a name="gethighlightedcolor"></a>CMFC컬러바::겟하이라이트컬러

색상 단추에 포커스가 있음을 나타내는 색상을 검색합니다. 즉, 버튼이 *뜨겁습니다.*

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Return Value

RGB 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorbargethorzmargin"></a><a name="gethorzmargin"></a>CMFC컬러바::게호즈마진

왼쪽 또는 오른쪽 색상 셀과 클라이언트 영역 경계 사이의 공간인 수평 여백을 검색합니다.

```
int GetHorzMargin();
```

### <a name="return-value"></a>Return Value

수평 여백입니다.

## <a name="cmfccolorbargetvertmargin"></a><a name="getvertmargin"></a>CMFC컬러바::게버트마진

위쪽 또는 아래쪽 색상 셀과 클라이언트 영역 경계 사이의 공간인 수직 여백을 검색합니다.

```
int GetVertMargin() const;
```

### <a name="return-value"></a>Return Value

수직 여백입니다.

## <a name="cmfccolorbarinitcolors"></a><a name="initcolors"></a>CMFC컬러바::이니트 컬러

지정된 팔레트 또는 시스템 기본 팔레트의 색상으로 색상 배열을 초기화합니다.

```
static int InitColors(
    CPalette* pPalette,
    CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pPalette*|【인】 팔레트 개체 또는 NULL에 대한 포인터입니다. 이 매개 변수가 NULL인 경우 이 메서드는 운영 체제의 기본 팔레트를 사용합니다.|
|*arColors*|【인】 색상의 배열입니다.|

### <a name="return-value"></a>Return Value

색상 배열의 요소 수입니다.

## <a name="cmfccolorbaristearoff"></a><a name="istearoff"></a>CMFC컬러바::이티어오프

현재 색상 막대가 도킹 가능한지 여부를 나타냅니다.

```
BOOL IsTearOff() const;
```

### <a name="return-value"></a>Return Value

TRUE 현재 색상 막대 컨트롤이 도킹 가능한 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

색상 막대 컨트롤을 도킹할 수 있는 경우 컨트롤 막대를 분리하고 다른 위치에 도킹할 수 있습니다.

## <a name="cmfccolorbaronkey"></a><a name="onkey"></a>CMFC컬러바::온키

사용자가 키보드 단추를 누를 때 프레임워크에서 호출됩니다.

```
virtual BOOL OnKey(UINT nChar);
```

### <a name="parameters"></a>매개 변수

*Nchar*<br/>
【인】 사용자가 누른 키에 대한 가상 키 코드입니다.

### <a name="return-value"></a>Return Value

이 메서드가 지정된 키를 처리하는 경우 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="cmfccolorbaronsendcommand"></a><a name="onsendcommand"></a>CMFC컬러바::온센드커맨드

팝업 컨트롤의 계층 구조를 닫기 위해 프레임 워크에서 호출 합니다.

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*p 버튼*|【인】 도구 모음에 있는 컨트롤에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="cmfccolorbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CMFC컬러바::온업데이트CmdUI

항목이 표시되기 전에 색상 막대 컨트롤의 사용자 인터페이스 항목을 사용하거나 사용하지 않도록 설정하려면 프레임워크에서 호출합니다.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>매개 변수

*p Target*<br/>
【인】 업데이트할 사용자 인터페이스 항목이 포함된 창에 대한 포인터입니다.

*bDisableIfNohndler*<br/>
【인】 TRUE 는 메시지 맵에 처리기가 정의되지 않은 경우 사용자 인터페이스 항목을 사용하지 않도록 설정합니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

응용 프로그램의 사용자가 사용자 인터페이스 항목을 클릭하면 항목이 사용 설정 또는 사용 중지됨으로 표시될지 여부를 알아야 합니다. 명령 메시지의 대상은 ON_UPDATE_COMMAND_UI 명령 처리기를 구현하여 이 정보를 제공합니다. 이 메서드를 사용하여 명령을 처리합니다. 자세한 내용은 [CCmdUI 클래스를](../../mfc/reference/ccmdui-class.md)참조하십시오.

## <a name="cmfccolorbaropencolordialog"></a><a name="opencolordialog"></a>CMFC컬러바::오픈컬러디아로그

색상 대화 상자를 엽니다.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>매개 변수

*색상기본값*<br/>
【인】 색상 대화 상자가 열릴 때 기본적으로 선택되는 색상입니다.

*컬러 레스*<br/>
【아웃】 사용자가 선택한 색상입니다.

### <a name="return-value"></a>Return Value

TRUE 사용자가 색상을 선택한 경우; 사용자가 색상 대화 상자를 취소한 경우 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorbarrebuild"></a><a name="rebuild"></a>CMFC컬러바::리빌드

색상 막대 컨트롤을 완전히 다시 그립니다.

```
virtual void Rebuild();
```

## <a name="cmfccolorbarselectpalette"></a><a name="selectpalette"></a>CMFC컬러바:셀렉트 팔레트

지정된 장치 컨텍스트의 논리적 팔레트를 현재 색상 막대 컨트롤의 상위 단추 팔레트로 설정합니다.

```
CPalette* SelectPalette(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pDC*|【인】 현재 색상 막대 컨트롤의 부모 단추의 장치 컨텍스트에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

현재 색상 막대 컨트롤의 부모 단추 팔레트로 대체되는 팔레트에 대한 포인터입니다.

## <a name="cmfccolorbarsetcolor"></a><a name="setcolor"></a>CMFC컬러바::세트컬러

현재 선택된 색상을 설정합니다.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
【인】 RGB 색상 값입니다.

## <a name="cmfccolorbarsetcolorname"></a><a name="setcolorname"></a>CMFC컬러바::세트컬러네임

지정된 색상에 대한 새 이름을 설정합니다.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
【인】 색상의 RGB 값입니다.

*strName*<br/>
【인】 지정된 색상의 새 이름입니다.

### <a name="remarks"></a>설명

이 메서드는 응용 프로그램의 모든 `CMFCColorBar` 개체에서 지정된 색상의 이름을 변경합니다.

## <a name="cmfccolorbarsetcommandid"></a><a name="setcommandid"></a>CMFC컬러바::세트커맨드ID

색상 막대 컨트롤에 대한 새 명령 ID를 설정합니다.

```cpp
void SetCommandID(UINT nCommandID);
```

### <a name="parameters"></a>매개 변수

*nCommandID*<br/>
【인】 명령 ID입니다.

### <a name="remarks"></a>설명

색상 막대 컨트롤의 명령 ID를 수정하고 ID가 변경되었음을 컨트롤의 상위 창에 알리기 위해 이 메서드를 호출합니다.

## <a name="cmfccolorbarsetdocumentcolors"></a><a name="setdocumentcolors"></a>CMFC컬러바::세트문서색상

현재 문서에 사용되는 색상 목록을 설정합니다.

```cpp
void SetDocumentColors(
    LPCTSTR lpszCaption,
    CList<COLORREF,COLORREF>& lstDocColors,
    BOOL bShowWhenDocked=FALSE);
```

### <a name="parameters"></a>매개 변수

*lpszCaption*<br/>
【인】 색상 막대 컨트롤이 도킹되지 않을 때 표시되는 캡션입니다.

*lstDocColors*<br/>
【인】 현재 문서 색상을 대체하는 색상 목록입니다.

*bShow때도킹*<br/>
【인】 TRUE는 색상 막대 컨트롤이 도킹될 때 문서 색상을 표시합니다. 그렇지 않으면 false입니다. 기본값은 FALSE입니다.

### <a name="remarks"></a>설명

*문서 색상은* 현재 문서에서 사용되는 색상입니다. 프레임워크는 문서 색상 목록을 자동으로 유지 관리하지만 이 메서드를 사용하여 목록을 수정할 수 있습니다.

## <a name="cmfccolorbarsethorzmargin"></a><a name="sethorzmargin"></a>CMFC컬러바::세트호즈마진

왼쪽 또는 오른쪽 색상 셀과 클라이언트 영역의 경계 사이의 공간인 수평 여백을 설정합니다.

```cpp
void SetHorzMargin(int nHorzMargin);
```

### <a name="parameters"></a>매개 변수

*n호르즈마진*<br/>
【인】 가로 여백(픽셀 단위)입니다.

### <a name="remarks"></a>설명

기본적으로 [CMFCColorBar::CMFCColorBar](#cmfccolorbar) 생성자는 수평 여백을 4픽셀로 설정합니다.

## <a name="cmfccolorbarsetproplist"></a><a name="setproplist"></a>CMFC컬러바::세트프로프리스트

보호된 `m_pWndPropList` 데이터 멤버를 지정된 포인터로 속성 그리드 컨트롤로 설정합니다.

```cpp
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pWndList*|【인】 속성 그리드 제어 개체에 대한 포인터입니다.|

## <a name="cmfccolorbarsetvertmargin"></a><a name="setvertmargin"></a>CMFC컬러바::세트버트마진

상하 색상 셀과 클라이언트 영역 경계 사이의 공간인 수직 여백을 설정합니다.

```cpp
void SetVertMargin(int nVertMargin);
```

### <a name="parameters"></a>매개 변수

*n버트마진*<br/>
【인】 세로 여백(픽셀 단위)입니다.

### <a name="remarks"></a>설명

기본적으로 [CMFCColorBar::CMFCColorBar](#cmfccolorbar) 생성자는 세로 여백을 4픽셀로 설정합니다.

## <a name="cmfccolorbarshowcommandmessagestring"></a><a name="showcommandmessagestring"></a>CMFC컬러바::쇼커맨드메시지스트링

상태 표시줄에서 메시지 줄을 업데이트하려면 색상 표시줄 컨트롤을 소유하는 프레임 창을 요청합니다.

```
virtual void ShowCommandMessageString(UINT uiCmdId);
```

### <a name="parameters"></a>매개 변수

*uiCmdId*<br/>
【인】 명령 ID입니다. (이 매개 변수는 무시됩니다.)

### <a name="remarks"></a>설명

이 메서드는 WM_SETMESSAGESTRING 메시지를 색상 막대 컨트롤의 소유자에게 보냅니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
