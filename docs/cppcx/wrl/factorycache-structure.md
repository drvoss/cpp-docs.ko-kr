---
title: FactoryCache 구조체
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
- module/Microsoft::WRL::Details::FactoryCache::cookie
- module/Microsoft::WRL::Details::FactoryCache::factory
helpviewer_keywords:
- Microsoft::WRL::Details::FactoryCache structure
- Microsoft::WRL::Details::FactoryCache::cookie data member
- Microsoft::WRL::Details::FactoryCache::factory data member
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
ms.openlocfilehash: 507d35179b9fa86399e56b18171800f41eaf1f10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371501"
---
# <a name="factorycache-structure"></a>FactoryCache 구조체

Windows 런타임 C++ 템플릿 라이브러리 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>설명

클래스 팩터리의 위치와 등록된 wrt 또는 COM 클래스 개체를 식별하는 값을 포함합니다.

## <a name="members"></a>멤버

### <a name="public-data-members"></a>공용 데이터 멤버

속성                              | Description
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[팩토리 캐시 :: 쿠키](#cookie)   | 등록된 Windows 런타임 또는 COM 클래스 개체를 식별하고 나중에 개체를 등록 취소하는 데 사용되는 값을 포함합니다.
[팩토리 캐시 :: 공장](#factory) | Windows 런타임 또는 COM 클래스 팩터리를 가리킵니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`FactoryCache`

## <a name="requirements"></a>요구 사항

**헤더:** 모듈.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="factorycachecookie"></a><a name="cookie"></a>팩토리 캐시 :: 쿠키

Windows 런타임 C++ 템플릿 라이브러리 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>설명

등록된 Windows 런타임 또는 COM 클래스 개체를 식별하고 나중에 개체를 등록 취소하는 데 사용되는 값을 포함합니다.

## <a name="factorycachefactory"></a><a name="factory"></a>팩토리 캐시 :: 공장

Windows 런타임 C++ 템플릿 라이브러리 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>설명

Windows 런타임 또는 COM 클래스 팩터리를 가리킵니다.
