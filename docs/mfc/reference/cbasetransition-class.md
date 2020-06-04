---
title: CBaseTransition 클래스
ms.date: 03/27/2019
f1_keywords:
- CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboardAtKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::Clear
- AFXANIMATIONCONTROLLER/CBaseTransition::Create
- AFXANIMATIONCONTROLLER/CBaseTransition::GetEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::GetStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::GetType
- AFXANIMATIONCONTROLLER/CBaseTransition::IsAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::SetKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::SetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_transition
- AFXANIMATIONCONTROLLER/CBaseTransition::m_type
helpviewer_keywords:
- CBaseTransition [MFC], CBaseTransition
- CBaseTransition [MFC], AddToStoryboard
- CBaseTransition [MFC], AddToStoryboardAtKeyframes
- CBaseTransition [MFC], Clear
- CBaseTransition [MFC], Create
- CBaseTransition [MFC], GetEndKeyframe
- CBaseTransition [MFC], GetRelatedVariable
- CBaseTransition [MFC], GetStartKeyframe
- CBaseTransition [MFC], GetTransition
- CBaseTransition [MFC], GetType
- CBaseTransition [MFC], IsAdded
- CBaseTransition [MFC], SetKeyframes
- CBaseTransition [MFC], SetRelatedVariable
- CBaseTransition [MFC], m_bAdded
- CBaseTransition [MFC], m_pEndKeyframe
- CBaseTransition [MFC], m_pRelatedVariable
- CBaseTransition [MFC], m_pStartKeyframe
- CBaseTransition [MFC], m_transition
- CBaseTransition [MFC], m_type
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
ms.openlocfilehash: 9abe4ae55d9d84ea435cd5d82925ff8b8a544480
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752966"
---
# <a name="cbasetransition-class"></a>CBaseTransition 클래스

기본 전환을 나타냅니다.

## <a name="syntax"></a>구문

```
class CBaseTransition : public CObject;
```

## <a name="members"></a>멤버

### <a name="public-enumerations"></a>public 열거형

