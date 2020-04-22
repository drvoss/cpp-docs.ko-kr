---
title: CAnimationGroup 클래스
ms.date: 03/27/2019
f1_keywords:
- CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::Animate
- AFXANIMATIONCONTROLLER/CAnimationGroup::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationGroup::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::Schedule
- AFXANIMATIONCONTROLLER/CAnimationGroup::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutoclearTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstKeyFrames
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pStoryboard
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pParentController
helpviewer_keywords:
- CAnimationGroup [MFC], CAnimationGroup
- CAnimationGroup [MFC], Animate
- CAnimationGroup [MFC], ApplyTransitions
- CAnimationGroup [MFC], FindAnimationObject
- CAnimationGroup [MFC], GetGroupID
- CAnimationGroup [MFC], RemoveKeyframes
- CAnimationGroup [MFC], RemoveTransitions
- CAnimationGroup [MFC], Schedule
- CAnimationGroup [MFC], SetAutodestroyTransitions
- CAnimationGroup [MFC], AddKeyframes
- CAnimationGroup [MFC], AddTransitions
- CAnimationGroup [MFC], CreateTransitions
- CAnimationGroup [MFC], m_bAutoclearTransitions
- CAnimationGroup [MFC], m_bAutodestroyAnimationObjects
- CAnimationGroup [MFC], m_bAutodestroyKeyframes
- CAnimationGroup [MFC], m_lstAnimationObjects
- CAnimationGroup [MFC], m_lstKeyFrames
- CAnimationGroup [MFC], m_pStoryboard
- CAnimationGroup [MFC], m_nGroupID
- CAnimationGroup [MFC], m_pParentController
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
ms.openlocfilehash: 14ac32524436ff46449171ad90599e60f63dff2a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750156"
---
# <a name="canimationgroup-class"></a>CAnimationGroup 클래스

