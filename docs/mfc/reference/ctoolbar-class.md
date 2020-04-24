---
title: CToolBar 클래스
ms.date: 11/04/2016
f1_keywords:
- CToolBar
- AFXEXT/CToolBar
- AFXEXT/CToolBar::CToolBar
- AFXEXT/CToolBar::CommandToIndex
- AFXEXT/CToolBar::Create
- AFXEXT/CToolBar::CreateEx
- AFXEXT/CToolBar::GetButtonInfo
- AFXEXT/CToolBar::GetButtonStyle
- AFXEXT/CToolBar::GetButtonText
- AFXEXT/CToolBar::GetItemID
- AFXEXT/CToolBar::GetItemRect
- AFXEXT/CToolBar::GetToolBarCtrl
- AFXEXT/CToolBar::LoadBitmap
- AFXEXT/CToolBar::LoadToolBar
- AFXEXT/CToolBar::SetBitmap
- AFXEXT/CToolBar::SetButtonInfo
- AFXEXT/CToolBar::SetButtons
- AFXEXT/CToolBar::SetButtonStyle
- AFXEXT/CToolBar::SetButtonText
- AFXEXT/CToolBar::SetHeight
- AFXEXT/CToolBar::SetSizes
helpviewer_keywords:
- CToolBar [MFC], CToolBar
- CToolBar [MFC], CommandToIndex
- CToolBar [MFC], Create
- CToolBar [MFC], CreateEx
- CToolBar [MFC], GetButtonInfo
- CToolBar [MFC], GetButtonStyle
- CToolBar [MFC], GetButtonText
- CToolBar [MFC], GetItemID
- CToolBar [MFC], GetItemRect
- CToolBar [MFC], GetToolBarCtrl
- CToolBar [MFC], LoadBitmap
- CToolBar [MFC], LoadToolBar
- CToolBar [MFC], SetBitmap
- CToolBar [MFC], SetButtonInfo
- CToolBar [MFC], SetButtons
- CToolBar [MFC], SetButtonStyle
- CToolBar [MFC], SetButtonText
- CToolBar [MFC], SetHeight
- CToolBar [MFC], SetSizes
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
ms.openlocfilehash: cbb2d1bb797737a14e9728d339305bf9c371b543
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752213"
---
# <a name="ctoolbar-class"></a>CToolBar 클래스

비트맵 단추의 행과 구분 기호(선택 사항)가 있는 컨트롤 막대입니다.

## <a name="syntax"></a>구문

