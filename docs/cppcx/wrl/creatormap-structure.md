---
title: CreatorMap 구조체
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
- module/Microsoft::WRL::Details::CreatorMap::activationId
- module/Microsoft::WRL::Details::CreatorMap::factoryCache
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
- module/Microsoft::WRL::Details::CreatorMap::serverName
helpviewer_keywords:
- Microsoft::WRL::Details::CreatorMap structure
- Microsoft::WRL::Details::CreatorMap::activationId data member
- Microsoft::WRL::Details::CreatorMap::factoryCache data member
- Microsoft::WRL::Details::CreatorMap::factoryCreator data member
- Microsoft::WRL::Details::CreatorMap::serverName data member
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
ms.openlocfilehash: 1527f81694d1d809d585f3f6504c0e6433a2c26b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372608"
---
# <a name="creatormap-structure"></a>CreatorMap 구조체

Windows 런타임 C++ 템플릿 라이브러리 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>설명

개체를 초기화, 등록 및 등록 취소하는 방법에 대한 정보가 포함되어 있습니다.

`CreatorMap`에는 다음 정보가 포함되어 있습니다.

- 개체를 초기화, 등록 및 등록 취소하는 방법

- 클래식 COM 또는 Windows 런타임 팩터리에 따라 정품 인증 데이터를 비교하는 방법.

- 인터페이스의 팩터리 캐시 및 서버 이름에 대한 정보입니다.

## <a name="members"></a>멤버

### <a name="public-data-members"></a>공용 데이터 멤버

속성                                          | Description
--------------------------------------------- | ------------------------------------------------------------------------------------------------------
[크리에이터 맵:::활성화Id](#activationid)     | 클래식 COM 클래스 ID 또는 Windows 런타임 이름으로 식별되는 개체 ID를 나타냅니다.
[크리에이터맵:::팩토리캐시](#factorycache)     | 에 대한 팩터리 캐시에 `CreatorMap`포인터를 저장합니다.
[크리에이터맵:::팩토리 크리에이터](#factorycreator) | 지정된 `CreatorMap`에 대한 팩터리를 만듭니다.
[크리에이터 맵:::서버이름](#servername)         | 에 대한 서버 `CreatorMap`이름을 저장합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CreatorMap`

## <a name="requirements"></a>요구 사항

**헤더:** 모듈.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="creatormapactivationid"></a><a name="activationid"></a>크리에이터 맵:::활성화Id

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
union {
   const IID* clsid;
   const wchar_t* (*getRuntimeName)();
} activationId;
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
인터페이스 ID입니다.

*getRuntimeName*<br/>
개체의 Windows 런타임 이름을 검색하는 함수입니다.

### <a name="remarks"></a>설명

클래식 COM 클래스 ID 또는 Windows 런타임 이름으로 식별되는 개체 ID를 나타냅니다.

## <a name="creatormapfactorycache"></a><a name="factorycache"></a>크리에이터맵:::팩토리캐시

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>설명

에 대한 팩터리 캐시에 `CreatorMap`포인터를 저장합니다.

## <a name="creatormapfactorycreator"></a><a name="factorycreator"></a>크리에이터맵:::팩토리 크리에이터

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
IUnknown** factory);
```

### <a name="parameters"></a>매개 변수

*현재 플래그*<br/>
[런타임클래스유형](runtimeclasstype-enumeration.md) 열거식 중 하나입니다.

*항목*<br/>
크리에이터맵.

*아이드클래스팩토리*<br/>
클래스 팩터리의 인터페이스 ID입니다.

*공장*<br/>
작업이 완료되면 클래스 팩터리의 주소입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

지정된 CreatorMap에 대한 팩터리를 만듭니다.

## <a name="creatormapservername"></a><a name="servername"></a>크리에이터 맵:::서버이름

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>설명

크리에이터맵의 서버 이름을 저장합니다.
