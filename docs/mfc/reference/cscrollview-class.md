---
title: C스크롤뷰 클래스
ms.date: 11/04/2016
f1_keywords:
- CScrollView
- AFXWIN/CScrollView
- AFXWIN/CScrollView::CScrollView
- AFXWIN/CScrollView::CheckScrollBars
- AFXWIN/CScrollView::FillOutsideRect
- AFXWIN/CScrollView::GetDeviceScrollPosition
- AFXWIN/CScrollView::GetDeviceScrollSizes
- AFXWIN/CScrollView::GetScrollPosition
- AFXWIN/CScrollView::GetTotalSize
- AFXWIN/CScrollView::ResizeParentToFit
- AFXWIN/CScrollView::ScrollToPosition
- AFXWIN/CScrollView::SetScaleToFitSize
- AFXWIN/CScrollView::SetScrollSizes
helpviewer_keywords:
- CScrollView [MFC], CScrollView
- CScrollView [MFC], CheckScrollBars
- CScrollView [MFC], FillOutsideRect
- CScrollView [MFC], GetDeviceScrollPosition
- CScrollView [MFC], GetDeviceScrollSizes
- CScrollView [MFC], GetScrollPosition
- CScrollView [MFC], GetTotalSize
- CScrollView [MFC], ResizeParentToFit
- CScrollView [MFC], ScrollToPosition
- CScrollView [MFC], SetScaleToFitSize
- CScrollView [MFC], SetScrollSizes
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
ms.openlocfilehash: 5d0eb163fae2aa5fc63470e1c499311ab1a402a6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754412"
---
# <a name="cscrollview-class"></a>C스크롤뷰 클래스

스크롤 기능이 있는 [CView입니다.](../../mfc/reference/cview-class.md)

## <a name="syntax"></a>구문

