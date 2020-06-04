---
title: CMFCHeaderCtrl Class
ms.date: 11/04/2016
f1_keywords:
- CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::EnableMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::GetColumnState
- AFXHEADERCTRL/CMFCHeaderCtrl::GetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::IsAscending
- AFXHEADERCTRL/CMFCHeaderCtrl::IsDialogControl
- AFXHEADERCTRL/CMFCHeaderCtrl::IsMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::RemoveSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::SetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawItem
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawSortArrow
- AFXHEADERCTRL/CMFCHeaderCtrl::OnFillBackground
helpviewer_keywords:
- CMFCHeaderCtrl [MFC], CMFCHeaderCtrl
- CMFCHeaderCtrl [MFC], EnableMultipleSort
- CMFCHeaderCtrl [MFC], GetColumnState
- CMFCHeaderCtrl [MFC], GetSortColumn
- CMFCHeaderCtrl [MFC], IsAscending
- CMFCHeaderCtrl [MFC], IsDialogControl
- CMFCHeaderCtrl [MFC], IsMultipleSort
- CMFCHeaderCtrl [MFC], RemoveSortColumn
- CMFCHeaderCtrl [MFC], SetSortColumn
- CMFCHeaderCtrl [MFC], OnDrawItem
- CMFCHeaderCtrl [MFC], OnDrawSortArrow
- CMFCHeaderCtrl [MFC], OnFillBackground
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
ms.openlocfilehash: 5140d02c5acbbc430c3b4d175da1933c79c702b3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752346"
---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl Class

클래스는 `CMFCHeaderCtrl` 헤더 컨트롤에서 여러 열 정렬을 지원합니다.

## <a name="syntax"></a>구문

