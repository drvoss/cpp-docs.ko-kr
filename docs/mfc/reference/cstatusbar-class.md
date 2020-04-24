---
title: CStatusBar 클래스
ms.date: 11/04/2016
f1_keywords:
- CStatusBar
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
helpviewer_keywords:
- CStatusBar [MFC], CStatusBar
- CStatusBar [MFC], CommandToIndex
- CStatusBar [MFC], Create
- CStatusBar [MFC], CreateEx
- CStatusBar [MFC], DrawItem
- CStatusBar [MFC], GetItemID
- CStatusBar [MFC], GetItemRect
- CStatusBar [MFC], GetPaneInfo
- CStatusBar [MFC], GetPaneStyle
- CStatusBar [MFC], GetPaneText
- CStatusBar [MFC], GetStatusBarCtrl
- CStatusBar [MFC], SetIndicators
- CStatusBar [MFC], SetPaneInfo
- CStatusBar [MFC], SetPaneStyle
- CStatusBar [MFC], SetPaneText
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
ms.openlocfilehash: 969edb3b1c87da851d83d390ab9d4e707bd2eb1e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753047"
---
# <a name="cstatusbar-class"></a>CStatusBar 클래스

텍스트 출력 창의 행 또는 "지표"가 있는 컨트롤 막대입니다.

## <a name="syntax"></a>구문

