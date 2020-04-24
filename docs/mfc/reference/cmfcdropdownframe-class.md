---
title: CMFC드롭다운프레임 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
helpviewer_keywords:
- CMFCDropDownFrame [MFC], Create
- CMFCDropDownFrame [MFC], GetParentMenuBar
- CMFCDropDownFrame [MFC], GetParentPopupMenu
- CMFCDropDownFrame [MFC], RecalcLayout
- CMFCDropDownFrame [MFC], SetAutoDestroy
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
ms.openlocfilehash: 508b27acd0a2004b1b8f75fde0bddcdf91194948
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752435"
---
# <a name="cmfcdropdownframe-class"></a>CMFC드롭다운프레임 클래스

드롭다운 도구 모음 및 드롭다운 도구 모음 단추에 드롭다운 프레임 창 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CMFCDropDownFrame : public CMiniFrameWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|`CMFCDropDownFrame::CMFCDropDownFrame`|기본 생성자입니다.|
|`CMFCDropDownFrame::~CMFCDropDownFrame`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|[CMFC드롭다운프레임::만들기](#create)|`CMFCDropDownFrame` 개체를 만듭니다.|
|`CMFCDropDownFrame::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFC드롭다운프레임::GetParentMenuBar](#getparentmenubar)|드롭다운 프레임의 상위 메뉴 모음을 검색합니다.|
|[CMFC드롭다운프레임::GetParentPopupMenu](#getparentpopupmenu)|드롭다운 프레임의 상위 팝업 메뉴를 검색합니다.|
|`CMFCDropDownFrame::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFC드롭다운프레임::리캘크레이아웃](#recalclayout)|드롭다운 프레임의 위치를 바립니다.|
|[CMFC드롭다운프레임::세트오토토토토토이](#setautodestroy)|하위 드롭다운 도구 모음 창이 자동으로 소멸되는지 여부를 설정합니다.|

### <a name="remarks"></a>설명

이 클래스는 사용자 코드에서 직접 사용할 수 없습니다.

프레임워크는 이 클래스를 사용하여 `CMFCDropDownToolbar` 및 `CMFCDropDownToolbarButton` 클래스에 프레임 동작을 제공합니다. 이러한 클래스에 대한 자세한 내용은 [CMFC드롭다운툴클래스](../../mfc/reference/cmfcdropdowntoolbar-class.md) 및 [CMFC드롭다운툴버튼 클래스를](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `CMFCDropDownFrame` `CFrameWnd` 클래스에서 개체에 대한 포인터를 검색하는 방법과 자식 드롭다운 도구 모음 창을 자동으로 소멸하도록 설정하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFC드롭다운프레임](../../mfc/reference/cmfcdropdownframe-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxdropdowntoolbar.h

## <a name="cmfcdropdownframecreate"></a><a name="create"></a>CMFC드롭다운프레임::만들기

`CMFCDropDownFrame` 개체를 만듭니다.

```
virtual BOOL Create(
    CWnd* pWndParent,
    int x,
    int y,
    CMFCDropDownToolBar* pWndOriginToolbar);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*pWndParent*|【인】 드롭다운 프레임의 상위 창입니다.|
|*x*|【인】 다운 다운 프레임의 위치에 대한 수평 화면 좌표입니다.|
|*Y*|【인】 다운다운 프레임의 위치에 대한 수직 화면 좌표입니다.|
|*pWndOriginToolbar*|【인】 이 메서드가 새 드롭다운 프레임 개체를 채우는 데 사용하는 드롭다운 버튼이 있는 도구 모음입니다.|

### <a name="return-value"></a>Return Value

드롭다운 프레임이 성공적으로 생성된 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 기본 [CMiniFrameWnd:CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) 메서드를 호출하여 WS_POPUP 스타일로 드롭다운 프레임 창을 만듭니다. 드롭다운 프레임 창이 지정된 화면 좌표에 나타납니다. [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) 메서드가 FALSE를 반환하는 경우 이 메서드가 실패합니다.

클래스는 `CMFCDropDownFrame` 제공된 `CMFCDropDownToolBar` 매개 변수의 복사본을 만듭니다. 이 메서드는 `pWndOriginToolbar` 매개 변수에서 데이터 멤버로 `m_pWndOriginToolbar` 단추 이미지와 단추 상태를 복사합니다.

## <a name="cmfcdropdownframegetparentmenubar"></a><a name="getparentmenubar"></a>CMFC드롭다운프레임::GetParentMenuBar

드롭다운 프레임의 상위 메뉴 모음을 검색합니다.

```
CMFCMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>Return Value

드롭다운 프레임의 상위 메뉴 모음에 대한 포인터 또는 프레임에 부모가 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

이 메서드는 부모 단추에서 부모 메뉴 모음을 검색합니다. 이 메서드는 드롭다운 프레임에 상위 버튼이 없거나 상위 단추에 상위 메뉴 모음이 없는 경우 NULL을 반환합니다.

## <a name="cmfcdropdownframegetparentpopupmenu"></a><a name="getparentpopupmenu"></a>CMFC드롭다운프레임::GetParentPopupMenu

드롭다운 프레임의 상위 팝업 메뉴를 검색합니다.

```
CMFCDropDownFrame* GetParentPopupMenu() const;
```

### <a name="return-value"></a>Return Value

드롭다운 프레임의 상위 드롭다운 메뉴에 대한 포인터 또는 프레임에 부모가 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

이 메서드는 부모 단추에서 부모 메뉴를 검색합니다. 이 메서드는 드롭다운 프레임에 상위 버튼이 없거나 상위 단추에 상위 메뉴가 없는 경우 NULL을 반환합니다.

## <a name="cmfcdropdownframerecalclayout"></a><a name="recalclayout"></a>CMFC드롭다운프레임::리캘크레이아웃

드롭다운 프레임의 위치를 바립니다.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*bNotify*|【인】 하지 않는.|

### <a name="remarks"></a>설명

프레임워크는 드롭다운 프레임이 만들어지거나 부모 창의 크기를 조정할 때 이 메서드를 호출합니다. 이 메서드는 상위 창의 위치와 크기를 사용 하 여 드롭다운 프레임의 위치와 크기를 계산 합니다.

## <a name="cmfcdropdownframesetautodestroy"></a><a name="setautodestroy"></a>CMFC드롭다운프레임::세트오토토토토토이

하위 드롭다운 도구 모음 창이 자동으로 소멸되는지 여부를 설정합니다.

```cpp
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*b오토파괴*<br/>
【인】 TRUE는 연결된 드롭다운 도구 모음 창을 자동으로 파괴합니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

*bAutoDestroyTRUE이면* `CMFCDropDownFrame` 소멸자가 연결된 드롭다운 도구 모음 창을 파괴합니다. 기본값은 TRUE입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC드롭다운툴바 클래스](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFC드롭다운툴버튼 클래스](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
