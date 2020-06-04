---
title: C슬라이더Ctrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CSliderCtrl
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
helpviewer_keywords:
- CSliderCtrl [MFC], CSliderCtrl
- CSliderCtrl [MFC], ClearSel
- CSliderCtrl [MFC], ClearTics
- CSliderCtrl [MFC], Create
- CSliderCtrl [MFC], CreateEx
- CSliderCtrl [MFC], GetBuddy
- CSliderCtrl [MFC], GetChannelRect
- CSliderCtrl [MFC], GetLineSize
- CSliderCtrl [MFC], GetNumTics
- CSliderCtrl [MFC], GetPageSize
- CSliderCtrl [MFC], GetPos
- CSliderCtrl [MFC], GetRange
- CSliderCtrl [MFC], GetRangeMax
- CSliderCtrl [MFC], GetRangeMin
- CSliderCtrl [MFC], GetSelection
- CSliderCtrl [MFC], GetThumbLength
- CSliderCtrl [MFC], GetThumbRect
- CSliderCtrl [MFC], GetTic
- CSliderCtrl [MFC], GetTicArray
- CSliderCtrl [MFC], GetTicPos
- CSliderCtrl [MFC], GetToolTips
- CSliderCtrl [MFC], SetBuddy
- CSliderCtrl [MFC], SetLineSize
- CSliderCtrl [MFC], SetPageSize
- CSliderCtrl [MFC], SetPos
- CSliderCtrl [MFC], SetRange
- CSliderCtrl [MFC], SetRangeMax
- CSliderCtrl [MFC], SetRangeMin
- CSliderCtrl [MFC], SetSelection
- CSliderCtrl [MFC], SetThumbLength
- CSliderCtrl [MFC], SetTic
- CSliderCtrl [MFC], SetTicFreq
- CSliderCtrl [MFC], SetTipSide
- CSliderCtrl [MFC], SetToolTips
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
ms.openlocfilehash: 2e3572b34f930bb6a7d99b437c01c8aaf970e6c3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751268"
---
# <a name="csliderctrl-class"></a>C슬라이더Ctrl 클래스