|속성|Description|
|----------|-----------------|
|[CBaseTransition::TRANSITION_TYPE 열거](#transition_type_enumeration)|Windows 애니메이션 API의 MFC 구현에서 현재 지원되는 전환 유형을 정의합니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CBase전환::CBase전환](#cbasetransition)|기본 전환 개체를 생성합니다.|
|[CBase전환::~CBase전환](#_dtorcbasetransition)|소멸자입니다. 전환 개체가 소멸될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CBaseTransition::추가 스토리 보드](#addtostoryboard)|스토리보드에 전환을 추가합니다.|
|[CBaseTransition::추가 스토리 보드At키프레임](#addtostoryboardatkeyframes)|스토리보드에 전환을 추가합니다.|
|[CBase전환::지우기](#clear)|캡슐화된 IUIAnimationTransition COM 개체를 해제합니다.|
|[CBase전환::만들기](#create)|COM 전환을 만듭니다.|
|[CBase전환::GetEndKeyframe](#getendkeyframe)|시작 키프레임을 반환합니다.|
|[CBaseTransition::Getrelated변수](#getrelatedvariable)|관련 변수에 대한 포인터를 반환합니다.|
|[CBase전환::겟스타트키프레임](#getstartkeyframe)|시작 키프레임을 반환합니다.|
|[CBase전환::GetTransition](#gettransition)|오버로드되었습니다. 기본 COM 전환 개체에 대한 포인터를 반환합니다.|
|[CBase전환::GetType](#gettype)|전환 형식을 반환합니다.|
|[CBase전환::추가](#isadded)|전환이 스토리보드에 추가되었는지 여부를 알려줍니다.|
|[CBase전환::세트키프레임](#setkeyframes)|전환에 대한 키프레임을 설정합니다.|
|[CBaseTransition::집합 관련 변수](#setrelatedvariable)|애니메이션 변수와 전환 간의 관계를 설정합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CBase전환::m_bAdded](#m_badded)|전환이 스토리보드에 추가되었는지 여부를 지정합니다.|
|[CBase전환::m_pEndKeyframe](#m_pendkeyframe)|전환의 끝을 지정하는 키프레임에 대한 포인터를 저장합니다.|
|[CBase전환::m_pRelatedVariable](#m_prelatedvariable)|m_transition 저장된 전환과 함께 애니메이션되는 애니메이션 변수에 대한 포인터입니다.|
|[CBase전환::m_pStartKeyframe](#m_pstartkeyframe)|전환의 시작을 지정하는 키프레임에 대한 포인터를 저장합니다.|
|[CBase전환::m_transition](#m_transition)|IUIAnimation전환에 대한 포인터를 저장합니다. COM 전환 개체가 만들어지지 않은 경우 NULL입니다.|
|[CBase전환::m_type](#m_type)|전환 유형을 저장합니다.|

## <a name="remarks"></a>설명

이 클래스는 IUIAnimationTransition 인터페이스를 캡슐화하 고 모든 전환에 대 한 기본 클래스 역할을 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CBaseTransition`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="cbasetransitioncbasetransition"></a><a name="_dtorcbasetransition"></a>CBase전환::~CBase전환

소멸자입니다. 전환 개체가 소멸될 때 호출됩니다.

```
virtual ~CBaseTransition();
```

## <a name="cbasetransitionaddtostoryboard"></a><a name="addtostoryboard"></a>CBaseTransition::추가 스토리 보드

스토리보드에 전환을 추가합니다.

```
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>매개 변수

*p스토리보드*<br/>
스토리보드에 대한 포인터로, 관련 변수에 애니메이션을 애니메이션합니다.

### <a name="return-value"></a>Return Value

TRUE, 전환이 스토리보드에 성공적으로 추가된 경우.

### <a name="remarks"></a>설명

스토리보드의 관련 변수에 전환을 적용합니다. 이 전환이 이 스토리보드의 이 변수에 적용된 첫 번째 전환인 경우 전환은 스토리보드의 시작 지점에서 시작됩니다. 그렇지 않으면 전환이 변수에 가장 최근에 추가된 전환에 추가됩니다.

## <a name="cbasetransitionaddtostoryboardatkeyframes"></a><a name="addtostoryboardatkeyframes"></a>CBaseTransition::추가 스토리 보드At키프레임

스토리보드에 전환을 추가합니다.

```
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>매개 변수

*p스토리보드*<br/>
스토리보드에 대한 포인터로, 관련 변수에 애니메이션을 애니메이션합니다.

### <a name="return-value"></a>Return Value

TRUE, 전환이 스토리보드에 성공적으로 추가된 경우.

### <a name="remarks"></a>설명

스토리보드의 관련 변수에 전환을 적용합니다. 시작 키프레임을 지정하면 해당 키프레임에서 전환이 시작됩니다. 끝 키프레임을 지정하면 전환이 시작 키프레임에서 시작되고 끝 키프레임에서 중지됩니다. 기간 매개 변수를 지정하여 전환을 만든 경우 해당 기간은 시작 키프레임과 끝 키프레임 사이의 시간 기간으로 덮어씁니까. 키프레임이 지정되지 않은 경우 전환이 변수에 가장 최근에 추가된 전환에 추가됩니다.

## <a name="cbasetransitioncbasetransition"></a><a name="cbasetransition"></a>CBase전환::CBase전환

기본 전환 개체를 생성합니다.

```
CBaseTransition();
```

## <a name="cbasetransitionclear"></a><a name="clear"></a>CBase전환::지우기

캡슐화된 IUIAnimationTransition COM 개체를 해제합니다.

```cpp
void Clear();
```

### <a name="remarks"></a>설명

IUITransition 인터페이스 누수 방지하기 위해 파생 클래스의 Create 메서드에서 이 메서드를 호출해야 합니다.

## <a name="cbasetransitioncreate"></a><a name="create"></a>CBase전환::만들기

COM 전환을 만듭니다.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory) = 0;
```

### <a name="parameters"></a>매개 변수

*p라이브러리*<br/>
표준 전환을 만드는 전환 라이브러리에 대한 포인터입니다. 사용자 지정 전환에 대해 NULL이 될 수 있습니다.

*pFactory*<br/>
사용자 지정 전환을 만드는 전환 팩터리에 대한 포인터입니다. 표준 전환의 경우 NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

TRUE 전환 COM 개체가 성공적으로 생성된 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

파생 클래스에서 재정의해야 하는 순수 가상 함수입니다. 기본 COM 전환 개체를 인스턴스화하기 위해 프레임워크에서 호출합니다.

## <a name="cbasetransitiongetendkeyframe"></a><a name="getendkeyframe"></a>CBase전환::GetEndKeyframe

시작 키프레임을 반환합니다.

```
CBaseKeyFrame* GetEndKeyframe();
```

### <a name="return-value"></a>Return Value

키프레임 사이에 전환을 삽입하지 않아야 하는 경우 키프레임또는 NULL에 대한 유효한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 SetKeyframes에서 이전에 설정한 키프레임 개체에 액세스하는 데 사용할 수 있습니다. 전환이 스토리보드에 추가될 때 최상위 코드에서 호출됩니다.

## <a name="cbasetransitiongetrelatedvariable"></a><a name="getrelatedvariable"></a>CBaseTransition::Getrelated변수

관련 변수에 대한 포인터를 반환합니다.

```
CAnimationVariable* GetRelatedVariable();
```

### <a name="return-value"></a>Return Value

SetRelatedVariable에 의해 애니메이션 변수가 설정되지 않은 경우 애니메이션 변수또는 NULL에 대한 유효한 포인터입니다.

### <a name="remarks"></a>설명

관련 애니메이션 변수에 대한 접근자입니다.

## <a name="cbasetransitiongetstartkeyframe"></a><a name="getstartkeyframe"></a>CBase전환::겟스타트키프레임

시작 키프레임을 반환합니다.

```
CBaseKeyFrame* GetStartKeyframe();
```

### <a name="return-value"></a>Return Value

키프레임에 대한 유효한 포인터 또는 키프레임 후에 전환이 시작되지 않아야 하는 경우 NULL입니다.

### <a name="remarks"></a>설명

이 메서드는 SetKeyframes에서 이전에 설정한 키프레임 개체에 액세스하는 데 사용할 수 있습니다. 전환이 스토리보드에 추가될 때 최상위 코드에서 호출됩니다.

## <a name="cbasetransitiongettransition"></a><a name="gettransition"></a>CBase전환::GetTransition

기본 COM 전환 개체에 대한 포인터를 반환합니다.

```
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory);

IUIAnimationTransition* GetTransition();
```

### <a name="parameters"></a>매개 변수

*p라이브러리*<br/>
표준 전환을 만드는 전환 라이브러리에 대한 포인터입니다. 사용자 지정 전환에 대해 NULL이 될 수 있습니다.

*pFactory*<br/>
사용자 지정 전환을 만드는 전환 팩터리에 대한 포인터입니다. 표준 전환의 경우 NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

기본 전환을 만들 수 없는 경우 IUIAnimationTransition 또는 NULL에 대한 유효한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 기본 COM 전환 개체에 대 한 포인터를 반환 하 고 필요한 경우 만듭니다.

## <a name="cbasetransitiongettype"></a><a name="gettype"></a>CBase전환::GetType

전환 형식을 반환합니다.

```
TRANSITION_TYPE GetType() const;
```

### <a name="return-value"></a>Return Value

TRANSITION_TYPE 수 있는 값 중 하나입니다.

### <a name="remarks"></a>설명

이 메서드는 해당 형식별로 전환 개체를 식별하는 데 사용할 수 있습니다. 형식은 파생 클래스의 생성자에서 설정됩니다.

## <a name="cbasetransitionisadded"></a><a name="isadded"></a>CBase전환::추가

전환이 스토리보드에 추가되었는지 여부를 알려줍니다.

```
BOOL IsAdded();
```

### <a name="return-value"></a>Return Value

전환이 스토리보드에 추가된 경우 TRUE를 반환합니다(그렇지 않으면 FALSE).

### <a name="remarks"></a>설명

이 플래그는 최상위 코드가 스토리보드에 전환을 추가하는 경우 내부적으로 설정됩니다.

## <a name="cbasetransitionm_badded"></a><a name="m_badded"></a>CBase전환::m_bAdded

전환이 스토리보드에 추가되었는지 여부를 지정합니다.

```
BOOL m_bAdded;
```

## <a name="cbasetransitionm_pendkeyframe"></a><a name="m_pendkeyframe"></a>CBase전환::m_pEndKeyframe

전환의 끝을 지정하는 키프레임에 대한 포인터를 저장합니다.

```
CBaseKeyFrame* m_pEndKeyframe;
```

## <a name="cbasetransitionm_prelatedvariable"></a><a name="m_prelatedvariable"></a>CBase전환::m_pRelatedVariable

m_transition 저장된 전환과 함께 애니메이션되는 애니메이션 변수에 대한 포인터입니다.

```
CAnimationVariable* m_pRelatedVariable;
```

## <a name="cbasetransitionm_pstartkeyframe"></a><a name="m_pstartkeyframe"></a>CBase전환::m_pStartKeyframe

전환의 시작을 지정하는 키프레임에 대한 포인터를 저장합니다.

```
CBaseKeyFrame* m_pStartKeyframe;
```

## <a name="cbasetransitionm_transition"></a><a name="m_transition"></a>CBase전환::m_transition

IUIAnimation전환에 대한 포인터를 저장합니다. COM 전환 개체가 만들어지지 않은 경우 NULL입니다.

```
ATL::CComPtr<IUIAnimationTransition> m_transition;
```

## <a name="cbasetransitionm_type"></a><a name="m_type"></a>CBase전환::m_type

전환 유형을 저장합니다.

```
TRANSITION_TYPE m_type;
```

## <a name="cbasetransitionsetkeyframes"></a><a name="setkeyframes"></a>CBase전환::세트키프레임

전환에 대한 키프레임을 설정합니다.

```cpp
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,
    CBaseKeyFrame* pEnd = NULL);
```

### <a name="parameters"></a>매개 변수

*p시작*<br/>
전환의 시작을 지정하는 키프레임입니다.

*보류*<br/>
전환의 끝을 지정하는 키프레임입니다.

### <a name="remarks"></a>설명

이 메서드는 지정된 키프레임 이후에 시작하도록 전환을 알려주며, 선택적으로 pEnd가 NULL이 아닌 경우 지정된 키프레임 앞에 끝납니다. 기간 매개 변수를 지정하여 전환을 만든 경우 해당 기간은 시작 키프레임과 끝 키프레임 사이의 시간 기간으로 덮어씁니까.

## <a name="cbasetransitionsetrelatedvariable"></a><a name="setrelatedvariable"></a>CBaseTransition::집합 관련 변수

애니메이션 변수와 전환 간의 관계를 설정합니다.

```cpp
void SetRelatedVariable(CAnimationVariable* pVariable);
```

### <a name="parameters"></a>매개 변수

*p변수*<br/>
관련 애니메이션 변수에 대한 포인터입니다.

### <a name="remarks"></a>설명

애니메이션 변수와 전환 간의 관계를 설정합니다. 전환은 하나의 변수에만 적용할 수 있습니다.

## <a name="cbasetransitiontransition_type-enumeration"></a><a name="transition_type_enumeration"></a>CBaseTransition::TRANSITION_TYPE 열거

Windows 애니메이션 API의 MFC 구현에서 현재 지원되는 전환 유형을 정의합니다.

```
enum TRANSITION_TYPE;
```

### <a name="remarks"></a>설명

전환 형식은 특정 전환의 생성자에서 설정됩니다. 예를 들어 CSinusoidalTransitionFromRange는 해당 형식을 SINUSOIDAL_FROM_RANGE 설정합니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
