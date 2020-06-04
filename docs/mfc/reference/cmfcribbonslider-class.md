---
title: CMFC리본슬라이더 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMax
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMin
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRegularSize
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetZoomIncrement
- AFXRIBBONSLIDER/CMFCRibbonSlider::HasZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::OnDraw
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetRange
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomIncrement
helpviewer_keywords:
- CMFCRibbonSlider [MFC], CMFCRibbonSlider
- CMFCRibbonSlider [MFC], GetPos
- CMFCRibbonSlider [MFC], GetRangeMax
- CMFCRibbonSlider [MFC], GetRangeMin
- CMFCRibbonSlider [MFC], GetRegularSize
- CMFCRibbonSlider [MFC], GetZoomIncrement
- CMFCRibbonSlider [MFC], HasZoomButtons
- CMFCRibbonSlider [MFC], OnDraw
- CMFCRibbonSlider [MFC], SetPos
- CMFCRibbonSlider [MFC], SetRange
- CMFCRibbonSlider [MFC], SetZoomButtons
- CMFCRibbonSlider [MFC], SetZoomIncrement
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
ms.openlocfilehash: 304581371c68817c6031153c3cec227137771c5d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754066"
---
# <a name="cmfcribbonslider-class"></a>CMFC리본슬라이더 클래스

