---
title: CRect 클래스
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
ms.openlocfilehash: 13f86c411cca98f5817d1b3b2d9162ae8af8b734
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423599"
---
# <a name="crect-class"></a>CRect 클래스

Windows [RECT](/windows/win32/api/windef/ns-windef-rect) 구조체와 유사 합니다.

## <a name="syntax"></a>구문

```
class CRect : public tagRECT
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CRect::CRect](#crect)|`CRect` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CRect::BottomRight](#bottomright)|`CRect`의 오른쪽 아래 지점을 반환 합니다.|
|[CRect::CenterPoint](#centerpoint)|`CRect`centerpoint를 반환 합니다.|
|[CRect::CopyRect](#copyrect)|`CRect`에 소스 사각형의 크기를 복사 합니다.|
|[CRect::DeflateRect](#deflaterect)|`CRect`의 너비와 높이를 줄입니다.|
|[CRect::EqualRect](#equalrect)|`CRect` 지정 된 사각형과 같은지 여부를 확인 합니다.|
|[CRect::Height](#height)|`CRect`높이를 계산 합니다.|
|[CRect::InflateRect](#inflaterect)|`CRect`의 너비와 높이를 늘립니다.|
|[CRect::IntersectRect](#intersectrect)|두 사각형이 교차 하는 것과 같은 `CRect`를 설정 합니다.|
|[CRect::IsRectEmpty](#isrectempty)|`CRect` 비어 있는지 여부를 확인 합니다. 너비 및/또는 높이가 0 이면 `CRect` 비어 있습니다.|
|[CRect::IsRectNull](#isrectnull)|`top`, `bottom`, `left`및 `right` 멤버 변수가 모두 0과 같은지 여부를 확인 합니다.|
|[CRect::MoveToX](#movetox)|`CRect`를 지정 된 x 좌표로 이동 합니다.|
|[CRect::MoveToXY](#movetoxy)|`CRect`를 지정 된 x 및 y 좌표로 이동 합니다.|
|[CRect::MoveToY](#movetoy)|`CRect`를 지정 된 y 좌표로 이동 합니다.|
|[CRect::NormalizeRect](#normalizerect)|`CRect`의 높이와 너비를 표준화 합니다.|
|[CRect::OffsetRect](#offsetrect)|지정 된 오프셋으로 `CRect` 이동 합니다.|
|[CRect::PtInRect](#ptinrect)|지정 된 지점이 `CRect`내에 있는지 여부를 확인 합니다.|
|[CRect::SetRect](#setrect)|`CRect`의 크기를 설정 합니다.|
|[CRect::SetRectEmpty](#setrectempty)|`CRect`를 빈 사각형 (모든 좌표가 0)으로 설정 합니다.|
|[CRect::Size](#size)|`CRect`의 크기를 계산 합니다.|
|[CRect::SubtractRect](#subtractrect)|한 사각형을 다른 사각형에서 뺍니다.|
|[CRect::TopLeft](#topleft)|`CRect`의 왼쪽 위 지점을 반환 합니다.|
|[CRect::UnionRect](#unionrect)|두 사각형의 합집합 `CRect` 같도록 설정 합니다.|
|[CRect::Width](#width)|`CRect`의 너비를 계산 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CRect:: operator-](#operator_-)|`CRect` 또는 수축 `CRect`에서 지정 된 오프셋을 빼고 결과 `CRect`반환 합니다.|
|[CRect:: operator LPCRECT](#operator_lpcrect)|`CRect`를 `LPCRECT`로 변환합니다.|
|[CRect:: operator LPRECT](#operator_lprect)|`CRect`를 `LPRECT`로 변환합니다.|
|[CRect::operator !=](#operator_neq)|`CRect` 사각형과 같지 않은지 여부를 확인 합니다.|
|[CRect:: operator &amp;](#operator_amp)|`CRect`와 사각형의 교집합을 만들고 결과 `CRect`을 반환 합니다.|
|[CRect::operator &amp;=](#operator_amp_eq)|`CRect`와 사각형의 교집합에 `CRect`을 설정 합니다.|
|[CRect:: operator&#124;](#operator_or)|`CRect`와 사각형의 합집합을 만들고 결과 `CRect`을 반환 합니다.|
|[CRect:: operator &#124;=](#operator_or_eq)|`CRect`와 사각형의 합집합 `CRect` 동일 하 게 설정 합니다.|
|[CRect:: operator +](#operator_add)|`CRect` 또는 늘어납니다 `CRect`에 지정 된 오프셋을 추가 하 고 결과 `CRect`반환 합니다.|
|[CRect:: operator + =](#operator_add_eq)|`CRect` 또는 늘어납니다 `CRect`에 지정 된 오프셋을 추가 합니다.|
|[CRect::operator =](#operator_eq)|사각형의 크기를 `CRect`에 복사 합니다.|
|[CRect::operator -=](#operator_-_eq)|`CRect` 또는 수축 `CRect`에서 지정 된 오프셋을 뺍니다.|
|[CRect::operator ==](#operator_eq_eq)|`CRect` 사각형과 같은지 여부를 확인 합니다.|

## <a name="remarks"></a>주의

`CRect`에는 `CRect` 개체와 Windows `RECT` 구조를 조작 하는 멤버 함수도 포함 됩니다.

`CRect` 개체는 `RECT` 구조, `LPCRECT`또는 `LPRECT`를 전달할 수 있는 모든 곳에서 함수 매개 변수로 전달 될 수 있습니다.

> [!NOTE]
> 이 클래스는 `tagRECT` 구조체에서 파생 됩니다. 이름 `tagRECT`은 일반적으로 사용 되지 않는 `RECT` 구조체 이름입니다.) 이는 `RECT` 구조의 데이터 멤버 (`left`, `top`, `right`및 `bottom`)가 `CRect`의 액세스 가능한 데이터 멤버 임을 의미 합니다.

`CRect`는 사각형의 왼쪽 위 및 오른쪽 아래를 정의 하는 멤버 변수를 포함 합니다.

`CRect`지정 하는 경우 왼쪽 좌표 값이 오른쪽 보다 작고 위쪽이 아래쪽 보다 작은 것으로 정규화 되도록 구성 해야 합니다. 즉, 해당 값을 정규화 해야 합니다. 예를 들어 (10, 10)의 왼쪽 위와 (20, 20)의 오른쪽 아래에는 정규화 된 사각형이 정의 되지만 (20, 20)의 왼쪽 위와 (10, 10)의 오른쪽 하단은 정규화 되지 않은 사각형을 정의 합니다. 사각형이 정규화 되지 않은 경우 많은 `CRect` 멤버 함수에서 잘못 된 결과를 반환할 수 있습니다. 이러한 함수 목록은 [Crect:: NormalizeRect](#normalizerect) 를 참조 하세요. 정규화 된 사각형이 필요한 함수를 호출 하기 전에 `NormalizeRect` 함수를 호출 하 여 정규화 되지 않은 사각형을 정규화 할 수 있습니다.

[Cdc::D ptolp](../../mfc/reference/cdc-class.md#dptolp) 및 [Cdc:: lptodp](../../mfc/reference/cdc-class.md#lptodp) 멤버 함수를 사용 하 여 `CRect`를 조작 하는 경우 주의 해야 합니다. 표시 컨텍스트의 매핑 모드가 `MM_LOENGLISH`와 같이 y 범위가 음수 이면 `CDC::DPtoLP`는 위쪽이 아래쪽 보다 더 큰지 `CRect`를 변환 하 게 됩니다. `Height` 및 `Size`와 같은 함수는 변환 된 `CRect`의 높이에 대해 음수 값을 반환 하 고 사각형은 정규화 되지 않습니다.

오버 로드 된 `CRect` 연산자를 사용하는 경우 첫 번째 피연산자는 `CRect`여야 하고, 두 번째 피연산자는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 `CRect` 개체 중 하나일 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagRECT`

