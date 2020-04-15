---
title: Module 클래스
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module
- module/Microsoft::WRL::Module::Create
- module/Microsoft::WRL::Module::DecrementObjectCount
- module/Microsoft::WRL::Module::GetActivationFactory
- module/Microsoft::WRL::Module::GetClassObject
- module/Microsoft::WRL::Module::GetModule
- module/Microsoft::WRL::Module::GetObjectCount
- module/Microsoft::WRL::Module::IncrementObjectCount
- module/Microsoft::WRL::Module::Module
- module/Microsoft::WRL::Module::objectCount_Data
- module/Microsoft::WRL::Module::RegisterCOMObject
- module/Microsoft::WRL::Module::RegisterObjects
- module/Microsoft::WRL::Module::RegisterWinRTObject
- module/Microsoft::WRL::Module::releaseNotifier_
- module/Microsoft::WRL::Module::Terminate
- module/Microsoft::WRL::Module::~Module
- module/Microsoft::WRL::Module::UnregisterCOMObject
- module/Microsoft::WRL::Module::UnregisterObjects
- module/Microsoft::WRL::Module::UnregisterWinRTObject
helpviewer_keywords:
- Microsoft::WRL::Module class
- Microsoft::WRL::Module::Create method
- Microsoft::WRL::Module::DecrementObjectCount method
- Microsoft::WRL::Module::GetActivationFactory method
- Microsoft::WRL::Module::GetClassObject method
- Microsoft::WRL::Module::GetModule method
- Microsoft::WRL::Module::GetObjectCount method
- Microsoft::WRL::Module::IncrementObjectCount method
- Microsoft::WRL::Module::Module, constructor
- Microsoft::WRL::Module::objectCount_ data member
- Microsoft::WRL::Module::RegisterCOMObject method
- Microsoft::WRL::Module::RegisterObjects method
- Microsoft::WRL::Module::RegisterWinRTObject method
- Microsoft::WRL::Module::releaseNotifier_ data member
- Microsoft::WRL::Module::Terminate method
- Microsoft::WRL::Module::~Module, destructor
- Microsoft::WRL::Module::UnregisterCOMObject method
- Microsoft::WRL::Module::UnregisterObjects method
- Microsoft::WRL::Module::UnregisterWinRTObject method
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
ms.openlocfilehash: afd2edacefdf5d62b50a03c0a8c37f13ee5d9c9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371311"
---
# <a name="module-class"></a>Module 클래스

관련된 개체의 컬렉션을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template<ModuleType moduleType>
class Module;

template<>
class Module<InProc> : public Details::ModuleBase;

