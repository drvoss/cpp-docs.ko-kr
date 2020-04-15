---
title: CMFC태스크파네태스크그룹 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsBottom
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsCollapsed
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsSpecial
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_lstTasks
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rect
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rectGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_strName
helpviewer_keywords:
- CMFCTasksPaneTaskGroup [MFC], CMFCTasksPaneTaskGroup
- CMFCTasksPaneTaskGroup [MFC], SetACCData
- CMFCTasksPaneTaskGroup [MFC], m_bIsBottom
- CMFCTasksPaneTaskGroup [MFC], m_bIsCollapsed
- CMFCTasksPaneTaskGroup [MFC], m_bIsSpecial
- CMFCTasksPaneTaskGroup [MFC], m_lstTasks
- CMFCTasksPaneTaskGroup [MFC], m_rect
- CMFCTasksPaneTaskGroup [MFC], m_rectGroup
- CMFCTasksPaneTaskGroup [MFC], m_strName
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
ms.openlocfilehash: 4c24eba646bede462a5f3cfb85715278cfa7daee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366265"
---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFC태스크파네태스크그룹 클래스

클래스는 `CMFCTasksPaneTaskGroup` [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) 컨트롤에서 사용하는 도우미 클래스입니다. `CMFCTasksPaneTaskGroup` 형식의 개체는 *작업 그룹*을 나타냅니다. 작업 그룹은 축소 단추가 포함된 별도 상자에 프레임워크가 표시하는 항목 목록입니다. 상자는 선택적 캡션(그룹 이름)을 가질 수 있습니다. 그룹을 축소하면 작업 목록이 표시되지 않습니다.

## <a name="syntax"></a>구문

```
class CMFCTasksPaneTaskGroup : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC태스크파네태스크그룹::CMFC태스크스패네태스크그룹](#cmfctaskspanetaskgroup)|`CMFCTasksPaneTaskGroup` 개체를 생성합니다.|
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC태스크파네태스크그룹::셋ACC데이터](#setaccdata)|현재 작업 그룹에 대한 내게 필요한 옵션 데이터를 결정합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CMFC태스크파네태스크그룹::m_bIsBottom](#m_bisbottom)|작업 그룹이 작업 창 컨트롤의 맨 아래에 정렬되어 있는지 여부를 결정합니다.|
|[CMFC태스크파네태스크그룹:m_bIsCollapsed](#m_biscollapsed)|작업 그룹이 축소되는지 여부를 결정합니다.|
|[CMFC태스크파네태스크그룹::m_bIsSpecial](#m_bisspecial)|작업 그룹이 *특수인지* 여부를 결정합니다. 프레임워크는 특수 캡션을 다른 색상으로 표시합니다.|
|[CMFC태스크파네태스크그룹::m_lstTasks](#m_lsttasks)|작업의 내부 목록을 포함합니다.|
|[CMFC태스크파네태스크그룹::m_rect](#m_rect)|그룹 캡션의 경계 사각형을 지정합니다.|
|[CMFC태스크파네태스크그룹::m_rectGroup](#m_rectgroup)|그룹의 경계 사각형을 지정합니다.|
|[CMFC태스크파네태스크그룹::m_strName](#m_strname)|그룹의 이름을 지정합니다.|

## <a name="remarks"></a>설명

다음 그림에서는 확장된 작업 그룹을 보여 주며 있습니다.

![작업 그룹, 확장](../../mfc/reference/media/nexttaskgrpexpand.png "작업 그룹, 확장됨")

다음 그림에서는 축소된 작업 그룹을 보여 주며 있습니다.

![축소된 작업 그룹](../../mfc/reference/media/nexttaskgrpcollapse.png "축소된 작업 그룹")

다음 그림에서는 캡션이 없는 작업 그룹을 보여 주며 있습니다.

![캡션이 없는 작업 그룹](../../mfc/reference/media/nexttaskgrpnocapt.png "캡션이 없는 작업 그룹")

다음 그림에서는 두 작업 그룹을 보여 주십니다. 첫 번째 작업 그룹은 플래그를 `m_bIsSpecial` TRUE로 설정하여 특수한 것으로 표시되고 두 번째 작업 그룹은 특별하지 않습니다. 첫 번째 작업 그룹의 캡션이 두 번째 작업 그룹보다 어떻게 어두운지 에 유의하십시오.

![특수 작업 그룹](../../mfc/reference/media/nexttaskgrpspecial.png "특수 작업 그룹")

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxTasksPane.h

## <a name="cmfctaskspanetaskgroupcmfctaskspanetaskgroup"></a><a name="cmfctaskspanetaskgroup"></a>CMFC태스크파네태스크그룹::CMFC태스크스패네태스크그룹

`CMFCTasksPaneTaskGroup` 개체를 생성합니다.

```
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,
    BOOL bIsBottom,
    BOOL bIsSpecial=FALSE,
    BOOL bIsCollapsed=FALSE,
    CMFCTasksPanePropertyPage* pPage=NULL,
    HICON hIcon=NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
그룹 캡션에서 그룹 이름을 지정합니다.

