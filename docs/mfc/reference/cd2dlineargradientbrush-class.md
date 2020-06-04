---
title: CD2DLinearGradientBrush 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::Attach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Create
- AFXRENDERTARGET/CD2DLinearGradientBrush::Destroy
- AFXRENDERTARGET/CD2DLinearGradientBrush::Detach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Get
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_LinearGradientBrushProperties
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_pLinearGradientBrush
helpviewer_keywords:
- CD2DLinearGradientBrush [MFC], CD2DLinearGradientBrush
- CD2DLinearGradientBrush [MFC], Attach
- CD2DLinearGradientBrush [MFC], Create
- CD2DLinearGradientBrush [MFC], Destroy
- CD2DLinearGradientBrush [MFC], Detach
- CD2DLinearGradientBrush [MFC], Get
- CD2DLinearGradientBrush [MFC], GetEndPoint
- CD2DLinearGradientBrush [MFC], GetStartPoint
- CD2DLinearGradientBrush [MFC], SetEndPoint
- CD2DLinearGradientBrush [MFC], SetStartPoint
- CD2DLinearGradientBrush [MFC], m_LinearGradientBrushProperties
- CD2DLinearGradientBrush [MFC], m_pLinearGradientBrush
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
ms.openlocfilehash: d87cdae5c24eae391be8db2fcdd04f91d592e427
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753163"
---
# <a name="cd2dlineargradientbrush-class"></a>CD2DLinearGradientBrush 클래스