template<>
class Module<OutOfProc> : public Module<InProc>;
```

### <a name="parameters"></a>매개 변수

*모듈유형*<br/>
하나 이상의 [ModuleType](moduletype-enumeration.md) 열거 값의 조합입니다.

## <a name="members"></a>멤버

### <a name="protected-classes"></a>보호된 클래스

속성                                                                                | Description
----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------
[모듈::일반 릴리스](module-genericreleasenotifier-class.md) | 현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다. 이벤트 처리기는 람다, 함수 또는 함수 포인터에 의해 지정됩니다.
[모듈::방법 릴리스 공고](module-methodreleasenotifier-class.md)   | 현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다. 이벤트 처리기는 개체 및 해당 포인터-메서드 멤버에 의해 지정 됩니다.
[모듈::릴리스 노티피어](module-releasenotifier-class.md)               | 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다.

### <a name="public-constructors"></a>Public 생성자

속성                             | Description
-------------------------------- | -----------------------------------------------------------
[모듈 : ~ 모듈](#tilde-module) | 클래스의 현재 인스턴스를 초기화합니다. `Module`

### <a name="protected-constructors"></a>Protected 생성자

속성                      | Description
------------------------- | ---------------------------------------------------
[모듈 : 모듈 : 모듈](#module) | `Module` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                                                    | Description
------------------------------------------------------- | --------------------------------------------------------------------------------------------------
[모듈::만들기](#create)                               | 모듈의 인스턴스를 만듭니다.
[모듈::D개체수 계산](#decrementobjectcount)   | 모듈에서 추적하는 개체 수를 줄입니다.
[모듈 :: Get활성화공장](#getactivationfactory)   | 모듈에 대한 활성화 팩터리를 가져옵니다.
[모듈::GetClass개체](#getclassobject)               | 클래스 팩터리의 캐시를 검색합니다.
[모듈 :: GetModule](#getmodule)                         | 모듈의 인스턴스를 만듭니다.
[모듈:::GetObjectCount](#getobjectcount)               | 이 모듈에서 관리되는 개체 수를 가져옵니다.
[모듈::증분개체카운트](#incrementobjectcount)   | 모듈에서 추적하는 개체 수를 늘립니다.
[모듈::레지스터콤오브젝트](#registercomobject)         | 다른 애플리케이션이 COM 개체에 연결할 수 있도록 이 개체를 하나 이상 등록합니다.
[모듈::레지스터 개체](#registerobjects)             | 다른 응용 프로그램이 연결할 수 있도록 COM 또는 Windows 런타임 개체를 등록합니다.
[모듈::레지스터WinRT개체](#registerwinrtobject)     | 다른 응용 프로그램이 연결할 수 있도록 하나 이상의 Windows 런타임 개체를 등록합니다.
[모듈::종료](#terminate)                         | 모듈에 의해 인스턴스화되는 모든 팩터리가 종료됩니다.
[모듈::레지스터 해제COMObject](#unregistercomobject)     | 다른 애플리케이션에서 COM 개체에 연결할 수 없도록 하나 이상의 COM 개체의 등록을 취소합니다.
[모듈:::레지스터 해제개체](#unregisterobjects)         | 다른 애플리케이션에서 지정된 모듈의 개체에 연결할 수 없도록 이 개체의 등록을 취소합니다.
[모듈::레지스터 해제WinRT개체](#unregisterwinrtobject) | 다른 응용 프로그램이 연결할 수 없도록 하나 이상의 Windows 런타임 개체를 등록 취소합니다.

### <a name="protected-methods"></a>Protected 메서드

속성                      | Description
------------------------- | --------------------------------
[모듈::만들기](#create) | 모듈의 인스턴스를 만듭니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

속성                                         | Description
-------------------------------------------- | --------------------------------------------------------------------------------------------------------
[모듈::objectCount_](#objectcount)         | [Make](make-function.md) 함수를 통해 생성된 클래스 수를 추적합니다.
[모듈::releaseNotifier_](#releasenotifier) | 개체에 대한 `ReleaseNotifier` 포인터를 보유합니다.

### <a name="macros"></a>Macros

속성                                                                   | Description
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ActivatableClass](activatableclass-macros.md)              | 지정된 클래스의 인스턴스를 만들 수 있는 팩터리가 포함된 내부 캐시를 채웁니다. 이 매크로는 기본 팩터리 및 그룹 ID 매개 변수를 지정합니다.
[ActivatableClassWithFactory](activatableclass-macros.md)   | 지정된 클래스의 인스턴스를 만들 수 있는 팩터리가 포함된 내부 캐시를 채웁니다. 이 매크로를 사용하면 특정 팩터리 매개 변수를 지정할 수 있습니다.
[ActivatableClassWithFactoryEx](activatableclass-macros.md) | 지정된 클래스의 인스턴스를 만들 수 있는 팩터리가 포함된 내부 캐시를 채웁니다. 이 매크로를 사용하면 특정 팩터리 및 그룹 ID 매개 변수를 지정할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ModuleBase`

`Module`

`Module`

## <a name="requirements"></a>요구 사항

**헤더:** 모듈.h

**네임스페이스:** Microsoft::WRL

## <a name="modulemodule"></a><a name="tilde-module"></a>모듈 : ~ 모듈

클래스의 현재 인스턴스를 초기화합니다. `Module`

```cpp
virtual ~Module();
```

## <a name="modulecreate"></a><a name="create"></a>모듈::만들기

모듈의 인스턴스를 만듭니다.

