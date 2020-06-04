---
title: CRectTracker 클래스
ms.date: 11/19/2018
f1_keywords:
- CRectTracker
- AFXEXT/CRectTracker
- AFXEXT/CRectTracker::CRectTracker
- AFXEXT/CRectTracker::AdjustRect
- AFXEXT/CRectTracker::Draw
- AFXEXT/CRectTracker::DrawTrackerRect
- AFXEXT/CRectTracker::GetHandleMask
- AFXEXT/CRectTracker::GetTrueRect
- AFXEXT/CRectTracker::HitTest
- AFXEXT/CRectTracker::NormalizeHit
- AFXEXT/CRectTracker::OnChangedRect
- AFXEXT/CRectTracker::SetCursor
- AFXEXT/CRectTracker::Track
- AFXEXT/CRectTracker::TrackRubberBand
- AFXEXT/CRectTracker::m_nHandleSize
- AFXEXT/CRectTracker::m_nStyle
- AFXEXT/CRectTracker::m_rect
- AFXEXT/CRectTracker::m_sizeMin
helpviewer_keywords:
- CRectTracker [MFC], CRectTracker
- CRectTracker [MFC], AdjustRect
- CRectTracker [MFC], Draw
- CRectTracker [MFC], DrawTrackerRect
- CRectTracker [MFC], GetHandleMask
- CRectTracker [MFC], GetTrueRect
- CRectTracker [MFC], HitTest
- CRectTracker [MFC], NormalizeHit
- CRectTracker [MFC], OnChangedRect
- CRectTracker [MFC], SetCursor
- CRectTracker [MFC], Track
- CRectTracker [MFC], TrackRubberBand
- CRectTracker [MFC], m_nHandleSize
- CRectTracker [MFC], m_nStyle
- CRectTracker [MFC], m_rect
- CRectTracker [MFC], m_sizeMin
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
ms.openlocfilehash: c3600bc5a945c24e91269bc280b4b8e99c54d4c8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750448"
---
# <a name="crecttracker-class"></a>CRectTracker 클래스

항목을 다른 방식으로 표시, 이동 및 크기를 조정할 수 있습니다.

## <a name="syntax"></a>구문

```
class CRectTracker
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CRectTracker::CRectTracker](#crecttracker)|`CRectTracker` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CRectTracker::adjustRect](#adjustrect)|사각형의 크기가 조정될 때 호출됩니다.|
|[CRectTracker::D로](#draw)|사각형을 렌더링합니다.|
|[CRectTracker::D로트래커렉트](#drawtrackerrect)|개체의 테두리를 그릴 `CRectTracker` 때 호출됩니다.|
|[CRectTracker::Get핸들마스크](#gethandlemask)|`CRectTracker` 항목의 크기 조정 핸들의 마스크를 얻으려면 호출됩니다.|
|[CRectTracker::GetTrueRect](#gettruerect)|크기 조정 핸들을 포함하여 사각형의 너비와 높이를 반환합니다.|
|[CRectTracker::히트 테스트](#hittest)|개체와 관련된 커서의 현재 위치를 `CRectTracker` 반환합니다.|
|[CRectTracker::정규화](#normalizehit)|적중 테스트 코드를 정규화합니다.|
|[CRectTracker::변경된 렉트](#onchangedrect)|사각형의 크기가 조정되거나 이동된 경우 호출됩니다.|
|[CRectTracker::세트커서](#setcursor)|사각형 위에 있는 위치에 따라 커서를 설정합니다.|
|[CRectTracker::트랙](#track)|사용자가 사각형을 조작할 수 있습니다.|
|[CRectTracker::트랙러버밴드](#trackrubberband)|사용자가 선택을 "고무 밴드"로 사용할 수 있습니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|크기 조정 핸들의 크기를 결정합니다.|
|[CRectTracker::m_nStyle](#m_nstyle)|트래커의 현재 스타일입니다.|
|[CRectTracker::m_rect](#m_rect)|사각형의 현재 위치(픽셀 단위)입니다.|
|[CRectTracker::m_sizeMin](#m_sizemin)|최소 사각형 너비와 높이를 결정합니다.|

## <a name="remarks"></a>설명

`CRectTracker`기본 클래스가 없습니다.

`CRectTracker` 클래스는 사용자가 그래픽 인터페이스를 사용하여 OLE 항목과 상호 작용할 수 있도록 설계되었지만 사용이 OLE 지원 응용 프로그램으로 제한되지는 않습니다. 이러한 사용자 인터페이스가 필요한 모든 곳에서 사용할 수 있습니다.

`CRectTracker`테두리는 솔리드 또는 점선일 수 있습니다. 항목에 해치된 테두리를 지정하거나 해치 패턴으로 오버레이하여 항목의 다른 상태를 나타낼 수 있습니다. 항목의 외부 또는 내부 테두리에 8개의 크기 조정 핸들을 배치할 수 있습니다. 크기 조정 핸들에 대한 설명은 [GetHandleMask를](#gethandlemask)참조하십시오. 마지막으로 a를 `CRectTracker` 사용하면 크기를 조정하는 동안 항목의 방향을 변경할 수 있습니다.

을 `CRectTracker`사용하려면 `CRectTracker` 객체를 생성하고 초기화할 표시 상태를 지정합니다. 그런 다음 이 인터페이스를 사용하여 `CRectTracker` 개체와 연결된 OLE 항목의 현재 상태에 대한 시각적 피드백을 사용자에게 제공할 수 있습니다.

사용에 `CRectTracker`대한 자세한 내용은 [추적기](../../mfc/trackers.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CRectTracker`

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="crecttrackeradjustrect"></a><a name="adjustrect"></a>CRectTracker::adjustRect

