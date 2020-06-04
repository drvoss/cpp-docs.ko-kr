---
title: ActivationFactory 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::AddRef
- module/Microsoft::WRL::ActivationFactory::GetIids
- module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
- module/Microsoft::WRL::ActivationFactory::QueryInterface
- module/Microsoft::WRL::ActivationFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ActivationFactory class
- Microsoft::WRL::ActivationFactory::ActivationFactory, constructor
- Microsoft::WRL::ActivationFactory::AddRef method
- Microsoft::WRL::ActivationFactory::GetIids method
- Microsoft::WRL::ActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::ActivationFactory::GetTrustLevel method
- Microsoft::WRL::ActivationFactory::QueryInterface method
- Microsoft::WRL::ActivationFactory::Release method
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
ms.openlocfilehash: 0655caeb3f49a18e9c57c78f0008901aaaedda4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368702"
---
# <a name="activationfactory-class"></a>ActivationFactory 클래스

Windows 런타임으로 활성화할 클래스를 하나 이상 사용합니다.

## <a name="syntax"></a>구문

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ActivationFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IActivationFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<WinRt | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>매개 변수

*I0*<br/>
제로 인터페이스입니다.

*I1*<br/>
첫 번째 인터페이스입니다.

*I2*<br/>
두 번째 인터페이스입니다.

## <a name="remarks"></a>설명

`ActivationFactory`은 `IActivationFactory` 인터페이스에 대한 등록 방법 및 기본 기능을 제공합니다. `ActivationFactory`또한 사용자 지정 팩터리 구현을 제공할 수 있습니다.

다음 코드 조각은 활성화를 사용하는 방법을 상징적으로 보여 줍니다.

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../codesnippet/CPP/activationfactory-class_1.cpp)]

다음 코드 조각에서는 구현 [구조에서](implements-structure.md) 세 개 이상의 인터페이스 아이디를 지정하는 방법을 보여 줍니다.

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                                       | Description
---------------------------------------------------------- | ------------------------------------------
[정품 인증공장::정품 인증공장](#activationfactory) | `ActivationFactory` 클래스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                                                           | Description
-------------------------------------------------------------- | --------------------------------------------------------------------------------------------
[정품 인증공장::추가 참조](#addref)                           | 현재 `ActivationFactory` 개체의 참조 수를 증가합니다.
[정품 인증공장::GetIids](#getiids)                         | 구현된 인터페이스 ID의 배열을 가져옵니다.
[정품 인증팩토리::GetRuntimeClass이름](#getruntimeclassname) | 현재 `ActivationFactory` 인스턴스화하는 개체의 런타임 클래스 이름을 가져옵니다.
[정품 인증팩토리::GetTrustLevel](#gettrustlevel)             | 현재 `ActivationFactory` 인스턴스화하는 개체의 신뢰 수준을 가져옵니다.
[정품 인증공장::쿼리 인터페이스](#queryinterface)           | 지정된 인터페이스에 대한 포인터를 검색합니다.
[정품 인증공장::릴리스](#release)                         | 현재 `ActivationFactory` 개체의 참조 수를 감소시입니다.

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

## <a name="requirements"></a>요구 사항

**헤더:** 모듈.h

**네임스페이스:** Microsoft::WRL

## <a name="activationfactoryactivationfactory"></a><a name="activationfactory"></a>정품 인증공장::정품 인증공장

`ActivationFactory` 클래스를 초기화합니다.

```cpp
ActivationFactory();
```

## <a name="activationfactoryaddref"></a><a name="addref"></a>정품 인증공장::추가 참조

현재 `ActivationFactory` 개체의 참조 수를 증가합니다.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.

## <a name="activationfactorygetiids"></a><a name="getiids"></a>정품 인증공장::GetIids

구현된 인터페이스 ID의 배열을 가져옵니다.

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>매개 변수

*이드 카운트*<br/>
이 작업이 완료되면 *iids* 배열의 인터ace ID 수가 됩니다.

*아이드 (이드)*<br/>
이 작업이 완료될 대 구현된 인터페이스 ID의 배열입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다. E_OUTOFMEMORY는 가능한 실패 HRESULT입니다.

## <a name="activationfactorygetruntimeclassname"></a><a name="getruntimeclassname"></a>정품 인증팩토리::GetRuntimeClass이름

현재 `ActivationFactory` 인스턴스화하는 개체의 런타임 클래스 이름을 가져옵니다.

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>매개 변수

*런타임 이름*<br/>
이 작업이 완료되면 현재 `ActivationFactory` 인스턴스화하는 개체의 런타임 클래스 이름이 포함된 문자열에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.

## <a name="activationfactorygettrustlevel"></a><a name="gettrustlevel"></a>정품 인증팩토리::GetTrustLevel

현재 `ActivationFactory` 인스턴스화하는 개체의 신뢰 수준을 가져옵니다.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>매개 변수

*트러스트Lvl*<br/>
이 작업이 완료되면 `ActivationFactory` 인스턴스화하는 런타임 클래스의 신뢰 수준이 됩니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 어설션 오류가 내보내지고 *trustLvl이* 로 `FullTrust`설정됩니다.

## <a name="activationfactoryqueryinterface"></a><a name="queryinterface"></a>정품 인증공장::쿼리 인터페이스

지정된 인터페이스에 대한 포인터를 검색합니다.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*ppvObject*<br/>
이 작업이 완료되면 매개 변수 *riid로*지정한 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.

## <a name="activationfactoryrelease"></a><a name="release"></a>정품 인증공장::릴리스

현재 `ActivationFactory` 개체의 참조 수를 감소시입니다.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.
