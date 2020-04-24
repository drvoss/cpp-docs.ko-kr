---
title: CAnimationStoryboardEventHandler 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationStoryboardEventHandler [MFC], CAnimationStoryboardEventHandler
- CAnimationStoryboardEventHandler [MFC], CreateInstance
- CAnimationStoryboardEventHandler [MFC], OnStoryboardStatusChanged
- CAnimationStoryboardEventHandler [MFC], OnStoryboardUpdated
- CAnimationStoryboardEventHandler [MFC], SetAnimationController
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
ms.openlocfilehash: 986555ca91d19dfa838f807665f2cbf9a003bcef
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755112"
---
# <a name="canimationstoryboardeventhandler-class"></a>CAnimationStoryboardEventHandler 클래스

스토리보드의 상태가 변경되거나 스토리보드가 업데이트될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C애니메이션스토리보드이벤트핸들러::C애니메이션스토리보드이벤트핸들러](#canimationstoryboardeventhandler)|`CAnimationStoryboardEventHandler` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션스토리보드이벤트핸들러::만들기 인스턴스](#createinstance)|콜백 인스턴스를 `CAnimationStoryboardEventHandler` 만듭니다.|
|[C애니메이션스토리보드이벤트핸들러::온스토리보드상태 변경](#onstoryboardstatuschanged)|스토리보드의 상태가 변경될 때 발생하는 `OnStoryboardStatusChanged` 이벤트를 처리합니다(재정의.) `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged`|
|[C애니메이션스토리보드이벤트핸들러::온스토리보드 업데이트](#onstoryboardupdated)|스토리보드가 `OnStoryboardUpdated` 업데이트될 때 발생하는 이벤트를 처리합니다(재정의.) `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated`|
|[C애니메이션스토리보드이벤트핸들러::세트애니메이션컨트롤러](#setanimationcontroller)|애니메이션 컨트롤러에 대한 포인터를 저장하여 이벤트를 라우팅합니다.|

## <a name="remarks"></a>설명

이 이벤트 처리기를 호출할 `IUIAnimationStoryboard::SetStoryboardEventHandler` `CAnimationController::EnableStoryboardEventHandler`때 메서드에 생성되고 전달됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CUIAnimationCallbackBase`

`CUIAnimationStoryboardEventHandlerBase`

`CAnimationStoryboardEventHandler`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationstoryboardeventhandlercanimationstoryboardeventhandler"></a><a name="canimationstoryboardeventhandler"></a>C애니메이션스토리보드이벤트핸들러::C애니메이션스토리보드이벤트핸들러

C애니메이션스토리보드이벤트오브젝트를 생성합니다.

```
CAnimationStoryboardEventHandler();
```

## <a name="canimationstoryboardeventhandlercreateinstance"></a><a name="createinstance"></a>C애니메이션스토리보드이벤트핸들러::만들기 인스턴스

CAnimationStoryboardEventHandler 콜백의 인스턴스를 만듭니다.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationStoryboardEventHandler** ppHandler);
```

### <a name="parameters"></a>매개 변수

*p애니메이션 컨트롤러*<br/>
이벤트를 수신하는 애니메이션 컨트롤러에 대한 포인터입니다.

*ppHandler*

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="canimationstoryboardeventhandleronstoryboardstatuschanged"></a><a name="onstoryboardstatuschanged"></a>C애니메이션스토리보드이벤트핸들러::온스토리보드상태 변경

스토리보드 상태 변경 이벤트 처리, 스토리보드의 상태가 변경될 때 발생

```
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>매개 변수

*스토리 보드*<br/>
상태가 변경된 스토리보드에 대한 포인터입니다.

*new Status*<br/>
새 스토리보드 상태를 지정합니다.

*이전 상태*<br/>
이전 스토리보드 상태를 지정합니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK. 그렇지 않으면 E_FAIL.

## <a name="canimationstoryboardeventhandleronstoryboardupdated"></a><a name="onstoryboardupdated"></a>C애니메이션스토리보드이벤트핸들러::온스토리보드 업데이트

스토리보드 업데이트 이벤트 처리

```
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```

### <a name="parameters"></a>매개 변수

*스토리 보드*<br/>
업데이트된 스토리보드에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK. 그렇지 않으면 E_FAIL.

## <a name="canimationstoryboardeventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>C애니메이션스토리보드이벤트핸들러::세트애니메이션컨트롤러

애니메이션 컨트롤러에 대한 포인터를 저장하여 이벤트를 라우팅합니다.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>매개 변수

*p애니메이션 컨트롤러*<br/>
이벤트를 수신하는 애니메이션 컨트롤러에 대한 포인터입니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
