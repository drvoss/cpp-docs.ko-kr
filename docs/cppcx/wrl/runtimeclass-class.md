---
title: RuntimeClass 클래스
ms.date: 09/11/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::AddRef
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
- implements/Microsoft::WRL::RuntimeClass::GetIids
- implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
- implements/Microsoft::WRL::RuntimeClass::InternalAddRef
- implements/Microsoft::WRL::RuntimeClass::QueryInterface
- implements/Microsoft::WRL::RuntimeClass::Release
- implements/Microsoft::WRL::RuntimeClass::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::~RuntimeClass
helpviewer_keywords:
- Microsoft::WRL::RuntimeClass class
- Microsoft::WRL::RuntimeClass::AddRef method
- Microsoft::WRL::RuntimeClass::DecrementReference method
- Microsoft::WRL::RuntimeClass::GetIids method
- Microsoft::WRL::RuntimeClass::GetRuntimeClassName method
- Microsoft::WRL::RuntimeClass::GetTrustLevel method
- Microsoft::WRL::RuntimeClass::GetWeakReference method
- Microsoft::WRL::RuntimeClass::InternalAddRef method
- Microsoft::WRL::RuntimeClass::QueryInterface method
- Microsoft::WRL::RuntimeClass::Release method
- Microsoft::WRL::RuntimeClass::RuntimeClass, constructor
- Microsoft::WRL::RuntimeClass::~RuntimeClass, destructor
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
ms.openlocfilehash: 64b4124ba3c60fdcb53fc29c7b791c0f73a49579
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376226"
---
# <a name="runtimeclass-class"></a>RuntimeClass 클래스

지정된 인터페이스를 상속 하 고 지정 된 Windows 런타임, 클래식 COM 및 약한 참조 지원을 제공 하는 WinRT 또는 COM 클래스를 나타냅니다.

이 클래스는 WinRT 및 COM 클래스의 상용구 구현을 `AddRef` `Release` 제공하여 모듈의 `QueryInterface`참조 수를 관리하고 활성화 가능한 개체에 대한 클래스 팩터리 제공을 지원합니다.

## <a name="syntax"></a>구문

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>매개 변수

*클래스 플래그*<br/>
선택적 매개 변수. 하나 이상의 [런타임클래스Type](runtimeclasstype-enumeration.md) 열거 형 열거 값의 조합입니다. 매크로는 `__WRL_CONFIGURATION_LEGACY__` 프로젝트의 모든 런타임 클래스에 대한 classFlags의 기본값을 변경하도록 정의할 수 있습니다. 정의된 경우 RuntimeClass 인스턴스는 기본적으로 애자일하지 않습니다. 정의되지 않은 경우 RuntimeClass 인스턴스는 기본적으로 민첩합니다. 모호성을 방지하려면 항상 `Microsoft::WRL::FtmBase` 를 `TInterfaces` `RuntimeClassType::InhibitFtmBase`지정하거나 . 참고, inhibitFtmBase 및 FtmBase 둘 다 사용 하는 경우 개체 민첩 한 될 것입니다.

*TInterfaces*<br/>
개체가 구현하는 `IUnknown`인터페이스 목록 `IInspectable` 또는 [RuntimeClassType에](runtimeclasstype-enumeration.md)의해 제어되는 다른 인터페이스. 또한 개체를 민첩하게 만들고 구현하도록 `Microsoft::WRL::FtmBase` `IMarshal`하기 위해 파생될 다른 클래스를 나열할 수도 있습니다.

## <a name="members"></a>멤버

`RuntimeClassInitialize`<br/>
`MakeAndInitialize` 템플릿 함수가 개체를 생성하는 데 사용되는 경우 개체를 초기화하는 함수입니다. 개체가 성공적으로 초기화되었는지 S_OK 초기화가 실패한 경우 COM 오류 코드가 반환됩니다. COM 오류 코드는 `MakeAndInitialize`의 반환 값으로 전파됩니다. `Make` 템플릿 함수가 개체를 `RuntimeClassInitialize` 생성하는 데 사용되는 경우 메서드가 호출되지 않습니다.

### <a name="public-constructors"></a>Public 생성자

