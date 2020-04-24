---
title: CAutoHideDock사이트 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::CanAcceptPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::DockPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::GetAlignRect
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::RepositionPanes
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetLeft
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetRight
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::UnSetAutoHideMode
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::m_nExtraSpace
helpviewer_keywords:
- CAutoHideDockSite [MFC], CanAcceptPane
- CAutoHideDockSite [MFC], DockPane
- CAutoHideDockSite [MFC], GetAlignRect
- CAutoHideDockSite [MFC], RepositionPanes
- CAutoHideDockSite [MFC], SetOffsetLeft
- CAutoHideDockSite [MFC], SetOffsetRight
- CAutoHideDockSite [MFC], UnSetAutoHideMode
- CAutoHideDockSite [MFC], m_nExtraSpace
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
ms.openlocfilehash: 1f23729ced02a151c6186bdcc72cb8938416be46
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753006"
---
# <a name="cautohidedocksite-class"></a>CAutoHideDock사이트 클래스

`CAutoHideDockSite` [CDockSite 클래스를](../../mfc/reference/cdocksite-class.md) 확장하여 자동 숨기기 도크 창을 구현합니다.

## <a name="syntax"></a>구문

```
class CAutoHideDockSite : public CDockSite
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|`CAutoHideDockSite::CAutoHideDockSite`|`CAutoHideDockSite` 개체를 생성합니다.|
|`CAutoHideDockSite::~CAutoHideDockSite`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|`CAutoHideDockSite::AllowShowOnPaneMenu`|창 메뉴에 표시되는지 여부를 `CAutoHideDockSite` 나타냅니다.|
|[CAutoHideDock사이트::캔 수락판](#canacceptpane)|기본 창 개체가 [CMFCAutoHideBar 클래스에서](../../mfc/reference/cmfcautohidebar-class.md)파생되는지 여부를 결정합니다.|
|[CAutoHideDock사이트::DockPane](#dockpane)|창을 이 `CAuotHideDockSite` 개체에 도킹합니다.|
|[CAutoHideDock사이트::GetAlignRect](#getalignrect)|화면 좌표에서 도크 사이트의 크기를 검색합니다.|
|[CAutoHideDockSite::재배치파네](#repositionpanes)|전역 여백과 단추 `CAutoHideDockSite` 간격으로 창을 다시 그립니다.|
|[C자동 하이드도크사이트::세트오프셋](#setoffsetleft)|도킹 바의 왼쪽에 여백을 설정합니다.|
|[자동 숨기기 독 사이트::세트오프셋라이트](#setoffsetright)|도킹 바의 오른쪽에 여백을 설정합니다.|
|[C자동숨기데독사이트::언셋오토하이드하이드모드](#unsetautohidemode)|[CMFC자동숨기기 바::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) 에서 `CAutoHideDockSite`개체에 대해 호출합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|속성|Description|
|[CAutoHideDock사이트::m_nExtraSpace](#m_nextraspace)|도구 모음과 도킹 막대 모서리 사이의 공간 크기를 정의합니다. 이 공간은 도크 공간의 정렬에 따라 왼쪽 가장자리 또는 위쪽 가장자리에서 측정됩니다.|

## <a name="remarks"></a>설명

[CFrameWndEx::EnableAutoHidePanes를](../../mfc/reference/cframewndex-class.md#enableautohidepanes)호출하면 프레임워크가 자동으로 `CAutoHideDockSite` 개체를 만듭니다. 대부분의 경우 이 클래스를 직접 인스턴스화하거나 사용할 필요가 없습니다.

도킹 바는 도크 창의 왼쪽과 [CMFCAutoHideButton 클래스의](../../mfc/reference/cmfcautohidebutton-class.md)왼쪽 사이의 간격입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="example"></a>예제

다음 예제에서는 `CAutoHideDockSite` `CMFCAutoHideBar` 개체에서 개체를 검색 하는 방법 및 도킹 막대의 왼쪽 및 오른쪽 여백을 설정 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxautohidedocksite.h

## <a name="cautohidedocksitecanacceptpane"></a><a name="canacceptpane"></a>CAutoHideDock사이트::캔 수락판

기본 창이 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 개체인지 에서 파생되는지 `CMFCAutoHideBar`여부를 결정합니다.

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*pBar*|【인】 프레임워크가 테스트하는 기본 창입니다.|

### <a name="return-value"></a>Return Value

true *pBar에서* `CMFCAutoHideBar`파생되는 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

기본 창 개체에서 `CMFCAutoHideBar`파생된 경우 `CAutoHideDockSite`을 포함할 수 있습니다.

## <a name="cautohidedocksitedockpane"></a><a name="dockpane"></a>CAutoHideDock사이트::DockPane

이 [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) 개체에 창을 도킹합니다.

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*pWnd*|【인】 프레임워크가 도킹하는 창입니다.|
|*dockMethod*|【인】 창에 대한 도킹 옵션입니다.|
|*Lprect*|【인】 도킹된 창의 경계를 지정하는 사각형입니다.|

### <a name="remarks"></a>설명

기본 구현은 나중에 사용할 수 위해 제공되는 매개 변수 *dockMethod를*사용하지 않습니다.

*lpRect가* NULL이면 프레임워크는 창을 도크 사이트의 기본 위치에 둡습니다. 도크 사이트가 수평인 경우 기본 위치는 도크 사이트의 맨 왼쪽에 있습니다. 그렇지 않으면 기본 위치가 도크 사이트의 맨 위에 있습니다.

## <a name="cautohidedocksitegetalignrect"></a><a name="getalignrect"></a>CAutoHideDock사이트::GetAlignRect

화면 좌표에서 도크 사이트의 크기를 검색합니다.

```cpp
void GetAlignRect(CRect& rect) const;
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*rect*|【인】 사각형에 대한 참조입니다. 메서드는 이 사각형에 도크 사이트의 크기를 저장합니다.|

