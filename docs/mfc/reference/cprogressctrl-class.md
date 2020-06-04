---
title: CProgressCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
helpviewer_keywords:
- CProgressCtrl [MFC], CProgressCtrl
- CProgressCtrl [MFC], Create
- CProgressCtrl [MFC], CreateEx
- CProgressCtrl [MFC], GetBarColor
- CProgressCtrl [MFC], GetBkColor
- CProgressCtrl [MFC], GetPos
- CProgressCtrl [MFC], GetRange
- CProgressCtrl [MFC], GetState
- CProgressCtrl [MFC], GetStep
- CProgressCtrl [MFC], OffsetPos
- CProgressCtrl [MFC], SetBarColor
- CProgressCtrl [MFC], SetBkColor
- CProgressCtrl [MFC], SetMarquee
- CProgressCtrl [MFC], SetPos
- CProgressCtrl [MFC], SetRange
- CProgressCtrl [MFC], SetState
- CProgressCtrl [MFC], SetStep
- CProgressCtrl [MFC], StepIt
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
ms.openlocfilehash: c9e94e334318b32efcf8c9de681a78349ab12151
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751131"
---
# <a name="cprogressctrl-class"></a>CProgressCtrl 클래스

Windows의 공용 진행률 표시줄 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CProgressCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CProgressCtrl:::CProgressCtrl](#cprogressctrl)|`CProgressCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CProgressCtrl::만들기](#create)|진행률 표시줄 컨트롤을 만들고 `CProgressCtrl` 개체에 연결합니다.|
|[CProgressCtrl::만들기](#createex)|지정된 Windows 확장 스타일을 사용하여 진행률 컨트롤을 `CProgressCtrl` 만들고 개체에 연결합니다.|
|[CProgressCtrl::GetBarColor](#getbarcolor)|현재 진행률 표시줄 컨트롤에 대한 진행률 표시줄의 색상을 가져옵니다.|
|[CProgressCtrl::GetBkColor](#getbkcolor)|현재 진행률 표시줄의 배경색을 가져옵니다.|
|[CProgressCtrl::GetPos](#getpos)|진행률 표시줄의 현재 위치를 가져옵니다.|
|[CProgressCtrl::GetRange](#getrange)|진행률 표시줄 컨트롤 범위의 하한 및 상한을 가져옵니다.|
|[CProgressCtrl::겟스테이트](#getstate)|현재 진행률 표시줄 컨트롤의 상태를 가져옵니다.|
|[CProgressCtrl::GetStep](#getstep)|현재 진행률 표시줄 컨트롤의 진행률 표시줄에 대한 단계 증분을 검색합니다.|
|[CProgressCtrl::오프셋포지](#offsetpos)|지정된 증분으로 진행률 표시줄 컨트롤의 현재 위치를 진행하고 새 위치를 반영하도록 막대를 다시 그립니다.|
|[CProgressCtrl::세트바컬러](#setbarcolor)|현재 진행률 표시줄 컨트롤에서 진행률 표시줄의 색상을 설정합니다.|
|[CProgressCtrl:::SetBkColor](#setbkcolor)|진행률 표시줄의 배경색을 설정합니다.|
|[CProgressCtrl:::세트마키](#setmarquee)|현재 진행률 표시줄 컨트롤의 선택 윤곽 모드를 켜거나 끕니다.|
|[CProgressCtrl::세트포지](#setpos)|진행률 표시줄 컨트롤의 현재 위치를 설정하고 새 위치를 반영하도록 막대를 다시 그립니다.|
|[CProgressCtrl::세트 레인지](#setrange)|진행률 표시줄 컨트롤의 최소 및 최대 범위를 설정하고 새 범위를 반영하도록 막대를 다시 그립니다.|
|[CProgressCtrl::설정 상태](#setstate)|현재 진행률 표시줄 컨트롤의 상태를 설정합니다.|
|[CProgressCtrl:::세트스텝](#setstep)|진행률 표시줄 컨트롤에 대한 단계 증분을 지정합니다.|
|[CProgressCtrl::단계적](#stepit)|단계 [증분(SetStep](#setstep)참조)에 의해 진행률 막대 컨트롤의 현재 위치를 진행하고 새 위치를 반영하도록 막대를 다시 그립니다.|

## <a name="remarks"></a>설명

진행률 표시줄 컨트롤은 응용 프로그램이 긴 작업의 진행률을 나타내는 데 사용할 수 있는 창입니다. 작업이 진행됨에 따라 시스템 강조 표시 색상과 함께 왼쪽에서 오른쪽으로 점차 채워지는 사각형으로 구성됩니다.

진행률 표시줄 컨트롤에는 범위와 현재 위치가 있습니다. 범위는 작업의 총 기간을 나타내며 현재 위치는 응용 프로그램이 작업을 완료하는 동안 수행한 진행 률을 나타냅니다. 창 프로시저는 범위와 현재 위치를 사용하여 강조 표시 색상으로 채울 진행률 표시줄의 백분율을 결정합니다. 범위 와 현재 위치 값은 서명 된 정수로 표현되기 때문에 현재 위치 값의 가능한 범위는 -2,147,483,648에서 2,147,483,647까지입니다.

사용에 `CProgressCtrl`대한 자세한 내용은 [컨트롤](../../mfc/controls-mfc.md) 및 [CProgressCtrl 사용](../../mfc/using-cprogressctrl.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CProgressCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="cprogressctrlcprogressctrl"></a><a name="cprogressctrl"></a>CProgressCtrl:::CProgressCtrl

`CProgressCtrl` 개체를 생성합니다.

```
CProgressCtrl();
```

### <a name="remarks"></a>설명

개체를 생성한 `CProgressCtrl` 후 `CProgressCtrl::Create` 호출하여 진행률 표시줄 컨트롤을 만듭니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]

## <a name="cprogressctrlcreate"></a><a name="create"></a>CProgressCtrl::만들기

진행률 표시줄 컨트롤을 만들고 `CProgressCtrl` 개체에 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
진행률 표시줄 컨트롤의 스타일을 지정합니다. 다음 진행률 표시줄 컨트롤 스타일 외에도 [CreateWindow에](/windows/win32/api/winuser/nf-winuser-createwindoww) 설명된 창 스타일 조합을 컨트롤에 적용합니다.

- PBS_VERTICAL 진행률 정보를 위에서 아래로 세로로 표시합니다. 이 플래그가 없으면 진행률 표시줄 컨트롤이 왼쪽에서 오른쪽으로 가로로 표시됩니다.

- PBS_SMOOTH 진행률 표시줄 컨트롤에서 점진적, 원활한 채우기를 표시합니다. 이 플래그가 없으면 컨트롤이 블록으로 채워집니다.

*rect*<br/>
진행률 표시줄 컨트롤의 크기와 위치를 지정합니다. [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조일 수 있습니다. 컨트롤은 자식 창이어야 하므로 지정된 좌표는 *pParentWnd의*클라이언트 영역을 기준으로 합니다.

*pParentWnd*<br/>
진행률 표시줄 컨트롤의 부모 창(일반적으로 `CDialog`을 지정합니다.) NULL이 아니어야 합니다.

*nID*<br/>
진행률 표시줄 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 개체가 `CProgressCtrl` 성공적으로 만들어지면 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

두 단계로 `CProgressCtrl` 객체를 생성합니다. 먼저 개체를 만드는 생성자 `CProgressCtrl` 호출 한 다음 `Create`progress 막대 컨트롤을 만드는 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]

## <a name="cprogressctrlcreateex"></a><a name="createex"></a>CProgressCtrl::만들기

컨트롤(하위 창)을 만들고 `CProgressCtrl` 개체와 연결합니다.

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
진행률 표시줄 컨트롤의 스타일을 지정합니다. Windows SDK의 [CreateWindow에](/windows/win32/api/winuser/nf-winuser-createwindoww) 설명된 창 스타일의 조합을 적용합니다.

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

## <a name="cprogressctrlgetbarcolor"></a><a name="getbarcolor"></a>CProgressCtrl::GetBarColor

현재 진행률 표시줄 컨트롤에 대한 진행률 표시줄의 색상을 가져옵니다.

```
COLORREF GetBarColor() const;
```

### <a name="return-value"></a>Return Value

[COLORREF](/windows/win32/gdi/colorref) 값으로 표시되는 현재 진행률 막대의 색상 또는 진행률 표시줄 색상이 기본 색상인 경우 CLR_DEFAULT.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PBM_GETBARCOLOR](/windows/win32/Controls/pbm-getbarcolor) 메시지를 보냅니다.

## <a name="cprogressctrlgetbkcolor"></a><a name="getbkcolor"></a>CProgressCtrl::GetBkColor

현재 진행률 표시줄의 배경색을 가져옵니다.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Return Value

[COLORREF](/windows/win32/gdi/colorref) 값으로 표시되는 현재 진행률 막대의 배경색입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PBM_GETBKCOLOR](/windows/win32/Controls/pbm-getbkcolor) 메시지를 보냅니다.

## <a name="cprogressctrlgetpos"></a><a name="getpos"></a>CProgressCtrl::GetPos

진행률 표시줄의 현재 위치를 검색합니다.

```
int GetPos();
```

### <a name="return-value"></a>Return Value

진행률 표시줄 컨트롤의 위치입니다.

### <a name="remarks"></a>설명

진행률 표시줄 컨트롤의 위치는 화면의 물리적 위치가 아니라 [SetRange에](#setrange)표시된 위쪽 범위와 하부 범위 사이에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]

## <a name="cprogressctrlgetrange"></a><a name="getrange"></a>CProgressCtrl::GetRange

진행률 표시줄 컨트롤의 현재 하한 및 상한 또는 범위를 가져옵니다.

```cpp
void GetRange(
    int& nLower,
    int& nUpper);
```

### <a name="parameters"></a>매개 변수

*nLower*<br/>
진행률 표시줄 제어의 하한을 수신하는 정수에 대한 참조입니다.

*어퍼*<br/>
진행률 표시줄 컨트롤의 상한을 수신하는 정수에 대한 참조입니다.

### <a name="remarks"></a>설명

이 함수는 *nLower* 및 *nUpper에서*참조하는 정수에 하한 및 상한 값을 각각 복사합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]

## <a name="cprogressctrlgetstate"></a><a name="getstate"></a>CProgressCtrl::겟스테이트

현재 진행률 표시줄 컨트롤의 상태를 가져옵니다.

```
int GetState() const;
```

### <a name="return-value"></a>Return Value

다음 값 중 하나인 현재 진행률 표시줄 컨트롤의 상태입니다.

|값|시스템 상태|
|-----------|-----------|
|PBST_NORMAL|진행 중|
|PBST_ERROR|Error|
|PBST_PAUSED|일시 중지됨|

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PBM_GETSTATE](/windows/win32/Controls/pbm-getstate) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>예제

다음 코드 예제는 현재 진행률 표시줄 컨트롤의 상태를 검색합니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]

## <a name="cprogressctrlgetstep"></a><a name="getstep"></a>CProgressCtrl::GetStep

현재 진행률 표시줄 컨트롤의 진행률 표시줄에 대한 단계 증분을 검색합니다.

```
int GetStep() const;
```

### <a name="return-value"></a>Return Value

진행률 표시줄의 단계 증분입니다.

### <a name="remarks"></a>설명

단계 증분은 [CProgressCtrl::StepIt에](#stepit) 대한 호출이 진행률 표시줄의 현재 위치를 증가시키는 양입니다.

이 메서드는 Windows SDK에 설명 된 [PBM_GETSTEP](/windows/win32/Controls/pbm-getstep) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 현재 진행률 표시줄 컨트롤의 단계 증분을 검색합니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]

## <a name="cprogressctrloffsetpos"></a><a name="offsetpos"></a>CProgressCtrl::오프셋포지

*nPos에서* 지정한 증분으로 진행률 표시줄 컨트롤의 현재 위치를 진행하고 새 위치를 반영하도록 막대를 다시 그립니다.

```
int OffsetPos(int nPos);
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
위치를 진행하는 금액.

### <a name="return-value"></a>Return Value

진행률 표시줄 컨트롤의 이전 위치입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]

## <a name="cprogressctrlsetbarcolor"></a><a name="setbarcolor"></a>CProgressCtrl::세트바컬러

현재 진행률 표시줄 컨트롤에서 진행률 표시줄의 색상을 설정합니다.

```
COLORREF SetBarColor(COLORREF clrBar);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*클러바*|【인】 진행률 표시줄의 새 색상을 지정하는 [COLORREF](/windows/win32/gdi/colorref) 값입니다. 진행률 표시줄이 기본 색상을 사용하도록 CLR_DEFAULT 지정합니다.|

### <a name="return-value"></a>Return Value

[COLORREF](/windows/win32/gdi/colorref) 값으로 표시되는 진행률 표시막대의 이전 색상 또는 진행률 표시줄의 색상이 기본 색상인 경우 CLR_DEFAULT.

### <a name="remarks"></a>설명

이 `SetBarColor` 메서드는 Windows Vista [테마가](/windows/win32/Controls/visual-styles-overview) 적용되지 않는 경우에만 진행률 표시줄 색상을 설정합니다.

이 메서드는 Windows SDK에 설명 된 [PBM_SETBARCOLOR](/windows/win32/Controls/pbm-setbarcolor) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 진행률 표시줄의 색상을 빨간색, 녹색, 파란색 또는 기본값으로 변경합니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]

## <a name="cprogressctrlsetbkcolor"></a><a name="setbkcolor"></a>CProgressCtrl:::SetBkColor

진행률 표시줄의 배경색을 설정합니다.

```
COLORREF SetBkColor(COLORREF clrNew);
```

### <a name="parameters"></a>매개 변수

*clrNew*<br/>
새 배경색을 지정하는 COLORREF 값입니다. 진행률 표시줄에 대한 기본 배경색을 사용하도록 CLR_DEFAULT 값을 지정합니다.

### <a name="return-value"></a>Return Value

[COLORREF](/windows/win32/gdi/colorref) 값은 이전 배경 색을 나타내거나 배경색이 기본 색상인 경우 CLR_DEFAULT.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]

## <a name="cprogressctrlsetmarquee"></a><a name="setmarquee"></a>CProgressCtrl:::세트마키

현재 진행률 표시줄 컨트롤의 선택 윤곽 모드를 켜거나 끕니다.

```
BOOL SetMarquee(
    BOOL fMarqueeMode,
    int nInterval);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*fMarqueeMode 모드*|【인】 선택 윤곽 모드를 켜거나 FALSE를 사용하여 선택 윤곽 모드를 끕니다.|
|*n간격*|【인】 선택 윤곽 애니메이션 업데이트 사이의 시간(밀리초)입니다.|

### <a name="return-value"></a>Return Value

이 메서드는 항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

선택 윤곽 모드가 켜져 있으면 진행률 표시줄이 애니메이션되고 극장 선택 윤곽의 기호처럼 스크롤됩니다.

이 메서드는 Windows SDK에 설명 된 [PBM_SETMARQUEE](/windows/win32/Controls/pbm-setmarquee) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 선택 윤곽 스크롤 애니메이션을 시작하고 중지합니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]

## <a name="cprogressctrlsetpos"></a><a name="setpos"></a>CProgressCtrl::세트포지

진행률 표시줄 컨트롤의 현재 위치를 *nPos에서* 지정한 대로 설정하고 새 위치를 반영하도록 막대를 다시 그립니다.

```
int SetPos(int nPos);
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
진행률 표시줄 컨트롤의 새 위치입니다.

### <a name="return-value"></a>Return Value

진행률 표시줄 컨트롤의 이전 위치입니다.

### <a name="remarks"></a>설명

진행률 표시줄 컨트롤의 위치는 화면의 물리적 위치가 아니라 [SetRange에](#setrange)표시된 위쪽 범위와 하부 범위 사이에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]

## <a name="cprogressctrlsetrange"></a><a name="setrange"></a>CProgressCtrl::세트 레인지

진행률 표시줄 컨트롤 범위의 상한및 하한을 설정하고 새 범위를 반영하도록 막대를 다시 그립니다.

```cpp
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>매개 변수

*nLower*<br/>
범위의 하한을 지정합니다(기본값은 0).

*어퍼*<br/>
범위의 상한을 지정합니다(기본값은 100).

### <a name="remarks"></a>설명

멤버 함수는 `SetRange32` 진행률 컨트롤에 대한 32비트 범위를 설정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]

## <a name="cprogressctrlsetstate"></a><a name="setstate"></a>CProgressCtrl::설정 상태

현재 진행률 표시줄 컨트롤의 상태를 설정합니다.

```
int SetState(int iState);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*아이 스테이트*|【인】 진행률 표시줄을 설정하는 상태입니다. 다음 값 중 하나를 사용합니다.<br /><br /> - PBST_NORMAL - 진행 중<br />- PBST_ERROR - 오류<br />- PBST_PAUSED - 일시 중지|

### <a name="return-value"></a>Return Value

현재 진행률 표시줄 컨트롤의 이전 상태입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [PBM_SETSTATE](/windows/win32/Controls/pbm-setstate) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 현재 진행률 표시줄 컨트롤의 상태를 일시 중지됨 또는 진행 중으로 설정합니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]

## <a name="cprogressctrlsetstep"></a><a name="setstep"></a>CProgressCtrl:::세트스텝

진행률 표시줄 컨트롤에 대한 단계 증분을 지정합니다.

```
int SetStep(int nStep);
```

### <a name="parameters"></a>매개 변수

*n스텝*<br/>
새 단계 증분.

### <a name="return-value"></a>Return Value

이전 단계 증분입니다.

### <a name="remarks"></a>설명

단계 증분은 진행률 표시줄의 `CProgressCtrl::StepIt` 현재 위치를 증가시키기 위한 호출의 양입니다.

기본 단계 증분은 10입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]

## <a name="cprogressctrlstepit"></a><a name="stepit"></a>CProgressCtrl::단계적

단계 증분에 의해 진행률 막대 컨트롤에 대한 현재 위치를 진행하고 새 위치를 반영하도록 막대를 다시 그립니다.

```
int StepIt();
```

### <a name="return-value"></a>Return Value

진행률 표시줄 컨트롤의 이전 위치입니다.

### <a name="remarks"></a>설명

단계 증분은 멤버 함수에 `CProgressCtrl::SetStep` 의해 설정됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
