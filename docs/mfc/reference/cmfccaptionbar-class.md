---
title: CMFCCaptionBar 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
helpviewer_keywords:
- CMFCCaptionBar [MFC], Create
- CMFCCaptionBar [MFC], DoesAllowDynInsertBefore
- CMFCCaptionBar [MFC], EnableButton
- CMFCCaptionBar [MFC], GetAlignment
- CMFCCaptionBar [MFC], GetBorderSize
- CMFCCaptionBar [MFC], GetButtonRect
- CMFCCaptionBar [MFC], GetMargin
- CMFCCaptionBar [MFC], IsMessageBarMode
- CMFCCaptionBar [MFC], RemoveBitmap
- CMFCCaptionBar [MFC], RemoveButton
- CMFCCaptionBar [MFC], RemoveIcon
- CMFCCaptionBar [MFC], RemoveText
- CMFCCaptionBar [MFC], SetBitmap
- CMFCCaptionBar [MFC], SetBorderSize
- CMFCCaptionBar [MFC], SetButton
- CMFCCaptionBar [MFC], SetButtonPressed
- CMFCCaptionBar [MFC], SetButtonToolTip
- CMFCCaptionBar [MFC], SetFlatBorder
- CMFCCaptionBar [MFC], SetIcon
- CMFCCaptionBar [MFC], SetImageToolTip
- CMFCCaptionBar [MFC], SetMargin
- CMFCCaptionBar [MFC], SetText
- CMFCCaptionBar [MFC], OnDrawBackground
- CMFCCaptionBar [MFC], OnDrawBorder
- CMFCCaptionBar [MFC], OnDrawButton
- CMFCCaptionBar [MFC], OnDrawImage
- CMFCCaptionBar [MFC], OnDrawText
- CMFCCaptionBar [MFC], m_clrBarBackground
- CMFCCaptionBar [MFC], m_clrBarBorder
- CMFCCaptionBar [MFC], m_clrBarText
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
ms.openlocfilehash: c42b1ccb51a3c290e0887717d900543b8d5b277a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752623"
---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar 클래스

`CMFCCaptionBar` 개체는 단추, 텍스트 레이블 및 비트맵의 세 가지 요소를 표시할 수 있는 컨트롤 막대입니다. 각 형식의 요소를 한 번에 하나만 표시할 수 있습니다. 각 요소를 컨트롤의 왼쪽 또는 오른쪽 가장자리나 가운데에 맞출 수 있습니다. 평면 또는 3D 스타일을 캡션 표시줄의 위쪽 및 아래쪽 테두리에 적용할 수도 있습니다.

## <a name="syntax"></a>구문

