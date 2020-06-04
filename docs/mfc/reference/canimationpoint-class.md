---
title: CAnimationPoint 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetX
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetY
- AFXANIMATIONCONTROLLER/CAnimationPoint::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_xValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_yValue
helpviewer_keywords:
- CAnimationPoint [MFC], CAnimationPoint
- CAnimationPoint [MFC], AddTransition
- CAnimationPoint [MFC], GetDefaultValue
- CAnimationPoint [MFC], GetValue
- CAnimationPoint [MFC], GetX
- CAnimationPoint [MFC], GetY
- CAnimationPoint [MFC], SetDefaultValue
- CAnimationPoint [MFC], GetAnimationVariableList
- CAnimationPoint [MFC], m_xValue
- CAnimationPoint [MFC], m_yValue
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
ms.openlocfilehash: fcdd07efb46c97d27a9f1349c297688b5705f176
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755145"
---
# <a name="canimationpoint-class"></a>CAnimationPoint 클래스

좌표에 애니메이션을 적용할 수 있는 점 기능을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationPoint : public CAnimationBaseObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C애니메이션 포인트::C애니메이션포인트](#canimationpoint)|오버로드되었습니다. CAnimationPoint 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션 포인트::추가 전환](#addtransition)|X 및 Y 좌표에 대한 전환을 추가합니다.|
|[C애니메이션 포인트::Getdefaultvalue](#getdefaultvalue)|X 및 Y 좌표의 기본값을 반환합니다.|
|[C애니메이션 포인트::GetValue](#getvalue)|현재 값을 반환합니다.|
|[C애니메이션 포인트::겟X](#getx)|X 좌표에 대한 CAnimation변수에 대한 액세스를 제공합니다.|
|[C애니메이션 포인트 :: GetY](#gety)|Y 좌표에 대한 CAnimation변수에 대한 액세스를 제공합니다.|
|[시애니메이션 포인트::설정기본값](#setdefaultvalue)|기본값을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션 포인트::GetAnimation변수리스트](#getanimationvariablelist)|캡슐화된 애니메이션 변수를 목록에 넣습니다. [(CAnimationBaseObject 재정의::GetAnimationVariablelist.)](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C애니메이션 포인트::연산자 C포인트](#operator_cpoint)|C애니메이션포인트를 CPoint로 변환합니다.|
|[C애니메이션 포인트::연산자=](#operator_eq)|CAnimationPoint에 ptSrc를 할당합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C애니메이션 포인트:m_xValue](#m_xvalue)|애니메이션 점의 X 좌표를 나타내는 캡슐화된 애니메이션 변수입니다.|
|[C애니메이션 포인트:m_yValue](#m_yvalue)|애니메이션 점의 Y 좌표를 나타내는 캡슐화된 애니메이션 변수입니다.|

## <a name="remarks"></a>설명

CAnimationPoint 클래스는 두 개의 CAnimationVariable 개체를 캡슐화하며 응용 프로그램에서 한 점을 나타낼 수 있습니다. 예를 들어 이 클래스를 사용하여 화면의 모든 개체(예: 텍스트 문자열, 원, 점 등)의 위치에 애니메이션을 만들 수 있습니다. 응용 프로그램에서 이 클래스를 사용하려면 이 클래스의 개체를 인스턴스화하고 CAnimationController::AddAnimationObject를 사용하여 애니메이션 컨트롤러에 추가하고 각 전환이 X 및/또는 Y 좌표에 적용될 경우 AddTransition를 호출합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C애니메이션베이스오브젝트](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationPoint`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationpointaddtransition"></a><a name="addtransition"></a>C애니메이션 포인트::추가 전환

X 및 Y 좌표에 대한 전환을 추가합니다.

```cpp
void AddTransition(
    CBaseTransition* pXTransition,
    CBaseTransition* pYTransition);
```

### <a name="parameters"></a>매개 변수

*pX트랜지션*<br/>
X 좌표에 대한 전환 포인터입니다.

*pY 전환*<br/>
Y 좌표에 대한 전환 포인터입니다.

### <a name="remarks"></a>설명

X 및 Y 좌표의 애니메이션 변수에 적용할 내부 전환 목록에 지정된 전환을 추가하려면 이 함수를 호출합니다. 전환을 추가하면 전환이 즉시 적용되지 않고 내부 목록에 저장됩니다. CAnimationController::AnimateGroup을 호출할 때 전환이 적용됩니다(특정 값에 대한 스토리보드에 추가). 좌표 중 하나에 전환을 적용할 필요가 없는 경우 NULL을 전달할 수 있습니다.

## <a name="canimationpointcanimationpoint"></a><a name="canimationpoint"></a>C애니메이션 포인트::C애니메이션포인트

CAnimationPoint 개체를 생성합니다.

```
CAnimationPoint();

CAnimationPoint(
    const CPoint& ptDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>매개 변수

*ptDefault*<br/>
기본 점 좌표를 지정합니다.

*n그룹 ID*<br/>
그룹 ID를 지정합니다.

*n개체 ID*<br/>
개체 ID를 지정합니다.

*dw사용자 데이터*<br/>
사용자 정의 데이터를 지정합니다.

### <a name="remarks"></a>설명

기본 속성이 있는 CAnimationPoint 오브젝트 생성: 기본 점 좌표, 그룹 ID 및 개체 ID가 0으로 설정됩니다.

## <a name="canimationpointgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>C애니메이션 포인트::GetAnimation변수리스트

캡슐화된 애니메이션 변수를 목록에 넣습니다.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```

### <a name="parameters"></a>매개 변수

*순*<br/>
함수가 반환되면 X 및 Y 좌표를 나타내는 두 개의 CAnimationVariable 개체에 대한 포인터가 포함됩니다.

## <a name="canimationpointgetdefaultvalue"></a><a name="getdefaultvalue"></a>C애니메이션 포인트::Getdefaultvalue

X 및 Y 좌표의 기본값을 반환합니다.

```
CPoint GetDefaultValue();
```

### <a name="return-value"></a>Return Value

기본값을 포함하는 점입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 생성자 또는 SetDefaultValue에 의해 이전에 설정된 기본값을 검색합니다.

## <a name="canimationpointgetvalue"></a><a name="getvalue"></a>C애니메이션 포인트::GetValue

현재 값을 반환합니다.

```
BOOL GetValue(CPoint& ptValue);
```

### <a name="parameters"></a>매개 변수

*pt값*<br/>
출력 이 메서드가 반환될 때 현재 값을 포함합니다.

### <a name="return-value"></a>Return Value

TRUE, 현재 값이 성공적으로 검색된 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 함수를 호출하여 애니메이션 점의 현재 값을 검색합니다. 이 메서드가 실패하거나 X 및 Y 좌표에 대한 기본 COM 개체가 초기화되지 않은 경우 ptValue에는 생성자 또는 SetDefaultValue에 의해 이전에 설정된 기본값이 포함됩니다.

## <a name="canimationpointgetx"></a><a name="getx"></a>C애니메이션 포인트::겟X

X 좌표에 대한 CAnimation변수에 대한 액세스를 제공합니다.

```
CAnimationVariable& GetX();
```

### <a name="return-value"></a>Return Value

X 좌표를 나타내는 캡슐화된 CAnimationVariable에 대한 참조입니다.

### <a name="remarks"></a>설명

X 좌표를 나타내는 기본 CAnimationVariable에 직접 액세스하려면 이 메서드를 호출할 수 있습니다.

## <a name="canimationpointgety"></a><a name="gety"></a>C애니메이션 포인트 :: GetY

Y 좌표에 대한 CAnimation변수에 대한 액세스를 제공합니다.

```
CAnimationVariable& GetY();
```

### <a name="return-value"></a>Return Value

Y 좌표를 나타내는 캡슐화된 CAnimationVariable에 대한 참조입니다.

### <a name="remarks"></a>설명

Y 좌표를 나타내는 기본 CAnimationVariable에 직접 액세스하려면 이 메서드를 호출할 수 있습니다.

## <a name="canimationpointm_xvalue"></a><a name="m_xvalue"></a>C애니메이션 포인트:m_xValue

애니메이션 점의 X 좌표를 나타내는 캡슐화된 애니메이션 변수입니다.

```
CAnimationVariable m_xValue;
```

## <a name="canimationpointm_yvalue"></a><a name="m_yvalue"></a>C애니메이션 포인트:m_yValue

애니메이션 점의 Y 좌표를 나타내는 캡슐화된 애니메이션 변수입니다.

```
CAnimationVariable m_yValue;
```

## <a name="canimationpointoperator-cpoint"></a><a name="operator_cpoint"></a>C애니메이션 포인트::연산자 C포인트

C애니메이션포인트를 CPoint로 변환합니다.

```
operator CPoint();
```

### <a name="return-value"></a>Return Value

C애니메이션포인트의 현재 값입니다.

### <a name="remarks"></a>설명

이 함수는 내부적으로 GetValue를 호출합니다. 어떤 이유로 GetValue가 실패하면 반환된 점에 X 및 Y 좌표의 기본값이 포함됩니다.

## <a name="canimationpointoperator"></a><a name="operator_eq"></a>C애니메이션 포인트::연산자=

CAnimationPoint에 ptSrc를 할당합니다.

```cpp
void operator=(const CPoint& ptSrc);
```

### <a name="parameters"></a>매개 변수

*ptSrc*<br/>
CPoint 또는 POINT를 나타냅니다.

### <a name="remarks"></a>설명

CAnimationPoint에 ptSrc를 할당합니다. 이 연산자는 설정됨값(SetDefaultValue)을 호출하여 X 및 Y 좌표에 대한 기본 COM 오브젝트를 다시 생성하므로 애니메이션을 시작하기 전에 이 작업을 수행하는 것이 좋습니다. 이 애니메이션 개체를 이벤트에 구독한 경우(ValueChanged 또는 IntegerValueChanged) 이러한 이벤트를 다시 활성화해야 합니다.

## <a name="canimationpointsetdefaultvalue"></a><a name="setdefaultvalue"></a>시애니메이션 포인트::설정기본값

기본값을 설정합니다.

```cpp
void SetDefaultValue(const POINT& ptDefault);
```

### <a name="parameters"></a>매개 변수

*ptDefault*<br/>
기본 점 값을 지정합니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 기본값을 애니메이션 오브젝트로 설정합니다. 이 메서드는 애니메이션 점의 X 및 Y 좌표에 기본값을 할당합니다. 또한 기본 COM 개체가 생성된 경우 다시 만듭니다. 이 애니메이션 개체를 이벤트에 구독한 경우(ValueChanged 또는 IntegerValueChanged) 이러한 이벤트를 다시 활성화해야 합니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
