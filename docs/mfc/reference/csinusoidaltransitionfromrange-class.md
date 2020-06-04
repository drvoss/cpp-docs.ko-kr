---
title: CSinusoidalTransitionFromRange 클래스
ms.date: 11/04/2016
f1_keywords:
- CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMaximumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMinimumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_period
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_slope
helpviewer_keywords:
- CSinusoidalTransitionFromRange [MFC], CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange [MFC], Create
- CSinusoidalTransitionFromRange [MFC], m_dblMaximumValue
- CSinusoidalTransitionFromRange [MFC], m_dblMinimumValue
- CSinusoidalTransitionFromRange [MFC], m_duration
- CSinusoidalTransitionFromRange [MFC], m_period
- CSinusoidalTransitionFromRange [MFC], m_slope
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
ms.openlocfilehash: 0612a4b365b928d3c9be6d76168a76b4ee1caa85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318250"
---
# <a name="csinusoidaltransitionfromrange-class"></a>CSinusoidalTransitionFromRange 클래스

진동 범위가 지정된 사인 곡선 범위 전환을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CSinusoidalTransitionFromRange : public CBaseTransition;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CSinusoidal전환범위::CSinusoidal전환범위](#csinusoidaltransitionfromrange)|전환 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSinusoidal전환범위::만들기](#create)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다. [(재정의 CBaseTransition::만들기.)](../../mfc/reference/cbasetransition-class.md#create)|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CSinusoidal전환에서 범위::m_dblMaximumValue](#m_dblmaximumvalue)|정현파의 피크에서 애니메이션 변수의 값입니다.|
|[CSinusoidal전환에서범위::m_dblMinimumValue](#m_dblminimumvalue)|정현파의 쓰루에서 애니메이션 변수의 값입니다.|
|[CSinusoidal전환범위::m_duration](#m_duration)|전환 기간입니다.|
|[CSinusoidal전환에서범위::m_period](#m_period)|초 에서 정현파의 진동 기간.|
|[CSinusoidal전환에서범위::m_slope](#m_slope)|전환 시작 시 경사입니다.|

## <a name="remarks"></a>설명

애니메이션 변수의 값은 정현파 범위 전환의 전체 기간 동안 지정된 최소값과 최대값 사이에서 변동합니다. 경사 매개변수는 다른 매개변수에 의해 지정된 두 개의 가능한 사위파 사이에서 모호성을 조정하는 데 사용됩니다. 모든 전환이 자동으로 지워지므로 운영자 new를 사용하여 할당하는 것이 좋습니다. 캡슐화된 IUIAnimationTransition COM 개체는 CAnimationController::AnimateGroup에 의해 만들어지며, 그때까지는 NULL이 됩니다. 이 COM 개체를 만든 후 멤버 변수를 변경하면 아무런 효과가 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C베이스 트랜지션](../../mfc/reference/cbasetransition-class.md)

[CSinusoidal전환에서범위](../../mfc/reference/csinusoidaltransitionfromrange-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="csinusoidaltransitionfromrangecreate"></a><a name="create"></a>CSinusoidal전환범위::만들기

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

## <a name="csinusoidaltransitionfromrangecsinusoidaltransitionfromrange"></a><a name="csinusoidaltransitionfromrange"></a>CSinusoidal전환범위::CSinusoidal전환범위

전환 개체를 생성합니다.

```
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,
    DOUBLE dblMinimumValue,
    DOUBLE dblMaximumValue,
    UI_ANIMATION_SECONDS period,
    UI_ANIMATION_SLOPE slope);
```

### <a name="parameters"></a>매개 변수

*기간*<br/>
전환 기간입니다.

*dblMinimum값*<br/>
정현파의 쓰루에서 애니메이션 변수의 값입니다.

*dblMaximumValue*<br/>
정현파의 피크에서 애니메이션 변수의 값입니다.

*기간*<br/>
초 에서 정현파의 진동 기간.

*경사*<br/>
전환 시작 시 경사입니다.

## <a name="csinusoidaltransitionfromrangem_dblmaximumvalue"></a><a name="m_dblmaximumvalue"></a>CSinusoidal전환에서 범위::m_dblMaximumValue

정현파의 피크에서 애니메이션 변수의 값입니다.

```
DOUBLE m_dblMaximumValue;
```

## <a name="csinusoidaltransitionfromrangem_dblminimumvalue"></a><a name="m_dblminimumvalue"></a>CSinusoidal전환에서범위::m_dblMinimumValue

정현파의 쓰루에서 애니메이션 변수의 값입니다.

```
DOUBLE m_dblMinimumValue;
```

## <a name="csinusoidaltransitionfromrangem_duration"></a><a name="m_duration"></a>CSinusoidal전환범위::m_duration

전환 기간입니다.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="csinusoidaltransitionfromrangem_period"></a><a name="m_period"></a>CSinusoidal전환에서범위::m_period

초 에서 정현파의 진동 기간.

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="csinusoidaltransitionfromrangem_slope"></a><a name="m_slope"></a>CSinusoidal전환에서범위::m_slope

전환 시작 시 경사입니다.

```
UI_ANIMATION_SLOPE m_slope;
```

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