```
class CToolBar : public CControlBar
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CToolBar:::CToolBar](#ctoolbar)|`CToolBar` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CToolBar::명령토인덱스](#commandtoindex)|지정된 명령 ID가 있는 단추의 인덱스를 반환합니다.|
|[CToolBar::만들기](#create)|Windows 도구 모음을 만들고 개체에 `CToolBar` 연결합니다.|
|[CToolBar::만들기](#createex)|포함된 `CToolBarCtrl` `CToolBar` 개체에 대한 추가 스타일이 있는 객체를 만듭니다.|
|[CToolBar::GetButtonInfo](#getbuttoninfo)|단추의 ID, 스타일 및 이미지 번호를 검색합니다.|
|[CToolBar::GetButton 스타일](#getbuttonstyle)|단추에 대한 스타일을 검색합니다.|
|[CToolBar::GetButton텍스트](#getbuttontext)|단추에 표시되는 텍스트를 검색합니다.|
|[CToolBar:::GetItemID](#getitemid)|지정된 인덱스에서 단추 또는 구분 기호의 명령 ID를 반환합니다.|
|[CToolBar::GetItemRect](#getitemrect)|지정된 인덱스에서 항목에 대한 표시 사각형을 검색합니다.|
|[CToolBar::GetToolBarCtrl](#gettoolbarctrl)|기본 공통 컨트롤에 직접 액세스할 수 있습니다.|
|[CToolBar::로드비트맵](#loadbitmap)|비트맵 단추 이미지가 포함된 비트맵을 로드합니다.|
|[CToolBar::로드툴바](#loadtoolbar)|리소스 편집기로 만든 도구 모음 리소스를 로드합니다.|
|[CToolBar::세트비트맵](#setbitmap)|비트매핑된 이미지를 설정합니다.|
|[CToolBar::설정 단추정보](#setbuttoninfo)|단추의 ID, 스타일 및 이미지 번호를 설정합니다.|
|[CToolBar::설정 단추](#setbuttons)|비트맵 내에서 단추 스타일과 단추 이미지 인덱스를 설정합니다.|
|[CToolBar::설정 단추 스타일](#setbuttonstyle)|단추의 스타일을 설정합니다.|
|[CToolBar::설정 단추 텍스트](#setbuttontext)|단추에 표시되는 텍스트를 설정합니다.|
|[CToolBar::설정높이](#setheight)|도구 모음의 높이를 설정합니다.|
|[CToolBar::설정 크기](#setsizes)|단추 크기와 비트맵을 설정합니다.|

## <a name="remarks"></a>설명

버튼은 푸시 버튼, 확인란 버튼 또는 라디오 버튼과 같이 작동할 수 있습니다. `CToolBar`개체는 일반적으로 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 또는 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)클래스에서 파생된 프레임 창 개체의 포함된 멤버입니다.

[CToolBar::GetToolBarCtrl,](#gettoolbarctrl)MFC 4.0에 새로운 멤버 함수, 도구 모음 사용자 지정 및 추가 기능에 대 한 Windows 공통 컨트롤의 지원을 활용할 수 있습니다. `CToolBar`멤버 함수는 Windows 공통 컨트롤의 대부분의 기능을 제공합니다. 그러나 호출 `GetToolBarCtrl`할 때 도구 모음에 Windows 95 /98 도구 모음의 특성을 더 많이 제공 할 수 있습니다. 호출하면 `GetToolBarCtrl`개체에 대한 참조가 `CToolBarCtrl` 반환됩니다. Windows 공통 컨트롤을 사용하여 도구 모음을 디자인하는 데 대한 자세한 내용은 [CToolBarCtrl을](../../mfc/reference/ctoolbarctrl-class.md) 참조하십시오. 일반적인 컨트롤에 대한 자세한 내용은 Windows SDK의 [일반 컨트롤을](/windows/win32/Controls/common-controls-intro) 참조하십시오.

Visual C++는 도구 모음을 만드는 두 가지 방법을 제공합니다. 리소스 편집기를 사용하여 도구 모음 리소스를 만들려면 다음 단계를 따르십시오.

1. 도구 모음 리소스를 만듭니다.

1. `CToolBar` 개체를 생성합니다.

1. [만들기(또는](#create) [CreateEx)](#createex)함수를 호출하여 Windows 도구 모음을 `CToolBar` 만들고 개체에 연결합니다.

1. [LoadToolBar를](#loadtoolbar) 호출하여 도구 모음 리소스를 로드합니다.

액세스 권한이 없는 경우 다음 단계를 수행하세요.

1. `CToolBar` 개체를 생성합니다.

1. [만들기(또는](#create) [CreateEx)](#createex)함수를 호출하여 Windows 도구 모음을 `CToolBar` 만들고 개체에 연결합니다.

1. [LoadBitmap을](#loadbitmap) 호출하여 도구 모음 단추 이미지가 포함된 비트맵을 로드합니다.

1. [SetButtons를](#setbuttons) 호출하여 단추 스타일을 설정하고 각 단추를 비트맵의 이미지와 연결합니다.

도구 모음의 모든 단추 이미지는 각 단추에 대해 하나의 이미지를 포함해야 하는 하나의 비트맵에서 가져온 것입니다. 모든 이미지의 크기가 같아야 합니다. 기본값은 너비가 16픽셀이고 높이가 15픽셀입니다. 이미지는 비트맵에서 나란히 있어야 합니다.

함수는 `SetButtons` 컨트롤 아이디배열에 대한 포인터와 배열의 요소 수를 지정하는 정수를 합니다. 이 함수는 각 단추의 ID를 배열의 해당 요소 값으로 설정하고 각 단추에 비트맵에서 단추 이미지의 위치를 지정하는 이미지 인덱스를 할당합니다. 배열 요소에 ID_SEPARATOR 값이 있으면 이미지 인덱스가 할당되지 않습니다.

비트맵에서 이미지의 순서는 일반적으로 화면에 그려지는 순서이지만 [SetButtonInfo](#setbuttoninfo) 함수를 사용하여 이미지 순서와 그리기 순서 간의 관계를 변경할 수 있습니다.

도구 모음의 모든 단추는 크기가 동일합니다. 기본값은 *소프트웨어 디자인에 대한 Windows 인터페이스 지침에*따라 24 x 22 픽셀입니다. 이미지 크기와 단추 크기 사이의 추가 공간은 이미지 주위에 테두리를 형성하는 데 사용됩니다.

각 버튼에는 하나의 이미지가 있습니다. 다양한 단추 상태 및 스타일(누른, 위, 아래, 비활성화, 아래로 및 확정되지 않음)이 해당 이미지에서 생성됩니다. 비트맵은 모든 색상일 수 있지만 검은색 및 회색 음영으로 이미지를 사용하면 최상의 결과를 얻을 수 있습니다.

> [!WARNING]
> `CToolBar`최대 16색의 비트맵을 지원합니다. 이미지를 도구 모음 편집기로 로드하면 Visual Studio는 필요한 경우 이미지를 자동으로 16색 비트맵으로 변환하고 이미지가 변환된 경우 경고 메시지를 표시합니다. 외부 편집기를 사용하여 이미지를 편집하는 경우 16개 이상의 색상이 있는 이미지를 사용하는 경우 응용 프로그램이 예기치 않게 동작할 수 있습니다.

도구 모음 단추는 기본적으로 푸시 버튼을 모방합니다. 그러나 도구 모음 단추는 확인란 단추 또는 라디오 단추를 모방할 수도 있습니다. 확인란 단추에는 선택, 선택 취소 및 확정되지 않은 세 가지 상태가 있습니다. 라디오 단추에는 두 가지 상태만 있습니다.

배열을 가리키지 않고 개별 단추 또는 구분 기호 스타일을 설정하려면 [GetButtonStyle을](#getbuttonstyle) 호출하여 스타일을 검색한 `SetButtons`다음 대신 [SetButtonStyle을](#setbuttonstyle) 호출합니다. `SetButtonStyle`런타임에 단추 스타일을 변경하려는 경우에 가장 유용합니다.

단추에 표시할 텍스트를 할당하려면 [GetButtonText를](#getbuttontext) 호출하여 단추에 표시할 텍스트를 검색한 다음 [SetButtonText를](#setbuttontext) 호출하여 텍스트를 설정합니다.

확인란 단추를 만들려면 스타일을 TBBS_CHECKBOX 할당하거나 ON_UPDATE_COMMAND_UI `CCmdUI` 처리기에서 개체의 `SetCheck` 멤버 함수를 사용합니다. 호출하면 `SetCheck` 푸시버튼이 확인란 버튼으로 바뀝니다. 선택되지 않은 경우 0, 선택되지 않은 인수의 경우 1, 확정되지 않은 인수는 2를 전달합니다. `SetCheck`

라디오 단추를 만들려면 ON_UPDATE_COMMAND_UI 처리기에서 [CCmdUI](../../mfc/reference/ccmdui-class.md) 개체의 [SetRadio](../../mfc/reference/ccmdui-class.md#setradio) 멤버 함수를 호출합니다. 선택되지 않은 경우 0의 인수를 전달하거나 0이 아닌 지의 경우 선택된 인수를 전달합니다. `SetRadio` 라디오 그룹의 상호 배타적 동작을 제공하려면 그룹의 모든 단추에 대해 ON_UPDATE_COMMAND_UI 처리기가 있어야 합니다.

사용에 `CToolBar`대한 자세한 내용은 [MFC 도구 모음 구현](../../mfc/mfc-toolbar-implementation.md) 및 기술 참고 사항 [31: 컨트롤 모음](../../mfc/tn031-control-bars.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CToolBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="ctoolbarcommandtoindex"></a><a name="commandtoindex"></a>CToolBar::명령토인덱스

이 멤버 함수는 명령 ID가 일치하는 `nIDFind`위치 0부터 시작하여 첫 번째 도구 모음 단추의 인덱스를 반환합니다.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>매개 변수

*니드찾기*<br/>
도구 모음 단추의 명령 ID입니다.

### <a name="return-value"></a>Return Value

지정된 명령 ID가 있는 단추(단추)가 없는 경우 단추의 인덱스 또는 -1입니다.

## <a name="ctoolbarcreate"></a><a name="create"></a>CToolBar::만들기

이 멤버 함수는 Windows 도구 모음(자식 창)을 만들고 `CToolBar` 개체와 연결합니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
도구 모음의 부모인 창에 대한 포인터입니다.

*dwStyle*<br/>
도구 모음 스타일입니다. 지원되는 추가 도구 모음 스타일은 다음과 같습니다.

- CBRS_TOP 컨트롤 막대는 프레임 창 의 맨 위에 있습니다.

- CBRS_BOTTOM 컨트롤 막대는 프레임 창 의 하단에 있습니다.

- CBRS_NOALIGN 컨트롤 막대는 부모의 크기를 조정할 때 위치가 바지지 않습니다.

- CBRS_TOOLTIPS 컨트롤 막대는 도구 팁을 표시합니다.

- CBRS_SIZE_DYNAMIC 컨트롤 바는 동적입니다.

- CBRS_SIZE_FIXED 컨트롤 바가 고정되어 있습니다.

- CBRS_FLOATING 컨트롤 바가 부동입니다.

- CBRS_FLYBY 상태 표시줄은 단추에 대한 정보를 표시합니다.

- CBRS_HIDE_INPLACE 컨트롤 막대가 사용자에게 표시되지 않습니다.

*nID*<br/>
도구 모음의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

또한 도구 모음 높이를 기본값으로 설정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]

## <a name="ctoolbarcreateex"></a><a name="createex"></a>CToolBar::만들기

이 함수를 호출하여 Windows 도구 모음(자식 창)을 만들고 개체와 연결합니다. `CToolBar`

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = TBSTYLE_FLAT,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_ALIGN_TOP,
    CRect rcBorders = CRect(
    0,
    0,
    0,
    0),
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
도구 모음의 부모인 창에 대한 포인터입니다.

*dwCtrl스타일*<br/>
포함된 [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) 개체를 만들기 위한 추가 스타일입니다. 기본적으로 이 값은 TBSTYLE_FLAT 설정됩니다. 도구 모음 스타일의 전체 목록은 *dwStyle*을 참조하십시오.

*dwStyle*<br/>
도구 모음 스타일입니다. 적절한 스타일 목록은 Windows SDK의 [도구 모음 컨트롤 및 단추 스타일을](/windows/win32/Controls/toolbar-control-and-button-styles) 참조하십시오.

*rcBorders*<br/>
도구 모음 창 테두리의 너비를 정의하는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체입니다. 이러한 테두리는 기본적으로 0,0,0,0으로 설정되어 테두리가 없는 도구 모음 창이 생성됩니다.

*nID*<br/>
도구 모음의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

또한 도구 모음 높이를 기본값으로 설정합니다.

포함된 도구 모음 컨트롤을 만드는 동안 특정 스타일이 있어야 하는 경우 `CreateEx` [Create](#create)대신 을 사용합니다. 예를 들어 *dwCtrlStyle을* TBSTYLE_FLAT &#124; TBSTYLE_TRANSPARENT 설정하여 Internet Explorer 4 도구 모음과 유사한 도구 모음을 만듭니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]

## <a name="ctoolbarctoolbar"></a><a name="ctoolbar"></a>CToolBar:::CToolBar

이 멤버 함수는 `CToolBar` 개체를 생성하고 기본 크기를 설정합니다.

```
CToolBar();
```

### <a name="remarks"></a>설명

도구 모음 창을 만들려면 멤버 [만들기](#create) 함수를 호출합니다.

## <a name="ctoolbargetbuttoninfo"></a><a name="getbuttoninfo"></a>CToolBar::GetButtonInfo

이 멤버 함수는 *nIndex에서* 지정한 위치에서 도구 모음 단추 또는 구분 기호의 컨트롤 ID, 스타일 및 이미지 인덱스를 검색합니다.

```cpp
void GetButtonInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& iImage) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
정보를 검색할 도구 모음 단추 또는 구분 기호의 인덱스입니다.

