---
title: WeakRef 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
- client/Microsoft::WRL::WeakRef::~WeakRef
- client/Microsoft::WRL::WeakRef::As
- client/Microsoft::WRL::WeakRef::AsIID
- client/Microsoft::WRL::WeakRef::CopyTo
- client/Microsoft::WRL::WeakRef::operator&
- client/Microsoft::WRL::WeakRef::WeakRef
helpviewer_keywords:
- Microsoft::WRL::WeakRef class
- Microsoft::WRL::WeakRef::~WeakRef, destructor
- Microsoft::WRL::WeakRef::As method
- Microsoft::WRL::WeakRef::AsIID method
- Microsoft::WRL::WeakRef::CopyTo method
- Microsoft::WRL::WeakRef::operator& operator
- Microsoft::WRL::WeakRef::WeakRef, constructor
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
ms.openlocfilehash: 681f5a64c3e2902c66facbd4f0ac3a3663a7e79d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374251"
---
# <a name="weakref-class"></a>WeakRef 클래스

클래식 COM이 아닌 Windows 런타임에서만 사용할 수 있는 *약한 참조* 를 나타냅니다. 약한 참조는 액세스할 수 있거나 액세스할 수 없는 개체를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class WeakRef : public ComPtr<IWeakReference>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[WeakRef::WeakRef 생성자](#weakref)|`WeakRef` 클래스의 새 인스턴스를 초기화합니다.|
|[WeakRef::~WeakRef 소멸자](#tilde-weakref)|클래스의 현재 인스턴스를 초기화합니다. `WeakRef`|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[WeakRef::As 메서드](#as)|지정된 인터페이스를 나타내도록 지정된 `ComPtr` 포인터 매개 변수를 설정합니다.|
|[WeakRef::AsIID 메서드](#asiid)|지정된 `ComPtr` 인터페이스 ID를 나타내도록 지정된 포인터 매개 변수를 설정합니다.|
|[WeakRef::CopyTo 메서드](#copyto)|사용 가능한 경우 지정된 포인터 변수에 인터페이스에 대한 포인터를 할당합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[WeakRef::operator& 연산자](#operator-ampersand-operator)|현재 `WeakRef` `ComPtrRef` 개체를 나타내는 개체를 반환합니다.|

## <a name="remarks"></a>설명

개체는 `WeakRef` 개체와 연결되고 유효하거나 유효하지 않을 수 있는 *강력한 참조를*유지 관리합니다. 강력한 `As()` 참조를 얻으려면 또는 `AsIID()` 메서드를 호출합니다. 강력한 참조가 유효한 경우 연결된 개체에 액세스할 수 있습니다. 강력한 참조가 올바르지 않은 경우(`nullptr`) 연결된 개체에 액세스할 수 없습니다.

`WeakRef` 개체는 일반적으로 외부 스레드 또는 응용 프로그램에 의해 존재가 제어되는 개체를 나타내는 데 사용됩니다. 예를 들어 참조에서 `WeakRef` 파일 개체로 개체를 생성합니다. 파일이 열려 있는 동안 강력한 참조는 유효합니다. 그러나 파일이 닫히면 강력한 참조는 유효하지 않게 됩니다.

Windows 10 SDK에서는 [As](#as), [AsIID](#asiid) 및 [CopyTo](#copyto) 메서드의 동작 변경이 있습니다. 이전에는 다음 코드에서와 같이 이러한 `WeakRef` 메서드를 호출한 후 를 `nullptr` 확인하여 강력한 참조가 성공적으로 수행되었는지 확인할 수 있습니다.

```cpp
WeakRef wr;
strongComptrRef.AsWeak(&wr);

// Now suppose that the object strongComPtrRef points to no longer exists
// and the following code tries to get a strong ref from the weak ref:
ComPtr<ISomeInterface> strongRef;
HRESULT hr = wr.As(&strongRef);

// This check won't work with the Windows 10 SDK version of the library.
// Check the input pointer instead.
if(wr == nullptr)
{
    wprintf(L"Couldn’t get strong ref!");
}
```

위의 코드는 Windows 10 SDK(이상)를 사용하는 경우 작동하지 않습니다. 대신 에 전달된 포인터를 `nullptr`확인합니다.

```cpp
if (strongRef == nullptr)
{
    wprintf(L"Couldn't get strong ref!");
}
```

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ComPtr`

`WeakRef`

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**네임스페이스:** Microsoft::WRL

## <a name="weakrefweakref-destructor"></a><a name="tilde-weakref"></a>약점 ::~약자 레프 소멸자

클래스의 현재 인스턴스를 초기화합니다. `WeakRef`

```cpp
~WeakRef();
```

## <a name="weakrefas-method"></a><a name="as"></a>약점 ::방법으로

지정된 인터페이스를 나타내도록 지정된 `ComPtr` 포인터 매개 변수를 설정합니다.

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* ptr
);

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr
);
```

### <a name="parameters"></a>매개 변수

*U*<br/>
인터페이스 ID입니다.

*Ptr*<br/>
이 작업이 완료되면 매개 변수 *U를*나타내는 개체입니다.

### <a name="return-value"></a>Return Value

- 이 작업이 성공하면 S_OK. 그렇지 않으면 작업이 실패한 이유를 나타내는 HRESULT와 *ptr이* 로 `nullptr`설정됩니다.

- 이 작업이 성공하지만 현재 `WeakRef` 개체가 이미 릴리스된 경우 S_OK. 매개 변수 *PTR이* `nullptr`로 설정됩니다.

- 이 작업이 성공하지만 현재 `WeakRef` 개체가 매개 변수 *U에서*파생되지 않은 경우 S_OK. 매개 변수 *PTR이* `nullptr`로 설정됩니다.

### <a name="remarks"></a>설명

매개 변수 *U가* `IWeakReference`에서 파생되지 않았거나 파생되지 `IInspectable`않은 경우 오류가 내보루게 됩니다.

첫 번째 템플릿은 코드에서 사용해야 하는 폼입니다. 두 번째 템플릿은 [자동](../../cpp/auto-cpp.md) 형식 추론 키워드와 같은 C++ 언어 기능을 지원하는 내부 도우미 특수화입니다.

Windows 10 SDK에서 시작하여 이 메서드는 `WeakRef` 약한 `nullptr` 참조를 가져올 수 없는 경우 인스턴스를 설정하지 않으므로 에 `WeakRef` `nullptr`대해 확인하는 오류 검사 코드를 피해야 합니다. 대신 *ptr을* `nullptr`확인합니다.

## <a name="weakrefasiid-method"></a><a name="asiid"></a>약점 ::AsIID 방법

지정된 `ComPtr` 인터페이스 ID를 나타내도록 지정된 포인터 매개 변수를 설정합니다.

```cpp
HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IInspectable>* ptr
);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*Ptr*<br/>
이 작업이 완료되면 매개 변수 *riid를*나타내는 개체가 있습니다.

### <a name="return-value"></a>Return Value

- 이 작업이 성공하면 S_OK. 그렇지 않으면 작업이 실패한 이유를 나타내는 HRESULT와 *ptr이* 로 `nullptr`설정됩니다.

- 이 작업이 성공하지만 현재 `WeakRef` 개체가 이미 릴리스된 경우 S_OK. 매개 변수 *PTR이* `nullptr`로 설정됩니다.

- 이 작업이 성공하지만 현재 `WeakRef` 개체가 매개 변수 *riid에서*파생되지 않는 S_OK. 매개 변수 *PTR이* `nullptr`로 설정됩니다. 자세한 내용은 설명 부분을 참조하세요.

### <a name="remarks"></a>설명

매개 변수 *riid에서* 파생되지 않은 경우 `IInspectable`오류가 내보내드립니다. 이 오류는 반환 값을 대체합니다.

첫 번째 템플릿은 코드에서 사용해야 하는 폼입니다. 두 번째 템플릿(여기에 표시되지 않지만 헤더 파일에서 선언됨)은 [자동](../../cpp/auto-cpp.md) 형식 추론 키워드와 같은 C++ 언어 기능을 지원하는 내부 도우미 특수화입니다.

Windows 10 SDK에서 시작하여 이 메서드는 `WeakRef` 약한 `nullptr` 참조를 가져올 수 없는 경우 인스턴스를 설정하지 않으므로 에 `WeakRef` `nullptr`대해 확인하는 오류 검사 코드를 피해야 합니다. 대신 *ptr을* `nullptr`확인합니다.

## <a name="weakrefcopyto-method"></a><a name="copyto"></a>약점::카피토 방법

사용 가능한 경우 지정된 포인터 변수에 인터페이스에 대한 포인터를 할당합니다.

```cpp
HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ IInspectable** ptr
);

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
);

HRESULT CopyTo(
   _Deref_out_ IWeakReference** ptr
);
```

### <a name="parameters"></a>매개 변수

*U*<br/>
인터페이스를 `IInspectable` 포인터로 합니다. *U에서 U가* 파생되지 않으면 오류가 `IInspectable`내보내드립니다.

*riid*<br/>
인터페이스 ID입니다. *id에서 파생되지* 않은 경우 오류가 `IWeakReference`내보내드립니다.

*Ptr*<br/>
또는 `IInspectable` `IWeakReference`에 대한 이중 간접 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다. 자세한 내용은 **비고를**참조하십시오.

### <a name="remarks"></a>설명

반환 값 S_OK는 이 작업이 성공했음을 의미하지만 약한 참조가 강한 참조로 확인되었는지를 나타내지 않습니다. S_OK 반환되는 경우 해당 매개 변수 *p가* 강력한 참조인 지테스트합니다. 즉, 매개 변수 *p는* `nullptr`와 같지 않습니다.

Windows 10 SDK에서 시작하여 이 메서드는 `WeakRef` 약한 `nullptr` 참조를 가져올 수 없는 경우 인스턴스를 설정하지 않으므로 `WeakRef` 에 `nullptr`대한 검사를 확인하는 오류를 피해야 합니다. 대신 *ptr을* `nullptr`확인합니다.

## <a name="weakrefoperatoramp-operator"></a><a name="operator-ampersand-operator"></a>WeakRef::연산자&amp;

현재 `WeakRef` `ComPtrRef` 개체를 나타내는 개체를 반환합니다.

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()
```

### <a name="return-value"></a>Return Value

현재 `ComPtrRef` `WeakRef` 개체를 나타내는 개체입니다.

### <a name="remarks"></a>설명

이 연산자는 코드에서 사용할 수 없는 내부 도우미 연산자입니다.

## <a name="weakrefweakref-constructor"></a><a name="weakref"></a>약점::약한 참조 생성자

`WeakRef` 클래스의 새 인스턴스를 초기화합니다.

```cpp
WeakRef();
WeakRef(
   decltype(__nullptr)
);

WeakRef(
   _In_opt_ IWeakReference* ptr
);

WeakRef(
   const ComPtr<IWeakReference>& ptr
);

WeakRef(
   const WeakRef& ptr
);

WeakRef(
   _Inout_ WeakRef&& ptr
);
```

### <a name="parameters"></a>매개 변수

*Ptr*<br/>
현재 `WeakRef` 개체를 초기화하는 기존 개체에 대한 포인터, 참조 또는 rvalue 참조입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 빈 `WeakRef` 개체를 초기화합니다. 두 번째 생성자는 포인터에서 `WeakRef` `IWeakReference` 인터페이스로 개체를 초기화합니다. 세 번째 생성자는 참조에서 개체에 `WeakRef` 대한 `ComPtr<IWeakReference>` 개체를 초기화합니다. 네 번째 및 다섯 번째 생성자는 `WeakRef` 다른 `WeakRef` 개체에서 개체를 초기화합니다.