### <a name="remarks"></a>설명

사각형은 포함되지 않도록 오프셋 여백에 대해 조정됩니다.

## <a name="cautohidedocksitem_nextraspace"></a><a name="m_nextraspace"></a>CAutoHideDock사이트::m_nExtraSpace

[CAutoHideDockSite 클래스의](../../mfc/reference/cautohidedocksite-class.md) 가장자리와 [CMFCAutoHideBar 클래스](../../mfc/reference/cmfcautohidebar-class.md) 개체 사이의 공간 크기입니다.

```
static int m_nExtraSpace;
```

### <a name="remarks"></a>설명

a가 `CMFCAutoHideBar` 에 `CAutoHideDockSite`도킹된 경우 전체 도크 사이트를 차지해서는 안 됩니다. 이 전역 변수는 왼쪽 또는 위쪽 `CMFCAutoHideBar` 테두리와 해당 `CAutoHideDockSite` 가장자리 사이의 추가 공간을 제어합니다. 상단 또는 왼쪽 모서리사용 여부는 현재 선형에 따라 다릅니다.

## <a name="cautohidedocksitesetoffsetleft"></a><a name="setoffsetleft"></a>C자동 하이드도크사이트::세트오프셋

도킹 바의 왼쪽에 여백을 설정합니다.

```cpp
void SetOffsetLeft(int nOffset);
```

### <a name="parameters"></a>매개 변수

*n오프셋*<br/>
【인】 새 오프셋입니다.

### <a name="remarks"></a>설명

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 개체는 `CAutoHideDockSite` 개체에 정적으로 배치됩니다. 즉, 사용자가 개체의 `CMFCAutoHideBar` 위치를 수동으로 변경할 수 없습니다. 메서드는 `SetOffsetLeft` 왼쪽의 `CMFCAutoHideBar` 왼쪽과 의 왼쪽 사이의 간격을 제어합니다. `CAutoHideDockSite`

## <a name="cautohidedocksitesetoffsetright"></a><a name="setoffsetright"></a>자동 숨기기 독 사이트::세트오프셋라이트

도킹 바의 오른쪽에 여백을 설정합니다.

```cpp
void SetOffsetRight(int nOffset);
```

### <a name="parameters"></a>매개 변수

*n오프셋*<br/>
【인】 새 오프셋입니다.

### <a name="remarks"></a>설명

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 개체는 `CAutoHideDockSite` 개체에 정적으로 배치됩니다. 즉, 사용자가 `CMFCAutoHideBar` 개체의 위치를 수동으로 변경할 수 없습니다. 메서드는 `SetOffsetRight` 오른쪽의 `CMFCAutoHideBar` 오른쪽과 오른쪽 의 사이의 간격을 제어합니다. `CAutoHideDockSite`

## <a name="cautohidedocksiterepositionpanes"></a><a name="repositionpanes"></a>CAutoHideDockSite::재배치파네

[CAutoHideDockSite에서](../../mfc/reference/cautohidedocksite-class.md)창을 다시 그립니다.

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*정류뉴클라이언트에어리어*|【인】 예약된 값입니다.|

### <a name="remarks"></a>설명

기본 구현은 *rectNewClientArea*. 전역 도구 모음 여백과 단추 간격으로 창을 다시 그립니다.

## <a name="cautohidedocksiteunsetautohidemode"></a><a name="unsetautohidemode"></a>C자동숨기데독사이트::언셋오토하이드하이드모드

도크 사이트의 개체에 대해 [CMFCAutoHideBar::UnSetAutoHideMode를](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) 호출합니다.

```cpp
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*pAutoHide도구모음*|【인】 에 있는 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 개체 창에 `CAutoHideDockSite`대한 포인터입니다.|

### <a name="remarks"></a>설명

이 메서드는 *pAutoHideToolbar를*포함 하는 행을 검색합니다. 해당 `CMFCAutoHideBar.UnSetAutoHideMode` 행의 `CMFCAutoHideBar` 모든 개체를 호출합니다. *pAutoHideToolbar를* 찾을 수 없거나 NULL인 경우 `CMFCAutoHideBar.UnSetAutoHideMode` 이 `CMFCAutoHideBar` 메서드는 `CAutoHideDockSite`의 모든 개체를 호출합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite Class](../../mfc/reference/cdocksite-class.md)
