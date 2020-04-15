---
title: IOleObjectImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl::Advise
- ATLCTL/ATL::IOleObjectImpl::Close
- ATLCTL/ATL::IOleObjectImpl::DoVerb
- ATLCTL/ATL::IOleObjectImpl::DoVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::DoVerbHide
- ATLCTL/ATL::IOleObjectImpl::DoVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::DoVerbOpen
- ATLCTL/ATL::IOleObjectImpl::DoVerbPrimary
- ATLCTL/ATL::IOleObjectImpl::DoVerbShow
- ATLCTL/ATL::IOleObjectImpl::DoVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::EnumAdvise
- ATLCTL/ATL::IOleObjectImpl::EnumVerbs
- ATLCTL/ATL::IOleObjectImpl::GetClientSite
- ATLCTL/ATL::IOleObjectImpl::GetClipboardData
- ATLCTL/ATL::IOleObjectImpl::GetExtent
- ATLCTL/ATL::IOleObjectImpl::GetMiscStatus
- ATLCTL/ATL::IOleObjectImpl::GetMoniker
- ATLCTL/ATL::IOleObjectImpl::GetUserClassID
- ATLCTL/ATL::IOleObjectImpl::GetUserType
- ATLCTL/ATL::IOleObjectImpl::InitFromData
- ATLCTL/ATL::IOleObjectImpl::IsUpToDate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::SetClientSite
- ATLCTL/ATL::IOleObjectImpl::SetColorScheme
- ATLCTL/ATL::IOleObjectImpl::SetExtent
- ATLCTL/ATL::IOleObjectImpl::SetHostNames
- ATLCTL/ATL::IOleObjectImpl::SetMoniker
- ATLCTL/ATL::IOleObjectImpl::Unadvise
- ATLCTL/ATL::IOleObjectImpl::Update
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
ms.openlocfilehash: 86d82aea2e92eb99903284abe4ac03478369616c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326519"
---
# <a name="ioleobjectimpl-class"></a>IOleObjectImpl 클래스

