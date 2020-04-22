---
title: CD2DSolidColorBrush 클래스
ms.date: 03/27/2019
f1_keywords:
- CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::Attach
- AFXRENDERTARGET/CD2DSolidColorBrush::Create
- AFXRENDERTARGET/CD2DSolidColorBrush::Destroy
- AFXRENDERTARGET/CD2DSolidColorBrush::Detach
- AFXRENDERTARGET/CD2DSolidColorBrush::Get
- AFXRENDERTARGET/CD2DSolidColorBrush::GetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::SetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::m_colorSolid
- AFXRENDERTARGET/CD2DSolidColorBrush::m_pSolidColorBrush
helpviewer_keywords:
- CD2DSolidColorBrush [MFC], CD2DSolidColorBrush
- CD2DSolidColorBrush [MFC], Attach
- CD2DSolidColorBrush [MFC], Create
- CD2DSolidColorBrush [MFC], Destroy
- CD2DSolidColorBrush [MFC], Detach
- CD2DSolidColorBrush [MFC], Get
- CD2DSolidColorBrush [MFC], GetColor
- CD2DSolidColorBrush [MFC], SetColor
- CD2DSolidColorBrush [MFC], m_colorSolid
- CD2DSolidColorBrush [MFC], m_pSolidColorBrush
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
ms.openlocfilehash: d66a92e4801f7a13c62e2d83fdb94411d077ff53
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750263"
---
# <a name="cd2dsolidcolorbrush-class"></a>CD2DSolidColorBrush 클래스

