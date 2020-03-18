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
ms.openlocfilehash: 69842e77aecaa94be66432e5fbba437a6fa3c5a4
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423071"
---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl 클래스

이 클래스는 `IUnknown`를 구현 하 고 [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) 인터페이스의 기본 구현을 제공 합니다.

> [!IMPORTANT]
>  이 클래스와 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IPropertyPageImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
`IPropertyPageImpl`에서 파생 된 클래스입니다.

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IPropertyPageImpl:: Activate](#activate)|속성 페이지에 대 한 대화 상자 창을 만듭니다.|
|[IPropertyPageImpl:: Apply](#apply)|`SetObjects`를 통해 지정 된 기본 개체에 현재 속성 페이지 값을 적용 합니다. ATL 구현은 S_OK 반환 합니다.|
|[IPropertyPageImpl::D eactivate](#deactivate)|`Activate`를 사용 하 여 만든 창을 소멸 시킵니다.|
|[IPropertyPageImpl:: GetPageInfo](#getpageinfo)|속성 페이지에 대 한 정보를 검색 합니다.|
|[IPropertyPageImpl:: Help](#help)|속성 페이지에 대 한 Windows 도움말을 호출 합니다.|
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|속성 페이지가 활성화 된 후 변경 되었는지 여부를 나타냅니다.|
|[IPropertyPageImpl:: Move](#move)|속성 페이지 대화 상자를 배치 하 고 크기를 조정 합니다.|
|[IPropertyPageImpl:: SetDirty](#setdirty)|속성 페이지의 상태를 변경 또는 변경 되지 않은 상태로 플래그를 변경 합니다.|
|[IPropertyPageImpl:: SetObjects](#setobjects)|속성 페이지와 연결 된 개체에 대 한 `IUnknown` 포인터의 배열을 제공 합니다. 이러한 개체는 `Apply`호출을 통해 현재 속성 페이지 값을 받습니다.|
|[IPropertyPageImpl:: SetPageSite](#setpagesite)|속성 페이지에서 속성 프레임과 통신 하는 데 사용할 `IPropertyPageSite` 포인터를 사용 하 여 속성 페이지를 제공 합니다.|
|[IPropertyPageImpl:: Show](#show)|속성 페이지 대화 상자를 표시 하거나 숨길 수 있습니다.|
|[IPropertyPageImpl:: TranslateAccelerator](#translateaccelerator)|지정 된 키 입력을 처리 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[IPropertyPageImpl:: m_bDirty](#m_bdirty)|속성 페이지의 상태가 변경 되었는지 여부를 지정 합니다.|
|[IPropertyPageImpl:: m_dwDocString](#m_dwdocstring)|속성 페이지를 설명 하는 텍스트 문자열과 연결 된 리소스 식별자를 저장 합니다.|
|[IPropertyPageImpl:: m_dwHelpContext](#m_dwhelpcontext)|속성 페이지와 연결 된 도움말 항목에 대 한 컨텍스트 식별자를 저장 합니다.|
|[IPropertyPageImpl:: m_dwHelpFile](#m_dwhelpfile)|속성 페이지를 설명 하는 도움말 파일의 이름과 연결 된 리소스 식별자를 저장 합니다.|
|[IPropertyPageImpl:: m_dwTitle](#m_dwtitle)|속성 페이지의 탭에 표시 되는 텍스트 문자열과 연결 된 리소스 식별자를 저장 합니다.|
|[IPropertyPageImpl:: m_nObjects](#m_nobjects)|속성 페이지와 연결 된 개체 수를 저장 합니다.|
|[IPropertyPageImpl:: m_pPageSite](#m_ppagesite)|속성 페이지가 속성 프레임과 통신 하는 데 사용 하는 `IPropertyPageSite` 인터페이스를 가리킵니다.|
|[IPropertyPageImpl:: m_ppUnk](#m_ppunk)|속성 페이지와 연결 된 개체에 대 한 `IUnknown` 포인터의 배열을 가리킵니다.|
|[IPropertyPageImpl:: m_size](#m_size)|속성 페이지 대화 상자의 높이와 너비를 픽셀 단위로 저장 합니다.|

## <a name="remarks"></a>설명

[IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) 인터페이스를 사용 하면 개체는 속성 시트 내의 특정 속성 페이지를 관리할 수 있습니다. 클래스 `IPropertyPageImpl`는이 인터페이스의 기본 구현을 제공 하 고 디버그 빌드에서 덤프 장치로 정보를 전송 하 여 `IUnknown`을 구현 합니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [atl 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층

`IPropertyPage`

`IPropertyPageImpl`

## <a name="requirements"></a>요구 사항

**헤더:** 없음 ctl. h

##  <a name="activate"></a>IPropertyPageImpl:: Activate

속성 페이지에 대 한 대화 상자 창을 만듭니다.

```
HRESULT Activate(
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```

### <a name="remarks"></a>설명

기본적으로이 대화 상자는 *Bmodal* 매개 변수의 값에 관계 없이 항상 모덜리스입니다.

Windows SDK에서 [IPropertyPage:: Activate](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-activate) 를 참조 하세요.

##  <a name="apply"></a>IPropertyPageImpl:: Apply

`SetObjects`를 통해 지정 된 기본 개체에 현재 속성 페이지 값을 적용 합니다.

```
HRESULT Apply();
```

### <a name="return-value"></a>Return Value

S_OK를 반환 합니다.

### <a name="remarks"></a>설명

Windows SDK [IPropertyPage:: Apply](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-apply) 를 참조 하세요.

##  <a name="deactivate"></a>IPropertyPageImpl::D eactivate

[활성화](#activate)를 사용 하 여 만든 대화 상자 창을 소멸 시킵니다.

```
HRESULT Deactivate();
```

### <a name="remarks"></a>설명

[IPropertyPage::D eactivate](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-deactivate) in Windows SDK를 참조 하세요.

##  <a name="getpageinfo"></a>IPropertyPageImpl:: GetPageInfo

*Ppageinfo* 구조를 데이터 멤버에 포함 된 정보로 채웁니다.

```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>설명

`GetPageInfo` [m_dwDocString](#m_dwdocstring), [m_dwHelpFile](#m_dwhelpfile)및 [m_dwTitle](#m_dwtitle)연결 된 문자열 리소스를 로드 합니다.

Windows SDK [IPropertyPage:: GetPageInfo](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-getpageinfo) 를 참조 하세요.

##  <a name="help"></a>IPropertyPageImpl:: Help

속성 페이지에 대 한 Windows 도움말을 호출 합니다.

```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>설명

Windows SDK [IPropertyPage:: Help](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-help) 를 참조 하세요.

##  <a name="ipropertypageimpl"></a>IPropertyPageImpl::IPropertyPageImpl

생성자입니다.

```
IPropertyPageImpl();
```

### <a name="remarks"></a>설명

모든 데이터 멤버를 초기화 합니다.

##  <a name="ispagedirty"></a>IPropertyPageImpl::IsPageDirty

속성 페이지가 활성화 된 후 변경 되었는지 여부를 나타냅니다.

```
HRESULT IsPageDirty(void);
```

### <a name="remarks"></a>설명

페이지가 활성화 된 후 변경 된 경우 `IsPageDirty` S_OK를 반환 합니다.

##  <a name="m_bdirty"></a>IPropertyPageImpl:: m_bDirty

속성 페이지의 상태가 변경 되었는지 여부를 지정 합니다.

```
BOOL m_bDirty;
```

##  <a name="m_nobjects"></a>IPropertyPageImpl:: m_nObjects

속성 페이지와 연결 된 개체 수를 저장 합니다.

```
ULONG m_nObjects;
```

##  <a name="m_dwhelpcontext"></a>IPropertyPageImpl:: m_dwHelpContext

속성 페이지와 연결 된 도움말 항목에 대 한 컨텍스트 식별자를 저장 합니다.

```
DWORD m_dwHelpContext;
```

##  <a name="m_dwdocstring"></a>IPropertyPageImpl:: m_dwDocString

속성 페이지를 설명 하는 텍스트 문자열과 연결 된 리소스 식별자를 저장 합니다.

```
UINT m_dwDocString;
```

##  <a name="m_dwhelpfile"></a>IPropertyPageImpl:: m_dwHelpFile

속성 페이지를 설명 하는 도움말 파일의 이름과 연결 된 리소스 식별자를 저장 합니다.

```
UINT m_dwHelpFile;
```

##  <a name="m_dwtitle"></a>IPropertyPageImpl:: m_dwTitle

속성 페이지의 탭에 표시 되는 텍스트 문자열과 연결 된 리소스 식별자를 저장 합니다.

```
UINT m_dwTitle;
```

##  <a name="m_ppagesite"></a>IPropertyPageImpl:: m_pPageSite

속성 페이지가 속성 프레임과 통신 하는 데 사용 하는 [IPropertyPageSite](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) 인터페이스를 가리킵니다.

```
IPropertyPageSite* m_pPageSite;
```

##  <a name="m_ppunk"></a>IPropertyPageImpl:: m_ppUnk

속성 페이지와 연결 된 개체에 대 한 `IUnknown` 포인터의 배열을 가리킵니다.

```
IUnknown** m_ppUnk;
```

##  <a name="m_size"></a>IPropertyPageImpl:: m_size

속성 페이지 대화 상자의 높이와 너비를 픽셀 단위로 저장 합니다.

```
SIZE m_size;
```

##  <a name="move"></a>IPropertyPageImpl:: Move

속성 페이지 대화 상자를 배치 하 고 크기를 조정 합니다.

```
HRESULT Move(LPCRECT pRect);
```

### <a name="remarks"></a>설명

Windows SDK [IPropertyPage:: Move](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-move) 를 참조 하세요.

##  <a name="setdirty"></a>IPropertyPageImpl:: SetDirty

*Bdirty*않은 값에 따라 속성 페이지의 상태를 변경 되거나 변경 되지 않은 상태로 플래그를 설정 합니다.

```
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>매개 변수

*bDirty*<br/>
진행 TRUE 이면 속성 페이지의 상태가 변경 됨으로 표시 됩니다. 그렇지 않으면 변경 되지 않은 것으로 표시 됩니다.

### <a name="remarks"></a>설명

필요한 경우 `SetDirty`는 속성 페이지가 변경 되었음을 프레임에 알립니다.

##  <a name="setobjects"></a>IPropertyPageImpl:: SetObjects

속성 페이지와 연결 된 개체에 대 한 `IUnknown` 포인터의 배열을 제공 합니다.

```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```

### <a name="remarks"></a>설명

Windows SDK [IPropertyPage:: SetObjects](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setobjects) 를 참조 하세요.

##  <a name="setpagesite"></a>IPropertyPageImpl:: SetPageSite

속성 페이지에서 속성 프레임과 통신 하는 데 사용 되는 [IPropertyPageSite](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) 포인터를 사용 하 여 속성 페이지를 제공 합니다.

```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```

### <a name="remarks"></a>설명

Windows SDK [IPropertyPage:: SetPageSite](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setpagesite) 를 참조 하세요.

##  <a name="show"></a>IPropertyPageImpl:: Show

속성 페이지 대화 상자를 표시 하거나 숨길 수 있습니다.

```
HRESULT Show(UINT nCmdShow);
```

### <a name="remarks"></a>설명

Windows SDK에서 [IPropertyPage:: Show](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-show) 를 참조 하세요.

##  <a name="translateaccelerator"></a>IPropertyPageImpl:: TranslateAccelerator

`pMsg`에 지정 된 키 입력을 처리 합니다.

```
HRESULT TranslateAccelerator(MSG* pMsg);
```

### <a name="remarks"></a>설명

Windows SDK에서 [IPropertyPage:: TranslateAccelerator](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-translateaccelerator) 를 참조 하세요.

## <a name="see-also"></a>참고 항목

[IPropertyPage2Impl 클래스](../../atl/reference/ipropertypage2impl-class.md)<br/>
[IPerPropertyBrowsingImpl 클래스](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl 클래스](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
