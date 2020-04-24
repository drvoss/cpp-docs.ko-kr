---
title: CStatusBarCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
- AFXCMN/CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::Create
- AFXCMN/CStatusBarCtrl::CreateEx
- AFXCMN/CStatusBarCtrl::DrawItem
- AFXCMN/CStatusBarCtrl::GetBorders
- AFXCMN/CStatusBarCtrl::GetIcon
- AFXCMN/CStatusBarCtrl::GetParts
- AFXCMN/CStatusBarCtrl::GetRect
- AFXCMN/CStatusBarCtrl::GetText
- AFXCMN/CStatusBarCtrl::GetTextLength
- AFXCMN/CStatusBarCtrl::GetTipText
- AFXCMN/CStatusBarCtrl::IsSimple
- AFXCMN/CStatusBarCtrl::SetBkColor
- AFXCMN/CStatusBarCtrl::SetIcon
- AFXCMN/CStatusBarCtrl::SetMinHeight
- AFXCMN/CStatusBarCtrl::SetParts
- AFXCMN/CStatusBarCtrl::SetSimple
- AFXCMN/CStatusBarCtrl::SetText
- AFXCMN/CStatusBarCtrl::SetTipText
helpviewer_keywords:
- CStatusBarCtrl [MFC], CStatusBarCtrl
- CStatusBarCtrl [MFC], Create
- CStatusBarCtrl [MFC], CreateEx
- CStatusBarCtrl [MFC], DrawItem
- CStatusBarCtrl [MFC], GetBorders
- CStatusBarCtrl [MFC], GetIcon
- CStatusBarCtrl [MFC], GetParts
- CStatusBarCtrl [MFC], GetRect
- CStatusBarCtrl [MFC], GetText
- CStatusBarCtrl [MFC], GetTextLength
- CStatusBarCtrl [MFC], GetTipText
- CStatusBarCtrl [MFC], IsSimple
- CStatusBarCtrl [MFC], SetBkColor
- CStatusBarCtrl [MFC], SetIcon
- CStatusBarCtrl [MFC], SetMinHeight
- CStatusBarCtrl [MFC], SetParts
- CStatusBarCtrl [MFC], SetSimple
- CStatusBarCtrl [MFC], SetText
- CStatusBarCtrl [MFC], SetTipText
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
ms.openlocfilehash: 57d040a7efd87d384e0aaa6275593bc91f38cc86
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753040"
---
# <a name="cstatusbarctrl-class"></a>CStatusBarCtrl 클래스