```
class CStatusBar : public CControlBar
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C상태 표시줄::CStatusBar](#cstatusbar)|`CStatusBar` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C상태 표시줄::명령토인덱스](#commandtoindex)|지정된 표시기 ID에 대한 인덱스를 가져옵니다.|
|[C 상태 표시줄::만들기](#create)|상태 표시줄을 만들고 `CStatusBar` 개체에 연결하고 초기 글꼴 및 막대 높이를 설정합니다.|
|[C상태 표시줄::만들기 Ex](#createex)|포함된 `CStatusBarCtrl` `CStatusBar` 개체에 대한 추가 스타일이 있는 객체를 만듭니다.|
|[CStatusBar::Draw항목](#drawitem)|소유자-그리기 상태 표시줄 컨트롤의 시각적 측면이 변경 될 때 호출 됩니다.|
|[C상태 표시줄::GetItemID](#getitemid)|지정된 인덱스에 대한 표시기 ID를 가져옵니다.|
|[C상태 표시줄::GetItemRect](#getitemrect)|지정된 인덱스에 대한 표시 사각형을 가져옵니다.|
|[CStatusBar::GetPaneInfo](#getpaneinfo)|지정된 인덱스에 대한 표시기 ID, 스타일 및 너비를 가져옵니다.|
|[CStatusBar::겟파인 스타일](#getpanestyle)|지정된 인덱스에 대한 표시기 스타일을 가져옵니다.|
|[C상태 표시줄::GetPaneText](#getpanetext)|지정된 인덱스에 대한 표시기 텍스트를 가져옵니다.|
|[C상태 표시줄::겟스테이노바크터](#getstatusbarctrl)|기본 공통 컨트롤에 직접 액세스할 수 있습니다.|
|[C상태 표시줄::설정 표시기](#setindicators)|표시기 아이디를 설정합니다.|
|[C상태 표시줄::SetPaneInfo](#setpaneinfo)|지정된 인덱스에 대한 표시기 ID, 스타일 및 너비를 설정합니다.|
|[CStatusBar::세파네스타일](#setpanestyle)|지정된 인덱스에 대한 표시기 스타일을 설정합니다.|
|[C 상태 표시줄::설정창](#setpanetext)|지정된 인덱스에 대한 표시기 텍스트를 설정합니다.|

## <a name="remarks"></a>설명

출력 창은 일반적으로 메시지 줄 및 상태 표시기로 사용됩니다. 예를 들어 선택한 메뉴 명령을 간략하게 설명하는 메뉴 도움말 메시지 줄과 스크롤 잠금, NUM LOCK 및 기타 키의 상태를 표시하는 표시등이 있습니다.

[CStatusBar::GetStatusBarCtrl,](#getstatusbarctrl)MFC 4.0에 새로운 멤버 함수, 상태 표시줄 사용자 지정 및 추가 기능에 대 한 Windows 공통 컨트롤의 지원을 활용할 수 있습니다. `CStatusBar`멤버 함수는 Windows 공통 컨트롤의 대부분의 기능을 제공합니다. 그러나 호출 `GetStatusBarCtrl`할 때 상태 표시 줄에 Windows 95/98 상태 표시줄의 특성을 더 많이 제공 할 수 있습니다. 호출하면 `GetStatusBarCtrl`개체에 대한 참조가 `CStatusBarCtrl` 반환됩니다. Windows 공통 컨트롤을 사용하여 도구 모음을 디자인하는 데 대한 자세한 내용은 [CStatusBarCtrl을](../../mfc/reference/cstatusbarctrl-class.md) 참조하십시오. 일반적인 컨트롤에 대한 자세한 내용은 Windows SDK의 [일반 컨트롤을](/windows/win32/Controls/common-controls-intro) 참조하십시오.

프레임워크는 가장 왼쪽 표시기와 위치 0에 배열에 표시기 정보를 저장합니다. 상태 표시줄을 만들 때 프레임워크가 해당 표시기와 연관되는 문자열 아이디 배열을 사용합니다. 그런 다음 문자열 ID 또는 인덱스를 사용하여 표시기에 액세스할 수 있습니다.

기본적으로 첫 번째 표시기는 "탄력적"입니다: 다른 표시기 창에서 사용하지 않는 상태 표시줄 길이를 차지하므로 다른 창이 오른쪽 정렬됩니다.

상태 표시줄을 만들려면 다음 단계를 따르십시오.

1. `CStatusBar` 개체를 생성합니다.

1. [만들기(또는](#create) [CreateEx)](#createex)함수를 호출하여 상태 표시줄 창을 `CStatusBar` 만들고 개체에 연결합니다.

1. [SetIndicators를](#setindicators) 호출하여 문자열 ID를 각 표시기와 연결합니다.

상태 표시줄 창에서 텍스트를 업데이트하는 방법에는 세 가지가 있습니다.

1. [CWnd::SetWindowText를](../../mfc/reference/cwnd-class.md#setwindowtext) 호출하여 창 0의 텍스트만 업데이트합니다.

1. [CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) 상태 표시줄의 ON_UPDATE_COMMAND_UI 처리기에서 호출합니다.

1. [SetPaneText를](#setpanetext) 호출하여 모든 창에 대한 텍스트를 업데이트합니다.

[SetPaneStyle을](#setpanestyle) 호출하여 상태 표시줄 창의 스타일을 업데이트합니다.

사용에 `CStatusBar`대한 자세한 내용은 MFC 및 [기술 참고 31 : 제어 막대의](../../mfc/tn031-control-bars.md)상태 [표시줄 구현](../../mfc/status-bar-implementation-in-mfc.md) 문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CStatusBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="cstatusbarcommandtoindex"></a><a name="commandtoindex"></a>C상태 표시줄::명령토인덱스

지정된 ID에 대한 표시기 인덱스를 가져옵니다.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>매개 변수

*니드찾기*<br/>
인덱스를 검색할 표시기의 문자열 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 표시기의 인덱스; -1이 성공하지 못할 경우.

### <a name="remarks"></a>설명

첫 번째 표시기의 인덱스는 0입니다.

## <a name="cstatusbarcreate"></a><a name="create"></a>C 상태 표시줄::만들기

상태 표시줄(자식 창)을 만들고 `CStatusBar` 개체와 연결합니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
Windows 창이 상태 표시줄의 상위인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터입니다.

*dwStyle*<br/>
상태 표시줄 스타일입니다. 표준 Windows [스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)외에도 이러한 스타일이 지원됩니다.

- CBRS_TOP 컨트롤 막대는 프레임 창 의 상단에 있습니다.

- CBRS_BOTTOM 컨트롤 막대는 프레임 창 의 하단에 있습니다.

- CBRS_NOALIGN 컨트롤 막대는 부모의 크기를 조정할 때 위치가 바지지 않습니다.

*nID*<br/>
도구 모음의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

또한 초기 글꼴을 설정하고 상태 표시줄의 높이를 기본값으로 설정합니다.

## <a name="cstatusbarcreateex"></a><a name="createex"></a>C상태 표시줄::만들기 Ex

이 함수를 호출하여 상태 표시줄(자식 창)을 만들고 개체와 연결합니다. `CStatusBar`

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
Windows 창이 상태 표시줄의 상위인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터입니다.

*dwCtrl스타일*<br/>
포함된 [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) 개체를 만들기 위한 추가 스타일입니다. 기본값은 크기 조정 그립 또는 도구 설명 지원이 없는 상태 표시줄을 지정합니다. 지원되는 상태 표시줄 스타일은 다음과 같습니다.

- SBARS_SIZEGRIP 상태 표시줄 컨트롤에는 상태 표시줄의 오른쪽 끝에 크기 조정 그립이 포함됩니다. 크기 조정 그립은 크기 조정 테두리와 유사합니다. 사용자가 클릭하고 드래그하여 부모 창의 크기를 조정할 수 있는 직사각형 영역입니다.

- SBT_TOOLTIPS 상태 표시줄은 도구 설명을 지원합니다.

이러한 스타일에 대한 자세한 내용은 [CStatusBarCtrl에 대한 설정을](../../mfc/settings-for-the-cstatusbarctrl.md)참조하십시오.

*dwStyle*<br/>
상태 표시줄 스타일입니다. 기본값은 프레임 창 아래쪽에 표시되는 상태 표시줄을 만들수 있도록 지정합니다. [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 및 [CDialogBar::Create에](../../mfc/reference/cdialogbar-class.md#create)나열된 상태 표시줄 컨트롤 스타일 조합을 적용합니다. 그러나 이 매개 변수에는 항상 WS_CHILD 및 WS_VISIBLE 스타일이 포함되어야 합니다.

*nID*<br/>
상태 표시줄의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

또한 이 함수는 초기 글꼴을 설정하고 상태 표시줄의 높이를 기본값으로 설정합니다.

포함된 상태 표시줄 컨트롤을 만드는 동안 특정 스타일이 있어야 하는 경우 `CreateEx` [Create](#create)대신 을 사용합니다. 예를 들어 *dwCtrlStyle을* SBT_TOOLTIPS 설정하여 상태 표시줄 개체에 도구 설명팁을 표시합니다.

## <a name="cstatusbarcstatusbar"></a><a name="cstatusbar"></a>C상태 표시줄::CStatusBar

개체를 `CStatusBar` 생성하고 필요한 경우 기본 상태 표시줄 글꼴을 만들고 글꼴 특성을 기본값으로 설정합니다.

```
CStatusBar();
```

## <a name="cstatusbardrawitem"></a><a name="drawitem"></a>CStatusBar::Draw항목

소유자가 그린 상태 표시줄의 시각적 측면이 변경될 때 이 멤버 함수는 프레임워크에서 호출됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
필요한 도면 유형에 대한 정보가 포함된 [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

`DRAWITEMSTRUCT` 구조의 멤버는 `itemAction` 수행할 드로잉 작업을 정의합니다. 이 멤버 함수를 재정의하여 소유자-그리기 객체에 대한 그리기를 구현합니다. `CStatusBar` 응용 프로그램은 이 멤버 함수가 종료되기 전에 *lpDrawItemStruct에* 제공된 디스플레이 컨텍스트에 대해 선택된 모든 GDI(그래픽 장치 인터페이스) 개체를 복원해야 합니다.

## <a name="cstatusbargetitemid"></a><a name="getitemid"></a>C상태 표시줄::GetItemID

*nIndex*.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
ID를 검색할 표시기의 인덱스입니다.

### <a name="return-value"></a>Return Value

*nIndex*.

## <a name="cstatusbargetitemrect"></a><a name="getitemrect"></a>C상태 표시줄::GetItemRect

*lpRect에*의해 가리키는 구조에 *nIndex에* 의해 지정 된 표시기의 좌표를 복사 합니다.

```cpp
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
사각형 좌표를 검색할 표기의 인덱스입니다.

