---
title: CReBarCtrl 클래스
ms.date: 11/19/2018
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
helpviewer_keywords:
- CReBarCtrl [MFC], CReBarCtrl
- CReBarCtrl [MFC], BeginDrag
- CReBarCtrl [MFC], Create
- CReBarCtrl [MFC], CreateEx
- CReBarCtrl [MFC], DeleteBand
- CReBarCtrl [MFC], DragMove
- CReBarCtrl [MFC], EndDrag
- CReBarCtrl [MFC], GetBandBorders
- CReBarCtrl [MFC], GetBandCount
- CReBarCtrl [MFC], GetBandInfo
- CReBarCtrl [MFC], GetBandMargins
- CReBarCtrl [MFC], GetBarHeight
- CReBarCtrl [MFC], GetBarInfo
- CReBarCtrl [MFC], GetBkColor
- CReBarCtrl [MFC], GetColorScheme
- CReBarCtrl [MFC], GetDropTarget
- CReBarCtrl [MFC], GetExtendedStyle
- CReBarCtrl [MFC], GetImageList
- CReBarCtrl [MFC], GetPalette
- CReBarCtrl [MFC], GetRect
- CReBarCtrl [MFC], GetRowCount
- CReBarCtrl [MFC], GetRowHeight
- CReBarCtrl [MFC], GetTextColor
- CReBarCtrl [MFC], GetToolTips
- CReBarCtrl [MFC], HitTest
- CReBarCtrl [MFC], IDToIndex
- CReBarCtrl [MFC], InsertBand
- CReBarCtrl [MFC], MaximizeBand
- CReBarCtrl [MFC], MinimizeBand
- CReBarCtrl [MFC], MoveBand
- CReBarCtrl [MFC], PushChevron
- CReBarCtrl [MFC], RestoreBand
- CReBarCtrl [MFC], SetBandInfo
- CReBarCtrl [MFC], SetBandWidth
- CReBarCtrl [MFC], SetBarInfo
- CReBarCtrl [MFC], SetBkColor
- CReBarCtrl [MFC], SetColorScheme
- CReBarCtrl [MFC], SetExtendedStyle
- CReBarCtrl [MFC], SetImageList
- CReBarCtrl [MFC], SetOwner
- CReBarCtrl [MFC], SetPalette
- CReBarCtrl [MFC], SetTextColor
- CReBarCtrl [MFC], SetToolTips
- CReBarCtrl [MFC], SetWindowTheme
- CReBarCtrl [MFC], ShowBand
- CReBarCtrl [MFC], SizeToRect
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
ms.openlocfilehash: 930322f1803eba7709505018c77ecea3f816dd15
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750639"
---
# <a name="crebarctrl-class"></a>CReBarCtrl 클래스

