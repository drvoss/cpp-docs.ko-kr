---
title: 크윈도우임플 클래스
ms.date: 11/04/2016
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::CWindowImpl::DefWindowProc
- ATLWIN/ATL::CWindowImpl::GetCurrentMessage
- ATLWIN/ATL::CWindowImpl::GetWindowProc
- ATLWIN/ATL::CWindowImpl::OnFinalMessage
- ATLWIN/ATL::CWindowImpl::SubclassWindow
- ATLWIN/ATL::CWindowImpl::UnsubclassWindow
- ATLWIN/ATL::CWindowImpl::GetWndClassInfo
- ATLWIN/ATL::CWindowImpl::WindowProc
- ATLWIN/ATL::CWindowImpl::m_pfnSuperWindowProc
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
ms.openlocfilehash: ea150195f06d12cd6549b9026714d9e1bbf392df
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745989"
---
# <a name="cwindowimpl-class"></a>크윈도우임플 클래스

창을 만들거나 서브클래싱하기 위한 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
`CWindowImpl`에서 파생된 새 클래스입니다.

*TBase*<br/>
클래스의 기본 클래스입니다. 기본적으로 기본 클래스는 [CWindow](../../atl/reference/cwindow-class.md)입니다.

*TWinTraits*<br/>
창의 스타일을 정의하는 [특성 클래스입니다.](../../atl/understanding-window-traits.md) 기본값은 `CControlWinTraits`입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CWindow Impl::만들기](#create)|창을 만듭니다.|

### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT 메서드

|||
|-|-|
|[DefWindowProc](#defwindowproc)|기본 메시지 처리를 제공합니다.|
|[GetCurrentMessage](#getcurrentmessage)|현재 메시지를 반환합니다.|
|[GetWindowProc](#getwindowproc)|현재 창 프로시저를 반환합니다.|
|[OnFinalMessage](#onfinalmessage)|마지막 메시지를 받은 후 호출됩니다(일반적으로 WM_NCDESTROY).|
|[SubclassWindow](#subclasswindow)|창을 서브클래싱합니다.|
|[UnsubclassWindow](#unsubclasswindow)|이전에 서브클래싱된 창을 복원합니다.|

### <a name="static-methods"></a>정적 메서드

|||
|-|-|
|[GetWndClassInfo](#getwndclassinfo)|창 클래스 정보를 관리하는 [CWndClassInfo의](../../atl/reference/cwndclassinfo-class.md)정적 인스턴스를 반환합니다.|
|[WindowProc](#windowproc)|창으로 보내는 메시지를 처리합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|창 클래스의 원본 창 프로시저를 가리킵니다.|

## <a name="remarks"></a>설명

창을 만들거나 기존 창을 하위 클래스로 만들 수 있습니다. `CWindowImpl` `CWindowImpl` 창 프로시저는 메시지 맵을 사용하여 적절한 처리기로 메시지를 배달합니다.

`CWindowImpl::Create`[CWndClassInfo에서](../../atl/reference/cwndclassinfo-class.md)관리하는 창 클래스 정보를 기반으로 창을 만듭니다. `CWindowImpl`DECLARE_WND_CLASS [매크로를](window-class-macros.md#declare_wnd_class) 포함하므로 `CWndClassInfo` 새 창 클래스를 등록합니다. 기존 window 클래스를 수퍼클래스로 지정하려면 `CWindowImpl` [클래스를](window-class-macros.md#declare_wnd_superclass) 파생시키고 DECLARE_WND_SUPERCLASS 매크로를 포함합니다. 이 경우 `CWndClassInfo`는 기존 클래스를 기반으로 하는 창 클래스 등록하지만 `CWindowImpl::WindowProc`를 사용합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]

> [!NOTE]
> `CWndClassInfo`는 한 윈도우 클래스의 정보만 관리하기 때문에, `CWindowImpl`의 인스턴스를 통해 생성된 각 창은 동일한 창 클래스를 기반으로 합니다.

`CWindowImpl`은 또한 창 서브클래싱도 지원합니다. `SubclassWindow` 메서드는 기존 창을 `CWindowImpl` 개체에 연결하고 창 프로시저를 `CWindowImpl::WindowProc`로 변경합니다. `CWindowImpl`의 각 인스턴스는 다른 창을 서브클래싱할 수 있습니다.

> [!NOTE]
> 지정된 `CWindowImpl` 개체의 경우 `Create` 또는 `SubclassWindow`에 전화하십시오. 동일한 개체에서 두 메서드를 모두 호출하지는 마십시오.

`CWindowImpl`또한 ATL은 [CContainedWindow를](../../atl/reference/ccontainedwindowt-class.md) 제공하여 다른 개체에 포함된 창을 만듭니다.

기본 클래스 소멸자(~)는 `CWindowImplRoot`개체가 소멸되기 전에 창이 사라졌음을 확인합니다.

`CWindowImpl`에서 `CWindowImplBaseT`파생 되는 에서 `CWindowImplRoot`파생 된 및 `TBase` [CMessageMap에서](../../atl/reference/cmessagemap-class.md)파생 됩니다.

|항목|참조|
|--------------------------------|---------|
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|
|ATL에서 창 사용하기|[ATL 윈도우 클래스](../../atl/atl-window-classes.md)|
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CWindowImplBaseT`

`CWindowImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="cwindowimplcreate"></a><a name="create"></a>CWindow Impl::만들기

새 창 클래스를 기반으로 창을 만듭니다.

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="parameters"></a>매개 변수

*hWnd부모*<br/>
【인】 상위 또는 소유자 창에 대한 핸들입니다.

*rect*<br/>
【인】 창의 위치를 지정하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조입니다. 포인터 `RECT` 또는 참조로 전달할 수 있습니다.

*szWindowName*<br/>
【인】 창의 이름을 지정합니다. 기본값은 NULL입니다.

*dwStyle*<br/>
【인】 창의 스타일입니다. 이 값은 창에 대한 특성 클래스에서 제공하는 스타일과 결합됩니다. 기본값은 특성 클래스가 스타일을 완전히 제어할 수 있게 합니다. 가능한 값 목록은 Windows SDK의 [CreateWindow를](/windows/win32/api/winuser/nf-winuser-createwindoww) 참조하십시오.

*dwExStyle*<br/>
【인】 확장된 창 스타일입니다. 이 값은 창에 대한 특성 클래스에서 제공하는 스타일과 결합됩니다. 기본값은 특성 클래스가 스타일을 완전히 제어할 수 있게 합니다. 가능한 값 목록은 Windows SDK의 [CreateWindowEx를](/windows/win32/api/winuser/nf-winuser-createwindowexw) 참조하십시오.

*MenuOrID*<br/>
【인】 자식 창의 경우 창 식별자입니다. 최상위 창의 경우 창의 메뉴 핸들입니다. 기본값은 **0U입니다.**

*lpCreateParam*<br/>
【인】 창 만들기 데이터에 대한 포인터입니다. 전체 설명은 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)에 대한 최종 매개 변수에 대한 설명을 참조하십시오.

### <a name="return-value"></a>Return Value

성공하면 새로 만든 창에 대한 핸들입니다. 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

`Create`먼저 아직 등록되지 않은 경우 창 클래스를 등록합니다. 새로 만든 창이 개체에 `CWindowImpl` 자동으로 연결됩니다.

> [!NOTE]
> 이미 [SubclassWindow](#subclasswindow)를 호출한 경우에는 `Create`를 호출하지 마세요.

기존 창 클래스를 기반으로 하는 window 클래스를 사용하려면 `CWindowImpl` [클래스를](window-class-macros.md#declare_wnd_superclass) 파생시키고 DECLARE_WND_SUPERCLASS 매크로를 포함합니다. 기존 창 클래스의 창 프로시저가 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)저장됩니다. 자세한 내용은 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 개요를 참조하십시오.

> [!NOTE]
> 0이 *MenuOrID* 매개 변수의 값으로 사용되는 경우 컴파일러 오류를 방지하려면 0U(기본값)로 지정해야 합니다.

## <a name="cwindowimpldefwindowproc"></a><a name="defwindowproc"></a>CWindowImpl::D프윈도우프로크

메시지 맵에서 처리되지 않는 메시지를 처리하기 위해 [WindowProc에서](#windowproc) 호출합니다.

```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```

### <a name="parameters"></a>매개 변수

*uMsg*<br/>
【인】 창으로 전송된 메시지입니다.

*wParam*<br/>
【인】 추가 메시지 관련 정보입니다.

*lParam*<br/>
【인】 추가 메시지 관련 정보입니다.

### <a name="return-value"></a>Return Value

메시지 처리의 결과입니다.

### <a name="remarks"></a>설명

기본적으로 `DefWindowProc` [CallWindowProc](/windows/win32/api/winuser/nf-winuser-callwindowprocw) Win32 함수를 호출하여 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)지정된 창 프로시저로 메시지 정보를 보냅니다.

매개 변수가 없는 함수는 현재 메시지에서 필요한 매개 변수를 자동으로 검색합니다.

## <a name="cwindowimplgetcurrentmessage"></a><a name="getcurrentmessage"></a>CWindow 임플::GetCurrentMessage

구조에 패키지된 현재 메시지를 `MSG` 반환합니다.

```
const MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Return Value

현재 메시지입니다.

## <a name="cwindowimplgetwindowproc"></a><a name="getwindowproc"></a>CWindow 임플::겟윈도우프로크

반환 `WindowProc`, 현재 창 프로시저입니다.

```
virtual WNDPROC GetWindowProc();
```

### <a name="return-value"></a>Return Value

현재 창 프로시저입니다.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 창 프로시저를 사용자 고유의 프로시저로 바꿉꿉습니다.

## <a name="cwindowimplgetwndclassinfo"></a><a name="getwndclassinfo"></a>Cwindow 임플:::GetWndClassInfo

창 클래스 정보에 액세스하려면 [Create에서](#create) 호출합니다.

```
static CWndClassInfo& GetWndClassInfo();
```

### <a name="return-value"></a>Return Value

[CWndClassInfo의](../../atl/reference/cwndclassinfo-class.md)정적 인스턴스 .

### <a name="remarks"></a>설명

기본적으로 새 `CWindowImpl` 창 클래스를 지정하는 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) 매크로를 통해 이 메서드를 가져옵니다.

기존 창 클래스를 수퍼클래스로 `CWindowImpl` 분류하려면 클래스를 파생시키고 `GetWndClassInfo`재정의할 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로를 포함합니다. 자세한 내용은 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 개요를 참조하십시오.

DECLARE_WND_CLASS 및 DECLARE_WND_SUPERCLASS 매크로를 사용하는 것 `GetWndClassInfo` 외에도 고유한 구현으로 재정의할 수 있습니다.

## <a name="cwindowimplm_pfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a>CWindow 임플::m_pfnSuperWindowProc

창에 따라 다음 창 절차 중 하나를 가리킵니다.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>설명

|창 유형|창 절차|
|--------------------|----------------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) 매크로를 통해 지정된 새 창 클래스를 기반으로 하는 창입니다.|[DefWindowProc](/windows/win32/api/winuser/nf-winuser-defwindowprocw) Win32 기능입니다.|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로를 통해 지정된 기존 클래스를 수정하는 창 클래스를 기반으로 하는 창입니다.|기존 창 클래스의 창 프로시저입니다.|
|하위 클래스창입니다.|하위 클래스창의 원래 창 프로시저를 참조하십시오.|

[CWindowImpl::DefWindowProc에](#defwindowproc) `m_pfnSuperWindowProc`저장된 창 프로시저에 메시지 정보를 보냅니다.

## <a name="cwindowimplonfinalmessage"></a><a name="onfinalmessage"></a>CWindow 임플::에 최종 메시지

마지막 메시지를 받은 후 호출됩니다(일반적으로 WM_NCDESTROY).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
【인】 파괴되는 창에 대한 핸들입니다.

### <a name="remarks"></a>설명

기본 구현은 `OnFinalMessage` 아무 것도 수행하지 않지만 창을 파괴하기 전에 정리를 처리하기 위해이 함수를 재정의 할 수 있습니다. 창 소멸 시 개체를 자동으로 삭제하려면 이 함수에서 **삭제를** 호출할 수 있습니다.

## <a name="cwindowimplsubclasswindow"></a><a name="subclasswindow"></a>CWindow 임플::하위 클래스창

*hWnd로* 식별된 창을 하위 클래스로 `CWindowImpl` 분류하고 개체에 연결합니다.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
【인】 하위 분류되는 창에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

TRUE 창이 성공적으로 하위 분류된 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

하위 분류된 창은 이제 [CWindowImpl::WindowProc](#windowproc)을 사용합니다. 원래 창 프로시저가 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)저장됩니다.

> [!NOTE]
> 이미 [Create](#create)를 호출한 경우에는 `SubclassWindow`를 호출하지 마세요.

## <a name="cwindowimplunsubclasswindow"></a><a name="unsubclasswindow"></a>CWindow 임플::하위 클래스창

`CWindowImpl` 개체에서 하위 분류된 창을 분리하고 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)저장된 원래 창 프로시저를 복원합니다.

```
HWND UnsubclassWindow();
```

### <a name="return-value"></a>Return Value

이전에 하위 클래스가 된 창에 대한 핸들입니다.

## <a name="cwindowimplwindowproc"></a><a name="windowproc"></a>CWindow임플:::윈도우프로크

이 정적 함수는 창 프로시저를 구현합니다.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
【인】 창에 대한 핸들입니다.

*uMsg*<br/>
【인】 창으로 전송된 메시지입니다.

*wParam*<br/>
【인】 추가 메시지 관련 정보입니다.

*lParam*<br/>
【인】 추가 메시지 관련 정보입니다.

### <a name="return-value"></a>Return Value

메시지 처리의 결과입니다.

### <a name="remarks"></a>설명

`WindowProc`BEGIN_MSG_MAP 선언된 기본 메시지 [맵을](message-map-macros-atl.md#begin_msg_map)사용하여 적절한 처리기로 메시지를 배달합니다. 필요한 경우 `WindowProc` 추가 메시지 처리를 위해 [DefWindowProc에](#defwindowproc) 호출합니다. 최종 메시지가 처리되지 않으면 `WindowProc` 다음을 수행합니다.

- 창이 하위 클래스가 없는 경우 하위 클래스를 해제합니다.

- `m_hWnd`을 지웁니다.

- 창이 소멸되기 전에 [OnFinalMessage를](#onfinalmessage) 호출합니다.

메시지를 처리하기 `WindowProc` 위한 다른 메커니즘을 제공하기 위해 재정의할 수 있습니다.

## <a name="see-also"></a>참조

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