```cpp
WRL_NOTHROW static Module& Create();
template<typename T>
WRL_NOTHROW static Module& Create(
   T callback
);
template<typename T>
WRL_NOTHROW static Module& Create(
   _In_ T* object,
   _In_ void (T::* method)()
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
모듈 유형입니다.

*콜백(callback)*<br/>
모듈의 마지막 인스턴스 개체가 해제될 때 호출됩니다.

*개체*<br/>
*개체* 및 *메서드* 매개 변수를 조합하여 사용됩니다. 모듈의 마지막 인스턴스 개체가 해제될 때 마지막 인스턴스 개체를 가리킵니다.

*메서드*<br/>
*개체* 및 *메서드* 매개 변수를 조합하여 사용됩니다. 모듈의 마지막 인스턴스 개체가 해제될 때 마지막 인스턴스 개체의 메서드를 가리킵니다.

### <a name="return-value"></a>Return Value

모듈을 참조하십시오.

## <a name="moduledecrementobjectcount"></a><a name="decrementobjectcount"></a>모듈::D개체수 계산

모듈에서 추적하는 개체 수를 줄입니다.

```cpp
virtual long DecrementObjectCount();
```

### <a name="return-value"></a>Return Value

감소 작업 전 수입니다.

## <a name="modulegetactivationfactory"></a><a name="getactivationfactory"></a>모듈 :: Get활성화공장

모듈에 대한 활성화 팩터리를 가져옵니다.

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>매개 변수

*aactivatibleClassId*<br/>
런타임 클래스의 IID입니다.

*ppIFactory*<br/>
지정된 런타임 클래스에 대한 IActivationFactory입니다.

*Servername*<br/>
현재 모듈의 클래스 팩터리 하위 집합 이름입니다. [ActivatableClassFactoryEx](activatableclass-macros.md) 매크로에 사용되는 서버 이름을 지정하거나 `nullptr` 기본 서버 이름을 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 GetActivationFactory에서 반환된 HRESULT입니다.

## <a name="modulegetclassobject"></a><a name="getclassobject"></a>모듈::GetClass개체

클래스 팩터리의 캐시를 가져옵니다.

```cpp
HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
클래스 ID입니다.

*riid*<br/>
요청하는 인터페이스 ID입니다.

*ppv*<br/>
반환된 개체에 대한 포인터입니다.

*Servername*<br/>
`ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx` 또는 `ActivatableClass` 매크로에 지정된 서버 이름 또는 기본 서버 이름을 가져오는 `nullptr`입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

이 메서드는 Windows 런타임이 아닌 COM에만 사용합니다. 이 메서드는 `IClassFactory` 메서드만 노출합니다.

## <a name="modulegetmodule"></a><a name="getmodule"></a>모듈 :: GetModule

모듈의 인스턴스를 만듭니다.

```cpp
static Module& GetModule();
WRL_NOTHROW static Module& GetModule();
```

### <a name="return-value"></a>Return Value

모듈에 대한 참조입니다.

## <a name="modulegetobjectcount"></a><a name="getobjectcount"></a>모듈:::GetObjectCount

이 모듈에서 관리되는 개체 수를 가져옵니다.

```cpp
virtual long GetObjectCount() const;
```

### <a name="return-value"></a>Return Value

이 모듈에서 관리되는 현재 개체 수입니다.

## <a name="moduleincrementobjectcount"></a><a name="incrementobjectcount"></a>모듈::증분개체카운트

모듈에서 추적하는 개체 수를 늘립니다.

```cpp
virtual long IncrementObjectCount();
```

### <a name="return-value"></a>Return Value

증가 연산 전 수입니다.

## <a name="modulemodule"></a><a name="module"></a>모듈 : 모듈 : 모듈

`Module` 클래스의 새 인스턴스를 초기화합니다.

```cpp
Module();
```

### <a name="remarks"></a>설명

