---
title: CAnimationValue 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationValue::GetValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationValue::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationValue::m_value
helpviewer_keywords:
- CAnimationValue [MFC], CAnimationValue
- CAnimationValue [MFC], AddTransition
- CAnimationValue [MFC], GetValue
- CAnimationValue [MFC], GetVariable
- CAnimationValue [MFC], SetDefaultValue
- CAnimationValue [MFC], GetAnimationVariableList
- CAnimationValue [MFC], m_value
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
ms.openlocfilehash: e020e3e123bb5dc96a623e7a41896d75c611b81e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755081"
---
# <a name="canimationvalue-class"></a>CAnimationValue 클래스

하나의 값을 갖는 애니메이션 개체 기능을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationValue : public CAnimationBaseObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C애니메이션값::C애니메이션값](#canimationvalue)|오버로드되었습니다. C애니메이션밸류 오브젝트를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션값::추가 전환](#addtransition)|값에 적용할 전환을 추가합니다.|
|[C애니메이션 값::GetValue](#getvalue)|오버로드되었습니다. 현재 값을 검색합니다.|
|[C애니메이션값::Get변수](#getvariable)|캡슐화된 애니메이션 변수에 대한 액세스를 제공합니다.|
|[C애니메이션값::설정디폴값](#setdefaultvalue)|기본값을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션값::GetAnimation변수리스트](#getanimationvariablelist)|캡슐화된 애니메이션 변수를 목록에 넣습니다. [(CAnimationBaseObject 재정의::GetAnimationVariablelist.)](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C애니메이션값::연산자 더블](#operator_double)|CAnimationValue와 DOUBLE 간의 변환을 제공합니다.|
|[C애니메이션값::연산자 INT32](#operator_int32)|CAnimationValue와 INT32 간의 변환을 제공합니다.|
|[C애니메이션값::연산자=](#operator_eq)|오버로드되었습니다. CAnimationValue에 INT32 값을 할당합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C애니메이션값:m_value](#m_value)|애니메이션 값을 나타내는 캡슐화된 애니메이션 변수입니다.|

## <a name="remarks"></a>설명

CAnimationValue 클래스는 단일 CAnimationVariable 개체를 캡슐화하고 응용 프로그램에서 단일 애니메이션 값을 나타낼 수 있습니다. 예를 들어 애니메이션된 투명도(페이드 효과), 각도(오브젝트 회전) 또는 애니메이션이 하나되는 값에 따라 애니메이션을 만들어야 하는 다른 경우에 이 클래스를 사용할 수 있습니다. 응용 프로그램에서 이 클래스를 사용하려면 이 클래스의 개체를 인스턴스화하고 CAnimationController::AddAnimationObject를 사용하여 애니메이션 컨트롤러에 추가하고 각 전환이 값에 적용될 경우 AddTransition를 호출합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C애니메이션베이스오브젝트](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationValue`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationvalueaddtransition"></a><a name="addtransition"></a>C애니메이션값::추가 전환

값에 적용할 전환을 추가합니다.

```cpp
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>매개 변수

*p전환*<br/>
개체를 전환하는 포인터입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 애니메이션 변수에 적용할 내부 전환 목록에 전환을 추가합니다. 전환을 추가하면 전환이 즉시 적용되지 않고 내부 목록에 저장됩니다. CAnimationController::AnimateGroup을 호출할 때 전환이 적용됩니다(특정 값에 대한 스토리보드에 추가).

## <a name="canimationvaluecanimationvalue"></a><a name="canimationvalue"></a>C애니메이션값::C애니메이션값

C애니메이션밸류 오브젝트를 생성합니다.

```
CAnimationValue();

CAnimationValue(
    DOUBLE dblDefaultValue,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>매개 변수

*dblDefault값*<br/>
기본값을 지정합니다.

*n그룹 ID*<br/>
그룹 ID를 지정합니다.

*n개체 ID*<br/>
개체 ID를 지정합니다.

*dw사용자 데이터*<br/>
사용자 정의 데이터를 지정합니다.

### <a name="remarks"></a>설명

기본 속성으로 CAnimationValue 개체 생성: 기본값, 그룹 ID 및 개체 ID가 0으로 설정됩니다.

## <a name="canimationvaluegetanimationvariablelist"></a><a name="getanimationvariablelist"></a>C애니메이션값::GetAnimation변수리스트

캡슐화된 애니메이션 변수를 목록에 넣습니다.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>매개 변수

*순*<br/>
함수가 반환되면 애니메이션된 값을 나타내는 CAnimationVariable에 대한 포인터가 포함되어 있습니다.

## <a name="canimationvaluegetvalue"></a><a name="getvalue"></a>C애니메이션 값::GetValue

현재 값을 검색합니다.

```
BOOL GetValue(DOUBLE& dblValue);
BOOL GetValue(INT32& nValue);
```

### <a name="parameters"></a>매개 변수

*dblValue*<br/>
출력 함수가 반환되면 애니메이션 변수의 현재 값이 포함됩니다.

*n값*<br/>
출력 함수가 반환되면 애니메이션 변수의 현재 값이 포함됩니다.

### <a name="return-value"></a>Return Value

현재 값을 성공적으로 검색한 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 함수를 호출하여 현재 값을 검색합니다. 이 구현은 캡슐화된 COM 개체를 호출하며 호출이 실패하면 이 메서드는 생성자 또는 SetDefaultValue로 이전에 설정된 기본값을 반환합니다.

## <a name="canimationvaluegetvariable"></a><a name="getvariable"></a>C애니메이션값::Get변수

캡슐화된 애니메이션 변수에 대한 액세스를 제공합니다.

```
CAnimationVariable& GetVariable();
```

### <a name="return-value"></a>Return Value

캡슐화된 애니메이션 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 캡슐화된 애니메이션 변수에 액세스합니다. CAnimationVariable에서 애니메이션 변수가 만들어지지 않은 경우 포인터가 NULL일 수 있는 기본 IUIAnimationVariable 개체에 액세스할 수 있습니다.

## <a name="canimationvaluem_value"></a><a name="m_value"></a>C애니메이션값:m_value

애니메이션 값을 나타내는 캡슐화된 애니메이션 변수입니다.

```
CAnimationVariable m_value;
```

## <a name="canimationvalueoperator-double"></a><a name="operator_double"></a>C애니메이션값::연산자 더블

CAnimationValue와 DOUBLE 간의 변환을 제공합니다.

```
operator DOUBLE();
```

### <a name="return-value"></a>Return Value

애니메이션 값의 현재 값입니다.

### <a name="remarks"></a>설명

CAnimationValue와 DOUBLE 간의 변환을 제공합니다. 이 메서드는 내부적으로 GetValue를 호출 하 고 오류를 확인 하지 않습니다. GetValue가 실패하면 반환된 값에는 생성자 또는 SetDefaultValue에 이전에 설정된 기본 값이 포함됩니다.

## <a name="canimationvalueoperator-int32"></a><a name="operator_int32"></a>C애니메이션값::연산자 INT32

CAnimationValue와 INT32 간의 변환을 제공합니다.

```
operator INT32();
```

### <a name="return-value"></a>Return Value

정수로 애니메이션 값의 현재 값입니다.

### <a name="remarks"></a>설명

CAnimationValue와 INT32 간의 변환을 제공합니다. 이 메서드는 내부적으로 GetValue를 호출 하 고 오류를 확인 하지 않습니다. GetValue가 실패하면 반환된 값에는 생성자 또는 SetDefaultValue에 이전에 설정된 기본 값이 포함됩니다.

## <a name="canimationvalueoperator"></a><a name="operator_eq"></a>C애니메이션값::연산자=

CAnimationValue에 DOUBLE 값을 할당합니다.

```cpp
void operator=(DOUBLE dblVal);
void operator=(INT32 nVal);
```

### <a name="parameters"></a>매개 변수

*dblVal*<br/>
애니메이션 값에 할당할 값을 지정합니다.

*n발 (것)*<br/>
애니메이션 값에 할당할 값을 지정합니다.

### <a name="remarks"></a>설명

CAnimationValue에 DOUBLE 값을 할당합니다. 이 값은 캡슐화된 애니메이션 변수의 기본값으로 설정됩니다. 이 애니메이션 개체를 이벤트에 구독한 경우(ValueChanged 또는 IntegerValueChanged) 이러한 이벤트를 다시 활성화해야 합니다.

## <a name="canimationvaluesetdefaultvalue"></a><a name="setdefaultvalue"></a>C애니메이션값::설정디폴값

기본값을 설정합니다.

```cpp
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>매개 변수

*dblDefault값*<br/>
기본값을 지정합니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 기본값을 설정합니다. 애니메이션이 시작되지 않았거나 기본 COM 개체가 만들어지지 않은 경우 기본값이 응용 프로그램에 반환됩니다. CAnimationVarible에 캡슐화된 기본 COM 개체가 이미 생성된 경우 이 메서드가 다시 만들어지므로 EnableValueChanged/EnableIntegerValueChanged 메서드를 다시 호출해야 할 수 있습니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
