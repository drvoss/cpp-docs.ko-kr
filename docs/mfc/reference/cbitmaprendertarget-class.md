---
title: CBitmapRenderTarget 클래스
ms.date: 11/04/2016
f1_keywords:
- CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::Attach
- AFXRENDERTARGET/CBitmapRenderTarget::Detach
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmap
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::m_pBitmapRenderTarget
helpviewer_keywords:
- CBitmapRenderTarget [MFC], CBitmapRenderTarget
- CBitmapRenderTarget [MFC], Attach
- CBitmapRenderTarget [MFC], Detach
- CBitmapRenderTarget [MFC], GetBitmap
- CBitmapRenderTarget [MFC], GetBitmapRenderTarget
- CBitmapRenderTarget [MFC], m_pBitmapRenderTarget
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
ms.openlocfilehash: 8ba8c8819b47185315d67d732fc90ab2ffc0ad0a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752939"
---
# <a name="cbitmaprendertarget-class"></a>CBitmapRenderTarget 클래스

ID2D1비트맵렌더대상용 래퍼입니다.

## <a name="syntax"></a>구문

```
class CBitmapRenderTarget : public CRenderTarget;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C비트맵렌더대상::C비트맵렌더타겟](#cbitmaprendertarget)|C비트맵렌더대상 오브젝트를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C비트맵렌더대상::첨부](#attach)|기존 렌더 대상 인터페이스를 오브젝트에 연결합니다.|
|[C비트맵렌더타겟::D](#detach)|개체에서 대상 인터페이스를 렌더링합니다.|
|[C비트맵렌더타겟::겟비트맵](#getbitmap)|이 렌더 대상에 대한 비트맵을 검색합니다. 반환된 비트맵을 그리기 작업에 사용할 수 있습니다.|
|[C비트맵렌더타겟::겟비트맵렌더타겟](#getbitmaprendertarget)|ID2D1비트맵렌더대상 인터페이스 반환|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C비트맵렌더대상::연산자 ID2D1비트맵렌더대상*](#operator_id2d1bitmaprendertarget_star)|ID2D1비트맵렌더대상 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C비트맵렌더타겟::m_pBitmapRenderTarget](#m_pbitmaprendertarget)|ID2D1BitmapRenderTarget 개체에 대한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

`CBitmapRenderTarget`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cbitmaprendertargetattach"></a><a name="attach"></a>C비트맵렌더대상::첨부

기존 렌더 대상 인터페이스를 오브젝트에 연결합니다.

```cpp
void Attach(ID2D1BitmapRenderTarget* pTarget);
```

### <a name="parameters"></a>매개 변수

*p Target*<br/>
기존 렌더 대상 인터페이스입니다. NULL일 수 없음

## <a name="cbitmaprendertargetcbitmaprendertarget"></a><a name="cbitmaprendertarget"></a>C비트맵렌더대상::C비트맵렌더타겟

C비트맵렌더대상 오브젝트를 생성합니다.

```
CBitmapRenderTarget();
```

## <a name="cbitmaprendertargetdetach"></a><a name="detach"></a>C비트맵렌더타겟::D

개체에서 대상 인터페이스를 렌더링합니다.

```
ID2D1BitmapRenderTarget* Detach();
```

### <a name="return-value"></a>Return Value

분리된 렌더 대상 인터페이스에 대한 포인터입니다.

## <a name="cbitmaprendertargetgetbitmap"></a><a name="getbitmap"></a>C비트맵렌더타겟::겟비트맵

이 렌더 대상에 대한 비트맵을 검색합니다. 반환된 비트맵을 그리기 작업에 사용할 수 있습니다.

```
BOOL GetBitmap(CD2DBitmap& bitmap);
```

### <a name="parameters"></a>매개 변수

*비트맵*<br/>
이 메서드가 반환되면 이 렌더 대상에 대한 유효한 비트맵이 포함됩니다. 이 비트맵은 그리기 작업에 사용할 수 있습니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cbitmaprendertargetgetbitmaprendertarget"></a><a name="getbitmaprendertarget"></a>C비트맵렌더타겟::겟비트맵렌더타겟

ID2D1비트맵렌더대상 인터페이스 반환

```
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1BitmapRenderTarget 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cbitmaprendertargetm_pbitmaprendertarget"></a><a name="m_pbitmaprendertarget"></a>C비트맵렌더타겟::m_pBitmapRenderTarget

ID2D1BitmapRenderTarget 개체에 대한 포인터입니다.

```
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;
```

## <a name="cbitmaprendertargetoperator-id2d1bitmaprendertarget"></a><a name="operator_id2d1bitmaprendertarget_star"></a>C비트맵렌더대상::연산자 ID2D1비트맵렌더대상*

ID2D1비트맵렌더대상 인터페이스 반환

```
operator ID2D1BitmapRenderTarget*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1BitmapRenderTarget 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