`CRect`

## <a name="requirements"></a>요구 사항

**헤더:** 이 형식 .h

##  <a name="bottomright"></a>  CRect::BottomRight

좌표는 `CRect`포함 된 [Cpoint](cpoint-class.md) 개체에 대 한 참조로 반환 됩니다.

```
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```

### <a name="return-value"></a>반환 값

사각형의 오른쪽 아래 모퉁이의 좌표입니다.

### <a name="remarks"></a>주의

이 함수를 사용 하 여 사각형의 오른쪽 아래 모퉁이를 가져오거나 설정할 수 있습니다. 할당 연산자의 왼쪽에서이 함수를 사용 하 여 모퉁이를 설정 합니다.

### <a name="example"></a>예

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

##  <a name="centerpoint"></a>  CRect::CenterPoint

왼쪽 및 오른쪽 값을 2로 나누고, 위쪽 및 아래쪽 값을 더하여 두 값을 나누어 `CRect`의 centerpoint 계산 합니다.

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>반환 값

`CRect`centerpoint `CPoint` 개체입니다.

### <a name="example"></a>예

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

##  <a name="copyrect"></a>  CRect::CopyRect

`lpSrcRect` 사각형을 `CRect`에 복사 합니다.

```
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>매개 변수

*lpSrcRect*<br/>
복사할 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 `CRect` 개체를 가리킵니다.

### <a name="example"></a>예

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

##  <a name="crect"></a>  CRect::CRect

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

*l*<br/>
`CRect`의 왼쪽 위치를 지정 합니다.

*t*<br/>
`CRect`의 맨 위를 지정 합니다.

*r*<br/>
`CRect`의 오른쪽 위치를 지정 합니다.

*b*<br/>
`CRect`의 아래쪽을 지정 합니다.

*srcRect*<br/>
`CRect`의 좌표가 포함 된 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조체를 참조 합니다.

*lpSrcRect*<br/>
`CRect`좌표를 사용 하 여 `RECT` 구조체를 가리킵니다.

*point*<br/>
생성할 사각형의 원본 지점을 지정 합니다. 왼쪽 위 모퉁이에 해당 합니다.

*size*<br/>
왼쪽 위 모서리에서 생성할 사각형의 오른쪽 아래 모퉁이 까지의 변위를 지정 합니다.

*topLeft*<br/>
`CRect`의 왼쪽 위 위치를 지정 합니다.

*bottomRight*<br/>
`CRect`의 오른쪽 아래 위치를 지정 합니다.

### <a name="remarks"></a>주의

인수를 지정 하지 않으면 `left`, `top`, `right`및 `bottom` 멤버가 초기화 되지 않습니다.

`CRect`(`const RECT&`) 및 `CRect`(`LPCRECT`) 생성자는 [copyrect](#copyrect)를 수행합니다. 다른 생성자는 개체의 멤버 변수를 직접 초기화 합니다.

### <a name="example"></a>예

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

##  <a name="deflaterect"></a>  CRect::DeflateRect

수축 `CRect`를 중심 쪽으로 이동 하 여 `DeflateRect` 합니다.

```
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
`CRect`의 왼쪽과 오른쪽을 수축 하는 단위 수를 지정 합니다.

