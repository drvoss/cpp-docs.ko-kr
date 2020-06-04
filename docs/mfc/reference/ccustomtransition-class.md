---
title: CCustomTransition 클래스
ms.date: 11/04/2016
f1_keywords:
- CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::Create
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialValueSpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialVelocitySpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_pInterpolator
helpviewer_keywords:
- CCustomTransition [MFC], CCustomTransition
- CCustomTransition [MFC], Create
- CCustomTransition [MFC], SetInitialValue
- CCustomTransition [MFC], SetInitialVelocity
- CCustomTransition [MFC], m_bInitialValueSpecified
- CCustomTransition [MFC], m_bInitialVelocitySpecified
- CCustomTransition [MFC], m_initialValue
- CCustomTransition [MFC], m_initialVelocity
- CCustomTransition [MFC], m_pInterpolator
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
ms.openlocfilehash: 76e0d12308ad579e4bdf9866dfcf1cde231a2d0c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749158"
---
# <a name="ccustomtransition-class"></a>CCustomTransition 클래스

사용자 지정 전환을 구현합니다.

## <a name="syntax"></a>구문

```
class CCustomTransition : public CBaseTransition;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C 사용자 지정 전환::C사용자 지정 전환](#ccustomtransition)|사용자 지정 전환 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C 사용자 지정 전환::만들기](#create)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다. [(재정의 CBaseTransition::만들기.)](../../mfc/reference/cbasetransition-class.md#create)|
|[C사용자 지정 전환::설정 초기 값](#setinitialvalue)|이 전환과 연결된 애니메이션 변수에 적용할 초기 값을 설정합니다.|
|[C 사용자 지정 전환::설정초기벨로시티](#setinitialvelocity)|이 전환과 연관된 애니메이션 변수에 적용되는 초기 속도를 설정합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C 사용자 지정 전환::m_bInitialValueSpecified](#m_binitialvaluespecified)|초기 값이 SetInitialValue로 지정되었는지 여부를 지정합니다.|
|[C 사용자 지정 전환::m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|초기 속도가 SetInitialVelocity로 지정되었는지 여부를 지정합니다.|
|[C 사용자 지정 전환::m_initialValue](#m_initialvalue)|초기 값을 저장합니다.|
|[C사용자 지정 전환::m_initialVelocity](#m_initialvelocity)|초기 속도를 저장합니다.|
|[C사용자 지정 전환::m_pInterpolator](#m_pinterpolator)|사용자 지정 보간기에 대한 포인터를 저장합니다.|

## <a name="remarks"></a>설명

CCustomTransitions 클래스를 사용하면 개발자가 사용자 지정 전환을 구현할 수 있습니다. 표준 전환으로 만들어지고 사용되지만 생성자는 사용자 지정 보간기의 매개 변수 포인터로 허용합니다. 사용자 지정 전환을 사용 하려면 다음 단계를 수행 합니다: 1. CCustom Interpolator에서 클래스를 파생 하 고 적어도 InterpolateValue 메서드를 구현 합니다. 2. 사용자 지정 보간 개체의 수명이 사용되는 애니메이션 의 지속 시간보다 길어야 합니다. 3. CCustomTransition 개체를 인스턴스화(연산자 new 사용)하고 생성자의 사용자 지정 보간자에게 포인터를 전달합니다. 4. 사용자 지정 보간을 위해 이러한 매개 변수가 필요한 경우 CCustomTransition::SetInitial값 및 CCustom전환::SetInitialVelocity를 호출합니다. 5. 사용자 지정 전환에 대한 포인터를 사용자 지정 알고리즘으로 애니메이션해야 하는 애니메이션 개체의 AddTransition 메서드에 전달합니다. 6. 애니메이션 개체의 값이 변경되어야 하는 경우 Windows 애니메이션 API는 CCustom Interpolator에서 InterpolateValue(및 기타 관련 메서드)를 호출합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C베이스 트랜지션](../../mfc/reference/cbasetransition-class.md)

`CCustomTransition`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="ccustomtransitionccustomtransition"></a><a name="ccustomtransition"></a>C 사용자 지정 전환::C사용자 지정 전환

사용자 지정 전환 개체를 생성합니다.

```
CCustomTransition(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>매개 변수

*핀인터폴레이터*<br/>
사용자 지정 보간기의 포인터입니다.

## <a name="ccustomtransitioncreate"></a><a name="create"></a>C 사용자 지정 전환::만들기

전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,
    IUIAnimationTransitionFactory* pFactory);
```

### <a name="parameters"></a>매개 변수

*pFactory*<br/>
사용자 지정 전환을 만드는 작업 팩터리에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

이 메서드는 이 전환과 연관된 애니메이션 변수에 적용할 초기 값및 초기 속도를 설정할 수도 있습니다. 이를 위해 프레임워크가 캡슐화된 전환 COM 개체를 만들기 전에 SetInitialValue 및 SetInitialVelocity를 호출해야 합니다(CAnimationController::AnimateGroup)를 호출할 때 발생합니다.

## <a name="ccustomtransitionm_binitialvaluespecified"></a><a name="m_binitialvaluespecified"></a>C 사용자 지정 전환::m_bInitialValueSpecified

초기 값이 SetInitialValue로 지정되었는지 여부를 지정합니다.

```
BOOL m_bInitialValueSpecified;
```

## <a name="ccustomtransitionm_binitialvelocityspecified"></a><a name="m_binitialvelocityspecified"></a>C 사용자 지정 전환::m_bInitialVelocitySpecified

초기 속도가 SetInitialVelocity로 지정되었는지 여부를 지정합니다.

```
BOOL m_bInitialVelocitySpecified;
```

## <a name="ccustomtransitionm_initialvalue"></a><a name="m_initialvalue"></a>C 사용자 지정 전환::m_initialValue

초기 값을 저장합니다.

```
DOUBLE m_initialValue;
```

## <a name="ccustomtransitionm_initialvelocity"></a><a name="m_initialvelocity"></a>C사용자 지정 전환::m_initialVelocity

초기 속도를 저장합니다.

```
DOUBLE m_initialVelocity;
```

## <a name="ccustomtransitionm_pinterpolator"></a><a name="m_pinterpolator"></a>C사용자 지정 전환::m_pInterpolator

사용자 지정 보간기에 대한 포인터를 저장합니다.

```
CCustomInterpolator* m_pInterpolator;
```

## <a name="ccustomtransitionsetinitialvalue"></a><a name="setinitialvalue"></a>C사용자 지정 전환::설정 초기 값

이 전환과 연결된 애니메이션 변수에 적용할 초기 값을 설정합니다.

```cpp
void SetInitialValue(DOUBLE initialValue);
```

### <a name="parameters"></a>매개 변수

*초기 값*

## <a name="ccustomtransitionsetinitialvelocity"></a><a name="setinitialvelocity"></a>C 사용자 지정 전환::설정초기벨로시티

이 전환과 연관된 애니메이션 변수에 적용되는 초기 속도를 설정합니다.

```cpp
void SetInitialVelocity(DOUBLE initialVelocity);
```

### <a name="parameters"></a>매개 변수

*초기 속도*

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
