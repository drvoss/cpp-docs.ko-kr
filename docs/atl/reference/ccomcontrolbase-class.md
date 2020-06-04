---
title: CComControlBase 클래스
ms.date: 11/04/2016
f1_keywords:
- CComControlBase
- ATLCTL/ATL::CComControlBase
- ATLCTL/ATL::CComControlBase::AppearanceType
- ATLCTL/ATL::CComControlBase::CComControlBase
- ATLCTL/ATL::CComControlBase::ControlQueryInterface
- ATLCTL/ATL::CComControlBase::DoesVerbActivate
- ATLCTL/ATL::CComControlBase::DoesVerbUIActivate
- ATLCTL/ATL::CComControlBase::DoVerbProperties
- ATLCTL/ATL::CComControlBase::FireViewChange
- ATLCTL/ATL::CComControlBase::GetAmbientAppearance
- ATLCTL/ATL::CComControlBase::GetAmbientAutoClip
- ATLCTL/ATL::CComControlBase::GetAmbientBackColor
- ATLCTL/ATL::CComControlBase::GetAmbientCharSet
- ATLCTL/ATL::CComControlBase::GetAmbientCodePage
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayAsDefault
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayName
- ATLCTL/ATL::CComControlBase::GetAmbientFont
- ATLCTL/ATL::CComControlBase::GetAmbientFontDisp
- ATLCTL/ATL::CComControlBase::GetAmbientForeColor
- ATLCTL/ATL::CComControlBase::GetAmbientLocaleID
- ATLCTL/ATL::CComControlBase::GetAmbientMessageReflect
- ATLCTL/ATL::CComControlBase::GetAmbientPalette
- ATLCTL/ATL::CComControlBase::GetAmbientProperty
- ATLCTL/ATL::CComControlBase::GetAmbientRightToLeft
- ATLCTL/ATL::CComControlBase::GetAmbientScaleUnits
- ATLCTL/ATL::CComControlBase::GetAmbientShowGrabHandles
- ATLCTL/ATL::CComControlBase::GetAmbientShowHatching
- ATLCTL/ATL::CComControlBase::GetAmbientSupportsMnemonics
- ATLCTL/ATL::CComControlBase::GetAmbientTextAlign
- ATLCTL/ATL::CComControlBase::GetAmbientTopToBottom
- ATLCTL/ATL::CComControlBase::GetAmbientUIDead
- ATLCTL/ATL::CComControlBase::GetAmbientUserMode
- ATLCTL/ATL::CComControlBase::GetDirty
- ATLCTL/ATL::CComControlBase::GetZoomInfo
- ATLCTL/ATL::CComControlBase::InPlaceActivate
- ATLCTL/ATL::CComControlBase::InternalGetSite
- ATLCTL/ATL::CComControlBase::OnDraw
- ATLCTL/ATL::CComControlBase::OnDrawAdvanced
- ATLCTL/ATL::CComControlBase::OnKillFocus
- ATLCTL/ATL::CComControlBase::OnMouseActivate
- ATLCTL/ATL::CComControlBase::OnPaint
- ATLCTL/ATL::CComControlBase::OnSetFocus
- ATLCTL/ATL::CComControlBase::PreTranslateAccelerator
- ATLCTL/ATL::CComControlBase::SendOnClose
- ATLCTL/ATL::CComControlBase::SendOnDataChange
- ATLCTL/ATL::CComControlBase::SendOnRename
- ATLCTL/ATL::CComControlBase::SendOnSave
- ATLCTL/ATL::CComControlBase::SendOnViewChange
- ATLCTL/ATL::CComControlBase::SetControlFocus
- ATLCTL/ATL::CComControlBase::SetDirty
- ATLCTL/ATL::CComControlBase::m_bAutoSize
- ATLCTL/ATL::CComControlBase::m_bDrawFromNatural
- ATLCTL/ATL::CComControlBase::m_bDrawGetDataInHimetric
- ATLCTL/ATL::CComControlBase::m_bInPlaceActive
- ATLCTL/ATL::CComControlBase::m_bInPlaceSiteEx
- ATLCTL/ATL::CComControlBase::m_bNegotiatedWnd
- ATLCTL/ATL::CComControlBase::m_bRecomposeOnResize
- ATLCTL/ATL::CComControlBase::m_bRequiresSave
- ATLCTL/ATL::CComControlBase::m_bResizeNatural
- ATLCTL/ATL::CComControlBase::m_bUIActive
- ATLCTL/ATL::CComControlBase::m_bUsingWindowRgn
- ATLCTL/ATL::CComControlBase::m_bWasOnceWindowless
- ATLCTL/ATL::CComControlBase::m_bWindowOnly
- ATLCTL/ATL::CComControlBase::m_bWndLess
- ATLCTL/ATL::CComControlBase::m_hWndCD
- ATLCTL/ATL::CComControlBase::m_nFreezeEvents
- ATLCTL/ATL::CComControlBase::m_rcPos
- ATLCTL/ATL::CComControlBase::m_sizeExtent
- ATLCTL/ATL::CComControlBase::m_sizeNatural
- ATLCTL/ATL::CComControlBase::m_spAdviseSink
- ATLCTL/ATL::CComControlBase::m_spAmbientDispatch
- ATLCTL/ATL::CComControlBase::m_spClientSite
- ATLCTL/ATL::CComControlBase::m_spDataAdviseHolder
- ATLCTL/ATL::CComControlBase::m_spInPlaceSite
- ATLCTL/ATL::CComControlBase::m_spOleAdviseHolder
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
ms.openlocfilehash: 15cfa205337248181f02e6a1218d49e75bda58e6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748115"
---
# <a name="ccomcontrolbase-class"></a>CComControlBase 클래스