*y*<br/>
`CRect`의 위쪽과 아래쪽을 수축 하는 단위 수를 지정 합니다.

*size*<br/>
`CRect`를 수축 하는 단위 수를 지정 하는 [크기](/windows/win32/api/windef/ns-windef-size) 또는 [csize](csize-class.md) 입니다. `cx` 값은 왼쪽과 오른쪽을 수축 하는 단위 수를 지정 하 고 `cy` 값은 위쪽 및 아래쪽을 수축 하는 단위 수를 지정 합니다.

*lpRect*<br/>
각 면을 수축 하는 단위 수를 지정 하는 `CRect` [RECT](/windows/win32/api/windef/ns-windef-rect) 구조체를 가리킵니다.

*l*<br/>
`CRect`의 왼쪽을 수축 하는 단위 수를 지정 합니다.

*t*<br/>
`CRect`의 맨 위를 수축 하는 단위 수를 지정 합니다.

*r*<br/>
`CRect`의 오른쪽을 수축 하는 단위 수를 지정 합니다.

*b*<br/>
`CRect`의 아래쪽을 수축 하는 단위 수를 지정 합니다.

### <a name="remarks"></a>주의

이렇게 하려면 `DeflateRect` 왼쪽 및 위쪽에 단위를 추가 하 고 오른쪽 및 아래쪽에서 단위를 뺍니다. `DeflateRect` 매개 변수는 부호 있는 값입니다. 양수 값 수축 `CRect` 및 음수 값은이를 확장 합니다.

처음 두 오버 로드는 `CRect`의 반대쪽 쌍을 모두 조정 하 여 전체 너비가 *x* (또는 `cx`) 두 번 감소 하 고 총 높이가 *y* (또는 `cy`)로 감소 합니다. 다른 두 오버 로드는 다른 두 오버 로드는 `CRect`의 양쪽에 독립적으로 deflate.

### <a name="example"></a>예

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

##  <a name="equalrect"></a>  CRect::EqualRect

`CRect` 지정 된 사각형과 같은지 여부를 확인 합니다.

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>매개 변수

*lpRect*<br/>
사각형의 왼쪽 위와 오른쪽 아래 모퉁이 좌표를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 `CRect`개체를 가리킵니다.

### <a name="return-value"></a>반환 값

두 사각형의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값이 같으면 0이 아닌 값입니다. 그렇지 않으면 0입니다.

> [!NOTE]
>  두 사각형 모두 정규화 되어야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

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

##  <a name="height"></a>  CRect::Height

맨 아래 값에서 상위 값을 빼서 `CRect`의 높이를 계산 합니다.

```
int Height() const throw();
```

### <a name="return-value"></a>반환 값

`CRect`높이입니다.

### <a name="remarks"></a>주의

결과 값은 음수일 수 있습니다.

> [!NOTE]
>  사각형을 정규화 해야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

// nHt is now 40
ASSERT(nHt == 40);
```

##  <a name="inflaterect"></a>  CRect::InflateRect

늘어납니다 `CRect`를 중심에서 멀리 이동 하 여 `InflateRect` 합니다.

```
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
`CRect`의 왼쪽과 오른쪽을 확장할 단위 수를 지정 합니다.

*y*<br/>
`CRect`의 위쪽과 아래쪽을 확장할 단위 수를 지정 합니다.

*size*<br/>
`CRect`확장할 단위 수를 지정 하는 [크기](/windows/win32/api/windef/ns-windef-size) 또는 [csize](csize-class.md) 입니다. `cx` 값은 왼쪽과 오른쪽을 확장할 단위 수를 지정 하 고 `cy` 값은 위쪽 및 아래쪽을 확장할 단위 수를 지정 합니다.

