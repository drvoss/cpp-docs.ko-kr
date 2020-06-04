---
title: 아이퍼프로퍼티브라우징임플 클래스
ms.date: 11/04/2016
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
ms.openlocfilehash: f8fb80cc38e775b9b26afa033647faac694e968a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326509"
---
# <a name="iperpropertybrowsingimpl-class"></a>아이퍼프로퍼티브라우징임플 클래스

이 클래스는 `IUnknown` 클라이언트가 개체의 속성 페이지에서 정보에 액세스할 수 있도록 구현하고 허용합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IPerPropertyBrowsingImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[아이퍼프로퍼브라우징임플::겟디스플레이스트링](#getdisplaystring)|지정된 속성을 설명하는 문자열을 검색합니다.|
|[IPerProperty브라우징 임플::GetPredefined스트링](#getpredefinedstrings)|지정된 속성이 허용할 수 있는 값에 해당하는 문자열 배열을 검색합니다.|
|[IPerProperty브라우징 임플::GetPredefined값](#getpredefinedvalue)|지정된 DISPID로 식별된 속성값을 포함하는 VARIANT을 검색합니다. DISPID는 에서 `GetPredefinedStrings`검색된 문자열 이름과 연결됩니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[아이퍼프로퍼브라우징임플::맵프로퍼토페이지](#mappropertytopage)|지정된 속성과 연결된 속성 페이지의 CLSID를 검색합니다.|

## <a name="remarks"></a>설명

[IPerPropertyBrowsing](/windows/win32/api/ocidl/nn-ocidl-iperpropertybrowsing) 인터페이스를 사용하면 클라이언트가 개체의 속성 페이지에서 정보에 액세스할 수 있습니다. 클래스는 `IPerPropertyBrowsingImpl` 디버그 빌드에서 덤프 `IUnknown` 장치에 정보를 전송하여 이 인터페이스및 구현의 기본 구현을 제공합니다.

> [!NOTE]
> Microsoft Access를 컨테이너 응용 프로그램으로 사용하는 경우 에서 `IPerPropertyBrowsingImpl`클래스를 파생해야 합니다. 그렇지 않으면 Access가 컨트롤을 로드하지 않습니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="iperpropertybrowsingimplgetdisplaystring"></a><a name="getdisplaystring"></a>아이퍼프로퍼브라우징임플::겟디스플레이스트링

지정된 속성을 설명하는 문자열을 검색합니다.

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>설명

[IPerPropertyBrowsing::GetDisplayString](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) 윈도우 SDK를 참조하십시오.

## <a name="iperpropertybrowsingimplgetpredefinedstrings"></a><a name="getpredefinedstrings"></a>IPerProperty브라우징 임플::GetPredefined스트링

각 배열을 0개의 항목으로 채웁니다.

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>Return Value

ATL의 [GetPredefinedValue](#getpredefinedvalue) 구현은 E_NOTIMPL 반환합니다.

### <a name="remarks"></a>설명

[IPerPropertyBrowsing::GetPredefinedStrings](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) 윈도우 SDK에서.

## <a name="iperpropertybrowsingimplgetpredefinedvalue"></a><a name="getpredefinedvalue"></a>IPerProperty브라우징 임플::GetPredefined값

지정된 DISPID로 식별된 속성값을 포함하는 VARIANT을 검색합니다. DISPID는 에서 `GetPredefinedStrings`검색된 문자열 이름과 연결됩니다.

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

ATL의 [GetPredefinedStrings](#getpredefinedstrings) 구현은 해당 문자열을 검색하지 않습니다.

[IPerPropertyBrowsing::GetPredefinedWindows](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) SDK에서 값을 참조하십시오.

## <a name="iperpropertybrowsingimplmappropertytopage"></a><a name="mappropertytopage"></a>아이퍼프로퍼브라우징임플::맵프로퍼토페이지

지정된 속성과 연결된 속성 페이지의 CLSID를 검색합니다.

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>설명

ATL은 개체의 속성 맵을 사용하여 이 정보를 가져옵니다.

[IPerPropertyBrowsing::MapPropertyToPage](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) 를 참조하십시오.

## <a name="see-also"></a>참고 항목

[IPropertyPageImpl 클래스](../../atl/reference/ipropertypageimpl-class.md)<br/>
[I지정속성페이지임플 클래스](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
