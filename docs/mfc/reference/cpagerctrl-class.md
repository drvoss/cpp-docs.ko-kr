---
title: CPagerCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CPagerCtrl
- AFXCMN/CPagerCtrl
- AFXCMN/CPagerCtrl::CPagerCtrl
- AFXCMN/CPagerCtrl::Create
- AFXCMN/CPagerCtrl::CreateEx
- AFXCMN/CPagerCtrl::ForwardMouse
- AFXCMN/CPagerCtrl::GetBkColor
- AFXCMN/CPagerCtrl::GetBorder
- AFXCMN/CPagerCtrl::GetButtonSize
- AFXCMN/CPagerCtrl::GetButtonState
- AFXCMN/CPagerCtrl::GetDropTarget
- AFXCMN/CPagerCtrl::GetScrollPos
- AFXCMN/CPagerCtrl::IsButtonDepressed
- AFXCMN/CPagerCtrl::IsButtonGrayed
- AFXCMN/CPagerCtrl::IsButtonHot
- AFXCMN/CPagerCtrl::IsButtonInvisible
- AFXCMN/CPagerCtrl::IsButtonNormal
- AFXCMN/CPagerCtrl::RecalcSize
- AFXCMN/CPagerCtrl::SetBkColor
- AFXCMN/CPagerCtrl::SetBorder
- AFXCMN/CPagerCtrl::SetButtonSize
- AFXCMN/CPagerCtrl::SetChild
- AFXCMN/CPagerCtrl::SetScrollPos
helpviewer_keywords:
- CPagerCtrl [MFC], CPagerCtrl
- CPagerCtrl [MFC], Create
- CPagerCtrl [MFC], CreateEx
- CPagerCtrl [MFC], ForwardMouse
- CPagerCtrl [MFC], GetBkColor
- CPagerCtrl [MFC], GetBorder
- CPagerCtrl [MFC], GetButtonSize
- CPagerCtrl [MFC], GetButtonState
- CPagerCtrl [MFC], GetDropTarget
- CPagerCtrl [MFC], GetScrollPos
- CPagerCtrl [MFC], IsButtonDepressed
- CPagerCtrl [MFC], IsButtonGrayed
- CPagerCtrl [MFC], IsButtonHot
- CPagerCtrl [MFC], IsButtonInvisible
- CPagerCtrl [MFC], IsButtonNormal
- CPagerCtrl [MFC], RecalcSize
- CPagerCtrl [MFC], SetBkColor
- CPagerCtrl [MFC], SetBorder
- CPagerCtrl [MFC], SetButtonSize
- CPagerCtrl [MFC], SetChild
- CPagerCtrl [MFC], SetScrollPos
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
ms.openlocfilehash: cd27a3acf26abe39831089546df317679f2ecab6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753709"
---
# <a name="cpagerctrl-class"></a>CPagerCtrl 클래스

`CPagerCtrl` 클래스는 윈도우에 맞지 않는 포함된 창을 보기로 스크롤할 수 있는 Windows 페이저 컨트롤을 래핑합니다.

## <a name="syntax"></a>구문