*lpRect*<br/>
각 면을 확장할 단위 수를 지정 하는 `CRect` [RECT](/windows/win32/api/windef/ns-windef-rect) 구조체를 가리킵니다.

*l*<br/>
`CRect`의 왼쪽을 확장할 단위 수를 지정 합니다.

*t*<br/>
`CRect`의 맨 위를 확장할 단위 수를 지정 합니다.

*r*<br/>
`CRect`우변을 확장할 단위 수를 지정 합니다.

*b*<br/>
`CRect`의 아래쪽을 확장할 단위 수를 지정 합니다.

### <a name="remarks"></a>주의

이렇게 하려면 왼쪽 및 위쪽에서 단위를 빼고 오른쪽 및 아래쪽에 단위를 추가 `InflateRect` 합니다. `InflateRect` 매개 변수는 부호 있는 값입니다. 양수 값은 `CRect`를 확장 하 고 음수 값은이를 수축 합니다.

처음 두 오버 로드는 `CRect`의 반대쪽 쌍을 모두 확장 하 여 총 너비가 *x* (또는 `cx`) 두 번 증가 하 고 총 높이가 *y* (또는 `cy`)로 증가 합니다. 다른 두 오버 로드는 다른 두 오버 로드는 `CRect`의 양쪽에 독립적으로 확장 됩니다.

### <a name="example"></a>예

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

##  <a name="intersectrect"></a>  CRect::IntersectRect

두 개의 기존 사각형이 교차 하는 것과 같은 `CRect`를 만듭니다.

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>매개 변수

*lpRect1*<br/>
소스 사각형을 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 `CRect` 개체를 가리킵니다.

*lpRect2*<br/>
소스 사각형을 포함 하는 `RECT` 구조체 또는 `CRect` 개체를 가리킵니다.

### <a name="return-value"></a>반환 값

교집합이 비어 있지 않으면 0이 아닙니다. 교집합이 비어 있으면 0입니다.

### <a name="remarks"></a>주의

교집합은 기존 사각형에 모두 포함 된 가장 큰 사각형입니다.

> [!NOTE]
>  두 사각형 모두 정규화 되어야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

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

##  <a name="isrectempty"></a>  CRect::IsRectEmpty

`CRect` 비어 있는지 여부를 확인 합니다.

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>반환 값

`CRect` 비어 있으면 0이 아닙니다. `CRect` 비어 있지 않으면 0입니다.

### <a name="remarks"></a>주의

너비 및/또는 높이가 0 또는 음수인 경우 사각형은 비어 있습니다. 는 사각형의 모든 좌표가 0 인지 여부를 결정 하는 `IsRectNull`와 다릅니다.

> [!NOTE]
>  사각형을 정규화 해야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
ASSERT(rectEmpty.IsRectEmpty());
```

##  <a name="isrectnull"></a>  CRect::IsRectNull

`CRect`의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값이 모두 0과 같은지 여부를 결정 합니다.

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>반환 값

`CRect`의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값이 모두 0 이면 0이 아닌 값입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>주의

사각형이 비어 있는지 여부를 결정 하는 `IsRectEmpty`와 다릅니다.

### <a name="example"></a>예

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
ASSERT(!rectSome.IsRectNull());
// note that null means _all_ zeros

CRect rectNotNull(0, 0, 35, 50);
ASSERT(!rectNotNull.IsRectNull());
```

##  <a name="movetox"></a>  CRect::MoveToX

사각형을 *x*로 지정 된 절대 x 좌표로 이동 하려면이 함수를 호출 합니다.

```
void MoveToX(int x) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
사각형의 왼쪽 위 모퉁이에 대 한 절대 x 좌표입니다.

### <a name="example"></a>예

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

// rect is now (10, 0, 110, 100);
ASSERT(rect == CRect(10, 0, 110, 100));
```

##  <a name="movetoxy"></a>  CRect::MoveToXY

사각형을 지정 된 절대 x 및 y 좌표로 이동 하려면이 함수를 호출 합니다.

```
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
사각형의 왼쪽 위 모퉁이에 대 한 절대 x 좌표입니다.

*y*<br/>
사각형의 왼쪽 위 모퉁이에 대 한 절대 y 좌표입니다.

*point*<br/>
사각형의 왼쪽 위 모퉁이를 지정 하는 `POINT` 구조체입니다.

### <a name="example"></a>예

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
ASSERT(rect == CRect(10, 10, 110, 110));
```

##  <a name="movetoy"></a>  CRect::MoveToY

사각형을 *y*로 지정 된 절대 y 좌표로 이동 하려면이 함수를 호출 합니다.

```
void MoveToY(int y) throw();
```

### <a name="parameters"></a>매개 변수

*y*<br/>
사각형의 왼쪽 위 모퉁이에 대 한 절대 y 좌표입니다.

