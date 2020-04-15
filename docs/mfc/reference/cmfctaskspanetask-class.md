---
title: CMFC태스크파네태스크 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTask::m_bAutoDestroyWindow
- AFXTASKSPANE/CMFCTasksPaneTask::m_bIsBold
- AFXTASKSPANE/CMFCTasksPaneTask::m_dwUserData
- AFXTASKSPANE/CMFCTasksPaneTask::m_hwndTask
- AFXTASKSPANE/CMFCTasksPaneTask::m_nIcon
- AFXTASKSPANE/CMFCTasksPaneTask::m_nWindowHeight
- AFXTASKSPANE/CMFCTasksPaneTask::m_pGroup
- AFXTASKSPANE/CMFCTasksPaneTask::m_rect
- AFXTASKSPANE/CMFCTasksPaneTask::m_strName
- AFXTASKSPANE/CMFCTasksPaneTask::m_uiCommandID
helpviewer_keywords:
- CMFCTasksPaneTask [MFC], CMFCTasksPaneTask
- CMFCTasksPaneTask [MFC], SetACCData
- CMFCTasksPaneTask [MFC], m_bAutoDestroyWindow
- CMFCTasksPaneTask [MFC], m_bIsBold
- CMFCTasksPaneTask [MFC], m_dwUserData
- CMFCTasksPaneTask [MFC], m_hwndTask
- CMFCTasksPaneTask [MFC], m_nIcon
- CMFCTasksPaneTask [MFC], m_nWindowHeight
- CMFCTasksPaneTask [MFC], m_pGroup
- CMFCTasksPaneTask [MFC], m_rect
- CMFCTasksPaneTask [MFC], m_strName
- CMFCTasksPaneTask [MFC], m_uiCommandID
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
ms.openlocfilehash: 49fccdf161da7deb1fd88a12a107df40bafdae92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375862"
---
# <a name="cmfctaskspanetask-class"></a>CMFC태스크파네태스크 클래스

클래스는 `CMFCTasksPaneTask` 작업 창 [컨트롤(CMFCTaskPane)에](../../mfc/reference/cmfctaskspane-class.md)대한 작업을 나타내는 도우미 클래스입니다. 작업 개체는 작업 [그룹(CMFCTaskPaneTaskGroup)의](../../mfc/reference/cmfctaskspanetaskgroup-class.md)항목을 나타냅니다. 각 작업은 사용자가 작업을 클릭할 때 프레임워크가 실행하는 명령과 작업 이름의 왼쪽에 나타내는 아이콘을 포함할 수 있습니다.

## <a name="syntax"></a>구문

