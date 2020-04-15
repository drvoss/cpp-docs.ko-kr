---
title: CReversalTransition 클래스
ms.date: 11/04/2016
f1_keywords:
- CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition::CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition::Create
- AFXANIMATIONCONTROLLER/CReversalTransition::m_duration
helpviewer_keywords:
- CReversalTransition [MFC], CReversalTransition
- CReversalTransition [MFC], Create
- CReversalTransition [MFC], m_duration
ms.assetid: e89516be-2d07-4885-95a8-fc278f46e3ad
ms.openlocfilehash: 73d12fb6bbaefcfac1437248ebe11f3a5c24c45b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368313"
---
# <a name="creversaltransition-class"></a>CReversalTransition 클래스

역방향 전환을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CReversalTransition : public CBaseTransition;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C반전전환::C역전전환](#creversaltransition)|반전 전환 개체를 생성하고 해당 기간을 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C반전전환::만들기](#create)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다. [(재정의 CBaseTransition::만들기.)](../../mfc/reference/cbasetransition-class.md#create)|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C반전전환::m_duration](#m_duration)|전환 기간입니다.|

## <a name="remarks"></a>설명

반전 전환은 주어진 기간 동안 방향을 원활하게 변경합니다. 최종 값은 초기 값과 동일하며 최종 속도는 초기 속도의 음수가 됩니다. 모든 전환이 자동으로 지워지므로 운영자 new를 사용하여 할당하는 것이 좋습니다. 캡슐화된 IUIAnimationTransition COM 개체는 CAnimationController::AnimateGroup에 의해 만들어지며, 그때까지는 NULL이 됩니다. 이 COM 개체를 만든 후 멤버 변수를 변경하면 아무런 효과가 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C베이스 트랜지션](../../mfc/reference/cbasetransition-class.md)

[C역전전환](../../mfc/reference/creversaltransition-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="creversaltransitioncreate"></a><a name="create"></a>C반전전환::만들기

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

## <a name="creversaltransitioncreversaltransition"></a><a name="creversaltransition"></a>C반전전환::C역전전환

반전 전환 개체를 생성하고 해당 기간을 초기화합니다.

```
CReversalTransition(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>매개 변수

*기간*<br/>
전환 기간입니다.

## <a name="creversaltransitionm_duration"></a><a name="m_duration"></a>C반전전환::m_duration

전환 기간입니다.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
