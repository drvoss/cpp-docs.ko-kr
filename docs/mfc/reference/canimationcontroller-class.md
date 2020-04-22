---
title: CAnimationController 클래스
ms.date: 03/27/2019
f1_keywords:
- CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::AddAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::AddKeyframeToGroup
- AFXANIMATIONCONTROLLER/CAnimationController::AnimateGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CleanUpGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CreateKeyframe
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationManagerEvent
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnablePriorityComparisonHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnableStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::GetKeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionLibrary
- AFXANIMATIONCONTROLLER/CAnimationController::IsAnimationInProgress
- AFXANIMATIONCONTROLLER/CAnimationController::IsValid
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnBeforeAnimationStart
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCancel
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCompress
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityConclude
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityTrim
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAllAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationController::ScheduleGroup
- AFXANIMATIONCONTROLLER/CAnimationController::SetRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::UpdateAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::OnAfterSchedule
- AFXANIMATIONCONTROLLER/CAnimationController::gkeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::m_bIsValid
- AFXANIMATIONCONTROLLER/CAnimationController::m_lstAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::m_pRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionLibrary
helpviewer_keywords:
- CAnimationController [MFC], CAnimationController
- CAnimationController [MFC], AddAnimationObject
- CAnimationController [MFC], AddKeyframeToGroup
- CAnimationController [MFC], AnimateGroup
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], CreateKeyframe
- CAnimationController [MFC], EnableAnimationManagerEvent
- CAnimationController [MFC], EnableAnimationTimerEventHandler
- CAnimationController [MFC], EnablePriorityComparisonHandler
- CAnimationController [MFC], EnableStoryboardEventHandler
- CAnimationController [MFC], FindAnimationGroup
- CAnimationController [MFC], FindAnimationObject
- CAnimationController [MFC], GetKeyframeStoryboardStart
- CAnimationController [MFC], GetUIAnimationManager
- CAnimationController [MFC], GetUIAnimationTimer
- CAnimationController [MFC], GetUITransitionFactory
- CAnimationController [MFC], GetUITransitionLibrary
- CAnimationController [MFC], IsAnimationInProgress
- CAnimationController [MFC], IsValid
- CAnimationController [MFC], OnAnimationIntegerValueChanged
- CAnimationController [MFC], OnAnimationManagerStatusChanged
- CAnimationController [MFC], OnAnimationTimerPostUpdate
- CAnimationController [MFC], OnAnimationTimerPreUpdate
- CAnimationController [MFC], OnAnimationTimerRenderingTooSlow
- CAnimationController [MFC], OnAnimationValueChanged
- CAnimationController [MFC], OnBeforeAnimationStart
- CAnimationController [MFC], OnHasPriorityCancel
- CAnimationController [MFC], OnHasPriorityCompress
- CAnimationController [MFC], OnHasPriorityConclude
- CAnimationController [MFC], OnHasPriorityTrim
- CAnimationController [MFC], OnStoryboardStatusChanged
- CAnimationController [MFC], OnStoryboardUpdated
- CAnimationController [MFC], RemoveAllAnimationGroups
- CAnimationController [MFC], RemoveAnimationGroup
- CAnimationController [MFC], RemoveAnimationObject
- CAnimationController [MFC], RemoveTransitions
- CAnimationController [MFC], ScheduleGroup
- CAnimationController [MFC], SetRelatedWnd
- CAnimationController [MFC], UpdateAnimationManager
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], OnAfterSchedule
- CAnimationController [MFC], gkeyframeStoryboardStart
- CAnimationController [MFC], m_bIsValid
- CAnimationController [MFC], m_lstAnimationGroups
- CAnimationController [MFC], m_pAnimationManager
- CAnimationController [MFC], m_pAnimationTimer
- CAnimationController [MFC], m_pRelatedWnd
- CAnimationController [MFC], m_pTransitionFactory
- CAnimationController [MFC], m_pTransitionLibrary
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
ms.openlocfilehash: 489e931c4063e7bf06ace1cb130b9891253c94d4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750182"
---
# <a name="canimationcontroller-class"></a>CAnimationController 클래스

