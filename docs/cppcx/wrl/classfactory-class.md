---
title: ClassFactory 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
- module/Microsoft::WRL::ClassFactory::AddRef
- module/Microsoft::WRL::ClassFactory::ClassFactory
- module/Microsoft::WRL::ClassFactory::LockServer
- module/Microsoft::WRL::ClassFactory::QueryInterface
- module/Microsoft::WRL::ClassFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ClassFactory class
- Microsoft::WRL::ClassFactory::AddRef method
- Microsoft::WRL::ClassFactory::ClassFactory, constructor
- Microsoft::WRL::ClassFactory::LockServer method
- Microsoft::WRL::ClassFactory::QueryInterface method
- Microsoft::WRL::ClassFactory::Release method
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
ms.openlocfilehash: 3b738cc8f439e6653162ab99b0a26e87aa8fee36
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372674"
---
# <a name="classfactory-class"></a>ClassFactory 클래스

`IClassFactory` 인터페이스의 기본 기능을 구현합니다.

## <a name="syntax"></a>구문

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ClassFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IClassFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<ClassicCom | InhibitWeakReference>,
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

사용자 `ClassFactory` 정의 팩터리 구현을 제공하는 데 활용합니다.

다음 프로그래밍 패턴에서는 [구현 구조를](implements-structure.md) 사용하여 클래스 팩터리에서 세 개 이상의 인터페이스를 지정하는 방법을 보여 줍니다.

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                        | Description
------------------------------------------- | -----------
[클래스팩토리::클래스팩토리](#classfactory) |

### <a name="public-methods"></a>Public 메서드

속성                                            | Description
----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------
[클래스팩토리::애드레프](#addref)                 | 현재 `ClassFactory` 개체에 대한 참조 수를 증가합니다.
[클래스 팩토리 :: 잠금 서버](#lockserver)         | 현재 `ClassFactory` 개체에서 추적하는 기본 개체의 수를 증가하거나 감소시입니다.
[클래스팩터::쿼리 인터페이스](#queryinterface) | 매개 변수에 의해 지정된 인터페이스에 대한 포인터를 검색합니다.
[클래스팩토리::릴리스](#release)               | 현재 `ClassFactory` 개체에 대한 참조 수를 감소시입니다.

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

## <a name="requirements"></a>요구 사항

**헤더:** 모듈.h

**네임스페이스:** Microsoft::WRL

## <a name="classfactoryaddref"></a><a name="addref"></a>클래스팩토리::애드레프

현재 `ClassFactory` 개체에 대한 참조 수를 증가합니다.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.

## <a name="classfactoryclassfactory"></a><a name="classfactory"></a>클래스팩토리::클래스팩토리

```cpp
WRL_NOTHROW ClassFactory();
```

## <a name="classfactorylockserver"></a><a name="lockserver"></a>클래스 팩토리 :: 잠금 서버

현재 `ClassFactory` 개체에서 추적하는 기본 개체의 수를 증가하거나 감소시입니다.

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>매개 변수

*무리*<br/>
**추적된** 개체 수를 증가시려면 true입니다. **추적된** 개체의 수를 감소시가지기 위해 false를 사용합니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 E_FAIL입니다.

### <a name="remarks"></a>설명

`ClassFactory`은 [Module](module-class.md) 클래스의 기본 인스턴스에서 개체를 추적합니다.

## <a name="classfactoryqueryinterface"></a><a name="queryinterface"></a>클래스팩터::쿼리 인터페이스

매개 변수에 의해 지정된 인터페이스에 대한 포인터를 검색합니다.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*ppvObject*<br/>
이 작업이 완료되면 매개 변수 *riid에*의해 지정된 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.

## <a name="classfactoryrelease"></a><a name="release"></a>클래스팩토리::릴리스

현재 `ClassFactory` 개체에 대한 참조 수를 감소시입니다.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.
