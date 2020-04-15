---
title: IDispatchImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
ms.openlocfilehash: 3b3899a0c4a49aa7fb1bd82af330f5f1cc7329c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329802"
---
# <a name="idispatchimpl-class"></a>IDispatchImpl 클래스

이중 인터페이스의 일부에 `IDispatch` 대한 기본 구현을 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T,
        const IID* piid= &__uuidof(T),
        const GUID* plibid = &CAtlModule::m_libid,
        WORD wMajor = 1,
        WORD wMinor = 0,
        class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IDispatchImpl : public T
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
【인】 듀얼 인터페이스.

*piid*<br/>
【인】 *T.*

*plibid*<br/>
【인】 인터페이스에 대한 정보가 포함된 형식 라이브러리의 LIBID에 대한 포인터입니다. 기본적으로 서버 수준 형식 라이브러리가 전달됩니다.

*wMajor*<br/>
【인】 형식 라이브러리의 주 버전입니다. 기본적으로 값은 1입니다.

*wMinor*<br/>
【인】 형식 라이브러리의 부 버전입니다. 기본적으로 값은 0입니다.

*tihclass*<br/>
【인】 *T에*대 한 형식 정보를 관리 하는 데 사용 하는 클래스입니다. 기본적으로 값은 은입니다. `CComTypeInfoHolder`

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[I디스패치임플::I디스패치임플](#idispatchimpl)|생성자입니다. 이중 `AddRef` 인터페이스에 대한 형식 정보를 관리하는 보호된 멤버 변수를 호출합니다. 이 소멸자는 `Release`을 호출합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|이름 집합을 해당하는 디스패치 식별자 집합에 매핑합니다.|
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|이중 인터페이스에 대한 형식 정보를 검색합니다.|
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|이중 인터페이스에 사용할 수 있는 형식 정보가 있는지 여부를 결정합니다.|
|[IDispatchImpl::호출](#invoke)|이중 인터페이스에서 노출되는 메서드 및 속성에 대한 액세스를 제공합니다.|

## <a name="remarks"></a>설명

`IDispatchImpl`은 개체의 모든 `IDispatch` 이중 인터페이스 부분에 대한 기본 구현을 제공합니다. 이중 인터페이스는 자동화 `IDispatch` 호환 형식에서 파생되고 사용됩니다. dispinterface와 마찬가지로 이중 인터페이스는 초기 바인딩 및 후기 바인딩을 지원합니다. 그러나 이중 인터페이스는 vtable 바인딩도 지원합니다.

다음 예제에서는 일반적인 구현은 `IDispatchImpl`합니다.

[!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]

기본적으로 클래스는 `IDispatchImpl` 레지스트리에서 *T에* 대한 형식 정보를 찾습니다. 등록되지 않은 인터페이스를 구현하려면 `IDispatchImpl` 미리 정의된 버전 번호를 사용하여 레지스트리에 액세스하지 않고 클래스를 사용할 수 있습니다. *wMajor* 및 `IDispatchImpl` 0xFFFF의 값으로 0xFFFF가 있는 개체를 *wMinor값으로* `IDispatchImpl` 만드는 경우 클래스는 레지스트리 대신 .dll 파일에서 형식 라이브러리를 검색합니다.

`IDispatchImpl`에는 이중 인터페이스에 `CComTypeInfoHolder` 대한 형식 정보를 관리하는 형식의 정적 멤버가 포함되어 있습니다. 동일한 이중 인터페이스를 구현하는 개체가 여러 개인 `CComTypeInfoHolder` 경우 하나의 인스턴스만 사용됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`T`

`IDispatchImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="idispatchimplgetidsofnames"></a><a name="getidsofnames"></a>IDispatchImpl::GetIDsOfNames

이름 집합을 해당하는 디스패치 식별자 집합에 매핑합니다.

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>설명

[IDispatch::GetIDsName](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames) Windows SDK에서 참조 합니다.

## <a name="idispatchimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispatchImpl::GetTypeInfo

이중 인터페이스에 대한 형식 정보를 검색합니다.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>설명

[IDispatch::GetTypeInfo](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo) Windows SDK를 참조하십시오.

## <a name="idispatchimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispatchImpl::GetTypeInfoCount

이중 인터페이스에 사용할 수 있는 형식 정보가 있는지 여부를 결정합니다.

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>설명

윈도우 `IDispatch::GetTypeInfoCount` SDK에서 참조하십시오.

## <a name="idispatchimplidispatchimpl"></a><a name="idispatchimpl"></a>I디스패치임플::I디스패치임플

생성자입니다. 이중 `AddRef` 인터페이스에 대한 형식 정보를 관리하는 보호된 멤버 변수를 호출합니다. 이 소멸자는 `Release`을 호출합니다.

```
IDispatchImpl();
```

## <a name="idispatchimplinvoke"></a><a name="invoke"></a>IDispatchImpl::호출

이중 인터페이스에서 노출되는 메서드 및 속성에 대한 액세스를 제공합니다.

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* pexcepinfo,
    UINT* puArgErr);
```

### <a name="remarks"></a>설명

[IDispatch::Windows](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) SDK에서 호출을 참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
