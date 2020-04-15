---
title: SimpleClassFactory 클래스
ms.date: 09/7/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
helpviewer_keywords:
- Microsoft::WRL::SimpleClassFactory class
- Microsoft::WRL::SimpleClassFactory::CreateInstance method
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
ms.openlocfilehash: 924b9d2c30f11e6f0444d9c647807f1c86dcc411
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373553"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory 클래스

기본 클래스를 만드는 기본적인 메커니즘을 제공합니다.

## <a name="syntax"></a>구문

```cpp
template<typename Base>
class SimpleClassFactory : public ClassFactory<>;
```

### <a name="parameters"></a>매개 변수

*기본*<br/>
기본 클래스입니다.

## <a name="remarks"></a>설명

기본 클래스는 기본 생성자제공을 제공해야 합니다.

다음 코드 예제에서는 `SimpleClassFactory` [ActivatableClassWithFactoryEx](activatableclass-macros.md) 매크로를 사용하는 방법을 보여 줍니다.

`ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[SimpleClassFactory::CreateInstance 메서드](#createinstance)|지정된 인터페이스의 인스턴스를 만듭니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ClassFactory`

`SimpleClassFactory`

## <a name="requirements"></a>요구 사항

**헤더:** 모듈.h

**네임스페이스:** Microsoft::WRL

## <a name="simpleclassfactorycreateinstance-method"></a><a name="createinstance"></a>심플클래스팩토리::만들기 인스턴스 메서드

지정된 인터페이스의 인스턴스를 만듭니다.

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

#### <a name="parameters"></a>매개 변수

*pUnkOuter*<br/>
이어야 `nullptr`합니다. 그렇지 않으면 반환 값이 CLASS_E_NOAGGREGATION.

SimpleClassFactory는 집계를 지원하지 않습니다. 집계가 지원되고 생성되는 개체가 집계의 일부인 경우 *pUnkOuter는* 집계의 `IUnknown` 제어 인터페이스에 대한 포인터가 됩니다.

*riid*<br/>
만들 개체의 인터페이스 ID입니다.

*ppvObject*<br/>
이 작업이 완료되면 *riid* 매개 변수에 의해 지정된 개체의 인스턴스에 대한 포인터를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

정의된 `__WRL_STRICT__` 경우 클래스 템플릿 매개 변수에 지정된 기본 클래스가 [RuntimeClass에서](runtimeclass-class.md)파생되지 않았거나 ClassicCom 또는 WinRtClassicComMix [런타임클래스 유형](runtimeclasstype-enumeration.md) 열거 값으로 구성되지 않은 경우 어설션 오류가 내보루션됩니다.
