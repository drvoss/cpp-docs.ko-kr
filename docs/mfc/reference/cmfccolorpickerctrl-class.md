---
title: CMFC컬러피커Ctrl 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SelectCellHexagon
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminanceBarWidth
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetOriginalColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetPalette
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetType
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::DrawCursor
helpviewer_keywords:
- CMFCColorPickerCtrl [MFC], CMFCColorPickerCtrl
- CMFCColorPickerCtrl [MFC], GetColor
- CMFCColorPickerCtrl [MFC], GetHLS
- CMFCColorPickerCtrl [MFC], GetHue
- CMFCColorPickerCtrl [MFC], GetLuminance
- CMFCColorPickerCtrl [MFC], GetSaturation
- CMFCColorPickerCtrl [MFC], SelectCellHexagon
- CMFCColorPickerCtrl [MFC], SetColor
- CMFCColorPickerCtrl [MFC], SetHLS
- CMFCColorPickerCtrl [MFC], SetHue
- CMFCColorPickerCtrl [MFC], SetLuminance
- CMFCColorPickerCtrl [MFC], SetLuminanceBarWidth
- CMFCColorPickerCtrl [MFC], SetOriginalColor
- CMFCColorPickerCtrl [MFC], SetPalette
- CMFCColorPickerCtrl [MFC], SetSaturation
- CMFCColorPickerCtrl [MFC], SetType
- CMFCColorPickerCtrl [MFC], DrawCursor
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
ms.openlocfilehash: fe35ee5d6fc6484788a2636151c386689f4bdd96
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752529"
---
# <a name="cmfccolorpickerctrl-class"></a>CMFC컬러피커Ctrl 클래스

