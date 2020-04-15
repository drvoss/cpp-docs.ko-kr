---
title: CCubicTransition 클래스
ms.date: 11/04/2016
f1_keywords:
- CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::Create
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalVelocity
- AFXANIMATIONCONTROLLER/CCubicTransition::m_duration
helpviewer_keywords:
- CCubicTransition [MFC], CCubicTransition
- CCubicTransition [MFC], Create
- CCubicTransition [MFC], m_dblFinalValue
- CCubicTransition [MFC], m_dblFinalVelocity
- CCubicTransition [MFC], m_duration
ms.assetid: 4fc30e9c-160c-45e1-bdbe-51adf8fee9c5
ms.openlocfilehash: de376503111dab157ca34744863fb1d35a58785e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369342"
---
# <a name="ccubictransition-class"></a>CCubicTransition 클래스

3차원 전환을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CCubicTransition : public CBaseTransition;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C큐빅 트랜지션::C큐빅트랜지션](#ccubictransition)|전환 개체를 생성하고 해당 매개 변수를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C큐빅 전환::만들기](#create)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다. [(재정의 CBaseTransition::만들기.)](../../mfc/reference/cbasetransition-class.md#create)|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C큐빅 트랜지션::m_dblFinalValue](#m_dblfinalvalue)|전환이 끝날 때의 애니메이션 변수의 값입니다.|
|[C큐빅 트랜지션::m_dblFinalVelocity](#m_dblfinalvelocity)|전환이 끝날 때변수의 속도입니다.|
|[C큐빅 트랜지션::m_duration](#m_duration)|전환 기간입니다.|

## <a name="remarks"></a>설명

입방 전환 중에 애니메이션 변수의 값은 전환 기간 동안 초기 값에서 지정된 최종 값으로 변경되어 지정된 속도로 끝납니다. 모든 전환이 자동으로 지워지므로 운영자 new를 사용하여 할당하는 것이 좋습니다. 캡슐화된 IUIAnimationTransition COM 개체는 CAnimationController::AnimateGroup에 의해 만들어지며, 그때까지는 NULL이 됩니다. 이 COM 개체를 만든 후 멤버 변수를 변경하면 아무런 효과가 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C베이스 트랜지션](../../mfc/reference/cbasetransition-class.md)

`CCubicTransition`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="ccubictransitionccubictransition"></a><a name="ccubictransition"></a>C큐빅 트랜지션::C큐빅트랜지션

전환 개체를 생성하고 해당 매개 변수를 초기화합니다.

```
CCubicTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE finalVelocity);
```

### <a name="parameters"></a>매개 변수

*기간*<br/>
전환 기간입니다.

*finalValue*<br/>
전환이 끝날 때의 애니메이션 변수의 값입니다.

*최종벨로시티*<br/>
전환이 끝날 때변수의 속도입니다.

## <a name="ccubictransitioncreate"></a><a name="create"></a>C큐빅 전환::만들기

전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>매개 변수

*p라이브러리*<br/>
표준 전환 라이브러리를 정의하는 [IUIAnimationTransitionLibrary 인터페이스에](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 전환이 성공적으로 만들어지면 그렇지 않으면 거짓.

## <a name="ccubictransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>C큐빅 트랜지션::m_dblFinalValue

전환이 끝날 때의 애니메이션 변수의 값입니다.

```
DOUBLE m_dblFinalValue;
```

## <a name="ccubictransitionm_dblfinalvelocity"></a><a name="m_dblfinalvelocity"></a>C큐빅 트랜지션::m_dblFinalVelocity

전환이 끝날 때변수의 속도입니다.

```
DOUBLE m_dblFinalVelocity;
```

## <a name="ccubictransitionm_duration"></a><a name="m_duration"></a>C큐빅 트랜지션::m_duration

전환 기간입니다.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