```
class CMFCTasksPaneTask : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC태스크파네태스크::CMFC태스크스패네태스크](#cmfctaskspanetask)|`CMFCTasksPaneTask` 개체를 만들어 초기화합니다.|
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC태스크파네태스크::셋아크데이터](#setaccdata)|현재 작업에 대한 내게 필요한 옵션 데이터를 결정합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CMFC태스크스패네태스크::m_bAutoDestroyWindow](#m_bautodestroywindow)|작업 창이 자동으로 소멸되는지 여부를 결정합니다.|
|[CMFC태스크스패네태스크::m_bIsBold](#m_bisbold)|프레임워크가 굵은 텍스트로 작업 레이블을 그리는지 여부를 결정합니다.|
|[CMFC태스크스패네태스크::m_dwUserData](#m_dwuserdata)|프레임워크가 작업과 연관되는 사용자 정의 데이터를 포함합니다. 작업에 연결된 데이터가 없는 경우 0으로 설정합니다.|
|[CMFC태스크스패네태스크::m_hwndTask](#m_hwndtask)|작업 창에 대한 핸들입니다.|
|[CMFC태스크스패네태스크::m_nIcon](#m_nicon)|작업 옆에 프레임워크가 표시되는 이미지의 이미지 목록의 인덱스입니다.|
|[CMFC태스크스패네태스크::m_nWindowHeight](#m_nwindowheight)|작업 창의 높이입니다. 작업에 작업 창이 없는 경우 이 값은 0입니다.|
|[CMFC태스크스패네태스크::m_pGroup](#m_pgroup)|이 작업이 `CMFCTasksPaneTaskGroup` 속한 포인터입니다.|
|[CMFC태스크스패네태스크::m_rect](#m_rect)|작업의 경계 사각형을 지정합니다.|
|[CMFC태스크스패네태스크::m_strName](#m_strname)|작업의 이름입니다.|
|[CMFC태스크스패네태스크::m_uiCommandID](#m_uicommandid)|사용자가 작업을 클릭할 때 프레임워크가 실행되는 명령 ID를 지정합니다. 이 값이 유효한 명령 ID가 아닌 경우 작업은 간단한 레이블로 처리됩니다.|

## <a name="remarks"></a>설명

다음 그림에서는 세 가지 작업을 포함하는 작업 그룹을 보여 주며 있습니다.

![작업 그룹, 확장](../../mfc/reference/media/nexttaskgrpexpand.png "작업 그룹, 확장됨")

> [!NOTE]
> 작업에 유효한 명령 ID가 없는 경우 간단한 레이블로 처리됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxTasksPane.h

## <a name="cmfctaskspanetaskcmfctaskspanetask"></a><a name="cmfctaskspanetask"></a>CMFC태스크파네태스크::CMFC태스크스패네태스크

`CMFCTasksPaneTask` 개체를 만들어 초기화합니다.

```
CMFCTasksPaneTask(
    CMFCTasksPaneTaskGroup* pGroup,
    LPCTSTR lpszName,
    int nIcon,
    UINT uiCommandID,
    DWORD dwUserData = 0,
    HWND hwndTask = NULL,
    BOOL bAutoDestroyWindow = FALSE,
    int nWindowHeight = 0);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
작업이 속한 [CMFCTaskPaneTaskGroup을](../../mfc/reference/cmfctaskspanetaskgroup-class.md) 지정합니다.

*lpszName*<br/>
작업 이름을 지정합니다.

*니콘 (것)*<br/>
이미지 목록에서 작업 이미지의 인덱스를 지정합니다.

*uiCommandID*<br/>
작업을 클릭할 때 실행되는 명령 ID를 지정합니다.

*dw사용자 데이터*<br/>
사용자 정의 데이터.

*hwndTask*<br/>
작업 창에 핸들을 지정합니다.

*b오토파괴창*<br/>
TRUE이면 작업 창이 자동으로 소멸됩니다.

*n창높이 높이*<br/>
작업 창의 높이를 지정합니다.

### <a name="remarks"></a>설명

## <a name="cmfctaskspanetaskm_bautodestroywindow"></a><a name="m_bautodestroywindow"></a>CMFC태스크스패네태스크::m_bAutoDestroyWindow

작업 창이 자동으로 소멸되는지 여부를 결정합니다.

```
BOOL m_bAutoDestroyWindow;
```

### <a name="remarks"></a>설명

