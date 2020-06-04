---
title: CRenderTarget 클래스
ms.date: 03/27/2019
f1_keywords:
- CRenderTarget
- AFXRENDERTARGET/CRenderTarget
- AFXRENDERTARGET/CRenderTarget::CRenderTarget
- AFXRENDERTARGET/CRenderTarget::Attach
- AFXRENDERTARGET/CRenderTarget::BeginDraw
- AFXRENDERTARGET/CRenderTarget::Clear
- AFXRENDERTARGET/CRenderTarget::COLORREF_TO_D2DCOLOR
- AFXRENDERTARGET/CRenderTarget::CreateCompatibleRenderTarget
- AFXRENDERTARGET/CRenderTarget::Destroy
- AFXRENDERTARGET/CRenderTarget::Detach
- AFXRENDERTARGET/CRenderTarget::DrawBitmap
- AFXRENDERTARGET/CRenderTarget::DrawEllipse
- AFXRENDERTARGET/CRenderTarget::DrawGeometry
- AFXRENDERTARGET/CRenderTarget::DrawGlyphRun
- AFXRENDERTARGET/CRenderTarget::DrawLine
- AFXRENDERTARGET/CRenderTarget::DrawRectangle
- AFXRENDERTARGET/CRenderTarget::DrawRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::DrawText
- AFXRENDERTARGET/CRenderTarget::DrawTextLayout
- AFXRENDERTARGET/CRenderTarget::EndDraw
- AFXRENDERTARGET/CRenderTarget::FillEllipse
- AFXRENDERTARGET/CRenderTarget::FillGeometry
- AFXRENDERTARGET/CRenderTarget::FillMesh
- AFXRENDERTARGET/CRenderTarget::FillOpacityMask
- AFXRENDERTARGET/CRenderTarget::FillRectangle
- AFXRENDERTARGET/CRenderTarget::FillRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::Flush
- AFXRENDERTARGET/CRenderTarget::GetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetDpi
- AFXRENDERTARGET/CRenderTarget::GetMaximumBitmapSize
- AFXRENDERTARGET/CRenderTarget::GetPixelFormat
- AFXRENDERTARGET/CRenderTarget::GetPixelSize
- AFXRENDERTARGET/CRenderTarget::GetRenderTarget
- AFXRENDERTARGET/CRenderTarget::GetSize
- AFXRENDERTARGET/CRenderTarget::GetTags
- AFXRENDERTARGET/CRenderTarget::GetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::GetTransform
- AFXRENDERTARGET/CRenderTarget::IsSupported
- AFXRENDERTARGET/CRenderTarget::IsValid
- AFXRENDERTARGET/CRenderTarget::PopAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PopLayer
- AFXRENDERTARGET/CRenderTarget::PushAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PushLayer
- AFXRENDERTARGET/CRenderTarget::RestoreDrawingState
- AFXRENDERTARGET/CRenderTarget::SaveDrawingState
- AFXRENDERTARGET/CRenderTarget::SetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetDpi
- AFXRENDERTARGET/CRenderTarget::SetTags
- AFXRENDERTARGET/CRenderTarget::SetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::SetTransform
- AFXRENDERTARGET/CRenderTarget::VerifyResource
- AFXRENDERTARGET/CRenderTarget::m_lstResources
- AFXRENDERTARGET/CRenderTarget::m_pRenderTarget
- AFXRENDERTARGET/CRenderTarget::m_pTextFormatDefault
helpviewer_keywords:
- CRenderTarget [MFC], CRenderTarget
- CRenderTarget [MFC], Attach
- CRenderTarget [MFC], BeginDraw
- CRenderTarget [MFC], Clear
- CRenderTarget [MFC], COLORREF_TO_D2DCOLOR
- CRenderTarget [MFC], CreateCompatibleRenderTarget
- CRenderTarget [MFC], Destroy
- CRenderTarget [MFC], Detach
- CRenderTarget [MFC], DrawBitmap
- CRenderTarget [MFC], DrawEllipse
- CRenderTarget [MFC], DrawGeometry
- CRenderTarget [MFC], DrawGlyphRun
- CRenderTarget [MFC], DrawLine
- CRenderTarget [MFC], DrawRectangle
- CRenderTarget [MFC], DrawRoundedRectangle
- CRenderTarget [MFC], DrawText
- CRenderTarget [MFC], DrawTextLayout
- CRenderTarget [MFC], EndDraw
- CRenderTarget [MFC], FillEllipse
- CRenderTarget [MFC], FillGeometry
- CRenderTarget [MFC], FillMesh
- CRenderTarget [MFC], FillOpacityMask
- CRenderTarget [MFC], FillRectangle
- CRenderTarget [MFC], FillRoundedRectangle
- CRenderTarget [MFC], Flush
- CRenderTarget [MFC], GetAntialiasMode
- CRenderTarget [MFC], GetDpi
- CRenderTarget [MFC], GetMaximumBitmapSize
- CRenderTarget [MFC], GetPixelFormat
- CRenderTarget [MFC], GetPixelSize
- CRenderTarget [MFC], GetRenderTarget
- CRenderTarget [MFC], GetSize
- CRenderTarget [MFC], GetTags
- CRenderTarget [MFC], GetTextAntialiasMode
- CRenderTarget [MFC], GetTextRenderingParams
- CRenderTarget [MFC], GetTransform
- CRenderTarget [MFC], IsSupported
- CRenderTarget [MFC], IsValid
- CRenderTarget [MFC], PopAxisAlignedClip
- CRenderTarget [MFC], PopLayer
- CRenderTarget [MFC], PushAxisAlignedClip
- CRenderTarget [MFC], PushLayer
- CRenderTarget [MFC], RestoreDrawingState
- CRenderTarget [MFC], SaveDrawingState
- CRenderTarget [MFC], SetAntialiasMode
- CRenderTarget [MFC], SetDpi
- CRenderTarget [MFC], SetTags
- CRenderTarget [MFC], SetTextAntialiasMode
- CRenderTarget [MFC], SetTextRenderingParams
- CRenderTarget [MFC], SetTransform
- CRenderTarget [MFC], VerifyResource
- CRenderTarget [MFC], m_lstResources
- CRenderTarget [MFC], m_pRenderTarget
- CRenderTarget [MFC], m_pTextFormatDefault
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
ms.openlocfilehash: 8c0a0d1f578b2f0d186ce0f4ea8c7da07e741b71
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747203"
---
# <a name="crendertarget-class"></a>CRenderTarget 클래스

