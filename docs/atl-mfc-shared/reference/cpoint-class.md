---
title: C포인트 클래스
ms.date: 11/04/2016
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
ms.openlocfilehash: 331b89ff118f727303e887670960ee6078b01fb1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747091"
---
# <a name="cpoint-class"></a>C포인트 클래스

Windows `POINT` 구조체와 유사합니다.

## <a name="syntax"></a>구문

```
class CPoint : public tagPOINT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C포인트::C포인트](#cpoint)|`CPoint`를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C포인트::오프셋](#offset)|및 의 멤버에 값을 추가합니다. `CPoint` `x` `y`|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C포인트::연산자 -](#operator_-)|a와 `CPoint` 크기의 차이 또는 점의 부정 또는 두 점 간의 크기 차이 또는 음수 크기로 오프셋을 반환합니다.|
|[C포인트::연산자!=](#operator_neq)|두 점 사이의 부등가를 확인합니다.|
|[C포인트::연산자 +](#operator_add)|a와 `CPoint` 크기 또는 점의 합계 또는 `CRect` 크기에 따라 오프셋을 반환합니다.|
|[C포인트::연산자 +=](#operator_add_eq)|`CPoint` 크기 또는 점을 추가하여 간격띄우기합니다.|
|[C포인트::연산자 -=](#operator_-_eq)|`CPoint` 크기 또는 점을 빼서 간격띄우기합니다.|
|[C포인트::연산자 ==](#operator_eq_eq)|두 점 간의 같음을 확인합니다.|

## <a name="remarks"></a>설명

또한 조작하는 멤버 `CPoint` 함수와 [POINT](/windows/win32/api/windef/ns-windef-point) 구조도 포함됩니다.

구조체가 `CPoint` 사용되는 모든 `POINT` 곳에서 개체를 사용할 수 있습니다. "크기"와 상호 작용하는 이 클래스의 연산자는 두 개체를 서로 교환할 수 있기 때문에 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체 또는 [SIZE](/windows/win32/api/windef/ns-windef-size) 구조를 허용합니다.

> [!NOTE]
> 이 클래스는 구조에서 `tagPOINT` 파생됩니다. (이름은 `tagPOINT` 구조에 대해 덜 일반적으로 `POINT` 사용되는 이름입니다.) 즉, `POINT` `x` 구조의 데이터 멤버 및 `y`의 데이터 멤버에 액세스할 수 `CPoint`있습니다.

> [!NOTE]
> 공유 유틸리티 클래스(예) `CPoint`자세한 내용은 공유 [클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagPOINT`

`CPoint`

## <a name="requirements"></a>요구 사항

**헤더:** atltypes.h

## <a name="cpointcpoint"></a><a name="cpoint"></a>C포인트::C포인트

`CPoint` 개체를 생성합니다.

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>매개 변수

*인트 X*<br/>
`x`의 `CPoint` 멤버 값을 지정합니다.

*이니티 (주)*<br/>
`y`의 `CPoint` 멤버 값을 지정합니다.

*initPt*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point) 구조 `CPoint` 또는 초기화에 사용되는 값을 `CPoint`지정합니다.

*initSize*<br/>
[초기화하는](/windows/win32/api/windef/ns-windef-size) `CPoint`데 사용되는 값을 지정하는 SIZE 구조 또는 [CSize입니다.](../../atl-mfc-shared/reference/csize-class.md)

*dw포인트*<br/>
dwPoint의 `y` 하위 순서 단어와 멤버를 *dwPoint의* 높은 순서 단어로 설정합니다. *dwPoint* `x`

### <a name="remarks"></a>설명

인수가 지정되지 않으면 `x` 및 `y` 멤버가 0으로 설정됩니다.

### <a name="example"></a>예제

```cpp
CPoint   ptTopLeft(0, 0);
// works from a POINT, too

POINT   ptHere;
ptHere.x = 35;
ptHere.y = 95;

CPoint   ptMFCHere(ptHere);

// works from a SIZE
SIZE   sHowBig;
sHowBig.cx = 300;
sHowBig.cy = 10;

CPoint ptMFCBig(sHowBig);
// or from a DWORD

DWORD   dwSize;
dwSize = MAKELONG(35, 95);

CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```

## <a name="cpointoffset"></a><a name="offset"></a>C포인트::오프셋

및 의 멤버에 값을 추가합니다. `CPoint` `x` `y`

```cpp
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>매개 변수

*x오프셋*<br/>
`CPoint`의 `x` 멤버를 오프셋할 금액을 지정합니다.

*y오프셋*<br/>
`CPoint`의 `y` 멤버를 오프셋할 금액을 지정합니다.

*지점*<br/>
을 오프셋할 [양(POINT](/windows/win32/api/windef/ns-windef-point) 또는)을 `CPoint`지정합니다. `CPoint`

*size*<br/>
을 오프셋할 [양(크기](/windows/win32/api/windef/ns-windef-size) 또는 [CSize)을](../../atl-mfc-shared/reference/csize-class.md)지정합니다. `CPoint`

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

## <a name="cpointoperator-"></a><a name="operator_eq_eq"></a>C포인트::연산자 ==

두 점 간의 같음을 확인합니다.

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point) 구조 또는 `CPoint` 개체를 포함합니다.

### <a name="return-value"></a>Return Value

포인트가 같으면 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

## <a name="cpointoperator-"></a><a name="operator_neq"></a>C포인트::연산자!=

두 점 사이의 부등가를 확인합니다.

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point) 구조 또는 `CPoint` 개체를 포함합니다.

### <a name="return-value"></a>Return Value

포인트가 같지 않은 경우 0이 아님을 말합니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add_eq"></a>C포인트::연산자 +=

첫 번째 오버로드는 `CPoint`에 크기를 추가합니다.

```cpp
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>매개 변수

