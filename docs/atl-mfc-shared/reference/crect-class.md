---
title: 트렉트 클래스
ms.date: 11/06/2018
f1_keywords:
- CRect
- ATLTYPES/ATL::CRect
- ATLTYPES/ATL::CRect::CRect
- ATLTYPES/ATL::CRect::BottomRight
- ATLTYPES/ATL::CRect::CenterPoint
- ATLTYPES/ATL::CRect::CopyRect
- ATLTYPES/ATL::CRect::DeflateRect
- ATLTYPES/ATL::CRect::EqualRect
- ATLTYPES/ATL::CRect::Height
- ATLTYPES/ATL::CRect::InflateRect
- ATLTYPES/ATL::CRect::IntersectRect
- ATLTYPES/ATL::CRect::IsRectEmpty
- ATLTYPES/ATL::CRect::IsRectNull
- ATLTYPES/ATL::CRect::MoveToX
- ATLTYPES/ATL::CRect::MoveToXY
- ATLTYPES/ATL::CRect::MoveToY
- ATLTYPES/ATL::CRect::NormalizeRect
- ATLTYPES/ATL::CRect::OffsetRect
- ATLTYPES/ATL::CRect::PtInRect
- ATLTYPES/ATL::CRect::SetRect
- ATLTYPES/ATL::CRect::SetRectEmpty
- ATLTYPES/ATL::CRect::Size
- ATLTYPES/ATL::CRect::SubtractRect
- ATLTYPES/ATL::CRect::TopLeft
- ATLTYPES/ATL::CRect::UnionRect
- ATLTYPES/ATL::CRect::Width
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
ms.openlocfilehash: b99eca7fe3a9c84f8b79ef3d694e27b6dd74dcd9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747061"
---
# <a name="crect-class"></a>트렉트 클래스

Windows [RECT](/windows/win32/api/windef/ns-windef-rect) 구조와 유사합니다.

## <a name="syntax"></a>구문

```
class CRect : public tagRECT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CRect:::CRect](#crect)|`CRect` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CRect::하단 오른쪽](#bottomright)|의 `CRect`오른쪽 아래 점을 반환합니다.|
|[CRect::CenterPoint](#centerpoint)|의 중심점을 `CRect`반환합니다.|
|[CRect::CopyRect](#copyrect)|소스 사각형의 치수를 에 `CRect`복사합니다.|
|[CRect::DeflateRect](#deflaterect)|의 너비와 높이를 `CRect`줄입니다.|
|[CRect::이퀄라이저](#equalrect)|지정된 사각형과 동일한지 여부를 `CRect` 결정합니다.|
|[CRect::높이](#height)|의 `CRect`높이를 계산합니다.|
|[CRect::팽창렉트](#inflaterect)|의 너비와 높이가 `CRect`증가합니다.|
|[CRect::교차렉트](#intersectrect)|두 `CRect` 사각형의 교차점과 동일하게 설정합니다.|
|[CRect::IsRectEmpty](#isrectempty)|비어 있는지 `CRect` 여부를 결정합니다. `CRect`너비 및/또는 높이가 0이면 비어 있습니다.|
|[CRect::IsRectNull](#isrectnull)|`top`의 및 `bottom` `left` `right` 멤버 변수가 모두 0과 같는지 여부를 결정합니다.|
|[CRect::MoveToX](#movetox)|지정된 `CRect` x 좌표로 이동합니다.|
|[CRect::MoveToXY](#movetoxy)|지정된 `CRect` x- 및 y 좌표로 이동합니다.|
|[CRect::MoveToY](#movetoy)|지정된 `CRect` y 좌표로 이동합니다.|
|[CRect::NormalizeRect](#normalizerect)|의 `CRect`높이와 너비를 표준화합니다.|
|[CRect::오프셋렉트](#offsetrect)|지정된 `CRect` 오프셋으로 이동합니다.|
|[CRect::PtInRect](#ptinrect)|지정된 점이 내에 `CRect`있는지 여부를 결정합니다.|
|[CRect::SetRect](#setrect)|의 `CRect`크기를 설정합니다.|
|[CRect::SetRect빈](#setrectempty)|빈 `CRect` 사각형으로 설정합니다(모든 좌표는 0과 같음).|
|[CRect::크기](#size)|의 크기를 계산합니다. `CRect`|
|[CRect::SubtractRect](#subtractrect)|한 사각형을 다른 사각형에서 뺍니다.|
|[CRect::TopLeft](#topleft)|왼쪽 상단 점을 반환합니다. `CRect`|
|[CRect::UnionRect](#unionrect)|두 `CRect` 사각형의 결합과 동일한 집합을 설정합니다.|
|[CRect::Width](#width)|의 `CRect`너비를 계산합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CRect::연산자 -](#operator_-)|지정된 오프셋을 `CRect` 빼거나 `CRect` 수축하고 결과 `CRect`입니다.|
|[CRect::연산자 LPCRECT](#operator_lpcrect)|`CRect`를 `LPCRECT`로 변환합니다.|
|[CRect::연산자 LPRECT](#operator_lprect)|`CRect`를 `LPRECT`로 변환합니다.|
|[CRect::연산자 !=](#operator_neq)|사각형과 `CRect` 같지 않은지 여부를 결정합니다.|
|[CRect::연산자&amp;](#operator_amp)|`CRect` 사각형과 교차를 만들고 결과 `CRect`입니다.|
|[CRect::연산자&amp;=](#operator_amp_eq)|사각형의 `CRect` `CRect` 교차점과 사각형과 동일하게 설정합니다.|
|[CRect:연산자 &#124;](#operator_or)|사각형과 사각형의 `CRect` 결합을 만들고 결과 `CRect`반환합니다.|
|[CRect::연산자 &#124;=](#operator_or_eq)|사각형의 결합및사각형과 동일한 집합체를 설정합니다. `CRect` `CRect`|
|[CRect::연산자 +](#operator_add)|지정된 오프셋을 `CRect` 추가하거나 `CRect` 팽창시키고 결과 `CRect`반환합니다.|
|[CRect::연산자 +=](#operator_add_eq)|지정된 오프셋을 `CRect` 에 추가하거나 `CRect`팽창시|
|[CRect::연산자 =](#operator_eq)|사각형의 치수를 에 `CRect`복사합니다.|
|[CRect::연산자 -=](#operator_-_eq)|에서 지정된 간격띄우기 `CRect` 또는 수축을 뺍니다. `CRect`|
|[CRect::연산자 ==](#operator_eq_eq)|사각형과 `CRect` 동일한지 여부를 결정합니다.|

## <a name="remarks"></a>설명

`CRect`개체 및 Windows `CRect` `RECT` 구조를 조작하는 멤버 함수도 포함되어 있습니다.

개체는 `CRect` 구조체가 `LPCRECT`어디든지 함수 매개 변수로 전달되거나 `LPRECT` 전달될 수 있습니다. `RECT`

> [!NOTE]
> 이 클래스는 구조에서 `tagRECT` 파생됩니다. (이름은 `tagRECT` `RECT` 구조에 대 한 덜 일반적으로 사용 되는 이름입니다.) `left`즉, `top` `right` `RECT` 구조의 `CRect`데이터 멤버 (, 및) `bottom`

A에는 `CRect` 사각형의 왼쪽 위 및 오른쪽 아래 점을 정의하는 멤버 변수가 포함되어 있습니다.

`CRect`을 지정할 때는 왼쪽 좌표값이 오른쪽보다 크고 위쪽이 아래쪽보다 적도록 정규화되도록 구성해야 합니다. 예를 들어 왼쪽 위(10,10)와 오른쪽 아래(20,20)는 정규화된 사각형을 정의하지만 왼쪽 위(20,20)와 오른쪽 아래(10,10)는 정규화되지 않은 사각형을 정의합니다. 사각형이 정규화되지 않으면 많은 `CRect` 멤버 함수가 잘못된 결과를 반환할 수 있습니다. (이러한 함수 목록은 [CRect::Normalizerect를](#normalizerect) 참조하십시오.) 정규화된 사각형이 필요한 함수를 호출하기 전에 함수를 `NormalizeRect` 호출하여 정규화되지 않은 사각형을 정규화할 수 있습니다.

`CRect` [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp) 및 [CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp) 멤버 함수로 조작할 때는 주의하십시오. 표시 컨텍스트의 매핑 모드가 y-익스텐션이 음수인 `MM_LOENGLISH`경우 `CDC::DPtoLP` 에서와 `CRect` 같이 의 맨 위가 아래쪽보다 커지되도록 변환합니다. 변환된 `CRect`높이의 `Height` `Size` 음수 값을 반환하고 같은 함수는 사각형이 정규화되지 않습니다.

오버 로드 된 `CRect` 연산자를 사용하는 경우 첫 번째 피연산자는 `CRect`여야 하고, 두 번째 피연산자는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 `CRect` 개체 중 하나일 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagRECT`