자식 창의 컨테이너인 rebar 컨트롤의 기능을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CReBarCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CReBarCtrl:::CReBarCtrl](#crebarctrl)|`CReBarCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CReBarCtrl::시작드래그](#begindrag)|보철근 컨트롤을 끌어서 놓기 모드로 배치합니다.|
|[CReBarCtrl::만들기](#create)|철근 컨트롤을 만들고 오브젝트에 `CReBarCtrl` 연결합니다.|
|[CReBarCtrl::만들기](#createex)|지정된 Windows 확장 스타일을 사용하여 철근 컨트롤을 만들고 `CReBarCtrl` 개체에 연결합니다.|
|[CReBarCtrl::D렐레테밴드](#deleteband)|철근 컨트롤에서 밴드를 삭제합니다.|
|[CReBarCtrl::D래그무브](#dragmove)|호출 후 철근 컨트롤의 드래그 위치를 `BeginDrag`업데이트합니다.|
|[CReBarCtrl::종료 드래그](#enddrag)|철근 컨트롤의 끌어서 놓기 작업을 종료합니다.|
|[CReBarCtrl::GetBandBorders](#getbandborders)|밴드의 테두리를 검색합니다.|
|[CReBarCtrl::GetBandCount](#getbandcount)|현재 철근 컨트롤에 있는 밴드 수를 검색합니다.|
|[CReBarCtrl::GetBandInfo](#getbandinfo)|철근 컨트롤에서 지정된 밴드에 대한 정보를 검색합니다.|
|[CReBarCtrl::GetBandMargins](#getbandmargins)|밴드의 여백을 검색합니다.|
|[CReBarCtrl::GetBarHeight](#getbarheight)|철근 컨트롤의 높이를 검색합니다.|
|[CReBarCtrl::GetBarInfo](#getbarinfo)|철근 컨트롤 및 사용 하는 이미지 목록에 대 한 정보를 검색합니다.|
|[CReBarCtrl::GetBkColor](#getbkcolor)|철근 컨트롤의 기본 배경색을 검색합니다.|
|[CReBarCtrl::겟컬러스킴](#getcolorscheme)|철근 컨트롤과 연결된 [COLORSCHEME](/windows/win32/api/commctrl/ns-commctrl-colorscheme) 구조를 검색합니다.|
|[CReBarCtrl:::GetDropTarget](#getdroptarget)|철근 컨트롤의 `IDropTarget` 인터페이스 포인터를 검색합니다.|
|[CReBarCtrl::GetExtended스타일](#getextendedstyle)|현재 철근 컨트롤의 확장된 스타일을 가져옵니다.|
|[CReBarCtrl::GetImageList](#getimagelist)|철근 컨트롤과 연결된 이미지 목록을 검색합니다.|
|[CReBarCtrl:::겟팔레트](#getpalette)|철근 컨트롤의 현재 팔레트를 검색합니다.|
|[CReBarCtrl::GetRect](#getrect)|철근 컨트롤에서 지정된 밴드의 경계 사각형을 검색합니다.|
|[CReBarCtrl::GetRowCount](#getrowcount)|철근 컨트롤에서 밴드 행 수를 검색합니다.|
|[CReBarCtrl::GetRowHeight높이](#getrowheight)|철근 컨트롤에서 지정된 행의 높이를 검색합니다.|
|[CReBarCtrl::GetTextColor](#gettextcolor)|철근 컨트롤의 기본 텍스트 색상을 검색합니다.|
|[CReBarCtrl::getToolTips](#gettooltips)|보철근 컨트롤과 연관된 모든 공구 팁 컨트롤로 핸들을 검색합니다.|
|[CReBarCtrl::히트 테스트](#hittest)|철근 밴드가 해당 지점에 있는 경우 화면에 지정된 지점에 있는 철근 밴드의 일부를 결정합니다.|
|[CReBarCtrl::IDToIndex](#idtoindex)|밴드 식별자(ID)를 철근 컨트롤의 밴드 인덱스로 변환합니다.|
|[CReBarCtrl::삽입 밴드](#insertband)|철근 컨트롤에 새 밴드를 삽입합니다.|
|[CReBarCtrl::최대밴드](#maximizeband)|철근 컨트롤의 밴드의 크기를 가장 큰 크기로 조정합니다.|
|[CReBarCtrl::최소화밴드](#minimizeband)|철근 컨트롤의 밴드의 크기를 가장 작은 크기로 조정합니다.|
|[CReBarCtrl:::무브밴드](#moveband)|밴드를 한 인덱스에서 다른 인덱스로 이동합니다.|
|[CReBarCtrl::PushChevron](#pushchevron)|프로그래밍 방식으로 갈매기를 밀어 넣습니다.|
|[CReBarCtrl::복원 밴드](#restoreband)|철근 컨트롤의 밴드의 크기를 이상적인 크기로 조정합니다.|
|[CReBarCtrl:::세트밴드정보](#setbandinfo)|철근 컨트롤에서 기존 밴드의 특성을 설정합니다.|
|[CReBarCtrl::세트밴드 폭](#setbandwidth)|현재 단조 막대 컨트롤에서 지정된 도킹 밴드의 폭을 설정합니다.|
|[CReBarCtrl:::세트바정보](#setbarinfo)|철근 컨트롤의 특성을 설정합니다.|
|[CReBarCtrl:::SetBkColor](#setbkcolor)|철근 컨트롤의 기본 배경색을 설정합니다.|
|[CReBarCtrl::세트컬러스킴](#setcolorscheme)|단고막대 컨트롤의 단추에 대한 색 구성표를 설정합니다.|
|[CReBarCtrl::세트확장스타일](#setextendedstyle)|현재 철근 컨트롤에 대한 확장 스타일을 설정합니다.|
|[CReBarCtrl::세트 이미지 리스트](#setimagelist)|철근 컨트롤의 이미지 목록을 설정합니다.|
|[CReBarCtrl:::세트 소유자](#setowner)|철근 컨트롤의 소유자 창을 설정합니다.|
|[CReBarCtrl:::세팔레트](#setpalette)|철근 컨트롤의 현재 팔레트를 설정합니다.|
|[CReBarCtrl::SetTextColor](#settextcolor)|철근 컨트롤의 기본 텍스트 색상을 설정합니다.|
|[CReBarCtrl::setToolTips](#settooltips)|공구 팁 컨트롤을 철근 컨트롤과 연결합니다.|
|[CReBarCtrl:::세트윈도우테임](#setwindowtheme)|철근 컨트롤의 시각적 스타일을 설정합니다.|
|[CReBarCtrl:::쇼밴드](#showband)|철근 컨트롤에서 지정된 밴드를 표시하거나 숨깁니다.|
|[CReBarCtrl::크기토렉트](#sizetorect)|철근 컨트롤을 지정된 사각형에 맞습니다.|

## <a name="remarks"></a>설명

철근 컨트롤이 상주하는 응용 프로그램은 철근 컨트롤에 포함된 하위 창을 철근 밴드에 할당합니다. 자식 창은 일반적으로 다른 일반적인 컨트롤입니다.

철근 컨트롤에는 하나 이상의 밴드가 포함되어 있습니다. 각 밴드에는 그리퍼 막대, 비트맵, 텍스트 레이블 및 하위 창이 조합되어 있습니다. 밴드는 이러한 각 항목 중 하나만 포함할 수 있습니다.

철근 컨트롤은 지정된 배경 비트맵 위에 자식 창을 표시할 수 있습니다. RBBS_FIXEDSIZE 스타일을 사용하는 밴드를 제외한 모든 철근 제어 대역의 크기를 조정할 수 있습니다. 철근 제어 밴드의 위치를 조정하거나 크기를 조정할 때 보철근 컨트롤은 해당 밴드에 할당된 자식 창의 크기와 위치를 관리합니다. 컨트롤 내에서 밴드의 크기를 조정하거나 변경하려면 밴드의 그리퍼 막대를 클릭하고 드래그합니다.

다음 그림에서는 세 개의 밴드가 있는 철근 컨트롤을 보여 주시면 됩니다.

- 밴드 0에는 평평하고 투명한 도구 모음 컨트롤이 포함되어 있습니다.

- 밴드 1에는 투명 표준 및 투명 드롭다운 버튼이 모두 포함되어 있습니다.

- 밴드 2에는 콤보 상자와 4개의 표준 버튼이 포함되어 있습니다.

   ![Rebar 메뉴의 예](../../mfc/reference/media/vc4scc1.gif "Rebar 메뉴의 예")

## <a name="rebar-control"></a>철근 제어

철근 컨트롤 지원:

- 이미지 목록입니다.

- 메시지 처리.

- 사용자 정의 그리기 기능.

- 표준 창 스타일 외에도 다양한 컨트롤 스타일입니다. 이러한 스타일 목록은 Windows SDK의 [철근 컨트롤 스타일을](/windows/win32/Controls/rebar-control-styles) 참조하십시오.

자세한 내용은 [CReBarCtrl 사용을](../../mfc/using-crebarctrl.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CReBarCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="crebarctrlbegindrag"></a><a name="begindrag"></a>CReBarCtrl::시작드래그

Windows SDK에 설명된 대로 RB_BEGINDRAG Win32 [메시지의](/windows/win32/Controls/rb-begindrag)동작을 구현합니다.

```cpp
void BeginDrag(
    UINT uBand,
    DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
끌어서 놓기 작업이 영향을 주는 밴드의 0기반 인덱스입니다.

*dwPos*<br/>
시작 마우스 좌표를 포함하는 DWORD 값입니다. 가로 좌표는 LOWORD에 포함되고 수직 좌표는 HIWORD에 포함됩니다. DWORD(DWORD)-1을 통과하면 철근 컨트롤은 컨트롤의 스레드가 마지막으로 호출될 `GetMessage` 때 `PeekMessage`마우스의 위치를 사용합니다.

## <a name="crebarctrlcreate"></a><a name="create"></a>CReBarCtrl::만들기

철근 컨트롤을 만들고 오브젝트에 `CReBarCtrl` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
컨트롤에 적용된 철근 컨트롤 스타일 조합을 지정합니다. 지원되는 스타일 목록은 Windows SDK의 [철근 제어 스타일을](/windows/win32/Controls/rebar-control-styles) 참조하십시오.

*rect*<br/>
철근 컨트롤의 위치와 크기인 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*pParentWnd*<br/>
철근 컨트롤의 상위 창인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터입니다. NULL이 아니어야 합니다.

*nID*<br/>
철근 컨트롤의 제어 ID를 지정합니다.

### <a name="return-value"></a>Return Value

개체가 성공적으로 생성된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

철근 컨트롤을 두 단계로 만듭니다.

1. [CReBarCtrl을](#crebarctrl) 호출하여 `CReBarCtrl` 개체를 생성합니다.

1. Windows 철근 컨트롤을 만들고 개체에 연결 하는 이 `CReBarCtrl` 멤버 함수를 호출 합니다.

호출하면 `Create`공통 컨트롤이 초기화됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]

## <a name="crebarctrlcreateex"></a><a name="createex"></a>CReBarCtrl::만들기

컨트롤(하위 창)을 만들고 `CReBarCtrl` 개체와 연결합니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
생성되는 컨트롤의 확장 스타일을 지정합니다. 확장 된 Windows 스타일 목록은 Windows SDK에서 [CreateWindowEx에](/windows/win32/api/winuser/nf-winuser-createwindowexw) 대한 *dwExStyle* 매개 변수를 참조하십시오.

*dwStyle*<br/>
컨트롤에 적용된 철근 컨트롤 스타일 조합을 지정합니다. 지원되는 스타일 목록은 Windows SDK의 [철근 컨트롤 스타일을](/windows/win32/Controls/rebar-control-styles) 참조하십시오.

*rect*<br/>
*pParentWnd의*클라이언트 좌표에서 생성할 창의 크기와 위치를 설명하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*pParentWnd*<br/>
컨트롤의 부모인 창에 대한 포인터입니다.

*nID*<br/>
컨트롤의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

만들기 `CreateEx` 대신 [Create](#create) Windows 확장 스타일 **서문 WS_EX_** 지정된 확장 된 Windows 스타일을 적용합니다.

## <a name="crebarctrlcrebarctrl"></a><a name="crebarctrl"></a>CReBarCtrl:::CReBarCtrl

`CReBarCtrl` 개체를 만듭니다.

```
CReBarCtrl();
```

### <a name="example"></a>예제

  [CReBarCtrl::Create에](#create)대한 예제를 참조하십시오.

## <a name="crebarctrldeleteband"></a><a name="deleteband"></a>CReBarCtrl::D렐레테밴드

Windows SDK에 설명된 대로 RB_DELETEBAND Win32 [메시지의](/windows/win32/Controls/rb-deleteband)동작을 구현합니다.

```
BOOL DeleteBand(UINT uBand);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
삭제할 밴드의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

밴드가 성공적으로 삭제된 경우 비영; 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]

## <a name="crebarctrldragmove"></a><a name="dragmove"></a>CReBarCtrl::D래그무브

Windows SDK에 설명된 대로 RB_DRAGMOVE Win32 [메시지의](/windows/win32/Controls/rb-dragmove)동작을 구현합니다.

```cpp
void DragMove(DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>매개 변수

*dwPos*<br/>
새 마우스 좌표를 포함하는 DWORD 값입니다. 가로 좌표는 LOWORD에 포함되고 수직 좌표는 HIWORD에 포함됩니다. DWORD(DWORD)-1을 통과하면 철근 컨트롤은 컨트롤의 스레드가 마지막으로 호출될 `GetMessage` 때 `PeekMessage`마우스의 위치를 사용합니다.

## <a name="crebarctrlenddrag"></a><a name="enddrag"></a>CReBarCtrl::종료 드래그

Windows SDK에 설명된 대로 [RB_ENDDRAG](/windows/win32/Controls/rb-enddrag)Win32 메시지의 동작을 구현합니다.

```cpp
void EndDrag();
```

## <a name="crebarctrlgetbandborders"></a><a name="getbandborders"></a>CReBarCtrl::GetBandBorders

Windows SDK에 설명된 대로 RB_GETBANDBORDERS Win32 [메시지의](/windows/win32/Controls/rb-getbandborders)동작을 구현합니다.

```cpp
void GetBandBorders(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
테두리가 검색되는 밴드의 0기반 인덱스입니다.

*Prc*<br/>
밴드 테두리를 수신하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 포인터입니다. 철근 컨트롤에 RBS_BANDBORDERS 스타일이 있는 경우 이 구조의 각 멤버는 경계를 구성하는 밴드의 해당 측면에 픽셀 수를 받게 됩니다. 단고수 바 컨트롤에 RBS_BANDBORDERS 스타일이 없는 경우 이 구조체의 왼쪽 멤버만 유효한 정보를 받습니다. 철근 컨트롤 스타일에 대한 설명은 Windows SDK의 [철근 컨트롤 스타일을](/windows/win32/Controls/rebar-control-styles) 참조하십시오.

## <a name="crebarctrlgetbandcount"></a><a name="getbandcount"></a>CReBarCtrl::GetBandCount

Windows SDK에 설명된 대로 RB_GETBANDCOUNT Win32 [메시지의](/windows/win32/Controls/rb-getbandcount)동작을 구현합니다.

```
UINT GetBandCount() const;
```

### <a name="return-value"></a>Return Value

컨트롤에 할당된 밴드 수입니다.

## <a name="crebarctrlgetbandinfo"></a><a name="getbandinfo"></a>CReBarCtrl::GetBandInfo

Windows SDK에 설명된 [대로](/windows/win32/Controls/rb-getbandinfo) RB_GETBANDINFO Win32 메시지의 동작을 구현합니다.

```
BOOL GetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi) const;
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
정보를 검색할 밴드의 0기반 인덱스입니다.

*prbbi*<br/>
밴드 정보를 수신하는 [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) 구조에 대한 포인터입니다. 이 메시지를 `cbSize` 보내기 전에 이 `sizeof(REBARBANDINFO)` 구조의 `fMask` 멤버를 설정하고 검색할 항목으로 멤버를 설정해야 합니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

## <a name="crebarctrlgetbandmargins"></a><a name="getbandmargins"></a>CReBarCtrl::GetBandMargins

밴드의 여백을 검색합니다.

```cpp
void GetBandMargins(PMARGINS pMargins);
```

### <a name="parameters"></a>매개 변수

*마진*<br/>
정보를 수신하는 [MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins)구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [RB_GETBANDMARGINS](/windows/win32/Controls/rb-getbandmargins) 메시지의 기능을 에뮬레이트합니다.

## <a name="crebarctrlgetbarheight"></a><a name="getbarheight"></a>CReBarCtrl::GetBarHeight

철근 막대의 높이를 검색합니다.

```
UINT GetBarHeight() const;
```

### <a name="return-value"></a>Return Value

컨트롤의 높이(픽셀 단위)를 나타내는 값입니다.

## <a name="crebarctrlgetbarinfo"></a><a name="getbarinfo"></a>CReBarCtrl::GetBarInfo

Windows SDK에 설명된 대로 RB_GETBARINFO Win32 [메시지의](/windows/win32/Controls/rb-getbarinfo)동작을 구현합니다.

```
BOOL GetBarInfo(REBARINFO* prbi) const;
```

### <a name="parameters"></a>매개 변수

*prbi*<br/>
철근 제어 정보를 수신하는 [REBARINFO](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) 구조에 대한 포인터입니다. 이 메시지를 보내기 전에 이 구조의 *cbSize* 멤버를 `sizeof(REBARINFO)` 설정해야 합니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

## <a name="crebarctrlgetbkcolor"></a><a name="getbkcolor"></a>CReBarCtrl::GetBkColor

Windows SDK에 설명된 대로 RB_GETBKCOLOR Win32 [메시지의](/windows/win32/Controls/rb-getbkcolor)동작을 구현합니다.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Return Value

현재 기본 배경색을 나타내는 COLORREF 값입니다.

## <a name="crebarctrlgetcolorscheme"></a><a name="getcolorscheme"></a>CReBarCtrl::겟컬러스킴

철근 컨트롤에 대한 [COLORSCHEME](/windows/win32/api/commctrl/ns-commctrl-colorscheme) 구조를 검색합니다.

```
BOOL GetColorScheme(COLORSCHEME* lpcs);
```

### <a name="parameters"></a>매개 변수

*lpcs*<br/>
Windows SDK에 설명된 대로 [COLORSCHEME](/windows/win32/api/commctrl/ns-commctrl-colorscheme) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

구조에는 `COLORSCHEME` 버튼 강조 표시 색상과 단추 그림자 색상이 포함됩니다.

## <a name="crebarctrlgetdroptarget"></a><a name="getdroptarget"></a>CReBarCtrl:::GetDropTarget

Windows SDK에 설명된 대로 [RB_GETDROPTARGET](/windows/win32/Controls/rb-getdroptarget)Win32 메시지의 동작을 구현합니다.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Return Value

IDropTarget 인터페이스에 대한 [포인터입니다.](/windows/win32/api/oleidl/nn-oleidl-idroptarget)

## <a name="crebarctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CReBarCtrl::GetExtended스타일

현재 철근 컨트롤의 확장된 스타일을 가져옵니다.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Return Value

확장 된 스타일을 나타내는 플래그의 비트 조합 (OR). 가능한 플래그는 RBS_EX_SPLITTER RBS_EX_TRANSPARENT. 자세한 내용은 [CReBarCtrl::SetExtendedStyle](#setextendedstyle) 메서드의 *dwMask* 매개 변수를 참조하십시오.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [RB_GETEXTENDEDSTYLE](/windows/win32/Controls/rb-dragmove) 메시지를 보냅니다.

## <a name="crebarctrlgetimagelist"></a><a name="getimagelist"></a>CReBarCtrl::GetImageList

철근 `CImageList` 컨트롤과 연결된 개체를 가져옵니다.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Return Value

[CImageList](../../mfc/reference/cimagelist-class.md) 개체에 대한 포인터입니다. 컨트롤에 대해 설정된 이미지 목록이 없는 경우 NULL을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [REBARINFO](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) 구조에 저장된 크기 및 마스크 정보를 사용합니다.

## <a name="crebarctrlgetpalette"></a><a name="getpalette"></a>CReBarCtrl:::겟팔레트

철근 컨트롤의 현재 팔레트를 검색합니다.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Return Value

철근 컨트롤의 현재 팔레트를 지정하는 [CPalette](../../mfc/reference/cpalette-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 `CPalette` 개체를 HPALETTE가 아닌 반환 값으로 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]

## <a name="crebarctrlgetrect"></a><a name="getrect"></a>CReBarCtrl::GetRect

Windows SDK에 설명된 대로 RB_GETRECT Win32 [메시지의](/windows/win32/Controls/rb-getrect)동작을 구현합니다.

```
BOOL GetRect(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
철근 컨트롤에서 밴드의 제로 기반 인덱스입니다.

*Prc*<br/>
철근 밴드의 경계를 수신하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]

## <a name="crebarctrlgetrowcount"></a><a name="getrowcount"></a>CReBarCtrl::GetRowCount

Windows SDK에 설명된 대로 RB_GETROWCOUNT Win32 [메시지의](/windows/win32/Controls/rb-getrowcount)동작을 구현합니다.

```
UINT GetRowCount() const;
```

### <a name="return-value"></a>Return Value

컨트롤의 대역 행 수를 나타내는 UINT 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]

## <a name="crebarctrlgetrowheight"></a><a name="getrowheight"></a>CReBarCtrl::GetRowHeight높이

Windows SDK에 설명된 대로 RB_GETROWHEIGHT Win32 [메시지의](/windows/win32/Controls/rb-getrowheight)동작을 구현합니다.

```
UINT GetRowHeight(UINT uRow) const;
```

### <a name="parameters"></a>매개 변수

*uRow*<br/>
높이를 검색할 밴드의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

행 높이를 픽셀 단위로 나타내는 UINT 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]

## <a name="crebarctrlgettextcolor"></a><a name="gettextcolor"></a>CReBarCtrl::GetTextColor

Windows SDK에 설명된 대로 RB_GETTEXTCOLOR Win32 [메시지의](/windows/win32/Controls/rb-gettextcolor)동작을 구현합니다.

```
COLORREF GetTextColor() const;
```

### <a name="return-value"></a>Return Value

현재 기본 텍스트 색상을 나타내는 COLORREF 값입니다.

## <a name="crebarctrlgettooltips"></a><a name="gettooltips"></a>CReBarCtrl::getToolTips

Windows SDK에 설명된 대로 RB_GETTOOLTIPS Win32 [메시지의](/windows/win32/Controls/rb-gettooltips)동작을 구현합니다.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Return Value

[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

MFC 구현은 HWND가 `GetToolTips` 아닌 `CToolTipCtrl`에 대한 포인터를 반환합니다.

## <a name="crebarctrlhittest"></a><a name="hittest"></a>CReBarCtrl::히트 테스트

Windows SDK에 설명된 대로 RB_HITTEST Win32 [메시지의](/windows/win32/Controls/rb-hittest)동작을 구현합니다.

```
int HitTest(RBHITTESTINFO* prbht);
```

### <a name="parameters"></a>매개 변수

*prbht*<br/>
[RBHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-rbhittestinfo) 구조에 대한 포인터입니다. 메시지를 보내기 전에 `pt` 이 구조의 멤버를 클라이언트 좌표에서 테스트할 지점으로 초기화해야 합니다.

### <a name="return-value"></a>Return Value

지정된 지점에서 밴드의 0기반 인덱스 또는 -1이 없는 경우 리브 타선 밴드가 지점에 있지 않은 경우.

## <a name="crebarctrlidtoindex"></a><a name="idtoindex"></a>CReBarCtrl::IDToIndex

Windows SDK에 설명된 대로 RB_IDTOINDEX Win32 [메시지의](/windows/win32/controls/rb-idtoindex)동작을 구현합니다.

```
int IDToIndex(UINT uBandID) const;
```

### <a name="parameters"></a>매개 변수

*uBandID*<br/>
밴드가 삽입될 때 `wID` [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) 구조의 멤버에 전달된 지정된 밴드의 응용 프로그램 정의 식별자입니다.

### <a name="return-value"></a>Return Value

성공하면 0기반 밴드 인덱스 또는 -1이 그렇지 않으면 중복 밴드 인덱스가 있으면 첫 번째 인덱스가 반환됩니다.

## <a name="crebarctrlinsertband"></a><a name="insertband"></a>CReBarCtrl::삽입 밴드

Windows SDK에 설명된 대로 RB_INSERTBAND Win32 [메시지의](/windows/win32/Controls/rb-insertband)동작을 구현합니다.

```
BOOL InsertBand(
    UINT uIndex,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>매개 변수

*u인덱스*<br/>
밴드가 삽입될 위치의 0기반 인덱스입니다. 이 매개변수를 -1로 설정하면 컨트롤이 마지막 위치에 새 밴드를 추가합니다.

*prbbi*<br/>
삽입할 밴드를 정의하는 [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) 구조에 대한 포인터입니다. 이 함수를 호출하기 전에 이 `sizeof(REBARBANDINFO)` 구조의 *cbSize* 멤버를 설정해야 합니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]

## <a name="crebarctrlmaximizeband"></a><a name="maximizeband"></a>CReBarCtrl::최대밴드

철근 컨트롤의 밴드의 크기를 가장 큰 크기로 조정합니다.

```cpp
void MaximizeBand(UINT uBand);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
밴드의 제로 기반 인덱스는 최대화될 것이다.

### <a name="remarks"></a>설명

Windows SDK에 설명된 [RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband) 대로 `fIdeal` 0으로 설정된 RB_MAXIMIZEBAND Win32 메시지의 동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]

## <a name="crebarctrlminimizeband"></a><a name="minimizeband"></a>CReBarCtrl::최소화밴드

철근 컨트롤의 밴드의 크기를 가장 작은 크기로 조정합니다.

```cpp
void MinimizeBand(UINT uBand);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
최소화할 밴드의 제로 기반 인덱스.

### <a name="remarks"></a>설명

Windows SDK에 설명된 대로 RB_MINIMIZEBAND Win32 [메시지의](/windows/win32/Controls/rb-minimizeband)동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]

## <a name="crebarctrlmoveband"></a><a name="moveband"></a>CReBarCtrl:::무브밴드

Windows SDK에 설명된 대로 [RB_MOVEBAND](/windows/win32/Controls/rb-moveband)Win32 메시지의 동작을 구현합니다.

```
BOOL MoveBand(
    UINT uFrom,
    UINT uTo);
```

### <a name="parameters"></a>매개 변수

*uFrom*<br/>
이동할 밴드의 0기반 인덱스입니다.

*uTo*<br/>
새 밴드 위치의 제로 기반 인덱스입니다. 이 매개 변수 값은 대역 수를 뺀 값보다 커서는 안 됩니다. 밴드 수를 얻으려면 [GetBandCount](#getbandcount)를 호출하십시오.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

## <a name="crebarctrlpushchevron"></a><a name="pushchevron"></a>CReBarCtrl::PushChevron

Windows SDK에 설명된 대로 RB_PUSHCHEVRON Win32 [메시지의](/windows/win32/Controls/rb-pushchevron)동작을 구현합니다.

```cpp
void PushChevron(
    UINT uBand,
    LPARAM lAppValue);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
그 갈매기가 밀려될 밴드의 제로 기반 인덱스.

*lApp값*<br/>
응용 프로그램이 32비트 값을 정의했습니다. windows SDK에서 [RB_PUSHCHEVRON](/windows/win32/Controls/rb-pushchevron) *lAppValue를* 참조하십시오.

## <a name="crebarctrlrestoreband"></a><a name="restoreband"></a>CReBarCtrl::복원 밴드

철근 컨트롤의 밴드의 크기를 이상적인 크기로 조정합니다.

```cpp
void RestoreBand(UINT uBand);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
밴드의 제로 기반 인덱스는 최대화될 것이다.

### <a name="remarks"></a>설명

Windows SDK에 설명된 [RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband) 대로 `fIdeal` 1로 설정된 RB_MAXIMIZEBAND Win32 메시지의 동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]

## <a name="crebarctrlsetbandinfo"></a><a name="setbandinfo"></a>CReBarCtrl:::세트밴드정보

Windows SDK에 설명된 대로 RB_SETBANDINFO Win32 [메시지의](/windows/win32/Controls/rb-setbandinfo)동작을 구현합니다.

```
BOOL SetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
밴드의 제로 기반 인덱스를 사용하여 새 설정을 수신합니다.

*prbbi*<br/>
삽입할 밴드를 정의하는 [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) 구조에 대한 포인터입니다. 이 메시지를 `cbSize` 보내기 전에 이 `sizeof(REBARBANDINFO)` 구조의 멤버를 설정해야 합니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]

## <a name="crebarctrlsetbandwidth"></a><a name="setbandwidth"></a>CReBarCtrl::세트밴드 폭

현재 단조 막대 컨트롤에서 지정된 도킹 밴드의 폭을 설정합니다.

```
BOOL SetBandWidth(
    UINT uBand,
    int cxWidth);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*uBand*|【인】 철근 밴드의 제로 기반 인덱스입니다.|
|*cxWidth*|【인】 보철근 밴드의 새 너비(픽셀 단위)입니다.|

### <a name="return-value"></a>Return Value

TRUE 메서드가 성공하면 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [RB_SETBANDWIDTH](/windows/win32/Controls/rb-setbandwidth) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 현재 `m_rebar`철근 컨트롤에 액세스하는 데 사용되는 변수 를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]

### <a name="example"></a>예제

다음 코드 예제는 각 철근 밴드를 동일한 너비로 설정합니다.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]

## <a name="crebarctrlsetbarinfo"></a><a name="setbarinfo"></a>CReBarCtrl:::세트바정보

Windows SDK에 설명된 대로 RB_SETBARINFO Win32 [메시지의](/windows/win32/Controls/rb-setbarinfo)동작을 구현합니다.

```
BOOL SetBarInfo(REBARINFO* prbi);
```

### <a name="parameters"></a>매개 변수

*prbi*<br/>
설정할 정보가 포함된 [REBARINFO](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) 구조에 대한 포인터입니다. 이 메시지를 `cbSize` 보내기 전에 이 `sizeof(REBARINFO)` 구조의 멤버를 설정해야 합니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]

## <a name="crebarctrlsetbkcolor"></a><a name="setbkcolor"></a>CReBarCtrl:::SetBkColor

Windows SDK에 설명된 대로 RB_SETBKCOLOR Win32 [메시지의](/windows/win32/Controls/rb-setbkcolor)동작을 구현합니다.

```
COLORREF SetBkColor(COLORREF clr);
```

### <a name="parameters"></a>매개 변수

*Clr*<br/>
새 기본 배경색을 나타내는 COLORREF 값입니다.

### <a name="return-value"></a>Return Value

이전 기본 배경색을 나타내는 [COLORREF](/windows/win32/gdi/colorref) 값입니다.

### <a name="remarks"></a>설명

배경색을 설정하는 시기와 기본값을 설정하는 방법에 대한 자세한 내용은 이 항목을 참조하십시오.

## <a name="crebarctrlsetcolorscheme"></a><a name="setcolorscheme"></a>CReBarCtrl::세트컬러스킴

단고막대 컨트롤의 단추에 대한 색 구성표를 설정합니다.

```cpp
void SetColorScheme(const COLORSCHEME* lpcs);
```

### <a name="parameters"></a>매개 변수

*lpcs*<br/>
Windows SDK에 설명된 대로 [COLORSCHEME](/windows/win32/api/commctrl/ns-commctrl-colorscheme) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

구조에는 `COLORSCHEME` 버튼 강조 표시 색상과 단추 그림자 색상이 모두 포함됩니다.

## <a name="crebarctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CReBarCtrl::세트확장스타일

현재 철근 컨트롤에 대한 확장 스타일을 설정합니다.

```
DWORD SetExtendedStyle(
    DWORD dwMask,
    DWORD dwStyleEx);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*dwMask*|【인】 *dwStyleEx* 매개 변수에 적용할 플래그를 지정하는 플래그의 비트 조합(OR)입니다. 다음 값 중 하나 이상을 사용합니다.<br /><br /> RBS_EX_SPLITTER: 기본적으로 가로 모드의 하단과 오른쪽수직 모드의 스플리터를 표시합니다.<br /><br /> RBS_EX_TRANSPARENT: [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd) 메시지를 부모 창으로 전달합니다.|
|*dwStyleEx*|【인】 적용할 스타일을 지정하는 플래그의 비트 조합(OR)입니다. 스타일을 설정하려면 *dwMask* 매개 변수에 사용되는 것과 동일한 플래그를 지정합니다. 스타일을 재설정하려면 이진 0을 지정합니다.|

### <a name="return-value"></a>Return Value

이전 확장 스타일입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [RB_SETEXTENDEDSTYLE](/windows/win32/Controls/rb-setextendedstyle) 메시지를 보냅니다.

## <a name="crebarctrlsetimagelist"></a><a name="setimagelist"></a>CReBarCtrl::세트 이미지 리스트

이미지 목록을 철근 컨트롤에 할당합니다.

```
BOOL SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>매개 변수

*pImageList*<br/>
철근 컨트롤에 할당할 이미지 목록을 포함하는 [CImageList](../../mfc/reference/cimagelist-class.md) 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

## <a name="crebarctrlsetowner"></a><a name="setowner"></a>CReBarCtrl:::세트 소유자

Windows SDK에 설명된 대로 RB_SETPARENT Win32 [메시지의](/windows/win32/Controls/rb-setparent)동작을 구현합니다.

```
CWnd* SetOwner(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
철근 컨트롤의 소유자로 설정할 `CWnd` 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

철근 컨트롤의 현재 소유자인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 창에 `CWnd` 대한 핸들이 아니라 현재 및 선택된 철근 컨트롤 소유자모두에 대한 개체에 대한 포인터를 사용합니다.

> [!NOTE]
> 이 멤버 함수는 컨트롤을 만들 때 설정된 실제 부모를 변경하지 않습니다. 대신 지정한 창으로 알림 메시지를 보냅니다.

## <a name="crebarctrlsetpalette"></a><a name="setpalette"></a>CReBarCtrl:::세팔레트

Windows SDK에 설명된 대로 RB_SETPALETTE Win32 [메시지의](/windows/win32/Controls/rb-setpalette)동작을 구현합니다.

```
CPalette* SetPalette(HPALETTE hPal);
```

### <a name="parameters"></a>매개 변수

*hPal*<br/>
철근 컨트롤에서 사용할 새 팔레트를 지정하는 HPALETTE입니다.

### <a name="return-value"></a>Return Value

철근 컨트롤의 이전 팔레트를 지정하는 [CPalette](../../mfc/reference/cpalette-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 `CPalette` 개체를 HPALETTE가 아닌 반환 값으로 사용합니다.

## <a name="crebarctrlsettextcolor"></a><a name="settextcolor"></a>CReBarCtrl::SetTextColor

Windows SDK에 설명된 대로 [RB_SETTEXTCOLOR](/windows/win32/Controls/rb-settextcolor)Win32 메시지의 동작을 구현합니다.

```
COLORREF SetTextColor(COLORREF clr);
```

### <a name="parameters"></a>매개 변수

*Clr*<br/>
개체의 새 텍스트 색상을 나타내는 COLORREF 값입니다. `CReBarCtrl`

### <a name="return-value"></a>Return Value

개체와 연결된 이전 텍스트 색상을 나타내는 `CReBarCtrl` [COLORREF](/windows/win32/gdi/colorref) 값입니다.

### <a name="remarks"></a>설명

철근 컨트롤에서 텍스트 색상 유연성을 지원 하기 위해 제공 됩니다.

## <a name="crebarctrlsettooltips"></a><a name="settooltips"></a>CReBarCtrl::setToolTips

공구 팁 컨트롤을 철근 컨트롤과 연결합니다.

```cpp
void SetToolTips(CToolTipCtrl* pToolTip);
```

### <a name="parameters"></a>매개 변수

*pTool팁*<br/>
[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 개체에 대한 포인터

### <a name="remarks"></a>설명

작업이 완료되면 `CToolTipCtrl` 개체를 삭제해야 합니다.

## <a name="crebarctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CReBarCtrl:::세트윈도우테임

철근 컨트롤의 시각적 스타일을 설정합니다.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>매개 변수

*pszSubAppName*<br/>
설정할 철근 시각적 스타일을 포함하는 유니코드 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

반환 값은 사용되지 않습니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [RB_SETWINDOWTHEME](/windows/win32/Controls/rb-setwindowtheme) 메시지의 기능을 에뮬레이트합니다.

## <a name="crebarctrlshowband"></a><a name="showband"></a>CReBarCtrl:::쇼밴드

Windows SDK에 설명된 대로 [RB_SHOWBAND](/windows/win32/Controls/rb-showband)Win32 메시지의 동작을 구현합니다.

```
BOOL ShowBand(
    UINT uBand,
    BOOL fShow = TRUE);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
철근 컨트롤에서 밴드의 제로 기반 인덱스입니다.

*fShow*<br/>
밴드를 표시하거나 숨춰야 하는지 를 나타냅니다. 이 값이 TRUE이면 밴드가 표시됩니다. 그렇지 않으면 밴드가 숨김이 있습니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

## <a name="crebarctrlsizetorect"></a><a name="sizetorect"></a>CReBarCtrl::크기토렉트

Windows SDK에 설명된 대로 RB_SIZETORECT Win32 [메시지의](/windows/win32/Controls/rb-sizetorect)동작을 구현합니다.

```
BOOL SizeToRect(CRect& rect);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
철근 컨트롤의 크기를 조정해야 하는 사각형을 지정하는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 `CRect` `RECT` 객체를 구조체가 아닌 매개 변수로 사용합니다.

## <a name="see-also"></a>참조

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