ID2D1LinearGradient브러시용 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DLinearGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2DLinear그라데이션 브러시::CD2D선형그라데이션 브러시](#cd2dlineargradientbrush)|CD2DLinearGradient브러시 오브젝트를 생성합니다.|
|[CD2DLinear그라데이션 브러시::~CD2DLinearGradient브러시](#_dtorcd2dlineargradientbrush)|소멸자입니다. D2D 선형 그라데이션 브러시 오브젝트가 소멸될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2D선형 그라데이션 브러시::연결](#attach)|기존 리소스 인터페이스를 개체에 연결합니다.|
|[CD2D선형 그라데이션 브러시::만들기](#create)|CD2DLinearGradient브러시를 만듭니다. [(CD2DResource::만들기](../../mfc/reference/cd2dresource-class.md#create)재정의.)|
|[CD2D리니어그라디언트 브러쉬::D에스트로이](#destroy)|CD2DLinearGradient브러시 오브젝트를 삭제합니다. [(CD2DGradient브러시::Destroy.)](../../mfc/reference/cd2dgradientbrush-class.md#destroy)|
|[CD2D리니어그라디언트 브러쉬::D에타치](#detach)|개체에서 리소스 인터페이스 분리|
|[CD2D선형 그라데이션 브러시::Get](#get)|ID2D1선형그라데이션 브러시 인터페이스 반환|
|[CD2D선형 그라데이션 브러시::GetEndPoint](#getendpoint)|선형 그라데이션의 끝 좌표를 검색합니다.|
|[CD2D선형 그라데이션 브러시::GetStartPoint](#getstartpoint)|선형 그라데이션의 시작 좌표를 검색합니다.|
|[CD2D선형 그라데이션 브러시::설정 끝점](#setendpoint)|브러시의 좌표 공간에서 선형 그라데이션의 끝 좌표 설정|
|[CD2D선형 그라데이션 브러시::셋스타트포인트](#setstartpoint)|브러시좌표 공간에서 선형 그라데이션의 시작 좌표 설정|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2DLinearGradient브러시::연산자 ID2D1Linear그라디언트 브러시*](#operator_id2d1lineargradientbrush_star)|ID2D1선형그라데이션 브러시 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D선형그라데이션 브러시::m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|그라데이션의 시작점과 끝점입니다.|
|[CD2D선형그라데이션 브러시::m_pLinearGradientBrush](#m_plineargradientbrush)|ID2D1LinearGradient브러시에 대한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

[CD2D브러시](../../mfc/reference/cd2dbrush-class.md)

[CD2D그라디엔트 브러쉬](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DLinearGradientBrush`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="_dtorcd2dlineargradientbrush"></a>CD2DLinear그라데이션 브러시::~CD2DLinearGradient브러시

소멸자입니다. D2D 선형 그라데이션 브러시 오브젝트가 소멸될 때 호출됩니다.

```
virtual ~CD2DLinearGradientBrush();
```

## <a name="cd2dlineargradientbrushattach"></a><a name="attach"></a>CD2D선형 그라데이션 브러시::연결

기존 리소스 인터페이스를 개체에 연결합니다.

```cpp
void Attach(ID2D1LinearGradientBrush* pResource);
```

### <a name="parameters"></a>매개 변수

*Presource*<br/>
기존 리소스 인터페이스입니다. NULL일 수 없음

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="cd2dlineargradientbrush"></a>CD2DLinear그라데이션 브러시::CD2D선형그라데이션 브러시

CD2DLinearGradient브러시 오브젝트를 생성합니다.

```
CD2DLinearGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES LinearGradientBrushProperties,
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

*선형 그라데이션 브러시 속성*<br/>
그라데이션의 시작점과 끝점입니다.

*색상인터폴레이션감마*<br/>
그라데이션 정지 사이의 색상 보간이 수행되는 공간입니다.

*확장 모드*<br/>
정규화된 범위를 벗어난 그라데이션의 동작입니다.

*p브러시프로퍼티*<br/>
브러시의 불투명도 및 변환에 대한 포인터입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

## <a name="cd2dlineargradientbrushcreate"></a><a name="create"></a>CD2D선형 그라데이션 브러시::만들기

CD2DLinearGradient브러시를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*p렌더대상*<br/>
렌더 대상에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dlineargradientbrushdestroy"></a><a name="destroy"></a>CD2D리니어그라디언트 브러쉬::D에스트로이

CD2DLinearGradient브러시 오브젝트를 삭제합니다.

```
virtual void Destroy();
```

## <a name="cd2dlineargradientbrushdetach"></a><a name="detach"></a>CD2D리니어그라디언트 브러쉬::D에타치

개체에서 리소스 인터페이스 분리

```
ID2D1LinearGradientBrush* Detach();
```

### <a name="return-value"></a>Return Value

분리된 리소스 인터페이스에 대한 포인터입니다.

## <a name="cd2dlineargradientbrushget"></a><a name="get"></a>CD2D선형 그라데이션 브러시::Get

ID2D1선형그라데이션 브러시 인터페이스 반환

```
ID2D1LinearGradientBrush* Get();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1LinearGradient브러시 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dlineargradientbrushgetendpoint"></a><a name="getendpoint"></a>CD2D선형 그라데이션 브러시::GetEndPoint

선형 그라데이션의 끝 좌표를 검색합니다.

```
CD2DPointF GetEndPoint() const;
```

### <a name="return-value"></a>Return Value

브러시의 좌표 공간에서 선형 그라데이션의 끝 2차원 좌표

## <a name="cd2dlineargradientbrushgetstartpoint"></a><a name="getstartpoint"></a>CD2D선형 그라데이션 브러시::GetStartPoint

선형 그라데이션의 시작 좌표를 검색합니다.

```
CD2DPointF GetStartPoint() const;
```

### <a name="return-value"></a>Return Value

브러시의 좌표 공간에서 선형 그라데이션의 시작 2차원 좌표

## <a name="cd2dlineargradientbrushm_lineargradientbrushproperties"></a><a name="m_lineargradientbrushproperties"></a>CD2D선형그라데이션 브러시::m_LinearGradientBrushProperties

그라데이션의 시작점과 끝점입니다.

```
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;
```

## <a name="cd2dlineargradientbrushm_plineargradientbrush"></a><a name="m_plineargradientbrush"></a>CD2D선형그라데이션 브러시::m_pLinearGradientBrush

ID2D1LinearGradient브러시에 대한 포인터입니다.

```
ID2D1LinearGradientBrush* m_pLinearGradientBrush;
```

## <a name="cd2dlineargradientbrushoperator-id2d1lineargradientbrush"></a><a name="operator_id2d1lineargradientbrush_star"></a>CD2DLinearGradient브러시::연산자 ID2D1Linear그라디언트 브러시*

ID2D1선형그라데이션 브러시 인터페이스 반환

```
operator ID2D1LinearGradientBrush*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1LinearGradient브러시 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dlineargradientbrushsetendpoint"></a><a name="setendpoint"></a>CD2D선형 그라데이션 브러시::설정 끝점

브러시의 좌표 공간에서 선형 그라데이션의 끝 좌표 설정

```cpp
void SetEndPoint(CD2DPointF point);
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
브러시의 좌표 공간에서 선형 그라데이션의 끝 2차원 좌표

## <a name="cd2dlineargradientbrushsetstartpoint"></a><a name="setstartpoint"></a>CD2D선형 그라데이션 브러시::셋스타트포인트

브러시좌표 공간에서 선형 그라데이션의 시작 좌표 설정

```cpp
void SetStartPoint(CD2DPointF point);
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
브러시의 좌표 공간에서 선형 그라데이션의 시작 2차원 좌표

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