이 생성자가 보호되고 `new` 키워드로 호출할 수 없습니다. 대신 [모듈::GetModule](#getmodule) 또는 [모듈::만들기](#create)중 하나를 호출합니다.

## <a name="moduleobjectcount_"></a><a name="objectcount"></a>모듈::objectCount_

[Make](make-function.md) 함수를 통해 생성된 클래스 수를 추적합니다.

```cpp
volatile long objectCount_;
```

## <a name="moduleregistercomobject"></a><a name="registercomobject"></a>모듈::레지스터콤오브젝트

다른 애플리케이션이 COM 개체에 연결할 수 있도록 이 개체를 하나 이상 등록합니다.

```cpp
WRL_NOTHROW virtual HRESULT RegisterCOMObject(
   const wchar_t* serverName,
   IID* clsids,
   IClassFactory** factories,
   DWORD* cookies,
   unsigned int count);
```

### <a name="parameters"></a>매개 변수

*Servername*<br/>
서버의 정규화된 이름입니다.

*Clsid*<br/>
등록할 CLSID의 배열입니다.

*factories*<br/>
가용성을 게시하고 있는 클래스 개체의 IUnknown 인터페이스 배열입니다.

*쿠키*<br/>
작업이 완료되면 등록된 클래스 개체를 식별하는 값에 대한 포인터 배열입니다. 이러한 값은 나중에 등록을 해지하는 데 사용됩니다.

*count*<br/>
등록할 CLSID 수입니다.

### <a name="return-value"></a>Return Value

성공할 경우 S_OK이고, 그렇지 않으면 작업에 실패한 이유를 나타내는 CO_E_OBJISREG와 같은 HRESULT가 발생합니다.

### <a name="remarks"></a>설명

COM 개체는 CLSCTX 열거형의 CLSCTX_LOCAL_SERVER 열거자를 사용하여 등록됩니다.

등록된 개체에 대한 연결 유형은 현재 *comflag* 템플릿 매개 변수와 REGCLS 열거REGCLS_SUSPENDED 열거자의 조합으로 지정됩니다.

## <a name="moduleregisterobjects"></a><a name="registerobjects"></a>모듈::레지스터 개체

다른 응용 프로그램이 연결할 수 있도록 COM 또는 Windows 런타임 개체를 등록합니다.

```cpp
HRESULT RegisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>매개 변수

*모듈*<br/>
COM 또는 Windows 런타임 개체의 배열입니다.

*Servername*<br/>
개체를 생성한 서버의 이름입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK이고, 그렇지 않으면 작업이 실패한 이유를 나타내는 HRESULT입니다.

## <a name="moduleregisterwinrtobject"></a><a name="registerwinrtobject"></a>모듈::레지스터WinRT개체

다른 응용 프로그램이 연결할 수 있도록 하나 이상의 Windows 런타임 개체를 등록합니다.

```cpp
HRESULT RegisterWinRTObject(const wchar_t* serverName,
   wchar_t** activatableClassIds,
   WINRT_REGISTRATION_COOKIE* cookie,
   unsigned int count)
```

### <a name="parameters"></a>매개 변수

*Servername*<br/>
이 작업으로 영향을 받는 개체의 하위 집합을 지정하는 이름입니다.

*활성 클래스Id*<br/>
등록할 활성화 가능한 CLSID 배열입니다.

*쿠키*<br/>
등록된 클래스 개체를 식별하는 값입니다. 이 값은 나중에 등록을 해지할 때 사용됩니다.

*count*<br/>
등록할 개체의 수입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고 그렇지 않으면 작업에 실패한 이유를 나타내는 CO_E_OBJISREG와 같은 HRESULT 오류가 발생합니다.

## <a name="modulereleasenotifier_"></a><a name="releasenotifier"></a>모듈::releaseNotifier_

개체에 대한 `ReleaseNotifier` 포인터를 보유합니다.

```cpp
ReleaseNotifier *releaseNotifier_;
```

## <a name="moduleterminate"></a><a name="terminate"></a>모듈::종료

모듈에 의해 인스턴스화되는 모든 팩터리가 종료됩니다.

```cpp
void Terminate();
```

### <a name="remarks"></a>설명

캐시에서 팩터리를 해제합니다.

## <a name="moduleunregistercomobject"></a><a name="unregistercomobject"></a>모듈::레지스터 해제COMObject

다른 애플리케이션에서 COM 개체에 연결할 수 없도록 하나 이상의 COM 개체의 등록을 취소합니다.

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>매개 변수

*Servername*<br/>
(사용되지 않음)

*쿠키*<br/>
등록 취소한 클래스 개체를 식별하는 값에 대한 포인터 배열입니다. 배열은 [RegisterCOMObject](#registercomobject) 메서드에 의해 만들어졌습니다.

*count*<br/>
등록 취소할 클래스 수입니다.

### <a name="return-value"></a>Return Value

이 작업에 성공하면 S_OK이고, 그렇지 않으면 작업에 실패한 이유를 나타내는 HRESULT 오류가 발생합니다.

## <a name="moduleunregisterobjects"></a><a name="unregisterobjects"></a>모듈:::레지스터 해제개체

다른 애플리케이션에서 지정된 모듈의 개체에 연결할 수 없도록 이 개체의 등록을 취소합니다.

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>매개 변수

*모듈*<br/>
모듈에 대한 포인터입니다.

*Servername*<br/>
이 작업으로 영향을 받는 개체의 하위 집합을 지정하는 정규화 이름입니다.

### <a name="return-value"></a>Return Value

이 작업에 성공하면 S_OK이고, 그렇지 않으면 이 작업에 실패한 이유를 나타내는 HRESULT 오류가 발생합니다.

## <a name="moduleunregisterwinrtobject"></a><a name="unregisterwinrtobject"></a>모듈::레지스터 해제WinRT개체

다른 응용 프로그램이 연결할 수 없도록 하나 이상의 Windows 런타임 개체를 등록 취소합니다.

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>매개 변수

*쿠키*<br/>
등록이 해지된 클래스 개체를 식별하는 값에 대한 포인터입니다.