`CRect`

## <a name="requirements"></a>요구 사항

**헤더:** atltypes.h

## <a name="crectbottomright"></a><a name="bottomright"></a>CRect::하단 오른쪽

좌표는 `CRect`에 포함된 [CPoint](cpoint-class.md) 개체에 대한 참조로 반환됩니다.

```
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```

### <a name="return-value"></a>Return Value

사각형의 오른쪽 아래 모서리의 좌표입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 사각형의 오른쪽 아래 모서리를 얻거나 설정할 수 있습니다. 할당 연산자의 왼쪽에 있는 이 함수를 사용하여 코너를 설정합니다.

### <a name="example"></a>예제

```cpp
// use BottomRight() to retrieve the bottom
// right POINT
CRect rect(210, 150, 350, 900);
CPoint ptDown;

ptDown = rect.BottomRight();

// ptDown is now set to (350, 900)
ASSERT(ptDown == CPoint(350, 900));

// or, use BottomRight() to set the bottom
// right POINT
CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);

CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);
rect2.BottomRight() = ptLow;

// rect2 is now (10, 10, 180, 180)
ASSERT(rect2 == CRect(10, 10, 180, 180));
```

## <a name="crectcenterpoint"></a><a name="centerpoint"></a>CRect::중앙 점

왼쪽 및 오른쪽 `CRect` 값을 추가하고 2로 나누고 위쪽 및 아래쪽 값을 추가하고 두 개로 나누어 중심점을 계산합니다.

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>Return Value

`CRect`의 중심점인 `CPoint` 개체입니다.

### <a name="example"></a>예제

```cpp
// Code from this OnPaint() implementation can be pasted into your own application
// to draw lines that would look like a letter "Y" within your dialog.
void CMyDlg::OnPaint()
{
    CPaintDC dc(this);

    // device context for painting

    // get the size and position of the client area of
    // your window

    CRect rect;
    GetClientRect(&rect);

    // Move the current pen to the top left of the window. We call the
    // TopLeft() member of CRect here and it returns a CPoint object we
    // pass to the override of CDC::MoveTo() that accepts a CPoint.

    dc.MoveTo(rect.TopLeft());

    // Draw a line from the top left to the center of the window.
    // CenterPoint() gives us the middle point of the window as a
    // CPoint, and since CDC::LineTo() has an override that accepts a
    // CPoint, we can just pass it along.

    dc.LineTo(rect.CenterPoint());

    // Now, draw a line to the top right of the window. There's no
    // CRect member which returns a CPoint for the top right of the
    // window, so we'll reference the CPoint members directly and call
    // the CDC::LineTo() override which takes two integers.

    dc.LineTo(rect.right, rect.top);

    // The top part of the "Y" is drawn. Now, we'll draw the stem. We
    // start from the center point.

    dc.MoveTo(rect.CenterPoint());

    // and then draw to the middle of the bottom edge of the window.
    // We'll get the x-coordinate from the x member of the CPOINT
    // returned by CenterPoint(), and the y value comes directly from
    // the rect.

    dc.LineTo(rect.CenterPoint().x, rect.bottom);
}
```