이 클래스는 `IUnknown` 컨테이너가 컨트롤과 통신하는 주 인터페이스를 구현하고 이를 구현합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IOleObjectImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IOleObjectImpl::조언](#advise)|컨트롤과 자문 연결을 설정합니다.|
|[IOleObjectImpl::닫기](#close)|컨트롤 상태가 실행 중인 상태에서 로드됨으로 변경합니다.|
|[아이올레오브젝트임플::D](#doverb)|확장된 작업 중 하나를 수행하도록 컨트롤에 지시합니다.|
|[아이올레오브젝트임플::DoverbDiscardUndo](#doverbdiscardundo)|컨트롤에 유지 관리 중이면 취소 상태를 삭제하도록 지시합니다.|
|[아이올레오브젝트임플::D](#doverbhide)|뷰에서 사용자 인터페이스를 제거하도록 컨트롤에 알려줍니다.|
|[아이올레오브젝트임플::D버빈플레이스활성화](#doverbinplaceactivate)|컨트롤을 실행하고 해당 창을 설치하지만 컨트롤의 사용자 인터페이스는 설치하지 않습니다.|
|[아이올레오브젝트임플::DoVerbOpen](#doverbopen)|별도의 창에서 컨트롤을 열어 편집합니다.|
|[아이올레오브젝트임플::D](#doverbprimary)|사용자가 컨트롤을 두 번 클릭할 때 지정된 작업을 수행합니다. 컨트롤은 일반적으로 컨트롤을 제자리에서 활성화하기 위해 작업을 정의합니다.|
|[아이올레오브젝트임플::DoVerbShow](#doverbshow)|사용자에게 새로 삽입된 컨트롤을 표시합니다.|
|[아이올레오브젝트임플::DoverbUIActivate](#doverbuiactivate)|컨트롤을 제자리에서 활성화하고 메뉴 및 도구 모음과 같은 컨트롤의 사용자 인터페이스를 표시합니다.|
|[아이올레오브젝트임플::에넘어](#enumadvise)|컨트롤의 권고 연결을 열거합니다.|
|[아이올레오브젝트임플::에이넘베브](#enumverbs)|컨트롤에 대한 작업을 등록합니다.|
|[IOleObjectImpl::GetClientSite](#getclientsite)|컨트롤의 클라이언트 사이트를 검색합니다.|
|[IOleObjectImpl::GetClipboard데이터](#getclipboarddata)|클립보드에서 데이터를 검색합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IOleObjectImpl::GetExtent](#getextent)|컨트롤의 표시 영역 범위를 검색합니다.|
|[아이올레오브젝트임플::겟미스시상태](#getmiscstatus)|컨트롤의 상태를 검색합니다.|
|[아이올레오브젝트임플::겟모니커](#getmoniker)|컨트롤의 모니커를 검색합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|컨트롤의 클래스 식별자를 검색합니다.|
|[IOleObjectImpl::GetuserType](#getusertype)|컨트롤의 사용자 유형 이름을 검색합니다.|
|[IOleObjectImpl::이니트데이터 데이터](#initfromdata)|선택한 데이터에서 컨트롤을 초기화합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[아이올레오브젝트임플::이스업토데이트](#isuptodate)|컨트롤이 최신 상태인지 확인합니다. ATL 구현은 S_OK 반환합니다.|
|[아이올레오브젝트임플::온포스트버버버버폐기운도](#onpostverbdiscardundo)|[DoVerbDiscardUndo에서](#doverbdiscardundo) 호출하면 취소 상태가 삭제됩니다.|
|[아이올레오브젝트임플::온포스트버브하이드](#onpostverbhide)|컨트롤이 숨겨진 후 [DoVerbHide에서](#doverbhide) 호출합니다.|
|[IOleObjectImpl::에포스트버빈플레이스활성화](#onpostverbinplaceactivate)|[DoVerbInPlace에서](#doverbinplaceactivate) 호출컨트롤이 활성화된 후 활성화합니다.|
|[아이올레오브젝트임플::온포스트버브오픈](#onpostverbopen)|별도의 창에서 편집하기 위해 컨트롤을 연 후 [DoVerbOpen에서](#doverbopen) 호출합니다.|
|[아이올레오브젝트임플::온포스트버브쇼](#onpostverbshow)|컨트롤이 표시 된 후 [DoVerbShow에](#doverbshow) 의해 호출 됩니다.|
|[IOleObjectImpl::에포스트버브UI활성화](#onpostverbuiactivate)|컨트롤의 사용자 인터페이스가 활성화된 후 [DoVerbUIActivate에서](#doverbuiactivate) 호출합니다.|
|[IOleObjectImpl::에프프리버 버버 버림운도](#onpreverbdiscardundo)|[DoVerbDiscardUndo에서](#doverbdiscardundo) 호출한 후 취소 상태가 삭제됩니다.|
|[아이올레오브젝트임플::온프리버하이드](#onpreverbhide)|컨트롤이 숨겨지기 전에 [DoVerbHide에서](#doverbhide) 호출합니다.|
|[IOleObjectImpl::에프프리버빈플레이스활성화](#onpreverbinplaceactivate)|[DoVerbInPlace에서](#doverbinplaceactivate) 호출컨트롤이 활성화되기 전에 활성화합니다.|
|[아이올레오브젝트임플::온프리버브오픈](#onpreverbopen)|별도의 창에서 편집하기 위해 컨트롤을 열기 전에 [DoVerbOpen에서](#doverbopen) 호출합니다.|
|[아이올레오브젝트임플::온프리버브쇼](#onpreverbshow)|컨트롤이 표시되기 전에 [DoVerbShow에서](#doverbshow) 호출합니다.|
|[IOleObjectImpl::에프리버브UI활성화](#onpreverbuiactivate)|컨트롤의 사용자 인터페이스가 활성화되기 전에 [DoVerbUIActivate에서](#doverbuiactivate) 호출합니다.|
|[IOleObjectImpl::SetClientSite](#setclientsite)|컨테이너의 클라이언트 사이트에 대한 컨트롤을 알려줍니다.|
|[아이올레오브젝트임플::세트컬러스킴](#setcolorscheme)|컨트롤의 응용 프로그램에 색 구성표를 권장합니다(있는 경우). ATL 구현은 E_NOTIMPL 반환합니다.|
|[IOleObjectImpl::SetExtent](#setextent)|컨트롤의 표시 영역 범위를 설정합니다.|
|[IOleObjectImpl::SetHostnames](#sethostnames)|컨트롤에 컨테이너 응용 프로그램 및 컨테이너 문서의 이름을 지정합니다.|
|[아이올레오브젝트임플::셋모니커](#setmoniker)|컨트롤에 모니커가 무엇인지 알려줍니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[아이올레오브젝트임플::조언 불굴의](#unadvise)|컨트롤과의 권고 연결을 삭제합니다.|
|[IOleObjectImpl::업데이트](#update)|컨트롤을 업데이트합니다. ATL 구현은 S_OK 반환합니다.|

## <a name="remarks"></a>설명

[IOleObject](/windows/win32/api/oleidl/nn-oleidl-ioleobject) 인터페이스는 컨테이너가 컨트롤과 통신하는 주요 인터페이스입니다. 클래스는 `IOleObjectImpl` 디버그 빌드에서 덤프 `IUnknown` 장치에 정보를 전송하여 이 인터페이스및 구현의 기본 구현을 제공합니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IOleObject`

`IOleObjectImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="ioleobjectimpladvise"></a><a name="advise"></a>IOleObjectImpl::조언

컨트롤과 자문 연결을 설정합니다.

```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>설명

[IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) SDK에서 조언을 참조하십시오.

## <a name="ioleobjectimplclose"></a><a name="close"></a>IOleObjectImpl::닫기

컨트롤 상태가 실행 중인 상태에서 로드됨으로 변경합니다.

```
STDMETHOD(Close)(DWORD dwSaveOption);
```

### <a name="remarks"></a>설명

컨트롤을 비활성화 하고 컨트롤 창이 있는 경우 삭제 합니다. 컨트롤 클래스 데이터 멤버 [CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) TRUE이고 *dwSaveOption* 매개 변수가 OLECLOSE_SAVEIFDIRTY 또는 OLECLOSE_PROMPTSAVE 경우 컨트롤 속성이 닫히기 전에 저장됩니다.

컨트롤 클래스 데이터 멤버 [CComControlBase::m_spInPlaceSite:m_spAdviseSink:m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) 에 있는 포인터가 해제되고 데이터 멤버 [CComControlBase:m_bNegotiatedWnd:](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd) [CComControlBase:m_bWndless 및](../../atl/reference/ccomcontrolbase-class.md#m_bwndless) [CComControlBase:m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) FALSE로 설정됩니다. [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)

[IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-close) SDK에서 닫기 참조.

## <a name="ioleobjectimpldoverb"></a><a name="doverb"></a>아이올레오브젝트임플::D

확장된 작업 중 하나를 수행하도록 컨트롤에 지시합니다.

```
STDMETHOD(DoVerb)(
    LONG iVerb,
    LPMSG /* pMsg */,
    IOleClientSite* pActiveSite,
    LONG /* lindex */,
    HWND hwndParent,
    LPCRECT lprcPosRect);
```

### <a name="remarks"></a>설명

`iVerb`의 값에 따라 ATL `DoVerb` 도우미 함수 중 하나가 다음과 같이 호출됩니다.

|*아이 버브 (이베르주)* 값|라는 DoVerb 도우미 함수|
|-------------------|-----------------------------------|
|OLEIVERB_DISCARDUNDOSTATE|[도버버버번운도](#doverbdiscardundo)|
|OLEIVERB_HIDE|[도버하이드](#doverbhide)|
|OLEIVERB_INPLACEACTIVATE|[도버빈플레이스활성화](#doverbinplaceactivate)|
|OLEIVERB_OPEN|[도버브오픈](#doverbopen)|
|OLEIVERB_PRIMARY|[도버브프라이머리](#doverbprimary)|
|OLEIVERB_PROPERTIES|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|
|OLEIVERB_SHOW|[도버브쇼](#doverbshow)|
|OLEIVERB_UIACTIVATE|[도버비인스](#doverbuiactivate)|

[IOleObject::DOVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) 를 참조하십시오.

## <a name="ioleobjectimpldoverbdiscardundo"></a><a name="doverbdiscardundo"></a>아이올레오브젝트임플::DoverbDiscardUndo

컨트롤에 유지 관리 중이면 취소 상태를 삭제하도록 지시합니다.

```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
【인】 사각형에 대한 포인터는 컨테이너가 컨트롤을 끌어들이기를 원합니다.

*hwndParent*<br/>
【인】 컨트롤을 포함하는 창의 핸들입니다.

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

## <a name="ioleobjectimpldoverbhide"></a><a name="doverbhide"></a>아이올레오브젝트임플::D

컨트롤의 사용자 인터페이스를 비활성화하고 제거하고 컨트롤을 숨깁니다.

```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
【인】 사각형에 대한 포인터는 컨테이너가 컨트롤을 끌어들이기를 원합니다.

*hwndParent*<br/>
【인】 컨트롤을 포함하는 창의 핸들입니다. ATL 구현에서는 사용되지 않습니다.

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

## <a name="ioleobjectimpldoverbinplaceactivate"></a><a name="doverbinplaceactivate"></a>아이올레오브젝트임플::D버빈플레이스활성화

컨트롤을 실행하고 해당 창을 설치하지만 컨트롤의 사용자 인터페이스는 설치하지 않습니다.

```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
【인】 사각형에 대한 포인터는 컨테이너가 컨트롤을 끌어들이기를 원합니다.

*hwndParent*<br/>
【인】 컨트롤을 포함하는 창의 핸들입니다. ATL 구현에서는 사용되지 않습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

[CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate)를 호출하여 컨트롤을 활성화합니다. 컨트롤 클래스의 데이터 멤버가 `m_bWindowOnly` TRUE가 아니면 `DoVerbInPlaceActivate` 먼저 창 없는 컨트롤로 컨트롤을 활성화하려고 시도합니다(컨테이너가 [IOleInPlaceSiteWindowless를](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless)지원하는 경우에만 가능). 실패하면 함수는 확장된 기능을 사용하여 컨트롤을 활성화하려고 시도합니다(컨테이너가 [IOleInPlaceSiteEx를](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)지원하는 경우에만 가능). 실패하면 함수는 확장된 기능 없이 컨트롤을 활성화하려고 시도합니다(컨테이너가 [IOleInPlaceSite를](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)지원하는 경우에만 가능). 활성화가 성공하면 이 함수는 컨테이너에 컨트롤이 활성화되었음을 통보합니다.

## <a name="ioleobjectimpldoverbopen"></a><a name="doverbopen"></a>아이올레오브젝트임플::DoVerbOpen

별도의 창에서 컨트롤을 열어 편집합니다.

```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
【인】 사각형에 대한 포인터는 컨테이너가 컨트롤을 끌어들이기를 원합니다.

*hwndParent*<br/>
【인】 컨트롤을 포함하는 창의 핸들입니다.

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

## <a name="ioleobjectimpldoverbprimary"></a><a name="doverbprimary"></a>아이올레오브젝트임플::D

사용자가 컨트롤을 두 번 클릭할 때 수행되는 작업을 정의합니다.

```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
【인】 사각형에 대한 포인터는 컨테이너가 컨트롤을 끌어들이기를 원합니다.

*hwndParent*<br/>
【인】 컨트롤을 포함하는 창의 핸들입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

기본적으로 속성 페이지를 표시하도록 설정합니다. 컨트롤 클래스에서 이 것을 재정의하여 두 번 클릭할 때 다른 동작을 호출할 수 있습니다. 예를 들어 비디오를 재생하거나 활성 상태로 이동합니다.

## <a name="ioleobjectimpldoverbshow"></a><a name="doverbshow"></a>아이올레오브젝트임플::DoVerbShow

컨테이너에 컨트롤을 표시하도록 지시합니다.

```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
【인】 사각형에 대한 포인터는 컨테이너가 컨트롤을 끌어들이기를 원합니다.

*hwndParent*<br/>
【인】 컨트롤을 포함하는 창의 핸들입니다. ATL 구현에서는 사용되지 않습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ioleobjectimpldoverbuiactivate"></a><a name="doverbuiactivate"></a>아이올레오브젝트임플::DoverbUIActivate

컨트롤의 사용자 인터페이스를 활성화하고 메뉴가 복합 메뉴로 대체되고 있음을 컨테이너에 통보합니다.

```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
【인】 사각형에 대한 포인터는 컨테이너가 컨트롤을 끌어들이기를 원합니다.

*hwndParent*<br/>
【인】 컨트롤을 포함하는 창의 핸들입니다. ATL 구현에서는 사용되지 않습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ioleobjectimplenumadvise"></a><a name="enumadvise"></a>아이올레오브젝트임플::에넘어

이 컨트롤에 등록된 자문 연결의 열거형을 제공합니다.

```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```

### <a name="remarks"></a>설명

[IOleObject::열거형](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumadvise) Windows SDK에서 조언합니다.

## <a name="ioleobjectimplenumverbs"></a><a name="enumverbs"></a>아이올레오브젝트임플::에이넘베브

을 호출하여 `OleRegEnumVerbs`이 컨트롤에 대해 등록된 작업(동사)의 열거를 제공합니다.

```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```

### <a name="remarks"></a>설명

프로젝트의 .rgs 파일에 동사를 추가할 수 있습니다. 예를 들어 CIRCCTL을 참조하십시오. [CIRC](../../overview/visual-cpp-samples.md) 샘플의 RGS.

[IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs) SDK에서 열거형 참조.

## <a name="ioleobjectimplgetclientsite"></a><a name="getclientsite"></a>IOleObjectImpl::GetClientSite

컨트롤 클래스 데이터 멤버 [CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) *ppClientSite에* 포인터를 넣고 포인터의 참조 수를 증가시입니다.

```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```

### <a name="remarks"></a>설명

[IOleObject::GetClient를](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclientsite) Windows SDK에서 참조하십시오.

## <a name="ioleobjectimplgetclipboarddata"></a><a name="getclipboarddata"></a>IOleObjectImpl::GetClipboard데이터

클립보드에서 데이터를 검색합니다.

```
STDMETHOD(GetClipboardData)(
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IOleObject::GetClipboardWindows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclipboarddata) SDK에서 데이터를 참조하십시오.

## <a name="ioleobjectimplgetextent"></a><a name="getextent"></a>IOleObjectImpl::GetExtent

HIMETRIC 단위(단위당 0.01밀리미터)에서 실행 중인 컨트롤의 표시 크기를 검색합니다.

```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>설명

크기는 컨트롤 클래스 데이터 멤버 [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)에 저장됩니다.

[IOleObject::GetExtent](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getextent) 윈도우 SDK를 참조하십시오.

## <a name="ioleobjectimplgetmiscstatus"></a><a name="getmiscstatus"></a>아이올레오브젝트임플::겟미스시상태

을 호출하여 `OleRegGetMiscStatus`컨트롤에 대해 등록된 상태 정보에 대한 포인터를 반환합니다.

```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```

### <a name="remarks"></a>설명

상태 정보에는 컨트롤 및 프레젠테이션 데이터에서 지원하는 동작이 포함됩니다. 프로젝트의 .rgs 파일에 상태 정보를 추가할 수 있습니다.

[IOleObject::GetMisc상태](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) 윈도우 SDK를 참조하십시오.

## <a name="ioleobjectimplgetmoniker"></a><a name="getmoniker"></a>아이올레오브젝트임플::겟모니커

컨트롤의 모니커를 검색합니다.

```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IOleObject::GetMoniker](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmoniker) 윈도우 SDK를 참조하십시오.

## <a name="ioleobjectimplgetuserclassid"></a><a name="getuserclassid"></a>IOleObjectImpl::GetUserClassID

컨트롤의 클래스 식별자를 반환합니다.

```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```

### <a name="remarks"></a>설명

[IOleObject::GetUserClassID](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getuserclassid) Windows SDK를 참조하십시오.

## <a name="ioleobjectimplgetusertype"></a><a name="getusertype"></a>IOleObjectImpl::GetuserType

을 호출하여 `OleRegGetUserType`컨트롤의 사용자 유형 이름을 반환합니다.

```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```

### <a name="remarks"></a>설명

사용자 유형 이름은 메뉴 및 대화 상자와 같은 사용자 인터페이스 요소에 표시하는 데 사용됩니다. 프로젝트의 .rgs 파일에서 사용자 유형 이름을 변경할 수 있습니다.

[IOleObject::GetUserType](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getusertype) Windows SDK를 참조하십시오.

## <a name="ioleobjectimplinitfromdata"></a><a name="initfromdata"></a>IOleObjectImpl::이니트데이터 데이터

선택한 데이터에서 컨트롤을 초기화합니다.

```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IOleObject::InitFrom데이터](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata) 윈도우 SDK에서 를 참조하십시오.

## <a name="ioleobjectimplisuptodate"></a><a name="isuptodate"></a>아이올레오브젝트임플::이스업토데이트

컨트롤이 최신 상태인지 확인합니다.

```
STDMETHOD(IsUpToDate)(void);
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

[IOleObject::IsUpToDate](/windows/win32/api/oleidl/nf-oleidl-ioleobject-isuptodate) 윈도우 SDK를 참조하십시오.

## <a name="ioleobjectimplonpostverbdiscardundo"></a><a name="onpostverbdiscardundo"></a>아이올레오브젝트임플::온포스트버버버버폐기운도

[DoVerbDiscardUndo에서](#doverbdiscardundo) 호출하면 취소 상태가 삭제됩니다.

```
HRESULT OnPostVerbDiscardUndo();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

실행 취소 상태가 삭제된 후 실행하려는 코드로 이 메서드를 재정의합니다.

## <a name="ioleobjectimplonpostverbhide"></a><a name="onpostverbhide"></a>아이올레오브젝트임플::온포스트버브하이드

컨트롤이 숨겨진 후 [DoVerbHide에서](#doverbhide) 호출합니다.

```
HRESULT OnPostVerbHide();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

컨트롤이 숨김 후에 실행하려는 코드로 이 메서드를 재정의합니다.

## <a name="ioleobjectimplonpostverbinplaceactivate"></a><a name="onpostverbinplaceactivate"></a>IOleObjectImpl::에포스트버빈플레이스활성화

[DoVerbInPlace에서](#doverbinplaceactivate) 호출컨트롤이 활성화된 후 활성화합니다.

```
HRESULT OnPostVerbInPlaceActivate();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

컨트롤이 활성화된 후 실행하려는 코드로 이 메서드를 재정의합니다.

## <a name="ioleobjectimplonpostverbopen"></a><a name="onpostverbopen"></a>아이올레오브젝트임플::온포스트버브오픈

별도의 창에서 편집하기 위해 컨트롤을 연 후 [DoVerbOpen에서](#doverbopen) 호출합니다.

```
HRESULT OnPostVerbOpen();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

별도의 창에서 편집하기 위해 컨트롤을 연 후 실행하려는 코드로 이 메서드를 재정의합니다.

## <a name="ioleobjectimplonpostverbshow"></a><a name="onpostverbshow"></a>아이올레오브젝트임플::온포스트버브쇼

컨트롤이 표시 된 후 [DoVerbShow에](#doverbshow) 의해 호출 됩니다.

```
HRESULT OnPostVerbShow();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

컨트롤이 표시된 후 실행하려는 코드로 이 메서드를 재정의합니다.

## <a name="ioleobjectimplonpostverbuiactivate"></a><a name="onpostverbuiactivate"></a>IOleObjectImpl::에포스트버브UI활성화

컨트롤의 사용자 인터페이스가 활성화된 후 [DoVerbUIActivate에서](#doverbuiactivate) 호출합니다.

```
HRESULT OnPostVerbUIActivate();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

컨트롤의 사용자 인터페이스가 활성화된 후 실행하려는 코드로 이 메서드를 재정의합니다.

## <a name="ioleobjectimplonpreverbdiscardundo"></a><a name="onpreverbdiscardundo"></a>IOleObjectImpl::에프프리버 버버 버림운도

[DoVerbDiscardUndo에서](#doverbdiscardundo) 호출한 후 취소 상태가 삭제됩니다.

```
HRESULT OnPreVerbDiscardUndo();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

취소 상태삭제를 방지하려면 이 메서드를 재정의하여 오류 HRESULT를 반환합니다.

## <a name="ioleobjectimplonpreverbhide"></a><a name="onpreverbhide"></a>아이올레오브젝트임플::온프리버하이드

컨트롤이 숨겨지기 전에 [DoVerbHide에서](#doverbhide) 호출합니다.

```
HRESULT OnPreVerbHide();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

컨트롤이 숨겨지는 것을 방지하려면 이 메서드를 재정의하여 오류 HRESULT를 반환합니다.

## <a name="ioleobjectimplonpreverbinplaceactivate"></a><a name="onpreverbinplaceactivate"></a>IOleObjectImpl::에프프리버빈플레이스활성화

[DoVerbInPlace에서](#doverbinplaceactivate) 호출컨트롤이 활성화되기 전에 활성화합니다.

```
HRESULT OnPreVerbInPlaceActivate();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

컨트롤이 제자리에서 활성화되지 않도록 하려면 이 메서드를 재정의하여 오류 HRESULT를 반환합니다.

## <a name="ioleobjectimplonpreverbopen"></a><a name="onpreverbopen"></a>아이올레오브젝트임플::온프리버브오픈

별도의 창에서 편집하기 위해 컨트롤을 열기 전에 [DoVerbOpen에서](#doverbopen) 호출합니다.

```
HRESULT OnPreVerbOpen();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

별도의 창에서 편집하기 위해 컨트롤이 열리지 않도록 하려면 이 메서드를 재정의하여 오류 HRESULT를 반환합니다.

## <a name="ioleobjectimplonpreverbshow"></a><a name="onpreverbshow"></a>아이올레오브젝트임플::온프리버브쇼

컨트롤이 표시되기 전에 [DoVerbShow에서](#doverbshow) 호출합니다.

```
HRESULT OnPreVerbShow();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

컨트롤이 표시되지 않도록 하려면 이 메서드를 재정의하여 오류 HRESULT를 반환합니다.

## <a name="ioleobjectimplonpreverbuiactivate"></a><a name="onpreverbuiactivate"></a>IOleObjectImpl::에프리버브UI활성화

컨트롤의 사용자 인터페이스가 활성화되기 전에 [DoVerbUIActivate에서](#doverbuiactivate) 호출합니다.

```
HRESULT OnPreVerbUIActivate();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

컨트롤의 사용자 인터페이스가 활성화되지 않도록 하려면 이 메서드를 재정의하여 오류 HRESULT를 반환합니다.

## <a name="ioleobjectimplsetclientsite"></a><a name="setclientsite"></a>IOleObjectImpl::SetClientSite

컨테이너의 클라이언트 사이트에 대한 컨트롤을 알려줍니다.

```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```

### <a name="remarks"></a>설명

그런 다음 메서드는 S_OK 반환합니다.

[IOleObject::SetClientWindows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setclientsite) SDK에서 참조하세요.

## <a name="ioleobjectimplsetcolorscheme"></a><a name="setcolorscheme"></a>아이올레오브젝트임플::세트컬러스킴

컨트롤의 응용 프로그램에 색 구성표를 권장합니다(있는 경우).

```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IOleObject::SetColorWindows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) SDK에서 를 참조하십시오.

## <a name="ioleobjectimplsetextent"></a><a name="setextent"></a>IOleObjectImpl::SetExtent

컨트롤의 표시 영역 범위를 설정합니다.

```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>설명

그렇지 `SetExtent` 않으면 컨트롤 클래스 `psizel` 데이터 멤버 [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)에 의해 가리키는 값을 저장합니다. 이 값은 HIMETRIC 단위(단위당 0.01밀리미터)입니다.

컨트롤 클래스 데이터 멤버 [CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) `SetExtent` TRUE인 경우 컨트롤 `psizel` 클래스 데이터 멤버 [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)에 의해 가리키는 값도 저장합니다.

컨트롤 클래스 데이터 멤버 [CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) `SetExtent` TRUE인 `SendOnViewChange` 경우 호출하고 `SendOnDataChange` 조언 홀더에 등록된 모든 권고 싱크에 제어 크기가 변경되었음을 알립니다.

[IOleObject::Set익](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setextent) 윈도우 SDK를 참조하십시오.

## <a name="ioleobjectimplsethostnames"></a><a name="sethostnames"></a>IOleObjectImpl::SetHostnames

컨트롤에 컨테이너 응용 프로그램 및 컨테이너 문서의 이름을 지정합니다.

```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

[IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-sethostnames) SDK에서 SetHostNames를 참조하십시오.

## <a name="ioleobjectimplsetmoniker"></a><a name="setmoniker"></a>아이올레오브젝트임플::셋모니커

컨트롤에 모니커가 무엇인지 알려줍니다.

```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setmoniker) SDK에서 SetMoniker를 참조하십시오.

## <a name="ioleobjectimplunadvise"></a><a name="unadvise"></a>아이올레오브젝트임플::조언 불굴의

컨트롤 클래스의 `m_spOleAdviseHolder` 데이터 멤버에 저장된 권고 연결을 삭제합니다.

```
STDMETHOD(Unadvise)(DWORD dwConnection);
```

### <a name="remarks"></a>설명

[IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) SDK에서 조언 해제를 참조하십시오.

## <a name="ioleobjectimplupdate"></a><a name="update"></a>IOleObjectImpl::업데이트

컨트롤을 업데이트합니다.

```
STDMETHOD(Update)(void);
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

[IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-update) SDK에서 업데이트 참조.

## <a name="see-also"></a>참고 항목

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[액티브X컨트롤 인터페이스](/windows/win32/com/activex-controls-interfaces)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
