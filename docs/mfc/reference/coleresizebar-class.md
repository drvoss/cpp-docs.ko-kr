---
title: 콜레레사이즈바 클래스
ms.date: 11/04/2016
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
ms.openlocfilehash: beb0c37b6ac23310b7d5c8506fbdaf677dd74d8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376148"
---
# <a name="coleresizebar-class"></a>콜레레사이즈바 클래스

내부 OLE 항목의 크기 변경을 지원하는 컨트롤 막대의 한 종류입니다.

## <a name="syntax"></a>구문

```
class COleResizeBar : public CControlBar
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레레사이즈바::콜레레사이즈바](#coleresizebar)|`COleResizeBar` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[콜레레사이즈바::만들기](#create)|Windows 자식 창을 만들고 초기화하고 개체에 `COleResizeBar` 연결합니다.|

## <a name="remarks"></a>설명

`COleResizeBar`개체는 해치된 테두리와 외부 크기 조정 핸들이 있는 [CRectTracker로](../../mfc/reference/crecttracker-class.md) 나타납니다.

`COleResizeBar`개체는 일반적으로 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) 클래스에서 파생된 프레임 창 개체의 포함된 멤버입니다.

자세한 내용은 [활성화](../../mfc/activation-cpp.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`COleResizeBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="coleresizebarcoleresizebar"></a><a name="coleresizebar"></a>콜레레사이즈바::콜레레사이즈바

`COleResizeBar` 개체를 생성합니다.

```
COleResizeBar();
```

### <a name="remarks"></a>설명

크기 `Create` 조정 막대 개체를 만들기 위해 호출합니다.

## <a name="coleresizebarcreate"></a><a name="create"></a>콜레레사이즈바::만들기

자식 창을 만들고 `COleResizeBar` 개체와 연결합니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_RESIZE_BAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
크기 조정 막대의 상위 창에 대한 포인터입니다.

*dwStyle*<br/>
[창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 특성을 지정합니다.

*nID*<br/>
크기 조정 막대의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

크기 조정 막대가 만들어진 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="see-also"></a>참고 항목

[MFC 샘플 슈퍼패드](../../overview/visual-cpp-samples.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[콜레서버독 클래스](../../mfc/reference/coleserverdoc-class.md)