크기 조정 핸들을 사용하여 추적 사각형의 크기를 조정할 때 프레임워크에서 호출합니다.

```
virtual void AdjustRect(
    int nHandle,
    LPRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*n핸들*<br/>
사용되는 핸들 인덱스입니다.

*Lprect*<br/>
사각형의 현재 크기에 대한 포인터입니다. 사각형의 크기는 높이와 너비에 따라 지정됩니다.

### <a name="remarks"></a>설명

이 함수의 기본 동작을 사용하면 사각형의 `Track` `TrackRubberBand` 방향이 반전이 허용되는 경우에만 변경될 수 있습니다.

이 함수를 재정의하여 끌기 작업 중에 추적 사각형의 조정을 제어합니다. 한 가지 방법은 반환하기 전에 *lpRect에* 의해 지정된 좌표를 조정하는 것입니다.

이 함수를 재정의하여 `CRectTracker`스냅-그리드 또는 유지 종횡비와 같이 직접 지원되지 않는 특수 기능을 구현할 수 있습니다.

## <a name="crecttrackercrecttracker"></a><a name="crecttracker"></a>CRectTracker::CRectTracker

`CRectTracker` 개체를 만들어 초기화합니다.

```
CRectTracker();

CRectTracker(
    LPCRECT lpSrcRect,
    UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*lpSrcRect*<br/>
사각형 오브젝트의 좌표입니다.

*nStyle*<br/>
개체의 스타일을 지정합니다. `CRectTracker` 지원되는 스타일은 다음과 같습니다.

- `CRectTracker::solidLine`사각형 테두리에 실선을 사용합니다.

- `CRectTracker::dottedLine`사각형 테두리에 점선을 사용합니다.

- `CRectTracker::hatchedBorder`사각형 테두리에 해치된 패턴을 사용합니다.

- `CRectTracker::resizeInside`사각형 내부에 있는 핸들크기를 조정합니다.

- `CRectTracker::resizeOutside`사각형 외부에 있는 핸들의 크기를 조정합니다.

- `CRectTracker::hatchInside`해치된 패턴은 전체 사각형을 덮습니다.

### <a name="remarks"></a>설명

기본 생성자는 `CRectTracker` *lpSrcRect의* 값으로 개체를 초기화하고 다른 크기를 시스템 기본값으로 초기화합니다. 매개 변수 없이 개체가 만들어지면 `m_rect` `m_nStyle` 및 데이터 멤버는 초기화되지 않습니다.

## <a name="crecttrackerdraw"></a><a name="draw"></a>CRectTracker::D로

이 함수를 호출하여 사각형의 외부 선과 내부 영역을 그립니다.

```cpp
void Draw(CDC* pDC) const;
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
그릴 장치 컨텍스트에 대한 포인터입니다.

### <a name="remarks"></a>설명

트래커 스타일에 따라 드로잉이 수행되는 방식이 결정됩니다. 사용 가능한 스타일에 `CRectTracker` 대한 자세한 내용은 생성자(생성자)를 참조하십시오.

## <a name="crecttrackerdrawtrackerrect"></a><a name="drawtrackerrect"></a>CRectTracker::D로트래커렉트

또는 `TrackRubberBand` 멤버 함수 내부에 있는 동안 트래커의 `Track` 위치가 변경될 때마다 프레임워크에서 호출됩니다.

```
virtual void DrawTrackerRect(
    LPCRECT lpRect,
    CWnd* pWndClipTo,
    CDC* pDC,
    CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*Lprect*<br/>
그릴 사각형을 `RECT` 포함하는 포인터입니다.

*pWndClipTo*<br/>
사각형을 클리핑하는 데 사용할 창에 대한 포인터입니다.

*pDC*<br/>
그릴 장치 컨텍스트에 대한 포인터입니다.

*pWnd*<br/>
도면이 발생하는 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

기본 구현에서는 점선 `CDC::DrawFocusRect`사각형을 그리는 을 호출합니다.

추적 작업 중에 다른 피드백을 제공하기 위해 이 함수를 재정의합니다.

## <a name="crecttrackergethandlemask"></a><a name="gethandlemask"></a>CRectTracker::Get핸들마스크

프레임워크는 이 멤버 함수를 호출하여 사각형의 크기 조정 핸들에 대한 마스크를 검색합니다.

```
virtual UINT GetHandleMask() const;
```

### <a name="return-value"></a>Return Value

`CRectTracker` 항목의 크기 조정 핸들의 마스크입니다.

### <a name="remarks"></a>설명

크기 조정 핸들은 사각형의 측면과 모서리에 표시되며 사용자가 사각형의 모양과 크기를 제어할 수 있습니다.

사각형에는 0-7로 번호가 매겨진 8개의 크기 조정 핸들이 있습니다. 각 크기 조정 핸들은 마스크에서 비트로 표시됩니다. 해당 비트의 값은 2^ *n이며* *n은* 크기 조정 핸들 번호입니다. 비트 0-3은 시계 방향으로 움직이는 왼쪽 상단부터 시작하여 코너 크기 조정 핸들에 해당합니다. 비트 4-7은 위쪽에서 시계 방향으로 이동하는 측면 크기 조정 핸들에 해당합니다. 다음 그림에서는 사각형의 크기 조정 핸들과 해당 크기 조정 핸들 번호 및 값을 보여 주었습니다.

![핸들 번호 크기 조정](../../mfc/reference/media/vc35dp1.gif "크기 조정 핸들 번호")

기본 구현은 `GetHandleMask` 크기 조정 핸들이 표시되도록 비트의 마스크를 반환합니다. 단일 비트가 켜지면 해당 크기 조정 핸들이 그려집니다.

이 멤버 함수를 재정의하여 표시된 크기 조정 핸들을 숨기거나 표시합니다.

## <a name="crecttrackergettruerect"></a><a name="gettruerect"></a>CRectTracker::GetTrueRect

이 함수를 호출하여 사각형의 좌표를 검색합니다.

```cpp
void GetTrueRect(LPRECT lpTrueRect) const;
```

### <a name="parameters"></a>매개 변수

*lp트루렉트*<br/>
개체의 `RECT` 장치 좌표를 포함하는 구조에 `CRectTracker` 대한 포인터입니다.

### <a name="remarks"></a>설명

사각형의 치수는 외부 테두리에 있는 크기 조정 핸들의 높이와 너비를 포함합니다. 반환 시 *lpTrueRect는* 항상 장치 좌표에서 정규화된 사각형입니다.

## <a name="crecttrackerhittest"></a><a name="hittest"></a>CRectTracker::히트 테스트

이 함수를 호출하여 사용자가 크기 조정 핸들을 잡았는지 확인합니다.

```
int HitTest(CPoint point) const;
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
장치 좌표에서 테스트할 점입니다.

### <a name="return-value"></a>Return Value

반환되는 값은 열거된 형식을 `CRectTracker::TrackerHit` 기반으로 하며 다음 값 중 하나를 가질 수 있습니다.

- `CRectTracker::hitNothing` -1

- `CRectTracker::hitTopLeft` 0

- `CRectTracker::hitTopRight`1

- `CRectTracker::hitBottomRight`2

- `CRectTracker::hitBottomLeft`3

- `CRectTracker::hitTop`4

- `CRectTracker::hitRight`5

- `CRectTracker::hitBottom`6

- `CRectTracker::hitLeft`7

- `CRectTracker::hitMiddle`8

## <a name="crecttrackerm_nhandlesize"></a><a name="m_nhandlesize"></a>CRectTracker::m_nHandleSize

크기 조정 핸들의 `CRectTracker` 크기(픽셀 단위)입니다.

```
int m_nHandleSize;
```

### <a name="remarks"></a>설명

기본 시스템 값으로 초기화되었습니다.

## <a name="crecttrackerm_rect"></a><a name="m_rect"></a>CRectTracker::m_rect

클라이언트 좌표(픽셀)에서 사각형의 현재 위치입니다.

```
CRect m_rect;
```

## <a name="crecttrackerm_sizemin"></a><a name="m_sizemin"></a>CRectTracker::m_sizeMin

사각형의 최소 크기입니다.

```
CSize m_sizeMin;
```

### <a name="remarks"></a>설명

`cx` 기본값과 `cy`은 모두 테두리 너비의 기본 시스템 값에서 계산됩니다. 이 데이터 멤버는 멤버 `AdjustRect` 함수에서만 사용됩니다.

## <a name="crecttrackerm_nstyle"></a><a name="m_nstyle"></a>CRectTracker::m_nStyle

사각형의 현재 스타일입니다.

```
UINT m_nStyle;
```

### <a name="remarks"></a>설명

가능한 스타일 목록은 [CRectTracker::CRectTracker를](#crecttracker) 참조하십시오.

## <a name="crecttrackernormalizehit"></a><a name="normalizehit"></a>CRectTracker::정규화

이 함수를 호출하여 잠재적으로 반전된 핸들을 변환합니다.

```
int NormalizeHit(int nHandle) const;
```

### <a name="parameters"></a>매개 변수

*n핸들*<br/>
사용자가 선택한 핸들입니다.

### <a name="return-value"></a>Return Value

정규화된 핸들의 인덱스입니다.

### <a name="remarks"></a>설명

반전이 `CRectTracker::TrackRubberBand` 허용되거나 호출되는 경우 `CRectTracker::Track` 사각형이 x축, y축 또는 둘 다에서 반전될 수 있습니다. 이 경우 `HitTest` 사각형과 관련하여 반전된 핸들도 반환됩니다. 피드백은 수정될 사각형 데이터 구조의 일부가 아니라 사각형의 화면 위치에 따라 달라지므로 커서 피드백을 그리는 데 적합하지 않습니다.

## <a name="crecttrackeronchangedrect"></a><a name="onchangedrect"></a>CRectTracker::변경된 렉트

를 호출하는 동안 추적기 사각형이 변경될 때마다 `Track`프레임워크에서 호출합니다.

```
virtual void OnChangedRect(const CRect& rectOld);
```

### <a name="parameters"></a>매개 변수

*정류*<br/>
`CRectTracker` 개체의 이전 장치 좌표를 포함합니다.

### <a name="remarks"></a>설명

이 함수가 호출될 때 그려진 `DrawTrackerRect` 모든 피드백이 제거되었습니다. 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다.

사각형의 크기를 조정한 후 작업을 수행하려는 경우 이 함수를 재정의합니다.

## <a name="crecttrackersetcursor"></a><a name="setcursor"></a>CRectTracker::세트커서

`CRectTracker` 이 함수를 호출하여 개체의 영역 위에 있는 동안 커서 모양을 변경합니다.

```
BOOL SetCursor(
    CWnd* pWnd,
    UINT nHitTest) const;
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
현재 커서가 포함된 창을 가리킵니다.

*n히트 테스트*<br/>
WM_SETCURSOR 메시지에서 이전 적중 테스트의 결과입니다.

### <a name="return-value"></a>Return Value

이전 적중률이 트래커 사각형 위에 있는 경우 0이 아닌 경우; 그렇지 않으면 0.

### <a name="remarks"></a>설명

WM_SETCURSOR 메시지(일반적으로)를 `OnSetCursor`처리하는 창 의 함수 내부에서 이 함수를 호출합니다.

## <a name="crecttrackertrack"></a><a name="track"></a>CRectTracker::트랙

이 함수를 호출하여 사각형 크기를 조정하기 위한 사용자 인터페이스를 표시합니다.

```
BOOL Track(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = FALSE,
    CWnd* pWndClipTo = NULL);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
사각형을 포함하는 창 개체입니다.

*지점*<br/>
클라이언트 영역을 기준으로 현재 마우스 위치의 장치 좌표입니다.

*bAllow인버트*<br/>
TRUE인 경우 사각형은 x축 또는 y축을 따라 반전될 수 있습니다. 그렇지 않으면 거짓.

*pWndClipTo*<br/>
그리기 작업이 잘린 창입니다. NULL인 경우 *pWnd가* 클리핑 사각형으로 사용됩니다.

### <a name="return-value"></a>Return Value

ESC 키를 누르면 추적 프로세스가 중지되고 추적기에 저장된 사각형이 변경되지 않고 0이 반환됩니다. 변경 내용이 커밋된 경우 마우스를 이동하고 왼쪽 마우스 단추를 놓으면 새 위치 및/또는 크기가 트래커의 사각형에 기록되고 영하지 않은 위치가 반환됩니다.

### <a name="remarks"></a>설명

일반적으로 `WM_LBUTTONDOWN` 메시지를 처리하는 응용 프로그램의 함수 내부에서 호출됩니다(일반적으로). `OnLButtonDown`

이 기능은 사용자가 왼쪽 마우스 버튼을 해제하거나 ESC 키를 누르거나 오른쪽 마우스 버튼을 누를 때까지 마우스를 캡처합니다. 사용자가 마우스 커서를 이동하면 에 대한 호출 `DrawTrackerRect` `OnChangedRect`및 에 의해 피드백이 업데이트됩니다.

*bAllowInvert가* TRUE이면 추적 사각형을 x축 또는 y축에서 반전할 수 있습니다.

## <a name="crecttrackertrackrubberband"></a><a name="trackrubberband"></a>CRectTracker::트랙러버밴드

이 함수를 호출하여 고무 밴드 선택을 수행합니다.

```
BOOL TrackRubberBand(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = TRUE);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
사각형을 포함하는 창 개체입니다.

*지점*<br/>
클라이언트 영역을 기준으로 현재 마우스 위치의 장치 좌표입니다.

*bAllow인버트*<br/>
TRUE인 경우 사각형은 x축 또는 y축을 따라 반전될 수 있습니다. 그렇지 않으면 거짓.

### <a name="return-value"></a>Return Value

마우스가 이동하고 사각형이 비어 있지 않은 경우 0이 아님을 말합니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

일반적으로 WM_LBUTTONDOWN 메시지(일반적으로)를 `OnLButtonDown`처리하는 응용 프로그램의 함수 내부에서 호출됩니다.

이 기능은 사용자가 왼쪽 마우스 버튼을 해제하거나 ESC 키를 누르거나 오른쪽 마우스 버튼을 누를 때까지 마우스를 캡처합니다. 사용자가 마우스 커서를 이동하면 에 대한 호출 `DrawTrackerRect` `OnChangedRect`및 에 의해 피드백이 업데이트됩니다.

추적은 오른쪽 아래 핸들에서 고무 밴드 형 선택으로 수행됩니다. 반전이 허용되는 경우 사각형의 크기를 위쪽과 왼쪽 또는 아래쪽으로 드래그하여 크기를 조정할 수 있습니다.

## <a name="see-also"></a>참조

[MFC 샘플 트래커](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 드로클리](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[콜레레사이즈바 클래스](../../mfc/reference/coleresizebar-class.md)<br/>
[트렉트 클래스](../../atl-mfc-shared/reference/crect-class.md)