애니메이션 스토리보드, 애니메이션 개체 및 전환을 결합하여 애니메이션을 정의하는 애니메이션 그룹을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationGroup;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C애니메이션 그룹::C애니메이션 그룹](#canimationgroup)|애니메이션 그룹을 생성합니다.|
|[C애니메이션 그룹:~C애니메이션 그룹](#_dtorcanimationgroup)|소멸자입니다. 애니메이션 그룹이 소멸될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션 그룹::애니메이션](#animate)|그룹에 애니메이션을 애니메이션합니다.|
|[C애니메이션 그룹::적용전환](#applytransitions)|애니메이션 개체에 전환을 적용합니다.|
|[C애니메이션 그룹::애니메이션 오브젝트 찾기](#findanimationobject)|지정된 애니메이션 변수가 포함된 애니메이션 개체를 찾습니다.|
|[C애니메이션 그룹::GetGroupID](#getgroupid)|GroupID를 반환합니다.|
|[C애니메이션 그룹::제거키프레임](#removekeyframes)|애니메이션 그룹에 속한 모든 키프레임을 제거하고 선택적으로 삭제합니다.|
|[C애니메이션 그룹::제거전환](#removetransitions)|애니메이션 그룹에 속한 애니메이션 개체에서 전환을 제거합니다.|
|[C애니메이션 그룹::일정](#schedule)|지정된 시간에 애니메이션을 예약합니다.|
|[C애니메이션 그룹::세트오토파괴전환](#setautodestroytransitions)|그룹에 속한 모든 애니메이션 오브젝트가 자동으로 전환을 삭제하도록 지시합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션 그룹::애드키프레임](#addkeyframes)|스토리보드에 키프레임을 추가하는 도우미입니다.|
|[C애니메이션 그룹::추가 전환](#addtransitions)|스토리보드에 전환을 추가하는 도우미입니다.|
|[C애니메이션 그룹::만들기전환](#createtransitions)|COM 전환 개체를 만드는 도우미입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C애니메이션 그룹::m_bAutoclearTransitions](#m_bautocleartransitions)|그룹에 속한 애니메이션 개체에서 전환을 지우는 방법을 지정합니다. 이 멤버가 TRUE이면 애니메이션이 예약되면 전환이 자동으로 제거됩니다. 그렇지 않으면 수동으로 전환을 제거해야 합니다.|
|[C애니메이션 그룹::m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|애니메이션 개체를 삭제하는 방법을 지정합니다. 이 매개변수가 TRUE이면 그룹이 소멸될 때 애니메이션 오브젝트가 자동으로 소멸됩니다. 그렇지 않으면 애니메이션 오브젝트를 수동으로 삭제해야 합니다. 기본값은 FALSE입니다. 그룹에 속한 모든 애니메이션 개체가 연산자 new와 동적으로 할당된 경우에만 이 값을 TRUE로 설정합니다.|
|[C애니메이션 그룹:m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|키프레임을 삭제하는 방법을 지정합니다. 이 값이 TRUE이면 모든 키프레임이 제거되고 소멸됩니다. 그렇지 않으면 목록에서만 제거됩니다. 기본값은 TRUE입니다.|
|[C애니메이션 그룹::m_lstAnimationObjects](#m_lstanimationobjects)|애니메이션 개체 목록을 포함합니다.|
|[C애니메이션 그룹::m_lstKeyFrames](#m_lstkeyframes)|키프레임 목록이 포함되어 있습니다.|
|[C애니메이션 그룹::m_pStoryboard](#m_pstoryboard)|애니메이션 스토리보드를 가리킵니다. 이 포인터는 Animate에 호출한 후에만 유효합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C애니메이션 그룹::m_nGroupID](#m_ngroupid)|애니메이션 그룹의 고유 식별자입니다.|
|[C애니메이션 그룹::m_pParentController](#m_pparentcontroller)|이 그룹에 속한 애니메이션 컨트롤러에 대한 포인터입니다.|

## <a name="remarks"></a>설명

애니메이션 그룹은 CAnimationController::AddAnimationObject를 사용하여 애니메이션 개체를 추가할 때 애니메이션 컨트롤러(CAnimationController)에 의해 자동으로 만들어집니다. 애니메이션 그룹은 일반적으로 애니메이션 그룹을 조작하는 매개 변수로 수행되는 GroupID로 식별됩니다. GroupID는 새 애니메이션 그룹에 추가되는 첫 번째 애니메이션 개체에서 가져온 것입니다. 캡슐화된 애니메이션 스토리보드는 CAnimationController::AnimateGroup을 호출한 후 만들어지며 공용 멤버 m_pStoryboard 통해 액세스할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CAnimationGroup`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationgroupcanimationgroup"></a><a name="_dtorcanimationgroup"></a>C애니메이션 그룹:~C애니메이션 그룹

소멸자입니다. 애니메이션 그룹이 소멸될 때 호출됩니다.

```
~CAnimationGroup();
```

## <a name="canimationgroupaddkeyframes"></a><a name="addkeyframes"></a>C애니메이션 그룹::애드키프레임

스토리보드에 키프레임을 추가하는 도우미입니다.

```cpp
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```

### <a name="parameters"></a>매개 변수

*p스토리보드*<br/>
스토리보드 COM 개체에 대한 포인터입니다.

*bAddDeep*<br/>
이 메서드가 다른 키프레임에 종속된 스토리보드 키프레임에 추가할지 여부를 지정합니다.

## <a name="canimationgroupaddtransitions"></a><a name="addtransitions"></a>C애니메이션 그룹::추가 전환

스토리보드에 전환을 추가하는 도우미입니다.

```cpp
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>매개 변수

*p스토리보드*<br/>
스토리보드 COM 개체에 대한 포인터입니다.

*b리곤키프레임*

## <a name="canimationgroupanimate"></a><a name="animate"></a>C애니메이션 그룹::애니메이션

그룹에 애니메이션을 애니메이션합니다.

```
BOOL Animate(
    IUIAnimationManager* pManager,
    IUIAnimationTimer* pTimer,
    BOOL bScheduleNow);
```

### <a name="parameters"></a>매개 변수

*pManager*<br/>
*pTimer*
*b스케줄나우*

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 내부 스토리 보드를 만들고, 전환을 만들고 적용 하 고 애니메이션을 예약 bScheduleNow TRUE 인 경우. bScheduleNow가 FALSE인 경우 지정된 시간에 애니메이션을 시작하려면 일정을 호출해야 합니다.

## <a name="canimationgroupapplytransitions"></a><a name="applytransitions"></a>C애니메이션 그룹::적용전환

애니메이션 개체에 전환을 적용합니다.

```cpp
void ApplyTransitions();
```

### <a name="remarks"></a>설명

이 메서드는 스토리 보드를 만들지 않은 경우 디버그 모드에서 ASSERTS입니다. 먼저 모든 전환을 생성한 다음 "정적" 키프레임(오프셋에 종속된 키프레임)을 추가하고, 키프레임에 의존하지 않는 전환을 추가하고, 전환 및 기타 키프레임에 따라 키프레임을 추가하고, 마지막으로 키프레임에 의존하는 전환을 추가합니다.

## <a name="canimationgroupcanimationgroup"></a><a name="canimationgroup"></a>C애니메이션 그룹::C애니메이션 그룹

애니메이션 그룹을 생성합니다.

```
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```

### <a name="parameters"></a>매개 변수

*p부모 컨트롤러*<br/>
그룹을 만드는 애니메이션 컨트롤러에 대한 포인터입니다.

*n그룹 ID*<br/>
그룹 ID를 지정합니다.

## <a name="canimationgroupcreatetransitions"></a><a name="createtransitions"></a>C애니메이션 그룹::만들기전환

COM 전환 개체를 만드는 도우미입니다.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Return Value

TRUE는 메서드가 성공하고 그렇지 않으면 FALSE입니다.

## <a name="canimationgroupfindanimationobject"></a><a name="findanimationobject"></a>C애니메이션 그룹::애니메이션 오브젝트 찾기

지정된 애니메이션 변수가 포함된 애니메이션 개체를 찾습니다.

```
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>매개 변수

*p변수*<br/>
애니메이션 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

애니메이션 개체에 대한 포인터 또는 애니메이션 개체를 찾을 수 없는 경우 NULL입니다.

## <a name="canimationgroupgetgroupid"></a><a name="getgroupid"></a>C애니메이션 그룹::GetGroupID

GroupID를 반환합니다.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Return Value

그룹 식별자입니다.

## <a name="canimationgroupm_bautocleartransitions"></a><a name="m_bautocleartransitions"></a>C애니메이션 그룹::m_bAutoclearTransitions

그룹에 속한 애니메이션 개체에서 전환을 지우는 방법을 지정합니다. 이 멤버가 TRUE이면 애니메이션이 예약되면 전환이 자동으로 제거됩니다. 그렇지 않으면 수동으로 전환을 제거해야 합니다.

```
BOOL m_bAutoclearTransitions;
```

## <a name="canimationgroupm_bautodestroyanimationobjects"></a><a name="m_bautodestroyanimationobjects"></a>C애니메이션 그룹::m_bAutodestroyAnimationObjects

애니메이션 개체를 삭제하는 방법을 지정합니다. 이 매개변수가 TRUE이면 그룹이 소멸될 때 애니메이션 오브젝트가 자동으로 소멸됩니다. 그렇지 않으면 애니메이션 오브젝트를 수동으로 삭제해야 합니다. 기본값은 FALSE입니다. 그룹에 속한 모든 애니메이션 개체가 연산자 new와 동적으로 할당된 경우에만 이 값을 TRUE로 설정합니다.

```
BOOL m_bAutodestroyAnimationObjects;
```

## <a name="canimationgroupm_bautodestroykeyframes"></a><a name="m_bautodestroykeyframes"></a>C애니메이션 그룹:m_bAutodestroyKeyframes

키프레임을 삭제하는 방법을 지정합니다. 이 값이 TRUE이면 모든 키프레임이 제거되고 소멸됩니다. 그렇지 않으면 목록에서만 제거됩니다. 기본값은 TRUE입니다.

```
BOOL m_bAutodestroyKeyframes;
```

## <a name="canimationgroupm_lstanimationobjects"></a><a name="m_lstanimationobjects"></a>C애니메이션 그룹::m_lstAnimationObjects

애니메이션 개체 목록을 포함합니다.

```
CObList m_lstAnimationObjects;
```

## <a name="canimationgroupm_lstkeyframes"></a><a name="m_lstkeyframes"></a>C애니메이션 그룹::m_lstKeyFrames

키프레임 목록이 포함되어 있습니다.

```
CObList m_lstKeyFrames;
```

## <a name="canimationgroupm_ngroupid"></a><a name="m_ngroupid"></a>C애니메이션 그룹::m_nGroupID

애니메이션 그룹의 고유 식별자입니다.

```
UINT32 m_nGroupID;
```

## <a name="canimationgroupm_pparentcontroller"></a><a name="m_pparentcontroller"></a>C애니메이션 그룹::m_pParentController

이 그룹에 속한 애니메이션 컨트롤러에 대한 포인터입니다.

```
CAnimationController* m_pParentController;
```

## <a name="canimationgroupm_pstoryboard"></a><a name="m_pstoryboard"></a>C애니메이션 그룹::m_pStoryboard

애니메이션 스토리보드를 가리킵니다. 이 포인터는 Animate에 호출한 후에만 유효합니다.

```
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;
```

## <a name="canimationgroupremovekeyframes"></a><a name="removekeyframes"></a>C애니메이션 그룹::제거키프레임

애니메이션 그룹에 속한 모든 키프레임을 제거하고 선택적으로 삭제합니다.

```cpp
void RemoveKeyframes();
```

### <a name="remarks"></a>설명

m_bAutodestroyKeyframes 멤버가 TRUE이면 키프레임이 제거되고 소멸되고 그렇지 않으면 키프레임이 내부 키프레임 목록에서 제거됩니다.

## <a name="canimationgroupremovetransitions"></a><a name="removetransitions"></a>C애니메이션 그룹::제거전환

애니메이션 그룹에 속한 애니메이션 개체에서 전환을 제거합니다.

```cpp
void RemoveTransitions();
```

### <a name="remarks"></a>설명

m_bAutoclearTransitions 플래그가 TRUE로 설정된 경우 이 메서드는 그룹에 속한 모든 애니메이션 개체를 반복하고 CAnimationObject::ClearTransitions(FALSE)를 호출합니다.

## <a name="canimationgroupschedule"></a><a name="schedule"></a>C애니메이션 그룹::일정

지정된 시간에 애니메이션을 예약합니다.

```
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```

### <a name="parameters"></a>매개 변수

*p타이머*<br/>
애니메이션 타이머에 대한 포인터입니다.

*time*<br/>
애니메이션을 예약할 시간을 지정합니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE입니다. 메서드가 실패하거나 animate가 호출되지 않은 경우 false는 false로 설정된 bScheduleNow로 설정됩니다.

### <a name="remarks"></a>설명

지정된 시간에 애니메이션을 예약하려면 이 함수를 호출합니다. 먼저 false로 설정된 bScheduleNow를 사용하여 애니메이션을 호출해야 합니다.

## <a name="canimationgroupsetautodestroytransitions"></a><a name="setautodestroytransitions"></a>C애니메이션 그룹::세트오토파괴전환

그룹에 속한 모든 애니메이션 오브젝트가 자동으로 전환을 삭제하도록 지시합니다.

```cpp
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*b오토파괴*<br/>
전환을 삭제하는 방법을 지정합니다.

### <a name="remarks"></a>설명

스택에 전환을 할당하는 경우에만 이 값을 FALSE로 설정합니다. 기본값은 TRUE이므로 새 연산자 new를 사용하여 전환 개체를 할당하는 것이 좋습니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
