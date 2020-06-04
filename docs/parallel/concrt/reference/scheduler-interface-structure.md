---
title: scheduler_interface 구조체
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: da2ebc2f9c2878baefcfa792bac08f420dbbb281
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358780"
---
# <a name="scheduler_interface-structure"></a>scheduler_interface 구조체

Scheduler 인터페이스

## <a name="syntax"></a>구문

```cpp
struct __declspec(novtable) scheduler_interface;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[scheduler_interface::일정](#schedule)||

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`scheduler_interface`

## <a name="requirements"></a>요구 사항

**헤더:** pplinterface.h

**네임스페이스:** 동시성

## <a name="scheduler_interfaceschedule-method"></a><a name="schedule"></a>scheduler_interface::일정 방법

```cpp
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)