이 클래스는 ATL 컨트롤을 만들고 관리하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class ATL_NO_VTABLE CComControlBase
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[CComControlBase::모양 유형](#appearancetype)|`m_nAppearance` 주식 속성이 **짧은**형식이 아닌 경우 재정의합니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComControlBase::CComControlBase](#ccomcontrolbase)|생성자입니다.|
|[CComControlBase::~CComControlBase](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComControlBase::ControlQueryInterface](#controlqueryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|사용자가 컨트롤의 사용자 인터페이스(iVerb OLEIVERB_UIACTIVATE)를 활성화하거나, 사용자가 컨트롤을 두 번 클릭할 때 수행되는 동작(iVerb가*iVerb* OLEIVERB_PRIMARY 같음), 컨트롤(iVerb 가 OLEIVERB_SHOW 같음) 또는 컨트롤(iVerb와 OLEIVERB_INPLACEACTIVATE 같음)을 활성화하는 데*iVerb* 사용되는*iVerb* `IOleObjectImpl::DoVerb` *iVerb* 매개 변수가 활성화되는지 확인합니다.*iVerb*|
|[CComControlBase::DoesverbUIActivate](#doesverbuiactivate)|에서 `IOleObjectImpl::DoVerb` 사용되는 *iVerb* 매개 변수가 컨트롤의 사용자 인터페이스를 활성화하고 TRUE를 반환하도록 하는지 확인합니다.|
|[CComControlBase::DoVerbProperties](#doverbproperties)|컨트롤의 속성 페이지를 표시합니다.|
|[CComControlBase::파이어뷰체인지](#fireviewchange)|이 메서드를 호출하여 컨테이너에 컨트롤을 다시 그리도록 지시하거나 등록된 조언 싱크에 컨트롤보기가 변경되었음을 알립니다.|
|[CComControlBase::Get앰비언트외관](#getambientappearance)|DISPID_AMBIENT_APPEARANCE 검색, 컨트롤의 현재 모양 설정: 플랫의 경우 0, 3D의 경우 1입니다.|
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|컨테이너가 컨트롤 표시 영역의 자동 클리핑을 지원하는지 여부를 나타내는 플래그인 DISPID_AMBIENT_AUTOCLIP 검색합니다.|
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|컨테이너에 의해 정의된 모든 컨트롤의 주변 배경 색인 DISPID_AMBIENT_BACKCOLOR 검색합니다.|
|[CComControlBase::겟앰비언트차셋](#getambientcharset)|컨테이너에 의해 정의된 모든 컨트롤에 대해 설정된 주변 문자 집합인 DISPID_AMBIENT_CHARSET 검색합니다.|
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|컨테이너에 의해 정의된 모든 컨트롤에 대해 설정된 주변 문자 집합인 DISPID_AMBIENT_CODEPAGE 검색합니다.|
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|컨테이너가 이 사이트의 컨트롤을 기본 단추로 표시한 경우 true인 플래그인 DISPID_AMBIENT_DISPLAYASDEFAULT 검색하므로 단추 컨트롤은 더 두꺼운 프레임으로 자신을 그려야 합니다.|
|[CComControlBase::GetAmbient표시 이름](#getambientdisplayname)|컨테이너가 컨트롤에 제공한 이름을 DISPID_AMBIENT_DISPLAYNAME 검색합니다.|
|[CComControlBase::GetAmbientFont](#getambientfont)|컨테이너의 주변 `IFont` 인터페이스에 대한 포인터를 검색합니다.|
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|컨테이너의 앰비언트 `IFontDisp` 디스패치 인터페이스에 대한 포인터를 검색합니다.|
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|컨테이너에 의해 정의된 모든 컨트롤의 주변 전경 색상인 DISPID_AMBIENT_FORECOLOR 검색합니다.|
|[CComControlBase::겟앰비언트 로컬ID](#getambientlocaleid)|컨테이너에서 사용하는 언어의 식별자인 DISPID_AMBIENT_LOCALEID 검색합니다.|
|[CComControlBase::GetAmbient메시지 반영](#getambientmessagereflect)|컨테이너가 WM_DRAWITEM 창 메시지를 이벤트로 수신할지 여부를 나타내는 플래그인 DISPID_AMBIENT_MESSAGEREFLECT 검색합니다.|
|[CComControlBase::겟앰비언트 팔레트](#getambientpalette)|컨테이너의 HPALETTE에 액세스하는 데 사용되는 DISPID_AMBIENT_PALETTE 검색합니다.|
|[CComControlBase::겟앰비언트속성](#getambientproperty)|*id로*지정된 컨테이너 속성을 검색합니다.|
|[CComControlBase::겟앰비언트라이트토레프트](#getambientrighttoleft)|컨테이너에 의해 콘텐츠가 표시되는 방향인 DISPID_AMBIENT_RIGHTTOLEFT 검색합니다.|
|[CComControlBase::GetAmbient 스케일유닛](#getambientscaleunits)|레이블 표시를 위해 컨테이너의 주변 단위(예: 인치 또는 센티미터)DISPID_AMBIENT_SCALEUNITS 검색합니다.|
|[CComControlBase::겟앰비언트쇼그랩핸들](#getambientshowgrabhandles)|DISPID_AMBIENT_SHOWGRABHANDLES 검색하여 컨테이너가 활성화될 때 컨트롤이 그랩 핸들을 자체적으로 표시할 수 있는지 여부를 나타내는 플래그입니다.|
|[CComControlBase::GetAmbient쇼해칭](#getambientshowhatching)|DISPID_AMBIENT_SHOWHATCHING 검색, UI가 활성화 될 때 컨테이너가 해치 된 패턴으로 자신을 표시 할 수 있는지 여부를 나타내는 플래그.|
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|컨테이너가 키보드 니모닉을 지원하는지 여부를 나타내는 플래그인 DISPID_AMBIENT_SUPPORTSMNEMONICS 검색합니다.|
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|DISPID_AMBIENT_TEXTALIGN 검색하면 컨테이너에서 선호하는 텍스트 맞춤: 일반 정렬의 경우 0(숫자 오른쪽, 왼쪽 텍스트 왼쪽), 왼쪽 맞춤의 경우 1, 중심 맞춤의 경우 2, 오른쪽 맞춤의 경우 3입니다.|
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|컨테이너에 의해 콘텐츠가 표시되는 방향인 DISPID_AMBIENT_TOPTOBOTTOM 검색합니다.|
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|DISPID_AMBIENT_UIDEAD 검색, 컨테이너가 사용자 인터페이스 작업에 응답하도록 컨트롤을 원하는지 여부를 나타내는 플래그입니다.|
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|컨테이너가 실행 모드(TRUE) 또는 디자인 모드(FALSE)에 있는지 여부를 나타내는 플래그인 DISPID_AMBIENT_USERMODE 검색합니다.|
|[CComControlBase::GetDirty](#getdirty)|데이터 멤버의 `m_bRequiresSave`값을 반환합니다.|
|[CComControlBase::GetZoomInfo](#getzoominfo)|현재 편집을 위해 활성화된 컨트롤에 대해 분자 및 확대/축소 계수의 분모의 x 및 y 값을 검색합니다.|
|[CComControlBase::인플레이스활성화](#inplaceactivate)|컨트롤이 비활성 상태에서 *iVerb의* 동사가 나타내는 상태대로 전환하게 합니다.|
|[CComControlBase::내부GetSite](#internalgetsite)|식별된 인터페이스에 대한 포인터에 대한 제어 사이트를 쿼리하려면 이 메서드를 호출합니다.|
|[CComControlBase::온드로우](#ondraw)|컨트롤을 그리려면 이 메서드를 재정의합니다.|
|[CComControlBase::온드로우어드](#ondrawadvanced)|기본값은 `OnDrawAdvanced` 드로잉을 위해 정규화된 장치 컨텍스트를 준비한 `OnDraw` 다음 컨트롤 클래스의 메서드를 호출합니다.|
|[CComControlBase::온킬 포커스](#onkillfocus)|컨트롤이 활성 상태이고 유효한 제어 사이트가 있는지 확인한 다음 컨트롤이 포커스를 잃었다는 것을 컨테이너에 알립니다.|
|[CComControlBase::온마우스 활성화](#onmouseactivate)|UI가 사용자 모드에 있는지 확인한 다음 컨트롤을 활성화합니다.|
|[CComControlBase::온페인트](#onpaint)|페인팅을 위해 컨테이너를 준비하고 컨트롤의 클라이언트 영역을 가져옵니다. `OnDraw`|
|[CComControlBase::온셋 포커스](#onsetfocus)|컨트롤이 활성 상태이고 유효한 제어 사이트가 있는지 확인한 다음 컨트롤이 포커스를 얻은 컨테이너에 알립니다.|
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|이 메서드를 재정의하여 고유한 키보드 가속기 처리기를 제공합니다.|
|[CComControlBase::센드온클로즈](#sendonclose)|조언 자에게 등록된 모든 권고 싱크는 제어가 닫혔다는 것을 알수 있습니다.|
|[CComControlBase::센드온데이터체인지](#sendondatachange)|조언 자에게 등록된 모든 권고 싱크에 제어 데이터가 변경되었음을 알수 있습니다.|
|[CComControlBase::센드온리네임](#sendonrename)|조언 홀더에 등록된 모든 권고 싱크에 컨트롤에 새 모니커가 있음을 알게 합니다.|
|[CComControlBase::센드온세이브](#sendonsave)|조언 홀더에 등록된 모든 권고 싱크에 컨트롤이 저장되었음을 알수 있습니다.|
|[CComControlBase::센드온뷰체인지](#sendonviewchange)|등록된 모든 권고 싱크에 컨트롤보기가 변경되었음을 알수 있습니다.|
|[CComControlBase::세트 컨트롤 포커스](#setcontrolfocus)|키보드 포커스를 컨트롤에서 설정하거나 제거합니다.|
|[CComControlBase::SetDirty](#setdirty)|데이터 멤버를 `m_bRequiresSave` *bDirty*의 값으로 설정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComControlBase::m_bAutoSize](#m_bautosize)|컨트롤을 나타내는 플래그는 다른 크기일 수 없습니다.|
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|에서 가 `IDataObjectImpl::GetData` `CComControlBase::GetZoomInfo` `m_sizeNatural` 아니라 `m_sizeExtent`컨트롤 크기를 설정해야 한다는 플래그를 나타내고.|
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|그림을 그릴 `IDataObjectImpl::GetData` 때 픽셀이 아닌 HIMETRIC 단위를 사용해야 한다는 플래그를 표시합니다.|
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|컨트롤이 활성 상태임을 나타내는 플래그입니다.|
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|컨테이너를 나타내는 플래그는 `IOleInPlaceSiteEx` 인터페이스및 OCX96 컨트롤 기능(예: 창 없는 컨트롤 및 깜박임 없는 컨트롤)을 지원합니다.|
|[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)|OCX96 컨트롤 기능(예: 깜박임 없는 컨트롤 및 창 없는 컨트롤)에 대한 지원에 대해 컨트롤이 컨테이너와 협상했는지 여부와 컨트롤이 창또는 창없는지 여부를 나타내는 플래그입니다.|
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|컨테이너가 컨트롤의 표시 크기를 변경할 때 컨트롤을 나타내는 플래그가 해당 프레젠테이션을 재구성하려고 합니다.|
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|컨트롤이 마지막으로 저장된 이후 변경되었음을 나타내는 플래그입니다.|
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|컨테이너가 컨트롤의 표시 크기를 변경할 때 컨트롤의 자연 범위(크기가 조정되지 않은 실제 크기)의 크기를 조정하려고 하는 컨트롤을 나타내는 플래그입니다.|
|[CComControlBase::m_bUIActive](#m_buiactive)|메뉴 및 도구 모음과 같은 컨트롤의 사용자 인터페이스를 나타내는 플래그가 활성화되어 있습니다.|
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|컨트롤이 컨테이너 제공 창 영역을 사용하고 있음을 나타내는 플래그입니다.|
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|컨트롤을 나타내는 플래그는 창이 없지만 지금은 창이 없을 수도 있습니다.|
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|컨테이너가 창 없는 컨트롤을 지원하는 경우에도 컨트롤을 나타내는 플래그는 창으로 표시되어야 합니다.|
|[CComControlBase::m_bWndLess](#m_bwndless)|컨트롤이 창이 없다는 플래그입니다.|
|[CComControlBase::m_hWndCD](#m_hwndcd)|컨트롤과 연결된 창 핸들에 대한 참조를 포함합니다.|
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|컨테이너가 이벤트의 중간 해동(이벤트 수락)을 하지 않고 이벤트를 고정(이벤트 수락 거부)한 횟수입니다.|
|[CComControlBase::m_rcPos](#m_rcpos)|컨테이너의 좌표로 표현된 컨트롤의 픽셀 위치입니다.|
|[CComControlBase::m_sizeExtent](#m_sizeextent)|특정 디스플레이에 대한 HIMETRIC 단위의 제어 범위(각 장치는 0.01밀리미터)입니다.|
|[CComControlBase::m_sizeNatural](#m_sizenatural)|HIMETRIC 단위의 컨트롤의 물리적 크기입니다(각 단위는 0.01밀리미터).|
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|컨테이너의 권고 연결에 대한 직접 포인터(컨테이너의 [IAdviseSink)입니다.](/windows/win32/api/objidl/nn-objidl-iadvisesink)|
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|포인터를 `CComDispatchDriver` 통해 컨테이너의 속성을 검색하고 설정할 `IDispatch` 수 있는 개체입니다.|
|[CComControlBase::m_spClientSite](#m_spclientsite)|컨테이너 내에서 컨트롤의 클라이언트 사이트에 대한 포인터입니다.|
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|데이터 개체 간의 자문 연결을 유지하고 싱크를 조언하는 표준 수단을 제공합니다.|
|[CComControlBase::m_spInPlaceSite](#m_spinplacesite)|컨테이너의 [IOleInPlaceSite,](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite) [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)또는 [IOleInPlaceSitein](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) 인터페이스 포인터에 대한 포인터입니다.|
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|자문 연결을 유지하는 방법의 표준 구현을 제공합니다.|

## <a name="remarks"></a>설명

이 클래스는 ATL 컨트롤을 만들고 관리하는 메서드를 제공합니다. [CComControl 클래스는](../../atl/reference/ccomcontrol-class.md) `CComControlBase`에서 파생됩니다. ATL 제어 마법사를 사용하여 표준 제어 또는 DHTML 컨트롤을 만들면 마법사가 에서 클래스를 자동으로 `CComControlBase`파생시됩니다.

컨트롤 을 만드는 것에 대한 자세한 내용은 [ATL 자습서를](../../atl/active-template-library-atl-tutorial.md)참조하십시오. ATL 프로젝트 마법사에 대한 자세한 내용은 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)문서를 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="ccomcontrolbaseappearancetype"></a><a name="appearancetype"></a>CComControlBase::모양 유형

`m_nAppearance` 주식 속성이 **짧은**형식이 아닌 경우 재정의합니다.

```
typedef short AppearanceType;
```

### <a name="remarks"></a>설명

ATL 제어 마법사는 짧은 형식의 주식 속성을 추가합니다. `m_nAppearance` 다른 `AppearanceType` 데이터 형식을 사용하는 경우 재정의합니다.

## <a name="ccomcontrolbaseccomcontrolbase"></a><a name="ccomcontrolbase"></a>CComControlBase::CComControlBase

생성자입니다.

```
CComControlBase(HWND& h);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
컨트롤과 연결된 창에 대한 핸들입니다.

### <a name="remarks"></a>설명

컨트롤 크기를 5080X5080 HIMETRIC 단위(2"X2")로 초기화하고 `CComControlBase` 데이터 멤버 값을 NULL 또는 FALSE로 초기화합니다.

## <a name="ccomcontrolbaseccomcontrolbase"></a><a name="dtor"></a>CComControlBase::~CComControlBase

소멸자입니다.

```
~CComControlBase();
```

### <a name="remarks"></a>설명

컨트롤이 창이 있는 `~CComControlBase` 경우 [DestroyWindow](/windows/win32/api/winuser/nf-winuser-destroywindow)를 호출하여 컨트롤을 파괴합니다.

## <a name="ccomcontrolbasecontrolqueryinterface"></a><a name="controlqueryinterface"></a>CComControlBase::제어 쿼리 인터페이스

요청된 인터페이스에 대한 포인터를 검색합니다.

```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
요청되는 인터페이스의 GUID입니다.

*ppv*<br/>
인터페이스를 찾을 수 없는 경우 *iid*또는 NULL로 식별된 인터페이스 포인터에 대한 포인터입니다.

### <a name="remarks"></a>설명

COM 맵 테이블의 인터페이스만 처리합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]

## <a name="ccomcontrolbasedoesverbactivate"></a><a name="doesverbactivate"></a>CComControlBase::DoesVerbActivate

사용자가 컨트롤의 사용자 인터페이스(iVerb OLEIVERB_UIACTIVATE)를 활성화하거나, 사용자가 컨트롤을 두 번 클릭할 때 수행되는 동작(iVerb가*iVerb* OLEIVERB_PRIMARY 같음), 컨트롤(iVerb 가 OLEIVERB_SHOW 같음) 또는 컨트롤(iVerb와 OLEIVERB_INPLACEACTIVATE 같음)을 활성화하는 데*iVerb* 사용되는*iVerb* `IOleObjectImpl::DoVerb` *iVerb* 매개 변수가 활성화되는지 확인합니다.*iVerb*

```
BOOL DoesVerbActivate(LONG iVerb);
```

### <a name="parameters"></a>매개 변수

*iVerb*<br/>
`DoVerb`에서 수행할 작업을 나타내는 값입니다.

### <a name="return-value"></a>Return Value

*iVerb가* OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW 또는 OLEIVERB_INPLACEACTIVATE 같으면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 고유한 활성화 동사를 정의할 수 있습니다.

## <a name="ccomcontrolbasedoesverbuiactivate"></a><a name="doesverbuiactivate"></a>CComControlBase::DoesverbUIActivate

에서 `IOleObjectImpl::DoVerb` 사용되는 *iVerb* 매개 변수가 컨트롤의 사용자 인터페이스를 활성화하고 TRUE를 반환하도록 하는지 확인합니다.

```
BOOL DoesVerbUIActivate(LONG iVerb);
```

### <a name="parameters"></a>매개 변수

*iVerb*<br/>
`DoVerb`에서 수행할 작업을 나타내는 값입니다.

### <a name="return-value"></a>Return Value

*iVerb가* OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW 또는 OLEIVERB_INPLACEACTIVATE 같으면 TRUE를 반환합니다. 그렇지 않으면 메서드는 FALSE를 반환합니다.

## <a name="ccomcontrolbasedoverbproperties"></a><a name="doverbproperties"></a>CComControlBase::Doverb속성

컨트롤의 속성 페이지를 표시합니다.

```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
예약되어 있습니다.

*hwndParent*<br/>
컨트롤을 포함하는 창의 핸들입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]

[!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]

## <a name="ccomcontrolbasefireviewchange"></a><a name="fireviewchange"></a>CComControlBase::파이어뷰체인지

이 메서드를 호출하여 컨테이너에 컨트롤을 다시 그리도록 지시하거나 등록된 조언 싱크에 컨트롤보기가 변경되었음을 알립니다.

```
HRESULT FireViewChange();
```

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

컨트롤이 활성 상태인 경우(컨트롤 클래스 데이터 멤버 [CComControlBase::m_bInPlaceActive](#m_binplaceactive) TRUE) 전체 컨트롤을 다시 그릴 컨테이너에 알려주는 것입니다. 컨트롤이 비활성 상태인 경우 컨트롤의 등록된 조언 싱크(컨트롤 클래스 데이터 멤버 [CComControlBase::m_spAdviseSink)를](#m_spadvisesink)통해 컨트롤의 보기가 변경되었음을 알수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]

## <a name="ccomcontrolbasegetambientappearance"></a><a name="getambientappearance"></a>CComControlBase::Get앰비언트외관

DISPID_AMBIENT_APPEARANCE 검색, 컨트롤의 현재 모양 설정: 플랫의 경우 0, 3D의 경우 1입니다.

```
HRESULT GetAmbientAppearance(short& nAppearance);
```

### <a name="parameters"></a>매개 변수

*nAppearance*<br/>
숙소는 DISPID_AMBIENT_APPEARANCE.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]

## <a name="ccomcontrolbasegetambientautoclip"></a><a name="getambientautoclip"></a>CComControlBase::GetAmbientAutoClip

컨테이너가 컨트롤 표시 영역의 자동 클리핑을 지원하는지 여부를 나타내는 플래그인 DISPID_AMBIENT_AUTOCLIP 검색합니다.

```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```

### <a name="parameters"></a>매개 변수

*bAutoClip*<br/>
숙소는 DISPID_AMBIENT_AUTOCLIP.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetambientbackcolor"></a><a name="getambientbackcolor"></a>CComControlBase::겟앰비언트백컬러

컨테이너에 의해 정의된 모든 컨트롤의 주변 배경 색인 DISPID_AMBIENT_BACKCOLOR 검색합니다.

```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```

### <a name="parameters"></a>매개 변수

*BackColor*<br/>
숙소는 DISPID_AMBIENT_BACKCOLOR.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetambientcharset"></a><a name="getambientcharset"></a>CComControlBase::겟앰비언트차셋

컨테이너에 의해 정의된 모든 컨트롤에 대해 설정된 주변 문자 집합인 DISPID_AMBIENT_CHARSET 검색합니다.

```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```

### <a name="parameters"></a>매개 변수

*bstrCharSet*<br/>
숙소는 DISPID_AMBIENT_CHARSET.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="ccomcontrolbasegetambientcodepage"></a><a name="getambientcodepage"></a>CComControlBase::GetAmbientCodePage

컨테이너에 의해 정의된 모든 컨트롤의 앰비언트 코드 페이지인 DISPID_AMBIENT_CODEPAGE 검색합니다.

```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```

### <a name="parameters"></a>매개 변수

*ulCodePage*<br/>
숙소는 DISPID_AMBIENT_CODEPAGE.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="ccomcontrolbasegetambientdisplayasdefault"></a><a name="getambientdisplayasdefault"></a>CComControlBase::GetAmbient디스플레이기본

컨테이너가 이 사이트의 컨트롤을 기본 단추로 표시한 경우 true인 플래그인 DISPID_AMBIENT_DISPLAYASDEFAULT 검색하므로 단추 컨트롤은 더 두꺼운 프레임으로 자신을 그려야 합니다.

```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```

### <a name="parameters"></a>매개 변수

*bDisplayAsDefault*<br/>
숙소는 DISPID_AMBIENT_DISPLAYASDEFAULT.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetambientdisplayname"></a><a name="getambientdisplayname"></a>CComControlBase::GetAmbient표시 이름

컨테이너가 컨트롤에 제공한 이름을 DISPID_AMBIENT_DISPLAYNAME 검색합니다.

```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```

### <a name="parameters"></a>매개 변수

*bstrDisplayName*<br/>
숙소는 DISPID_AMBIENT_DISPLAYNAME.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetambientfont"></a><a name="getambientfont"></a>CComControlBase::겟앰비언트폰트

컨테이너의 주변 `IFont` 인터페이스에 대한 포인터를 검색합니다.

```
HRESULT GetAmbientFont(IFont** ppFont);
```

### <a name="parameters"></a>매개 변수

*ppFont*<br/>
컨테이너의 주변 [IFont](/windows/win32/api/ocidl/nn-ocidl-ifont) 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

속성이 NULL이면 포인터는 NULL입니다. 포인터가 NULL이 아닌 경우 호출자는 포인터를 해제해야 합니다.

## <a name="ccomcontrolbasegetambientfontdisp"></a><a name="getambientfontdisp"></a>CComControlBase::겟앰비언트폰티스

컨테이너의 앰비언트 `IFontDisp` 디스패치 인터페이스에 대한 포인터를 검색합니다.

```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```

### <a name="parameters"></a>매개 변수

*ppFont*<br/>
컨테이너의 주변 [IFontDisp](/windows/win32/api/ocidl/nn-ocidl-ifontdisp) 디스패치 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

속성이 NULL이면 포인터는 NULL입니다. 포인터가 NULL이 아닌 경우 호출자는 포인터를 해제해야 합니다.

## <a name="ccomcontrolbasegetambientforecolor"></a><a name="getambientforecolor"></a>CComControlBase::GetAmbient포어컬러

컨테이너에 의해 정의된 모든 컨트롤의 주변 전경 색상인 DISPID_AMBIENT_FORECOLOR 검색합니다.

```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```

### <a name="parameters"></a>매개 변수

*Forecolor*<br/>
숙소는 DISPID_AMBIENT_FORECOLOR.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetambientlocaleid"></a><a name="getambientlocaleid"></a>CComControlBase::겟앰비언트 로컬ID

컨테이너에서 사용하는 언어의 식별자인 DISPID_AMBIENT_LOCALEID 검색합니다.

```
HRESULT GetAmbientLocaleID(LCID& lcid);
```

### <a name="parameters"></a>매개 변수

*Lcid*<br/>
숙소는 DISPID_AMBIENT_LOCALEID.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

컨트롤은 이 식별자를 사용하여 사용자 인터페이스를 다른 언어로 조정할 수 있습니다.

## <a name="ccomcontrolbasegetambientmessagereflect"></a><a name="getambientmessagereflect"></a>CComControlBase::GetAmbient메시지 반영

컨테이너가 창 메시지를 `WM_DRAWITEM`이벤트로 수신할지 여부를 나타내는 플래그인 DISPID_AMBIENT_MESSAGEREFLECT 검색합니다.

```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```

### <a name="parameters"></a>매개 변수

*bMessageReflect*<br/>
숙소는 DISPID_AMBIENT_MESSAGEREFLECT.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetambientpalette"></a><a name="getambientpalette"></a>CComControlBase::겟앰비언트 팔레트

컨테이너의 HPALETTE에 액세스하는 데 사용되는 DISPID_AMBIENT_PALETTE 검색합니다.

```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```

### <a name="parameters"></a>매개 변수

*hPalette*<br/>
숙소는 DISPID_AMBIENT_PALETTE.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetambientproperty"></a><a name="getambientproperty"></a>CComControlBase::겟앰비언트속성

*dispid에서*지정한 컨테이너 속성을 검색합니다.

```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```

### <a name="parameters"></a>매개 변수

*디스피드 (것)들*<br/>
검색할 컨테이너 속성의 식별자입니다.

*var*<br/>
속성을 받을 변수입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

ATL은 특정 속성을 검색하는 도우미 함수 집합을 제공했습니다(예: [CComControlBase:GetAmbientBackColor)](#getambientbackcolor) 사용 가능한 적절한 방법이 없는 `GetAmbientProperty`경우 을 사용합니다.

## <a name="ccomcontrolbasegetambientrighttoleft"></a><a name="getambientrighttoleft"></a>CComControlBase::겟앰비언트라이트토레프트

컨테이너에 의해 콘텐츠가 표시되는 방향인 DISPID_AMBIENT_RIGHTTOLEFT 검색합니다.

```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```

### <a name="parameters"></a>매개 변수

*bRightToLeft*<br/>
숙소는 DISPID_AMBIENT_RIGHTTOLEFT. 콘텐츠가 오른쪽에서 왼쪽으로 표시되는 경우 TRUE로 설정, 왼쪽에서 오른쪽으로 표시되는 경우 FALSE로 설정합니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="ccomcontrolbasegetambientscaleunits"></a><a name="getambientscaleunits"></a>CComControlBase::GetAmbient 스케일유닛

레이블 표시를 위해 컨테이너의 주변 단위(예: 인치 또는 센티미터)DISPID_AMBIENT_SCALEUNITS 검색합니다.

```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```

### <a name="parameters"></a>매개 변수

*bstrScaleUnits*<br/>
숙소는 DISPID_AMBIENT_SCALEUNITS.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetambientshowgrabhandles"></a><a name="getambientshowgrabhandles"></a>CComControlBase::겟앰비언트쇼그랩핸들

DISPID_AMBIENT_SHOWGRABHANDLES 검색하여 컨테이너가 활성화될 때 컨트롤이 그랩 핸들을 자체적으로 표시할 수 있는지 여부를 나타내는 플래그입니다.

```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```

### <a name="parameters"></a>매개 변수

*bShowGrabHandles*<br/>
숙소는 DISPID_AMBIENT_SHOWGRABHANDLES.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetambientshowhatching"></a><a name="getambientshowhatching"></a>CComControlBase::GetAmbient쇼해칭

DISPID_AMBIENT_SHOWHATCHING 검색, 컨테이너 컨트롤의 사용자 인터페이스가 활성화 될 때 해치 된 패턴으로 자신을 표시 할 수 있는지 여부를 나타내는 플래그.

```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```

### <a name="parameters"></a>매개 변수

*bShowHatching*<br/>
숙소는 DISPID_AMBIENT_SHOWHATCHING.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetambientsupportsmnemonics"></a><a name="getambientsupportsmnemonics"></a>CComControlBase::GetAmbientSupportsMnemonics

컨테이너가 키보드 니모닉을 지원하는지 여부를 나타내는 플래그인 DISPID_AMBIENT_SUPPORTSMNEMONICS 검색합니다.

```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```

### <a name="parameters"></a>매개 변수

*bSupportsMnemonics*<br/>
숙소는 DISPID_AMBIENT_SUPPORTSMNEMONICS.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetambienttextalign"></a><a name="getambienttextalign"></a>CComControlBase::GetAmbient텍스트정렬

DISPID_AMBIENT_TEXTALIGN 검색하면 컨테이너에서 선호하는 텍스트 맞춤: 일반 정렬의 경우 0(숫자 오른쪽, 왼쪽 텍스트 왼쪽), 왼쪽 맞춤의 경우 1, 중심 맞춤의 경우 2, 오른쪽 맞춤의 경우 3입니다.

```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```

### <a name="parameters"></a>매개 변수

*nTextAlign*<br/>
숙소는 DISPID_AMBIENT_TEXTALIGN.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetambienttoptobottom"></a><a name="getambienttoptobottom"></a>CComControlBase::GetAmbientTopToBottom

컨테이너에 의해 콘텐츠가 표시되는 방향인 DISPID_AMBIENT_TOPTOBOTTOM 검색합니다.

```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```

### <a name="parameters"></a>매개 변수

*bTopToBottom*<br/>
숙소는 DISPID_AMBIENT_TOPTOBOTTOM. 텍스트가 위에서 아래로 표시되는 경우 TRUE로 설정되고 아래쪽에서 위쪽으로 표시되는 경우 FALSE로 설정합니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="ccomcontrolbasegetambientuidead"></a><a name="getambientuidead"></a>CComControlBase::겟앰비언트UI데드

DISPID_AMBIENT_UIDEAD 검색, 컨테이너가 사용자 인터페이스 작업에 응답하도록 컨트롤을 원하는지 여부를 나타내는 플래그입니다.

```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```

### <a name="parameters"></a>매개 변수

*bUIDead*<br/>
숙소는 DISPID_AMBIENT_UIDEAD.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

TRUE이면 컨트롤이 응답하지 않아야 합니다. 이 플래그는 DISPID_AMBIENT_USERMODE 플래그에 관계없이 적용됩니다. [CComControlBase::GetAmbientUserMode](#getambientusermode)를 참조하십시오.

## <a name="ccomcontrolbasegetambientusermode"></a><a name="getambientusermode"></a>CComControlBase::GetAmbient유저모드

컨테이너가 실행 모드(TRUE) 또는 디자인 모드(FALSE)에 있는지 여부를 나타내는 플래그인 DISPID_AMBIENT_USERMODE 검색합니다.

```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```

### <a name="parameters"></a>매개 변수

*bUserMode*<br/>
숙소는 DISPID_AMBIENT_USERMODE.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomcontrolbasegetdirty"></a><a name="getdirty"></a>CComControlBase::GetDirty

데이터 멤버의 `m_bRequiresSave`값을 반환합니다.

```
BOOL GetDirty();
```

### <a name="return-value"></a>Return Value

m_bRequiresSave 데이터 [멤버](#m_brequiressave)의 값을 반환합니다.

### <a name="remarks"></a>설명

이 값은 [CComControlBase::SetDirty](#setdirty)을 사용하여 설정됩니다.

## <a name="ccomcontrolbasegetzoominfo"></a><a name="getzoominfo"></a>CComControlBase::GetZoomInfo

현재 편집을 위해 활성화된 컨트롤에 대해 분자 및 확대/축소 계수의 분모의 x 및 y 값을 검색합니다.

```cpp
void GetZoomInfo(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>매개 변수

*디*<br/>
확대/축소 계수의 분자 및 분모를 보유하는 구조입니다. 자세한 내용은 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)를 참조하십시오.

### <a name="remarks"></a>설명

확대/축소 계수는 컨트롤의 자연 크기에서 현재 범위의 비율입니다.

## <a name="ccomcontrolbaseinplaceactivate"></a><a name="inplaceactivate"></a>CComControlBase::인플레이스활성화

컨트롤이 비활성 상태에서 *iVerb의* 동사가 나타내는 상태대로 전환하게 합니다.

```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```

### <a name="parameters"></a>매개 변수

*iVerb*<br/>
[IOleObjectImpl::DoVerb에](../../atl/reference/ioleobjectimpl-class.md#doverb)의해 수행될 작업을 나타내는 값입니다.

*prcPosRect*<br/>
위치 제어의 위치에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

활성화하기 전에 이 메서드는 컨트롤에 클라이언트 사이트가 있는지 확인하고, 표시되는 컨트롤의 양을 확인하고, 부모 창에서 컨트롤의 위치를 가져옵니다. 컨트롤이 활성화된 후 이 메서드는 컨트롤의 사용자 인터페이스를 활성화하고 컨테이너에 컨트롤을 표시하도록 지시합니다.

또한 이 메서드는 `IOleInPlaceSite` `IOleInPlaceSiteEx`컨트롤에 `IOleInPlaceSiteWindowless` 대한 의 또는 인터페이스 포인터를 검색하고 컨트롤 클래스의 데이터 멤버 [CComControlBase::m_spInPlaceSite](#m_spinplacesite)에 저장합니다. 컨트롤 클래스 데이터 멤버 [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex): [CComControlBase:m_bWndLess](#m_bwndless): [CComControlBase :m_bWasOnceWindowless :](#m_bwasoncewindowless)및 [CComControlBase :m_bNegotiatedWnd](#m_bnegotiatedwnd) true로 설정됩니다.

## <a name="ccomcontrolbaseinternalgetsite"></a><a name="internalgetsite"></a>CComControlBase::내부GetSite

식별된 인터페이스에 대한 포인터에 대한 제어 사이트를 쿼리하려면 이 메서드를 호출합니다.

```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
*ppUnkSite에서*반환해야 하는 인터페이스 포인터의 IID입니다.

*ppUnkSite*<br/>
*riid에서*요청된 인터페이스 포인터를 수신하는 포인터 변수의 주소입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

사이트가 *riid에서*요청된 인터페이스를 지원하는 경우 *포인터는 ppUnkSite를*사용하여 반환됩니다. 그렇지 않으면 *ppUnkSiteNULL로* 설정됩니다.

## <a name="ccomcontrolbasem_bautosize"></a><a name="m_bautosize"></a>CComControlBase::m_bAutoSize

컨트롤을 나타내는 플래그는 다른 크기일 수 없습니다.

```
unsigned m_bAutoSize:1;
```

### <a name="remarks"></a>설명

이 플래그는 `IOleObjectImpl::SetExtent` 확인되고 TRUE인 경우 함수가 E_FAIL 반환합니다.

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

ATL 컨트롤 마법사의 [스톡 속성](../../atl/reference/stock-properties-atl-control-wizard.md) 탭에서 **자동 크기** 옵션을 추가 하는 경우 마법사는이 데이터 멤버를 컨트롤 클래스에 자동으로 만들고, 속성에 대 한 put 및 get 메서드를 만들며, [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)을 지원 합니다. 속성이 변경 될 때 컨테이너에 자동으로 알리려면입니다.

## <a name="ccomcontrolbasem_bdrawfromnatural"></a><a name="m_bdrawfromnatural"></a>CComControlBase::m_bDrawFromNatural

에서 가 `IDataObjectImpl::GetData` `CComControlBase::GetZoomInfo` `m_sizeNatural` 아니라 `m_sizeExtent`컨트롤 크기를 설정해야 한다는 플래그를 나타내고.

```
unsigned m_bDrawFromNatural:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_bdrawgetdatainhimetric"></a><a name="m_bdrawgetdatainhimetric"></a>CComControlBase::m_bDrawGetDataInHimetric

그림을 그릴 `IDataObjectImpl::GetData` 때 픽셀이 아닌 HIMETRIC 단위를 사용해야 한다는 플래그를 표시합니다.

```
unsigned m_bDrawGetDataInHimetric:1;
```

### <a name="remarks"></a>설명

각 논리 HIMETRIC 단위는 0.01 밀리미터입니다.

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_binplaceactive"></a><a name="m_binplaceactive"></a>CComControlBase::m_bInPlaceActive

컨트롤이 활성 상태임을 나타내는 플래그입니다.

```
unsigned m_bInPlaceActive:1;
```

### <a name="remarks"></a>설명

즉, 컨트롤이 표시되고 창(있는 경우)이 표시되지만 메뉴 및 도구 모음이 활성화되지 않을 수 있습니다. 플래그는 `m_bUIActive` 메뉴와 같은 컨트롤의 사용자 인터페이스도 활성화되어 있음을 나타냅니다.

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_binplacesiteex"></a><a name="m_binplacesiteex"></a>CComControlBase::m_bInPlaceSiteEx

컨테이너를 나타내는 플래그는 `IOleInPlaceSiteEx` 인터페이스및 OCX96 컨트롤 기능(예: 창 없는 컨트롤 및 깜박임 없는 컨트롤)을 지원합니다.

```
unsigned m_bInPlaceSiteEx:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

데이터 멤버 `m_spInPlaceSite`는 `m_bWndLess` 및 `m_bInPlaceSiteEx` 플래그의 값에 따라 [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex) 또는 [IOleInPlaceSiteWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) 인터페이스를 가리킵니다. 포인터가 유효하려면 데이터 멤버가 `m_bNegotiatedWnd` TRUE여야 `m_spInPlaceSite` 합니다.

FALSE이고 `m_bWndLess` `m_bInPlaceSiteEx` TRUE인 경우 `m_spInPlaceSite` 인터페이스 `IOleInPlaceSiteEx` 포인터입니다. 이러한 세 데이터 멤버 간의 관계를 보여 주면 [m_spInPlaceSite](#m_spinplacesite) 참조하세요.

## <a name="ccomcontrolbasem_bnegotiatedwnd"></a><a name="m_bnegotiatedwnd"></a>CComControlBase::m_bNegotiatedWnd

OCX96 컨트롤 기능(예: 깜박임 없는 컨트롤 및 창 없는 컨트롤)에 대한 지원에 대해 컨트롤이 컨테이너와 협상했는지 여부와 컨트롤이 창또는 창없는지 여부를 나타내는 플래그입니다.

```
unsigned m_bNegotiatedWnd:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

포인터가 `m_bNegotiatedWnd` 유효하려면 플래그가 `m_spInPlaceSite` TRUE여야 합니다.

## <a name="ccomcontrolbasem_brecomposeonresize"></a><a name="m_brecomposeonresize"></a>CComControlBase::m_bRecomposeOnResize

컨테이너가 컨트롤의 표시 크기를 변경할 때 컨트롤을 나타내는 플래그가 해당 프레젠테이션을 재구성하려고 합니다.

```
unsigned m_bRecomposeOnResize:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

이 플래그는 [IOleObjectImpl::SetExtent에서](../../atl/reference/ioleobjectimpl-class.md#setextent) 검사하고 `SetExtent` TRUE인 경우 뷰 변경 컨테이너에 대해 알리고 있습니다. 이 플래그가 설정된 경우 [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc) 열거형의 OLEMISC_RECOMPOSEONRESIZE 비트도 설정해야 합니다.

## <a name="ccomcontrolbasem_brequiressave"></a><a name="m_brequiressave"></a>CComControlBase::m_bRequiresSave

컨트롤이 마지막으로 저장된 이후 변경되었음을 나타내는 플래그입니다.

```
unsigned m_bRequiresSave:1;
```

### <a name="remarks"></a>설명

값은 `m_bRequiresSave` [CComControlBase::SetDirty로](#setdirty) 설정하고 [CComControlBase::GetDirty](#getdirty)로 검색할 수 있습니다.

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_bresizenatural"></a><a name="m_bresizenatural"></a>CComControlBase::m_bResizeNatural

컨테이너가 컨트롤의 표시 크기를 변경할 때 컨트롤의 자연 범위(크기가 조정되지 않은 실제 크기)의 크기를 조정하려고 하는 컨트롤을 나타내는 플래그입니다.

```
unsigned m_bResizeNatural:1;
```

### <a name="remarks"></a>설명

이 플래그는 `IOleObjectImpl::SetExtent` 에 의해 검사되며 TRUE인 `SetExtent` 경우 `m_sizeNatural`전달된 크기가 에 할당됩니다.

`SetExtent` 전달된 크기는 `m_bResizeNatural`의 값에 관계없이 항상 에 `m_sizeExtent`할당됩니다.

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_buiactive"></a><a name="m_buiactive"></a>CComControlBase::m_bUIActive

메뉴 및 도구 모음과 같은 컨트롤의 사용자 인터페이스를 나타내는 플래그가 활성화되어 있습니다.

```
unsigned m_bUIActive:1;
```

### <a name="remarks"></a>설명

플래그는 `m_bInPlaceActive` 컨트롤이 활성 상태이지만 사용자 인터페이스가 활성 상태임을 나타냅니다.

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_busingwindowrgn"></a><a name="m_busingwindowrgn"></a>CComControlBase::m_bUsingWindowRgn

컨트롤이 컨테이너 제공 창 영역을 사용하고 있음을 나타내는 플래그입니다.

```
unsigned m_bUsingWindowRgn:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_bwasoncewindowless"></a><a name="m_bwasoncewindowless"></a>CComControlBase::m_bWasOnceWindowless

컨트롤을 나타내는 플래그는 창이 없지만 지금은 창이 없을 수도 있습니다.

```
unsigned m_bWasOnceWindowless:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_bwindowonly"></a><a name="m_bwindowonly"></a>CComControlBase::m_bWindowOnly

컨테이너가 창 없는 컨트롤을 지원하는 경우에도 컨트롤을 나타내는 플래그는 창으로 표시되어야 합니다.

```
unsigned m_bWindowOnly:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_bwndless"></a><a name="m_bwndless"></a>CComControlBase::m_bWndLess

컨트롤이 창이 없다는 플래그입니다.

```
unsigned m_bWndLess:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

`m_spInPlaceSite` 데이터 멤버는 [IOleInPlaceSite,](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite) [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)또는 [IOleInPlaceSiteIn[iOleInPlaceSiteIn]](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) 및 `m_bWndLess` [CComControlBase:m_bInPlaceSiteEx](#m_binplacesiteex) 플래그의 값에 따라 표시됩니다. (데이터 멤버 [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) [CComControlBase::m_spInPlaceSite](#m_spinplacesite) 포인터가 유효하려면 TRUE여야 합니다.)

TRUE인 `m_bWndLess` 경우 `m_spInPlaceSite` 인터페이스 `IOleInPlaceSiteWindowless` 포인터입니다. 이러한 데이터 멤버 간의 전체 관계를 보여 주면 [CComControlBase::m_spInPlaceSite](#m_spinplacesite) 를 참조하십시오.

## <a name="ccomcontrolbasem_hwndcd"></a><a name="m_hwndcd"></a>CComControlBase::m_hWndCD

컨트롤과 연결된 창 핸들에 대한 참조를 포함합니다.

```
HWND& m_hWndCD;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_nfreezeevents"></a><a name="m_nfreezeevents"></a>CComControlBase::m_nFreezeEvents

컨테이너가 이벤트의 중간 해동(이벤트 수락)을 하지 않고 이벤트를 고정(이벤트 수락 거부)한 횟수입니다.

```
short m_nFreezeEvents;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_rcpos"></a><a name="m_rcpos"></a>CComControlBase::m_rcPos

컨테이너의 좌표로 표현된 컨트롤의 픽셀 위치입니다.

```
RECT m_rcPos;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_sizeextent"></a><a name="m_sizeextent"></a>CComControlBase::m_sizeExtent

특정 디스플레이에 대한 HIMETRIC 단위의 제어 범위(각 장치는 0.01밀리미터)입니다.

```
SIZE m_sizeExtent;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

이 크기는 디스플레이에 따라 배율이 조정됩니다. 컨트롤의 물리적 크기는 데이터 `m_sizeNatural` 멤버에 지정되고 고정됩니다.

전역 함수 [AtlHiMetricToPixel을](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)사용하여 크기를 픽셀로 변환할 수 있습니다.

## <a name="ccomcontrolbasem_sizenatural"></a><a name="m_sizenatural"></a>CComControlBase::m_sizeNatural

HIMETRIC 단위의 컨트롤의 물리적 크기입니다(각 단위는 0.01밀리미터).

```
SIZE m_sizeNatural;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

이 크기는 고정된 반면 `m_sizeExtent` 의 크기는 디스플레이에 의해 배율이 조정됩니다.

전역 함수 [AtlHiMetricToPixel을](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)사용하여 크기를 픽셀로 변환할 수 있습니다.

## <a name="ccomcontrolbasem_spadvisesink"></a><a name="m_spadvisesink"></a>CComControlBase::m_spAdviseSink

컨테이너의 권고 연결에 대한 직접 포인터(컨테이너의 [IAdviseSink)입니다.](/windows/win32/api/objidl/nn-objidl-iadvisesink)

```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_spambientdispatch"></a><a name="m_spambientdispatch"></a>CComControlBase::m_spAmbientDispatch

`CComDispatchDriver` 포인터를 통해 개체의 속성을 검색하고 설정할 `IDispatch` 수 있는 개체입니다.

```
CComDispatchDriver m_spAmbientDispatch;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_spclientsite"></a><a name="m_spclientsite"></a>CComControlBase::m_spClientSite

컨테이너 내에서 컨트롤의 클라이언트 사이트에 대한 포인터입니다.

```
CComPtr<IOleClientSite>
    m_spClientSite;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

## <a name="ccomcontrolbasem_spdataadviseholder"></a><a name="m_spdataadviseholder"></a>CComControlBase::m_spDataAdviseHolder

데이터 개체 간의 자문 연결을 유지하고 싱크를 조언하는 표준 수단을 제공합니다.

```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

데이터 개체는 데이터를 전송할 수 있는 컨트롤이며 데이터의 형식 및 전송 매체를 지정하는 메서드를 구현하는 [IDataObject를](/windows/win32/api/objidl/nn-objidl-idataobject)구현합니다.

인터페이스는 `m_spDataAdviseHolder` [IDataObject::D조언](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) 및 [IDataObject::DUnadvise](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) 메서드를 구현 하 고 컨테이너에 대 한 자문 연결을 설정 하 고 삭제 합니다. 컨트롤의 컨테이너는 [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) 인터페이스를 지원 하여 조언 싱크를 구현 해야 합니다.

## <a name="ccomcontrolbasem_spinplacesite"></a><a name="m_spinplacesite"></a>CComControlBase::m_spInPlaceSite

컨테이너의 [IOleInPlaceSite,](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite) [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)또는 [IOleInPlaceSitein](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) 인터페이스 포인터에 대한 포인터입니다.

```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

`m_spInPlaceSite` 포인터는 [m_bNegotiatedWnd](#m_bnegotiatedwnd) 플래그가 TRUE인 경우에만 유효합니다.

다음 표에서는 포인터 `m_spInPlaceSite` 형식이 [m_bWndLess](#m_bwndless) 및 [m_bInPlaceSiteEx](#m_binplacesiteex) 데이터 멤버 플래그에 종속되는 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주며 있습니다.

|m_spInPlaceSite 유형|m_bWndLess 값|m_bInPlaceSiteEx 값|
|---------------------------|-----------------------|-----------------------------|
|`IOleInPlaceSiteWindowless`|TRUE|참 또는 거짓|
|`IOleInPlaceSiteEx`|FALSE|TRUE|
|`IOleInPlaceSite`|FALSE|FALSE|

## <a name="ccomcontrolbasem_spoleadviseholder"></a><a name="m_spoleadviseholder"></a>CComControlBase::m_spOleAdviseHolder

자문 연결을 유지하는 방법의 표준 구현을 제공합니다.

```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 클래스 내에서 이 데이터 멤버를 사용하려면 컨트롤 클래스의 데이터 멤버로 선언해야 합니다. 컨트롤 클래스는 기본 클래스의 공용 구조화 내에서 선언되므로 기본 클래스에서 이 데이터 멤버를 상속하지 않습니다.

인터페이스는 `m_spOleAdviseHolder` [IOleObject::조언](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) 및 [IOleObject::unadvise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) 메서드를 구현 하 고 컨테이너에 대 한 자문 연결을 설정 하 고 삭제 합니다. 컨트롤의 컨테이너는 [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) 인터페이스를 지원 하여 조언 싱크를 구현 해야 합니다.

## <a name="ccomcontrolbaseondraw"></a><a name="ondraw"></a>CComControlBase::온드로우

컨트롤을 그리려면 이 메서드를 재정의합니다.

```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>매개 변수

*디*<br/>
도면 측면, 컨트롤 경계 및 도면이 최적화되는지 여부와 같은 도면 정보가 포함된 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) 구조에 대한 참조입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

기본값은 `OnDraw` [CComControlBase::OnDrawAdvanced에](#ondrawadvanced)설정된 플래그에 따라 장치 컨텍스트를 삭제하거나 복원하거나 아무 것도 수행하지 않습니다.

ATL 컨트롤 마법사를 사용하여 컨트롤을 `OnDraw` 만들 때 메서드가 컨트롤 클래스에 자동으로 추가됩니다. 마법사의 기본값은 `OnDraw` "ATL 8.0"이라는 레이블이 있는 사각형을 그립니다.

### <a name="example"></a>예제

[CComControlBase::Get앰비언트 모양의](#getambientappearance)예제를 참조하십시오.

## <a name="ccomcontrolbaseondrawadvanced"></a><a name="ondrawadvanced"></a>CComControlBase::온드로우어드

기본값은 `OnDrawAdvanced` 드로잉을 위해 정규화된 장치 컨텍스트를 준비한 `OnDraw` 다음 컨트롤 클래스의 메서드를 호출합니다.

```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>매개 변수

*디*<br/>
도면 측면, 컨트롤 경계 및 도면이 최적화되는지 여부와 같은 도면 정보가 포함된 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) 구조에 대한 참조입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

컨테이너에서 전달된 장치 컨텍스트를 정규화하지 않고 수락하려면 이 메서드를 재정의합니다.

자세한 내용은 [CComControlBase::OnDraw를](#ondraw) 참조하십시오.

## <a name="ccomcontrolbaseonkillfocus"></a><a name="onkillfocus"></a>CComControlBase::온킬 포커스

컨트롤이 활성 상태이고 유효한 제어 사이트가 있는지 확인한 다음 컨트롤이 포커스를 잃었다는 것을 컨테이너에 알립니다.

```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>매개 변수

*nMsg*<br/>
예약되어 있습니다.

*wParam*<br/>
예약되어 있습니다.

*lParam*<br/>
예약되어 있습니다.

*bHandled*<br/>
창 메시지가 성공적으로 처리되었는지 여부를 나타내는 플래그입니다. 기본값은 FALSE입니다.

### <a name="return-value"></a>Return Value

항상 1을 반환합니다.

## <a name="ccomcontrolbaseonmouseactivate"></a><a name="onmouseactivate"></a>CComControlBase::온마우스 활성화

UI가 사용자 모드에 있는지 확인한 다음 컨트롤을 활성화합니다.

```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>매개 변수

*nMsg*<br/>
예약되어 있습니다.

*wParam*<br/>
예약되어 있습니다.

*lParam*<br/>
예약되어 있습니다.

*bHandled*<br/>
창 메시지가 성공적으로 처리되었는지 여부를 나타내는 플래그입니다. 기본값은 FALSE입니다.

### <a name="return-value"></a>Return Value

항상 1을 반환합니다.

## <a name="ccomcontrolbaseonpaint"></a><a name="onpaint"></a>CComControlBase::온페인트

페인팅을 위해 컨테이너를 준비하고 컨트롤의 클라이언트 영역을 가져옵니다. `OnDrawAdvanced`

```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```

### <a name="parameters"></a>매개 변수

*nMsg*<br/>
예약되어 있습니다.

*wParam*<br/>
기존 HDC.

*lParam*<br/>
예약되어 있습니다.

*l결과*<br/>
예약되어 있습니다.

### <a name="return-value"></a>Return Value

항상 0을 반환합니다.

### <a name="remarks"></a>설명

*wParam이* NULL이 `OnPaint` 아닌 경우 유효한 HDC가 포함되어 있다고 가정하고 [CComControlBase::m_hWndCD](#m_hwndcd)대신 사용합니다.

## <a name="ccomcontrolbaseonsetfocus"></a><a name="onsetfocus"></a>CComControlBase::온셋 포커스

컨트롤이 활성 상태이고 유효한 제어 사이트가 있는지 확인한 다음 컨트롤이 포커스를 얻은 컨테이너에 알립니다.

```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>매개 변수

*nMsg*<br/>
예약되어 있습니다.

*wParam*<br/>
예약되어 있습니다.

*lParam*<br/>
예약되어 있습니다.

*bHandled*<br/>
창 메시지가 성공적으로 처리되었는지 여부를 나타내는 플래그입니다. 기본값은 FALSE입니다.

### <a name="return-value"></a>Return Value

항상 1을 반환합니다.

### <a name="remarks"></a>설명

컨트롤이 포커스를 받았다는 알림을 컨테이너에 보냅니다.

## <a name="ccomcontrolbasepretranslateaccelerator"></a><a name="pretranslateaccelerator"></a>CComControlBase::PreTranslateAccelerator

이 메서드를 재정의하여 고유한 키보드 가속기 처리기를 제공합니다.

```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
예약되어 있습니다.

*hRet*<br/>
예약되어 있습니다.

### <a name="return-value"></a>Return Value

기본적으로 FALSE를 반환합니다.

## <a name="ccomcontrolbasesendonclose"></a><a name="sendonclose"></a>CComControlBase::센드온클로즈

조언 자에게 등록된 모든 권고 싱크는 제어가 닫혔다는 것을 알수 있습니다.

```
HRESULT SendOnClose();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

컨트롤이 권고 싱크를 닫았다는 알림을 보냅니다.

## <a name="ccomcontrolbasesendondatachange"></a><a name="sendondatachange"></a>CComControlBase::센드온데이터체인지

조언 자에게 등록된 모든 권고 싱크에 제어 데이터가 변경되었음을 알수 있습니다.

```
HRESULT SendOnDataChange(DWORD advf = 0);
```

### <a name="parameters"></a>매개 변수

*advf*<br/>
[IAdviseSink::OnDataChange에](/windows/win32/api/objidl/nf-objidl-iadvisesink-ondatachange) 대한 호출이 수행되는 방법을 지정하는 플래그를 조언합니다. 값은 [ADVF](/windows/win32/api/objidl/ne-objidl-advf) 열거형에서 발오있습니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="ccomcontrolbasesendonrename"></a><a name="sendonrename"></a>CComControlBase::센드온리네임

조언 홀더에 등록된 모든 권고 싱크에 컨트롤에 새 모니커가 있음을 알게 합니다.

```
HRESULT SendOnRename(IMoniker* pmk);
```

### <a name="parameters"></a>매개 변수

*pmk*<br/>
컨트롤의 새 모니커에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

컨트롤의 모니커가 변경되었음을 알림을 보냅니다.

## <a name="ccomcontrolbasesendonsave"></a><a name="sendonsave"></a>CComControlBase::센드온세이브

조언 홀더에 등록된 모든 권고 싱크에 컨트롤이 저장되었음을 알수 있습니다.

```
HRESULT SendOnSave();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

컨트롤이 방금 데이터를 저장했다는 알림을 보냅니다.

## <a name="ccomcontrolbasesendonviewchange"></a><a name="sendonviewchange"></a>CComControlBase::센드온뷰체인지

등록된 모든 권고 싱크에 컨트롤보기가 변경되었음을 알수 있습니다.

```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```

### <a name="parameters"></a>매개 변수

*dwAspect*<br/>
컨트롤의 측면 또는 보기입니다.

*lindex*<br/>
변경 된 보기의 일부입니다. -1만 유효합니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

`SendOnViewChange`[IAdvise싱크::OnViewChange를](/windows/win32/api/objidl/nf-objidl-iadvisesink-onviewchange)호출합니다. 현재 지원되는 *lindex의* 유일한 값은 -1이며, 이는 전체 뷰가 관심 있는 값임을 나타냅니다.

## <a name="ccomcontrolbasesetcontrolfocus"></a><a name="setcontrolfocus"></a>CComControlBase::세트 컨트롤 포커스

키보드 포커스를 컨트롤에서 설정하거나 제거합니다.

```
BOOL SetControlFocus(BOOL bGrab);
```

### <a name="parameters"></a>매개 변수

*bGrab*<br/>
TRUE인 경우 키보드 포커스를 호출 컨트롤로 설정합니다. FALSE인 경우 포커스가 있는 경우 호출 컨트롤에서 키보드 포커스를 제거합니다.

### <a name="return-value"></a>Return Value

컨트롤이 포커스를 성공적으로 수신하면 TRUE를 반환합니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

창이 있는 컨트롤의 경우 Windows API 함수 [SetFocus가](/windows/win32/api/winuser/nf-winuser-setfocus) 호출됩니다. 창 없는 컨트롤의 경우 [IOleInPlaceSitein::SetFocus가](/windows/win32/api/ocidl/nf-ocidl-ioleinplacesitewindowless-setfocus) 호출됩니다. 이 호출을 통해 창 없는 컨트롤은 키보드 포커스를 가져오고 창 메시지에 응답할 수 있습니다.

## <a name="ccomcontrolbasesetdirty"></a><a name="setdirty"></a>CComControlBase::SetDirty

데이터 멤버를 `m_bRequiresSave` *bDirty*의 값으로 설정합니다.

```cpp
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>매개 변수

*bDirty*<br/>
데이터 멤버 [CComControlBase의 값:m_bRequiresSave.](#m_brequiressave)

### <a name="remarks"></a>설명

`SetDirty(TRUE)`컨트롤이 마지막으로 저장된 이후 변경되었음을 플래그로 표시하도록 호출해야 합니다. 의 `m_bRequiresSave` 값은 [CComControlBase::GetDirty](#getdirty).

## <a name="see-also"></a>참조

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
