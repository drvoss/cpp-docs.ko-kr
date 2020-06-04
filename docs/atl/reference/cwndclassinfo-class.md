---
title: CWndClassInfo 클래스
ms.date: 11/04/2016
f1_keywords:
- CWndClassInfo
- ATLWIN/ATL::CWndClassInfo
- ATLWIN/ATL::Register
- ATLWIN/ATL::m_atom
- ATLWIN/ATL::m_bSystemCursor
- ATLWIN/ATL::m_lpszCursorID
- ATLWIN/ATL::m_lpszOrigName
- ATLWIN/ATL::m_szAutoName
- ATLWIN/ATL::m_wc
- ATLWIN/ATL::pWndProc
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
ms.openlocfilehash: 01706bf61c3b977c28998325ece68724cfbc7452
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330332"
---
# <a name="cwndclassinfo-class"></a>CWndClassInfo 클래스

이 클래스는 창 클래스에 대 한 정보를 등록 하는 메서드를 제공 합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CWndClassInfo
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|[등록](#register)|창 클래스를 등록합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_atom](#m_atom)|등록된 창 클래스를 고유하게 식별합니다.|
|[m_bSystemCursor](#m_bsystemcursor)|커서 리소스가 시스템 커서또는 모듈 리소스에 포함된 커서를 참조하는지 여부를 지정합니다.|
|[m_lpszCursorID](#m_lpszcursorid)|커서 리소스의 이름을 지정합니다.|
|[m_lpszOrigName](#m_lpszorigname)|기존 창 클래스의 이름을 포함 합니다.|
|[m_szAutoName](#m_szautoname)|창 클래스의 ATL 생성 이름을 보유합니다.|
|[m_wc](#m_wc)|구조에서 창 클래스 `WNDCLASSEX` 정보를 유지 관리합니다.|
|[pWndProc](#pwndproc)|기존 창 클래스의 창 프로시저를 가리킵니다.|

## <a name="remarks"></a>설명

`CWndClassInfo`창 클래스의 정보를 관리합니다. 일반적으로 다음 `CWndClassInfo` 표에 설명된 대로 DECLARE_WND_CLASS, DECLARE_WND_CLASS_EX 또는 DECLARE_WND_SUPERCLASS 세 가지 매크로 중 하나를 통해 사용합니다.

|매크로|Description|
|-----------|-----------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo`새 창 클래스에 대한 정보를 등록합니다.|
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo`은 클래스 매개 변수를 포함하여 새 창 클래스에 대한 정보를 등록합니다.|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo`기존 클래스를 기반으로 하지만 다른 창 프로시저를 사용하는 창 클래스에 대한 정보를 등록합니다. 이 기술을 수퍼 클래스링이라고 합니다.|

기본적으로 [CWindowImpl에는](../../atl/reference/cwindowimpl-class.md) 새 `DECLARE_WND_CLASS` 창 클래스를 기반으로 창을 만드는 매크로가 포함됩니다. DECLARE_WND_CLASS 컨트롤의 기본 스타일과 배경색을 제공합니다. 스타일과 배경 색을 직접 지정하려면 클래스에서 파생되고 클래스 정의에 `CWindowImpl` DECLARE_WND_CLASS_EX 매크로를 포함합니다.

기존 window 클래스를 기반으로 창을 만들려면 클래스에서 파생되고 클래스 정의에 `CWindowImpl` DECLARE_WND_SUPERCLASS 매크로를 포함합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

창 클래스에 대한 자세한 내용은 Windows SDK의 [창 클래스를](/windows/win32/winmsg/window-classes) 참조하십시오.

ATL에서 창 사용에 대 한 자세한 내용은 [ATL 창 클래스](../../atl/atl-window-classes.md)문서를 참조 하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="cwndclassinfom_atom"></a><a name="m_atom"></a>CWndClass정보::m_atom

등록된 창 클래스의 고유 식별자를 포함합니다.

```
ATOM m_atom;
```

## <a name="cwndclassinfom_bsystemcursor"></a><a name="m_bsystemcursor"></a>CWndClassInfo::m_bSystemCursor

TRUE이면 창 클래스가 등록될 때 시스템 커서 리소스가 로드됩니다.

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>설명

그렇지 않으면 모듈에 포함된 커서 리소스가 로드됩니다.

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ([CWindowImpl](../../atl/reference/cwindowimpl-class.md)의 기본값) 또는 [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) 매크로가 지정 된 `CWndClassInfo` 경우에만 `m_bSystemCursor`를 사용합니다. 이 경우 `m_bSystemCursor` TRUE로 초기화됩니다. 자세한 내용은 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 개요를 참조하십시오.

## <a name="cwndclassinfom_lpszcursorid"></a><a name="m_lpszcursorid"></a>CWndClassInfo::m_lpszCursorID

커서 리소스의 이름 또는 낮은 순서 의 단어에서 리소스 식별자를 지정하고 높은 순서의 단어에서 0을 지정합니다.

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>설명

창 클래스가 등록되면 `m_lpszCursorID` [m_wc](#m_wc)의해 식별된 커서에 대한 핸들을 검색하여 저장합니다.

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ([CWindowImpl](../../atl/reference/cwindowimpl-class.md)의 기본값) 또는 [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) 매크로가 지정 된 `CWndClassInfo` 경우에만 `m_lpszCursorID`를 사용합니다. 이 경우 `m_lpszCursorID` IDC_ARROW 초기화됩니다. 자세한 내용은 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 개요를 참조하십시오.

## <a name="cwndclassinfom_lpszorigname"></a><a name="m_lpszorigname"></a>CWndClassInfo::m_lpszOrigName

기존 창 클래스의 이름을 포함 합니다.

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>설명

`CWndClassInfo`클래스 `m_lpszOrigName` 정의에 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로를 포함하는 경우에만 사용합니다. 이 경우 `CWndClassInfo` `m_lpszOrigName`에서 명명된 클래스를 기반으로 창 클래스를 등록합니다. 자세한 내용은 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 개요를 참조하십시오.

## <a name="cwndclassinfom_szautoname"></a><a name="m_szautoname"></a>CWndClassInfo::m_szAutoName

창 클래스의 이름을 보유합니다.

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>설명

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class), [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) 또는 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)에 대해 NULL이 `WndClassName`매개 변수에 전달 되는 `CWndClassInfo` 경우에만 `m_szAutoName`를 사용합니다. ATL은 창 클래스가 등록될 때 이름을 생성합니다.

## <a name="cwndclassinfom_wc"></a><a name="m_wc"></a>CWndClassInfo::m_wc

[WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw) 구조에서 창 클래스 정보를 유지 관리합니다.

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>설명

[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) `m_wc` [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) [DECLARE_WND_CLASS(CWindowImpl의](../../atl/reference/cwindowimpl-class.md)기본값) 또는 DECLARE_WND_CLASS_EX 매크로를 지정한 경우 새 창 클래스에 대한 정보가 포함됩니다.

[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로를 지정한 `m_wc` 경우 기존 클래스를 기반으로 하지만 다른 창 프로시저를 사용하는 창 클래스인 수퍼클래스에 대한 정보가 들어 있습니다. [m_lpszOrigName](#m_lpszorigname) 및 [pWndProc은](#pwndproc) 각각 기존 창 클래스의 이름과 창 프로시저를 저장합니다.

## <a name="cwndclassinfopwndproc"></a><a name="pwndproc"></a>CWndClassInfo::pWndProc

기존 창 클래스의 창 프로시저를 가리킵니다.

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>설명

`CWndClassInfo`클래스 `pWndProc` 정의에 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로를 포함하는 경우에만 사용합니다. 이 경우 `CWndClassInfo` 기존 클래스를 기반으로 하지만 다른 창 프로시저를 사용 하는 창 클래스를 등록 합니다. 기존 창 클래스의 창 프로시저가 에 저장됩니다. `pWndProc` 자세한 내용은 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 개요를 참조하십시오.

## <a name="cwndclassinforegister"></a><a name="register"></a>CWndClass정보::등록

[CWindowImpl::아직](../../atl/reference/cwindowimpl-class.md#create) 등록되지 않은 경우 창 클래스를 등록하도록 만들기

```
ATOM Register(WNDPROC* pProc);
```

### <a name="parameters"></a>매개 변수

*pProc*<br/>
【아웃】 기존 창 클래스의 원래 창 프로시저를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 등록중인 창 클래스를 고유하게 식별하는 원자입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) `Register` [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) [DECLARE_WND_CLASS(CWindowImpl의](../../atl/reference/cwindowimpl-class.md)기본값) 또는 DECLARE_WND_CLASS_EX 매크로를 지정한 경우 새 창 클래스를 등록합니다. 이 경우 *pProc* 매개 변수가 사용되지 않습니다.

[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로를 지정한 `Register` 경우 기존 클래스를 기반으로 하지만 다른 창 프로시저를 사용하는 창 클래스인 수퍼 클래스를 등록합니다. 기존 창 클래스의 창 프로시저가 *pProc로*반환됩니다.

## <a name="see-also"></a>참고 항목

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
