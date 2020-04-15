---
title: SimpleActivationFactory 클래스
ms.date: 09/07/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
helpviewer_keywords:
- Microsoft::WRL::SimpleActivationFactory class
- Microsoft::WRL::SimpleActivationFactory::ActivateInstance method
- Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::SimpleActivationFactory::GetTrustLevel method
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
ms.openlocfilehash: 39e539c63e91b508f51656114ee8fbd68150991f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370945"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory 클래스

Windows 런타임 또는 클래식 COM 기본 클래스를 만드는 기본적인 메커니즘을 제공합니다.

## <a name="syntax"></a>구문

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>매개 변수

*기본*<br/>
기본 클래스입니다.

## <a name="remarks"></a>설명

기본 클래스는 기본 생성자제공을 제공해야 합니다.

다음 코드 예제에서는 SimpleActivationFactory를 사용 하는 방법을 보여 [줍니다.ActivatableClassWithFactoryEx](activatableclass-macros.md) 매크로를 사용 하 여.

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[SimpleActivationFactory::ActivateInstance 메서드](#activateinstance)|지정된 인터페이스의 인스턴스를 만듭니다.|
|[SimpleActivationFactory::GetRuntimeClassName 메서드](#getruntimeclassname)|*Base* 클래스 템플릿 매개 변수에 의해 지정된 클래스의 인스턴스의 런타임 클래스 이름을 가져옵니다.|
|[SimpleActivationFactory::GetTrustLevel 메서드](#gettrustlevel)|*Base* 클래스 템플릿 매개 변수에 의해 지정된 클래스의 인스턴스의 신뢰 수준을 가져옵니다.|

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

`ActivationFactory`

`SimpleActivationFactory`

## <a name="requirements"></a>요구 사항

**헤더:** 모듈.h

**네임스페이스:** Microsoft::WRL

## <a name="simpleactivationfactoryactivateinstance-method"></a><a name="activateinstance"></a>단순 활성화공장::활성화 인스턴스 메서드

지정된 인터페이스의 인스턴스를 만듭니다.

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

#### <a name="parameters"></a>매개 변수

*ppvObject*<br/>
이 작업이 완료되면 클래스 템플릿 매개 변수에 의해 `Base` 지정된 개체의 인스턴스에 대한 포인터를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

정의된 `__WRL_STRICT__` 경우 클래스 템플릿 매개 변수에 지정된 기본 클래스가 [RuntimeClass에서](runtimeclass-class.md)파생되지 않았거나 WinRt 또는 WinRtClassicComMix [런타임클래스 유형](runtimeclasstype-enumeration.md) 열거 값으로 구성되지 않은 경우 어설션 오류가 내보루션됩니다.

## <a name="simpleactivationfactorygetruntimeclassname-method"></a><a name="getruntimeclassname"></a>단순 활성화 공장::GetRuntimeClassName 메서드

`Base` 클래스 템플릿 매개 변수에 의해 지정된 클래스의 인스턴스의 런타임 클래스 이름을 가져옵니다.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

#### <a name="parameters"></a>매개 변수

*런타임 이름*<br/>
이 작업이 완료되면 런타임 클래스 이름이 지정됩니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

정의된 `__WRL_STRICT__` 경우 `Base` 클래스 템플릿 매개 변수에 의해 지정된 클래스가 [RuntimeClass에서](runtimeclass-class.md)파생되지 않았거나 WinRt 또는 WinRtClassicComMix [런타임클래스 유형](runtimeclasstype-enumeration.md) 열거 값으로 구성되지 않은 경우 어설션 오류가 내보루션됩니다.

## <a name="simpleactivationfactorygettrustlevel-method"></a><a name="gettrustlevel"></a>단순 활성화팩토리::GetTrustLevel 방법

클래스 템플릿 매개 변수에 의해 지정된 `Base` 클래스의 인스턴스의 신뢰 수준을 가져옵니다.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

#### <a name="parameters"></a>매개 변수

*트러스트Lvl*<br/>
이 작업이 완료되면 현재 클래스 개체의 신뢰 수준이 됩니다.

### <a name="return-value"></a>Return Value

항상 S_OK.
