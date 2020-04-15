---
title: CSmoothStopTransition 클래스
ms.date: 11/04/2016
f1_keywords:
- CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::Create
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_maximumDuration
helpviewer_keywords:
- CSmoothStopTransition [MFC], CSmoothStopTransition
- CSmoothStopTransition [MFC], Create
- CSmoothStopTransition [MFC], m_dblFinalValue
- CSmoothStopTransition [MFC], m_maximumDuration
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
ms.openlocfilehash: 0ba550b4a0b9443d0681e17195687fb94c207ace
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318198"
---
# <a name="csmoothstoptransition-class"></a>CSmoothStopTransition 클래스

부드러운 중지 전환을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CSmoothStopTransition : public CBaseTransition;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C스무스스톱 트랜지션::C스무스스톱트랜지션](#csmoothstoptransition)|부드러운 중지 전환을 구성하고 최대 지속 시간과 최종 값을 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C스무스스톱 전환::만들기](#create)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다. [(재정의 CBaseTransition::만들기.)](../../mfc/reference/cbasetransition-class.md#create)|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C스무스스톱트랜지션:m_dblFinalValue](#m_dblfinalvalue)|전환이 끝날 때의 애니메이션 변수의 값입니다.|
|[C스무스스톱 트랜지션::m_maximumDuration](#m_maximumduration)|전환의 최대 기간입니다.|

## <a name="remarks"></a>설명

매끄러운 정지 전환은 지정된 최종 값에 접근할 때 속도가 느려지고 속도가 0으로 느려집니다. 전환 기간은 초기 속도, 초기 값과 최종 값 간의 차이 및 지정된 최대 기간에 따라 결정됩니다. 단일 포물선 호로 구성된 솔루션이 없는 경우 이 메서드는 입방 전환을 만듭니다. 모든 전환이 자동으로 지워지므로 운영자 new를 사용하여 할당하는 것이 좋습니다. 캡슐화된 IUIAnimationTransition COM 개체는 CAnimationController::AnimateGroup에 의해 만들어지며, 그때까지는 NULL이 됩니다. 이 COM 개체를 만든 후 멤버 변수를 변경하면 아무런 효과가 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C베이스 트랜지션](../../mfc/reference/cbasetransition-class.md)

[C스무스스톱트랜지션](../../mfc/reference/csmoothstoptransition-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="csmoothstoptransitioncreate"></a><a name="create"></a>C스무스스톱 전환::만들기

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

## <a name="csmoothstoptransitioncsmoothstoptransition"></a><a name="csmoothstoptransition"></a>C스무스스톱 트랜지션::C스무스스톱트랜지션

부드러운 중지 전환을 구성하고 최대 지속 시간과 최종 값을 초기화합니다.

```
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>매개 변수

*최대지속시간*<br/>
전환의 최대 기간입니다.

*dblFinalValue*<br/>
전환이 끝날 때의 애니메이션 변수의 값입니다.

## <a name="csmoothstoptransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>C스무스스톱트랜지션:m_dblFinalValue

전환이 끝날 때의 애니메이션 변수의 값입니다.

```
DOUBLE m_dblFinalValue;
```

## <a name="csmoothstoptransitionm_maximumduration"></a><a name="m_maximumduration"></a>C스무스스톱 트랜지션::m_maximumDuration

전환의 최대 기간입니다.

```
UI_ANIMATION_SECONDS m_maximumDuration;
```

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