TRUE로 설정하여 작업 [창(CMFCTaskPaneTask::m_hwndTask)을](#m_hwndtask)자동으로 소멸하도록 지정합니다. 그렇지 않으면 false입니다.

## <a name="cmfctaskspanetaskm_bisbold"></a><a name="m_bisbold"></a>CMFC태스크스패네태스크::m_bIsBold

작업 레이블이 굵은 텍스트로 그려지는지 여부를 결정합니다.

```
BOOL m_bIsBold;
```

### <a name="remarks"></a>설명

작업 레이블에 대한 굵은 텍스트를 표시하려면 이 멤버를 TRUE로 설정합니다.

## <a name="cmfctaskspanetaskm_dwuserdata"></a><a name="m_dwuserdata"></a>CMFC태스크스패네태스크::m_dwUserData

작업과 연결된 사용자 정의 데이터를 포함합니다. 작업과 연결된 데이터가 없는 경우 0으로 설정합니다.

```
DWORD m_dwUserData;
```

### <a name="remarks"></a>설명

## <a name="cmfctaskspanetaskm_hwndtask"></a><a name="m_hwndtask"></a>CMFC태스크스패네태스크::m_hwndTask

작업 창에 대한 핸들입니다.

```
HWND m_hwndTask;
```

### <a name="remarks"></a>설명

작업 창을 추가하려면 [CMFCTaskPane::AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow)를 호출합니다.

## <a name="cmfctaskspanetaskm_nicon"></a><a name="m_nicon"></a>CMFC태스크스패네태스크::m_nIcon

지정된 작업 옆에 표시되는 이미지를 식별하는 이미지 목록의 인덱스 위치입니다.

```
int m_nIcon;
```

### <a name="remarks"></a>설명

이미지 목록은 [CMFCTasksPane::SetIconsList에 의해 설정됩니다.](../../mfc/reference/cmfctaskspane-class.md#seticonslist)

이미지 `m_nIcon` 없이 작업을 표시하려는 경우 -1로 설정합니다.

## <a name="cmfctaskspanetaskm_nwindowheight"></a><a name="m_nwindowheight"></a>CMFC태스크스패네태스크::m_nWindowHeight

작업 창의 높이입니다. 작업에 작업 창이 없는 경우 이 값은 0입니다.

```
int m_nWindowHeight;
```

### <a name="remarks"></a>설명

## <a name="cmfctaskspanetaskm_pgroup"></a><a name="m_pgroup"></a>CMFC태스크스패네태스크::m_pGroup

이 작업이 속한 [CMFCTaskPaneTaskGroup에](../../mfc/reference/cmfctaskspanetaskgroup-class.md) 대한 포인터입니다.

```
CMFCTasksPaneTaskGroup* m_pGroup;
```

### <a name="remarks"></a>설명

모든 작업에는 상위 그룹이 있어야 합니다. [CMFCTaskPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)을 호출하여 작업 창에 그룹을 추가합니다.

## <a name="cmfctaskspanetaskm_rect"></a><a name="m_rect"></a>CMFC태스크스패네태스크::m_rect

작업의 경계 사각형을 지정합니다.

```
CRect m_rect;
```

### <a name="remarks"></a>설명

이 값은 작업이 그려질 때 프레임워크에 의해 계산됩니다.

## <a name="cmfctaskspanetaskm_strname"></a><a name="m_strname"></a>CMFC태스크스패네태스크::m_strName

작업의 이름입니다.

```
CString m_strName;
```

### <a name="remarks"></a>설명

## <a name="cmfctaskspanetaskm_uicommandid"></a><a name="m_uicommandid"></a>CMFC태스크스패네태스크::m_uiCommandID

사용자가 작업을 클릭할 때 실행되는 명령 ID를 지정합니다. 이 값이 유효한 명령 ID가 아닌 경우 작업은 간단한 레이블로 처리됩니다.

```
UINT m_uiCommandID;
```

### <a name="remarks"></a>설명

## <a name="cmfctaskspanetasksetaccdata"></a><a name="setaccdata"></a>CMFC태스크파네태스크::셋아크데이터

현재 작업에 대한 내게 필요한 옵션 데이터를 결정합니다.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
【인】 현재 작업의 상위 창을 나타냅니다.

*데이터*<br/>
【아웃】 현재 작업의 `CAccessibilityData` 내게 필요한 옵션 데이터로 채워진 형식의 개체입니다.

### <a name="return-value"></a>Return Value

*TRUE 데이터* 매개 변수가 현재 작업의 내게 필요한 옵션 데이터로 성공적으로 채워진 경우 그렇지 않으면 false입니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)
