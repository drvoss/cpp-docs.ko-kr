---
title: CSinusoidalTransitionFromVelocity 클래스
ms.date: 11/04/2016
f1_keywords:
- CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_period
helpviewer_keywords:
- CSinusoidalTransitionFromVelocity [MFC], CSinusoidalTransitionFromVelocity
- CSinusoidalTransitionFromVelocity [MFC], Create
- CSinusoidalTransitionFromVelocity [MFC], m_duration
- CSinusoidalTransitionFromVelocity [MFC], m_period
ms.assetid: cc885f17-b84b-45ee-8f1f-36a8bbb7adad
ms.openlocfilehash: 0df9ca6d140cb9e3ec85be3ce32760a66599c5d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318241"
---
# <a name="csinusoidaltransitionfromvelocity-class"></a>CSinusoidalTransitionFromVelocity 클래스

애니메이션 변수의 초기 속도에 의해 진폭이 결정되는 사인 곡선 속도 전환을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CSinusoidalTransitionFromVelocity : public CBaseTransition;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CSinusoidal전환에서벨로시티::CSinusoidal전환로부터벨로시티](#csinusoidaltransitionfromvelocity)|전환 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSinusoidal전환에서Velocity::만들기](#create)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다. [(재정의 CBaseTransition::만들기.)](../../mfc/reference/cbasetransition-class.md#create)|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CSinusoidal전환에서벨로시티::m_duration](#m_duration)|전환 기간입니다.|
|[CSinusoidal전환에서벨로시티::m_period](#m_period)|초 에서 정현파의 진동 기간.|

## <a name="remarks"></a>설명

애니메이션 변수의 값은 정현파 범위 전환의 전체 기간 동안 초기 값을 중심으로 진동합니다. 진동의 진폭은 전환이 시작될 때 애니메이션 변수의 속도에 의해 결정됩니다. 모든 전환이 자동으로 지워지므로 운영자 new를 사용하여 할당하는 것이 좋습니다. 캡슐화된 IUIAnimationTransition COM 개체는 CAnimationController::AnimateGroup에 의해 만들어지며, 그때까지는 NULL이 됩니다. 이 COM 개체를 만든 후 멤버 변수를 변경하면 아무런 효과가 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C베이스 트랜지션](../../mfc/reference/cbasetransition-class.md)

[CSinusoidal전환에서벨로시티](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="csinusoidaltransitionfromvelocitycreate"></a><a name="create"></a>CSinusoidal전환에서Velocity::만들기

전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>매개 변수

*p라이브러리*<br/>
표준 전환을 만드는 작업 라이브러리에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 전환이 성공적으로 만들어지면 그렇지 않으면 거짓.

## <a name="csinusoidaltransitionfromvelocitycsinusoidaltransitionfromvelocity"></a><a name="csinusoidaltransitionfromvelocity"></a>CSinusoidal전환에서벨로시티::CSinusoidal전환로부터벨로시티

전환 개체를 생성합니다.

```
CSinusoidalTransitionFromVelocity(
    UI_ANIMATION_SECONDS duration,
    UI_ANIMATION_SECONDS period);
```

### <a name="parameters"></a>매개 변수

*기간*<br/>
전환 기간입니다.

*기간*<br/>
초 에서 정현파의 진동 기간.

## <a name="csinusoidaltransitionfromvelocitym_duration"></a><a name="m_duration"></a>CSinusoidal전환에서벨로시티::m_duration

전환 기간입니다.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="csinusoidaltransitionfromvelocitym_period"></a><a name="m_period"></a>CSinusoidal전환에서벨로시티::m_period

초 에서 정현파의 진동 기간.

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
