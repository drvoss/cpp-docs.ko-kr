---
title: C컴클래스팩토리2 클래스
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
ms.openlocfilehash: 0cb2064cfaea6317c4522ff917f3963fca2219b8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321010"
---
# <a name="ccomclassfactory2-class"></a>C컴클래스팩토리2 클래스

이 클래스는 [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) 인터페이스를 구현합니다.

## <a name="syntax"></a>구문

```
template <class license>
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

#### <a name="parameters"></a>매개 변수

*라이센스*<br/>
다음과 같은 정적 함수를 구현하는 클래스:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComClassFactory2::만들기 인스턴스](#createinstance)|지정된 CLSID의 개체를 만듭니다.|
|[CComClassFactory2::만들기인스턴스Lic](#createinstancelic)|라이센스 키가 주어지면 지정된 CLSID의 개체가 만들어집니다.|
|[CComClass팩토리2::GetLicInfo](#getlicinfo)|클래스 팩터리의 라이선스 기능을 설명하는 정보를 검색합니다.|
|[CComClassFactory2::잠금 서버](#lockserver)|메모리에서 클래스 팩터리를 잠급합니다.|
|[CComClassFactory2::요청 리키](#requestlickey)|라이센스 키를 만들고 반환합니다.|

## <a name="remarks"></a>설명

`CComClassFactory2`[IClassFactory의](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) 확장인 [IClassFactory2](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)인터페이스를 구현합니다. `IClassFactory2`라이선스를 통해 개체 생성을 제어합니다. 라이센스가 부여된 컴퓨터에서 실행되는 클래스 팩터리는 런타임 라이센스 키를 제공할 수 있습니다. 이 라이센스 키를 사용하면 전체 컴퓨터 라이센스가 없는 경우 응용 프로그램이 개체를 인스턴스화할 수 있습니다.

ATL 개체는 일반적으로 [CComCoClass에서](../../atl/reference/ccomcoclass-class.md)파생하여 클래스 팩터리를 획득합니다. 이 클래스에는 [CComClassFactory를](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 선언하는 매크로 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)포함됩니다. 을 `CComClassFactory2`사용하려면 개체의 클래스 정의에서 [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) 매크로를 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]

`CMyLicense`에서 템플릿 매개 `CComClassFactory2`변수를 " 정적 `VerifyLicenseKey` `GetLicenseKey`함수 `IsLicenseValid`를 구현해야 합니다. 다음은 간단한 라이센스 클래스의 예입니다.

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]

`CComClassFactory2`라이선스 모두에서 `CComClassFactory2Base` 파생됩니다. *license* `CComClassFactory2Base`, 차례로, 에서 `IClassFactory2` 파생됩니다. `CComObjectRootEx< CComGlobalsThreadModel >`

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

`license`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory2`

`CComClassFactory2`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomclassfactory2createinstance"></a><a name="createinstance"></a>CComClassFactory2::만들기 인스턴스

지정된 CLSID의 개체를 만들고 이 개체에 대한 인터페이스 포인터를 검색합니다.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>매개 변수

*pUnkOuter*<br/>
【인】 개체가 집계의 일부로 생성되는 경우 *pUnKOuter는* 알 수 없는 외부여야 합니다. 그렇지 않으면 *pUnkOuter는* NULL이어야 합니다.

*riid*<br/>
【인】 요청된 인터페이스의 IID입니다. *pUnkOuter가* NULL이 아닌 경우 *riid가* 되어야 `IID_IUnknown`합니다.

*ppvObj*<br/>
【아웃】 *riid로*식별된 인터페이스 포인터에 대한 포인터입니다. 개체가 이 인터페이스를 지원하지 않으면 *ppvObj가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

