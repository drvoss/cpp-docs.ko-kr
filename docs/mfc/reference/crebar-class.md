---
title: CReBar 클래스
ms.date: 11/19/2018
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
helpviewer_keywords:
- CReBar [MFC], AddBar
- CReBar [MFC], Create
- CReBar [MFC], GetReBarCtrl
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
ms.openlocfilehash: c1379d1ef8effea0df564da1b43769bb9a11435d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363937"
---
# <a name="crebar-class"></a>CReBar 클래스

rebar 컨트롤의 레이아웃, 지속성 및 상태 정보를 제공하는 컨트롤 막대입니다.

## <a name="syntax"></a>구문

```
class CReBar : public CControlBar
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CReBar::애드바](#addbar)|철근에 밴드를 추가합니다.|
|[CReBar::만들기](#create)|철근 컨트롤을 만들고 오브젝트에 `CReBar` 연결합니다.|
|[CReBar::GetReBarCtrl](#getrebarctrl)|기본 공통 컨트롤에 직접 액세스할 수 있습니다.|

## <a name="remarks"></a>설명

철근 개체에는 편집 상자, 도구 모음 및 목록 상자를 비롯한 다양한 하위 창(일반적으로 다른 컨트롤)이 포함될 수 있습니다. 철근 객체는 지정된 비트맵 위에 자식 창을 표시할 수 있습니다. 응용 프로그램에서 자동으로 적용 막대의 크기를 조정하거나 그리퍼 막대를 클릭하거나 드래그하여 철근의 크기를 수동으로 조정할 수 있습니다.

![RebarMenu의 예](../../mfc/reference/media/vc4sc61.gif "RebarMenu의 예")

## <a name="rebar-control"></a>철근 제어

철근 객체는 도구 모음 오브젝트와 유사하게 행동합니다. 철근은 클릭 앤 드래그 메커니즘을 사용하여 밴드의 크기를 조정합니다. rebar 컨트롤은 그리퍼 막대, 비트맵, 텍스트 레이블 및 자식 창이 조합된 하나 이상의 밴드를 포함할 수 있습니다. 그러나 밴드는 둘 이상의 자식 창을 포함할 수 없습니다.

`CReBar`에서는 [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) 클래스를 사용하여 구현을 제공합니다. [GetReBarCtrl을](#getrebarctrl) 통해 철근 컨트롤에 액세스하여 컨트롤의 사용자 지정 옵션을 활용할 수 있습니다. 철근 컨트롤에 대한 자세한 `CReBarCtrl`내용은 을 참조하십시오. 철근 컨트롤 사용에 대한 자세한 내용은 [CReBarCtrl 사용을](../../mfc/using-crebarctrl.md)참조하십시오.

> [!CAUTION]
> 철근 및 철근 컨트롤 개체는 MFC 컨트롤 표시줄 도킹을 지원하지 않습니다. 호출된 경우 `CRebar::EnableDocking` 응용 프로그램이 어설션합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="crebaraddbar"></a><a name="addbar"></a>CReBar::애드바

이 멤버 함수를 호출하여 단고막대에 밴드를 추가합니다.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
철근에 `CWnd` 삽입할 하위 창인 개체에 대한 포인터입니다. 참조된 개체에는 WS_CHILD 있어야 합니다.

*lpszText*<br/>
철근에 표시할 텍스트가 포함된 문자열에 대한 포인터입니다. 기본적으로 NULL입니다. *lpszText에* 포함된 텍스트는 자식 창의 일부가 아닙니다. 철근 자체에 있습니다.

*pbmp*<br/>
철근 배경에 표시할 `CBitmap` 개체에 대한 포인터입니다. 기본적으로 NULL입니다.

*dwStyle*<br/>
철근에 적용할 스타일을 포함하는 DWORD입니다. 밴드 `fStyle` 스타일의 전체 목록은 Win32 구조 [REBARBANDINFO의](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) 함수 설명을 참조하십시오.

*clrFore*<br/>
철근의 전경 색상을 나타내는 COLORREF 값입니다.

*clrBack*<br/>
검고조 막대의 배경색을 나타내는 COLORREF 값입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

## <a name="crebarcreate"></a><a name="create"></a>CReBar::만들기

이 멤버 함수를 호출하여 단고막대를 만듭니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
Windows 창이 `CWnd` 상태 표시줄의 상위 인 개체에 대한 포인터입니다. 일반적으로 프레임 창.

*dwCtrl스타일*<br/>
철근 컨트롤 스타일입니다. 기본적으로 RBS_BANDBORDERS 철근 컨트롤 내에서 인접 밴드를 분리하기 위해 좁은 선을 표시합니다. 스타일 목록은 Windows SDK의 [철근 컨트롤 스타일을](/windows/win32/Controls/rebar-control-styles) 참조하십시오.

*dwStyle*<br/>
철근 창 스타일입니다.

*nID*<br/>
단조고명의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  [CReBar::AddBar](#addbar)에 대한 예제를 참조하십시오.

## <a name="crebargetrebarctrl"></a><a name="getrebarctrl"></a>CReBar::GetReBarCtrl

이 멤버 함수를 사용하면 기본 공통 컨트롤에 직접 액세스할 수 있습니다.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Return Value

[CReBarCtrl](../../mfc/reference/crebarctrl-class.md) 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 호출하여 철근 사용자 지정시 Windows 철근 공통 컨트롤의 기능을 활용합니다. 호출할 `GetReBarCtrl`때 참조 개체를 `CReBarCtrl` 반환하므로 멤버 함수 집합 중 하나를 사용할 수 있습니다.

철근을 사용자 `CReBarCtrl` 지정하는 데 사용하는 데 사용하는 자세한 내용은 [CReBarCtrl 사용](../../mfc/using-crebarctrl.md)을 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>참고 항목

[MFC 샘플 MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
