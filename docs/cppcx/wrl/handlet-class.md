---
title: HandleT 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Get
- corewrappers/Microsoft::WRL::Wrappers::HandleT::handle_
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
- corewrappers/Microsoft::WRL::Wrappers::HandleT::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
- corewrappers/Microsoft::WRL::Wrappers::HandleT::~HandleT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleT class
- Microsoft::WRL::Wrappers::HandleT::Attach method
- Microsoft::WRL::Wrappers::HandleT::Close method
- Microsoft::WRL::Wrappers::HandleT::Detach method
- Microsoft::WRL::Wrappers::HandleT::Get method
- Microsoft::WRL::Wrappers::HandleT::handle_ data member
- Microsoft::WRL::Wrappers::HandleT::HandleT, constructor
- Microsoft::WRL::Wrappers::HandleT::InternalClose method
- Microsoft::WRL::Wrappers::HandleT::IsValid method
- Microsoft::WRL::Wrappers::HandleT::operator= operator
- Microsoft::WRL::Wrappers::HandleT::~HandleT, destructor
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
ms.openlocfilehash: bde7d7f1bd6730d96cb0f7a0d191a32eb8ed3e8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371458"
---
# <a name="handlet-class"></a>HandleT 클래스

개체에 대한 핸들을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template <typename HandleTraits>
class HandleT;
```

### <a name="parameters"></a>매개 변수

*핸들트레이스*<br/>
핸들의 일반적인 특성을 정의하는 [HandleTraits](handletraits-structure.md) 구조의 인스턴스입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성     | Description
-------- | -----------------------------
`Traits` | `HandleTraits`의 동의어입니다.

### <a name="public-constructors"></a>Public 생성자

속성                                | Description
----------------------------------- | --------------------------------------------------
[핸들: 핸들: 핸들](#handlet)        | `HandleT` 클래스의 새 인스턴스를 초기화합니다.
[핸들T :~핸들](#tilde-handlet) | 클래스의 인스턴스를 초기화합니다. `HandleT`

### <a name="public-methods"></a>Public 메서드

속성                         | Description
---------------------------- | ----------------------------------------------------------------------
[핸들T::부착](#attach)   | 지정된 핸들을 현재 `HandleT` 개체와 연결합니다.
[핸들: :닫기](#close)     | 현재 `HandleT` 개체를 닫습니다.
[핸들트::D에타치](#detach)   | 기본 핸들에서 `HandleT` 현재 개체를 분리합니다.
[핸들 : : 얻을](#get)         | 기본 핸들의 값을 가져옵니다.
[핸들: :: 유효합니다.](#isvalid) | 현재 `HandleT` 개체가 핸들을 나타내는지 여부를 나타냅니다.

### <a name="protected-methods"></a>Protected 메서드

속성                                     | Description
---------------------------------------- | ------------------------------------
[핸들::내부 닫기](#internalclose) | 현재 `HandleT` 개체를 닫습니다.

### <a name="public-operators"></a>Public 연산자

속성                                   | Description
-------------------------------------- | ----------------------------------------------------------------------------------
[핸들T::연산자=](#operator-assign) | 지정된 `HandleT` 개체의 값을 현재 `HandleT` 개체로 이동합니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

속성                        | Description
--------------------------- | ----------------------------------------------------------------
[핸들:handle_](#handle) | 개체로 표시되는 핸들을 `HandleT` 포함합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HandleT`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼

## <a name="handlethandlet"></a><a name="tilde-handlet"></a>핸들T :~핸들

클래스의 인스턴스를 초기화합니다. `HandleT`

```cpp
~HandleT();
```

## <a name="handletattach"></a><a name="attach"></a>핸들T::부착

지정된 핸들을 현재 `HandleT` 개체와 연결합니다.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
핸들입니다.

## <a name="handletclose"></a><a name="close"></a>핸들: :닫기

현재 `HandleT` 개체를 닫습니다.

```cpp
void Close();
```

### <a name="remarks"></a>설명

전류의 `HandleT` 기초가 되는 `HandleT` 핸들이 닫혀 있고 이 핸들이 잘못된 상태로 설정됩니다.

핸들이 제대로 닫히지 않은 경우 호출 스레드에서 예외가 발생합니다.

## <a name="handletdetach"></a><a name="detach"></a>핸들트::D에타치

기본 핸들에서 `HandleT` 현재 개체를 분리합니다.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>Return Value

기본 핸들입니다.

### <a name="remarks"></a>설명

이 작업이 완료되면 전류가 `HandleT` 잘못된 상태로 설정됩니다.

## <a name="handletget"></a><a name="get"></a>핸들 : : 얻을

기본 핸들의 값을 가져옵니다.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>Return Value

핸들입니다.

## <a name="handlethandle_"></a><a name="handle"></a>핸들:handle_

개체로 표시되는 핸들을 `HandleT` 포함합니다.

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlethandlet"></a><a name="handlet"></a>핸들: 핸들: 핸들

`HandleT` 클래스의 새 인스턴스를 초기화합니다.

```cpp
explicit HandleT(
   typename HandleTraits::Type h =
      HandleTraits::GetInvalidValue()
);

HandleT(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
핸들입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 개체에 대한 `HandleT` 올바른 핸들이 아닌 개체를 초기화합니다. 두 번째 생성자는 `HandleT` 매개 변수 *h에서*새 개체를 만듭니다.

## <a name="handletinternalclose"></a><a name="internalclose"></a>핸들::내부 닫기

현재 `HandleT` 개체를 닫습니다.

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>Return Value

현재가 `HandleT` 성공적으로 닫힌 경우 **true;** 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

`InternalClose()`은 `protected`입니다.

## <a name="handletisvalid"></a><a name="isvalid"></a>핸들: :: 유효합니다.

현재 `HandleT` 개체가 핸들을 나타내는지 여부를 나타냅니다.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Return Value

**true는** `HandleT` 핸들을 나타내는 경우입니다. 그렇지 **않으면, 거짓**.

## <a name="handletoperator"></a><a name="operator-assign"></a>핸들T::연산자=

지정된 `HandleT` 개체의 값을 현재 `HandleT` 개체로 이동합니다.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
핸들에 대한 rvalue 참조입니다.

### <a name="return-value"></a>Return Value

현재 `HandleT` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 작업은 매개 `HandleT` 변수 *h로*지정된 개체를 무효화합니다.