*nID*<br/>
단추의 명령 ID로 설정된 UINT를 참조합니다.

*nStyle*<br/>
단추 의 스타일로 설정된 UINT를 참조합니다.

*아이 이미지*<br/>
비트맵 내에서 단추 이미지의 인덱스로 설정된 정수를 참조합니다.

### <a name="remarks"></a>설명

이러한 값은 *nID,* *nStyle*및 *iImage에서*참조하는 변수에 할당됩니다. 이미지 인덱스는 모든 도구 모음 단추에 대한 이미지가 포함된 비트맵 내의 이미지 위치입니다. 첫 번째 이미지는 위치 0에 있습니다.

*nIndex가* 구분 기호를 지정하는 경우 *iImage는* 픽셀의 구분 기호 너비로 설정됩니다.

## <a name="ctoolbargetbuttonstyle"></a><a name="getbuttonstyle"></a>CToolBar::GetButton 스타일

이 멤버 함수를 호출하여 도구 모음에서 단추 또는 구분 기호의 스타일을 검색합니다.

```
UINT GetButtonStyle(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
검색할 도구 모음 단추 또는 구분 기호 스타일의 인덱스입니다.

### <a name="return-value"></a>Return Value

*nIndex에서*지정한 단추 또는 구분 기호의 스타일입니다.

### <a name="remarks"></a>설명

단추의 스타일에 따라 단추가 표시되는 방식과 단추의 응답 방식이 결정됩니다. 단추 스타일의 예는 [SetButtonStyle을](#setbuttonstyle) 참조하십시오.

## <a name="ctoolbargetbuttontext"></a><a name="getbuttontext"></a>CToolBar::GetButton텍스트

이 멤버 함수를 호출하여 단추에 나타나는 텍스트를 검색합니다.

```
CString GetButtonText(int nIndex) const;

