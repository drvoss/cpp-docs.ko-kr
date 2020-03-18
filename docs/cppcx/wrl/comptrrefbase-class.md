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
ms.openlocfilehash: df4e2aa1ce650fd5b1f04baf2f7c4cd2fb4cff93
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423647"
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
[ComPtr\<t >](comptr-class.md) 형식 또는이 형식에서 파생 된 형식으로, `ComPtr`표시 되는 인터페이스 일 뿐입니다.

## <a name="remarks"></a>설명

[Comptrref](comptrref-class.md) 클래스의 기본 클래스를 나타냅니다.

## <a name="members"></a>구성원

### <a name="public-typedefs"></a>공용 형식 정의

속성            | Description
--------------- | -------------------------------------------------
`InterfaceType` | 템플릿 매개 변수 *T*형식의 동의어입니다.

### <a name="public-operators"></a>Public 연산자

속성                                                                       | Description
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[ComPtrRefBase:: operator IInspectable * *](#operator-iinspectable-star-star) | 현재 [ptr_](#ptr) 데이터 멤버를 `IInspectable` 인터페이스에 대 한 포인터 포인터로 캐스팅 합니다.
[ComPtrRefBase:: operator IUnknown * *](#operator-iunknown-star-star)         | 현재 [ptr_](#ptr) 데이터 멤버를 `IUnknown` 인터페이스에 대 한 포인터 포인터로 캐스팅 합니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

속성                        | Description
--------------------------- | ----------------------------------------------------------------
[ComPtrRefBase::p tr_](#ptr) | 현재 템플릿 매개 변수에 지정 된 형식에 대 한 포인터입니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`ComPtrRefBase`

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**네임 스페이스:** Microsoft:: WRL::D etails

## <a name="operator-iinspectable-star-star"></a>ComPtrRefBase:: operator IInspectable\*\* 연산자

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>설명

현재 [ptr_](#ptr) 데이터 멤버를 `IInspectable` 인터페이스에 대 한 포인터 포인터로 캐스팅 합니다.

현재 `ComPtrRefBase` `IInspectable`에서 파생 되지 않으면 오류가 발생 합니다.

이 캐스트는 `__WRL_CLASSIC_COM__` 정의 된 경우에만 사용할 수 있습니다.

## <a name="operator-iunknown-star-star"></a>ComPtrRefBase:: operator IUnknown * * 연산자

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>설명

현재 [ptr_](#ptr) 데이터 멤버를 `IUnknown` 인터페이스에 대 한 포인터 포인터로 캐스팅 합니다.

현재 `ComPtrRefBase` `IUnknown`에서 파생 되지 않으면 오류가 발생 합니다.

## <a name="ptr"></a>ComPtrRefBase::p tr_

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
T* ptr_;
```

### <a name="remarks"></a>설명

현재 템플릿 매개 변수에 지정 된 형식에 대 한 포인터입니다. `ptr_` 보호 된 데이터 멤버입니다.