```
class CMFCCaptionBar : public CPane
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC 캡션바::만들기](#create)|캡션 막대 컨트롤을 만들고 개체에 `CMFCCaptionBar` 연결합니다.|
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|캡션 막대와 상위 프레임 사이에 다른 창을 동적으로 삽입할 수 있는지 여부를 나타냅니다. [(재정의 CBasePane::DoesAllowDyn인가 전에](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFC 캡션바::사용 버튼](#enablebutton)|캡션 표시줄의 단추를 활성화하거나 사용하지 않도록 설정합니다.|
|[CMFC 캡션바::정렬 정렬](#getalignment)|지정된 요소의 선형을 반환합니다.|
|[CMFC 캡션바::GetBorderSize](#getbordersize)|캡션 막대의 테두리 크기를 반환합니다.|
|[CMFC 캡션바::GetButtonRect](#getbuttonrect)|캡션 막대에서 단추의 경계 사각형을 검색합니다.|
|[CMFC 캡션바::겟마진](#getmargin)|캡션 막대 요소의 가장자리와 캡션 막대 컨트롤의 가장자리 사이의 거리를 반환합니다.|
|[CMFC 캡션바::이메시지 바모드](#ismessagebarmode)|캡션 막대가 메시지 표시줄 모드에 있는지 여부를 지정합니다.|
|[CMFC캡션바::리모크비트맵](#removebitmap)|캡션 표시줄에서 비트맵 이미지를 제거합니다.|
|[CMFC 캡션바::제거 버튼](#removebutton)|캡션 표시줄에서 단추를 제거합니다.|
|[CMFC캡션바::리모크아이콘](#removeicon)|캡션 표시줄에서 아이콘을 제거합니다.|
|[CMFC 캡션바::삭제텍스트](#removetext)|캡션 표시줄에서 텍스트 레이블을 제거합니다.|
|[CMFC캡션바::세트비트맵](#setbitmap)|캡션 막대의 비트맵 이미지를 설정합니다.|
|[CMFC 캡션바::설정경계 크기](#setbordersize)|캡션 막대의 테두리 크기를 설정합니다.|
|[CMFC 캡션바::설정 버튼](#setbutton)|캡션 막대의 단추를 설정합니다.|
|[CMFC 캡션바::버튼 누른](#setbuttonpressed)|단추를 계속 누른 상태로 유지되는지 여부를 지정합니다.|
|[CMFC 캡션바::설정 단추도구 팁](#setbuttontooltip)|단추의 도구 설명입니다.|
|[CMFC 캡션바::세트플랫보더](#setflatborder)|캡션 막대의 테두리 스타일을 설정합니다.|
|[CMFC캡션바::세티콘](#seticon)|캡션 막대의 아이콘을 설정합니다.|
|[CMFC 캡션바::세트이미지툴팁](#setimagetooltip)|캡션 막대의 이미지에 대한 도구 설명입니다.|
|[CMFC캡션바::세트마진](#setmargin)|캡션 막대 요소의 가장자리와 캡션 막대 컨트롤의 가장자리 사이의 거리를 설정합니다.|
|[CMFC 캡션바::SetText](#settext)|캡션 막대의 텍스트 레이블을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC 캡션바::온드로우백](#ondrawbackground)|캡션 막대의 배경을 채우기 위해 프레임워크에서 호출됩니다.|
|[CMFC캡션바::온드로우보더](#ondrawborder)|캡션 막대의 테두리를 그리는 프레임워크에서 호출됩니다.|
|[CMFC 캡션바::온드로우 버튼](#ondrawbutton)|캡션 막대 단추를 그리는 프레임워크에서 호출됩니다.|
|[CMFC 캡션바::온드로우 이미지](#ondrawimage)|캡션 막대 이미지를 그리는 프레임워크에서 호출됩니다.|
|[CMFC 캡션바::온드로우텍스트](#ondrawtext)|캡션 막대 텍스트를 그리는 프레임워크에서 호출됩니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CMFC캡션바::m_clrBarBackground](#m_clrbarbackground)|캡션 막대의 배경색입니다.|
|[CMFC캡션바::m_clrBarBorder](#m_clrbarborder)|캡션 막대의 테두리의 색상입니다.|
|[CMFC캡션바::m_clrBarText](#m_clrbartext)|캡션 막대 텍스트의 색상입니다.|

## <a name="remarks"></a>설명

캡션 막대를 만들려면 다음 단계를 따르세요.

1. `CMFCCaptionBar` 개체를 생성합니다. 일반적으로 프레임 창 클래스에 캡션 막대를 추가합니다.

1. [CMFCCaptionBar::Create](#create) 메서드를 호출하여 캡션 막대 컨트롤을 `CMFCCaptionBar` 만들고 개체에 연결합니다.

1. [CMFC캡션Bar::SetButton,](#setbutton) [CMFC캡션Bar::SetText,](#settext) [CMFC캡션Bar::SetIcon](#seticon)및 [CMFCCaptionBar::SetBitmap을](#setbitmap) 사용하여 캡션 막대 요소를 설정합니다.

단추 요소를 설정할 때 단추에 명령 ID를 할당해야 합니다. 사용자가 단추를 클릭하면 캡션 막대는 이 ID가 있는 WM_COMMAND 메시지를 부모 프레임 창으로 라우팅합니다.

캡션 표시줄은 Microsoft Office 2007 응용 프로그램에 나타나는 메시지 표시줄을 에뮬레이트하는 메시지 표시줄 모드에서도 작동할 수 있습니다. 메시지 표시줄 모드에서 캡션 막대에는 비트맵, 메시지 및 버튼(일반적으로 대화 상자가 열리는)이 표시됩니다. 도구 팁을 비트맵에 할당할 수 있습니다.

메시지 표시줄 모드를 사용하려면 [CMFCCaptionBar::만들기를](#create) 호출하고 네 번째 매개 변수(bIsMessageBarMode)를 TRUE로 설정합니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCCaptionBar` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 캡션 막대 컨트롤을 만들고, 캡션 막대의 3D 테두리를 설정하고, 캡션 막대 요소의 가장자리와 캡션 막대 컨트롤의 가장자리 사이의 거리를 픽셀 단위로 설정하고, 캡션 막대의 단추를 설정하고, 단추에 대한 도구 설명세트를 설정하고, 캡션 막대의 텍스트 레이블을 설정하고, 캡션 막대의 비트맵 이미지를 설정하는 방법을 보여 주며, 캡션 막대의 비트맵 이미지를 설정하는 방법을 보여 주며, 캡션 막대의 3D 테두리를 설정합니다. 을 클릭하고 캡션 막대에서 이미지에 대한 도구 설명입니다. 이 코드 조각은 MS [Office 2007 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afx캡션바.h

## <a name="cmfccaptionbarcreate"></a><a name="create"></a>CMFC 캡션바::만들기

캡션 막대 컨트롤을 만들고 개체에 `CMFCCaptionBar` 연결합니다.

```
BOOL Create(
    DWORD dwStyle,
    CWnd* pParentWnd,
    UINT uID,
    int nHeight=-1,
    BOOL bIsMessageBarMode=FALSE);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
캡션 막대 스타일의 논리적 OR 조합입니다.

*pParentWnd*<br/>
캡션 막대 컨트롤의 상위 창입니다.

*Uid*<br/>
캡션 막대 컨트롤의 ID입니다.

*nHeight*<br/>
캡션 막대 컨트롤의 높이(픽셀 단위)입니다. -1이면 높이가 아이콘의 높이, 텍스트 및 캡션 막대 컨트롤이 표시하는 단추에 따라 계산됩니다.

*비스메시지바모드*<br/>
캡션 막대가 메시지 표시줄 모드에 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="return-value"></a>Return Value

캡션 막대 컨트롤이 성공적으로 만들어지면 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

두 단계로 `CMFCCaptionBar` 객체를 생성합니다. 먼저 생성자 호출 한 다음 Windows `Create` 컨트롤을 만들고 `CMFCCaptionBar` 개체에 연결 하는 메서드를 호출 합니다.

## <a name="cmfccaptionbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CMFC 캡션바::DoesAllowDyn인더인

캡션 막대와 상위 프레임 사이에 다른 창을 동적으로 삽입할 수 있는지 여부를 나타냅니다.

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Return Value

재정의하지 않는 한 FALSE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfccaptionbarenablebutton"></a><a name="enablebutton"></a>CMFC 캡션바::사용 버튼

캡션 표시줄의 단추를 활성화하거나 사용하지 않도록 설정합니다.

```cpp
void EnableButton(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE 버튼을 활성화하려면 FALSE가 버튼을 비활성화합니다.

## <a name="cmfccaptionbargetalignment"></a><a name="getalignment"></a>CMFC 캡션바::정렬 정렬

지정된 요소의 선형을 반환합니다.

```
BarElementAlignment GetAlignment(BarElement elem);
```

### <a name="parameters"></a>매개 변수

*Elem*<br/>
【인】 선형을 검색할 캡션 막대 요소입니다.

### <a name="return-value"></a>Return Value

단추, 비트맵, 텍스트 또는 아이콘과 같은 요소의 정렬입니다.

### <a name="remarks"></a>설명

요소의 정렬은 다음 값 중 하나일 수 있습니다.

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbargetbordersize"></a><a name="getbordersize"></a>CMFC 캡션바::GetBorderSize

캡션 막대의 테두리 크기를 반환합니다.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Return Value

테두리의 크기(픽셀 단위)입니다.

## <a name="cmfccaptionbargetbuttonrect"></a><a name="getbuttonrect"></a>CMFC 캡션바::GetButtonRect

캡션 막대에서 단추의 경계 사각형을 검색합니다.

```
CRect GetButtonRect() const;
```

### <a name="return-value"></a>Return Value

캡션 `CRect` 막대에 있는 단추의 경계 사각형의 좌표를 포함하는 개체입니다.

## <a name="cmfccaptionbargetmargin"></a><a name="getmargin"></a>CMFC 캡션바::겟마진

캡션 막대 요소의 가장자리와 캡션 막대 컨트롤의 가장자리 사이의 거리를 반환합니다.

```
int GetMargin() const;
```

### <a name="return-value"></a>Return Value

캡션 막대 요소의 가장자리와 캡션 막대 컨트롤의 가장자리 사이의 거리(픽셀 단위)입니다.

## <a name="cmfccaptionbarismessagebarmode"></a><a name="ismessagebarmode"></a>CMFC 캡션바::이메시지 바모드

캡션 막대가 메시지 표시줄 모드에 있는지 여부를 지정합니다.

```
BOOL IsMessageBarMode() const;
```

### <a name="return-value"></a>Return Value

캡션 막대가 메시지 표시줄 모드에 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

메시지 표시줄 모드에서 캡션 막대는 도구 설명, 메시지 텍스트 및 단추가 있는 이미지를 표시합니다.

## <a name="cmfccaptionbarm_clrbarbackground"></a><a name="m_clrbarbackground"></a>CMFC캡션바::m_clrBarBackground

캡션 막대의 배경색입니다.

```
COLORREF m_clrBarBackground
```

## <a name="cmfccaptionbarm_clrbarborder"></a><a name="m_clrbarborder"></a>CMFC캡션바::m_clrBarBorder

캡션 막대의 테두리의 색상입니다.

```
COLORREF m_clrBarBorder
```

## <a name="cmfccaptionbarm_clrbartext"></a><a name="m_clrbartext"></a>CMFC캡션바::m_clrBarText

캡션 막대 텍스트의 색상입니다.

```
COLORREF m_clrBarText
```

## <a name="cmfccaptionbarondrawbackground"></a><a name="ondrawbackground"></a>CMFC 캡션바::온드로우백

캡션 막대의 배경을 채우기 위해 프레임워크에서 호출됩니다.

```
virtual void OnDrawBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 캡션 막대의 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 채울 경계 사각형입니다.

### <a name="remarks"></a>설명

캡션 `OnDrawBackground` 막대의 배경이 채워질 때 메서드가 호출됩니다. 기본 구현은 [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground) 색상을 사용하여 배경을 채웁니다.

파생 클래스에서 이 `CMFCCaptionBar` 메서드를 재정의하여 캡션 막대의 모양을 사용자 지정합니다.

## <a name="cmfccaptionbarondrawborder"></a><a name="ondrawborder"></a>CMFC캡션바::온드로우보더

캡션 막대의 테두리를 그리는 프레임워크에서 호출됩니다.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 테두리를 표시하는 데 사용되는 장치 컨텍스트입니다.

*rect*<br/>
【인】 경계 사각형입니다.

### <a name="remarks"></a>설명

기본적으로 테두리에는 플랫 스타일이 있습니다.

파생 클래스에서 이 `CMFCCaptionBar` 메서드를 재정의하여 캡션 막대의 테두리 모양을 사용자 지정합니다.

## <a name="cmfccaptionbarondrawbutton"></a><a name="ondrawbutton"></a>CMFC 캡션바::온드로우 버튼

캡션 막대 단추를 그리는 프레임워크에서 호출됩니다.

```
virtual void OnDrawButton(
    CDC* pDC,
    CRect rect,
    const CString& strButton,
    BOOL bEnabled);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 단추를 표시하는 데 사용되는 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 단추의 경계 사각형입니다.

*스트버튼*<br/>
【인】 단추의 텍스트 레이블입니다.

*bEnabled*<br/>
【인】 TRUE 버튼이 활성화되어 있는 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

파생 클래스에서 이 `CMFCCaptionBar` 메서드를 재정의하여 캡션 막대 단추의 모양을 사용자 지정합니다.

## <a name="cmfccaptionbarondrawimage"></a><a name="ondrawimage"></a>CMFC 캡션바::온드로우 이미지

캡션 막대 이미지를 그리는 프레임워크에서 호출됩니다.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 이미지를 표시하는 데 사용되는 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 이미지의 경계 사각형을 지정합니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 `CMFCCaptionBar` 메서드를 재정의하여 이미지 모양을 사용자 지정합니다.

## <a name="cmfccaptionbarondrawtext"></a><a name="ondrawtext"></a>CMFC 캡션바::온드로우텍스트

캡션 막대 텍스트를 그리는 프레임워크에서 호출됩니다.

```
virtual void OnDrawText(
    CDC* pDC,
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 단추를 표시하는 데 사용되는 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 텍스트의 경계 사각형입니다.

*strText*<br/>
【인】 표시할 텍스트 문자열입니다.

### <a name="remarks"></a>설명

기본 구현은 `CDC::DrawText` [CMFCCaptionBar::m_clrBarText](#m_clrbartext) 색상을 사용하여 텍스트를 표시합니다.

파생 클래스에서 이 `CMFCCaptionBar` 메서드를 재정의하여 캡션 막대텍스트의 모양을 사용자 지정합니다.

## <a name="cmfccaptionbarremovebitmap"></a><a name="removebitmap"></a>CMFC캡션바::리모크비트맵

캡션 표시줄에서 비트맵 이미지를 제거합니다.

```cpp
void RemoveBitmap();
```

## <a name="cmfccaptionbarremovebutton"></a><a name="removebutton"></a>CMFC 캡션바::제거 버튼

캡션 표시줄에서 단추를 제거합니다.

```cpp
void RemoveButton();
```

### <a name="remarks"></a>설명

캡션 막대 요소의 레이아웃이 자동으로 조정됩니다.

## <a name="cmfccaptionbarremoveicon"></a><a name="removeicon"></a>CMFC캡션바::리모크아이콘

캡션 표시줄에서 아이콘을 제거합니다.

```cpp
void RemoveIcon();
```

## <a name="cmfccaptionbarremovetext"></a><a name="removetext"></a>CMFC 캡션바::삭제텍스트

캡션 표시줄에서 텍스트 레이블을 제거합니다.

```cpp
void RemoveText();
```

## <a name="cmfccaptionbarsetbitmap"></a><a name="setbitmap"></a>CMFC캡션바::세트비트맵

캡션 막대의 비트맵 이미지를 설정합니다.

```cpp
void SetBitmap(
    HBITMAP hBitmap,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

void SetBitmap(
    UINT uiBmpResID,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>매개 변수

*hBitmap*<br/>
【인】 설정할 비트맵의 핸들입니다.

*clr투명*<br/>
【인】 비트맵의 투명 색상을 지정하는 RGB 값입니다.

*b스트레치*<br/>
【인】 TRUE인 경우 비트맵이 이미지 경계 사각형에 맞지 않으면 늘어납니다. 그렇지 않으면 비트맵이 늘어나지 않습니다.

*bmp정렬*<br/>
【인】 비트맵의 정렬입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 캡션 막대에 비트맵을 설정합니다.

이전 비트맵이 자동으로 소멸됩니다. [CMFCCaptionBar::SetIcon](#seticon) 메서드를 호출했기 때문에 캡션 표시줄에 아이콘이 표시되면 [CMFCCaptionBar::RemoveIcon을](#removeicon)호출하여 아이콘을 제거하지 않으면 비트맵이 표시되지 않습니다.

비트맵은 *bmpAlignment* 매개 변수에 의해 지정된 대로 정렬됩니다.  이 매개 변수는 다음 `BarElementAlignment` 값 중 하나일 수 있습니다.

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetbordersize"></a><a name="setbordersize"></a>CMFC 캡션바::설정경계 크기

캡션 막대의 테두리 크기를 설정합니다.

```cpp
void SetBorderSize(int nSize);
```

### <a name="parameters"></a>매개 변수

*nSize*<br/>
【인】 캡션 막대 테두리의 새 크기(픽셀 단위)입니다.

## <a name="cmfccaptionbarsetbutton"></a><a name="setbutton"></a>CMFC 캡션바::설정 버튼

캡션 막대의 단추를 설정합니다.

```cpp
void SetButton(
    LPCTSTR lpszLabel,
    UINT uiCmdUI,
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,
    BOOL bHasDropDownArrow=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
단추의 명령 레이블입니다.

*uiCmdui*<br/>
단추의 명령 ID입니다.

*btnAlignmnet*<br/>
단추의 정렬입니다.

*bHasDropDownArrow*<br/>
TRUE 단추에 드롭다운 화살표가 표시되면 FALSE가 표시됩니다.

## <a name="cmfccaptionbarsetbuttonpressed"></a><a name="setbuttonpressed"></a>CMFC 캡션바::버튼 누른

단추를 계속 누른 상태로 유지되는지 여부를 지정합니다.

```cpp
void SetButtonPressed(BOOL bPresed=TRUE);
```

### <a name="parameters"></a>매개 변수

*bPresed*<br/>
TRUE 단추의 누른 상태를 유지 하는 경우 TRUE, FALSE 그렇지 않으면.

## <a name="cmfccaptionbarsetbuttontooltip"></a><a name="setbuttontooltip"></a>CMFC 캡션바::설정 단추도구 팁

단추의 도구 설명입니다.

```cpp
void SetButtonToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>매개 변수

*lpszToolTip*<br/>
【인】 도구 설명 캡션입니다.

*lpszDescription*<br/>
【인】 도구 설명 설명입니다.

## <a name="cmfccaptionbarsetflatborder"></a><a name="setflatborder"></a>CMFC 캡션바::세트플랫보더

캡션 막대의 테두리 스타일을 설정합니다.

```cpp
void SetFlatBorder(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>매개 변수

*b플랫*<br/>
【인】 캡션 막대의 테두리가 평평한 경우 TRUE입니다. 테두리가 3D인 경우 FALSE입니다.

## <a name="cmfccaptionbarseticon"></a><a name="seticon"></a>CMFC캡션바::세티콘

캡션 막대의 아이콘을 설정합니다.

```cpp
void SetIcon(
    HICON hIcon,
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>매개 변수

*hIcon*<br/>
【인】 설정할 아이콘의 핸들입니다.

*아이콘정렬*<br/>
【인】 아이콘의 정렬입니다.

### <a name="remarks"></a>설명

캡션 막대는 아이콘 또는 비트맵을 표시할 수 있습니다. 비트맵을 표시하는 방법을 알아보려면 [CMFC캡션Bar::SetBitmap을](#setbitmap) 참조하십시오. 아이콘과 비트맵을 모두 설정하면 아이콘이 항상 표시됩니다. [CMFC캡션Bar::RemoveIcon을](#removeicon) 호출하여 캡션 바에서 아이콘을 제거합니다.

아이콘은 *아이콘정렬* 매개 변수에 따라 정렬됩니다. 다음 `BarElementAlignment` 값 중 하나가 될 수 있습니다.

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetimagetooltip"></a><a name="setimagetooltip"></a>CMFC 캡션바::세트이미지툴팁

캡션 막대에서 이미지의 도구 설명입니다.

```cpp
void SetImageToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>매개 변수

*lpszToolTip*<br/>
【인】 도구 설명의 텍스트입니다.

*lpszDescription*<br/>
【인】 도구 설명 설명입니다.

## <a name="cmfccaptionbarsetmargin"></a><a name="setmargin"></a>CMFC캡션바::세트마진

캡션 막대 요소의 가장자리와 캡션 막대 컨트롤의 가장자리 사이의 거리를 설정합니다.

```cpp
void SetMargin(int nMargin);
```

### <a name="parameters"></a>매개 변수

*nMargin*<br/>
【인】 캡션 막대 요소의 가장자리와 캡션 막대 컨트롤의 가장자리 사이의 거리(픽셀 단위)입니다.

## <a name="cmfccaptionbarsettext"></a><a name="settext"></a>CMFC 캡션바::SetText

캡션 막대의 텍스트 레이블을 설정합니다.

```cpp
void SetText(
    const CString& strText,
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>매개 변수

*strText*<br/>
【인】 설정할 텍스트 문자열입니다.

*텍스트 정렬*<br/>
【인】 텍스트 정렬입니다.

### <a name="remarks"></a>설명

텍스트 레이블은 *텍스트정렬* 매개변수에 지정된 대로 정렬됩니다. 다음 `BarElementAlignment` 값 중 하나가 될 수 있습니다.

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
