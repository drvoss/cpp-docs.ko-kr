---
title: ComPtrRef 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf
- client/Microsoft::WRL::Details::ComPtrRef::operator==
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
- client/Microsoft::WRL::Details::ComPtrRef::operator InterfaceType**
- client/Microsoft::WRL::Details::ComPtrRef::operator*
- client/Microsoft::WRL::Details::ComPtrRef::operator T*
- client/Microsoft::WRL::Details::ComPtrRef::operator void**
- client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRef class
- Microsoft::WRL::Details::ComPtrRef::ComPtrRef, constructor
- Microsoft::WRL::Details::ComPtrRef::GetAddressOf method
- Microsoft::WRL::Details::ComPtrRef::operator== operator
- Microsoft::WRL::Details::ComPtrRef::operator!= operator
- Microsoft::WRL::Details::ComPtrRef::operator InterfaceType** operator
- Microsoft::WRL::Details::ComPtrRef::operator* operator
- Microsoft::WRL::Details::ComPtrRef::operator T* operator
- Microsoft::WRL::Details::ComPtrRef::operator void** operator
- Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf method
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
ms.openlocfilehash: df9ded817227547493c04035e0abc3d948e24495
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372629"
---
# <a name="comptrref-class"></a>ComPtrRef 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename T>
class ComPtrRef : public ComPtrRefBase<T>;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[ComPtr\<T>](comptr-class.md) 형식 또는 이 형식에서 파생된 형식은 단순히 `ComPtr`에서 표시되는 인터페이스가 아닙니다.

## <a name="remarks"></a>설명

