---
title: CD2DRadialGradientBrush 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::Attach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Create
- AFXRENDERTARGET/CD2DRadialGradientBrush::Destroy
- AFXRENDERTARGET/CD2DRadialGradientBrush::Detach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Get
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_pRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_RadialGradientBrushProperties
helpviewer_keywords:
- CD2DRadialGradientBrush [MFC], CD2DRadialGradientBrush
- CD2DRadialGradientBrush [MFC], Attach
- CD2DRadialGradientBrush [MFC], Create
- CD2DRadialGradientBrush [MFC], Destroy
- CD2DRadialGradientBrush [MFC], Detach
- CD2DRadialGradientBrush [MFC], Get
- CD2DRadialGradientBrush [MFC], GetCenter
- CD2DRadialGradientBrush [MFC], GetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], GetRadiusX
- CD2DRadialGradientBrush [MFC], GetRadiusY
- CD2DRadialGradientBrush [MFC], SetCenter
- CD2DRadialGradientBrush [MFC], SetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], SetRadiusX
- CD2DRadialGradientBrush [MFC], SetRadiusY
- CD2DRadialGradientBrush [MFC], m_pRadialGradientBrush
- CD2DRadialGradientBrush [MFC], m_RadialGradientBrushProperties
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
ms.openlocfilehash: 450314fdbf8441b0cc345430518d083573659add
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750310"
---
# <a name="cd2dradialgradientbrush-class"></a>CD2DRadialGradientBrush 클래스

ID2D1RadialGradient브러시용 래퍼.

## <a name="syntax"></a>구문

```
class CD2DRadialGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2DRadial그라데이션 브러쉬::CD2DRadial그라데이션 브러쉬](#cd2dradialgradientbrush)|CD2DLinearGradient브러시 오브젝트를 생성합니다.|
|[CD2DRadial그라데이션 브러쉬:~~CD2DRadial그라데이션 브러쉬](#_dtorcd2dradialgradientbrush)|소멸자입니다. D2D 방사형 그라데이션 브러시 오브젝트가 파괴될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2DRadial그라데이션 브러시::연결](#attach)|기존 리소스 인터페이스를 개체에 연결합니다.|
|[CD2DRadial그라데이션 브러시::만들기](#create)|CD2DRadialGradient브러시를 만듭니다. [(CD2DResource::만들기](../../mfc/reference/cd2dresource-class.md#create)재정의.)|
|[CD2DRadial그라데이션 브러쉬::D에스트로이](#destroy)|CD2DRadialGradient브러시 오브젝트를 파괴합니다. [(CD2DGradient브러시::Destroy.)](../../mfc/reference/cd2dgradientbrush-class.md#destroy)|
|[CD2DRadial그라데이션 브러쉬::D에타치](#detach)|개체에서 리소스 인터페이스 분리|
|[CD2DRadial그라데이션 브러쉬::Get](#get)|ID2D1RadialGradient브러시 인터페이스 반환|
|[CD2DRadial그라데이션 브러쉬::겟센터](#getcenter)|그라데이션 타원의 중심을 검색합니다.|
|[CD2DRadial그라데이션 브러쉬::겟그라디엔트원산지오프셋](#getgradientoriginoffset)|그라데이션 타원의 중심을 기준으로 그라데이션 원점의 오프셋을 검색합니다.|
|[CD2DRadial그라데이션 브러쉬::겟라디우스X](#getradiusx)|그라데이션 타원의 x 반지름을 검색합니다.|
|[CD2DRadial그라데이션 브러쉬::GetRadiusY](#getradiusy)|그라데이션 타원의 y 반지름을 검색합니다.|
|[CD2DRadial그라데이션 브러쉬::세트센터](#setcenter)|브러시좌표 공간에서 그라데이션 타원의 중심을 지정합니다.|
|[CD2DRadial그라디언트 브러시::세트그라디엔테이션원산지](#setgradientoriginoffset)|그라데이션 타원의 중심을 기준으로 그라데이션 원점의 간격띄우기를 지정합니다.|
|[CD2DRadial그라데이션 브러시::세트배엽X](#setradiusx)|브러시의 좌표 공간에서 그라데이션 타원의 x 반지름을 지정합니다.|
|[CD2DRadial그라데이션 브러시::세트배엽](#setradiusy)|브러시의 좌표 공간에서 그라데이션 타원의 y 반지름을 지정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2DRadial그라데이션 브러쉬::연산자 ID2D1RadialGradient브러시*](#operator_id2d1radialgradientbrush_star)|ID2D1RadialGradient브러시 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2DRadial그라데이션 브러쉬::m_pRadialGradientBrush](#m_pradialgradientbrush)|ID2D1RadialGradient브러시에 대한 포인터입니다.|
|[CD2DRadial그라데이션 브러쉬::m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|브러시 그라데이션의 중심, 그라데이션 원점 간격띄우기 및 x 반지름 및 y 반지름입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

[CD2D브러시](../../mfc/reference/cd2dbrush-class.md)

[CD2D그라디엔트 브러쉬](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DRadialGradientBrush`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="_dtorcd2dradialgradientbrush"></a>CD2DRadial그라데이션 브러쉬:~~CD2DRadial그라데이션 브러쉬

