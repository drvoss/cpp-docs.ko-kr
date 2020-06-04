---
title: C스핀버튼Ctrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::Create
- AFXCMN/CSpinButtonCtrl::CreateEx
- AFXCMN/CSpinButtonCtrl::GetAccel
- AFXCMN/CSpinButtonCtrl::GetBase
- AFXCMN/CSpinButtonCtrl::GetBuddy
- AFXCMN/CSpinButtonCtrl::GetPos
- AFXCMN/CSpinButtonCtrl::GetRange
- AFXCMN/CSpinButtonCtrl::SetAccel
- AFXCMN/CSpinButtonCtrl::SetBase
- AFXCMN/CSpinButtonCtrl::SetBuddy
- AFXCMN/CSpinButtonCtrl::SetPos
- AFXCMN/CSpinButtonCtrl::SetRange
helpviewer_keywords:
- CSpinButtonCtrl [MFC], CSpinButtonCtrl
- CSpinButtonCtrl [MFC], Create
- CSpinButtonCtrl [MFC], CreateEx
- CSpinButtonCtrl [MFC], GetAccel
- CSpinButtonCtrl [MFC], GetBase
- CSpinButtonCtrl [MFC], GetBuddy
- CSpinButtonCtrl [MFC], GetPos
- CSpinButtonCtrl [MFC], GetRange
- CSpinButtonCtrl [MFC], SetAccel
- CSpinButtonCtrl [MFC], SetBase
- CSpinButtonCtrl [MFC], SetBuddy
- CSpinButtonCtrl [MFC], SetPos
- CSpinButtonCtrl [MFC], SetRange
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
ms.openlocfilehash: cedfe16a6870bc779121e8e864866cfcb711b148
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753116"
---
# <a name="cspinbuttonctrl-class"></a>C스핀버튼Ctrl 클래스

