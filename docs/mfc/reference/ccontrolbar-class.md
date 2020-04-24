---
title: CControlBar Class
ms.date: 11/04/2016
f1_keywords:
- CControlBar
- AFXEXT/CControlBar
- AFXEXT/CControlBar::CControlBar
- AFXEXT/CControlBar::CalcDynamicLayout
- AFXEXT/CControlBar::CalcFixedLayout
- AFXEXT/CControlBar::CalcInsideRect
- AFXEXT/CControlBar::DoPaint
- AFXEXT/CControlBar::DrawBorders
- AFXEXT/CControlBar::DrawGripper
- AFXEXT/CControlBar::EnableDocking
- AFXEXT/CControlBar::GetBarStyle
- AFXEXT/CControlBar::GetBorders
- AFXEXT/CControlBar::GetCount
- AFXEXT/CControlBar::GetDockingFrame
- AFXEXT/CControlBar::IsFloating
- AFXEXT/CControlBar::OnUpdateCmdUI
- AFXEXT/CControlBar::SetBarStyle
- AFXEXT/CControlBar::SetBorders
- AFXEXT/CControlBar::SetInPlaceOwner
- AFXEXT/CControlBar::m_bAutoDelete
- AFXEXT/CControlBar::m_pInPlaceOwner
helpviewer_keywords:
- CControlBar [MFC], CControlBar
- CControlBar [MFC], CalcDynamicLayout
- CControlBar [MFC], CalcFixedLayout
- CControlBar [MFC], CalcInsideRect
- CControlBar [MFC], DoPaint
- CControlBar [MFC], DrawBorders
- CControlBar [MFC], DrawGripper
- CControlBar [MFC], EnableDocking
- CControlBar [MFC], GetBarStyle
- CControlBar [MFC], GetBorders
- CControlBar [MFC], GetCount
- CControlBar [MFC], GetDockingFrame
- CControlBar [MFC], IsFloating
- CControlBar [MFC], OnUpdateCmdUI
- CControlBar [MFC], SetBarStyle
- CControlBar [MFC], SetBorders
- CControlBar [MFC], SetInPlaceOwner
- CControlBar [MFC], m_bAutoDelete
- CControlBar [MFC], m_pInPlaceOwner
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
ms.openlocfilehash: c2f8ea48bf9a1f015928650085b07198b152771a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754794"
---
# <a name="ccontrolbar-class"></a>CControlBar Class