Windows의 공용 상태 표시줄 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CStatusBarCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|`CStatusBarCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CStatusBarCtrl::만들기](#create)|상태 표시줄 컨트롤을 만들고 개체에 `CStatusBarCtrl` 연결합니다.|
|[CStatusBarCtrl::만들기](#createex)|지정된 Windows 확장 스타일을 사용하여 상태 표시줄 컨트롤을 `CStatusBarCtrl` 만들고 개체에 연결합니다.|
|[CStatusBarCtrl::D원시항목](#drawitem)|소유자-그리기 상태 표시줄 컨트롤의 시각적 측면이 변경 될 때 호출 됩니다.|
|[CStatusBarCtrl::GetBorders](#getborders)|상태 표시줄 컨트롤의 가로 및 세로 테두리의 현재 너비를 검색합니다.|
|[CStatusBarCtrl::GetIcon](#geticon)|현재 상태 표시줄 컨트롤에서 부품(창이라고도 함)에 대한 아이콘을 검색합니다.|
|[CStatusBarCtrl::Get부품](#getparts)|상태 표시줄 컨트롤에서 부품 수를 검색합니다.|
|[CStatusBarCtrl::GetRect](#getrect)|상태 표시줄 컨트롤에서 부품의 경계 사각형을 검색합니다.|
|[CStatusBarCtrl::GetText](#gettext)|상태 표시줄 컨트롤의 지정된 부분에서 텍스트를 검색합니다.|
|[CStatusBarCtrl::GetText길이](#gettextlength)|상태 표시줄 컨트롤의 지정된 부분에서 텍스트의 길이(문자)를 검색합니다.|
|[CStatusBarCtrl::GetTipText](#gettiptext)|상태 표시줄에서 창에 대한 도구 설명 텍스트를 검색합니다.|
|[CStatusBarCtrl::IsSimple](#issimple)|상태 창 컨트롤을 확인하여 단순 모드인지 확인합니다.|
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|상태 표시줄에서 배경색을 설정합니다.|
|[CStatusBarCtrl::세티콘](#seticon)|상태 표시줄에서 창아이콘을 설정합니다.|
|[CStatusBarCtrl::SetMinHeight](#setminheight)|상태 표시줄 컨트롤의 도면 영역의 최소 높이를 설정합니다.|
|[CStatusBarCtrl::세트부품](#setparts)|상태 표시줄 컨트롤의 부품 수와 각 부품의 오른쪽 모서리 좌표를 설정합니다.|
|[CStatusBarCtrl::설정 간단](#setsimple)|상태 표시줄 컨트롤이 간단한 텍스트를 표시할지 또는 이전 호출에 `SetParts`의해 설정된 모든 컨트롤 파트를 표시할지 여부를 지정합니다.|
|[C상태바Ctrl::SetText](#settext)|상태 표시줄 컨트롤의 특정 부분에서 텍스트를 설정합니다.|
|[C상태바Ctrl::SetTipText](#settiptext)|상태 표시줄에서 창에 대한 도구 설명 텍스트를 설정합니다.|

## <a name="remarks"></a>설명

"상태 표시줄 컨트롤"은 일반적으로 부모 창의 맨 아래에 표시되는 가로 창으로, 응용 프로그램에서 다양한 종류의 상태 정보를 표시할 수 있습니다. 상태 표시줄 컨트롤은 부분으로 나누어 두 개 이상의 정보 유형을 표시할 수 있습니다.

이 컨트롤(및 `CStatusBarCtrl` 따라서 클래스)은 Windows 95/98 및 Windows NT 버전 3.51 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.

사용에 `CStatusBarCtrl`대한 자세한 내용은 [컨트롤](../../mfc/controls-mfc.md) 및 [CStatusBarCtrl 사용](../../mfc/using-cstatusbarctrl.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatusBarCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="cstatusbarctrlcreate"></a><a name="create"></a>CStatusBarCtrl::만들기

상태 표시줄 컨트롤을 만들고 개체에 `CStatusBarCtrl` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
상태 표시줄 컨트롤의 스타일을 지정합니다. Windows SDK의 [공통 제어](/windows/win32/Controls/common-control-styles) 스타일에 나열된 상태 표시줄 컨트롤 스타일의 조합을 적용합니다. 이 매개변수에는 WS_CHILD 스타일이 포함되어야 합니다. 또한 WS_VISIBLE 스타일을 포함해야 합니다.

*rect*<br/>
상태 표시줄 컨트롤의 크기와 위치를 지정합니다. [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조일 수 있습니다.

*pParentWnd*<br/>
상태 표시줄 컨트롤의 부모 창(일반적으로 `CDialog`을 지정합니다.) NULL이 아니어야 합니다.

*nID*<br/>
상태 표시줄 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 단계로 `CStatusBarCtrl` 구성합니다. 먼저 생성자 호출 한 다음 `Create`상태 표시줄 컨트롤을 만들고 `CStatusBarCtrl` 개체에 연결 하는 호출 합니다.

상태 창의 기본 위치는 부모 창의 아래쪽을 따라 있지만 부모 창의 클라이언트 영역 맨 위에 표시되도록 CCS_TOP 스타일을 지정할 수 있습니다. 상태 창의 오른쪽 끝에 크기 조정 그립을 포함하도록 SBARS_SIZEGRIP 스타일을 지정할 수 있습니다. 시스템이 상태 창에서 CCS_TOP SBARS_SIZEGRIP 그리는 경우에도 결과 크기 조정 그립이 작동하지 않으므로 CCS_TOP 및 SBARS_SIZEGRIP 스타일을 결합하는 것은 권장되지 않습니다.

확장 된 창 스타일을 가진 상태 표시줄을 만들려면 [CStatusBarCtrl::CreateEx](#createex) 대신 `Create`호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]

## <a name="cstatusbarctrlcreateex"></a><a name="createex"></a>CStatusBarCtrl::만들기

컨트롤(하위 창)을 만들고 `CStatusBarCtrl` 개체와 연결합니다.

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
상태 표시줄 컨트롤의 스타일을 지정합니다. Windows SDK의 [공통 제어](/windows/win32/Controls/common-control-styles) 스타일에 나열된 상태 표시줄 컨트롤 스타일의 조합을 적용합니다. 이 매개변수에는 WS_CHILD 스타일이 포함되어야 합니다. 또한 WS_VISIBLE 스타일을 포함해야 합니다.

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

## <a name="cstatusbarctrlcstatusbarctrl"></a><a name="cstatusbarctrl"></a>CStatusBarCtrl::CStatusBarCtrl

`CStatusBarCtrl` 개체를 생성합니다.

```
CStatusBarCtrl();
```

## <a name="cstatusbarctrldrawitem"></a><a name="drawitem"></a>CStatusBarCtrl::D원시항목

소유자-그리기 상태 표시줄 컨트롤의 시각적 측면이 변경될 때 프레임워크에서 호출됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
필요한 도면 유형에 대한 정보가 포함된 [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 구조에 대한 긴 포인터입니다.

### <a name="remarks"></a>설명

`DRAWITEMSTRUCT` 구조의 멤버는 `itemAction` 수행할 드로잉 작업을 정의합니다.

기본적으로 이 멤버 함수는 아무 것도 수행하지 않습니다. 이 멤버 함수를 재정의하여 소유자-그리기 객체에 대한 그리기를 구현합니다. `CStatusBarCtrl`

응용 프로그램은 이 멤버 함수가 종료되기 전에 *lpDrawItemStruct에서* 제공된 디스플레이 컨텍스트에 대해 선택된 모든 GDI(그래픽 장치 인터페이스) 개체를 복원해야 합니다.

## <a name="cstatusbarctrlgetborders"></a><a name="getborders"></a>CStatusBarCtrl::GetBorders

상태 표시줄 컨트롤의 현재 너비와 가로 및 세로 테두리및 사각형 사이의 공간을 검색합니다.

```
BOOL GetBorders(int* pBorders) const;

