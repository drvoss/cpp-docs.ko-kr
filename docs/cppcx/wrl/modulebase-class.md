---
title: ModuleBase 클래스
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::~ModuleBase
helpviewer_keywords:
- ModuleBase class
- Microsoft::WRL::Details::ModuleBase::DecrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::IncrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::ModuleBase, constructor
- Microsoft::WRL::Details::ModuleBase::~ModuleBase, destructor
ms.assetid: edce7591-6893-46f7-94a7-382827775548
ms.openlocfilehash: 13a8ceef3133e9946524e1fcd02e96535eccd7fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371266"
---
# <a name="modulebase-class"></a>ModuleBase 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
class ModuleBase;
```

## <a name="remarks"></a>설명

[모듈](module-class.md) 클래스의 기본 클래스를 나타냅니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                         | Description
-------------------------------------------- | ---------------------------------------------------------
[모듈 베이스 :: 모듈 베이스](#modulebase)        | `Module` 클래스의 인스턴스를 초기화합니다.
[모듈 베이스 ::~모듈 베이스](#tilde-modulebase) | 클래스의 현재 인스턴스를 초기화합니다. `Module`

### <a name="public-methods"></a>Public 메서드

속성                                                      | Description
--------------------------------------------------------- | -------------------------------------------------------------------------
[모듈베이스::D개체카운트](#decrementobjectcount) | 구현될 때 모듈에서 추적하는 개체 수를 감소시입니다.
[모듈 베이스::증분개체카운트](#incrementobjectcount) | 구현될 때 모듈에서 추적하는 개체 수를 늘입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ModuleBase`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="modulebasemodulebase"></a><a name="tilde-modulebase"></a>모듈 베이스 ::~모듈 베이스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>설명

클래스의 현재 인스턴스를 초기화합니다. `ModuleBase`

## <a name="modulebasedecrementobjectcount"></a><a name="decrementobjectcount"></a>모듈베이스::D개체카운트

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>Return Value

감소 작업 전 수입니다.

### <a name="remarks"></a>설명

구현될 때 모듈에서 추적하는 개체 수를 감소시입니다.

## <a name="modulebaseincrementobjectcount"></a><a name="incrementobjectcount"></a>모듈 베이스::증분개체카운트

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>Return Value

증가 연산 전 수입니다.

### <a name="remarks"></a>설명

구현될 때 모듈에서 추적하는 개체 수를 늘입니다.

## <a name="modulebasemodulebase"></a><a name="modulebase"></a>모듈 베이스 :: 모듈 베이스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
ModuleBase();
```

### <a name="remarks"></a>설명

`Module` 클래스의 인스턴스를 초기화합니다.
