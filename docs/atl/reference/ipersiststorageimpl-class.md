---
title: IPersistStorageImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl::GetClassID
- ATLCOM/ATL::IPersistStorageImpl::HandsOffStorage
- ATLCOM/ATL::IPersistStorageImpl::InitNew
- ATLCOM/ATL::IPersistStorageImpl::IsDirty
- ATLCOM/ATL::IPersistStorageImpl::Load
- ATLCOM/ATL::IPersistStorageImpl::Save
- ATLCOM/ATL::IPersistStorageImpl::SaveCompleted
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
ms.openlocfilehash: b235b190f237293932705e4d290ac963088722f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326477"
---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl 클래스

이 클래스는 [IPersistStorage](/windows/win32/api/objidl/nn-objidl-ipersiststorage) 인터페이스를 구현합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IPersistStorageImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IPersistStorage임플::GetClassID](#getclassid)|개체의 CLSID를 검색합니다.|
|[IPersistStorage임플::핸즈오프스토리지](#handsoffstorage)|개체에 모든 저장소 개체를 해제하고 HandsOff 모드로 들어가도록 지시합니다. ATL 구현은 S_OK 반환합니다.|
|[IPersistStorage임플::이니트뉴](#initnew)|새 저장소를 초기화합니다.|
|[IPersistStorage임플::더러워](#isdirty)|개체의 데이터가 마지막으로 저장된 이후 변경되었는지 확인합니다.|
|[IPersistStorage임플::로드](#load)|지정된 저장소에서 개체의 속성을 로드합니다.|
|[IPersistStorageImpl::저장](#save)|개체의 속성을 지정된 저장소에 저장합니다.|
|[IPersistStorageImpl::저장 완료](#savecompleted)|저장소 개체에 쓸 수 있는 개체를 일반 모드로 되돌릴 수 있음을 지정합니다. ATL 구현은 S_OK 반환합니다.|

## <a name="remarks"></a>설명

`IPersistStorageImpl`을 사용하면 클라이언트가 개체로드를 요청하고 저장소를 사용하여 영구 데이터를 저장할 수 있는 [IPersistStorage](/windows/win32/api/objidl/nn-objidl-ipersiststorage) 인터페이스를 구현합니다.

이 클래스를 구현하려면 `T` 클래스를 통해 `QueryInterface` `IPersistStreamInit` 인터페이스의 구현을 사용할 수 있도록 해야 합니다. 일반적으로 클래스는 `T` [IPersistStreamInitImpl에서](../../atl/reference/ipersiststreaminitimpl-class.md)파생되고 COM `IPersistStreamInit` [맵에](com-map-macros.md)대한 항목을 제공하고 [속성 맵을](property-map-macros.md) 사용하여 클래스의 영구 데이터를 설명해야 합니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPersistStorage`

`IPersistStorageImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ipersiststorageimplgetclassid"></a><a name="getclassid"></a>IPersistStorage임플::GetClassID

개체의 CLSID를 검색합니다.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>설명

[IPersist::GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) 를 Windows SDK에서 참조하십시오.

## <a name="ipersiststorageimplhandsoffstorage"></a><a name="handsoffstorage"></a>IPersistStorage임플::핸즈오프스토리지

개체에 모든 저장소 개체를 해제하고 HandsOff 모드로 들어가도록 지시합니다.

```
STDMETHOD(HandsOffStorage)(void);
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

[IPersistStorage::HandsOffWindows](/windows/win32/api/objidl/nf-objidl-ipersiststorage-handsoffstorage) SDK의 저장을 참조하십시오.

## <a name="ipersiststorageimplinitnew"></a><a name="initnew"></a>IPersistStorage임플::이니트뉴

새 저장소를 초기화합니다.

```
STDMETHOD(InitNew)(IStorage*);
```

### <a name="remarks"></a>설명

ATL 구현은 [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) 인터페이스에 위임합니다.

[IPersistStorage:InitNew](/windows/win32/api/objidl/nf-objidl-ipersiststorage-initnew) Windows SDK를 참조하십시오.

## <a name="ipersiststorageimplisdirty"></a><a name="isdirty"></a>IPersistStorage임플::더러워

개체의 데이터가 마지막으로 저장된 이후 변경되었는지 확인합니다.

```
STDMETHOD(IsDirty)(void);
```

### <a name="remarks"></a>설명

ATL 구현은 [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) 인터페이스에 위임합니다.

[IPersistStorage:Windows](/windows/win32/api/objidl/nf-objidl-ipersiststorage-isdirty) SDK에서 더러운 것을 참조하십시오.

## <a name="ipersiststorageimplload"></a><a name="load"></a>IPersistStorage임플::로드

지정된 저장소에서 개체의 속성을 로드합니다.

```
STDMETHOD(Load)(IStorage* pStorage);
```

### <a name="remarks"></a>설명

ATL 구현은 [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) 인터페이스에 위임합니다. `Load`에서는 "콘텐츠"라는 스트림을 사용하여 개체의 데이터를 검색합니다. [저장](#save) 메서드는 원래 이 스트림을 만듭니다.

[IPersistStorage:Windows](/windows/win32/api/objidl/nf-objidl-ipersiststorage-load) SDK에서 로드를 참조하십시오.

## <a name="ipersiststorageimplsave"></a><a name="save"></a>IPersistStorageImpl::저장

개체의 속성을 지정된 저장소에 저장합니다.

```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```

### <a name="remarks"></a>설명

ATL 구현은 [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) 인터페이스에 위임합니다. 처음 `Save` 호출될 때 지정된 저장소에 "콘텐츠"라는 스트림을 만듭니다. 이 스트림은 나중에 로드 `Save` 를 호출하고 [로드할](#load)때 사용됩니다.

[IPersistStorage:Windows](/windows/win32/api/objidl/nf-objidl-ipersiststorage-save) SDK에 저장을 참조하십시오.

## <a name="ipersiststorageimplsavecompleted"></a><a name="savecompleted"></a>IPersistStorageImpl::저장 완료

저장소 개체에 쓸 수 있는 개체를 일반 모드로 되돌릴 수 있음을 지정합니다.

```
STDMETHOD(SaveCompleted)(IStorage*);
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

[IPersistStorage:저장 Windows](/windows/win32/api/objidl/nf-objidl-ipersiststorage-savecompleted) SDK에서 완료 됨을 참조하십시오.

## <a name="see-also"></a>참고 항목

[스토리지 및 스트림](/windows/win32/Stg/storages-and-streams)<br/>
[IPersistStreamInitImpl 클래스](../../atl/reference/ipersiststreaminitimpl-class.md)<br/>
[IPersistPropertyBagImpl 클래스](../../atl/reference/ipersistpropertybagimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
