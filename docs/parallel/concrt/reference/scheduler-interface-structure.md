---
title: scheduler_interface 구조체
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: 36feff80cab1c5d301c009a581b869d5c2bad5e9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142146"
---
# <a name="scheduler_interface-structure"></a>scheduler_interface 구조체

Scheduler 인터페이스

## <a name="syntax"></a>구문

```cpp
struct __declspec(novtable) scheduler_interface;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[scheduler_interface:: schedule](#schedule)||

## <a name="inheritance-hierarchy"></a>상속 계층

`scheduler_interface`

## <a name="requirements"></a>요구 사항

**헤더:** pplinterface.h

**네임스페이스:** 동시성

## <a name="schedule"></a>scheduler_interface:: schedule 메서드

```cpp
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)
