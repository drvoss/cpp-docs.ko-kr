---
title: IAtlMemMgr 클래스
ms.date: 11/04/2016
f1_keywords:
- IAtlMemMgr
- ATLMEM/ATL::IAtlMemMgr
- ATLMEM/ATL::Allocate
- ATLMEM/ATL::Free
- ATLMEM/ATL::GetSize
- ATLMEM/ATL::Reallocate
helpviewer_keywords:
- IAtlMemMgr class
- memory, managing
- memory, memory manager
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
ms.openlocfilehash: fcecf716e9d865b1b8590a733216576e0da4c2fb
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746006"
---
# <a name="iatlmemmgr-class"></a>IAtlMemMgr 클래스

이 클래스는 메모리 관리자에 대한 인터페이스를 나타냅니다.

## <a name="syntax"></a>구문

```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[할당](#allocate)|메모리 블록을 할당하려면 이 메서드를 호출합니다.|
|[Free](#free)|메모리 블록을 해제하려면 이 메서드를 호출합니다.|
|[GetSize](#getsize)|할당된 메모리 블록의 크기를 검색하려면 이 메서드를 호출합니다.|
|[재할당](#reallocate)|메모리 블록을 재할당하려면 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 [CComHeap,](../../atl/reference/ccomheap-class.md) [CCRTHeap,](../../atl/reference/ccrtheap-class.md) [CLocalHeap,](../../atl/reference/clocalheap-class.md) [CGlobalHeap,](../../atl/reference/cglobalheap-class.md)또는 [CWin32Heap에](../../atl/reference/cwin32heap-class.md)의해 구현됩니다.

> [!NOTE]
> 로컬 및 전역 힙 함수는 다른 메모리 관리 기능보다 느리며 많은 기능을 제공하지 않습니다. 따라서 새 응용 프로그램은 [힙 함수를](/windows/win32/Memory/heap-functions)사용해야 합니다. [CWin32Heap](../../atl/reference/cwin32heap-class.md) 클래스에서 사용할 수 있습니다.

## <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** 아틀렘.h

## <a name="iatlmemmgrallocate"></a><a name="allocate"></a>IAtlMemgr::할당

메모리 블록을 할당하려면 이 메서드를 호출합니다.

```cpp
void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*n바이트*<br/>
새 메모리 블록의 요청된 바이트 수입니다.

### <a name="return-value"></a>Return Value

새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