*Lprect*<br/>
*nIndex에서*지정한 표시기의 좌표를 수신하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체를 가리킵니다.

### <a name="remarks"></a>설명

좌표는 상태 표시줄의 왼쪽 위 모서리를 기준으로 픽셀에 있습니다.

## <a name="cstatusbargetpaneinfo"></a><a name="getpaneinfo"></a>CStatusBar::GetPaneInfo

*nIndex에서*지정한 위치에서 표시기 창의 ID, 스타일 및 너비에 *nID,* *nStyle*및 *cxWidth를* 설정합니다.

```cpp
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
정보를 검색할 창의 인덱스입니다.

*nID*<br/>
창의 ID로 설정된 UINT를 참조합니다.

*nStyle*<br/>
창의 스타일로 설정된 UINT를 참조합니다.

*cxWidth*<br/>
창의 너비로 설정된 정수를 참조합니다.

## <a name="cstatusbargetpanestyle"></a><a name="getpanestyle"></a>CStatusBar::겟파인 스타일

이 멤버 함수를 호출하여 상태 표시줄 창의 스타일을 검색합니다.

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
스타일을 검색할 창의 인덱스입니다.

### <a name="return-value"></a>Return Value

*nIndex에서*지정한 상태 표시줄 창의 스타일입니다.

### <a name="remarks"></a>설명

창의 스타일에 따라 창이 표시되는 방식이 결정됩니다.

상태 표시줄에 사용할 수 있는 스타일 목록은 [을](#create)참조하십시오.

## <a name="cstatusbargetpanetext"></a><a name="getpanetext"></a>C상태 표시줄::GetPaneText

이 멤버 함수를 호출하여 상태 표시줄 창에 나타나는 텍스트를 검색합니다.

```
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
텍스트를 검색할 창의 인덱스입니다.

