---
title: CDockablePane어댑터 클래스
ms.date: 11/04/2016
f1_keywords:
- CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::GetWrappedWnd
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::LoadState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SaveState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SetWrappedWnd
helpviewer_keywords:
- CDockablePaneAdapter [MFC], GetWrappedWnd
- CDockablePaneAdapter [MFC], LoadState
- CDockablePaneAdapter [MFC], SaveState
- CDockablePaneAdapter [MFC], SetWrappedWnd
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
ms.openlocfilehash: 2fbaf99e4cc9bcbecf1a94012713b34e986f7ecb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375588"
---
# <a name="cdockablepaneadapter-class"></a>CDockablePane어댑터 클래스

`CWnd`파생 창에 대해 도킹 지원을 제공합니다.

## <a name="syntax"></a>구문

```
class CDockablePaneAdapter : public CDockablePane
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDockablePane어댑터::GetWrappedD](#getwrappedwnd)|래핑된 창을 반환합니다.|
|[CDockablePaneAdapter::LoadState](#loadstate)|[(CDockablePane 재정의::로드 상태.)](cdockablepane-class.md#loadstate)|
|[CDockablePaneAdapter::SaveState](#savestate)|[(CDockablePane 재정의::SaveState.)](cdockablepane-class.md)|
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||

## <a name="remarks"></a>설명

일반적으로 프레임워크는 [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) 또는 [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) 메서드를 사용할 때 이 클래스의 개체를 인스턴스화합니다.

동작을 `CDockablePaneAdapter` 사용자 지정하려면 새 클래스를 파생하고 [CMFCBaseTabCtrl::SetDockingBarWrapperRTC를](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc)사용하여 런타임 클래스 정보를 탭된 창으로 설정하면 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[Cobject](../../mfc/reference/cobject-class.md)\
❏&nbsp;[CCmd Target](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[크파네](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[독킹파인](../../mfc/reference/cdockablepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[독커블파네어댑터](../../mfc/reference/cdockablepaneadapter-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDockablePaneAdapter.h

## <a name="cdockablepaneadaptergetwrappedwnd"></a><a name="getwrappedwnd"></a>CDockablePane어댑터::GetWrappedD

도킹 가능한 창 어댑터의 기본 창을 반환합니다.

```
virtual CWnd* GetWrappedWnd() const;
```

### <a name="return-value"></a>Return Value

래핑된 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 래핑된 창에 액세스합니다.

## <a name="cdockablepaneadapterloadstate"></a><a name="loadstate"></a>CDockablePane어댑터::로드스테이트

레지스트리에서 창의 상태를 로드합니다.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 프로필 이름입니다.

*nIndex*<br/>
【인】 프로파일 인덱스입니다.

*uiID*<br/>
【인】 창 ID입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockablepaneadaptersavestate"></a><a name="savestate"></a>CDockablePane어댑터::저장 상태

창의 상태를 레지스트리에 저장합니다.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 프로필 이름입니다.

*nIndex*<br/>
【인】 프로파일 인덱스(기본적으로 창의 컨트롤 ID)입니다.

*uiID*<br/>
【인】 창 ID입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdockablepaneadaptersetwrappedwnd"></a><a name="setwrappedwnd"></a>CDockablePane어::설정 포장 된 Wnd

도킹 가능한 창 어댑터의 기본 창을 설정합니다.

```
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 창 어댑터가 래핑할 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)
