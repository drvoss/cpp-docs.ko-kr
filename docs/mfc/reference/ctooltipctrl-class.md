---
title: CToolTipCtrl Class
ms.date: 11/04/2016
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
ms.openlocfilehash: 53a5a5b6871680f9758d140174dcceae6c53f568
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752192"
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class

애플리케이션 도구의 용도를 설명하는 텍스트 한 줄을 표시하는 작은 팝업 창인 "도구 설명 컨트롤"의 기능을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CToolTipCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CToolTipCtrl:::CToolTipCtrl](#ctooltipctrl)|`CToolTipCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CToolTipCtrl::활성화](#activate)|공구 팁 컨트롤을 활성화하고 비활성화합니다.|
|[CTool팁Ctrl::추가 도구](#addtool)|도구 팁 컨트롤에 도구를 등록합니다.|
|[CToolTipCtrl::adjustRect](#adjustrect)|도구 설명 컨트롤의 텍스트 표시 사각형과 창 사각형 간에 변환합니다.|
|[CTool팁Ctrl::만들기](#create)|도구 팁 컨트롤을 만들고 오브젝트에 `CToolTipCtrl` 연결합니다.|
|[CToolTipCtrl::만들기](#createex)|지정된 Windows 확장 스타일을 사용하여 도구 설명 컨트롤을 `CToolTipCtrl` 만들고 개체에 연결합니다.|
|[CToolTipCtrl: :D엘툴](#deltool)|도구 팁 컨트롤에서 도구를 제거합니다.|
|[CToolTipCtrl::GetBubblesize](#getbubblesize)|도구 설명의 크기를 검색합니다.|
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|현재 도구 설명 컨트롤이 표시하는 도구 설명 창의 크기, 위치 및 텍스트와 같은 정보를 검색합니다.|
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|도구 설명 컨트롤에 대해 현재 설정된 초기, 팝업 및 다시 표시 기간을 검색합니다.|
|[CToolTipCtrl::GetMargin](#getmargin)|도구 설명 창에 대해 설정된 위쪽, 왼쪽, 아래쪽 및 오른쪽 여백을 검색합니다.|
|[CToolTipCtrl:::겟맥스팁폭](#getmaxtipwidth)|공구 팁 창의 최대 너비를 검색합니다.|
|[CToolTipCtrl::GetText](#gettext)|도구 설명 컨트롤이 도구에 대해 유지 관리하는 텍스트를 검색합니다.|
|[CToolTipCtrl:::겟팁BkColor](#gettipbkcolor)|도구 설명 창에서 배경색을 검색합니다.|
|[CToolTipCtrl:::GetTipTextColor](#gettiptextcolor)|도구 설명 창에서 텍스트 색상을 검색합니다.|
|[CToolTipCtrl::GetTitle](#gettitle)|현재 도구 설명 컨트롤의 제목을 검색합니다.|
|[CToolTipCtrl::gettoolCount](#gettoolcount)|도구 팁 컨트롤에서 유지 관리하는 도구 수를 검색합니다.|
|[CToolTipCtrl::getToolInfo](#gettoolinfo)|도구 설명 컨트롤이 도구에 대해 유지 관리하는 정보를 검색합니다.|
|[CToolTipCtrl::히트 테스트](#hittest)|지정된 도구의 경계 사각형 내에 있는지 여부를 확인하기 위해 점을 테스트합니다. 그렇다면 도구에 대한 정보를 검색합니다.|
|[CToolTipCtrl::P](#pop)|표시된 도구 팁 창을 보기에서 제거합니다.|
|[CToolTipCtrl::P](#popup)|현재 ToolTip 컨트롤이 마지막 마우스 메시지의 좌표에 표시됩니다.|
|[CToolTipCtrl::릴레이 이벤트](#relayevent)|처리를 위해 마우스 메시지를 도구 설명 컨트롤에 전달합니다.|
|[CToolTipCtrl::세트지연 시간](#setdelaytime)|도구 설명 컨트롤의 초기, 팝업 및 다시 표시 기간을 설정합니다.|
|[CToolTipCtrl::세트마진](#setmargin)|공구 팁 창의 상단, 왼쪽, 아래쪽 및 오른쪽 여백을 설정합니다.|
|[CToolTipCtrl::설정맥스팁폭](#setmaxtipwidth)|공구 팁 창의 최대 너비를 설정합니다.|
|[CToolTipCtrl::setTipBkColor](#settipbkcolor)|도구 설명 창에서 배경색을 설정합니다.|
|[CToolTipCtrl::settipTextColor](#settiptextcolor)|도구 설명 창에서 텍스트 색상을 설정합니다.|
|[CToolTipCtrl::세트타이틀](#settitle)|도구 설명에 표준 아이콘과 제목 문자열을 추가합니다.|
|[CToolTipCtrl::setToolInfo](#settoolinfo)|도구 설명이 도구에 대해 유지 관리하는 정보를 설정합니다.|
|[CToolTipCtrl::setToolRect](#settoolrect)|도구에 대한 새 경계 사각형을 설정합니다.|
|[CToolTipCtrl::세트윈도우테임](#setwindowtheme)|도구 팁 창의 시각적 스타일을 설정합니다.|
|[CToolTipCtrl::업데이트](#update)|현재 도구를 다시 그려야 합니다.|
|[CToolTipCtrl::업데이트 팁텍스트](#updatetiptext)|도구의 도구 팁 텍스트를 설정합니다.|

## <a name="remarks"></a>설명

"도구"는 자식 창 또는 컨트롤과 같은 창 또는 창의 클라이언트 영역 내의 응용 프로그램 정의 직사각형 영역입니다. 도구 설명은 대부분의 경우 숨겨져 있으며 사용자가 도구에 커서를 놓고 약 반 초 동안 사용할 때만 표시됩니다. 도구 설명은 커서 근처에 나타나며 사용자가 마우스 단추를 클릭하거나 커서를 도구에서 떼어내면 사라집니다.

`CToolTipCtrl`는 도구 설명의 초기 시간 및 지속 시간, 도구 설명 텍스트 주변의 여백 너비, 도구 설명 창 자체의 너비 및 도구 설명의 배경 및 텍스트 색상을 제어하는 기능을 제공합니다. 단일 공구 팁 컨트롤은 하나 이상의 도구에 대한 정보를 제공할 수 있습니다.

클래스는 `CToolTipCtrl` Windows 공통 도구 설명 컨트롤의 기능을 제공합니다. 이 컨트롤(및 `CToolTipCtrl` 따라서 클래스)은 Windows 95/98 및 Windows NT 버전 3.51 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.

도구 설명 사용에 대한 자세한 내용은 [CFrameWnd에서 파생되지 않은 Windows의 도구 팁을](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)참조하십시오.

사용에 `CToolTipCtrl`대한 자세한 내용은 [컨트롤](../../mfc/controls-mfc.md) 및 [CToolTipCtrl 사용](../../mfc/using-ctooltipctrl.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CToolTipCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="ctooltipctrlactivate"></a><a name="activate"></a>CToolTipCtrl::활성화

이 함수를 호출하여 공구 팁 컨트롤을 활성화하거나 비활성화합니다.

```cpp
void Activate(BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*bActivate*<br/>
도구 팁 컨트롤을 활성화 또는 비활성화할지 여부를 지정합니다.

### <a name="remarks"></a>설명

*bActivate가* TRUE이면 컨트롤이 활성화됩니다. FALSE면 비활성화됩니다.

도구 팁 컨트롤이 활성화되면 커서가 컨트롤에 등록된 도구에 있을 때 도구 팁 정보가 나타납니다. 비활성 상태일 때는 커서가 도구에 있는 경우에도 도구 설명 정보가 나타나지 않습니다.

### <a name="example"></a>예제

  [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)에 대한 예제를 참조하십시오.

## <a name="ctooltipctrladdtool"></a><a name="addtool"></a>CTool팁Ctrl::추가 도구

도구 팁 컨트롤에 도구를 등록합니다.

```
BOOL AddTool(
    CWnd* pWnd,
    UINT nIDText,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);

BOOL AddTool(
    CWnd* pWnd,
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
도구가 포함된 창에 대한 포인터입니다.

*니디텍스트*<br/>
도구의 텍스트가 포함된 문자열 리소스의 ID입니다.

*lpRectTool*<br/>
도구의 경계 사각형좌표를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 포인터입니다. 좌표는 *pWnd로*식별된 창의 클라이언트 영역의 왼쪽 위 모서리를 기준으로 합니다.

*니드툴*<br/>
도구의 ID입니다.

*lpszText*<br/>
도구의 텍스트에 대한 포인터입니다. 이 매개 변수에 LPSTR_TEXTCALLBACK 값이 포함된 경우 TTN_NEEDTEXT 알림 메시지는 *pWnd가* 가리키는 창의 상위로 이동합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

*lpRectTool* 및 *nIDTool* 매개 변수는 모두 유효해야 하며 *lpRectTool이* NULL인 경우 *nIDTool은* 0이어야 합니다.

공구 팁 컨트롤은 두 개 이상의 도구와 연결할 수 있습니다. 이 함수를 호출하여 도구 설명 컨트롤에 도구를 등록하여 커서가 도구에 있을 때 도구 설명에 저장된 정보가 표시됩니다.

> [!NOTE]
> 을 사용하여 `AddTool`도구 팁을 정적 컨트롤로 설정할 수 없습니다.

### <a name="example"></a>예제

  [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)에 대한 예제를 참조하십시오.

## <a name="ctooltipctrladjustrect"></a><a name="adjustrect"></a>CToolTipCtrl::adjustRect

도구 설명 컨트롤의 텍스트 표시 사각형과 창 사각형 간에 변환합니다.

```
BOOL AdjustRect(
    LPRECT lprc,
    BOOL bLarger = TRUE);
```

### <a name="parameters"></a>매개 변수

*lprc*<br/>
도구 팁 창 사각형 또는 텍스트 표시 사각형을 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 포인터입니다.

*bLarger*<br/>
TRUE인 경우 *lprc는* 텍스트 표시 사각형을 지정하는 데 사용되며 해당 창 사각형을 수신합니다. FALSE인 경우 *lprc는* 창 사각형을 지정하는 데 사용되며 해당 텍스트 표시 사각형을 수신합니다.

### <a name="return-value"></a>Return Value

사각형이 성공적으로 조정된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수는 창 사각형에서 도구 팁 컨트롤의 텍스트 표시 사각형 또는 지정된 텍스트 표시 사각형을 표시하는 데 필요한 도구 팁 창 사각형을 계산합니다.

이 멤버 함수는 Windows SDK에 설명된 대로 [TTM_ADJUSTRECT](/windows/win32/Controls/ttm-adjustrect)Win32 메시지의 동작을 구현합니다.

## <a name="ctooltipctrlcreate"></a><a name="create"></a>CTool팁Ctrl::만들기

도구 팁 컨트롤을 만들고 오브젝트에 `CToolTipCtrl` 연결합니다.

```
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
도구 설명 컨트롤의 상위 창(일반적으로)을 `CDialog`지정합니다. NULL이 아니어야 합니다.

*dwStyle*<br/>
공구 팁 컨트롤의 스타일을 지정합니다. 자세한 내용은 **비고** 섹션을 참조하십시오.

### <a name="return-value"></a>Return Value

개체가 성공적으로 `CToolTipCtrl` 생성되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

두 단계로 `CToolTipCtrl` 구성합니다. 먼저 생성자를 호출하여 개체를 `CToolTipCtrl` 생성한 `Create` 다음 호출하여 도구 팁 컨트롤을 `CToolTipCtrl` 만들고 개체에 연결합니다.

*dwStyle* 매개 변수는 [창 스타일의](../../mfc/reference/styles-used-by-mfc.md#window-styles)모든 조합일 수 있습니다. 또한 공구 팁 컨트롤에는 TTS_ALWAYSTIP 및 TTS_NOPREFIX 두 가지 클래스별 스타일이 있습니다.

|스타일|의미|
|-----------|-------------|
|TTS_ALWAYSTIP|도구 설명 컨트롤의 소유자 창이 활성 상태인지 비활성 상태인지여부에 관계없이 커서가 도구에 있을 때 도구 설명이 표시되도록 지정합니다. 이 스타일이 없으면 도구의 소유자 창이 활성 상태일 때 도구 팁 컨트롤이 표시되지만 비활성 상태일 때는 나타나지 않습니다.|
|TTS_NOPREFIX|이 스타일은 시스템이 앰퍼샌드(&) 문자를 문자열에서 제거하지 못하게 합니다. 도구 설명 컨트롤에 TTS_NOPREFIX 스타일이 없는 경우 시스템은 앰퍼샌드 문자를 자동으로 제거하여 응용 프로그램이 메뉴 항목과 동일한 문자열을 도구 팁 컨트롤의 텍스트로 사용할 수 있도록 합니다.|

도구 팁 컨트롤에는 컨트롤을 만들 때 지정여부에 관계없이 WS_POPUP 및 WS_EX_TOOLWINDOW 창 스타일이 있습니다.

확장된 창 스타일을 사용하여 도구 설명 컨트롤을 만들려면 `Create` [대신 CToolTipCtrl::CreateEx를](#createex) 호출합니다.

### <a name="example"></a>예제

  [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)에 대한 예제를 참조하십시오.

## <a name="ctooltipctrlcreateex"></a><a name="createex"></a>CToolTipCtrl::만들기

컨트롤(하위 창)을 만들고 개체와 `CToolTipCtrl` 연결합니다.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwStyle = 0,
    DWORD dwStyleEx = 0);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
컨트롤의 부모인 창에 대한 포인터입니다.

*dwStyle*<br/>
공구 팁 컨트롤의 스타일을 지정합니다. 자세한 내용은 [만들기의](#create) **비고** 섹션을 참조하십시오.

*dwStyleEx*<br/>
생성되는 컨트롤의 확장 스타일을 지정합니다. 확장 된 Windows 스타일 목록은 Windows SDK에서 [CreateWindowEx에](/windows/win32/api/winuser/nf-winuser-createwindowexw) 대한 *dwExStyle* 매개 변수를 참조하십시오.

### <a name="return-value"></a>Return Value

그렇지 않으면 성공하면 0이 아닙니다.

### <a name="remarks"></a>설명

Windows `CreateEx` 확장 `Create` 스타일 **서문 WS_EX_** 지정된 확장 된 Windows 스타일을 적용하는 대신 사용합니다.

## <a name="ctooltipctrlctooltipctrl"></a><a name="ctooltipctrl"></a>CToolTipCtrl:::CToolTipCtrl

`CToolTipCtrl` 개체를 생성합니다.

```
CToolTipCtrl();
```

### <a name="remarks"></a>설명

개체를 `Create` 생성한 후 호출해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]

## <a name="ctooltipctrldeltool"></a><a name="deltool"></a>CToolTipCtrl: :D엘툴

도구 팁 컨트롤에서 지원하는 도구 컬렉션에서 *pWnd* 및 *nIDTool에서* 지정한 도구를 제거합니다.

```cpp
void DelTool(
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
도구가 포함된 창에 대한 포인터입니다.

*니드툴*<br/>
도구의 ID입니다.

## <a name="ctooltipctrlgetbubblesize"></a><a name="getbubblesize"></a>CToolTipCtrl::GetBubblesize

도구 설명의 크기를 검색합니다.

```
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>매개 변수

*lpToolInfo*<br/>
도구 팁의 [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

공구 팁의 크기입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [TTM_GETBUBBLESIZE](/windows/win32/Controls/ttm-getbubblesize)Win32 메시지의 동작을 구현합니다.

## <a name="ctooltipctrlgetcurrenttool"></a><a name="getcurrenttool"></a>CToolTipCtrl::GetCurrentTool

현재 도구 설명 컨트롤에서 표시되는 도구 설명 창의 크기, 위치 및 텍스트와 같은 정보를 검색합니다.

```
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*lpToolInfo*|【아웃】 현재 도구 설명 창에 대한 정보를 받는 [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) 구조에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

TRUE 정보가 성공적으로 검색되는 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [TTM_GETCURRENTTOOL](/windows/win32/Controls/ttm-getcurrenttool) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제는 현재 도구 설명 창에 대한 정보를 검색합니다.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]

## <a name="ctooltipctrlgetdelaytime"></a><a name="getdelaytime"></a>CToolTipCtrl::GetDelayTime

도구 설명 컨트롤에 대해 현재 설정된 초기, 팝업 및 다시 표시 기간을 검색합니다.

```
int GetDelayTime(DWORD dwDuration) const;
```

### <a name="parameters"></a>매개 변수

*dwDuration*<br/>
검색할 기간 값을 지정하는 플래그입니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다.

- TTDT_AUTOPOP 포인터가 도구의 경계 사각형 내에 고정되어 있는 경우 도구 팁 창이 표시되는 시간을 검색합니다.

- TTDT_INITIAL 도구 팁 창이 나타나기 전에 포인터가 도구의 경계 사각형 내에 고정된 상태로 유지되어야 하는 시간을 검색합니다.

- TTDT_RESHOW 포인터가 한 도구에서 다른 도구로 이동할 때 후속 도구 설명 창이 표시되는 데 걸리는 시간을 검색합니다.

### <a name="return-value"></a>Return Value

지정된 지연 시간(밀리초)

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 TTM_GETDELAYTIME Win32 [메시지의](/windows/win32/Controls/ttm-getdelaytime)동작을 구현합니다.

## <a name="ctooltipctrlgetmargin"></a><a name="getmargin"></a>CToolTipCtrl::GetMargin

도구 설명 창에 대해 설정된 위쪽, 왼쪽, 아래쪽 및 오른쪽 여백을 검색합니다.

```cpp
void GetMargin(LPRECT lprc) const;
```

### <a name="parameters"></a>매개 변수

*lprc*<br/>
여백 `RECT` 정보를 수신하는 구조의 주소입니다. [RECT](/windows/win32/api/windef/ns-windef-rect) 구조의 멤버는 경계 사각형을 정의하지 않습니다. 이 메시지의 목적에 따라 구조 멤버는 다음과 같이 해석됩니다.

|멤버|표시|
|------------|--------------------|
|`top`|도구 팁 텍스트의 위쪽 테두리와 위쪽 사이의 거리(픽셀)입니다.|
|`left`|팁 텍스트의 왼쪽 테두리와 왼쪽 끝 사이의 거리(픽셀)입니다.|
|`bottom`|팁 텍스트의 아래쪽 테두리와 아래쪽 사이의 거리(픽셀)입니다.|
|`right`|오른쪽 테두리와 팁 텍스트의 오른쪽 끝 사이의 거리(픽셀 단위)입니다.|

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [TTM_GETMARGIN](/windows/win32/Controls/ttm-getmargin)Win32 메시지의 동작을 구현합니다.

## <a name="ctooltipctrlgetmaxtipwidth"></a><a name="getmaxtipwidth"></a>CToolTipCtrl:::겟맥스팁폭

공구 팁 창의 최대 너비를 검색합니다.

```
int GetMaxTipWidth() const;
```

### <a name="return-value"></a>Return Value

공구 팁 창의 최대 너비입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [TTM_GETMAXTIPWIDTH](/windows/win32/Controls/ttm-getmaxtipwidth)Win32 메시지의 동작을 구현합니다.

## <a name="ctooltipctrlgettext"></a><a name="gettext"></a>CToolTipCtrl::GetText

도구 설명 컨트롤이 도구에 대해 유지 관리하는 텍스트를 검색합니다.

```cpp
void GetText(
    CString& str,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
도구의 `CString` 텍스트를 받는 개체를 참조합니다.

*pWnd*<br/>
도구가 포함된 창에 대한 포인터입니다.

*니드툴*<br/>
도구의 ID입니다.

### <a name="remarks"></a>설명

*pWnd* 및 *nIDTool* 매개 변수는 도구를 식별합니다. 해당 도구가 이전 호출을 통해 도구 설명 컨트롤에 `CToolTipCtrl::AddTool`등록된 경우 *str* 매개 변수에서 참조하는 개체에 도구의 텍스트가 할당됩니다.

## <a name="ctooltipctrlgettipbkcolor"></a><a name="gettipbkcolor"></a>CToolTipCtrl:::겟팁BkColor

도구 설명 창에서 배경색을 검색합니다.

```
COLORREF GetTipBkColor() const;
```

### <a name="return-value"></a>Return Value

배경색을 나타내는 [COLORREF](/windows/win32/gdi/colorref) 값입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 TTM_GETTIPBKCOLOR Win32 [메시지의](/windows/win32/Controls/ttm-gettipbkcolor)동작을 구현합니다.

## <a name="ctooltipctrlgettiptextcolor"></a><a name="gettiptextcolor"></a>CToolTipCtrl:::GetTipTextColor

도구 설명 창에서 텍스트 색상을 검색합니다.

```
COLORREF GetTipTextColor() const;
```

### <a name="return-value"></a>Return Value

텍스트 색상을 나타내는 [COLORREF](/windows/win32/gdi/colorref) 값입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 TTM_GETTIPTEXTCOLOR Win32 [메시지의](/windows/win32/Controls/ttm-gettiptextcolor)동작을 구현합니다.

## <a name="ctooltipctrlgettitle"></a><a name="gettitle"></a>CToolTipCtrl::GetTitle

현재 도구 설명 컨트롤의 제목을 검색합니다.

```cpp
void GetTitle(PTTGETTITLE pttgt) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pttgt*|【아웃】 ToolTip 컨트롤에 대한 정보가 포함된 [TTGETTITLE](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) 구조에 대한 포인터입니다. 이 메서드가 반환 하면 [TTGETTITLE](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) 구조의 *pszTitle* 멤버는 제목의 텍스트를 가리킵니다.|

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [TTM_GETTITLE](/windows/win32/Controls/ttm-gettitle) 메시지를 보냅니다.

## <a name="ctooltipctrlgettoolcount"></a><a name="gettoolcount"></a>CToolTipCtrl::gettoolCount

도구 팁 컨트롤에 등록된 도구 수를 검색합니다.

```
int GetToolCount() const;
```

### <a name="return-value"></a>Return Value

도구 팁 컨트롤에 등록된 도구 수입니다.

## <a name="ctooltipctrlgettoolinfo"></a><a name="gettoolinfo"></a>CToolTipCtrl::getToolInfo

도구 설명 컨트롤이 도구에 대해 유지 관리하는 정보를 검색합니다.

```
BOOL GetToolInfo(
    CToolInfo& ToolInfo,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>매개 변수

*도구 정보*<br/>
도구의 `TOOLINFO` 텍스트를 받는 개체를 참조합니다.

*pWnd*<br/>
도구가 포함된 창에 대한 포인터입니다.

*니드툴*<br/>
도구의 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

*CToolInfo에서* 참조하는 [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) 구조의 `hwnd` 멤버는 `uId` 도구를 식별합니다. 해당 도구가 이전 호출을 통해 도구 설명 부 `AddTool`컨트롤에 등록된 경우 구조는 `TOOLINFO` 도구에 대한 정보로 채워져 있습니다.

## <a name="ctooltipctrlhittest"></a><a name="hittest"></a>CToolTipCtrl::히트 테스트

점을 테스트하여 지정된 도구의 경계 사각형 내에 있는지 확인하고, 이 경우 도구에 대한 정보를 검색합니다.

```
BOOL HitTest(
    CWnd* pWnd,
    CPoint pt,
    LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
도구가 포함된 창에 대한 포인터입니다.

*pt*<br/>
테스트할 `CPoint` 점의 좌표를 포함하는 개체에 대한 포인터입니다.

*lpToolInfo*<br/>
도구 [정보](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) 구조에 대한 포인터도구 도구 에 대한 정보를 포함하는 도구 정보 구조입니다.

### <a name="return-value"></a>Return Value

적중 테스트 정보에 의해 지정된 점이 도구의 경계 사각형 내에 있는 경우 비영점; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수가 영하지 않은 값을 반환하는 경우 *lpToolInfo가* 가리키는 구조는 사각형이 있는 사각형에 있는 도구에 대한 정보로 채워집니다.

구조는 `TTHITTESTINFO` 다음과 같이 정의됩니다.

```cpp
typedef struct _TT_HITTESTINFO { // tthti
    HWND hwnd;   // handle of tool or window with tool
    POINT pt;    // client coordinates of point to test
    TOOLINFO ti; // receives information about the tool
} TTHITTESTINFO, FAR * LPHITTESTINFO;
```

- `hwnd`

   도구의 핸들을 지정합니다.

- `pt`

   점이 도구의 경계 사각형에 있는 경우 점좌좌를 지정합니다.

- `ti`

   도구에 대한 정보입니다. 구조에 `TOOLINFO` 대한 자세한 내용은 [CToolTipCtrl::GetToolInfo](#gettoolinfo)를 참조하십시오.

## <a name="ctooltipctrlpop"></a><a name="pop"></a>CToolTipCtrl::P

뷰에서 표시된 도구 설명 창을 제거합니다.

```cpp
void Pop();
```

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [TTM_POP](/windows/win32/Controls/ttm-pop)Win32 메시지의 동작을 구현합니다.

## <a name="ctooltipctrlpopup"></a><a name="popup"></a>CToolTipCtrl::P

현재 도구 설명 컨트롤이 마지막 마우스 메시지의 좌표에 표시됩니다.

```cpp
void Popup();
```

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [TTM_POPUP](/windows/win32/Controls/ttm-popup) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에는 도구 설명 창이 표시됩니다.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]

## <a name="ctooltipctrlrelayevent"></a><a name="relayevent"></a>CToolTipCtrl::릴레이 이벤트

처리를 위해 마우스 메시지를 도구 설명 컨트롤에 전달합니다.

```cpp
void RelayEvent(LPMSG lpMsg);
```

### <a name="parameters"></a>매개 변수

*lpMsg*<br/>
릴레이할 메시지가 포함된 [MSG](/windows/win32/api/winuser/ns-winuser-msg) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

도구 팁 제어는 다음 메시지만 처리하며 다음 `RelayEvent`메시지로 전송됩니다.

|WM_LBUTTONDOWN|WM_MOUSEMOVE|
|---------------------|-------------------|
|WM_LBUTTONUP|WM_RBUTTONDOWN|
|WM_MBUTTONDOWN|WM_RBUTTONUP|
|WM_MBUTTONUP||

### <a name="example"></a>예제

  [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)에 대한 예제를 참조하십시오.

## <a name="ctooltipctrlsetdelaytime"></a><a name="setdelaytime"></a>CToolTipCtrl::세트지연 시간

공구 팁 컨트롤의 지연 시간을 설정합니다.

```cpp
void SetDelayTime(UINT nDelay);

void SetDelayTime(
    DWORD dwDuration,
    int iTime);
```

### <a name="parameters"></a>매개 변수

*nDelay*<br/>
새 지연 시간을 밀리초 단위로 지정합니다.

*dwDuration*<br/>
검색할 기간 값을 지정하는 플래그입니다. 유효한 값에 대한 설명은 [CToolTipCtrl::GetDelayTime을](#getdelaytime) 참조하십시오.

*iTime*<br/>
지정된 지연 시간(밀리초)입니다.

### <a name="remarks"></a>설명

지연 시간은 도구 팁 창이 나타나기 전에 커서가 도구에 남아 있어야 하는 시간입니다. 기본 지연 시간은 500밀리초입니다.

## <a name="ctooltipctrlsetmargin"></a><a name="setmargin"></a>CToolTipCtrl::세트마진

공구 팁 창의 상단, 왼쪽, 아래쪽 및 오른쪽 여백을 설정합니다.

```cpp
void SetMargin(LPRECT lprc);
```

### <a name="parameters"></a>매개 변수

*lprc*<br/>
설정할 여백 정보가 포함된 `RECT` 구조의 주소입니다. 구조의 `RECT` 멤버는 경계 사각형을 정의하지 않습니다. 여백 정보에 대한 설명은 [CToolTipCtrl::GetMargin을](#getmargin) 참조하십시오.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [TTM_SETMARGIN](/windows/win32/Controls/ttm-setmargin)Win32 메시지의 동작을 구현합니다.

## <a name="ctooltipctrlsetmaxtipwidth"></a><a name="setmaxtipwidth"></a>CToolTipCtrl::설정맥스팁폭

공구 팁 창의 최대 너비를 설정합니다.

```
int SetMaxTipWidth(int iWidth);
```

### <a name="parameters"></a>매개 변수

*아이 폭*<br/>
설정할 최대 공구 팁 창 너비입니다.

### <a name="return-value"></a>Return Value

이전 최대 팁 너비입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [TTM_SETMAXTIPWIDTH](/windows/win32/Controls/ttm-setmaxtipwidth)Win32 메시지의 동작을 구현합니다.

## <a name="ctooltipctrlsettipbkcolor"></a><a name="settipbkcolor"></a>CToolTipCtrl::setTipBkColor

도구 설명 창에서 배경색을 설정합니다.

```cpp
void SetTipBkColor(COLORREF clr);
```

### <a name="parameters"></a>매개 변수

*Clr*<br/>
새 배경 색입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [TTM_SETTIPBKCOLOR](/windows/win32/Controls/ttm-settipbkcolor)Win32 메시지의 동작을 구현합니다.

## <a name="ctooltipctrlsettiptextcolor"></a><a name="settiptextcolor"></a>CToolTipCtrl::settipTextColor

도구 설명 창에서 텍스트 색상을 설정합니다.

```cpp
void SetTipTextColor(COLORREF clr);
```

### <a name="parameters"></a>매개 변수

*Clr*<br/>
새 텍스트 색상입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 TTM_SETTIPTEXTCOLOR Win32 [메시지의](/windows/win32/Controls/ttm-settiptextcolor)동작을 구현합니다.

## <a name="ctooltipctrlsettitle"></a><a name="settitle"></a>CToolTipCtrl::세트타이틀

도구 설명에 표준 아이콘과 제목 문자열을 추가합니다.

```
BOOL SetTitle(
    UINT uIcon,
    LPCTSTR lpstrTitle);
```

### <a name="parameters"></a>매개 변수

*uIcon*<br/>
Windows SDK의 [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle) *아이콘을* 참조하십시오.

*lpstrTitle*<br/>
제목 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle)Win32 메시지의 동작을 구현합니다.

## <a name="ctooltipctrlsettoolinfo"></a><a name="settoolinfo"></a>CToolTipCtrl::setToolInfo

도구 설명이 도구에 대해 유지 관리하는 정보를 설정합니다.

```cpp
void SetToolInfo(LPTOOLINFO lpToolInfo);
```

### <a name="parameters"></a>매개 변수

*lpToolInfo*<br/>
설정할 정보를 지정하는 [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) 구조에 대한 포인터입니다.

## <a name="ctooltipctrlsettoolrect"></a><a name="settoolrect"></a>CToolTipCtrl::setToolRect

도구에 대한 새 경계 사각형을 설정합니다.

```cpp
void SetToolRect(
    CWnd* pWnd,
    UINT_PTR nIDTool,
    LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
도구가 포함된 창에 대한 포인터입니다.

*니드툴*<br/>
도구의 ID입니다.

*Lprect*<br/>
새 경계 사각형을 지정하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 포인터입니다.

## <a name="ctooltipctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CToolTipCtrl::세트윈도우테임

도구 팁 창의 시각적 스타일을 설정합니다.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>매개 변수

*pszSubAppName*<br/>
설정할 시각적 스타일이 포함된 유니코드 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

반환 값은 사용되지 않습니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [TTM_SETWINDOWTHEME](/windows/win32/Controls/ttm-setwindowtheme) 메시지의 기능을 에뮬레이트합니다.

## <a name="ctooltipctrlupdate"></a><a name="update"></a>CToolTipCtrl::업데이트

현재 도구를 다시 그려야 합니다.

```cpp
void Update();
```

## <a name="ctooltipctrlupdatetiptext"></a><a name="updatetiptext"></a>CToolTipCtrl::업데이트 팁텍스트

이 컨트롤의 도구에 대한 도구 설명 텍스트를 업데이트합니다.

```cpp
void UpdateTipText(
    LPCTSTR lpszText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);

void UpdateTipText(
    UINT nIDText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
도구의 텍스트에 대한 포인터입니다.

*pWnd*<br/>
도구가 포함된 창에 대한 포인터입니다.

*니드툴*<br/>
도구의 ID입니다.

*니디텍스트*<br/>
도구의 텍스트가 포함된 문자열 리소스의 ID입니다.

## <a name="see-also"></a>참조

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CToolBar 클래스](../../mfc/reference/ctoolbar-class.md)
