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
ms.openlocfilehash: 0b88ddd4184e982a5e07c536efc301eaa16f4a41
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368067"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification 구조체

차단되었으며 스케줄러의 지정된 일정 컨텍스트로의 반환을 트리거한 스레드 프록시가 차단 해제되고 예약할 준비가 되었다는 리소스 관리자의 알림을 나타냅니다. `GetContext` 메서드에서 반환된 스레드 프록시의 연결된 실행 컨텍스트가 다시 예약된 후에는 이 인터페이스가 유효하지 않습니다.

## <a name="syntax"></a>구문

```cpp
struct IUMSUnblockNotification;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IUMSUn차단 알림::GetContext](#getcontext)|차단 `IExecutionContext` 해제된 스레드 프록시와 연결된 실행 컨텍스트에 대한 인터페이스를 반환합니다. 메서드에 대 `IThreadProxy::SwitchTo` 한 호출을 통해 이 메서드가 반환 되 고 기본 실행 컨텍스트를 다시 예약 하면 이 인터페이스는 더 이상 유효 하지 않습니다.|
|[IUMSUn차단 알림::GetNextUn차단 알림](#getnextunblocknotification)|메서드에서 `IUMSCompletionList::GetUnblockNotifications` `IUMSUnblockNotification` 반환된 체인의 다음 인터페이스를 반환합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IUMSUnblockNotification`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="iumsunblocknotificationgetcontext-method"></a><a name="getcontext"></a>IUMSUn차단 알림::GetContext 방법

차단 `IExecutionContext` 해제된 스레드 프록시와 연결된 실행 컨텍스트에 대한 인터페이스를 반환합니다. 메서드에 대 `IThreadProxy::SwitchTo` 한 호출을 통해 이 메서드가 반환 되 고 기본 실행 컨텍스트를 다시 예약 하면 이 인터페이스는 더 이상 유효 하지 않습니다.

```cpp
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>Return Value

차단이 해제된 스레드 프록시에 대한 실행 컨텍스트에 대한 `IExecutionContext` 인터페이스입니다.

## <a name="iumsunblocknotificationgetnextunblocknotification-method"></a><a name="getnextunblocknotification"></a>IUMSUn차단 알림::GetNextUn블록 알림 방법

메서드에서 `IUMSCompletionList::GetUnblockNotifications` `IUMSUnblockNotification` 반환된 체인의 다음 인터페이스를 반환합니다.

```cpp
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>Return Value

체인의 `IUMSUnblockNotification` 다음 인터페이스는 메서드에서 `IUMSCompletionList::GetUnblockNotifications`반환됩니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)<br/>
[IUMSScheduler 구조체](iumsscheduler-structure.md)<br/>
[IUMSCompletionList 구조체](iumscompletionlist-structure.md)