BOOL GetBorders(
    int& nHorz,
    int& nVert,
    int& nSpacing) const;
```

### <a name="parameters"></a>매개 변수

*국경*<br/>
세 가지 요소가 있는 정수 배열의 주소입니다. 첫 번째 요소는 가로 테두리의 너비를 받고 두 번째 요소는 세로 테두리의 너비를 받고 세 번째 요소는 사각형 사이의 테두리 너비를 받습니다.

*n호르츠 (것)엔호르츠*<br/>
가로 테두리의 너비를 받는 정수를 참조합니다.

*n버트*<br/>
세로 테두리의 너비를 받는 정수를 참조합니다.

*n 간격*<br/>
사각형 사이의 테두리 너비를 받는 정수를 참조합니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이러한 테두리는 컨트롤의 외부 가장자리와 텍스트가 포함된 컨트롤 내의 사각형 사이의 간격을 결정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]

## <a name="cstatusbarctrlgeticon"></a><a name="geticon"></a>CStatusBarCtrl::GetIcon

현재 상태 표시줄 컨트롤에서 부품(창이라고도 함)에 대한 아이콘을 검색합니다.

```
HICON GetIcon(int iPart) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*아이 파트*|【인】 검색할 아이콘이 포함된 부품의 0기반 인덱스입니다. 이 매개 변수가 -1이면 상태 표시줄은 단순 모드 상태 표시줄로 가정합니다.|

### <a name="return-value"></a>Return Value

메서드가 성공하면 아이콘에 대한 핸들입니다. 그렇지 않으면 NULL이 됩니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [SB_GETICON](/windows/win32/Controls/sb-geticon) 메시지를 보냅니다.