## <a name="crectcopyrect"></a><a name="copyrect"></a>CRect::복사렉트

사각형을 `lpSrcRect` 로 복사합니다. `CRect`

```cpp
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>매개 변수

*lpSrcRect*<br/>
복사할 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 `CRect` 또는 개체를 가리킵니다.

### <a name="example"></a>예제

```cpp
CRect rectSource(35, 10, 125, 10);
CRect rectDest;

rectDest.CopyRect(&rectSource);

// rectDest is now set to (35, 10, 125, 10)

RECT rectSource2;
rectSource2.left = 0;
rectSource2.top = 0;
rectSource2.bottom = 480;
rectSource2.right = 640;

rectDest.CopyRect(&rectSource2);

// works against RECT structures, too!
// rectDest is now set to (0, 0, 640, 480)
```

## <a name="crectcrect"></a><a name="crect"></a>CRect:::CRect

`CRect` 개체를 생성합니다.

```
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();
```

### <a name="parameters"></a>매개 변수

*ℓ*<br/>
의 `CRect`왼쪽 위치를 지정합니다.

*t*<br/>
의 맨 위를 `CRect`지정합니다.

*r*<br/>
의 올바른 위치를 지정합니다. `CRect`

*B*<br/>
의 `CRect`맨 아래를 지정합니다.

*srcRect*<br/>
에 대한 좌표가 있는 RECT 구조를 나타냅니다. [RECT](/windows/win32/api/windef/ns-windef-rect) `CRect`

*lpSrcRect*<br/>
의 좌표가 `RECT` 있는 구조를 `CRect`가리킵니다.

*지점*<br/>
사각형을 생성할 원점을 지정합니다. 왼쪽 위 모서리에 해당합니다.

*size*<br/>
생성할 사각형의 왼쪽 위 모서리에서 오른쪽 아래 모서리로 변위를 지정합니다.

*topLeft*<br/>
왼쪽 상단 위치를 `CRect`지정합니다.

*bottomRight*<br/>
의 `CRect`오른쪽 아래 위치를 지정합니다.

### <a name="remarks"></a>설명

인수가 제공되지 않으면 `left`및 `top` `right` `bottom` 구성원은 초기화되지 않습니다.

`CRect`(`const RECT&`) 및 `CRect`(`LPCRECT`) 생성자는 [copyrect](#copyrect)를 수행합니다. 다른 생성자는 개체의 멤버 변수를 직접 초기화합니다.

### <a name="example"></a>예제

```cpp
// default constructor doesn't initialize!
CRect rectUnknown;

// four-integers are left, top, right, and bottom
CRect rect(0, 0, 100, 50);
ASSERT(rect.Width() == 100);
ASSERT(rect.Height() == 50);

// Initialize from RECT structure
RECT sdkRect;
sdkRect.left = 0;
sdkRect.top = 0;
sdkRect.right = 100;
sdkRect.bottom = 50;

CRect rect2(sdkRect);
// by reference
CRect rect3(&sdkRect);

// by address
ASSERT(rect2 == rect);
ASSERT(rect3 == rect);

// from a point and a size
CPoint pt(0, 0);
CSize sz(100, 50);
CRect rect4(pt, sz);
ASSERT(rect4 == rect2);

// from two points
CPoint ptBottomRight(100, 50);
CRect rect5(pt, ptBottomRight);
ASSERT(rect5 == rect4);
```

## <a name="crectdeflaterect"></a><a name="deflaterect"></a>CRect::D레플러트렉트

`DeflateRect`측면을 중심으로 `CRect` 이동하여 수축합니다.

```cpp
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
`CRect`의 왼쪽과 오른쪽을 수축할 단위 수를 지정합니다.

*Y*<br/>
`CRect`의 위쪽과 아래쪽을 수축할 단위 수를 지정합니다.

*size*<br/>
[수축할](/windows/win32/api/windef/ns-windef-size) 단위 수를 지정하는 크기 또는 `CRect` [CSize입니다.](csize-class.md) 값은 `cx` 왼쪽 과 오른쪽면을 수축하는 단위 수를 지정하고 `cy` 값은 상단과 하단을 수축할 단위 수를 지정합니다.

*Lprect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) 구조를 가리키거나 `CRect` 각 면을 수축할 단위 수를 지정합니다.

*ℓ*<br/>
의 왼쪽을 수축할 단위 수를 지정합니다. `CRect`

*t*<br/>
의 맨 위를 수축할 단위 수를 `CRect`지정합니다.

*r*<br/>
`CRect`의 오른쪽을 수축할 단위 수를 지정합니다.

*B*<br/>
`CRect`의 맨 아래를 수축할 단위 수를 지정합니다.

### <a name="remarks"></a>설명

이렇게 하려면 `DeflateRect` 왼쪽과 위쪽에 단위를 추가하고 오른쪽과 아래쪽에서 단위를 뺍니다. 의 `DeflateRect` 매개 변수는 서명 된 값입니다. 양수 값은 수축하고 `CRect` 음수 값은 팽창시입니다.

처음 두 오버로드는 양쪽 의 양쪽 `CRect` 쌍을 수축시켜 총 너비가 *x(또는)* `cx`두 배 감소하고 총 높이가 `cy`y(또는)의 두 배 감소합니다. *y* 다른 두 오버로드는 다른 `CRect` 오버로드와 독립적으로 각 면을 수축시됩니다.

### <a name="example"></a>예제

