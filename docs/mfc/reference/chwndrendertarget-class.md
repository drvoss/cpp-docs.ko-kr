---
title: CHwndRenderTarget 클래스
ms.date: 11/04/2016
f1_keywords:
- CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::Attach
- AFXRENDERTARGET/CHwndRenderTarget::CheckWindowState
- AFXRENDERTARGET/CHwndRenderTarget::Create
- AFXRENDERTARGET/CHwndRenderTarget::Detach
- AFXRENDERTARGET/CHwndRenderTarget::GetHwnd
- AFXRENDERTARGET/CHwndRenderTarget::GetHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::ReCreate
- AFXRENDERTARGET/CHwndRenderTarget::Resize
- AFXRENDERTARGET/CHwndRenderTarget::m_pHwndRenderTarget
helpviewer_keywords:
- CHwndRenderTarget [MFC], CHwndRenderTarget
- CHwndRenderTarget [MFC], Attach
- CHwndRenderTarget [MFC], CheckWindowState
- CHwndRenderTarget [MFC], Create
- CHwndRenderTarget [MFC], Detach
- CHwndRenderTarget [MFC], GetHwnd
- CHwndRenderTarget [MFC], GetHwndRenderTarget
- CHwndRenderTarget [MFC], ReCreate
- CHwndRenderTarget [MFC], Resize
- CHwndRenderTarget [MFC], m_pHwndRenderTarget
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
ms.openlocfilehash: d1669d89183cd971e1afe0f05a1bad040f6b07df
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752708"
---
# <a name="chwndrendertarget-class"></a>CHwndRenderTarget 클래스

ID2D1HwndRenderTarget에 대한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CHwndRenderTarget : public CRenderTarget;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|HWND에서 CHwndRenderTarget 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CHwndRenderTarget::연결](#attach)|기존 렌더 대상 인터페이스를 오브젝트에 연결합니다.|
|[CHwndRenderTarget::체크윈도우 상태](#checkwindowstate)|이 렌더 대상과 연결된 HWND가 폐색되었는지 여부를 나타냅니다.|
|[CHwndRenderTarget::만들기](#create)|창과 연결된 렌더 대상 을 만듭니다.|
|[CHwndRenderTarget::D에타치](#detach)|개체에서 대상 인터페이스를 렌더링합니다.|
|[CHwndRenderTarget::GetHwnd](#gethwnd)|이 렌더 대상과 연결된 HWND를 반환합니다.|
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|ID2D1HwndRenderTarget 인터페이스를 반환합니다.|
|[CHwnd렌더대상::다시 만들기](#recreate)|창과 연결된 렌더 대상을 다시 만듭니다.|
|[CHwndRenderTarget::크기 조정](#resize)|렌더 대상의 크기를 지정된 픽셀 크기로 변경합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CHwndRenderTarget::연산자 ID2D1HwndRenderTarget*](#operator_id2d1hwndrendertarget_star)|ID2D1HwndRenderTarget 인터페이스를 반환합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|ID2D1HwndRenderTarget 개체에 대한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CHwnd렌더대상](../../mfc/reference/chwndrendertarget-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="chwndrendertargetattach"></a><a name="attach"></a>CHwndRenderTarget::연결

기존 렌더 대상 인터페이스를 오브젝트에 연결합니다.

```cpp
void Attach(ID2D1HwndRenderTarget* pTarget);
```

### <a name="parameters"></a>매개 변수

*p Target*<br/>
기존 렌더 대상 인터페이스입니다. NULL일 수 없음

## <a name="chwndrendertargetcheckwindowstate"></a><a name="checkwindowstate"></a>CHwndRenderTarget::체크윈도우 상태

이 렌더 대상과 연결된 HWND가 폐색되었는지 여부를 나타냅니다.

```
D2D1_WINDOW_STATE CheckWindowState() const;
```

### <a name="return-value"></a>Return Value

이 렌더 대상과 연결된 HWND가 가려져 있는지 여부를 나타내는 값입니다.

## <a name="chwndrendertargetchwndrendertarget"></a><a name="chwndrendertarget"></a>CHwndRenderTarget::CHwndRenderTarget

HWND에서 CHwndRenderTarget 개체를 생성합니다.

```
CHwndRenderTarget(HWND hwnd = NULL);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
이 렌더 대상과 연결된 HWND

## <a name="chwndrendertargetcreate"></a><a name="create"></a>CHwndRenderTarget::만들기

창과 연결된 렌더 대상 을 만듭니다.

```
BOOL Create(HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
이 렌더 대상과 연결된 HWND

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="chwndrendertargetdetach"></a><a name="detach"></a>CHwndRenderTarget::D에타치

개체에서 대상 인터페이스를 렌더링합니다.

```
ID2D1HwndRenderTarget* Detach();
```

### <a name="return-value"></a>Return Value

분리된 렌더 대상 인터페이스에 대한 포인터입니다.

## <a name="chwndrendertargetgethwnd"></a><a name="gethwnd"></a>CHwndRenderTarget::GetHwnd

이 렌더 대상과 연결된 HWND를 반환합니다.

```
HWND GetHwnd() const;
```

### <a name="return-value"></a>Return Value

이 렌더링 대상과 연결된 HWND입니다.

## <a name="chwndrendertargetgethwndrendertarget"></a><a name="gethwndrendertarget"></a>CHwndRenderTarget::GetHwndRenderTarget

ID2D1HwndRenderTarget 인터페이스를 반환합니다.

```
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1HwndRenderTarget 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="chwndrendertargetm_phwndrendertarget"></a><a name="m_phwndrendertarget"></a>CHwndRenderTarget::m_pHwndRenderTarget

ID2D1HwndRenderTarget 개체에 대한 포인터입니다.

```
ID2D1HwndRenderTarget* m_pHwndRenderTarget;
```

## <a name="chwndrendertargetoperator-id2d1hwndrendertarget"></a><a name="operator_id2d1hwndrendertarget_star"></a>CHwndRenderTarget::연산자 ID2D1HwndRenderTarget*

ID2D1HwndRenderTarget 인터페이스를 반환합니다.

```
operator ID2D1HwndRenderTarget*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1HwndRenderTarget 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="chwndrendertargetrecreate"></a><a name="recreate"></a>CHwnd렌더대상::다시 만들기

창과 연결된 렌더 대상을 다시 만듭니다.

```
BOOL ReCreate(HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
이 렌더 대상과 연결된 HWND

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="chwndrendertargetresize"></a><a name="resize"></a>CHwndRenderTarget::크기 조정

렌더 대상의 크기를 지정된 픽셀 크기로 변경합니다.

```
BOOL Resize(const CD2DSizeU& size);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
장치 픽셀의 렌더 대상의 새 크기

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
