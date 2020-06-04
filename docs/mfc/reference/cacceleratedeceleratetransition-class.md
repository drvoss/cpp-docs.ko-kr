---
title: CAccelerateDecerate전환 클래스
ms.date: 11/04/2016
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
ms.openlocfilehash: 356ba30e6d9a638672d2c356676735ebfaed8f3e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371143"
---
# <a name="cacceleratedeceleratetransition-class"></a>CAccelerateDecerate전환 클래스

가속-감속 전환을 구현합니다.

## <a name="syntax"></a>구문

```
class CAccelerateDecelerateTransition : public CBaseTransition;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAccelerateDecerate전환::CAccelerateDecelerate전환](#cacceleratedeceleratetransition)|전환 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAccelerateDecerate전환::만들기](#create)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다. [(재정의 CBaseTransition::만들기.)](../../mfc/reference/cbasetransition-class.md#create)|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CAccelerateDecerate전환::m_accelerationRatio](#m_accelerationratio)|지속 시간까지 가속화하는 데 소요된 시간의 비율입니다.|
|[CAccelerateDecerate전환::m_decelerationRatio](#m_decelerationratio)|지속 시간으로 감속하는 데 소요된 시간의 비율입니다.|
|[CAccelerateDecerate전환::m_duration](#m_duration)|전환 기간입니다.|
|[CAccelerateDecerate전환::m_finalValue](#m_finalvalue)|전환이 끝날 때의 애니메이션 변수의 값입니다.|

## <a name="remarks"></a>설명

가속 감속 전환 중에 애니메이션 변수의 속도가 빨라지고 전환 기간 동안 속도가 느려지며 지정된 값으로 끝납니다. 다양한 가속 및 감속 비율을 지정하여 변수가 독립적으로 가속 및 감속하는 속도를 제어할 수 있습니다. 초기 속도가 0이면 가속 비는 변수가 가속을 소비하는 기간의 일부입니다. 감속 비율도 마찬가지입니다. 초기 속도가 0이 아닌 경우 속도가 0에 도달하는 속도와 전환 종료 사이의 시간의 일부입니다. 가속도와 감속비는 최대 1.0으로 합산되어야 합니다. 모든 전환이 자동으로 지워지므로 운영자 new를 사용하여 할당하는 것이 좋습니다. 캡슐화된 IUIAnimationTransition COM 개체는 CAnimationController::AnimateGroup에 의해 만들어지며, 그때까지는 NULL이 됩니다. 이 COM 개체를 만든 후 멤버 변수를 변경하면 아무런 효과가 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C베이스 트랜지션](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="cacceleratedeceleratetransitioncacceleratedeceleratetransition"></a><a name="cacceleratedeceleratetransition"></a>CAccelerateDecerate전환::CAccelerateDecelerate전환

전환 개체를 생성합니다.

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>매개 변수

*기간*<br/>
전환 기간입니다.

*finalValue*<br/>
전환이 끝날 때의 애니메이션 변수의 값입니다.

*가속도*<br/>
지속 시간까지 가속화하는 데 소요된 시간의 비율입니다.

*감속비율*<br/>
지속 시간으로 감속하는 데 소요된 시간의 비율입니다.

## <a name="cacceleratedeceleratetransitioncreate"></a><a name="create"></a>CAccelerateDecerate전환::만들기

전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>매개 변수

*p라이브러리*<br/>
표준 전환 라이브러리를 정의하는 [IUIAnimationTransitionLibrary 인터페이스에](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 전환이 성공적으로 만들어지면 그렇지 않으면 거짓.

## <a name="cacceleratedeceleratetransitionm_accelerationratio"></a><a name="m_accelerationratio"></a>CAccelerateDecerate전환::m_accelerationRatio

지속 시간까지 가속화하는 데 소요된 시간의 비율입니다.

```
DOUBLE m_accelerationRatio;
```

## <a name="cacceleratedeceleratetransitionm_decelerationratio"></a><a name="m_decelerationratio"></a>CAccelerateDecerate전환::m_decelerationRatio

지속 시간으로 감속하는 데 소요된 시간의 비율입니다.

```
DOUBLE m_decelerationRatio;
```

## <a name="cacceleratedeceleratetransitionm_duration"></a><a name="m_duration"></a>CAccelerateDecerate전환::m_duration

전환 기간입니다.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="cacceleratedeceleratetransitionm_finalvalue"></a><a name="m_finalvalue"></a>CAccelerateDecerate전환::m_finalValue

전환이 끝날 때의 애니메이션 변수의 값입니다.

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
