---
title: CAnimationVariable 클래스
ms.date: 03/27/2019
f1_keywords:
- CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationVariable::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::Create
- AFXANIMATIONCONTROLLER/CAnimationVariable::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_dblDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_lstTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_pParentObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_variable
helpviewer_keywords:
- CAnimationVariable [MFC], CAnimationVariable
- CAnimationVariable [MFC], AddTransition
- CAnimationVariable [MFC], ApplyTransitions
- CAnimationVariable [MFC], ClearTransitions
- CAnimationVariable [MFC], Create
- CAnimationVariable [MFC], CreateTransitions
- CAnimationVariable [MFC], EnableIntegerValueChangedEvent
- CAnimationVariable [MFC], EnableValueChangedEvent
- CAnimationVariable [MFC], GetDefaultValue
- CAnimationVariable [MFC], GetParentAnimationObject
- CAnimationVariable [MFC], GetValue
- CAnimationVariable [MFC], GetVariable
- CAnimationVariable [MFC], SetDefaultValue
- CAnimationVariable [MFC], SetParentAnimationObject
- CAnimationVariable [MFC], m_bAutodestroyTransitions
- CAnimationVariable [MFC], m_dblDefaultValue
- CAnimationVariable [MFC], m_lstTransitions
- CAnimationVariable [MFC], m_pParentObject
- CAnimationVariable [MFC], m_variable
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
ms.openlocfilehash: b53a1338566a329fbdf5b91c41d0411a529afe8d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755065"
---
# <a name="canimationvariable-class"></a>CAnimationVariable 클래스

애니메이션 변수를 나타냅니다.

## <a name="syntax"></a>구문

```
class CAnimationVariable;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C애니메이션변수::C애니메이션변수](#canimationvariable)|애니메이션 변수 개체를 생성합니다.|
|[C애니메이션변수::~C애니메이션변수](#_dtorcanimationvariable)|소멸자입니다. CAnimationVariable 개체가 소멸될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션변수::추가 전환](#addtransition)|전환을 추가합니다.|
|[C애니메이션변수::적용전환](#applytransitions)|내부 목록에서 스토리보드로전환을 추가합니다.|
|[C애니메이션변수::클리어 트랜지션](#cleartransitions)|전환을 지웁션을 지웁습니다.|
|[C애니메이션변수::만들기](#create)|기본 애니메이션 변수 COM 개체를 만듭니다.|
|[C애니메이션변수::만들기전환](#createtransitions)|이 애니메이션 변수에 적용할 모든 전환을 만듭니다.|
|[C애니메이션변수::인에이블인티거밸류변경이벤트](#enableintegervaluechangedevent)|IntegerValueChanged 이벤트를 활성화하거나 사용하지 않도록 설정합니다.|
|[C애니메이션변수::인에이블밸류변경이벤트](#enablevaluechangedevent)|ValueChanged 이벤트를 활성화하거나 사용하지 않도록 설정합니다.|
|[C애니메이션 변수::Getdefaultvalue](#getdefaultvalue)|기본값을 반환합니다.|
|[C애니메이션변수::GetParent애니메이션오브젝트](#getparentanimationobject)|상위 애니메이션 개체를 반환합니다.|
|[C애니메이션변수::Getvalue](#getvalue)|오버로드되었습니다. 애니메이션 변수의 현재 값을 반환합니다.|
|[C애니메이션변수::Get변수](#getvariable)|IUIAnimationVariable COM 개체에 대한 포인터를 반환합니다.|
|[C애니메이션 변수::설정디폴값](#setdefaultvalue)|기본값을 설정하고 IUIAnimationVariable COM 개체를 해제합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션변수::설정부모애니메이션오브젝트](#setparentanimationobject)|애니메이션 변수와 애니메이션 개체 간의 관계를 설정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C애니메이션변수::m_bAutodestroyTransitions](#m_bautodestroytransitions)|관련 전환 개체를 삭제할지 여부를 지정합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C애니메이션변수::m_dblDefaultValue](#m_dbldefaultvalue)|IUIAnimation변수에 전파되는 기본값을 지정합니다.|
|[C애니메이션변수:m_lstTransitions](#m_lsttransitions)|이 애니메이션 변수에 애니메이션을 만드는 전환 목록이 포함되어 있습니다.|
|[C애니메이션변수:m_pParentObject](#m_pparentobject)|이 애니메이션 변수를 캡슐화하는 애니메이션 개체에 대한 포인터입니다.|
|[C애니메이션변수::m_variable](#m_variable)|IUIAnimationVariable COM 개체에 대한 포인터를 저장합니다. COM 개체가 아직 생성되지 않았거나 생성에 실패한 경우 NULL입니다.|

## <a name="remarks"></a>설명

CAnimationVariable 클래스는 IUIAnimationVariable COM 개체를 캡슐화합니다. 또한 스토리보드의 애니메이션 변수에 적용할 전환 목록도 보유하고 있습니다. CAnimationVariable 오브젝트는 애니메이션 오브젝트에 포함되며, 이 개체는 응용 프로그램에서 애니메이션 값, 점, 크기, 색상 및 사각형을 나타낼 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CAnimationVariable`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationvariablecanimationvariable"></a><a name="_dtorcanimationvariable"></a>C애니메이션변수::~C애니메이션변수

