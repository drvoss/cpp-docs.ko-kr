---
title: CD2DResource 클래스
ms.date: 03/27/2019
f1_keywords:
- CD2DResource
- AFXRENDERTARGET/CD2DResource
- AFXRENDERTARGET/CD2DResource::CD2DResource
- AFXRENDERTARGET/CD2DResource::Create
- AFXRENDERTARGET/CD2DResource::Destroy
- AFXRENDERTARGET/CD2DResource::IsValid
- AFXRENDERTARGET/CD2DResource::IsAutoDestroy
- AFXRENDERTARGET/CD2DResource::ReCreate
- AFXRENDERTARGET/CD2DResource::m_bIsAutoDestroy
- AFXRENDERTARGET/CD2DResource::m_pParentTarget
helpviewer_keywords:
- CD2DResource [MFC], CD2DResource
- CD2DResource [MFC], Create
- CD2DResource [MFC], Destroy
- CD2DResource [MFC], IsValid
- CD2DResource [MFC], IsAutoDestroy
- CD2DResource [MFC], ReCreate
- CD2DResource [MFC], m_bIsAutoDestroy
- CD2DResource [MFC], m_pParentTarget
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
ms.openlocfilehash: 5e747eda42e625d0f4cf65859e471933bbb043ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369090"
---
# <a name="cd2dresource-class"></a>CD2DResource 클래스

브러시, 레이어 및 텍스트와 같은 D2D 리소스를 만들고 관리하기 위한 인터페이스를 제공하는 추상 클래스입니다.

## <a name="syntax"></a>구문

```
class CD2DResource : public CObject;
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CD2D자원::CD2D자원](#cd2dresource)|CD2DResource 개체를 생성합니다.|
|[CD2D자원::~CD2D자원](#_dtorcd2dresource)|소멸자입니다. D2D 리소스 개체가 소멸될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2D리소스:만들기](#create)|CD2DResource를 만듭니다.|
|[CD2D자원::D에스트로이](#destroy)|CD2DResource 개체를 삭제합니다.|
|[CD2D리소스:유효하지 않음](#isvalid)|리소스 유효성 검사|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CD2D자원::IsAutoDestroy](#isautodestroy)|자동 파괴 플래그를 확인합니다.|
|[CD2D리소스:재현](#recreate)|CD2DResource를 다시 만듭니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D리소스:m_bIsAutoDestroy](#m_bisautodestroy)|소유자는 리소스를 파괴합니다(CRenderTarget)|
|[CD2D리소스:m_pParentTarget](#m_pparenttarget)|부모 CRenderTarget에 대한 포인터)|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CD2DResource`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dresourcecd2dresource"></a><a name="_dtorcd2dresource"></a>CD2D자원::~CD2D자원

소멸자입니다. D2D 리소스 개체가 소멸될 때 호출됩니다.

```
virtual ~CD2DResource();
```

## <a name="cd2dresourcecd2dresource"></a><a name="cd2dresource"></a>CD2D자원::CD2D자원

CD2DResource 개체를 생성합니다.

```
CD2DResource(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy);
```

### <a name="parameters"></a>매개 변수

*p부모 대상*<br/>
렌더 대상에 대한 포인터입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

## <a name="cd2dresourcecreate"></a><a name="create"></a>CD2D리소스:만들기

CD2DResource를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;
```

### <a name="parameters"></a>매개 변수

*p렌더대상*<br/>
렌더 대상에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dresourcedestroy"></a><a name="destroy"></a>CD2D자원::D에스트로이

CD2DResource 개체를 삭제합니다.

```
virtual void Destroy() = 0;
```

## <a name="cd2dresourceisautodestroy"></a><a name="isautodestroy"></a>CD2D자원::IsAutoDestroy

자동 파괴 플래그를 확인합니다.

```
BOOL IsAutoDestroy() const;
```

### <a name="return-value"></a>Return Value

TRUE 개체가 소유자에 의해 파괴되는 경우 그렇지 않으면 거짓.

## <a name="cd2dresourceisvalid"></a><a name="isvalid"></a>CD2D리소스:유효하지 않음

리소스 유효성 검사

```
virtual BOOL IsValid() const = 0;
```

### <a name="return-value"></a>Return Value

TRUE 리소스가 유효한 경우; 그렇지 않으면 거짓.

## <a name="cd2dresourcem_bisautodestroy"></a><a name="m_bisautodestroy"></a>CD2D리소스:m_bIsAutoDestroy

소유자는 리소스를 파괴합니다(CRenderTarget)

```
BOOL m_bIsAutoDestroy;
```

## <a name="cd2dresourcem_pparenttarget"></a><a name="m_pparenttarget"></a>CD2D리소스:m_pParentTarget

부모 CRenderTarget에 대한 포인터)

```
CRenderTarget* m_pParentTarget;
```

## <a name="cd2dresourcerecreate"></a><a name="recreate"></a>CD2D리소스:재현

CD2DResource를 다시 만듭니다.

```
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*p렌더대상*<br/>
렌더 대상에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