상태 표시줄 컨트롤은 부품이라고도 하는 텍스트 출력 창 행으로 구성됩니다. 상태 표시줄에 대한 자세한 내용은 [MFC의 상태 표시줄 구현](../../mfc/status-bar-implementation-in-mfc.md) 및 [CStatusBarCtrl 개체의 모드 설정을](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)참조하십시오.

### <a name="example"></a>예제

다음 코드 예제에서는 현재 `m_statusBar`상태 표시줄 컨트롤에 액세스하는 데 사용되는 변수 를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]

### <a name="example"></a>예제

다음 코드 예제는 현재 상태 표시줄 컨트롤의 두 창에 아이콘을 복사합니다. 코드 예제의 이전 섹션에서는 세 개의 창이 있는 상태 표시줄 컨트롤을 만든 다음 첫 번째 창에 아이콘을 추가했습니다. 이 예제는 첫 번째 창에서 아이콘을 검색한 다음 두 번째 및 세 번째 창에 추가합니다.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]

## <a name="cstatusbarctrlgetparts"></a><a name="getparts"></a>CStatusBarCtrl::Get부품

상태 표시줄 컨트롤에서 부품 수를 검색합니다.

```
int GetParts(
    int nParts,
    int* pParts) const;
```

### <a name="parameters"></a>매개 변수

*n부품*<br/>
좌표를 검색할 부품 수입니다. 이 매개변수가 컨트롤의 부품 수보다 크면 메시지는 기존 부품에 대해서만 좌표를 검색합니다.

*p부품*<br/>
*nParts에서*지정한 부품 수와 동일한 수의 요소를 갖는 정수 배열의 주소입니다. 배열의 각 요소는 해당 부품의 오른쪽 가장자리의 클라이언트 좌표를 받습니다. 요소가 -1로 설정된 경우 해당 부품의 오른쪽 모서리 의 위치는 상태 표시줄의 오른쪽 가장자리로 확장됩니다.

### <a name="return-value"></a>Return Value

성공한 경우 컨트롤의 부품 수 또는 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

또한 이 멤버 함수는 지정된 부품 수의 오른쪽 가장자리좌표를 검색합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]

## <a name="cstatusbarctrlgetrect"></a><a name="getrect"></a>CStatusBarCtrl::GetRect

상태 표시줄 컨트롤에서 부품의 경계 사각형을 검색합니다.

```
BOOL GetRect(
    int nPane,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*nPane*<br/>
경계 사각형을 검색할 부품의 0기반 인덱스입니다.

*Lprect*<br/>
경계 사각형을 받는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조의 주소입니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]

## <a name="cstatusbarctrlgettext"></a><a name="gettext"></a>CStatusBarCtrl::GetText

상태 표시줄 컨트롤의 지정된 부분에서 텍스트를 검색합니다.

```
CString GetText(
    int nPane,
    int* pType = NULL) const;

int GetText(
    LPCTSTR lpszText,
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
텍스트를 받는 버퍼의 주소입니다. 이 매개 변수는 null-종료된 문자열입니다.

*nPane*<br/>
텍스트를 검색할 부품의 0기반 인덱스입니다.

*p유형*<br/>
형식 정보를 수신하는 정수에 대한 포인터입니다. 형식은 다음 값 중 하나일 수 있습니다.

- **0** 상태 표시줄의 평면보다 낮은 테두리로 텍스트가 그려집니다.

- SBT_NOBORDERS 텍스트는 테두리 없이 그려집니다.

- SBT_POPOUT 상태 표시줄의 평면보다 높게 표시되도록 테두리로 텍스트가 그려집니다.

- SBT_OWNERDRAW 텍스트에 SBT_OWNERDRAW 그리기 유형이 있는 경우 *pType은* 이 메시지를 수신하고 길이 및 작업 유형 대신 텍스트와 연결된 32비트 값을 반환합니다.

### <a name="return-value"></a>Return Value

문자, 텍스트 또는 현재 텍스트를 포함하는 [CString의](../../atl-mfc-shared/reference/cstringt-class.md) 길이입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]

