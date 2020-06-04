---
title: IPersistStreamInitImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl::GetClassID
- ATLCOM/ATL::IPersistStreamInitImpl::GetSizeMax
- ATLCOM/ATL::IPersistStreamInitImpl::InitNew
- ATLCOM/ATL::IPersistStreamInitImpl::IsDirty
- ATLCOM/ATL::IPersistStreamInitImpl::Load
- ATLCOM/ATL::IPersistStreamInitImpl::Save
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
ms.openlocfilehash: 0d6ac4639ac0cfb97416ca80b7a2ec3903d7b8e6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326455"
---
# <a name="ipersiststreaminitimpl-class"></a>IPersistStreamInitImpl 클래스

이 클래스는 `IUnknown` [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) 인터페이스의 기본 구현을 구현하고 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class ATL_NO_VTABLE IPersistStreamInitImpl
   : public IPersistStreamInit
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IPersistStreamInitImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IPersistStreamInitImpl::GetClassID](#getclassid)|개체의 CLSID를 검색합니다.|
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|개체의 데이터를 저장하는 데 필요한 스트림 크기를 검색합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IPersistStreamInitImpl::InitNew](#initnew)|새로 만든 개체를 초기화합니다.|
|[IPersistStreamInitImpl::더러워진](#isdirty)|개체의 데이터가 마지막으로 저장된 이후 변경되었는지 확인합니다.|
|[IPersistStreamInitImpl::로드](#load)|지정된 스트림에서 개체의 속성을 로드합니다.|
|[IPersistStreamInitImpl::저장](#save)|개체의 속성을 지정된 스트림에 저장합니다.|

## <a name="remarks"></a>설명

[IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) 인터페이스를 사용하면 클라이언트가 개체가 영구 데이터를 로드하고 단일 스트림에 저장하도록 요청할 수 있습니다. 클래스는 `IPersistStreamInitImpl` 디버그 빌드에서 덤프 `IUnknown` 장치에 정보를 전송하여 이 인터페이스및 구현의 기본 구현을 제공합니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPersistStreamInit`

`IPersistStreamInitImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ipersiststreaminitimplgetclassid"></a><a name="getclassid"></a>IPersistStreamInitImpl::GetClassID

개체의 CLSID를 검색합니다.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>설명

[IPersist::GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) 를 Windows SDK에서 참조하십시오.

## <a name="ipersiststreaminitimplgetsizemax"></a><a name="getsizemax"></a>IPersistStreamInitImpl::GetSizeMax

개체의 데이터를 저장하는 데 필요한 스트림 크기를 검색합니다.

```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IPersistStreamInit::GetSizeMax](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-getsizemax) 윈도우 SDK를 참조하십시오.

## <a name="ipersiststreaminitimplinitnew"></a><a name="initnew"></a>IPersistStreamInitImpl::InitNew

새로 만든 개체를 초기화합니다.

```
STDMETHOD(InitNew)();
```

### <a name="remarks"></a>설명

[IPersistStreamInit::InitNew](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-initnew) Windows SDK를 참조하십시오.

## <a name="ipersiststreaminitimplisdirty"></a><a name="isdirty"></a>IPersistStreamInitImpl::더러워진

개체의 데이터가 마지막으로 저장된 이후 변경되었는지 확인합니다.

```
STDMETHOD(IsDirty)();
```

### <a name="remarks"></a>설명

[IPersistStreamInit::Windows](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-isdirty) SDK에서 더러운 것을 참조하십시오.

## <a name="ipersiststreaminitimplload"></a><a name="load"></a>IPersistStreamInitImpl::로드

지정된 스트림에서 개체의 속성을 로드합니다.

```
STDMETHOD(Load)(LPSTREAM pStm);
```

### <a name="remarks"></a>설명

ATL은 개체의 속성 맵을 사용하여 이 정보를 검색합니다.

[IPersistStreamInit::Windows](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-load) SDK에서 로드를 참조하십시오.

## <a name="ipersiststreaminitimplsave"></a><a name="save"></a>IPersistStreamInitImpl::저장

개체의 속성을 지정된 스트림에 저장합니다.

```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```

### <a name="remarks"></a>설명

ATL은 개체의 속성 맵을 사용하여 이 정보를 저장합니다.

[IPersistStreamInit::Windows](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-save) SDK에 저장을 참조하십시오.

## <a name="see-also"></a>참고 항목

[스토리지 및 스트림](/windows/win32/Stg/storages-and-streams)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
