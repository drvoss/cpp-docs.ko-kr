---
title: ComPtr 클래스
ms.date: 07/26/2019
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
- client/Microsoft::WRL::ComPtr::As
- client/Microsoft::WRL::ComPtr::AsIID
- client/Microsoft::WRL::ComPtr::AsWeak
- client/Microsoft::WRL::ComPtr::Attach
- client/Microsoft::WRL::ComPtr::ComPtr
- client/Microsoft::WRL::ComPtr::CopyTo
- client/Microsoft::WRL::ComPtr::Detach
- client/Microsoft::WRL::ComPtr::Get
- client/Microsoft::WRL::ComPtr::GetAddressOf
- client/Microsoft::WRL::ComPtr::InternalAddRef
- client/Microsoft::WRL::ComPtr::InternalRelease
- client/Microsoft::WRL::ComPtr::operator&
- client/Microsoft::WRL::ComPtr::operator->
- client/Microsoft::WRL::ComPtr::operator=
- client/Microsoft::WRL::ComPtr::operator==
- client/Microsoft::WRL::ComPtr::operator!=
- client/Microsoft::WRL::ComPtr::operator Microsoft::WRL::Details::BoolType
- client/Microsoft::WRL::ComPtr::ptr_
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
- client/Microsoft::WRL::ComPtr::Reset
- client/Microsoft::WRL::ComPtr::Swap
- client/Microsoft::WRL::ComPtr::~ComPtr
helpviewer_keywords:
- Microsoft::WRL::ComPtr class
- Microsoft::WRL::ComPtr::As method
- Microsoft::WRL::ComPtr::AsIID method
- Microsoft::WRL::ComPtr::AsWeak method
- Microsoft::WRL::ComPtr::Attach method
- Microsoft::WRL::ComPtr::ComPtr, constructor
- Microsoft::WRL::ComPtr::CopyTo method
- Microsoft::WRL::ComPtr::Detach method
- Microsoft::WRL::ComPtr::Get method
- Microsoft::WRL::ComPtr::GetAddressOf method
- Microsoft::WRL::ComPtr::InternalAddRef method
- Microsoft::WRL::ComPtr::InternalRelease method
- Microsoft::WRL::ComPtr::operator& operator
- Microsoft::WRL::ComPtr::operator-> operator
- Microsoft::WRL::ComPtr::operator= operator
- Microsoft::WRL::ComPtr::operator== operator
- Microsoft::WRL::ComPtr::operator!= operator
- Microsoft::WRL::ComPtr::operator Microsoft::WRL::Details::BoolType operator
- Microsoft::WRL::ComPtr::ptr_ data member
- Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf method
- Microsoft::WRL::ComPtr::Reset method
- Microsoft::WRL::ComPtr::Swap method
- Microsoft::WRL::ComPtr::~ComPtr, destructor
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
ms.openlocfilehash: 89c09ede972f5bdd5da1dde810cad31733bdf338
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372648"
---
# <a name="comptr-class"></a>ComPtr 클래스

템플릿 매개 변수로 지정된 인터페이스를 나타내는 *스마트 포인터* 형식을 만듭니다. `ComPtr`은 기본 인터페이스 포인터의 참조 개수를 자동으로 관리하여 참조 횟수가 0이 되면 인터페이스를 릴리스합니다.

## <a name="syntax"></a>구문

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
나타내는 인터페이스입니다. `ComPtr`

*U*<br/>
현재가 `ComPtr` 친구인 클래스입니다. 이 매개 변수를 사용하는 템플릿은 보호됩니다.

## <a name="remarks"></a>설명

`ComPtr<>`기본 인터페이스 포인터를 나타내는 형식을 선언합니다. `ComPtr<>` 변수를 선언한 다음 화살표 멤버 액세스 연산자 ()를`->`사용하여 인터페이스 멤버 함수에 액세스합니다.

스마트 포인터에 대한 자세한 내용은 MSDN 라이브러리의 COM [코딩 사례](/windows/win32/LearnWin32/com-coding-practices) 항목의 "COM 스마트 포인터" 하위 섹션을 참조하십시오.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성            | Description
--------------- | ---------------------------------------------------------------
`InterfaceType` | *T* 템플릿 매개 변수에 의해 지정된 형식의 동의어입니다.

### <a name="public-constructors"></a>Public 생성자

