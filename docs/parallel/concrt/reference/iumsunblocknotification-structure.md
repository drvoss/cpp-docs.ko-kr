---
title: IUMSUnblockNotification 구조체
ms.date: 11/04/2016
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
ms.openlocfilehash: d4fd95b1f11ed6edac26cb03e41e8b650acfafa3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139977"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification 구조체

차단되었으며 스케줄러의 지정된 일정 컨텍스트로의 반환을 트리거한 스레드 프록시가 차단 해제되고 예약할 준비가 되었다는 리소스 관리자의 알림을 나타냅니다. `GetContext` 메서드에서 반환된 스레드 프록시의 연결된 실행 컨텍스트가 다시 예약된 후에는 이 인터페이스가 유효하지 않습니다.

## <a name="syntax"></a>구문

```cpp
struct IUMSUnblockNotification;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[IUMSUnblockNotification:: GetContext](#getcontext)|차단 해제 된 스레드 프록시와 연결 된 실행 컨텍스트에 대 한 `IExecutionContext` 인터페이스를 반환 합니다. 이 메서드가 반환 되 고 `IThreadProxy::SwitchTo` 메서드에 대 한 호출을 통해 기본 실행 컨텍스트가 다시 예약 되 면이 인터페이스는 더 이상 유효 하지 않습니다.|
|[IUMSUnblockNotification:: GetNextUnblockNotification](#getnextunblocknotification)|`IUMSCompletionList::GetUnblockNotifications`메서드에서 반환 된 체인의 다음 `IUMSUnblockNotification` 인터페이스를 반환 합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`IUMSUnblockNotification`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm. h

**네임스페이스:** 동시성

## <a name="getcontext"></a>IUMSUnblockNotification:: GetContext 메서드

차단 해제 된 스레드 프록시와 연결 된 실행 컨텍스트에 대 한 `IExecutionContext` 인터페이스를 반환 합니다. 이 메서드가 반환 되 고 `IThreadProxy::SwitchTo` 메서드에 대 한 호출을 통해 기본 실행 컨텍스트가 다시 예약 되 면이 인터페이스는 더 이상 유효 하지 않습니다.

```cpp
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>Return Value

차단 해제 된 스레드 프록시에 대 한 실행 컨텍스트에 대 한 `IExecutionContext` 인터페이스입니다.

## <a name="getnextunblocknotification"></a>IUMSUnblockNotification:: GetNextUnblockNotification 메서드

`IUMSCompletionList::GetUnblockNotifications`메서드에서 반환 된 체인의 다음 `IUMSUnblockNotification` 인터페이스를 반환 합니다.

```cpp
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>Return Value

메서드에서 반환 된 체인의 다음 `IUMSUnblockNotification` 인터페이스 `IUMSCompletionList::GetUnblockNotifications`입니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[IUMSScheduler 구조체](iumsscheduler-structure.md)<br/>
[IUMSCompletionList 구조체](iumscompletionlist-structure.md)
