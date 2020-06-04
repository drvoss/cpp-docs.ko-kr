---
title: RoInitializeWrapper 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::HRESULT
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
helpviewer_keywords:
- Microsoft::WRL::Wrappers::RoInitializeWrapper class
- Microsoft::WRL::Wrappers::RoInitializeWrapper::operator HRESULT operator
- Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper, constructor
- Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper, destructor
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
ms.openlocfilehash: eba9162f17b98d13a9caf956b4f110b89dd81c37
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371242"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper 클래스

Windows 런타임을 초기화합니다.

## <a name="syntax"></a>구문

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>설명

`RoInitializeWrapper`은 Windows 런타임을 초기화하고 작업이 성공했는지 여부를 나타내는 HRESULT를 반환하는 편리함입니다. 클래스 소멸자가 호출하기 `::Windows::Foundation::Uninitialize`때문에 전역 `RoInitializeWrapper` 또는 최상위 범위에서 인스턴스를 선언해야 합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                                                    | Description
----------------------------------------------------------------------- | -----------------------------------------------------------------
[Ro초기화래퍼::로초기화래퍼](#roinitializewrapper)        | `RoInitializeWrapper` 클래스의 새 인스턴스를 초기화합니다.
[Ro초기화래퍼::~로초기화래퍼](#tilde-roinitializewrapper) | 클래스의 현재 인스턴스를 `RoInitializeWrapper` 삭제합니다.

### <a name="public-operators"></a>Public 연산자

속성                                       | Description
------------------------------------------ | ------------------------------------------------------------------------
[Ro초기화래퍼::HRESULT()](#hresult) | 생성자가 생성한 HRESULT를 `RoInitializeWrapper` 검색합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`RoInitializeWrapper`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼

## <a name="roinitializewrapperhresult"></a><a name="hresult"></a>Ro초기화래퍼::HRESULT()

마지막 `RoInitializeWrapper` 생성자가 생성한 HRESULT 값을 검색합니다.

```cpp
operator HRESULT()
```

## <a name="roinitializewrapperroinitializewrapper"></a><a name="roinitializewrapper"></a>Ro초기화래퍼::로초기화래퍼

`RoInitializeWrapper` 클래스의 새 인스턴스를 초기화합니다.

```cpp
RoInitializeWrapper(RO_INIT_TYPE flags)
```

### <a name="parameters"></a>매개 변수

*플래그*<br/>
Windows 런타임에서 제공하는 지원을 지정하는 RO_INIT_TYPE 열거형 중 하나입니다.

### <a name="remarks"></a>설명

클래스는 `RoInitializeWrapper` 을 `Windows::Foundation::Initialize(flags)`호출합니다.

## <a name="roinitializewrapperroinitializewrapper"></a><a name="tilde-roinitializewrapper"></a>Ro초기화래퍼::~로초기화래퍼

Windows 런타임을 초기화하지 않습니다.

```cpp
~RoInitializeWrapper()
```

### <a name="remarks"></a>설명

클래스는 `RoInitializeWrapper` 을 `Windows::Foundation::Uninitialize()`호출합니다.