```
class CPagerCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CPagerCtrl:::CPagerCtrl](#cpagerctrl)|`CPagerCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CPagerCtrl::만들기](#create)|지정된 스타일로 호출기 컨트롤을 만들고 현재 `CPagerCtrl` 개체에 연결합니다.|
|[CPagerCtrl::만들기](#createex)|지정된 확장 된 스타일을 사용하여 호출기 컨트롤을 `CPagerCtrl` 만들고 현재 개체에 연결합니다.|
|[CPagerCtrl::포워드 마우스](#forwardmouse)|현재 호출기 컨트롤에 포함된 WM_MOUSEMOVE [메시지를](/windows/win32/inputdev/wm-mousemove) 창으로 전달하거나 사용하지 않도록 설정합니다.|
|[CPagerCtrl::GetBkColor](#getbkcolor)|현재 호출기 컨트롤의 배경색을 검색합니다.|
|[CPagerCtrl::GetBorder](#getborder)|현재 호출기 컨트롤의 테두리 크기를 검색합니다.|
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|현재 호출기 컨트롤의 단추 크기를 검색합니다.|
|[CPagerCtrl::GetButton상태](#getbuttonstate)|현재 호출기 컨트롤에서 지정된 단추의 상태를 검색합니다.|
|[CPagerCtrl::GetDropTarget](#getdroptarget)|현재 호출기 컨트롤에 대 한 [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) 인터페이스를 검색합니다.|
|[CPagerCtrl::Get스크롤포스](#getscrollpos)|현재 호출기 컨트롤의 스크롤 위치를 검색합니다.|
|[CPagerCtrl::이버튼 우울](#isbuttondepressed)|현재 호출기 컨트롤의 `pressed` 지정된 단추상태가 있는지 여부를 나타냅니다.|
|[CPagerCtrl::이버튼그레이드](#isbuttongrayed)|현재 호출기 컨트롤의 `grayed` 지정된 단추상태가 있는지 여부를 나타냅니다.|
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|현재 호출기 컨트롤의 `hot` 지정된 단추상태가 있는지 여부를 나타냅니다.|
|[CPagerCtrl::이 버튼 보이지 않는](#isbuttoninvisible)|현재 호출기 컨트롤의 `invisible` 지정된 단추상태가 있는지 여부를 나타냅니다.|
|[CPagerCtrl::IsButton 일반](#isbuttonnormal)|현재 호출기 컨트롤의 `normal` 지정된 단추상태가 있는지 여부를 나타냅니다.|
|[CPagerCtrl::리칼크사이즈](#recalcsize)|현재 호출기 컨트롤이 포함된 창의 크기를 다시 계산하도록 합니다.|
|[CPagerCtrl::SetBkColor](#setbkcolor)|현재 호출기 컨트롤의 배경 색을 설정합니다.|
|[CPagerCtrl:::세트 보더](#setborder)|현재 호출기 컨트롤의 테두리 크기를 설정합니다.|
|[CPagerCtrl::설정 단추 크기](#setbuttonsize)|현재 호출기 컨트롤의 단추 크기를 설정합니다.|
|[CPagerCtrl::세트차일드](#setchild)|현재 호출기 컨트롤에 대해 포함된 창을 설정합니다.|
|[CPagerCtrl::세트스크롤포스](#setscrollpos)|현재 호출기 컨트롤의 스크롤 위치를 설정합니다.|

## <a name="remarks"></a>설명

호출기 컨트롤은 포함된 창보다 선형이고 큰 다른 창을 포함하는 창이며 포함된 창을 보기로 스크롤할 수 있는 창입니다. 호출기 컨트롤에는 포함된 창이 가장 먼 범위로 스크롤될 때 자동으로 사라지고 그렇지 않으면 다시 나타나는 두 개의 스크롤 버튼이 표시됩니다. 가로 또는 세로로 스크롤하는 호출기 컨트롤을 만들 수 있습니다.

예를 들어 응용 프로그램에 모든 항목을 표시할 수 있을 만큼 넓지 않은 도구 모음이 있는 경우 호출기 컨트롤에 도구 모음을 할당할 수 있으며 사용자는 도구 모음을 왼쪽 또는 오른쪽으로 스크롤하여 모든 항목에 액세스할 수 있습니다. 마이크로소프트 인터넷 익스플로러 버전 4.0 (commctrl.dll 버전 4.71) 호출기 컨트롤을 소개 합니다.

클래스는 `CPagerCtrl` [CWnd](../../mfc/reference/cwnd-class.md) 클래스에서 파생됩니다. 자세한 정보 및 호출기 컨트롤의 그림을 보려면 [호출기 컨트롤](/windows/win32/Controls/pager-controls)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPagerCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="cpagerctrlcpagerctrl"></a><a name="cpagerctrl"></a>CPagerCtrl:::CPagerCtrl

`CPagerCtrl` 개체를 생성합니다.

```
CPagerCtrl();
```

### <a name="remarks"></a>설명

[CPagerCtrl::만들기](#create) 또는 [CPagerCtrl:CreateEx](#createex) 메서드를 사용하여 호출기 컨트롤을 만들고 `CPagerCtrl` 개체에 연결합니다.

## <a name="cpagerctrlcreate"></a><a name="create"></a>CPagerCtrl::만들기

지정된 스타일로 호출기 컨트롤을 만들고 현재 `CPagerCtrl` 개체에 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*dwStyle*|【인】 컨트롤에 적용할 [창 스타일과](../../mfc/reference/styles-used-by-mfc.md#window-styles) [호출기 컨트롤 스타일의](/windows/win32/Controls/pager-control-styles) 비트 조합(OR)입니다.|
|*rect*|【인】 클라이언트 좌표에서 컨트롤의 위치와 크기를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.|
|*pParentWnd*|【인】 컨트롤의 상위 창인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터입니다. 이 매개 변수는 NULL일 수 없습니다.|
|*nID*|【인】 컨트롤의 ID입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

호출기 컨트롤을 만들려면 `CPagerCtrl` 변수를 선언 한 다음 해당 변수에 [CPagerCtrl::만들기](#create) 또는 [CPagerCtrl:CreateEx](#createex) 메서드를 호출 합니다.

### <a name="example"></a>예제

다음 예제에서는 호출기 컨트롤을 만들고 [CPagerCtrl:SetChild](#setchild) 메서드를 사용하여 매우 긴 단추 컨트롤을 호출기 컨트롤과 연결합니다. 그런 다음 이 예제에서는 [CPagerCtrl:SetButtonSize](#setbuttonsize) 메서드를 사용하여 호출기 컨트롤의 높이를 20픽셀로 설정하고 [CPagerCtrl::SetBorder](#setborder) 메서드를 사용하여 테두리 두께를 1픽셀로 설정합니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlcreateex"></a><a name="createex"></a>CPagerCtrl::만들기

지정된 확장 된 스타일을 사용하여 호출기 컨트롤을 `CPagerCtrl` 만들고 현재 개체에 연결합니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*dwExStyle*|【인】 컨트롤에 적용할 확장 된 스타일의 비트 조합입니다. 자세한 내용은 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) 함수의 *dwExStyle* 매개 변수를 참조하십시오.|
|*dwStyle*|【인】 컨트롤에 적용할 [창 스타일과](../../mfc/reference/styles-used-by-mfc.md#window-styles) [호출기 컨트롤 스타일의](/windows/win32/Controls/pager-control-styles) 비트 조합(OR)입니다.|
|*rect*|【인】 클라이언트 좌표에서 컨트롤의 위치와 크기를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.|
|*pParentWnd*|【인】 컨트롤의 상위 창인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터입니다. 이 매개 변수는 NULL일 수 없습니다.|
|*nID*|【인】 컨트롤의 ID입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

호출기 컨트롤을 만들려면 `CPagerCtrl` 변수를 선언 한 다음 해당 변수에 [CPagerCtrl::만들기](#create) 또는 [CPagerCtrl:CreateEx](#createex) 메서드를 호출 합니다.

## <a name="cpagerctrlforwardmouse"></a><a name="forwardmouse"></a>CPagerCtrl::포워드 마우스

현재 호출기 컨트롤에 포함된 WM_MOUSEMOVE [메시지를](/windows/win32/inputdev/wm-mousemove) 창으로 전달하거나 사용하지 않도록 설정합니다.

```cpp
void ForwardMouse(BOOL bForward);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*b앞으로*|【인】 TRUE는 마우스 메시지를 전달하거나 FALSE는 마우스 메시지를 전달하지 않습니다.|

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_FORWARDMOUSE](/windows/win32/Controls/pgm-forwardmouse) 메시지를 보냅니다.

## <a name="cpagerctrlgetborder"></a><a name="getborder"></a>CPagerCtrl::GetBorder

현재 호출기 컨트롤의 테두리 크기를 검색합니다.

```
int GetBorder() const;
```

### <a name="return-value"></a>Return Value

픽셀단위로 측정된 현재 테두리 크기입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_GETBORDER](/windows/win32/Controls/pgm-getborder) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 예제에서는 [CPagerCtrl::GetBorder](#getborder) 메서드를 사용 하 여 호출기 컨트롤의 테두리의 두께 검색합니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]

## <a name="cpagerctrlgetbkcolor"></a><a name="getbkcolor"></a>CPagerCtrl::GetBkColor

현재 호출기 컨트롤의 배경색을 검색합니다.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Return Value

호출기 컨트롤의 현재 배경 색을 포함 하는 [COLORREF](/windows/win32/gdi/colorref) 값입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_GETBKCOLOR](/windows/win32/Controls/pgm-getbkcolor) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 예제에서는 [CPagerCtrl:SetBkColor](#setbkcolor) 메서드를 사용 하 여 호출기 컨트롤의 배경 색을 빨간색으로 설정 하 고 [CPagerCtrl:GetBkColor](#getbkcolor) 메서드를 사용 하 여 변경 되었습니다 확인 합니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

## <a name="cpagerctrlgetbuttonsize"></a><a name="getbuttonsize"></a>CPagerCtrl::GetButtonSize

현재 호출기 컨트롤의 단추 크기를 검색합니다.

```
int GetButtonSize() const;
```

### <a name="return-value"></a>Return Value

픽셀 단위로 측정되는 현재 단추 크기입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_GETBUTTONSIZE](/windows/win32/Controls/pgm-getbuttonsize) 메시지를 보냅니다.

호출기 컨트롤에 PGS_HORZ 스타일이 있는 경우 단추 크기는 호출기 단추의 너비를 결정하고 호출기 컨트롤에 PGS_VERT 스타일이 있는 경우 단추 크기는 호출기 단추의 높이를 결정합니다. 자세한 내용은 [페이저 제어 스타일을](/windows/win32/Controls/pager-control-styles)참조하십시오.

## <a name="cpagerctrlgetbuttonstate"></a><a name="getbuttonstate"></a>CPagerCtrl::GetButton상태

현재 호출기 컨트롤에서 지정된 스크롤 단추의 상태를 검색합니다.

```
DWORD GetButtonState(int iButton) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*iButton*|【인】 상태가 검색되는 단추를 나타냅니다. 호출기 컨트롤 스타일이 PGS_HORZ 경우 왼쪽 단추에 PGB_TOPORLEFT 지정하고 오른쪽 단추의 PGB_BOTTOMORRIGHT 지정합니다. 호출기 컨트롤 스타일이 PGS_VERT 경우 위쪽 단추의 PGB_TOPORLEFT 지정하고 아래쪽 단추의 PGB_BOTTOMORRIGHT. 자세한 내용은 [페이저 제어 스타일을](/windows/win32/Controls/pager-control-styles)참조하십시오.|

### <a name="return-value"></a>Return Value

*iButton* 매개 변수에 의해 지정 된 단추의 상태입니다. 상태는 PGF_INVISIBLE, PGF_NORMAL, PGF_GRAYED, PGF_DEPRESSED 또는 PGF_HOT. 자세한 내용은 [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) 메시지의 반환 값 섹션을 참조하십시오.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) 메시지를 보냅니다.

## <a name="cpagerctrlgetdroptarget"></a><a name="getdroptarget"></a>CPagerCtrl::GetDropTarget

현재 호출기 컨트롤에 대 한 [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) 인터페이스를 검색합니다.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Return Value

현재 호출기 `IDropTarget` 컨트롤의 인터페이스에 대한 포인터입니다.

### <a name="remarks"></a>설명

`IDropTarget`는 응용 프로그램에서 끌어서 놓기 작업을 지원하기 위해 구현하는 인터페이스 중 하나입니다.

이 메서드는 Windows SDK에 설명 된 [PGM_GETDROPTARGET](/windows/win32/Controls/pgm-getdroptarget) 메시지를 보냅니다. 이 메서드의 호출자는 인터페이스가 `Release` 더 이상 필요하지 않은 경우 [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) 인터페이스의 멤버를 호출해야 합니다.

## <a name="cpagerctrlgetscrollpos"></a><a name="getscrollpos"></a>CPagerCtrl::Get스크롤포스

현재 호출기 컨트롤의 스크롤 위치를 검색합니다.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Return Value

픽셀 단위로 측정된 현재 스크롤 위치입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_GETPOS](/windows/win32/Controls/pgm-getpos) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 예제에서는 [CPagerCtrl::GetScrollPos](#getscrollpos) 메서드를 사용 하 여 호출기 컨트롤의 현재 스크롤 위치를 검색합니다. 호출기 컨트롤이 아직 0으로 스크롤되지 않은 경우 가장 왼쪽 위치인 이 예제에서는 [CPagerCtrl::SetScrollPos](#setscrollpos) 메서드를 사용하여 스크롤 위치를 0으로 설정합니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]

## <a name="cpagerctrlisbuttondepressed"></a><a name="isbuttondepressed"></a>CPagerCtrl::이버튼 우울

현재 호출기 컨트롤의 지정된 스크롤 단추를 누른 상태인지 여부를 나타냅니다.

```
BOOL IsButtonDepressed(int iButton) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*iButton*|【인】 상태가 검색되는 단추를 나타냅니다. 호출기 컨트롤 스타일이 PGS_HORZ 경우 왼쪽 단추에 PGB_TOPORLEFT 지정하고 오른쪽 단추의 PGB_BOTTOMORRIGHT 지정합니다. 호출기 컨트롤 스타일이 PGS_VERT 경우 위쪽 단추의 PGB_TOPORLEFT 지정하고 아래쪽 단추의 PGB_BOTTOMORRIGHT. 자세한 내용은 [페이저 제어 스타일을](/windows/win32/Controls/pager-control-styles)참조하십시오.|

### <a name="return-value"></a>Return Value

TRUE 지정된 단추를 누른 상태인 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) 메시지를 보냅니다. 그런 다음 반환되는 상태가 PGF_DEPRESSED 있는지 여부를 테스트합니다. 자세한 내용은 [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) 메시지의 반환 값 섹션을 참조하십시오.

## <a name="cpagerctrlisbuttongrayed"></a><a name="isbuttongrayed"></a>CPagerCtrl::이버튼그레이드

현재 호출기 컨트롤의 지정된 스크롤 단추가 회색 상태인지 여부를 나타냅니다.

```
BOOL IsButtonGrayed(int iButton) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*iButton*|【인】 상태가 검색되는 단추를 나타냅니다. 호출기 컨트롤 스타일이 PGS_HORZ 경우 왼쪽 단추에 PGB_TOPORLEFT 지정하고 오른쪽 단추의 PGB_BOTTOMORRIGHT 지정합니다. 호출기 컨트롤 스타일이 PGS_VERT 경우 위쪽 단추의 PGB_TOPORLEFT 지정하고 아래쪽 단추의 PGB_BOTTOMORRIGHT. 자세한 내용은 [페이저 제어 스타일을](/windows/win32/Controls/pager-control-styles)참조하십시오.|

### <a name="return-value"></a>Return Value

TRUE 지정된 단추가 회색 상태인 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) 메시지를 보냅니다. 그런 다음 반환되는 상태가 PGF_GRAYED 여부를 테스트합니다. 자세한 내용은 [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) 메시지의 반환 값 섹션을 참조하십시오.

## <a name="cpagerctrlisbuttonhot"></a><a name="isbuttonhot"></a>CPagerCtrl::IsButtonHot

현재 호출기 컨트롤의 지정된 스크롤 단추가 핫 상태에 있는지 여부를 나타냅니다.

```
BOOL IsButtonHot(int iButton) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*iButton*|【인】 상태가 검색되는 단추를 나타냅니다. 호출기 컨트롤 스타일이 PGS_HORZ 경우 왼쪽 단추에 PGB_TOPORLEFT 지정하고 오른쪽 단추의 PGB_BOTTOMORRIGHT 지정합니다. 호출기 컨트롤 스타일이 PGS_VERT 경우 위쪽 단추의 PGB_TOPORLEFT 지정하고 아래쪽 단추의 PGB_BOTTOMORRIGHT. 자세한 내용은 [페이저 제어 스타일을](/windows/win32/Controls/pager-control-styles)참조하십시오.|

### <a name="return-value"></a>Return Value

TRUE 지정된 단추가 핫 상태에 있는 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) 메시지를 보냅니다. 그런 다음 반환되는 상태가 PGF_HOT 여부를 테스트합니다. 자세한 내용은 [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) 메시지의 반환 값 섹션을 참조하십시오.

## <a name="cpagerctrlisbuttoninvisible"></a><a name="isbuttoninvisible"></a>CPagerCtrl::이 버튼 보이지 않는

현재 호출기 컨트롤의 지정된 스크롤 단추가 보이지 않는 상태인지 여부를 나타냅니다.

```
BOOL IsButtonInvisible(int iButton) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*iButton*|【인】 상태가 검색되는 단추를 나타냅니다. 호출기 컨트롤 스타일이 PGS_HORZ 경우 왼쪽 단추에 PGB_TOPORLEFT 지정하고 오른쪽 단추의 PGB_BOTTOMORRIGHT 지정합니다. 호출기 컨트롤 스타일이 PGS_VERT 경우 위쪽 단추의 PGB_TOPORLEFT 지정하고 아래쪽 단추의 PGB_BOTTOMORRIGHT. 자세한 내용은 [페이저 제어 스타일을](/windows/win32/Controls/pager-control-styles)참조하십시오.|

### <a name="return-value"></a>Return Value

TRUE 지정된 단추가 보이지 않는 상태인 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

Windows는 포함된 창을 가장 먼 범위로 스크롤할 때 특정 방향으로 스크롤 단추를 표시하지 않게 합니다.

이 메서드는 Windows SDK에 설명 된 [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) 메시지를 보냅니다. 그런 다음 반환되는 상태가 PGF_INVISIBLE 있는지 여부를 테스트합니다. 자세한 내용은 [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) 메시지의 반환 값 섹션을 참조하십시오.

### <a name="example"></a>예제

다음 예제에서는 [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible) 메서드를 사용하여 호출기 컨트롤의 왼쪽 및 오른쪽 스크롤 단추를 볼 수 있는지 여부를 확인합니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]

## <a name="cpagerctrlisbuttonnormal"></a><a name="isbuttonnormal"></a>CPagerCtrl::IsButton 일반

현재 호출기 컨트롤의 지정된 스크롤 단추가 정상 상태인지 여부를 나타냅니다.

```
BOOL IsButtonNormal(int iButton) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*iButton*|【인】 상태가 검색되는 단추를 나타냅니다. 호출기 컨트롤 스타일이 PGS_HORZ 경우 왼쪽 단추에 PGB_TOPORLEFT 지정하고 오른쪽 단추의 PGB_BOTTOMORRIGHT 지정합니다. 호출기 컨트롤 스타일이 PGS_VERT 경우 위쪽 단추의 PGB_TOPORLEFT 지정하고 아래쪽 단추의 PGB_BOTTOMORRIGHT. 자세한 내용은 [페이저 제어 스타일을](/windows/win32/Controls/pager-control-styles)참조하십시오.|

### <a name="return-value"></a>Return Value

TRUE 지정된 단추가 정상 상태인 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) 메시지를 보냅니다. 그런 다음 반환되는 상태가 PGF_NORMAL 있는지 여부를 테스트합니다. 자세한 내용은 [PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate) 메시지의 반환 값 섹션을 참조하십시오.

## <a name="cpagerctrlrecalcsize"></a><a name="recalcsize"></a>CPagerCtrl::리칼크사이즈

현재 호출기 컨트롤이 포함된 창의 크기를 다시 계산하도록 합니다.

```cpp
void RecalcSize();
```

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_RECALCSIZE](/windows/win32/Controls/pgm-recalcsize) 메시지를 보냅니다. 따라서 호출기 컨트롤은 [PGN_CALCSIZE](/windows/win32/Controls/pgn-calcsize) 알림을 보내 포함된 창의 스크롤 가능한 크기를 가져옵니다.

### <a name="example"></a>예제

다음 예제에서는 [CPagerCtrl::RecalcSize](#recalcsize) 메서드를 사용하여 현재 호출기 컨트롤을 요청하여 크기를 다시 계산합니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]

### <a name="example"></a>예제

다음 예제에서는 [메시지 리플렉션을](../../mfc/tn062-message-reflection-for-windows-controls.md) 사용하여 호출기 컨트롤이 계산을 수행하기 위해 컨트롤의 상위 대화 상자를 요구하는 대신 자체 크기를 다시 계산할 수 있도록 합니다. 이 예제는 `MyPagerCtrl` [CPagerCtrl 클래스에서 클래스를](../../mfc/reference/cpagerctrl-class.md)파생한 다음 메시지 [PGN_CALCSIZE](/windows/win32/Controls/pgn-calcsize) 맵을 `OnCalcsize` 사용하여 PGN_CALCSIZE 알림을 알림 처리기와 연결합니다. 이 예제에서 알림 처리기는 호출기 컨트롤의 너비와 높이를 고정값으로 설정합니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]

## <a name="cpagerctrlsetbkcolor"></a><a name="setbkcolor"></a>CPagerCtrl::SetBkColor

현재 호출기 컨트롤의 배경 색을 설정합니다.

```
COLORREF SetBkColor(COLORREF clrBk);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*clrBk*|【인】 호출기 컨트롤의 새 배경 색을 포함 하는 [COLORREF](/windows/win32/gdi/colorref) 값입니다.|

### <a name="return-value"></a>Return Value

호출기 컨트롤의 이전 배경 색을 포함 하는 [COLORREF](/windows/win32/gdi/colorref) 값입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_SETBKCOLOR](/windows/win32/Controls/pgm-setbkcolor) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 예제에서는 [CPagerCtrl:SetBkColor](#setbkcolor) 메서드를 사용 하 여 호출기 컨트롤의 배경 색을 빨간색으로 설정 하 고 [CPagerCtrl:GetBkColor](#getbkcolor) 메서드를 사용 하 여 변경 되었습니다 확인 합니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

## <a name="cpagerctrlsetborder"></a><a name="setborder"></a>CPagerCtrl:::세트 보더

현재 호출기 컨트롤의 테두리 크기를 설정합니다.

```
int SetBorder(int iBorder);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*아이 보더*|【인】 픽셀 단위로 측정된 새 테두리 크기입니다. *iBorder* 매개 변수가 음수이면 테두리 크기가 0으로 설정됩니다.|

### <a name="return-value"></a>Return Value

픽셀단위로 측정된 이전 테두리 크기입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_SETBORDER](/windows/win32/Controls/pgm-setborder) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 예제에서는 호출기 컨트롤을 만들고 [CPagerCtrl:SetChild](#setchild) 메서드를 사용하여 매우 긴 단추 컨트롤을 호출기 컨트롤과 연결합니다. 그런 다음 이 예제에서는 [CPagerCtrl:SetButtonSize](#setbuttonsize) 메서드를 사용하여 호출기 컨트롤의 높이를 20픽셀로 설정하고 [CPagerCtrl::SetBorder](#setborder) 메서드를 사용하여 테두리 두께를 1픽셀로 설정합니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetbuttonsize"></a><a name="setbuttonsize"></a>CPagerCtrl::설정 단추 크기

현재 호출기 컨트롤의 단추 크기를 설정합니다.

```
int SetButtonSize(int iButtonSize);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*아이 버튼 사이즈*|【인】 픽셀 단위로 측정된 새 단추 크기입니다.|

### <a name="return-value"></a>Return Value

픽셀 단위로 측정된 이전 단추 크기입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_SETBUTTONSIZE](/windows/win32/Controls/pgm-setpos) 메시지를 보냅니다.

호출기 컨트롤에 PGS_HORZ 스타일이 있는 경우 단추 크기는 호출기 단추의 너비를 결정하고 호출기 컨트롤에 PGS_VERT 스타일이 있는 경우 단추 크기는 호출기 단추의 높이를 결정합니다. 기본 단추 크기는 스크롤 막대 너비의 3/4이며 최소 단추 크기는 12픽셀입니다. 자세한 내용은 [페이저 제어 스타일을](/windows/win32/Controls/pager-control-styles)참조하십시오.

### <a name="example"></a>예제

다음 예제에서는 호출기 컨트롤을 만들고 [CPagerCtrl:SetChild](#setchild) 메서드를 사용하여 매우 긴 단추 컨트롤을 호출기 컨트롤과 연결합니다. 그런 다음 이 예제에서는 [CPagerCtrl:SetButtonSize](#setbuttonsize) 메서드를 사용하여 호출기 컨트롤의 높이를 20픽셀로 설정하고 [CPagerCtrl::SetBorder](#setborder) 메서드를 사용하여 테두리 두께를 1픽셀로 설정합니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetchild"></a><a name="setchild"></a>CPagerCtrl::세트차일드

현재 호출기 컨트롤에 대해 포함된 창을 설정합니다.

```cpp
void SetChild(HWND hwndChild);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*hwndChild*|【인】 포함할 창에 핸들을 보입니다.|

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_SETCHILD](/windows/win32/Controls/pgm-setchild) 메시지를 보냅니다.

이 메서드는 포함된 창의 부모를 변경하지 않습니다. 스크롤을 위해 호출기 컨트롤에 창 핸들만 할당합니다. 대부분의 경우 포함된 창은 호출기 컨트롤의 자식 창이 됩니다.

### <a name="example"></a>예제

다음 예제에서는 호출기 컨트롤을 만들고 [CPagerCtrl:SetChild](#setchild) 메서드를 사용하여 매우 긴 단추 컨트롤을 호출기 컨트롤과 연결합니다. 그런 다음 이 예제에서는 [CPagerCtrl:SetButtonSize](#setbuttonsize) 메서드를 사용하여 호출기 컨트롤의 높이를 20픽셀로 설정하고 [CPagerCtrl::SetBorder](#setborder) 메서드를 사용하여 테두리 두께를 1픽셀로 설정합니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetscrollpos"></a><a name="setscrollpos"></a>CPagerCtrl::세트스크롤포스

현재 호출기 컨트롤의 스크롤 위치를 설정합니다.

```cpp
void SetScrollPos(int iPos);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*Ipos*|【인】 픽셀 단위로 측정된 새 스크롤 위치입니다.|

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PGM_SETPOS](/windows/win32/Controls/pgm-setpos) 메시지를 보냅니다.

## <a name="see-also"></a>참조

[CPagerCtrl 클래스](../../mfc/reference/cpagerctrl-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[호출기 컨트롤](/windows/win32/Controls/pager-controls)
