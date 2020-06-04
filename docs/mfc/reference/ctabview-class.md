---
title: CTabView 클래스
ms.date: 11/04/2016
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
helpviewer_keywords:
- CTabView [MFC], AddView
- CTabView [MFC], FindTab
- CTabView [MFC], GetActiveView
- CTabView [MFC], GetTabControl
- CTabView [MFC], RemoveView
- CTabView [MFC], SetActiveView
- CTabView [MFC], IsScrollBar
- CTabView [MFC], OnActivateView
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
ms.openlocfilehash: ad30cbbf5de195708d2d357a76c38b661d095c2f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365917"
---
# <a name="ctabview-class"></a>CTabView 클래스

클래스는 `CTabView` MFC의 문서/보기 아키텍처를 사용하는 응용 프로그램에서 탭 제어 [클래스(CMFCTabCtrl)의](../../mfc/reference/ctabview-class.md)사용을 단순화합니다.

## <a name="syntax"></a>구문

```
class CTabbedView : public CView
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CTabView::추가 보기](#addview)|탭 컨트롤에 새 보기를 추가합니다.|
|[CTabView::찾기 탭](#findtab)|탭 컨트롤에서 지정된 뷰의 인덱스를 반환합니다.|
|[CTabView::GetActiveView](#getactiveview)|현재 활성 보기에 대한 포인터 반환|
|[CTabView::GetTabControl](#gettabcontrol)|뷰와 연결된 탭 컨트롤에 대한 참조를 반환합니다.|
|[CTabView::제거보기](#removeview)|탭 컨트롤에서 보기를 제거합니다.|
|[CTabView::설정활성보기](#setactiveview)|뷰를 활성화합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C탭뷰::이스크롤바](#isscrollbar)|탭 보기를 만들 때 프레임워크에서 호출하여 탭 보기에 공유 가로 스크롤 막대가 있는지 여부를 확인합니다.|
|[CTabView::온인스로이브뷰](#onactivateview)|탭 보기가 활성 또는 비활성으로 만들어지면 프레임워크에서 호출됩니다.|

## <a name="remarks"></a>설명

이 클래스를 사용하면 탭된 보기를 문서/보기 응용 프로그램에 쉽게 넣을 수 있습니다. `CTabView`는 `CView`포함된 `CMFCTabCtrl` 개체를 포함하는 -derived 클래스입니다. `CTabView`은 개체를 지원하는 데 `CMFCTabCtrl` 필요한 모든 메시지를 처리합니다. 클래스를 `CTabView` 파생하고 응용 프로그램에 연결한 다음 `CView`메서드를 사용하여 -derived 클래스를 `AddView` 추가하기만 하면 됩니다. 탭 컨트롤은 이러한 보기를 탭으로 표시합니다.

예를 들어 스프레드시트, 차트, 편집 가능한 양식 등 다양한 방식으로 나타낼 수 있는 문서가 있을 수 있습니다. 필요에 따라 데이터를 그리는 개별 뷰를 `CTabView`만들고-파생 된 개체에 삽입하고 추가 코딩없이 탭할 수 있습니다.

[TabbedView 샘플: MFC 탭 뷰](../../overview/visual-cpp-samples.md) 응용 `CTabView`프로그램의 사용을 보여 줍니다.

## <a name="example"></a>예제

다음 예제에서는 `CTabView` TabbedView 샘플에서 사용 되는 방법을 보여 봅니다.

[!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]

## <a name="requirements"></a>요구 사항

**헤더:** afxTabView.h

## <a name="ctabviewaddview"></a><a name="addview"></a>CTabView::추가 보기

탭 컨트롤에 보기를 추가합니다.

```
int AddView(
    CRuntimeClass* pViewClass,
    const CString& strViewLabel,
    int iIndex=-1,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>매개 변수

*pView클래스*<br/>
【인】 삽입된 뷰의 런타임 클래스에 대한 포인터입니다.

*스트뷰라벨*<br/>
【인】 탭의 텍스트를 지정합니다.

*iIndex*<br/>
【인】 뷰를 삽입할 0기반 위치를 지정합니다. 위치가 -1이면 새 탭이 끝에 삽입됩니다.

*pContext*<br/>
【인】 뷰에 대한 `CCreateContext` 포인터입니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 보기 인덱스입니다. 그렇지 않으면 -1입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 프레임에 포함된 탭 컨트롤에 뷰를 추가합니다.

## <a name="ctabviewfindtab"></a><a name="findtab"></a>CTabView::찾기 탭

탭 컨트롤에서 지정된 뷰의 인덱스를 반환합니다.

```
int FindTab(HWND hWndView) const;
```

### <a name="parameters"></a>매개 변수

*hWndView*<br/>
【인】 뷰의 핸들입니다.

### <a name="return-value"></a>Return Value

뷰가 발견되면 뷰의 인덱스입니다. 그렇지 않으면 -1.

### <a name="remarks"></a>설명

이 함수를 호출하여 지정된 핸들이 있는 뷰의 인덱스를 검색합니다.

## <a name="ctabviewgetactiveview"></a><a name="getactiveview"></a>CTabView::GetActiveView

현재 활성 보기에 대한 포인터를 반환합니다.

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Return Value

활성 보기에 대한 유효한 포인터 또는 활성 보기가 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

## <a name="ctabviewgettabcontrol"></a><a name="gettabcontrol"></a>CTabView::GetTabControl

뷰와 연결된 탭 컨트롤에 대한 참조를 반환합니다.

```
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```

### <a name="return-value"></a>Return Value

뷰와 연결된 탭 컨트롤에 대한 참조입니다.

## <a name="ctabviewisscrollbar"></a><a name="isscrollbar"></a>C탭뷰::이스크롤바

탭 보기를 만들 때 프레임워크에서 호출하여 탭 보기에 공유 가로 스크롤 막대가 있는지 여부를 확인합니다.

```
virtual BOOL IsScrollBar() const;
```

### <a name="return-value"></a>Return Value

탭 보기를 공유 스크롤 막대와 함께 만들어야 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

*프레임워크는 CTabView* 개체를 만들 때 이 메서드를 호출합니다.

*CTabView*-파생 클래스에서 *IsScrollBar* 메서드를 재정의하고 공유 가로 스크롤 막대가 있는 뷰를 만들려면 TRUE를 반환합니다.

## <a name="ctabviewonactivateview"></a><a name="onactivateview"></a>CTabView::온인스로이브뷰

탭 보기가 활성 또는 비활성으로 만들어지면 프레임워크에서 호출됩니다.

```
virtual void OnActivateView(CView* view);
```

### <a name="parameters"></a>매개 변수

*보기*<br/>
【인】 뷰에 대한 포인터입니다.

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행하지 않습니다. `CTabView`이 알림을 처리 하려면 -derived 클래스에서이 메서드를 재정의 합니다.

## <a name="ctabviewremoveview"></a><a name="removeview"></a>CTabView::제거보기

탭 컨트롤에서 보기를 제거합니다.

```
BOOL RemoveView(int iTabNum);
```

### <a name="parameters"></a>매개 변수

*iTabNum*<br/>
【인】 제거할 뷰의 인덱스입니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 제거된 뷰의 인덱스입니다. 그렇지 않으면 -1.

### <a name="remarks"></a>설명

## <a name="ctabviewsetactiveview"></a><a name="setactiveview"></a>CTabView::설정활성보기

뷰를 활성화합니다.

```
BOOL SetActiveView(int iTabNum);
```

### <a name="parameters"></a>매개 변수

*iTabNum*<br/>
【인】 탭 보기의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

TRUE 지정된 뷰가 활성 상태인 경우 보기의 인덱스가 잘못되면 FALSE입니다.

### <a name="remarks"></a>설명

자세한 내용은 [CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTabCtrl](../../mfc/reference/ctabview-class.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)
