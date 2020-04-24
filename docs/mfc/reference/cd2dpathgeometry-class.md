---
title: CD2DPathGeometry 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::Attach
- AFXRENDERTARGET/CD2DPathGeometry::Create
- AFXRENDERTARGET/CD2DPathGeometry::Destroy
- AFXRENDERTARGET/CD2DPathGeometry::Detach
- AFXRENDERTARGET/CD2DPathGeometry::GetFigureCount
- AFXRENDERTARGET/CD2DPathGeometry::GetSegmentCount
- AFXRENDERTARGET/CD2DPathGeometry::Open
- AFXRENDERTARGET/CD2DPathGeometry::Stream
- AFXRENDERTARGET/CD2DPathGeometry::m_pPathGeometry
helpviewer_keywords:
- CD2DPathGeometry [MFC], CD2DPathGeometry
- CD2DPathGeometry [MFC], Attach
- CD2DPathGeometry [MFC], Create
- CD2DPathGeometry [MFC], Destroy
- CD2DPathGeometry [MFC], Detach
- CD2DPathGeometry [MFC], GetFigureCount
- CD2DPathGeometry [MFC], GetSegmentCount
- CD2DPathGeometry [MFC], Open
- CD2DPathGeometry [MFC], Stream
- CD2DPathGeometry [MFC], m_pPathGeometry
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
ms.openlocfilehash: 91460e3435130530ecc57bdcc09d1c7301333a3b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753082"
---
# <a name="cd2dpathgeometry-class"></a>CD2DPathGeometry 클래스

ID2D1Path지오메지리에 대한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DPathGeometry : public CD2DGeometry;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D패스지오메기미지::CD2D패스지오메기](#cd2dpathgeometry)|CD2DPathGeometry 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2D패스지오메기::연결](#attach)|기존 리소스 인터페이스를 개체에 연결합니다.|
|[CD2D패스지오메지오메트리::만들기](#create)|CD2DPath지오메지오메트리를 작성합니다. [(CD2DResource::만들기](../../mfc/reference/cd2dresource-class.md#create)재정의.)|
|[CD2D패스지오메기::D에스트로이](#destroy)|CD2DPathGeometry 개체를 삭제합니다. [(CD2D지오메트리::Destroy.)](../../mfc/reference/cd2dgeometry-class.md#destroy)|
|[CD2D패스지오메기::D에타크](#detach)|개체에서 리소스 인터페이스 분리|
|[CD2D패스지오메지오메트리::겟피규수](#getfigurecount)|경로 형상의 그림 수를 검색합니다.|
|[CD2DPath지오메지오메트리::겟세그먼트카운트](#getsegmentcount)|경로 형상의 세그먼트 수를 검색합니다.|
|[CD2D패스지오메지오메트리::열기](#open)|패스 형상을 그림 및 세그먼트로 채우는 데 사용되는 형상 싱크를 검색합니다.|
|[CD2D패스지오메지오메트리::스트림](#stream)|경로 형상의 내용을 지정된 ID2D1 Geometry싱크에 복사합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D패스지오메지오메트리::m_pPathGeometry](#m_ppathgeometry)|ID2D1Path지오메지리에 대한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

[CD2D지오메트리](../../mfc/reference/cd2dgeometry-class.md)

`CD2DPathGeometry`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dpathgeometryattach"></a><a name="attach"></a>CD2D패스지오메기::연결

기존 리소스 인터페이스를 개체에 연결합니다.

```cpp
void Attach(ID2D1PathGeometry* pResource);
```

### <a name="parameters"></a>매개 변수

*Presource*<br/>
기존 리소스 인터페이스입니다. NULL일 수 없음

## <a name="cd2dpathgeometrycd2dpathgeometry"></a><a name="cd2dpathgeometry"></a>CD2D패스지오메기미지::CD2D패스지오메기

CD2DPathGeometry 개체를 생성합니다.

```
CD2DPathGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*p부모 대상*<br/>
렌더 대상에 대한 포인터입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

## <a name="cd2dpathgeometrycreate"></a><a name="create"></a>CD2D패스지오메지오메트리::만들기

CD2DPath지오메지오메트리를 작성합니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*p렌더대상*<br/>
렌더 대상에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dpathgeometrydestroy"></a><a name="destroy"></a>CD2D패스지오메기::D에스트로이

CD2DPathGeometry 개체를 삭제합니다.

```
virtual void Destroy();
```

## <a name="cd2dpathgeometrydetach"></a><a name="detach"></a>CD2D패스지오메기::D에타크

개체에서 리소스 인터페이스 분리

```
ID2D1PathGeometry* Detach();
```

### <a name="return-value"></a>Return Value

분리된 리소스 인터페이스에 대한 포인터입니다.

## <a name="cd2dpathgeometrygetfigurecount"></a><a name="getfigurecount"></a>CD2D패스지오메지오메트리::겟피규수

경로 형상의 그림 수를 검색합니다.

```
int GetFigureCount() const;
```

### <a name="return-value"></a>Return Value

경로 형상의 그림 수를 반환합니다.

## <a name="cd2dpathgeometrygetsegmentcount"></a><a name="getsegmentcount"></a>CD2DPath지오메지오메트리::겟세그먼트카운트

경로 형상의 세그먼트 수를 검색합니다.

```
int GetSegmentCount() const;
```

### <a name="return-value"></a>Return Value

경로 형상의 세그먼트 수를 반환합니다.

## <a name="cd2dpathgeometrym_ppathgeometry"></a><a name="m_ppathgeometry"></a>CD2D패스지오메지오메트리::m_pPathGeometry

ID2D1Path지오메지리에 대한 포인터입니다.

```
ID2D1PathGeometry* m_pPathGeometry;
```

## <a name="cd2dpathgeometryopen"></a><a name="open"></a>CD2D패스지오메지오메트리::열기

패스 형상을 그림 및 세그먼트로 채우는 데 사용되는 형상 싱크를 검색합니다.

```
ID2D1GeometrySink* Open();
```

### <a name="return-value"></a>Return Value

패스 형상을 그림과 세그먼트로 채우는 데 사용되는 ID2D1GeometrySink에 대한 포인터입니다.

## <a name="cd2dpathgeometrystream"></a><a name="stream"></a>CD2D패스지오메지오메트리::스트림

경로 형상의 내용을 지정된 ID2D1 Geometry싱크에 복사합니다.

```
BOOL Stream(ID2D1GeometrySink* geometrySink);
```

### <a name="parameters"></a>매개 변수

*지오메트리 싱크*<br/>
경로 지오메트리의 내용이 복사되는 싱크입니다. 이 싱크를 수정해도 이 경로 형상의 내용은 변경되지 않습니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
