---
title: CAtlPreviewCtrlImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Create
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Destroy
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Focus
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::OnPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Redraw
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetHost
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetPreviewVisuals
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetRect
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::DoPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_plf
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrBack
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrText
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
ms.openlocfilehash: 1ccd01bc4d48dc088538f4799b595cce3fb910ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321363"
---
# <a name="catlpreviewctrlimpl-class"></a>CAtlPreviewCtrlImpl 클래스

이 클래스는 리치 미리 보기에 대 한 셸에서 제공 하는 호스트 창에 배치 되는 창의 ATL 구현입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAtl프리뷰CtrlImpl:::~CAtl프리뷰CtrlImpl](#dtor)|미리 보기 컨트롤 개체를 소멸합니다.|
|[CAtl프리뷰CtrlImpl::CAtl프리뷰CtrlImpl](#catlpreviewctrlimpl)|미리 보기 컨트롤 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAtl프리뷰CtrlImpl::만들기](#create)|리치 미리 보기 처리기에 의해 호출되어 Windows 창을 만듭니다.|
|[카틀프프렉트릴임플::D에스트로이](#destroy)|이 컨트롤을 삭제해야 할 때 리치 미리 보기 처리기에 의해 호출됩니다.|
|[CAtl프리뷰CtrlImpl::포커스](#focus)|이 컨트롤에 입력 포커스를 설정합니다.|
|[카틀프프렉트릴임플::온페인트](#onpaint)|WM_PAINT 메시지를 처리합니다.|
|[CAtl프리뷰CtrlImpl::다시 그리기](#redraw)|이 컨트롤을 다시 그리도록 지시합니다.|
|[CAtl프리뷰CtrlImpl::SetHost](#sethost)|이 컨트롤에 대한 새 부모를 설정합니다.|
|[CAtl프리뷰CtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|리치 미리 보기 콘텐츠의 시각적 개체를 설정해야 하는 경우 리치 미리 보기 처리기에 의해 호출됩니다.|
|[CAtl프리뷰CtrlImpl::SetRect](#setrect)|이 컨트롤에 대한 새 경계 사각형을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[카틀프프렉트릴임플::D오페인트](#dopaint)|미리 보기를 렌더링하는 프레임워크에서 호출됩니다.|

### <a name="protected-constants"></a>보호상수

|속성|Description|
|----------|-----------------|
|[CAtl프리뷰CtrlImpl::m_plf](#m_plf)|미리 보기 창에 텍스트를 표시하는 데 사용되는 글꼴입니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CAtl프리뷰CtrlImpl::m_clrBack](#m_clrback)|미리 보기 창의 배경 색입니다.|
|[CAtl프리뷰CtrlImpl::m_clrText](#m_clrtext)|미리 보기 창의 텍스트 색상입니다.|

## <a name="remarks"></a>설명

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`TBase`

`ATL::CMessageMap`

`ATL::CWindowImplRoot<TBase>`

`ATL::CWindowImplBaseT<TBase,TWinTraits>`

[ATL:::CWindowImpl\<카틀프프렌플임>](../../atl/reference/cwindowimpl-class.md)

`IPreviewCtrl`

`ATL::CAtlPreviewCtrlImpl`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀프클리프틀.h

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="catlpreviewctrlimpl"></a>CAtl프리뷰CtrlImpl::CAtl프리뷰CtrlImpl

미리 보기 컨트롤 개체를 생성합니다.

```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="dtor"></a>CAtl프리뷰CtrlImpl:::~CAtl프리뷰CtrlImpl

미리 보기 컨트롤 개체를 소멸합니다.

```
virtual ~CAtlPreviewCtrlImpl(void);
```

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimplcreate"></a><a name="create"></a>CAtl프리뷰CtrlImpl::만들기

리치 미리 보기 처리기에 의해 호출되어 Windows 창을 만듭니다.

```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```

### <a name="parameters"></a>매개 변수

*hWnd부모*<br/>
리치 미리 보기에 대해 셸에서 제공하는 호스트 창에 대한 핸들입니다.

*Prc*<br/>
창의 초기 크기와 위치를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimpldestroy"></a><a name="destroy"></a>카틀프프렉트릴임플::D에스트로이

이 컨트롤을 삭제해야 할 때 리치 미리 보기 처리기에 의해 호출됩니다.

```
virtual void Destroy();
```

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimpldopaint"></a><a name="dopaint"></a>카틀프프렉트릴임플::D오페인트

미리 보기를 렌더링하는 프레임워크에서 호출됩니다.

```
virtual void DoPaint(HDC hdc);
```

### <a name="parameters"></a>매개 변수

*Hdc*<br/>
페인팅을 위한 장치 컨텍스트에 대한 핸들입니다.

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimplfocus"></a><a name="focus"></a>CAtl프리뷰CtrlImpl::포커스

이 컨트롤에 입력 포커스를 설정합니다.

```
virtual void Focus();
```

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimplm_clrback"></a><a name="m_clrback"></a>CAtl프리뷰CtrlImpl::m_clrBack

미리 보기 창의 배경 색입니다.

```
COLORREF m_clrBack;
```

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimplm_clrtext"></a><a name="m_clrtext"></a>CAtl프리뷰CtrlImpl::m_clrText

미리 보기 창의 텍스트 색상입니다.

```
COLORREF m_clrText;
```

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimplm_plf"></a><a name="m_plf"></a>CAtl프리뷰CtrlImpl::m_plf

미리 보기 창에 텍스트를 표시하는 데 사용되는 글꼴입니다.

```
const LOGFONTW* m_plf;
```

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimplonpaint"></a><a name="onpaint"></a>카틀프프렉트릴임플::온페인트

WM_PAINT 메시지를 처리합니다.

```
LRESULT OnPaint(
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>매개 변수

*nMsg*<br/>
WM_PAINT 설정합니다.

*wParam*<br/>
이 매개 변수는 사용되지 않습니다.

*lParam*<br/>
이 매개 변수는 사용되지 않습니다.

*bHandled*<br/>
이 함수가 반환되면 TRUE가 포함됩니다.

### <a name="return-value"></a>Return Value

항상 0을 반환합니다.

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimplredraw"></a><a name="redraw"></a>CAtl프리뷰CtrlImpl::다시 그리기

이 컨트롤을 다시 그리도록 지시합니다.

```
virtual void Redraw();
```

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimplsethost"></a><a name="sethost"></a>CAtl프리뷰CtrlImpl::SetHost

이 컨트롤에 대한 새 부모를 설정합니다.

```
virtual void SetHost(HWND hWndParent);
```

### <a name="parameters"></a>매개 변수

*hWnd부모*<br/>
새 상위 창에 대한 핸들입니다.

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>CAtl프리뷰CtrlImpl::SetPreviewVisuals

리치 미리 보기 콘텐츠의 시각적 개체를 설정해야 하는 경우 리치 미리 보기 처리기에 의해 호출됩니다.

```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```

### <a name="parameters"></a>매개 변수

*clrBack*<br/>
미리 보기 창의 배경 색입니다.

*clrText*<br/>
미리 보기 창의 텍스트 색상입니다.

*Plf*<br/>
미리 보기 창에 텍스트를 표시하는 데 사용되는 글꼴입니다.

### <a name="remarks"></a>설명

## <a name="catlpreviewctrlimplsetrect"></a><a name="setrect"></a>CAtl프리뷰CtrlImpl::SetRect

이 컨트롤에 대한 새 경계 사각형을 설정합니다.

```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```

### <a name="parameters"></a>매개 변수

*Prc*<br/>
미리 보기 컨트롤의 새 크기와 위치를 지정합니다.

*bRedraw*<br/>
컨트롤을 다시 그려야 하는지 여부를 지정합니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)
