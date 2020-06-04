---
title: IUMSCompletionList 구조체
ms.date: 11/04/2016
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
ms.openlocfilehash: c388cc98aedbd35b2d0e00a4653a85a47abcb838
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368116"
---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList 구조체

UMS 완성 목록을 나타냅니다. UMS 스레드가 차단되는 경우 원래 스레드가 차단되는 동안 기본 가상 프로세서 루트에 예약할 항목을 결정하기 위해 스케줄러의 지정된 일정 컨텍스트가 디스패치됩니다. 원래 스레드가 차단 해제되면 운영 체제에서 이 인터페이스를 통해 액세스할 수 있는 완성 목록에 대기시킵니다. 스케줄러는 지정된 일정 컨텍스트 또는 작업을 검색하는 다른 위치에 있는 완성 목록을 쿼리할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
struct IUMSCompletionList;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IUMS완성 목록::GetUn블록 알림](#getunblocknotifications)|이 메서드가 `IUMSUnblockNotification` 마지막으로 호출된 이후 연결된 스레드 프록시가 차단 해제된 실행 컨텍스트를 나타내는 인터페이스 체인을 검색합니다.|

## <a name="remarks"></a>설명

스케줄러는 이 인터페이스를 사용하여 완료 목록에서 항목을 큐에 넣은 후 수행되는 작업에 대해 매우 주의해야 합니다. 항목은 스케줄러의 실행 가능한 컨텍스트 목록에 배치해야 하며 일반적으로 가능한 한 빨리 액세스할 수 있어야 합니다. 큐에 추가된 항목 중 하나에 임의 잠금의 소유권이 부여되었을 수 있습니다. 스케줄러는 항목을 큐 제거하기 위한 호출과 일반적으로 스케줄러 내에서 액세스할 수 있는 목록에 해당 항목의 배치 사이에서 차단할 수 있는 임의의 함수 호출을 만들 수 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IUMSCompletionList`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="iumscompletionlistgetunblocknotifications-method"></a><a name="getunblocknotifications"></a>IUMS완성 목록::GetUnblockNotifications 방법

이 메서드가 `IUMSUnblockNotification` 마지막으로 호출된 이후 연결된 스레드 프록시가 차단 해제된 실행 컨텍스트를 나타내는 인터페이스 체인을 검색합니다.

```cpp
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>Return Value

인터페이스 체인입니다. `IUMSUnblockNotification`

### <a name="remarks"></a>설명

실행 컨텍스트가 다시 예약되면 반환된 알림이 유효하지 않습니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)<br/>
[IUMSScheduler 구조체](iumsscheduler-structure.md)<br/>
[IUMSUnblockNotification 구조체](iumsunblocknotification-structure.md)
