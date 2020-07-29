---
title: HANDLENullTraits 구조체
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue method
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
ms.openlocfilehash: a7ce730b8d723a839c5b509c825cff84111ca613
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226921"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits 구조체

초기화 되지 않은 핸들의 공통 특성을 정의 합니다.

## <a name="syntax"></a>구문

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

Name   | 설명
------ | ---------------------
`Type` | 핸들의 동의어입니다.

### <a name="public-methods"></a>Public 메서드

이름                                                  | 설명
----------------------------------------------------- | -----------------------------
[HANDLENullTraits:: Close](#close)                     | 지정 된 핸들을 닫습니다.
[HANDLENullTraits:: GetInvalidValue](#getinvalidvalue) | 는 잘못 된 핸들을 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HANDLENullTraits`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임 스페이스:** Microsoft:: WRL:: 래퍼:: 핸드

## <a name="handlenulltraitsclose"></a><a name="close"></a>HANDLENullTraits:: Close

지정 된 핸들을 닫습니다.

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
닫을 핸들입니다.

### <a name="return-value"></a>Return Value

**`true`***핸들을* 성공적으로 닫았습니다. 그렇지 않으면 **`false`** 입니다.

## <a name="handlenulltraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>HANDLENullTraits:: GetInvalidValue

는 잘못 된 핸들을 나타냅니다.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Return Value

항상 **`nullptr`** 를 반환 합니다.