```cpp
CRect rect(10, 10, 50, 50);
rect.DeflateRect(1, 2);
ASSERT(rect.left == 11 && rect.right == 49);
ASSERT(rect.top == 12 && rect.bottom == 48);

CRect rect2(10, 10, 50, 50);
CRect rectDeflate(1, 2, 3, 4);
rect2.DeflateRect(&rectDeflate);
ASSERT(rect2.left == 11 && rect2.right == 47);
ASSERT(rect2.top == 12 && rect2.bottom == 46);
```

## <a name="crectequalrect"></a><a name="equalrect"></a>CRect::이퀄라이저

지정된 사각형과 동일한지 여부를 `CRect` 결정합니다.

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>매개 변수

*Lprect*<br/>
사각형의 왼쪽 위와 오른쪽 아래 모퉁이 좌표를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 `CRect`개체를 가리킵니다.

### <a name="return-value"></a>Return Value

두 사각형의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값이 동일한 경우 0이 아닙니다. 그렇지 않으면 0.

> [!NOTE]
> 두 사각형을 모두 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1.EqualRect(rect2));
ASSERT(!rect1.EqualRect(rect3));
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1.EqualRect(&test));
```

## <a name="crectheight"></a><a name="height"></a>CRect::높이

맨 아래 값에서 상단 값을 빼서 높이를 `CRect` 계산합니다.

```
int Height() const throw();
```

### <a name="return-value"></a>Return Value

의 `CRect`높이입니다.

### <a name="remarks"></a>설명

결과 값은 음수일 수 있습니다.

> [!NOTE]
> 사각형을 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

// nHt is now 40
ASSERT(nHt == 40);
```

## <a name="crectinflaterect"></a><a name="inflaterect"></a>CRect::팽창렉트

`InflateRect`측면을 중심에서 멀리 `CRect` 이동하여 팽창시됩니다.

```cpp
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
`CRect`의 왼쪽과 오른쪽을 팽창시키는 단위 수를 지정합니다.

*Y*<br/>
`CRect`의 위쪽과 아래쪽을 팽창시키는 단위 수를 지정합니다.

*size*<br/>
[팽창할](/windows/win32/api/windef/ns-windef-size) 단위 수를 지정하는 크기 또는 `CRect` [CSize입니다.](csize-class.md) 값은 `cx` 왼쪽과 오른쪽을 팽창시키는 단위 수를 지정하고 값은 `cy` 위쪽과 아래쪽을 팽창시키는 단위 수를 지정합니다.

*Lprect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) 구조를 가리키거나 `CRect` 각 면을 팽창시킬 단위 수를 지정합니다.

*ℓ*<br/>
`CRect`의 왼쪽을 팽창할 단위 수를 지정합니다.

*t*<br/>
의 맨 위를 팽창할 단위 수를 지정합니다. `CRect`

*r*<br/>
`CRect`의 오른쪽을 팽창할 단위 수를 지정합니다.

*B*<br/>
`CRect`의 맨 아래를 팽창할 단위 수를 지정합니다.

### <a name="remarks"></a>설명

이렇게 하려면 `InflateRect` 왼쪽과 위쪽에서 단위를 빼고 오른쪽과 아래쪽에 단위를 추가합니다. 의 `InflateRect` 매개 변수는 서명 된 값입니다. 양수 값이 `CRect` 팽창하고 음수 값이 팽창합니다.

처음 두 오버로드는 양쪽 의 반대쪽 `CRect` 쌍을 팽창시켜 총 너비가 *x(또는)* `cx`두 배 증가하고 총 높이가 `cy`y(또는)의 두 배 증가합니다. *y* 다른 두 오버로드는 다른 오버로드와 `CRect` 독립적으로 각 면을 팽창시입니다.

### <a name="example"></a>예제

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

## <a name="crectintersectrect"></a><a name="intersectrect"></a>CRect::교차렉트

두 `CRect` 개의 기존 사각형의 교차점과 동일하게 만듭니다.

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>매개 변수

*lpRect1*<br/>
소스 사각형을 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 `CRect` 개체를 가리킵니다.

*lpRect2*<br/>
소스 사각형이 `RECT` `CRect` 포함된 구조체 또는 개체를 가리킵니다.

### <a name="return-value"></a>Return Value

교차점이 비어 있지 않으면 0이 아님을 교차가 비어 있는 경우 0입니다.

### <a name="remarks"></a>설명

교차는 두 기존 사각형에 포함된 가장 큰 사각형입니다.

> [!NOTE]
> 두 사각형을 모두 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect rectOne(125,  0, 150, 200);
CRect rectTwo(0, 75, 350, 95);
CRect rectInter;

rectInter.IntersectRect(rectOne, rectTwo);
ASSERT(rectInter == CRect(125, 75, 150, 95));
// operator &= can do the same task:

CRect rectInter2 = rectOne;
rectInter2 &= rectTwo;
ASSERT(rectInter2 == CRect(125, 75, 150, 95));
```

## <a name="crectisrectempty"></a><a name="isrectempty"></a>CRect::IsRect빈

비어 있는지 `CRect` 여부를 결정합니다.

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>Return Value

비어 있는 `CRect` 경우 영하지 않습니다. 0이 `CRect` 비어 있지 않은 경우.

### <a name="remarks"></a>설명

너비 및/또는 높이가 0 또는 음수인 경우 사각형이 비어 있습니다. 사각형의 `IsRectNull`모든 좌표가 0인지 여부를 결정하는 와 다릅니다.

> [!NOTE]
> 사각형을 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
ASSERT(rectEmpty.IsRectEmpty());
```

## <a name="crectisrectnull"></a><a name="isrectnull"></a>CRect::IsRectNull

위쪽, 왼쪽, 아래쪽 및 오른쪽 `CRect` 값이 모두 0과 같은지 여부를 결정합니다.

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>Return Value

비영점의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값이 모두 0인 경우; `CRect` 그렇지 않으면 0.

### <a name="remarks"></a>설명

사각형이 `IsRectEmpty`비어 있는지 여부를 결정하는 와 다릅니다.

### <a name="example"></a>예제

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
ASSERT(!rectSome.IsRectNull());
// note that null means _all_ zeros

CRect rectNotNull(0, 0, 35, 50);
ASSERT(!rectNotNull.IsRectNull());
```

