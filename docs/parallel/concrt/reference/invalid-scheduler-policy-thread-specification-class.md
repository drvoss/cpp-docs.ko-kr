---
title: invalid_scheduler_policy_thread_specification 클래스
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
ms.openlocfilehash: b6c2fd853ae19c48ae04d6601eb47e5afcb71944
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143032"
---
# <a name="invalid_scheduler_policy_thread_specification-class"></a>invalid_scheduler_policy_thread_specification 클래스

이 클래스는 `SchedulerPolicy` 키의 값이 `MinConcurrency` 키의 값보다 작도록 `MaxConcurrency` 개체의 동시성 제한을 설정하려고 시도하는 경우 발생하는 예외를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class invalid_scheduler_policy_thread_specification : public std::exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-value-class.md#ctor|오버로드됨. `invalid_scheduler_policy_value` 개체를 생성합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`exception`

`invalid_scheduler_policy_thread_specification`

## <a name="requirements"></a>요구 사항

**헤더:** concrt .h

**네임스페이스:** 동시성

## <a name="ctor"></a>invalid_scheduler_policy_thread_specification

`invalid_scheduler_policy_value` 개체를 생성합니다.

```cpp
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류 설명 메시지입니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[SchedulerPolicy 클래스](schedulerpolicy-class.md)