소멸자입니다. CAnimationVariable 개체가 소멸될 때 호출됩니다.

```
virtual ~CAnimationVariable();
```

## <a name="canimationvariableaddtransition"></a><a name="addtransition"></a>C애니메이션변수::추가 전환

전환을 추가합니다.

```cpp
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>매개 변수

*p전환*<br/>
추가할 전환에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 애니메이션 변수에 적용할 전환의 내부 목록에 전환을 추가 하기 위해 호출 됩니다. 애니메이션이 예약되었을 때 이 목록을 지워야 합니다.

## <a name="canimationvariableapplytransitions"></a><a name="applytransitions"></a>C애니메이션변수::적용전환

내부 목록에서 스토리보드로전환을 추가합니다.

```cpp
void ApplyTransitions(
    CAnimationController* pController,
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>매개 변수

*p 컨트롤러*<br/>
상위 애니메이션 컨트롤러에 대한 포인터입니다.

*p스토리보드*<br/>
스토리보드에 대한 포인터입니다.

*b리곤키프레임*<br/>
TRUE, 이 메서드는 키프레임에 종속 된 전환을 추가 해야 하는 경우.

### <a name="remarks"></a>설명

이 메서드는 내부 목록에서 스토리보드로전환을 추가합니다. 키프레임에 의존하지 않는 전환을 추가하고 키프레임에 의존하는 전환을 추가하기 위해 최상위 코드에서 여러 번 호출됩니다. 기본 애니메이션 변수 COM 개체가 만들어지지 않은 경우 이 메서드는 이 단계에서 만듭니다.

## <a name="canimationvariablecanimationvariable"></a><a name="canimationvariable"></a>C애니메이션변수::C애니메이션변수

애니메이션 변수 개체를 생성합니다.

```
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```

### <a name="parameters"></a>매개 변수

*dblDefault값*<br/>
기본값을 지정합니다.

### <a name="remarks"></a>설명

애니메이션 변수 개체를 생성하고 기본값을 설정합니다. 기본값은 변수가 애니메이션되지 않거나 애니메이션할 수 없는 경우에 사용됩니다.

## <a name="canimationvariablecleartransitions"></a><a name="cleartransitions"></a>C애니메이션변수::클리어 트랜지션

전환을 지웁션을 지웁습니다.

```cpp
void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>매개 변수

*b 자동 파괴*<br/>
이 메서드는 전환 개체를 삭제할지 여부를 지정합니다.

### <a name="remarks"></a>설명

이 메서드는 내부 전환 목록에서 모든 전환을 제거합니다. b자동 파괴가 TRUE이거나 truem_bAutodestroyTransitions 경우 전환이 삭제됩니다. 그렇지 않으면 호출자는 전환 개체를 할당 할당 해야 합니다.

## <a name="canimationvariablecreate"></a><a name="create"></a>C애니메이션변수::만들기

기본 애니메이션 변수 COM 개체를 만듭니다.

```
virtual BOOL Create(IUIAnimationManager* pManager);
```

### <a name="parameters"></a>매개 변수

*pManager*<br/>
애니메이션 관리자에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 애니메이션 변수가 성공적으로 생성된 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 기본 애니메이션 변수 COM 개체를 만들고 기본 값을 설정 합니다.

## <a name="canimationvariablecreatetransitions"></a><a name="createtransitions"></a>C애니메이션변수::만들기전환

이 애니메이션 변수에 적용할 모든 전환을 만듭니다.

```
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>매개 변수

*p라이브러리*<br/>
표준 전환 라이브러리를 정의하는 [IUIAnimationTransitionLibrary 인터페이스에](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 전환이 성공적으로 생성된 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 변수의 내부 전환 목록에 추가된 전환을 만들어야 할 때 프레임워크에서 호출됩니다.

## <a name="canimationvariableenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a>C애니메이션변수::인에이블인티거밸류변경이벤트

IntegerValueChanged 이벤트를 활성화하거나 사용하지 않도록 설정합니다.

```cpp
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*p 컨트롤러*<br/>
상위 컨트롤러에 대한 포인터입니다.

*bEnable*<br/>
TRUE - 활성화 이벤트, FALSE - 이벤트를 사용하지 않도록 설정합니다.

### <a name="remarks"></a>설명

ValueChanged 이벤트가 활성화되면 프레임워크는 가상 메서드 CAnimationController::OnAnimationIntegerValueChanged를 호출합니다. 이 이벤트를 처리하려면 CAnimationController에서 파생된 클래스에서 재정의해야 합니다. 이 메서드는 애니메이션 변수의 정수 값이 변경될 때마다 호출됩니다.

## <a name="canimationvariableenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a>C애니메이션변수::인에이블밸류변경이벤트

ValueChanged 이벤트를 활성화하거나 사용하지 않도록 설정합니다.

```cpp
void EnableValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*p 컨트롤러*<br/>
상위 컨트롤러에 대한 포인터입니다.

*bEnable*<br/>
TRUE - 활성화 이벤트, FALSE - 이벤트를 사용하지 않도록 설정합니다.

### <a name="remarks"></a>설명

ValueChanged 이벤트가 활성화되면 프레임워크는 가상 메서드 CAnimationController::OnAnimationValueChanged를 호출합니다. 이 이벤트를 처리하려면 CAnimationController에서 파생된 클래스에서 재정의해야 합니다. 이 메서드는 애니메이션 변수의 값이 변경될 때마다 호출됩니다.

## <a name="canimationvariablegetdefaultvalue"></a><a name="getdefaultvalue"></a>C애니메이션 변수::Getdefaultvalue

기본값을 반환합니다.

```
DOUBLE GetDefaultValue() const;
```

### <a name="return-value"></a>Return Value

기본값입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 애니메이션 변수의 기본값을 가져옵니다. 기본값은 생성자 또는 SetDefaultValue 메서드에 의해 설정할 수 있습니다.

## <a name="canimationvariablegetparentanimationobject"></a><a name="getparentanimationobject"></a>C애니메이션변수::GetParent애니메이션오브젝트

상위 애니메이션 개체를 반환합니다.

```
CAnimationBaseObject* GetParentAnimationObject();
```

### <a name="return-value"></a>Return Value

부모 애니메이션 개체에 대한 포인터(관계가 설정된 경우, 그렇지 않으면 NULL).

### <a name="remarks"></a>설명

이 메서드를 호출하여 상위 애니메이션 개체(컨테이너)에 대한 포인터를 검색할 수 있습니다.

## <a name="canimationvariablegetvalue"></a><a name="getvalue"></a>C애니메이션변수::Getvalue

애니메이션 변수의 현재 값을 반환합니다.

```
HRESULT GetValue(DOUBLE& dblValue);
HRESULT GetValue(INT32& nValue);
```

### <a name="parameters"></a>매개 변수

*dblValue*<br/>
애니메이션 변수의 현재 값입니다.

*n값*<br/>
애니메이션 변수의 현재 값입니다.

### <a name="return-value"></a>Return Value

값이 성공적으로 가져온 경우 또는 기본 애니메이션 변수가 만들어지지 않은 S_OK. 그렇지 않으면 HRESULT 오류 코드.

### <a name="remarks"></a>설명

이 메서드를 호출하여 애니메이션 변수의 현재 값을 검색할 수 있습니다. 기본 COM 개체가 만들어지지 않은 경우 dblValue는 함수가 반환될 때 기본값을 포함합니다.

## <a name="canimationvariablegetvariable"></a><a name="getvariable"></a>C애니메이션변수::Get변수

IUIAnimationVariable COM 개체에 대한 포인터를 반환합니다.

```
IUIAnimationVariable* GetVariable();
```

### <a name="return-value"></a>Return Value

IUIAnimationVariable COM 개체에 대한 유효한 포인터 또는 애니메이션 변수가 만들어지지 않았거나 만들 수 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 기본 IUIAnimationVariable COM 개체에 액세스하고 필요한 경우 해당 메서드를 직접 호출합니다.

## <a name="canimationvariablem_bautodestroytransitions"></a><a name="m_bautodestroytransitions"></a>C애니메이션변수::m_bAutodestroyTransitions

관련 전환 개체를 삭제할지 여부를 지정합니다.

```
BOOL m_bAutodestroyTransitions;
```

### <a name="remarks"></a>설명

이 값을 TRUE로 설정하여 전환 객체가 내부 전환 목록에서 제거될 때 강제로 삭제됩니다. 이 값이 FALSE이면 응용 프로그램을 호출하여 전환을 삭제해야 합니다. 애니메이션이 예약된 후에는 전환 목록이 항상 지워집니다. 기본값은 FALSE입니다.

## <a name="canimationvariablem_dbldefaultvalue"></a><a name="m_dbldefaultvalue"></a>C애니메이션변수::m_dblDefaultValue

IUIAnimation변수에 전파되는 기본값을 지정합니다.

```
DOUBLE m_dblDefaultValue;
```

## <a name="canimationvariablem_lsttransitions"></a><a name="m_lsttransitions"></a>C애니메이션변수:m_lstTransitions

이 애니메이션 변수에 애니메이션을 만드는 전환 목록이 포함되어 있습니다.

```
CObList m_lstTransitions;
```

## <a name="canimationvariablem_pparentobject"></a><a name="m_pparentobject"></a>C애니메이션변수:m_pParentObject

이 애니메이션 변수를 캡슐화하는 애니메이션 개체에 대한 포인터입니다.

```
CAnimationBaseObject* m_pParentObject;
```

## <a name="canimationvariablem_variable"></a><a name="m_variable"></a>C애니메이션변수::m_variable

IUIAnimationVariable COM 개체에 대한 포인터를 저장합니다. COM 개체가 아직 생성되지 않았거나 생성에 실패한 경우 NULL입니다.

```
ATL::CComPtr<IUIAnimationVariable> m_variable;
```

## <a name="canimationvariablesetdefaultvalue"></a><a name="setdefaultvalue"></a>C애니메이션 변수::설정디폴값

기본값을 설정하고 IUIAnimationVariable COM 개체를 해제합니다.

```cpp
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>매개 변수

*dblDefault값*<br/>
새 기본값을 지정합니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 기본값을 재설정합니다. 이 메서드는 내부 IUIAnimationVariable COM 개체를 해제하므로 애니메이션 변수를 다시 만들 때 기본 COM 개체에 새 기본 값이 가져옵니다. 애니메이션 변수를 나타내는 COM 개체가 생성되지 않았거나 변수가 애니메이션되지 않은 경우 기본값은 GetValue에 의해 반환됩니다.

## <a name="canimationvariablesetparentanimationobject"></a><a name="setparentanimationobject"></a>C애니메이션변수::설정부모애니메이션오브젝트

애니메이션 변수와 애니메이션 개체 간의 관계를 설정합니다.

```cpp
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```

### <a name="parameters"></a>매개 변수

*p부모 오브젝트*<br/>
이 변수를 포함하는 애니메이션 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 내부적으로 호출되어 애니메이션 변수와 애니메이션 변수를 캡슐화하는 애니메이션 개체 간의 일대일 관계를 설정합니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