ID2D1솔리드컬러브러시용 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DSolidColorBrush : public CD2DBrush;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D 솔리드 컬러 브러시 :: CD2D 솔리드 컬러 브러시](#cd2dsolidcolorbrush)|오버로드되었습니다. CD2DSolidColorBrush 개체를 생성합니다.|
|[CD2D 솔리드 컬러 브러시 :~~CD2D 솔리드 컬러 브러시](#_dtorcd2dsolidcolorbrush)|소멸자입니다. D2D 솔리드 브러시 오브젝트가 파괴될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2D 솔리드 컬러 브러시 ::부착](#attach)|기존 리소스 인터페이스를 개체에 연결합니다.|
|[CD2D 솔리드 컬러 브러시 ::만들기](#create)|CD2D솔리드컬러브러시를 만듭니다. [(CD2DResource::만들기](../../mfc/reference/cd2dresource-class.md#create)재정의.)|
|[CD2D 솔리드 컬러 브러시 : :Destroy](#destroy)|CD2D솔리드컬러브러시 오브젝트를 삭제합니다. [(CD2D브러시::D에스트로이](../../mfc/reference/cd2dbrush-class.md#destroy)재사용.|
|[CD2D 솔리드 컬러 브러시 : :D](#detach)|개체에서 리소스 인터페이스 분리|
|[CD2D 솔리드 컬러 브러시 : : 가져옵니다](#get)|ID2D1솔리드컬러브러시 인터페이스 반환|
|[CD2D 솔리드 컬러 브러시 : : GetColor](#getcolor)|단색 브러쉬의 색상을 검색합니다.|
|[CD2D 솔리드 컬러 브러시 : : 세트 컬러](#setcolor)|이 단색 브러시의 색상을 지정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2D 솔리드 컬러 브러시 :: 연산자 ID2D1 솔리드 컬러 브러시 *](#operator_id2d1solidcolorbrush_star)|ID2D1솔리드컬러브러시 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D 솔리드 컬러 브러시 :m_colorSolid](#m_colorsolid)|단색을 브러시합니다.|
|[CD2D 솔리드 컬러 브러시 :m_pSolidColorBrush](#m_psolidcolorbrush)|ID2D1SolidColorBrush 개체에 대한 포인터를 저장합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

[CD2D브러시](../../mfc/reference/cd2dbrush-class.md)

[CD2D 솔리드 컬러 브러시](../../mfc/reference/cd2dsolidcolorbrush-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="_dtorcd2dsolidcolorbrush"></a>CD2D 솔리드 컬러 브러시 :~~CD2D 솔리드 컬러 브러시

소멸자입니다. D2D 솔리드 브러시 오브젝트가 파괴될 때 호출됩니다.

```
virtual ~CD2DSolidColorBrush();
```

## <a name="cd2dsolidcolorbrushattach"></a><a name="attach"></a>CD2D 솔리드 컬러 브러시 ::부착

기존 리소스 인터페이스를 개체에 연결합니다.

```cpp
void Attach(ID2D1SolidColorBrush* pResource);
```

### <a name="parameters"></a>매개 변수

*Presource*<br/>
기존 리소스 인터페이스입니다. NULL일 수 없음

## <a name="cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="cd2dsolidcolorbrush"></a>CD2D 솔리드 컬러 브러시 :: CD2D 솔리드 컬러 브러시

CD2DSolidColorBrush 개체를 생성합니다.

```
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    D2D1_COLOR_F color,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    COLORREF color,
    int nAlpha = 255,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*p부모 대상*<br/>
렌더 대상에 대한 포인터입니다.

*색*<br/>
브러시 색상의 빨간색, 녹색, 파란색 및 알파 값입니다.

*p브러시프로퍼티*<br/>
브러시의 불투명도 및 변환에 대한 포인터입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

*n알파 (주)*<br/>
브러시 색상의 불투명도입니다.

## <a name="cd2dsolidcolorbrushcreate"></a><a name="create"></a>CD2D 솔리드 컬러 브러시 ::만들기

CD2D솔리드컬러브러시를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*p렌더대상*<br/>
렌더 대상에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dsolidcolorbrushdestroy"></a><a name="destroy"></a>CD2D 솔리드 컬러 브러시 : :Destroy

CD2D솔리드컬러브러시 오브젝트를 삭제합니다.

```
virtual void Destroy();
```

## <a name="cd2dsolidcolorbrushdetach"></a><a name="detach"></a>CD2D 솔리드 컬러 브러시 : :D

개체에서 리소스 인터페이스 분리

```
ID2D1SolidColorBrush* Detach();
```

### <a name="return-value"></a>Return Value

분리된 리소스 인터페이스에 대한 포인터입니다.

## <a name="cd2dsolidcolorbrushget"></a><a name="get"></a>CD2D 솔리드 컬러 브러시 : : 가져옵니다

ID2D1솔리드컬러브러시 인터페이스 반환

```
ID2D1SolidColorBrush* Get();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1SolidColorBrush 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dsolidcolorbrushgetcolor"></a><a name="getcolor"></a>CD2D 솔리드 컬러 브러시 : : GetColor

단색 브러쉬의 색상을 검색합니다.

```
D2D1_COLOR_F GetColor() const;
```

### <a name="return-value"></a>Return Value

이 단색 브러쉬의 색상

## <a name="cd2dsolidcolorbrushm_colorsolid"></a><a name="m_colorsolid"></a>CD2D 솔리드 컬러 브러시 :m_colorSolid

단색을 브러시합니다.

```
D2D1_COLOR_F m_colorSolid;
```

## <a name="cd2dsolidcolorbrushm_psolidcolorbrush"></a><a name="m_psolidcolorbrush"></a>CD2D 솔리드 컬러 브러시 :m_pSolidColorBrush

ID2D1SolidColorBrush 개체에 대한 포인터를 저장합니다.

```
ID2D1SolidColorBrush* m_pSolidColorBrush;
```

## <a name="cd2dsolidcolorbrushoperator-id2d1solidcolorbrush"></a><a name="operator_id2d1solidcolorbrush_star"></a>CD2D 솔리드 컬러 브러시 :: 연산자 ID2D1 솔리드 컬러 브러시 *

ID2D1솔리드컬러브러시 인터페이스 반환

```
operator ID2D1SolidColorBrush*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1SolidColorBrush 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dsolidcolorbrushsetcolor"></a><a name="setcolor"></a>CD2D 솔리드 컬러 브러시 : : 세트 컬러

이 단색 브러시의 색상을 지정합니다.

```cpp
void SetColor(D2D1_COLOR_F color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
이 단색 브러쉬의 색상

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
