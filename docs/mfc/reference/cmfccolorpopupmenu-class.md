---
title: CMFCColorPopupMenu 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
helpviewer_keywords:
- CMFCColorPopupMenu [MFC], CMFCColorPopupMenu
- CMFCColorPopupMenu [MFC], CreateTearOffBar
- CMFCColorPopupMenu [MFC], GetMenuBar
- CMFCColorPopupMenu [MFC], SetPropList
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
ms.openlocfilehash: 901a44c8f5fdecd1b277ebdecc995722a3afe9a3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752500"
---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu 클래스

사용자가 문서 또는 응용 프로그램에서 색상을 선택하는 데 사용하는 팝업 메뉴를 나타냅니다.

## <a name="syntax"></a>구문

```
class CMFCColorPopupMenu : public CMFCPopupMenu
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|[CMFC컬러팝업메뉴::CMFC컬러팝메뉴](#cmfccolorpopupmenu)|`CMFCColorPopupMenu` 개체를 생성합니다.|
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|[CMFC컬러팝업메뉴::티어오프바 만들기](#createtearoffbar)|도킹 가능한 분리 가능한 색상 막대를 만듭니다. [(CMFCPopup메뉴 재정의::만들기티어오프바.)](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar)|
|[CMFC컬러팝업메뉴::겟메뉴바](#getmenubar)|팝업 메뉴에 포함된 [CMFCPopupMenuBar를](../../mfc/reference/cmfcpopupmenubar-class.md) 반환합니다. [(재정의 CMFCPopup메뉴::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|
|`CMFCColorPopupMenu::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFC컬러팝업메뉴::세트프로프리스트](#setproplist)|포함된 `CMFCColorBar` 개체의 속성 그리드 제어 개체를 설정합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|속성|Description|
|`m_bEnabledInCustomizeMode`|색상 막대를 표시할지 여부를 결정하는 부울 값입니다.|
|`m_wndColorBar`|색상 `CMFCColorBar` 선택을 제공하는 개체입니다.|

### <a name="remarks"></a>설명

이 클래스는 `CMFCPopupMenu` 클래스의 팝업 메뉴 기능을 상속 `CMFCColorBar` 하 고 색상 선택을 제공 하는 개체를 관리 합니다. 도구 모음 프레임워크가 사용자 지정 모드에 있고 멤버가 `m_bEnabledInCustomizeMode` FALSE로 설정되면 색상 막대 개체가 표시되지 않습니다. 사용자 지정 모드에 대한 자세한 내용은 [CMFCToolBar::IsCustomizeMode를](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) 참조하십시오.

자세한 `CMFCColorBar`내용은 [CMFCColorBar 클래스를](../../mfc/reference/cmfccolorbar-class.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

[CMFC컬러팝메뉴](../../mfc/reference/cmfccolorpopupmenu-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxcolorpopupmenu.h

## <a name="cmfccolorpopupmenucmfccolorpopupmenu"></a><a name="cmfccolorpopupmenu"></a>CMFC컬러팝업메뉴::CMFC컬러팝메뉴

`CMFCColorPopupMenu` 개체를 생성합니다.

```
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    int nHorzDockRows,
    int nVertDockColumns,
    COLORREF colorAutomatic,
    UINT uiCommandID,
    BOOL bStdColorDlg = FALSE);

CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic);

CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*색상*<br/>
【인】 프레임워크가 팝업 메뉴에 표시되는 색상 배열입니다.

*색*<br/>
【인】 기본 선택 된 색상입니다.

*lpszAutoColor*<br/>
【인】 자동(기본) *automatic* 색상 단추 또는 NULL의 텍스트 레이블입니다.

자동 단추의 표준 레이블은 **자동**입니다.

*lpszOtherColor*<br/>
【인】 더 많은 색상 선택 또는 NULL을 표시하는 *다른* 단추의 텍스트 레이블입니다.

다른 버튼의 표준 레이블은 **더 많은 색상입니다...**.

*lpszDocColors*<br/>
【인】 문서 색상 단추의 텍스트 레이블입니다. 문서 색상팔레트에는 문서가 현재 사용하는 모든 색상이 나열됩니다.

*lstDocColors*<br/>
【인】 문서에서 현재 사용하는 색상 목록입니다.

*nColumns*<br/>
【인】 색상 배열에 있는 열 수입니다.

*n호르즈독로우스*<br/>
【인】 색상 막대가 가로로 도킹될 때 있는 행 수입니다.

*nVertDock열*<br/>
【인】 색상 막대가 세로로 도킹될 때 있는 열 수입니다.

*colorAutomatic*<br/>
【인】 자동 단추를 클릭할 때 프레임워크가 적용되는 기본 색상입니다.

*uiCommandID*<br/>
【인】 색상 막대 컨트롤 명령 ID입니다.

*bStdColorDlg*<br/>
【인】 표준 시스템 색상 대화 상자 또는 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 대화 상자를 표시할지 여부를 나타내는 부울입니다.

*p부모Btn*<br/>
【인】 상위 단추에 대한 포인터입니다.

*nID*<br/>
【인】 명령 ID입니다.

### <a name="remarks"></a>설명

오버로드된 각 생성자는 멤버를 `m_bEnabledInCustomizeMode` FALSE로 설정합니다.

### <a name="example"></a>예제

다음 예제에서는 개체를 `CMFCColorPopupMenu` 구성하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]

## <a name="cmfccolorpopupmenucreatetearoffbar"></a><a name="createtearoffbar"></a>CMFC컬러팝업메뉴::티어오프바 만들기

도킹 가능한 분리 가능한 색상 막대를 만듭니다.

```
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,
    UINT uiID,
    LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*pWndMain*|【인】 찢어짐 막대의 상위 창에 대한 포인터입니다.|
|*uiID*|【인】 찢어짐 막대의 명령 ID입니다.|
|*lpszName*|【인】 찢어짐 막대의 창 텍스트입니다.|

### <a name="return-value"></a>Return Value

새 해제 컨트롤 막대 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md) 개체를 만들고 [CPane 클래스](../../mfc/reference/cpane-class.md) 포인터에 캐스팅 합니다. [MFC 클래스 개체의 형식 캐스팅에](../../mfc/reference/type-casting-of-mfc-class-objects.md)설명된 캐스팅 매크로 중 하나를 사용하여 이 값을 [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md) 포인터로 다시 캐스팅할 수 있습니다.

## <a name="cmfccolorpopupmenugetmenubar"></a><a name="getmenubar"></a>CMFC컬러팝업메뉴::겟메뉴바

팝업 메뉴에 포함된 [CMFCPopupMenuBar를](../../mfc/reference/cmfcpopupmenubar-class.md) 반환합니다.

```
virtual CMFCPopupMenuBar* GetMenuBar();
```

### <a name="return-value"></a>Return Value

임베디드에 `CMFCPopupMenuBar`대한 포인터입니다.

### <a name="remarks"></a>설명

색상 팝업 메뉴에는 [CMFCPopupMenuBar 클래스](../../mfc/reference/cmfcpopupmenubar-class.md) 개체가 포함되어 있습니다. 응용 프로그램에서 다른 임베디드 형식을 사용하는 경우 derived 클래스에서 이 메서드를 재정의합니다.

## <a name="cmfccolorpopupmenusetproplist"></a><a name="setproplist"></a>CMFC컬러팝업메뉴::세트프로프리스트

포함된 `CMFCColorBar` 개체의 속성 그리드 제어 개체를 설정합니다.

```cpp
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>매개 변수

*pWndList*<br/>
【인】 속성 그리드 제어 개체에 대한 포인터입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
