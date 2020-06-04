---
title: 이벤트 클래스(WRL)
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Event class
- Microsoft::WRL::Wrappers::Event::Event, constructor
- Microsoft::WRL::Wrappers::Event::operator= operator
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
ms.openlocfilehash: 85b4c2d1f1a27e90a65e47aa749e079f4aa08739
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371530"
---
# <a name="event-class-wrl"></a>이벤트 클래스(WRL)

이벤트를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                   | Description
---------------------- | ------------------------------------------------
[이벤트::이벤트](#event) | `Event` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-operators"></a>Public 연산자

속성                                 | Description
------------------------------------ | ------------------------------------------------------------------------
[이벤트::연산자=](#operator-assign) | 현재 `Event` 인스턴스에 `Event` 지정된 참조를 할당합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HandleT`

`Event`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼

## <a name="eventevent"></a><a name="event"></a>이벤트::이벤트

`Event` 클래스의 새 인스턴스를 초기화합니다.

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
이벤트에 대한 핸들. 기본적으로 *h는* `nullptr`에 초기화됩니다.

## <a name="eventoperator"></a><a name="operator-assign"></a>이벤트::연산자=

현재 `Event` 인스턴스에 `Event` 지정된 참조를 할당합니다.

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
인스턴스에 대한 rvalue `Event` 참조입니다.

### <a name="return-value"></a>Return Value

현재 `Event` 인스턴스에 대한 포인터입니다.