| 속성                                               | Description                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| [런타임 클래스::런타임클래스](#runtimeclass)        | 클래스의 현재 인스턴스를 `RuntimeClass` 초기화합니다.   |
| [런타임 클래스::~런타임클래스](#tilde-runtimeclass) | 클래스의 현재 인스턴스를 초기화합니다. `RuntimeClass` |

### <a name="public-methods"></a>Public 메서드

| 속성                                                      | Description                                                                                        |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [런타임 클래스::추가](#addref)                           | 현재 `RuntimeClass` 개체에 대한 참조 수를 증가합니다.                              |
| [런타임 클래스::D:Decrecrereference](#decrementreference)   | 현재 `RuntimeClass` 개체에 대한 참조 수를 감소시입니다.                              |
| [런타임 클래스::GetIids](#getiids)                         | 현재 `RuntimeClass` 개체에서 구현한 인터페이스 ID를 포함할 수 있는 배열을 가져옵니다. |
| [런타임 클래스::겟런타임클래스이름](#getruntimeclassname) | 현재 `RuntimeClass` 개체의 런타임 클래스 이름을 가져옵니다.                                  |
| [런타임 클래스::GetTrustLevel](#gettrustlevel)             | 현재 `RuntimeClass` 개체의 신뢰 수준을 가져옵니다.                                         |
| [런타임 클래스::GetWeak참조](#getweakreference)       | 현재 `RuntimeClass` 개체에 대한 약한 참조 개체에 대한 포인터를 가져옵니다.                 |
| [런타임 클래스::내부 애드레프](#internaladdref)           | 참조 수를 현재 `RuntimeClass` 개체에 증분합니다.                               |
| [런타임 클래스::쿼리 인터페이스](#queryinterface)           | 지정된 인터페이스 ID에 대한 포인터를 검색합니다.                                                 |
| [런타임 클래스::릴리스](#release)                         | 현재 `RuntimeClass` 개체에서 COM 릴리스 작업을 수행합니다.                             |

## <a name="inheritance-hierarchy"></a>상속 계층 구조

이 구현 세부 정보입니다.

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="runtimeclassruntimeclass"></a><a name="tilde-runtimeclass"></a>런타임 클래스::~런타임클래스

클래스의 현재 인스턴스를 초기화합니다. `RuntimeClass`

```cpp
virtual ~RuntimeClass();
```

## <a name="runtimeclassaddref"></a><a name="addref"></a>런타임 클래스::추가

현재 `RuntimeClass` 개체에 대한 참조 수를 증가합니다.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="runtimeclassdecrementreference"></a><a name="decrementreference"></a>런타임 클래스::D:Decrecrereference

현재 `RuntimeClass` 개체에 대한 참조 수를 감소시입니다.

```cpp
ULONG DecrementReference();
```

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="runtimeclassgetiids"></a><a name="getiids"></a>런타임 클래스::GetIids

현재 `RuntimeClass` 개체에서 구현한 인터페이스 ID를 포함할 수 있는 배열을 가져옵니다.

```cpp
STDMETHOD(
   GetIids
)
   (_Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>매개 변수

*이드 카운트*<br/>
이 작업이 완료되면 배열 *iids의*총 요소 수가 됩니다.

*아이드 (이드)*<br/>
이 작업이 완료될 때 인터페이스 ID 배열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 E_OUTOFMEMORY입니다.

## <a name="runtimeclassgetruntimeclassname"></a><a name="getruntimeclassname"></a>런타임 클래스::겟런타임클래스이름

현재 `RuntimeClass` 개체의 런타임 클래스 이름을 가져옵니다.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>매개 변수

*런타임 이름*<br/>
이 작업이 완료되면 런타임 클래스 이름이 지정됩니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

어설션 오류가 `__WRL_STRICT__` 정의되거나 `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` 정의되지 않은 경우 내보내입니다.

## <a name="runtimeclassgettrustlevel"></a><a name="gettrustlevel"></a>런타임 클래스::GetTrustLevel

현재 `RuntimeClass` 개체의 신뢰 수준을 가져옵니다.

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>매개 변수

*트러스트Lvl*<br/>
이 작업이 완료되면 현재 `RuntimeClass` 개체의 신뢰 수준이 됩니다.

### <a name="return-value"></a>Return Value

항상 S_OK.

### <a name="remarks"></a>설명

어설션 오류가 `__WRL_STRICT__` 정의되거나 `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` 정의되지 않은 경우 내보내입니다.

## <a name="runtimeclassgetweakreference"></a><a name="getweakreference"></a>런타임 클래스::GetWeak참조

현재 `RuntimeClass` 개체에 대한 약한 참조 개체에 대한 포인터를 가져옵니다.

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>매개 변수

*약한 참조*<br/>
이 작업이 완료되면 약한 참조 개체에 대한 포인터가 됩니다.

### <a name="return-value"></a>Return Value

항상 S_OK.

## <a name="runtimeclassinternaladdref"></a><a name="internaladdref"></a>런타임 클래스::내부 애드레프

참조 수를 현재 `RuntimeClass` 개체에 증분합니다.

```cpp
ULONG InternalAddRef();
```

### <a name="return-value"></a>Return Value

결과 참조 수입니다.

## <a name="runtimeclassqueryinterface"></a><a name="queryinterface"></a>런타임 클래스::쿼리 인터페이스

지정된 인터페이스 ID에 대한 포인터를 검색합니다.

```cpp
STDMETHOD(
   QueryInterface
)
   (REFIID riid,
   _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*ppvObject*<br/>
이 피연산이 완료되면 *riid* 매개 변수에 의해 지정된 인터페이스에 대한 포인터가 됩니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="runtimeclassrelease"></a><a name="release"></a>런타임 클래스::릴리스

현재 `RuntimeClass` 개체에서 COM 릴리스 작업을 수행합니다.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

참조 수가 0이 되면 `RuntimeClass` 개체가 삭제됩니다.

## <a name="runtimeclassruntimeclass"></a><a name="runtimeclass"></a>런타임 클래스::런타임클래스

클래스의 현재 인스턴스를 `RuntimeClass` 초기화합니다.

```cpp
RuntimeClass();
```