## <a name="crectmovetox"></a><a name="movetox"></a>CRect::무브톡스

이 함수를 호출하여 사각형을 *x로*지정된 절대 x 좌표로 이동합니다.

```cpp
void MoveToX(int x) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
사각형의 왼쪽 위 모서리에 대한 절대 x 좌표입니다.

### <a name="example"></a>예제

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

// rect is now (10, 0, 110, 100);
ASSERT(rect == CRect(10, 0, 110, 100));
```

## <a name="crectmovetoxy"></a><a name="movetoxy"></a>CRect::무브톡시

이 함수를 호출하여 사각형을 지정된 절대 x- 및 y 좌표로 이동합니다.

```cpp
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
사각형의 왼쪽 위 모서리에 대한 절대 x 좌표입니다.

*Y*<br/>
사각형의 왼쪽 위 모서리에 대한 절대 y 좌표입니다.

*지점*<br/>
사각형의 왼쪽 위 절대 모서리를 지정하는 `POINT` 구조입니다.

### <a name="example"></a>예제

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
ASSERT(rect == CRect(10, 10, 110, 110));
```

## <a name="crectmovetoy"></a><a name="movetoy"></a>CRect::무브토이

이 함수를 호출하여 사각형을 *y로*지정된 절대 y 좌표로 이동합니다.

```cpp
void MoveToY(int y) throw();
```

### <a name="parameters"></a>매개 변수

*Y*<br/>
사각형의 왼쪽 위 모서리에 대한 절대 y 좌표입니다.

### <a name="example"></a>예제

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
ASSERT(rect == CRect(0, 10, 100, 110));
```

## <a name="crectnormalizerect"></a><a name="normalizerect"></a>CRect::정규수정

높이와 `CRect` 너비가 모두 양수이되도록 정규화합니다.

```cpp
void NormalizeRect() throw();
```

### <a name="remarks"></a>설명

사각형은 Windows에서 일반적으로 좌표에 사용하는 네 번째 사분면 위치 지정에 대해 정규화됩니다. `NormalizeRect`은 위쪽 및 아래쪽 값을 비교하고 위쪽값이 아래쪽보다 큰 경우 바꿉습니다. 마찬가지로 왼쪽이 오른쪽보다 큰 경우 왼쪽 및 오른쪽 값을 바꿉습니다. 이 함수는 서로 다른 매핑 모드와 반전된 사각형을 처리할 때 유용합니다.

> [!NOTE]
> `CRect` 다음 멤버 함수는 [높이,](#height) [너비](#width), [크기,](#size) [IsRectEmpty,](#isrectempty) [PtInRect](#ptinrect), [EqualRect](#equalrect), [유니온렉트](#unionrect), [교차 Rect](#intersectrect), [빼기](#subtractrect), [연산자 = =](#operator_eq_eq)= , [연산자](#operator_neq)&#124;, [연산자 ](#operator_or) [&#124;= 연산자](#operator_or_eq) [&](#operator_amp)= 및 [연산자 &=](#operator_amp_eq)

### <a name="example"></a>예제

```cpp
CRect rect1(110, 100, 250, 310);
CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
rect2.NormalizeRect();
ASSERT(rect1 == rect2);
```

## <a name="crectoffsetrect"></a><a name="offsetrect"></a>CRect::오프셋렉트

지정된 `CRect` 오프셋으로 이동합니다.

```cpp
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
왼쪽 또는 오른쪽으로 이동할 양을 지정합니다. 왼쪽으로 이동하려면 음수여야 합니다.

*Y*<br/>
위 또는 아래로 이동할 양을 지정합니다. 위로 이동하려면 음수여야 합니다.

*지점*<br/>
이동할 [두](/windows/win32/api/windef/ns-windef-point) 차원을 지정하는 POINT 구조 또는 [CPoint](cpoint-class.md) 객체를 포함합니다.

*size*<br/>
이동할 [두](/windows/win32/api/windef/ns-windef-size) 차원을 지정하는 SIZE 구조 또는 [CSize](csize-class.md) 개체가 포함되어 있습니다.

### <a name="remarks"></a>설명

x축을 따라 `CRect` *x* 단위와 *y축을* 따라 y 단위를 이동합니다. *x* 및 *y* 매개변수는 서명된 값이므로 `CRect` 왼쪽 또는 오른쪽 및 위 또는 아래로 이동할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect rect(0, 0, 35, 35);
rect.OffsetRect(230, 230);

// rect is now (230, 230, 265, 265)
ASSERT(rect == CRect(230, 230, 265, 265));
```

## <a name="crectoperator-lpcrect-converts-a-crect-to-an-lpcrect"></a><a name="operator_lpcrect"></a>CRect::연산자 LPCRECT는 `CRect` [A를 LPCRECT로](../../mfc/reference/data-types-mfc.md)변환합니다.

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>설명

이 함수를 사용하면 주소()**&** 연산자가 필요하지 않습니다. 이 연산자는 `CRect` `LPCRECT`개체를 예상하는 함수에 전달할 때 자동으로 사용됩니다.

## <a name="crectoperator-lprect"></a><a name="operator_lprect"></a>CRect::연산자 LPRECT

을 `CRect` [LPRECT로](../../mfc/reference/data-types-mfc.md)변환합니다.

```
operator LPRECT() throw();
```

### <a name="remarks"></a>설명

이 함수를 사용하면 주소()**&** 연산자가 필요하지 않습니다. 이 연산자는 `CRect` `LPRECT`개체를 예상하는 함수에 전달할 때 자동으로 사용됩니다.

### <a name="example"></a>예제

[CRect::연산자 LPCRECT에](#operator_lpcrect)대한 예제를 참조하십시오.

## <a name="crectoperator-"></a><a name="operator_eq"></a>CRect::연산자 =

*srcRect를* 에 `CRect`할당합니다.

```cpp
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>매개 변수

