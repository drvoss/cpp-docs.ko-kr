---
title: IPropertyPageImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::Activate
- ATLCTL/ATL::IPropertyPageImpl::Apply
- ATLCTL/ATL::IPropertyPageImpl::Deactivate
- ATLCTL/ATL::IPropertyPageImpl::GetPageInfo
- ATLCTL/ATL::IPropertyPageImpl::Help
- ATLCTL/ATL::IPropertyPageImpl::IsPageDirty
- ATLCTL/ATL::IPropertyPageImpl::Move
- ATLCTL/ATL::IPropertyPageImpl::SetDirty
- ATLCTL/ATL::IPropertyPageImpl::SetObjects
- ATLCTL/ATL::IPropertyPageImpl::SetPageSite
- ATLCTL/ATL::IPropertyPageImpl::Show
- ATLCTL/ATL::IPropertyPageImpl::TranslateAccelerator
- ATLCTL/ATL::IPropertyPageImpl::m_bDirty
- ATLCTL/ATL::IPropertyPageImpl::m_dwDocString
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpContext
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpFile
- ATLCTL/ATL::IPropertyPageImpl::m_dwTitle
- ATLCTL/ATL::IPropertyPageImpl::m_nObjects
- ATLCTL/ATL::IPropertyPageImpl::m_pPageSite
- ATLCTL/ATL::IPropertyPageImpl::m_ppUnk
- ATLCTL/ATL::IPropertyPageImpl::m_size
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
ms.openlocfilehash: 154bfb5beb258ff26649f44f0bd4c23fb8708977
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745869"
---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl 클래스

이 클래스는 `IUnknown` [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) 인터페이스의 기본 구현을 구현하고 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IPropertyPageImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IPropertyPageImpl`

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[아이프로퍼페이지임플:::아이프로퍼페이지임플](#ipropertypageimpl)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IPropertyPageImpl::활성화](#activate)|속성 페이지에 대한 대화 상자 창을 만듭니다.|
|[IPropertyPageImpl::적용](#apply)|을 통해 `SetObjects`지정된 기본 개체에 현재 속성 페이지 값을 적용합니다. ATL 구현은 S_OK 반환합니다.|
|[IPropertyPageImpl::D](#deactivate)|을 통해 `Activate`만든 창을 삭제합니다.|
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|속성 페이지에 대한 정보를 검색합니다.|
|[IPropertyPageImpl::도움말](#help)|속성 페이지에 대 한 Windows 도움말을 호출 합니다.|
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|속성 페이지가 활성화된 이후 변경되었는지 여부를 나타냅니다.|
|[IPropertyPageImpl::이동](#move)|위치 및 속성 페이지 대화 상자 크기를 조정합니다.|
|[IPropertyPageImpl::SetDirty](#setdirty)|속성 페이지의 상태를 변경또는 변경되지 않은 상태로 플래그를 표시합니다.|
|[IPropertyPageImpl::설정 개체](#setobjects)|속성 페이지와 `IUnknown` 연결된 개체에 대한 포인터 배열을 제공합니다. 이러한 개체는 `Apply`에 대한 호출을 통해 현재 속성 페이지 값을 받습니다.|
|[IPropertyPageImpl::설정 페이지사이트](#setpagesite)|속성 페이지가 속성 `IPropertyPageSite` 프레임과 통신하는 포인터를 속성 페이지에 제공합니다.|
|[IPropertyPageImpl::표시](#show)|속성 페이지 대화 상자가 표시또는 표시되지 않게 합니다.|
|[IPropertyPageImpl:::번역가속기](#translateaccelerator)|지정된 키 입력을 처리합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|속성 페이지의 상태가 변경되었는지 여부를 지정합니다.|
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|속성 페이지를 설명하는 텍스트 문자열과 연결된 리소스 식별자를 저장합니다.|
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|속성 페이지와 연결된 도움말 항목에 대한 컨텍스트 식별자를 저장합니다.|
|[아이프로퍼페이지임플::m_dwHelpFile](#m_dwhelpfile)|속성 페이지를 설명하는 도움말 파일의 이름과 연결된 리소스 식별자를 저장합니다.|
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|속성 페이지의 탭에 나타나는 텍스트 문자열과 연결된 리소스 식별자를 저장합니다.|
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|속성 페이지와 연결된 개체 수를 저장합니다.|
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|속성 페이지가 `IPropertyPageSite` 속성 프레임과 통신하는 인터페이스를 가리킵니다.|
|[아이프로퍼페이지임플::m_ppUnk](#m_ppunk)|속성 페이지와 `IUnknown` 연결된 개체를 가리키는 포인터 배열을 가리킵니다.|
|[IPropertyPageImpl::m_size](#m_size)|속성 페이지의 대화 상자의 높이와 너비를 픽셀 단위로 저장합니다.|

## <a name="remarks"></a>설명

[IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) 인터페이스를 사용하면 개체가 속성 시트 내의 특정 속성 페이지를 관리할 수 있습니다. 클래스는 `IPropertyPageImpl` 디버그 빌드에서 덤프 `IUnknown` 장치에 정보를 전송하여 이 인터페이스및 구현의 기본 구현을 제공합니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPropertyPage`

`IPropertyPageImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="ipropertypageimplactivate"></a><a name="activate"></a>IPropertyPageImpl::활성화

속성 페이지에 대한 대화 상자 창을 만듭니다.

```
HRESULT Activate(
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```

### <a name="remarks"></a>설명

기본적으로 대화 상자는 *bModal* 매개 변수의 값에 관계없이 항상 모데리스입니다.

[IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-activate) SDK에서 활성화를 참조하십시오.

## <a name="ipropertypageimplapply"></a><a name="apply"></a>IPropertyPageImpl::적용

을 통해 `SetObjects`지정된 기본 개체에 현재 속성 페이지 값을 적용합니다.

```
HRESULT Apply();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

[IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-apply) SDK에 적용을 참조하십시오.

## <a name="ipropertypageimpldeactivate"></a><a name="deactivate"></a>IPropertyPageImpl::D

[활성화](#activate)를 통해 만든 대화 상자 창을 삭제합니다.

```
HRESULT Deactivate();
```

### <a name="remarks"></a>설명

[IPropertyPage::D](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-deactivate) Windows SDK에서 활성화를 참조하십시오.

## <a name="ipropertypageimplgetpageinfo"></a><a name="getpageinfo"></a>IPropertyPageImpl::GetPageInfo

데이터 멤버에 포함된 정보로 *pPageInfo* 구조를 채웁니다.

```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>설명

`GetPageInfo`[m_dwDocString,](#m_dwdocstring) [m_dwHelpFile](#m_dwhelpfile)및 [m_dwTitle](#m_dwtitle)와 관련된 문자열 리소스를 로드합니다.

[IPropertyPage::GetPageInfo](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-getpageinfo) 윈도우 SDK를 참조하십시오.

## <a name="ipropertypageimplhelp"></a><a name="help"></a>IPropertyPageImpl::도움말

속성 페이지에 대 한 Windows 도움말을 호출 합니다.

```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>설명

[IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-help) SDK에서 도움말을 참조하십시오.

## <a name="ipropertypageimplipropertypageimpl"></a><a name="ipropertypageimpl"></a>아이프로퍼페이지임플:::아이프로퍼페이지임플

생성자입니다.

```
IPropertyPageImpl();
```

### <a name="remarks"></a>설명

모든 데이터 멤버를 초기화합니다.

## <a name="ipropertypageimplispagedirty"></a><a name="ispagedirty"></a>IPropertyPageImpl::IsPageDirty

속성 페이지가 활성화된 이후 변경되었는지 여부를 나타냅니다.

```
HRESULT IsPageDirty(void);
```

### <a name="remarks"></a>설명

`IsPageDirty`페이지가 활성화된 이후 변경된 경우 S_OK 반환합니다.

## <a name="ipropertypageimplm_bdirty"></a><a name="m_bdirty"></a>IPropertyPageImpl::m_bDirty

속성 페이지의 상태가 변경되었는지 여부를 지정합니다.

```
BOOL m_bDirty;
```

## <a name="ipropertypageimplm_nobjects"></a><a name="m_nobjects"></a>IPropertyPageImpl::m_nObjects

속성 페이지와 연결된 개체 수를 저장합니다.

```
ULONG m_nObjects;
```

## <a name="ipropertypageimplm_dwhelpcontext"></a><a name="m_dwhelpcontext"></a>IPropertyPageImpl::m_dwHelpContext

속성 페이지와 연결된 도움말 항목에 대한 컨텍스트 식별자를 저장합니다.

```
DWORD m_dwHelpContext;
```

## <a name="ipropertypageimplm_dwdocstring"></a><a name="m_dwdocstring"></a>IPropertyPageImpl::m_dwDocString

속성 페이지를 설명하는 텍스트 문자열과 연결된 리소스 식별자를 저장합니다.

```
UINT m_dwDocString;
```

## <a name="ipropertypageimplm_dwhelpfile"></a><a name="m_dwhelpfile"></a>아이프로퍼페이지임플::m_dwHelpFile

속성 페이지를 설명하는 도움말 파일의 이름과 연결된 리소스 식별자를 저장합니다.

```
UINT m_dwHelpFile;
```

## <a name="ipropertypageimplm_dwtitle"></a><a name="m_dwtitle"></a>IPropertyPageImpl::m_dwTitle

속성 페이지의 탭에 나타나는 텍스트 문자열과 연결된 리소스 식별자를 저장합니다.

```
UINT m_dwTitle;
```

## <a name="ipropertypageimplm_ppagesite"></a><a name="m_ppagesite"></a>IPropertyPageImpl::m_pPageSite

속성 페이지가 속성 프레임과 통신하는 [IPropertyPageSite](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) 인터페이스를 가리킵니다.

```
IPropertyPageSite* m_pPageSite;
```

## <a name="ipropertypageimplm_ppunk"></a><a name="m_ppunk"></a>아이프로퍼페이지임플::m_ppUnk

속성 페이지와 `IUnknown` 연결된 개체를 가리키는 포인터 배열을 가리킵니다.

```
IUnknown** m_ppUnk;
```

## <a name="ipropertypageimplm_size"></a><a name="m_size"></a>IPropertyPageImpl::m_size

속성 페이지의 대화 상자의 높이와 너비를 픽셀 단위로 저장합니다.

```
SIZE m_size;
```

## <a name="ipropertypageimplmove"></a><a name="move"></a>IPropertyPageImpl::이동

위치 및 속성 페이지 대화 상자 크기를 조정합니다.

```
HRESULT Move(LPCRECT pRect);
```

### <a name="remarks"></a>설명

[IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-move) SDK에서 이동을 참조하십시오.

## <a name="ipropertypageimplsetdirty"></a><a name="setdirty"></a>IPropertyPageImpl::SetDirty

*bDirty*의 값에 따라 속성 페이지의 상태를 변경또는 변경되지 않은 상태로 플래그를 표시합니다.

```cpp
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>매개 변수

*bDirty*<br/>
【인】 TRUE이면 속성 페이지의 상태가 변경된 것으로 표시됩니다. 그렇지 않으면 변경되지 않은 것으로 표시됩니다.

### <a name="remarks"></a>설명

필요한 `SetDirty` 경우 속성 페이지가 변경되었음을 프레임에 알립니다.

## <a name="ipropertypageimplsetobjects"></a><a name="setobjects"></a>IPropertyPageImpl::설정 개체

속성 페이지와 `IUnknown` 연결된 개체에 대한 포인터 배열을 제공합니다.

```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```

### <a name="remarks"></a>설명

[IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setobjects) SDK의 설정 개체를 참조하십시오.

## <a name="ipropertypageimplsetpagesite"></a><a name="setpagesite"></a>IPropertyPageImpl::설정 페이지사이트

속성 페이지와 속성 프레임과 통신 하는 [IPropertyPageSite](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) 포인터를 속성 페이지를 제공합니다.

```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```

### <a name="remarks"></a>설명

[IPropertyPage::SetPageWindows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setpagesite) SDK에서 사이트 참조.

## <a name="ipropertypageimplshow"></a><a name="show"></a>IPropertyPageImpl::표시

속성 페이지 대화 상자가 표시또는 표시되지 않게 합니다.

```
HRESULT Show(UINT nCmdShow);
```

### <a name="remarks"></a>설명

[IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-show) SDK에서 표시를 참조하십시오.

## <a name="ipropertypageimpltranslateaccelerator"></a><a name="translateaccelerator"></a>IPropertyPageImpl:::번역가속기

에 지정된 키 `pMsg`입력을 처리합니다.

```
HRESULT TranslateAccelerator(MSG* pMsg);
```

### <a name="remarks"></a>설명

[IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-translateaccelerator) SDK에서 번역가속기를 참조하십시오.

## <a name="see-also"></a>참조

[IPropertyPage2Impl 클래스](../../atl/reference/ipropertypage2impl-class.md)<br/>
[아이퍼프로퍼티브라우징임플 클래스](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[I지정속성페이지임플 클래스](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
