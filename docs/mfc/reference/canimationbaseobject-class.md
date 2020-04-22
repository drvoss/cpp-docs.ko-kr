---
title: CAnimationBaseObject 클래스
ms.date: 03/27/2019
f1_keywords:
- CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ContainsVariable
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::DetachFromController
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetParentAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_dwUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_pParentController
helpviewer_keywords:
- CAnimationBaseObject [MFC], CAnimationBaseObject
- CAnimationBaseObject [MFC], ApplyTransitions
- CAnimationBaseObject [MFC], ClearTransitions
- CAnimationBaseObject [MFC], ContainsVariable
- CAnimationBaseObject [MFC], CreateTransitions
- CAnimationBaseObject [MFC], DetachFromController
- CAnimationBaseObject [MFC], EnableIntegerValueChangedEvent
- CAnimationBaseObject [MFC], EnableValueChangedEvent
- CAnimationBaseObject [MFC], GetAutodestroyTransitions
- CAnimationBaseObject [MFC], GetGroupID
- CAnimationBaseObject [MFC], GetObjectID
- CAnimationBaseObject [MFC], GetUserData
- CAnimationBaseObject [MFC], SetAutodestroyTransitions
- CAnimationBaseObject [MFC], SetID
- CAnimationBaseObject [MFC], SetUserData
- CAnimationBaseObject [MFC], GetAnimationVariableList
- CAnimationBaseObject [MFC], SetParentAnimationObjects
- CAnimationBaseObject [MFC], m_bAutodestroyTransitions
- CAnimationBaseObject [MFC], m_dwUserData
- CAnimationBaseObject [MFC], m_nGroupID
- CAnimationBaseObject [MFC], m_nObjectID
- CAnimationBaseObject [MFC], m_pParentController
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
ms.openlocfilehash: 1874ddfdd26b8dd371e32f7e68ea8f668c47d8e1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750213"
---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject 클래스

