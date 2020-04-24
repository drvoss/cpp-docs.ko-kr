---
title: CAnimationVariableIntegerChangeHandler 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableIntegerChangeHandler [MFC], CAnimationVariableIntegerChangeHandler
- CAnimationVariableIntegerChangeHandler [MFC], CreateInstance
- CAnimationVariableIntegerChangeHandler [MFC], OnIntegerValueChanged
- CAnimationVariableIntegerChangeHandler [MFC], SetAnimationController
ms.assetid: 6ac8e91b-e514-4ff6-babd-33f77c4b2b61
ms.openlocfilehash: dec940d2f5e68f0531fc917df447b5a1a5cb8189
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755049"
---
# <a name="canimationvariableintegerchangehandler-class"></a>CAnimationVariableIntegerChangeHandler 클래스

애니메이션 변수 값이 변경될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C애니메이션변수인테거체인지핸들러::C애니메이션변수인테저체인지핸들러](#canimationvariableintegerchangehandler)|`CAnimationVariableIntegerChangeHandler` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션변수인테저체인지핸들러::만들기 인스턴스](#createinstance)|콜백 인스턴스를 `CAnimationVariableIntegerChangeHandler` 만듭니다.|
|[C애니메이션변수인테거체인지핸들러::온인테이저밸류변경](#onintegervaluechanged)|애니메이션 변수의 값이 변경된 경우 호출됩니다. ( `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`을 재정의합니다.)|
|[C애니메이션변수인테저체인지핸들러::세트애니메이션컨트롤러](#setanimationcontroller)|애니메이션 컨트롤러에 대한 포인터를 저장하여 이벤트를 라우팅합니다.|

## <a name="remarks"></a>설명

이 이벤트 처리기는 IUIAnimationVariable::SetVariableIntegerChangeHandler 메서드를 만들고 CAnimationVariable::EnableIntegerValueChangedEvent 또는 CAnimationBaseValueEvent::EnableIntegerValueChangedEvent(애니메이션 개체에 캡슐화된 모든 애니메이션 변수에 대해 이 이벤트를 활성화)를 호출할 때 만들어집니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[MFC 클래스](../../mfc/reference/mfc-classes.md)

`CUIAnimationCallbackBase`

`CUIAnimationVariableIntegerChangeHandlerBase`

`CAnimationVariableIntegerChangeHandler`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationvariableintegerchangehandlercanimationvariableintegerchangehandler"></a><a name="canimationvariableintegerchangehandler"></a>C애니메이션변수인테거체인지핸들러::C애니메이션변수인테저체인지핸들러

CAnimationVariableIntegerChangeHandler 개체를 생성합니다.

```
CAnimationVariableIntegerChangeHandler ();
```

## <a name="canimationvariableintegerchangehandlercreateinstance"></a><a name="createinstance"></a>C애니메이션변수인테저체인지핸들러::만들기 인스턴스

CAnimationVariableIntegerChangeHandler 콜백의 인스턴스를 만듭니다.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationVariableIntegerChangeHandler** ppHandler);
```

### <a name="parameters"></a>매개 변수

*p애니메이션 컨트롤러*<br/>
이벤트를 수신하는 애니메이션 컨트롤러에 대한 포인터입니다.

*ppHandler*

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="canimationvariableintegerchangehandleronintegervaluechanged"></a><a name="onintegervaluechanged"></a>C애니메이션변수인테거체인지핸들러::온인테이저밸류변경

애니메이션 변수의 값이 변경된 경우 호출됩니다.

```
IFACEMETHOD(OnIntegerValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in INT32 newValue,
    __in INT32 previousValue);
```

### <a name="parameters"></a>매개 변수

*스토리 보드*<br/>
변수에 애니메이션을 만드는 스토리보드입니다.

*변수*<br/>
업데이트된 애니메이션 변수입니다.

*newValue*<br/>
새 반올림 된 값입니다.

*이전값*<br/>
이전 반올림 된 값입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK. 그렇지 않으면 E_FAIL.

## <a name="canimationvariableintegerchangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>C애니메이션변수인테저체인지핸들러::세트애니메이션컨트롤러

애니메이션 컨트롤러에 대한 포인터를 저장하여 이벤트를 라우팅합니다.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>매개 변수

*p애니메이션 컨트롤러*<br/>
이벤트를 수신하는 애니메이션 컨트롤러에 대한 포인터입니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
