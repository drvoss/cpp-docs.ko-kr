---
title: C그리기 관리자 클래스
ms.date: 11/04/2016
f1_keywords:
- CDrawingManager
- AFXDRAWMANAGER/CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CreateBitmap_32
- AFXDRAWMANAGER/CDrawingManager::DrawAlpha
- AFXDRAWMANAGER/CDrawingManager::DrawRotated
- AFXDRAWMANAGER/CDrawingManager::DrawEllipse
- AFXDRAWMANAGER/CDrawingManager::DrawGradientRing
- AFXDRAWMANAGER/CDrawingManager::DrawRect
- AFXDRAWMANAGER/CDrawingManager::DrawShadow
- AFXDRAWMANAGER/CDrawingManager::Fill4ColorsGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient2
- AFXDRAWMANAGER/CDrawingManager::GrayRect
- AFXDRAWMANAGER/CDrawingManager::HighlightRect
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_ONE
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_TWO
- AFXDRAWMANAGER/CDrawingManager::HSVtoRGB
- AFXDRAWMANAGER/CDrawingManager::HuetoRGB
- AFXDRAWMANAGER/CDrawingManager::MirrorRect
- AFXDRAWMANAGER/CDrawingManager::PixelAlpha
- AFXDRAWMANAGER/CDrawingManager::PrepareShadowMask
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSL
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSV
- AFXDRAWMANAGER/CDrawingManager::SetAlphaPixel
- AFXDRAWMANAGER/CDrawingManager::SetPixel
- AFXDRAWMANAGER/CDrawingManager::SmartMixColors
helpviewer_keywords:
- CDrawingManager [MFC], CDrawingManager
- CDrawingManager [MFC], CreateBitmap_32
- CDrawingManager [MFC], DrawAlpha
- CDrawingManager [MFC], DrawRotated
- CDrawingManager [MFC], DrawEllipse
- CDrawingManager [MFC], DrawGradientRing
- CDrawingManager [MFC], DrawRect
- CDrawingManager [MFC], DrawShadow
- CDrawingManager [MFC], Fill4ColorsGradient
- CDrawingManager [MFC], FillGradient
- CDrawingManager [MFC], FillGradient2
- CDrawingManager [MFC], GrayRect
- CDrawingManager [MFC], HighlightRect
- CDrawingManager [MFC], HLStoRGB_ONE
- CDrawingManager [MFC], HLStoRGB_TWO
- CDrawingManager [MFC], HSVtoRGB
- CDrawingManager [MFC], HuetoRGB
- CDrawingManager [MFC], MirrorRect
- CDrawingManager [MFC], PixelAlpha
- CDrawingManager [MFC], PrepareShadowMask
- CDrawingManager [MFC], RGBtoHSL
- CDrawingManager [MFC], RGBtoHSV
- CDrawingManager [MFC], SetAlphaPixel
- CDrawingManager [MFC], SetPixel
- CDrawingManager [MFC], SmartMixColors
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
ms.openlocfilehash: 73c5775c2cb83dea79401615b31f2194094fac8e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753230"
---
# <a name="cdrawingmanager-class"></a>C그리기 관리자 클래스

클래스는 `CDrawingManager` 복잡한 그리기 알고리즘을 구현합니다.

## <a name="syntax"></a>구문

