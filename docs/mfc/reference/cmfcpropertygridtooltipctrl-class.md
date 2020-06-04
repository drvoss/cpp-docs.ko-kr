---
title: CMFCPropertyGridToolTipCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Create
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Deactivate
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::GetLastRect
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Hide
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::SetTextMargin
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Track
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl [MFC], CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl [MFC], Create
- CMFCPropertyGridToolTipCtrl [MFC], Deactivate
- CMFCPropertyGridToolTipCtrl [MFC], GetLastRect
- CMFCPropertyGridToolTipCtrl [MFC], Hide
- CMFCPropertyGridToolTipCtrl [MFC], SetTextMargin
- CMFCPropertyGridToolTipCtrl [MFC], Track
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
ms.openlocfilehash: fc5d6d99c326fba7020e8c5040c3bf28d09f8f0a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754123"
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl 클래스

[CMFCPropertyGridCtrl 클래스가](../../mfc/reference/cmfcpropertygridctrl-class.md) 도구 팁을 표시하는 데 사용하는 도구 설명 컨트롤을 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCPropertyGridToolTipCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|[CMFCProperty그리드툴팁트르:::CMFC프로퍼티그리드툴팁Ctrl](#cmfcpropertygridtooltipctrl)|`CMFCPropertyGridToolTipCtrl` 개체를 생성합니다.|
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|[CMFCProperty그리드툴팁Ctrl::만들기](#create)|도구 설명 컨트롤에 대한 창을 만듭니다.|
|[CMFC속성그리드툴팁트르::D](#deactivate)|도구 설명 컨트롤을 비활성화하고 숨깁니다.|
|[CMFCProperty그리드툴팁트르::겟라스트렉트](#getlastrect)|도구 설명 컨트롤의 마지막 위치의 좌표를 반환합니다.|
|[CMFCProperty그리드툴팁트르::숨기기](#hide)|도구 설명 컨트롤을 숨깁니다.|
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|창 메시지가 [TranslateMessage](../../mfc/reference/cwinapp-class.md) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) Windows 함수로 디스패치되기 전에 [CWinApp](/windows/win32/api/winuser/nf-winuser-dispatchmessage) 클래스가 이 메시지를 해석하는 데 사용됩니다. ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 재정의합니다.)|
|[CMFCProperty그리드툴팁트rl::세트텍스트마진](#settextmargin)|도구 설명 텍스트와 도구 설명 창의 테두리 사이의 간격을 설정합니다.|
|[CMFC속성그리드툴팁트르:::트랙](#track)|도구 설명 컨트롤을 표시합니다.|

## <a name="remarks"></a>설명

포인터가 속성 이름에 있을 때 도구 설명이 표시됩니다. [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) 클래스는 사용자가 쉽게 읽을 수 있도록 도구 설명이 표시됩니다. 일반적으로 도구 설명의 위치는 포인터의 위치에 따라 결정됩니다. 이 클래스를 사용하면 도구 설명이 속성 이름 위에 나타나고 속성 이름이 완전히 표시되도록 자연 속성 확장과 유사합니다.

MFC는 자동으로 이 컨트롤을 만들고 [CMFCPropertyGridCtrl 클래스에서](../../mfc/reference/cmfcpropertygridctrl-class.md)사용합니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCPropertyGridToolTipCtrl` 클래스의 개체를 생성 하는 방법 및 도구 설명 컨트롤을 표시 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFC프로퍼티그리드툴팁트르](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpropertygridtooltipctrl.h

## <a name="cmfcpropertygridtooltipctrlcmfcpropertygridtooltipctrl"></a><a name="cmfcpropertygridtooltipctrl"></a>CMFCProperty그리드툴팁트르:::CMFC프로퍼티그리드툴팁Ctrl

`CMFCPropertyGridToolTipCtrl` 개체를 생성합니다.

```
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```

## <a name="cmfcpropertygridtooltipctrlcreate"></a><a name="create"></a>CMFCProperty그리드툴팁Ctrl::만들기

도구 설명 컨트롤에 대한 창을 만듭니다.

```
BOOL Create(CWnd* pWndParent);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 상위 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 창이 성공적으로 생성된 경우 그렇지 않으면 false입니다.

## <a name="cmfcpropertygridtooltipctrldeactivate"></a><a name="deactivate"></a>CMFC속성그리드툴팁트르::D

도구 설명 컨트롤을 비활성화하고 숨깁니다.

```cpp
void Deactivate();
```

### <a name="remarks"></a>설명

이 메서드는 마지막 위치와 텍스트를 빈 값으로 설정하여 나중에 [CMFCPropertyGridToolTipCtrl::Track에](#track) 대한 호출이 도구 설명에 표시되도록 합니다.

## <a name="cmfcpropertygridtooltipctrlgetlastrect"></a><a name="getlastrect"></a>CMFCProperty그리드툴팁트르::겟라스트렉트

도구 설명 컨트롤의 마지막 위치의 좌표를 반환합니다.

```cpp
void GetLastRect(CRect& rect) const;
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【아웃】 도구 설명 컨트롤의 마지막 위치를 포함합니다.

## <a name="cmfcpropertygridtooltipctrlhide"></a><a name="hide"></a>CMFCProperty그리드툴팁트르::숨기기

도구 설명 컨트롤을 숨깁니다.

```cpp
void Hide();
```

## <a name="cmfcpropertygridtooltipctrlsettextmargin"></a><a name="settextmargin"></a>CMFCProperty그리드툴팁트rl::세트텍스트마진

도구 설명 텍스트와 도구 설명 창의 테두리 사이의 간격을 설정합니다.

```cpp
void SetTextMargin(int nTextMargin);
```

### <a name="parameters"></a>매개 변수

*n텍스트마진*<br/>
【인】 도구 설명 컨트롤 텍스트와 도구 설명 창의 테두리 사이의 간격을 지정합니다. 기본값은 10픽셀입니다.

## <a name="cmfcpropertygridtooltipctrltrack"></a><a name="track"></a>CMFC속성그리드툴팁트르:::트랙

도구 설명 컨트롤을 표시합니다.

```cpp
void Track(
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 툴팁 컨트롤의 위치와 크기를 지정합니다.

*strText*<br/>
【인】 도구 설명에 표시할 텍스트를 지정합니다.

### <a name="remarks"></a>설명

이 메서드는 정류에 의해 지정된 위치와 크기로 도구 설명 컨트롤을 *표시합니다.* 이 메서드가 마지막으로 호출된 이후 위치, 크기 및 텍스트가 변경되지 않은 경우 이 메서드는 영향을 주지 않습니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