속성                             | Description
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[컴프트::컴프트](#comptr)        | `ComPtr` 클래스의 새 인스턴스를 초기화합니다. 오버로드는 기본, 복사, 이동 및 변환 생성자를 제공합니다.
[컴프트::~컴프트](#tilde-comptr) | 의 `ComPtr`인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                                                      | Description
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[컴프트::As](#as)                                         | 지정된 `ComPtr` 템플릿 매개 변수로 식별된 인터페이스를 나타내는 개체를 반환합니다.
[컴프트:::아시이드](#asiid)                                   | 지정된 `ComPtr` 인터페이스 ID로 식별된 인터페이스를 나타내는 개체를 반환합니다.
[컴프트::로약한](#asweak)                                 | 현재 개체에 대한 약한 참조를 검색합니다.
[컴프트::연결](#attach)                                 | 이를 `ComPtr` 현재 템플릿 형식 매개 변수에 의해 지정된 인터페이스 유형과 연결합니다.
[컴프트::카피토](#copyto)                                 | 이와 `ComPtr` 연관된 현재 또는 지정된 인터페이스를 지정된 출력 포인터에 복사합니다.
[컴프트::D에타치](#detach)                                 | 이를 `ComPtr` 나타내는 인터페이스에서 분리합니다.
[컴프트::Get](#get)                                       | 이와 `ComPtr`연결된 인터페이스에 대한 포인터를 검색합니다.
[컴프트::겟주소](#getaddressof)                     | [ptr_](#ptr) 데이터 멤버의 주소를 검색합니다. `ComPtr`
[컴프트::릴리스앤겟주소](#releaseandgetaddressof) | 이와 `ComPtr` 연관된 인터페이스를 해제한 다음 [릴리스된](#ptr) 인터페이스에 대한 포인터를 포함하는 ptr_ 데이터 멤버의 주소를 검색합니다.
[ComPtr::Reset](#reset)                                   | 이와 `ComPtr`연결된 인터페이스에 대한 포인터에 대한 모든 참조를 해제합니다.
[컴프트::스왑](#swap)                                     | 현재에서 `ComPtr` 관리하는 인터페이스를 지정된 `ComPtr`에서 관리하는 인터페이스로 교환합니다.

### <a name="protected-methods"></a>Protected 메서드

속성                                        | Description
------------------------------------------- | --------------------------------------------------------------------------------
[컴프트::내부애드레프](#internaladdref)   | 이와 `ComPtr`연결된 인터페이스의 참조 수를 증가시요.
[컴프트::내부 릴리스](#internalrelease) | 이와 `ComPtr`연결된 인터페이스에서 COM 릴리스 작업을 수행합니다.

### <a name="public-operators"></a>Public 연산자

속성                                                                                           | Description
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[컴프트:운영자&](#operator-ampersand)                                                       | 현재 `ComPtr`의 주소를 검색합니다.
[컴프트::연산자 >](#operator-arrow)                                                          | 현재 템플릿 매개 변수에 지정된 형식에 대한 포인터를 검색합니다.
[컴프트::연산자=](#operator-assign)                                                          | 현재 `ComPtr`에 값을 할당합니다.
[컴프트::연산자==](#operator-equality)                                                       | 두 `ComPtr` 개체가 같은지를 나타냅니다.
[컴프트::연산자!=](#operator-inequality)                                                     | 두 `ComPtr` 개체가 같지 않은지를 나타냅니다.
[컴프트::연산자 마이크로 소프트::WRL::D테일::BoolType](#operator-microsoft-wrl-details-booltype) | a가 `ComPtr` 인터페이스의 개체 수명을 관리하고 있는지 여부를 나타냅니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

속성                 | Description
-------------------- | ------------------------------------------------------------------------------------------
[컴프트::p트르_](#ptr) | 이에 `ComPtr`의해 연결되고 관리되는 인터페이스에 대한 포인터가 포함되어 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ComPtr`

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**네임스페이스:** Microsoft::WRL

## <a name="comptrcomptr"></a><a name="tilde-comptr"></a>컴프트::~컴프트

의 `ComPtr`인스턴스를 초기화합니다.

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="comptras"></a><a name="as"></a>컴프트::As

지정된 `ComPtr` 템플릿 매개 변수로 식별된 인터페이스를 나타내는 개체를 반환합니다.

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* p
) const;

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> p
) const;
```

### <a name="parameters"></a>매개 변수

*U*<br/>
매개 변수 *p로*나타낼 인터페이스.

*P*<br/>
매개 `ComPtr` 변수 *U로*지정된 인터페이스를 나타내는 개체입니다. 매개 변수 *p는* 현재 `ComPtr` 개체를 참조해서는 안 됩니다.

### <a name="remarks"></a>설명

첫 번째 템플릿은 코드에서 사용해야 하는 폼입니다. 두 번째 템플릿은 [자동](../../cpp/auto-cpp.md) 형식 추론 키워드와 같은 C++ 언어 기능을 지원하는 내부 도우미 특수화입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="comptrasiid"></a><a name="asiid"></a>컴프트:::아시이드

지정된 `ComPtr` 인터페이스 ID로 식별된 인터페이스를 나타내는 개체를 반환합니다.

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*P*<br/>
개체에 ID가 *riid와*같은 인터페이스가 있는 경우 *riid* 매개 변수에 의해 지정된 인터페이스에 대한 이중 간접 포인터입니다. 그렇지 않으면 에 `IUnknown`대한 포인터가 있습니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="comptrasweak"></a><a name="asweak"></a>컴프트::로약한

현재 개체에 대한 약한 참조를 검색합니다.

```cpp
HRESULT AsWeak(
   _Out_ WeakRef* pWeakRef
);
```

### <a name="parameters"></a>매개 변수

*pweakRef*<br/>
이 작업이 완료되면 약한 참조 개체에 대한 포인터가 됩니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="comptrattach"></a><a name="attach"></a>컴프트::연결

이를 `ComPtr` 현재 템플릿 형식 매개 변수에 의해 지정된 인터페이스 유형과 연결합니다.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>매개 변수

*다른*<br/>
인터페이스 유형입니다.

## <a name="comptrcomptr"></a><a name="comptr"></a>컴프트::컴프트

`ComPtr` 클래스의 새 인스턴스를 초기화합니다. 오버로드는 기본, 복사, 이동 및 변환 생성자를 제공합니다.

```cpp
WRL_NOTHROW ComPtr();

WRL_NOTHROW ComPtr(
   decltype(__nullptr)
);

template<class U>
WRL_NOTHROW ComPtr(
   _In_opt_ U *other
);

WRL_NOTHROW ComPtr(
   const ComPtr& other
);

template<class U>
WRL_NOTHROW ComPtr(
   const ComPtr<U> &other,
   typename ENABLE_IF<__is_convertible_to(U*, T*), void *>
);

WRL_NOTHROW ComPtr(
   _Inout_ ComPtr &&other
);

template<class U>
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr<U>&& other, typename ENABLE_IF<__is_convertible_to(U*, T*), void *>
);
```

### <a name="parameters"></a>매개 변수

*U*<br/>
*다른* 매개 변수의 형식입니다.

*다른*<br/>
*U*형식의 개체입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

첫 번째 생성자는 빈 개체를 만드는 기본 생성자입니다. 두 번째 생성자는 [__nullptr](../../extensions/nullptr-cpp-component-extensions.md)__nullptr 지정하여 빈 개체를 명시적으로 만듭니다.

세 번째 생성자는 포인터에 의해 지정된 개체에서 개체를 만듭니다. ComPtr은 이제 뾰족한 메모리를 소유하고 참조 수를 유지합니다.

네 번째 및 다섯 번째 생성자는 복사 생성자입니다. 다섯 번째 생성자는 현재 유형으로 변환할 수 있는 경우 개체를 복사합니다.

여섯 번째 와 일곱 번째 생성자는 이동 생성자입니다. 일곱 번째 생성자는 현재 유형으로 변환할 수 있는 경우 개체를 이동합니다.

## <a name="comptrcopyto"></a><a name="copyto"></a>컴프트::카피토

이와 `ComPtr` 연관된 현재 또는 지정된 인터페이스를 지정된 포인터에 복사합니다.

```cpp
HRESULT CopyTo(
   _Deref_out_ InterfaceType** ptr
);

HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ void** ptr
) const;

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
) const;
```

### <a name="parameters"></a>매개 변수

*U*<br/>
형식 이름.

*Ptr*<br/>
이 작업이 완료되면 요청된 인터페이스에 대한 포인터가 됩니다.

*riid*<br/>
인터페이스 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 암시적 `QueryInterface` 작업이 실패한 이유를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

첫 번째 함수는 포인터의 복사본을 이와 `ComPtr`연결된 인터페이스에 반환합니다. 이 함수는 항상 S_OK 반환합니다.

두 번째 함수는 *riid* 매개 `ComPtr` 변수에 의해 지정된 인터페이스에 대해 이와 연결된 인터페이스에서 `QueryInterface` 작업을 수행합니다.

세 번째 함수는 `QueryInterface` *U* 매개 변수의 기본 인터페이스에 대해 이와 `ComPtr` 관련된 인터페이스에서 작업을 수행합니다.

## <a name="comptrdetach"></a><a name="detach"></a>컴프트::D에타치

이 개체가 `ComPtr` 나타내는 인터페이스에서 이 개체를 분리합니다.

```cpp
T* Detach();
```

### <a name="return-value"></a>Return Value

이 `ComPtr` 개체로 표시된 인터페이스에 대한 포인터입니다.

## <a name="comptrget"></a><a name="get"></a>컴프트::Get

이와 `ComPtr`연결된 인터페이스에 대한 포인터를 검색합니다.

```cpp
T* Get() const;
```

### <a name="return-value"></a>Return Value

이와 `ComPtr`연결된 인터페이스에 대한 포인터 .

## <a name="comptrgetaddressof"></a><a name="getaddressof"></a>컴프트::겟주소

[ptr_](#ptr) 데이터 멤버의 주소를 검색합니다. `ComPtr`

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>Return Value

변수의 주소입니다.

## <a name="comptrinternaladdref"></a><a name="internaladdref"></a>컴프트::내부애드레프

이와 `ComPtr`연결된 인터페이스의 참조 수를 증가시요.

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>설명

이 메서드는 보호 됩니다.

## <a name="comptrinternalrelease"></a><a name="internalrelease"></a>컴프트::내부 릴리스

이와 `ComPtr`연결된 인터페이스에서 COM 릴리스 작업을 수행합니다.

```cpp
void InternalRelease();
```

### <a name="remarks"></a>설명

이 메서드는 보호 됩니다.

## <a name="comptroperatoramp"></a><a name="operator-ampersand"></a>컴프트::연산자&amp;

이 `ComPtr` 개체와 연결된 인터페이스를 해제한 다음 `ComPtr` 개체의 주소를 검색합니다.

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>Return Value

현재에 `ComPtr`대한 약한 참조 .

### <a name="remarks"></a>설명

이 메서드는 [ComPtr::GetAddressOf](#getaddressof) 이 메서드는 인터페이스 포인터에 대 한 참조를 해제 합니다. 인터페이스 `ComPtr::GetAddressOf` 포인터의 주소가 필요하지만 해당 인터페이스를 해제하지 않으려는 경우에 사용합니다.

## <a name="comptroperator-gt"></a><a name="operator-arrow"></a>컴프트::연산자-&gt;

현재 템플릿 매개 변수에 지정된 형식에 대한 포인터를 검색합니다.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>Return Value

현재 템플릿 유형 이름으로 지정된 형식에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 도우미 함수는 STDMETHOD 매크로를 사용하여 발생하는 불필요한 오버헤드를 제거합니다. 이 `IUnknown` 함수는 `private` `virtual`.

## <a name="comptroperator"></a><a name="operator-assign"></a>컴프트::연산자=

현재 `ComPtr`에 값을 할당합니다.

```cpp
WRL_NOTHROW ComPtr& operator=(
   decltype(__nullptr)
);
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ T *other
);
template <typename U>
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ U *other
);
WRL_NOTHROW ComPtr& operator=(
   const ComPtr &other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   const ComPtr<U>& other
);
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr<U>&& other
);
```

### <a name="parameters"></a>매개 변수

*U*<br/>
클래스입니다.

*다른*<br/>
형식 또는 다른 `ComPtr`에 대한 포인터, 참조 또는 rvalue 참조입니다.

### <a name="return-value"></a>Return Value

현재 `ComPtr`에 대한 참조입니다.

### <a name="remarks"></a>설명

이 연산자의 첫 번째 버전은 현재 `ComPtr`에 빈 값을 할당합니다.

두 번째 버전에서는 할당 인터페이스 포인터가 현재 `ComPtr` 인터페이스 포인터와 같지 않으면 두 번째 인터페이스 `ComPtr`포인터가 현재 에 할당됩니다.

세 번째 버전에서는 인터페이스 포인터 할당이 현재 `ComPtr`에 할당됩니다.

네 번째 버전에서 할당 값의 인터페이스 포인터가 현재 `ComPtr` 인터페이스 포인터와 같지 않으면 두 번째 인터페이스 `ComPtr`포인터가 현재 에 할당됩니다.

다섯 번째 버전은 복사 연산자입니다. a에 `ComPtr` 대한 참조가 현재 `ComPtr`에 할당됩니다.

여섯 번째 버전은 이동 의미 체계를 사용하는 복사 연산자입니다. a에 대한 rvalue `ComPtr` 참조는 모든 형식이 정적 `ComPtr`캐스트인 경우 현재 에 할당됩니다.

일곱 번째 버전은 이동 의미 체계를 사용하는 복사 연산자입니다. A `ComPtr` 형식 *U에* 대한 rvalue 참조는 정적 캐스트이며 현재 `ComPtr`에 할당됩니다.

## <a name="comptroperator"></a><a name="operator-equality"></a>컴프트::연산자==

두 `ComPtr` 개체가 같은지를 나타냅니다.

```cpp
bool operator==(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator==(
   const ComPtr<T>& a,
   decltype(__nullptr)
);

bool operator==(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>매개 변수

*a.*<br/>
`ComPtr` 개체에 대한 참조입니다.

*B*<br/>
다른 `ComPtr` 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

첫 번째 `true` 연산자는 개체 *a가* 개체 *b와*같으면 생성됩니다. 그렇지 `false`않으면 .

두 번째 및 세 `true` 번째 연산자는 `nullptr`개체 *a가* 와 같으면 yield입니다. 그렇지 `false`않으면 .

## <a name="comptroperator"></a><a name="operator-inequality"></a>컴프트::연산자!=

두 `ComPtr` 개체가 같지 않은지를 나타냅니다.

```cpp
bool operator!=(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator!=(
   const ComPtr<T>& a,
   decltype(__nullptr)
);

bool operator!=(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>매개 변수

*a.*<br/>
`ComPtr` 개체에 대한 참조입니다.

*B*<br/>
다른 `ComPtr` 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

첫 번째 `true` 연산자는 개체 *a가* 개체 *b와*같지 않은 경우 생성됩니다. 그렇지 `false`않으면 .

두 번째 및 세 `true` 번째 연산자는 `nullptr`개체 *a가* 같지 않은 경우 yield; 그렇지 `false`않으면 .

## <a name="comptroperator-microsoftwrldetailsbooltype"></a><a name="operator-microsoft-wrl-details-booltype"></a>컴프트::연산자 마이크로 소프트::WRL::D테일::BoolType

a가 `ComPtr` 인터페이스의 개체 수명을 관리하고 있는지 여부를 나타냅니다.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>Return Value

인터페이스가 이것과 `ComPtr`연관된 경우 [BoolStruct::Member](boolstruct-structure.md#member) 데이터 멤버의 주소; 그렇지 `nullptr`않으면 .

## <a name="comptrptr_"></a><a name="ptr"></a>컴프트::p트르_

이에 `ComPtr`의해 연결되고 관리되는 인터페이스에 대한 포인터가 포함되어 있습니다.

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>설명

`ptr_`은 보호된 내부 데이터 멤버입니다.

## <a name="comptrreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>컴프트::릴리스앤겟주소

이와 `ComPtr` 연관된 인터페이스를 해제한 다음 [릴리스된](#ptr) 인터페이스에 대한 포인터를 포함하는 ptr_ 데이터 멤버의 주소를 검색합니다.

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Return Value

ptr_ [데이터](#ptr) 멤버의 주소입니다. `ComPtr`

## <a name="comptrreset"></a><a name="reset"></a>컴프트::재설정

이와 `ComPtr`연결된 인터페이스에 대한 포인터에 대한 모든 참조를 해제합니다.

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>Return Value

해제된 참조 수입니다(있는 경우).

## <a name="comptrswap"></a><a name="swap"></a>컴프트::스왑

현재에서 `ComPtr` 관리하는 인터페이스를 지정된 `ComPtr`에서 관리하는 인터페이스로 교환합니다.

```cpp
void Swap(
   _Inout_ ComPtr&& r
);

void Swap(
   _Inout_ ComPtr& r
);
```

### <a name="parameters"></a>매개 변수

*R*<br/>
`ComPtr`입니다.