소멸자입니다. D2D 방사형 그라데이션 브러시 오브젝트가 파괴될 때 호출됩니다.

```
virtual ~CD2DRadialGradientBrush();
```

## <a name="cd2dradialgradientbrushattach"></a><a name="attach"></a>CD2DRadial그라데이션 브러시::연결

기존 리소스 인터페이스를 개체에 연결합니다.

```cpp
void Attach(ID2D1RadialGradientBrush* pResource);
```

### <a name="parameters"></a>매개 변수

*Presource*<br/>
기존 리소스 인터페이스입니다. NULL일 수 없음

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="cd2dradialgradientbrush"></a>CD2DRadial그라데이션 브러쉬::CD2DRadial그라데이션 브러쉬

CD2DLinearGradient브러시 오브젝트를 생성합니다.

```
CD2DRadialGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES RadialGradientBrushProperties,
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*p부모 대상*<br/>
렌더 대상에 대한 포인터입니다.

*그라데이션스톱*<br/>
D2D1_GRADIENT_STOP 구조의 배열에 대한 포인터입니다.

*그라데이션스스카운트*<br/>
그라데이션Stops 배열에서 그라데이션 스톱 수를 지정하는 값보다 크거나 1과 같은 값입니다.

*방사형 그라데이션 브러쉬프로퍼티*<br/>
브러시 그라데이션의 중심, 그라데이션 원점 간격띄우기 및 x 반지름 및 y 반지름입니다.

*색상인터폴레이션감마*<br/>
그라데이션 정지 사이의 색상 보간이 수행되는 공간입니다.

*확장 모드*<br/>
정규화된 범위를 벗어난 그라데이션의 동작입니다.

*p브러시프로퍼티*<br/>
브러시의 불투명도 및 변환에 대한 포인터입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

## <a name="cd2dradialgradientbrushcreate"></a><a name="create"></a>CD2DRadial그라데이션 브러시::만들기

CD2DRadialGradient브러시를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*p렌더대상*<br/>
렌더 대상에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dradialgradientbrushdestroy"></a><a name="destroy"></a>CD2DRadial그라데이션 브러쉬::D에스트로이

CD2DRadialGradient브러시 오브젝트를 파괴합니다.

```
virtual void Destroy();
```

## <a name="cd2dradialgradientbrushdetach"></a><a name="detach"></a>CD2DRadial그라데이션 브러쉬::D에타치

개체에서 리소스 인터페이스 분리

```
ID2D1RadialGradientBrush* Detach();
```

### <a name="return-value"></a>Return Value

분리된 리소스 인터페이스에 대한 포인터입니다.

## <a name="cd2dradialgradientbrushget"></a><a name="get"></a>CD2DRadial그라데이션 브러쉬::Get

ID2D1RadialGradient브러시 인터페이스 반환

```
ID2D1RadialGradientBrush* Get();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1RadialGradientientBrush 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dradialgradientbrushgetcenter"></a><a name="getcenter"></a>CD2DRadial그라데이션 브러쉬::겟센터

그라데이션 타원의 중심을 검색합니다.

```
CD2DPointF GetCenter() const;
```

### <a name="return-value"></a>Return Value

그라데이션 타원의 중심입니다. 이 값은 브러시의 좌표 공간에 표현됩니다.

## <a name="cd2dradialgradientbrushgetgradientoriginoffset"></a><a name="getgradientoriginoffset"></a>CD2DRadial그라데이션 브러쉬::겟그라디엔트원산지오프셋