기계에 대한 라이센스를 완전히 부여해야 합니다. 전체 컴퓨터 라이센스가 없는 경우 [CreateInstanceLic](#createinstancelic)을 호출합니다.

## <a name="ccomclassfactory2createinstancelic"></a><a name="createinstancelic"></a>CComClassFactory2::만들기인스턴스Lic

[CreateInstance와](#createinstance)유사합니다. `CreateInstanceLic`

```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
*/,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*pUnkOuter*<br/>
【인】 개체가 집계의 일부로 생성되는 경우 *pUnKOuter는* 알 수 없는 외부여야 합니다. 그렇지 않으면 *pUnkOuter는* NULL이어야 합니다.

*펀크예약*<br/>
【인】 사용되지 않습니다. Null이어야 합니다.

*riid*<br/>
【인】 요청된 인터페이스의 IID입니다. *pUnkOuter가* NULL이 아닌 경우 *riid가* 되어야 `IID_IUnknown`합니다.

*블스트키*<br/>
【인】 에 대한 호출에서 이전에 얻은 런타임 `RequestLicKey`라이센스 키입니다. 이 키는 개체를 만드는 데 필요합니다.

*ppvObject*<br/>
【아웃】 *riid*. 개체가 이 인터페이스를 지원하지 않으면 *ppvObject가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

[RequestLicKey](#requestlickey)을 사용하여 라이센스 키를 얻을 수 있습니다. 라이센스가 없는 컴퓨터에서 개체를 만들려면 을 `CreateInstanceLic`호출해야 합니다.

## <a name="ccomclassfactory2getlicinfo"></a><a name="getlicinfo"></a>CComClass팩토리2::GetLicInfo

CLASS 팩터리의 라이선스 기능을 설명하는 정보로 [LICINFO](/windows/win32/api/ocidl/ns-ocidl-licinfo) 구조를 채웁니다.

```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```

### <a name="parameters"></a>매개 변수

*pLicInfo*<br/>
【아웃】 구조에 `LICINFO` 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 `fRuntimeKeyAvail` 구조의 멤버는 라이센스 키가 주어지면 클래스 팩터리에서 라이센스가 없는 컴퓨터에서 개체를 만들 수 있는지 여부를 나타냅니다. *fLicVerifi된* 멤버는 전체 컴퓨터 라이센스가 있는지 여부를 나타냅니다.

## <a name="ccomclassfactory2lockserver"></a><a name="lockserver"></a>CComClassFactory2::잠금 서버

모듈 잠금 수를 각각 호출하고 `_Module::Lock` `_Module::Unlock`,

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>매개 변수

*무리*<br/>
【인】 TRUE이면 잠금 수가 증가합니다. 그렇지 않으면 잠금 수가 감소됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

`_Module`은 [CComModule의](../../atl/reference/ccommodule-class.md) 전역 인스턴스 또는 이로부터 파생된 클래스를 나타냅니다.

호출을 `LockServer` 사용하면 클라이언트가 클래스 팩터리를 보유하여 여러 개체를 빠르게 만들 수 있습니다.

## <a name="ccomclassfactory2requestlickey"></a><a name="requestlickey"></a>CComClassFactory2::요청 리키

LICINFO 구조의 구성원이 TRUE인 `fRuntimeKeyAvail` 경우 [라이센스](/windows/win32/api/ocidl/ns-ocidl-licinfo) 키를 만들고 반환합니다.

```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```

### <a name="parameters"></a>매개 변수

*dwReserved*<br/>
【인】 사용되지 않습니다. 0이어야 합니다.

*pbstrKey*<br/>
【아웃】 라이센스 키에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

라이센스 키는 라이센스가 없는 컴퓨터에서 개체를 만들려면 [CreateInstanceLic을](#createinstancelic) 호출하는 데 필요합니다. FALSE인 경우 `fRuntimeKeyAvail` 개체는 완전히 사용이 허가된 컴퓨터에서만 만들 수 있습니다.

[GetLicInfo에](#getlicinfo) 전화하여 의 `fRuntimeKeyAvail`값을 검색합니다.

## <a name="see-also"></a>참고 항목

[CComClass팩토리오토스레드 클래스](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComClassFactorySingleton 클래스](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObject루트텍스 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
