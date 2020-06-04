---
title: CAnimationManagerEventHandler 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::OnManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationManagerEventHandler [MFC], CAnimationManagerEventHandler
- CAnimationManagerEventHandler [MFC], CreateInstance
- CAnimationManagerEventHandler [MFC], OnManagerStatusChanged
- CAnimationManagerEventHandler [MFC], SetAnimationController
ms.assetid: 6089ec07-e661-4805-b227-823b4652aade
ms.openlocfilehash: 58bb37e9de40f4bc711b417eab107aa55b8ff0e8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750111"
---
# <a name="canimationmanagereventhandler-class"></a>CAnimationManagerEventHandler 클래스

애니메이션 관리자의 상태가 변경될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationManagerEventHandler : public CUIAnimationManagerEventHandlerBase<CAnimationManagerEventHandler>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C애니메이션관리자이벤트핸들러::C애니메이션매니저이벤트핸들러](#canimationmanagereventhandler)|`CAnimationManagerEventHandler` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션관리자이벤트핸들러::만들기 인스턴스](#createinstance)|개체의 `CAnimationManagerEventHandler` 인스턴스를 만듭니다.|
|[C애니메이션관리자이벤트핸들러::온매니저 상태 변경](#onmanagerstatuschanged)|애니메이션 관리자의 상태가 변경된 경우 호출됩니다. ( `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`을 재정의합니다.)|
|[C애니메이션관리자이벤트핸들러::세트애니메이션컨트롤러](#setanimationcontroller)|애니메이션 컨트롤러에 대한 포인터를 저장하여 이벤트를 라우팅합니다.|

## <a name="remarks"></a>설명

이 이벤트 처리기는 CAnimationController::EnableAnimationManagerEvent를 호출할 때 IUIAnimationManager::SetManagerEvent 메서드에 생성되고 전달됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CUIAnimationCallbackBase`

`CUIAnimationManagerEventHandlerBase`

`CAnimationManagerEventHandler`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationmanagereventhandlercanimationmanagereventhandler"></a><a name="canimationmanagereventhandler"></a>C애니메이션관리자이벤트핸들러::C애니메이션매니저이벤트핸들러

Visual Studio 2010 SP1이 필요합니다.

CAnimationManagerEventHandler 개체를 생성합니다.

```
CAnimationManagerEventHandler();
```

## <a name="canimationmanagereventhandlercreateinstance"></a><a name="createinstance"></a>C애니메이션관리자이벤트핸들러::만들기 인스턴스

Visual Studio 2010 SP1이 필요합니다.

CAnimationManagerEventHandler 개체의 인스턴스를 만듭니다.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationManagerEventHandler** ppManagerEventHandler);
```

### <a name="parameters"></a>매개 변수

*p애니메이션 컨트롤러*<br/>
이벤트를 수신하는 애니메이션 컨트롤러에 대한 포인터입니다.

*pp관리자이벤트*<br/>
출력 메서드가 성공하면 애니메이션 관리자에 대한 상태 업데이트를 처리하는 COM 개체에 대한 포인터가 포함되어 있습니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="canimationmanagereventhandleronmanagerstatuschanged"></a><a name="onmanagerstatuschanged"></a>C애니메이션관리자이벤트핸들러::온매니저 상태 변경

Visual Studio 2010 SP1이 필요합니다.

애니메이션 관리자의 상태가 변경된 경우 호출됩니다.

```
IFACEMETHOD(OnManagerStatusChanged)(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>매개 변수

*new Status*<br/>
새 상태입니다.

*이전 상태*<br/>
이전 상태입니다.

### <a name="return-value"></a>Return Value

현재 구현은 항상 S_OK 반환합니다.

## <a name="canimationmanagereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>C애니메이션관리자이벤트핸들러::세트애니메이션컨트롤러

Visual Studio 2010 SP1이 필요합니다.

애니메이션 컨트롤러에 대한 포인터를 저장하여 이벤트를 라우팅합니다.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>매개 변수

*p애니메이션 컨트롤러*<br/>
이벤트를 수신하는 애니메이션 컨트롤러에 대한 포인터입니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