Windows의 공용 스핀 단추 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CSpinButtonCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CSpinButtonCtrl:::CSpinButtonCtrl](#cspinbuttonctrl)|`CSpinButtonCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSpinButtonCtrl::만들기](#create)|스핀 버튼 컨트롤을 만들고 오브젝트에 `CSpinButtonCtrl` 연결합니다.|
|[CSpinButtonCtrl::만들기](#createex)|지정된 Windows 확장 스타일로 스핀 단추 컨트롤을 만들고 `CSpinButtonCtrl` 개체에 연결합니다.|
|[CSpinButtonCtrl::GetAccel](#getaccel)|스핀 버튼 컨트롤에 대한 가속 정보를 검색합니다.|
|[CSpinButtonCtrl::GetBase](#getbase)|스핀 버튼 컨트롤의 현재 베이스를 검색합니다.|
|[CSpinButtonCtrl:::GetBuddy](#getbuddy)|현재 버디 창에 대한 포인터를 검색합니다.|
|[CSpinButtonCtrl::GetPos](#getpos)|스핀 버튼 컨트롤의 현재 위치를 검색합니다.|
|[C스핀버튼Ctrl::GetRange](#getrange)|스핀 버튼 컨트롤의 상한 및 하한(범위)을 검색합니다.|
|[C스핀버튼Ctrl::세타셀](#setaccel)|스핀 버튼 컨트롤의 가속을 설정합니다.|
|[C스핀버튼Ctrl::세트베이스](#setbase)|스핀 버튼 컨트롤의 베이스를 설정합니다.|
|[C스핀버튼Ctrl::세트버디](#setbuddy)|스핀 버튼 컨트롤의 버디 창을 설정합니다.|
|[CSpinButtonCtrl::setpos](#setpos)|컨트롤의 현재 위치를 설정합니다.|
|[C스핀버튼Ctrl::세트레인지](#setrange)|스핀 버튼 컨트롤의 상한 및 하한(범위)을 설정합니다.|

## <a name="remarks"></a>설명

"스핀 버튼 컨트롤"(업다운 컨트롤이라고도 함)은 사용자가 클릭하여 스크롤 위치 또는 컴패니언 컨트롤에 표시되는 숫자와 같은 값을 증가 또는 감소시키기 위해 클릭할 수 있는 화살표 단추 쌍입니다. 스핀 단추 컨트롤과 관련된 값을 현재 위치라고 합니다. 스핀 버튼 컨트롤은 "버디 창"이라고 하는 컴패니언 컨트롤과 함께 가장 자주 사용됩니다.

이 컨트롤(및 `CSpinButtonCtrl` 따라서 클래스)은 Windows 95/98 및 Windows NT 버전 3.51 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.

사용자에게 는 스핀 버튼 컨트롤과 버디 창이 단일 컨트롤처럼 보이는 경우가 많습니다. 스핀 단추 컨트롤이 자동으로 버디 창 옆에 배치되도록 지정하고 버디 창의 캡션을 현재 위치로 자동으로 설정하도록 지정할 수 있습니다. 편집 컨트롤이 있는 스핀 버튼 컨트롤을 사용하여 사용자에게 숫자 입력을 요청합니다.

위쪽 화살표를 클릭하면 현재 위치가 최대값으로 이동하고 아래쪽 화살표를 클릭하면 현재 위치가 최소값으로 이동합니다. 기본적으로 최소값은 100이고 최대값은 0입니다. 최소 설정이 최대 설정보다 클 때마다(예: 기본 설정을 사용하는 경우) 위쪽 화살표를 클릭하면 위치 값이 줄어들고 아래쪽 화살표를 클릭하면 위치 값이 증가합니다.

버디 창이없는 스핀 버튼 컨트롤은 일종의 단순화 된 스크롤 막대로 작동합니다. 예를 들어 탭 컨트롤에 사용자가 추가 탭을 보기로 스크롤할 수 있도록 스핀 단추 컨트롤이 표시되는 경우가 있습니다.

사용에 `CSpinButtonCtrl`대한 자세한 내용은 [컨트롤](../../mfc/controls-mfc.md) 및 [CSpinButtonCtrl 사용](../../mfc/using-cspinbuttonctrl.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSpinButtonCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="cspinbuttonctrlcreate"></a><a name="create"></a>CSpinButtonCtrl::만들기

스핀 단추 컨트롤을 만들고 `CSpinButtonCtrl` 개체에 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
스핀 버튼 컨트롤의 스타일을 지정합니다. 스핀 버튼 컨트롤 스타일의 조합을 컨트롤에 적용합니다. 이러한 스타일은 Windows SDK의 [업다운 컨트롤 스타일에](/windows/win32/Controls/up-down-control-styles) 설명되어 있습니다.

*rect*<br/>
스핀 버튼 컨트롤의 크기와 위치를 지정합니다. [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조일 수 있습니다.

*pParentWnd*<br/>
스핀 단추 컨트롤의 부모 창에 대한 `CDialog`포인터( 일반적으로 ). NULL이 아니어야 합니다.

*nID*<br/>
스핀 버튼 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

초기화가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

먼저 두 `CSpinButtonCtrl` 단계로 개체를 생성하고 생성자 호출한 `Create`다음 호출하여 스핀 단추 컨트롤을 `CSpinButtonCtrl` 만들고 개체에 연결합니다.

확장된 창 스타일로 스핀 단추 컨트롤을 만들려면 [CSpinButtonCtrl::CreateEx](#createex) 대신 `Create`호출합니다.

## <a name="cspinbuttonctrlcreateex"></a><a name="createex"></a>CSpinButtonCtrl::만들기

컨트롤(하위 창)을 만들고 `CSpinButtonCtrl` 개체와 연결합니다.

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
생성되는 컨트롤의 확장 스타일을 지정합니다. 확장된 창 스타일 목록은 Windows SDK의 [CreateWindowEx에](/windows/win32/api/winuser/nf-winuser-createwindowexw) 대한 *dwExStyle* 매개 변수를 참조하십시오.

*dwStyle*<br/>
스핀 버튼 컨트롤의 스타일을 지정합니다. 스핀 버튼 컨트롤 스타일의 조합을 컨트롤에 적용합니다. 이러한 스타일은 Windows SDK의 [업다운 컨트롤 스타일에](/windows/win32/Controls/up-down-control-styles) 설명되어 있습니다.

*rect*<br/>
*pParentWnd의*클라이언트 좌표에서 생성할 창의 크기와 위치를 설명하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*pParentWnd*<br/>
컨트롤의 부모인 창에 대한 포인터입니다.

*nID*<br/>
컨트롤의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

만들기 `CreateEx` 대신 [Create](#create) Windows 확장 스타일 서문 WS_EX_ 지정된 확장 된 Windows 스타일을 적용 합니다.

## <a name="cspinbuttonctrlcspinbuttonctrl"></a><a name="cspinbuttonctrl"></a>CSpinButtonCtrl:::CSpinButtonCtrl

`CSpinButtonCtrl` 개체를 생성합니다.

```
CSpinButtonCtrl();
```

## <a name="cspinbuttonctrlgetaccel"></a><a name="getaccel"></a>CSpinButtonCtrl::GetAccel

스핀 버튼 컨트롤에 대한 가속 정보를 검색합니다.

```
UINT GetAccel(
    int nAccel,
    UDACCEL* pAccel) const;
```

### <a name="parameters"></a>매개 변수

*nAccel*<br/>
*pAccel에서*지정한 배열의 요소 수입니다.

*파셀 (것)과 함께*<br/>
가속 정보를 수신하는 [UDACCEL](/windows/win32/api/commctrl/ns-commctrl-udaccel) 구조의 배열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

검색된 가속기 구조의 수입니다.

## <a name="cspinbuttonctrlgetbase"></a><a name="getbase"></a>CSpinButtonCtrl::GetBase

스핀 버튼 컨트롤의 현재 베이스를 검색합니다.

```
UINT GetBase() const;
```

### <a name="return-value"></a>Return Value

현재 기준 값입니다.

## <a name="cspinbuttonctrlgetbuddy"></a><a name="getbuddy"></a>CSpinButtonCtrl:::GetBuddy

현재 버디 창에 대한 포인터를 검색합니다.

```
CWnd* GetBuddy() const;
```

### <a name="return-value"></a>Return Value

현재 버디 창에 대한 포인터입니다.

## <a name="cspinbuttonctrlgetpos"></a><a name="getpos"></a>CSpinButtonCtrl::GetPos

스핀 버튼 컨트롤의 현재 위치를 검색합니다.

```
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;
```

### <a name="parameters"></a>매개 변수

*lpbError*<br/>
값이 성공적으로 검색되는 경우 0으로 설정된 부울 값에 대한 포인터 또는 오류가 발생할 경우 0이 아닌 값입니다. 이 매개 변수가 NULL로 설정되면 오류가 보고되지 않습니다.

### <a name="return-value"></a>Return Value

첫 번째 버전은 낮은 순서의 단어에서 16비트 현재 위치를 반환합니다. 오류가 발생한 경우 높은 순서의 단어는 0이 아닙니다.

두 번째 버전은 32비트 위치를 반환합니다.

### <a name="remarks"></a>설명

반환된 값을 처리하면 컨트롤은 버디 창의 캡션을 기반으로 현재 위치를 업데이트합니다. 버디 창이 없거나 캡션이 유효하지 않거나 범위를 벗어난 값을 지정하는 경우 컨트롤에서 오류를 반환합니다.

## <a name="cspinbuttonctrlgetrange"></a><a name="getrange"></a>C스핀버튼Ctrl::GetRange

스핀 버튼 컨트롤의 상한 및 하한(범위)을 검색합니다.

```
DWORD GetRange() const;

void GetRange(
    int& lower,
    int& upper) const;

void GetRange32(
    int& lower,
    int &upper) const;
```

### <a name="parameters"></a>매개 변수

*낮은*<br/>
컨트롤의 하한을 받는 정수에 대한 참조입니다.

*상단*<br/>
컨트롤의 상한을 받는 정수에 대한 참조입니다.

### <a name="return-value"></a>Return Value

첫 번째 버전은 상한과 하한을 포함하는 32비트 값을 반환합니다. 하위 순서 단어는 컨트롤의 상한이며 상위 값은 하한입니다.

### <a name="remarks"></a>설명

멤버 함수는 `GetRange32` 스핀 버튼 컨트롤의 범위를 32비트 정수로 검색합니다.

## <a name="cspinbuttonctrlsetaccel"></a><a name="setaccel"></a>C스핀버튼Ctrl::세타셀

스핀 버튼 컨트롤의 가속을 설정합니다.

```
BOOL SetAccel(
    int nAccel,
    UDACCEL* pAccel);
```

### <a name="parameters"></a>매개 변수

*nAccel*<br/>
*pAccel에*의해 지정된 [UDACCEL](/windows/win32/api/commctrl/ns-commctrl-udaccel) 구조의 수.

*파셀 (것)과 함께*<br/>
가속 정보를 포함하는 UDACCEL 구조의 배열에 대한 포인터입니다. 요소는 `nSec` 멤버에 따라 오름차순으로 정렬되어야 합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

## <a name="cspinbuttonctrlsetbase"></a><a name="setbase"></a>C스핀버튼Ctrl::세트베이스

스핀 버튼 컨트롤의 베이스를 설정합니다.

```
int SetBase(int nBase);
```

### <a name="parameters"></a>매개 변수

*nBase*<br/>
컨트롤에 대한 새 기본 값입니다. 소수점의 경우 10, 헥사데피의 경우 16일 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 이전 기준 값, 잘못된 기준이 주어지면 0입니다.

### <a name="remarks"></a>설명

기준 값은 버디 창에 소수점 또는 육각형 숫자로 숫자를 표시할지 여부를 결정합니다. 헥사데피풀 번호는 항상 서명되지 않습니다. 소수 자릿수가 서명됩니다.

## <a name="cspinbuttonctrlsetbuddy"></a><a name="setbuddy"></a>C스핀버튼Ctrl::세트버디

스핀 버튼 컨트롤의 버디 창을 설정합니다.

```
CWnd* SetBuddy(CWnd* pWndBuddy);
```

### <a name="parameters"></a>매개 변수

*pwndBuddy*<br/>
새 버디 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

이전 버디 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

스핀 컨트롤은 거의 항상 일부 콘텐츠를 표시하는 편집 컨트롤과 같은 다른 창과 연결됩니다. 이 다른 창을 스핀 컨트롤의 "버디"라고 합니다.

## <a name="cspinbuttonctrlsetpos"></a><a name="setpos"></a>CSpinButtonCtrl::setpos

스핀 버튼 컨트롤의 현재 위치를 설정합니다.

```
int SetPos(int nPos);
int SetPos32(int nPos);
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
컨트롤의 새 위치입니다. 이 값은 컨트롤의 상한 및 하한으로 지정된 범위에 있어야 합니다.

### <a name="return-value"></a>Return Value

이전 위치(16비트 정밀도 `SetPos`, 32비트 `SetPos32`정밀도).

### <a name="remarks"></a>설명

`SetPos32`32비트 위치를 설정합니다.

## <a name="cspinbuttonctrlsetrange"></a><a name="setrange"></a>C스핀버튼Ctrl::세트레인지

스핀 버튼 컨트롤의 상한 및 하한(범위)을 설정합니다.

```cpp
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>매개 변수

*nLower* 및 *upper*<br/>
컨트롤의 상한 및 하한입니다. 에 `SetRange`대해 두 제한은 UD_MAXVAL 보다 크거나 UD_MINVAL 수 없습니다. 또한 두 제한 간의 차이는 UD_MAXVAL 초과할 수 없습니다. `SetRange32`한도에 제한을 두지 않습니다. 정수만 사용합니다.

### <a name="remarks"></a>설명

멤버 함수는 `SetRange32` 스핀 버튼 컨트롤의 32비트 범위를 설정합니다.

> [!NOTE]
> 스핀 버튼의 기본 범위에는 최대 값이 0(0)으로 설정되고 최소 값이 100으로 설정됩니다. 최대값이 최소값보다 적기 때문에 위쪽 화살표를 클릭하면 위치가 줄어들고 아래쪽 화살표를 클릭하면 화살표가 증가합니다. 이러한 `CSpinButtonCtrl::SetRange` 값을 조정하는 데 사용합니다.

## <a name="see-also"></a>참조

[MFC 샘플 CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C슬라이더Ctrl 클래스](../../mfc/reference/csliderctrl-class.md)