```
class CDrawingManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C그리기 관리자::C그리기 관리자](#cdrawingmanager)|`CDrawingManager` 개체를 생성합니다.|
|`CDrawingManager::~CDrawingManager`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C그리기 관리자::CreateBitmap_32](#createbitmap_32)|응용 프로그램이 직접 쓸 수 있는 32비트 장치 독립 비트맵(DIB)을 만듭니다.|
|[C그리기 관리자::D로알파](#drawalpha)|투명 또는 반투명 픽셀이 있는 비트맵을 표시합니다.|
|[C그리기 관리자::D회전](#drawrotated)|지정된 사각형 내부의 소스 DC 콘텐츠를 +/- 90도 회전|
|[C그리기 관리자::D로엘립스](#drawellipse)|제공된 채우기 및 테두리 색상으로 타원을 그립니다.|
|[C그리기 관리자::D로그라데이션링](#drawgradientring)|링을 그리고 색상 그라데이션으로 채웁니다.|
|[C그리기 관리자::DrawLine, CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|선을 그립니다.|
|[C그리기 관리자::D로렉트](#drawrect)|제공된 채우기 및 테두리 색상이 있는 사각형을 그립니다.|
|[C그리기 관리자::D로그림자](#drawshadow)|직사각형 영역에 대한 그림자를 그립니다.|
|[C그리기 관리자::채우기4색상그라데이션](#fill4colorsgradient)|직사각형 영역을 두 개의 색상 그라데이션으로 채웁니다.|
|[C그리기 관리자::필그라데이션](#fillgradient)|지정된 색상 그라데이션으로 직사각형 영역을 채웁니다.|
|[C그리기 관리자::필그라디언트2](#fillgradient2)|지정된 색상 그라데이션으로 직사각형 영역을 채웁니다. 그라데이션의 색상 변경 방향도 지정됩니다.|
|[C그리기 관리자::그레이렉트](#grayrect)|사각형을 지정된 회색으로 채웁니다.|
|[C그리기 관리자::하이라이트](#highlightrect)|직사각형 영역을 강조 표시됩니다.|
|[C그리기 관리자::HLStoRGB_ONE](#hlstorgb_one)|HLS 표현에서 RGB 표현으로 색상을 변환합니다.|
|[C그리기 관리자::HLStoRGB_TWO](#hlstorgb_two)|HLS 표현에서 RGB 표현으로 색상을 변환합니다.|
|[C그리기 관리자::HSVtoRGB](#hsvtorgb)|HSV 표현에서 RGB 표현으로 색상을 변환합니다.|
|[C드로잉 매니저::휴토RGB](#huetorgb)|색조 값을 빨간색, 녹색 또는 파란색 구성 요소로 변환하는 도우미 메서드입니다.|
|[C그리기 관리자::미러렉트](#mirrorrect)|직사각형 영역을 뒤집습니다.|
|[C그리기 관리자::P익셀알파](#pixelalpha)|반투명 픽셀의 최종 색상을 결정하는 도우미 방법입니다.|
|[C그리기 관리자::P레파레섀도우 마스크](#prepareshadowmask)|그림자로 사용할 수 있는 비트맵을 만듭니다.|
|[C그리기 관리자::RGBtoHSL](#rgbtohsl)|RGB 표현에서 HSL 표현으로 색상을 변환합니다.|
|[C그리기 관리자::RGBtoHSV](#rgbtohsv)|RGB 표현에서 HSV 표현으로 색상을 변환합니다.|
|[C그리기 관리자::설정알파픽셀](#setalphapixel)|비트맵에서 부분적으로 투명한 픽셀을 채색하는 도우미 방법입니다.|
|[C그리기 관리자::설정 픽셀](#setpixel)|비트맵의 단일 픽셀을 지정된 색상으로 변경하는 도우미 메서드입니다.|
|[C그리기 관리자::스마트 믹스 컬러](#smartmixcolors)|가중 비율에 따라 두 가지 색상을 결합합니다.|

## <a name="remarks"></a>설명

클래스는 `CDrawingManager` 그림자, 색상 그라데이션 및 강조 표시된 사각형을 그리는 함수를 제공합니다. 또한 알파 블렌딩을 수행합니다. 이 클래스를 사용하여 응용 프로그램의 UI를 직접 변경할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)<br/>
`CDrawingManager`

## <a name="requirements"></a>요구 사항

**헤더:** afxdrawmanager.h

## <a name="cdrawingmanagercdrawingmanager"></a><a name="cdrawingmanager"></a>C그리기 관리자::C그리기 관리자

[CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) 개체를 생성합니다.

```
CDrawingManager(CDC& dc);
```

### <a name="parameters"></a>매개 변수

*Dc*<br/>
【인】 장치 컨텍스트에 대한 참조입니다. 는 `CDrawingManager` 드로잉에 이 컨텍스트를 사용합니다.

## <a name="cdrawingmanagercreatebitmap_32"></a><a name="createbitmap_32"></a>C그리기 관리자::CreateBitmap_32

응용 프로그램이 직접 쓸 수 있는 32비트 장치 독립 비트맵(DIB)을 만듭니다.

```
static HBITMAP __stdcall CreateBitmap_32(
    const CSize& size,
    void** pBits);

static HBITMAP __stdcall CreateBitmap_32(
    HBITMAP bitmap,
    COLORREF clrTransparent = -1);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*size*|【인】 비트맵의 크기를 나타내는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 매개 변수입니다.|
|*비트*|【아웃】 DIB의 비트 값의 위치를 수신하는 데이터 포인터에 대한 포인터입니다.|
|*비트맵*|원래 비트맵에 대한 핸들|
|*clr투명*|원래 비트맵의 투명한 색상을 지정하는 RGB 값입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 새로 만든 DIB 비트맵에 대한 핸들입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

DIB 비트맵을 만드는 방법에 대한 자세한 내용은 [CreateDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibitmap)을 참조하십시오.

## <a name="cdrawingmanagerdrawalpha"></a><a name="drawalpha"></a>C그리기 관리자::D로알파

투명 또는 반투명 픽셀이 있는 비트맵을 표시합니다.

```cpp
void DrawAlpha(
    CDC* pDstDC,
    const CRect& rectDst,
    CDC* pSrcDC,
    const CRect& rectSrc);
```

### <a name="parameters"></a>매개 변수

*pDstDC*<br/>
【인】 대상에 대한 장치 컨텍스트에 대한 포인터입니다.

*정류자*<br/>
【인】 대상 사각형입니다.

*pSrcDC*<br/>
【인】 원본에 대한 장치 컨텍스트에 대한 포인터입니다.

*rectSrc*<br/>
【인】 소스 사각형입니다.

### <a name="remarks"></a>설명

이 메서드는 두 비트 맵에 대해 알파 블렌딩을 수행합니다. 알파 블렌딩에 대한 자세한 내용은 Windows SDK의 [AlphaBlend를](/windows/win32/api/wingdi/nf-wingdi-alphablend) 참조하십시오.

## <a name="cdrawingmanagerdrawellipse"></a><a name="drawellipse"></a>C그리기 관리자::D로엘립스

