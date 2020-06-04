---
title: CComCompositeControl 클래스
ms.date: 11/04/2016
f1_keywords:
- CComCompositeControl
- ATLCTL/ATL::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::AdviseSinkMap
- ATLCTL/ATL::CComCompositeControl::CalcExtent
- ATLCTL/ATL::CComCompositeControl::Create
- ATLCTL/ATL::CComCompositeControl::CreateControlWindow
- ATLCTL/ATL::CComCompositeControl::SetBackgroundColorFromAmbient
- ATLCTL/ATL::CComCompositeControl::m_hbrBackground
- ATLCTL/ATL::CComCompositeControl::m_hWndFocus
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
ms.openlocfilehash: 700a8047ab1fa9df85c8e6530eb3eed5f29bd3d3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320801"
---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl 클래스

이 클래스는 복합 제어를 구현하는 데 필요한 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T>
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx에서](../../atl/reference/ccomobjectrootex-class.md)파생된 클래스와 복합 컨트롤을 지원하려는 다른 인터페이스에서 파생됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CCom복합 제어::CCom복합 제어](#ccomcompositecontrol)|생성자입니다.|
|[CCom복합 제어::~CCom복합 제어](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CCom복합 제어::조언싱크맵](#advisesinkmap)|복합 컨트롤에서 호스팅되는 모든 컨트롤에 대해 조언하거나 해제하려면 이 메서드를 호출합니다.|
|[CCom복합 제어::calcExtent](#calcextent)|복합 컨트롤을 호스트하는 데 사용되는 대화 상자 리소스의 HIMETRIC 단위로 크기를 계산하려면 이 메서드를 호출합니다.|
|[CComCompositeControl::만들기](#create)|이 메서드는 복합 컨트롤에 대 한 컨트롤 창을 만들기 위해 호출 됩니다.|
|[CCom복합 제어::만들기 제어 창](#createcontrolwindow)|이 메서드를 호출하여 컨트롤 창을 만들고 호스팅된 컨트롤에 대해 조언합니다.|
|[CComCompositeControl::설정배경색에서 앰비언트](#setbackgroundcolorfromambient)|이 메서드를 호출하여 컨테이너의 배경색을 사용하여 복합 컨트롤의 배경색을 설정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CCom복합 제어::m_hbrBackground](#m_hbrbackground)|배경 브러시입니다.|
|[CCom복합 제어::m_hWndFocus](#m_hwndfocus)|현재 포커스가 있는 창의 핸들입니다.|

## <a name="remarks"></a>설명

클래스에서 `CComCompositeControl` 파생된 클래스는 ActiveX 복합 컨트롤의 기능을 상속합니다. 파생된 `CComCompositeControl` ActiveX 컨트롤은 표준 대화 상자에서 호스팅됩니다. 이러한 유형의 컨트롤은 다른 컨트롤(기본 Windows 컨트롤 및 ActiveX 컨트롤)을 호스트할 수 있으므로 복합 컨트롤이라고 합니다.

`CComCompositeControl`는 자식 클래스에서 열거된 데이터 멤버를 찾아 복합 컨트롤을 만드는 데 사용할 대화 상자 리소스를 식별합니다. 이 자식 클래스의 멤버 IDD는 컨트롤의 창으로 사용되는 대화 상자 리소스의 리소스 ID로 설정됩니다. 다음은 컨트롤의 창에 `CComCompositeControl` 사용할 대화 상자 리소스를 식별하기 위해 파생된 클래스가 포함해야 하는 데이터 멤버의 예입니다.

[!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]

> [!NOTE]
> 복합 컨트롤은 창 없는 컨트롤을 포함할 수 있지만 항상 창이 있는 컨트롤입니다.

`CComCompositeControl`-derived 클래스에 의해 구현 된 컨트롤에는 기본 탭 동작이 내장 되어 있습니다. 컨트롤이 포함된 응용 프로그램에서 탭된 대로 포커스를 받으면 TAB 키를 연속적으로 누르면 복합 컨트롤의 포함된 모든 컨트롤을 순환한 다음 복합 컨트롤에서 컨테이너의 탭 순서로 다음 항목으로 포커스가 순환됩니다. 호스팅된 컨트롤의 탭 순서는 대화 상자 리소스에 의해 결정되며 탭이 발생하는 순서를 결정합니다.

> [!NOTE]
> 가속기가 `CComCompositeControl`a와 함께 제대로 작동하려면 컨트롤이 생성될 때 가속기 테이블을 로드하고, 핸들과 가속기 수를 [IOleControlImpl::GetControlInfo로](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo)다시 전달하고, 컨트롤이 해제될 때 테이블을 마지막으로 파괴해야 합니다.

## <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

[CComControl](../../atl/reference/ccomcontrol-class.md)

`CComCompositeControl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="ccomcompositecontroladvisesinkmap"></a><a name="advisesinkmap"></a>CCom복합 제어::조언싱크맵

복합 컨트롤에서 호스팅되는 모든 컨트롤에 대해 조언하거나 해제하려면 이 메서드를 호출합니다.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>매개 변수

*bAdvise*<br/>
모든 컨트롤을 권고해야 하는 경우 True; 그렇지 않으면 거짓.

### <a name="return-value"></a>Return Value

|||
|-|-|
|S_OK  |이벤트 싱크 맵의 모든 컨트롤이 이벤트 소스에서 연결되거나 연결이 끊어졌습니다.|
|E_FAIL  |이벤트 싱크 맵의 모든 컨트롤이 이벤트 소스에서 연결되거나 연결되지 않을 수 있습니다.|
|E_POINTER  |이 오류는 일반적으로 컨트롤의 이벤트 싱크 맵에 있는 항목에 문제가 있거나 `IDispEventImpl` 또는 기본 `IDispEventSimpleImpl` 클래스에 사용되는 템플릿 인수에 문제가 있음을 나타냅니다.|
|CONNECT_E_ADVISELIMIT  |연결 지점이 이미 연결 한계에 도달하여 더 이상 수용할 수 없습니다.|
|CONNECT_E_CANNOTCONNECT  |싱크는 이 연결 지점에 필요한 인터페이스를 지원하지 않습니다.|
|CONNECT_E_NOCONNECTION  |쿠키 값이 유효한 연결을 나타내지 않습니다. 이 오류는 일반적으로 컨트롤의 이벤트 싱크 맵에 있는 항목에 문제가 있거나 `IDispEventImpl` 또는 기본 `IDispEventSimpleImpl` 클래스에 사용되는 템플릿 인수에 문제가 있음을 나타냅니다.|

### <a name="remarks"></a>설명

이 메서드의 기본 구현은 이벤트 싱크 맵의 항목을 검색합니다. 그런 다음 이벤트 싱크 맵의 싱크 항목에 설명된 COM 개체에 대한 연결 점을 조언하거나 해제합니다. 또한 이 멤버 메서드는 파생된 클래스가 싱크 맵의 `IDispEventImpl` 모든 컨트롤에 대해 한 인스턴스에서 상속된다는 사실에 의존합니다.

## <a name="ccomcompositecontrolcalcextent"></a><a name="calcextent"></a>CCom복합 제어::calcExtent

복합 컨트롤을 호스트하는 데 사용되는 대화 상자 리소스의 HIMETRIC 단위로 크기를 계산하려면 이 메서드를 호출합니다.

```
BOOL CalcExtent(SIZE& size);
```

### <a name="parameters"></a>매개 변수

*크기*<br/>
이 방법으로 `SIZE` 채울 구조체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

TRUE 컨트롤이 대화 상자에서 호스팅되는 경우입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

크기 매개 변수에서 *크기가* 반환됩니다.

## <a name="ccomcompositecontrolcreate"></a><a name="create"></a>CComCompositeControl::만들기

이 메서드는 복합 컨트롤에 대 한 컨트롤 창을 만들기 위해 호출 됩니다.

```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>매개 변수

*hWnd부모*<br/>
컨트롤의 상위 창에 대한 핸들입니다.

*rcPos*<br/>
예약되어 있습니다.

*dwInitParam*<br/>
컨트롤 을 만드는 동안 컨트롤에 전달될 데이터입니다. *dwInitParam으로* 전달된 데이터는 [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) 메시지의 LPARAM 매개 변수로 표시되며, 이 매개 변수가 생성되면 복합 컨트롤로 전송됩니다.

### <a name="return-value"></a>Return Value

새로 만든 복합 제어 대화 상자에 대한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 일반적으로 컨트롤의 내부 활성화 중에 호출 됩니다.

## <a name="ccomcompositecontrolccomcompositecontrol"></a><a name="ccomcompositecontrol"></a>CCom복합 제어::CCom복합 제어

생성자입니다.

```
CComCompositeControl();
```

### <a name="remarks"></a>설명

[CComCompositeControl::m_hbrBackground](#m_hbrbackground) 및 [CComCompositeControl::m_hWndFocus](#m_hwndfocus) 데이터 멤버를 NULL로 초기화합니다.

## <a name="ccomcompositecontrolccomcompositecontrol"></a><a name="dtor"></a>CCom복합 제어::~CCom복합 제어

소멸자입니다.

```
~CComCompositeControl();
```

### <a name="remarks"></a>설명

백그라운드 개체가 있는 경우 삭제합니다.

## <a name="ccomcompositecontrolcreatecontrolwindow"></a><a name="createcontrolwindow"></a>CCom복합 제어::만들기 제어 창

이 메서드를 호출하여 컨트롤 창을 만들고 호스팅된 컨트롤에 대해 조언합니다.

```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```

### <a name="parameters"></a>매개 변수

*hWnd부모*<br/>
컨트롤의 상위 창에 대한 핸들입니다.

*rcPos*<br/>
*hWndParent를*기준으로 클라이언트 좌표에서 복합 컨트롤의 위치 사각형입니다.

### <a name="return-value"></a>Return Value

새로 만든 복합 제어 대화 상자에 핸들을 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 [CComCompositeControl::만들기](#create) 및 [CComCompositeControl::adviseSinkMap](#advisesinkmap)을 호출합니다.

## <a name="ccomcompositecontrolm_hbrbackground"></a><a name="m_hbrbackground"></a>CCom복합 제어::m_hbrBackground

배경 브러시입니다.

```
HBRUSH m_hbrBackground;
```

## <a name="ccomcompositecontrolm_hwndfocus"></a><a name="m_hwndfocus"></a>CCom복합 제어::m_hWndFocus

현재 포커스가 있는 창의 핸들입니다.

```
HWND m_hWndFocus;
```

## <a name="ccomcompositecontrolsetbackgroundcolorfromambient"></a><a name="setbackgroundcolorfromambient"></a>CComCompositeControl::설정배경색에서 앰비언트

이 메서드를 호출하여 컨테이너의 배경색을 사용하여 복합 컨트롤의 배경색을 설정합니다.

```
HRESULT SetBackgroundColorFromAmbient();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="see-also"></a>참고 항목

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[복합 컨트롤 기본 사항](../../atl/atl-composite-control-fundamentals.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
