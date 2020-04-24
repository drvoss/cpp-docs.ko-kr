---
title: CD2DLayer 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DLayer
- AFXRENDERTARGET/CD2DLayer
- AFXRENDERTARGET/CD2DLayer::CD2DLayer
- AFXRENDERTARGET/CD2DLayer::Attach
- AFXRENDERTARGET/CD2DLayer::Create
- AFXRENDERTARGET/CD2DLayer::Destroy
- AFXRENDERTARGET/CD2DLayer::Detach
- AFXRENDERTARGET/CD2DLayer::Get
- AFXRENDERTARGET/CD2DLayer::GetSize
- AFXRENDERTARGET/CD2DLayer::IsValid
- AFXRENDERTARGET/CD2DLayer::m_pLayer
helpviewer_keywords:
- CD2DLayer [MFC], CD2DLayer
- CD2DLayer [MFC], Attach
- CD2DLayer [MFC], Create
- CD2DLayer [MFC], Destroy
- CD2DLayer [MFC], Detach
- CD2DLayer [MFC], Get
- CD2DLayer [MFC], GetSize
- CD2DLayer [MFC], IsValid
- CD2DLayer [MFC], m_pLayer
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
ms.openlocfilehash: 30025d6097e439c07202d144a6e549845b78ffa6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754750"
---
# <a name="cd2dlayer-class"></a>CD2DLayer 클래스

ID2D1Layer용 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DLayer : public CD2DResource;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D레이어::CD2D레이어](#cd2dlayer)|CD2DLayer 개체를 생성합니다.|
|[CD2D레이어::~CD2D레이어](#_dtorcd2dlayer)|소멸자입니다. D2D 레이어 오브젝트가 파괴될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2DLayer::연결](#attach)|기존 리소스 인터페이스를 개체에 연결합니다.|
|[CD2DLayer::만들기](#create)|CD2DLayer를 만듭니다. [(CD2DResource::만들기](../../mfc/reference/cd2dresource-class.md#create)재정의.)|
|[CD2DLayer::D에스트로이](#destroy)|CD2DLayer 오브젝트를 삭제합니다. [(CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy)재정의.)|
|[CD2DLayer: :D에타치](#detach)|개체에서 리소스 인터페이스 분리|
|[CD2DLayer: :Get](#get)|ID2D1Layer 인터페이스 반환|
|[CD2DLayer::겟사이즈](#getsize)|장치 독립적인 픽셀에서 렌더링 대상의 크기를 반환합니다.|
|[CD2DLayer::유효합니다.](#isvalid)|리소스 유효성 [검사(CD2DResource 재정의::유효합니다.)](../../mfc/reference/cd2dresource-class.md#isvalid)|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2DLayer::연산자 ID2D1Layer*](#operator_id2d1layer_star)|ID2D1Layer 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2DLayer::m_pLayer](#m_player)|ID2D1Layer 개체에 대한 포인터를 저장합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

`CD2DLayer`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dlayercd2dlayer"></a><a name="_dtorcd2dlayer"></a>CD2D레이어::~CD2D레이어

소멸자입니다. D2D 레이어 오브젝트가 파괴될 때 호출됩니다.

```
virtual ~CD2DLayer();
```

## <a name="cd2dlayerattach"></a><a name="attach"></a>CD2DLayer::연결

기존 리소스 인터페이스를 개체에 연결합니다.

```cpp
void Attach(ID2D1Layer* pResource);
```

### <a name="parameters"></a>매개 변수

*Presource*<br/>
기존 리소스 인터페이스입니다. NULL일 수 없음

## <a name="cd2dlayercd2dlayer"></a><a name="cd2dlayer"></a>CD2D레이어::CD2D레이어

CD2DLayer 개체를 생성합니다.

```
CD2DLayer(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*p부모 대상*<br/>
렌더 대상에 대한 포인터입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

## <a name="cd2dlayercreate"></a><a name="create"></a>CD2DLayer::만들기

CD2DLayer를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*p렌더대상*<br/>
렌더 대상에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dlayerdestroy"></a><a name="destroy"></a>CD2DLayer::D에스트로이

CD2DLayer 오브젝트를 삭제합니다.

```
virtual void Destroy();
```

## <a name="cd2dlayerdetach"></a><a name="detach"></a>CD2DLayer: :D에타치

개체에서 리소스 인터페이스 분리

```
ID2D1Layer* Detach();
```

### <a name="return-value"></a>Return Value

분리된 리소스 인터페이스에 대한 포인터입니다.

## <a name="cd2dlayerget"></a><a name="get"></a>CD2DLayer: :Get

ID2D1Layer 인터페이스 반환

```
ID2D1Layer* Get();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1Layer 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dlayergetsize"></a><a name="getsize"></a>CD2DLayer::겟사이즈

장치 독립적인 픽셀에서 렌더링 대상의 크기를 반환합니다.

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Return Value

장치 독립적인 픽셀의 렌더 대상의 현재 크기

## <a name="cd2dlayerisvalid"></a><a name="isvalid"></a>CD2DLayer::유효합니다.

리소스 유효성 검사

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Return Value

TRUE 리소스가 유효한 경우; 그렇지 않으면 거짓.

## <a name="cd2dlayerm_player"></a><a name="m_player"></a>CD2DLayer::m_pLayer

ID2D1Layer 개체에 대한 포인터를 저장합니다.

```
ID2D1Layer* m_pLayer;
```

## <a name="cd2dlayeroperator-id2d1layer"></a><a name="operator_id2d1layer_star"></a>CD2DLayer::연산자 ID2D1Layer*

ID2D1Layer 인터페이스 반환

```
operator ID2D1Layer* ();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1Layer 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
