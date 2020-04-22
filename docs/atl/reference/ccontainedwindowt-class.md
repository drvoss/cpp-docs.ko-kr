---
title: CContainedWindowT 클래스
ms.date: 11/04/2016
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
ms.openlocfilehash: 7b89346bbc62cdda808b193a199fdf121f052ebb
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747751"
---
# <a name="ccontainedwindowt-class"></a>CContainedWindowT 클래스

이 클래스는 다른 개체 내에 포함된 창을 구현합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>
class CContainedWindowT : public TBase
```

#### <a name="parameters"></a>매개 변수

*TBase*<br/>
새 클래스의 기본 클래스입니다. 기본 기본 클래스는 . `CWindow`

*TWinTraits*<br/>
창 스타일을 정의하는 특성 클래스입니다. 기본값은 `CControlWinTraits`입니다.

> [!NOTE]
> [CContainedWindow는](ccontainedwindowt-class.md) 의 `CContainedWindowT`전문화입니다. 기본 클래스 나 특성을 변경하려면 `CContainedWindowT` 직접 사용하십시오.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C포함창:::C포함윈도우T](#ccontainedwindowt)|생성자입니다. 데이터 멤버를 초기화하여 포함된 창의 메시지를 처리할 메시지 맵을 지정합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C포함창::만들기](#create)|창을 만듭니다.|
|[CContainedWindowT::DefWindowProc](#defwindowproc)|기본 메시지 처리를 제공합니다.|
|[C포함창::현재 메시지 가져옵니다.](#getcurrentmessage)|현재 메시지를 반환합니다.|
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|포함된 창의 창 클래스를 등록합니다.|
|[C포함창::하위 클래스창](#subclasswindow)|창을 서브클래싱합니다.|
|[CContained창::스위치 메시지맵](#switchmessagemap)|포함된 창의 메시지를 처리하는 데 사용되는 메시지 맵을 변경합니다.|
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|이전에 서브클래싱된 창을 복원합니다.|
|[CContainedWindowT::WindowProc](#windowproc)|(정적) 포함된 창으로 전송된 메시지를 처리합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|포함된 창의 메시지를 처리할 메시지 맵을 식별합니다.|
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|새 창 클래스의 기반이 되는 기존 창 클래스의 이름을 지정합니다.|
|[CContained윈도우:m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|창 클래스의 원본 창 프로시저를 가리킵니다.|
|[CContained윈도우:m_pObject](#m_pobject)|포함된 개체를 가리킵니다.|

## <a name="remarks"></a>설명

`CContainedWindowT`은 다른 개체 내에 포함된 창을 구현합니다. `CContainedWindowT`'의 창 프로시저는 포함된 개체의 메시지 맵을 사용하여 적절한 처리기로 메시지를 배달합니다. 개체를 생성할 `CContainedWindowT` 때 사용할 메시지 맵을 지정합니다.

`CContainedWindowT`을 사용하면 기존 창 클래스를 수퍼클래스로 분류하여 새 창을 만들 수 있습니다. 메서드는 `Create` 먼저 기존 클래스를 기반으로 하지만 을 사용하는 `CContainedWindowT::WindowProc`window 클래스를 등록합니다. `Create`그런 다음 이 새 창 클래스를 기반으로 창을 만듭니다. 각 인스턴스는 `CContainedWindowT` 다른 창 클래스를 수퍼클래스로 분류할 수 있습니다.

`CContainedWindowT`은 또한 창 서브클래싱도 지원합니다. `SubclassWindow` 메서드는 기존 창을 `CContainedWindowT` 개체에 연결하고 창 프로시저를 `CContainedWindowT::WindowProc`로 변경합니다. `CContainedWindowT`의 각 인스턴스는 다른 창을 서브클래싱할 수 있습니다.

> [!NOTE]
> 지정된 `CContainedWindowT` 개체의 경우 `Create` 또는 `SubclassWindow`에 전화하십시오. 동일한 개체에서 두 메서드를 호출해서는 안 됩니다.

ATL 프로젝트 마법사에서 **옵션에 따라 컨트롤 추가를** 사용하면 마법사가 `CContainedWindowT` 컨트롤을 구현하는 클래스에 데이터 멤버를 자동으로 추가합니다. 다음 예제에서는 포함된 창이 선언되는 방법을 보여 주며 있습니다.

[!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]

[!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]

[!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]

|항목|참조|
|--------------------------------|---------|
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|
|ATL에서 창 사용하기|[ATL 윈도우 클래스](../../atl/atl-window-classes.md)|
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|
|Windows|[윈도우](/windows/win32/winmsg/windows) 및 Windows SDK의 후속 항목|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`TBase`

`CContainedWindowT`

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="ccontainedwindowtccontainedwindowt"></a><a name="ccontainedwindowt"></a>C포함창:::C포함윈도우T

생성자는 데이터 멤버를 초기화합니다.

```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>
【인】 포함된 창의 기반이 되는 기존 창 클래스의 이름입니다.

