---
title: 아이뷰오브젝트엑스임플 클래스
ms.date: 11/04/2016
f1_keywords:
- IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl::Draw
- ATLCTL/ATL::IViewObjectExImpl::Freeze
- ATLCTL/ATL::IViewObjectExImpl::GetAdvise
- ATLCTL/ATL::IViewObjectExImpl::GetColorSet
- ATLCTL/ATL::IViewObjectExImpl::GetExtent
- ATLCTL/ATL::IViewObjectExImpl::GetNaturalExtent
- ATLCTL/ATL::IViewObjectExImpl::GetRect
- ATLCTL/ATL::IViewObjectExImpl::GetViewStatus
- ATLCTL/ATL::IViewObjectExImpl::QueryHitPoint
- ATLCTL/ATL::IViewObjectExImpl::QueryHitRect
- ATLCTL/ATL::IViewObjectExImpl::SetAdvise
- ATLCTL/ATL::IViewObjectExImpl::Unfreeze
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
ms.openlocfilehash: 59c5657dcd892544f7e790b52325cb9ecba0dd56
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326339"
---
# <a name="iviewobjecteximpl-class"></a>아이뷰오브젝트엑스임플 클래스

이 클래스는 `IUnknown` [IViewObject,](/windows/win32/api/oleidl/nn-oleidl-iviewobject) [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)및 [IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex) 인터페이스의 기본 구현을 구현하고 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class ATL_NO_VTABLE IViewObjectExImpl
   : public IViewObjectEx
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IViewObjectExImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IView개체ExImpl::D](#draw)|장치 컨텍스트에 컨트롤의 표현을 그립니다.|
|[IViewObjectExImpl::동결](#freeze)|컨트롤의 그려진 표현을 고정하여 `Unfreeze`. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IViewObjectExImpl::GetAdvise](#getadvise)|컨트롤에 있는 경우 컨트롤에서 기존 권고 싱크 연결을 검색합니다.|
|[IViewObjectExImpl::GetColorSet](#getcolorset)|그리기에 대 한 컨트롤에서 사용 하는 논리 팔레트를 반환 합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IViewObjectExImpl::GetExtent](#getextent)|컨트롤 클래스 데이터 멤버 [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)에서 HIMETRIC 단위(단위당 0.01밀리미터)로 컨트롤의 표시 크기를 검색합니다.|
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|사용자가 크기를 조정할 때 사용할 개체에 대한 컨테이너의 크기 조정 힌트를 제공합니다.|
|[IViewObjectExImpl::GetRect](#getrect)|요청된 그리기 측면을 설명하는 사각형을 반환합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IViewObjectExImpl::GetView상태](#getviewstatus)|객체의 불투명도 및 지원되는 도면 측면에 대한 정보를 반환합니다.|
|[IViewObjectExImpl::쿼리 히트 포인트](#queryhitpoint)|지정된 점이 지정된 사각형에 있는지 확인하고 `pHitResult`에서 [HITRESULT](/windows/win32/api/ocidl/ne-ocidl-hitresult) 값을 반환합니다.|
|[IViewObjectExImpl::쿼리히트렉트](#queryhitrect)|컨트롤의 표시 사각형이 지정된 위치 사각형의 모든 지점과 겹치는지 확인하고 `pHitResult`에서 HITRESULT 값을 반환합니다.|
|[IViewObjectExImpl::SetAdvise](#setadvise)|컨트롤과 조언 싱크 사이의 연결을 설정하여 싱크에 컨트롤 보기의 변경 사항에 대해 알 수 있습니다.|
|[IViewObjectExImpl::고정 해제](#unfreeze)|컨트롤의 그려진 표현을 고정 해제합니다. ATL 구현은 E_NOTIMPL 반환합니다.|

## <a name="remarks"></a>설명

[IViewObject](/windows/win32/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)및 [IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex) 인터페이스를 사용하면 컨트롤이 직접 자신을 표시하고 컨트롤 디스플레이의 변경 내용을 컨테이너에 알리기 위해 조언 싱크를 만들고 관리할 수 있습니다. 인터페이스는 `IViewObjectEx` 깜박임 없는 그리기, 직사각형이 아닌 투명 한 컨트롤 및 적중 테스트(예: 컨트롤에서 마우스 클릭을 고려해야 하는 위치)와 같은 확장된 제어 기능을 지원합니다. 클래스는 `IViewObjectExImpl` 디버그 빌드에서 덤프 장치에 `IUnknown` 정보를 전송하여 이러한 인터페이스 및 구현의 기본 구현을 제공합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IViewObjectEx`

`IViewObjectExImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="iviewobjecteximpldraw"></a><a name="draw"></a>IView개체ExImpl::D

장치 컨텍스트에 컨트롤의 표현을 그립니다.

```
STDMETHOD(Draw)(
    DWORD dwDrawAspect,
    LONG lindex,
    void* pvAspect,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    LPCRECTL prcBounds,
    LPCRECTL prcWBounds,
    BOOL(_stdcall* /* pfnContinue*/) (DWORD_PTR dwContinue),
    DWORD_PTR /* dwContinue */);
```

### <a name="remarks"></a>설명

이 메서드는 컨트롤 클래스의 `CComControl::OnDrawAdvanced` `OnDraw` 메서드를 호출합니다. ATL 컨트롤 마법사를 사용하여 컨트롤을 `OnDraw` 만들 때 메서드가 컨트롤 클래스에 자동으로 추가됩니다. 마법사의 기본값은 `OnDraw` "ATL 3.0"이라는 레이블이 있는 사각형을 그립니다.

[IViewObject::D](/windows/win32/api/oleidl/nf-oleidl-iviewobject-draw) 윈도우 SDK에서 raw를 참조하십시오.

## <a name="iviewobjecteximplfreeze"></a><a name="freeze"></a>IViewObjectExImpl::동결

컨트롤의 그려진 표현을 고정하여 `Unfreeze`. ATL 구현은 E_NOTIMPL 반환합니다.

```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```

### <a name="remarks"></a>설명

[IViewObject::Windows](/windows/win32/api/oleidl/nf-oleidl-iviewobject-freeze) SDK에서 고정을 참조하십시오.

## <a name="iviewobjecteximplgetadvise"></a><a name="getadvise"></a>IViewObjectExImpl::GetAdvise

컨트롤에 있는 경우 컨트롤에서 기존 권고 싱크 연결을 검색합니다.

```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```

### <a name="remarks"></a>설명

권고 싱크는 컨트롤 클래스 데이터 멤버 [CComControlBase::m_spAdviseSink에](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)저장됩니다.

[IViewObject::Get조언](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getadvise) 윈도우 SDK에서.

## <a name="iviewobjecteximplgetcolorset"></a><a name="getcolorset"></a>IViewObjectExImpl::GetColorSet

그리기에 대 한 컨트롤에서 사용 하는 논리 팔레트를 반환 합니다. ATL 구현은 E_NOTIMPL 반환합니다.

```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```

### <a name="remarks"></a>설명

[IViewObject::GetColor를](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getcolorset) Windows SDK에서 참조하십시오.

## <a name="iviewobjecteximplgetextent"></a><a name="getextent"></a>IViewObjectExImpl::GetExtent

컨트롤 클래스 데이터 멤버 [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)에서 HIMETRIC 단위(단위당 0.01밀리미터)로 컨트롤의 표시 크기를 검색합니다.

```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```

### <a name="remarks"></a>설명

[IViewObject2::GetExtent](/windows/win32/api/oleidl/nf-oleidl-iviewobject2-getextent) 윈도우 SDK를 참조하십시오.

## <a name="iviewobjecteximplgetnaturalextent"></a><a name="getnaturalextent"></a>IViewObjectExImpl::GetNaturalExtent

사용자가 크기를 조정할 때 사용할 개체에 대한 컨테이너의 크기 조정 힌트를 제공합니다.

```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```

### <a name="remarks"></a>설명

DVASPECT_CONTENT `dwAspect` 및 *pExtentInfo->dwExtentMode가* DVEXTENT_CONTENT `psizel` 경우 *를 컨트롤 클래스의 데이터 멤버 [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)로 설정합니다. 그렇지 않으면 오류 HRESULT를 반환합니다.

[IViewObjectEx::GetNaturalWindows](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getnaturalextent) SDK에서 익스텐트를 참조하십시오.

## <a name="iviewobjecteximplgetrect"></a><a name="getrect"></a>IViewObjectExImpl::GetRect

요청된 그리기 측면을 설명하는 사각형을 반환합니다. ATL 구현은 E_NOTIMPL 반환합니다.

```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```

### <a name="remarks"></a>설명

[IViewObjectEx::GetRect](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getrect) Windows SDK를 참조하십시오.

## <a name="iviewobjecteximplgetviewstatus"></a><a name="getviewstatus"></a>IViewObjectExImpl::GetView상태

객체의 불투명도 및 지원되는 도면 측면에 대한 정보를 반환합니다.

```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```

### <a name="remarks"></a>설명

기본적으로 ATL은 `pdwStatus` 컨트롤이 VIEWSTATUS_OPAQUE 지원함을 나타내도록 설정합니다(가능한 값은 [VIEWSTATUS](/windows/win32/api/ocidl/ne-ocidl-viewstatus) 열거형에 있음).

[IViewObjectEx::GetViewWindows](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getviewstatus) SDK에서 상태를 참조하십시오.

## <a name="iviewobjecteximplqueryhitpoint"></a><a name="queryhitpoint"></a>IViewObjectExImpl::쿼리 히트 포인트

지정된 점이 지정된 사각형에 있는지 확인하고 `pHitResult`에서 [HITRESULT](/windows/win32/api/ocidl/ne-ocidl-hitresult) 값을 반환합니다.

```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>설명

값은 HITRESULT_HIT 또는 HITRESULT_OUTSIDE 수 있습니다.

DVASPECT_CONTENT `dwAspect` 경우 [DVASPECT_CONTENT](/windows/win32/api/wtypes/ne-wtypes-dvaspect)메서드는 S_OK 반환합니다. 그렇지 않으면 메서드가 E_FAIL 반환합니다.

윈도우 SDK에서 [IViewObjectEx::쿼리 히트포인트를](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitpoint) 참조하십시오.

## <a name="iviewobjecteximplqueryhitrect"></a><a name="queryhitrect"></a>IViewObjectExImpl::쿼리히트렉트

컨트롤의 표시 사각형이 지정된 위치 사각형의 모든 지점과 겹치는지 확인하고 `pHitResult` [에서 HITRESULT](/windows/win32/api/ocidl/ne-ocidl-hitresult) 값을 반환합니다.

```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>설명

값은 HITRESULT_HIT 또는 HITRESULT_OUTSIDE 수 있습니다.

DVASPECT_CONTENT `dwAspect` 경우 [DVASPECT_CONTENT](/windows/win32/api/wtypes/ne-wtypes-dvaspect)메서드는 S_OK 반환합니다. 그렇지 않으면 메서드가 E_FAIL 반환합니다.

윈도우 SDK에서 [IViewObjectEx::쿼리히트렉트](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitrect) 를 참조하십시오.

## <a name="iviewobjecteximplsetadvise"></a><a name="setadvise"></a>IViewObjectExImpl::SetAdvise

컨트롤과 조언 싱크 사이의 연결을 설정하여 싱크에 컨트롤 보기의 변경 사항에 대해 알 수 있습니다.

```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```

### <a name="remarks"></a>설명

조언 [싱크의 IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) 인터페이스에 대한 포인터는 컨트롤 클래스 데이터 멤버 [CComControlBase:m_spAdviseSink에](ccomcontrolbase-class.md#m_spadvisesink)저장됩니다.

[IViewObject::SetWindows](/windows/win32/api/oleidl/nf-oleidl-iviewobject-setadvise) SDK에서 조언참조.

## <a name="iviewobjecteximplunfreeze"></a><a name="unfreeze"></a>IViewObjectExImpl::고정 해제

컨트롤의 그려진 표현을 고정 해제합니다. ATL 구현은 E_NOTIMPL 반환합니다.

```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```

### <a name="remarks"></a>설명

[IViewObject::Windows](/windows/win32/api/oleidl/nf-oleidl-iviewobject-unfreeze) SDK에서 고정 해제를 참조하십시오.

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a>IWorker스레드 클라이언트::닫기 핸들

이 메서드를 구현하여 이 개체와 연결된 핸들을 닫습니다.

```
HRESULT CloseHandle(HANDLE hHandle);
```

### <a name="parameters"></a>매개 변수

*h핸들*<br/>
닫을 핸들입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드에 전달 된 핸들은 이전에 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)에 대 한 호출에 의해이 개체와 연결 되었습니다.

### <a name="example"></a>예제

다음 코드는 의 `IWorkerThreadClient::CloseHandle`간단한 구현을 보여 주며 의 구현을 보여 주며 있습니다.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a>IWorker스레드 클라이언트::실행

이 개체와 연결된 핸들이 신호가 표시될 때 코드를 실행하려면 이 메서드를 구현합니다.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>매개 변수

*dwParam*<br/>
사용자 매개 변수입니다.

*h개체*<br/>
신호가 된 핸들입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드에 전달 된 핸들 및 DWORD/포인터는 이전에 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)에 대 한 호출에 의해이 개체와 연결 되었습니다.

### <a name="example"></a>예제

다음 코드는 의 `IWorkerThreadClient::Execute`간단한 구현을 보여 주며 의 구현을 보여 주며 있습니다.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]

## <a name="see-also"></a>참고 항목

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[액티브X컨트롤 인터페이스](/windows/win32/com/activex-controls-interfaces)<br/>
[자습서](../../atl/active-template-library-atl-tutorial.md)<br/>
[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
