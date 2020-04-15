---
title: CComControl 클래스
ms.date: 11/04/2016
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
ms.openlocfilehash: 3518de3596748fa284c1f898b69d1576903e9510
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320762"
---
# <a name="ccomcontrol-class"></a>CComControl 클래스

이 클래스는 ATL 컨트롤을 만들고 관리하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T, class WinBase = CWindowImpl<T>>
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컨트롤을 구현하는 클래스입니다.

*윈베이스*<br/>
창 기능을 구현하는 기본 클래스입니다. 기본값은 [CWindowImpl](../../atl/reference/cwindowimpl-class.md).

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComControl::CComControl](#ccomcontrol)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComControl::제어 쿼리 인터페이스](#controlqueryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|
|[CComControl::만들기 제어 창](#createcontrolwindow)|컨트롤에 대한 창을 만듭니다.|
|[CComControl:::파이어온변경](#fireonchanged)|컨테이너의 싱크에 제어 속성이 변경되었음을 지정합니다.|
|[CComControl::FireonRequestedit](#fireonrequestedit)|컨테이너의 싱크에 제어 속성이 변경될 것이고 개체가 싱크에 진행 방법을 묻고 있음을 지정합니다.|
|[CComControl::메시지 상자](#messagebox)|이 메서드를 호출하여 메시지 상자를 만들고 표시하고 조작합니다.|

## <a name="remarks"></a>설명

`CComControl`는 ATL 컨트롤에 유용한 제어 도우미 함수 및 필수 데이터 멤버 집합입니다. ATL 컨트롤 마법사를 사용하여 표준 컨트롤 또는 DHTML 컨트롤을 만들면 마법사가 `CComControl`에서 클래스를 자동으로 파생시됩니다. `CComControl`[CComControlBase에서](../../atl/reference/ccomcontrolbase-class.md)대부분의 메서드를 파생합니다.

컨트롤 을 만드는 것에 대한 자세한 내용은 [ATL 자습서를](../../atl/active-template-library-atl-tutorial.md)참조하십시오. ATL 프로젝트 마법사에 대한 자세한 내용은 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)문서를 참조하십시오.

메서드 및 `CComControl` 데이터 멤버에 대한 데모는 [CIRC](../../overview/visual-cpp-samples.md) 샘플을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

`CComControl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="ccomcontrolccomcontrol"></a><a name="ccomcontrol"></a>CComControl::CComControl

생성자입니다.

```
CComControl();
```

### <a name="remarks"></a>설명

[CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) 생성자 호출하여 `m_hWnd` [CWindowImpl을](../../atl/reference/cwindowimpl-class.md)통해 상속된 데이터 멤버를 전달합니다.

## <a name="ccomcontrolcontrolqueryinterface"></a><a name="controlqueryinterface"></a>CComControl::제어 쿼리 인터페이스

요청된 인터페이스에 대한 포인터를 검색합니다.

```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 요청되는 인터페이스의 GUID입니다.

*ppv*<br/>
【아웃】 인터페이스를 찾을 수 없는 경우 *iid*또는 NULL로 식별된 인터페이스 포인터에 대한 포인터입니다.

### <a name="remarks"></a>설명

COM 맵 테이블의 인터페이스만 처리합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]

## <a name="ccomcontrolcreatecontrolwindow"></a><a name="createcontrolwindow"></a>CComControl::만들기 제어 창

기본적으로 를 호출하여 `CWindowImpl::Create`컨트롤에 대한 창을 만듭니다.

```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```

### <a name="parameters"></a>매개 변수

*hWnd부모*<br/>
【인】 상위 또는 소유자 창에 핸들을 보입니다. 유효한 창 핸들을 제공해야 합니다. 컨트롤 창은 부모 창의 영역에 국한됩니다.

*rcPos*<br/>
【인】 작성할 창의 초기 크기 및 위치입니다.

### <a name="remarks"></a>설명

단일 창을 만드는 것 이외의 작업을 수행하려는 경우 이 메서드를 재정의하여 두 개의 창을 만들수 있으며 그 중 하나는 컨트롤의 도구 모음이 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]

## <a name="ccomcontrolfireonchanged"></a><a name="fireonchanged"></a>CComControl:::파이어온변경

컨테이너의 싱크에 제어 속성이 변경되었음을 지정합니다.

```
HRESULT FireOnChanged(DISPID dispID);
```

### <a name="parameters"></a>매개 변수

*dispID*<br/>
【인】 변경된 속성의 식별자입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

컨트롤 클래스가 [IPropertyNotifySink에서](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)파생되는 경우 이 메서드는 [CFirePropNotifyEvent::FireOnChanged를](cfirepropnotifyevent-class.md#fireonchanged) 호출하여 연결된 모든 `IPropertyNotifySink` 인터페이스에 지정된 제어 속성이 변경되었음을 알립니다. 컨트롤 클래스에서 `IPropertyNotifySink`파생 되지 않는 경우이 메서드는 S_OK 반환 합니다.

이 메서드는 컨트롤이 연결 지점을 지원하지 않는 경우에도 호출해도 안전합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]

## <a name="ccomcontrolfireonrequestedit"></a><a name="fireonrequestedit"></a>CComControl::FireonRequestedit

컨테이너의 싱크에 제어 속성이 변경될 것이고 개체가 싱크에 진행 방법을 묻고 있음을 지정합니다.

```
HRESULT FireOnRequestEdit(DISPID dispID);
```

### <a name="parameters"></a>매개 변수

*dispID*<br/>
【인】 변경하려는 속성의 식별자입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

컨트롤 클래스가 [IPropertyNotifySink에서](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)파생되는 경우 이 메서드는 [CFirePropNotifyEvent::FireOnRequestEdit를](cfirepropnotifyevent-class.md#fireonrequestedit) 호출하여 연결된 모든 `IPropertyNotifySink` 인터페이스에 지정된 제어 속성이 변경될 것이라는 사실을 알립니다. 컨트롤 클래스에서 `IPropertyNotifySink`파생 되지 않는 경우이 메서드는 S_OK 반환 합니다.

이 메서드는 컨트롤이 연결 지점을 지원하지 않는 경우에도 호출해도 안전합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]

## <a name="ccomcontrolmessagebox"></a><a name="messagebox"></a>CComControl::메시지 상자

이 메서드를 호출하여 메시지 상자를 만들고 표시하고 조작합니다.

```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
메시지 상자에 표시할 텍스트입니다.

*lpszCaption*<br/>
대화 상자 제목입니다. NULL(기본값)이 면 제목 "오류"가 사용됩니다.

*nType*<br/>
대화 상자의 내용과 동작을 지정합니다. 사용 가능한 다른 메시지 상자 목록은 Windows SDK 설명서의 [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) 항목을 참조하십시오. 기본값은 간단한 **확인** 단추를 제공합니다.

### <a name="return-value"></a>Return Value

Windows SDK 설명서의 [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) 아래에 나열된 메뉴 항목 값 중 하나를 지정하는 정수 값을 반환합니다.

### <a name="remarks"></a>설명

`MessageBox`개발 중및 사용자에게 오류 또는 경고 메시지를 표시하는 쉬운 방법으로 유용합니다.

## <a name="see-also"></a>참고 항목

[크윈도우임플 클래스](../../atl/reference/cwindowimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CComControlBase 클래스](../../atl/reference/ccomcontrolbase-class.md)<br/>
[CComCompositeControl 클래스](../../atl/reference/ccomcompositecontrol-class.md)