void GetButtonText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
검색할 텍스트의 인덱스입니다.

*rString*<br/>
검색할 텍스트를 포함하는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

단추 `CString` 텍스트가 포함된 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수의 두 번째 `CString` 양식은 개체를 문자열 텍스트로 채웁니다.

## <a name="ctoolbargetitemid"></a><a name="getitemid"></a>CToolBar:::GetItemID

이 멤버 함수는 *nIndex*.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
ID를 검색할 항목의 인덱스입니다.

### <a name="return-value"></a>Return Value

*nIndex에서*지정한 단추 또는 구분 기호의 명령 ID입니다.

### <a name="remarks"></a>설명

분리기는 ID_SEPARATOR 반환합니다.

## <a name="ctoolbargetitemrect"></a><a name="getitemrect"></a>CToolBar::GetItemRect

이 멤버 함수는 `RECT` 주소가 *lpRect에* 포함된 구조를 *nIndex에서*지정한 단추 또는 구분 기호로 채웁니다.

```
virtual void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
사각형 좌표를 검색할 항목(단추 또는 구분 기호)의 인덱스입니다.

*Lprect*<br/>
항목의 좌표를 포함 하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조의 주소입니다.

### <a name="remarks"></a>설명

좌표는 도구 모음의 왼쪽 위 모서리를 기준으로 픽셀에 있습니다.

콤보 상자 또는 기타 컨트롤로 대체하려는 구분 기호의 좌표를 얻는 데 사용합니다. `GetItemRect`

### <a name="example"></a>예제

  [CToolBar::SetSizes에](#setsizes)대한 예제를 참조하십시오.

## <a name="ctoolbargettoolbarctrl"></a><a name="gettoolbarctrl"></a>CToolBar::GetToolBarCtrl

이 멤버 함수를 사용하면 기본 공통 컨트롤에 직접 액세스할 수 있습니다.

```
CToolBarCtrl& GetToolBarCtrl() const;
```

### <a name="return-value"></a>Return Value

`CToolBarCtrl` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

Windows `GetToolBarCtrl` 도구 모음 공통 컨트롤의 기능을 활용하고 [CToolBarCtrl이](../../mfc/reference/ctoolbarctrl-class.md) 도구 모음 사용자 지정에 제공하는 지원을 활용하는 데 사용합니다.

일반적인 컨트롤 사용에 대한 자세한 내용은 Windows SDK의 [컨트롤](../../mfc/controls-mfc.md) 및 [일반 컨트롤](/windows/win32/Controls/common-controls-intro) 문서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]

## <a name="ctoolbarloadbitmap"></a><a name="loadbitmap"></a>CToolBar::로드비트맵

이 멤버 함수를 호출하여 에 `lpszResourceName` `nIDResource`의해 지정된 비트맵을 로드하거나.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>매개 변수

*lpszResourceName*<br/>
로드할 비트맵의 리소스 이름에 대한 포인터입니다.

*nIDResource*<br/>
로드할 비트맵의 리소스 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

비트맵에는 각 도구 모음 단추에 대해 하나의 이미지가 포함되어야 합니다. 이미지가 표준 크기(너비 16픽셀 및 높이 15픽셀)가 아닌 경우 [SetSizes를](#setsizes) 호출하여 단추 크기와 이미지를 설정합니다.

> [!WARNING]
> `CToolBar`최대 16색의 비트맵을 지원합니다. 이미지를 도구 모음 편집기로 로드하면 Visual Studio는 필요한 경우 이미지를 자동으로 16색 비트맵으로 변환하고 이미지가 변환된 경우 경고 메시지를 표시합니다. 외부 편집기를 사용하여 이미지를 편집하는 경우 16개 이상의 색상이 있는 이미지를 사용하는 경우 응용 프로그램이 예기치 않게 동작할 수 있습니다.

## <a name="ctoolbarloadtoolbar"></a><a name="loadtoolbar"></a>CToolBar::로드툴바

*lpszResourceName* 또는 *nIDResource*.

```
BOOL LoadToolBar(LPCTSTR lpszResourceName);
BOOL LoadToolBar(UINT nIDResource);
```

### <a name="parameters"></a>매개 변수

*lpszResourceName*<br/>
로드할 도구 모음의 리소스 이름에 대한 포인터입니다.

*nIDResource*<br/>
로드할 도구 모음의 리소스 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

도구 모음 리소스 를 만드는 것에 대한 자세한 내용은 [도구 모음 편집기에서](../../windows/toolbar-editor.md) 를 참조하십시오.

### <a name="example"></a>예제

  [CToolBar::CreateEx](#createex)에 대한 예제를 참조하십시오.

## <a name="ctoolbarsetbitmap"></a><a name="setbitmap"></a>CToolBar::세트비트맵

이 멤버 함수를 호출하여 도구 모음의 비트맵 이미지를 설정합니다.

```
BOOL SetBitmap(HBITMAP hbmImageWell);
```

### <a name="parameters"></a>매개 변수

*hbm이미지웰*<br/>
도구 모음과 연결된 비트맵 이미지의 핸들입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

예를 들어 `SetBitmap` 사용자가 단추의 작업을 변경하는 문서에서 작업을 수행한 후 비트매핑된 이미지를 변경하도록 요청합니다.

## <a name="ctoolbarsetbuttoninfo"></a><a name="setbuttoninfo"></a>CToolBar::설정 단추정보

이 멤버 함수를 호출하여 단추의 명령 ID, 스타일 및 이미지 번호를 설정합니다.

```cpp
void SetButtonInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int iImage);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
정보를 설정할 단추 또는 구분 기호의 0 기반 인덱스입니다.