모든 애니메이션 개체의 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CAnimationBaseObject : public CObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C애니메이션베이스오브젝트::C애니메이션베이스오브젝트](#canimationbaseobject)|오버로드되었습니다. 애니메이션 개체를 생성합니다.|
|[C애니메이션베이스오브젝트:~C애니메이션베이스오브젝트](#_dtorcanimationbaseobject)|소멸자입니다. 애니메이션 개체가 소멸될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션베이스오브젝트:적용전환](#applytransitions)|캡슐화된 애니메이션 변수가 있는 스토리보드에 전환을 추가합니다.|
|[C애니메이션베이스오브젝트:클리어트랜지션](#cleartransitions)|관련된 모든 전환을 제거합니다.|
|[C애니메이션베이스오브젝트::contains변수](#containsvariable)|애니메이션 개체에 특정 애니메이션 변수가 포함되어 있는지 여부를 확인합니다.|
|[C애니메이션베이스오브젝트:만들기전환](#createtransitions)|애니메이션 개체와 연결된 전환을 만듭니다.|
|[C애니메이션베이스오브젝트::D에타치From컨트롤러](#detachfromcontroller)|상위 애니메이션 컨트롤러에서 애니메이션 개체를 분리합니다.|
|[C애니메이션베이스오브젝트::인에이블인티거밸류변경이벤트](#enableintegervaluechangedevent)|정수 값 변경 이벤트 처리기를 설정합니다.|
|[C애니메이션베이스오브젝트::인에이블밸류변경이벤트](#enablevaluechangedevent)|값 변경 이벤트 처리기를 설정합니다.|
|[C애니메이션베이스오브젝트::겟오토파괴전환](#getautodestroytransitions)|관련 전환이 자동으로 소멸되는지 여부를 알려줍니다.|
|[C애니메이션베이스오브젝트::GetGroupID](#getgroupid)|현재 그룹 ID를 반환합니다.|
|[C애니메이션베이스오브젝트::게오브젝트ID](#getobjectid)|현재 개체 ID를 반환합니다.|
|[시애니메이션베이스오브젝트::게유저 데이터](#getuserdata)|사용자 정의 데이터를 반환합니다.|
|[C애니메이션베이스오브젝트:셋오토파괴전환](#setautodestroytransitions)|전환을 자동으로 삭제하는 플래그를 설정합니다.|
|[C애니메이션베이스오브젝트::세팅ID](#setid)|새 아이디를 설정합니다.|
|[시애니메이션베이스오브젝트::사용자 데이터 설정](#setuserdata)|사용자 정의 데이터를 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션베이스오브젝트::겟애니메이션변수리스트](#getanimationvariablelist)|포함된 애니메이션 변수에 대한 포인터를 수집합니다.|
|[C애니메이션베이스오브젝트::설정부모애니메이션오브젝트](#setparentanimationobjects)|애니메이션 개체에 포함된 애니메이션 변수와 해당 컨테이너 간의 관계를 설정합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[시애니메이션베이스오브젝트:m_bAutodestroyTransitions](#m_bautodestroytransitions)|관련 전환을 자동으로 삭제할지 여부를 지정합니다.|
|[C애니메이션베이스오브젝트:m_dwUserData](#m_dwuserdata)|사용자 정의 데이터를 저장합니다.|
|[C애니메이션베이스오브젝트:m_nGroupID](#m_ngroupid)|애니메이션 개체의 그룹 ID를 지정합니다.|
|[시애니메이션베이스오브젝트:m_nObjectID](#m_nobjectid)|애니메이션 개체의 개체 ID를 지정합니다.|
|[시애니메이션베이스오브젝트:m_pParentController](#m_pparentcontroller)|상위 애니메이션 컨트롤러에 대한 포인터입니다.|

## <a name="remarks"></a>설명

이 클래스는 모든 애니메이션 개체에 대한 기본 메서드를 구현합니다. 애니메이션 개체는 응용 프로그램의 값, 점, 크기, 사각형 또는 색상을 나타낼 수 있으며 사용자 지정 엔터티도 나타낼 수 있습니다. 애니메이션 개체는 애니메이션 그룹에 저장됩니다(CAnimationGroup 참조). 각 그룹은 별도로 애니메이션할 수 있으며 스토리보드의 아날로그로 취급할 수 있습니다. 애니메이션 개체는 논리적 표현에 따라 하나 이상의 애니메이션 변수(CAnimationVariable 참조)를 캡슐화합니다. 예를 들어 CAnimationRect에는 사각형의 각 측면에 대해 하나의 변수인 네 개의 애니메이션 변수가 포함되어 있습니다. 각 애니메이션 개체 클래스는 캡슐화된 애니메이션 변수에 전환을 적용하는 데 사용해야 하는 오버로드된 AddTransition 메서드를 노출합니다. 애니메이션 개체는 개체 ID(선택 사항)와 그룹 ID로 식별할 수 있습니다. 그룹을 수정하기 위해 애니메이션 개체를 배치하려면 그룹 ID가 필요하지만 그룹 ID를 지정하지 않으면 개체가 ID 0이 있는 기본 그룹에 배치됩니다. 다른 GroupID를 사용하여 SetID를 호출하면 애니메이션 개체가 다른 그룹으로 이동됩니다(필요한 경우 새 그룹이 만들어집니다).

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationBaseObject`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="_dtorcanimationbaseobject"></a>C애니메이션베이스오브젝트:~C애니메이션베이스오브젝트

소멸자입니다. 애니메이션 개체가 소멸될 때 호출됩니다.

```
virtual ~CAnimationBaseObject();
```

## <a name="canimationbaseobjectapplytransitions"></a><a name="applytransitions"></a>C애니메이션베이스오브젝트:적용전환

캡슐화된 애니메이션 변수가 있는 스토리보드에 전환을 추가합니다.

```
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>매개 변수

*p스토리보드*<br/>
스토리보드에 대한 포인터입니다.

*b리곤키프레임*<br/>
FALSE인 경우 이 메서드는 키프레임에 종속되지 않는 전환만 추가합니다.

### <a name="return-value"></a>Return Value

전환이 성공적으로 추가된 경우 TRUE입니다.

### <a name="remarks"></a>설명

AddTransition(파생 클래스에서 오버로드된 메서드)와 함께 추가된 관련 전환을 스토리보드에 추가합니다.

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="canimationbaseobject"></a>C애니메이션베이스오브젝트::C애니메이션베이스오브젝트

애니메이션 개체를 생성합니다.

```
CAnimationBaseObject();

CAnimationBaseObject(
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>매개 변수

*n그룹 ID*<br/>
그룹 ID를 지정합니다.

*n개체 ID*<br/>
개체 ID를 지정합니다.

*dw사용자 데이터*<br/>
애니메이션 개체와 연결되고 런타임 나중에 검색할 수 있는 사용자 정의 데이터입니다.

### <a name="remarks"></a>설명

애니메이션 개체를 생성하고 기본 개체 ID(0)와 그룹 ID(0)를 할당합니다.

## <a name="canimationbaseobjectcleartransitions"></a><a name="cleartransitions"></a>C애니메이션베이스오브젝트:클리어트랜지션

관련된 모든 전환을 제거합니다.

```
virtual void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>매개 변수

*b 자동 파괴*<br/>
전환 개체를 자동으로 삭제할지 또는 관련 목록에서 제거할지 지정합니다.

### <a name="remarks"></a>설명

bAutodestroy 또는 m_bAutodestroyTransitions 플래그가 TRUE인 경우 모든 관련 전환을 제거하고 이를 파괴합니다. 전환은 스택에 할당되지 않은 경우에만 자동으로 소멸되어야 합니다. 위의 플래그가 FALSE이면 전환이 관련 전환의 내부 목록에서 제거됩니다.

## <a name="canimationbaseobjectcontainsvariable"></a><a name="containsvariable"></a>C애니메이션베이스오브젝트::contains변수

애니메이션 개체에 특정 애니메이션 변수가 포함되어 있는지 여부를 확인합니다.

```
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>매개 변수

*p변수*<br/>
애니메이션 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 애니메이션 변수가 애니메이션 오브젝트에 포함되어 있는 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 pVariable에 의해 지정된 애니메이션 변수가 애니메이션 개체 내에 포함되어 있는지 여부를 확인하는 데 사용할 수 있습니다. 애니메이션 개체는 유형에 따라 여러 애니메이션 변수를 포함할 수 있습니다. 예를 들어 CAnimationColor에는 각 색상 구성 요소(빨간색, 녹색 및 파란색)에 대해 하나씩 세 개의 변수가 포함되어 있습니다. 애니메이션 변수의 값이 변경되면 Windows 애니메이션 API는 ValueChanged 또는 IntegerValueChanged 이벤트(활성화된 경우)를 보내고 이 이벤트의 매개 변수는 애니메이션 변수의 IUIAnimationVariable인터페이스에 대한 포인터입니다. 이 메서드는 포함 된 COM 개체에 대 한 포인터에서 애니메이션에 대 한 포인터를 가져오는 데 도움이 됩니다.

## <a name="canimationbaseobjectcreatetransitions"></a><a name="createtransitions"></a>C애니메이션베이스오브젝트:만들기전환

애니메이션 개체와 연결된 전환을 만듭니다.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Return Value

TRUE 전환이 성공적으로 생성된 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

파생 애니메이션 개체에 캡슐화된 애니메이션 변수 목록을 반복하고 각 애니메이션 변수와 연결된 전환을 만듭니다.

## <a name="canimationbaseobjectdetachfromcontroller"></a><a name="detachfromcontroller"></a>C애니메이션베이스오브젝트::D에타치From컨트롤러

상위 애니메이션 컨트롤러에서 애니메이션 개체를 분리합니다.

```cpp
void DetachFromController();
```

### <a name="remarks"></a>설명

이 메서드는 내부적으로 사용 됩니다.

## <a name="canimationbaseobjectenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a>C애니메이션베이스오브젝트::인에이블인티거밸류변경이벤트

정수 값 변경 이벤트 처리기를 설정합니다.

```
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*p 컨트롤러*<br/>
상위 컨트롤러에 대한 포인터입니다.

*bEnable*<br/>
정수 값 변경 된 이벤트를 사용 하거나 사용 하지 않도록 설정할지 여부를 지정 합니다.

### <a name="remarks"></a>설명

정수 값 변경 이벤트 처리기가 활성화된 경우 CAnimationController:OnAnimationIntegerValueChanged 메서드에서 이 이벤트를 처리할 수 있습니다.CAnimationController 파생 클래스에서 재정의 해야 합니다. 이 메서드는 애니메이션 정수 값이 변경될 때마다 호출됩니다.

## <a name="canimationbaseobjectenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a>C애니메이션베이스오브젝트::인에이블밸류변경이벤트

값 변경 이벤트 처리기를 설정합니다.

```
virtual void EnableValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*p 컨트롤러*<br/>
상위 컨트롤러에 대한 포인터입니다.

*bEnable*<br/>
값 변경 이벤트를 활성화하거나 사용하지 않도록 설정할지 여부를 지정합니다.

### <a name="remarks"></a>설명

값 변경된 이벤트 처리기가 활성화된 경우 CAnimationController:OnAnimationValueChanged 메서드에서 이 이벤트를 처리할 수 있습니다.CAnimationController 파생 클래스에서 재정의 해야 합니다. 이 메서드는 애니메이션 값이 변경될 때마다 호출됩니다.

## <a name="canimationbaseobjectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>C애니메이션베이스오브젝트::겟애니메이션변수리스트

포함된 애니메이션 변수에 대한 포인터를 수집합니다.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& list) = 0;
```

### <a name="parameters"></a>매개 변수

*list*<br/>
애니메이션 개체에 포함된 애니메이션 변수로 채워야 하는 목록입니다.

### <a name="remarks"></a>설명

이 순수 가상 메서드는 파생 클래스에서 재정의되어야 합니다. 애니메이션 개체는 유형에 따라 하나 이상의 애니메이션 변수를 포함합니다. 예를 들어 CAnimationPoint에는 각각 X 및 Y 좌표에 대한 두 개의 변수가 포함되어 있습니다. 기본 클래스 CAnimationBaseObject 애니메이션 변수 목록에 작동 하는 몇 가지 일반적인 메서드를 구현 합니다. 이러한 메서드는 특정 애니메이션 개체에 포함 된 실제 애니메이션 변수파생 클래스에 채워집니다 GetAnimationVariableList 를 호출, 다음 목록을 통해 루프 하 고 필요한 작업을 수행 합니다. 사용자 지정 애니메이션 개체를 만드는 경우 해당 개체에 포함된 모든 애니메이션 변수를 *나열하기* 위해 추가해야 합니다.

## <a name="canimationbaseobjectgetautodestroytransitions"></a><a name="getautodestroytransitions"></a>C애니메이션베이스오브젝트::겟오토파괴전환

관련 전환이 자동으로 소멸되는지 여부를 알려줍니다.

```
BOOL GetAutodestroyTransitions() const;
```

### <a name="return-value"></a>Return Value

TRUE이면 관련 전환이 자동으로 소멸됩니다. FALSE인 경우 응용 프로그램을 호출하여 전환 개체를 할당 지정해야 합니다.

### <a name="remarks"></a>설명

기본적으로 이 플래그는 TRUE입니다. 스택 및/또는 전환에 전환을 할당한 경우에만 이 플래그를 호출 응용 프로그램에서 할당 할 수 있습니다.

## <a name="canimationbaseobjectgetgroupid"></a><a name="getgroupid"></a>C애니메이션베이스오브젝트::GetGroupID

현재 그룹 ID를 반환합니다.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Return Value

현재 그룹 ID입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 그룹 ID를 검색합니다. 생성자 또는 SetID를 통해 그룹 ID가 명시적으로 설정되지 않은 경우 0입니다.

## <a name="canimationbaseobjectgetobjectid"></a><a name="getobjectid"></a>C애니메이션베이스오브젝트::게오브젝트ID

현재 개체 ID를 반환합니다.

```
UINT32 GetObjectID() const;
```

### <a name="return-value"></a>Return Value

현재 개체 ID입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 개체 ID를 검색합니다. 생성자 또는 SetID를 사용하면 개체 ID가 명시적으로 설정되지 않은 경우 0입니다.

## <a name="canimationbaseobjectgetuserdata"></a><a name="getuserdata"></a>시애니메이션베이스오브젝트::게유저 데이터

사용자 정의 데이터를 반환합니다.

```
DWORD GetUserData() const;
```

### <a name="return-value"></a>Return Value

사용자 지정 데이터의 값입니다.

### <a name="remarks"></a>설명

런타임시 사용자 지정 데이터를 검색하려면 이 메서드를 호출합니다. 생성자 또는 SetUserData에서 명시적으로 초기화되지 않은 경우 반환된 값은 0이 됩니다.

## <a name="canimationbaseobjectm_bautodestroytransitions"></a><a name="m_bautodestroytransitions"></a>시애니메이션베이스오브젝트:m_bAutodestroyTransitions

관련 전환을 자동으로 삭제할지 여부를 지정합니다.

```
BOOL m_bAutodestroyTransitions;
```

## <a name="canimationbaseobjectm_dwuserdata"></a><a name="m_dwuserdata"></a>C애니메이션베이스오브젝트:m_dwUserData

사용자 정의 데이터를 저장합니다.

```
DWORD m_dwUserData;
```

## <a name="canimationbaseobjectm_ngroupid"></a><a name="m_ngroupid"></a>C애니메이션베이스오브젝트:m_nGroupID

애니메이션 개체의 그룹 ID를 지정합니다.

```
UINT32 m_nGroupID;
```

## <a name="canimationbaseobjectm_nobjectid"></a><a name="m_nobjectid"></a>시애니메이션베이스오브젝트:m_nObjectID

애니메이션 개체의 개체 ID를 지정합니다.

```
UINT32 m_nObjectID;
```

## <a name="canimationbaseobjectm_pparentcontroller"></a><a name="m_pparentcontroller"></a>시애니메이션베이스오브젝트:m_pParentController

상위 애니메이션 컨트롤러에 대한 포인터입니다.

```
CAnimationController* m_pParentController;
```

## <a name="canimationbaseobjectsetautodestroytransitions"></a><a name="setautodestroytransitions"></a>C애니메이션베이스오브젝트:셋오토파괴전환

전환을 자동으로 삭제하는 플래그를 설정합니다.

```cpp
void SetAutodestroyTransitions(BOOL bValue);
```

### <a name="parameters"></a>매개 변수

*b값*<br/>
자동 소멸 플래그를 지정합니다.

### <a name="remarks"></a>설명

새 연산자 new를 사용하여 전환 개체를 할당한 경우에만 이 플래그를 설정합니다. 어떤 이유로 전환 개체가 스택에 할당된 경우 자동 삭제 플래그는 FALSE여야 합니다. 기본적으로 이 플래그는 TRUE입니다.

## <a name="canimationbaseobjectsetid"></a><a name="setid"></a>C애니메이션베이스오브젝트::세팅ID

새 아이디를 설정합니다.

```cpp
void SetID(
    UINT32 nObjectID,
    UINT32 nGroupID = 0);
```

### <a name="parameters"></a>매개 변수

*n개체 ID*<br/>
새 개체 ID를 지정합니다.

*n그룹 ID*<br/>
새 그룹 ID를 지정합니다.

### <a name="remarks"></a>설명

개체 ID 및 그룹 ID를 변경할 수 있습니다. 새 그룹 ID가 현재 ID와 다른 경우 애니메이션 개체가 다른 그룹으로 이동됩니다(필요한 경우 새 그룹이 만들어집니다).

## <a name="canimationbaseobjectsetparentanimationobjects"></a><a name="setparentanimationobjects"></a>C애니메이션베이스오브젝트::설정부모애니메이션오브젝트

애니메이션 개체에 포함된 애니메이션 변수와 해당 컨테이너 간의 관계를 설정합니다.

```
virtual void SetParentAnimationObjects();
```

### <a name="remarks"></a>설명

이 도우미는 애니메이션 개체에 포함된 애니메이션 변수와 해당 컨테이너 간의 관계를 설정하는 데 사용할 수 있습니다. 애니메이션 변수를 반복하고 각 애니메이션 변수에 부모 애니메이션 개체에 대한 백 포인터를 설정합니다. 현재 구현에서 실제 관계는 CAnimationBaseObject::ApplyTransitions에 설정되므로 CAnimationGroup::Animate를 호출할 때까지 백 포인터가 설정되지 않습니다. 관계를 아는 것은 이벤트를 처리하고 CAnimationVariable에서 부모 애니메이션 개체를 얻어야 할 때 유용할 수 있습니다. CAnimation변수 사용::GetParent애니메이션오브젝트.

## <a name="canimationbaseobjectsetuserdata"></a><a name="setuserdata"></a>시애니메이션베이스오브젝트::사용자 데이터 설정

사용자 정의 데이터를 설정합니다.

```cpp
void SetUserData (DWORD dwUserData);
```

### <a name="parameters"></a>매개 변수

*dw사용자 데이터*<br/>
사용자 지정 데이터를 지정합니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 사용자 지정 데이터를 애니메이션 개체와 연결합니다. 이 데이터는 GetUserData에 의해 런타임에 나중에 검색될 수 있습니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