### <a name="example"></a>예

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
ASSERT(rect == CRect(0, 10, 100, 110));
```

##  <a name="normalizerect"></a>  CRect::NormalizeRect

높이와 너비가 모두 양수인 `CRect` 정규화 합니다.

```
void NormalizeRect() throw();
```

### <a name="remarks"></a>주의

사각형은 Windows에서 일반적으로 좌표에 사용 하는 네 번째 사분면 위치에 대해 정규화 됩니다. `NormalizeRect`는 위쪽 및 아래쪽 값을 비교 하 고 위쪽이 아래쪽 보다 크면 바꿉니다. 마찬가지로 왼쪽이 오른쪽 보다 큰 경우 왼쪽 및 오른쪽 값을 바꿉니다. 이 함수는 다양 한 매핑 모드와 반전 된 사각형을 처리할 때 유용 합니다.

> [!NOTE]
> 다음 `CRect` 멤버 함수는 정상적으로 작동 하기 위해 정규화 된 사각형이 필요 합니다. [Height](#height), [Width](#width), [Size](#size), [isrectempty](#isrectempty), [ptinrect](#ptinrect), [EqualRect](#equalrect), [UnionRect](#unionrect), [IntersectRect](#intersectrect), [SubtractRect](#subtractrect), [operator = =](#operator_eq_eq), [operator! =](#operator_neq), [연산자 &#124; ](#operator_or), [operator &#124;=](#operator_or_eq), [operator &](#operator_amp)및 [operator & =](#operator_amp_eq)입니다.

### <a name="example"></a>예제

```cpp
CRect rect1(110, 100, 250, 310);
CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
rect2.NormalizeRect();
ASSERT(rect1 == rect2);
```

##  <a name="offsetrect"></a>  CRect::OffsetRect

지정 된 오프셋으로 `CRect` 이동 합니다.

```
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
왼쪽 또는 오른쪽으로 이동할 크기를 지정 합니다. 왼쪽으로 이동 하려면 음수 여야 합니다.

*y*<br/>
위나 아래로 이동할 크기를 지정 합니다. 위로 이동 하려면 음수 여야 합니다.

*point*<br/>
이동할 두 차원을 모두 지정 하는 [점](/windows/win32/api/windef/ns-windef-point) 구조 또는 [cpoint](cpoint-class.md) 개체를 포함 합니다.

*size*<br/>
이동할 크기를 모두 지정 하는 [크기](/windows/win32/api/windef/ns-windef-size) 구조 또는 [csize](csize-class.md) 개체를 포함 합니다.

### <a name="remarks"></a>주의

X 축과 y 축을 따라 x 축과 *y* 단위를 따라 `CRect`*x* 단위를 이동 합니다. *X* 및 *y* 매개 변수는 부호 있는 값 이므로 `CRect` 왼쪽 이나 오른쪽 및 위쪽/아래쪽으로 이동할 수 있습니다.

### <a name="example"></a>예

```cpp
CRect rect(0, 0, 35, 35);
rect.OffsetRect(230, 230);

// rect is now (230, 230, 265, 265)
ASSERT(rect == CRect(230, 230, 265, 265));
```

##  <a name="operator_lpcrect"></a>CRect:: operator LPCRECT `CRect`을 [Lpcrect](../../mfc/reference/data-types-mfc.md)로 변환 합니다.

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>주의

이 함수를 사용 하는 경우 주소 ( **&** ) 연산자가 필요 하지 않습니다. 이 연산자는 `LPCRECT`를 기대 하는 함수에 `CRect` 개체를 전달할 때 자동으로 사용 됩니다.

##  <a name="operator_lprect"></a>  CRect::operator LPRECT

`CRect`를 [LPRECT](../../mfc/reference/data-types-mfc.md)변환 합니다.

```
operator LPRECT() throw();
```

### <a name="remarks"></a>주의

이 함수를 사용 하는 경우 주소 ( **&** ) 연산자가 필요 하지 않습니다. 이 연산자는 `LPRECT`를 기대 하는 함수에 `CRect` 개체를 전달할 때 자동으로 사용 됩니다.

### <a name="example"></a>예

