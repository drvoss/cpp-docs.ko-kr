---
title: CAnimationVariableChangeHandler 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
ms.openlocfilehash: 2dc8f2c03f9df34012fb9db1ed5e5b0bb448b17f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755048"
---
# <a name="canimationvariablechangehandler-class"></a>CAnimationVariableChangeHandler 클래스

애니메이션 변수 값이 변경될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|`CAnimationVariableChangeHandler` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CreateInstance`|개체의 `CAnimationVariableChangeHandler` 인스턴스를 만듭니다.|
|[C애니메이션변수변경핸들러::온밸류변경](#onvaluechanged)|애니메이션 변수의 값이 변경된 경우 호출됩니다. ( `CUIAnimationVariableChangeHandlerBase::OnValueChanged`을 재정의합니다.)|
|[C애니메이션변수체인지핸들러:세트애니메이션컨트롤러](#setanimationcontroller)|애니메이션 컨트롤러에 대한 포인터를 저장하여 이벤트를 라우팅합니다.|

## <a name="remarks"></a>설명

이 이벤트 처리기는 `IUIAnimationVariable::SetVariableChangeHandler` 호출하거나 `CAnimationVariable::EnableValueChangedEvent` `CAnimationBaseObject::EnableValueChangedEvent` 애니메이션 개체에 캡슐화된 모든 애니메이션 변수에 대해 이 이벤트를 활성화할 때 메서드에 생성되고 전달됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CUIAnimationCallbackBase`

`CUIAnimationVariableChangeHandlerBase`

`CAnimationVariableChangeHandler`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationvariablechangehandleronvaluechanged"></a><a name="onvaluechanged"></a>C애니메이션변수변경핸들러::온밸류변경

애니메이션 변수의 값이 변경된 경우 호출됩니다.

```
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```

### <a name="parameters"></a>매개 변수

*스토리 보드*<br/>
변수에 애니메이션을 만드는 스토리보드입니다.

*변수*<br/>
업데이트된 애니메이션 변수입니다.

*newValue*<br/>
새 값입니다.

*이전값*<br/>
이전 값입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="canimationvariablechangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>C애니메이션변수체인지핸들러:세트애니메이션컨트롤러

애니메이션 컨트롤러에 대한 포인터를 저장하여 이벤트를 라우팅합니다.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>매개 변수

*p애니메이션 컨트롤러*<br/>
이벤트를 수신하는 애니메이션 컨트롤러에 대한 포인터입니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
