---
title: CDiscreteTransition 클래스
ms.date: 11/04/2016
f1_keywords:
- CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::Create
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_delay
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_hold
helpviewer_keywords:
- CDiscreteTransition [MFC], CDiscreteTransition
- CDiscreteTransition [MFC], Create
- CDiscreteTransition [MFC], m_dblFinalValue
- CDiscreteTransition [MFC], m_delay
- CDiscreteTransition [MFC], m_hold
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
ms.openlocfilehash: 2a32ee7921e927e25a5196d38c8f5ae350ab2b8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375664"
---
# <a name="cdiscretetransition-class"></a>CDiscreteTransition 클래스

불연속 전환을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CDiscreteTransition : public CBaseTransition;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C이너드레테 트랜지션::C이너디티트랜지션](#cdiscretetransition)|불연속 전환 개체를 생성하고 해당 매개 변수를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C이너드레테 트랜지션::만들기](#create)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다. [(재정의 CBaseTransition::만들기.)](../../mfc/reference/cbasetransition-class.md#create)|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C이너드레테 트랜지션::m_dblFinalValue](#m_dblfinalvalue)|전환이 끝날 때의 애니메이션 변수의 값입니다.|
|[C이너드레테 트랜지션::m_delay](#m_delay)|순간 전환을 최종 값으로 지연시키는 시간입니다.|
|[C이너드레테 트랜지션::m_hold](#m_hold)|변수를 최종 값으로 보유할 시간입니다.|

## <a name="remarks"></a>설명

불연속 전환 중에 애니메이션 변수는 지정된 지연 시간에 대한 초기 값에 유지된 다음 지정된 최종 값으로 즉시 전환되고 지정된 보류 시간에 대해 해당 값으로 유지됩니다. 모든 전환이 자동으로 지워지므로 운영자 new를 사용하여 할당하는 것이 좋습니다. 캡슐화된 IUIAnimationTransition COM 개체는 CAnimationController::AnimateGroup에 의해 만들어지며, 그때까지는 NULL이 됩니다. 이 COM 개체를 만든 후 멤버 변수를 변경하면 아무런 효과가 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C베이스 트랜지션](../../mfc/reference/cbasetransition-class.md)

[C이너드레테트랜지션](../../mfc/reference/cdiscretetransition-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="cdiscretetransitioncdiscretetransition"></a><a name="cdiscretetransition"></a>C이너드레테 트랜지션::C이너디티트랜지션

불연속 전환 개체를 생성하고 해당 매개 변수를 초기화합니다.

```
CDiscreteTransition(
    UI_ANIMATION_SECONDS delay,
    DOUBLE dblFinalValue,
    UI_ANIMATION_SECONDS hold);
```

### <a name="parameters"></a>매개 변수

*지연*<br/>
순간 전환을 최종 값으로 지연시키는 시간입니다.

*dblFinalValue*<br/>
전환이 끝날 때의 애니메이션 변수의 값입니다.

*개최*<br/>
변수를 최종 값으로 보유할 시간입니다.

## <a name="cdiscretetransitioncreate"></a><a name="create"></a>C이너드레테 트랜지션::만들기

전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

*p라이브러리*<br/>
표준 전환 라이브러리를 정의하는 [IUIAnimationTransitionLibrary 인터페이스에](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 전환이 성공적으로 만들어지면 그렇지 않으면 거짓.

## <a name="cdiscretetransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>C이너드레테 트랜지션::m_dblFinalValue

전환이 끝날 때의 애니메이션 변수의 값입니다.

```
DOUBLE m_dblFinalValue;
```

## <a name="cdiscretetransitionm_delay"></a><a name="m_delay"></a>C이너드레테 트랜지션::m_delay

순간 전환을 최종 값으로 지연시키는 시간입니다.

```
UI_ANIMATION_SECONDS m_delay;
```

## <a name="cdiscretetransitionm_hold"></a><a name="m_hold"></a>C이너드레테 트랜지션::m_hold

변수를 최종 값으로 보유할 시간입니다.

```
UI_ANIMATION_SECONDS m_hold;
```

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
