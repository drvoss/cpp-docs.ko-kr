---
title: HANDLETraits 구조체
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue method
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
ms.openlocfilehash: 604098cd3289722767117910d6e44e272dcb8b77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371442"
---
# <a name="handletraits-structure"></a>HANDLETraits 구조체

핸들의 일반적인 특성을 정의합니다.

## <a name="syntax"></a>구문

```cpp
struct HANDLETraits;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성   | Description
------ | ---------------------
`Type` | 핸들의 동의어입니다.

### <a name="public-methods"></a>Public 메서드

속성                                              | Description
------------------------------------------------- | -----------------------------
[핸들 해협::닫기](#close)                     | 지정된 핸들을 닫습니다.
[핸들 해협::GetInvalid값](#getinvalidvalue) | 잘못된 핸들을 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HANDLETraits`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼::핸들 트레이츠

## <a name="handletraitsclose"></a><a name="close"></a>핸들 해협::닫기

지정된 핸들을 닫습니다.

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
핸들을 닫습니다.

### <a name="return-value"></a>Return Value

핸들 *h가* 성공적으로 닫힌 경우 **true;** 그렇지 **않으면, 거짓**.

## <a name="handletraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>핸들 해협::GetInvalid값

잘못된 핸들을 나타냅니다.

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>Return Value

항상 INVALID_HANDLE_VALUE 반환합니다. (INVALID_HANDLE_VALUE Windows에서 정의합니다.)