*비스 바텀*<br/>
그룹이 작업 창 컨트롤의 맨 아래에 정렬되어 있는지 여부를 지정합니다.

*비스스페셜*<br/>
그룹이 *특별으로* 지정되었는지 여부를 지정하여 그룹 캡션이 다른 색상으로 채워지는지 여부를 지정합니다.

*비스접지*<br/>
그룹이 축소되는지 여부를 지정합니다.

*p페이지*<br/>
이 작업 그룹이 속한 속성 페이지를 지정합니다.

*hIcon*<br/>
그룹 캡션에 표시되는 아이콘을 지정합니다.

### <a name="remarks"></a>설명

## <a name="cmfctaskspanetaskgroupm_bisbottom"></a><a name="m_bisbottom"></a>CMFC태스크파네태스크그룹::m_bIsBottom

작업 그룹이 작업 창 컨트롤의 맨 아래에 정렬되어 있는지 여부를 결정합니다.

```
BOOL m_bIsBottom;
```

### <a name="remarks"></a>설명

하나의 그룹만 작업 창 컨트롤의 맨 아래에 정렬할 수 있습니다. 이 작업 그룹을 마지막으로 추가해야 합니다. 자세한 내용은 [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)을 참조하십시오.

## <a name="cmfctaskspanetaskgroupm_biscollapsed"></a><a name="m_biscollapsed"></a>CMFC태스크파네태스크그룹:m_bIsCollapsed

작업 그룹이 축소되는지 여부를 결정합니다.

```
BOOL m_bIsCollapsed;
```

### <a name="remarks"></a>설명

[CMFCTaskPane::EnableGroupCollapse를](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse)호출하여 작업 창에서 그룹을 축소하는 기능을 활성화하거나 사용하지 않도록 설정할 수 있습니다.

## <a name="cmfctaskspanetaskgroupm_bisspecial"></a><a name="m_bisspecial"></a>CMFC태스크파네태스크그룹::m_bIsSpecial

작업 그룹이 *특수인지* 여부와 특수 작업 그룹의 캡션을 다른 색상으로 식별해야 하는지 여부를 결정합니다.

```
BOOL m_bIsSpecial;
```

### <a name="remarks"></a>설명

응용 프로그램이 Windows XP 시각적 테마를 `m_bIsSpecial` 사용하고 있고 FALSE인 경우 프레임워크는 EBP_NORMALGROUPBACKGROUND 플래그를 호출합니다. `DrawThemeBackground` TRUE이면 `m_bIsSpecial` 프레임워크는 `DrawThemeBackground` EBP_SPECIALGROUPBACKGROUND 플래그를 호출합니다.

## <a name="cmfctaskspanetaskgroupm_lsttasks"></a><a name="m_lsttasks"></a>CMFC태스크파네태스크그룹::m_lstTasks

작업의 내부 목록을 포함합니다.

```
CObList m_lstTasks;
```

### <a name="remarks"></a>설명

이 목록을 채우려면 [CMFCTaskPane::AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask)를 호출합니다.

## <a name="cmfctaskspanetaskgroupm_rect"></a><a name="m_rect"></a>CMFC태스크파네태스크그룹::m_rect

그룹 캡션의 경계 사각형을 지정합니다.

```
CRect m_rect;
```

### <a name="remarks"></a>설명

이 값은 프레임워크에 의해 자동으로 계산됩니다.

## <a name="cmfctaskspanetaskgroupm_rectgroup"></a><a name="m_rectgroup"></a>CMFC태스크파네태스크그룹::m_rectGroup

그룹의 경계 사각형을 지정합니다.

```
CRect m_rectGroup;
```

### <a name="remarks"></a>설명

이 값은 프레임워크에 의해 자동으로 계산됩니다.

## <a name="cmfctaskspanetaskgroupm_strname"></a><a name="m_strname"></a>CMFC태스크파네태스크그룹::m_strName

그룹의 이름을 지정합니다.

```
CString m_strName;
```

### <a name="remarks"></a>설명

이 값이 비어 있으면 그룹 캡션이 표시되지 않으며 그룹을 축소할 수 없습니다.

## <a name="cmfctaskspanetaskgroupsetaccdata"></a><a name="setaccdata"></a>CMFC태스크파네태스크그룹::셋ACC데이터

현재 작업 그룹에 대한 내게 필요한 옵션 데이터를 결정합니다.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
【인】 현재 작업 그룹의 상위 창을 나타냅니다.

*데이터*<br/>
【아웃】 현재 작업 `CAccessibilityData` 그룹의 내게 필요한 옵션 데이터로 채워진 형식의 개체입니다.

### <a name="return-value"></a>Return Value

*TRUE 데이터* 매개 변수가 현재 작업 그룹의 내게 필요한 옵션 데이터로 성공적으로 채워진 경우 그렇지 않으면 false입니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC태스크스팬 클래스](../../mfc/reference/cmfctaskspane-class.md)<br/>
[CMFC태스크파네태스크 클래스](../../mfc/reference/cmfctaskspanetask-class.md)<br/>
[CMFC아웃아웃바 클래스](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)
