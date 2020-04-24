---
title: C스크롤바 클래스
ms.date: 11/04/2016
f1_keywords:
- CScrollBar
- AFXWIN/CScrollBar
- AFXWIN/CScrollBar::CScrollBar
- AFXWIN/CScrollBar::Create
- AFXWIN/CScrollBar::EnableScrollBar
- AFXWIN/CScrollBar::GetScrollBarInfo
- AFXWIN/CScrollBar::GetScrollInfo
- AFXWIN/CScrollBar::GetScrollLimit
- AFXWIN/CScrollBar::GetScrollPos
- AFXWIN/CScrollBar::GetScrollRange
- AFXWIN/CScrollBar::SetScrollInfo
- AFXWIN/CScrollBar::SetScrollPos
- AFXWIN/CScrollBar::SetScrollRange
- AFXWIN/CScrollBar::ShowScrollBar
helpviewer_keywords:
- CScrollBar [MFC], CScrollBar
- CScrollBar [MFC], Create
- CScrollBar [MFC], EnableScrollBar
- CScrollBar [MFC], GetScrollBarInfo
- CScrollBar [MFC], GetScrollInfo
- CScrollBar [MFC], GetScrollLimit
- CScrollBar [MFC], GetScrollPos
- CScrollBar [MFC], GetScrollRange
- CScrollBar [MFC], SetScrollInfo
- CScrollBar [MFC], SetScrollPos
- CScrollBar [MFC], SetScrollRange
- CScrollBar [MFC], ShowScrollBar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
ms.openlocfilehash: 2079e12eccde42fe8c456a7852a029f44ae3cd77
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754407"
---
# <a name="cscrollbar-class"></a>C스크롤바 클래스