*size*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체를 포함합니다.

*지점*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체를 포함합니다.

### <a name="remarks"></a>설명

두 번째 오버로드는 `CPoint`에 대한 점을 추가합니다.

두 경우 모두, 추가는 `x` 오른쪽 `cx`의 `x` 부재에 (또는) 오른손 지각의 `CPoint` 부재를 `y` 추가하고 `cy`의 `y` 부재에 (또는) 부재를 추가하여 `CPoint`수행된다.

예를 들어, `CPoint(5, -7)` 변수를 포함하는 `CPoint(30, 40)` 변수에 `CPoint(35, 33)`추가하면 변수를 에 변경합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-_eq"></a>C포인트::연산자 -=

첫 번째 오버로드는 `CPoint`에서 크기를 뺍니다.

```cpp
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>매개 변수

*size*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체를 포함합니다.

*지점*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체를 포함합니다.

### <a name="remarks"></a>설명

두 번째 오버로드는 `CPoint`에서 점을 뺍니다.

두 경우 모두, 빼기는 오른쪽 `x` 의 `cx`부재로부터 `x` 오른쪽 의 (또는) 부재를 `CPoint` 빼고 의 `y` `cy` `y` 부재로부터 우측 심각부(or)의 부재를 빼는 방식으로 `CPoint`수행된다.

예를 들어, 포함된 `CPoint(5, -7)` `CPoint(30, 40)` 변수에서 빼면 변수가 `CPoint(25, 47)`로 변경됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add"></a>C포인트::연산자 +

이 `CPoint` 연산자를 `CPoint` 사용하여 `CSize` 또는 개체로 `CRect` 오프셋하거나 `CPoint`를 에 의해 오프셋합니다.

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>매개 변수

*size*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체를 포함합니다.

*지점*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체를 포함합니다.

*Lprect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체에 대한 포인터를 포함합니다.

### <a name="return-value"></a>Return Value

크기로 오프셋되는 `CPoint` A, `CPoint` 점으로 오프셋되는 a `CRect` 또는 점에 의한 오프셋입니다.

### <a name="remarks"></a>설명

예를 들어 처음 두 오버로드 중 하나를 `CPoint(25, -19)` 사용하여 점 `CPoint(15, 5)` 또는 `CSize(15, 5)` 크기로 `CPoint(40, -14)`점을 오프셋하면 값이 반환됩니다.

점에 사각형을 추가하면 점에 지정된 `x` 값으로 `y` 오프셋된 후 사각형이 반환됩니다. 예를 들어 마지막 오버로드를 사용하여 사각형을 `CRect(125, 219, 325, 419)` 포인트로 `CPoint(25, -19)` `CRect(150, 200, 350, 400)`오프셋하면 반환됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-"></a>C포인트::연산자 -

처음 두 오버로드 중 하나를 사용하여 `CPoint` `CSize` `CPoint`에서 또는 개체를 뺍니다.

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.

*size*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.

*Lprect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

A는 `CSize` 두 점의 차이, `CPoint` 크기의 부정에 의해 오프셋되는 `CRect` a, 점의 부정에 의해 오프셋되는 a 또는 `CPoint` 점의 부정입니다.

### <a name="remarks"></a>설명

세 번째 오버로드는 `CRect` `CPoint`의 부정에 의해 오프셋됩니다. 마지막으로 unary 연산자를 `CPoint`사용하여 무효화합니다.

예를 들어 첫 번째 오버로드를 사용하여 두 `CPoint(25, -19)` `CPoint(15, 5)` 점과 반환 `CSize(10, -24)`사이의 차이를 찾습니다.

에서 `CSize` `CPoint` 를 빼면 위와 동일한 계산을 `CPoint` 수행하지만 개체가 아닌 객체를 반환합니다. `CSize` 예를 들어 두 번째 오버로드를 사용하여 점과 `CPoint(25, -19)` 크기 `CSize(15, 5)` `CPoint(10, -24)`간의 차이를 찾을 수 있습니다.

점에서 사각형을 빼면 점에 지정된 `x` 값과 `y` 음수로 직사각형 오프셋이 반환됩니다. 예를 들어 마지막 오버로드를 사용하여 점반환에 `CRect(125, 200, 325, 400)` `CPoint(25, -19)` 의해 `CRect(100, 219, 300, 419)`사각형을 오프셋합니다.

unary 연산자에서 점을 부정합니다. 예를 들어 포인트가 `CPoint(25, -19)` 있는 unary `CPoint(-25, 19)`연산자 사용이 반환됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[포인트 구조](/windows/win32/api/windef/ns-windef-point)<br/>
[트렉트 클래스](../../atl-mfc-shared/reference/crect-class.md)<br/>
[C사이즈 클래스](../../atl-mfc-shared/reference/csize-class.md)