제공된 채우기 및 테두리 색상으로 타원을 그립니다.

```cpp
void DrawEllipse(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 타원의 경계 사각형입니다.

*clrFill*<br/>
【인】 이 메서드는 타원을 채우는 데 사용하는 색상입니다.

*클라인*<br/>
【인】 이 메서드가 타원의 테두리로 사용하는 색상입니다.

### <a name="remarks"></a>설명

이 메서드는 두 색상 중 하나가 -1로 설정된 경우 타원을 그리지 않고 반환합니다. 또한 경계 사각형의 치수가 0인 경우 타원을 그리지 않고 반환됩니다.

## <a name="cdrawingmanagerdrawgradientring"></a><a name="drawgradientring"></a>C그리기 관리자::D로그라데이션링

링을 그리고 색상 그라데이션으로 채웁니다.

```
BOOL DrawGradientRing(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    COLORREF colorBorder,
    int nAngle,
    int nWidth,
    COLORREF clrFace = (COLORREF)-1);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 그라데이션 링의 경계를 지정하는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 매개변수입니다.

*색상 시작*<br/>
【인】 그라데이션의 첫 번째 색상입니다.

*색상 마무리*<br/>
【인】 그라데이션의 마지막 색상입니다.

*색상테두리*<br/>
【인】 테두리의 색상입니다.

*n각도*<br/>
【인】 초기 그라데이션 도면 각도를 지정하는 매개변수입니다. 이 값은 0에서 360 사이여야 합니다.

*nWidth*<br/>
【인】 링의 테두리 너비입니다.

*클러 페이스*<br/>
【인】 반지의 내부의 색상입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

*직사각형으로* 정의된 사각형의 너비는 너비가 5픽셀 이상이어야 하며 높이는 5픽셀이상이어야 합니다.

## <a name="cdrawingmanagerdrawline-cdrawingmanagerdrawlinea"></a><a name="drawline_cdrawingmanager__drawlinea"></a>C그리기 관리자::DrawLine, CDrawingManager::DrawLineA

선을 그립니다.

