---
title: CInterpolatorBase 클래스
ms.date: 11/04/2016
f1_keywords:
- CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CreateInstance
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDependencies
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetFinalValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetCustomInterpolator
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetInitialValueAndVelocity
helpviewer_keywords:
- CInterpolatorBase [MFC], CInterpolatorBase
- CInterpolatorBase [MFC], CreateInstance
- CInterpolatorBase [MFC], GetDependencies
- CInterpolatorBase [MFC], GetDuration
- CInterpolatorBase [MFC], GetFinalValue
- CInterpolatorBase [MFC], InterpolateValue
- CInterpolatorBase [MFC], InterpolateVelocity
- CInterpolatorBase [MFC], SetCustomInterpolator
- CInterpolatorBase [MFC], SetDuration
- CInterpolatorBase [MFC], SetInitialValueAndVelocity
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
ms.openlocfilehash: efa08aa5dd556d7e136323c31451a9f33bd72ec6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754953"
---
# <a name="cinterpolatorbase-class"></a>CInterpolatorBase 클래스

애니메이션 API에서 애니메이션 변수의 새 값을 계산해야 할 때 호출하는 콜백을 구현합니다.

## <a name="syntax"></a>구문

```
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[인터폴레이터베이스::C인터폴레이터베이스](#cinterpolatorbase)|개체를 `CInterpolatorBase` 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CInterpolatorBase::만들기 인스턴스](#createinstance)|인스턴스를 `CInterpolatorBase` 만들고 이벤트를 처리할 사용자 지정 보간기에 대한 포인터를 저장합니다.|
|[CInterpolatorBase::Get 의존성](#getdependencies)|인터폴레이터의 종속성을 가져옵니다. ( `CUIAnimationInterpolatorBase::GetDependencies`을 재정의합니다.)|
|[CInterpolator베이스 ::GetDuration](#getduration)|인터폴레이터의 지속 시간을 가져옵니다. ( `CUIAnimationInterpolatorBase::GetDuration`을 재정의합니다.)|
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|보간자가 리드하는 최종 값을 가져옵니다. ( `CUIAnimationInterpolatorBase::GetFinalValue`을 재정의합니다.)|
|[CInterpolatorBase::인터폴레이터값](#interpolatevalue)|지정된 오프셋에서 값을 보간합니다(재정의.) `CUIAnimationInterpolatorBase::InterpolateValue`|
|[CInterpolatorBase::보간속도](#interpolatevelocity)|지정된 오프셋에서 속도를 보간합니다(재정의.) `CUIAnimationInterpolatorBase::InterpolateVelocity`|
|[CInterpolator베이스 ::설정 사용자 정의 인터폴리터](#setcustominterpolator)|이벤트를 처리할 사용자 지정 보간기에 대한 포인터를 저장합니다.|
|[CInterpolator베이스::설정 기간](#setduration)|보간자의 지속 시간을 설정합니다(재정의.) `CUIAnimationInterpolatorBase::SetDuration`|
|[CInterpolatorBase::SetInitial값AndVelocity](#setinitialvalueandvelocity)|인터폴레이터의 초기 값과 속도를 설정합니다. ( `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`을 재정의합니다.)|

## <a name="remarks"></a>설명

이 처리기는 애니메이션 `IUIAnimationTransitionFactory::CreateTransition` 초기화 `CCustomTransition` `CAnimationController::AnimateGroup`프로세스(시작)의 일부로 개체를 만들 때 만들어지고 전달됩니다. 일반적으로 이 클래스를 직접 사용할 필요는 없으며 모든 이벤트를 `CCustomInterpolator`-derived 클래스로 라우팅할 뿐이며, 포인터는 `CCustomTransition`의 생성자에게 전달됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="cinterpolatorbasecinterpolatorbase"></a><a name="cinterpolatorbase"></a>인터폴레이터베이스::C인터폴레이터베이스

CInterpolatorBase 개체를 생성합니다.

```
CInterpolatorBase();
```

## <a name="cinterpolatorbasecreateinstance"></a><a name="createinstance"></a>CInterpolatorBase::만들기 인스턴스

CInterpolatorBase의 인스턴스를 만들고 이벤트를 처리할 사용자 지정 보간자에 대한 포인터를 저장합니다.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>매개 변수

*핀인터폴레이터*<br/>
사용자 지정 보간기의 포인터입니다.

*ppHandler*<br/>
출력 함수가 반환될 때 CInterpolatorBase 인스턴스에 대한 포인터를 포함합니다.

### <a name="return-value"></a>Return Value

## <a name="cinterpolatorbasegetdependencies"></a><a name="getdependencies"></a>CInterpolatorBase::Get 의존성

인터폴레이터의 종속성을 가져옵니다.

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>매개 변수

*초기값 종속성*<br/>
출력 SetInitialValueAndVelocity에 전달 된 초기 값에 종속 된 보간기의 측면입니다.

*초기Velocity의존적*<br/>
출력 초기 속도에 의존하는 보간기의 측면은 SetInitialValueAndVelocity로 전달되었습니다.

*지속 시간 종속성*<br/>
출력 SetDuration에 전달된 기간에 따라 인터폴레이터의 측면입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, CCustomInterpolator가 설정되지 않은 경우 E_FAIL 반환하거나 사용자 지정 구현은 GetDependencies 메서드에서 FALSE를 반환합니다.

## <a name="cinterpolatorbasegetduration"></a><a name="getduration"></a>CInterpolator베이스 ::GetDuration

인터폴레이터의 지속 시간을 가져옵니다.

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
출력 전환 기간(초)입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, CCustomInterpolator가 설정되지 않은 경우 E_FAIL 반환하거나 사용자 지정 구현은 GetDuration 메서드에서 FALSE를 반환합니다.

## <a name="cinterpolatorbasegetfinalvalue"></a><a name="getfinalvalue"></a>CInterpolatorBase::GetFinalValue

보간자가 리드하는 최종 값을 가져옵니다.

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>매개 변수

*value*<br/>
출력 전환이 끝날 때 변수의 최종 값입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, CCustomInterpolator가 설정되지 않은 경우 E_FAIL 반환하거나 사용자 지정 구현은 GetFinalValue 메서드에서 FALSE를 반환합니다.

## <a name="cinterpolatorbaseinterpolatevalue"></a><a name="interpolatevalue"></a>CInterpolatorBase::인터폴레이터값

지정된 오프셋에서 값을 보간합니다.

```
IFACEMETHOD(InterpolateValue)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* value);
```

### <a name="parameters"></a>매개 변수

*offset*<br/>
전환 시작부터 오프셋입니다. 오프셋은 항상 0보다 크거나 같으며 전환 기간보다 적습니다. 전환 기간이 0인 경우 이 메서드가 호출되지 않습니다.

*value*<br/>
출력 보간된 값입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, CCustom Interpolator가 설정되지 않은 경우 E_FAIL 반환하거나 사용자 지정 구현이 InterpolateValue 메서드에서 FALSE를 반환합니다.

## <a name="cinterpolatorbaseinterpolatevelocity"></a><a name="interpolatevelocity"></a>CInterpolatorBase::보간속도

지정된 오프셋에서 속도를 보간합니다.

```
IFACEMETHOD(InterpolateVelocity)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* velocity);
```

### <a name="parameters"></a>매개 변수

*offset*<br/>
전환 시작부터 오프셋입니다. 오프셋은 항상 0보다 크거나 같으며 전환 기간보다 크거나 동일합니다. 전환 기간이 0인 경우 이 메서드가 호출되지 않습니다.

*velocity*<br/>
출력 오프셋에서 변수의 속도입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, CCustomInterpolator가 설정되지 않은 경우 E_FAIL 반환하거나 사용자 지정 구현은 interpolateVelocity 메서드에서 FALSE를 반환합니다.

## <a name="cinterpolatorbasesetcustominterpolator"></a><a name="setcustominterpolator"></a>CInterpolator베이스 ::설정 사용자 정의 인터폴리터

이벤트를 처리할 사용자 지정 보간기에 대한 포인터를 저장합니다.

```cpp
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>매개 변수

*핀인터폴레이터*<br/>
사용자 지정 보간기의 포인터입니다.

## <a name="cinterpolatorbasesetduration"></a><a name="setduration"></a>CInterpolator베이스::설정 기간

인터폴레이터의 지속 시간 설정

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
전환 기간입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, CCustomInterpolator가 설정되지 않은 경우 E_FAIL 반환하거나 사용자 지정 구현은 SetDuration 메서드에서 FALSE를 반환합니다.

## <a name="cinterpolatorbasesetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a>CInterpolatorBase::SetInitial값AndVelocity

인터폴레이터의 초기 값과 속도를 설정합니다.

```
IFACEMETHOD(SetInitialValueAndVelocity)(
    __in DOUBLE initialValue,
    __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>매개 변수

*초기 값*<br/>
전환 시작 시 변수의 값입니다.

*초기 속도*<br/>
전환 시작 시 변수의 속도입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, CCustomInterpolator가 설정되지 않은 경우 E_FAIL 반환하거나 사용자 지정 구현은 SetInitialValueAndVelocity 메서드에서 FALSE를 반환합니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