*rString*<br/>
검색할 텍스트가 포함된 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

창의 텍스트가 포함된 `CString` 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수의 두 번째 `CString` 양식은 개체를 문자열 텍스트로 채웁니다.

## <a name="cstatusbargetstatusbarctrl"></a><a name="getstatusbarctrl"></a>C상태 표시줄::겟스테이노바크터

이 멤버 함수를 사용하면 기본 공통 컨트롤에 직접 액세스할 수 있습니다.

```
CStatusBarCtrl& GetStatusBarCtrl() const;
```

### <a name="return-value"></a>Return Value

[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) 개체에 대한 참조를 포함합니다.

### <a name="remarks"></a>설명

Windows `GetStatusBarCtrl` 상태 표시줄 공통 컨트롤의 기능을 활용하고 [CStatusBarCtrl이](../../mfc/reference/cstatusbarctrl-class.md) 상태 표시줄 사용자 지정에 제공하는 지원을 활용하는 데 사용합니다. 예를 들어 공통 컨트롤을 사용하여 상태 표시줄의 크기 조정 그립이 포함된 스타일을 지정하거나 상태 표시줄이 부모 창의 클라이언트 영역 맨 위에 표시되도록 스타일을 지정할 수 있습니다.

일반적인 컨트롤에 대한 자세한 내용은 Windows SDK의 [일반 컨트롤을](/windows/win32/Controls/common-controls-intro) 참조하십시오.

## <a name="cstatusbarsetindicators"></a><a name="setindicators"></a>C상태 표시줄::설정 표시기

각 표시기의 ID를 배열 *lpIDArray의*해당 요소에 의해 지정 된 값으로 설정 하 고 각 ID에 의해 지정 된 문자열 리소스를 로드 하 고 표시기의 텍스트를 문자열에 설정 합니다.

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>매개 변수

*lpID어레이*<br/>
아이디 배열에 대한 포인터입니다.

*니드 카운트*<br/>
배열의 요소 수는 *lpIDArray로*가리켰습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

## <a name="cstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a>C상태 표시줄::SetPaneInfo

지정된 표시기 창을 새 ID, 스타일 및 너비로 설정합니다.

```cpp
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
스타일을 설정할 표시기 창의 인덱스입니다.

*nID*<br/>
표시기 창에 대한 새 ID입니다.

*nStyle*<br/>
표시기 창에 대한 새 스타일입니다.

*cxWidth*<br/>
표시기 창에 대한 새 너비입니다.

### <a name="remarks"></a>설명

다음 표시기 스타일이 지원됩니다.

- SBPS_NOBORDERS 창 주위의 3D 테두리가 없습니다.

- SBPS_POPOUT 텍스트가 튀어나오게 되도록 테두리를 반대로 합니다.

- SBPS_DISABLED 텍스트를 그리지 마십시오.

- SBPS_STRETCH 창을 늘려 사용하지 않은 공간을 채웁니다. 상태 표시줄당 하나의 창만 이 스타일을 가질 수 있습니다.

- SBPS_NORMAL 스트레치, 테두리 또는 팝아웃이 없습니다.

## <a name="cstatusbarsetpanestyle"></a><a name="setpanestyle"></a>CStatusBar::세파네스타일

이 멤버 함수를 호출하여 상태 표시줄창의 스타일을 설정합니다.

```cpp
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
스타일을 설정할 창의 인덱스입니다.

*nStyle*<br/>
스타일을 설정해야 하는 창의 스타일입니다.

### <a name="remarks"></a>설명

창의 스타일에 따라 창이 표시되는 방식이 결정됩니다.

상태 표시줄에 사용할 수 있는 스타일 목록은 [SetPaneInfo](#setpaneinfo)을 참조하십시오.

## <a name="cstatusbarsetpanetext"></a><a name="setpanetext"></a>C 상태 표시줄::설정창

이 멤버 함수를 호출하여 창 텍스트를 *lpszNewText로*가리키는 문자열로 설정합니다.

```
BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
텍스트를 설정할 창의 인덱스입니다.

*lpszNewText*<br/>
새 창 텍스트에 대한 포인터입니다.

*bUpdate*<br/>
TRUE이면 텍스트를 설정한 후 창이 무효화됩니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출한 `SetPaneText`후 상태 표시줄에 새 텍스트를 표시하려면 UI 업데이트 처리기를 추가해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC Sample DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CStatusBarCtrl 클래스](../../mfc/reference/cstatusbarctrl-class.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)