[IAtlMemgr 호출::무료](#free) 또는 [IAtlMemmgr::이](#reallocate) 메서드에 의해 할당 된 메모리를 해제 하려면 재할당.

### <a name="example"></a>예제

예를 들어 [IAtlMemgr 개요를](../../atl/reference/iatlmemmgr-class.md)참조하십시오.

## <a name="iatlmemmgrfree"></a><a name="free"></a>IAtlMemgr::무료

메모리 블록을 해제하려면 이 메서드를 호출합니다.

```cpp
void Free(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.

### <a name="remarks"></a>설명

[IAtlMemMgr에서](#allocate) 얻은 메모리를 사용 하 여 이 메서드를 사용 하 여 :할당 또는 [IAtlMemMgr::재할당](#reallocate).

### <a name="example"></a>예제

예를 들어 [IAtlMemgr 개요를](../../atl/reference/iatlmemmgr-class.md)참조하십시오.

## <a name="iatlmemmgrgetsize"></a><a name="getsize"></a>IAtlMemgr::GetSize

할당된 메모리 블록의 크기를 검색하려면 이 메서드를 호출합니다.

```
size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메모리 블록의 크기를 바이트로 반환합니다.

### <a name="example"></a>예제

예를 들어 [IAtlMemgr 개요를](../../atl/reference/iatlmemmgr-class.md)참조하십시오.

## <a name="iatlmemmgrreallocate"></a><a name="reallocate"></a>IAtlMemgr::재할당

이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.

```cpp
void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.

*n바이트*<br/>
새 메모리 블록의 요청된 바이트 수입니다.

### <a name="return-value"></a>Return Value

새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

[IAtlMemgr 호출::무료](#free) 또는 [IAtlMemmgr::이](#reallocate) 메서드에 의해 할당 된 메모리를 해제 하려면 재할당.

개념적으로 이 메서드는 기존 메모리를 해제 하 고 새 메모리 블록을 할당 합니다. 실제로 기존 메모리를 확장하거나 다시 사용할 수 있습니다.

### <a name="example"></a>예제

예를 들어 [IAtlMemgr 개요를](../../atl/reference/iatlmemmgr-class.md)참조하십시오.

## <a name="iaxwinambientdispatchget_allowcontextmenu"></a><a name="get_allowcontextmenu"></a>IAxWin 앰비언트 디스패치::get_AllowContextMenu

속성은 `AllowContextMenu` 호스트된 컨트롤이 자체 컨텍스트 메뉴를 표시할 수 있는지 여부를 지정합니다.

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>매개 변수

*pbAllow컨텍스트메뉴*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_allowshowui"></a><a name="get_allowshowui"></a>IAxWin 앰비언트 디스패치::get_AllowShowUI

속성은 `AllowShowUI` 호스팅된 컨트롤이 자체 사용자 인터페이스를 표시할 수 있는지 여부를 지정합니다.

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>매개 변수

*pbAllowShowui*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_FALSE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_allowwindowlessactivation"></a><a name="get_allowwindowlessactivation"></a>IAxWin 앰비언트 디스패치::get_AllowWindowlessActivation

이 `AllowWindowlessActivation` 속성은 컨테이너가 창 없는 활성화를 허용할지 여부를 지정합니다.

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>매개 변수

*pbAllow창없는*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_backcolor"></a><a name="get_backcolor"></a>IAxWin 앰비언트 디스패치::get_BackColor

속성은 `BackColor` 컨테이너의 주변 배경색을 지정합니다.

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>매개 변수

*pclr배경*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 COLOR_BTNFACE 또는 COLOR_WINDOW 이 속성의 기본값으로 사용합니다(호스트 창의 부모가 대화 상자인지 여부에 따라 다름).

## <a name="iaxwinambientdispatchget_displayasdefault"></a><a name="get_displayasdefault"></a>IAxWin 앰비언트 디스패치::get_DisplayAsDefault

`DisplayAsDefault`는 컨트롤이 기본 컨트롤인지 확인할 수 있는 앰비언트 속성입니다.

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>매개 변수

*pbDisplayAsDefault*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_FALSE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_dochostdoubleclickflags"></a><a name="get_dochostdoubleclickflags"></a>IAxWin 앰비언트 디스패치::get_DocHostDoubleClickFlags

속성은 `DocHostDoubleClickFlags` 두 번 클릭에 대 한 응답으로 수행 해야 하는 작업을 지정 합니다.

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>매개 변수

*pdwDocHost더블클릭플래그*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 DOCHOSTUIDBLCLK_DEFAULT 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_dochostflags"></a><a name="get_dochostflags"></a>IAxWin 앰비언트 디스패치::get_DocHostFlags

속성은 `DocHostFlags` 호스트 개체의 사용자 인터페이스 기능을 지정합니다.

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>매개 변수

*pdwDocHostFlags*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 DOCHOSTUIFLAG_NO3DBORDER 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_font"></a><a name="get_font"></a>IAxWin 앰비언트 디스패치::get_Font

속성은 `Font` 컨테이너의 주변 글꼴을 지정합니다.

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
【아웃】 이 속성의 `IFontDisp` 현재 값을 수신하는 데 사용되는 인터페이스 포인터의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 기본 GUI 글꼴 또는 시스템 글꼴을 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_forecolor"></a><a name="get_forecolor"></a>IAxWin 앰비언트 디스패치::get_ForeColor

속성은 `ForeColor` 컨테이너의 주변 전경 색상을 지정합니다.

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>매개 변수

*pclr 전경*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 시스템 창 텍스트 색상을 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_localeid"></a><a name="get_localeid"></a>IAxWin 앰비언트 디스패치::get_LocaleID

속성은 `LocaleID` 컨테이너의 주변 로캘 ID를 지정합니다.

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>매개 변수

*plcidLocaleID*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 사용자의 기본 로캘을 이 속성의 기본값으로 사용합니다.

이 메서드를 사용 하 여 앰비언트 LocalID, 즉 컨트롤이 사용 되는 프로그램의 LocaleID를 검색할 수 있습니다. LocaleID를 알게 되면 코드를 호출하여 리소스 파일 또는 위성 DLL에서 로캘별 캡션, 오류 메시지 텍스트 등을 로드할 수 있습니다.

## <a name="iaxwinambientdispatchget_messagereflect"></a><a name="get_messagereflect"></a>IAxWin 앰비언트 디스패치::get_MessageReflect

앰비언트 속성은 `MessageReflect` 컨테이너가 호스트된 컨트롤에 메시지를 반영할지 여부를 지정합니다.

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>매개 변수

*pbMessage반사*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_optionkeypath"></a><a name="get_optionkeypath"></a>IAxWin 앰비언트 디스패치::get_OptionKeyPath

속성은 `OptionKeyPath` 사용자 설정에 대한 레지스트리 키 경로를 지정합니다.

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>매개 변수

*pbstr옵션키패스*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="iaxwinambientdispatchget_showgrabhandles"></a><a name="get_showgrabhandles"></a>IAxWin 앰비언트 디스패치::get_ShowGrabHandles

`ShowGrabHandles` 주변 속성을 사용하면 컨트롤이 그랩 핸들로 자신을 그려야 하는지 확인할 수 있습니다.

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>매개 변수

*pbShowGrab핸들즈*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 항상 VARIANT_FALSE 이 속성의 값으로 반환합니다.

## <a name="iaxwinambientdispatchget_showhatching"></a><a name="get_showhatching"></a>IAxWin 앰비언트 디스패치::get_ShowHatching

`ShowHatching` 앰비언트 속성을 사용하면 컨트롤이 해치된 자체를 그려야 하는지 확인할 수 있습니다.

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>매개 변수

*pbShowHatching*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 항상 VARIANT_FALSE 이 속성의 값으로 반환합니다.

## <a name="iaxwinambientdispatchget_usermode"></a><a name="get_usermode"></a>IAxWin 앰비언트 디스패치::get_UserMode

속성은 `UserMode` 컨테이너의 주변 사용자 모드를 지정합니다.

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>매개 변수

*pbUserMode*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_allowcontextmenu"></a><a name="put_allowcontextmenu"></a>IAxWin 앰비언트 디스패치::put_allowContextMenu

속성은 `AllowContextMenu` 호스트된 컨트롤이 자체 컨텍스트 메뉴를 표시할 수 있는지 여부를 지정합니다.

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>매개 변수

*b허용컨텍스트메뉴*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_allowshowui"></a><a name="put_allowshowui"></a>IAxWin앰비언트 디스패치::put_AllowShowUI

속성은 `AllowShowUI` 호스팅된 컨트롤이 자체 사용자 인터페이스를 표시할 수 있는지 여부를 지정합니다.

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>매개 변수

*bAllowShowui*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_FALSE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_allowwindowlessactivation"></a><a name="put_allowwindowlessactivation"></a>IAxWin 앰비언트 디스패치::putut_AllowWindow없는 활성화

이 `AllowWindowlessActivation` 속성은 컨테이너가 창 없는 활성화를 허용할지 여부를 지정합니다.

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>매개 변수

*bAllow창없는*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_backcolor"></a><a name="put_backcolor"></a>IAxWin앰비언트 디스패치::put_BackColor

속성은 `BackColor` 컨테이너의 주변 배경색을 지정합니다.

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>매개 변수

*clrBackground*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 COLOR_BTNFACE 또는 COLOR_WINDOW 이 속성의 기본값으로 사용합니다(호스트 창의 부모가 대화 상자인지 여부에 따라 다름).

## <a name="iaxwinambientdispatchput_displayasdefault"></a><a name="put_displayasdefault"></a>IAxWin 앰비언트 디스패치::putut_DisplayAsDefault

`DisplayAsDefault`는 컨트롤이 기본 컨트롤인지 확인할 수 있는 앰비언트 속성입니다.

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>매개 변수

*bDisplayAsDefault*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_FALSE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_dochostdoubleclickflags"></a><a name="put_dochostdoubleclickflags"></a>IAxWin앰비언트 디스패치::put_DocHost더블클릭플래그

속성은 `DocHostDoubleClickFlags` 두 번 클릭에 대 한 응답으로 수행 해야 하는 작업을 지정 합니다.

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>매개 변수

*dwDocHost더블클릭플래그*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 DOCHOSTUIDBLCLK_DEFAULT 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_dochostflags"></a><a name="put_dochostflags"></a>IAxWin앰비언트 디스패치::put_DocHostFlags

속성은 `DocHostFlags` 호스트 개체의 사용자 인터페이스 기능을 지정합니다.

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>매개 변수

*dwDocHostFlags*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 DOCHOSTUIFLAG_NO3DBORDER 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_font"></a><a name="put_font"></a>IAxWin 앰비언트 디스패치::put_글꼴

속성은 `Font` 컨테이너의 주변 글꼴을 지정합니다.

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 기본 GUI 글꼴 또는 시스템 글꼴을 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_forecolor"></a><a name="put_forecolor"></a>IAxWin앰비언트 디스패치::put_ForeColor

속성은 `ForeColor` 컨테이너의 주변 전경 색상을 지정합니다.

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>매개 변수

*클러 포그라운드*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 시스템 창 텍스트 색상을 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_localeid"></a><a name="put_localeid"></a>IAxWin앰비언트 디스패치::put_LocaleID

속성은 `LocaleID` 컨테이너의 주변 로캘 ID를 지정합니다.

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>매개 변수

*lcidLocaleID*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 사용자의 기본 로캘을 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_messagereflect"></a><a name="put_messagereflect"></a>IAxWin 앰비언트 디스패치::put_MessageReflect

앰비언트 속성은 `MessageReflect` 컨테이너가 호스트된 컨트롤에 메시지를 반영할지 여부를 지정합니다.

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>매개 변수

*bMessageReflect*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_optionkeypath"></a><a name="put_optionkeypath"></a>IAxWin 앰비언트 디스패치::put_OptionKeyPath

속성은 `OptionKeyPath` 사용자 설정에 대한 레지스트리 키 경로를 지정합니다.

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>매개 변수

*브스트옵션키패스*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="iaxwinambientdispatchput_usermode"></a><a name="put_usermode"></a>IAxWin 앰비언트 디스패치::put_UserMode

속성은 `UserMode` 컨테이너의 주변 사용자 모드를 지정합니다.

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>매개 변수

*bUserMode*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a>IAxWin 앰비언트 디스패치Ex::세트앰비언트 디스패치

이 메서드는 사용자 정의 인터페이스와 기본 앰비언트 속성 인터페이스를 보완 하기 위해 호출 됩니다.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>매개 변수

*p디스패치*<br/>
새 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

새 `SetAmbientDispatch` 인터페이스에 대한 포인터로 호출될 때 이 새 인터페이스는 [IAxWinAmbientDispatch에서](../../atl/reference/iaxwinambientdispatch-interface.md)해당 속성이 아직 제공되지 않은 경우 호스팅 컨트롤에서 요청한 속성 이나 메서드를 호출하는 데 사용됩니다.

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a>IAxWinHostWindow::연결 제어

*hWnd로*식별된 창을 사용하여 기존(이전에 초기화) 컨트롤을 호스트 개체에 연결합니다.

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*펀크 컨트롤*<br/>
【인】 호스트 개체에 `IUnknown` 연결할 컨트롤의 인터페이스에 대한 포인터입니다.

*Hwnd*<br/>
【인】 호스팅에 사용할 창에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a>IAxWinHostWindow::만들기 제어

컨트롤을 만들고 초기화하며 *hWnd로*식별된 창에서 컨트롤을 호스트합니다.

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>매개 변수

*lpTricsData*<br/>
【인】 만들 컨트롤을 식별하는 문자열입니다. CLSID(중괄호포함), ProgID, URL 또는 원시 **HTML(MSHTML:** 접두사)일 수 있습니다.

*Hwnd*<br/>
【인】 호스팅에 사용할 창에 대한 핸들입니다.

*pStream*<br/>
【인】 컨트롤에 대한 초기화 데이터가 포함된 스트림에 대한 인터페이스 포인터입니다. NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 창은 이 인터페이스를 노출하는 호스트 개체에 의해 하위 분류되므로 메시지가 컨트롤에 반영되고 다른 컨테이너 기능이 작동합니다.

이 메서드를 호출하는 것은 [IAxWinHostWindow::CreateControlEx](#createcontrolex)를 호출하는 것과 같습니다.

라이센스가 부여된 ActiveX 컨트롤을 만들려면 [IAxWinHostWindowLic::CreateControlLic](#createcontrollicex)을 참조하십시오.

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a>IAxWinHostWindow::만들기 제어 Ex

ActiveX 컨트롤을 만들고 초기화하며 [IAxWinHostWindow::CreateControl](#createcontrol)과 유사한 지정된 창에서 호스트합니다.

```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```

### <a name="parameters"></a>매개 변수

*lpTricsData*<br/>
【인】 만들 컨트롤을 식별하는 문자열입니다. CLSID(중괄호포함), ProgID, URL 또는 원시 **HTML(MSHTML 접두사:**)일 수 있습니다.

*Hwnd*<br/>
【인】 호스팅에 사용할 창에 대한 핸들입니다.

*pStream*<br/>
【인】 컨트롤에 대한 초기화 데이터가 포함된 스트림에 대한 인터페이스 포인터입니다. NULL일 수 있습니다.

*ppunk*<br/>
【아웃】 생성된 컨트롤의 `IUnknown` 인터페이스를 수신하는 포인터의 주소입니다. NULL일 수 있습니다.

*리드어드*<br/>
【인】 포함된 개체에 나가는 인터페이스의 인터페이스 식별자입니다. IID_NULL 수 있습니다.

*펑크어드바이드*<br/>
【인】 에 의해 `IUnknown` 지정된 포함된 개체의 연결 점에 연결할 싱크 개체의 `iidSink`인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

메서드와 `CreateControl` 달리 `CreateControlEx` 새로 만든 컨트롤에 대한 인터페이스 포인터를 수신하고 컨트롤에서 발생된 이벤트를 수신하도록 이벤트 싱크를 설정할 수도 있습니다.

라이센스가 부여된 ActiveX 컨트롤을 만들려면 [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)를 참조하십시오.

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a>IAxWinHostWindow::쿼리 제어

호스트된 컨트롤에서 제공하는 지정된 인터페이스 포인터를 반환합니다.

```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
【인】 요청되는 컨트롤의 인터페이스 ID입니다.

*ppvObject*<br/>
【아웃】 생성된 컨트롤의 지정된 인터페이스를 수신하는 포인터의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>IAxWinHostWindow::Set외부 디스패치

[IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) 메서드를 통해 포함 된 컨트롤에 사용할 수 있는 외부 dispinterface를 설정 합니다.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
【인】 인터페이스에 대한 `IDispatch` 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>IAxWinHostWindow::SetexternalUIHandler

이 함수를 호출하여 개체에 대한 외부 [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) 인터페이스를 설정합니다. `CAxWindow`

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
【인】 인터페이스에 대한 `IDocHostUIHandlerDispatch` 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 함수는 인터페이스에 대한 호스트의 사이트를 쿼리하는 컨트롤(예: `IDocHostUIHandlerDispatch` 웹 브라우저 컨트롤)에서 사용됩니다.

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a>IAxWinHost윈도우릭::컨트롤릭 만들기

라이센스가 부여된 컨트롤을 만들고 초기화하며 `hWnd`로 식별된 창에서 호스트합니다.

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>매개 변수

*블스트릭*<br/>
【인】 컨트롤에 대한 라이센스 키가 포함된 BSTR입니다.

### <a name="remarks"></a>설명

나머지 매개 변수 및 반환 값에 대한 설명은 [IAxWinHostWindow::CreateControl을](#createcontrol) 참조하십시오.

이 메서드를 호출하는 것은 [IAxWinHostWindowLic::CreateControlLicEx를](#createcontrollicex) 호출하는 것과 같습니다.

### <a name="example"></a>예제

을 사용하는 `IAxWinHostWindowLic::CreateControlLic`샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a>IAxWinHost윈도우릭::만들기제어

라이선스가 부여된 ActiveX 컨트롤을 만들고, 초기화하고, [IAxWinHostWindow::CreateControl](#createcontrol)과 유사한 지정된 창에서 호스트합니다.

```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```

### <a name="parameters"></a>매개 변수

*블스트릭*<br/>
【인】 컨트롤에 대한 라이센스 키가 포함된 BSTR입니다.

### <a name="remarks"></a>설명

나머지 매개 변수 및 반환 값에 대한 설명은 [IAxWinHostWindow::CreateControlEx를](#createcontrolex) 참조하십시오.

### <a name="example"></a>예제

을 사용하는 `IAxWinHostWindowLic::CreateControlLicEx`샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)