*srcRect*<br/>
소스 사각형을 나타냅니다. [RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`.

### <a name="example"></a>예제

```cpp
CRect rect(0, 0, 127, 168);
CRect rect2;

rect2 = rect;
ASSERT(rect2 == CRect(0, 0, 127, 168));
```

## <a name="crectoperator-"></a><a name="operator_eq_eq"></a>CRect::연산자 ==

왼쪽 위 `rect` 및 `CRect` 오른쪽 아래 모서리의 좌표를 비교하여 같는지 여부를 결정합니다.

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
소스 사각형을 나타냅니다. [RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`.

### <a name="return-value"></a>Return Value

비영점(같음); 그렇지 않으면 0.

### <a name="remarks"></a>설명

> [!NOTE]
> 두 사각형을 모두 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1 == rect2);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1 == test);
```

## <a name="crectoperator-"></a><a name="operator_neq"></a>CRect::연산자 !=

*rect가* 왼쪽 위 및 `CRect` 오른쪽 아래 모서리의 좌표를 비교하여 정사각형이 같지 않은지 여부를 결정합니다.

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
소스 사각형을 나타냅니다. [RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`.

### <a name="return-value"></a>Return Value

비영이 같지 않은 경우; 그렇지 않으면 0.

### <a name="remarks"></a>설명

> [!NOTE]
> 두 사각형을 모두 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999,  6,  3);
ASSERT(rect1 != rect3);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect3 != test);
```

## <a name="crectoperator-"></a><a name="operator_add_eq"></a>CRect::연산자 +=

처음 두 오버로드는 지정된 오프셋에 의해 이동합니다. `CRect`

```cpp
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
사각형을 이동할 단위 수를 지정하는 [POINT](/windows/win32/api/windef/ns-windef-point) 구조 또는 [CPoint](cpoint-class.md) 개체입니다.

*size*<br/>
사각형을 이동할 단위 수를 지정하는 [SIZE](/windows/win32/api/windef/ns-windef-size) 구조 또는 [CSize](csize-class.md) 개체입니다.

*Lprect*<br/>
각 측면을 확장할 단위 수를 포함하는 [](/windows/win32/api/windef/ns-windef-rect)RECT`CRect` 구조체 또는 `CRect`개체를 가리킵니다.

### <a name="remarks"></a>설명

매개 변수의 *x* 및 `cx` `cy` *y(또는)* 값이 `CRect`에 추가됩니다.

세 번째 오버로드는 `CRect` 매개변수의 각 멤버에 지정된 단위 수에 따라 팽창합니다.

### <a name="example"></a>예제

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint  pt(35, 65);
CRect   rect2(135, 300, 235, 400);

rect1 += pt;
ASSERT(rect1 == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-_eq"></a>CRect::연산자 -=

처음 두 오버로드는 지정된 오프셋에 의해 이동합니다. `CRect`

```cpp
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
사각형을 이동할 단위 수를 지정하는 [POINT](/windows/win32/api/windef/ns-windef-point) 구조 또는 [CPoint](cpoint-class.md) 개체입니다.

*size*<br/>
사각형을 이동할 단위 수를 지정하는 [SIZE](/windows/win32/api/windef/ns-windef-size) 구조 또는 [CSize](csize-class.md) 개체입니다.

*Lprect*<br/>
각 측면을 수축하는 단위 수를 포함하는 [](/windows/win32/api/windef/ns-windef-rect)RECT`CRect` 구조체 또는 `CRect` 개체를 가리킵니다.

### <a name="remarks"></a>설명

매개 변수의 *x* 및 `cx` `cy` *y(또는)* 값은 `CRect`에서 뺍니다.

세 번째 오버로드는 `CRect` 매개변수의 각 멤버에 지정된 단위 수에 따라 수축됩니다. 이 오버로드 는 [DeflateRect](#deflaterect)와 같은 기능입니다.

### <a name="example"></a>예제

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);

rect1 -= pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect1 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp_eq"></a>CRect::연산자&amp;=

의 `CRect` 교차와 같게 `rect`설정합니다. `CRect`

```cpp
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`.

### <a name="remarks"></a>설명

교차는 두 사각형모두에 포함된 가장 큰 사각형입니다.

> [!NOTE]
> 두 사각형을 모두 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

[CRect::IntersectRect에](#intersectrect)대한 예제를 참조하십시오.

## <a name="crectoperator-124"></a><a name="operator_or_eq"></a>CRect::연산자 &#124;=

의 `CRect` 결합과 `CRect` `rect`같음을 설정합니다.

```cpp
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
`CRect` 또는 [RECT](/windows/win32/api/windef/ns-windef-rect)를 포함합니다.

### <a name="remarks"></a>설명

공용 구조는 두 소스 사각형을 모두 포함하는 가장 작은 사각형입니다.

> [!NOTE]
> 두 사각형을 모두 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);

