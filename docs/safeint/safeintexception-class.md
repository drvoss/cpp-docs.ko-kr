---
title: SafeIntException 클래스
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeIntException Class
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
helpviewer_keywords:
- SafeIntException class
- SafeIntException, constructor
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
ms.openlocfilehash: e118d7e3cce47ebb93cef16319a8fc45aab1118b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349949"
---
# <a name="safeintexception-class"></a>SafeIntException 클래스

`SafeInt` 클래스는 `SafeIntException`을 사용하여 수학 연산을 완료할 수 없는 이유를 확인합니다.

> [!NOTE]
> 이 라이브러리의 최신 버전은 [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt)에 있습니다.

## <a name="syntax"></a>구문

```cpp
class SafeIntException;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                                    | Description
------------------------------------------------------- | ------------------------------------
[세이프인트예외::세이프인트예외](#safeintexception) | `SafeIntException` 개체를 만듭니다.

## <a name="remarks"></a>설명

[SafeInt 클래스](../safeint/safeint-class.md)는 `SafeIntException` 클래스를 사용하는 유일한 클래스입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`SafeIntException`

## <a name="requirements"></a>요구 사항

**헤더:** safeint.h

**네임스페이스:** msl::utilities

## <a name="safeintexceptionsafeintexception"></a><a name="safeintexception"></a>세이프인트예외::세이프인트예외

`SafeIntException` 개체를 만듭니다.

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>매개 변수

*코드*<br/>
[in] 발생한 오류를 설명하는 열거형 데이터 값입니다.

### <a name="remarks"></a>설명

가능한 *code* 값은 Safeint.h 파일에서 정의됩니다. 편의를 위해 여기에도 가능한 값이 나와 있습니다.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`