애니메이션을 만들고 관리하기 위한 중앙 인터페이스를 제공하는 애니메이션 컨트롤러를 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationController : public CObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C애니메이션 컨트롤러::C애니메이션 컨트롤러](#canimationcontroller)|애니메이션 컨트롤러를 생성합니다.|
|[C애니메이션 컨트롤러::~C애니메이션 컨트롤러](#_dtorcanimationcontroller)|소멸자입니다. 애니메이션 컨트롤러 개체가 소멸될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션 컨트롤러::애니메이션 개체 추가](#addanimationobject)|애니메이션 컨트롤러에 속한 그룹에 애니메이션 개체를 추가합니다.|
|[C애니메이션 컨트롤러::추가키프레임토그룹](#addkeyframetogroup)|그룹에 키프레임을 추가합니다.|
|[C애니메이션 컨트롤러::애니메이션 그룹](#animategroup)|애니메이션을 실행할 그룹을 준비하고 선택적으로 예약합니다.|
|[C애니메이션 컨트롤러::정리 그룹](#cleanupgroup)|오버로드되었습니다. 애니메이션이 예약되었을 때 그룹을 정리하기 위해 프레임워크에서 호출합니다.|
|[CAnimationController::CreateKeyframe](#createkeyframe)|오버로드되었습니다. 전환을 사용하는 키 프레임을 만들어 지정된 그룹에 추가합니다.|
|[C애니메이션 컨트롤러::인에이블 애니메이션 관리자 이벤트](#enableanimationmanagerevent)|애니메이션 관리자의 상태가 변경될 때 호출할 처리기를 설정하거나 해제합니다.|
|[C애니메이션 컨트롤러::인에이블애니메이션타이머이벤트핸들러](#enableanimationtimereventhandler)|타이밍 이벤트에 대한 처리기를 설정하거나 해제하고 타이밍 업데이트를 위한 처리기를 해제합니다.|
|[C애니메이션 컨트롤러::인에이블 우선 순위비교 처리기](#enableprioritycomparisonhandler)|예약된 스토리보드를 취소, 체결, 트리밍 또는 압축할 수 있는지 여부를 결정하기 위해 우선 순위 비교 처리기를 설정하거나 해제합니다.|
|[C애니메이션 컨트롤러::인에이블스토리보드이벤트핸들러](#enablestoryboardeventhandler)|스토리보드 상태 및 업데이트 이벤트에 대한 처리기를 설정하거나 해제합니다.|
|[C애니메이션 컨트롤러::찾기 애니메이션 그룹](#findanimationgroup)|오버로드되었습니다. 스토리보드를 통해 애니메이션 그룹을 찾습니다.|
|[C애니메이션 컨트롤러::찾기 애니메이션 오브젝트](#findanimationobject)|지정된 애니메이션 변수를 포함하는 애니메이션 개체를 찾습니다.|
|[C애니메이션 컨트롤러::겟키프레임스토리보드스타트](#getkeyframestoryboardstart)|스토리보드의 시작을 식별하는 키프레임을 반환합니다.|
|[C애니메이션 컨트롤러::GetUI애니메이션관리자](#getuianimationmanager)|캡슐화된 IUIAnimationManager 개체에 대한 액세스를 제공합니다.|
|[C애니메이션 컨트롤러::GetUI애니메이션타이머](#getuianimationtimer)|캡슐화된 IUIAnimationTimer 개체에 대한 액세스를 제공합니다.|
|[C애니메이션 컨트롤러::GetUITransition공장](#getuitransitionfactory)|전환 라이브러리 생성에 실패한 경우 IUIAnimationTransitionFactory 인터페이스 또는 NULL에 대한 포인터입니다.|
|[C애니메이션 컨트롤러::GetUI전환 라이브러리](#getuitransitionlibrary)|캡슐화된 IUIAnimationTransitionLibrary 개체에 대한 액세스를 제공합니다.|
|[C애니메이션 컨트롤러::IsANIMATION진행](#isanimationinprogress)|한 그룹이 애니메이션을 재생하고 있는지 여부를 알려줍니다.|
|[C애니메이션 컨트롤러::유효하지 않음](#isvalid)|애니메이션 컨트롤러가 유효한지 여부를 알려줍니다.|
|[C애니메이션 컨트롤러::온애니메이션인테이거밸류변경](#onanimationintegervaluechanged)|애니메이션 변수의 정수 값이 변경된 경우 프레임워크에서 호출됩니다.|
|[C애니메이션 컨트롤러::온애니메이션 관리자 상태 변경](#onanimationmanagerstatuschanged)|애니메이션 관리자에서 StatusChanged 이벤트에 대한 응답으로 프레임워크에서 호출합니다.|
|[C애니메이션 컨트롤러::온애니메이션타이머포스트업데이트](#onanimationtimerpostupdate)|애니메이션 업데이트가 완료된 후 프레임워크에서 호출됩니다.|
|[C애니메이션 컨트롤러::온애니메이션타이머사전업데이트](#onanimationtimerpreupdate)|애니메이션 업데이트가 시작되기 전에 프레임워크에서 호출됩니다.|
|[C애니메이션 컨트롤러::온애니메이션타이머렌더링투슬로우](#onanimationtimerrenderingtooslow)|애니메이션의 렌더링 프레임 속도가 최소 바람직한 프레임 속도보다 낮을 때 프레임워크에서 호출됩니다.|
|[C애니메이션 컨트롤러::온애니메이션값 변경](#onanimationvaluechanged)|애니메이션 변수의 값이 변경된 경우 프레임워크에서 호출합니다.|
|[C애니메이션 컨트롤러::온온애니메이션스타트](#onbeforeanimationstart)|애니메이션이 예약되기 바로 전에 프레임워크에서 호출됩니다.|
|[C애니메이션 컨트롤러::온하스우선취소](#onhasprioritycancel)|일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.|
|[C애니메이션 컨트롤러::온하스우선 순위 압축](#onhasprioritycompress)|일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.|
|[C애니메이션 컨트롤러::온하스우선순위체결](#onhaspriorityconclude)|일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.|
|[C애니메이션 컨트롤러::온하스우선순위트림](#onhasprioritytrim)|일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.|
|[C애니메이션 컨트롤러::온스토리보드상태 변경](#onstoryboardstatuschanged)|스토리보드 상태가 변경되면 프레임워크에서 호출됩니다.|
|[C애니메이션 컨트롤러::온스토리보드 업데이트](#onstoryboardupdated)|스토리보드가 업데이트되면 프레임워크에서 호출됩니다.|
|[C애니메이션 컨트롤러::리모크모든애니메이션 그룹](#removeallanimationgroups)|애니메이션 컨트롤러에서 모든 애니메이션 그룹을 제거합니다.|
|[C애니메이션 컨트롤러::애니메이션 그룹 제거](#removeanimationgroup)|애니메이션 컨트롤러에서 지정된 ID가 있는 애니메이션 그룹을 제거합니다.|
|[C애니메이션 컨트롤러::애니메이션 오브젝트 제거](#removeanimationobject)|애니메이션 컨트롤러에서 애니메이션 개체를 제거합니다.|
|[C애니메이션 컨트롤러::제거전환](#removetransitions)|지정된 그룹에 속한 애니메이션 개체에서 전환을 제거합니다.|
|[C애니메이션 컨트롤러::일정 그룹](#schedulegroup)|애니메이션을 예약합니다.|
|[C애니메이션 컨트롤러::설정 관련 Wnd](#setrelatedwnd)|애니메이션 컨트롤러와 창 간의 관계를 설정합니다.|
|[C애니메이션 컨트롤러::업데이트 애니메이션 관리자](#updateanimationmanager)|애니메이션 관리자가 모든 애니메이션 변수의 값을 업데이트하도록 지시합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션 컨트롤러::정리 그룹](#cleanupgroup)|오버로드되었습니다. 그룹을 정리하는 도우미입니다.|
|[C애니메이션 컨트롤러::온애프터스케줄](#onafterschedule)|지정된 그룹에 대한 애니메이션이 방금 예약된 경우 프레임워크에서 호출합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C애니메이션 컨트롤러::gkeyframe스토리보드시작](#g_keyframestoryboardstart)|스토리보드의 시작을 나타내는 키프레임입니다.|
|[C애니메이션 컨트롤러::m_bIsValid](#m_bisvalid)|애니메이션 컨트롤러가 유효한지 여부를 지정합니다. 현재 OS에서 Windows 애니메이션 API를 지원하지 않는 경우 이 멤버는 FALSE로 설정됩니다.|
|[C애니메이션 컨트롤러:m_lstAnimationGroups](#m_lstanimationgroups)|이 애니메이션 컨트롤러에 속하는 애니메이션 그룹 목록입니다.|
|[C애니메이션 컨트롤러::m_pAnimationManager](#m_panimationmanager)|애니메이션 관리자 COM 개체에 대한 포인터를 저장합니다.|
|[C애니메이션 컨트롤러::m_pAnimationTimer](#m_panimationtimer)|애니메이션 타이머 COM 개체에 대한 포인터를 저장합니다.|
|[C애니메이션 컨트롤러::m_pRelatedWnd](#m_prelatedwnd)|애니메이션 관리자의 상태가 변경되거나 업데이트 후 이벤트가 발생했을 때 자동으로 다시 그릴 수 있는 관련 CWnd 개체에 대한 포인터입니다. NULL일 수 있습니다.|
|[C애니메이션 컨트롤러:m_pTransitionFactory](#m_ptransitionfactory)|전환 팩터리 COM 개체에 대한 포인터를 저장합니다.|
|[C애니메이션 컨트롤러:m_pTransitionLibrary](#m_ptransitionlibrary)|전환 라이브러리 COM 개체에 대한 포인터를 저장합니다.|

## <a name="remarks"></a>설명

CAnimationController 클래스는 애니메이션을 관리하는 키 클래스입니다. 응용 프로그램에서 하나 이상의 애니메이션 컨트롤러 인스턴스를 만들 수 있으며, 선택적으로 CAnimationController:SetRelatedWnd를 사용하여 애니메이션 컨트롤러의 인스턴스를 CWnd 개체에 연결할 수 있습니다. 이 연결은 애니메이션 관리자 상태가 변경되었거나 애니메이션 타이머가 업데이트되면 관련 창에 WM_PAINT 메시지를 자동으로 보내야 합니다. 이 관계를 활성화하지 않으면 애니메이션을 수동으로 표시하는 창을 다시 그려야 합니다. 이를 위해 CAnimationController에서 클래스를 파생 하 고 OnAnimationManagerStatus변경 및/또는 OnAnimationTimerPostUpdate를 재정의 하 고 필요한 경우 하나 이상의 창을 무효화할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationController`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationcontrollercanimationcontroller"></a><a name="_dtorcanimationcontroller"></a>C애니메이션 컨트롤러::~C애니메이션 컨트롤러

소멸자입니다. 애니메이션 컨트롤러 개체가 소멸될 때 호출됩니다.

```
virtual ~CAnimationController(void);
```

## <a name="canimationcontrolleraddanimationobject"></a><a name="addanimationobject"></a>C애니메이션 컨트롤러::애니메이션 개체 추가

애니메이션 컨트롤러에 속한 그룹에 애니메이션 개체를 추가합니다.

```
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```

### <a name="parameters"></a>매개 변수

*pObject*<br/>
애니메이션 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 pObject가 추가된 기존 또는 새 애니메이션 그룹에 대한 포인터입니다. 다른 애니메이션 컨트롤러에 속한 그룹에 pObject가 이미 추가된 경우 NULL입니다.

### <a name="remarks"></a>설명

애니메이션 컨트롤러에 애니메이션 개체를 추가 하려면이 메서드를 호출 합니다. 개체의 GroupID에 따라 개체가 그룹에 추가됩니다(CAnimationBaseObject:SetID 참조). 애니메이션 컨트롤러는 지정된 GroupID와 함께 추가되는 첫 번째 개체인 경우 새 그룹을 만듭니다. 애니메이션 오브젝트는 하나의 애니메이션 컨트롤러에만 추가할 수 있습니다. 다른 컨트롤러에 개체를 추가해야 하는 경우 먼저 RemoveAnimationObject를 호출합니다. 그룹에 이미 추가된 개체에 대해 SetID를 새 GroupID로 호출하면 개체가 이전 그룹에서 제거되고 지정된 ID가 있는 다른 그룹에 추가됩니다.

## <a name="canimationcontrolleraddkeyframetogroup"></a><a name="addkeyframetogroup"></a>C애니메이션 컨트롤러::추가키프레임토그룹

그룹에 키프레임을 추가합니다.

```
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe);
```

### <a name="parameters"></a>매개 변수

*n그룹 ID*<br/>
그룹 ID를 지정합니다.

*pKeyframe*<br/>
키프레임에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 함수가 성공하면 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

일반적으로 이 메서드를 호출할 필요가 없습니다.

## <a name="canimationcontrolleranimategroup"></a><a name="animategroup"></a>C애니메이션 컨트롤러::애니메이션 그룹

애니메이션을 실행할 그룹을 준비하고 선택적으로 예약합니다.

```
BOOL AnimateGroup(
    UINT32 nGroupID,
    BOOL bScheduleNow = TRUE);
```

### <a name="parameters"></a>매개 변수

*n그룹 ID*<br/>
그룹 ID를 지정합니다.

*b스케줄지금*<br/>
애니메이션을 바로 실행할지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 애니메이션이 예약되고 실행된 경우

### <a name="remarks"></a>설명

이 메서드는 스토리보드를 만드는 실제 작업, 애니메이션 변수 추가, 전환 적용 및 키프레임 설정작업을 수행합니다. bScheduleNow를 FALSE로 설정하면 일정을 지연할 수 있습니다. 이 경우 지정된 그룹에는 애니메이션에 대해 설정된 스토리보드가 유지됩니다. 이 시점에서 스토리보드 및 애니메이션 변수에 대한 이벤트를 설정할 수 있습니다. 실제로 애니메이션 호출을 실행 해야 하는 경우 CAnimationController::ScheduleGroup.

## <a name="canimationcontrollercanimationcontroller"></a><a name="canimationcontroller"></a>C애니메이션 컨트롤러::C애니메이션 컨트롤러

애니메이션 컨트롤러를 생성합니다.

```
CAnimationController(void);
```

## <a name="canimationcontrollercleanupgroup"></a><a name="cleanupgroup"></a>C애니메이션 컨트롤러::정리 그룹

애니메이션이 예약되었을 때 그룹을 정리하기 위해 프레임워크에서 호출합니다.

```cpp
void CleanUpGroup(UINT32 nGroupID);
void CleanUpGroup(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>매개 변수

*n그룹 ID*<br/>
그룹 ID를 지정합니다.

*pGroup*<br/>
정리할 애니메이션 그룹에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 애니메이션을 예약한 후 관련이 없기 때문에 지정된 그룹에서 모든 전환 및 키프레임을 제거합니다.

## <a name="canimationcontrollercreatekeyframe"></a><a name="createkeyframe"></a>C애니메이션 컨트롤러::만들기키프레임

전환을 사용하는 키 프레임을 만들어 지정된 그룹에 추가합니다.

```
CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,
    CBaseTransition* pTransition);

CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>매개 변수

*n그룹 ID*<br/>
키 프레임을 만들 그룹 ID를 지정합니다.

*p전환*<br/>
전환에 대한 포인터입니다. 이 전환 후 스토리보드에 키 프레임이 삽입됩니다.

*pKeyframe*<br/>
이 키 프레임의 기본 키 프레임에 대한 포인터입니다.

*offset*<br/>
pKeyframe에 지정된 기본 키 프레임에서의 오프셋(초)입니다.

### <a name="return-value"></a>Return Value

함수가 성공할 경우 새로 생성되는 키 프레임에 대한 포인터입니다.

### <a name="remarks"></a>설명

반환된 포인터를 저장하고 새로 만든 키 프레임을 다른 키 프레임의 기반으로 사용할 수 있습니다(두 번째 오버로드 참조). 키 프레임에서 전환을 시작할 수 있습니다(CBaseTransition::SetKeyframes 참조). 이런 방법으로 만든 키 프레임은 애니메이션 그룹에 의해 자동으로 삭제되기 때문에 삭제할 필요가 없습니다. 다른 키 프레임 및 전환을 기반으로 하여 키 프레임을 만들 때는 순환 참조가 발생하지 않도록 주의하세요.

## <a name="canimationcontrollerenableanimationmanagerevent"></a><a name="enableanimationmanagerevent"></a>C애니메이션 컨트롤러::인에이블 애니메이션 관리자 이벤트

애니메이션 관리자의 상태가 변경될 때 호출할 처리기를 설정하거나 해제합니다.

```
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
처리기를 설정하거나 해제할지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

처리기가 성공적으로 설정또는 해제된 경우 TRUE입니다.

### <a name="remarks"></a>설명

처리기가 설정되면(사용) Windows 애니메이션호출 OnAnimationManagerStatus애니메이션 관리자의 상태가 변경될 때 변경됨.

## <a name="canimationcontrollerenableanimationtimereventhandler"></a><a name="enableanimationtimereventhandler"></a>C애니메이션 컨트롤러::인에이블애니메이션타이머이벤트핸들러

타이밍 이벤트에 대한 처리기를 설정하거나 해제하고 타이밍 업데이트를 위한 처리기를 해제합니다.

```
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
처리기를 설정하거나 해제할지 여부를 지정합니다.

*유휴 행동*<br/>
타이머 업데이트 처리기에 대한 유휴 동작을 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 처리기가 성공적으로 설정되거나 해제된 경우 FALSE 이 메서드가 처리기를 먼저 해제하지 않고 두 번째로 호출되는 경우 또는 다른 오류가 발생하는 경우.

### <a name="remarks"></a>설명

처리기가 설정되면 (사용) 윈도우 애니메이션 API는 OnAnimationTimerPreUpdate, OnAnimationTimerPostUpdate, OnRenderingTooSlow 메서드를 호출합니다. Windows 애니메이션 API 업데이트 스토리보드를 허용하려면 애니메이션 타이머를 사용하도록 설정해야 합니다. 그렇지 않으면 모든 애니메이션 변수의 값을 업데이트하도록 애니메이션 관리자를 지시하기 위해 CAnimationController::UpdateAnimationManager를 호출해야 합니다.

## <a name="canimationcontrollerenableprioritycomparisonhandler"></a><a name="enableprioritycomparisonhandler"></a>C애니메이션 컨트롤러::인에이블 우선 순위비교 처리기

예약된 스토리보드를 취소, 체결, 트리밍 또는 압축할 수 있는지 여부를 결정하기 위해 우선 순위 비교 처리기를 설정하거나 해제합니다.

```
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```

### <a name="parameters"></a>매개 변수

*dwHandlerType*<br/>
UI_ANIMATION_PHT_ 플래그(비고 참조)의 조합으로, 어떤 처리기를 설정하거나 해제할지 지정합니다.

### <a name="return-value"></a>Return Value

처리기가 성공적으로 설정또는 해제된 경우 TRUE입니다.

### <a name="remarks"></a>설명

처리기가 설정되면(사용) Windows 애니메이션은 dwHandlerType: OnHasPriorityCancel, OnHasPriority절, OnHasPriorityTrim, OnHasPriorityTrim, OnHasPriority압축에 따라 다음과 같은 가상 메서드를 호출합니다. dwHandler는 다음 플래그의 조합일 수 있습니다: UI_ANIMATION_PHT_NONE - 모든 처리기 UI_ANIMATION_PHT_CANCEL 해제 - 설정 비교 처리기 UI_ANIMATION_PHT_CONCLUDE - set 결론 비교 처리기 UI_ANIMATION_PHT_COMPRESS - 설정 비교 처리기 UI_ANIMATION_PHT_TRIM - 설정 트림 비교 처리기 UI_ANIMATION_PHT_CANCEL_REMOVE - 비교 처리기 UI_ANIMATION_PHT_CONCLUDE_REMOVE 제거 - 결론 비교 처리기 UI_ANIMATION_PHT_COMPRESS_REMOVE 제거 - 압축 비교 처리기 UI_ANIMATION_PHT_TRIM_REMOVE 제거 - 트림 비교 처리기 제거

## <a name="canimationcontrollerenablestoryboardeventhandler"></a><a name="enablestoryboardeventhandler"></a>C애니메이션 컨트롤러::인에이블스토리보드이벤트핸들러

스토리보드 상태 및 업데이트 이벤트에 대한 처리기를 설정하거나 해제합니다.

```
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*n그룹 ID*<br/>
그룹 ID를 지정합니다.

*bEnable*<br/>
처리기를 설정하거나 해제할지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

처리기가 성공적으로 설정또는 해제된 경우 TRUE입니다. FALSE 지정된 애니메이션 그룹을 찾았거나 지정된 그룹에 대한 애니메이션이 시작되지 않았고 내부 스토리보드가 NULL인 경우 FALSE입니다.

### <a name="remarks"></a>설명

처리기가 설정되면(사용) Windows 애니메이션 API는 OnStoryboardStatus변경 및 온스토리보드업데이트된 가상 메서드를 호출합니다. CAnimationController::Animate가 캡슐화된 IUIAnimationStoryboard 개체를 생성하기 때문에 지정된 애니메이션 그룹에 대해 호출된 후 처리기를 설정해야 합니다.

## <a name="canimationcontrollerfindanimationgroup"></a><a name="findanimationgroup"></a>C애니메이션 컨트롤러::찾기 애니메이션 그룹

그룹 ID로 애니메이션 그룹을 찾습니다.

```
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>매개 변수

*n그룹 ID*<br/>
GroupID를 지정합니다.

*p스토리보드*<br/>
스토리보드에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

지정된 ID가 있는 그룹을 찾을 수 없는 경우 애니메이션 그룹 또는 NULL에 대한 포인터입니다.

### <a name="remarks"></a>설명

런타임시 애니메이션 그룹을 찾으려면 이 메서드를 사용합니다. 특정 GroupID가 있는 첫 번째 애니메이션 오브젝트가 애니메이션 컨트롤러에 추가될 때 그룹이 만들어지고 애니메이션 그룹의 내부 목록에 추가됩니다.

## <a name="canimationcontrollerfindanimationobject"></a><a name="findanimationobject"></a>C애니메이션 컨트롤러::찾기 애니메이션 오브젝트

지정된 애니메이션 변수를 포함하는 애니메이션 개체를 찾습니다.

```
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,
    CAnimationBaseObject** ppObject,
    CAnimationGroup** ppGroup);
```

### <a name="parameters"></a>매개 변수

*p변수*<br/>
애니메이션 변수에 대한 포인터입니다.

*ppObject*<br/>
출력 애니메이션 개체 또는 NULL에 대한 포인터를 포함합니다.

*pp그룹*<br/>
출력 애니메이션 개체 또는 NULL을 보유 하는 애니메이션 그룹에 대 한 포인터를 포함 합니다.

### <a name="return-value"></a>Return Value

TRUE 개체가 발견되면 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

들어오는 애니메이션 변수에서 애니메이션 개체를 찾아야 하는 경우 이벤트 처리기에서 호출됩니다.

## <a name="canimationcontrollergkeyframestoryboardstart"></a><a name="g_keyframestoryboardstart"></a>C애니메이션 컨트롤러::gkeyframe스토리보드시작

스토리보드의 시작을 나타내는 키프레임입니다.

```
static CBaseKeyFrame gkeyframeStoryboardStart;
```

## <a name="canimationcontrollergetkeyframestoryboardstart"></a><a name="getkeyframestoryboardstart"></a>C애니메이션 컨트롤러::겟키프레임스토리보드스타트

스토리보드의 시작을 식별하는 키프레임을 반환합니다.

```
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```

### <a name="return-value"></a>Return Value

스토리보드의 시작을 식별하는 기본 키프레임에 대한 포인터입니다.

### <a name="remarks"></a>설명

스토리보드가 시작되는 순간에 다른 키프레임이나 전환을 기반으로 하려면 이 키프레임을 가져옵니다.

## <a name="canimationcontrollergetuianimationmanager"></a><a name="getuianimationmanager"></a>C애니메이션 컨트롤러::GetUI애니메이션관리자

캡슐화된 IUIAnimationManager 개체에 대한 액세스를 제공합니다.

```
IUIAnimationManager* GetUIAnimationManager();
```

### <a name="return-value"></a>Return Value

애니메이션 관리자 생성에 실패한 경우 IUIAnimationManager 인터페이스 또는 NULL에 대한 포인터입니다.

### <a name="remarks"></a>설명

현재 OS가 Windows 애니메이션 API를 지원하지 않는 경우 이 메서드는 NULL을 반환하고 그 후 CAnimationController::IsValid 반환 FALSE에 대한 모든 후속 호출을 반환합니다. 애니메이션 컨트롤러에 의해 래핑되지 않은 인터페이스 메서드를 호출하려면 IUIAnimationManager에 액세스해야 할 수 있습니다.

## <a name="canimationcontrollergetuianimationtimer"></a><a name="getuianimationtimer"></a>C애니메이션 컨트롤러::GetUI애니메이션타이머

캡슐화된 IUIAnimationTimer 개체에 대한 액세스를 제공합니다.

```
IUIAnimationTimer* GetUIAnimationTimer();
```

### <a name="return-value"></a>Return Value

애니메이션 타이머 생성에 실패한 경우 IUIAnimationTimer 인터페이스 또는 NULL에 대한 포인터입니다.

### <a name="remarks"></a>설명

현재 OS가 Windows 애니메이션 API를 지원하지 않는 경우 이 메서드는 NULL을 반환하고 그 후 CAnimationController::IsValid 반환 FALSE에 대한 모든 후속 호출을 반환합니다.

## <a name="canimationcontrollergetuitransitionfactory"></a><a name="getuitransitionfactory"></a>C애니메이션 컨트롤러::GetUITransition공장

전환 라이브러리 생성에 실패한 경우 IUIAnimationTransitionFactory 인터페이스 또는 NULL에 대한 포인터입니다.

```
IUIAnimationTransitionFactory* GetUITransitionFactory();
```

### <a name="return-value"></a>Return Value

IUIAnimation전환팩토리 또는 NULL에 대한 포인터로 전환 팩토리 생성에 실패한 경우.

### <a name="remarks"></a>설명

현재 OS가 Windows 애니메이션 API를 지원하지 않는 경우 이 메서드는 NULL을 반환하고 그 후 CAnimationController::IsValid 반환 FALSE에 대한 모든 후속 호출을 반환합니다.

## <a name="canimationcontrollergetuitransitionlibrary"></a><a name="getuitransitionlibrary"></a>C애니메이션 컨트롤러::GetUI전환 라이브러리

캡슐화된 IUIAnimationTransitionLibrary 개체에 대한 액세스를 제공합니다.

```
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```

### <a name="return-value"></a>Return Value

전환 라이브러리 생성에 실패한 경우 IUIAnimationTransitionLibrary 인터페이스 또는 NULL에 대한 포인터입니다.

### <a name="remarks"></a>설명

현재 OS가 Windows 애니메이션 API를 지원하지 않는 경우 이 메서드는 NULL을 반환하고 그 후 CAnimationController::IsValid 반환 FALSE에 대한 모든 후속 호출을 반환합니다.

## <a name="canimationcontrollerisanimationinprogress"></a><a name="isanimationinprogress"></a>C애니메이션 컨트롤러::IsANIMATION진행

한 그룹이 애니메이션을 재생하고 있는지 여부를 알려줍니다.

```
virtual BOOL IsAnimationInProgress();
```

### <a name="return-value"></a>Return Value

TRUE 이 애니메이션 컨트롤러에 대해 진행 중인 애니메이션이 있는 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

애니메이션 관리자의 상태를 확인하고 상태가 UI_ANIMATION_MANAGER_BUSY 경우 TRUE를 반환합니다.

## <a name="canimationcontrollerisvalid"></a><a name="isvalid"></a>C애니메이션 컨트롤러::유효하지 않음

애니메이션 컨트롤러가 유효한지 여부를 알려줍니다.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Return Value

TRUE 애니메이션 컨트롤러가 유효한 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 현재 OS에서 Windows 애니메이션 API가 지원되지 않고 등록되지 않았기 때문에 애니메이션 관리자 생성에 실패한 경우에만 FALSE를 반환합니다. COM 라이브러리를 초기화한 후 GetUIAnimationManager를 호출하여 이 플래그를 설정해야 합니다.

## <a name="canimationcontrollerm_bisvalid"></a><a name="m_bisvalid"></a>C애니메이션 컨트롤러::m_bIsValid

애니메이션 컨트롤러가 유효한지 여부를 지정합니다. 현재 OS에서 Windows 애니메이션 API를 지원하지 않는 경우 이 멤버는 FALSE로 설정됩니다.

```
BOOL m_bIsValid;
```

## <a name="canimationcontrollerm_lstanimationgroups"></a><a name="m_lstanimationgroups"></a>C애니메이션 컨트롤러:m_lstAnimationGroups

이 애니메이션 컨트롤러에 속하는 애니메이션 그룹 목록입니다.

```
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;
```

## <a name="canimationcontrollerm_panimationmanager"></a><a name="m_panimationmanager"></a>C애니메이션 컨트롤러::m_pAnimationManager

애니메이션 관리자 COM 개체에 대한 포인터를 저장합니다.

```
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;
```

## <a name="canimationcontrollerm_panimationtimer"></a><a name="m_panimationtimer"></a>C애니메이션 컨트롤러::m_pAnimationTimer

애니메이션 타이머 COM 개체에 대한 포인터를 저장합니다.

```
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;
```

## <a name="canimationcontrollerm_prelatedwnd"></a><a name="m_prelatedwnd"></a>C애니메이션 컨트롤러::m_pRelatedWnd

애니메이션 관리자의 상태가 변경되거나 업데이트 후 이벤트가 발생했을 때 자동으로 다시 그릴 수 있는 관련 CWnd 개체에 대한 포인터입니다. NULL일 수 있습니다.

```
CWnd* m_pRelatedWnd;
```

## <a name="canimationcontrollerm_ptransitionfactory"></a><a name="m_ptransitionfactory"></a>C애니메이션 컨트롤러:m_pTransitionFactory

전환 팩터리 COM 개체에 대한 포인터를 저장합니다.

```
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;
```

## <a name="canimationcontrollerm_ptransitionlibrary"></a><a name="m_ptransitionlibrary"></a>C애니메이션 컨트롤러:m_pTransitionLibrary

전환 라이브러리 COM 개체에 대한 포인터를 저장합니다.

```
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;
```

## <a name="canimationcontrolleronafterschedule"></a><a name="onafterschedule"></a>C애니메이션 컨트롤러::온애프터스케줄

지정된 그룹에 대한 애니메이션이 방금 예약된 경우 프레임워크에서 호출합니다.

```
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
예약된 애니메이션 그룹에 대한 포인터입니다.

### <a name="remarks"></a>설명

기본 구현은 지정된 그룹에서 키프레임과 지정된 그룹에 속한 애니메이션 변수에서 전환을 제거합니다. 파생 클래스에서 재정의하여 애니메이션 일정에 따라 추가 작업을 수행할 수 있습니다.

## <a name="canimationcontrolleronanimationintegervaluechanged"></a><a name="onanimationintegervaluechanged"></a>C애니메이션 컨트롤러::온애니메이션인테이거밸류변경

애니메이션 변수의 정수 값이 변경된 경우 프레임워크에서 호출됩니다.

```
virtual void OnAnimationIntegerValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    INT32 newValue,
    INT32 prevValue);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
값이 변경된 애니메이션 개체를 보유하는 애니메이션 그룹에 대한 포인터입니다.

*pObject*<br/>
값이 변경된 애니메이션 변수를 포함하는 애니메이션 개체에 대한 포인터입니다.

*변수*<br/>
애니메이션 변수에 대한 포인터입니다.

*newValue*<br/>
새 값을 지정합니다.

*이전 값*<br/>
이전 값을 지정합니다.

### <a name="remarks"></a>설명

이 메서드는 EnableIntegerValueChangedEvent 특정 애니메이션 변수 또는 애니메이션 개체에 대 한 호출 된 애니메이션 변수 이벤트를 사용 하는 경우 호출 됩니다. 애플리케이션별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다.

## <a name="canimationcontrolleronanimationmanagerstatuschanged"></a><a name="onanimationmanagerstatuschanged"></a>C애니메이션 컨트롤러::온애니메이션 관리자 상태 변경

애니메이션 관리자에서 StatusChanged 이벤트에 대한 응답으로 프레임워크에서 호출합니다.

```
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>매개 변수

*new Status*<br/>
새 애니메이션 관리자 상태입니다.

*이전 상태*<br/>
이전 애니메이션 관리자 상태입니다.

### <a name="remarks"></a>설명

이 메서드는 EnableAnimationManagerEvent를 사용 하 고 애니메이션 관리자 이벤트를 사용 하는 경우 호출 됩니다. 애플리케이션별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다. 기본 구현은 SetRelatedWnd로 설정된 경우 관련 창을 업데이트합니다.

## <a name="canimationcontrolleronanimationtimerpostupdate"></a><a name="onanimationtimerpostupdate"></a>C애니메이션 컨트롤러::온애니메이션타이머포스트업데이트

애니메이션 업데이트가 완료된 후 프레임워크에서 호출됩니다.

```
virtual void OnAnimationTimerPostUpdate();
```

### <a name="remarks"></a>설명

이 메서드는 EnableAnimationTimerEventHandler를 사용 하 여 타이머 이벤트 처리기를 사용 하는 경우 호출 됩니다. 애플리케이션별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다.

## <a name="canimationcontrolleronanimationtimerpreupdate"></a><a name="onanimationtimerpreupdate"></a>C애니메이션 컨트롤러::온애니메이션타이머사전업데이트

애니메이션 업데이트가 시작되기 전에 프레임워크에서 호출됩니다.

```
virtual void OnAnimationTimerPreUpdate();
```

### <a name="remarks"></a>설명

이 메서드는 EnableAnimationTimerEventHandler를 사용 하 여 타이머 이벤트 처리기를 사용 하는 경우 호출 됩니다. 애플리케이션별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다.

## <a name="canimationcontrolleronanimationtimerrenderingtooslow"></a><a name="onanimationtimerrenderingtooslow"></a>C애니메이션 컨트롤러::온애니메이션타이머렌더링투슬로우

애니메이션의 렌더링 프레임 속도가 최소 바람직한 프레임 속도보다 낮을 때 프레임워크에서 호출됩니다.

```
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```

### <a name="parameters"></a>매개 변수

*Fps*<br/>
초당 프레임의 현재 프레임 속도입니다.

### <a name="remarks"></a>설명

이 메서드는 EnableAnimationTimerEventHandler를 사용 하 여 타이머 이벤트 처리기를 사용 하는 경우 호출 됩니다. 애플리케이션별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다. 최소 바람직한 프레임 속도는 IUIAnimationTimer::SetFrameRate임계값을 호출하여 지정됩니다.

## <a name="canimationcontrolleronanimationvaluechanged"></a><a name="onanimationvaluechanged"></a>C애니메이션 컨트롤러::온애니메이션값 변경

애니메이션 변수의 값이 변경된 경우 프레임워크에서 호출합니다.

```
virtual void OnAnimationValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    DOUBLE newValue,
    DOUBLE prevValue);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
값이 변경된 애니메이션 개체를 보유하는 애니메이션 그룹에 대한 포인터입니다.

*pObject*<br/>
값이 변경된 애니메이션 변수를 포함하는 애니메이션 개체에 대한 포인터입니다.

*변수*<br/>
애니메이션 변수에 대한 포인터입니다.

*newValue*<br/>
새 값을 지정합니다.

*이전 값*<br/>
이전 값을 지정합니다.

### <a name="remarks"></a>설명

이 메서드는 특정 애니메이션 변수 또는 애니메이션 개체에 대 한 호출 EnableValueChangedEvent애니메이션 변수 이벤트를 사용 하는 경우 호출 됩니다. 애플리케이션별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다.

## <a name="canimationcontrolleronbeforeanimationstart"></a><a name="onbeforeanimationstart"></a>C애니메이션 컨트롤러::온온애니메이션스타트

애니메이션이 예약되기 바로 전에 프레임워크에서 호출됩니다.

```
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
애니메이션이 시작하려고 하는 애니메이션 그룹에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 호출은 관련 CWnd로 라우팅되며 파생 클래스에서 재정의하여 지정된 그룹에 대해 애니메이션이 시작되기 전에 추가 작업을 수행할 수 있습니다.

## <a name="canimationcontrolleronhasprioritycancel"></a><a name="onhasprioritycancel"></a>C애니메이션 컨트롤러::온하스우선취소

일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.

```
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>매개 변수

*p그룹일정*<br/>
현재 예약된 스토리보드를 소유하고 있는 그룹입니다.

*p그룹신규*<br/>
pGroupScheduled에서 소유한 예약된 스토리보드와 충돌을 예약하고 있는 새 스토리보드를 소유하는 그룹입니다.

*우선 순위 효과*<br/>
pGroupScheduled에 높은 우선 순위가 있는 경우 pGroupNew에서 발생할 수 있는 효과입니다.

### <a name="return-value"></a>Return Value

pGroupNew에서 소유한 스토리보드가 우선인 경우 TRUE를 반환해야 합니다. pGroupScheduled에서 소유한 스토리보드가 우선인 경우 FALSE를 반환해야 합니다.

### <a name="remarks"></a>설명

이 메서드는 CAnimationController::EnablePriorityComparisonHandler를 사용하여 우선 순위 비교 이벤트를 활성화하고 UI_ANIMATION_PHT_CANCEL을 지정하는 경우 호출됩니다. 애플리케이션별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다. Windows 애니메이션 API 설명서를 읽고 충돌 관리에 대한 자세한 내용을 [참조하십시오.](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)

## <a name="canimationcontrolleronhasprioritycompress"></a><a name="onhasprioritycompress"></a>C애니메이션 컨트롤러::온하스우선 순위 압축

일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.

```
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>매개 변수

*p그룹일정*<br/>
현재 예약된 스토리보드를 소유하고 있는 그룹입니다.

*p그룹신규*<br/>
pGroupScheduled에서 소유한 예약된 스토리보드와 충돌을 예약하고 있는 새 스토리보드를 소유하는 그룹입니다.

*우선 순위 효과*<br/>
pGroupScheduled에 높은 우선 순위가 있는 경우 pGroupNew에서 발생할 수 있는 효과입니다.

### <a name="return-value"></a>Return Value

pGroupNew에서 소유한 스토리보드가 우선인 경우 TRUE를 반환해야 합니다. pGroupScheduled에서 소유한 스토리보드가 우선인 경우 FALSE를 반환해야 합니다.

### <a name="remarks"></a>설명

이 메서드는 CAnimationController::EnablePriorityComparisonHandler를 사용하여 우선 순위 비교 이벤트를 활성화하고 UI_ANIMATION_PHT_COMPRESS를 지정하는 경우 호출됩니다. 애플리케이션별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다. Windows 애니메이션 API 설명서를 읽고 충돌 관리에 대한 자세한 내용을 [참조하십시오.](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)

## <a name="canimationcontrolleronhaspriorityconclude"></a><a name="onhaspriorityconclude"></a>C애니메이션 컨트롤러::온하스우선순위체결

일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.

```
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>매개 변수

*p그룹일정*<br/>
현재 예약된 스토리보드를 소유하고 있는 그룹입니다.

*p그룹신규*<br/>
pGroupScheduled에서 소유한 예약된 스토리보드와 충돌을 예약하고 있는 새 스토리보드를 소유하는 그룹입니다.

*우선 순위 효과*<br/>
pGroupScheduled에 높은 우선 순위가 있는 경우 pGroupNew에서 발생할 수 있는 효과입니다.

### <a name="return-value"></a>Return Value

pGroupNew에서 소유한 스토리보드가 우선인 경우 TRUE를 반환해야 합니다. pGroupScheduled에서 소유한 스토리보드가 우선인 경우 FALSE를 반환해야 합니다.

### <a name="remarks"></a>설명

이 메서드는 CAnimationController::EnablePriorityComparisonHandler를 사용하여 우선 순위 비교 이벤트를 활성화하고 UI_ANIMATION_PHT_TRIM을 지정하는 경우 호출됩니다. 애플리케이션별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다. Windows 애니메이션 API 설명서를 읽고 충돌 관리에 대한 자세한 내용을 [참조하십시오.](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)

## <a name="canimationcontrolleronhasprioritytrim"></a><a name="onhasprioritytrim"></a>C애니메이션 컨트롤러::온하스우선순위트림

일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.

```
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>매개 변수

*p그룹일정*<br/>
현재 예약된 스토리보드를 소유하고 있는 그룹입니다.

*p그룹신규*<br/>
pGroupScheduled에서 소유한 예약된 스토리보드와 충돌을 예약하고 있는 새 스토리보드를 소유하는 그룹입니다.

*우선 순위 효과*<br/>
pGroupScheduled에 높은 우선 순위가 있는 경우 pGroupNew에서 발생할 수 있는 효과입니다.

### <a name="return-value"></a>Return Value

pGroupNew에서 소유한 스토리보드가 우선인 경우 TRUE를 반환해야 합니다. pGroupScheduled에서 소유한 스토리보드가 우선인 경우 FALSE를 반환해야 합니다.

### <a name="remarks"></a>설명

이 메서드는 CAnimationController::EnablePriorityComparisonHandler를 사용하여 우선 순위 비교 이벤트를 활성화하고 UI_ANIMATION_PHT_TRIM을 지정하는 경우 호출됩니다. 애플리케이션별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다. Windows 애니메이션 API 설명서를 읽고 충돌 관리에 대한 자세한 내용을 [참조하십시오.](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)

## <a name="canimationcontrolleronstoryboardstatuschanged"></a><a name="onstoryboardstatuschanged"></a>C애니메이션 컨트롤러::온스토리보드상태 변경

스토리보드 상태가 변경되면 프레임워크에서 호출됩니다.

```
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,
    UI_ANIMATION_STORYBOARD_STATUS newStatus,
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
상태가 변경된 스토리보드를 소유한 애니메이션 그룹에 대한 포인터입니다.

*new Status*<br/>
새 상태를 지정합니다.

*이전 상태*<br/>
이전 상태를 지정합니다.

### <a name="remarks"></a>설명

이 메서드는 CAnimationController::EnableStoryboardEvent를 사용 하 여 스토리 보드 이벤트를 사용 하는 경우 호출 됩니다. 애플리케이션별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다.

## <a name="canimationcontrolleronstoryboardupdated"></a><a name="onstoryboardupdated"></a>C애니메이션 컨트롤러::온스토리보드 업데이트

스토리보드가 업데이트되면 프레임워크에서 호출됩니다.

```
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
스토리보드를 소유한 그룹에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 CAnimationController::EnableStoryboardEvent를 사용 하 여 스토리 보드 이벤트를 사용 하는 경우 호출 됩니다. 애플리케이션별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다.

## <a name="canimationcontrollerremoveallanimationgroups"></a><a name="removeallanimationgroups"></a>C애니메이션 컨트롤러::리모크모든애니메이션 그룹

애니메이션 컨트롤러에서 모든 애니메이션 그룹을 제거합니다.

```cpp
void RemoveAllAnimationGroups();
```

### <a name="remarks"></a>설명

모든 그룹이 삭제되고 응용 프로그램 수준에 저장된 경우 포인터가 무효화되어야 합니다. 삭제되는 그룹에 대한 CAnimationGroup::m_bAutodestroyAnimationObjects TRUE인 경우 해당 그룹에 속한 모든 애니메이션 개체가 삭제됩니다. 그렇지 않으면 부모 애니메이션 컨트롤러에 대한 참조가 NULL로 설정되고 다른 컨트롤러에 추가할 수 있습니다.

## <a name="canimationcontrollerremoveanimationgroup"></a><a name="removeanimationgroup"></a>C애니메이션 컨트롤러::애니메이션 그룹 제거

애니메이션 컨트롤러에서 지정된 ID가 있는 애니메이션 그룹을 제거합니다.

```cpp
void RemoveAnimationGroup(UINT32 nGroupID);
```

### <a name="parameters"></a>매개 변수

*n그룹 ID*<br/>
애니메이션 그룹 ID를 지정합니다.

### <a name="remarks"></a>설명

이 메서드는 그룹 내부 목록에서 애니메이션 그룹을 제거 하 고 해당 애니메이션 그룹에 대 한 포인터를 저장 하는 경우 무효화 해야 합니다. CAnimationGroup::m_bAutodestroyAnimationObjects TRUE이면 해당 그룹에 속한 모든 애니메이션 개체가 삭제됩니다. 그렇지 않으면 부모 애니메이션 컨트롤러에 대한 참조가 NULL로 설정되고 다른 컨트롤러에 추가할 수 있습니다.

## <a name="canimationcontrollerremoveanimationobject"></a><a name="removeanimationobject"></a>C애니메이션 컨트롤러::애니메이션 오브젝트 제거

애니메이션 컨트롤러에서 애니메이션 개체를 제거합니다.

```cpp
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,
    BOOL bNoDelete = FALSE);
```

### <a name="parameters"></a>매개 변수

*pObject*<br/>
애니메이션 개체에 대한 포인터입니다.

*b삭제 안 해*<br/>
이 매개 변수가 TRUE이면 제거시 개체가 삭제되지 않습니다.

### <a name="remarks"></a>설명

애니메이션 컨트롤러 및 애니메이션 그룹에서 애니메이션 개체를 제거합니다. 특정 오브젝트를 더 이상 애니메이션하지 않아야 하거나 오브젝트를 다른 애니메이션 컨트롤러로 이동해야 하는 경우 이 함수를 호출합니다. 마지막 경우 bNoDelete는 TRUE여야 합니다.

## <a name="canimationcontrollerremovetransitions"></a><a name="removetransitions"></a>C애니메이션 컨트롤러::제거전환

지정된 그룹에 속한 애니메이션 개체에서 전환을 제거합니다.

```cpp
void RemoveTransitions(UINT32 nGroupID);
```

### <a name="parameters"></a>매개 변수

*n그룹 ID*<br/>
그룹 ID를 지정합니다.

### <a name="remarks"></a>설명

이 그룹은 애니메이션 개체를 반복하고 각 애니메이션 개체에 대해 ClearTransitions(FALSE)를 호출합니다. 이 메서드는 애니메이션이 예약된 후 프레임워크에서 호출됩니다.

## <a name="canimationcontrollerschedulegroup"></a><a name="schedulegroup"></a>C애니메이션 컨트롤러::일정 그룹

애니메이션을 예약합니다.

```
BOOL ScheduleGroup(
    UINT32 nGroupID,
    UI_ANIMATION_SECONDS time = 0.0);
```

### <a name="parameters"></a>매개 변수

*n그룹 ID*<br/>
예약할 애니메이션 그룹 ID를 지정합니다.

*time*<br/>
예약 시간을 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 애니메이션이 성공적으로 예약된 경우 False 스토리보드를 만들지 않았거나 다른 오류가 발생하는 경우 false입니다.

### <a name="remarks"></a>설명

매개 변수 bScheduleNow FALSE 이전 일정 그룹으로 설정 된 AnimateGroup을 호출 해야 합니다. IUIAnimationTimer::GetTime에서 얻은 원하는 애니메이션 시간을 지정할 수 있습니다. 시간 매개 변수가 0.0이면 애니메이션이 현재 시간으로 예약됩니다.

## <a name="canimationcontrollersetrelatedwnd"></a><a name="setrelatedwnd"></a>C애니메이션 컨트롤러::설정 관련 Wnd

애니메이션 컨트롤러와 창 간의 관계를 설정합니다.

```cpp
void SetRelatedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
설정할 창 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

관련 CWnd 개체가 설정된 경우 애니메이션 관리자의 상태가 변경되었거나 타이머 포스트 업데이트 이벤트가 발생했을 때 애니메이션 컨트롤러가 자동으로 업데이트(WM_PAINT 메시지 보내기)할 수 있습니다.

## <a name="canimationcontrollerupdateanimationmanager"></a><a name="updateanimationmanager"></a>C애니메이션 컨트롤러::업데이트 애니메이션 관리자

애니메이션 관리자가 모든 애니메이션 변수의 값을 업데이트하도록 지시합니다.

```
virtual void UpdateAnimationManager();
```

### <a name="remarks"></a>설명

이 메서드를 호출하면 애니메이션 관리자가 현재 시간으로 진행되어 필요에 따라 스토리보드의 상태를 변경하고 애니메이션 변수를 적절한 보간된 값으로 업데이트합니다. 내부적으로이 메서드는 IUIAnimationTimer::GetTime (timeNow) 및 IUIAnimationManager::Update(timeNow)를 호출합니다. 파생 클래스에서 이 메서드를 재정의하여 이 동작을 사용자 지정합니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
