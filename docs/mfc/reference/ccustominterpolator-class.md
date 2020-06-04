---
title: CCustomInterpolator 클래스
ms.date: 11/04/2016
f1_keywords:
- CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDependencies
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetFinalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::Init
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetInitialValueAndVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_duration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_finalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialVelocity
helpviewer_keywords:
- CCustomInterpolator [MFC], CCustomInterpolator
- CCustomInterpolator [MFC], GetDependencies
- CCustomInterpolator [MFC], GetDuration
- CCustomInterpolator [MFC], GetFinalValue
- CCustomInterpolator [MFC], Init
- CCustomInterpolator [MFC], InterpolateValue
- CCustomInterpolator [MFC], InterpolateVelocity
- CCustomInterpolator [MFC], SetDuration
- CCustomInterpolator [MFC], SetInitialValueAndVelocity
- CCustomInterpolator [MFC], m_currentValue
- CCustomInterpolator [MFC], m_currentVelocity
- CCustomInterpolator [MFC], m_duration
- CCustomInterpolator [MFC], m_finalValue
- CCustomInterpolator [MFC], m_initialValue
- CCustomInterpolator [MFC], m_initialVelocity
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
ms.openlocfilehash: 00ce0661fa3fbde714a7299ecbbd54df7c9bcc36
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749167"
---
# <a name="ccustominterpolator-class"></a>CCustomInterpolator 클래스

기본 보간자를 구현합니다.

## <a name="syntax"></a>구문

```
class CCustomInterpolator;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C커스 인터폴리터::C커스트 인터폴리터](#ccustominterpolator)|오버로드되었습니다. 사용자 지정 보간기 개체를 생성하고 지속 시간과 속도를 지정된 값으로 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C사용자 간교자::Get 의존성](#getdependencies)|인터폴레이터의 종속성을 가져옵니다.|
|[C사용자 간교자::GetDuration](#getduration)|인터폴레이터의 지속 시간을 가져옵니다.|
|[C사용자 간간 조정기::GetFinalValue](#getfinalvalue)|보간자가 리드하는 최종 값을 가져옵니다.|
|[C사용자 간간 조정기::이니트](#init)|기간 및 최종 값을 초기화합니다.|
|[C사용자 간간 조정자::인터폴레이터값](#interpolatevalue)|지정된 오프셋에서 값을 보간합니다.|
|[C사용자 간간 조정기::보간속도](#interpolatevelocity)|지정된 오프셋에서 속도를 보간합니다.|
|[C사용자 간간 조정기::설정 기간](#setduration)|인터폴레이터의 지속 시간을 설정합니다.|
|[C사용자 간간 조정기::설정 초기값및 벨로시티](#setinitialvalueandvelocity)|인터폴레이터의 초기 값과 속도를 설정합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C사용자 간중간 조정기::m_currentValue](#m_currentvalue)|보간된 값입니다.|
|[C사용자 간중간 조정기::m_currentVelocity](#m_currentvelocity)|보간된 속도입니다.|
|[C사용자 간간 조정기::m_duration](#m_duration)|전환 기간입니다.|
|[C사용자 간중간 개입자:m_finalValue](#m_finalvalue)|전환이 끝날 때 변수의 최종 값입니다.|
|[C사용자 간중간 조정기::m_initialValue](#m_initialvalue)|전환 시작 시 변수의 값입니다.|
|[C사용자 간중간 조정기:m_initialVelocity](#m_initialvelocity)|전환 시작 시 변수의 속도입니다.|

## <a name="remarks"></a>설명

CCustomInterpolator에서 클래스를 파생 하 고 사용자 지정 보간 알고리즘을 구현 하기 위해 필요한 모든 메서드를 재정의 합니다. 이 클래스에 대한 포인터는 CCustomTransition에 매개 변수로 전달되어야 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CCustomInterpolator`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="ccustominterpolatorccustominterpolator"></a><a name="ccustominterpolator"></a>C커스 인터폴리터::C커스트 인터폴리터

사용자 지정 보간기 개체를 생성하고 모든 값을 기본값 0으로 설정합니다.

```
CCustomInterpolator();

CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
전환 기간입니다.

*finalValue*

### <a name="remarks"></a>설명

CCustom Interpolator::Init을 사용하여 코드의 나중에 기간 및 최종 값을 초기화합니다.

## <a name="ccustominterpolatorgetdependencies"></a><a name="getdependencies"></a>C사용자 간교자::Get 의존성

인터폴레이터의 종속성을 가져옵니다.

```
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>매개 변수

*초기값 종속성*<br/>
출력 SetInitialValueAndVelocity에 전달 된 초기 값에 종속 된 보간기의 측면입니다.

*초기Velocity의존적*<br/>
출력 초기 속도에 의존하는 보간기의 측면은 SetInitialValueAndVelocity로 전달되었습니다.

*지속 시간 종속성*<br/>
출력 SetDuration에 전달된 기간에 따라 인터폴레이터의 측면입니다.

