---
title: IProvideClassInfo2Impl 클래스
ms.date: 11/04/2016
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
ms.openlocfilehash: 0d1ee9acc1cfabc71ecf33fcb5919d826899c671
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329565"
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl 클래스

이 클래스는 [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) 및 [IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) 메서드의 기본 구현을 제공합니다.

## <a name="syntax"></a>구문

```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```

#### <a name="parameters"></a>매개 변수

*pcoclsid*<br/>
공동 클래스의 식별자에 대한 포인터입니다.

*psrcid*<br/>
공동 클래스의 기본 나가는 인터페이스에 대한 식별자포인터입니다.

*plibid*<br/>
인터페이스에 대한 정보가 포함된 형식 라이브러리의 LIBID에 대한 포인터입니다. 기본적으로 서버 수준 형식 라이브러리가 전달됩니다.

*wMajor*<br/>
형식 라이브러리의 주 버전입니다. 기본값은 1입니다.

*wMinor*<br/>
형식 라이브러리의 부 버전입니다. 기본값은 0입니다.

*tihclass*<br/>
공동 클래스의 형식 정보를 관리하는 데 사용되는 클래스입니다. 기본값은 `CComTypeInfoHolder`입니다.

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|속성|Description|
|----------|-----------------|
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|공동 클래스의 `ITypeInfo` 형식 정보에 대한 포인터를 검색합니다.|
|[IProvideClassInfo2Impl::GetGUID](#getguid)|개체의 나가는 인터페이스에 대한 GUID를 검색합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[IProvideClassInfo2Impl::_tih](#_tih)|공동 클래스의 형식 정보를 관리합니다.|

## <a name="remarks"></a>설명

마샬러가 [iprovideclassinfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) 인터페이스는 `GetGUID` 메서드를 추가하여 [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo)를 확장합니다. 이 메서드를 사용 하면 클라이언트기본 이벤트 집합에 대 한 개체의 나가는 인터페이스 IID를 검색할 수 있습니다. 클래스는 `IProvideClassInfo2Impl` 및 `IProvideClassInfo` `IProvideClassInfo2` 메서드의 기본 구현을 제공합니다.

`IProvideClassInfo2Impl`에는 coclass에 `CComTypeInfoHolder` 대한 형식 정보를 관리하는 형식의 정적 멤버가 포함되어 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="iprovideclassinfo2implgetclassinfo"></a><a name="getclassinfo"></a>IProvideClassInfo2Impl::GetClassInfo

공동 클래스의 `ITypeInfo` 형식 정보에 대한 포인터를 검색합니다.

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>설명

[IProvideClassInfo::GetClassInfo](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo) 윈도우 SDK에서 참조.

## <a name="iprovideclassinfo2implgetguid"></a><a name="getguid"></a>IProvideClassInfo2Impl::GetGUID

개체의 나가는 인터페이스에 대한 GUID를 검색합니다.

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>설명

[IProvideClassInfo2::GetGUID](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid) 윈도우 SDK를 참조하십시오.

## <a name="iprovideclassinfo2impliprovideclassinfo2impl"></a><a name="iprovideclassinfo2impl"></a>IProvideClassInfo2Impl:::IProvideClassInfo2Impl

생성자입니다.

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>설명

`AddRef` [_tih](#_tih) 멤버를 호출합니다. 이 소멸자는 `Release`을 호출합니다.

## <a name="iprovideclassinfo2impl_tih"></a><a name="_tih"></a>IProvideClassInfo2Impl::_tih

이 정적 데이터 멤버는 기본적으로 는 클래스 템플릿 매개 변수 `CComTypeInfoHolder`인 *tihclass의*인스턴스입니다.

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>설명

`_tih`는 공동 클래스의 형식 정보를 관리합니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
