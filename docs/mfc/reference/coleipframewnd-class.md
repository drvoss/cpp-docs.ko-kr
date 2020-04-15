---
title: 콜레IP프레임, 클래스
ms.date: 11/04/2016
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
helpviewer_keywords:
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
ms.openlocfilehash: 01e259cf01c42add26088b0cbd2f6dab311eb9b1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374952"
---
# <a name="coleipframewnd-class"></a>콜레IP프레임, 클래스

애플리케이션의 내부 편집 창의 기준입니다.

## <a name="syntax"></a>구문

```
class COleIPFrameWnd : public CFrameWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레IP프레임 Wnd:::콜레IP프레임](#coleipframewnd)|`COleIPFrameWnd` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[콜레IP프레임Wnd::온크리에이드컨트롤바](#oncreatecontrolbars)|항목이 내부 편집을 위해 활성화될 때 프레임워크에서 호출됩니다.|
|[콜레IP프레임Wnd::재배치프레임](#repositionframe)|프레임워크에서 호출하여 현재 편집 창의 위치를 지정합니다.|

## <a name="remarks"></a>설명

이 클래스는 컨테이너 응용 프로그램의 문서 창 내에서 컨트롤 막대를 만들고 배치합니다. 또한 사용자가 내부 편집 창의 크기를 조정할 때 포함된 [COleResizeBar](../../mfc/reference/coleresizebar-class.md) 개체에서 생성된 알림을 처리합니다.

사용에 `COleIPFrameWnd`대한 자세한 내용은 [활성화](../../mfc/activation-cpp.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="coleipframewndcoleipframewnd"></a><a name="coleipframewnd"></a>콜레IP프레임 Wnd:::콜레IP프레임

개체를 `COleIPFrameWnd` 구성하고 올레인플레이스FRAMEINFO 형식의 구조에 저장되는 해당 상태 정보를 초기화합니다.

```
COleIPFrameWnd();
```

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [OLEINPLACEFRAMEINFO를](/windows/win32/api/oleidl/ns-oleidl-oleinplaceframeinfo) 참조하십시오.

## <a name="coleipframewndoncreatecontrolbars"></a><a name="oncreatecontrolbars"></a>콜레IP프레임Wnd::온크리에이드컨트롤바

프레임워크는 내부 `OnCreateControlBars` 편집을 위해 항목이 활성화될 때 함수를 호출합니다.

```
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,
    CWnd* pWndDoc);

virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,
    CFrameWnd* pWndDoc);
```

### <a name="parameters"></a>매개 변수

*pWnd프레임*<br/>
컨테이너 응용 프로그램의 프레임 창에 대한 포인터입니다.

*pWndDoc*<br/>
컨테이너의 문서 수준 창에 대한 포인터입니다. 컨테이너가 SDI 응용 프로그램인 경우 NULL이 될 수 있습니다.

### <a name="return-value"></a>Return Value

성공에 비제로; 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행하지 않습니다. 컨트롤 막대를 만들 때 필요한 모든 특수 처리를 수행 하려면이 함수를 재정의 합니다.

## <a name="coleipframewndrepositionframe"></a><a name="repositionframe"></a>콜레IP프레임Wnd::재배치프레임

프레임워크는 멤버 `RepositionFrame` 함수를 호출하여 컨트롤 막대를 배치하고 모든 편집 창을 표시하도록 편집 창을 재배치합니다.

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>매개 변수

*lpPosRect*<br/>
클라이언트 영역을 `RECT` 기준으로 `CRect` 현재 프레임 창의 현재 위치 좌표를 포함하는 구조체 또는 객체에 대한 포인터입니다.

*lpClipRect*<br/>
클라이언트 영역을 `RECT` 기준으로 `CRect` 현재 클리핑-사각형 좌표를 포함하는 구조체 또는 객체에 대한 포인터입니다.

### <a name="remarks"></a>설명

컨테이너 창의 컨트롤 막대 레이아웃은 OLE가 아닌 프레임 창에서 수행하는 것과 다릅니다. OLE가 아닌 프레임 창은 [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout)에 대한 호출에서와 같이 지정된 프레임 창 크기에서 컨트롤 막대 및 기타 개체의 위치를 계산합니다. 클라이언트 영역은 컨트롤 막대 및 기타 개체에 대한 공간을 빼고 남은 영역입니다. 반면에 창은 `COleIPFrameWnd` 지정된 클라이언트 영역에 따라 도구 모음을 배치합니다. 즉, `CFrameWnd::RecalcLayout` "외부에서" 작업하는 반면"내부에서 `COleIPFrameWnd::RepositionFrame` 부터 는 작동합니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)