클래스는 `CMFCRibbonSlider` 리본 막대 또는 리본 상태 표시줄에 추가할 수 있는 슬라이더 컨트롤을 구현합니다. 리본 슬라이더 컨트롤은 Office 2007 애플리케이션의 확대/축소 슬라이더와 유사합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonSlider : public CMFCRibbonBaseElement
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC리본 슬라이더::CMFC리본 슬라이더](#cmfcribbonslider)|리본 슬라이더 컨트롤을 생성하고 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC리본 슬라이더::GetPos](#getpos)|슬라이더 컨트롤의 현재 위치를 반환합니다.|
|[CMFC리본 슬라이더::겟레인지맥스](#getrangemax)|슬라이더의 최대값을 반환합니다.|
|[CMFC리본 슬라이더::겟레인지민](#getrangemin)|슬라이더의 최소값을 반환합니다.|
|[CMFC 리본 슬라이더 :: GetRegularsize](#getregularsize)|리본 요소의 보통 크기를 반환합니다. [(CMFC 리본베이스 요소 재정의::GetRegularSize.)](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)|
|[CMFC리본 슬라이더::GetZoomIncrement](#getzoomincrement)|슬라이더 컨트롤에 대 한 확대 의 크기를 반환 합니다.|
|[CMFC리본 슬라이더::하스줌 버튼](#haszoombuttons)|슬라이더에 확대/축소 버튼이 있는지 여부를 지정합니다.|
|[CMFC 리본 슬라이더::온드로우](#ondraw)|리본 요소를 그리기 위해 프레임워크에서 호출됩니다. [(CMFC 리본베이스 요소 재정의::온드로우.)](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw)|
|[CMFC 리본 슬라이더::세트포지](#setpos)|슬라이더 컨트롤의 현재 위치를 설정합니다.|
|[CMFC리본 슬라이더::세트 레인지](#setrange)|최소 값과 최대값을 설정하여 슬라이더 컨트롤의 범위를 지정합니다.|
|[CMFC리본 슬라이더::설정 확대 단추](#setzoombuttons)|확대/축소 단추를 표시하거나 숨깁니다.|
|[CMFC리본 슬라이더::설정 확대](#setzoomincrement)|슬라이더 컨트롤에 대한 확대 크기를 설정합니다.|

## <a name="remarks"></a>설명

이 메서드를 `SetRange` 사용하여 슬라이더의 확대 확대 범위를 구성할 수 있습니다. `SetPos` 메서드를 사용하여 슬라이더의 현재 위치를 설정할 수 있습니다.

이 방법을 사용하여 슬라이더 컨트롤의 왼쪽과 오른쪽에 원형 확대/축소 단추를 `SetZoomButtons` 표시할 수 있습니다. 기본적으로 슬라이더는 수평이고 왼쪽 확대/축소 버튼은 마이너스 기호를 표시하고 오른쪽 확대/축소 버튼에는 더하기 기호가 표시됩니다.

이 `SetZoomIncrement` 메서드는 사용자가 확대/축소 단추를 클릭할 때 현재 위치에 추가하거나 빼는 증분을 정의합니다.

## <a name="example"></a>예제

다음 예제에서는 클래스에서 다양 한 `CMFCRibbonSlider` 메서드를 사용 하 여 슬라이더의 속성을 설정 하는 방법을 보여 줍니다. 이 예제에서는 `CMFCRibbonSlider` 객체를 생성하고, 확대/축소 단추를 표시하고, 슬라이더 컨트롤의 현재 위치를 설정하고, 슬라이더 컨트롤의 값 범위를 설정하는 방법을 보여 주었습니다.

[!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribbonslider.h

## <a name="cmfcribbonslidercmfcribbonslider"></a><a name="cmfcribbonslider"></a>CMFC리본 슬라이더::CMFC리본 슬라이더

리본 슬라이더를 생성합니다.

```
CMFCRibbonSlider(
    UINT nID,
    int nWidth=100);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 슬라이더 ID.

[에서]. *n 너비* 슬라이더 너비(픽셀 단위)입니다.

### <a name="remarks"></a>설명

슬라이더가 추가되는 패널 범주에서 *너비가 큰 nWidth* 픽셀인 리본 슬라이더를 구성합니다. 기본적으로 슬라이더는 수평입니다.

## <a name="cmfcribbonslidergetpos"></a><a name="getpos"></a>CMFC리본 슬라이더::GetPos

슬라이더 컨트롤의 현재 위치를 반환합니다.

```
int GetPos() const;
```

### <a name="return-value"></a>Return Value

슬라이더 컨트롤의 현재 위치(슬라이더의 시작 부분에 대한 위치)입니다.

## <a name="cmfcribbonslidergetrangemax"></a><a name="getrangemax"></a>CMFC리본 슬라이더::겟레인지맥스

슬라이더가 슬라이더 컨트롤에서 이동할 수 있는 슬라이더의 최대 증분을 가져옵니다.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Return Value

슬라이더가 슬라이더 컨트롤에서 이동할 수 있는 슬라이더의 최대 증분입니다.

## <a name="cmfcribbonslidergetrangemin"></a><a name="getrangemin"></a>CMFC리본 슬라이더::겟레인지민

슬라이더가 슬라이더 컨트롤에서 이동할 수 있는 최소 증분을 반환합니다.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Return Value

슬라이더가 슬라이더 컨트롤에서 이동할 수 있는 최소 증분입니다.

## <a name="cmfcribbonslidergetregularsize"></a><a name="getregularsize"></a>CMFC 리본 슬라이더 :: GetRegularsize

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonslidergetzoomincrement"></a><a name="getzoomincrement"></a>CMFC리본 슬라이더::GetZoomIncrement

슬라이더 컨트롤의 확대/축소를 가져옵니다.

```
int GetZoomIncrement() const;
```

### <a name="return-value"></a>Return Value

슬라이더 컨트롤의 확대/축소입니다.

## <a name="cmfcribbonsliderhaszoombuttons"></a><a name="haszoombuttons"></a>CMFC리본 슬라이더::하스줌 버튼

슬라이더에 확대/축소 버튼이 있는지 여부를 지정합니다.

```
BOOL HasZoomButtons() const;
```

### <a name="return-value"></a>Return Value

슬라이더에 확대/축소 버튼이 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cmfcribbonsliderondraw"></a><a name="ondraw"></a>CMFC 리본 슬라이더::온드로우

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcribbonslidersetpos"></a><a name="setpos"></a>CMFC 리본 슬라이더::세트포지

슬라이더 컨트롤의 현재 위치를 설정합니다.

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
【인】 슬라이더에 대해 설정할 위치를 지정합니다. 위치는 슬라이더의 시작 부분을 기준으로 합니다.

*bRedraw*<br/>
【인】 TRUE이면 슬라이더가 다시 그려집니다.

## <a name="cmfcribbonslidersetrange"></a><a name="setrange"></a>CMFC리본 슬라이더::세트 레인지

슬라이더 컨트롤의 값 범위를 설정합니다.

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
【인】 슬라이더 컨트롤의 최소 값을 지정합니다.

*nMax*<br/>
【인】 슬라이더 컨트롤의 최대값을 지정합니다.

### <a name="remarks"></a>설명

최소 값과 최대 값을 설정하여 슬라이더 컨트롤의 값 범위를 지정합니다.

## <a name="cmfcribbonslidersetzoombuttons"></a><a name="setzoombuttons"></a>CMFC리본 슬라이더::설정 확대 단추

확대/축소 단추를 표시하거나 숨깁니다.

```cpp
void SetZoomButtons(BOOL bSet=TRUE);
```

### <a name="parameters"></a>매개 변수

[에서]. *bSet* TRUE는 확대/축소 버튼을 표시합니다. 그들을 숨기기 위해 거짓.

## <a name="cmfcribbonslidersetzoomincrement"></a><a name="setzoomincrement"></a>CMFC리본 슬라이더::설정 확대

슬라이더 컨트롤의 확대/축소를 설정합니다.

```cpp
void SetZoomIncrement(int nZoomIncrement);
```

### <a name="parameters"></a>매개 변수

*nZoomIncrement*<br/>
【인】 슬라이더 컨트롤의 확대/축소를 지정합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본베이스요소 클래스](../../mfc/reference/cmfcribbonbaseelement-class.md)