rect1 |= rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect1);
```

## <a name="crectoperator-"></a><a name="operator_add"></a>CRect::연산자 +

처음 두 오버로드는 `CRect` 지정된 오프셋에 의해 `CRect` 변위된 오브젝트와 동일한 객체를 반환합니다.

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
반환 값을 이동할 단위 수를 지정하는 [POINT](/windows/win32/api/windef/ns-windef-point) 구조 또는 [CPoint](cpoint-class.md) 개체입니다.

*size*<br/>
반환 값을 이동할 단위 수를 지정하는 [SIZE](/windows/win32/api/windef/ns-windef-size) 구조 또는 [CSize](csize-class.md) 개체입니다.

*Lprect*<br/>
반환 값의 각 면을 확장할 단위 수를 포함 하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 `CRect` 개체를 가리킵니다.

### <a name="return-value"></a>Return Value

매개변수에 지정된 단위 `CRect` `CRect` 수에 따라 이동하거나 팽창한 결과입니다.

### <a name="remarks"></a>설명

매개 변수의 *x* 및 `cx` *y(또는* 및) `cy` `CRect`매개변수가 '위치에 추가됩니다.

세 번째 오버로드는 `CRect` 매개 변수의 각 멤버에 지정된 단위 수로 `CRect` 팽창된 새 를 반환합니다.

### <a name="example"></a>예제

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 + pt;
CRect   rectResult(135, 300, 235, 400);
ASSERT(rectResult == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-"></a>CRect::연산자 -

처음 두 오버로드는 `CRect` 지정된 오프셋에 의해 `CRect` 변위된 오브젝트와 동일한 객체를 반환합니다.

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
반환 값을 이동할 단위 수를 지정하는 [점](/windows/win32/api/windef/ns-windef-point) 구조 또는 `CPoint` 개체입니다.

*size*<br/>
반환 값을 이동할 단위 수를 지정하는 [크기](/windows/win32/api/windef/ns-windef-size) 구조체 또는 `CSize` 개체입니다.

*Lprect*<br/>
반환 값의 각 측면을 수축하는 단위 수를 포함 하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조체 또는 `CRect` 개체를 가리킵니다.

### <a name="return-value"></a>Return Value

매개변수에 지정된 단위 `CRect` `CRect` 수에 따라 이동 또는 수축으로 인한 결과입니다.

### <a name="remarks"></a>설명

매개 변수의 *x* 및 `cx` *y(또는* 및) `cy`매개변수는 '위치'에서 `CRect`뺍니다.

세 번째 오버로드는 `CRect` 매개 변수의 각 멤버에 지정된 단위 수로 `CRect` 수축된 새 를 반환합니다. 이 오버로드 함수는 [DeflateRect와](#deflaterect) [SubtractRect](#subtractrect)같은 함수입니다.

### <a name="example"></a>예제

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 - pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect2 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp"></a>CRect::연산자&amp;

rect2의 `CRect` `CRect` 교차점인 *a를 반환합니다.*

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>매개 변수

*rect2*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`.

### <a name="return-value"></a>Return Value

A는 `CRect` `CRect` *rect2의*교차점입니다.

### <a name="remarks"></a>설명

교차는 두 사각형모두에 포함된 가장 큰 사각형입니다.

> [!NOTE]
> 두 사각형을 모두 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 & rect2;
CRect   rectResult(100, 100, 200, 200);
ASSERT(rectResult == rect3);
```

## <a name="crectoperator-124"></a><a name="operator_or"></a>CRect::연산자 &#124;

`CRect` `CRect` *rect2의*결합인 을 반환합니다.

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>매개 변수

*rect2*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`.

### <a name="return-value"></a>Return Value

A는 `CRect` `CRect` *rect2의*결합입니다.

### <a name="remarks"></a>설명

공용 구조는 두 사각형을 모두 포함하는 가장 작은 사각형입니다.

> [!NOTE]
> 두 사각형을 모두 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 | rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectptinrect"></a><a name="ptinrect"></a>트렉트::P트인렉트

지정된 점이 내에 `CRect`있는지 여부를 결정합니다.

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point) 구조 또는 [CPoint](cpoint-class.md) 개체를 포함합니다.

### <a name="return-value"></a>Return Value

포인트가 내에 `CRect`있는 경우 비영점; 그렇지 않으면 0.

### <a name="remarks"></a>설명

점은 왼쪽 `CRect` 또는 위쪽에 있거나 네 면 내에 있는 경우 내에 있습니다. 오른쪽 또는 아래쪽에 있는 점은 `CRect`바깥쪽에 있습니다.

> [!NOTE]
> 사각형을 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect rect(5, 5, 100, 100);
CPoint pt1(35, 50);
CPoint pt2(125, 298);

// this is true, because pt1 is inside the rectangle
ASSERT(rect.PtInRect(pt1));

// this is NOT true, because pt2 is outside the rectangle
ASSERT(!rect.PtInRect(pt2));

// note that the right and the bottom aren't inside
ASSERT(!rect.PtInRect(CPoint(35, 100)));
ASSERT(!rect.PtInRect(CPoint(100, 98)));

// but the top and the left are inside
ASSERT(rect.PtInRect(CPoint(5, 65)));
ASSERT(rect.PtInRect(CPoint(88, 5)));

