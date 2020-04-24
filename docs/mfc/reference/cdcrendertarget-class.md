---
title: CDCRenderTarget 클래스
ms.date: 11/04/2016
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
helpviewer_keywords:
- CDCRenderTarget [MFC], CDCRenderTarget
- CDCRenderTarget [MFC], Attach
- CDCRenderTarget [MFC], BindDC
- CDCRenderTarget [MFC], Create
- CDCRenderTarget [MFC], Detach
- CDCRenderTarget [MFC], GetDCRenderTarget
- CDCRenderTarget [MFC], m_pDCRenderTarget
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
ms.openlocfilehash: 8c07962c017d160cb3ce5841a75f1ae8a8761641
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753385"
---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget 클래스

ID2D1DCRenderTarget용 래퍼입니다.

## <a name="syntax"></a>구문

```
class CDCRenderTarget : public CRenderTarget;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDC렌더대상::CDC렌더대상](#cdcrendertarget)|CDCRenderTarget 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDC렌더대상::첨부](#attach)|기존 렌더 대상 인터페이스를 오브젝트에 연결합니다.|
|[CDC렌더대상::바인드DC](#binddc)|그리기 명령을 발행하는 장치 컨텍스트에 렌더링 대상을 바인딩합니다.|
|[CDC렌더대상::만들기](#create)|CDCRenderTarget을 만듭니다.|
|[CDC렌더대상::D에타치](#detach)|개체에서 대상 인터페이스를 렌더링합니다.|
|[CDC렌더대상::겟DC렌더대상](#getdcrendertarget)|ID2D1DCRenderTarget 인터페이스 반환|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CDC렌더대상::연산자 ID2D1DC렌더대상*](#operator_id2d1dcrendertarget_star)|ID2D1DCRenderTarget 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDC렌더대상::m_pDCRenderTarget](#m_pdcrendertarget)|ID2D1DCRenderTarget 개체에 대한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CDC렌더대상](../../mfc/reference/cdcrendertarget-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cdcrendertargetattach"></a><a name="attach"></a>CDC렌더대상::첨부

기존 렌더 대상 인터페이스를 오브젝트에 연결합니다.

```cpp
void Attach(ID2D1DCRenderTarget* pTarget);
```

### <a name="parameters"></a>매개 변수

*p Target*<br/>
기존 렌더 대상 인터페이스입니다. NULL일 수 없음

## <a name="cdcrendertargetbinddc"></a><a name="binddc"></a>CDC렌더대상::바인드DC

그리기 명령을 발행하는 장치 컨텍스트에 렌더링 대상을 바인딩합니다.

```
BOOL BindDC(
    const CDC& dc,
    const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*Dc*<br/>
렌더 대상이 그리기 명령을 발행하는 장치 컨텍스트

*rect*<br/>
렌더링 대상이 바인딩된 장치 컨텍스트(HDC)에 대한 핸들 치수

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cdcrendertargetcdcrendertarget"></a><a name="cdcrendertarget"></a>CDC렌더대상::CDC렌더대상

CDCRenderTarget 개체를 생성합니다.

```
CDCRenderTarget();
```

## <a name="cdcrendertargetcreate"></a><a name="create"></a>CDC렌더대상::만들기

CDCRenderTarget을 만듭니다.

```
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```

### <a name="parameters"></a>매개 변수

*소품*<br/>
렌더링 모드, 픽셀 형식, 원격 옵션, DPI 정보 및 하드웨어 렌더링에 필요한 최소 DirectX 지원.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cdcrendertargetdetach"></a><a name="detach"></a>CDC렌더대상::D에타치

개체에서 대상 인터페이스를 렌더링합니다.

```
ID2D1DCRenderTarget* Detach();
```

### <a name="return-value"></a>Return Value

분리된 렌더 대상 인터페이스에 대한 포인터입니다.

## <a name="cdcrendertargetgetdcrendertarget"></a><a name="getdcrendertarget"></a>CDC렌더대상::겟DC렌더대상

ID2D1DCRenderTarget 인터페이스 반환

```
ID2D1DCRenderTarget* GetDCRenderTarget();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1DCRenderTarget 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cdcrendertargetm_pdcrendertarget"></a><a name="m_pdcrendertarget"></a>CDC렌더대상::m_pDCRenderTarget

ID2D1DCRenderTarget 개체에 대한 포인터입니다.

```
ID2D1DCRenderTarget* m_pDCRenderTarget;
```

## <a name="cdcrendertargetoperator-id2d1dcrendertarget"></a><a name="operator_id2d1dcrendertarget_star"></a>CDC렌더대상::연산자 ID2D1DC렌더대상*

ID2D1DCRenderTarget 인터페이스 반환

```
operator ID2D1DCRenderTarget*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1DCRenderTarget 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