[Crect:: operator LPCRECT](#operator_lpcrect)의 예제를 참조 하세요.

##  <a name="operator_eq"></a>  CRect::operator =

`CRect`에 *srcRect* 를 할당 합니다.

```
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>매개 변수

*srcRect*<br/>
소스 사각형을 참조 합니다. 는 [RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`일 수 있습니다.

### <a name="example"></a>예

```cpp
CRect rect(0, 0, 127, 168);
CRect rect2;

rect2 = rect;
ASSERT(rect2 == CRect(0, 0, 127, 168));
```

##  <a name="operator_eq_eq"></a>  CRect::operator ==

왼쪽 위 모퉁이와 오른쪽 아래 모퉁이의 좌표를 비교 하 여 `rect` `CRect` 같은지 여부를 확인 합니다.

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
소스 사각형을 참조 합니다. 는 [RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`일 수 있습니다.

### <a name="return-value"></a>반환 값

같으면 0이 아닌 것입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>주의

> [!NOTE]
>  두 사각형 모두 정규화 되어야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

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

##  <a name="operator_neq"></a>  CRect::operator !=

*Rect* 가 왼쪽 위 모퉁이와 오른쪽 아래 모퉁이의 좌표를 비교 하 여 `CRect`와 같지 않은지 여부를 확인 합니다.

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
소스 사각형을 참조 합니다. 는 [RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`일 수 있습니다.

### <a name="return-value"></a>반환 값

같지 않으면 0이 아닙니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>주의

> [!NOTE]
>  두 사각형 모두 정규화 되어야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

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

##  <a name="operator_add_eq"></a>  CRect::operator +=

처음 두 오버 로드는 지정 된 오프셋으로 `CRect` 이동 합니다.

```
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
사각형을 이동할 단위 수를 지정 하는 [점](/windows/win32/api/windef/ns-windef-point) 구조 또는 [cpoint](cpoint-class.md) 개체입니다.

*size*<br/>
사각형을 이동할 단위 수를 지정 하는 [크기](/windows/win32/api/windef/ns-windef-size) 구조체 또는 [csize](csize-class.md) 개체입니다.

*lpRect*<br/>
각 측면을 확장할 단위 수를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조체 또는 `CRect`개체를 가리킵니다.

### <a name="remarks"></a>주의

매개 변수의 *x* 및 *y* (또는 `cx` 및 `cy`) 값이 `CRect`에 추가 됩니다.

세 번째 오버 로드는 매개 변수의 각 멤버에 지정 된 단위 수 만큼 `CRect` 늘어납니다.

### <a name="example"></a>예

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint  pt(35, 65);
CRect   rect2(135, 300, 235, 400);

rect1 += pt;
ASSERT(rect1 == rect2);
```

##  <a name="operator_-_eq"></a>  CRect::operator -=

처음 두 오버 로드는 지정 된 오프셋으로 `CRect` 이동 합니다.

```
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
사각형을 이동할 단위 수를 지정 하는 [점](/windows/win32/api/windef/ns-windef-point) 구조 또는 [cpoint](cpoint-class.md) 개체입니다.

*size*<br/>
사각형을 이동할 단위 수를 지정 하는 [크기](/windows/win32/api/windef/ns-windef-size) 구조체 또는 [csize](csize-class.md) 개체입니다.

*lpRect*<br/>
각 측면을 수축하는 단위 수를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조체 또는 `CRect` 개체를 가리킵니다.

### <a name="remarks"></a>주의

매개 변수의 *x* 및 *y* (또는 `cx` 및 `cy`) 값을 `CRect`에서 뺍니다.

세 번째 오버 로드는 매개 변수의 각 멤버에 지정 된 단위 수 만큼 `CRect` 수축. 이 오버 로드는 [DeflateRect](#deflaterect)와 같은 기능을 합니다.

### <a name="example"></a>예

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);

rect1 -= pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect1 == rectResult);
```

##  <a name="operator_amp_eq"></a>  CRect::operator &amp;=

`CRect`와 `rect`의 교집합에 `CRect`을 설정 합니다.

```
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
에는 [RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`포함 됩니다.

### <a name="remarks"></a>주의

교차는 두 사각형에 모두 포함 된 가장 큰 사각형입니다.

> [!NOTE]
>  두 사각형 모두 정규화 되어야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

[Crect:: IntersectRect](#intersectrect)에 대 한 예제를 참조 하세요.

##  <a name="operator_or_eq"></a>CRect:: operator &#124;=

`CRect`와 `rect`의 합집합 `CRect` 같도록 설정 합니다.

```
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
`CRect` 또는 [RECT](/windows/win32/api/windef/ns-windef-rect)를 포함합니다.

### <a name="remarks"></a>주의

합집합은 두 소스 사각형을 모두 포함 하는 가장 작은 사각형입니다.

> [!NOTE]
>  두 사각형 모두 정규화 되어야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);

rect1 |= rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect1);
```

##  <a name="operator_add"></a>  CRect::operator +

처음 두 오버 로드는 지정 된 오프셋으로 치환 `CRect` 같은 `CRect` 개체를 반환 합니다.

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
반환 값을 이동할 단위 수를 지정 하는 [점](/windows/win32/api/windef/ns-windef-point) 구조 또는 [cpoint](cpoint-class.md) 개체입니다.

*size*<br/>
반환 값을 이동할 단위 수를 지정 하는 [크기](/windows/win32/api/windef/ns-windef-size) 구조체 또는 [csize](csize-class.md) 개체입니다.

*lpRect*<br/>
반환 값의 각 면을 확장할 단위 수를 포함 하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 `CRect` 개체를 가리킵니다.

### <a name="return-value"></a>반환 값

`CRect` 이동 하거나 않아서 `CRect` 매개 변수에 지정 된 단위 수 만큼 이동 하는 것입니다.

### <a name="remarks"></a>주의

매개 변수의 *x* 및 *y* (또는 `cx` 및 `cy`) 매개 변수가 `CRect`의 위치에 추가 됩니다.

세 번째 오버 로드는 매개 변수의 각 멤버에 지정 된 단위 수 만큼 `CRect` 팽창 같은 새 `CRect`을 반환 합니다.

### <a name="example"></a>예

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 + pt;
CRect   rectResult(135, 300, 235, 400);
ASSERT(rectResult == rect2);
```

##  <a name="operator_-"></a>  CRect::operator -

처음 두 오버 로드는 지정 된 오프셋으로 치환 `CRect` 같은 `CRect` 개체를 반환 합니다.

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
반환 값을 이동할 단위 수를 지정하는 [점](/windows/win32/api/windef/ns-windef-point) 구조 또는 `CPoint` 개체입니다.

*size*<br/>
반환 값을 이동할 단위 수를 지정하는 [크기](/windows/win32/api/windef/ns-windef-size) 구조체 또는 `CSize` 개체입니다.

*lpRect*<br/>
반환 값의 각 측면을 수축하는 단위 수를 포함 하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조체 또는 `CRect` 개체를 가리킵니다.

### <a name="return-value"></a>반환 값

`CRect` 이동 하거나 deflating `CRect` 매개 변수에 지정 된 단위 수 만큼 이동 하는 것입니다.

### <a name="remarks"></a>주의

매개 변수의 *x* 및 *y* (또는 `cx` 및 `cy`) 매개 변수를 `CRect`의 위치에서 뺍니다.

세 번째 오버 로드는 매개 변수의 각 멤버에 지정 된 단위 수 만큼 `CRect` deflated 같은 새 `CRect`을 반환 합니다. 이 오버 로드는 [SubtractRect](#subtractrect)가 아닌 [DeflateRect](#deflaterect)처럼 작동 합니다.

### <a name="example"></a>예

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 - pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect2 == rectResult);
```

##  <a name="operator_amp"></a>  CRect::operator &amp;

`CRect`와 *rect2*의 교집합에 해당 하는 `CRect`를 반환 합니다.

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>매개 변수

*rect2*<br/>
에는 [RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`포함 됩니다.

### <a name="return-value"></a>반환 값

`CRect`와 *rect2*의 교집합에 해당 하는 `CRect`입니다.

### <a name="remarks"></a>주의

교차는 두 사각형에 모두 포함 된 가장 큰 사각형입니다.

> [!NOTE]
>  두 사각형 모두 정규화 되어야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 & rect2;
CRect   rectResult(100, 100, 200, 200);
ASSERT(rectResult == rect3);
```

##  <a name="operator_or"></a>  CRect::operator &#124;

`CRect` 및 *rect2*의 합집합에 해당 하는 `CRect`를 반환 합니다.

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>매개 변수

*rect2*<br/>
에는 [RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`포함 됩니다.

### <a name="return-value"></a>반환 값

`CRect` 및 *rect2*의 합집합 인 `CRect`입니다.

### <a name="remarks"></a>주의

Union은 두 사각형을 모두 포함 하는 가장 작은 사각형입니다.

> [!NOTE]
>  두 사각형 모두 정규화 되어야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 | rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

##  <a name="ptinrect"></a>  CRect::PtInRect

지정 된 지점이 `CRect`내에 있는지 여부를 확인 합니다.

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
[점](/windows/win32/api/windef/ns-windef-point) 구조 또는 [cpoint](cpoint-class.md) 개체를 포함 합니다.

### <a name="return-value"></a>반환 값

요소가 `CRect`내에 있으면 0이 아닌 값입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>주의

점이 왼쪽 또는 위쪽에 있거나 네 면 모두에 있는 경우 `CRect` 내에 있습니다. 오른쪽 또는 아래쪽의 점이 `CRect`외부에 있습니다.

> [!NOTE]
>  사각형을 정규화 해야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

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

##  <a name="setrect"></a>  CRect::SetRect

`CRect`의 차원을 지정 된 좌표로 설정 합니다.

```
void SetRect(int x1, int y1, int x2, int y2) throw();
```

### <a name="parameters"></a>매개 변수

*x1*<br/>
왼쪽 위 모퉁이의 x 좌표를 지정 합니다.

*y1*<br/>
왼쪽 위 모퉁이의 y 좌표를 지정 합니다.

*x2*<br/>
오른쪽 아래 모퉁이의 x 좌표를 지정 합니다.

*y2*<br/>
오른쪽 아래 모퉁이의 y 좌표를 지정 합니다.

### <a name="example"></a>예

```cpp
CRect rect;
rect.SetRect(256, 256, 512, 512);
ASSERT(rect == CRect(256, 256, 512, 512));
```

##  <a name="setrectempty"></a>  CRect::SetRectEmpty

모든 좌표를 0으로 설정 하 여 null 사각형을 `CRect` 만듭니다.

```
void SetRectEmpty() throw();
```

### <a name="example"></a>예

```cpp
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());
```

##  <a name="size"></a>  CRect::SIZE

반환 값의 `cx` 및 `cy` 멤버는 `CRect`의 높이와 너비를 포함 합니다.

```
CSize Size() const throw();
```

### <a name="return-value"></a>반환 값

`CRect`의 크기를 포함 하는 [Csize](csize-class.md) 개체입니다.

### <a name="remarks"></a>주의

높이나 너비는 음수일 수 있습니다.

> [!NOTE]
>  사각형을 정규화 해야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

##  <a name="subtractrect"></a>  CRect::SubtractRect

`CRect`의 차원을 `lpRectSrc1`에서의 `lpRectSrc2` 뺄셈과 같도록 만듭니다.

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>매개 변수

*lpRectSrc1*<br/>
사각형을 뺄 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 `CRect` 개체를 가리킵니다.

*lpRectSrc2*<br/>
*LpRectSrc1* 매개 변수가 가리키는 사각형에서 뺄 `RECT` 구조체 또는 `CRect` 개체를 가리킵니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>주의

빼기는 *lpRectScr1* 및 *lpRectScr2*의 교집합에 속하지 않은 *lpRectScr1* 의 모든 요소를 포함 하는 가장 작은 사각형입니다.

*LpRectSrc2* 에 의해 지정 된 사각형이 x 또는 y 방향 중 하나 이상에서 *lpRectSrc1* 에 의해 지정 된 사각형과 완전히 겹치면 *lpRectSrc1* 에 의해 지정 된 사각형이 변경 되지 않습니다.

예를 들어 *lpRectSrc1* 가 (10, 10, 100100)이 고 *lpRectSrc2* 가 (50, 50, 150150) 인 경우 함수가 반환 될 때 *lpRectSrc1* 가 가리키는 사각형은 변경 되지 않습니다. 그러나 *lpRectSrc1* 가 (10, 10, 100100)이 고 *lpRectSrc2* 가 (50, 10, 150150) 인 경우 함수가 반환 될 때 *lpRectSrc1* 가 가리키는 사각형에 좌표 (10, 10, 50100)가 포함 됩니다.

`SubtractRect` [연산자](#operator_-) 또는 [연산자-=](#operator_-_eq)와 같지 않습니다. 이러한 연산자는 `SubtractRect`호출 하지 않습니다.

> [!NOTE]
>  두 사각형 모두 정규화 되어야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

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

##  <a name="topleft"></a>  CRect::TopLeft

좌표는 `CRect`포함 된 [Cpoint](cpoint-class.md) 개체에 대 한 참조로 반환 됩니다.

```
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw();
```

### <a name="return-value"></a>반환 값

사각형의 왼쪽 위 모퉁이에 대 한 좌표입니다.

### <a name="remarks"></a>주의

이 함수를 사용 하 여 사각형의 왼쪽 위 모퉁이를 가져오거나 설정할 수 있습니다. 할당 연산자의 왼쪽에서이 함수를 사용 하 여 모퉁이를 설정 합니다.

### <a name="example"></a>예

[Crect:: CenterPoint](#centerpoint)에 대 한 예제를 참조 하세요.

##  <a name="unionrect"></a>  CRect::UnionRect

`CRect`의 크기를 두 소스 사각형의 합집합과 동일 하 게 만듭니다.

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>매개 변수

*lpRect1*<br/>
소스 사각형을 포함 하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 또는 `CRect`을 가리킵니다.

*lpRect2*<br/>
소스 사각형을 포함 하는 `RECT` 또는 `CRect`를 가리킵니다.

### <a name="return-value"></a>반환 값

Union이 비어 있지 않으면 0이 아닙니다. 합집합이 비어 있으면 0입니다.

### <a name="remarks"></a>주의

합집합은 두 소스 사각형을 모두 포함 하는 가장 작은 사각형입니다.

Windows에서는 빈 사각형의 크기를 무시 합니다. 즉, 높이가 없거나 너비가 없는 사각형입니다.

> [!NOTE]
>  두 사각형 모두 정규화 되어야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3.UnionRect(&rect1, &rect2);
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

##  <a name="width"></a>  CRect::Width

오른쪽 값에서 왼쪽 값을 빼서 `CRect`의 너비를 계산 합니다.

```
int Width() const throw();
```

### <a name="return-value"></a>반환 값

`CRect`의 너비입니다.

### <a name="remarks"></a>주의

너비는 음수일 수 있습니다.

> [!NOTE]
>  사각형을 정규화 해야 합니다. 그렇지 않으면이 함수가 실패할 수 있습니다. 이 함수를 호출 하기 전에 [NormalizeRect](#normalizerect) 를 호출 하 여 사각형을 정규화 할 수 있습니다.

### <a name="example"></a>예

```cpp
CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
// nWid is now 60
ASSERT(nWid == 60);
```

## <a name="see-also"></a>참조

[CPoint 클래스](cpoint-class.md)<br/>
[CSize 클래스](csize-class.md)<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)