// and that PtInRect() works against a POINT, too
POINT pt;
pt.x = 35;
pt.y = 50;
ASSERT(rect.PtInRect(pt));
```

## <a name="crectsetrect"></a><a name="setrect"></a>CRect:::SetRect

지정된 좌표로 `CRect` 치수를 설정합니다.

```cpp
void SetRect(int x1, int y1, int x2, int y2) throw();
```

### <a name="parameters"></a>매개 변수

*x1*<br/>
왼쪽 위 모서리의 x 좌표를 지정합니다.

*y1*<br/>
왼쪽 위 모서리의 y 좌표를 지정합니다.

*x2*<br/>
오른쪽 아래 모서리의 x 좌표를 지정합니다.

*y2*<br/>
오른쪽 아래 모서리의 y 좌표를 지정합니다.

### <a name="example"></a>예제

```cpp
CRect rect;
rect.SetRect(256, 256, 512, 512);
ASSERT(rect == CRect(256, 256, 512, 512));
```

## <a name="crectsetrectempty"></a><a name="setrectempty"></a>CRect::SetRect빈

모든 `CRect` 좌표를 0으로 설정하여 null 사각형을 만듭니다.

```cpp
void SetRectEmpty() throw();
```

### <a name="example"></a>예제

```cpp
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());
```

## <a name="crectsize"></a><a name="size"></a>CRect::크기

`cx` 반환 `cy` 값의 멤버에는 의 높이와 `CRect`너비가 포함됩니다.

```
CSize Size() const throw();
```

### <a name="return-value"></a>Return Value

의 크기를 포함하는 [CSize](csize-class.md) `CRect`개체입니다.

### <a name="remarks"></a>설명

높이 나 너비는 음수일 수 있습니다.

> [!NOTE]
> 사각형을 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

## <a name="crectsubtractrect"></a><a name="subtractrect"></a>CRect::빼기

의 치수를 에서 `CRect` 빼기와 `lpRectSrc2` 동일하게 `lpRectSrc1`만듭니다.

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>매개 변수

*lpRectSrc1*<br/>
사각형을 빼는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 `CRect` 오브젝트를 가리킵니다.

*lpRectSrc2*<br/>
`RECT` *lpRectSrc1* 매개변수가 가리키는 사각형에서 빼야 할 구조또는 `CRect` 객체를 가리킵니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

빼기는 *lpRectScr1 및 lpRectScr2의 교차점에 없는 lpRectScr1의* 모든 *lpRectScr2*점을 포함하는 가장 작은 사각형입니다. *lpRectScr1*

*lpRectSrc1에* 의해 지정된 사각형이 *lpRectSrc2에* 의해 지정된 사각형이 x- 또는 y 방향 중 하나 이상에서 *lpRectSrc1에* 의해 지정된 사각형과 완전히 겹치지 않는 경우 lpRectSrc1에 의해 지정된 사각형은 변경되지 않습니다.

예를 들어 *lpRectSrc1이* (10,10, 100,100) 및 *lpRectSrc2(50,50,* 150,150)인 경우 함수가 반환될 때 *lpRectSrc1이* 가리키는 사각형은 변경되지 않습니다. *lpRectSrc1이* (10,10, 100,100) 및 *lpRectSrc2* (50,10, 150,150)인 경우, 그러나 *lpRectSrc1에* 의해 가리키는 사각형은 함수가 반환 될 때 좌표 (10,10, 50,100)를 포함합니다.

`SubtractRect`[연산자와](#operator_-) 동일하지 않습니다 - 도 [연산자 -=](#operator_-_eq). 이러한 연산자 중 `SubtractRect`어느 것도 호출하지 않습니다.

> [!NOTE]
> 두 사각형을 모두 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
RECT   rectOne;
RECT   rectTwo;

rectOne.left = 10;
rectOne.top = 10;
rectOne.bottom = 100;
rectOne.right = 100;

rectTwo.left = 50;
rectTwo.top = 10;
rectTwo.bottom = 150;
rectTwo.right = 150;

CRect   rectDiff;

rectDiff.SubtractRect(&rectOne, &rectTwo);
CRect   rectResult(10, 10, 50, 100);

ASSERT(rectDiff == rectResult);

// works for CRect, too, since there is
// implicit CRect -> LPCRECT conversion

CRect rect1(10, 10, 100, 100);
CRect rect2(50, 10, 150, 150);
CRect rectOut;

rectOut.SubtractRect(rect1, rect2);
ASSERT(rectResult == rectOut);
```

## <a name="crecttopleft"></a><a name="topleft"></a>CRect:::맨 위 왼쪽

좌표는 `CRect`에 포함된 [CPoint](cpoint-class.md) 개체에 대한 참조로 반환됩니다.

```
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw();
```

### <a name="return-value"></a>Return Value

사각형의 왼쪽 위 모서리의 좌표입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 사각형의 왼쪽 위 모서리를 얻거나 설정할 수 있습니다. 할당 연산자의 왼쪽에 있는 이 함수를 사용하여 코너를 설정합니다.

### <a name="example"></a>예제

[CRect::CenterPoint](#centerpoint)에 대한 예제를 참조하십시오.

## <a name="crectunionrect"></a><a name="unionrect"></a>CRect:::유니온렉트

두 소스 사각형의 결합과 `CRect` 동일한 크기를 만듭니다.

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>매개 변수

*lpRect1*<br/>
[RECT또는](/windows/win32/api/windef/ns-windef-rect) `CRect` 소스 사각형이 포함된 것을 가리킵니다.

*lpRect2*<br/>
소스 사각형이 `CRect` 포함된 또는 를 `RECT` 가리킵니다.

### <a name="return-value"></a>Return Value

공용 구조가 비어 있지 않으면 0이 아님을 의미합니다. 공용 구조가 비어 있는 경우 0입니다.

### <a name="remarks"></a>설명

공용 구조는 두 소스 사각형을 모두 포함하는 가장 작은 사각형입니다.

Windows는 빈 사각형의 크기를 무시합니다. 즉, 높이가 없거나 너비가 없는 사각형입니다.

> [!NOTE]
> 두 사각형을 모두 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3.UnionRect(&rect1, &rect2);
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectwidth"></a><a name="width"></a>CRect::너비

오른쪽 값에서 `CRect` 왼쪽 값을 빼서 너비를 계산합니다.

```
int Width() const throw();
```

### <a name="return-value"></a>Return Value

의 `CRect`너비입니다.

### <a name="remarks"></a>설명

너비는 음수일 수 있습니다.

> [!NOTE]
> 사각형을 정규화해야 하거나 이 함수가 실패할 수 있습니다. 이 함수를 호출하기 전에 [NormalizeRect를](#normalizerect) 호출하여 사각형을 정규화할 수 있습니다.

### <a name="example"></a>예제

```cpp
CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
// nWid is now 60
ASSERT(nWid == 60);
```

## <a name="see-also"></a>참조

[C포인트 클래스](cpoint-class.md)<br/>
[C사이즈 클래스](csize-class.md)<br/>
[Rect](/windows/win32/api/windef/ns-windef-rect)
