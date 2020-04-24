---
title: CMFC리스트Ctrl 클래스
ms.date: 07/30/2019
f1_keywords:
- CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl::EnableMarkSortedColumn
- AFXLISTCTRL/CMFCListCtrl::EnableMultipleSort
- AFXLISTCTRL/CMFCListCtrl::GetHeaderCtrl
- AFXLISTCTRL/CMFCListCtrl::IsMultipleSort
- AFXLISTCTRL/CMFCListCtrl::OnCompareItems
- AFXLISTCTRL/CMFCListCtrl::OnGetCellBkColor
- AFXLISTCTRL/CMFCListCtrl::OnGetCellFont
- AFXLISTCTRL/CMFCListCtrl::OnGetCellTextColor
- AFXLISTCTRL/CMFCListCtrl::RemoveSortColumn
- AFXLISTCTRL/CMFCListCtrl::SetSortColumn
- AFXLISTCTRL/CMFCListCtrl::Sort
helpviewer_keywords:
- CMFCListCtrl [MFC], EnableMarkSortedColumn
- CMFCListCtrl [MFC], EnableMultipleSort
- CMFCListCtrl [MFC], GetHeaderCtrl
- CMFCListCtrl [MFC], IsMultipleSort
- CMFCListCtrl [MFC], OnCompareItems
- CMFCListCtrl [MFC], OnGetCellBkColor
- CMFCListCtrl [MFC], OnGetCellFont
- CMFCListCtrl [MFC], OnGetCellTextColor
- CMFCListCtrl [MFC], RemoveSortColumn
- CMFCListCtrl [MFC], SetSortColumn
- CMFCListCtrl [MFC], Sort
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
ms.openlocfilehash: 099ec086bd95a1180af4cf5a8f6a9fa7f1d099ea
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754236"
---
# <a name="cmfclistctrl-class"></a>CMFC리스트Ctrl 클래스

클래스는 `CMFCListCtrl` [CMFCHeaderCtrl 클래스의](../../mfc/reference/clistctrl-class.md) 고급 헤더 제어 기능을 지원하여 CListCtrl [클래스의](../../mfc/reference/cmfcheaderctrl-class.md)기능을 확장합니다.

## <a name="syntax"></a>구문

```
class CMFCListCtrl : public CListCtrl
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCListCtrl::인에이블마크정렬칼럼](#enablemarksortedcolumn)|정렬된 열을 다른 배경색으로 표시할 수 있습니다.|
|[CMFCListCtrl::인에이블멀티소이드정렬](#enablemultiplesort)|여러 정렬 모드를 활성화합니다.|
|[CMFCListCtrl:::겟헤더Ctrl](#getheaderctrl)|밑줄이 그어진 헤더 컨트롤에 대한 참조를 반환합니다.|
|[CMFCListCtrl::IsMultiple정렬](#ismultiplesort)|목록 컨트롤이 여러 정렬 모드에 있는지 확인합니다.|
|[CMFCListCtrl:::온비교항목](#oncompareitems)|두 목록 컨트롤 항목을 비교해야 하는 경우 프레임워크에서 호출합니다.|
|[CMFCListCtrl:::온겟셀BkColor](#ongetcellbkcolor)|개별 셀의 배경색을 결정해야 하는 경우 프레임워크에서 호출합니다.|
|[CMFCListCtrl:::온겟셀폰트](#ongetcellfont)|그려지는 셀에 대한 글꼴을 가져와야 하는 경우 프레임워크에서 호출합니다.|
|[CMFCListCtrl:::온겟셀텍스트컬러](#ongetcelltextcolor)|개별 셀의 텍스트 색상을 결정해야 하는 경우 프레임워크에서 호출합니다.|
|[CMFCListCtrl::제거정렬열](#removesortcolumn)|정렬 열을 정렬 열 목록에서 제거합니다.|
|[CMFCListCtrl:::세트정렬열](#setsortcolumn)|현재 정렬된 열과 정렬 순서를 설정합니다.|
|[CMFCListCtrl::정렬](#sort)|목록 컨트롤을 정렬합니다.|

## <a name="remarks"></a>설명

`CMFCListCtrl`[CListCtrl 클래스](../../mfc/reference/clistctrl-class.md) 클래스에 대한 두 가지 향상된 기능을 제공합니다. 첫째, 헤더에 정렬 화살표를 자동으로 그려 열 정렬이 사용 가능한 옵션임을 나타냅니다. 둘째, 동시에 여러 열에서 데이터 정렬을 지원합니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCListCtrl` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 목록 컨트롤을 만들고, 열을 삽입하고, 항목을 삽입하고, 항목의 텍스트를 설정하고, 목록 컨트롤의 글꼴을 설정하는 방법을 보여 줍니다. 이 코드 조각은 Visual [Studio 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListCtrl](../../mfc/reference/clistctrl-class.md)

[CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxlistctrl.h

## <a name="cmfclistctrlenablemarksortedcolumn"></a><a name="enablemarksortedcolumn"></a>CMFCListCtrl::인에이블마크정렬칼럼

정렬된 열을 다른 배경색으로 표시합니다.

```cpp
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>매개 변수

*b마크*<br/>
【인】 다른 배경색을 사용하도록 설정할지 여부를 결정하는 부울 매개변수입니다.

*bRedraw*<br/>
【인】 컨트롤을 즉시 다시 그릴지 여부를 결정하는 부울 매개 변수입니다.

### <a name="remarks"></a>설명

`EnableMarkSortedColumn`이 메서드를 `CDrawingManager::PixelAlpha` 사용하여 정렬된 열에 사용할 색상을 계산합니다. 선택한 색상은 일반 배경 색을 기반으로 합니다.

## <a name="cmfclistctrlenablemultiplesort"></a><a name="enablemultiplesort"></a>CMFCListCtrl::인에이블멀티소이드정렬

목록 컨트롤의 데이터 행을 여러 열로 정렬할 수 있습니다.

```cpp
void EnableMultipleSort(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 여러 열 정렬 모드를 사용하도록 설정할지 여부를 지정하는 부울입니다.

### <a name="remarks"></a>설명

여러 열을 기반으로 정렬을 사용하도록 설정하면 열에 계층구조가 있습니다. 데이터 행은 먼저 기본 열로 정렬됩니다. 그런 다음 등가 값은 우선 순위에 따라 각 후속 열에 의해 정렬됩니다.

## <a name="cmfclistctrlgetheaderctrl"></a><a name="getheaderctrl"></a>CMFCListCtrl:::겟헤더Ctrl

헤더 컨트롤에 대한 참조를 반환합니다.

```
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```

### <a name="return-value"></a>Return Value

기본 [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

목록 컨트롤의 헤더 컨트롤은 열의 제목을 포함하는 창입니다. 일반적으로 열 바로 위에 배치됩니다.

## <a name="cmfclistctrlismultiplesort"></a><a name="ismultiplesort"></a>CMFCListCtrl::IsMultiple정렬

목록 컨트롤이 현재 여러 열에 대한 정렬을 지원하는지 여부를 확인합니다.

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Return Value

목록 컨트롤이 여러 정렬을 지원하는 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

[CMFCListCtrl 클래스가](../../mfc/reference/cmfclistctrl-class.md) 여러 정렬을 지원하는 경우 사용자는 목록 컨트롤의 데이터를 여러 열로 정렬할 수 있습니다. 여러 정렬을 사용하려면 [CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)을 호출합니다.

## <a name="cmfclistctrloncompareitems"></a><a name="oncompareitems"></a>CMFCListCtrl:::온비교항목

프레임워크는 두 항목을 비교할 때 이 메서드를 호출합니다.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>매개 변수

*l파라름1*<br/>
【인】 비교할 첫 번째 항목입니다.

*l파라름2*<br/>
【인】 비교할 두 번째 항목입니다.

*iColumn*<br/>
【인】 이 메서드가 정렬하는 열의 인덱스입니다.

### <a name="return-value"></a>Return Value

두 항목의 상대위치를 나타내는 정수입니다. 음수 값은 첫 번째 항목이 두 번째 항목 앞에 와야 한다는 것을 나타내고, 양수 값은 첫 번째 항목이 두 번째 항목을 따라야 한다는 것을 나타내고, 0은 두 항목이 동일하다는 것을 나타냅니다.

### <a name="remarks"></a>설명

기본 구현은 항상 0을 반환합니다. 이 함수를 재정의하여 고유한 정렬 알고리즘을 제공합니다.

## <a name="cmfclistctrlongetcellbkcolor"></a><a name="ongetcellbkcolor"></a>CMFCListCtrl:::온겟셀BkColor

프레임워크는 개별 셀의 배경색을 결정해야 할 때 이 메서드를 호출합니다.

```
virtual COLORREF OnGetCellBkColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>매개 변수

*nRow*<br/>
【인】 해당 셀의 행입니다.

*n열*<br/>
【인】 해당 셀의 열입니다.

### <a name="return-value"></a>Return Value

셀의 배경색을 지정하는 COLOREF 값입니다.

### <a name="remarks"></a>설명

기본 `OnGetCellBkColor` 구현은 제공된 입력 매개 변수를 사용하지 `GetBkColor`않고 대신 단순히 호출합니다. 따라서 기본적으로 전체 목록 컨트롤에는 동일한 배경 색이 있습니다. 파생 클래스에서 `OnGetCellBkColor` 재정의하여 개별 셀을 별도의 배경색으로 표시할 수 있습니다.

## <a name="cmfclistctrlongetcellfont"></a><a name="ongetcellfont"></a>CMFCListCtrl:::온겟셀폰트

프레임워크는 개별 셀에 대한 글꼴을 가져올 때 이 메서드를 호출합니다.

```
virtual HFONT OnGetCellFont(
    int nRow,
    int nColumn,
    DWORD dwData = 0);
```

### <a name="parameters"></a>매개 변수

*nRow*<br/>
【인】 해당 셀의 행입니다.

*n열*<br/>
【인】 해당 셀의 열입니다.

*dwData*<br/>
【인】 사용자 정의 데이터. 기본 구현에서 이 매개 변수를 사용하지 않습니다.

### <a name="return-value"></a>Return Value

현재 셀에 사용되는 글꼴에 대한 핸들입니다.

### <a name="remarks"></a>설명

기본적으로 이 메서드는 NULL을 반환합니다. 목록 컨트롤의 모든 셀에는 동일한 글꼴이 있습니다. 이 메서드를 재정의하여 셀마다 다른 글꼴을 제공합니다.

## <a name="cmfclistctrlongetcelltextcolor"></a><a name="ongetcelltextcolor"></a>CMFCListCtrl:::온겟셀텍스트컬러

프레임워크는 개별 셀의 텍스트 색상을 결정해야 할 때 이 메서드를 호출합니다.

```
virtual COLORREF OnGetCellTextColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>매개 변수

*nRow*<br/>
【인】 해당 셀의 행입니다.

*n열*<br/>
【인】 해당 셀의 열입니다.

### <a name="return-value"></a>Return Value

셀의 텍스트 색상을 지정하는 COLOREF 값입니다.

### <a name="remarks"></a>설명

기본적으로 이 메서드는 `GetTextColor` 입력 매개 변수에 관계 없이 호출합니다. 전체 목록 컨트롤은 동일한 텍스트 색상을 갖습니다. 파생 클래스에서 `OnGetCellTextColor` 재정의하여 개별 셀을 별도의 텍스트 색상으로 표시할 수 있습니다.

## <a name="cmfclistctrlremovesortcolumn"></a><a name="removesortcolumn"></a>CMFCListCtrl::제거정렬열

정렬 열을 정렬 열 목록에서 제거합니다.

```cpp
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>매개 변수

*iColumn*<br/>
【인】 제거할 열입니다.

### <a name="remarks"></a>설명

이 메서드는 헤더 컨트롤에서 정렬 열을 제거 합니다. [CMFCHeaderCtrl::Remove정렬열을](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn)호출합니다.

## <a name="cmfclistctrlsetsortcolumn"></a><a name="setsortcolumn"></a>CMFCListCtrl:::세트정렬열

현재 정렬된 열과 정렬 순서를 설정합니다.

```cpp
void SetSortColumn(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>매개 변수

*iColumn*<br/>
【인】 정렬할 열입니다.

*b에 이빙*<br/>
【인】 정렬 순서를 지정하는 부울입니다.

*bAdd*<br/>
【인】 메서드가 정렬 열 목록에 *iColumn으로* 표시된 열을 추가하는지 여부를 지정하는 부울입니다.

### <a name="remarks"></a>설명

이 메서드는 [CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn)메서드를 사용 하 여 헤더 컨트롤에 입력 매개 변수를 전달 합니다.

## <a name="cmfclistctrlsort"></a><a name="sort"></a>CMFCListCtrl::정렬

목록 컨트롤을 정렬합니다.

```
virtual void Sort(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>매개 변수

*iColumn*<br/>
【인】 정렬할 열입니다.

*b에 이빙*<br/>
【인】 정렬 순서를 지정하는 부울입니다.

*bAdd*<br/>
【인】 이 메서드가 *iColumn으로* 표시된 열을 정렬 열 목록에 추가하는지 여부를 지정하는 부울입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CListCtrl 클래스](../../mfc/reference/clistctrl-class.md)