```cpp
void DrawLine(
    int x1,
    int y1,
    int x2,
    int y2,
    COLORREF clrLine);

void DrawLineA(
    double x1,
    double y1,
    double x2,
    double y2,
    COLORREF clrLine);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*x1*|【인】 선이 시작되는 좌표입니다.|
|*y1*|【인】 선이 시작되는 y 좌표입니다.|
|*x2*|【인】 선이 끝나는 좌표입니다.|
|*y2*|【인】 선이 끝나는 y 좌표입니다.|
|*클라인*|【인】 선의 색상입니다.|

### <a name="remarks"></a>설명

*clrLine이* -1이면 이 메서드가 실패합니다.

## <a name="cdrawingmanagerdrawrect"></a><a name="drawrect"></a>C그리기 관리자::D로렉트

제공된 채우기 및 테두리 색상이 있는 사각형을 그립니다.

```cpp
void DrawRect(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 사각형의 경계입니다.

*clrFill*<br/>
【인】 이 메서드는 사각형을 채우는 데 사용하는 색상입니다.

*클라인*<br/>
【인】 이 메서드가 사각형의 테두리에 사용하는 색상입니다.

### <a name="remarks"></a>설명

이 메서드는 사각형을 그리지 않고 반환 하는 경우 두 색상 -1로 설정 되어 있습니다. 사각형의 차원이 0인 경우에도 반환됩니다.

## <a name="cdrawingmanagerdrawshadow"></a><a name="drawshadow"></a>C그리기 관리자::D로그림자

직사각형 영역에 대한 그림자를 그립니다.

```
BOOL DrawShadow(
    CRect rect,
    int nDepth,
    int iMinBrightness = 100,
    int iMaxBrightness = 50,
    CBitmap* pBmpSaveBottom = NULL,
    CBitmap* pBmpSaveRight = NULL,
    COLORREF clrBase = (COLORREF)-1,
    BOOL bRightShadow = TRUE);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 응용 프로그램의 직사각형 영역입니다. 드로잉 관리자는 이 영역 아래에 그림자를 그립니다.

*n 깊이*<br/>
【인】 그림자의 너비와 높이입니다.

*아이민밝기*<br/>
【인】 그림자의 최소 밝기입니다.

*아이맥스밝기*<br/>
【인】 그림자의 최대 밝기입니다.

*pBmp세이브바텀*<br/>
【인】 그림자의 아래쪽 부분에 대한 이미지가 포함된 비트맵에 대한 포인터입니다.

*pBmp세이브라이트*<br/>
【인】 사각형의 오른쪽에 그려진 그림자에 대한 이미지가 포함된 비트맵에 대한 포인터입니다.

*클러베이스*<br/>
【인】 그림자의 색상입니다.

*b라이트섀도우*<br/>
【인】 그림자가 그려지는 방법을 나타내는 부울 매개변수입니다. *bRightShadow인* `TRUE`경우 `DrawShadow` 사각형의 오른쪽에 그림자가 그려지습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

매개 변수 *pBmpSaveBottom* 및 *pBmpSaveRight를*사용하여 아래쪽 및 오른쪽 그림자에 대해 두 개의 유효한 비트맵을 제공할 수 있습니다. 이러한 [CBitmap](../../mfc/reference/cbitmap-class.md) 개체에 연결된 GDI `DrawShadow` 개체가 있는 경우 해당 비트맵을 그림자로 사용합니다. 매개 `CBitmap` 변수에 연결된 GDI 개체가 `DrawShadow` 없는 경우 그림자를 그리고 비트맵을 매개 변수에 연결합니다. 나중에 `DrawShadow`에 대한 호출에서는 이러한 비트맵을 제공하여 그리기 프로세스를 가속화할 수 있습니다. 클래스 및 GDI 개체에 `CBitmap` 대한 자세한 내용은 그래픽 [개체](../../mfc/graphic-objects.md)를 참조하십시오.

이러한 매개 변수 중 `NULL` `DrawShadow` 하나가 있는 경우 자동으로 그림자를 그립니다.

*bRightShadow를* FALSE로 설정하면 그림자가 직사각형 영역의 아래와 왼쪽에 그려집니다.

### <a name="example"></a>예제

다음 예제에서는 `DrawShadow` `CDrawingManager` 클래스의 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 Prop [시트 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]

## <a name="cdrawingmanagerfill4colorsgradient"></a><a name="fill4colorsgradient"></a>C그리기 관리자::채우기4색상그라데이션

직사각형 영역을 두 개의 색상 그라데이션으로 채웁니다.

```cpp
void Fill4ColorsGradient(
    CRect rect,
    COLORREF colorStart1,
    COLORREF colorFinish1,
    COLORREF colorStart2,
    COLORREF colorFinish2,
    BOOL bHorz = TRUE,
    int nPercentage = 50);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 채울 사각형입니다.

*색상 시작1*<br/>
【인】 첫 번째 색상 그라데이션의 초기 색상입니다.

*색상마무리1*<br/>
【인】 첫 번째 색상 그라데이션의 마지막 색상입니다.

*색상 시작2*<br/>
【인】 두 번째 색상 그라데이션의 초기 색상입니다.

*색상마무리2*<br/>
【인】 두 번째 색상 그라데이션의 마지막 색상입니다.

*b호르츠 (주)*<br/>
【인】 수평 또는 수직 그라데이션의 색상 여부를 `Fill4ColorsGradient` 나타내는 부울 매개변수입니다. TRUE는 수평 그라데이션을 나타냅니다.

*n백분율*<br/>
【인】 0-100의 정수입니다. 이 값은 첫 번째 색상 그라데이션으로 채울 사각형의 백분율을 나타냅니다.

### <a name="remarks"></a>설명

사각형이 두 개의 색상 그라데이션으로 채워지면 *bHorz*값에 따라 서로 위에 있거나 옆에 있습니다. 각 색상 그라데이션은 [CDrawingManager::FillGradient](#fillgradient)메서드와 독립적으로 계산됩니다.

이 메서드는 *nPercentage이* 0보다 작거나 100보다 작으면 어설션 오류를 생성합니다.

## <a name="cdrawingmanagerfillgradient"></a><a name="fillgradient"></a>C그리기 관리자::필그라데이션

지정된 색상 그라데이션으로 직사각형 영역을 채웁니다.

```cpp
void FillGradient(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    BOOL bHorz = TRUE,
    int nStartFlatPercentage = 0,
    int nEndFlatPercentage = 0);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 채울 직사각형 영역입니다.

*색상 시작*<br/>
【인】 그라데이션의 첫 번째 색상입니다.

*색상 마무리*<br/>
【인】 그라데이션의 마지막 색상입니다.

*b호르츠 (주)*<br/>
【인】 가로 또는 수직 그라데이션을 그려야 하는지 여부를 `FillGradient` 지정하는 부울 매개변수입니다.

*n스타트플랫백분율*<br/>
【인】 그라데이션을 시작하기 전에 `FillGradient` *colorStart로* 채우는 사각형의 백분율입니다.

*nEndFlat백분율*<br/>
【인】 그라데이션을 완료한 `FillGradient` 후 *완료색으로* 채우는 사각형의 백분율입니다.

### <a name="example"></a>예제

다음 예제에서는 `FillGradient` `CDrawingManager` 클래스의 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 MS [Office 2007 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]

## <a name="cdrawingmanagerfillgradient2"></a><a name="fillgradient2"></a>C그리기 관리자::필그라디언트2

지정된 색상 그라데이션으로 직사각형 영역을 채웁니다.

```cpp
void FillGradient2 (
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    int nAngle = 0);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 채울 직사각형 영역입니다.

*색상 시작*<br/>
【인】 그라데이션의 첫 번째 색상입니다.

*색상 마무리*<br/>
【인】 그라데이션의 마지막 색상입니다.

*n각도*<br/>
【인】 0에서 360 사이의 정수입니다. 이 매개변수는 색상 그라데이션의 방향을 지정합니다.

### <a name="remarks"></a>설명

*nAngle을* 사용하여 색상 그라데이션의 방향을 지정합니다. 색상 그라데이션의 방향을 지정할 때 색상 그라데이션이 시작되는 위치도 지정합니다. *nAngle에* 대한 값이 0이면 그라데이션이 사각형의 맨 위에서 시작됩니다. *nAngle이* 증가하면 그라데이션의 시작 위치가 각도에 따라 시계 반대 방향으로 이동합니다.

### <a name="example"></a>예제

다음 예제에서는 `FillGradient2` `CDrawingManager` 클래스의 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 새 [컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]

## <a name="cdrawingmanagergrayrect"></a><a name="grayrect"></a>C그리기 관리자::그레이렉트

사각형을 지정된 회색으로 채웁니다.

```
BOOL GrayRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    COLORREF clrDisabled = (COLORREF)-1);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 채울 직사각형 영역입니다.

*n백분율*<br/>
【인】 사각형에서 원하는 회색의 백분율입니다.

*clr투명*<br/>
【인】 투명 한 색상입니다.

*clr장애인*<br/>
【인】 *nPercentage이* -1로 설정된 경우 이 메서드가 채도 를 해제하는 데 사용하는 색상입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

매개변수 *nPercentage의*경우 값이 낮을수록 더 어두운 색상을 나타냅니다.

*nPercentage의* 최대값은 200입니다. 값이 200보다 크면 사각형의 모양이 변경되지 않습니다. 값이 -1이면 이 메서드는 *clrDisabled를* 사용하여 사각형의 채도를 제한합니다.

## <a name="cdrawingmanagerhighlightrect"></a><a name="highlightrect"></a>C그리기 관리자::하이라이트

직사각형 영역을 강조 표시됩니다.

```
BOOL HighlightRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    int nTolerance = 0,
    COLORREF clrBlend = (COLORREF)-1);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 강조 표시할 직사각형 영역입니다.

*n백분율*<br/>
【인】 강조 표시가 얼마나 투명해야 하는지 나타내는 백분율입니다.

*clr투명*<br/>
【인】 투명 한 색상입니다.

*n관용*<br/>
【인】 색상 공차를 나타내는 0에서 255 사이의 정수입니다.

*클러 블렌드*<br/>
【인】 블렌딩을 위한 기본 색상입니다.

### <a name="return-value"></a>Return Value

TRUE 메서드가 성공하면 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

*nPercentage이* 0에서 99 `HighlightRect` 사이인 경우 알파 혼합 알고리즘을 사용합니다. 알파 블렌딩에 대한 자세한 내용은 [알파 혼합 선 및 채우기를](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills)참조하십시오. *nPercentage이* -1인 경우 이 메서드는 기본 강조 표시 수준을 사용합니다. *nPercentage이* 100이면 이 메서드는 아무 것도 수행하지 않으며 TRUE를 반환합니다.

메서드는 매개 변수 *nTolerance를* 사용하여 직사각형 영역을 강조 표시할지 여부를 결정합니다. 사각형을 강조 표시하려면 응용 프로그램의 배경색과 *clrTransparent* 의 차이는 각 색상 구성 요소(빨간색, 녹색 및 파란색)의 *nTolerance보다* 낮아야 합니다.

## <a name="cdrawingmanagerhlstorgb_one"></a><a name="hlstorgb_one"></a>C그리기 관리자::HLStoRGB_ONE

HLS 표현에서 RGB 표현으로 색상을 변환합니다.

```
static COLORREF __stdcall HLStoRGB_ONE(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
【인】 색상의 색조를 나타내는 0에서 1 사이의 숫자입니다.

*ℓ*<br/>
【인】 0에서 1 사이의 숫자로 색상의 광도를 나타냅니다.

*S*<br/>
【인】 색상의 채도를 나타내는 0에서 1 사이의 숫자입니다.

### <a name="return-value"></a>Return Value

제공된 HLS 색상의 RGB 표현입니다.

### <a name="remarks"></a>설명

색상은 HSV(색조, 채도 및 값), HSL(색조, 채도 및 광도) 또는 RGB(빨간색, 녹색 및 파란색)로 나타낼 수 있습니다. 다양한 색상 표현에 대한 자세한 내용은 [색상](/windows/win32/uxguide/vis-color)을 참조하십시오.

이 메서드와 `CDrawingManager::HLStoRGB_TWO` 메서드는 동일한 작업을 수행하지만 *H* 매개 변수에 대해 다른 값이 필요합니다. 이 방법에서 *H는* 원의 백분율입니다. 이 `CDrawingManager::HLStoRGB_TWO` 메서드에서 *H는* 0과 360 사이의 정도 값이며 둘 다 빨간색을 나타냅니다. 예를 들어 `HLStoRGB_ONE`h에 *대한* 값이 0.25인 경우 는 90과 `HLStoRGB_TWO`같습니다.

## <a name="cdrawingmanagerhlstorgb_two"></a><a name="hlstorgb_two"></a>C그리기 관리자::HLStoRGB_TWO

HLS 표현에서 RGB 표현으로 색상을 변환합니다.

```
static COLORREF __stdcall HLStoRGB_TWO(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
【인】 색상의 색조를 나타내는 0에서 360 사이의 숫자입니다.

*ℓ*<br/>
【인】 0에서 1 사이의 숫자로 색상의 광도를 나타냅니다.

*S*<br/>
【인】 색상의 채도를 나타내는 0에서 1 사이의 숫자입니다.

### <a name="return-value"></a>Return Value

제공된 HLS 색상의 RGB 표현입니다.

### <a name="remarks"></a>설명

색상은 HSV(색조, 채도 및 값), HSL(색조, 채도 및 광도) 또는 RGB(빨간색, 녹색 및 파란색)로 나타낼 수 있습니다. 다양한 색상 표현에 대한 자세한 내용은 [색상](/windows/win32/uxguide/vis-color)을 참조하십시오.

이 메서드와 [CDrawingManager:HLStoRGB_ONE](#hlstorgb_one) 메서드는 동일한 작업을 수행하지만 *H* 매개 변수에 대해 다른 값이 필요합니다. 이 방법에서 *H는* 0과 360 사이의 정도 값이며 둘 다 빨간색을 나타냅니다. [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) 메서드에서 *H는* 원의 백분율입니다. 예를 들어 `HLStoRGB_ONE`h에 *대한* 값이 0.25인 경우 는 90과 `HLStoRGB_TWO`같습니다.

## <a name="cdrawingmanagerhsvtorgb"></a><a name="hsvtorgb"></a>C그리기 관리자::HSVtoRGB

HSV 표현에서 RGB 표현으로 색상을 변환합니다.

```
static COLORREF __stdcall HSVtoRGB(
    double H,
    double S,
    double V);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*H*|【인】 0에서 360 사이의 숫자로 색조의 색조를 나타냅니다.|
|*S*|【인】 색상의 채도를 나타내는 0에서 1 사이의 숫자입니다.|
|*Ⅴ*|【인】 0에서 1 사이의 숫자로 색상 값을 나타냅니다.|

### <a name="return-value"></a>Return Value

제공된 HSV 색상의 RGB 표현.

### <a name="remarks"></a>설명

색상은 HSV(색조, 채도 및 값), HSL(색조, 채도 및 광도) 또는 RGB(빨간색, 녹색 및 파란색)로 나타낼 수 있습니다. 다양한 색상 표현에 대한 자세한 내용은 [색상](/windows/win32/uxguide/vis-color)을 참조하십시오.

## <a name="cdrawingmanagerhuetorgb"></a><a name="huetorgb"></a>C드로잉 매니저::휴토RGB

색조 값을 빨간색, 녹색 또는 파란색 구성요소로 변환합니다.

```
static double __stdcall HuetoRGB(
    double m1,
    double m2,
    double h);

static BYTE __stdcall HueToRGB(
    float rm1,
    float rm2,
    float rh);
```

### <a name="parameters"></a>매개 변수

*m1*<br/>
【인】 비고를 참조하십시오.

*m2*<br/>
【인】 비고를 참조하십시오.

*H*<br/>
【인】 비고를 참조하십시오.

*rm1*<br/>
【인】 비고를 참조하십시오.

*rm2*<br/>
【인】 비고를 참조하십시오.

*Rh*<br/>
【인】 비고를 참조하십시오.

### <a name="return-value"></a>Return Value

제공된 색조에 대한 개별 빨간색, 녹색 또는 파란색 구성 요소입니다.

### <a name="remarks"></a>설명

이 메서드는 클래스에서 `CDrawingManager` HSV 또는 HSL 표현에서 색상의 개별 빨간색, 녹색 및 파란색 구성 요소를 계산하는 데 사용하는 도우미 방법입니다. 이 메서드는 프로그래머가 직접 호출하도록 설계되지 않았습니다. 입력 매개 변수는 변환 알고리즘에 종속된 값입니다.

HSV 또는 HSL 색상을 RGB 표현으로 변환하려면 다음 방법 중 하나를 호출하십시오.

- [C그리기 관리자::HSVtoRGB](#hsvtorgb)

- [C그리기 관리자::HLStoRGB_ONE](#hlstorgb_one)

- [C그리기 관리자::HLStoRGB_TWO](#hlstorgb_two)

## <a name="cdrawingmanagermirrorrect"></a><a name="mirrorrect"></a>C그리기 관리자::미러렉트

직사각형 영역을 뒤집습니다.

```cpp
void MirrorRect(
    CRect rect,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 뒤집을 영역의 경계 사각형입니다.

*b호르츠 (주)*<br/>
【인】 사각형이 수평 또는 수직으로 뒤집히는지 여부를 나타내는 부울 매개변수입니다.

### <a name="remarks"></a>설명

이 메서드는 클래스가 소유한 장치 컨텍스트의 모든 영역을 대칭 반전할 `CDrawingManager` 수 있습니다. *bHorz가* TRUE로 설정된 경우 이 메서드는 영역을 수평으로 뒤집습니다. 그렇지 않으면 영역을 수직으로 뒤집습니다.

## <a name="cdrawingmanagerpixelalpha"></a><a name="pixelalpha"></a>C그리기 관리자::P익셀알파

반투명 픽셀의 최종 색상을 계산합니다.

```
static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    int percent);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    double percentR,
    double percentG,
    double percentB);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    COLORREF dstPixel,
    int percent);
```

### <a name="parameters"></a>매개 변수

*스르픽셀*<br/>
【인】 픽셀의 초기 색상입니다.

*퍼센트*<br/>
【인】 투명도 의 백분율을 나타내는 0에서 100 사이의 숫자입니다. 값이 100이면 초기 색상이 완전히 투명하다는 것을 나타냅니다.

*백분율R*<br/>
【인】 빨간색 구성요소에 대한 투명도 백분율을 나타내는 0에서 100 사이의 숫자입니다.

*백분율G*<br/>
【인】 녹색 구성 요소에 대한 투명도 백분율을 나타내는 0에서 100 사이의 숫자입니다.

*백분율B*<br/>
【인】 파란색 구성요소에 대한 투명도 백분율을 나타내는 0에서 100 사이의 숫자입니다.

*dstPixel*<br/>
【인】 픽셀의 기본 색상입니다.

### <a name="return-value"></a>Return Value

반투명 픽셀의 마지막 색상입니다.

### <a name="remarks"></a>설명

이 클래스는 반투명 비트맵을 색칠하기 위한 도우미 클래스이며 프로그래머가 직접 호출하도록 설계되지 않았습니다.

*dstPixel이있는*메서드의 버전을 사용하는 경우 최종 색상은 *dstPixel과* *srcPixel의*조합입니다. *srcPixel* 색상은 *dstPixel의*기본 색상에 부분적으로 투명한 색상입니다.

## <a name="cdrawingmanagerprepareshadowmask"></a><a name="prepareshadowmask"></a>C그리기 관리자::P레파레섀도우 마스크

그림자로 사용할 수 있는 비트맵을 만듭니다.

```
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,
    COLORREF clrBase,
    int iMinBrightness = 0,
    int iMaxBrightness = 100);
```

### <a name="parameters"></a>매개 변수

*n 깊이*<br/>
【인】 그림자의 너비와 높이입니다.

*클러베이스*<br/>
【인】 그림자의 색상입니다.

*아이민밝기*<br/>
【인】 그림자의 최소 밝기입니다.

*아이맥스밝기*<br/>
【인】 그림자의 최대 밝기입니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 생성된 비트맵에 대한 핸들입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

*nDepth가* 0으로 설정된 경우 이 메서드는 NULL을 종료하고 반환합니다. *nDepth가* 3보다 작으면 그림자의 너비와 높이가 3픽셀로 설정됩니다.

## <a name="cdrawingmanagerrgbtohsl"></a><a name="rgbtohsl"></a>C그리기 관리자::RGBtoHSL

빨간색, 녹색 및 파란색(RGB) 표현에서 색조, 채도 및 가벼움(HSL) 표현으로 색상을 변환합니다.

```
static void __stdcall RGBtoHSL(
    COLORREF rgb,
    double* H,
    double* S,
    double* L);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*Rgb*|【인】 RGB 값의 색상입니다.|
|*H*|【아웃】 메서드가 색상의 색조를 저장하는 이중포인터입니다.|
|*S*|【아웃】 메서드가 색상의 채도를 저장하는 이중포인터입니다.|
|*ℓ*|【아웃】 메서드가 색상의 가벼움을 저장하는 이중포인터입니다.|

### <a name="remarks"></a>설명

색상은 HSV(색조, 채도 및 값), HSL(색조, 채도 및 광도) 또는 RGB(빨간색, 녹색 및 파란색)로 나타낼 수 있습니다. 다양한 색상 표현에 대한 자세한 내용은 [색상](/windows/win32/uxguide/vis-color)을 참조하십시오.

*H에* 대한 반환된 값은 0과 1 사이의 분수로 표시되며, 여기서 0과 1은 모두 빨간색을 나타냅니다. *S와* *L에* 대해 반환된 값은 0과 1 사이의 숫자입니다.

## <a name="cdrawingmanagerrgbtohsv"></a><a name="rgbtohsv"></a>C그리기 관리자::RGBtoHSV

RGB 표현에서 HSV 표현으로 색상을 변환합니다.

```
static void __stdcall RGBtoHSV(
    COLORREF rgb,
    double* H,
    double* S,
    double* V);
```

### <a name="parameters"></a>매개 변수

*Rgb*<br/>
【인】 RGB 표현으로 변환할 색상입니다.

*H*<br/>
【아웃】 이 메서드는 색상의 결과 색조를 저장하는 이중포인터입니다.

*S*<br/>
【아웃】 이 메서드는 색상의 결과 채도를 저장하는 이중포인터입니다.

*Ⅴ*<br/>
【아웃】 이 메서드는 색상의 결과 값을 저장하는 이중포인터입니다.

### <a name="remarks"></a>설명

색상은 HSV(색조, 채도 및 값), HSL(색조, 채도 및 광도) 또는 RGB(빨간색, 녹색 및 파란색)로 나타낼 수 있습니다. 다양한 색상 표현에 대한 자세한 내용은 [색상](/windows/win32/uxguide/vis-color)을 참조하십시오.

*H에* 대해 반환된 값은 0과 360 사이의 숫자이며 0과 360은 모두 빨간색을 나타냅니다. *S와* *V의* 반환 값은 0과 1 사이의 숫자입니다.

## <a name="cdrawingmanagersetalphapixel"></a><a name="setalphapixel"></a>C그리기 관리자::설정알파픽셀

비트맵의 투명 픽셀에 색상을 표시합니다.

```
static void __stdcall SetAlphaPixel(
    COLORREF* pBits,
    CRect rect,
    int x,
    int y,
    int percent,
    int iShadowSize,
    COLORREF clrBase = (COLORREF)-1,
    BOOL bIsRight = TRUE);
```

### <a name="parameters"></a>매개 변수

*비트*<br/>
【인】 비트맵의 비트 값에 대한 포인터입니다.

*rect*<br/>
【인】 응용 프로그램의 직사각형 영역입니다. 드로잉 관리자는 이 영역의 아래와 오른쪽에 그림자를 그립니다.

*x*<br/>
【인】 색상픽셀의 수평 좌표입니다.

*Y*<br/>
【인】 색상에 픽셀의 세로 좌표입니다.

*퍼센트*<br/>
【인】 투명도의 백분율입니다.

*아이섀도우 사이즈*<br/>
【인】 그림자의 너비와 높이입니다.

*클러베이스*<br/>
【인】 그림자의 색상입니다.

*비스라이트*<br/>
【인】 색상을 표시할 픽셀을 나타내는 부울 매개변수입니다. 자세한 내용은 주의 섹션을 참조하십시오.

### <a name="remarks"></a>설명

이 메서드는 [CDrawingManager::DrawShadow](#drawshadow) 메서드에서 사용 되는 도우미 메서드입니다. 그림자를 그리려면 대신 호출하는 `CDrawingManager::DrawShadow` 것이 좋습니다.

*bIsRight가* TRUE로 설정된 경우 픽셀에서 색상까지의 픽셀은 *직사각형의*오른쪽 가장자리에서 *x* 픽셀로 측정됩니다. FALSE이면 픽셀에서 색상까지의 픽셀이 *직사각형의*왼쪽 가장자리에서 *x* 픽셀로 측정됩니다.

## <a name="cdrawingmanagersetpixel"></a><a name="setpixel"></a>C그리기 관리자::설정 픽셀

비트맵의 단일 픽셀을 지정된 색상으로 변경합니다.

```
static void __stdcall SetPixel(
    COLORREF* pBits,
    int cx,
    int cy,
    int x,
    int y,
    COLORREF color);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*비트*|【인】 비트맵의 비트 값에 대한 포인터입니다.|
|*Cx*|【인】 비트맵의 총 너비입니다.|
|*Cy*|【인】 비트맵의 총 높이입니다.|
|*x*|【인】 변경할 비트맵의 픽셀의 x 좌표입니다.|
|*Y*|【인】 변경할 비트맵의 픽셀의 y 좌표입니다.|
|*색*|【인】 제공된 좌표로 식별된 픽셀의 새 색상입니다.|

## <a name="cdrawingmanagersmartmixcolors"></a><a name="smartmixcolors"></a>C그리기 관리자::스마트 믹스 컬러

가중 비율에 따라 두 가지 색상을 결합합니다.

```
static COLORREF __stdcall SmartMixColors(
    COLORREF color1,
    COLORREF color2,
    double dblLumRatio = 1.,
    int k1 = 1,
    int k2 = 1);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*색상1*|【인】 혼합 하는 첫 번째 색상입니다.|
|*색상2*|【인】 혼합 할 두 번째 색상.|
|*dblLumRatio*|【인】 새 색상의 광도에 대한 비율입니다. `SmartMixColors`최종 색상을 결정하기 전에 혼합 색상의 광도에 이 비율을 곱합니다.|
|*k1*|【인】 첫 번째 색상의 가중 비율입니다.|
|*k2*|【인】 두 번째 색상의 가중 비율입니다.|

### <a name="return-value"></a>Return Value

제공된 색상의 가중 혼합을 나타내는 색상입니다.

### <a name="remarks"></a>설명

*k1* 또는 *k2가* 0보다 크면 이 메서드가 오류와 함께 실패합니다. 이러한 매개 변수가 모두 0으로 설정된 `RGB(0, 0, 0)`경우 메서드가 반환합니다.

가중 비율은 다음 공식으로 계산됩니다(color1 \* k1 \* + color2 k2)/(k1 + k2). 가중 비가 결정된 후, 방법은 혼합 된 색상의 광도를 계산한다. 그런 다음 *dblLumRatio에*광도를 곱합니다. 값이 1.0보다 큰 경우 메서드는 혼합 색상의 광도를 새 값으로 설정합니다. 그렇지 않으면 광도가 1.0으로 설정됩니다.

## <a name="cdrawingmanagerdrawrotated"></a><a name="drawrotated"></a>C그리기 관리자::D회전

지정된 사각형 내부의 소스 DC 콘텐츠를 90도 회전합니다.

```cpp
void DrawRotated(
    CRect rectDest,
    CDC& dcSrc,
    BOOL bClockWise);
```

### <a name="parameters"></a>매개 변수

*rectDest*<br/>
대상 사각형입니다.

*dcSrc*<br/>
소스 장치 컨텍스트입니다.

*b시계 와이즈*<br/>
TRUE는 회전 +90도를 나타냅니다. FALSE는 -90도 회전을 나타냅니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
