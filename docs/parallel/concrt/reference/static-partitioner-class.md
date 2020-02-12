---
title: static_partitioner 클래스
ms.date: 11/04/2016
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
ms.openlocfilehash: 7a58daa27bc7a2f51f78a3068a2f152979ffdd72
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142688"
---
# <a name="static_partitioner-class"></a>static_partitioner 클래스

`static_partitioner` 클래스는 `parallel_for`에서 반복하는 범위의 정적 분할을 나타냅니다. 파티 셔 너는 기본 스케줄러에서 사용할 수 있는 작업자의 수 만큼의 청크로 범위를 나눕니다.

## <a name="syntax"></a>구문

```cpp
class static_partitioner;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[static_partitioner](#ctor)|`static_partitioner` 개체를 생성합니다.|
|[~ static_partitioner 소멸자](#dtor)|`static_partitioner` 개체를 제거합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`static_partitioner`

## <a name="requirements"></a>요구 사항

**헤더:** ppl. h

**네임스페이스:** 동시성

## <a name="dtor"></a>~ static_partitioner

`static_partitioner` 개체를 제거합니다.

```cpp
~static_partitioner();
```

## <a name="ctor"></a>static_partitioner

`static_partitioner` 개체를 생성합니다.

```cpp
static_partitioner();
```

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)
