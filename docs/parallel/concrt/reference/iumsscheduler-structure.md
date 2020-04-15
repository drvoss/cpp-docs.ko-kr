---
title: IUMSScheduler 구조체
ms.date: 11/04/2016
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
ms.openlocfilehash: 70954906122c048e5199a801632626d35a8e3f18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368092"
---
# <a name="iumsscheduler-structure"></a>IUMSScheduler 구조체

동시성 런타임의 리소스 관리자를 통해 UMS(사용자 모드 예약 가능) 스레드를 전달하려는 작업 스케줄러의 추상화에 대한 인터페이스입니다. 리소스 관리자는 이 인터페이스를 사용하여 UMS 스레드 스케줄러와 통신합니다. `IUMSScheduler` 인터페이스는 `IScheduler` 인터페이스에서 상속됩니다.

## <a name="syntax"></a>구문

```cpp
struct IUMSScheduler : public IScheduler;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IUMS스케줄러::세트 완성목록](#setcompletionlist)|UMS `IUMSCompletionList` 스레드 스케줄러에 인터페이스를 할당합니다.|

## <a name="remarks"></a>설명

리소스 관리자와 통신하는 사용자 지정 스케줄러를 구현하고 UMS 스레드를 일반 Win32 스레드 대신 스케줄러에 전달하려는 경우 `IUMSScheduler` 인터페이스의 구현을 제공해야 합니다. 또한 스케줄러 정책 키에 `SchedulerKind` 대한 정책 값을 `UmsThreadDefault`로 설정해야 합니다. 정책이 UMS 스레드를 지정하는 `IScheduler` 경우 [IResourceManager::RegisterScheduler](iresourcemanager-structure.md#registerscheduler) 메서드에 매개 변수로 전달되는 `IUMSScheduler` 인터페이스는 인터페이스여야 합니다.

리소스 관리자는 UMS 기능이 있는 운영 체제에서만 UMS 스레드를 전달할 수 있습니다. 버전 윈도우 7 이상 지원 UMS 스레드와 64 비트 운영 체제. 키를 `SchedulerKind` `UmsThreadDefault` 값으로 설정하고 기본 플랫폼이 UMS를 지원하지 않는 스케줄러 정책을 만들면 `SchedulerKind` 해당 정책의 키 값이 값으로 `ThreadScheduler`변경됩니다. UMS 스레드를 받기 전에 항상 이 정책 값을 다시 읽어야 합니다.

인터페이스는 `IUMSScheduler` 스케줄러와 리소스 관리자 간의 양방향 통신 채널의 한쪽 끝입니다. 다른 쪽 끝은 `IResourceManager` 리소스 `ISchedulerProxy` 관리자에 의해 구현 되는 및 인터페이스에 의해 표현 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[Ischeduler](ischeduler-structure.md)

`IUMSScheduler`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="iumsschedulersetcompletionlist-method"></a><a name="setcompletionlist"></a>IUMS스케줄러::설정완성리스트 방법

UMS `IUMSCompletionList` 스레드 스케줄러에 인터페이스를 할당합니다.

```cpp
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```

### <a name="parameters"></a>매개 변수

*p완성 목록*<br/>
스케줄러의 완료 목록 인터페이스입니다. 스케줄러당 단일 목록이 있습니다.

### <a name="remarks"></a>설명

리소스 관리자는 스케줄러가 리소스의 초기 할당을 요청한 후 UMS 스레드를 원하는 지 지정하는 스케줄러에서 이 메서드를 호출합니다. 스케줄러는 인터페이스를 `IUMSCompletionList` 사용하여 UMS 스레드 프록시가 차단 해제된 시기를 확인할 수 있습니다. UMS 스케줄러에 할당된 가상 프로세서 루트에서 실행되는 스레드 프록시에서 이 인터페이스에 액세스하는 경우에만 유효합니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)<br/>
[정책요소키](concurrency-namespace-enums.md)<br/>
[IScheduler 구조체](ischeduler-structure.md)<br/>
[IUMSCompletionList 구조체](iumscompletionlist-structure.md)<br/>
[IResourceManager 구조체](iresourcemanager-structure.md)
