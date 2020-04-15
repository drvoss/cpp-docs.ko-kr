---
title: Module::GenericReleaseNotifier 클래스
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::callback_
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::Invoke
helpviewer_keywords:
- Microsoft::WRL::Module::GenericReleaseNotifier class
- Microsoft::WRL::Module::GenericReleaseNotifier::callback_ data member
- Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier, constructor
- Microsoft::WRL::Module::GenericReleaseNotifier::Invoke method
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
ms.openlocfilehash: e3cc8e33d596fb1d3ecc4a94fee7971a50ffe596
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371302"
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier 클래스

현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다. 이벤트 처리기는 람다, 함수 또는 함수 포인터에 의해 지정됩니다.

## <a name="syntax"></a>구문

```cpp
template<typename T>
class GenericReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
이벤트 처리기의 위치를 포함하는 데이터 멤버 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                                                                                     | Description
-------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------
[모듈:::일반 릴리스 어미::일반 릴리스](#genericreleasenotifier-genericreleasenotifier) | `Module::GenericReleaseNotifier` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                                                                     | Description
------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------
[모듈:::일반 릴리스 공보::호출](#genericreleasenotifier-invoke) | 현재 `Module::GenericReleaseNotifier` 개체와 연결된 이벤트 처리기를 호출합니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

속성                                                                          | Description
----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------
[모듈:::일반 릴리스 어이티피어::callback_](#genericreleasenotifier-callback) | 현재 `Module::GenericReleaseNotifier` 개체와 연결된 람다, 펑터 또는 포인터-함수 이벤트 처리기를 보유합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ReleaseNotifier`

`GenericReleaseNotifier`

## <a name="requirements"></a>요구 사항

**헤더:** 모듈.h

**네임스페이스:** Microsoft::WRL

## <a name="modulegenericreleasenotifiercallback_"></a><a name="genericreleasenotifier-callback"></a>모듈:::일반 릴리스 어이티피어::callback_

현재 `Module::GenericReleaseNotifier` 개체와 연결된 람다, 펑터 또는 포인터-함수 이벤트 처리기를 보유합니다.

```cpp
T callback_;
```

## <a name="modulegenericreleasenotifiergenericreleasenotifier"></a><a name="genericreleasenotifier-genericreleasenotifier"></a>모듈:::일반 릴리스 어미::일반 릴리스

`Module::GenericReleaseNotifier` 클래스의 새 인스턴스를 초기화합니다.

```cpp
GenericReleaseNotifier(
   T callback,
   bool release
) throw() : ReleaseNotifier(release), callback_(callback);
```

### <a name="parameters"></a>매개 변수

*콜백(callback)*<br/>
괄호 함수 연산자 ()를`()`사용하여 호출할 수 있는 람다, 펑터 또는 함수 간 포인터 이벤트 처리기입니다.

*릴리스*<br/>
기본 `true` [모듈::ReleaseNotifier::Release()](module-releasenotifier-class.md#releasenotifier-release) 메서드를 호출하도록 지정합니다. 그렇지 않으면 `false`을 지정합니다.

## <a name="modulegenericreleasenotifierinvoke"></a><a name="genericreleasenotifier-invoke"></a>모듈:::일반 릴리스 공보::호출

현재 `Module::GenericReleaseNotifier` 개체와 연결된 이벤트 처리기를 호출합니다.

```cpp
void Invoke();
```