그라데이션 타원의 중심을 기준으로 그라데이션 원점의 오프셋을 검색합니다.

```
CD2DPointF GetGradientOriginOffset() const;
```

### <a name="return-value"></a>Return Value

그라데이션 타원의 중심에서 그라데이션 원원의 간격띄우기입니다. 이 값은 브러시의 좌표 공간에 표현됩니다.

## <a name="cd2dradialgradientbrushgetradiusx"></a><a name="getradiusx"></a>CD2DRadial그라데이션 브러쉬::겟라디우스X

그라데이션 타원의 x 반지름을 검색합니다.

```
FLOAT GetRadiusX() const;
```

### <a name="return-value"></a>Return Value

그라데이션 타원의 x 반지름입니다. 이 값은 브러시의 좌표 공간에 표현됩니다.

## <a name="cd2dradialgradientbrushgetradiusy"></a><a name="getradiusy"></a>CD2DRadial그라데이션 브러쉬::GetRadiusY

그라데이션 타원의 y 반지름을 검색합니다.

```
FLOAT GetRadiusY() const;
```

### <a name="return-value"></a>Return Value

그라데이션 타원의 y 반지름입니다. 이 값은 브러시의 좌표 공간에 표현됩니다.

## <a name="cd2dradialgradientbrushm_pradialgradientbrush"></a><a name="m_pradialgradientbrush"></a>CD2DRadial그라데이션 브러쉬::m_pRadialGradientBrush

ID2D1RadialGradient브러시에 대한 포인터입니다.

```
ID2D1RadialGradientBrush* m_pRadialGradientBrush;
```

## <a name="cd2dradialgradientbrushm_radialgradientbrushproperties"></a><a name="m_radialgradientbrushproperties"></a>CD2DRadial그라데이션 브러쉬::m_RadialGradientBrushProperties

브러시 그라데이션의 중심, 그라데이션 원점 간격띄우기 및 x 반지름 및 y 반지름입니다.

```
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;
```

## <a name="cd2dradialgradientbrushoperator-id2d1radialgradientbrush"></a><a name="operator_id2d1radialgradientbrush_star"></a>CD2DRadial그라데이션 브러쉬::연산자 ID2D1RadialGradient브러시*

ID2D1RadialGradient브러시 인터페이스 반환

```
operator ID2D1RadialGradientBrush*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1RadialGradientientBrush 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dradialgradientbrushsetcenter"></a><a name="setcenter"></a>CD2DRadial그라데이션 브러쉬::세트센터

브러시좌표 공간에서 그라데이션 타원의 중심을 지정합니다.

```cpp
void SetCenter(CD2DPointF point);
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
브러시의 좌표 공간에서 그라데이션 타원의 중심

## <a name="cd2dradialgradientbrushsetgradientoriginoffset"></a><a name="setgradientoriginoffset"></a>CD2DRadial그라디언트 브러시::세트그라디엔테이션원산지

그라데이션 타원의 중심을 기준으로 그라데이션 원점의 간격띄우기를 지정합니다.

```cpp
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```

### <a name="parameters"></a>매개 변수

*그라데이션원산지오프셋*<br/>
그라데이션 타원의 중심에서 그라데이션 원원의 간격띄우기

## <a name="cd2dradialgradientbrushsetradiusx"></a><a name="setradiusx"></a>CD2DRadial그라데이션 브러시::세트배엽X

브러시의 좌표 공간에서 그라데이션 타원의 x 반지름을 지정합니다.

```cpp
void SetRadiusX(FLOAT radiusX);
```

### <a name="parameters"></a>매개 변수

*반경 X*<br/>
그라데이션 타원의 x 반지름입니다. 이 값은 브러시의 좌표 공간에 있습니다.

## <a name="cd2dradialgradientbrushsetradiusy"></a><a name="setradiusy"></a>CD2DRadial그라데이션 브러시::세트배엽

브러시의 좌표 공간에서 그라데이션 타원의 y 반지름을 지정합니다.

```cpp
void SetRadiusY(FLOAT radiusY);
```

### <a name="parameters"></a>매개 변수

*반경*<br/>
그라데이션 타원의 y 반지름입니다. 이 값은 브러시의 좌표 공간에 있습니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