ID2D1RenderTarget용 래퍼입니다.

## <a name="syntax"></a>구문

```
class CRenderTarget : public CObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CRenderTarget::CRenderTarget](#crendertarget)|CRenderTarget 개체를 생성합니다.|
|[CRenderTarget::~CRenderTarget](#_dtorcrendertarget)|소멸자입니다. 렌더링 대상 개체가 소멸될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CRenderTarget::연결](#attach)|기존 렌더 대상 인터페이스를 오브젝트에 연결합니다.|
|[CRenderTarget::시작 그리기](#begindraw)|이 렌더 대상에 그리기를 시작합니다.|
|[CRenderTarget::지우기](#clear)|드로잉 영역을 지정된 색상으로 지웁습니다.|
|[CRenderTarget::COLORREF_TO_D2DCOLOR](#colorref_to_d2dcolor)|GDI 색상 및 알파 값을 D2D1_COLOR_F 개체로 변환합니다.|
|[CRenderTarget::생성 호환렌더 대상](#createcompatiblerendertarget)|현재 렌더 대상과 호환되는 중간 오프스크린 드로잉 중에 사용할 새 비트맵 렌더 대상을 만듭니다.|
|[CRenderTarget::D에스트로이](#destroy)|하나 이상의 리소스 삭제|
|[CRenderTarget::D](#detach)|개체에서 대상 인터페이스를 렌더링합니다.|
|[CRenderTarget::D로비트맵](#drawbitmap)|지정된 IDWriteTextLayout 개체에서 설명하는 서식이 지정된 텍스트를 그립니다.|
|[CRenderTarget::D로엘립스](#drawellipse)|지정된 스트로크 스타일을 사용하여 지정된 타원의 윤곽선을 그립니다.|
|[CRenderTarget::D원시 지오메트리](#drawgeometry)|지정된 선 스타일을 사용하여 지정된 형상의 윤곽선을 그립니다.|
|[CRenderTarget::D로글리프런](#drawglyphrun)|지정된 글리프를 그립니다.|
|[CRenderTarget::DrawLine](#drawline)|지정된 선 스타일을 사용하여 지정된 점 사이에 선을 그립니다.|
|[CRenderTarget::Draw Rectangle](#drawrectangle)|지정된 치수 및 획 스타일이 있는 사각형의 윤곽선을 그립니다.|
|[CRenderTarget::Drawrounded 사각형](#drawroundedrectangle)|지정된 선 스타일을 사용하여 지정된 둥근 사각형의 윤곽선을 그립니다.|
|[CRenderTarget::DrawText](#drawtext)|IDWriteTextFormat 개체에서 제공하는 형식 정보를 사용하여 지정된 텍스트를 그립니다.|
|[CRenderTarget::Draw텍스트 레이아웃](#drawtextlayout)|지정된 IDWriteTextLayout 개체에서 설명하는 서식이 지정된 텍스트를 그립니다.|
|[CRenderTarget::끝 그리기](#enddraw)|렌더 대상에서 그리기 작업을 종료하고 현재 오류 상태 및 관련 태그를 나타냅니다.|
|[CRenderTarget::필엘립스](#fillellipse)|지정된 타원의 내부를 페인트합니다.|
|[CRenderTarget::채우기 지오메트리](#fillgeometry)|지정된 형상의 내부를 페인트합니다.|
|[CRenderTarget::채우기 메시](#fillmesh)|지정된 메시의 내부를 페인트합니다.|
|[CRenderTarget::필불투명시 마스크](#fillopacitymask)|지정된 비트맵에서 설명한 불투명도 마스크를 브러시에 적용하고 해당 브러시를 사용하여 렌더 대상의 영역을 페인팅합니다.|
|[CRenderTarget::채우기 사각형](#fillrectangle)|지정된 사각형의 내부를 페인트합니다.|
|[CRenderTarget::채우기 둥근 사각형](#fillroundedrectangle)|지정된 둥근 사각형의 내부를 페인트합니다.|
|[CRenderTarget::플러시](#flush)|보류 중인 모든 그리기 명령을 실행합니다.|
|[CRenderTarget::GetAntialiasMode](#getantialiasmode)|텍스트가 아닌 그리기 작업에 대해 현재 안티 앨리어싱 모드를 검색합니다.|
|[CRenderTarget::GetDpi](#getdpi)|인치당 렌더 대상의 점 반환(DPI)|
|[C렌더 대상::GetMaximum비트맵크기](#getmaximumbitmapsize)|렌더 대상에서 지원하는 하나의 비트맵 차원의 장치 종속 단위(픽셀)에서 최대 크기를 가져옵니다.|
|[CRenderTarget::GetPixelFormat](#getpixelformat)|렌더 대상의 픽셀 형식 및 알파 모드 검색|
|[CRenderTarget::GetPixelSize](#getpixelsize)|장치 픽셀에서 렌더링 대상의 크기를 반환합니다.|
|[CRenderTarget::GetRenderTarget](#getrendertarget)|ID2D1RenderTarget 인터페이스 반환|
|[CRenderTarget::GetSize](#getsize)|장치 독립적인 픽셀에서 렌더링 대상의 크기를 반환합니다.|
|[CRenderTarget::GetTags](#gettags)|후속 그리기 작업에 대한 레이블을 가져옵니다.|
|[CRenderTarget::GetTextAntialias모드](#gettextantialiasmode)|텍스트 및 문자 그림 그리기 작업에 대한 현재 안티 앨리어싱 모드를 가져옵니다.|
|[CRenderTarget::GetText렌더링파라름](#gettextrenderingparams)|렌더 대상의 현재 텍스트 렌더링 옵션을 검색합니다.|
|[CRenderTarget::GetTransform](#gettransform)|지정된 변환을 기존 변환을 대체하여 렌더 대상에 적용합니다. 이후의 모든 그리기 작업은 변환된 공간에서 발생합니다.|
|[CRenderTarget::지원됩니다.](#issupported)|렌더 대상이 지정된 속성을 지원하는지 여부를 나타냅니다.|
|[CRenderTarget::유효하지 않음](#isvalid)|리소스 유효성 검사|
|[CRenderTarget::Popaxis정렬 클립](#popaxisalignedclip)|렌더 대상에서 마지막 축 정렬 클립을 제거합니다. 이 메서드를 호출한 후에는 클립이 후속 그리기 작업에 더 이상 적용되지 않습니다.|
|[CRenderTarget::P](#poplayer)|마지막 PushLayer 호출에 의해 지정된 도면 작업리디렉션을 중지합니다.|
|[CRenderTarget::PushAxis정렬 클립](#pushaxisalignedclip)|렌더 대상에서 마지막 축 정렬 클립을 제거합니다. 이 메서드를 호출한 후에는 클립이 후속 그리기 작업에 더 이상 적용되지 않습니다.|
|[CRenderTarget::P허슬레이어](#pushlayer)|PopLayer가 호출될 때까지 모든 후속 그리기 작업을 수신하도록 지정된 레이어를 렌더 대상에 추가합니다.|
|[CRenderTarget::복원 그리기 상태](#restoredrawingstate)|렌더 대상의 그리기 상태를 지정된 ID2D1DrawingStateBlock의 로 설정합니다.|
|[CRenderTarget::저장 그리기 상태](#savedrawingstate)|현재 도면 상태를 지정된 ID2D1DrawingStateBlock에 저장합니다.|
|[CRenderTarget::SetAntialiasMode](#setantialiasmode)|렌더 대상의 안티 앨리어싱 모드를 설정합니다. 안티 앨리어싱 모드는 텍스트 및 문자 모양 그리기 작업을 제외한 모든 후속 그리기 작업에 적용됩니다.|
|[CRenderTarget::SetDpi](#setdpi)|렌더 대상의 인치당 점(DPI)을 설정합니다.|
|[CRenderTarget::SetTags](#settags)|후속 그리기 작업에 대한 레이블을 지정합니다.|
|[CRenderTarget::SetText안티알리아스모드](#settextantialiasmode)|후속 텍스트 및 문자 그림 그리기 작업에 사용할 안티 앨리어싱 모드를 지정합니다.|
|[CRenderTarget::SetText렌더링파라름](#settextrenderingparams)|이후의 모든 텍스트 및 문자 그림 그리기 작업에 적용할 텍스트 렌더링 옵션을 지정합니다.|
|[CRenderTarget::세트 변환](#settransform)|오버로드되었습니다. 지정된 변환을 기존 변환을 대체하여 렌더 대상에 적용합니다. 이후의 모든 그리기 작업은 변환된 공간에서 발생합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CRenderTarget::검증 리소스](#verifyresource)|CD2DResource 개체 유효성을 확인합니다. 개체가 아직 존재하지 않는 경우 개체를 만듭니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CRenderTarget::연산자 ID2D1렌더대상*](#operator_id2d1rendertarget_star)|ID2D1RenderTarget 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CRenderTarget::m_lstResources](#m_lstresources)|CD2DResource 개체에 대한 포인터 목록입니다.|
|[CRenderTarget::m_pRenderTarget](#m_prendertarget)|ID2D1RenderTarget 개체에 대한 포인터입니다.|
|[CRenderTarget::m_pTextFormatDefault](#m_ptextformatdefault)|기본 텍스트 형식이 포함된 CD2DTextFormat 개체에 대한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="crendertargetcrendertarget"></a><a name="_dtorcrendertarget"></a>CRenderTarget::~CRenderTarget

소멸자입니다. 렌더링 대상 개체가 소멸될 때 호출됩니다.

```
virtual ~CRenderTarget();
```

## <a name="crendertargetattach"></a><a name="attach"></a>CRenderTarget::연결

기존 렌더 대상 인터페이스를 오브젝트에 연결합니다.

```cpp
void Attach(ID2D1RenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*p렌더대상*<br/>
기존 렌더 대상 인터페이스입니다. NULL일 수 없음

## <a name="crendertargetbegindraw"></a><a name="begindraw"></a>CRenderTarget::시작 그리기

이 렌더 대상에 그리기를 시작합니다.

```cpp
void BeginDraw();
```

## <a name="crendertargetclear"></a><a name="clear"></a>CRenderTarget::지우기

드로잉 영역을 지정된 색상으로 지웁습니다.

```cpp
void Clear(D2D1_COLOR_F color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
드로잉 영역이 지워지는 색상입니다.

## <a name="crendertargetcolorref_to_d2dcolor"></a><a name="colorref_to_d2dcolor"></a>CRenderTarget::COLORREF_TO_D2DCOLOR

GDI 색상 및 알파 값을 D2D1_COLOR_F 개체로 변환합니다.

```
static D2D1_COLOR_F COLORREF_TO_D2DCOLOR(
    COLORREF color,
    int nAlpha = 255);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
RGB 값입니다.

*n알파 (주)*

### <a name="return-value"></a>Return Value

D2D1_COLOR_F 값입니다.

## <a name="crendertargetcreatecompatiblerendertarget"></a><a name="createcompatiblerendertarget"></a>CRenderTarget::생성 호환렌더 대상

현재 렌더 대상과 호환되는 중간 오프스크린 드로잉 중에 사용할 새 비트맵 렌더 대상을 만듭니다.

```
BOOL CreateCompatibleRenderTarget(
    CBitmapRenderTarget& bitmapTarget,
    CD2DSizeF sizeDesired = CD2DSizeF(0., 0.),
    CD2DSizeU sizePixelDesired = CD2DSizeU(0, 0),
    D2D1_PIXEL_FORMAT* desiredFormat = NULL,
    D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS options = D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS_NONE);
```

### <a name="parameters"></a>매개 변수

*비트맵대상*<br/>
이 메서드가 반환되면 새 비트맵 렌더 대상에 대한 포인터의 주소가 포함됩니다. 이 매개 변수는 초기화되지 않은 상태로 전달됩니다.

*크기원하는*<br/>
원래 렌더링 대상 또는 NULL과 달라야 하는 경우 장치 독립적인 픽셀에서 새 렌더 대상의 원하는 크기입니다. 자세한 내용은 주의 섹션을 참조하세요.

*크기픽셀원하는*<br/>
원래 렌더링 대상 또는 NULL과 달라야 하는 경우 픽셀 단위로 새 렌더 대상의 원하는 크기입니다. 자세한 내용은 주의 섹션을 참조하세요.

*원하는 형식*<br/>
새 렌더 대상 또는 NULL의 원하는 픽셀 형식 및 알파 모드입니다. 픽셀 형식이 DXGI_FORMAT_UNKNOWN 설정하거나 이 매개 변수가 null인 경우 새 렌더 대상은 원래 렌더링 대상과 동일한 픽셀 형식을 사용합니다. 알파 모드가 D2D1_ALPHA_MODE_UNKNOWN 또는 이 매개 변수가 NULL인 경우 새 렌더 대상의 알파 모드는 D2D1_ALPHA_MODE_PREMULTIPLIED 기본값입니다. 지원되는 픽셀 형식에 대한 자세한 내용은 지원되는 픽셀 형식 및 알파 모드를 참조하세요.

*options*<br/>
새 렌더 대상이 GDI와 호환되어야 하는지 여부를 지정하는 값입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="crendertargetcrendertarget"></a><a name="crendertarget"></a>CRenderTarget::CRenderTarget

CRenderTarget 개체를 생성합니다.

```
CRenderTarget();
```

## <a name="crendertargetdestroy"></a><a name="destroy"></a>CRenderTarget::D에스트로이

하나 이상의 리소스 삭제

```
BOOL Destroy(BOOL bDeleteResources = TRUE);
```

### <a name="parameters"></a>매개 변수

*b삭제리소스*<br/>
bDeleteResourcesTRUE이면 m_lstResources 있는 모든 리소스가 자동으로 소멸됩니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="crendertargetdetach"></a><a name="detach"></a>CRenderTarget::D

개체에서 대상 인터페이스를 렌더링합니다.

```
ID2D1RenderTarget* Detach ();
```

### <a name="return-value"></a>Return Value

분리된 렌더 대상 인터페이스에 대한 포인터입니다.

## <a name="crendertargetdrawbitmap"></a><a name="drawbitmap"></a>CRenderTarget::D로비트맵

지정된 IDWriteTextLayout 개체에서 설명하는 서식이 지정된 텍스트를 그립니다.

```cpp
void DrawBitmap(
    CD2DBitmap* pBitmap,
    const CD2DRectF& rectDest,
    float fOpacity = 1.0,
    D2D1_BITMAP_INTERPOLATION_MODE interpolationMode = D2D1_BITMAP_INTERPOLATION_MODE_LINEAR,
    const CD2DRectF* pRectSrc = NULL);
```

### <a name="parameters"></a>매개 변수

*pBitmap*<br/>
렌더링할 비트맵입니다.

*rectDest*<br/>
비트맵이 그려지는 영역의 렌더 대상 좌표 공간에서 장치 독립적인 픽셀의 크기와 위치입니다. 사각형이 잘 정렬되지 않으면 아무 것도 그려지지 않지만 렌더링 대상이 오류 상태가 되지 않습니다.

*fOpacity*<br/>
비트맵에 적용할 불투명도 값을 지정하는 0.0f에서 1.0f 사이의 값입니다. 이 값은 비트맵 내용의 알파 값에 곱해지됩니다.

*보간 모드*<br/>
그리기 작업에 의해 비트맵의 배율이 조정또는 회전되는 경우 사용할 보간 모드입니다.

*프렉트스rc*<br/>
비트맵의 좌표 공간에서 장치 독립적인 픽셀의 크기와 위치, 그릴 비트맵 내의 영역입니다.

## <a name="crendertargetdrawellipse"></a><a name="drawellipse"></a>CRenderTarget::D로엘립스

지정된 스트로크 스타일을 사용하여 지정된 타원의 윤곽선을 그립니다.

```cpp
void DrawEllipse(
    const CD2DEllipse& ellipse,
    CD2DBrush* pBrush,
    FLOAT fStrokeWidth = 1.0,
    ID2D1StrokeStyle* strokeStyle = NULL);
```

### <a name="parameters"></a>매개 변수

*ellipse*<br/>
장치 독립적인 픽셀에서 그릴 타원의 위치와 반지름입니다.

*p브러시*<br/>
타원의 윤곽선을 그리는 데 사용되는 브러시입니다.

*f스트로크 폭*<br/>
타원의 스트로크 의 두께입니다. 획은 타원의 윤곽선 가운데 에 배치됩니다.

*스트로크 스타일*<br/>
타원의 윤곽선에 적용할 스트로크 스타일 또는 솔리드 스트로크를 페인칠하는 NULL 스타일입니다.

## <a name="crendertargetdrawgeometry"></a><a name="drawgeometry"></a>CRenderTarget::D원시 지오메트리

지정된 선 스타일을 사용하여 지정된 형상의 윤곽선을 그립니다.

```cpp
void DrawGeometry(
    CD2DGeometry* pGeometry,
    CD2DBrush* pBrush,
    FLOAT fStrokeWidth = 1.0,
    ID2D1StrokeStyle* strokeStyle = NULL);
```

### <a name="parameters"></a>매개 변수

*p지오메지리*<br/>
그릴 형상입니다.

*p브러시*<br/>
형상의 스트로크를 그리는 데 사용되는 브러시입니다.

*f스트로크 폭*<br/>
형상 선의 두께입니다. 획은 형상의 윤곽선에 중심을 두고 있습니다.

*스트로크 스타일*<br/>
형상의 윤곽선에 적용할 스트로크 스타일 또는 솔리드 스트로크를 페인칠하는 NULL입니다.

## <a name="crendertargetdrawglyphrun"></a><a name="drawglyphrun"></a>CRenderTarget::D로글리프런

지정된 글리프를 그립니다.

```cpp
void DrawGlyphRun(
    const CD2DPointF& ptBaseLineOrigin,
    const DWRITE_GLYPH_RUN& glyphRun,
    CD2DBrush* pForegroundBrush,
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```

### <a name="parameters"></a>매개 변수

*ptBaseLineOrigin*<br/>
장치 독립적인 픽셀의 원점은 글리프 기준선입니다.

*Glyphrun*<br/>
렌더링할 글리프입니다.

*p 포그라운드 브러쉬*<br/>
지정된 글리프를 페인칠하는 데 사용되는 브러시입니다.

*측정 모드*<br/>
문자 그림 메트릭이 서식이 지정될 때 텍스트를 측정하는 데 사용되는 방법을 나타내는 값입니다. 기본값은 DWRITE_MEASURING_MODE_NATURAL.

## <a name="crendertargetdrawline"></a><a name="drawline"></a>CRenderTarget::DrawLine

지정된 선 스타일을 사용하여 지정된 점 사이에 선을 그립니다.

```cpp
void DrawLine(
    const CD2DPointF& ptFrom,
    const CD2DPointF& ptTo,
    CD2DBrush* pBrush,
    FLOAT fStrokeWidth = 1.0,
    ID2D1StrokeStyle* strokeStyle = NULL);
```

### <a name="parameters"></a>매개 변수

*ptFrom*<br/>
장치 독립적인 픽셀에서 줄의 시작점입니다.

*ptTo*<br/>
장치 독립적인 픽셀에서 줄의 끝점입니다.

*p브러시*<br/>
선의 스트로크를 그리는 데 사용되는 브러시입니다.

*f스트로크 폭*<br/>
스트로크의 폭을 지정하는 0.0f보다 크거나 같은 값입니다. 이 매개 변수를 지정하지 않으면 기본값은 1.0f입니다. 획은 선의 가운데에 있습니다.

*스트로크 스타일*<br/>
선을 칠할 스트로크 스타일 또는 실선을 페인트할 NULL스타일입니다.

## <a name="crendertargetdrawrectangle"></a><a name="drawrectangle"></a>CRenderTarget::Draw Rectangle

지정된 치수 및 획 스타일이 있는 사각형의 윤곽선을 그립니다.

```cpp
void DrawRectangle(
    const CD2DRectF& rectangle,
    CD2DBrush* pBrush,
    FLOAT fStrokeWidth = 1.0,
    ID2D1StrokeStyle* strokeStyle = NULL);
```

### <a name="parameters"></a>매개 변수

*사각형*<br/>
장치 독립적인 픽셀에서 그리는 사각형의 치수

*p브러시*<br/>
사각형의 스트로크를 그리는 데 사용되는 브러시

*f스트로크 폭*<br/>
사각형 의 스트로크 너비를 지정하는 0.0f보다 크거나 같은 값입니다. 스트로크는 사각형의 윤곽선에 중심을 두고 있습니다.

*스트로크 스타일*<br/>
페인트할 스트로크 스타일 또는 솔리드 스트로크를 페인칠할 NULL스타일입니다.

## <a name="crendertargetdrawroundedrectangle"></a><a name="drawroundedrectangle"></a>CRenderTarget::Drawrounded 사각형

지정된 선 스타일을 사용하여 지정된 둥근 사각형의 윤곽선을 그립니다.

```cpp
void DrawRoundedRectangle(
    const CD2DRoundedRect& rectRounded,
    CD2DBrush* pBrush,
    FLOAT fStrokeWidth = 1.0,
    ID2D1StrokeStyle* strokeStyle = NULL);
```

### <a name="parameters"></a>매개 변수

*정류*<br/>
장치 독립적인 픽셀에서 그릴 둥근 사각형의 크기입니다.

*p브러시*<br/>
둥근 사각형의 윤곽선을 그리는 데 사용되는 브러시입니다.

*f스트로크 폭*<br/>
둥근 사각형의 스트로크의 너비입니다. 획은 둥근 사각형의 윤곽선 가운데 에 배치됩니다. 기본값은 1.0f입니다.

*스트로크 스타일*<br/>
둥근 사각형의 스트로크 스타일 또는 솔리드 스트로크를 페인칠하는 NULL입니다. 기본값은 NULL입니다.

## <a name="crendertargetdrawtext"></a><a name="drawtext"></a>CRenderTarget::DrawText

IDWriteTextFormat 개체에서 제공하는 형식 정보를 사용하여 지정된 텍스트를 그립니다.

```cpp
void DrawText(
    const CString& strText,
    const CD2DRectF& rectangle,
    CD2DBrush* pForegroundBrush,
    CD2DTextFormat* textFormat = NULL,
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE,
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```

### <a name="parameters"></a>매개 변수

*strText*<br/>
그릴 유니코드 문자 배열에 대한 포인터입니다.

*사각형*<br/>
텍스트가 그려지는 영역의 크기와 위치입니다.

*p 포그라운드 브러쉬*<br/>
텍스트를 그리는 데 사용되는 브러시입니다.

*textFormat*<br/>
글꼴, 글꼴 크기 및 흐름 방향과 같이 그릴 텍스트의 서식 세부 정보를 설명하는 개체입니다.

*options*<br/>
텍스트를 픽셀 경계에 스냅할지 여부와 텍스트를 레이아웃 사각형으로 잘라야 하는지 여부를 나타내는 값입니다. 기본값은 D2D1_DRAW_TEXT_OPTIONS_NONE 텍스트가 픽셀 경계에 스냅되어야 하며 레이아웃 사각형으로 잘려서는 안 됨을 나타냅니다.

*측정 모드*<br/>
문자 그림 메트릭이 서식이 지정될 때 텍스트를 측정하는 데 사용되는 방법을 나타내는 값입니다. 기본값은 DWRITE_MEASURING_MODE_NATURAL.

## <a name="crendertargetdrawtextlayout"></a><a name="drawtextlayout"></a>CRenderTarget::Draw텍스트 레이아웃

지정된 IDWriteTextLayout 개체에서 설명하는 서식이 지정된 텍스트를 그립니다.

```cpp
void DrawTextLayout(
    const CD2DPointF& ptOrigin,
    CD2DTextLayout* textLayout,
    CD2DBrush* pBrushForeground,
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE);
```

### <a name="parameters"></a>매개 변수

*ptOrigin*<br/>
textLayout로 설명된 텍스트의 왼쪽 위 모서리가 그려지는 장치 독립적 픽셀에서 설명하는 점입니다.

*텍스트 레이아웃*<br/>
그릴 서식이 지정된 텍스트입니다. ID2D1Resource에서 상속되지 않는 모든 그리기 효과는 무시됩니다. 브러시가 아닌 ID2D1Resource에서 상속되는 그리기 효과가 있는 경우 이 메서드가 실패하고 렌더링 대상이 오류 상태에 놓입니다.

*p브러쉬포그라운드*<br/>
텍스트에 텍스트를 그리는 데 사용되는 브러시아직 그리기 효과로 연결된 브러시가없는 레이아웃 (IDWriteTextLayout:SetDrawingEffect 방법에 의해 지정).

*options*<br/>
텍스트를 픽셀 경계에 스냅할지 여부와 텍스트를 레이아웃 사각형으로 잘라야 하는지 여부를 나타내는 값입니다. 기본값은 D2D1_DRAW_TEXT_OPTIONS_NONE 텍스트가 픽셀 경계에 스냅되어야 하며 레이아웃 사각형으로 잘려서는 안 됨을 나타냅니다.

## <a name="crendertargetenddraw"></a><a name="enddraw"></a>CRenderTarget::끝 그리기

렌더 대상에서 그리기 작업을 종료하고 현재 오류 상태 및 관련 태그를 나타냅니다.

```
HRESULT EndDraw();
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="crendertargetfillellipse"></a><a name="fillellipse"></a>CRenderTarget::필엘립스

지정된 타원의 내부를 페인트합니다.

```cpp
void FillEllipse(
    const CD2DEllipse& ellipse,
    CD2DBrush* pBrush);
```

### <a name="parameters"></a>매개 변수

*ellipse*<br/>
칠할 타원의 장치 독립 픽셀의 위치 및 반지름입니다.

*p브러시*<br/>
타원의 내부를 페인트하는 데 사용되는 브러시입니다.

## <a name="crendertargetfillgeometry"></a><a name="fillgeometry"></a>CRenderTarget::채우기 지오메트리

지정된 형상의 내부를 페인트합니다.

```cpp
void FillGeometry(
    CD2DGeometry* pGeometry,
    CD2DBrush* pBrush,
    CD2DBrush* pOpacityBrush = NULL);
```

### <a name="parameters"></a>매개 변수

*p지오메지리*<br/>
페인트할 형상입니다.

*p브러시*<br/>
지오메트리의 내부를 페인트하는 데 사용되는 브러시입니다.

*포파시티 브러쉬*<br/>
형상에 적용할 불투명도 마스크; 불투명 마스크가 없는 경우 NULL입니다. 불투명도 마스크(불투명브러시 매개 변수)를 지정한 경우 브러시는 x-및 y 확장 모드가 D2D1_EXTEND_MODE_CLAMP 설정된 ID2D1BitmapBrush여야 합니다. 자세한 내용은 주의 섹션을 참조하세요.

## <a name="crendertargetfillmesh"></a><a name="fillmesh"></a>CRenderTarget::채우기 메시

지정된 메시의 내부를 페인트합니다.

```cpp
void FillMesh(
    CD2DMesh* pMesh,
    CD2DBrush* pBrush);
```

### <a name="parameters"></a>매개 변수

*pmesh*<br/>
페인트할 메시입니다.

*p브러시*<br/>
메시를 페인트하는 데 사용되는 브러시입니다.

## <a name="crendertargetfillopacitymask"></a><a name="fillopacitymask"></a>CRenderTarget::필불투명시 마스크

지정된 비트맵에서 설명한 불투명도 마스크를 브러시에 적용하고 해당 브러시를 사용하여 렌더 대상의 영역을 페인팅합니다.

```cpp
void FillOpacityMask(
    CD2DBitmap* pOpacityMask,
    CD2DBrush* pBrush,
    D2D1_OPACITY_MASK_CONTENT content,
    const CD2DRectF& rectDest,
    const CD2DRectF& rectSrc);
```

### <a name="parameters"></a>매개 변수

*포파시티 마스크*<br/>
칠할 타원의 장치 독립 픽셀의 위치 및 반지름입니다.

*p브러시*<br/>
대상에 의해 지정된 렌더 대상의 영역을 페인트하는 데 사용되는 브러시Rectangle.

*content*<br/>
불투명도 마스크에 포함된 콘텐츠 유형입니다. 이 값은 불투명도 마스크가 혼합되는 색상 공간을 결정하는 데 사용됩니다.

*rectDest*<br/>
장치 독립적인 픽셀에서 페인팅할 렌더 대상의 영역입니다.

*rectSrc*<br/>
장치 독립적인 픽셀에서 불투명도 마스크로 사용할 비트맵 영역입니다.

## <a name="crendertargetfillrectangle"></a><a name="fillrectangle"></a>CRenderTarget::채우기 사각형

지정된 사각형의 내부를 페인트합니다.

```cpp
void FillRectangle(
    const CD2DRectF& rectangle,
    CD2DBrush* pBrush);
```

### <a name="parameters"></a>매개 변수

*사각형*<br/>
장치 독립적인 픽셀에서 페인트할 사각형의 치수입니다.

*p브러시*<br/>
사각형의 내부를 페인트하는 데 사용되는 브러시입니다.

## <a name="crendertargetfillroundedrectangle"></a><a name="fillroundedrectangle"></a>CRenderTarget::채우기 둥근 사각형

지정된 둥근 사각형의 내부를 페인트합니다.

```cpp
void FillRoundedRectangle(
    const CD2DRoundedRect& rectRounded,
    CD2DBrush* pBrush);
```

### <a name="parameters"></a>매개 변수

*정류*<br/>
장치 독립 픽셀에서 페인트할 둥근 사각형의 크기입니다.

*p브러시*<br/>
둥근 사각형의 내부를 페인트하는 데 사용되는 브러시입니다.

## <a name="crendertargetflush"></a><a name="flush"></a>CRenderTarget::플러시

보류 중인 모든 그리기 명령을 실행합니다.

```cpp
void Flush(
    D2D1_TAG* tag1 = NULL,
    D2D1_TAG* tag2 = NULL);
```

### <a name="parameters"></a>매개 변수

*태그1*<br/>
오류가 발생한 그리기 작업에 대한 태그 또는 오류가 없는 경우 0을 포함합니다. 이 매개 변수는 초기화되지 않은 상태로 전달됩니다.

*태그2*<br/>
오류가 발생한 그리기 작업에 대한 태그 또는 오류가 없는 경우 0을 포함합니다. 이 매개 변수는 초기화되지 않은 상태로 전달됩니다.

## <a name="crendertargetgetantialiasmode"></a><a name="getantialiasmode"></a>CRenderTarget::GetAntialiasMode

텍스트가 아닌 그리기 작업에 대해 현재 안티 앨리어싱 모드를 검색합니다.

```
D2D1_ANTIALIAS_MODE GetAntialiasMode() const;
```

### <a name="return-value"></a>Return Value

텍스트가 아닌 그리기 작업에 대한 현재 안티 앨리어싱 모드입니다.

## <a name="crendertargetgetdpi"></a><a name="getdpi"></a>CRenderTarget::GetDpi

인치당 렌더 대상의 점 반환(DPI)

```
CD2DSizeF GetDpi() const;
```

### <a name="return-value"></a>Return Value

DPI(인치당 렌더 대상의 점)입니다.

## <a name="crendertargetgetmaximumbitmapsize"></a><a name="getmaximumbitmapsize"></a>C렌더 대상::GetMaximum비트맵크기

렌더 대상에서 지원하는 하나의 비트맵 차원의 장치 종속 단위(픽셀)에서 최대 크기를 가져옵니다.

```
UINT32 GetMaximumBitmapSize() const;
```

### <a name="return-value"></a>Return Value

렌더 대상에서 지원하는 하나의 비트맵 차원의 최대 크기(픽셀 단위)

## <a name="crendertargetgetpixelformat"></a><a name="getpixelformat"></a>CRenderTarget::GetPixelFormat

렌더 대상의 픽셀 형식 및 알파 모드 검색

```
D2D1_PIXEL_FORMAT GetPixelFormat() const;
```

### <a name="return-value"></a>Return Value

렌더 대상의 픽셀 형식 및 알파 모드

## <a name="crendertargetgetpixelsize"></a><a name="getpixelsize"></a>CRenderTarget::GetPixelSize

장치 픽셀에서 렌더링 대상의 크기를 반환합니다.

```
CD2DSizeU GetPixelSize() const;
```

### <a name="return-value"></a>Return Value

장치 픽셀의 렌더 대상 크기

## <a name="crendertargetgetrendertarget"></a><a name="getrendertarget"></a>CRenderTarget::GetRenderTarget

ID2D1RenderTarget 인터페이스 반환

```
ID2D1RenderTarget* GetRenderTarget();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1RenderTarget 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="crendertargetgetsize"></a><a name="getsize"></a>CRenderTarget::GetSize

장치 독립적인 픽셀에서 렌더링 대상의 크기를 반환합니다.

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Return Value

장치 독립적인 픽셀의 렌더 대상의 현재 크기

## <a name="crendertargetgettags"></a><a name="gettags"></a>CRenderTarget::GetTags

후속 그리기 작업에 대한 레이블을 가져옵니다.

```cpp
void GetTags(
    D2D1_TAG* tag1 = NULL,
    D2D1_TAG* tag2 = NULL) const;
```

### <a name="parameters"></a>매개 변수

*태그1*<br/>
후속 그리기 작업에 대한 첫 번째 레이블을 포함합니다. 이 매개 변수는 초기화되지 않은 상태로 전달됩니다. NULL을 지정하면 이 매개 변수에 대한 값이 검색되지 않습니다.

*태그2*<br/>
후속 그리기 작업에 대한 두 번째 레이블을 포함합니다. 이 매개 변수는 초기화되지 않은 상태로 전달됩니다. NULL을 지정하면 이 매개 변수에 대한 값이 검색되지 않습니다.

## <a name="crendertargetgettextantialiasmode"></a><a name="gettextantialiasmode"></a>CRenderTarget::GetTextAntialias모드

텍스트 및 문자 그림 그리기 작업에 대한 현재 안티 앨리어싱 모드를 가져옵니다.

```
D2D1_TEXT_ANTIALIAS_MODE GetTextAntialiasMode() const;
```

### <a name="return-value"></a>Return Value

텍스트 및 문자 그림 그리기 작업에 대한 현재 안티 앨리어싱 모드입니다.

## <a name="crendertargetgettextrenderingparams"></a><a name="gettextrenderingparams"></a>CRenderTarget::GetText렌더링파라름

렌더 대상의 현재 텍스트 렌더링 옵션을 검색합니다.

```cpp
void GetTextRenderingParams(IDWriteRenderingParams** textRenderingParams);
```

### <a name="parameters"></a>매개 변수

*텍스트렌더링파라름*<br/>
이 메서드가 반환 될 때 textRenderingParams 렌더링 대상의 현재 텍스트 렌더링 옵션에 대 한 포인터의 주소를 포함 합니다.

## <a name="crendertargetgettransform"></a><a name="gettransform"></a>CRenderTarget::GetTransform

렌더 대상의 현재 변환을 가져옵니다.

```cpp
void GetTransform(D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>매개 변수

*transform*<br/>
이 반환 될 때 렌더 대상의 현재 변환을 포함 합니다. 이 매개 변수는 초기화되지 않은 상태로 전달됩니다.

## <a name="crendertargetissupported"></a><a name="issupported"></a>CRenderTarget::지원됩니다.

렌더 대상이 지정된 속성을 지원하는지 여부를 나타냅니다.

```
BOOL IsSupported(const D2D1_RENDER_TARGET_PROPERTIES& renderTargetProperties) const;
```

### <a name="parameters"></a>매개 변수

*렌더대상 속성*<br/>
테스트할 렌더 대상 속성

### <a name="return-value"></a>Return Value

TRUE 지정된 렌더 대상 속성이 이 렌더 대상에서 지원되는 경우 그렇지 않으면 FALSE

## <a name="crendertargetisvalid"></a><a name="isvalid"></a>CRenderTarget::유효하지 않음

리소스 유효성 검사

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Return Value

TRUE 리소스가 유효한 경우; 그렇지 않으면 거짓.

## <a name="crendertargetm_lstresources"></a><a name="m_lstresources"></a>CRenderTarget::m_lstResources

CD2DResource 개체에 대한 포인터 목록입니다.

```
CObList m_lstResources;
```

## <a name="crendertargetm_prendertarget"></a><a name="m_prendertarget"></a>CRenderTarget::m_pRenderTarget

ID2D1RenderTarget 개체에 대한 포인터입니다.

```
ID2D1RenderTarget* m_pRenderTarget;
```

## <a name="crendertargetm_ptextformatdefault"></a><a name="m_ptextformatdefault"></a>CRenderTarget::m_pTextFormatDefault

기본 텍스트 형식이 포함된 CD2DTextFormat 개체에 대한 포인터입니다.

```
CD2DTextFormat* m_pTextFormatDefault;
```

## <a name="crendertargetoperator-id2d1rendertarget"></a><a name="operator_id2d1rendertarget_star"></a>CRenderTarget::연산자 ID2D1렌더대상*

ID2D1RenderTarget 인터페이스 반환

```
operator ID2D1RenderTarget*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1RenderTarget 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="crendertargetpopaxisalignedclip"></a><a name="popaxisalignedclip"></a>CRenderTarget::Popaxis정렬 클립

렌더 대상에서 마지막 축 정렬 클립을 제거합니다. 이 메서드를 호출한 후에는 클립이 후속 그리기 작업에 더 이상 적용되지 않습니다.

```cpp
void PopAxisAlignedClip();
```

## <a name="crendertargetpoplayer"></a><a name="poplayer"></a>CRenderTarget::P

마지막 PushLayer 호출에 의해 지정된 도면 작업리디렉션을 중지합니다.

```cpp
void PopLayer();
```

## <a name="crendertargetpushaxisalignedclip"></a><a name="pushaxisalignedclip"></a>CRenderTarget::PushAxis정렬 클립

렌더 대상에서 마지막 축 정렬 클립을 제거합니다. 이 메서드를 호출한 후에는 클립이 후속 그리기 작업에 더 이상 적용되지 않습니다.

```cpp
void PushAxisAlignedClip(
    const CD2DRectF& rectClip,
    D2D1_ANTIALIAS_MODE mode = D2D1_ANTIALIAS_MODE_PER_PRIMITIVE);
```

### <a name="parameters"></a>매개 변수

*렉클립*<br/>
장치 독립적인 픽셀에서 클리핑 영역의 크기와 위치입니다.

*모드*<br/>
하위 픽셀 경계가 있는 클립 사각형의 가장자리를 그리고 클립과 장면 내용을 혼합하는 데 사용되는 안티 앨리어싱 모드입니다. 혼합은 PopAxisAlignedClip 메서드가 호출될 때 한 번 수행되며 레이어 내의 각 기본 에 적용되지 않습니다.

## <a name="crendertargetpushlayer"></a><a name="pushlayer"></a>CRenderTarget::P허슬레이어

PopLayer가 호출될 때까지 모든 후속 그리기 작업을 수신하도록 지정된 레이어를 렌더 대상에 추가합니다.

```cpp
void PushLayer(
    const D2D1_LAYER_PARAMETERS& layerParameters,
    CD2DLayer& layer);
```

### <a name="parameters"></a>매개 변수

*레이어매개 변수*<br/>
콘텐츠 경계, 기하학적 마스크, 불투명도, 불투명도 마스크 및 레이어에 대한 안티 앨리어싱 옵션입니다.

*계층(layer)*<br/>
후속 그리기 작업을 받는 도면층입니다.

## <a name="crendertargetrestoredrawingstate"></a><a name="restoredrawingstate"></a>CRenderTarget::복원 그리기 상태

렌더 대상의 그리기 상태를 지정된 ID2D1DrawingStateBlock의 로 설정합니다.

```cpp
void RestoreDrawingState(ID2D1DrawingStateBlock& drawingStateBlock);
```

### <a name="parameters"></a>매개 변수

*드로잉상태 차단*<br/>
렌더 대상의 새 그리기 상태입니다.

## <a name="crendertargetsavedrawingstate"></a><a name="savedrawingstate"></a>CRenderTarget::저장 그리기 상태

현재 도면 상태를 지정된 ID2D1DrawingStateBlock에 저장합니다.

```cpp
void SaveDrawingState(ID2D1DrawingStateBlock& drawingStateBlock) const;
```

### <a name="parameters"></a>매개 변수

*드로잉상태 차단*<br/>
이 메서드가 반환되면 렌더 대상의 현재 그리기 상태가 포함됩니다. 이 매개 변수는 메서드에 전달하기 전에 초기화되어야 합니다.

## <a name="crendertargetsetantialiasmode"></a><a name="setantialiasmode"></a>CRenderTarget::SetAntialiasMode

렌더 대상의 안티 앨리어싱 모드를 설정합니다. 안티 앨리어싱 모드는 텍스트 및 문자 모양 그리기 작업을 제외한 모든 후속 그리기 작업에 적용됩니다.

```cpp
void SetAntialiasMode(D2D1_ANTIALIAS_MODE antialiasMode);
```

### <a name="parameters"></a>매개 변수

*안티알리아스모드*<br/>
향후 그리기 작업에 대한 안티 앨리어싱 모드입니다.

## <a name="crendertargetsetdpi"></a><a name="setdpi"></a>CRenderTarget::SetDpi

렌더 대상의 인치당 점(DPI)을 설정합니다.

```cpp
void SetDpi(const CD2DSizeF& sizeDPI);
```

### <a name="parameters"></a>매개 변수

*sizeDPI*<br/>
렌더 대상의 가로/세로DPI를 지정하는 0보다 크거나 같을 값입니다.

## <a name="crendertargetsettags"></a><a name="settags"></a>CRenderTarget::SetTags

후속 그리기 작업에 대한 레이블을 지정합니다.

```cpp
void SetTags(
    D2D1_TAG tag1,
    D2D1_TAG tag2);
```

### <a name="parameters"></a>매개 변수

*태그1*<br/>
후속 도면 작업에 적용할 레이블입니다.

*태그2*<br/>
후속 도면 작업에 적용할 레이블입니다.

## <a name="crendertargetsettextantialiasmode"></a><a name="settextantialiasmode"></a>CRenderTarget::SetText안티알리아스모드

후속 텍스트 및 문자 그림 그리기 작업에 사용할 안티 앨리어싱 모드를 지정합니다.

```cpp
void SetTextAntialiasMode(D2D1_TEXT_ANTIALIAS_MODE textAntialiasMode);
```

### <a name="parameters"></a>매개 변수

*텍스트안티알리아스모드*<br/>
후속 텍스트 및 문자 그림 그리기 작업에 사용할 안티 앨리어싱 모드입니다.

## <a name="crendertargetsettextrenderingparams"></a><a name="settextrenderingparams"></a>CRenderTarget::SetText렌더링파라름

이후의 모든 텍스트 및 문자 그림 그리기 작업에 적용할 텍스트 렌더링 옵션을 지정합니다.

```cpp
void SetTextRenderingParams(IDWriteRenderingParams* textRenderingParams = NULL);
```

### <a name="parameters"></a>매개 변수

*텍스트렌더링파라름*<br/>
이후의 모든 텍스트 및 문자 그림 그리기 작업에 적용할 텍스트 렌더링 옵션; NULL을 사용하여 현재 텍스트 렌더링 옵션을 지웁히 지웁습니다.

## <a name="crendertargetsettransform"></a><a name="settransform"></a>CRenderTarget::세트 변환

지정된 변환을 기존 변환을 대체하여 렌더 대상에 적용합니다. 이후의 모든 그리기 작업은 변환된 공간에서 발생합니다.

```cpp
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
void SetTransform(const D2D1_MATRIX_3X2_F& transform);
```

### <a name="parameters"></a>매개 변수

*transform*<br/>
렌더링 대상에 적용할 변환입니다.

## <a name="crendertargetverifyresource"></a><a name="verifyresource"></a>CRenderTarget::검증 리소스

CD2DResource 개체 유효성을 확인합니다. 개체가 아직 존재하지 않는 경우 개체를 만듭니다.

```
BOOL VerifyResource(CD2DResource* pResource);
```

### <a name="parameters"></a>매개 변수

*Presource*<br/>
CD2DResource 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE가 유효한 경우 개체입니다. 그렇지 않으면 거짓.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
