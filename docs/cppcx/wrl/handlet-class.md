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
ms.openlocfilehash: f66fbe23c305be15e09928242175dfa7ce8c141b
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821820"
---
# <a name="handlet-class"></a>HandleT 클래스

개체에 대한 핸들을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template <typename HandleTraits>
class HandleT;
```

### <a name="parameters"></a>매개 변수

*HandleTraits*<br/>
핸들의 공통 특성을 정의 하는 [해당 구조체의 인스턴스를 만듭니다](handletraits-structure.md) .

## <a name="members"></a>Members

### <a name="public-typedefs"></a>공용 형식 정의

이름     | 설명
-------- | -----------------------------
`Traits` | `HandleTraits`의 동의어입니다.

### <a name="public-constructors"></a>Public 생성자

이름                                | 설명
----------------------------------- | --------------------------------------------------
[HandleT::HandleT](#handlet)        | `HandleT` 클래스의 새 인스턴스를 초기화합니다.
[HandleT::~HandleT](#tilde-handlet) | `HandleT` 클래스의 인스턴스를 초기화 하지 않습니다.

### <a name="public-methods"></a>Public 메서드

이름                         | 설명
---------------------------- | ----------------------------------------------------------------------
[HandleT::Attach](#attach)   | 지정 된 핸들을 현재 `HandleT` 개체와 연결 합니다.
[수동 Let:: Close](#close)     | 현재 닫습니다 `HandleT` 개체입니다.
[HandleT::Detach](#detach)   | 현재 `HandleT` 개체를 내부 핸들에서 분리 합니다.
[HandleT::Get](#get)         | 내부 핸들의 값을 가져옵니다.
[HandleT::IsValid](#isvalid) | 현재 `HandleT` 개체가 핸들을 나타내는지 여부를 나타냅니다.

### <a name="protected-methods"></a>Protected 메서드

이름                                     | 설명
---------------------------------------- | ------------------------------------
[수동 Let:: InternalClose](#internalclose) | 현재 닫습니다 `HandleT` 개체입니다.

### <a name="public-operators"></a>Public 연산자

이름                                   | 설명
-------------------------------------- | ----------------------------------------------------------------------------------
[HandleT::operator=](#operator-assign) | 지정 된 `HandleT` 개체의 값을 현재 `HandleT` 개체로 이동 합니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

이름                        | 설명
--------------------------- | ----------------------------------------------------------------
[HandleT::handle_](#handle) | `HandleT` 개체가 나타내는 핸들을 포함 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HandleT`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임 스페이스:** Microsoft:: WRL:: 래퍼

## <a name="tilde-handlet"></a>HandleT::~HandleT

`HandleT` 클래스의 인스턴스를 초기화 하지 않습니다.

```cpp
~HandleT();
```

## <a name="attach"></a>HandleT::Attach

지정 된 핸들을 현재 `HandleT` 개체와 연결 합니다.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
핸들입니다.

## <a name="close"></a>수동 Let:: Close

현재 닫습니다 `HandleT` 개체입니다.

```cpp
void Close();
```

### <a name="remarks"></a>주의

현재 `HandleT`의 기반이 되는 핸들이 닫혀 있고 `HandleT`가 잘못 된 상태로 설정 된 경우

핸들이 제대로 닫히지 않은 경우 호출 스레드에서 예외가 발생합니다.

## <a name="detach"></a>HandleT::Detach

현재 `HandleT` 개체를 내부 핸들에서 분리 합니다.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>반환 값

내부 핸들입니다.

### <a name="remarks"></a>주의

이 작업이 완료 되 면 현재 `HandleT` 잘못 된 상태로 설정 됩니다.

## <a name="get"></a>HandleT::Get

내부 핸들의 값을 가져옵니다.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>반환 값

핸들입니다.

## <a name="handle"></a>HandleT::handle_

`HandleT` 개체가 나타내는 핸들을 포함 합니다.

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlet"></a>HandleT::HandleT

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

*h*<br/>
핸들입니다.

### <a name="remarks"></a>주의

첫 번째 생성자는 개체에 대 한 유효한 핸들이 아닌 `HandleT` 개체를 초기화 합니다. 두 번째 생성자는 매개 변수 *h*에서 새 `HandleT` 개체를 만듭니다.

## <a name="internalclose"></a>수동 Let:: InternalClose

현재 닫습니다 `HandleT` 개체입니다.

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>반환 값

현재 `HandleT` 성공적으로 닫히면 **true** 이 고, 그렇지 않으면입니다. 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>주의

`InternalClose()`이(가) `protected`인 경우.

## <a name="isvalid"></a>HandleT::IsValid

현재 `HandleT` 개체가 핸들을 나타내는지 여부를 나타냅니다.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>반환 값

`HandleT` 핸들을 나타내면 **true** 이 고, 그렇지 않으면입니다. 그렇지 않으면 **false**입니다.

## <a name="operator-assign"></a>HandleT::operator=

지정 된 `HandleT` 개체의 값을 현재 `HandleT` 개체로 이동 합니다.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
핸들에 대 한 rvalue 참조입니다.

### <a name="return-value"></a>반환 값

현재 `HandleT` 개체에 대 한 참조입니다.

### <a name="remarks"></a>주의

이 작업은 매개 변수 *h*에서 지정 된 `HandleT` 개체를 무효화 합니다.