Windows의 공용 슬라이더 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CSliderCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CSliderCtrl:::C슬라이더Ctrl](#csliderctrl)|`CSliderCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSliderCtrl::클리어셀](#clearsel)|슬라이더 컨트롤에서 현재 선택 영역을 지웁봅을 선택합니다.|
|[CSliderCtrl::클리어틱스](#cleartics)|슬라이더 컨트롤에서 현재 눈금 표시를 제거합니다.|
|[CSliderCtrl::만들기](#create)|슬라이더 컨트롤을 만들고 개체에 `CSliderCtrl` 연결합니다.|
|[CSliderCtrl::만들기](#createex)|지정된 Windows 확장 스타일을 사용하여 슬라이더 컨트롤을 만들고 `CSliderCtrl` 개체에 연결합니다.|
|[CSliderCtrl:::GetBuddy](#getbuddy)|지정된 위치에서 핸들을 슬라이더 컨트롤 버디 창으로 검색합니다.|
|[CSliderCtrl::GetChannelRect](#getchannelrect)|슬라이더 컨트롤의 채널 크기를 검색합니다.|
|[CSliderCtrl::GetLineSize](#getlinesize)|슬라이더 컨트롤의 줄 크기를 검색합니다.|
|[CSliderCtrl:::GetNumtics](#getnumtics)|슬라이더 컨트롤에서 눈금 표시 수를 검색합니다.|
|[CSliderCtrl::GetPageSize](#getpagesize)|슬라이더 컨트롤의 페이지 크기를 검색합니다.|
|[CSliderCtrl::GetPos](#getpos)|슬라이더의 현재 위치를 검색합니다.|
|[CSliderCtrl::GetRange](#getrange)|슬라이더의 최소 및 최대 위치를 검색합니다.|
|[C슬라이더Ctrl::겟레인지맥스](#getrangemax)|슬라이더의 최대 위치를 검색합니다.|
|[CSliderCtrl::GetRangeMin](#getrangemin)|슬라이더의 최소 위치를 검색합니다.|
|[CSliderCtrl::Getselection](#getselection)|현재 선택 영역의 범위를 검색합니다.|
|[CSliderCtrl::GetThumbLength](#getthumblength)|현재 트랙 바 컨트롤에서 슬라이더의 길이를 검색합니다.|
|[CSliderCtrl::GetThumbRect](#getthumbrect)|슬라이더 컨트롤의 엄지 손가락 크기를 검색합니다.|
|[CSliderCtrl::Gettic](#gettic)|지정된 눈금 표시의 위치를 검색합니다.|
|[CSliderCtrl::GetticArray](#getticarray)|슬라이더 컨트롤에 대 한 틱 마크 위치의 배열을 검색 합니다.|
|[CSliderCtrl::Getticpos](#getticpos)|클라이언트 좌표에서 지정된 눈금 표시의 위치를 검색합니다.|
|[CSliderCtrl::getToolTips](#gettooltips)|슬라이더 컨트롤에 할당 된 도구 설명 컨트롤에 핸들을 검색 합니다(있는 경우).|
|[CSliderCtrl:::세트버디](#setbuddy)|창을 슬라이더 컨트롤의 버디 창으로 할당합니다.|
|[CSliderCtrl::설정선 크기](#setlinesize)|슬라이더 컨트롤의 선 크기를 설정합니다.|
|[C슬라이더Ctrl::세트 페이지 크기](#setpagesize)|슬라이더 컨트롤의 페이지 크기를 설정합니다.|
|[CSliderCtrl::SetPos](#setpos)|슬라이더의 현재 위치를 설정합니다.|
|[CSliderCtrl::세트 레인지](#setrange)|슬라이더의 최소 및 최대 위치를 설정합니다.|
|[C슬라이더Ctrl::세트레인지맥스](#setrangemax)|슬라이더의 최대 위치를 설정합니다.|
|[C슬라이더Ctrl::세트레인지민](#setrangemin)|슬라이더의 최소 위치를 설정합니다.|
|[CSliderCtrl::세트 선택](#setselection)|현재 선택 영역의 범위를 설정합니다.|
|[C슬라이더Ctrl::세트엄지손가락 길이](#setthumblength)|현재 트랙바 컨트롤에서 슬라이더의 길이를 설정합니다.|
|[CSliderCtrl::Settic](#settic)|지정된 눈금 표시의 위치를 설정합니다.|
|[CSliderCtrl:::세틱프렉](#setticfreq)|슬라이더 컨트롤 증분당 눈금 표시 빈도를 설정합니다.|
|[CSliderCtrl::SetTipSide](#settipside)|트랙 바 컨트롤에서 사용하는 도구 설명 컨트롤을 배치합니다.|
|[CSliderCtrl::설정 도구 팁](#settooltips)|도구 설명 컨트롤을 슬라이더 컨트롤에 할당합니다.|

## <a name="remarks"></a>설명

"슬라이더 컨트롤"(트랙바이라고도 함)은 슬라이더와 선택적 눈금 표시가 포함된 창입니다. 사용자가 슬라이더를 이동하면 마우스 또는 방향 키를 사용하여 컨트롤이 알림 메시지를 보내 변경 을 나타냅니다.

슬라이더 컨트롤은 사용자가 범위에서 불연속 값 또는 연속값 집합을 선택하도록 할 때 유용합니다. 예를 들어 슬라이더 컨트롤을 사용하여 사용자가 슬라이더를 지정된 눈금 표시로 이동하여 키보드의 반복 속도를 설정할 수 있습니다.

이 컨트롤(및 `CSliderCtrl` 따라서 클래스)은 Windows 95/98 및 Windows NT 버전 3.51 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.

슬라이더는 만들 때 지정한 증분으로 이동합니다. 예를 들어 슬라이더의 범위가 5이어야 한다고 지정하면 슬라이더는 슬라이더 컨트롤의 왼쪽에 있는 위치와 범위의 각 증분에 대해 하나의 위치등 6개의 위치만 차지할 수 있습니다. 일반적으로 이러한 각 위치는 눈금 표시로 식별됩니다.

의 생성자 및 멤버 함수를 `Create` 사용하여 `CSliderCtrl`슬라이더를 만듭니다. 슬라이더 컨트롤을 만든 후에는 멤버 함수를 `CSliderCtrl` 사용하여 많은 속성을 변경할 수 있습니다. 슬라이더에 대한 최소 및 최대 위치 설정, 눈금 표시 그리기, 선택 범위 설정 및 슬라이더 위치 조정을 변경할 수 있습니다.

사용에 `CSliderCtrl`대한 자세한 내용은 [컨트롤](../../mfc/controls-mfc.md) 및 [CSliderCtrl 사용](../../mfc/using-csliderctrl.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSliderCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="csliderctrlclearsel"></a><a name="clearsel"></a>CSliderCtrl::클리어셀

슬라이더 컨트롤에서 현재 선택 영역을 지웁봅을 선택합니다.

```cpp
void ClearSel(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>매개 변수

*bRedraw*<br/>
플래그를 다시 그립니다. 이 매개변수가 TRUE이면 선택 영역을 지운 후 슬라이더가 다시 그려집니다. 그렇지 않으면 슬라이더가 다시 그려지지 않습니다.

## <a name="csliderctrlcleartics"></a><a name="cleartics"></a>CSliderCtrl::클리어틱스

슬라이더 컨트롤에서 현재 눈금 표시를 제거합니다.

```cpp
void ClearTics(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>매개 변수

*bRedraw*<br/>
플래그를 다시 그립니다. 이 매개변수가 TRUE이면 눈금 표시를 지운 후 슬라이더가 다시 그려집니다. 그렇지 않으면 슬라이더가 다시 그려지지 않습니다.

## <a name="csliderctrlcreate"></a><a name="create"></a>CSliderCtrl::만들기

슬라이더 컨트롤을 만들고 개체에 `CSliderCtrl` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
슬라이더 컨트롤의 스타일을 지정합니다. Windows SDK에 설명된 [슬라이더 컨트롤 스타일의](/windows/win32/Controls/trackbar-control-styles)조합을 컨트롤에 적용합니다.

*rect*<br/>
슬라이더 컨트롤의 크기와 위치를 지정합니다. [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조일 수 있습니다.

*pParentWnd*<br/>
슬라이더 컨트롤의 부모 창(일반적으로 )을 `CDialog`지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
슬라이더 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

초기화가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

두 단계로 `CSliderCtrl` 구성합니다. 먼저 생성자 호출 한 다음 `Create`슬라이더 컨트롤을 만들고 `CSliderCtrl` 개체에 연결 하는 호출 합니다.

*dwStyle에*대해 설정된 값에 따라 슬라이더 컨트롤에는 수직 또는 수평 방향이 있을 수 있습니다. 양쪽, 양쪽 또는 둘 다에 눈금 표시가 있을 수 있습니다. 연속 값의 범위를 지정하는 데 사용할 수도 있습니다.

슬라이더 컨트롤에 확장 창 스타일을 적용하려면 대신 `Create` [CreateEx를](#createex) 호출합니다.

## <a name="csliderctrlcreateex"></a><a name="createex"></a>CSliderCtrl::만들기

컨트롤(하위 창)을 만들고 `CSliderCtrl` 개체와 연결합니다.

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
슬라이더 컨트롤의 스타일을 지정합니다. Windows SDK에 설명된 [슬라이더 컨트롤 스타일의](/windows/win32/Controls/trackbar-control-styles)조합을 컨트롤에 적용합니다.

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

## <a name="csliderctrlcsliderctrl"></a><a name="csliderctrl"></a>CSliderCtrl:::C슬라이더Ctrl

`CSliderCtrl` 개체를 생성합니다.

```
CSliderCtrl();
```

## <a name="csliderctrlgetbuddy"></a><a name="getbuddy"></a>CSliderCtrl:::GetBuddy

지정된 위치에서 핸들을 슬라이더 컨트롤 버디 창으로 검색합니다.

```
CWnd* GetBuddy(BOOL fLocation = TRUE) const;
```

### <a name="parameters"></a>매개 변수

*fLocation*<br/>
검색할 두 개의 버디 창 핸들을 나타내는 부울 값입니다. 다음 값 중 하나를 사용할 수 있습니다.

- TRUE 슬라이더의 왼쪽에 있는 버디에 핸들을 검색합니다. 슬라이더 컨트롤이 TBS_VERT 스타일을 사용하는 경우 메시지는 슬라이더 위의 버디를 검색합니다.

- FALSE 슬라이더의 오른쪽에 있는 버디에 핸들을 검색합니다. 슬라이더 컨트롤이 TBS_VERT 스타일을 사용하는 경우 메시지는 슬라이더 아래의 버디를 검색합니다.

### <a name="return-value"></a>Return Value

*fLocation에*의해 지정된 위치의 버디 창인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터 또는 해당 위치에 버디 창이 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [TBM_GETBUDDY](/windows/win32/Controls/tbm-getbuddy)Win32 메시지의 동작을 구현합니다. 슬라이더 컨트롤 스타일에 대한 설명은 Windows SDK의 [트랙바 컨트롤 스타일을](/windows/win32/Controls/trackbar-control-styles) 참조하십시오.

## <a name="csliderctrlgetchannelrect"></a><a name="getchannelrect"></a>CSliderCtrl::GetChannelRect

슬라이더 컨트롤의 채널에 대한 경계 사각형의 크기와 위치를 검색합니다.

```cpp
void GetChannelRect(LPRECT lprc) const;
```

### <a name="parameters"></a>매개 변수

*lprc*<br/>
함수가 반환될 때 채널경계 사각형의 크기와 위치를 포함하는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

채널은 슬라이더가 이동하고 범위를 선택할 때 강조 표시가 포함된 영역입니다.

## <a name="csliderctrlgetlinesize"></a><a name="getlinesize"></a>CSliderCtrl::GetLineSize

슬라이더 컨트롤에 대 한 줄의 크기를 검색합니다.

```
int GetLineSize() const;
```

### <a name="return-value"></a>Return Value

슬라이더 컨트롤에 대 한 줄의 크기입니다.

### <a name="remarks"></a>설명

줄 크기는 TB_LINEUP 및 TB_LINEDOWN 알림에 대해 슬라이더가 이동하는 양에 영향을 줍니다. 선 크기의 기본 설정은 1입니다.

## <a name="csliderctrlgetnumtics"></a><a name="getnumtics"></a>CSliderCtrl:::GetNumtics

슬라이더 컨트롤에서 눈금 표시 수를 검색합니다.

```
UINT GetNumTics() const;
```

### <a name="return-value"></a>Return Value

슬라이더 컨트롤의 눈금 표시 수입니다.

## <a name="csliderctrlgetpagesize"></a><a name="getpagesize"></a>CSliderCtrl::GetPageSize

슬라이더 컨트롤에 대 한 페이지의 크기를 검색합니다.

```
int GetPageSize() const;
```

### <a name="return-value"></a>Return Value

슬라이더 컨트롤에 대 한 페이지의 크기입니다.

### <a name="remarks"></a>설명

페이지 크기는 TB_PAGEUP 및 TB_PAGEDOWN 알림에 대해 슬라이더가 이동하는 정도에 영향을 줍니다.

## <a name="csliderctrlgetpos"></a><a name="getpos"></a>CSliderCtrl::GetPos

슬라이더 컨트롤에서 슬라이더의 현재 위치를 검색합니다.

```
int GetPos() const;
```

### <a name="return-value"></a>Return Value

현재 위치입니다.

## <a name="csliderctrlgetrange"></a><a name="getrange"></a>CSliderCtrl::GetRange

슬라이더 컨트롤에서 슬라이더의 최대 및 최소 위치를 검색합니다.

```cpp
void GetRange(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
최소 위치를 받는 정수에 대한 참조입니다.

*nMax*<br/>
최대 위치를 받는 정수에 대한 참조입니다.

### <a name="remarks"></a>설명

이 함수는 *nMin* 및 *nMax에서*참조하는 정수에 값을 복사합니다.

## <a name="csliderctrlgetrangemax"></a><a name="getrangemax"></a>C슬라이더Ctrl::겟레인지맥스

슬라이더 컨트롤에서 슬라이더의 최대 위치를 검색합니다.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Return Value

컨트롤의 최대 위치입니다.

## <a name="csliderctrlgetrangemin"></a><a name="getrangemin"></a>CSliderCtrl::GetRangeMin

슬라이더 컨트롤에서 슬라이더의 최소 위치를 검색합니다.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Return Value

컨트롤의 최소 위치입니다.

## <a name="csliderctrlgetselection"></a><a name="getselection"></a>CSliderCtrl::Getselection

슬라이더 컨트롤에서 현재 선택 영역의 시작 및 끝 위치를 검색합니다.

```cpp
void GetSelection(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
현재 선택 영역의 시작 위치를 받는 정수를 참조합니다.

*nMax*<br/>
현재 선택 영역의 끝 위치를 받는 정수를 참조합니다.

## <a name="csliderctrlgetthumblength"></a><a name="getthumblength"></a>CSliderCtrl::GetThumbLength

현재 트랙 바 컨트롤에서 슬라이더의 길이를 검색합니다.

```
int GetThumbLength() const;
```

### <a name="return-value"></a>Return Value

슬라이더의 길이(픽셀)입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [TBM_GETTHUMBLENGTH](/windows/win32/Controls/tbm-getthumblength) 메시지를 보냅니다.

## <a name="csliderctrlgetthumbrect"></a><a name="getthumbrect"></a>CSliderCtrl::GetThumbRect

슬라이더 컨트롤에서 슬라이더(엄지 손가락)에 대한 경계 사각형의 크기와 위치를 검색합니다.

```cpp
void GetThumbRect(LPRECT lprc) const;
```

### <a name="parameters"></a>매개 변수

*lprc*<br/>
함수가 `CRect` 반환될 때 슬라이더에 대한 경계 사각형이 포함된 개체에 대한 포인터입니다.

## <a name="csliderctrlgettic"></a><a name="gettic"></a>CSliderCtrl::Gettic

슬라이더 컨트롤에서 눈금 표시의 위치를 검색합니다.

```
int GetTic(int nTic) const;
```

### <a name="parameters"></a>매개 변수

*nTic*<br/>
눈금 표시를 식별하는 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

*nTic이* 유효한 인덱스를 지정하지 않은 경우 지정된 눈금 표시 또는 - 1의 위치입니다.

## <a name="csliderctrlgetticarray"></a><a name="getticarray"></a>CSliderCtrl::GetticArray

슬라이더 컨트롤에 대 한 눈금 표시의 위치를 포함 하는 배열의 주소를 검색합니다.

```
DWORD* GetTicArray() const;
```

### <a name="return-value"></a>Return Value

슬라이더 컨트롤에 대 한 틱 마크 위치를 포함 하는 배열의 주소입니다.

## <a name="csliderctrlgetticpos"></a><a name="getticpos"></a>CSliderCtrl::Getticpos

슬라이더 컨트롤에서 눈금 표시의 현재 물리적 위치를 검색합니다.

```
int GetTicPos(int nTic) const;
```

### <a name="parameters"></a>매개 변수

*nTic*<br/>
눈금 표시를 식별하는 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

클라이언트 좌표에서 지정된 눈금 표시의 물리적 위치 또는 *nTic이* 유효한 인덱스를 지정하지 않는 경우 -1입니다.

## <a name="csliderctrlgettooltips"></a><a name="gettooltips"></a>CSliderCtrl::getToolTips

슬라이더 컨트롤에 할당 된 도구 설명 컨트롤에 핸들을 검색 합니다(있는 경우).

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Return Value

도구 설명이 사용되지 않는 경우 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 개체 또는 NULL에 대한 포인터입니다. 슬라이더 컨트롤이 TBS_TOOLTIPS 스타일을 사용하지 않는 경우 반환 값은 NULL입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [TBM_GETTOOLTIPS](/windows/win32/Controls/tbm-gettooltips)Win32 메시지의 동작을 구현합니다. 이 멤버 함수는 `CToolTipCtrl` 컨트롤에 핸들 대신 개체를 반환합니다.

슬라이더 컨트롤 스타일에 대한 설명은 Windows SDK의 [트랙바 컨트롤 스타일을](/windows/win32/Controls/trackbar-control-styles) 참조하십시오.

## <a name="csliderctrlsetbuddy"></a><a name="setbuddy"></a>CSliderCtrl:::세트버디

창을 슬라이더 컨트롤의 버디 창으로 할당합니다.

```
CWnd* SetBuddy(
    CWnd* pWndBuddy,
    BOOL fLocation = TRUE);
```

### <a name="parameters"></a>매개 변수

*pwndBuddy*<br/>
슬라이더 컨트롤의 `CWnd` 버디로 설정 될 개체에 대 한 포인터입니다.

*fLocation*<br/>
버디 창을 표시할 위치를 지정하는 값입니다. 이 값은 다음 중 하나일 수 있습니다.

- TRUE 트랙바 컨트롤이 TBS_HORZ 스타일을 사용하는 경우 버디가 트랙바의 왼쪽에 나타납니다. 트랙바에서 TBS_VERT 스타일을 사용하는 경우 버디가 트랙바 컨트롤 위에 나타납니다.

- FALSE 트랙바 컨트롤이 TBS_HORZ 스타일을 사용하는 경우 버디가 트랙바 오른쪽에 나타납니다. 트랙바에서 TBS_VERT 스타일을 사용하는 경우 버디가 트랙바 컨트롤 아래에 나타납니다.

### <a name="return-value"></a>Return Value

해당 위치에서 슬라이더 컨트롤에 이전에 할당된 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 TBM_SETBUDDY Win32 [메시지의](/windows/win32/Controls/tbm-setbuddy)동작을 구현합니다. 이 멤버 함수는 반환 `CWnd` 값과 매개 변수 모두에 대해 창 핸들이 아닌 개체에 대한 포인터를 사용합니다.

슬라이더 컨트롤 스타일에 대한 설명은 Windows SDK의 [트랙바 컨트롤 스타일을](/windows/win32/Controls/trackbar-control-styles) 참조하십시오.

## <a name="csliderctrlsetlinesize"></a><a name="setlinesize"></a>CSliderCtrl::설정선 크기

슬라이더 컨트롤의 줄 크기를 설정합니다.

```
int SetLineSize(int nSize);
```

### <a name="parameters"></a>매개 변수

*nSize*<br/>
슬라이더 컨트롤의 새 줄 크기입니다.

### <a name="return-value"></a>Return Value

이전 줄 크기입니다.

### <a name="remarks"></a>설명

줄 크기는 TB_LINEUP 및 TB_LINEDOWN 알림에 대해 슬라이더가 이동하는 양에 영향을 줍니다.

## <a name="csliderctrlsetpagesize"></a><a name="setpagesize"></a>C슬라이더Ctrl::세트 페이지 크기

슬라이더 컨트롤의 페이지 크기를 설정합니다.

```
int SetPageSize(int nSize);
```

### <a name="parameters"></a>매개 변수

*nSize*<br/>
슬라이더 컨트롤의 새 페이지 크기입니다.

### <a name="return-value"></a>Return Value

이전 페이지 크기입니다.

### <a name="remarks"></a>설명

페이지 크기는 TB_PAGEUP 및 TB_PAGEDOWN 알림에 대해 슬라이더가 이동하는 정도에 영향을 줍니다.

## <a name="csliderctrlsetpos"></a><a name="setpos"></a>CSliderCtrl::SetPos

슬라이더 컨트롤에서 슬라이더의 현재 위치를 설정합니다.

```cpp
void SetPos(int nPos);
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
새 슬라이더 위치를 지정합니다.

## <a name="csliderctrlsetrange"></a><a name="setrange"></a>CSliderCtrl::세트 레인지

슬라이더 컨트롤에서 슬라이더의 범위(최소 및 최대 위치)를 설정합니다.

```cpp
void SetRange(
    int nMin,
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
슬라이더의 최소 위치입니다.

*nMax*<br/>
슬라이더의 최대 위치입니다.

*bRedraw*<br/>
다시 그리기 플래그입니다. 이 매개변수가 TRUE이면 범위를 설정한 후 슬라이더가 다시 그려집니다. 그렇지 않으면 슬라이더가 다시 그려지지 않습니다.

## <a name="csliderctrlsetrangemax"></a><a name="setrangemax"></a>C슬라이더Ctrl::세트레인지맥스

슬라이더 컨트롤에서 슬라이더의 최대 범위를 설정합니다.

```cpp
void SetRangeMax(
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>매개 변수

*nMax*<br/>
슬라이더의 최대 위치입니다.

*bRedraw*<br/>
다시 그리기 플래그입니다. 이 매개변수가 TRUE이면 범위를 설정한 후 슬라이더가 다시 그려집니다. 그렇지 않으면 슬라이더가 다시 그려지지 않습니다.

## <a name="csliderctrlsetrangemin"></a><a name="setrangemin"></a>C슬라이더Ctrl::세트레인지민

슬라이더 컨트롤에서 슬라이더의 최소 범위를 설정합니다.

```cpp
void SetRangeMin(
    int nMin,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
슬라이더의 최소 위치입니다.

*bRedraw*<br/>
다시 그리기 플래그입니다. 이 매개변수가 TRUE이면 범위를 설정한 후 슬라이더가 다시 그려집니다. 그렇지 않으면 슬라이더가 다시 그려지지 않습니다.

## <a name="csliderctrlsetselection"></a><a name="setselection"></a>CSliderCtrl::세트 선택

슬라이더 컨트롤에서 현재 선택 영역의 시작 및 끝 위치를 설정합니다.

```cpp
void SetSelection(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
슬라이더의 시작 위치입니다.

*nMax*<br/>
슬라이더의 종료 위치입니다.

## <a name="csliderctrlsetthumblength"></a><a name="setthumblength"></a>C슬라이더Ctrl::세트엄지손가락 길이

현재 트랙바 컨트롤에서 슬라이더의 길이를 설정합니다.

```cpp
void SetThumbLength(int nLength);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*nLength*|【인】 슬라이더의 길이(픽셀 단위)입니다.|

### <a name="remarks"></a>설명

이 방법을 사용하려면 트랙바 컨트롤을 [TBS_FIXEDLENGTH](/windows/win32/Controls/trackbar-control-styles) 스타일로 설정해야 합니다.

이 메서드는 Windows SDK에 설명 된 [TBM_SETTHUMBLENGTH](/windows/win32/Controls/tbm-setthumblength) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 현재 `m_sliderCtrl`트랙바 컨트롤에 액세스하는 데 사용되는 변수 를 정의합니다. 또한 이 예제에서는 트랙바 컨트롤의 thumb 구성 요소의 기본 길이를 저장하는 데 사용되는 `thumbLength`변수를 정의합니다. 이러한 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]

### <a name="example"></a>예제

다음 코드 예제는 트랙바 컨트롤의 thumb 구성 요소를 기본 길이의 두 배로 설정합니다.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]

## <a name="csliderctrlsettic"></a><a name="settic"></a>CSliderCtrl::Settic

슬라이더 컨트롤에서 눈금 표시의 위치를 설정합니다.

```
BOOL SetTic(int nTic);
```

### <a name="parameters"></a>매개 변수

*nTic*<br/>
눈금 표시의 위치입니다. 이 매개 변수는 양수 값을 지정해야 합니다.

### <a name="return-value"></a>Return Value

눈금 표시가 설정된 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="csliderctrlsetticfreq"></a><a name="setticfreq"></a>CSliderCtrl:::세틱프렉

눈금 표시가 슬라이더에 표시되는 빈도를 설정합니다.

```cpp
void SetTicFreq(int nFreq);
```

### <a name="parameters"></a>매개 변수

*nFreq*<br/>
눈금 표시의 빈도입니다.

### <a name="remarks"></a>설명

예를 들어 빈도가 2로 설정된 경우 슬라이더 범위의 다른 모든 증분에 대해 눈금 표시가 표시됩니다. 주파수의 기본 설정은 1입니다(즉, 범위의 모든 증분은 눈금 표시와 연결됩니다).

이 함수를 사용하려면 TBS_AUTOTICKS 스타일로 컨트롤을 만들어야 합니다. 자세한 내용은 [CSliderCtrl::만들기](#create)를 참조하십시오.

## <a name="csliderctrlsettipside"></a><a name="settipside"></a>CSliderCtrl::SetTipSide

트랙 바 컨트롤에서 사용하는 도구 설명 컨트롤을 배치합니다.

```
int SetTipSide(int nLocation);
```

### <a name="parameters"></a>매개 변수

*n위치*<br/>
도구 설명 컨트롤을 표시할 위치를 나타내는 값입니다. 가능한 값 목록은 Windows SDK에 설명된 대로 [TBM_SETTIPSIDE](/windows/win32/Controls/tbm-settipside)Win32 메시지를 참조하십시오.

### <a name="return-value"></a>Return Value

도구 설명 컨트롤의 이전 위치를 나타내는 값입니다. 반환 값은 *nLocation*에 대해 가능한 값 중 하나와 같습니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 TBM_SETTIPSIDE Win32 메시지의 동작을 구현합니다. TBS_TOOLTIPS 스타일 표시 도구 설명팁을 사용하는 슬라이더 컨트롤입니다. 슬라이더 컨트롤 스타일에 대한 설명은 Windows SDK의 [트랙바 컨트롤 스타일을](/windows/win32/Controls/trackbar-control-styles) 참조하십시오.

## <a name="csliderctrlsettooltips"></a><a name="settooltips"></a>CSliderCtrl::설정 도구 팁

도구 설명 컨트롤을 슬라이더 컨트롤에 할당합니다.

```cpp
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>매개 변수

*pWndTip*<br/>
슬라이더 컨트롤과 함께 사용할 도구 설명이 포함된 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 TBM_SETTOOLTIPS Win32 [메시지의](/windows/win32/Controls/tbm-settooltips)동작을 구현합니다. TBS_TOOLTIPS 스타일로 슬라이더 컨트롤을 만들면 슬라이더 옆에 슬라이더의 현재 위치가 표시되는 기본 도구 설명 컨트롤이 만들어집니다. 슬라이더 컨트롤 스타일에 대한 설명은 Windows SDK의 [트랙바 컨트롤 스타일을](/windows/win32/Controls/trackbar-control-styles) 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CProgressCtrl 클래스](../../mfc/reference/cprogressctrl-class.md)