컨트롤 바 [클래스CStatusBar,](../../mfc/reference/cstatusbar-class.md) [CToolBar,](../../mfc/reference/ctoolbar-class.md) [CDialogBar,](../../mfc/reference/cdialogbar-class.md) [CReBar](../../mfc/reference/crebar-class.md)및 [COleResizeBar의](../../mfc/reference/coleresizebar-class.md)기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CControlBar : public CWnd
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CControlBar:::CControlBar](#ccontrolbar)|`CControlBar` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C컨트롤바::석회화레이아웃](#calcdynamiclayout)|동적 컨트롤 막대의 크기를 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체로 반환합니다.|
|[C컨트롤바::석회화레이아웃](#calcfixedlayout)|컨트롤 막대의 크기를 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체로 반환합니다.|
|[CControlBar:::칼크인사이드렉트](#calcinsiderect)|컨트롤 막대 영역의 현재 치수를 반환합니다. 테두리를 포함합니다.|
|[CControlBar: :D오페인트](#dopaint)|컨트롤 막대의 테두리와 그리퍼를 렌더링합니다.|
|[CControlBar::D원시보더스](#drawborders)|컨트롤 막대의 테두리를 렌더링합니다.|
|[CControlBar::D로그리퍼](#drawgripper)|컨트롤 막대의 그리퍼를 렌더링합니다.|
|[CControlBar::사용 도킹](#enabledocking)|컨트롤 막대를 도킹하거나 부동할 수 있습니다.|
|[CControlBar::겟바스타일](#getbarstyle)|컨트롤 막대 스타일 설정을 검색합니다.|
|[CControlBar:::GetBorders](#getborders)|컨트롤 막대의 테두리 값을 검색합니다.|
|[CControlBar::GetCount](#getcount)|컨트롤 막대에서 비 HWND 요소의 수를 반환합니다.|
|[CControlBar::GetDockingFrame](#getdockingframe)|컨트롤 막대가 도킹된 프레임에 대한 포인터를 반환합니다.|
|[CControlBar::떠있는](#isfloating)|문제의 컨트롤 막대가 부동 컨트롤 모음인 경우 zero가 아닌 값을 반환합니다.|
|[CControlBar::에업데이트CmdUI](#onupdatecmdui)|명령 UI 처리기를 호출합니다.|
|[CControlBar::SetBar스타일](#setbarstyle)|컨트롤 막대 스타일 설정을 수정합니다.|
|[C컨트롤바:::설정 테두리](#setborders)|컨트롤 막대의 테두리 값을 설정합니다.|
|[CControlBar::SetInPlace 소유자](#setinplaceowner)|컨트롤 막대의 소유자를 변경합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CControlBar::m_bAutoDelete](#m_bautodelete)|0이 아닌 `CControlBar` 경우 Windows 컨트롤 막대가 소멸되면 개체가 삭제됩니다.|
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|컨트롤 막대의 소유자입니다.|

## <a name="remarks"></a>설명

컨트롤 막대는 일반적으로 프레임 창의 왼쪽 또는 오른쪽에 정렬되는 창입니다. 여기에는 Windows 메시지를 생성하고 응답하는 창인 HWND 기반 컨트롤인 자식 항목또는 창이 아니며 응용 프로그램 코드 또는 프레임워크 코드에서 관리하는 HWND 기반 항목이 포함될 수 있습니다. 목록 상자 및 편집 컨트롤은 HWND 기반 컨트롤의 예입니다. 상태 표시줄 창과 비트맵 단추는 HWND 기반이 아닌 컨트롤의 예입니다.

컨트롤-막대 창은 일반적으로 상위 프레임 창의 하위 창이며 일반적으로 프레임 창의 클라이언트 보기 또는 MDI 클라이언트에 대한 형제입니다. 개체는 `CControlBar` 부모 창의 클라이언트 사각형에 대한 정보를 사용하여 자체 위치를 지정합니다. 그런 다음 부모 창의 클라이언트 영역에 할당되지 않은 공간의 양을 부모 창에 알립니다.

에 대한 `CControlBar`자세한 내용은 다음을 참조하십시오.

- [컨트롤 막대](../../mfc/control-bars.md)

- [기술 참고 31: 컨트롤 바.](../../mfc/tn031-control-bars.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CControlBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="ccontrolbarcalcdynamiclayout"></a><a name="calcdynamiclayout"></a>C컨트롤바::석회화레이아웃

프레임워크는 동적 도구 모음의 차원을 계산하기 위해 이 멤버 함수를 호출합니다.

```
virtual CSize CalcDynamicLayout(
    int nLength,
    DWORD nMode);
```

### <a name="parameters"></a>매개 변수

*nLength*<br/>
*dwMode에*따라 컨트롤 막대의 요청된 치수(수평 또는 수직).

*nMode*<br/>
다음과 같은 미리 정의된 플래그는 동적 컨트롤 막대의 높이와 너비를 결정하는 데 사용됩니다. 비트와이즈 OR(&#124;) 연산자를 사용하여 플래그를 결합합니다.

|레이아웃 모드 플래그|의미|
|-----------------------|-------------------|
|LM_STRETCH|컨트롤 막대를 프레임 크기로 늘려야 하는지 여부를 나타냅니다. 막대가 도킹 바가 아닌 경우 설정합니다(도킹에는 사용할 수 없음). 막대가 도킹되거나 부동(도킹 가능)에는 설정되지 않습니다. 설정하면 LM_STRETCH *nLength를* 무시하고 LM_HORZ 상태를 기반으로 치수를 반환합니다. LM_STRETCH [CalcFixedLayout에](#calcfixedlayout)사용되는 *bStretch* 매개 변수와 유사하게 작동합니다. 이 멤버 함수를 참조하여 스트레칭과 방향 간의 관계에 대한 자세한 정보를 확인하십시오.|
|LM_HORZ|막대가 수평 또는 수직 방향임을 나타냅니다. 막대가 수평 방향이고 세로 방향인 경우 설정되지 않습니다. LM_HORZ [CalcFixedLayout에](#calcfixedlayout)사용되는 *bHorz* 매개 변수와 유사하게 작동합니다. 이 멤버 함수를 참조하여 스트레칭과 방향 간의 관계에 대한 자세한 정보를 확인하십시오.|
|LM_MRUWIDTH|가장 최근에 사용한 동적 폭입니다. *nLength* 매개 변수를 무시하고 가장 최근에 사용한 가장 최근에 사용한 너비를 사용합니다.|
|LM_HORZDOCK|수평 도킹 치수입니다. *nLength* 매개 변수를 무시하고 가장 큰 너비를 가진 동적 크기를 반환합니다.|
|LM_VERTDOCK|수직 도킹 치수입니다. *nLength* 매개 변수를 무시하고 높이가 가장 큰 동적 크기를 반환합니다.|
|LM_LENGTHY|*nLength가* 너비 대신 높이(Y 방향)를 나타내는 경우 설정합니다.|
|LM_COMMIT|LM_MRUWIDTH 부동 제어 막대의 현재 너비로 재설정합니다.|

### <a name="return-value"></a>Return Value

[CSize](../../atl-mfc-shared/reference/csize-class.md) 개체의 컨트롤 막대 크기(픽셀 단위)입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 재정의하여 파생 된 클래스에서 고유한 동적 레이아웃을 `CControlBar`제공합니다. [CToolbar와](../../mfc/reference/ctoolbar-class.md)같은 `CControlBar`에서 파생된 MFC 클래스는 이 멤버 함수를 재정의하고 자체 구현을 제공합니다.

## <a name="ccontrolbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>C컨트롤바::석회화레이아웃

컨트롤 막대의 수평 크기를 계산하려면 이 멤버 함수를 호출합니다.

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>매개 변수

*b스트레치*<br/>
막대를 프레임 크기로 늘려야 하는지 여부를 나타냅니다. *bStretch* 매개변수는 막대가 도킹 막대가 아닌 경우 0이 아니며 도킹 또는 부동(도킹에 사용 가능)이 0입니다.

*b호르츠 (주)*<br/>
막대가 수평 또는 수직 방향임을 나타냅니다. 막대가 가로 방향이고 세로 방향인 경우 0인 경우 *bHorz* 매개변수는 0이 아닙니다.

### <a name="return-value"></a>Return Value

개체의 컨트롤 막대 크기(픽셀 `CSize` 단위)입니다.

### <a name="remarks"></a>설명

도구 모음과 같은 컨트롤 막대는 컨트롤 막대에 포함된 단추를 수용하기 위해 수평 또는 수직으로 늘릴 수 있습니다.

*bStretch가* TRUE이면 *bHorz에서*제공하는 방향을 따라 치수를 늘입니다. 즉, *bHorz가* FALSE이면 컨트롤 막대가 세로로 늘어납니다. *bStretch가* FALSE이면 스트레치가 발생하지 않습니다. 다음 표에서는 *bStretch* 및 *bHorz의*가능한 순열 및 결과 컨트롤 막대 스타일을 보여 주었습니다.

|b스트레치|b호르츠 (주)|스트레칭|방향|도킹/도킹 안|
|--------------|-----------|----------------|-----------------|--------------------------|
|TRUE|TRUE|수평 스트레칭|수평 방향|도킹되지 않음|
|TRUE|FALSE|수직 스트레칭|수직 방향|도킹되지 않음|
|FALSE|TRUE|사용할 수 있는 스트레칭 없음|수평 방향|도킹|
|FALSE|FALSE|사용할 수 있는 스트레칭 없음|수직 방향|도킹|

## <a name="ccontrolbarcalcinsiderect"></a><a name="calcinsiderect"></a>CControlBar:::칼크인사이드렉트

프레임워크는 이 함수를 호출하여 컨트롤 막대의 클라이언트 영역을 계산합니다.

```
virtual void CalcInsideRect(
    CRect& rect,
    BOOL bHorz) const;
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
컨트롤 막대의 현재 치수를 포함합니다. 테두리를 포함합니다.

*b호르츠 (주)*<br/>
막대가 수평 또는 수직 방향임을 나타냅니다. 막대가 가로 방향이고 세로 방향인 경우 0인 경우 *bHorz* 매개변수는 0이 아닙니다.

### <a name="remarks"></a>설명

이 함수는 컨트롤 막대가 그려지기 전에 호출됩니다.

이 함수를 재정의하여 컨트롤 막대의 테두리 및 그리퍼 막대의 렌더링을 사용자 지정합니다.

## <a name="ccontrolbarccontrolbar"></a><a name="ccontrolbar"></a>CControlBar:::CControlBar

`CControlBar` 개체를 생성합니다.

```
CControlBar();
```

## <a name="ccontrolbardopaint"></a><a name="dopaint"></a>CControlBar: :D오페인트

컨트롤 막대의 테두리 및 그리퍼 막대를 렌더링하기 위해 프레임워크에서 호출합니다.

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
컨트롤 막대의 테두리와 그리퍼를 렌더링하는 데 사용할 장치 컨텍스트를 가리킵니다.

### <a name="remarks"></a>설명

이 함수를 재정의하여 컨트롤 막대의 그리기 동작을 사용자 지정합니다.

또 다른 사용자 지정 방법은 `DrawBorders` `DrawGripper` 및 함수를 재정의하고 테두리 및 그리퍼에 대한 사용자 지정 그리기 코드를 추가하는 것입니다. 이러한 메서드는 기본 `DoPaint` 메서드에서 호출되므로 `DoPaint` 재정의가 필요하지 않습니다.

## <a name="ccontrolbardrawborders"></a><a name="drawborders"></a>CControlBar::D원시보더스

컨트롤 막대의 테두리를 렌더링하는 프레임워크에서 호출됩니다.

```
virtual void DrawBorders(
    CDC* pDC,
    CRect& rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
컨트롤 막대의 테두리를 렌더링하는 데 사용할 장치 컨텍스트를 가리킵니다.

*rect*<br/>
컨트롤 `CRect` 막대의 치수를 포함하는 개체입니다.

### <a name="remarks"></a>설명

이 함수를 재정의하여 컨트롤 막대 테두리의 모양을 사용자 지정합니다.

## <a name="ccontrolbardrawgripper"></a><a name="drawgripper"></a>CControlBar::D로그리퍼

컨트롤 막대의 그리퍼를 렌더링하기 위해 프레임워크에서 호출합니다.

```
virtual void DrawGripper(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
컨트롤 바 그리퍼를 렌더링하는 데 사용할 장치 컨텍스트를 가리킵니다.

*rect*<br/>
컨트롤 `CRect` 바 그리퍼의 치수를 포함하는 오브젝트입니다.

### <a name="remarks"></a>설명

이 함수를 재정의하여 컨트롤 바 그리퍼의 모양을 사용자 지정합니다.

## <a name="ccontrolbarenabledocking"></a><a name="enabledocking"></a>CControlBar::사용 도킹

이 함수를 호출하여 컨트롤 막대를 도킹할 수 있습니다.

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>매개 변수

*dwDockStyle*<br/>
컨트롤 막대가 도킹을 지원하는지 여부와 지원되는 경우 컨트롤 막대를 도킹할 수 있는 부모 창의 측면을 지정합니다. 다음 중 하나 이상이 될 수 있습니다.

- CBRS_ALIGN_TOP 클라이언트 영역의 맨 위에 도킹할 수 있습니다.

- CBRS_ALIGN_BOTTOM 클라이언트 영역 의 맨 아래에 도킹을 허용합니다.

- CBRS_ALIGN_LEFT 클라이언트 영역의 왼쪽에 도킹을 허용합니다.

- CBRS_ALIGN_RIGHT 클라이언트 영역의 오른쪽에 도킹할 수 있습니다.

- CBRS_ALIGN_ANY 클라이언트 영역의 모든 측면에 도킹을 허용합니다.

- CBRS_FLOAT_MULTI 여러 컨트롤 막대를 단일 미니 프레임 창에 부동할 수 있습니다.

0(즉, 플래그없음을 나타내는 경우)이 면 컨트롤 막대가 도킹되지 않습니다.

### <a name="remarks"></a>설명

지정된 측면은 대상 프레임 창에서 도킹에 사용하도록 설정된 측면 중 하나와 일치해야 하거나 컨트롤 막대를 해당 프레임 창에 도킹할 수 없습니다.

## <a name="ccontrolbargetbarstyle"></a><a name="getbarstyle"></a>CControlBar::겟바스타일

이 함수를 호출하여 컨트롤 막대에 대해 현재 설정된 **CBRS_(컨트롤** 막대 스타일) 설정을 확인합니다.

```
DWORD GetBarStyle();
```

### <a name="return-value"></a>Return Value

**컨트롤** CBRS_(컨트롤 막대 스타일) 설정이 현재입니다. 사용 가능한 스타일의 전체 목록은 [CControlBar::SetBarStyle을](#setbarstyle) 참조하십시오.

### <a name="remarks"></a>설명

**WS_(창** 스타일) 스타일을 처리하지 않습니다.

## <a name="ccontrolbargetborders"></a><a name="getborders"></a>CControlBar:::GetBorders

컨트롤 막대에 대한 현재 테두리 값을 반환합니다.

```
CRect GetBorders() const;
```

### <a name="return-value"></a>Return Value

컨트롤 `CRect` 막대 개체의 각 측면의 현재 너비(픽셀)를 포함하는 개체입니다. 예를 들어 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체의 *왼쪽* 멤버 값은 왼쪽 테두리의 너비입니다.

## <a name="ccontrolbargetcount"></a><a name="getcount"></a>CControlBar::GetCount

개체에서 HWND가 아닌 항목 `CControlBar` 수를 반환합니다.

```
int GetCount() const;
```

### <a name="return-value"></a>Return Value

개체의 HWND가 아닌 항목의 수입니다. `CControlBar` 이 함수는 [CDialogBar](../../mfc/reference/cdialogbar-class.md) 개체에 대해 0을 반환합니다.

### <a name="remarks"></a>설명

항목의 형식은 파생 된 개체에 따라 달라 집니다: [CStatusBar](../../mfc/reference/cstatusbar-class.md) 개체에 대 한 창 및 [CToolBar](../../mfc/reference/ctoolbar-class.md) 개체에 대 한 단추 및 구분 기호.

## <a name="ccontrolbargetdockingframe"></a><a name="getdockingframe"></a>CControlBar::GetDockingFrame

이 멤버 함수를 호출하여 컨트롤 막대가 도킹된 현재 프레임 창에 대한 포인터를 가져옵니다.

```
CFrameWnd* GetDockingFrame() const;
```

### <a name="return-value"></a>Return Value

성공하면 프레임 창에 대한 포인터입니다. 그렇지 않으면 NULL.

컨트롤 막대가 프레임 창에 도킹되지 않은 경우(즉, 컨트롤 막대가 부동하는 경우) 이 함수는 상위 [CMiniFrameWnd에](../../mfc/reference/cminiframewnd-class.md)대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

도킹 가능한 컨트롤 막대에 대한 자세한 내용은 [CControlBar::인에이블도킹](#enabledocking) 및 [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)를 참조하십시오.

## <a name="ccontrolbarisfloating"></a><a name="isfloating"></a>CControlBar::떠있는

이 멤버 함수를 호출하여 컨트롤 막대가 부동 또는 도킹되어 있는지 확인합니다.

```
BOOL IsFloating() const;
```

### <a name="return-value"></a>Return Value

컨트롤 바가 부동하는 경우 0이 아닌 경우; 그렇지 않으면 0.

### <a name="remarks"></a>설명

제어 막대의 상태를 도킹에서 부동으로 변경하려면 [CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar)를 호출합니다.

## <a name="ccontrolbarm_bautodelete"></a><a name="m_bautodelete"></a>CControlBar::m_bAutoDelete

0이 아닌 `CControlBar` 경우 Windows 컨트롤 막대가 소멸되면 개체가 삭제됩니다.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>설명

*m_bAutoDelete* BOOL 형식의 공용 변수입니다.

컨트롤-막대 개체는 일반적으로 프레임 창 개체에 포함 됩니다. 이 경우 프레임 창이 소멸될 때 포함된 컨트롤 막대 개체가 소멸되므로 *m_bAutoDelete* 0입니다.

힙에 `CControlBar` 개체를 할당하고 **delete를**호출하지 않을 경우 이 변수를 zero가 아닌 값으로 설정합니다.

## <a name="ccontrolbarm_pinplaceowner"></a><a name="m_pinplaceowner"></a>CControlBar::m_pInPlaceOwner

컨트롤 막대의 소유자입니다.

```
CWnd* m_pInPlaceOwner;
```

## <a name="ccontrolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CControlBar::에업데이트CmdUI

이 멤버 함수는 도구 모음 또는 상태 표시줄의 상태를 업데이트하기 위해 프레임워크에서 호출됩니다.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler) = 0;
```

### <a name="parameters"></a>매개 변수

*p Target*<br/>
응용 프로그램의 주 프레임 창을 가리킵니다. 이 포인터는 업데이트 메시지를 라우팅하는 데 사용됩니다.

*bDisableIfNohndler*<br/>
업데이트 처리기가 없는 컨트롤을 비활성화된 것으로 자동으로 표시해야 하는지 여부를 나타내는 플래그입니다.

### <a name="remarks"></a>설명

개별 단추 또는 창을 업데이트하려면 메시지 맵에서 ON_UPDATE_COMMAND_UI 매크로를 사용하여 업데이트 처리기를 적절하게 설정합니다. 이 매크로 사용에 대한 자세한 내용은 [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) 를 참조하십시오.

`OnUpdateCmdUI`응용 프로그램이 유휴 상태일 때 프레임워크에서 호출됩니다. 업데이트할 프레임 창은 적어도 간접적으로 표시되는 프레임 창의 자식 창이어야 합니다. `OnUpdateCmdUI`는 고급 재정의 할 수 있습니다.

## <a name="ccontrolbarsetbarstyle"></a><a name="setbarstyle"></a>CControlBar::SetBar스타일

이 함수를 호출하여 컨트롤 막대에 대해 원하는 **CBRS_** 스타일을 설정합니다.

```cpp
void SetBarStyle(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
컨트롤 막대에 원하는 스타일입니다. 다음 중 하나 이상이 될 수 있습니다.

- CBRS_ALIGN_TOP 컨트롤 막대를 프레임 창의 클라이언트 영역 맨 위에 도킹할 수 있습니다.

- CBRS_ALIGN_BOTTOM 컨트롤 막대를 프레임 창의 클라이언트 영역 아래쪽에 도킹할 수 있습니다.

- CBRS_ALIGN_LEFT 컨트롤 막대를 프레임 창의 클라이언트 영역의 왼쪽에 도킹할 수 있습니다.

- CBRS_ALIGN_RIGHT 컨트롤 막대를 프레임 창의 클라이언트 영역 의 오른쪽에 도킹할 수 있습니다.

- CBRS_ALIGN_ANY 컨트롤 막대를 프레임 창의 클라이언트 영역의 모든 측면에 도킹할 수 있습니다.

- CBRS_BORDER_TOP 컨트롤 막대의 위쪽 가장자리에 테두리가 표시될 때 테두리를 그려집니다.

- CBRS_BORDER_BOTTOM 컨트롤 막대의 아래쪽 가장자리에 테두리가 표시될 때 테두리가 그려집니다.

- CBRS_BORDER_LEFT 컨트롤 막대의 왼쪽 가장자리에 테두리가 표시될 때 테두리를 그려집니다.

- CBRS_BORDER_RIGHT 볼 때 컨트롤 막대의 오른쪽 가장자리에 테두리가 그려집니다.

- CBRS_FLOAT_MULTI 여러 컨트롤 막대를 단일 미니 프레임 창에 부동할 수 있습니다.

- CBRS_TOOLTIPS 컨트롤 막대에 대해 도구 설명이 표시됩니다.

- CBRS_FLYBY 도구 설명과 동시에 메시지 텍스트를 업데이트합니다.

- CBRS_GRIPPER `CReBar` 오브젝트의 밴드에 사용된 그리퍼가 `CControlBar`파생된 클래스에 대해 그려지도록 합니다.

### <a name="remarks"></a>설명

**WS_(창** 스타일) 설정에는 영향을 주지 않습니다.

## <a name="ccontrolbarsetborders"></a><a name="setborders"></a>C컨트롤바:::설정 테두리

이 함수를 호출하여 컨트롤 막대 테두리의 크기를 설정합니다.

```cpp
void SetBorders(
    int cxLeft = 0,
    int cyTop = 0,
    int cxRight = 0,
    int cyBottom = 0);

void SetBorders(LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*cxLeft*<br/>
컨트롤 막대의 왼쪽 테두리의 너비(픽셀)입니다.

*사이탑*<br/>
컨트롤 막대의 위쪽 테두리의 높이(픽셀)입니다.

*cxRight*<br/>
컨트롤 막대의 오른쪽 테두리의 너비(픽셀)입니다.

*사이 바텀*<br/>
컨트롤 막대의 아래쪽 테두리의 높이(픽셀)입니다.

*Lprect*<br/>
컨트롤 막대 개체의 각 테두리의 현재 너비(픽셀)를 포함하는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체에 대한 포인터입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 컨트롤 막대의 위쪽 및 아래쪽 테두리를 5픽셀로 설정하고 왼쪽 및 오른쪽 테두리를 2픽셀로 설정합니다.

[!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]

## <a name="ccontrolbarsetinplaceowner"></a><a name="setinplaceowner"></a>CControlBar::SetInPlace 소유자

컨트롤 막대의 소유자를 변경합니다.

```cpp
void SetInPlaceOwner(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
`CWnd` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[MFC 샘플 CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CToolBar 클래스](../../mfc/reference/ctoolbar-class.md)<br/>
[클리클로그바 클래스](../../mfc/reference/cdialogbar-class.md)<br/>
[CStatusBar 클래스](../../mfc/reference/cstatusbar-class.md)<br/>
[CReBar 클래스](../../mfc/reference/crebar-class.md)
