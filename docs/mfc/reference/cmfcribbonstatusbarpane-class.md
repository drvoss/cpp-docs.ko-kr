---
title: CMFC리본상태바파네 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
helpviewer_keywords:
- CMFCRibbonStatusBarPane [MFC], CMFCRibbonStatusBarPane
- CMFCRibbonStatusBarPane [MFC], GetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], GetTextAlign
- CMFCRibbonStatusBarPane [MFC], IsAnimation
- CMFCRibbonStatusBarPane [MFC], IsExtended
- CMFCRibbonStatusBarPane [MFC], OnDrawBorder
- CMFCRibbonStatusBarPane [MFC], OnFillBackground
- CMFCRibbonStatusBarPane [MFC], SetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], SetAnimationList
- CMFCRibbonStatusBarPane [MFC], SetTextAlign
- CMFCRibbonStatusBarPane [MFC], StartAnimation
- CMFCRibbonStatusBarPane [MFC], StopAnimation
- CMFCRibbonStatusBarPane [MFC], OnFinishAnimation
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
ms.openlocfilehash: bb4e09eabab17061812ed22b2739d06accd57fee
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753507"
---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFC리본상태바파네 클래스

클래스는 `CMFCRibbonStatusBarPane` 리본 상태 표시줄에 추가할 수 있는 리본 요소를 구현 합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonStatusBarPane : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC리본상태바파네::CMFC리본상태바파네](#cmfcribbonstatusbarpane)|`CMFCRibbonStatusBarPane` 개체를 생성하고 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC리본 상태바파인::Get거의큰텍스트](#getalmostlargetext)|잘리지 않고 창에 표시할 수 있는 가장 긴 텍스트 문자열을 정의하는 문자열을 반환합니다.|
|[CMFC리본 상태바파인::GetText정렬](#gettextalign)|텍스트 정렬의 현재 설정을 반환합니다.|
|[CMFC리본 상태바파네::IsAnimation](#isanimation)|애니메이션이 진행 중인지 여부를 확인합니다.|
|[CMFC리본 상태바파인::확장됨](#isextended)|창이 리본 상태 표시줄의 확장 영역에 있는지 여부를 결정합니다.|
|[CMFC리본 상태바파인::온드로우보더](#ondrawborder)|[(CMFC 리본 단추 재정의::온드로우 보더.)](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder)|
|[CMFC리본 상태바파인::온필백](#onfillbackground)|[(CMFC 리본 단추 재정의::온필백](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|
|[CMFC리본 상태 바파인::세트거의 큰 텍스트](#setalmostlargetext)|잘리지 않고 창에 표시할 수 있는 가장 긴 텍스트 문자열을 정의합니다.|
|[CMFC리본 상태바파인::세트애니메이션리스트](#setanimationlist)|창에 애니메이션에 사용할 수 있는 이미지 목록을 할당합니다.|
|[CMFC리본 상태 바파인::SetText정렬](#settextalign)|텍스트 정렬을 설정합니다.|
|[CMFC리본 상태바파인::시작 애니메이션](#startanimation)|창에 할당된 애니메이션을 시작합니다.|
|[CMFC리본 상태바파인::스톱 애니메이션](#stopanimation)|창에 할당된 애니메이션을 중지합니다. .|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC리본 상태 바파인::온피니애니메이션](#onfinishanimation)|창에 할당된 애니메이션이 중지될 때 프레임워크에서 호출됩니다.|

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonStatusBarPane` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 `CMFCRibbonStatusBarPane` 객체를 생성하고, 상태 표시줄 창의 레이블의 텍스트 정렬을 설정하고, 잘리지 않고 상태 표시줄 창에 표시할 수 있는 가장 긴 텍스트를 정의하고, 상태 표시줄 창에 애니메이션에 사용할 수 있는 이미지 목록을 연결하고, 애니메이션을 시작하는 방법을 보여 주며, 애니메이션을 시작합니다.

[!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribbonstatusbarpane.h

## <a name="cmfcribbonstatusbarpanecmfcribbonstatusbarpane"></a><a name="cmfcribbonstatusbarpane"></a>CMFC리본상태바파네::CMFC리본상태바파네

상태 표시줄에서 창 오브젝트를 생성합니다.

```
CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    BOOL bIsStatic=FALSE,
    HICON hIcon=NULL,
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);
```

### <a name="parameters"></a>매개 변수

*nCmdID*<br/>
【인】 창의 명령 ID를 지정합니다.

*lpszText*<br/>
【인】 창에 표시할 텍스트 문자열을 지정합니다.

*비스틱*<br/>
【인】 TRUE인 경우 상태 창을 클릭하여 강조 표시하거나 선택할 수 없습니다.

*hIcon*<br/>
【인】 창에 표시할 아이콘에 대한 핸들을 지정합니다.

*lpsz거의큰텍스트*<br/>
【인】 창에서 표시할 수 있는 가장 긴 텍스트 문자열을 지정합니다.

*hBmp애니메이션리스트*<br/>
【인】 애니메이션에 사용되는 이미지 목록에 대한 핸들을 지정합니다.

*cx애니메이션*<br/>
【인】 애니메이션에 사용되는 이미지 목록의 아이콘 너비(픽셀)를 지정합니다.

*클러트르스프*<br/>
【인】 애니메이션에 사용되는 이미지 목록에서 이미지의 투명한 색상을 지정합니다.

*ui애니메이션리스트ResID*<br/>
【인】 애니메이션에 사용되는 이미지 목록의 리소스 ID를 지정합니다.

## <a name="cmfcribbonstatusbarpanegetalmostlargetext"></a><a name="getalmostlargetext"></a>CMFC리본 상태바파인::Get거의큰텍스트

상태 표시줄 창에 표시할 수 있는 가장 긴 텍스트 문자열을 가져옵니다.

```
LPCTSTR GetAlmostLargeText() const;
```

### <a name="return-value"></a>Return Value

상태 표시줄 창에 표시할 수 있는 가장 긴 텍스트 문자열입니다.

## <a name="cmfcribbonstatusbarpanegettextalign"></a><a name="gettextalign"></a>CMFC리본 상태바파인::GetText정렬

상태 표시줄 창의 레이블의 텍스트 정렬의 현재 설정을 가져옵니다.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>Return Value

다음 중 하나가 될 수 있는 현재 텍스트 정렬:

- TA_LEFT

- TA_CENTER

- TA_RIGHT.

## <a name="cmfcribbonstatusbarpaneisanimation"></a><a name="isanimation"></a>CMFC리본 상태바파네::IsAnimation

애니메이션이 진행 중인지 여부를 확인합니다.

```
BOOL IsAnimation() const;
```

### <a name="return-value"></a>Return Value

TRUE 애니메이션이 진행 중이면 그렇지 않으면 거짓.

## <a name="cmfcribbonstatusbarpaneisextended"></a><a name="isextended"></a>CMFC리본 상태바파인::확장됨

창이 리본 상태 표시줄의 확장 영역에 있는지 확인합니다.

```
BOOL IsExtended() const;
```

### <a name="return-value"></a>Return Value

TRUE 창이 상태 표시줄 확장 영역에 있는 경우. 그렇지 않으면 FALSE입니다.

## <a name="cmfcribbonstatusbarpaneondrawborder"></a><a name="ondrawborder"></a>CMFC리본 상태바파인::온드로우보더

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual void OnDrawBorder(CDC*);
```

### <a name="parameters"></a>매개 변수

【인】 *CDC&#42;*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcribbonstatusbarpaneonfillbackground"></a><a name="onfillbackground"></a>CMFC리본 상태바파인::온필백

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual COLORREF OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonstatusbarpaneonfinishanimation"></a><a name="onfinishanimation"></a>CMFC리본 상태 바파인::온피니애니메이션

프레임워크는 창에 할당된 애니메이션이 끝날 때 이 메서드를 호출합니다.

```
virtual void OnFinishAnimation();
```

### <a name="remarks"></a>설명

`StopAnimation`메서드는 `OnFinishAnimation` 애니메이션이 끝날 때 데이터를 정리하는 데 사용할 수 있는 메서드를 호출합니다.

## <a name="cmfcribbonstatusbarpanesetalmostlargetext"></a><a name="setalmostlargetext"></a>CMFC리본 상태 바파인::세트거의 큰 텍스트

잘린 상태에서 상태 표시줄 창에 표시할 수 있는 가장 긴 텍스트를 정의합니다.

```cpp
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```

### <a name="parameters"></a>매개 변수

*lpsz거의큰텍스트*<br/>
【인】 잘린 상태에서 상태 표시줄 창에 표시할 수 있는 가장 긴 문자열을 지정합니다.

### <a name="remarks"></a>설명

라이브러리는 *lpszAlmostLargeText가* 지정하고 그에 따라 창크기를 조정하는 텍스트의 크기를 계산합니다. 창에 여전히 맞지 않으면 텍스트가 잘립니다.

## <a name="cmfcribbonstatusbarpanesetanimationlist"></a><a name="setanimationlist"></a>CMFC리본 상태바파인::세트애니메이션리스트

상태 표시줄 창에 애니메이션에 사용할 수 있는 이미지 목록을 연결합니다.

```cpp
void SetAnimationList(
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```

### <a name="parameters"></a>매개 변수

*hBmp애니메이션리스트*<br/>
【인】 이미지 목록에 대한 핸들을 지정합니다.

*cx애니메이션*<br/>
【인】 이미지 목록에서 프레임의 너비(픽셀)를 지정합니다.

*clrTransp*<br/>
【인】 이미지 목록의 투명한 색상을 지정합니다.

*ui애니메이션리스트ResID*<br/>
【인】 이미지 목록의 리소스 ID를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 이미지 목록이 상태 표시줄 창에 성공적으로 첨부된 경우; 그렇지 않으면 거짓.

## <a name="cmfcribbonstatusbarpanesettextalign"></a><a name="settextalign"></a>CMFC리본 상태 바파인::SetText정렬

상태 표시줄 창의 레이블의 텍스트 정렬을 설정합니다.

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>매개 변수

*nAlign*<br/>
【인】 텍스트 정렬을 지정합니다.

### <a name="remarks"></a>설명

*nAlign은* 다음 값 중 하나를 가질 수 있습니다.

- TA_LEFT: 왼쪽 맞춤

- TA_CENTER: 중심 맞춤

- TA_RIGHT: 오른쪽 정렬

## <a name="cmfcribbonstatusbarpanestartanimation"></a><a name="startanimation"></a>CMFC리본 상태바파인::시작 애니메이션

창에 할당한 애니메이션을 시작합니다.

```cpp
void StartAnimation(
    UINT nFrameDelay=500,
    UINT nDuration=-1);
```

### <a name="parameters"></a>매개 변수

*n프레임딜레이지*<br/>
【인】 애니메이션 프레임 속도를 밀리초 단위로 지정합니다.

*n기간*<br/>
【인】 애니메이션을 재생하는 시간(밀리초)을 지정합니다. 무한 루프에 -1을 사용합니다.

### <a name="remarks"></a>설명

을 사용하여 `StartAnimation` `SetAnimationList`호출하기 전에 이미지 목록에 대한 핸들을 지정해야 합니다.

## <a name="cmfcribbonstatusbarpanestopanimation"></a><a name="stopanimation"></a>CMFC리본 상태바파인::스톱 애니메이션

상태 표시줄 창에 할당한 애니메이션을 중지합니다.

```cpp
void StopAnimation();
```

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본버튼 클래스](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFC리본상태 바 클래스](../../mfc/reference/cmfcribbonstatusbar-class.md)
