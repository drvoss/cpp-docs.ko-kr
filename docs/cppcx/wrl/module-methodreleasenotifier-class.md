---
title: Module::MethodReleaseNotifier 클래스
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::MethodReleaseNotifier::method_
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::object_
helpviewer_keywords:
- Microsoft::WRL::Module::MethodReleaseNotifier class
- Microsoft::WRL::Module::MethodReleaseNotifier::Invoke method
- Microsoft::WRL::Module::MethodReleaseNotifier::method_ data member
- Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier, constructor
- Microsoft::WRL::Module::MethodReleaseNotifier::object_ data member
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
ms.openlocfilehash: c641f150b6f029facffa62f7b47c7da32138735e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371296"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier 클래스

현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다. 이벤트 처리기는 개체 및 해당 포인터-메서드 멤버에 의해 지정 됩니다.

## <a name="syntax"></a>구문

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
멤버 함수가 이벤트 처리기인 개체의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                                                                                 | Description
---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------
[모듈:::방법 릴리스 공고자::방법 릴리스](#methodreleasenotifier-methodreleasenotifier) | `Module::MethodReleaseNotifier` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                                                                   | Description
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------
[모듈:::방법 해제 공보::호출](#methodreleasenotifier-invoke) | 현재 `Module::MethodReleaseNotifier` 개체와 연결된 이벤트 처리기를 호출합니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

속성                                                                    | Description
----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[모듈:::방법 릴리스공교자::method_](#methodreleasenotifier-method) | 현재 `Module::MethodReleaseNotifier` 개체에 대 한 이벤트 처리기에 대 한 포인터를 보유 합니다.
[모듈:::방법 릴리스 공고자::object_](#methodreleasenotifier-object) | 현재 `Module::MethodReleaseNotifier` 개체에 대 한 이벤트 처리기는 멤버 함수개체에 대 한 포인터를 보유 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>요구 사항

**헤더:** 모듈.h

**네임스페이스:** Microsoft::WRL

## <a name="modulemethodreleasenotifierinvoke"></a><a name="methodreleasenotifier-invoke"></a>모듈:::방법 해제 공보::호출

현재 `Module::MethodReleaseNotifier` 개체와 연결된 이벤트 처리기를 호출합니다.

```cpp
void Invoke();
```

## <a name="modulemethodreleasenotifiermethod_"></a><a name="methodreleasenotifier-method"></a>모듈:::방법 릴리스공교자::method_

현재 `Module::MethodReleaseNotifier` 개체에 대 한 이벤트 처리기에 대 한 포인터를 보유 합니다.

```cpp
void (T::* method_)();
```

## <a name="modulemethodreleasenotifiermethodreleasenotifier"></a><a name="methodreleasenotifier-methodreleasenotifier"></a>모듈:::방법 릴리스 공고자::방법 릴리스

`Module::MethodReleaseNotifier` 클래스의 새 인스턴스를 초기화합니다.

```cpp
MethodReleaseNotifier(
   _In_ T* object,
   _In_ void (T::* method)(),
   bool release) throw() :
            ReleaseNotifier(release), object_(object),
            method_(method);
```

### <a name="parameters"></a>매개 변수

*개체*<br/>
멤버 함수가 이벤트 처리기인 개체입니다.

*메서드*<br/>
이벤트 처리기인 매개 변수 *개체의* 멤버 함수입니다.

*릴리스*<br/>
기본 `true` [모듈::ReleaseNotifier::Release()](module-releasenotifier-class.md#releasenotifier-release) 메서드를 호출하도록 지정합니다. 그렇지 않으면 `false`을 지정합니다.

## <a name="modulemethodreleasenotifierobject_"></a><a name="methodreleasenotifier-object"></a>모듈:::방법 릴리스 공고자::object_

현재 `Module::MethodReleaseNotifier` 개체에 대 한 이벤트 처리기는 멤버 함수개체에 대 한 포인터를 보유 합니다.

```cpp
T* object_;
```
