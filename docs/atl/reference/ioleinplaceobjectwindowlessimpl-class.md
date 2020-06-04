---
title: 아이올레인플레이스오브젝트윈도우리스임플 클래스
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
ms.openlocfilehash: b0438692161f38445eb7cbed54edcc8a0ba8c0d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326574"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>아이올레인플레이스오브젝트윈도우리스임플 클래스

이 클래스는 `IUnknown` 창 없는 컨트롤이 창 메시지를 수신하고 끌어서 놓기 작업에 참여할 수 있도록 하는 메서드를 구현하고 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IOleInPlaceObjectWindowlessImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IOleInPlace개체윈도우리스임플::컨텍스트민감성 도움말](#contextsensitivehelp)|상황에 맞는 도움말을 활성화합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IOleInPlace개체윈도우리스임플::겟드롭타겟](#getdroptarget)|끌어서 `IDropTarget` 놓기를 지원하는 창없는 내부 활성 개체에 대한 인터페이스를 제공합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[아이올레인플레이스오브젝트윈도우리스임플::겟윈도우](#getwindow)|창 핸들을 가져옵니다.|
|[IOleInPlace개체윈도우리스임플::인플레이스비활성화](#inplacedeactivate)|활성 내부 컨트롤을 비활성화합니다.|
|[IOleInPlace개체윈도우리스임플::온윈도우메시지](#onwindowmessage)|컨테이너에서 활성 상태인 창 없는 컨트롤로 메시지를 디스패치합니다.|
|[아이올레인플레이스오브젝트윈도우리스임플::재활성화안운도](#reactivateandundo)|이전에 비활성화된 컨트롤을 다시 활성화합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IOleInPlace개체윈도우리스임플::세트오브젝트렉트](#setobjectrects)|현재 제어의 어떤 부분이 표시되는지 나타냅니다.|
|[아이올레인플레이스오브젝트윈도우리스임플::UI비활성화](#uideactivate)|내부 활성화를 지원하는 사용자 인터페이스를 비활성화하고 제거합니다.|

## <a name="remarks"></a>설명

[IOleInPlaceObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject) 인터페이스는 내부 컨트롤의 재활성화 및 비활성화를 관리하고 표시되는 컨트롤의 양을 결정합니다. [IOleInPlaceObjectWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) 인터페이스를 사용하면 창 없는 컨트롤을 사용하여 창 메시지를 수신하고 끌어서 놓기 작업에 참여할 수 있습니다. 클래스는 `IOleInPlaceObjectWindowlessImpl` 디버그 `IOleInPlaceObject` 빌드에서 덤프 `IUnknown` 장치에 정보를 전송하여 기본 구현 및 `IOleInPlaceObjectWindowless` 구현을 제공합니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IOleInPlaceObjectWindowless`

`IOleInPlaceObjectWindowlessImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="ioleinplaceobjectwindowlessimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a>IOleInPlace개체윈도우리스임플::컨텍스트민감성 도움말

E_NOTIMPL을 반환합니다.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="remarks"></a>설명

[IOleWindow::컨텍스트민감성](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) Windows SDK의 도움말을 참조하십시오.

## <a name="ioleinplaceobjectwindowlessimplgetdroptarget"></a><a name="getdroptarget"></a>IOleInPlace개체윈도우리스임플::겟드롭타겟

E_NOTIMPL을 반환합니다.

```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```

### <a name="remarks"></a>설명

[IOleInPlace개체창없는::윈도우](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-getdroptarget) SDK에서 GetDropTarget을 참조하십시오.

## <a name="ioleinplaceobjectwindowlessimplgetwindow"></a><a name="getwindow"></a>아이올레인플레이스오브젝트윈도우리스임플::겟윈도우

컨테이너는 컨트롤의 창 핸들을 얻기 위해 이 함수를 호출합니다.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>설명

일부 컨테이너는 현재 창이 있는 경우에도 창이 없는 컨트롤로 작동하지 않습니다. ATL 구현에서 컨트롤 클래스의 데이터 멤버가 `m_bWasOnceWindowless` TRUE이면 함수가 E_FAIL 반환합니다. 그렇지 않으면 *phwnd가* NULL이 \* 아닌 경우 *phwnd를* 컨트롤 `m_hWnd` 클래스의 데이터 멤버로 `GetWindow` 설정하고 S_OK 반환합니다.

[IOleWindow::GetWindow](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) 윈도우 SDK에서.

## <a name="ioleinplaceobjectwindowlessimplinplacedeactivate"></a><a name="inplacedeactivate"></a>IOleInPlace개체윈도우리스임플::인플레이스비활성화

컨테이너에서 호출하여 내부 활성 컨트롤을 비활성화합니다.

```
HRESULT InPlaceDeactivate(HWND* phwnd);
```

### <a name="remarks"></a>설명

이 메서드는 컨트롤의 상태에 따라 전체 또는 부분 비활성화를 수행 합니다. 필요한 경우 컨트롤의 사용자 인터페이스가 비활성화되고 컨트롤의 창(있는 경우)이 소멸됩니다. 컨테이너는 컨트롤이 더 이상 활성 상태가 아님을 통보합니다. 메뉴와 테두리 공간을 협상하기 위해 컨테이너에서 사용하는 `IOleInPlaceUIWindow` 인터페이스가 해제됩니다.

[IOleInPlaceObject::InPlaceWindows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) SDK에서 비활성화를 참조하십시오.

## <a name="ioleinplaceobjectwindowlessimplonwindowmessage"></a><a name="onwindowmessage"></a>IOleInPlace개체윈도우리스임플::온윈도우메시지

컨테이너에서 활성 상태인 창 없는 컨트롤로 메시지를 디스패치합니다.

```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```

### <a name="remarks"></a>설명

[IOleInPlace개체창없는::윈도우](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-onwindowmessage) SDK에서 온윈도우 메시지.

## <a name="ioleinplaceobjectwindowlessimplreactivateandundo"></a><a name="reactivateandundo"></a>아이올레인플레이스오브젝트윈도우리스임플::재활성화안운도

E_NOTIMPL을 반환합니다.

```
HRESULT ReactivateAndUndo();
```

### <a name="remarks"></a>설명

[IOleInPlaceObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-reactivateandundo) SDK에서 다시 활성화AndUndo를 참조하십시오.

## <a name="ioleinplaceobjectwindowlessimplsetobjectrects"></a><a name="setobjectrects"></a>IOleInPlace개체윈도우리스임플::세트오브젝트렉트

컨테이너에서 호출하여 컨트롤의 크기 및/또는 위치가 변경되었음을 사용자에게 알립니다.

```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```

### <a name="remarks"></a>설명

컨트롤의 `m_rcPos` 데이터 멤버와 컨트롤 표시를 업데이트합니다. 클립 영역과 교차하는 컨트롤의 일부만 표시됩니다. 컨트롤의 디스플레이가 이전에 잘렸지만 클리핑이 제거된 경우 이 함수를 호출하여 컨트롤의 전체 보기를 다시 그릴 수 있습니다.

[IOleInPlaceObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-setobjectrects) SDK에서 설정개체 수정을 참조하십시오.

## <a name="ioleinplaceobjectwindowlessimpluideactivate"></a><a name="uideactivate"></a>아이올레인플레이스오브젝트윈도우리스임플::UI비활성화

내부 활성화를 지원하는 컨트롤의 사용자 인터페이스를 비활성화하고 제거합니다.

```
HRESULT UIDeactivate();
```

### <a name="remarks"></a>설명

컨트롤 클래스의 데이터 멤버를 `m_bUIActive` FALSE로 설정합니다. 이 함수의 ATL 구현은 항상 S_OK 반환합니다.

[IOleInPlaceObject::UI비활성화](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-uideactivate) 윈도우 SDK에서 를 참조하십시오.

## <a name="see-also"></a>참고 항목

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
