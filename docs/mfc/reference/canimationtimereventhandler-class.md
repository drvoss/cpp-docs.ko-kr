---
title: CAnimationTimerEventHandler 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationTimerEventHandler [MFC], CreateInstance
- CAnimationTimerEventHandler [MFC], OnPostUpdate
- CAnimationTimerEventHandler [MFC], OnPreUpdate
- CAnimationTimerEventHandler [MFC], OnRenderingTooSlow
- CAnimationTimerEventHandler [MFC], SetAnimationController
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
ms.openlocfilehash: d1653e50fef03deb8eb23dd9a989d1ca2a529dd8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755098"
---
# <a name="canimationtimereventhandler-class"></a>CAnimationTimerEventHandler 클래스

타이밍 이벤트가 발생할 때 애니메이션 API에서 호출하는 콜백을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션타이머이벤트::만들기 인스턴스](#createinstance)|콜백 인스턴스를 `CAnimationTimerEventHandler` 만듭니다.|
|[C애니메이션타이머이벤트::온포스트업데이트](#onpostupdate)|애니메이션 업데이트가 완료된 후 발생하는 이벤트를 처리합니다. ( `CUIAnimationTimerEventHandlerBase::OnPostUpdate`을 재정의합니다.)|
|[C애니메이션타이머이벤트::온사전업데이트](#onpreupdate)|애니메이션 업데이트가 시작되기 전에 발생하는 이벤트를 처리합니다. ( `CUIAnimationTimerEventHandlerBase::OnPreUpdate`을 재정의합니다.)|
|[C애니메이션타이머이벤트::온렌더링투슬로우](#onrenderingtooslow)|애니메이션의 렌더링 프레임 속도가 최소 바람직한 프레임 속도보다 낮을 때 발생하는 이벤트를 처리합니다. ( `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`을 재정의합니다.)|
|[C애니메이션타이머이벤트::세트애니메이션컨트롤러](#setanimationcontroller)|애니메이션 컨트롤러에 대한 포인터를 저장하여 이벤트를 라우팅합니다.|

## <a name="remarks"></a>설명

이 이벤트 처리기는 CAnimationController::EnableAnimationTimerEventHandler를 호출할 때 IUIAnimationTimer::SetTimerEventHandler에 생성되고 전달됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CUIAnimationCallbackBase`

`CUIAnimationTimerEventHandlerBase`

`CAnimationTimerEventHandler`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationtimereventhandlercreateinstance"></a><a name="createinstance"></a>C애니메이션타이머이벤트::만들기 인스턴스

CAnimationTimerEventHandler 콜백의 인스턴스를 만듭니다.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```

### <a name="parameters"></a>매개 변수

*p애니메이션 컨트롤러*<br/>
이벤트를 수신하는 애니메이션 컨트롤러에 대한 포인터입니다.

*pp타이머이벤트핸들러*

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="canimationtimereventhandleronpostupdate"></a><a name="onpostupdate"></a>C애니메이션타이머이벤트::온포스트업데이트

애니메이션 업데이트가 완료된 후 발생하는 이벤트를 처리합니다.

```
IFACEMETHOD(OnPostUpdate)();
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK. 그렇지 않으면 E_FAIL.

## <a name="canimationtimereventhandleronpreupdate"></a><a name="onpreupdate"></a>C애니메이션타이머이벤트::온사전업데이트

애니메이션 업데이트가 시작되기 전에 발생하는 이벤트를 처리합니다.

```
IFACEMETHOD(OnPreUpdate)();
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK. 그렇지 않으면 E_FAIL.

## <a name="canimationtimereventhandleronrenderingtooslow"></a><a name="onrenderingtooslow"></a>C애니메이션타이머이벤트::온렌더링투슬로우

애니메이션의 렌더링 프레임 속도가 최소 바람직한 프레임 속도보다 낮을 때 발생하는 이벤트를 처리합니다.

```
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```

### <a name="parameters"></a>매개 변수

*Fps*

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK. 그렇지 않으면 E_FAIL.

## <a name="canimationtimereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>C애니메이션타이머이벤트::세트애니메이션컨트롤러

애니메이션 컨트롤러에 대한 포인터를 저장하여 이벤트를 라우팅합니다.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>매개 변수

*p애니메이션 컨트롤러*<br/>
이벤트를 수신하는 애니메이션 컨트롤러에 대한 포인터입니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
