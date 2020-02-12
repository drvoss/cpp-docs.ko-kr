---
title: invalid_scheduler_policy_key 클래스
ms.date: 11/04/2016
f1_keywords:
- invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key::invalid_scheduler_policy_key
helpviewer_keywords:
- invalid_scheduler_policy_key class
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
ms.openlocfilehash: 60d5a57ff9cb33a3d522c14514f5107844216852
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143018"
---
# <a name="invalid_scheduler_policy_key-class"></a>invalid_scheduler_policy_key 클래스

이 클래스는 잘못되었거나 알 수 없는 키가 `SchedulerPolicy` 개체 생성자에 전달된 경우 또는 `SetPolicyValue` 개체의 `SchedulerPolicy` 메서드에 `SetConcurrencyLimits` 메서드와 같은 기타 방법으로 변경해야 하는 키가 전달된 경우 발생하는 예외를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class invalid_scheduler_policy_key : public std::exception;
```

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[invalid_scheduler_policy_key](#ctor)|오버로드되었습니다. `invalid_scheduler_policy_key` 개체를 생성합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`exception`

`invalid_scheduler_policy_key`

## <a name="requirements"></a>요구 사항

**헤더:** concrt .h

**네임스페이스:** 동시성

## <a name="ctor"></a>invalid_scheduler_policy_key

`invalid_scheduler_policy_key` 개체를 생성합니다.

```cpp
explicit _CRTIMP invalid_scheduler_policy_key(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_key() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류 설명 메시지입니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[SchedulerPolicy 클래스](schedulerpolicy-class.md)