형식의 `ComPtr<T>`개체에 대한 참조를 나타냅니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                               | Description
---------------------------------- | -------------------------------------------------------------------------------------------------------------
[컴프트레프:콤프트레프](#comptrref) | 지정된 포인터에서 다른 `ComPtrRef` `ComPtrRef` 개체로 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                                                         | Description
------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------
[컴프트레프::겟주소](#getaddressof)                     | 현재 `ComPtrRef` 개체로 표시되는 인터페이스에 대한 포인터의 주소를 검색합니다.
[컴프트레프::릴리즈앤겟주소](#releaseandgetaddressof) | 현재 `ComPtrRef` 개체를 삭제 하 고 개체에 의해 표현 된 인터페이스에 `ComPtrRef` 포인터-대-포인터를 반환 합니다.

### <a name="public-operators"></a>Public 연산자

속성                                                                     | Description
------------------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[컴프트레프::연산자 인터페이스유형**](#operator-interfacetype-star-star) | 현재 `ComPtrRef` 개체를 삭제 하 고 개체에 의해 표현 된 인터페이스에 `ComPtrRef` 포인터-대-포인터를 반환 합니다.
[컴프트레프:연산자 T*](#operator-t-star)                               | 현재 ComPtrRef 개체의 [ptr_](comptrrefbase-class.md#ptr) 데이터 멤버의 값을 반환 합니다.
[컴프트레프::연산자 무효**](#operator-void-star-star)                   | 현재 `ComPtrRef` 개체를 삭제하고 개체가 포인터-대 포인터-로 `ComPtrRef` 표시된 인터페이스에 포인터를 캐스팅한 다음 cast 포인터를 반환합니다. `void`
[컴프트레프:연산자*](#operator-star)                                   | 현재 `ComPtrRef` 개체로 표시되는 인터페이스에 대한 포인터를 검색합니다.
[컴프트레프::연산자==](#operator-equality)                              | 두 `ComPtrRef` 개체가 같은지를 나타냅니다.
[컴프트레프::연산자!=](#operator-inequality)                            | 두 `ComPtrRef` 개체가 같지 않은지를 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="comptrrefcomptrref"></a><a name="comptrref"></a>컴프트레프:콤프트레프

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
ComPtrRef(
   _In_opt_ T* ptr
);
```

### <a name="parameters"></a>매개 변수

*Ptr*<br/>
다른 `ComPtrRef` 개체의 기본 값입니다.

### <a name="remarks"></a>설명

지정된 포인터에서 다른 `ComPtrRef` `ComPtrRef` 개체로 클래스의 새 인스턴스를 초기화합니다.

## <a name="comptrrefgetaddressof"></a><a name="getaddressof"></a>컴프트레프::겟주소

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
InterfaceType* const * GetAddressOf() const;
```

### <a name="return-value"></a>Return Value

현재 `ComPtrRef` 개체로 표시되는 인터페이스에 대한 포인터의 주소입니다.

### <a name="remarks"></a>설명

현재 `ComPtrRef` 개체로 표시되는 인터페이스에 대한 포인터의 주소를 검색합니다.

## <a name="comptrrefoperator"></a><a name="operator-equality"></a>컴프트레프::연산자==

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);

bool operator==(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator==(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>매개 변수

*a.*<br/>
`ComPtrRef` 개체에 대한 참조입니다.

*B*<br/>
다른 `ComPtrRef` 개체에 대한 참조 또는 익명 형식()에`void*`대한 포인터입니다.

### <a name="return-value"></a>Return Value

첫 번째 연산자는 개체 *a가* 개체 *b와*같으면 **true를** 산출합니다. 그렇지 **않으면, 거짓**.

두 번째 및 세 번째 연산자는 개체 *a가* **nullptr과**같으면 **true를** 산출합니다. 그렇지 **않으면, 거짓**.

네 번째 및 다섯 번째 연산자는 개체 *a가* 개체 *b와*같으면 **true를** 산출합니다. 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

두 `ComPtrRef` 개체가 같은지를 나타냅니다.

## <a name="comptrrefoperator"></a><a name="operator-inequality"></a>컴프트레프::연산자!=

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);

bool operator!=(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator!=(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>매개 변수

*a.*<br/>
`ComPtrRef` 개체에 대한 참조입니다.

*B*<br/>
다른 `ComPtrRef` 개체에 대한 참조 또는 익명 개체에 대한 포인터()입니다.`void*`

### <a name="return-value"></a>Return Value

첫 번째 연산자는 개체 *a가* 개체 *b와*같지 않은 경우 **true를** 생성합니다. 그렇지 **않으면, 거짓**.

두 번째 및 세 번째 연산자는 개체 *a가* **nullptr과**같지 않은 경우 **true를** 산출합니다. 그렇지 **않으면, 거짓**.

네 번째 및 다섯 번째 연산자는 개체 *a가* 개체 *b와*같지 않은 경우 **true를** 산출합니다. 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

두 `ComPtrRef` 개체가 같지 않은지를 나타냅니다.

## <a name="comptrrefoperator-interfacetype"></a><a name="operator-interfacetype-star-star"></a>컴프트레프::연산자 인터페이스유형**

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
operator InterfaceType**();
```

### <a name="remarks"></a>설명

현재 `ComPtrRef` 개체를 삭제 하 고 개체에 의해 표현 된 인터페이스에 `ComPtrRef` 포인터-대-포인터를 반환 합니다.

## <a name="comptrrefoperator"></a><a name="operator-star"></a>컴프트레프:연산자*

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
InterfaceType* operator *();
```

### <a name="return-value"></a>Return Value

현재 `ComPtrRef` 개체로 표시되는 인터페이스에 대한 포인터입니다.

### <a name="remarks"></a>설명

현재 `ComPtrRef` 개체로 표시되는 인터페이스에 대한 포인터를 검색합니다.

## <a name="comptrrefoperator-t"></a><a name="operator-t-star"></a>컴프트레프:연산자 T*

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
operator T*();
```

### <a name="remarks"></a>설명

현재 `ComPtrRef` 개체의 [ptr_](comptrrefbase-class.md#ptr) 데이터 멤버의 값을 반환합니다.

## <a name="comptrrefoperator-void"></a><a name="operator-void-star-star"></a>컴프트레프:연산자 무효\*\*

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
operator void**() const;
```

### <a name="remarks"></a>설명

현재 `ComPtrRef` 개체를 삭제하고 개체가 포인터-대 포인터-로 `ComPtrRef` 표시된 인터페이스에 포인터를 캐스팅한 다음 cast 포인터를 반환합니다. `void`

## <a name="comptrrefreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>컴프트레프::릴리즈앤겟주소

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Return Value

삭제된 `ComPtrRef` 개체로 표시된 인터페이스에 대한 포인터입니다.

### <a name="remarks"></a>설명

현재 `ComPtrRef` 개체를 삭제 하 고 개체에 의해 표현 된 인터페이스에 `ComPtrRef` 포인터-대-포인터를 반환 합니다.