클래스는 `CMFCColorPickerCtrl` 색상을 선택하는 데 사용되는 컨트롤에 대한 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CMFCColorPickerCtrl : public CButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC컬러피커Ctrl::CMFC컬러피커Ctrl](#cmfccolorpickerctrl)|`CMFCColorPickerCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC컬러피커Ctrl::겟컬러](#getcolor)|사용자가 선택한 색상을 검색합니다.|
|[CMFC컬러피커Ctrl::GetHLS](#gethls)|사용자가 선택한 색상의 색조, 휘도 및 채도 값을 검색합니다.|
|[CMFC컬러피커Ctrl::겟휴](#gethue)|사용자가 선택한 색상의 색조 구성 요소를 검색합니다.|
|[CMFC컬러피커Ctrl::GetLuminance](#getluminance)|사용자가 선택한 색상의 휘도 구성 요소를 검색합니다.|
|[CMFCColor피커Ctrl::GetSaturation](#getsaturation)|사용자가 선택한 색상의 채도 구성 요소를 검색합니다.|
|[CMFC컬러피커Ctrl::셀렉트셀헥사곤](#selectcellhexagon)|현재 색상을 지정된 RGB 색상 구성 요소 또는 지정된 셀 육각형에 의해 정의된 색상으로 설정합니다.|
|[CMFC컬러피커Ctrl::세트컬러](#setcolor)|현재 색상을 지정된 RGB 색상 값으로 설정합니다.|
|[CMFC컬러피커Ctrl::SetHLS](#sethls)|현재 색상을 지정된 HLS 색상 값으로 설정합니다.|
|[CMFC컬러피커Ctrl::세휴](#sethue)|현재 선택한 색상의 색조 구성요소를 변경합니다.|
|[CMFC컬러피커Ctrl::세트루우티](#setluminance)|현재 선택한 색상의 휘도 구성 요소를 변경합니다.|
|[CMFCColor피커Ctrl::세트루노피폭](#setluminancebarwidth)|색상 선택기 컨트롤에서 휘도 막대의 너비를 설정합니다.|
|[CMFC컬러피커Ctrl::세트 오리지널컬러](#setoriginalcolor)|선택한 초기 색상을 설정합니다.|
|[CMFC컬러피커Ctrl::세팔레트](#setpalette)|현재 색상 팔레트를 설정합니다.|
|[CMFCColor피커Ctrl::설정](#setsaturation)|현재 선택한 색상의 채도 구성 요소를 변경합니다.|
|[CMFC컬러피커Ctrl::세트타입](#settype)|표시할 색상 선택기 컨트롤의 유형을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC컬러피커Ctrl::D로커서](#drawcursor)|선택한 색상을 가리키는 커서가 표시되기 전에 프레임워크에서 호출됩니다.|

## <a name="remarks"></a>설명

표준 색상은 육각형 색상 표에서 선택되며 사용자 지정 색상은 빨간색/녹색/파란색 표기또는 색조/조정/휘도 표기색을 사용하여 색상이 지정된 휘도 막대에서 선택됩니다.

다음 그림에서는 여러 `CMFCColorPickerCtrl` 개체를 묘사합니다.

![CMFCColorPickerCtrl 대화 상자](../../mfc/reference/media/colorpicker.png "CMFCColorPickerCtrl 대화 상자")

는 `CMFCColorPickerCtrl` 두 쌍의 스타일을 지원합니다. HEX 및 HEX_GREYSCALE 스타일은 표준 색상 선택에 적합합니다. PICKER 및 휘도 스타일은 사용자 지정 색상 선택에 적합합니다.

다음 단계를 수행하여 대화 `CMFCColorPickerCtrl` 상자에 컨트롤을 통합합니다.

1. **ClassWizard를**사용하는 경우 `CMFCColorPickerCtrl` 클래스가 클래스에서 상속되므로 대화 상자 템플릿에 새 단추 `CButton` 컨트롤을 삽입합니다.

1. 새 단추 컨트롤과 연결된 멤버 변수를 대화 상자 클래스에 삽입합니다. 그런 다음 변수 `CButton` 형식을 `CMFCColorPickerCtrl`에서 로 변경합니다.

1. 대화 `WM_INITDIALOG` 상자 클래스에 대한 메시지 처리기를 삽입합니다. 처리기에서 `CMFCColorPickerCtrl` 컨트롤의 유형, 팔레트 및 초기 선택된 색상을 설정합니다.

## <a name="example"></a>예제

다음 예제에서는 클래스에서 다양 `CMFCColorPickerCtrl` 한 메서드를 사용 `CMFCColorPickerCtrl` 하 여 개체를 구성 하는 방법을 보여 줍니다. 이 예제에서는 선택기 컨트롤의 형식을 설정하는 방법과 색상, 색조, 휘도 및 채도를 설정하는 방법을 보여 줍니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxcolorpickerctrl.h

## <a name="cmfccolorpickerctrlcmfccolorpickerctrl"></a><a name="cmfccolorpickerctrl"></a>CMFC컬러피커Ctrl::CMFC컬러피커Ctrl

`CMFCColorPickerCtrl` 개체를 생성합니다.

```
CMFCColorPickerCtrl();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfccolorpickerctrldrawcursor"></a><a name="drawcursor"></a>CMFC컬러피커Ctrl::D로커서

선택한 색상을 가리키는 커서가 표시되기 전에 프레임워크에서 호출됩니다.

```
virtual void DrawCursor(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 선택한 색상 주위의 직사각형 영역을 지정합니다.

### <a name="remarks"></a>설명

선택한 색상을 가리키는 커서의 모양을 변경해야 하는 경우 이 메서드를 재정의합니다.

## <a name="cmfccolorpickerctrlgetcolor"></a><a name="getcolor"></a>CMFC컬러피커Ctrl::겟컬러

사용자가 선택한 색상을 검색합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Return Value

선택한 색상의 RGB 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorpickerctrlgethls"></a><a name="gethls"></a>CMFC컬러피커Ctrl::GetHLS

사용자가 선택한 색상의 색조, 휘도 및 채도 값을 검색합니다.

```cpp
void GetHLS(
    double* hue,
    double* luminance,
    double* saturation);
```

### <a name="parameters"></a>매개 변수

*색조*<br/>
【아웃】 색조 정보를 받는 double 형식의 변수에 대한 포인터입니다.

*광도*<br/>
【아웃】 휘도 정보를 수신하는 이중 형식의 변수에 대한 포인터입니다.

*채도*<br/>
【아웃】 포화 정보를 받는 double 형식의 변수에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorpickerctrlgethue"></a><a name="gethue"></a>CMFC컬러피커Ctrl::겟휴

사용자가 선택한 색상의 색조 구성 요소를 검색합니다.

```
double GetHue() const;
```

### <a name="return-value"></a>Return Value

선택한 색상의 색조 구성 요소입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorpickerctrlgetluminance"></a><a name="getluminance"></a>CMFC컬러피커Ctrl::GetLuminance

사용자가 선택한 색상의 휘도 구성 요소를 검색합니다.

```
double GetLuminance() const;
```

### <a name="return-value"></a>Return Value

선택한 색상의 휘도 구성 요소입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorpickerctrlgetsaturation"></a><a name="getsaturation"></a>CMFCColor피커Ctrl::GetSaturation

사용자가 선택한 색상의 채도 값을 검색합니다.

```
double GetSaturation() const;
```

### <a name="return-value"></a>Return Value

선택한 색상의 채도 구성 요소입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorpickerctrlselectcellhexagon"></a><a name="selectcellhexagon"></a>CMFC컬러피커Ctrl::셀렉트셀헥사곤

현재 색상을 지정된 RGB 색상 구성 요소 또는 지정된 셀 육각형에 의해 정의된 색상으로 설정합니다.

```cpp
void SelectCellHexagon(
    BYTE R,
    BYTE G,
    BYTE B);

BOOL SelectCellHexagon(
    int x,
    int y);
```

### <a name="parameters"></a>매개 변수

*R*<br/>
【인】 빨간색 구성 요소입니다.

*G*<br/>
【인】 녹색 색상 구성 요소입니다.

*B*<br/>
【인】 파란색 구성 요소입니다.

*x*<br/>
【인】 셀 육각형을 가리키는 커서의 x 좌표입니다.

*Y*<br/>
【인】 셀 육각형을 가리키는 커서의 y 좌표입니다.

### <a name="return-value"></a>Return Value

이 메서드의 두 번째 오버로드는 항상 FALSE를 반환합니다.

### <a name="remarks"></a>설명

이 메서드의 첫 번째 오버로드는 색상 선택 컨트롤의 지정된 빨간색, 녹색 및 파란색 색상 구성 요소에 해당하는 색상으로 현재 색상을 설정합니다.

이 메서드의 두 번째 오버로드는 현재 색상을 지정된 커서 위치로 가리키는 셀 육각형의 색상으로 설정합니다.

## <a name="cmfccolorpickerctrlsetcolor"></a><a name="setcolor"></a>CMFC컬러피커Ctrl::세트컬러

현재 색상을 지정된 RGB 색상 값으로 설정합니다.

```cpp
void SetColor(COLORREF Color);
```

### <a name="parameters"></a>매개 변수

*Color*<br/>
【인】 RGB 색상 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorpickerctrlsethls"></a><a name="sethls"></a>CMFC컬러피커Ctrl::SetHLS

현재 색상을 지정된 HLS 색상 값으로 설정합니다.

```cpp
void SetHLS(
    double hue,
    double luminance,
    double saturation,
    BOOL bInvalidate=TRUE);
```

### <a name="parameters"></a>매개 변수

*색조*<br/>
【인】 색조 값입니다.

*광도*<br/>
【인】 휘도 값입니다.

*채도*<br/>
【인】 포화 값입니다.

*b 무효화*<br/>
【인】 TRUE는 창을 강제로 강제로 새 색상으로 즉시 업데이트합니다. 그렇지 않으면 false입니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorpickerctrlsethue"></a><a name="sethue"></a>CMFC컬러피커Ctrl::세휴

현재 선택한 색상의 색조가 변경됩니다.

```cpp
void SetHue(double Hue);
```

### <a name="parameters"></a>매개 변수

*Hue*<br/>
【인】 색조 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorpickerctrlsetluminance"></a><a name="setluminance"></a>CMFC컬러피커Ctrl::세트루우티

현재 선택한 색상의 휘도가 변경됩니다.

```cpp
void SetLuminance(double Luminance);
```

### <a name="parameters"></a>매개 변수

*광도*<br/>
【인】 휘도 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorpickerctrlsetluminancebarwidth"></a><a name="setluminancebarwidth"></a>CMFCColor피커Ctrl::세트루노피폭

색상 선택기 컨트롤에서 휘도 막대의 너비를 설정합니다.

```cpp
void SetLuminanceBarWidth(int w);
```

### <a name="parameters"></a>매개 변수

*w*<br/>
【인】 픽셀단위로 측정된 휘도 막대의 너비입니다.

### <a name="remarks"></a>설명

색상 선택기 컨트롤의 **사용자 지정** 탭에 있는 휘도 막대의 크기를 조정하려면 이 메서드를 사용합니다. *w* 매개변수는 휘도 막대의 새 너비를 지정합니다. 너비 값은 클라이언트 영역 너비의 3/4를 초과하면 무시됩니다.

## <a name="cmfccolorpickerctrlsetoriginalcolor"></a><a name="setoriginalcolor"></a>CMFC컬러피커Ctrl::세트 오리지널컬러

선택한 초기 색상을 설정합니다.

```cpp
void SetOriginalColor(COLORREF ref);
```

### <a name="parameters"></a>매개 변수

*ref*<br/>
【인】 RGB 색상 값입니다.

### <a name="remarks"></a>설명

색상 선택기 컨트롤이 초기화될 때 이 메서드를 호출합니다.

## <a name="cmfccolorpickerctrlsetpalette"></a><a name="setpalette"></a>CMFC컬러피커Ctrl::세팔레트

현재 색상 팔레트를 설정합니다.

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>매개 변수

*pPalette*<br/>
【인】 색상 팔레트에 대한 포인터입니다.

### <a name="remarks"></a>설명

색상 팔레트는 색상 선택기 컨트롤에 표시되는 색상 배열을 정의합니다.

## <a name="cmfccolorpickerctrlsetsaturation"></a><a name="setsaturation"></a>CMFCColor피커Ctrl::설정

현재 선택한 색상의 채도를 변경합니다.

```cpp
void SetSaturation(double Saturation);
```

### <a name="parameters"></a>매개 변수

*채도*<br/>
【인】 포화 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfccolorpickerctrlsettype"></a><a name="settype"></a>CMFC컬러피커Ctrl::세트타입

표시할 색상 선택기 컨트롤의 유형을 설정합니다.

```cpp
void SetType(COLORTYPE colorType);
```

### <a name="parameters"></a>매개 변수

*색상 유형*<br/>
【인】 색상 선택기 컨트롤 유형입니다.

형식은 열거형에 `CMFCColorPickerCtrl::COLORTYPE` 의해 정의됩니다. 가능한 유형은 휘도, 피커, 헥스 및 HEX_GREYSCALE. 기본 유형은 PICKER입니다.

### <a name="remarks"></a>설명

색상 선택기 컨트롤 유형을 지정하려면 Windows 컨트롤을 생성하기 전에 이 메서드를 호출합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC컬러디아로그 클래스](../../mfc/reference/cmfccolordialog-class.md)