*pObject*<br/>
【인】 메시지 맵을 선언하는 포함 개체에 대한 포인터입니다. 이 개체의 클래스는 [CMessageMap](../../atl/reference/cmessagemap-class.md)에서 파생되어야 합니다.

*dwMsgMapID*<br/>
【인】 포함된 창의 메시지를 처리할 메시지 맵을 식별합니다. 기본값 0은 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)선언된 기본 메시지 맵을 지정합니다. [ALT_MSG_MAP(msgMapID)로](message-map-macros-atl.md#alt_msg_map)선언된 대체 메시지 맵을 사용하려면 을 전달합니다. `msgMapID`

### <a name="remarks"></a>설명

[Create를](#create)통해 새 창을 만들려면 *lpszClassName* 매개 변수에 대한 기존 창 클래스의 이름을 전달해야 합니다. 예를 들어 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 개요를 참조하십시오.

세 가지 생성자가 있습니다.

- 세 개의 인수가 있는 생성자는 일반적으로 호출됩니다.

- 두 개의 인수가 있는 생성자는 `TBase::GetWndClassName`에서 클래스 이름을 사용합니다.

- 나중에 인수를 제공하려는 경우 인수가 없는 생성자가 사용됩니다. 나중에 호출할 `Create`때 창 클래스 이름, 메시지 맵 개체 및 메시지 맵 ID를 제공해야 합니다.

[하위 클래스창을](#subclasswindow)통해 기존 창을 하위 클래스로 지정하는 경우 *lpszClassName* 값이 사용되지 않습니다. 따라서 이 매개 변수에 대해 NULL을 전달할 수 있습니다.

## <a name="ccontainedwindowtcreate"></a><a name="create"></a>C포함창::만들기

기존 클래스를 기반으로 하지만 [CContainedWindowT::WindowProc를](#windowproc)사용 하는 창 클래스를 등록 하려면 [RegisterWndSuperclass](#registerwndsuperclass) 호출 합니다.

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>
【인】 포함된 창의 기반이 되는 기존 창 클래스의 이름입니다.

*pObject*<br/>
【인】 메시지 맵을 선언하는 포함 개체에 대한 포인터입니다. 이 개체의 클래스는 [CMessageMap](../../atl/reference/cmessagemap-class.md)에서 파생되어야 합니다.

*dwMsgMapID*<br/>
【인】 포함된 창의 메시지를 처리할 메시지 맵을 식별합니다. 기본값 0은 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)선언된 기본 메시지 맵을 지정합니다. [ALT_MSG_MAP(msgMapID)로](message-map-macros-atl.md#alt_msg_map)선언된 대체 메시지 맵을 사용하려면 을 전달합니다. `msgMapID`

*hWnd부모*<br/>
【인】 상위 또는 소유자 창에 대한 핸들입니다.

*rect*<br/>
【인】 창의 위치를 지정하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조입니다. 포인터 `RECT` 또는 참조로 전달할 수 있습니다.

*szWindowName*<br/>
【인】 창의 이름을 지정합니다. 기본값은 NULL입니다.

*dwStyle*<br/>
【인】 창의 스타일입니다. 기본값은 &#124; WS_VISIBLE WS_CHILD. 가능한 값 목록은 Windows SDK의 [CreateWindow를](/windows/win32/api/winuser/nf-winuser-createwindoww) 참조하십시오.

*dwExStyle*<br/>
【인】 확장된 창 스타일입니다. 기본값은 0이며 확장 된 스타일이 없음을 의미합니다. 가능한 값 목록은 Windows SDK의 [CreateWindowEx를](/windows/win32/api/winuser/nf-winuser-createwindowexw) 참조하십시오.

*MenuOrID*<br/>
【인】 자식 창의 경우 창 식별자입니다. 최상위 창의 경우 창의 메뉴 핸들입니다. 기본값은 **0U입니다.**

*lpCreateParam*<br/>
【인】 창 만들기 데이터에 대한 포인터입니다. 전체 설명은 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)에 대한 최종 매개 변수에 대한 설명을 참조하십시오.

### <a name="return-value"></a>Return Value

성공하면 새로 만든 창에 대한 핸들입니다. 그렇지 않으면 NULL이 됩니다.

### <a name="remarks"></a>설명

기존 창 클래스 이름이 [m_lpszClassName](#m_lpszclassname)저장됩니다. `Create`그런 다음 이 새 클래스를 기반으로 창을 만듭니다. 새로 만든 창이 개체에 `CContainedWindowT` 자동으로 연결됩니다.

> [!NOTE]
> 이미 [SubclassWindow](#subclasswindow)를 호출한 경우에는 `Create`를 호출하지 마세요.

> [!NOTE]
> 0이 *MenuOrID* 매개 변수의 값으로 사용되는 경우 컴파일러 오류를 방지하려면 0U(기본값)로 지정해야 합니다.

## <a name="ccontainedwindowtdefwindowproc"></a><a name="defwindowproc"></a>CContained윈도우T::D프윈도우프로크

메시지 맵에서 처리되지 않는 메시지를 처리하기 위해 [WindowProc에서](#windowproc) 호출합니다.

```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
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

## <a name="ccontainedwindowtgetcurrentmessage"></a><a name="getcurrentmessage"></a>C포함창::현재 메시지 가져옵니다.

현재 메시지 ()를`m_pCurrentMsg`반환합니다.

```
const _ATL_MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Return Value

구조에 패키지된 현재 `MSG` 메시지입니다.

## <a name="ccontainedwindowtm_dwmsgmapid"></a><a name="m_dwmsgmapid"></a>CContained윈도우::m_dwMsgMapID

현재 포함된 창에 사용 중인 메시지 맵의 식별자를 보유합니다.

```
DWORD m_dwMsgMapID;
```

### <a name="remarks"></a>설명

이 메시지 맵은 포함된 개체에 선언되어야 합니다.

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)선언된 기본 메시지 맵은 항상 0으로 식별됩니다. [ALT_MSG_MAP(msgMapID)로](message-map-macros-atl.md#alt_msg_map)선언된 대체 메시지 맵은 `msgMapID`에 의해 식별됩니다.

`m_dwMsgMapID`생성자에서 먼저 초기화되며 [SwitchMessageMap](#switchmessagemap)을 호출하여 변경할 수 있습니다. 예를 들어 [CContainedWindowT 개요를](../../atl/reference/ccontainedwindowt-class.md)참조하십시오.

## <a name="ccontainedwindowtm_lpszclassname"></a><a name="m_lpszclassname"></a>CContained윈도우::m_lpszClassName

기존 창 클래스의 이름을 지정합니다.

```
LPTSTR m_lpszClassName;
```

### <a name="remarks"></a>설명

창을 만들 때 [만들기는](#create) 이 기존 클래스를 기반으로 하지만 [CContainedWindowT::WindowProc](#windowproc)를 사용하는 새 창 클래스를 등록합니다.

`m_lpszClassName`생성자에 의해 초기화됩니다. 예를 들어 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) 개요를 참조하십시오.

## <a name="ccontainedwindowtm_pfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a>CContained윈도우:m_pfnSuperWindowProc

포함된 창이 하위 클래스인 `m_pfnSuperWindowProc` 경우 창 클래스의 원래 창 프로시저를 가리킵니다.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>설명

포함된 창이 과칭된 경우 기존 클래스를 수정하는 창 클래스를 기반으로 `m_pfnSuperWindowProc` 하며, 기존 창 클래스의 창 프로시저를 가리킵니다.

[DefWindowProc](#defwindowproc) 메서드는 에 `m_pfnSuperWindowProc`저장된 창 프로시저로 메시지 정보를 보냅니다.

## <a name="ccontainedwindowtm_pobject"></a><a name="m_pobject"></a>CContained윈도우:m_pObject

개체를 포함하는 개체를 `CContainedWindowT` 가리킵니다.

```
CMessageMap* m_pObject;
```

### <a name="remarks"></a>설명

[클래스가 CMessageMap에서](../../atl/reference/cmessagemap-class.md)파생되어야 하는 이 컨테이너는 포함된 창에서 사용하는 메시지 맵을 선언합니다.

`m_pObject`생성자에 의해 초기화됩니다. 예를 들어 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) 개요를 참조하십시오.

## <a name="ccontainedwindowtregisterwndsuperclass"></a><a name="registerwndsuperclass"></a>CContained윈도우::레지스터WndSuperclass

포함된 창의 창 클래스를 등록하려면 [만들기에서](#create) 호출합니다.

```
ATOM RegisterWndSuperClass();
```

### <a name="return-value"></a>Return Value

성공하면 등록된 창 클래스를 고유하게 식별하는 원자; 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 창 클래스는 기존 클래스를 기반으로 하지만 [CContainedWindowT::WindowProc](#windowproc)을 사용합니다. 기존 창 클래스의 이름과 창 프로시저는 각각 [m_lpszClassName](#m_lpszclassname) [및 m_pfnSuperWindowProc](#m_pfnsuperwindowproc)저장됩니다.

## <a name="ccontainedwindowtsubclasswindow"></a><a name="subclasswindow"></a>C포함창::하위 클래스창

*hWnd로* 식별된 창을 하위 클래스로 `CContainedWindowT` 분류하고 개체에 연결합니다.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
【인】 하위 분류되는 창에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

TRUE 창이 성공적으로 하위 분류된 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

하위 분류된 창은 이제 [CContainedWindowT::WindowProc](#windowproc)을 사용합니다. 원래 창 프로시저가 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)저장됩니다.

> [!NOTE]
> 이미 [Create](#create)를 호출한 경우에는 `SubclassWindow`를 호출하지 마세요.

## <a name="ccontainedwindowtswitchmessagemap"></a><a name="switchmessagemap"></a>CContained창::스위치 메시지맵

포함된 창의 메시지를 처리하는 데 사용할 메시지 맵을 변경합니다.

```cpp
void SwitchMessageMap(DWORD dwMsgMapID);
```

### <a name="parameters"></a>매개 변수

*dwMsgMapID*<br/>
【인】 메시지 맵 식별자입니다. [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)선언된 기본 메시지 맵을 사용하려면 0을 전달합니다. [ALT_MSG_MAP(msgMapID)로](message-map-macros-atl.md#alt_msg_map)선언된 대체 메시지 맵을 사용하려면 을 전달합니다. `msgMapID`

### <a name="remarks"></a>설명

메시지 맵은 포함된 개체에 정의되어야 합니다.

처음에 생성자에서 메시지 맵 식별자를 지정합니다.

## <a name="ccontainedwindowtunsubclasswindow"></a><a name="unsubclasswindow"></a>C포함창::하위 클래스 창

`CContainedWindowT` 개체에서 하위 분류된 창을 분리하고 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)저장된 원래 창 프로시저를 복원합니다.

```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```

### <a name="parameters"></a>매개 변수

*bForce*<br/>
【인】 TRUE로 설정하여 이 `CContainedWindowT` 개체의 창 프로시저가 현재 활성화되어 있지 않더라도 원래 창 프로시저를 강제로 복원합니다. *bForce가* FALSE로 설정되어 있고 이 `CContainedWindowT` 개체의 창 프로시저가 현재 활성화되어 있지 않으면 원래 창 프로시저가 복원되지 않습니다.

### <a name="return-value"></a>Return Value

이전에 하위 클래스가 된 창에 대한 핸들입니다. *bForce가* FALSE로 설정되어 있고 이 `CContainedWindowT` 개체의 창 프로시저가 현재 활성화되어 있지 않으면 NULL을 반환합니다.

### <a name="remarks"></a>설명

창이 소멸되기 전에 원래 창 프로시저를 복원하려는 경우에만 이 메서드를 사용합니다. 그렇지 않으면 창이 소멸되면 [WindowProc이](#windowproc) 자동으로 이 작업을 수행합니다.

## <a name="ccontainedwindowtwindowproc"></a><a name="windowproc"></a>C포함창::윈도우프로크

이 정적 메서드는 창 프로시저를 구현합니다.

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

`WindowProc`m_dwMsgMapID [식별된](#m_dwmsgmapid)메시지 맵으로 메시지를 배달합니다. 필요한 경우 `WindowProc` 추가 메시지 처리를 위해 [DefWindowProc에](#defwindowproc) 호출합니다.

## <a name="see-also"></a>참조

[C윈도우 클래스](../../atl/reference/cwindow-class.md)<br/>
[크윈도우임플 클래스](../../atl/reference/cwindowimpl-class.md)<br/>
[CMessageMap 클래스](../../atl/reference/cmessagemap-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
