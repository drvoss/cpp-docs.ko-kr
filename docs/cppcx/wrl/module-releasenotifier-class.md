---
title: Module::ReleaseNotifier 클래스
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::ReleaseNotifier::Release
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
helpviewer_keywords:
- Microsoft::WRL::Module::ReleaseNotifier class
- Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier, destructor
- Microsoft::WRL::Module::ReleaseNotifier::Invoke method
- Microsoft::WRL::Module::ReleaseNotifier::Release method
- Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier, constructor
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
ms.openlocfilehash: f314d09c443d0d284e3a821b5c879bfb74baf812
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371283"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier 클래스

모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다.

## <a name="syntax"></a>구문

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                                                                | Description
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[모듈::릴리스 통보자::~릴리스](#releasenotifier-tilde-releasenotifier) | 클래스의 현재 인스턴스를 초기화합니다. `Module::ReleaseNotifier`
[모듈::릴리즈어::릴리즈어](#releasenotifier-releasenotifier)        | `Module::ReleaseNotifier` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                                                         | Description
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[모듈::릴리스통보자::호출](#releasenotifier-invoke)   | 구현될 때 모듈의 마지막 개체가 해제되면 이벤트 처리기를 호출합니다.
[Module::ReleaseNotifier::Release](#releasenotifier-release) | `Module::ReleaseNotifier` **true의**매개변수로 객체가 생성된 경우 현재 개체를 삭제합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ReleaseNotifier`

## <a name="requirements"></a>요구 사항

**헤더:** 모듈.h

**네임스페이스:** Microsoft::WRL

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-tilde-releasenotifier"></a>모듈::릴리스 통보자::~릴리스

클래스의 현재 인스턴스를 초기화합니다. `Module::ReleaseNotifier`

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="modulereleasenotifierinvoke"></a><a name="releasenotifier-invoke"></a>모듈::릴리스통보자::호출

구현될 때 모듈의 마지막 개체가 해제되면 이벤트 처리기를 호출합니다.

```cpp
virtual void Invoke() = 0;
```

## <a name="modulereleasenotifierrelease"></a><a name="releasenotifier-release"></a>모듈::릴리스통보자::릴리즈

`Module::ReleaseNotifier` **true의**매개변수로 객체가 생성된 경우 현재 개체를 삭제합니다.

```cpp
void Release() throw();
```

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-releasenotifier"></a>모듈::릴리즈어::릴리즈어

`Module::ReleaseNotifier` 클래스의 새 인스턴스를 초기화합니다.

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>매개 변수

*릴리스*<br/>
`true`메서드가 호출될 `Release` 때 이 인스턴스를 삭제합니다. `false` 이 인스턴스를 삭제하지 않습니다.
