---
title: MakeAllocator 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
- implements/Microsoft::WRL::Details::MakeAllocator::Detach
- implements/Microsoft::WRL::Details::MakeAllocator::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator
helpviewer_keywords:
- Microsoft::WRL::Details::MakeAllocator class
- Microsoft::WRL::Details::MakeAllocator::Allocate method
- Microsoft::WRL::Details::MakeAllocator::Detach method
- Microsoft::WRL::Details::MakeAllocator::MakeAllocator, constructor
- Microsoft::WRL::Details::MakeAllocator::~MakeAllocator, destructor
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
ms.openlocfilehash: dc0d83f2550646572a4eff2bec7850037c6dbf6a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371329"
---
# <a name="makeallocator-class"></a>MakeAllocator 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<
    typename T,
    bool hasWeakReferenceSupport =
          !__is_base_of(RuntimeClassFlags<InhibitWeakReference>,
                        T)
>
class MakeAllocator;

template<typename T>
class MakeAllocator<T, false>;

template<typename T>
class MakeAllocator<T, true>;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
형식 이름.

*hasWeak참조 지원*<br/>
**true는** 약한 참조를 지원하는 개체에 메모리를 할당합니다. **false는** 약한 참조를 지원하지 않는 개체에 메모리를 할당합니다.

## <a name="remarks"></a>설명

약한 참조 지원 유무에 관계없이 활성화 가능한 클래스에 메모리를 할당합니다.

`MakeAllocator` 사용자 정의 메모리 할당 모델을 구현하기 위해 클래스를 재정의합니다.

`MakeAllocator`일반적으로 생성 중에 개체가 throw되는 경우 메모리 누수 방지에 사용됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                                  | Description
----------------------------------------------------- | ----------------------------------------------------------------
[메이크알로카이터::메이크알로카토르](#makeallocator)        | `MakeAllocator` 클래스의 새 인스턴스를 초기화합니다.
[메이크알로카이터::~메이크알로카토르](#tilde-makeallocator) | 클래스의 현재 인스턴스를 초기화합니다. `MakeAllocator`

### <a name="public-methods"></a>Public 메서드

속성                                 | Description
------------------------------------ | -----------------------------------------------------------------------------------------------------------
[메이크알로카이터:할당](#allocate) | 메모리를 할당하고 현재 `MakeAllocator` 개체와 연결합니다.
[메이크알로카터::D에타치](#detach)     | 현재 `MakeAllocator` 개체에서 [할당](#allocate) 메서드에 의해 할당된 메모리를 분리합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`MakeAllocator`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="makeallocatorallocate"></a><a name="allocate"></a>메이크알로카이터:할당

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
__forceinline void* Allocate();
```

### <a name="return-value"></a>Return Value

성공하면 할당된 메모리에 대한 포인터; 그렇지 `nullptr`않으면 .

### <a name="remarks"></a>설명

메모리를 할당하고 현재 `MakeAllocator` 개체와 연결합니다.

할당된 메모리의 크기는 현재 `MakeAllocator` 템플릿 매개 변수에 의해 지정된 형식의 크기입니다.

개발자는 다른 메모리 할당 `Allocate()` 모델을 구현하는 메서드만 재정의해야 합니다.

## <a name="makeallocatordetach"></a><a name="detach"></a>메이크알로카터::D에타치

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
__forceinline void Detach();
```

### <a name="remarks"></a>설명

현재 `MakeAllocator` 개체에서 [할당](#allocate) 메서드에 의해 할당된 메모리를 분리합니다.

호출하는 `Detach()`경우 메서드에서 `Allocate` 제공하는 메모리를 삭제해야 합니다.

## <a name="makeallocatormakeallocator"></a><a name="makeallocator"></a>메이크알로카이터::메이크알로카토르

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
MakeAllocator();
```

### <a name="remarks"></a>설명

`MakeAllocator` 클래스의 새 인스턴스를 초기화합니다.

## <a name="makeallocatormakeallocator"></a><a name="tilde-makeallocator"></a>메이크알로카이터::~메이크알로카토르

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
~MakeAllocator();
```

### <a name="remarks"></a>설명

클래스의 현재 인스턴스를 초기화합니다. `MakeAllocator`

이 소멸자는 필요한 경우 기본 할당된 메모리도 삭제합니다.
