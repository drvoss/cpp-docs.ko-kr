---
title: CComClassFactorySingleton 클래스
ms.date: 11/04/2016
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
ms.openlocfilehash: ec860f7ef59b7d3289bf2e18fea0f0e064a7c8f9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320814"
---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton 클래스

이 클래스는 [CComClassFactory에서](../../atl/reference/ccomclassfactory-class.md) 파생되며 [CComObjectGlobal을](../../atl/reference/ccomobjectglobal-class.md) 사용하여 단일 개체를 생성합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
당신의 클래스.

`CComClassFactorySingleton`[CComClassFactory에서](../../atl/reference/ccomclassfactory-class.md) 파생되며 [CComObjectGlobal을](../../atl/reference/ccomobjectglobal-class.md) 사용하여 단일 개체를 생성합니다. 메서드에 대한 `CreateInstance` 각 호출은 인터페이스 포인터에 대해 이 개체를 쿼리하기만 하면 됩니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComClassFactorySingleton::CreateInstance](#createinstance)|인터페이스 `m_spObj` 포인터에 대한 쿼리입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComClassFactorySingleton::m_spObj](#m_spobj)|`CComClassFactorySingleton`에 의해 생성된 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 개체입니다.|

## <a name="remarks"></a>설명

ATL 개체는 일반적으로 [CComCoClass에서](../../atl/reference/ccomcoclass-class.md)파생하여 클래스 팩터리를 획득합니다. 이 클래스에는 `CComClassFactory`를 기본 클래스 팩터리로 선언하는 매크로 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) 포함되어 있습니다. 을 `CComClassFactorySingleton`사용하려면 개체의 클래스 정의에서 [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) 매크로를 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)

`CComClassFactorySingleton`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomclassfactorysingletoncreateinstance"></a><a name="createinstance"></a>CComClass팩토리싱글톤::만들기 인스턴스

[M_spObj](#m_spobj)를 통해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색합니다.

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

## <a name="ccomclassfactorysingletonm_spobj"></a><a name="m_spobj"></a>CComClass팩토리싱글톤::m_spObj

`CComClassFactorySingleton`에 의해 생성된 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 개체입니다.

```
CComPtr<IUnknown> m_spObj;
```

### <a name="remarks"></a>설명

[CreateInstance](#createinstance) 메서드에 대 한 각 호출 단순히 인터페이스 포인터에 대 한이 개체를 쿼리합니다.

현재 형식은 `m_spObj` 이전 버전의 ATL에서 `CComClassFactorySingleton` 작동했던 방식에서 획기적인 변화를 나타냅니다. 이전 버전에서는 `CComClassFactorySingleton` 서버 초기화 중에 개체가 클래스 팩터리와 동시에 만들어졌습니다. Visual C++.NET 2003 이상에서 첫 번째 요청시 개체가 느리게 만들어집니다. 이 변경으로 인해 초기화에 의존하는 프로그램에서 오류가 발생할 수 있습니다.

## <a name="see-also"></a>참고 항목

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[C컴클래스팩토리2 클래스](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClass팩토리오토스레드 클래스](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComObject루트텍스 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