```
class CScrollView : public CView
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[C스크롤뷰::C스크롤뷰](#cscrollview)|`CScrollView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C스크롤뷰::체크스크롤바](#checkscrollbars)|스크롤 보기에 가로 및 세로 스크롤 막대가 있는지 여부를 나타냅니다.|
|[C스크롤뷰::채우기외부](#filloutsiderect)|스크롤 영역 외부의 뷰 영역을 채웁니다.|
|[C스크롤뷰::GetDevice스크롤 포지션](#getdevicescrollposition)|장치 단위에서 현재 스크롤 위치를 가져옵니다.|
|[C스크롤뷰::겟디바이스스크롤사이즈](#getdevicescrollsizes)|현재 매핑 모드, 총 크기 및 스크롤 가능한 보기의 선 및 페이지 크기를 가져옵니다. 크기는 장치 단위에 있습니다.|
|[C스크롤뷰::Get스크롤 포지션](#getscrollposition)|논리 단위로 현재 스크롤 위치를 가져옵니다.|
|[C스크롤뷰::겟토탈사이즈](#gettotalsize)|논리 단위로 스크롤 뷰의 총 크기를 가져옵니다.|
|[C스크롤뷰::크기 조정부모토핏](#resizeparenttofit)|뷰의 크기가 프레임 크기를 지정하도록 합니다.|
|[C스크롤뷰::스크롤위치](#scrolltoposition)|논리 단위로 지정된 지정된 지점으로 뷰를 스크롤합니다.|
|[C스크롤뷰::세트스케일토핏사이즈](#setscaletofitsize)|스크롤 보기를 크기 조정-맞춤 모드로 넣습니다.|
|[C스크롤뷰::세트스크롤크기](#setscrollsizes)|스크롤 뷰의 매핑 모드, 총 크기 및 가로 및 세로 스크롤 양을 설정합니다.|

## <a name="remarks"></a>설명

메시지 매핑된 `CView` [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) 및 [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) 멤버 함수를 재정의하여 파생된 모든 클래스에서 표준 스크롤을 처리할 수 있습니다. 그러나 `CScrollView` 기능에 다음 기능을 `CView` 추가합니다.

- 창 및 뷰포트 크기 및 매핑 모드를 관리합니다.

- 스크롤 막대 메시지에 대한 응답으로 자동으로 스크롤됩니다.

- 키보드, 비스크롤 마우스 또는 IntelliMouse 휠의 메시지에 대한 응답으로 자동으로 스크롤됩니다.

키보드의 메시지에 대한 응답으로 자동으로 스크롤하려면 WM_KEYDOWN 메시지를 추가하고 VK_DOWN 테스트하고 [VK_PREV 및 SetScrollPos](/windows/win32/api/winuser/nf-winuser-setscrollpos)를 호출합니다.

메시지 매핑된 [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) 및 [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) 멤버 함수를 재정의하여 마우스 휠 스크롤을 직접 처리할 수 있습니다. 이러한 멤버 `CScrollView`함수는 휠 회전 [메시지인 WM_MOUSEWHEEL](/windows/win32/inputdev/wm-mousewheel)권장 동작을 지원합니다.

자동 스크롤을 활용하려면 `CScrollView` `CView`에서 대신 보기 클래스를 파생합니다. 뷰를 처음 만들 때 문서 크기에 따라 스크롤 가능한 뷰의 크기를 계산하려면 `SetScrollSizes` [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) 또는 [CView:OnUpdate](../../mfc/reference/cview-class.md#onupdate)의 재정의에서 멤버 함수를 호출합니다. 문서 크기를 쿼리하려면 사용자 고유의 코드를 작성해야 합니다. 예를 들어 낙서 [샘플을](../../overview/visual-cpp-samples.md)참조하십시오.)

멤버 함수에 `SetScrollSizes` 대한 호출은 뷰의 매핑 모드, 스크롤 뷰의 총 치수 및 가로 및 세로로 스크롤할 양을 설정합니다. 모든 크기는 논리적 단위입니다. 뷰의 논리적 크기는 일반적으로 문서에 저장된 데이터에서 계산되지만 경우에 따라 고정 크기를 지정할 수 있습니다. 두 가지 접근 방식의 예는 [CScrollView:SetScrollSize 를](#setscrollsizes)참조하십시오.

논리 단위로 가로 및 세로로 스크롤할 양을 지정합니다. 기본적으로 사용자가 스크롤 상자 외부의 스크롤 막대 샤프트를 `CScrollView` 클릭하면 "페이지"를 스크롤합니다. 사용자가 스크롤 막대의 양쪽 끝에서 스크롤 화살표를 `CScrollView` 클릭하면 "선"을 스크롤합니다. 기본적으로 페이지는 뷰의 총 크기의 1/10입니다. 한 줄은 페이지 크기의 1/10입니다. `SetScrollSizes` 멤버 함수에서 사용자 지정 크기를 전달하여 이러한 기본값을 재정의합니다. 예를 들어 가로 크기를 전체 크기 너비의 일부 분수로 설정하고 세로 크기를 현재 글꼴의 줄 높이로 설정할 수 있습니다.

스크롤 하는 대신 `CScrollView` 자동으로 현재 창 크기로 뷰를 배율 조정할 수 있습니다. 이 모드에서는 뷰에 스크롤 막대가 없으며 논리적 뷰가 창의 클라이언트 영역에 정확히 맞게 늘어나거나 축소됩니다. 이 맞춤 기능 사용하려면 [CScrollView::SetScaleToFitSize](#setscaletofitsize)를 호출합니다. (또는 `SetScaleToFitSize` 전화 `SetScrollSizes`또는 , 둘 다.)

파생 `OnDraw` 뷰 클래스의 멤버 함수가 호출되기 전에 에 전달하는 장치 `CPaintDC` 컨텍스트 개체에 대한 뷰포트 원본을 `OnDraw` `CScrollView` 자동으로 조정합니다.

스크롤 창의 뷰포트 원원을 `CScrollView` 조정하려면 [CView::OnPrepareDC를](../../mfc/reference/cview-class.md#onpreparedc)재정의합니다. 이 조정은 `CPaintDC` `CScrollView` `OnDraw`에 전달하는 장치 컨텍스트에 대해 `CScrollView::OnPrepareDC` 자동으로 수행되지만 `CClientDC`에서와 같이 사용하는 다른 장치 컨텍스트에 대해 직접 호출해야 합니다. 펜, 배경 `CScrollView::OnPrepareDC` 색 및 기타 그리기 특성을 설정하도록 재정의할 수 있지만 기본 클래스를 호출하여 배율 조정을 수행할 수 있습니다.

스크롤 막대는 다음과 같은 경우와 같이 뷰를 기준으로 세 위치에 나타날 수 있습니다.

- 표준 창 스타일 스크롤 막대는 WS_HSCROLL 및 WS_VSCROLL[Windows 스타일을](../../mfc/reference/styles-used-by-mfc.md#window-styles)사용하여 보기에 대해 설정할 수 있습니다.

- 스크롤 막대 컨트롤을 뷰를 포함하는 프레임에 추가할 수도 있으며, 이 경우 프레임워크는 WM_HSCROLL 전달하고 프레임 창에서 현재 활성 보기로 메시지를 WM_VSCROLL.

- 또한 프레임워크는 `CSplitterWnd` 스크롤 메시지를 스플리터 컨트롤에서 현재 활성 스플리터 창(보기)으로 전달합니다. 공유 스크롤 막대가 있는 [CSplitterWnd에](../../mfc/reference/csplitterwnd-class.md) 배치하면 개체는 `CScrollView` 자체 를 만드는 대신 공유 막대를 사용합니다.

사용에 `CScrollView`대한 자세한 내용은 [MFC에서 사용할 수 있는](../../mfc/derived-view-classes-available-in-mfc.md) [문서/보기 아키텍처](../../mfc/document-view-architecture.md) 및 파생 보기 클래스를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cscrollviewcheckscrollbars"></a><a name="checkscrollbars"></a>C스크롤뷰::체크스크롤바

이 멤버 함수를 호출하여 스크롤 보기에 가로 및 세로 막대가 있는지 확인합니다.

```cpp
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>매개 변수

*bHasHorzBar*<br/>
응용 프로그램에 가로 스크롤 막대가 있음을 나타냅니다.

*bHasVertBar*<br/>
응용 프로그램에 세로 스크롤 막대가 있음을 나타냅니다.

## <a name="cscrollviewcscrollview"></a><a name="cscrollview"></a>C스크롤뷰::C스크롤뷰

`CScrollView` 개체를 생성합니다.

```
CScrollView();
```

### <a name="remarks"></a>설명

스크롤 보기를 `SetScrollSizes` 사용할 `SetScaleToFitSize` 수 있는 전에 호출해야 합니다.

## <a name="cscrollviewfilloutsiderect"></a><a name="filloutsiderect"></a>C스크롤뷰::채우기외부

스크롤 `FillOutsideRect` 영역 외부에 나타나는 뷰 영역을 채우기 위해 호출합니다.

```cpp
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
채우기를 수행할 장치 컨텍스트입니다.

*p브러시*<br/>
영역을 채울 브러시입니다.

### <a name="remarks"></a>설명

스크롤 `FillOutsideRect` 뷰의 `OnEraseBkgnd` 처리기 함수에서 과도한 백그라운드 다시 그리기를 방지합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

## <a name="cscrollviewgetdevicescrollposition"></a><a name="getdevicescrollposition"></a>C스크롤뷰::GetDevice스크롤 포지션

스크롤 `GetDeviceScrollPosition` 막대에서 스크롤 상자의 현재 가로 및 세로 위치가 필요한 경우 호출합니다.

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>Return Value

`CPoint` 개체로 스크롤 상자의 수평 및 수직 위치(장치 단위)입니다.

### <a name="remarks"></a>설명

이 좌표 쌍은 뷰의 왼쪽 위 모서리가 스크롤된 문서의 위치에 해당합니다. 이 기능은 마우스 장치 위치를 스크롤 보기 장치 위치로 오프셋하는 데 유용합니다.

`GetDeviceScrollPosition`장치 단위에서 값을 반환합니다. 논리 단위를 원하는 `GetScrollPosition` 경우 대신 사용 합니다.

## <a name="cscrollviewgetdevicescrollsizes"></a><a name="getdevicescrollsizes"></a>C스크롤뷰::겟디바이스스크롤사이즈

`GetDeviceScrollSizes`스크롤 가능한 보기의 현재 매핑 모드, 총 크기 및 선 및 페이지 크기를 가져옵니다.

```cpp
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>매개 변수

*n맵 모드*<br/>
이 뷰에 대한 현재 매핑 모드를 반환합니다. 사용 가능한 값 목록을 보려면 `SetScrollSizes`을 참조하십시오.

*크기합계*<br/>
장치 단위로 스크롤 뷰의 현재 총 크기를 반환합니다.

*크기페이지*<br/>
스크롤 막대 샤프트에서 마우스 클릭에 대한 응답으로 각 방향으로 스크롤할 현재 의 수평 및 수직 양을 반환합니다. 멤버에 `cx` 가로 금액이 포함됩니다. 멤버에 `cy` 세로 양이 포함됩니다.

*크기라인*<br/>
스크롤 화살표에서 마우스 클릭에 대한 응답으로 각 방향으로 스크롤할 현재 의 가로 및 세로 양을 반환합니다. 멤버에 `cx` 가로 금액이 포함됩니다. 멤버에 `cy` 세로 양이 포함됩니다.

### <a name="remarks"></a>설명

크기는 장치 단위에 있습니다. 이 멤버 함수는 거의 호출되지 않습니다.

## <a name="cscrollviewgetscrollposition"></a><a name="getscrollposition"></a>C스크롤뷰::Get스크롤 포지션

스크롤 `GetScrollPosition` 막대에서 스크롤 상자의 현재 가로 및 세로 위치가 필요한 경우 호출합니다.

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>Return Value

`CPoint` 개체로 스크롤 상자의 가로 및 세로 위치(논리 단위)입니다.

### <a name="remarks"></a>설명

이 좌표 쌍은 뷰의 왼쪽 위 모서리가 스크롤된 문서의 위치에 해당합니다.

`GetScrollPosition`값을 논리 단위로 반환합니다. 장치 단위를 원하는 `GetDeviceScrollPosition` 경우 대신 사용하십시오.

## <a name="cscrollviewgettotalsize"></a><a name="gettotalsize"></a>C스크롤뷰::겟토탈사이즈

스크롤 `GetTotalSize` 뷰의 현재 가로 및 세로 크기를 검색하려면 호출합니다.

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>Return Value

논리 단위로 스크롤 뷰의 총 크기입니다. 가로 크기는 반환 `cx` 값의 `CSize` 멤버에 있습니다. 세로 크기는 멤버에 있습니다. `cy`

## <a name="cscrollviewresizeparenttofit"></a><a name="resizeparenttofit"></a>C스크롤뷰::크기 조정부모토핏

호출을 `ResizeParentToFit` 통해 뷰 크기가 프레임 창의 크기를 지정하도록 합니다.

```cpp
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>매개 변수

*b수축전용*<br/>
수행할 크기 조정의 종류입니다. 기본값 TRUE는 적절한 경우 프레임 창을 축소합니다. 스크롤 막대는 여전히 큰 뷰 또는 작은 프레임 창에 대해 나타납니다. FALSE 값을 사용하면 뷰가 항상 프레임 창의 크기를 정확하게 조정합니다. 프레임 창이 너무 커서 MDI(여러 문서 인터페이스) 프레임 창이나 화면 내부에 들어갈 수 없기 때문에 다소 위험할 수 있습니다.

### <a name="remarks"></a>설명

MDI 자식 프레임 창의 보기에만 권장됩니다. 파생 `ResizeParentToFit` 클래스의 `OnInitialUpdate` `CScrollView` 처리기 함수에 사용합니다. 이 멤버 함수의 예는 [CScrollView:SetScrollSize](#setscrollsizes)를 참조하십시오.

`ResizeParentToFit`뷰 창의 크기가 설정되었다고 가정합니다. 호출될 때 `ResizeParentToFit` 뷰 창 크기가 설정되지 않은 경우 어설션을 받게 됩니다. 이 경우 이러한 일이 발생하지 않도록 하려면 `ResizeParentToFit`호출하기 전에 다음 호출을 수행하십시오.

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

## <a name="cscrollviewscrolltoposition"></a><a name="scrolltoposition"></a>C스크롤뷰::스크롤위치

호출하여 `ScrollToPosition` 뷰의 지정된 지점으로 스크롤합니다.

```cpp
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
논리적 단위로 스크롤할 점입니다. 멤버는 `x` 양수 값이어야 합니다(뷰의 총 크기까지 0보다 크거나 같음). 매핑 모드가 `y` MM_TEXT 멤버도 마찬가지입니다. 멤버가 `y` MM_TEXT 이외의 매핑 모드에서 음수입니다.

### <a name="remarks"></a>설명

이 점이 창의 왼쪽 위 모서리에 있도록 뷰가 스크롤됩니다. 뷰의 크기조정이 적합하면 이 멤버 함수를 호출할 수 없습니다.

## <a name="cscrollviewsetscaletofitsize"></a><a name="setscaletofitsize"></a>C스크롤뷰::세트스케일토핏사이즈

뷰포트 크기를 현재 창 크기로 자동으로 배율 조정하려는 경우 호출합니다. `SetScaleToFitSize`

```cpp
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>매개 변수

*크기합계*<br/>
뷰의 배율을 조정하는 수평 및 수직 크기입니다. 스크롤 뷰의 크기는 논리적 단위로 측정됩니다. 가로 크기는 멤버에 `cx` 포함되어 있습니다. 세로 크기는 멤버에 `cy` 포함됩니다. 둘 `cx` `cy` 다 0보다 크거나 같아야 합니다.

### <a name="remarks"></a>설명

스크롤 막대를 사용하면 논리 보기의 일부만 언제든지 볼 수 있습니다. 그러나 맞춤 기능의 경우 뷰에는 스크롤 막대가 없으며 논리적 뷰가 창의 클라이언트 영역에 정확히 맞게 늘어나거나 축소됩니다. 창의 크기가 조정되면 뷰는 창 크기에 따라 새 축척으로 데이터를 그립니다.

일반적으로 뷰의 `SetScaleToFitSize` `OnInitialUpdate` 멤버 함수를 재정의하여 호출합니다. 자동 크기 조정을 원하지 않는 `SetScrollSizes` 경우 대신 멤버 함수를 호출합니다.

`SetScaleToFitSize`"맞춤 확대/축소" 작업을 구현하는 데 사용할 수 있습니다. 스크롤을 다시 초기화하는 데 사용합니다. `SetScrollSizes`

`SetScaleToFitSize`뷰 창의 크기가 설정되었다고 가정합니다. 호출될 때 `SetScaleToFitSize` 뷰 창 크기가 설정되지 않은 경우 어설션을 받게 됩니다. 이 경우 이러한 일이 발생하지 않도록 하려면 `SetScaleToFitSize`호출하기 전에 다음 호출을 수행하십시오.

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

## <a name="cscrollviewsetscrollsizes"></a><a name="setscrollsizes"></a>C스크롤뷰::세트스크롤크기

뷰가 업데이트될 때 호출합니다. `SetScrollSizes`

```cpp
void SetScrollSizes(
    int nMapMode,
    SIZE sizeTotal,
    const SIZE& sizePage = sizeDefault,
    const SIZE& sizeLine = sizeDefault);
```

### <a name="parameters"></a>매개 변수

*n맵 모드*<br/>
이 뷰에 대해 설정할 매핑 모드입니다. 가능한 값은 다음과 같습니다.

|매핑 모드|논리 단위|양수 y축 확장...|
|------------------|------------------|---------------------------------|
|Mm_text|1 픽셀|하향|
|MM_HIMETRIC|0.01 mm|상승|
|MM_TWIPS|1/1440 년|상승|
|MM_HIENGLISH|0.001 에서|상승|
|MM_LOMETRIC|0.1 mm|상승|
|MM_LOENGLISH|0.01 에서|상승|

이러한 모든 모드는 Windows에서 정의합니다. MM_ISOTROPIC 및 MM_ANISOTROPIC 두 가지 표준 매핑 `CScrollView`모드는 에 사용되지 않습니다. 클래스 라이브러리는 `SetScaleToFitSize` 뷰를 창 크기로 조정하기 위한 멤버 함수를 제공합니다. 위 표의 열 3은 좌표 방향을 설명합니다.

*크기합계*<br/>
스크롤 뷰의 총 크기입니다. 멤버에 `cx` 가로 익범위가 포함됩니다. 멤버에 `cy` 세로 익스텐달이 포함되어 있습니다. 크기는 논리적 단위입니다. 둘 `cx` `cy` 다 0보다 크거나 같아야 합니다.

*크기페이지*<br/>
가로 및 세로 양은 스크롤 막대 샤프트에서 마우스 클릭에 대한 응답으로 각 방향으로 스크롤됩니다. 멤버에 `cx` 가로 금액이 포함됩니다. 멤버에 `cy` 세로 양이 포함됩니다.

*크기라인*<br/>
가로 및 세로 양은 스크롤 화살표에서 마우스 클릭에 대한 응답으로 각 방향으로 스크롤합니다. 멤버에 `cx` 가로 금액이 포함됩니다. 멤버에 `cy` 세로 양이 포함됩니다.

### <a name="remarks"></a>설명

`OnUpdate` 문서의 재정의에서 호출하여 문서가 처음 표시되거나 크기가 변경될 때 스크롤 특성을 조정합니다.

일반적으로 파생 문서 클래스와 함께 제공하는 문서 멤버 함수(아마도 라고 `GetMyDocSize`함)를 호출하여 뷰의 관련 문서에서 크기 정보를 가져옵니다. 다음 코드는 이 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

또는 다음 코드에서와 같이 고정 크기를 설정해야 할 수도 있습니다.

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

매핑 모드를 MM_ISOTROPIC 또는 MM_ANISOTROPIC 제외한 모든 Windows 매핑 모드로 설정해야 합니다. 제한되지 않은 매핑 모드를 사용하려면 `SetScaleToFitSize` `SetScrollSizes`을 대신 멤버 함수를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 디브룩](../../overview/visual-cpp-samples.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[C스플리터Wnd 클래스](../../mfc/reference/csplitterwnd-class.md)