### <a name="return-value"></a>Return Value

기본 구현은 항상 TRUE를 반환합니다. 이벤트에 실패하려면 재정의된 구현에서 FALSE를 반환합니다.

## <a name="ccustominterpolatorgetduration"></a><a name="getduration"></a>C사용자 간교자::GetDuration

인터폴레이터의 지속 시간을 가져옵니다.

```
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
출력 전환 기간(초)입니다.

### <a name="return-value"></a>Return Value

기본 구현은 항상 TRUE를 반환합니다. 이벤트에 실패하려면 재정의된 구현에서 FALSE를 반환합니다.

## <a name="ccustominterpolatorgetfinalvalue"></a><a name="getfinalvalue"></a>C사용자 간간 조정기::GetFinalValue

보간자가 리드하는 최종 값을 가져옵니다.

```
virtual BOOL GetFinalValue(DOUBLE* value);
```

### <a name="parameters"></a>매개 변수

*value*<br/>
출력 전환이 끝날 때 변수의 최종 값입니다.

### <a name="return-value"></a>Return Value

기본 구현은 항상 TRUE를 반환합니다. 이벤트에 실패하려면 재정의된 구현에서 FALSE를 반환합니다.

## <a name="ccustominterpolatorinit"></a><a name="init"></a>C사용자 간간 조정기::이니트

기간 및 최종 값을 초기화합니다.

```cpp
void Init(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
전환 기간입니다.

*finalValue*<br/>
전환이 끝날 때 변수의 최종 값입니다.

## <a name="ccustominterpolatorinterpolatevalue"></a><a name="interpolatevalue"></a>C사용자 간간 조정자::인터폴레이터값

지정된 오프셋에서 값을 보간합니다.

```
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,
    DOUBLE* value);
```

### <a name="parameters"></a>매개 변수

*value*<br/>
출력 보간된 값입니다.

### <a name="return-value"></a>Return Value

기본 구현은 항상 TRUE를 반환합니다. 이벤트에 실패하려면 재정의된 구현에서 FALSE를 반환합니다.

## <a name="ccustominterpolatorinterpolatevelocity"></a><a name="interpolatevelocity"></a>C사용자 간간 조정기::보간속도

지정된 오프셋에서 속도를 보간합니다.

```
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,
    DOUBLE* velocity);
```

### <a name="parameters"></a>매개 변수

*velocity*<br/>
출력 오프셋에서 변수의 속도입니다.

### <a name="return-value"></a>Return Value

기본 구현은 항상 TRUE를 반환합니다. 이벤트에 실패하려면 재정의된 구현에서 FALSE를 반환합니다.

## <a name="ccustominterpolatorm_currentvalue"></a><a name="m_currentvalue"></a>C사용자 간중간 조정기::m_currentValue

보간된 값입니다.

```
DOUBLE m_currentValue;
```

## <a name="ccustominterpolatorm_currentvelocity"></a><a name="m_currentvelocity"></a>C사용자 간중간 조정기::m_currentVelocity

보간된 속도입니다.

```
DOUBLE m_currentVelocity;
```

## <a name="ccustominterpolatorm_duration"></a><a name="m_duration"></a>C사용자 간간 조정기::m_duration

전환 기간입니다.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="ccustominterpolatorm_finalvalue"></a><a name="m_finalvalue"></a>C사용자 간중간 개입자:m_finalValue

전환이 끝날 때 변수의 최종 값입니다.

```
DOUBLE m_finalValue;
```

## <a name="ccustominterpolatorm_initialvalue"></a><a name="m_initialvalue"></a>C사용자 간중간 조정기::m_initialValue

전환 시작 시 변수의 값입니다.

```
DOUBLE m_initialValue;
```

## <a name="ccustominterpolatorm_initialvelocity"></a><a name="m_initialvelocity"></a>C사용자 간중간 조정기:m_initialVelocity

전환 시작 시 변수의 속도입니다.

```
DOUBLE m_initialVelocity;
```

## <a name="ccustominterpolatorsetduration"></a><a name="setduration"></a>C사용자 간간 조정기::설정 기간

인터폴레이터의 지속 시간을 설정합니다.

```
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
전환 기간입니다.

### <a name="return-value"></a>Return Value

기본 구현은 항상 TRUE를 반환합니다. 이벤트에 실패하려면 재정의된 구현에서 FALSE를 반환합니다.

## <a name="ccustominterpolatorsetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a>C사용자 간간 조정기::설정 초기값및 벨로시티

인터폴레이터의 초기 값과 속도를 설정합니다.

```
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,
    DOUBLE initialVelocity);
```

### <a name="parameters"></a>매개 변수

*초기 값*<br/>
전환 시작 시 변수의 값입니다.

*초기 속도*<br/>
전환 시작 시 변수의 속도입니다.

### <a name="return-value"></a>Return Value

기본 구현은 항상 TRUE를 반환합니다. 이벤트에 실패하려면 재정의된 구현에서 FALSE를 반환합니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
