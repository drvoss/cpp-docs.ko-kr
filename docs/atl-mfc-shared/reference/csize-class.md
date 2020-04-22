---
title: C사이즈 클래스
ms.date: 10/18/2018
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
ms.openlocfilehash: dc876781cca568a332072938bec2cda0afb2ac8b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746965"
---
# <a name="csize-class"></a>C사이즈 클래스

상대 좌표 또는 위치를 구현하는 Windows [SIZE](/windows/win32/api/windef/ns-windef-size) 구조체와 유사합니다.

## <a name="syntax"></a>구문

```
class CSize : public tagSIZE
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C사이즈::C사이즈](#csize)|`CSize` 개체를 생성합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C크기::연산자 -](#operator_-)|두 가지 크기를 뺍니다.|
|[C크기::연산자 !=](#operator_neq)|크기와 사이의 `CSize` 부등가를 확인합니다.|
|[C크기::연산자 +](#operator_add)|두 가지 크기를 추가합니다.|
|[C크기::연산자 +=](#operator_add_eq)|에 크기를 `CSize`추가합니다.|
|[CSize::operator -=](#operator_-_eq)|에서 크기를 `CSize`뺍니다.|
|[C크기::연산자 ==](#operator_eq_eq)|크기와 의 `CSize` 같음이 맞는지 확인합니다.|

## <a name="remarks"></a>설명

이 클래스는 구조에서 `SIZE` 파생됩니다. `CSize` 즉, 을 `SIZE` 호출하는 매개 변수에 전달할 수 있으며 `SIZE` 구조의 데이터 멤버가 `CSize`에 액세스할 수 있는 데이터 멤버임을 의미합니다.

`cx` 및 `cy` `SIZE` (및)의 `CSize`구성원은 공개됩니다. 또한 구조를 `CSize` 조작하는 멤버 함수를 `SIZE` 구현합니다.

> [!NOTE]
> 공유 유틸리티 클래스(예) `CSize`자세한 내용은 공유 [클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagSIZE`

`CSize`

## <a name="requirements"></a>요구 사항

**헤더:** atltypes.h

## <a name="csizecsize"></a><a name="csize"></a>C사이즈::C사이즈

`CSize` 개체를 생성합니다.

```
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw();
```

### <a name="parameters"></a>매개 변수

*initCX*<br/>
에 `cx` 대한 멤버를 설정합니다. `CSize`

*initCY*<br/>
에 `cy` 대한 멤버를 설정합니다. `CSize`

*initSize*<br/>
`CSize`를 초기화하는 데 사용되는 [크기](/windows/win32/api/windef/ns-windef-size) 구조 또는 `CSize`개체입니다.

*initPt*<br/>
`CSize`를 초기화 하는 데 사용되는 [요소](/windows/win32/api/windef/ns-windef-point) 구조 또는 `CPoint`개체입니다.

*dwSize*<br/>
DWORD를 초기화하는 `CSize`데 사용됩니다. 낮은 순서의 단어는 `cx` 멤버이고 높은 순서의 단어는 `cy` 멤버입니다.

### <a name="remarks"></a>설명

인수가 지정되지 `cx` 않고 `cy` 0으로 초기화되는 경우.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

## <a name="csizeoperator-"></a><a name="operator_eq_eq"></a>C크기::연산자 ==

두 크기 간의 같음이 확인됩니다.

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>설명

크기가 같으면 0이 아닌 것을 반환하고 0을 다시 시작합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

## <a name="csizeoperator-"></a><a name="operator_neq"></a>C크기::연산자 !=

두 크기 간의 부등가를 확인합니다.

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>설명

크기가 같지 않은 경우 0이 아닌 경우 0이 아닌 경우 0이 아닌 것을 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add_eq"></a>C크기::연산자 +=

이 `CSize`에 크기를 추가합니다.

```cpp
void operator+=(SIZE size) throw();
```

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-_eq"></a>C크기::연산자 -=

이 `CSize`것에서 크기를 뺍니다.

```cpp
void operator-=(SIZE size) throw();
```

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add"></a>C크기::연산자 +

이러한 연산자는 `CSize` 이 값을 매개 변수 값에 추가합니다.

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>설명

개별 연산자의 다음 설명을 참조하십시오.

- **연산자** *+(크기)* **)**

  이 작업은 `CSize` 두 개의 값을 추가합니다.

- **operator +(** *point* **)**

  이 작업은 이 `CSize` 값으로 [POINT(또는](/windows/win32/api/windef/ns-windef-point) [CPoint)](../../atl-mfc-shared/reference/cpoint-class.md)값을 오프셋(이동)합니다. 이 `cx` `CSize` `cy` 값의 멤버와 는 `x` 값의 및 `y` `POINT` 데이터 멤버에 추가됩니다. [SIZE](/windows/win32/api/windef/ns-windef-size) 매개 변수를 취하는 [CPoint::operator +의](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) 버전과 유사합니다.

- **연산자** *+(lpRect)* **)**

   이 작업은 이 `CSize` 값으로 [RECT(또는](/windows/win32/api/windef/ns-windef-rect) [CRect)](../../atl-mfc-shared/reference/crect-class.md)값을 오프셋(이동)합니다. 이 `cx` `CSize` `cy` 값의 및 멤버는 `left` `RECT` 값의 `right`" `bottom` 및 `top`데이터 멤버에 추가됩니다. [SIZE](/windows/win32/api/windef/ns-windef-size) 매개 변수를 취하는 [CRect::operator +의](../../atl-mfc-shared/reference/crect-class.md#operator_add) 버전과 유사합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-"></a>C크기::연산자 -

이러한 연산자 중 처음 `CSize` 세 개는 이 값을 매개 변수 값으로 뺍니다.

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>설명

네 번째 연산자인 unary 빼기는 `CSize` 값의 부호를 변경합니다. 개별 연산자의 다음 설명을 참조하십시오.

- **연산자 -(** *크기)* **)**

  이 작업은 두 `CSize` 값을 뺍니다.

- **연산자** *-(점)* **)**

  이 작업은 이 `CSize` 값의 가산 역으로 [POINT](/windows/win32/api/windef/ns-windef-point) 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 값을 오프셋(이동)합니다. 이 `cx` `cy` 값의 `CSize` 및 값의 및 `x` `y` 값의 `POINT` 데이터 멤버에서 뺍니다. [SIZE](/windows/win32/api/windef/ns-windef-size) 매개 변수를 취하는 [CPoint::operator](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) 버전과 유사합니다.

- **operator -(** *lpRect* **)**

  이 작업은 이 `CSize` 값의 가산 역으로 [RECT](/windows/win32/api/windef/ns-windef-rect) 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 값을 오프셋(이동)합니다. 이 `cx` `CSize` `cy` 값의 및 멤버는 `RECT` 값의 `left` `top`" `right`및 `bottom` 데이터 멤버에서 뺍니다. [SIZE](/windows/win32/api/windef/ns-windef-size) 매개 변수를 취하는 [CRect::operator](../../atl-mfc-shared/reference/crect-class.md#operator_-) 버전과 유사합니다.

- **연산자 -()**

  이 작업은 이 값의 가산 `CSize` 역반전을 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[트렉트 클래스](../../atl-mfc-shared/reference/crect-class.md)<br/>
[C포인트 클래스](../../atl-mfc-shared/reference/cpoint-class.md)
