---
title: CD2DMesh 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DMesh
- AFXRENDERTARGET/CD2DMesh
- AFXRENDERTARGET/CD2DMesh::CD2DMesh
- AFXRENDERTARGET/CD2DMesh::Attach
- AFXRENDERTARGET/CD2DMesh::Create
- AFXRENDERTARGET/CD2DMesh::Destroy
- AFXRENDERTARGET/CD2DMesh::Detach
- AFXRENDERTARGET/CD2DMesh::Get
- AFXRENDERTARGET/CD2DMesh::IsValid
- AFXRENDERTARGET/CD2DMesh::Open
- AFXRENDERTARGET/CD2DMesh::m_pMesh
helpviewer_keywords:
- CD2DMesh [MFC], CD2DMesh
- CD2DMesh [MFC], Attach
- CD2DMesh [MFC], Create
- CD2DMesh [MFC], Destroy
- CD2DMesh [MFC], Detach
- CD2DMesh [MFC], Get
- CD2DMesh [MFC], IsValid
- CD2DMesh [MFC], Open
- CD2DMesh [MFC], m_pMesh
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
ms.openlocfilehash: eaecdb6ba6f1382f16177e0567b31c9fd09da6ff
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753086"
---
# <a name="cd2dmesh-class"></a>CD2DMesh 클래스

ID2D1Mesh용 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DMesh : public CD2DResource;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D메쉬:CD2D메쉬](#cd2dmesh)|CD2DMesh 개체를 생성합니다.|
|[CD2D 메쉬: :~CD2D메쉬](#_dtorcd2dmesh)|소멸자입니다. D2D 메시 오브젝트가 파괴될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2D메쉬::연결](#attach)|기존 리소스 인터페이스를 개체에 연결합니다.|
|[CD2D메시:만들기](#create)|CD2D메시를 만듭니다. [(CD2DResource::만들기](../../mfc/reference/cd2dresource-class.md#create)재정의.)|
|[CD2D메쉬::D에스트로이](#destroy)|CD2DMesh 개체를 삭제합니다. [(CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy)재정의.)|
|[CD2D메쉬: :D](#detach)|개체에서 리소스 인터페이스 분리|
|[CD2D 메쉬 :: Get](#get)|ID2D1Mesh 인터페이스 반환|
|[CD2D메시:유효하지 않음](#isvalid)|리소스 유효성 [검사(CD2DResource 재정의::유효합니다.)](../../mfc/reference/cd2dresource-class.md#isvalid)|
|[CD2D메쉬::열기](#open)|채우기에 대한 메시를 엽니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2D메쉬::연산자 ID2D1Mesh*](#operator_id2d1mesh_star)|ID2D1Mesh 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D메쉬:m_pMesh](#m_pmesh)|ID2D1Mesh에 대한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

`CD2DMesh`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dmeshcd2dmesh"></a><a name="_dtorcd2dmesh"></a>CD2D 메쉬: :~CD2D메쉬

소멸자입니다. D2D 메시 오브젝트가 파괴될 때 호출됩니다.

```
virtual ~CD2DMesh();
```

## <a name="cd2dmeshattach"></a><a name="attach"></a>CD2D메쉬::연결

기존 리소스 인터페이스를 개체에 연결합니다.

```cpp
void Attach(ID2D1Mesh* pResource);
```

### <a name="parameters"></a>매개 변수

*Presource*<br/>
기존 리소스 인터페이스입니다. NULL일 수 없음

## <a name="cd2dmeshcd2dmesh"></a><a name="cd2dmesh"></a>CD2D메쉬:CD2D메쉬

CD2DMesh 개체를 생성합니다.

```
CD2DMesh(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*p부모 대상*<br/>
렌더 대상에 대한 포인터입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

## <a name="cd2dmeshcreate"></a><a name="create"></a>CD2D메시:만들기

CD2D메시를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*p렌더대상*<br/>
렌더 대상에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dmeshdestroy"></a><a name="destroy"></a>CD2D메쉬::D에스트로이

CD2DMesh 개체를 삭제합니다.

```
virtual void Destroy();
```

## <a name="cd2dmeshdetach"></a><a name="detach"></a>CD2D메쉬: :D

개체에서 리소스 인터페이스 분리

```
ID2D1Mesh* Detach();
```

### <a name="return-value"></a>Return Value

분리된 리소스 인터페이스에 대한 포인터입니다.

## <a name="cd2dmeshget"></a><a name="get"></a>CD2D 메쉬 :: Get

ID2D1Mesh 인터페이스 반환

```
ID2D1Mesh* Get();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1Mesh 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dmeshisvalid"></a><a name="isvalid"></a>CD2D메시:유효하지 않음

리소스 유효성 검사

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Return Value

TRUE 리소스가 유효한 경우; 그렇지 않으면 거짓.

## <a name="cd2dmeshm_pmesh"></a><a name="m_pmesh"></a>CD2D메쉬:m_pMesh

ID2D1Mesh에 대한 포인터입니다.

```
ID2D1Mesh* m_pMesh;
```

## <a name="cd2dmeshopen"></a><a name="open"></a>CD2D메쉬::열기

채우기에 대한 메시를 엽니다.

```
ID2D1TessellationSink* Open();
```

### <a name="return-value"></a>Return Value

메시를 채우는 데 사용되는 ID2D1Tessellation싱크에 대한 포인터입니다.

## <a name="cd2dmeshoperator-id2d1mesh"></a><a name="operator_id2d1mesh_star"></a>CD2D메쉬::연산자 ID2D1Mesh*

ID2D1Mesh 인터페이스 반환

```
operator ID2D1Mesh*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1Mesh 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