*nID*<br/>
단추의 명령 ID가 설정된 값입니다.

*nStyle*<br/>
새 단추 스타일입니다. 다음 단추 스타일이 지원됩니다.

- TBBS_BUTTON 표준 푸시 버튼(기본값)

- TBBS_SEPARATOR 분리기

- TBBS_CHECKBOX 자동 확인란 버튼

- TBBS_GROUP 단추 그룹의 시작을 표시합니다.

- TBBS_CHECKGROUP 확인란 단추 그룹의 시작을 표시합니다.

- TBBS_DROPDOWN 드롭다운 목록 단추를 만듭니다.

- TBBS_AUTOSIZE 단추의 너비는 이미지 크기가 아니라 단추의 텍스트를 기반으로 계산됩니다.

- TBBS_NOPREFIX 단추 텍스트에는 가속기 접두사가 연결되어 있지 않습니다.

*아이 이미지*<br/>
비트맵 내에서 단추 이미지에 대한 새 인덱스입니다.

### <a name="remarks"></a>설명

스타일 TBBS_SEPARATOR 구분 기호의 경우 이 함수는 구분 기호의 너비를 픽셀 단위로 *iImage에*저장된 값으로 설정합니다.

> [!NOTE]
> *nStyle* 매개 변수를 사용하여 단추 상태를 설정할 수도 있습니다. 그러나 단추 상태는 [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) 처리기에 의해 제어되므로 다음 `SetButtonInfo` 유휴 처리 중에 사용한 모든 상태가 손실됩니다. 자세한 내용은 사용자 인터페이스 개체 및 [TN031: 제어 막대를](../../mfc/tn031-control-bars.md) [업데이트하는 방법을](../../mfc/how-to-update-user-interface-objects.md) 참조하십시오.

