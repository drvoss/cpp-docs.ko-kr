---
title: IPersistPropertyBagImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
ms.openlocfilehash: f656ecc76b175eae523059c60bb8a3efc6f0b312
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326491"
---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl 클래스

이 클래스는 `IUnknown` 개체가 클라이언트에서 제공하는 속성 가방에 해당 속성을 저장하도록 구현하고 허용합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IPersistPropertyBagImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|개체의 CLSID를 검색합니다.|
|[IPersistPropertyBagImpl::Initnew](#initnew)|새로 만든 개체를 초기화합니다. ATL 구현은 S_OK 반환합니다.|
|[IPersistPropertyBagImpl::로드](#load)|클라이언트에서 제공한 속성 백에서 개체의 속성을 로드합니다.|
|[IPersistPropertyBagImpl::저장](#save)|개체의 속성을 클라이언트에서 제공하는 속성 가방에 저장합니다.|

## <a name="remarks"></a>설명

[IPersistPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768205\(v=vs.85\)) 인터페이스를 사용하면 개체가 클라이언트에서 제공하는 속성 가방에 해당 속성을 저장할 수 있습니다. 클래스는 `IPersistPropertyBagImpl` 디버그 빌드에서 덤프 `IUnknown` 장치에 정보를 전송하여 이 인터페이스및 구현의 기본 구현을 제공합니다.

`IPersistPropertyBag`[IPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768196\(v=vs.85\)) 및 [IErrorLog와](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768231\(v=vs.85\))함께 작동합니다. 이러한 후자의 두 인터페이스는 클라이언트에서 구현해야 합니다. 를 `IPropertyBag`통해 클라이언트는 개체의 개별 속성을 저장하고 로드합니다. Through `IErrorLog`개체와 클라이언트 는 모두 발생한 오류를 보고할 수 있습니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ipersistpropertybagimplgetclassid"></a><a name="getclassid"></a>IPersistPropertyBagImpl::GetClassID

개체의 CLSID를 검색합니다.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>설명

[IPersist::GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) 를 Windows SDK에서 참조하십시오.

## <a name="ipersistpropertybagimplinitnew"></a><a name="initnew"></a>IPersistPropertyBagImpl::Initnew

새로 만든 개체를 초기화합니다.

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

[IPersistPropertyBag::InitNew](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768204\(v=vs.85\)) Windows SDK를 참조하십시오.

## <a name="ipersistpropertybagimplload"></a><a name="load"></a>IPersistPropertyBagImpl::로드

클라이언트에서 제공한 속성 백에서 개체의 속성을 로드합니다.

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>설명

ATL은 개체의 속성 맵을 사용하여 이 정보를 검색합니다.

[IPersistPropertyBag::Windows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768206\(v=vs.85\)) SDK에서 로드를 참조하십시오.

## <a name="ipersistpropertybagimplsave"></a><a name="save"></a>IPersistPropertyBagImpl::저장

개체의 속성을 클라이언트에서 제공하는 속성 가방에 저장합니다.

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>설명

ATL은 개체의 속성 맵을 사용하여 이 정보를 저장합니다. 기본적으로 이 메서드는 *fSaveAllProperties*의 값에 관계없이 모든 속성을 저장합니다.

[IPersistPropertyBag::Windows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768207\(v=vs.85\)) SDK에 저장을 참조하십시오.

## <a name="see-also"></a>참고 항목

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
