---
title: CMFC베이스툴바 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar::GetDockingMode
- AFXBASETOOLBAR/CMFCBaseToolBar::GetMinSize
- AFXBASETOOLBAR/CMFCBaseToolBar::OnAfterChangeParent
helpviewer_keywords:
- CMFCBaseToolBar [MFC], GetDockingMode
- CMFCBaseToolBar [MFC], GetMinSize
- CMFCBaseToolBar [MFC], OnAfterChangeParent
ms.assetid: 5d79206d-55e4-46f8-b1b8-042e34d7f9da
ms.openlocfilehash: 027fe8569ff133bb3f348c9d0607f19c6d778c4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367837"
---
# <a name="cmfcbasetoolbar-class"></a>CMFC베이스툴바 클래스

도구 모음의 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CMFCBaseToolBar : public CPane
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCBaseToolBar::CMFCBaseToolBar`|기본 생성자입니다.|
|`CMFCBaseToolBar::~CMFCBaseToolBar`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CMFCBaseToolBar::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFC베이스툴바::겟도킹모드](#getdockingmode)|도킹 모드를 반환합니다. [(재정의 CBasePane::GetDockingMode.)](../../mfc/reference/cbasepane-class.md#getdockingmode)|
|[CMFC베이스툴바::겟민사이즈](#getminsize)|도구 모음의 최소 크기를 반환합니다. [(재정의 CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|
|[CMFC베이스툴바::온애프터체인지부모](#onafterchangeparent)|창의 부모가 변경된 후 프레임워크에서 호출됩니다. [(재정의 CBasePane::OnAfterChangeParent](../../mfc/reference/cbasepane-class.md#onafterchangeparent).)|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFC베이스툴바](../../mfc/reference/cmfcbasetoolbar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxbasetoolbar.h

## <a name="cmfcbasetoolbargetdockingmode"></a><a name="getdockingmode"></a>CMFC베이스툴바::겟도킹모드

도킹 모드를 반환합니다.

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>Return Value

도킹 모드입니다.

## <a name="cmfcbasetoolbargetminsize"></a><a name="getminsize"></a>CMFC베이스툴바::겟민사이즈

도구 모음의 최소 크기를 반환합니다.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>매개 변수

*크기*<br/>
【아웃】 도구 모음의 최소 크기입니다.

## <a name="cmfcbasetoolbaronafterchangeparent"></a><a name="onafterchangeparent"></a>CMFC베이스툴바::온애프터체인지부모

창의 부모가 변경된 후 프레임워크에서 호출됩니다.

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>매개 변수

*pWndOld부모*<br/>
【인】 이전 부모 창에 대한 포인터입니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
