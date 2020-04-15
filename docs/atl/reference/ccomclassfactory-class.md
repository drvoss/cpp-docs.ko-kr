---
title: CComClassFactory 클래스
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
ms.openlocfilehash: 041575339906b83488697f1db5a7f8b08b53070e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321030"
---
# <a name="ccomclassfactory-class"></a>CComClassFactory 클래스

이 클래스는 [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) 인터페이스를 구현합니다.

## <a name="syntax"></a>구문

```
class CComClassFactory
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComClassFactory::CreateInstance](#createinstance)|지정된 CLSID의 개체를 만듭니다.|
|[CComClass공장::잠금 서버](#lockserver)|메모리에서 클래스 팩터리를 잠급합니다.|

## <a name="remarks"></a>설명

`CComClassFactory`에서는 특정 CLSID의 개체를 만드는 메서드를 포함 하는 [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) 인터페이스를 구현 하 고 새 개체를 더 빨리 만들 수 있도록 메모리에 클래스 팩터리 잠금을 포함 합니다. `IClassFactory`시스템 레지스트리에 등록하고 CLSID를 할당하는 모든 클래스에 대해 구현되어야 합니다.

ATL 개체는 일반적으로 [CComCoClass에서](../../atl/reference/ccomcoclass-class.md)파생하여 클래스 팩터리를 획득합니다. 이 클래스에는 `CComClassFactory`를 기본 클래스 팩터리로 선언하는 매크로 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) 포함되어 있습니다. 이 기본값을 재정의하려면 클래스 `DECLARE_CLASSFACTORY`정의에서 *XXX* 매크로 중 하나를 지정합니다. 예를 들어 [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) 매크로는 클래스 팩터리에 대해 지정된 클래스를 사용합니다.

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]

위의 클래스 정의는 `CMyClassFactory` 개체의 기본 클래스 팩터리로 사용할 지정합니다. `CMyClassFactory`에서 `CComClassFactory` 파생되고 재정의해야 `CreateInstance`합니다.

ATL은 클래스 팩터리를 선언하는 세 가지 다른 매크로를 제공합니다.

- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) 라이센스를 통해 생성을 제어하는 [CComClassFactory2를](../../atl/reference/ccomclassfactory2-class.md)사용합니다.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) [CComClassFactoryAutoThread를](../../atl/reference/ccomclassfactoryautothread-class.md)사용하여 여러 아파트에서 개체를 만듭니다.

- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) 단일 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 개체를 생성하는 [CComClassFactorySingleton을](../../atl/reference/ccomclassfactorysingleton-class.md)사용합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomclassfactorycreateinstance"></a><a name="createinstance"></a>CComClassFactory::만들기 인스턴스

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

## <a name="ccomclassfactorylockserver"></a><a name="lockserver"></a>CComClass공장::잠금 서버

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

## <a name="see-also"></a>참고 항목

[CComObject루트텍스 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