## <a name="cstatusbarctrlgettextlength"></a><a name="gettextlength"></a>CStatusBarCtrl::GetText길이

상태 표시줄 컨트롤의 지정된 부분에서 텍스트의 길이(문자)를 검색합니다.

```
int GetTextLength(
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>매개 변수

*nPane*<br/>
텍스트를 검색할 부품의 0기반 인덱스입니다.

*p유형*<br/>
형식 정보를 수신하는 정수에 대한 포인터입니다. 형식은 다음 값 중 하나일 수 있습니다.

- **0** 상태 표시줄의 평면보다 낮은 테두리로 텍스트가 그려집니다.

- SBT_NOBORDERS 텍스트는 테두리 없이 그려집니다.

- SBT_OWNERDRAW 텍스트는 부모 창에 의해 그려집니다.

- SBT_POPOUT 상태 표시줄의 평면보다 높게 표시되도록 테두리로 텍스트가 그려집니다.

### <a name="return-value"></a>Return Value

텍스트의 길이(문자)입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]

## <a name="cstatusbarctrlgettiptext"></a><a name="gettiptext"></a>CStatusBarCtrl::GetTipText

상태 표시줄에서 창에 대한 도구 설명 텍스트를 검색합니다.

```
CString GetTipText(int nPane) const;
```

### <a name="parameters"></a>매개 변수

*nPane*<br/>
도구 설명 텍스트를 수신할 상태 표시줄 창의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

도구 설명에 사용할 텍스트를 포함하는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 SB_GETTIPTEXT Win32 [메시지의](/windows/win32/Controls/sb-gettiptext)동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]

## <a name="cstatusbarctrlissimple"></a><a name="issimple"></a>CStatusBarCtrl::IsSimple

상태 창 컨트롤을 확인하여 단순 모드인지 확인합니다.

```
BOOL IsSimple() const;
```

### <a name="return-value"></a>Return Value

상태 창 컨트롤이 단순 모드인 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 SB_ISSIMPLE Win32 [메시지의](/windows/win32/Controls/sb-issimple)동작을 구현합니다.

## <a name="cstatusbarctrlsetbkcolor"></a><a name="setbkcolor"></a>CStatusBarCtrl::SetBkColor

상태 표시줄에서 배경색을 설정합니다.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>매개 변수

*Cr*<br/>
새 배경색을 지정하는 COLORREF 값입니다. 상태 표시줄이 기본 배경색을 사용하도록 CLR_DEFAULT 값을 지정합니다.

### <a name="return-value"></a>Return Value

이전 기본 배경색을 나타내는 [COLORREF](/windows/win32/gdi/colorref) 값입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 SB_SETBKCOLOR Win32 [메시지의](/windows/win32/Controls/sb-setbkcolor)동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]

## <a name="cstatusbarctrlseticon"></a><a name="seticon"></a>CStatusBarCtrl::세티콘

상태 표시줄에서 창아이콘을 설정합니다.

```
BOOL SetIcon(
    int nPane,
    HICON hIcon);
```

### <a name="parameters"></a>매개 변수

*nPane*<br/>
아이콘을 받을 창의 0기반 인덱스입니다. 이 매개 변수가 -1이면 상태 표시줄은 단순 상태 표시줄로 가정합니다.

*hIcon*<br/>
설정할 아이콘을 처리합니다. 이 값이 NULL이면 아이콘이 파트에서 제거됩니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 SB_SETICON Win32 [메시지의](/windows/win32/Controls/sb-seticon)동작을 구현합니다.

### <a name="example"></a>예제

  [CStatusBarCtrl::SetBkColor에](#setbkcolor)대한 예제를 참조하십시오.

## <a name="cstatusbarctrlsetminheight"></a><a name="setminheight"></a>CStatusBarCtrl::SetMinHeight

상태 표시줄 컨트롤의 도면 영역의 최소 높이를 설정합니다.

```cpp
void SetMinHeight(int nMin);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
컨트롤의 최소 높이(픽셀 단위)입니다.

