---
title: CMFC캡션버튼 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
ms.openlocfilehash: 1b0a999f1fd1e3df1b0a971220454397cead02a9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752602"
---
# <a name="cmfccaptionbutton-class"></a>CMFC캡션버튼 클래스

클래스는 `CMFCCaptionButton` 도킹 창 또는 미니 프레임 창에 대 한 캡션 표시줄에 표시 되는 단추를 구현 합니다. 일반적으로 프레임워크는 캡션 단추를 자동으로 만듭니다.

## <a name="syntax"></a>구문

```
class CMFCCaptionButton : public CObject
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|속성|Description|
|----------|-----------------|
|[CMFC 캡션 버튼::CMFC캡션버튼](#cmfccaptionbutton)|CMFC캡션Button 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC 캡션 버튼 :: 겟히트](#gethit)|단추로 표시되는 명령을 반환합니다.|
|[CMFC 캡션 버튼::게시니드](#geticonid)|단추와 연결된 이미지 ID를 반환합니다.|
|[CMFC 캡션 버튼::GetRect](#getrect)|단추에서 차지하는 사각형을 반환합니다.|
|[CMFC 캡션 버튼 ::GetSize](#getsize)|단추의 너비와 높이를 반환합니다.|
|[CMFC캡션버튼::이스미니프레임 버튼](#isminiframebutton)|제목 막대 높이가 미니 크기로 설정되어 있는지 여부를 나타냅니다.|
|[CMFC 캡션버튼::이동](#move)|단추 그리기 위치와 창 표시 상태를 설정합니다.|
|[CMFC 캡션 버튼::온드로우](#ondraw)|캡션 단추를 그립니다.|
|[CMFC캡션버튼::셋미니프레임버튼](#setminiframebutton)|제목 표시줄의 미니 크기를 설정합니다.|

## <a name="remarks"></a>설명

[CPaneFrameWnd 클래스에서](../../mfc/reference/cpaneframewnd-class.md) 클래스를 파생 하고 보호 `AddButton`된 메서드를 사용 하 여 캡션 단추를 미니 프레임 창에 추가할 수 있습니다.

CPaneFrameWnd.h는 두 가지 유형의 캡션 단추에 대한 명령 암호를 정의합니다.

- AFX_CAPTION_BTN_PIN 고정 창이 자동 숨기기 모드를 지원할 때 핀 버튼을 표시합니다.

- 창을 닫거나 숨길 수 있을 때 **닫기** 단추를 표시하는 AFX_CAPTION_BTN_CLOSE.

## <a name="example"></a>예제

다음 예제에서는 개체를 `CMFCCaptionButton` 생성하고 제목 표시줄의 미니 크기를 설정하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afx캡션버튼.h

## <a name="cmfccaptionbuttoncmfccaptionbutton"></a><a name="cmfccaptionbutton"></a>CMFC 캡션 버튼::CMFC캡션버튼

`CMFCCaptionButton` 개체를 생성합니다.

```
CMFCCaptionButton();

CMFCCaptionButton(
    UINT nHit,
    BOOL bLeftAlign = FALSE);
```

### <a name="parameters"></a>매개 변수

*n히트 (것)엔 히트*<br/>
【인】 단추와 연결된 명령입니다.

*bLeft정렬*<br/>
【인】 단추를 왼쪽에 정렬하는지 여부를 지정합니다.

다음 표에는 nHit 매개 변수에 대한 가능한 값이 *나열됩니다.*

|값|명령|
|-----------|-------------|
|AFX_HTCLOSE|버튼을 닫습니다.|
|HTMINBUTTON|버튼을 최소화합니다.|
|HTMAXBUTTON|버튼을 최대화합니다.|
|AFX_HTLEFTBUTTON|왼쪽 화살표 버튼.|
|AFX_HTRIGHTBUTTON|오른쪽 화살표 버튼.|
|AFX_HTMENU|아래쪽 화살표 메뉴 버튼입니다.|
|HTNOWHERE|기본값; 은 명령을 나타내지 않습니다.|

### <a name="remarks"></a>설명

기본적으로 캡션 단추는 명령과 연결되지 않습니다.

캡션 버튼은 오른쪽 또는 왼쪽에 정렬됩니다.

## <a name="cmfccaptionbuttongethit"></a><a name="gethit"></a>CMFC 캡션 버튼 :: 겟히트

단추로 표시되는 명령을 반환합니다.

```
UINT GetHit() const;
```

### <a name="return-value"></a>Return Value

단추로 표시되는 명령입니다.

다음 표에는 가능한 반환 값이 나열되어 있습니다.

|값|명령|
|-----------|-------------|
|AFX_HTCLOSE|버튼을 닫습니다.|
|HTMINBUTTON|버튼을 최소화합니다.|
|HTMAXBUTTON|버튼을 최대화합니다.|
|AFX_HTLEFTBUTTON|왼쪽 화살표 버튼.|
|AFX_HTRIGHTBUTTON|오른쪽 화살표 버튼.|
|AFX_HTMENU|아래쪽 화살표 메뉴 버튼입니다.|
|HTNOWHERE|기본값; 은 명령을 나타내지 않습니다.|

## <a name="cmfccaptionbuttongeticonid"></a><a name="geticonid"></a>CMFC 캡션 버튼::게시니드

단추와 연결된 이미지 ID를 반환합니다.

```
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,
    BOOL bMaximized = FALSE) const;