비트맵 이미지 및 단추에 대한 자세한 내용은 [CToolBar](../../mfc/reference/ctoolbar-class.md) 개요 및 [CToolBar::LoadBitmap](#loadbitmap)을 참조하십시오.

## <a name="ctoolbarsetbuttons"></a><a name="setbuttons"></a>CToolBar::설정 단추

이 멤버 함수는 각 도구 모음 단추의 명령 ID를 배열 *lpIDArray의*해당 요소에 의해 지정된 값으로 설정합니다.

```
BOOL SetButtons(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>매개 변수

*lpID어레이*<br/>
명령 ID의 배열에 대한 포인터입니다. 빈 단추를 할당하려면 NULL일 수 있습니다.

*니드 카운트*<br/>
배열의 요소 수는 *lpIDArray로*가리켰습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

배열의 요소에 ID_SEPARATOR 값이 있는 경우 도구 모음의 해당 위치에 구분 기호가 만들어집니다. 또한 이 함수는 각 단추의 스타일을 TBBS_BUTTON 설정하고 각 구분 기호의 스타일을 TBBS_SEPARATOR 각 단추에 이미지 인덱스를 할당합니다. 이미지 인덱스는 비트맵 내에서 단추 이미지의 위치를 지정합니다.

이 함수는 구분 기호에 대한 이미지 인덱스를 할당하지 않으므로 비트맵에서 구분 기호를 설명할 필요가 없습니다. 도구 모음에 위치 0, 1 및 3에 버튼이 있고 위치 2의 구분 기호가 있는 경우 비트맵의 위치 0, 1 및 2의 이미지는 각각 위치 0, 1 및 3의 단추에 할당됩니다.

*lpIDArray가* NULL이면 이 함수는 *nIDCount*에 의해 지정된 항목 수에 대한 공간을 할당합니다. [SetButtonInfo를](#setbuttoninfo) 사용하여 각 항목의 속성을 설정합니다.

## <a name="ctoolbarsetbuttonstyle"></a><a name="setbuttonstyle"></a>CToolBar::설정 단추 스타일

이 멤버 함수를 호출하여 단추 또는 구분 기호의 스타일을 설정하거나 단추를 그룹화합니다.

```cpp
void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
정보를 설정해야 하는 단추 또는 구분 기호의 인덱스입니다.

*nStyle*<br/>
단추 스타일입니다. 다음 단추 스타일이 지원됩니다.

- TBBS_BUTTON 표준 푸시 버튼(기본값)

- TBBS_SEPARATOR 분리기

- TBBS_CHECKBOX 자동 확인란 버튼

- TBBS_GROUP 단추 그룹의 시작을 표시합니다.

- TBBS_CHECKGROUP 확인란 단추 그룹의 시작을 표시합니다.

- TBBS_DROPDOWN 드롭다운 목록 단추 를 만듭니다.

- TBBS_AUTOSIZE 단추의 너비는 이미지 의 크기가 아니라 단추의 텍스트를 기반으로 계산됩니다.

- TBBS_NOPREFIX 단추 텍스트에 연결된 가속기 접두사가 없습니다.

### <a name="remarks"></a>설명

단추의 스타일에 따라 단추가 표시되는 방식과 단추의 응답 방식이 결정됩니다.

호출하기 `SetButtonStyle`전에 [GetButtonStyle](#getbuttonstyle) 멤버 함수를 호출하여 단추 또는 구분 기호 스타일을 검색합니다.

> [!NOTE]
> *nStyle* 매개 변수를 사용하여 단추 상태를 설정할 수도 있습니다. 그러나 단추 상태는 [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) 처리기에 의해 제어되므로 다음 `SetButtonStyle` 유휴 처리 중에 사용한 모든 상태가 손실됩니다. 자세한 내용은 사용자 인터페이스 개체 및 [TN031: 제어 막대를](../../mfc/tn031-control-bars.md) [업데이트하는 방법을](../../mfc/how-to-update-user-interface-objects.md) 참조하십시오.

## <a name="ctoolbarsetbuttontext"></a><a name="setbuttontext"></a>CToolBar::설정 단추 텍스트

이 함수를 호출하여 단추의 텍스트를 설정합니다.

```
BOOL SetButtonText(
    int nIndex,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
텍스트를 설정할 단추의 인덱스입니다.

*lpszText*<br/>
단추에 설정할 텍스트를 가리킵니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  [CToolBar::GetToolBarCtrl에](#gettoolbarctrl)대한 예제를 참조하십시오.

## <a name="ctoolbarsetheight"></a><a name="setheight"></a>CToolBar::설정높이

이 멤버 함수는 *cyHeight*에 지정된 픽셀 단위로 도구 모음의 높이를 값으로 설정합니다.

```cpp
void SetHeight(int cyHeight);
```

### <a name="parameters"></a>매개 변수

*사이 높이*<br/>
도구 모음의 픽셀 높이입니다.

### <a name="remarks"></a>설명

[SetSizes를](#setsizes)호출한 후 이 멤버 함수를 사용하여 표준 도구 모음 높이를 재정의합니다. 높이가 너무 작으면 버튼이 아래쪽에 잘립니다.

이 함수가 호출되지 않으면 프레임워크는 단추 크기를 사용하여 도구 모음 높이를 결정합니다.

## <a name="ctoolbarsetsizes"></a><a name="setsizes"></a>CToolBar::설정 크기

이 멤버 함수를 호출하여 도구 모음단추를 *크기버튼으로*지정된 픽셀 크기로 설정합니다.

```cpp
void SetSizes(
    SIZE sizeButton,
    SIZE sizeImage);
```

### <a name="parameters"></a>매개 변수

*크기 버튼*<br/>
각 버튼의 픽셀 크기입니다.

*크기이미지*<br/>
각 이미지의 픽셀 크기입니다.

### <a name="remarks"></a>설명

*sizeImage* 매개 변수는 도구 모음의 비트맵에 있는 이미지의 크기(픽셀)를 포함해야 합니다. *크기 크기Button* 은 이미지에 너비가 7픽셀, 높이가 6픽셀이 더커지도록 충분해야 합니다. 이 기능은 또한 단추에 맞게 도구 모음 높이를 설정합니다.

단추 및 이미지 크기에 대한 소프트웨어 *디자인* 권장 사항에 대한 Windows 인터페이스 지침을 따르지 않는 도구 모음에 대해서만 이 멤버 함수를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC Sample DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 도크툴](../../overview/visual-cpp-samples.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C툴바크터터 클래스](../../mfc/reference/ctoolbarctrl-class.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)
