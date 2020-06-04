---
title: CD2DGradientBrush 클래스
ms.date: 03/27/2019
f1_keywords:
- CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::Destroy
- AFXRENDERTARGET/CD2DGradientBrush::m_arGradientStops
- AFXRENDERTARGET/CD2DGradientBrush::m_colorInterpolationGamma
- AFXRENDERTARGET/CD2DGradientBrush::m_extendMode
- AFXRENDERTARGET/CD2DGradientBrush::m_pGradientStops
helpviewer_keywords:
- CD2DGradientBrush [MFC], CD2DGradientBrush
- CD2DGradientBrush [MFC], Destroy
- CD2DGradientBrush [MFC], m_arGradientStops
- CD2DGradientBrush [MFC], m_colorInterpolationGamma
- CD2DGradientBrush [MFC], m_extendMode
- CD2DGradientBrush [MFC], m_pGradientStops
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
ms.openlocfilehash: 861bc32382737bd6482a3d51eb8470bf834e8508
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369225"
---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush 클래스

CD2DLinearGradient브러시및CD2DRadialGradient브러시 클래스의 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CD2DGradientBrush : public CD2DBrush;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D그라디엔트 브러쉬::CD2D그라디언트 브러쉬](#cd2dgradientbrush)|CD2DGradient브러시 오브젝트를 생성합니다.|
|[CD2D그라디엔트 브러쉬::~CD2D그라디언트 브러쉬](#_dtorcd2dgradientbrush)|소멸자입니다. D2D 그라데이션 브러시 오브젝트가 소멸될 때 호출됩니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CD2D그라디엔트 브러쉬::D에스트로이](#destroy)|CD2DGradient브러시 오브젝트를 삭제합니다. [(CD2D브러시::D에스트로이](../../mfc/reference/cd2dbrush-class.md#destroy)재사용.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D그라디언트 브러쉬::m_arGradientStops](#m_argradientstops)|D2D1_GRADIENT_STOP 구조의 배열입니다.|
|[CD2D그라디언트 브러쉬::m_colorInterpolationGamma](#m_colorinterpolationgamma)|그라데이션 정지 사이의 색상 보간이 수행되는 공간입니다.|
|[CD2D그라디언트 브러쉬::m_extendMode](#m_extendmode)|정규화된 범위를 벗어난 그라데이션의 동작입니다.|
|[CD2D그라디언트 브러쉬::m_pGradientStops](#m_pgradientstops)|D2D1_GRADIENT_STOP 구조의 배열에 대한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

[CD2D브러시](../../mfc/reference/cd2dbrush-class.md)

`CD2DGradientBrush`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="_dtorcd2dgradientbrush"></a>CD2D그라디엔트 브러쉬::~CD2D그라디언트 브러쉬

소멸자입니다. D2D 그라데이션 브러시 오브젝트가 소멸될 때 호출됩니다.

```
virtual ~CD2DGradientBrush();
```

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="cd2dgradientbrush"></a>CD2D그라디엔트 브러쉬::CD2D그라디언트 브러쉬

CD2DGradient브러시 오브젝트를 생성합니다.

```
CD2DGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
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

*색상인터폴레이션감마*<br/>
그라데이션 정지 사이의 색상 보간이 수행되는 공간입니다.

*확장 모드*<br/>
정규화된 범위를 벗어난 그라데이션의 동작입니다.

*p브러시프로퍼티*<br/>
브러시의 불투명도 및 변환에 대한 포인터입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

## <a name="cd2dgradientbrushdestroy"></a><a name="destroy"></a>CD2D그라디엔트 브러쉬::D에스트로이

CD2DGradient브러시 오브젝트를 삭제합니다.

```
virtual void Destroy();
```

## <a name="cd2dgradientbrushm_argradientstops"></a><a name="m_argradientstops"></a>CD2D그라디언트 브러쉬::m_arGradientStops

D2D1_GRADIENT_STOP 구조의 배열입니다.

```
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;
```

## <a name="cd2dgradientbrushm_colorinterpolationgamma"></a><a name="m_colorinterpolationgamma"></a>CD2D그라디언트 브러쉬::m_colorInterpolationGamma

그라데이션 정지 사이의 색상 보간이 수행되는 공간입니다.

```
D2D1_GAMMA m_colorInterpolationGamma;
```

## <a name="cd2dgradientbrushm_extendmode"></a><a name="m_extendmode"></a>CD2D그라디언트 브러쉬::m_extendMode

정규화된 범위를 벗어난 그라데이션의 동작입니다.

```
D2D1_EXTEND_MODE m_extendMode;
```

## <a name="cd2dgradientbrushm_pgradientstops"></a><a name="m_pgradientstops"></a>CD2D그라디언트 브러쉬::m_pGradientStops

D2D1_GRADIENT_STOP 구조의 배열에 대한 포인터입니다.

```
ID2D1GradientStopCollection* m_pGradientStops;
```

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