```

### <a name="parameters"></a>매개 변수

*b호르츠 (주)*<br/>
【인】 왼쪽 또는 오른쪽 화살표 이미지 의 경우 TRUE; 위쪽 또는 아래쪽 화살표 이미지 아이디에 대한 FALSE입니다.

*b최대화*<br/>
【인】 이미지 ID를 최대화하기 위한 TRUE; 이미지 ID 최소화에 대한 FALSE입니다.

### <a name="return-value"></a>Return Value

이미지 ID입니다.

### <a name="remarks"></a>설명

매개 변수는 캡션 단추를 최소화하거나 최대화하기 위해 이미지 ID를 지정합니다.

## <a name="cmfccaptionbuttongetrect"></a><a name="getrect"></a>CMFC 캡션 버튼::GetRect

단추에서 차지하는 사각형을 반환합니다.

```
virtual CRect GetRect() const;
```

### <a name="return-value"></a>Return Value

단추의 위치를 나타내는 사각형입니다.

### <a name="remarks"></a>설명

단추를 볼 수 없는 경우 반환되는 크기는 0입니다.

## <a name="cmfccaptionbuttongetsize"></a><a name="getsize"></a>CMFC 캡션 버튼 ::GetSize

단추의 너비와 높이를 반환합니다.

```
static CSize GetSize();
```

### <a name="return-value"></a>Return Value

단추의 외부 치수입니다.

### <a name="remarks"></a>설명

반환된 크기에는 단추 여백과 테두리가 포함됩니다.

## <a name="cmfccaptionbuttonisminiframebutton"></a><a name="isminiframebutton"></a>CMFC캡션버튼::이스미니프레임 버튼

제목 막대 높이가 미니 크기로 설정되어 있는지 여부를 나타냅니다.

```
BOOL IsMiniFrameButton() const;
```

### <a name="return-value"></a>Return Value

캡션이 미니 크기로 설정된 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="cmfccaptionbuttonmove"></a><a name="move"></a>CMFC 캡션버튼::이동

단추 그리기 위치와 창 표시 상태를 설정합니다.

```cpp
void Move(
    const CPoint& ptTo,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>매개 변수

*ptTo*<br/>
【인】 새 위치입니다.

*bHide*<br/>
【인】 단추를 표시할지 여부입니다.

## <a name="cmfccaptionbuttonondraw"></a><a name="ondraw"></a>CMFC 캡션 버튼::온드로우

캡션 단추를 그립니다.

```
virtual void OnDraw(
    CDC* pDC,
    BOOL bActive,
    BOOL bHorz = TRUE,
    BOOL bMaximized = TRUE,
    BOOL bDisabled = FALSE);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 단추에 대한 장치 컨텍스트에 대한 포인터입니다.

*b활성*<br/>
【인】 활성 버튼 이미지를 그릴지 여부입니다.

*b호르츠 (주)*<br/>
【인】 파생 클래스에서 사용하도록 예약되었습니다.

*b최대화*<br/>
【인】 최대화된 버튼 이미지를 그릴지 여부입니다.

*b 장애인*<br/>
【인】 활성화된 단추 이미지를 그릴지 여부입니다.

### <a name="remarks"></a>설명

*bMaximized* 매개 변수는 단추가 최대화 또는 최소화 단추인 경우 사용됩니다.

## <a name="cmfccaptionbuttonsetminiframebutton"></a><a name="setminiframebutton"></a>CMFC캡션버튼::셋미니프레임버튼

제목 표시줄의 미니 크기를 설정합니다.

```cpp
void SetMiniFramebutton(BOOL bSet = TRUE);
```

### <a name="parameters"></a>매개 변수

*bSet*<br/>
【인】 미니 타이틀 바 높이에 대한 TRUE; 기본 제목 막대 높이에 대한 FALSE입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)
