---
title: CComClass팩토리오토스레드 클래스
ms.date: 11/04/2016
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
ms.openlocfilehash: e997d92adfa9df46c82dacbd297db495b037c6e6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320913"
---
# <a name="ccomclassfactoryautothread-class"></a>CComClass팩토리오토스레드 클래스

이 클래스는 [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) 인터페이스를 구현하고 여러 아파트에서 개체를 만들 수 있습니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CComClassFactoryAutoThread
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComClassFactory자동 스레드::만들기 인스턴스](#createinstance)|지정된 CLSID의 개체를 만듭니다.|
|[CComClass팩토리오토스레드::록서버](#lockserver)|메모리에서 클래스 팩터리를 잠급합니다.|

## <a name="remarks"></a>설명

`CComClassFactoryAutoThread`[CComClassFactory와](../../atl/reference/ccomclassfactory-class.md)유사하지만 여러 아파트에서 개체를 만들 수 있습니다. 이 지원을 활용하려면 [CComAutoThreadModule에서](../../atl/reference/ccomautothreadmodule-class.md)EXE 모듈을 파생합니다.

ATL 개체는 일반적으로 [CComCoClass에서](../../atl/reference/ccomcoclass-class.md)파생하여 클래스 팩터리를 획득합니다. 이 클래스에는 [CComClassFactory를](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 선언하는 매크로 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)포함됩니다. 을 `CComClassFactoryAutoThread`사용하려면 개체의 클래스 정의에서 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 매크로를 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

`CComClassFactoryAutoThread`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomclassfactoryautothreadcreateinstance"></a><a name="createinstance"></a>CComClassFactory자동 스레드::만들기 인스턴스

지정된 CLSID의 개체를 만들고 이 개체에 대한 인터페이스 포인터를 검색합니다.

```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
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

모듈이 [CComAutoThreadModule에서](../../atl/reference/ccomautothreadmodule-class.md)파생되는 `CreateInstance` 경우 먼저 스레드를 선택하여 연결된 아파트에서 개체를 만듭니다.

## <a name="ccomclassfactoryautothreadlockserver"></a><a name="lockserver"></a>CComClass팩토리오토스레드::록서버

모듈 잠금 수를 각각 호출하고 `_Module::Lock` `_Module::Unlock`,

```
STDMETHODIMP LockServer(BOOL fLock);
```

### <a name="parameters"></a>매개 변수

*무리*<br/>
【인】 TRUE이면 잠금 수가 증가합니다. 그렇지 않으면 잠금 수가 감소됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

을 `_Module` `CComClassFactoryAutoThread`사용하는 경우 일반적으로 [CComAutoThreadModule의](../../atl/reference/ccomautothreadmodule-class.md)전역 인스턴스를 참조합니다.

호출을 `LockServer` 사용하면 클라이언트가 클래스 팩터리를 보유하여 여러 개체를 빠르게 만들 수 있습니다.

## <a name="see-also"></a>참고 항목

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[C컴클래스팩토리2 클래스](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactorySingleton 클래스](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObject루트텍스 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