### <a name="remarks"></a>설명

최소 높이는 *nMin의* 합이며 상태 표시줄 컨트롤의 세로 테두리의 너비(픽셀)의 두 배입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]

## <a name="cstatusbarctrlsetparts"></a><a name="setparts"></a>CStatusBarCtrl::세트부품

상태 표시줄 컨트롤의 부품 수와 각 부품의 오른쪽 모서리 좌표를 설정합니다.

```
BOOL SetParts(
    int nParts,
    int* pWidths);
```

### <a name="parameters"></a>매개 변수

*n부품*<br/>
설정할 부품 수입니다. 부품 수는 255를 초과할 수 없습니다.

*p너비*<br/>
*nParts에서*지정한 부품과 동일한 수의 요소를 갖는 정수 배열의 주소입니다. 배열의 각 요소는 해당 부품의 오른쪽 가장자리의 클라이언트 좌표에서 위치를 지정합니다. 요소가 1인 경우 해당 부품의 오른쪽 모서리 위치는 컨트롤의 오른쪽 가장자리로 확장됩니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]

## <a name="cstatusbarctrlsetsimple"></a><a name="setsimple"></a>CStatusBarCtrl::설정 간단

상태 표시줄 컨트롤이 간단한 텍스트를 표시할지 또는 [SetParts에](#setparts)대한 이전 호출에서 설정한 모든 컨트롤 파트를 표시할지 여부를 지정합니다.

```
BOOL SetSimple(BOOL bSimple = TRUE);
```

### <a name="parameters"></a>매개 변수

*b 심플*<br/>
【인】 표시 형 플래그입니다. 이 매개변수가 TRUE이면 컨트롤에 간단한 텍스트가 표시됩니다. FALSE이면 여러 부분이 표시됩니다.

### <a name="return-value"></a>Return Value

항상 0을 반환합니다.

### <a name="remarks"></a>설명

응용 프로그램에서 상태 표시줄 컨트롤을 단순하지 않은 컨트롤에서 단순으로 변경하거나 그 반대로 변경하면 시스템은 즉시 컨트롤을 다시 그립니다.

## <a name="cstatusbarctrlsettext"></a><a name="settext"></a>C상태바Ctrl::SetText

상태 표시줄 컨트롤의 특정 부분에서 텍스트를 설정합니다.

```
BOOL SetText(
    LPCTSTR lpszText,
    int nPane,
    int nType);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
설정할 텍스트를 지정하는 null 종료 문자열의 주소입니다. *nType이* SBT_OWNERDRAW 경우 *lpszText는* 32비트의 데이터를 나타냅니다.

*nPane*<br/>
설정할 부분의 0부터 시작하는 인덱스입니다. 이 값이 255인 경우에는 상태 표시줄 컨트롤이 하나의 부분만 있는 단일 컨트롤인 것으로 간주됩니다.

*nType*<br/>
그리기 작업의 형식입니다. 가능한 값 목록은 [SB_SETTEXT 메시지를](/windows/win32/Controls/sb-settext) 참조하십시오.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 메시지는 변경된 컨트롤 부분을 무효화하여 다음에 컨트롤이 WM_PAINT 메시지를 받을 때 새 텍스트를 표시합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]

## <a name="cstatusbarctrlsettiptext"></a><a name="settiptext"></a>C상태바Ctrl::SetTipText

상태 표시줄에서 창에 대한 도구 설명 텍스트를 설정합니다.

```cpp
void SetTipText(
    int nPane,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>매개 변수

*nPane*<br/>
도구 설명 텍스트를 수신할 상태 표시줄 창의 0기반 인덱스입니다.

*pszTip텍스트*<br/>
도구 설명 텍스트가 포함된 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 SB_SETTIPTEXT Win32 [메시지의](/windows/win32/Controls/sb-settiptext)동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]

## <a name="see-also"></a>참조

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C툴바크터터 클래스](../../mfc/reference/ctoolbarctrl-class.md)