Windows 스크롤 막대 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CScrollBar : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C스크롤바::C스크롤바](#cscrollbar)|`CScrollBar` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C스크롤바::만들기](#create)|Windows 스크롤 막대를 만들고 개체에 `CScrollBar` 연결합니다.|
|[C스크롤바::인에이블스크롤바](#enablescrollbar)|스크롤 막대의 화살표 하나 또는 둘 다를 사용하거나 사용하지 않도록 설정합니다.|
|[C스크롤바::Get스크롤바정보](#getscrollbarinfo)|구조를 사용하여 스크롤 막대에 `SCROLLBARINFO` 대한 정보를 검색합니다.|
|[C스크롤바::Get스크롤정보](#getscrollinfo)|스크롤 막대에 대한 정보를 검색합니다.|
|[C스크롤바::Get스크롤제한](#getscrolllimit)|스크롤 막대의 제한을 검색합니다.|
|[C스크롤바::Get스크롤포스](#getscrollpos)|스크롤 상자의 현재 위치를 검색합니다.|
|[C스크롤바::겟스크롤레인지](#getscrollrange)|지정된 스크롤 막대의 현재 최소 및 최대 스크롤 막대 위치를 검색합니다.|
|[C스크롤바::세트스크롤정보](#setscrollinfo)|스크롤 막대에 대한 정보를 설정합니다.|
|[C스크롤바::세트스크롤포스](#setscrollpos)|스크롤 상자의 현재 위치를 설정합니다.|
|[C스크롤바::세트스크롤레인지](#setscrollrange)|지정된 스크롤 막대에 대한 최소 및 최대 위치 값을 설정합니다.|
|[C스크롤바::쇼스크롤바](#showscrollbar)|스크롤 막대를 표시하거나 숨깁니다.|

## <a name="remarks"></a>설명

두 단계로 스크롤 막대 컨트롤을 만듭니다. 먼저 `CScrollBar` 생성자 호출하여 개체를 `CScrollBar` 생성한 다음 멤버 [만들기](#create) 함수를 호출하여 Windows 스크롤 `CScrollBar` 막대 컨트롤을 만들고 개체에 연결합니다.

대화 상자 `CScrollBar` 내에서(대화 상자 리소스를 통해) `CScrollBar` 개체를 만들면 사용자가 대화 상자를 닫으면 자동으로 소멸됩니다.

창 내에서 `CScrollBar` 객체를 만드는 경우 객체를 삭제해야 할 수도 있습니다.

스택에서 객체를 `CScrollBar` 만들면 자동으로 소멸됩니다. 새 함수를 `CScrollBar` 사용하여 힙에 개체를 **new** 만드는 경우 사용자가 Windows 스크롤 막대를 종료할 때 개체에 **삭제를** 호출하여 개체를 삭제해야 합니다.

개체에 메모리를 `CScrollBar` 할당하는 경우 `CScrollBar` 소멸자 재정의하여 할당을 삭제합니다.

사용에 `CScrollBar`대한 관련 정보는 [컨트롤](../../mfc/controls-mfc.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CScrollBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cscrollbarcreate"></a><a name="create"></a>C스크롤바::만들기

Windows 스크롤 막대를 만들고 개체에 `CScrollBar` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
스크롤 막대의 스타일을 지정합니다. 스크롤 막대 스타일의 조합을 스크롤 [막대에](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles) 적용합니다.

*rect*<br/>
스크롤 막대의 크기와 위치를 지정합니다. 구조체 `RECT` 또는 개체일 `CRect` 수 있습니다.

*pParentWnd*<br/>
스크롤 막대의 부모 창(일반적으로 개체)을 지정합니다. `CDialog` NULL이 아니어야 합니다.

*nID*<br/>
스크롤 막대의 컨트롤 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 단계로 `CScrollBar` 객체를 생성합니다. 먼저 개체를 생성하는 생성자 호출합니다. `CScrollBar` `Create`그런 다음 연결된 Windows 스크롤 막대를 만들고 초기화하고 `CScrollBar` 개체에 연결합니다.

스크롤 막대에 다음 [창 스타일을](../../mfc/reference/styles-used-by-mfc.md#window-styles) 적용합니다.

- 항상 WS_CHILD

- WS_VISIBLE 보통

- WS_DISABLED 드물게

- WS_GROUP 컨트롤그룹

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]

## <a name="cscrollbarcscrollbar"></a><a name="cscrollbar"></a>C스크롤바::C스크롤바

`CScrollBar` 개체를 생성합니다.

```
CScrollBar();
```

### <a name="remarks"></a>설명

개체를 생성한 후 `Create` 멤버 함수를 호출하여 Windows 스크롤 막대를 만들고 초기화합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]

## <a name="cscrollbarenablescrollbar"></a><a name="enablescrollbar"></a>C스크롤바::인에이블스크롤바

스크롤 막대의 화살표 하나 또는 둘 다를 사용하거나 사용하지 않도록 설정합니다.

```
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```

### <a name="parameters"></a>매개 변수

*nArrowFlags*<br/>
스크롤 화살표가 활성화 또는 비활성화되는지 여부와 활성화 또는 비활성화된 화살표를 지정합니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다.

- ESB_ENABLE_BOTH 스크롤 막대의 두 화살표를 모두 활성화합니다.

- ESB_DISABLE_LTUP 가로 스크롤 막대의 왼쪽 화살표 또는 세로 스크롤 막대의 위쪽 화살표를 사용하지 않도록 설정합니다.

- ESB_DISABLE_RTDN 가로 스크롤 막대의 오른쪽 화살표 또는 세로 스크롤 막대의 아래쪽 화살표를 사용하지 않도록 설정합니다.

- ESB_DISABLE_BOTH 스크롤 막대의 두 화살표를 모두 사용하지 않도록 설정합니다.

### <a name="return-value"></a>Return Value

화살표가 지정된 대로 활성화되거나 비활성화된 경우 0이 아닙니다. 그렇지 않으면 0을 통해 화살표가 이미 요청된 상태에 있거나 오류가 발생했음을 나타냅니다.

### <a name="example"></a>예제

  [CScrollBar::Set스크롤 범위에](#setscrollrange)대한 예제를 참조하십시오.

## <a name="cscrollbargetscrollbarinfo"></a><a name="getscrollbarinfo"></a>C스크롤바::Get스크롤바정보

`SCROLLBARINFO` 구조체에서 스크롤 막대에 대해 유지 관리하는 정보를 검색합니다.

```
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;
```

### <a name="parameters"></a>매개 변수

*p스크롤정보*<br/>
[SCROLLBARINFO](/windows/win32/api/winuser/ns-winuser-scrollbarinfo) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [SBM_SCROLLBARINFO](/windows/win32/Controls/sbm-getscrollbarinfo) 메시지의 기능을 에뮬레이트합니다.

## <a name="cscrollbargetscrollinfo"></a><a name="getscrollinfo"></a>C스크롤바::Get스크롤정보

`SCROLLINFO` 구조체에서 스크롤 막대에 대해 유지 관리하는 정보를 검색합니다.

```
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    UINT nMask = SIF_ALL);
```

### <a name="parameters"></a>매개 변수

*lp스크롤정보*<br/>
[SCROLLINFO](/windows/win32/api/winuser/ns-winuser-scrollinfo) 구조에 대한 포인터입니다. 이 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

*nMask*<br/>
검색할 스크롤 막대 매개 변수를 지정합니다. 일반적인 사용, SIF_ALL SIF_PAGE, SIF_POS, SIF_TRACKPOS 및 SIF_RANGE 조합을 지정합니다. nMask 값에 대한 자세한 내용은 을 참조하십시오. `SCROLLINFO`

### <a name="return-value"></a>Return Value

메시지가 값을 검색한 경우 반환은 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

`GetScrollInfo`응용 프로그램에서 32비트 스크롤 위치를 사용할 수 있습니다.

[SCROLLINFO](/windows/win32/api/winuser/ns-winuser-scrollinfo) 구조에는 최소 및 최대 스크롤 위치, 페이지 크기 및 스크롤 상자(엄지 손가락)의 위치를 비롯한 스크롤 막대에 대한 정보가 포함되어 있습니다. 구조 `SCROLLINFO` 기본값 변경에 대한 자세한 내용은 Windows SDK의 구조 항목을 참조하십시오.

스크롤 막대 위치를 나타내는 MFC Windows 메시지 처리기[CWnd:OnHScroll 및 [CWnd::OnVScroll)는](../../mfc/reference/cwnd-class.md#onvscroll)16비트의 위치 데이터만 제공합니다. `GetScrollInfo`스크롤 `SetScrollInfo` 막대 위치 데이터의 32 비트를 제공합니다. 따라서 응용 프로그램은 `GetScrollInfo` 처리 중 `CWnd::OnHScroll` `CWnd::OnVScroll` 하나를 호출하거나 32비트 스크롤 막대 위치 데이터를 가져올 수 있습니다.

### <a name="example"></a>예제

  [CWnd::OnH스크롤](../../mfc/reference/cwnd-class.md#onhscroll)에 대한 예제를 참조하십시오.

## <a name="cscrollbargetscrolllimit"></a><a name="getscrolllimit"></a>C스크롤바::Get스크롤제한

스크롤 막대의 최대 스크롤 위치를 검색합니다.

```
int GetScrollLimit();
```

### <a name="return-value"></a>Return Value

성공한 경우 스크롤 막대의 최대 위치를 지정합니다. 그렇지 않으면 0.

### <a name="example"></a>예제

  [CWnd::OnH스크롤](../../mfc/reference/cwnd-class.md#onhscroll)에 대한 예제를 참조하십시오.

## <a name="cscrollbargetscrollpos"></a><a name="getscrollpos"></a>C스크롤바::Get스크롤포스

스크롤 상자의 현재 위치를 검색합니다.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Return Value

성공한 경우 스크롤 상자의 현재 위치를 지정합니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

현재 위치는 현재 스크롤 범위에 종속된 상대 값입니다. 예를 들어 스크롤 범위가 100~200이고 스크롤 상자가 막대 중간에 있는 경우 현재 위치는 150입니다.

### <a name="example"></a>예제

  [CWnd::OnH스크롤](../../mfc/reference/cwnd-class.md#onhscroll)에 대한 예제를 참조하십시오.

## <a name="cscrollbargetscrollrange"></a><a name="getscrollrange"></a>C스크롤바::겟스크롤레인지

지정된 스크롤 막대의 현재 최소 및 최대 스크롤 막대 위치를 *lpMinPos* 및 *lpMaxPos에서*지정한 위치로 복사합니다.

```cpp
void GetScrollRange(
    LPINT lpMinPos,
    LPINT lpMaxPos) const;
```

### <a name="parameters"></a>매개 변수

*lpMinpos*<br/>
최소 위치를 수신하는 정수 변수를 가리킵니다.

*lp맥스포스*<br/>
최대 위치를 수신하는 정수 변수를 가리킵니다.

### <a name="remarks"></a>설명

스크롤 막대 컨트롤의 기본 범위는 비어 있습니다(두 값 모두 0).

### <a name="example"></a>예제

  [CWnd::OnH스크롤](../../mfc/reference/cwnd-class.md#onhscroll)에 대한 예제를 참조하십시오.

## <a name="cscrollbarsetscrollinfo"></a><a name="setscrollinfo"></a>C스크롤바::세트스크롤정보

구조가 스크롤 `SCROLLINFO` 막대에 대해 유지 관리하는 정보를 설정합니다.

```
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>매개 변수

*lp스크롤정보*<br/>
[SCROLLINFO](/windows/win32/api/winuser/ns-winuser-scrollinfo) 구조에 대한 포인터입니다.

*bRedraw*<br/>
스크롤 막대를 다시 그려 새 정보를 반영할지 여부를 지정합니다. *bRedraw가* TRUE이면 스크롤 막대가 다시 그려집니다. FALSE이면 다시 그려지지 않습니다. 스크롤 막대는 기본적으로 다시 그려집니다.

### <a name="return-value"></a>Return Value

성공하면 반환은 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

플래그 값을 포함하여 구조 `SCROLLINFO` 매개 변수에 필요한 값을 제공해야 합니다.

구조에는 `SCROLLINFO` 최소 및 최대 스크롤 위치, 페이지 크기 및 스크롤 상자(엄지 손가락)의 위치를 비롯한 스크롤 막대에 대한 정보가 포함되어 있습니다. 구조 기본값 변경에 대한 자세한 내용은 Windows SDK의 [SCROLLINFO](/windows/win32/api/winuser/ns-winuser-scrollinfo) 구조 항목을 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]

## <a name="cscrollbarsetscrollpos"></a><a name="setscrollpos"></a>C스크롤바::세트스크롤포스

스크롤 상자의 현재 위치를 *nPos에서* 지정한 위치로 설정하고 지정된 경우 스크롤 막대를 다시 그려 새 위치를 반영합니다.

```
int SetScrollPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
스크롤 상자의 새 위치를 지정합니다. 스크롤 범위 내에 있어야 합니다.

*bRedraw*<br/>
스크롤 막대를 새 위치를 반영하도록 다시 그려야 하는지 여부를 지정합니다. *bRedraw가* TRUE이면 스크롤 막대가 다시 그려집니다. FALSE이면 다시 그려지지 않습니다. 스크롤 막대는 기본적으로 다시 그려집니다.

### <a name="return-value"></a>Return Value

성공한 경우 스크롤 상자의 이전 위치를 지정합니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

스크롤 막대가 짧은 간격 내에 스크롤 막대를 두 번 다시 그리지 않도록 다른 함수에 대한 후속 호출로 다시 그려질 때마다 *bRedraw를* FALSE로 설정합니다.

### <a name="example"></a>예제

  [CScrollBar::Set스크롤 범위에](#setscrollrange)대한 예제를 참조하십시오.

## <a name="cscrollbarsetscrollrange"></a><a name="setscrollrange"></a>C스크롤바::세트스크롤레인지

지정된 스크롤 막대에 대한 최소 및 최대 위치 값을 설정합니다.

```cpp
void SetScrollRange(
    int nMinPos,
    int nMaxPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>매개 변수

*n민포스*<br/>
최소 스크롤 위치를 지정합니다.

*n맥스포스*<br/>
최대 스크롤 위치를 지정합니다.

*bRedraw*<br/>
변경 내용을 반영하도록 스크롤 막대를 다시 그려야 하는지 여부를 지정합니다. *bRedraw가* TRUE이면 스크롤 막대가 다시 그려집니다. FALSE인 경우 다시 그려지지 않습니다. 기본적으로 다시 그려집니다.

### <a name="remarks"></a>설명

표준 스크롤 막대를 숨기려면 *nMinPos* 및 *nMaxPos를* 0으로 설정합니다.

스크롤 막대 알림 메시지를 처리하는 동안 스크롤 막대를 숨기기 위해 이 함수를 호출하지 마십시오.

멤버 함수에 `SetScrollRange` 대한 호출을 즉시 따르는 경우 *bRedraw를* `SetScrollPos` 0으로 설정하여 스크롤 막대가 두 번 다시 그려지지 않도록 합니다. `SetScrollPos`

*nMinPos와* *nMaxPos에서* 지정한 값 의 차이는 32,767보다 크지 않아야 합니다. 스크롤 막대 컨트롤의 기본 범위는 비어 *있습니다(nMinPos* 및 *nMaxPos* 모두 0).

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]

## <a name="cscrollbarshowscrollbar"></a><a name="showscrollbar"></a>C스크롤바::쇼스크롤바

스크롤 막대를 표시하거나 숨깁니다.

```cpp
void ShowScrollBar(BOOL bShow = TRUE);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
스크롤 막대가 표시되거나 숨김여부를 지정합니다. 이 매개 변수가 TRUE이면 스크롤 막대가 표시됩니다. 그렇지 않으면 숨김이 있습니다.

### <a name="remarks"></a>설명

응용 프로그램은 스크롤 막대 알림 메시지를 처리하는 동안 스크롤 막대를 숨기기 위해 이 함수를 호출해서는 안 됩니다.

### <a name="example"></a>예제

  [CScrollBar::만들기에](#create)대한 예제를 참조하십시오.

## <a name="see-also"></a>참조

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CButton 클래스](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit 클래스](../../mfc/reference/cedit-class.md)<br/>
[클리스박스 클래스](../../mfc/reference/clistbox-class.md)<br/>
[정적 클래스](../../mfc/reference/cstatic-class.md)<br/>
[클리언로그 클래스](../../mfc/reference/cdialog-class.md)
