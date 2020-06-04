---
title: CD2DBrush 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
helpviewer_keywords:
- CD2DBrush [MFC], CD2DBrush
- CD2DBrush [MFC], Attach
- CD2DBrush [MFC], Destroy
- CD2DBrush [MFC], Detach
- CD2DBrush [MFC], Get
- CD2DBrush [MFC], GetOpacity
- CD2DBrush [MFC], GetTransform
- CD2DBrush [MFC], IsValid
- CD2DBrush [MFC], SetOpacity
- CD2DBrush [MFC], SetTransform
- CD2DBrush [MFC], m_pBrush
- CD2DBrush [MFC], m_pBrushProperties
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
ms.openlocfilehash: 536d84fe2c2f68d62490e1ce2b65085426762e87
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754201"
---
# <a name="cd2dbrush-class"></a>CD2DBrush 클래스

ID2D1브러시용 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DBrush : public CD2DResource;
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CD2D 브러시 : : CD2D 브러시](#cd2dbrush)|CD2DBrush 개체를 생성합니다.|
|[CD2D 브러시 : : ~ CD2D 브러시](#_dtorcd2dbrush)|소멸자입니다. D2D 브러시 개체가 파괴될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2D브러시::연결](#attach)|기존 리소스 인터페이스를 개체에 연결합니다.|
|[CD2D브러시::D에스트로이](#destroy)|CD2DBrush 개체를 삭제합니다. [(CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy)재정의.)|
|[CD2D브러쉬: :D에타치](#detach)|개체에서 리소스 인터페이스 분리|
|[CD2D 브러시 : : 가져옵니다](#get)|ID2D1브러시 인터페이스 반환|
|[CD2D브러쉬::게파시티](#getopacity)|이 브러시의 불투명도도를 가져옵니다.|
|[CD2D브러시::겟트랜스포메이션](#gettransform)|렌더 대상의 현재 변환을 가져옵니다.|
|[CD2D브러시::유효하지 않음](#isvalid)|리소스 유효성 [검사(CD2DResource 재정의::유효합니다.)](../../mfc/reference/cd2dresource-class.md#isvalid)|
|[CD2D브러시::셋오파시티](#setopacity)|이 브러시의 불투명도 도 설정|
|[CD2D브러시::세트변환](#settransform)|지정된 변환을 기존 변환을 대체하여 렌더 대상에 적용합니다. 이후의 모든 그리기 작업은 변환된 공간에서 발생합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2D브러시::연산자 ID2D1브러시*](#operator_id2d1brush_star)|ID2D1브러시 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D브러시:m_pBrush](#m_pbrush)|ID2D1Brush 개체에 대한 포인터를 저장합니다.|
|[CD2D브러시:m_pBrushProperties](#m_pbrushproperties)|브러시 속성입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

`CD2DBrush`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dbrushcd2dbrush"></a><a name="_dtorcd2dbrush"></a>CD2D 브러시 : : ~ CD2D 브러시

소멸자입니다. D2D 브러시 개체가 파괴될 때 호출됩니다.

```
virtual ~CD2DBrush();
```

## <a name="cd2dbrushattach"></a><a name="attach"></a>CD2D브러시::연결

기존 리소스 인터페이스를 개체에 연결합니다.

```cpp
void Attach(ID2D1Brush* pResource);
```

### <a name="parameters"></a>매개 변수

*Presource*<br/>
기존 리소스 인터페이스입니다. NULL이 될 수 없습니다.

## <a name="cd2dbrushcd2dbrush"></a><a name="cd2dbrush"></a>CD2D 브러시 : : CD2D 브러시

CD2DBrush 개체를 생성합니다.

```
CD2DBrush(
    CRenderTarget* pParentTarget,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*p부모 대상*<br/>
렌더 대상에 대한 포인터입니다.

*p브러시프로퍼티*<br/>
브러시의 불투명도 및 변환에 대한 포인터입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

## <a name="cd2dbrushdestroy"></a><a name="destroy"></a>CD2D브러시::D에스트로이

CD2DBrush 개체를 삭제합니다.

```
virtual void Destroy();
```

## <a name="cd2dbrushdetach"></a><a name="detach"></a>CD2D브러쉬: :D에타치

개체에서 리소스 인터페이스를 분리합니다.

```
ID2D1Brush* Detach();
```

### <a name="return-value"></a>Return Value

분리된 리소스 인터페이스에 대한 포인터입니다.

## <a name="cd2dbrushget"></a><a name="get"></a>CD2D 브러시 : : 가져옵니다

ID2D1브러시 인터페이스 반환

```
ID2D1Brush* Get();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1Brush 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dbrushgetopacity"></a><a name="getopacity"></a>CD2D브러쉬::게파시티

이 브러시의 불투명도도를 가져옵니다.

```
FLOAT GetOpacity() const;
```

### <a name="return-value"></a>Return Value

브러시의 불투명도를 나타내는 0과 1 사이의 값입니다. 이 값은 브러시로 채워진 모든 픽셀의 알파 값을 선형으로 조정하는 상수 승수입니다. 불투명도 값은 함께 곱하기 전에 범위 0에서 1로 고정됩니다.

## <a name="cd2dbrushgettransform"></a><a name="gettransform"></a>CD2D브러시::겟트랜스포메이션

렌더 대상의 현재 변환을 가져옵니다.

```cpp
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;
```

### <a name="parameters"></a>매개 변수

*transform*<br/>
이 반환 될 때 렌더 대상의 현재 변환을 포함 합니다. 이 매개 변수는 초기화되지 않은 상태로 전달됩니다.

## <a name="cd2dbrushisvalid"></a><a name="isvalid"></a>CD2D브러시::유효하지 않음

리소스 유효성 검사

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Return Value

TRUE 리소스가 유효한 경우; 그렇지 않으면 거짓.

## <a name="cd2dbrushm_pbrush"></a><a name="m_pbrush"></a>CD2D브러시:m_pBrush

ID2D1Brush 개체에 대한 포인터를 저장합니다.

```
ID2D1Brush* m_pBrush;
```

## <a name="cd2dbrushm_pbrushproperties"></a><a name="m_pbrushproperties"></a>CD2D브러시:m_pBrushProperties

브러시 속성입니다.

```
CD2DBrushProperties* m_pBrushProperties;
```

## <a name="cd2dbrushoperator-id2d1brush"></a><a name="operator_id2d1brush_star"></a>CD2D브러시::연산자 ID2D1브러시*

ID2D1브러시 인터페이스 반환

```
operator ID2D1Brush*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1Brush 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dbrushsetopacity"></a><a name="setopacity"></a>CD2D브러시::셋오파시티

이 브러시의 불투명도 도 설정

```cpp
void SetOpacity(FLOAT opacity);
```

### <a name="parameters"></a>매개 변수

*불투명도*<br/>
브러시의 불투명도를 나타내는 0과 1 사이의 값입니다. 이 값은 브러시로 채워진 모든 픽셀의 알파 값을 선형으로 조정하는 상수 승수입니다. 불투명도 값은 함께 곱하기 전에 범위 0에서 1로 고정됩니다.

## <a name="cd2dbrushsettransform"></a><a name="settransform"></a>CD2D브러시::세트변환

지정된 변환을 기존 변환을 대체하여 렌더 대상에 적용합니다. 이후의 모든 그리기 작업은 변환된 공간에서 발생합니다.

```cpp
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>매개 변수

*transform*<br/>
렌더 대상에 적용할 변환

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
