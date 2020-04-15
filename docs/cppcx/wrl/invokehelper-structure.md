---
title: InvokeHelper 구조체
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper
- event/Microsoft::WRL::Details::InvokeHelper::callback_
- event/Microsoft::WRL::Details::InvokeHelper::Invoke
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
helpviewer_keywords:
- Microsoft::WRL::Details::InvokeHelper structure
- Microsoft::WRL::Details::callback_ data member
- Microsoft::WRL::Details::Invoke method
- Microsoft::WRL::Details::InvokeHelper, constructor
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
ms.openlocfilehash: 9cb4e166628a6b5e7671494446d467e73c9f8cc3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371380"
---
# <a name="invokehelper-structure"></a>InvokeHelper 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<typename TDelegateInterface, typename TCallback, unsigned int argCount>
struct InvokeHelper;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 0> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 1> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 2> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 3> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 4> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 5> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 6> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 7> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 8> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 9> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;
```

### <a name="parameters"></a>매개 변수

*TDelegateInterface*<br/>
대리자 인터페이스 유형입니다.

*T콜백*<br/>
이벤트 처리기 함수의 형식입니다.

*아르그카운트*<br/>
`InvokeHelper` 전문화 된 인수의 수입니다.

## <a name="remarks"></a>설명

지정된 수와 `Invoke()` 인수 유형에 따라 메서드의 구현을 제공합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성     | Description
-------- | -----------------------------------------------------------------------------
`Traits` | 각 이벤트 처리기 인수의 형식을 정의하는 클래스의 동의어입니다.

### <a name="public-constructors"></a>Public 생성자

속성                                        | Description
------------------------------------------- | -------------------------------------------------------
[호출 도우미::호출 도우미](#invokehelper) | `InvokeHelper` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                            | Description
------------------------------- | -----------------------------------------------------------------------------------
[호출도우미::호출](#invoke) | 지정된 인수 수를 포함하는 시그니처를 포함하는 이벤트 처리기를 호출합니다.

### <a name="public-data-members"></a>공용 데이터 멤버

속성                                 | Description
------------------------------------ | ----------------------------------------------------------
[호출도우미::callback_](#callback) | 이벤트가 발생할 때 호출할 이벤트 처리기를 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`InvokeHelper`

## <a name="requirements"></a>요구 사항

**헤더:** event.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="invokehelpercallback_"></a><a name="callback"></a>호출도우미::callback_

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
TCallback callback_;
```

### <a name="remarks"></a>설명

이벤트가 발생할 때 호출할 이벤트 처리기를 나타냅니다.

템플릿 `TCallback` 매개 변수는 이벤트 처리기의 형식을 지정합니다.

## <a name="invokehelperinvoke"></a><a name="invoke"></a>호출도우미::호출

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
STDMETHOD(
   Invoke
)();
STDMETHOD(
   Invoke
)(typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
```

### <a name="parameters"></a>매개 변수

*아르그1*<br/>
인수 1.

*아르그2*<br/>
인수 2.

*아르그3*<br/>
인수 3.

*arg4*<br/>
인수 4.

*아르그 5*<br/>
인수 5.

*아르그6*<br/>
인수 6.

*아르그7*<br/>
인수 7.

*아르그8*<br/>
인수 8.

*아르그9*<br/>
인수 9.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류를 설명하는 HRESULT입니다.

### <a name="remarks"></a>설명

지정된 인수 수를 포함하는 시그니처를 포함하는 이벤트 처리기를 호출합니다.

## <a name="invokehelperinvokehelper"></a><a name="invokehelper"></a>호출 도우미::호출 도우미

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>매개 변수

*콜백(callback)*<br/>
이벤트 처리기입니다.

### <a name="remarks"></a>설명

`InvokeHelper` 클래스의 새 인스턴스를 초기화합니다.

템플릿 `TCallback` 매개 변수는 이벤트 처리기의 형식을 지정합니다.
