---
title: ComPtrRefBase 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
- client/Microsoft::WRL::Details::ComPtrRefBase::ptr_
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRefBase class
- Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable** operator
- Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown** operator
- Microsoft::WRL::Details::ComPtrRefBase::ptr_ data member
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
ms.openlocfilehash: 4f6dd6449cf8135ad14486d64cea95d8329e0014
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372612"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[ComPtr\<T>](comptr-class.md) 형식 또는 이 형식에서 파생된 형식은 단순히 `ComPtr`에서 표시되는 인터페이스가 아닙니다.

## <a name="remarks"></a>설명

[ComPtrRef](comptrref-class.md) 클래스의 기본 클래스를 나타냅니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성            | Description
--------------- | -------------------------------------------------
`InterfaceType` | 템플릿 매개 변수 *T의*형식에 대한 동의어입니다.

### <a name="public-operators"></a>Public 연산자

속성                                                                       | Description
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[컴프트레프베이스::연산자 IInspectable**](#operator-iinspectable-star-star) | 현재 [ptr_](#ptr) 데이터 멤버를 `IInspectable` 포인터-a-포인터-인터페이스에 캐스팅합니다.
[컴프트레프베이스::연산자 I알 수 없음**](#operator-iunknown-star-star)         | 현재 [ptr_](#ptr) 데이터 멤버를 `IUnknown` 포인터-a-포인터-인터페이스에 캐스팅합니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

속성                        | Description
--------------------------- | ----------------------------------------------------------------
[컴프트레프베이스::p트르_](#ptr) | 현재 템플릿 매개 변수에 의해 지정된 형식에 대한 포인터입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ComPtrRefBase`

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="comptrrefbaseoperator-iinspectable-operator"></a><a name="operator-iinspectable-star-star"></a>컴프트레프베이스::연산자 I검사 가능\* \* 연산자

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>설명

현재 [ptr_](#ptr) 데이터 멤버를 `IInspectable` 포인터-a-포인터-인터페이스에 캐스팅합니다.

전류가 `ComPtrRefBase` `IInspectable`파생되지 않으면 오류가 내보내드립니다.

이 캐스트는 정의된 `__WRL_CLASSIC_COM__` 경우에만 사용할 수 있습니다.

## <a name="comptrrefbaseoperator-iunknown-operator"></a><a name="operator-iunknown-star-star"></a>컴프트레프베이스::연산자 I알 수 없음** 연산자

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>설명

현재 [ptr_](#ptr) 데이터 멤버를 `IUnknown` 포인터-a-포인터-인터페이스에 캐스팅합니다.

전류가 `ComPtrRefBase` `IUnknown`파생되지 않으면 오류가 내보내드립니다.

## <a name="comptrrefbaseptr_"></a><a name="ptr"></a>컴프트레프베이스::p트르_

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
T* ptr_;
```

### <a name="remarks"></a>설명

현재 템플릿 매개 변수에 의해 지정된 형식에 대한 포인터입니다. `ptr_`은 보호된 데이터 멤버입니다.