```
class CMFCHeaderCtrl : public CHeaderCtrl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC헤더트rl::CMFC헤더트rl](#cmfcheaderctrl)|`CMFCHeaderCtrl` 개체를 생성합니다.|
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC헤더Ctrl::인에이블멀티소이드정렬](#enablemultiplesort)|현재 헤더 컨트롤에 대해 *여러 열 정렬* 모드를 활성화하거나 사용하지 않도록 설정합니다.|
|[CMFC헤더Ctrl::겟컬럼상태](#getcolumnstate)|열이 정렬되지 않았는지 또는 오름차순 또는 내림차순으로 정렬되는지 여부를 나타냅니다.|
|[CMFC헤더Ctrl::GetSortColumn](#getsortcolumn)|헤더 컨트롤에서 첫 번째 정렬된 열의 0기반 인덱스를 검색합니다.|
|`CMFCHeaderCtrl::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFC헤더트rl::IsAscending](#isascending)|헤더 컨트롤의 열이 오름차순으로 정렬되는지 여부를 나타냅니다.|
|[CMFC헤더트rl:::이디아로그제어](#isdialogcontrol)|현재 헤더 컨트롤의 상위 창이 대화 상자인지 여부를 나타냅니다.|
|[CMFC헤더Ctrl::IsMultiple정렬](#ismultiplesort)|현재 헤더 컨트롤이 *여러 열 정렬* 모드에 있는지 여부를 나타냅니다.|
|[CMFC헤더Ctrl::제거정렬열](#removesortcolumn)|정렬 열 목록에서 지정된 열을 제거합니다.|
|[CMFC헤더Ctrl::세트정렬열](#setsortcolumn)|헤더 컨트롤에서 지정된 열의 정렬 순서를 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC헤더Ctrl:::온드로우아이템](#ondrawitem)|헤더 컨트롤 열을 그리는 프레임워크에서 호출합니다.|
|[CMFC헤더트rl::온드로우정렬로우](#ondrawsortarrow)|정렬 화살표를 그리는 프레임워크에서 호출합니다.|
|[CMFC헤더트rl::온필백](#onfillbackground)|헤더 컨트롤 열의 배경을 채우기 위해 프레임워크에서 호출합니다.|

## <a name="example"></a>예제

다음 예제에서는 `CMFCHeaderCtrl` 클래스의 개체를 생성 하는 방법 및 현재 헤더 컨트롤에 대 한 여러 열 *정렬* 모드를 사용 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]

## <a name="remarks"></a>설명

클래스는 `CMFCHeaderCtrl` 열이 정렬되었음을 나타내기 위해 헤더 제어 열에 정렬 화살표를 그립니다. 상위 목록 [컨트롤(CMFCListCtrl 클래스)의](../../mfc/reference/cmfclistctrl-class.md)열 집합을 동시에 정렬할 수 있는 경우 *여러 열 정렬* 모드를 사용합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)

[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxheaderctrl.h

## <a name="cmfcheaderctrlcmfcheaderctrl"></a><a name="cmfcheaderctrl"></a>CMFC헤더트rl::CMFC헤더트rl

`CMFCHeaderCtrl` 개체를 생성합니다.

```
CMFCHeaderCtrl::CMFCHeaderCtrl()
```

### <a name="remarks"></a>설명

이 생성자는 다음 멤버 변수를 지정된 값으로 초기화합니다.

|멤버 변수|값|
|---------------------|-----------|
|`m_bIsMousePressed`|FALSE|
|`m_bMultipleSort`|FALSE|
|`m_bAscending`|TRUE|
|`m_nHighlightedItem`|-1|
|`m_bTracked`|FALSE|
|`m_bIsDlgControl`|FALSE|
|`m_hFont`|NULL|

## <a name="cmfcheaderctrlenablemultiplesort"></a><a name="enablemultiplesort"></a>CMFC헤더Ctrl::인에이블멀티소이드정렬

현재 헤더 컨트롤에 대해 *여러 열 정렬* 모드를 활성화하거나 사용하지 않도록 설정합니다.

```cpp
void EnableMultipleSort(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE는 여러 열 정렬 모드를 활성화합니다. FALSE는 여러 열 정렬 모드를 사용하지 않도록 설정하고 정렬된 열 목록에서 열을 제거합니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 여러 열 정렬 모드를 활성화하거나 사용하지 않도록 설정합니다. 헤더 컨트롤이 여러 열 정렬 모드인 경우 둘 이상의 열이 정렬에 참여할 수 있습니다.

## <a name="cmfcheaderctrlgetcolumnstate"></a><a name="getcolumnstate"></a>CMFC헤더Ctrl::겟컬럼상태

열이 정렬되지 않았는지 또는 오름차순 또는 내림차순으로 정렬되는지 여부를 나타냅니다.

```
int GetColumnState(int iColumn) const;
```

### <a name="parameters"></a>매개 변수

*iColumn*<br/>
【인】 열의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

지정된 열의 정렬 상태를 나타내는 값입니다. 다음 테이블에서는 가능한 값을 나열합니다.

|값|설명|
|-----------|-----------------|
|-1|내림차순으로 정렬됩니다.|
|0|정렬되지 않았습니다.|
|1|오름차순으로 정렬됩니다.|

### <a name="remarks"></a>설명

## <a name="cmfcheaderctrlgetsortcolumn"></a><a name="getsortcolumn"></a>CMFC헤더Ctrl::GetSortColumn

헤더 컨트롤에서 첫 번째 정렬된 열의 0기반 인덱스를 검색합니다.

```
int GetSortColumn() const;
```

### <a name="return-value"></a>Return Value

정렬된 열의 인덱스 또는 정렬된 열이 없는 경우 -1입니다.

### <a name="remarks"></a>설명

헤더 컨트롤이 *여러 열 정렬* 모드에 있고 디버그 모드에서 응용 프로그램을 컴파일한 경우 이 메서드는 [CMFCHeaderCtrl::GetColumnState](#getcolumnstate) 메서드를 대신 사용하도록 어설션하고 사용하는 것이 좋습니다. 헤더 컨트롤이 여러 열 정렬 모드에 있고 정품 모드에서 응용 프로그램을 컴파일한 경우 이 메서드는 -1을 반환합니다.

## <a name="cmfcheaderctrlisascending"></a><a name="isascending"></a>CMFC헤더트rl::IsAscending

헤더 컨트롤의 열이 오름차순으로 정렬되는지 여부를 나타냅니다.

```
BOOL IsAscending() const;
```

### <a name="return-value"></a>Return Value

TRUE 헤더 컨트롤의 열이 오름차순으로 정렬되는 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드가 반환 하는 값헤더 컨트롤 항목에 적절 한 정렬 화살표를 표시 하는 데 사용 됩니다. [CMFCHeaderCtrl::SetSortColumn](#setsortcolumn) 메서드를 사용하여 정렬 순서를 설정합니다.

## <a name="cmfcheaderctrlisdialogcontrol"></a><a name="isdialogcontrol"></a>CMFC헤더트rl:::이디아로그제어

현재 헤더 컨트롤의 상위 창이 대화 상자인지 여부를 나타냅니다.

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>Return Value

TRUE 현재 헤더 컨트롤의 부모 창이 대화 상자인 경우 그렇지 않으면 false입니다.

## <a name="cmfcheaderctrlismultiplesort"></a><a name="ismultiplesort"></a>CMFC헤더Ctrl::IsMultiple정렬

현재 헤더 컨트롤이 *여러 열 정렬* 모드에 있는지 여부를 나타냅니다.

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Return Value

여러 열 정렬 모드가 활성화된 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) 메서드를 사용하여 여러 열 정렬 모드를 활성화 하거나 비활성화합니다. 헤더 컨트롤이 여러 열 정렬 모드인 경우 둘 이상의 열이 정렬에 참여할 수 있습니다.

## <a name="cmfcheaderctrlondrawitem"></a><a name="ondrawitem"></a>CMFC헤더Ctrl:::온드로우아이템

헤더 컨트롤 열을 그리는 프레임워크에서 호출합니다.

```
virtual void OnDrawItem(
    CDC* pDC,
    int iItem,
    CRect rect,
    BOOL bIsPressed,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*iItem*<br/>
【인】 그릴 항목의 0기반 인덱스입니다.

*rect*<br/>
【인】 그릴 항목의 경계 사각형입니다.

*비스누른*<br/>
【인】 TRUE가 항목을 누른 상태로 그리는 경우; 그렇지 않으면 false입니다.

*비스하이라이트*<br/>
【인】 TRUE 강조 표시된 상태로 항목을 그립니다. 그렇지 않으면 false입니다.

## <a name="cmfcheaderctrlondrawsortarrow"></a><a name="ondrawsortarrow"></a>CMFC헤더트rl::온드로우정렬로우

정렬 화살표를 그리는 프레임워크에서 호출합니다.

```
virtual void OnDrawSortArrow(
    CDC* pDC,
    CRect rectArrow);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*직사각형 화살표*<br/>
【인】 정렬 화살표의 경계 사각형입니다.

## <a name="cmfcheaderctrlonfillbackground"></a><a name="onfillbackground"></a>CMFC헤더트rl::온필백

헤더 컨트롤 열의 배경을 채우기 위해 프레임워크에서 호출합니다.

```
virtual void OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmfcheaderctrlremovesortcolumn"></a><a name="removesortcolumn"></a>CMFC헤더Ctrl::제거정렬열

정렬 열 목록에서 지정된 열을 제거합니다.

```cpp
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>매개 변수

*iColumn*<br/>
【인】 제거할 열의 0기반 인덱스입니다.

## <a name="cmfcheaderctrlsetsortcolumn"></a><a name="setsortcolumn"></a>CMFC헤더Ctrl::세트정렬열

헤더 컨트롤에서 지정된 열의 정렬 순서를 설정합니다.

```cpp
void SetSortColumn(
    int iColumn,
    BOOL bAscending=TRUE,
    BOOL bAdd=FALSE);
```

### <a name="parameters"></a>매개 변수

*iColumn*<br/>
【인】 헤더 제어 열의 0기반 인덱스입니다. 이 매개 변수가 0보다 적으면 이 메서드는 정렬 열 목록에서 모든 열을 제거합니다.

*b에 이빙*<br/>
【인】 *iColumn* 매개 변수가 지정하는 열의 정렬 순서를 지정합니다. 오름차순을 설정하는 TRUE; false를 설정하여 내림차순을 설정합니다. 기본값은 TRUE입니다.

*bAdd*<br/>
【인】 true는 *iColumn* 매개 변수가 지정하는 열의 정렬 순서를 설정합니다.

현재 헤더 컨트롤이 *여러 열 정렬* 모드에 있는 경우 이 메서드는 지정된 열을 정렬 열 목록에 추가합니다. [CMFCHeaderCtrl::EnableMultipleSort를](#enablemultiplesort) 사용하여 여러 열 정렬 모드를 설정합니다.

여러 열 정렬 모드가 설정되지 않고 이 메서드가 디버그 모드로 컴파일되는 경우 이 메서드는 어설션합니다. 여러 열 정렬 모드가 설정되지 않고 이 메서드가 소매 모드에서 컴파일되는 경우 이 메서드는 먼저 정렬 열 목록에서 모든 열을 제거한 다음 지정된 열을 목록에 추가합니다.

FALSE를 먼저 정렬 열 목록에서 모든 열을 제거한 다음 지정된 열을 목록에 추가합니다. 기본값은 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 열의 정렬 순서를 설정합니다. 필요한 경우 이 메서드는 정렬 열 목록에 열을 추가합니다. 헤더 컨트롤은 정렬 순서를 사용하여 위 또는 아래를 가리키는 정렬 화살표를 그립니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리스트Ctrl 클래스](../../mfc/reference/cmfclistctrl-class.md)
